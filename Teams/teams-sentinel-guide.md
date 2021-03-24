---
title: Azure Sentinel и Microsoft Teams
author: MicrosoftHeidi
ms.author: tracyp
manager: dansimp
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Советы по безопасности и учебные материалы для ИТ-администраторов по использованию Sentinel для отслеживания и обнаружения угроз, которые могут возникать в Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 320accf1e0588024e72d69dcbb4af45c0a6765eb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098185"
---
# <a name="azure-sentinel-and-microsoft-teams"></a><span data-ttu-id="9f438-103">Azure Sentinel и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9f438-103">Azure Sentinel and Microsoft Teams</span></span>

<span data-ttu-id="9f438-104">Teams играет центральную роль как во взаимодействии, так и в распространении данных в облаке Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9f438-104">Teams serves a central role in both communication and data sharing in the Microsoft 365 Cloud.</span></span> <span data-ttu-id="9f438-105">Так как служба Teams связана со многими базовыми технологиями в облаке, она может использовать преимущества человеческого и автоматизированного анализа не только при *поиске в журналах*, но и при *отслеживании собраний в реальном времени*.</span><span class="sxs-lookup"><span data-stu-id="9f438-105">Because the Teams service touches on so many underlying technologies in the Cloud, it can benefit from human and automated analysis not only when it comes to *hunting in logs*, but also in *real-time monitoring of meetings*.</span></span> <span data-ttu-id="9f438-106">Azure Sentinel предлагает эти решения администраторам.</span><span class="sxs-lookup"><span data-stu-id="9f438-106">Azure Sentinel offers admins these solutions.</span></span>

> [!NOTE]
> <span data-ttu-id="9f438-107">Требуется освежить знания по Azure Sentinel?</span><span class="sxs-lookup"><span data-stu-id="9f438-107">Need a refresher on Azure Sentinel?</span></span> <span data-ttu-id="9f438-108">[Эта статья](/azure/sentinel/overview) как раз для этого.</span><span class="sxs-lookup"><span data-stu-id="9f438-108">[This article](/azure/sentinel/overview) is just the thing.</span></span>

## <a name="sentinel-and-microsoft-teams-activity-logs"></a><span data-ttu-id="9f438-109">Sentinel и журналы действий Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9f438-109">Sentinel and Microsoft Teams Activity Logs</span></span>

<span data-ttu-id="9f438-110">В этой статье рассматривается сбор журналов действий Teams в Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="9f438-110">This article focuses on collecting Teams activity logs in Azure Sentinel.</span></span> <span data-ttu-id="9f438-111">Помимо предоставления администраторам возможности управления безопасностью в одном месте (включая любые выбранные сторонние устройства, Защиту от угроз (Майкрософт) и другие рабочие нагрузки Microsoft 365), книги Sentinel и runbook позволяют систематизировать мониторинг безопасности.</span><span class="sxs-lookup"><span data-stu-id="9f438-111">Aside from allowing administrators to put security management under one pane of glass (including any selected 3rd party devices, Microsoft Threat Protection, and other Microsoft 365 Workloads), Sentinel workbooks, and runbooks can make security monitoring systematic.</span></span> <span data-ttu-id="9f438-112">Хорошим первым шагом в этом процессе является сбор необходимых журналов для анализа.</span><span class="sxs-lookup"><span data-stu-id="9f438-112">A good first step in this process is collecting the needed logs for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="9f438-113">В одном экземпляре Azure Sentinel можно использовать несколько подписок на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9f438-113">More than one Microsoft 365 subscription can be surfaced in the same instance of Azure Sentinel.</span></span> <span data-ttu-id="9f438-114">Это позволит выполнять [отслеживание в реальном времени](/azure/sentinel/livestream) и обнаруживать угрозы в архивных файлах журнала.</span><span class="sxs-lookup"><span data-stu-id="9f438-114">This will allow for [realtime monitoring](/azure/sentinel/livestream) and hunting for threats in historical log file s.</span></span> <span data-ttu-id="9f438-115">Администраторы смогут выполнять поиск, используя [запросы в разных ресурсах](/azure/azure-monitor/log-query/cross-workspace-query), в одной группе ресурсов, в разных группах ресурсов или в другой подписке.</span><span class="sxs-lookup"><span data-stu-id="9f438-115">Administrators will be able to hunt using [cross-resource queries](/azure/azure-monitor/log-query/cross-workspace-query), that is within a single resource group, across resource groups, or in another subscription.</span></span>

## <a name="step-1-collect-teams-logs"></a><span data-ttu-id="9f438-116">Шаг 1. Сбор журналов Teams</span><span class="sxs-lookup"><span data-stu-id="9f438-116">Step 1: Collect Teams logs</span></span>

<span data-ttu-id="9f438-117">Этот раздел состоит из трех частей:</span><span class="sxs-lookup"><span data-stu-id="9f438-117">This section has three parts:</span></span>

1. <span data-ttu-id="9f438-118">Включение журналов аудита в **Microsoft 365** (M365).</span><span class="sxs-lookup"><span data-stu-id="9f438-118">Enabling Audit Logs in **Microsoft 365** (M365).</span></span>
2. <span data-ttu-id="9f438-119">Регистрация приложения в **Microsoft Azure**, чтобы разрешить проверку подлинности и авторизацию для сбора журналов.</span><span class="sxs-lookup"><span data-stu-id="9f438-119">Registering an App in **Microsoft Azure** to permit authentication and authorization for log collection.</span></span>
3. <span data-ttu-id="9f438-120">Регистрация подписки на API, которая позволит осуществлять сбор журналов через API M365 посредством **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="9f438-120">Registering the API subscription that will allow log collection via M365 API via **PowerShell**.</span></span>

### <a name="enable-audit-logs-in-m365"></a><span data-ttu-id="9f438-121">Включение журналов аудита в M365</span><span class="sxs-lookup"><span data-stu-id="9f438-121">Enable Audit logs in M365</span></span>

<span data-ttu-id="9f438-122">Так как Teams регистрирует действия через M365, журналы аудита не собираются по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9f438-122">Because Teams logs activity through M365, audit logs aren't collected by default.</span></span> <span data-ttu-id="9f438-123">Включите эту функцию с помощью [этих действий](/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%c2%a0).</span><span class="sxs-lookup"><span data-stu-id="9f438-123">Turn on this feature via [these steps](/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%c2%a0).</span></span> <span data-ttu-id="9f438-124">Данные Teams собираются для аудита M365 в разделе *Audit.General*.</span><span class="sxs-lookup"><span data-stu-id="9f438-124">Teams data is collected in the M365 audit under *Audit.General*.</span></span>

### <a name="register-an-app-in-microsoft-azure-for-log-collection"></a><span data-ttu-id="9f438-125">Регистрация приложения в Microsoft Azure для сбора журналов</span><span class="sxs-lookup"><span data-stu-id="9f438-125">Register an App in Microsoft Azure for log collection</span></span>

> [!TIP]
> <span data-ttu-id="9f438-126">Перед началом вам потребуется записать ваш **идентификатор приложения/идентификатор клиента** и **идентификатор клиента** для использования в дальнейшем.</span><span class="sxs-lookup"><span data-stu-id="9f438-126">Before you begin, you will need to record you **Application ID / Client ID**, and your **Tenant ID** for later use.</span></span> <span data-ttu-id="9f438-127">Запишите их при выполнении действий регистрации приложения ниже.</span><span class="sxs-lookup"><span data-stu-id="9f438-127">Be sure to capture them as you walk through app registration steps below.</span></span> <span data-ttu-id="9f438-128">Вы увидите оба идентификатора.</span><span class="sxs-lookup"><span data-stu-id="9f438-128">You will see both IDs.</span></span>
>- <span data-ttu-id="9f438-129">После создания приложения щелкните "Регистрация приложений" на боковой панели быстрого запуска, найдите отображаемое имя вашего нового приложения и скопируйте идентификатор приложения (клиент).</span><span class="sxs-lookup"><span data-stu-id="9f438-129">After your app is created, click App Registration on the quick launch side-bar > Find your new app's display name > copy the Application (client) ID.</span></span>
>- <span data-ttu-id="9f438-130">Щелкните "Обзор" на боковой панели быстрого запуска и скопируйте идентификатор каталога (клиент).</span><span class="sxs-lookup"><span data-stu-id="9f438-130">Click Overview on the quick launch side-bar > copy the Directory (tenant) ID.</span></span>

<span data-ttu-id="9f438-131">Проверьте подлинность и авторизуйте приложение Azure Active Directory (Azure AD) для сбора данных журналов из API.</span><span class="sxs-lookup"><span data-stu-id="9f438-131">Authenticate and authorize an Azure Active Directory (Azure AD) app to collect log data from the API.</span></span>

1. <span data-ttu-id="9f438-132">Перейдите в колонку *Azure AD* на портале Azure.</span><span class="sxs-lookup"><span data-stu-id="9f438-132">Navigate to your *Azure AD* blade in the Azure portal.</span></span>
2. <span data-ttu-id="9f438-133">На боковой панели быстрого запуска щелкните *Регистрация приложений*.</span><span class="sxs-lookup"><span data-stu-id="9f438-133">Click on *App registrations* in the quick launch side-bar.</span></span>
3. <span data-ttu-id="9f438-134">Выберите *Новая регистрация*.</span><span class="sxs-lookup"><span data-stu-id="9f438-134">Select *New registration*.</span></span>
4. <span data-ttu-id="9f438-135">Назовите свое приложение для сбора журналов Teams и нажмите *Зарегистрировать*.</span><span class="sxs-lookup"><span data-stu-id="9f438-135">Name your Teams log collecting app and click *Register*.</span></span>
5. <span data-ttu-id="9f438-136">Последовательно выберите *Разрешения API* > *Добавить разрешение* > *Office 365 Management APIs* > *Разрешения приложения*.</span><span class="sxs-lookup"><span data-stu-id="9f438-136">Click along this path: *API Permissions* > *Add a permission* > *Office 365 Management APIs* > *Application permissions*.</span></span>
6. <span data-ttu-id="9f438-137">Разверните раздел "Веб-канал активности" и установите флажок *ActivityFeed.Read*.</span><span class="sxs-lookup"><span data-stu-id="9f438-137">Expand Activity Feed and check *ActivityFeed.Read*.</span></span>
7. <span data-ttu-id="9f438-138">Выберите здесь *Предоставить согласие администратора*.</span><span class="sxs-lookup"><span data-stu-id="9f438-138">Choose *Grand admin consent* here.</span></span> <span data-ttu-id="9f438-139">Щелкните "Да" при появлении запроса на подтверждение.</span><span class="sxs-lookup"><span data-stu-id="9f438-139">Click Yes when prompted asking if you mean it.</span></span>
8. <span data-ttu-id="9f438-140">Щелкните *Сертификаты и секреты* на боковой панели и нажмите кнопку *Новый секрет клиента*.</span><span class="sxs-lookup"><span data-stu-id="9f438-140">Click *Certificates and Secrets* in the side-bar> *New client secret* button.</span></span>
9. <span data-ttu-id="9f438-141">В окне "Добавить секрет клиента" введите описание нового секрета клиента, выберите "Никогда" для истечения срока действия и нажмите *Добавить*.</span><span class="sxs-lookup"><span data-stu-id="9f438-141">On the New client secret window, enter a description for the new Client Secret, make sure you choose 'Never' for Expiration, and click *Add*.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9f438-142">**Очень важно** скопировать новый секрет клиента в запись диспетчера паролей под именем созданного приложения.</span><span class="sxs-lookup"><span data-stu-id="9f438-142">It's **critical** to copy the new client secret into a password manager entry that goes under the name of the newly created app.</span></span> <span data-ttu-id="9f438-143">Вы не сможете вернуться для просмотра этого секрета после закрытия колонки Azure (*колонка* — это термин Azure, обозначающий окно).</span><span class="sxs-lookup"><span data-stu-id="9f438-143">You won't be able to get back to look at this secret after the closing out of the Azure blade (*blade* being the Azure term for window).</span></span>

### <a name="register-the-api-with-powershell-to-collect-teams-logs"></a><span data-ttu-id="9f438-144">Регистрация API с помощью PowerShell для сбора журналов Teams</span><span class="sxs-lookup"><span data-stu-id="9f438-144">Register the API with PowerShell to collect Teams logs</span></span>

<span data-ttu-id="9f438-145">Завершающее действие настройки — получение и регистрация подписки на API, чтобы можно было собирать данные журналов.</span><span class="sxs-lookup"><span data-stu-id="9f438-145">The final step in setup is to collect and register the API subscription so that you can collect your log data.</span></span> <span data-ttu-id="9f438-146">Это выполняется с помощью вызовов REST PowerShell в API действий управления M365.</span><span class="sxs-lookup"><span data-stu-id="9f438-146">This is done via PowerShell REST calls to the M365 Management Activity API.</span></span>

<span data-ttu-id="9f438-147">Будьте готовы указать значения **идентификатора приложения (клиент)**, нового **секрета клиента**, вашего **домена URL-адреса для M365** и **идентификатора каталога (клиент)** в командлете PowerShell ниже.</span><span class="sxs-lookup"><span data-stu-id="9f438-147">Be ready to supply **Application (client) ID**, the new **Client Secret**, your **URL domain for M365**, and **Directory (tenant) ID** values in the PowerShell cmdlet below.</span></span>

```PowerShell
$ClientID = "<Application (client) ID>"  
$ClientSecret = "<Client secret>"  
$loginURL = "https://login.microsoftonline.com/"  
$tenantdomain = "<domain>.onmicrosoft.com"  

$TenantGUID = "<Directory (tenant) ID>"  
$resource = "https://manage.office.com"  
$body = @{grant_type="client_credentials";resource=$resource;client_id=$ClientID;client_secret=$ClientSecret}
$oauth = Invoke-RestMethod -Method Post -Uri $loginURL/$tenantdomain/oauth2/token?api-version=1.0 -Body $body  
$headerParams = @{'Authorization'="$($oauth.token_type) $($oauth.access_token)"}
$publisher = New-Guid
Invoke-WebRequest -Method Post -Headers $headerParams -Uri "https://manage.office.com/api/v1.0/$tenantGuid/activity/feed/subscriptions/start?contentType=Audit.General&PublisherIdentifier=$Publisher"
```

## <a name="step-2-deploy-a-sentinel-playbook-to-ingest-the-teams-logs"></a><span data-ttu-id="9f438-148">Шаг 2. Развертывание сборника схем Sentinel для приема журналов Teams</span><span class="sxs-lookup"><span data-stu-id="9f438-148">Step 2: Deploy a Sentinel Playbook to ingest the Teams logs</span></span>

<span data-ttu-id="9f438-149">Сборники схем Azure Sentinel (также называемые приложениями логики) позволяют Azure принимать ваши собранные данные Teams.</span><span class="sxs-lookup"><span data-stu-id="9f438-149">Azure Sentinel Playbooks (also called Logic Apps) will allow Azure to ingest your collected Teams data.</span></span> <span data-ttu-id="9f438-150">Приложение логики опрашивает Office 365, чтобы найти данные аудита, записываемые в рабочую область Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="9f438-150">The Logic App queries Office 365 to find the audit data it writes into the Azure Sentinel workspace.</span></span>

<span data-ttu-id="9f438-151">Используйте [этот](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) шаблон ARM, чтобы развернуть сборник схем Sentinel.</span><span class="sxs-lookup"><span data-stu-id="9f438-151">Use [this](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) ARM template to deploy your Sentinel Playbook.</span></span>

<span data-ttu-id="9f438-152">Вот о чем нужно помнить:</span><span class="sxs-lookup"><span data-stu-id="9f438-152">Things to remember:</span></span>

1. <span data-ttu-id="9f438-153">Вам потребуется просмотреть шаблон ARM и определенные значения заменить значениями, соответствующими вашей среде.</span><span class="sxs-lookup"><span data-stu-id="9f438-153">You will need to walk through the ARM template and replace certain of the values with values appropriate for your own environment.</span></span>
2. <span data-ttu-id="9f438-154">Вам требуется предусмотреть время между приемом журналов и просмотром результатов в Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="9f438-154">You will need to allow time between the ingestion of logs and looking at the results in Azure Sentinel.</span></span>

   <span data-ttu-id="9f438-155">Подождите 5–10 минут, учитывая, что если в течение последних 5 минут данные отсутствуют, отобразится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="9f438-155">Wait for 5 to 10 minutes, understanding that if there is no data within the past 5 minutes you will see an error message.</span></span> <span data-ttu-id="9f438-156">Проверьте журналы аудита и имейте в виду, что в используемых системах результаты должны отображаться в течение 5–10 минут, так как сведения Teams находятся в событиях Audit.General, собирающих больше данных, чем журналы Teams.</span><span class="sxs-lookup"><span data-stu-id="9f438-156">Check Audit logs and keep in mind that because Teams information is in the Audit.General events, which collects more than Teams logs, results should appear within 5 to 10 minutes on systems that are in use.</span></span> <span data-ttu-id="9f438-157">При использовании текстовой среды обязательно применяйте Teams, чтобы создавать журналы.</span><span class="sxs-lookup"><span data-stu-id="9f438-157">If using a text environment, be certain to use Teams in order to generate logging.</span></span>

![Рисунок с классами приложений логики.](media/tracyp-teams-sentinel-logic-app.png#thumbnail)

 <p><details><summary> <span data-ttu-id="9f438-159">Объяснение действий на рисунке:</span><span class="sxs-lookup"><span data-stu-id="9f438-159">Explanation of actions in the graphic:</span></span> 
  </summary>

  <span data-ttu-id="9f438-160">• Повторение — это триггер приложения логики, указывающий рабочему процессу необходимость запуска каждый час.</span><span class="sxs-lookup"><span data-stu-id="9f438-160">• Recurrence is the Logic App Trigger that tells the workflow to run every hour.</span></span>
  <p>
<span data-ttu-id="9f438-161">• Действие "Текущее время" очень простое и заключается в получении текущего времени.</span><span class="sxs-lookup"><span data-stu-id="9f438-161">• The Current Time action is very basic and just gets the current time.</span></span>
  <p>
<span data-ttu-id="9f438-162">• Инициализация переменной создает переменную NextPage и присваивает ей значение 1.</span><span class="sxs-lookup"><span data-stu-id="9f438-162">• Initialize Variable creates a variable called NextPage and sets it to 1.</span></span> <span data-ttu-id="9f438-163">Это будет применено позже, чтобы обработать разбивку на страницы из API Office 365.</span><span class="sxs-lookup"><span data-stu-id="9f438-163">This will be used later in order to handle pagination from the O365 API.</span></span>
  <p>
<span data-ttu-id="9f438-164">• Инициализация переменной 2 создает пустую переменную "Start Time".</span><span class="sxs-lookup"><span data-stu-id="9f438-164">• Initialize Variable 2 creates an empty variable called Start Time.</span></span>
  <p>
<span data-ttu-id="9f438-165">• Выполнение запроса и перечисление результатов — это действие Azure Monitor, запрашивающее в рабочей области последний журнал O365, введенный из приложения логики.</span><span class="sxs-lookup"><span data-stu-id="9f438-165">• Run Query and list results is an Azure Monitor action that will query the workspace for the last O365 log that was entered from the Logic App.</span></span>
  <p>
<span data-ttu-id="9f438-166">• Условие 4 используется, чтобы проверить, возвратил ли запрос "Выполнение запроса и перечисление результатов" какие-либо данные.</span><span class="sxs-lookup"><span data-stu-id="9f438-166">• Condition 4 is used to check whether the Run Query and list results query returned any data.</span></span> <span data-ttu-id="9f438-167">Это выполняется, чтобы проверить, впервые ли использовано приложение логики.</span><span class="sxs-lookup"><span data-stu-id="9f438-167">This is done to check if this is the very first time the Logic App has been used.</span></span> <span data-ttu-id="9f438-168">Если данные не возвращаются, переменной StartTime присваивается значение Now — 24 часа.</span><span class="sxs-lookup"><span data-stu-id="9f438-168">If no data is returned, StartTime variable is set to Now – 24 hours.</span></span> <span data-ttu-id="9f438-169">Если данные возвращаются, переменной StartTime присваивается значение последней записи TimeGenerated.</span><span class="sxs-lookup"><span data-stu-id="9f438-169">If data is returned, StartTime is set to the last record TimeGenerated.</span></span> <span data-ttu-id="9f438-170">Это делается для того, чтобы запрос мог получить данные от последней записи до текущего момента в опросе API Office 365 или за последние 24 часа, если это первый запуск.</span><span class="sxs-lookup"><span data-stu-id="9f438-170">This is done so that the query can get data from the last entry till now in the poll against the O365 API, or in the last 24 hours if this is the first run.</span></span>
  <p>
<span data-ttu-id="9f438-171">• Инициализация переменной 3 создает переменную AvailableUri.</span><span class="sxs-lookup"><span data-stu-id="9f438-171">• Initialize Variable 3 creates a variable called AvailableUri.</span></span> <span data-ttu-id="9f438-172">Это строка с URL-адресом, созданная с использованием StartTime и CurrentTime в качестве времени начала и окончания соответственно.</span><span class="sxs-lookup"><span data-stu-id="9f438-172">This is a string with the URL built using the StartTime and CurrentTime as start and end times, respectively.</span></span>
  <p>
<span data-ttu-id="9f438-173">• Условие Until — это цикл, позволяющий приложению логики продолжать опрашивать API, чтобы проверять наличие дополнительных данных (разбивка на страницы).</span><span class="sxs-lookup"><span data-stu-id="9f438-173">• The Until condition is a loop that allows the logic app to keep polling the API to see if there is more data (pagination).</span></span> <span data-ttu-id="9f438-174">Пока переменная NextPage имеет значение 1, цикл продолжается.</span><span class="sxs-lookup"><span data-stu-id="9f438-174">As long as NextPage variable is 1 the loop will continue.</span></span> <span data-ttu-id="9f438-175">Позже эта переменная будет обновлена, если закончатся страницы для получения.</span><span class="sxs-lookup"><span data-stu-id="9f438-175">Later this variable will be updated if there are no more pages left to retrieve.</span></span>
  <p>
<span data-ttu-id="9f438-176">• В цикле Until первый шаг HTTP подключается к AvailableURI.</span><span class="sxs-lookup"><span data-stu-id="9f438-176">• Inside the Until loop, the first HTTP step Connects to the AvailableURI.</span></span> <span data-ttu-id="9f438-177">Этот URI возвращает список доступного содержимого и URI каждого элемента содержимого.</span><span class="sxs-lookup"><span data-stu-id="9f438-177">This URI returns a list of available content and each contents URI.</span></span> <span data-ttu-id="9f438-178">Дополнительные сведения об этих принципах работы см. по URL-адресу https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span><span class="sxs-lookup"><span data-stu-id="9f438-178">There's more on how this works at this URL: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span></span>
  <p>
<span data-ttu-id="9f438-179">• Далее выполняется проверка, чтобы убедиться в возвращении данных.</span><span class="sxs-lookup"><span data-stu-id="9f438-179">• Next a check is run to make sure data is returned.</span></span> <span data-ttu-id="9f438-180">Условие проверяет, равна ли длина текста 0.</span><span class="sxs-lookup"><span data-stu-id="9f438-180">The Condition checks if the length of the body is 0.</span></span> <span data-ttu-id="9f438-181">Если это так, данные для записи в аналитику журнала отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="9f438-181">If so there is no data to write to Log Analytics.</span></span> <span data-ttu-id="9f438-182">Если значение больше 0, существуют данные для обработки.</span><span class="sxs-lookup"><span data-stu-id="9f438-182">If the value is greater than 0, there is data to process.</span></span>
  <p>
<span data-ttu-id="9f438-183">• Если данные обнаружены, их требуется обработать.</span><span class="sxs-lookup"><span data-stu-id="9f438-183">• If data is detected, it must next be processed.</span></span> <span data-ttu-id="9f438-184">Анализ JSON определяет схему возвращаемых данных.</span><span class="sxs-lookup"><span data-stu-id="9f438-184">Parse JSON defines a schema of the returned data.</span></span> <span data-ttu-id="9f438-185">Это позволяет приложениям логики использовать проанализированные данные в качестве динамического контента в последующих действиях.</span><span class="sxs-lookup"><span data-stu-id="9f438-185">This allows logic apps to use the parsed data as Dynamic content in later steps.</span></span>
  <p>
<span data-ttu-id="9f438-186">• Так как возвращаемый список доступных данных является массивом, используется действие For Each для циклического перебора списка доступных элементов содержимого.</span><span class="sxs-lookup"><span data-stu-id="9f438-186">• Since the returned list of available data is an Array, a For Each action is used to loop through the list of available content.</span></span>
  <p>
<span data-ttu-id="9f438-187">• Затем захватывается содержимое.</span><span class="sxs-lookup"><span data-stu-id="9f438-187">• Next is grabbing the content.</span></span>  <span data-ttu-id="9f438-188">Вновь используется параметр HTTP для получения contentUri (динамическое свойство, созданное из анализа JSON), являющегося URL-адресом получаемых данных.</span><span class="sxs-lookup"><span data-stu-id="9f438-188">HTTP is used again to get the contentUri (a dynamic property created from Parse JSON), which is the URL of the data to retrieve.</span></span>
  <p>
<span data-ttu-id="9f438-189">• Анализ JSON также используется для синтаксического анализа возвращаемых данных.</span><span class="sxs-lookup"><span data-stu-id="9f438-189">• Parse JSON is also used to parse the returned data.</span></span> <span data-ttu-id="9f438-190">Некоторые примеры содержимого доступны по URL-адресу https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span><span class="sxs-lookup"><span data-stu-id="9f438-190">You can find some sample content at this URL: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span></span>
  <p>
<span data-ttu-id="9f438-191">• Возвращаемые данные также являются массивом.</span><span class="sxs-lookup"><span data-stu-id="9f438-191">• The data returned is also an array.</span></span> <span data-ttu-id="9f438-192">Здесь также можно использовать цикл For Each.</span><span class="sxs-lookup"><span data-stu-id="9f438-192">A For Each loop can be used here as well.</span></span> <span data-ttu-id="9f438-193">В этом цикле рабочий процесс получает текущий элемент данных и использует действие Send Data для записи данных в аналитику журнала.</span><span class="sxs-lookup"><span data-stu-id="9f438-193">In this loop, the workflow takes the current item of data and uses the Send Data action to write the data to Log Analytics.</span></span>
  <p>
<span data-ttu-id="9f438-194">• Так как в доступном содержимом может быть несколько страниц, условие проверяет, что параметру NextPageUri не присвоено значение NULL.</span><span class="sxs-lookup"><span data-stu-id="9f438-194">• Since there may be multiple pages of available content, a condition checks if the NextPageUri is not NULL.</span></span> <span data-ttu-id="9f438-195">Если он имеет значение NULL, параметру NextPage присваивается значение 0, что завершает цикл Until.</span><span class="sxs-lookup"><span data-stu-id="9f438-195">If it is NULL, or empty, NextPage is set to 0, which ends the Until loop.</span></span> <span data-ttu-id="9f438-196">Если в нем есть URL-адрес, переменная AvaibleUri обновляется с использованием этого URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="9f438-196">If it contains a URL, the AvaibleUri variable is updated to that URL.</span></span> <span data-ttu-id="9f438-197">В этом случае при следующем запуске цикла Until используется следующий доступный URL-адрес, а не начальный URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="9f438-197">This way, the next run of the Until loop uses a next available URL, and not the starting URL.</span></span>

  </details>

> [!TIP]
> <span data-ttu-id="9f438-198">Вместо этого вы можете использовать *функцию Azure*, чтобы принять эти журналы. В этом случае см. сведения о развертывании [здесь](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20Data) или [здесь](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20DataCSharp) в зависимости от предпочтений.</span><span class="sxs-lookup"><span data-stu-id="9f438-198">You may choose to use an *Azure Function* to ingest those logs, instead, and if you do, the information on how to deploy is [here](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20Data), or [here](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20DataCSharp), depending on your preference.</span></span>

<span data-ttu-id="9f438-199">При запущенном соединителе (независимо от выбранных выше вариантов) вы должны увидеть настраиваемую таблицу O365API_CL в рабочей области Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="9f438-199">With the connector (whichever of the options above you chose) running, you should see a custom table called O365API_CL in the Azure Sentinel workspace.</span></span> <span data-ttu-id="9f438-200">В ней размещаются ваши журналы Teams.</span><span class="sxs-lookup"><span data-stu-id="9f438-200">This will house your Teams logs.</span></span>

## <a name="step-3-use-sentinel-to-monitor-microsoft-teams"></a><span data-ttu-id="9f438-201">Шаг 3. Использование Sentinel для мониторинга Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9f438-201">Step 3: Use Sentinel to monitor Microsoft Teams</span></span>

<span data-ttu-id="9f438-202">Удостоверение — это важный для отслеживания вектор атаки, связанный с Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9f438-202">Identity is an important attack vector to monitor when it comes to Microsoft Teams.</span></span> <span data-ttu-id="9f438-203">Так как Azure Active Directory (Azure AD) — это основа каталога Microsoft 365, включая Teams, сбор и поиск в журналах Azure AD угроз, связанных с проверкой подлинности, облегчает выявление подозрительных действий в отношении удостоверений.</span><span class="sxs-lookup"><span data-stu-id="9f438-203">Because Azure Active Directory (Azure AD) is the underpinning of Microsoft 365's directory, including Teams, collecting and hunting for threats in Azure AD logs around authentication will be useful in capturing suspicious behavior around identity.</span></span> <span data-ttu-id="9f438-204">Вы можете использовать встроенный соединитель для извлечения данных Azure AD в Azure Sentinel, а также использовать эти запросы [обнаружения](https://github.com/Azure/Azure-Sentinel/tree/master/Detections/SigninLogs) и [поиска](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/SigninLogs) для выявления проблем.</span><span class="sxs-lookup"><span data-stu-id="9f438-204">You can use the built-in connector to pull Azure AD data into Azure Sentinel, and use these [detection](https://github.com/Azure/Azure-Sentinel/tree/master/Detections/SigninLogs) and [hunting](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/SigninLogs) queries to look for problems.</span></span>

<span data-ttu-id="9f438-205">В отношении специфичных для Microsoft Teams атак, например угроз для данных, в Azure Sentinel также имеются средства для их отслеживания и поиска.</span><span class="sxs-lookup"><span data-stu-id="9f438-205">Regarding attacks specific to Microsoft Teams, threats to data, for example, Azure Sentinel also has means to monitor for them and hunt them down.</span></span>

### <a name="create-a-parser-for-your-data"></a><span data-ttu-id="9f438-206">Создание средства синтаксического анализа для данных</span><span class="sxs-lookup"><span data-stu-id="9f438-206">Create a parser for your data</span></span>

<span data-ttu-id="9f438-207">Первое, что нужно сделать, чтобы разобраться в большом наборе собранных данных, — понять их значение с помощью синтаксического анализа.</span><span class="sxs-lookup"><span data-stu-id="9f438-207">The first thing to do in order to make sense of the large set of collected data is to give it meaning by parsing it.</span></span> <span data-ttu-id="9f438-208">Это осуществляется с помощью функции языка запросов Kusto (KQL), упрощающей работу с данными.</span><span class="sxs-lookup"><span data-stu-id="9f438-208">This is done with a Kusto Query Language (KQL) Function that makes the data easier to use.</span></span>

> [!NOTE]
> <span data-ttu-id="9f438-209">Функции KQL — это запросы KQL, сохраненные в виде данных под названием "функция".</span><span class="sxs-lookup"><span data-stu-id="9f438-209">KQL functions are KQL queries saved as a data-type called 'function'.</span></span> <span data-ttu-id="9f438-210">Функции KQL содержат псевдоним, который можно ввести в поле запроса в Sentinel, чтобы быстро повторить запрос.</span><span class="sxs-lookup"><span data-stu-id="9f438-210">KQL functions have an alias that can be entered into the query box in Sentinel to quickly run the query again.</span></span> <span data-ttu-id="9f438-211">Дополнительные сведения о функциях KQL и создании функции синтаксического анализа см. в [этой статье сообщества Tech Community](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span><span class="sxs-lookup"><span data-stu-id="9f438-211">For more about KQL functions and how to build a parser function, read [this Tech Community article](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span></span>
 
 <span data-ttu-id="9f438-212">Средство синтаксического анализа ниже — это настраиваемый пример, предназначенный для выбора подмножества полей API управления Office 365, относящихся к *Teams*.</span><span class="sxs-lookup"><span data-stu-id="9f438-212">The parser below is a customizable example aimed at selecting a subset of the Office 365 Management API fields relevant to *Teams*.</span></span> <span data-ttu-id="9f438-213">Также существует предлагаемое средство синтаксического анализа [GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt), но в примере ниже можно вносить изменения для соблюдения различных потребностей и предпочтений.</span><span class="sxs-lookup"><span data-stu-id="9f438-213">There is also a suggested parser [GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt), but the parser below can be modified to fit different needs and preferences.</span></span>

```kusto
O365API_CL
| where Workload_s =~ "MicrosoftTeams"
| project TimeGenerated,
          Workload=Workload_s,
          Operation=Operation_s,
          TeamName=columnifexists('TeamName_s', ""),
          UserId=columnifexists('UserId_s', ""),
          AddOnName=columnifexists('AddOnName_s', AddOnGuid_g),
          Members=columnifexists('Members_s', ""),
          Settings=iif(Operation_s contains "Setting", pack("Name", columnifexists('Name_s', ""), "Old Value", columnifexists('OldValue_s', ""), "New Value", columnifexists('NewValue_s', "")),""),
          Details=pack("Id", columnifexists('Id_g', ""),  "OrganizationId", columnifexists('OrganizationId_g', ""), "UserType", columnifexists('UserType_d', ""), "UserKey", columnifexists('UserKey_g', ""), "TeamGuid", columnifexists('TeamGuid_s', "")) 
```
 <span data-ttu-id="9f438-214">Сохраните средство синтаксического анализа как функцию KQL с псевдонимом TeamsData.</span><span class="sxs-lookup"><span data-stu-id="9f438-214">Save the parser as a KQL function, with an alias of TeamsData.</span></span> <span data-ttu-id="9f438-215">Она будет использоваться в последующих запросах.</span><span class="sxs-lookup"><span data-stu-id="9f438-215">It will be used for the queries to follow.</span></span> <span data-ttu-id="9f438-216">Сведения о настройке и использовании функции KQL в качестве средства синтаксического анализа, можно найти в этой [статье сообщества Tech Community](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span><span class="sxs-lookup"><span data-stu-id="9f438-216">Details on configuring and using a KQL function as a parser can be found in this [Tech Community article](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span></span>

## <a name="helpful-hunting-kql-queries"></a><span data-ttu-id="9f438-217">Полезные запросы KQL для поиска</span><span class="sxs-lookup"><span data-stu-id="9f438-217">Helpful hunting KQL queries</span></span>

<span data-ttu-id="9f438-218">Используйте эти запросы, чтобы познакомиться с данными и средой Teams.</span><span class="sxs-lookup"><span data-stu-id="9f438-218">Use these queries to familiarize yourself with your Teams data and Teams environment.</span></span> <span data-ttu-id="9f438-219">Понимание среды и ее поведения — это отличный первый шаг по выявлению подозрительных действий.</span><span class="sxs-lookup"><span data-stu-id="9f438-219">Knowing how the environment should look and behave is a good first step in recognizing suspicious activity.</span></span> <span data-ttu-id="9f438-220">После этого вы можете перейти к поиску угроз.</span><span class="sxs-lookup"><span data-stu-id="9f438-220">From there, you can branch out into threat hunting.</span></span>

#### <a name="federated-external-users-query"></a><span data-ttu-id="9f438-221">Запросы федеративных внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="9f438-221">Federated external users query</span></span>

<span data-ttu-id="9f438-222">Получите список сайтов Teams с федеративными внешними пользователями.</span><span class="sxs-lookup"><span data-stu-id="9f438-222">Get the list of Teams sites that have federated external users.</span></span> <span data-ttu-id="9f438-223">У этих пользователей будет доменное имя или суффикс UPN, *не* принадлежащие вашей организации.</span><span class="sxs-lookup"><span data-stu-id="9f438-223">These users will have a domain name / UPN suffix that *isn't* owned by your organization.</span></span> <span data-ttu-id="9f438-224">В этом примере запроса организации принадлежит домен contoso.com.</span><span class="sxs-lookup"><span data-stu-id="9f438-224">In this example query, the organization owns contoso.com.</span></span>

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| extend UPN = tostring(parse_json(Members)[0].Upn)
| where UPN !endswith "contoso.com"
| where parse_json(Members)[0].Role == 3
| project TeamName, Operation, UserId, Members, UPN
```

> [!TIP]
> <span data-ttu-id="9f438-225">Дополнительные сведения о внешнем и гостевом типах доступа в Teams см. в [этой статье](./communicate-with-users-from-other-organizations.md) или в разделе *Типы участников* в [руководстве по безопасности Teams](./teams-security-guide.md).</span><span class="sxs-lookup"><span data-stu-id="9f438-225">To learn more about External and Guest access types in Teams see [this article](./communicate-with-users-from-other-organizations.md), or the *Participant Types* section in the [Teams Security Guide](./teams-security-guide.md).</span></span>

#### <a name="who-recently-joined--whose-role-changed"></a><span data-ttu-id="9f438-226">Кто недавно присоединился или чья роль изменена</span><span class="sxs-lookup"><span data-stu-id="9f438-226">Who recently joined / Whose role changed</span></span>

<span data-ttu-id="9f438-227">Запросите определенного пользователя, чтобы проверить, был ли он добавлен в канал Teams за последние 7 дней или в течение недели:</span><span class="sxs-lookup"><span data-stu-id="9f438-227">Query a specific user to check if they were added to a Teams channel in the last 7 days, or within a week:</span></span>

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members contains "UserName"
```

<span data-ttu-id="9f438-228">Изменилась ли роль пользователя в команде за последние 7 дней:</span><span class="sxs-lookup"><span data-stu-id="9f438-228">Was a user's role changed for a Team in the last 7 days:</span></span>

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| where Members contains "Role" and Members contains "1"
```

#### <a name="external-users-from-unknown-or-new-organizations"></a><span data-ttu-id="9f438-229">Внешние пользователи из неизвестных или новых организаций</span><span class="sxs-lookup"><span data-stu-id="9f438-229">External users from unknown or new organizations</span></span>

<span data-ttu-id="9f438-230">В Teams вы можете добавлять внешних пользователей в среду или каналы.</span><span class="sxs-lookup"><span data-stu-id="9f438-230">In Teams, you can add external users to your environment or channels.</span></span> <span data-ttu-id="9f438-231">Организации часто имеют ограниченное количество ключевых партнеров и добавляют пользователей этих партнеров.</span><span class="sxs-lookup"><span data-stu-id="9f438-231">Organizations often have a limited number of key partnerships and add users from among these partners.</span></span> <span data-ttu-id="9f438-232">Эта функция KQL ищет добавленных в команды внешних пользователей из организаций, которые раньше отсутствовали или не добавлялись.</span><span class="sxs-lookup"><span data-stu-id="9f438-232">This KQL looks at external users added to teams who come from organizations that haven't been seen or added before.</span></span>

```kusto
// If you have more than 14 days worth of Teams data change this value 
let data_date = 14d; 
// If you want to look at users further back than the last day change this value 
let lookback_data = 1d; 
let known_orgs = ( 
TeamsData  
| where TimeGenerated > ago(data_date) 
| where Operation =~ "MemberAdded" or Operation =~ "TeamsSessionStarted" 
// Extract the correct UPN and parse our external organization domain 
| extend UPN = iif(Operation == "MemberAdded", tostring(parse_json(Members)[0].UPN), UserId) 
| extend Organization = tostring(split(split(UPN, "_")[1], "#")[0]) 
| where isnotempty(Organization) 
| summarize by Organization); 
TeamsData  
| where TimeGenerated > ago(lookback_data) 
| where Operation =~ "MemberAdded" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| extend Organization = tostring(split(split(UPN, "_")[1], "#")[0]) 
| where isnotempty(Organization) 
| where Organization !in (known_orgs) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = UPN 
```

#### <a name="external-users-who-were-added-and-then-removed"></a><span data-ttu-id="9f438-233">Внешние пользователи, которые были добавлены, а затем удалены</span><span class="sxs-lookup"><span data-stu-id="9f438-233">External users who were added and then removed</span></span>

<span data-ttu-id="9f438-234">Злоумышленники с определенным уровнем доступа могут добавить новую внешнюю учетную запись в Teams, чтобы получить доступ и извлечь данные.</span><span class="sxs-lookup"><span data-stu-id="9f438-234">Attackers with some level of existing access may add a new external account to Teams to access and exfiltrate data.</span></span> <span data-ttu-id="9f438-235">Они также могут быстро удалить этого пользователя, чтобы скрыть получение доступа.</span><span class="sxs-lookup"><span data-stu-id="9f438-235">They may also quickly remove that user to hide that they made access.</span></span> <span data-ttu-id="9f438-236">Этот запрос используется для поиска внешних учетных записей, которые добавлены в Teams и быстро удалены, чтобы выявить подозрительное поведение.</span><span class="sxs-lookup"><span data-stu-id="9f438-236">This query hunts for external accounts that are added to Teams and swiftly removed to help identify suspicious behavior.</span></span>

```kusto
// If you want to look at user added further than 7 days ago adjust this value 
let time_ago = 7d; 
// If you want to change the timeframe of how quickly accounts need to be added and removed change this value 
let time_delta = 1h; 
TeamsData  
| where TimeGenerated > ago(time_ago) 
| where Operation =~ "MemberAdded" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| project TimeAdded=TimeGenerated, Operation, UPN, UserWhoAdded = UserId, TeamName, TeamGuid = tostring(Details.TeamGuid) 
| join ( 
TeamsData  
| where TimeGenerated > ago(time_ago) 
| where Operation =~ "MemberRemoved" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| project TimeDeleted=TimeGenerated, Operation, UPN, UserWhoDeleted = UserId, TeamName, TeamGuid = tostring(Details.TeamGuid)) on UPN, TeamGuid 
| where TimeDeleted < (TimeAdded + time_delta) 
| project TimeAdded, TimeDeleted, UPN, UserWhoAdded, UserWhoDeleted, TeamName, TeamGuid 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeAdded, AccountCustomEntity = UPN 
```

#### <a name="new-bot-or-application-added"></a><span data-ttu-id="9f438-237">Добавлен новый бот или приложение</span><span class="sxs-lookup"><span data-stu-id="9f438-237">New bot or application added</span></span>

<span data-ttu-id="9f438-238">В Teams можно добавлять приложения или ботов для команды, чтобы расширить набор функций.</span><span class="sxs-lookup"><span data-stu-id="9f438-238">Teams has the ability to include apps or bots in a Team to extend the feature set.</span></span> <span data-ttu-id="9f438-239">Сюда относятся пользовательские приложения и боты.</span><span class="sxs-lookup"><span data-stu-id="9f438-239">This includes custom apps and bots.</span></span> <span data-ttu-id="9f438-240">В некоторых случаях приложение или бот могут использоваться для создания присутствия в Teams без необходимости пользовательской учетной записи, а также могут обращаться к файлам и другим данным.</span><span class="sxs-lookup"><span data-stu-id="9f438-240">In some cases, an app or bot could be used to establish persistence in Teams without needing a user account, as well as access files and other data.</span></span> <span data-ttu-id="9f438-241">Этот запрос используется для поиска новых приложений и ботов в Teams.</span><span class="sxs-lookup"><span data-stu-id="9f438-241">This query hunts for apps or bots that are new to Teams.</span></span>

```kusto
// If you have more than 14 days worth of Teams data change this value 
let data_date = 14d; 
let historical_bots = ( 
TeamsData 
| where TimeGenerated > ago(data_date) 
| where isnotempty(AddOnName) 
| project AddOnName); 
TeamsData 
| where TimeGenerated > ago(1d) 
// Look for add-ins we have never seen before 
| where AddOnName in (historical_bots) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = UserId 
```

#### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a><span data-ttu-id="9f438-242">Учетные записи пользователей, являющихся владельцами большого количества команд</span><span class="sxs-lookup"><span data-stu-id="9f438-242">User accounts who are Owners of large numbers of Teams</span></span>

<span data-ttu-id="9f438-243">Злоумышленники, пытающиеся получить дополнительные права, могут назначать себе права владельцев большого количества разнообразных команд, а пользователи обычно создают и владеют небольшим количеством команд, посвященных определенным темам.</span><span class="sxs-lookup"><span data-stu-id="9f438-243">Attackers looking to elevate their privileges may assign themselves Owner privileges of a large number of diverse teams, when, usually, users create and own a small number of teams around specific topics.</span></span> <span data-ttu-id="9f438-244">Этот запрос KQL ищет подозрительные действия.</span><span class="sxs-lookup"><span data-stu-id="9f438-244">This KQL query looks for suspicious behavior.</span></span>

```kusto
// Adjust this value to change how many teams a user is made owner of before detecting 
let max_owner_count = 3; 
// Change this value to adjust how larger timeframe the query is run over. 
let time_window = 1d; 
let high_owner_count = (TeamsData 
| where TimeGenerated > ago(time_window) 
| where Operation =~ "MemberRoleChanged" 
| extend Member = tostring(parse_json(Members)[0].UPN)  
| extend NewRole = toint(parse_json(Members)[0].Role)  
| where NewRole == 2 
| summarize dcount(TeamName) by Member 
| where dcount_TeamName > max_owner_count 
| project Member); 
TeamsData 
| where TimeGenerated > ago(time_window) 
| where Operation =~ "MemberRoleChanged" 
| extend Member = tostring(parse_json(Members)[0].UPN)  
| extend NewRole = toint(parse_json(Members)[0].Role)  
| where NewRole == 2 
| where Member in (high_owner_count) 
| extend TeamGuid = tostring(Details.TeamGuid) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = Member 
```

#### <a name="many-team-deletions-by-a-single-user"></a><span data-ttu-id="9f438-245">Удаление большого количества команд одним пользователем</span><span class="sxs-lookup"><span data-stu-id="9f438-245">Many Team deletions by a single user</span></span>

<span data-ttu-id="9f438-246">Злоумышленники могут вызывать нарушения в работе и создавать угрозы проектам и данным, удаляя несколько команд.</span><span class="sxs-lookup"><span data-stu-id="9f438-246">Attackers can cause disruptions and jeopardize projects and data by deleting multiple teams.</span></span> <span data-ttu-id="9f438-247">Так как команды обычно удаляются отдельными владельцами, централизованное удаление нескольких команд может быть признаком проблемы.</span><span class="sxs-lookup"><span data-stu-id="9f438-247">Because teams are generally deleted by individual Owners, a central deletion of many teams can be a sign of trouble.</span></span> <span data-ttu-id="9f438-248">Этот запрос KQL ищет отдельных пользователей, удаляющих несколько команд.</span><span class="sxs-lookup"><span data-stu-id="9f438-248">This KQL looks for single users who delete multiple teams.</span></span>

```kusto
 // Adjust this value to change how many Teams should be deleted before including
 let max_delete = 3;
 // Adjust this value to change the timewindow the query runs over
 let time_window = 1d;
 let deleting_users = (
 TeamsData 
 | where TimeGenerated > ago(time_window)
 | where Operation =~ "TeamDeleted"
 | summarize count() by UserId
 | where count_ > max_delete
 | project UserId);
 TeamsData
 | where TimeGenerated > ago(time_window)
 | where Operation =~ "TeamDeleted"
 | where UserId in (deleting_users)
 | extend TeamGuid = tostring(Details.TeamGuid)
 | project-away AddOnName, Members, Settings
 // Uncomment the following line to map query entities is you plan to use this as a detection query
 //| extend timestamp = TimeGenerated, AccountCustomEntity = UserId
```

#### <a name="expanding-your-thread-hunting-opportunities"></a><span data-ttu-id="9f438-249">Расширение возможностей поиска цепочек</span><span class="sxs-lookup"><span data-stu-id="9f438-249">Expanding your thread hunting opportunities</span></span>

<span data-ttu-id="9f438-250">Вы можете расширить поиск, объединив запросы из таких ресурсов, как Azure Active Directory (Azure AD) или других рабочих нагрузок Office 365, с запросами Teams.</span><span class="sxs-lookup"><span data-stu-id="9f438-250">You can expand your hunting by combining queries from resources like Azure Active Directory (Azure AD), or other Office 365 workloads with your Teams queries.</span></span> <span data-ttu-id="9f438-251">Одним из примеров является объединенное обнаружение подозрительных закономерностей в Azure AD SigninLogs и использование этих сведений при поиске владельцев команд.</span><span class="sxs-lookup"><span data-stu-id="9f438-251">One example is combining detection of suspicious patterns in Azure AD SigninLogs, and using that information while hunting for Team Owners.</span></span>

```kusto
let timeRange = 1d;
let lookBack = 7d;
let threshold_Failed = 5;
let threshold_FailedwithSingleIP = 20;
let threshold_IPAddressCount = 2;
let isGUID = "[0-9a-z]{8}-[0-9a-z]{4}-[0-9a-z]{4}-[0-9a-z]{4}-[0-9a-z]{12}";
let azPortalSignins = SigninLogs
| where TimeGenerated >= ago(timeRange)
// Azure Portal only and exclude non-failure Result Types
| where AppDisplayName has "Azure Portal" and ResultType !in ("0", "50125", "50140")
// Tagging identities not resolved to friendly names
| extend Unresolved = iff(Identity matches regex isGUID, true, false);
// Lookup up resolved identities from last 7 days
let identityLookup = SigninLogs
| where TimeGenerated >= ago(lookBack)
| where not(Identity matches regex isGUID)
| summarize by UserId, lu_UserDisplayName = UserDisplayName, lu_UserPrincipalName = UserPrincipalName;
// Join resolved names to unresolved list from portal signins
let unresolvedNames = azPortalSignins | where Unresolved == true | join kind= inner (
   identityLookup ) on UserId
| extend UserDisplayName = lu_UserDisplayName, UserPrincipalName = lu_UserPrincipalName
| project-away lu_UserDisplayName, lu_UserPrincipalName;
// Join Signins that had resolved names with list of unresolved that now have a resolved name
let u_azPortalSignins = azPortalSignins | where Unresolved == false | union unresolvedNames;
let failed_signins = (u_azPortalSignins
| extend Status = strcat(ResultType, ": ", ResultDescription), OS = tostring(DeviceDetail.operatingSystem), Browser = tostring(DeviceDetail.browser)
| extend FullLocation = strcat(Location,'|', LocationDetails.state, '|', LocationDetails.city)
| summarize TimeGenerated = makelist(TimeGenerated), Status = makelist(Status), IPAddresses = makelist(IPAddress), IPAddressCount = dcount(IPAddress), FailedLogonCount = count()
by UserPrincipalName, UserId, UserDisplayName, AppDisplayName, Browser, OS, FullLocation
| mvexpand TimeGenerated, IPAddresses, Status
| extend TimeGenerated = todatetime(tostring(TimeGenerated)), IPAddress = tostring(IPAddresses), Status = tostring(Status)
| project-away IPAddresses
| summarize StartTime = min(TimeGenerated), EndTime = max(TimeGenerated) by UserPrincipalName, UserId, UserDisplayName, Status, FailedLogonCount, IPAddress, IPAddressCount, AppDisplayName, Browser, OS, FullLocation
| where (IPAddressCount >= threshold_IPAddressCount and FailedLogonCount >= threshold_Failed) or FailedLogonCount >= threshold_FailedwithSingleIP
| project UserPrincipalName);
TeamsData
| where TimeGenerated > ago(time_window)
| where Operation =~ "MemberRoleChanged"
| extend Member = tostring(parse_json(Members)[0].UPN) 
| extend NewRole = toint(parse_json(Members)[0].Role) 
| where NewRole == 2
| where Member in (failed_signins)
| extend TeamGuid = tostring(Details.TeamGuid)
```

<span data-ttu-id="9f438-252">Вы также можете сделать обнаружения SigninLogs специфичными для Teams, добавив фильтр только для входов Teams:</span><span class="sxs-lookup"><span data-stu-id="9f438-252">Also, you can make the SigninLogs detections specific to Teams by adding a filter for only Teams-based sign-ins by using:</span></span>

```kusto
| where AppDisplayName startswith "Microsoft Teams"
```

<span data-ttu-id="9f438-253">Для дополнительного разъяснения использования `where AppDisplayName starts with "Microsoft Teams"` запрос KQL ниже демонстрирует успешный вход с одного IP-адреса и неудачный вход с другого IP-адреса применительно только ко входам Teams:</span><span class="sxs-lookup"><span data-stu-id="9f438-253">To help explain using `where AppDisplayName starts with "Microsoft Teams"` further, the KQL below demonstrates a successful logon from one IP address with failure from a different IP address, but scoped only to Teams sign-ins:</span></span>

```kusto
let timeFrame = 1d;
let logonDiff = 10m;
SigninLogs 
  | where TimeGenerated >= ago(timeFrame) 
  | where ResultType == "0" 
  | where AppDisplayName startswith "Microsoft Teams"
  | project SuccessLogonTime = TimeGenerated, UserPrincipalName, SuccessIPAddress = IPAddress, AppDisplayName, SuccessIPBlock = strcat(split(IPAddress, ".")[0], ".", split(IPAddress, ".")[1])
  | join kind= inner (
      SigninLogs 
      | where TimeGenerated >= ago(timeFrame) 
      | where ResultType !in ("0", "50140") 
      | where ResultDescription !~ "Other"  
      | where AppDisplayName startswith "Microsoft Teams"
      | project FailedLogonTime = TimeGenerated, UserPrincipalName, FailedIPAddress = IPAddress, AppDisplayName, ResultType, ResultDescription
  ) on UserPrincipalName, AppDisplayName 
  | where SuccessLogonTime < FailedLogonTime and FailedLogonTime - SuccessLogonTime <= logonDiff and FailedIPAddress !startswith SuccessIPBlock
  | summarize FailedLogonTime = max(FailedLogonTime), SuccessLogonTime = max(SuccessLogonTime) by UserPrincipalName, SuccessIPAddress, AppDisplayName, FailedIPAddress, ResultType, ResultDescription 
  | extend timestamp = SuccessLogonTime, AccountCustomEntity = UserPrincipalName, IPCustomEntity = SuccessIPAddress
```

## <a name="important-information-and-updates"></a><span data-ttu-id="9f438-254">Важная информация и обновления</span><span class="sxs-lookup"><span data-stu-id="9f438-254">Important information and updates</span></span>

<span data-ttu-id="9f438-255">**Благодарим за совместную работу над контентом Пита Брайана, Николаса Диколу и Мэтью Лоу.**</span><span class="sxs-lookup"><span data-stu-id="9f438-255">**Thank you for content collaboration, Pete Bryan, Nicholas DiCola, and Matthew Lowe.**</span></span> <span data-ttu-id="9f438-256">Пит Брайан и люди, с которыми он совместно работает, продолжат разрабатывать запросы обнаружения и поиска для Teams, поэтому проверяйте обновления в этом репозитории [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs).</span><span class="sxs-lookup"><span data-stu-id="9f438-256">Pete Bryan and the people he collaborates with will continue to develop detection and hunting queries for Teams, so keep in touch with this [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) repository for updates.</span></span>  <span data-ttu-id="9f438-257">Отслеживайте обновления для [средства синтаксического анализа](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) и [приложений логики](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data), использовавшихся в этой статье.</span><span class="sxs-lookup"><span data-stu-id="9f438-257">Monitor for updates to the [parser](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) and [logic app](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) used in this article.</span></span> <span data-ttu-id="9f438-258">Вы также можете присоединиться к [сообществу Azure Sentinel](https://github.com/Azure/Azure-Sentinel/wiki) и участвовать в нем.</span><span class="sxs-lookup"><span data-stu-id="9f438-258">You can also join and contribute to the [Azure Sentinel community](https://github.com/Azure/Azure-Sentinel/wiki).</span></span> <span data-ttu-id="9f438-259">Спасибо!</span><span class="sxs-lookup"><span data-stu-id="9f438-259">Thank you!</span></span> <span data-ttu-id="9f438-260">Удачного поиска.</span><span class="sxs-lookup"><span data-stu-id="9f438-260">Happy hunting.</span></span>

[<span data-ttu-id="9f438-261">Регистрация приложения в Azure AD</span><span class="sxs-lookup"><span data-stu-id="9f438-261">Registering your application in Azure AD</span></span>](/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0)

[<span data-ttu-id="9f438-262">Включение и отключение поиска в журнале аудита</span><span class="sxs-lookup"><span data-stu-id="9f438-262">Turn audit log search on or off</span></span>](/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%c2%a0)

[<span data-ttu-id="9f438-263">Что такое Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="9f438-263">What is Azure Sentinel</span></span>](/azure/sentinel/overview)