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
ms.openlocfilehash: 1075a2c345bd866266b175a4b62432e9f819b330
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598528"
---
# <a name="azure-sentinel-and-microsoft-teams"></a><span data-ttu-id="71326-103">Azure Sentinel и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="71326-103">Azure Sentinel and Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71326-104">Теперь у Azure Sentinel есть интегрированный соединитель.</span><span class="sxs-lookup"><span data-stu-id="71326-104">Azure Sentinel now has an integrated connector.</span></span> <span data-ttu-id="71326-105">Дополнительные сведения см. в статье [Подключение журналов Office 365 к Azure Sentinel](/azure/sentinel/connect-office-365).</span><span class="sxs-lookup"><span data-stu-id="71326-105">For more information, see [Connect Office 365 Logs to Azure Sentinel](/azure/sentinel/connect-office-365).</span></span> <span data-ttu-id="71326-106">Таков рекомендуемый метод для сбора этих журналов; он заменяет собой методы сбора, описанные ниже.</span><span class="sxs-lookup"><span data-stu-id="71326-106">This is the recommended route for collecting these logs and supersedes the collection methods described below.</span></span>

<span data-ttu-id="71326-107">Teams играет центральную роль как во взаимодействии, так и в распространении данных в облаке Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="71326-107">Teams serves a central role in both communication and data sharing in the Microsoft 365 Cloud.</span></span> <span data-ttu-id="71326-108">Так как служба Teams связана со многими базовыми технологиями в облаке, она может использовать преимущества человеческого и автоматизированного анализа не только при *поиске в журналах*, но и при *отслеживании собраний в реальном времени*.</span><span class="sxs-lookup"><span data-stu-id="71326-108">Because the Teams service touches on so many underlying technologies in the Cloud, it can benefit from human and automated analysis not only when it comes to *hunting in logs*, but also in *real-time monitoring of meetings*.</span></span> <span data-ttu-id="71326-109">Azure Sentinel предлагает эти решения администраторам.</span><span class="sxs-lookup"><span data-stu-id="71326-109">Azure Sentinel offers admins these solutions.</span></span>

> [!NOTE]
> <span data-ttu-id="71326-110">Требуется освежить знания по Azure Sentinel?</span><span class="sxs-lookup"><span data-stu-id="71326-110">Need a refresher on Azure Sentinel?</span></span> <span data-ttu-id="71326-111">[Эта статья](/azure/sentinel/overview) как раз для этого.</span><span class="sxs-lookup"><span data-stu-id="71326-111">[This article](/azure/sentinel/overview) is just the thing.</span></span>

## <a name="sentinel-and-microsoft-teams-activity-logs"></a><span data-ttu-id="71326-112">Sentinel и журналы действий Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="71326-112">Sentinel and Microsoft Teams Activity Logs</span></span>

<span data-ttu-id="71326-113">В этой статье рассматривается сбор журналов действий Teams в Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="71326-113">This article focuses on collecting Teams activity logs in Azure Sentinel.</span></span> <span data-ttu-id="71326-114">Помимо предоставления администраторам возможности управления безопасностью в одном месте (включая любые выбранные сторонние устройства, Защиту от угроз (Майкрософт) и другие рабочие нагрузки Microsoft 365), книги Sentinel и runbook позволяют систематизировать мониторинг безопасности.</span><span class="sxs-lookup"><span data-stu-id="71326-114">Aside from allowing administrators to put security management under one pane of glass (including any selected 3rd party devices, Microsoft Threat Protection, and other Microsoft 365 Workloads), Sentinel workbooks, and runbooks can make security monitoring systematic.</span></span> <span data-ttu-id="71326-115">Хорошим первым шагом в этом процессе является сбор необходимых журналов для анализа.</span><span class="sxs-lookup"><span data-stu-id="71326-115">A good first step in this process is collecting the needed logs for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="71326-116">В одном экземпляре Azure Sentinel можно использовать несколько подписок на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="71326-116">More than one Microsoft 365 subscription can be surfaced in the same instance of Azure Sentinel.</span></span> <span data-ttu-id="71326-117">Это позволит выполнять [отслеживание в реальном времени](/azure/sentinel/livestream) и обнаруживать угрозы в архивных файлах журнала.</span><span class="sxs-lookup"><span data-stu-id="71326-117">This will allow for [realtime monitoring](/azure/sentinel/livestream) and hunting for threats in historical log file s.</span></span> <span data-ttu-id="71326-118">Администраторы смогут выполнять поиск, используя [запросы в разных ресурсах](/azure/azure-monitor/log-query/cross-workspace-query), в одной группе ресурсов, в разных группах ресурсов или в другой подписке.</span><span class="sxs-lookup"><span data-stu-id="71326-118">Administrators will be able to hunt using [cross-resource queries](/azure/azure-monitor/log-query/cross-workspace-query), that is within a single resource group, across resource groups, or in another subscription.</span></span>

## <a name="step-1-collect-teams-logs"></a><span data-ttu-id="71326-119">Шаг 1. Сбор журналов Teams</span><span class="sxs-lookup"><span data-stu-id="71326-119">Step 1: Collect Teams logs</span></span>

<span data-ttu-id="71326-120">Этот раздел состоит из трех частей:</span><span class="sxs-lookup"><span data-stu-id="71326-120">This section has three parts:</span></span>

1. <span data-ttu-id="71326-121">Включение журналов аудита в **Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="71326-121">Enabling Audit Logs in **Microsoft 365**.</span></span>
2. <span data-ttu-id="71326-122">Регистрация приложения в **Microsoft Azure**, чтобы разрешить проверку подлинности и авторизацию для сбора журналов.</span><span class="sxs-lookup"><span data-stu-id="71326-122">Registering an App in **Microsoft Azure** to permit authentication and authorization for log collection.</span></span>
3. <span data-ttu-id="71326-123">Регистрация подписки на API, которая позволит осуществлять сбор журналов через API Microsoft 365 с помощью **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="71326-123">Registering the API subscription that will allow log collection via Microsoft 365 API via **PowerShell**.</span></span>

### <a name="enable-audit-logs-in-microsoft-365"></a><span data-ttu-id="71326-124">Включение журналов аудита в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="71326-124">Enable Audit logs in Microsoft 365</span></span>

<span data-ttu-id="71326-125">Так как Teams регистрирует действия через Microsoft 365, журналы аудита не собираются по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="71326-125">Because Teams logs activity through Microsoft 365, audit logs aren't collected by default.</span></span> <span data-ttu-id="71326-126">Эту функцию можно включить, выполнив [следующие шаги](/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%c2%a0).</span><span class="sxs-lookup"><span data-stu-id="71326-126">Turn on this feature via [these steps](/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%c2%a0).</span></span> <span data-ttu-id="71326-127">Данные Teams собираются для аудита Microsoft 365 в разделе *Audit.General*.</span><span class="sxs-lookup"><span data-stu-id="71326-127">Teams data is collected in the Microsoft 365 audit under *Audit.General*.</span></span>

### <a name="register-an-app-in-microsoft-azure-for-log-collection"></a><span data-ttu-id="71326-128">Регистрация приложения в Microsoft Azure для сбора журналов</span><span class="sxs-lookup"><span data-stu-id="71326-128">Register an App in Microsoft Azure for log collection</span></span>

> [!TIP]
> <span data-ttu-id="71326-129">Перед началом вам потребуется записать ваш **идентификатор приложения/идентификатор клиента** и **идентификатор клиента** для использования в дальнейшем.</span><span class="sxs-lookup"><span data-stu-id="71326-129">Before you begin, you will need to record you **Application ID / Client ID**, and your **Tenant ID** for later use.</span></span> <span data-ttu-id="71326-130">Запишите их при выполнении действий регистрации приложения ниже.</span><span class="sxs-lookup"><span data-stu-id="71326-130">Be sure to capture them as you walk through app registration steps below.</span></span> <span data-ttu-id="71326-131">Вы увидите оба идентификатора.</span><span class="sxs-lookup"><span data-stu-id="71326-131">You will see both IDs.</span></span>
>- <span data-ttu-id="71326-132">После создания приложения щелкните "Регистрация приложений" на боковой панели быстрого запуска, найдите отображаемое имя вашего нового приложения и скопируйте идентификатор приложения (клиент).</span><span class="sxs-lookup"><span data-stu-id="71326-132">After your app is created, click App Registration on the quick launch side-bar > Find your new app's display name > copy the Application (client) ID.</span></span>
>- <span data-ttu-id="71326-133">Щелкните "Обзор" на боковой панели быстрого запуска и скопируйте идентификатор каталога (клиент).</span><span class="sxs-lookup"><span data-stu-id="71326-133">Click Overview on the quick launch side-bar > copy the Directory (tenant) ID.</span></span>

<span data-ttu-id="71326-134">Проверьте подлинность и авторизуйте приложение Azure Active Directory (Azure AD) для сбора данных журналов из API.</span><span class="sxs-lookup"><span data-stu-id="71326-134">Authenticate and authorize an Azure Active Directory (Azure AD) app to collect log data from the API.</span></span>

1. <span data-ttu-id="71326-135">Перейдите в колонку *Azure AD* на портале Azure.</span><span class="sxs-lookup"><span data-stu-id="71326-135">Navigate to your *Azure AD* blade in the Azure portal.</span></span>
2. <span data-ttu-id="71326-136">На боковой панели быстрого запуска щелкните *Регистрация приложений*.</span><span class="sxs-lookup"><span data-stu-id="71326-136">Click on *App registrations* in the quick launch side-bar.</span></span>
3. <span data-ttu-id="71326-137">Выберите *Новая регистрация*.</span><span class="sxs-lookup"><span data-stu-id="71326-137">Select *New registration*.</span></span>
4. <span data-ttu-id="71326-138">Назовите свое приложение для сбора журналов Teams и нажмите *Зарегистрировать*.</span><span class="sxs-lookup"><span data-stu-id="71326-138">Name your Teams log collecting app and click *Register*.</span></span>
5. <span data-ttu-id="71326-139">Последовательно выберите *Разрешения API* > *Добавить разрешение* > *Office 365 Management APIs* > *Разрешения приложения*.</span><span class="sxs-lookup"><span data-stu-id="71326-139">Click along this path: *API Permissions* > *Add a permission* > *Office 365 Management APIs* > *Application permissions*.</span></span>
6. <span data-ttu-id="71326-140">Разверните раздел "Веб-канал активности" и установите флажок *ActivityFeed.Read*.</span><span class="sxs-lookup"><span data-stu-id="71326-140">Expand Activity Feed and check *ActivityFeed.Read*.</span></span>
7. <span data-ttu-id="71326-141">Выберите здесь *Предоставить согласие администратора*.</span><span class="sxs-lookup"><span data-stu-id="71326-141">Choose *Grand admin consent* here.</span></span> <span data-ttu-id="71326-142">Щелкните "Да" при появлении запроса на подтверждение.</span><span class="sxs-lookup"><span data-stu-id="71326-142">Click Yes when prompted asking if you mean it.</span></span>
8. <span data-ttu-id="71326-143">Щелкните *Сертификаты и секреты* на боковой панели и нажмите кнопку *Новый секрет клиента*.</span><span class="sxs-lookup"><span data-stu-id="71326-143">Click *Certificates and Secrets* in the side-bar> *New client secret* button.</span></span>
9. <span data-ttu-id="71326-144">В окне "Добавить секрет клиента" введите описание нового секрета клиента, выберите "Никогда" для истечения срока действия и нажмите *Добавить*.</span><span class="sxs-lookup"><span data-stu-id="71326-144">On the New client secret window, enter a description for the new Client Secret, make sure you choose 'Never' for Expiration, and click *Add*.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71326-145">**Очень важно** скопировать новый секрет клиента в запись диспетчера паролей под именем созданного приложения.</span><span class="sxs-lookup"><span data-stu-id="71326-145">It's **critical** to copy the new client secret into a password manager entry that goes under the name of the newly created app.</span></span> <span data-ttu-id="71326-146">Вы не сможете вернуться для просмотра этого секрета после закрытия колонки Azure (*колонка* — это термин Azure, обозначающий окно).</span><span class="sxs-lookup"><span data-stu-id="71326-146">You won't be able to get back to look at this secret after the closing out of the Azure blade (*blade* being the Azure term for window).</span></span>

### <a name="register-the-api-with-powershell-to-collect-teams-logs"></a><span data-ttu-id="71326-147">Регистрация API с помощью PowerShell для сбора журналов Teams</span><span class="sxs-lookup"><span data-stu-id="71326-147">Register the API with PowerShell to collect Teams logs</span></span>

<span data-ttu-id="71326-148">Завершающее действие настройки — получение и регистрация подписки на API, чтобы можно было собирать данные журналов.</span><span class="sxs-lookup"><span data-stu-id="71326-148">The final step in setup is to collect and register the API subscription so that you can collect your log data.</span></span> <span data-ttu-id="71326-149">Для этого API действий управления Microsoft 365 должен получать вызовы REST PowerShell.</span><span class="sxs-lookup"><span data-stu-id="71326-149">This is done via PowerShell REST calls to the Microsoft 365 Management Activity API.</span></span>

<span data-ttu-id="71326-150">Будьте готовы указать значения **идентификатора приложения (клиент)**, нового **секрета клиента**, вашего **домена URL-адреса для M365** и **идентификатора каталога (клиент)** в командлете PowerShell ниже.</span><span class="sxs-lookup"><span data-stu-id="71326-150">Be ready to supply **Application (client) ID**, the new **Client Secret**, your **URL domain for M365**, and **Directory (tenant) ID** values in the PowerShell cmdlet below.</span></span>

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

## <a name="step-2-deploy-a-sentinel-playbook-to-ingest-the-teams-logs"></a><span data-ttu-id="71326-151">Шаг 2. Развертывание сборника схем Sentinel для приема журналов Teams</span><span class="sxs-lookup"><span data-stu-id="71326-151">Step 2: Deploy a Sentinel Playbook to ingest the Teams logs</span></span>

<span data-ttu-id="71326-152">Сборники схем Azure Sentinel (также называемые приложениями логики) позволяют Azure принимать ваши собранные данные Teams.</span><span class="sxs-lookup"><span data-stu-id="71326-152">Azure Sentinel Playbooks (also called Logic Apps) will allow Azure to ingest your collected Teams data.</span></span> <span data-ttu-id="71326-153">Приложение логики опрашивает Office 365, чтобы найти данные аудита, записываемые в рабочую область Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="71326-153">The Logic App queries Office 365 to find the audit data it writes into the Azure Sentinel workspace.</span></span>

<span data-ttu-id="71326-154">Используйте [этот](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) шаблон ARM, чтобы развернуть сборник схем Sentinel.</span><span class="sxs-lookup"><span data-stu-id="71326-154">Use [this](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) ARM template to deploy your Sentinel Playbook.</span></span>

<span data-ttu-id="71326-155">Вот о чем нужно помнить:</span><span class="sxs-lookup"><span data-stu-id="71326-155">Things to remember:</span></span>

1. <span data-ttu-id="71326-156">Вам потребуется просмотреть шаблон ARM и определенные значения заменить значениями, соответствующими вашей среде.</span><span class="sxs-lookup"><span data-stu-id="71326-156">You will need to walk through the ARM template and replace certain of the values with values appropriate for your own environment.</span></span>
2. <span data-ttu-id="71326-157">Вам требуется предусмотреть время между приемом журналов и просмотром результатов в Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="71326-157">You will need to allow time between the ingestion of logs and looking at the results in Azure Sentinel.</span></span>

   <span data-ttu-id="71326-158">Подождите 5–10 минут, учитывая, что если в течение последних 5 минут данные отсутствуют, отобразится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="71326-158">Wait for 5 to 10 minutes, understanding that if there is no data within the past 5 minutes you will see an error message.</span></span> <span data-ttu-id="71326-159">Проверьте журналы аудита и имейте в виду, что в используемых системах результаты должны отображаться в течение 5–10 минут, так как сведения Teams находятся в событиях Audit.General, собирающих больше данных, чем журналы Teams.</span><span class="sxs-lookup"><span data-stu-id="71326-159">Check Audit logs and keep in mind that because Teams information is in the Audit.General events, which collects more than Teams logs, results should appear within 5 to 10 minutes on systems that are in use.</span></span> <span data-ttu-id="71326-160">При использовании текстовой среды обязательно применяйте Teams, чтобы создавать журналы.</span><span class="sxs-lookup"><span data-stu-id="71326-160">If using a text environment, be certain to use Teams in order to generate logging.</span></span>

![Рисунок с классами приложений логики.](media/tracyp-teams-sentinel-logic-app.png#thumbnail)

 <p><details><summary> <span data-ttu-id="71326-162">Объяснение действий на рисунке:</span><span class="sxs-lookup"><span data-stu-id="71326-162">Explanation of actions in the graphic:</span></span> 
  </summary>

  <span data-ttu-id="71326-163">• Повторение — это триггер приложения логики, указывающий рабочему процессу необходимость запуска каждый час.</span><span class="sxs-lookup"><span data-stu-id="71326-163">• Recurrence is the Logic App Trigger that tells the workflow to run every hour.</span></span>
  <p>
<span data-ttu-id="71326-164">• Действие "Текущее время" очень простое и заключается в получении текущего времени.</span><span class="sxs-lookup"><span data-stu-id="71326-164">• The Current Time action is very basic and just gets the current time.</span></span>
  <p>
<span data-ttu-id="71326-165">• Инициализация переменной создает переменную NextPage и присваивает ей значение 1.</span><span class="sxs-lookup"><span data-stu-id="71326-165">• Initialize Variable creates a variable called NextPage and sets it to 1.</span></span> <span data-ttu-id="71326-166">Это будет применено позже, чтобы обработать разбивку на страницы из API Office 365.</span><span class="sxs-lookup"><span data-stu-id="71326-166">This will be used later in order to handle pagination from the O365 API.</span></span>
  <p>
<span data-ttu-id="71326-167">• Инициализация переменной 2 создает пустую переменную "Start Time".</span><span class="sxs-lookup"><span data-stu-id="71326-167">• Initialize Variable 2 creates an empty variable called Start Time.</span></span>
  <p>
<span data-ttu-id="71326-168">• Выполнение запроса и перечисление результатов — это действие Azure Monitor, запрашивающее в рабочей области последний журнал O365, введенный из приложения логики.</span><span class="sxs-lookup"><span data-stu-id="71326-168">• Run Query and list results is an Azure Monitor action that will query the workspace for the last O365 log that was entered from the Logic App.</span></span>
  <p>
<span data-ttu-id="71326-169">• Условие 4 используется, чтобы проверить, возвратил ли запрос "Выполнение запроса и перечисление результатов" какие-либо данные.</span><span class="sxs-lookup"><span data-stu-id="71326-169">• Condition 4 is used to check whether the Run Query and list results query returned any data.</span></span> <span data-ttu-id="71326-170">Это выполняется, чтобы проверить, впервые ли использовано приложение логики.</span><span class="sxs-lookup"><span data-stu-id="71326-170">This is done to check if this is the very first time the Logic App has been used.</span></span> <span data-ttu-id="71326-171">Если данные не возвращаются, переменной StartTime присваивается значение Now — 24 часа.</span><span class="sxs-lookup"><span data-stu-id="71326-171">If no data is returned, StartTime variable is set to Now – 24 hours.</span></span> <span data-ttu-id="71326-172">Если данные возвращаются, переменной StartTime присваивается значение последней записи TimeGenerated.</span><span class="sxs-lookup"><span data-stu-id="71326-172">If data is returned, StartTime is set to the last record TimeGenerated.</span></span> <span data-ttu-id="71326-173">Это делается для того, чтобы запрос мог получить данные от последней записи до текущего момента в опросе API Office 365 или за последние 24 часа, если это первый запуск.</span><span class="sxs-lookup"><span data-stu-id="71326-173">This is done so that the query can get data from the last entry till now in the poll against the O365 API, or in the last 24 hours if this is the first run.</span></span>
  <p>
<span data-ttu-id="71326-174">• Инициализация переменной 3 создает переменную AvailableUri.</span><span class="sxs-lookup"><span data-stu-id="71326-174">• Initialize Variable 3 creates a variable called AvailableUri.</span></span> <span data-ttu-id="71326-175">Это строка с URL-адресом, созданная с использованием StartTime и CurrentTime в качестве времени начала и окончания соответственно.</span><span class="sxs-lookup"><span data-stu-id="71326-175">This is a string with the URL built using the StartTime and CurrentTime as start and end times, respectively.</span></span>
  <p>
<span data-ttu-id="71326-176">• Условие Until — это цикл, позволяющий приложению логики продолжать опрашивать API, чтобы проверять наличие дополнительных данных (разбивка на страницы).</span><span class="sxs-lookup"><span data-stu-id="71326-176">• The Until condition is a loop that allows the logic app to keep polling the API to see if there is more data (pagination).</span></span> <span data-ttu-id="71326-177">Пока переменная NextPage имеет значение 1, цикл продолжается.</span><span class="sxs-lookup"><span data-stu-id="71326-177">As long as NextPage variable is 1 the loop will continue.</span></span> <span data-ttu-id="71326-178">Позже эта переменная будет обновлена, если закончатся страницы для получения.</span><span class="sxs-lookup"><span data-stu-id="71326-178">Later this variable will be updated if there are no more pages left to retrieve.</span></span>
  <p>
<span data-ttu-id="71326-179">• В цикле Until первый шаг HTTP подключается к AvailableURI.</span><span class="sxs-lookup"><span data-stu-id="71326-179">• Inside the Until loop, the first HTTP step Connects to the AvailableURI.</span></span> <span data-ttu-id="71326-180">Этот URI возвращает список доступного содержимого и URI каждого элемента содержимого.</span><span class="sxs-lookup"><span data-stu-id="71326-180">This URI returns a list of available content and each contents URI.</span></span> <span data-ttu-id="71326-181">Дополнительные сведения об этих принципах работы см. по URL-адресу https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span><span class="sxs-lookup"><span data-stu-id="71326-181">There's more on how this works at this URL: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span></span>
  <p>
<span data-ttu-id="71326-182">• Далее выполняется проверка, чтобы убедиться в возвращении данных.</span><span class="sxs-lookup"><span data-stu-id="71326-182">• Next a check is run to make sure data is returned.</span></span> <span data-ttu-id="71326-183">Условие проверяет, равна ли длина текста 0.</span><span class="sxs-lookup"><span data-stu-id="71326-183">The Condition checks if the length of the body is 0.</span></span> <span data-ttu-id="71326-184">Если это так, данные для записи в аналитику журнала отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="71326-184">If so there is no data to write to Log Analytics.</span></span> <span data-ttu-id="71326-185">Если значение больше 0, существуют данные для обработки.</span><span class="sxs-lookup"><span data-stu-id="71326-185">If the value is greater than 0, there is data to process.</span></span>
  <p>
<span data-ttu-id="71326-186">• Если данные обнаружены, их требуется обработать.</span><span class="sxs-lookup"><span data-stu-id="71326-186">• If data is detected, it must next be processed.</span></span> <span data-ttu-id="71326-187">Анализ JSON определяет схему возвращаемых данных.</span><span class="sxs-lookup"><span data-stu-id="71326-187">Parse JSON defines a schema of the returned data.</span></span> <span data-ttu-id="71326-188">Это позволяет приложениям логики использовать проанализированные данные в качестве динамического контента в последующих действиях.</span><span class="sxs-lookup"><span data-stu-id="71326-188">This allows logic apps to use the parsed data as Dynamic content in later steps.</span></span>
  <p>
<span data-ttu-id="71326-189">• Так как возвращаемый список доступных данных является массивом, используется действие For Each для циклического перебора списка доступных элементов содержимого.</span><span class="sxs-lookup"><span data-stu-id="71326-189">• Since the returned list of available data is an Array, a For Each action is used to loop through the list of available content.</span></span>
  <p>
<span data-ttu-id="71326-190">• Затем захватывается содержимое.</span><span class="sxs-lookup"><span data-stu-id="71326-190">• Next is grabbing the content.</span></span>  <span data-ttu-id="71326-191">Вновь используется параметр HTTP для получения contentUri (динамическое свойство, созданное из анализа JSON), являющегося URL-адресом получаемых данных.</span><span class="sxs-lookup"><span data-stu-id="71326-191">HTTP is used again to get the contentUri (a dynamic property created from Parse JSON), which is the URL of the data to retrieve.</span></span>
  <p>
<span data-ttu-id="71326-192">• Анализ JSON также используется для синтаксического анализа возвращаемых данных.</span><span class="sxs-lookup"><span data-stu-id="71326-192">• Parse JSON is also used to parse the returned data.</span></span> <span data-ttu-id="71326-193">Некоторые примеры содержимого доступны по URL-адресу https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span><span class="sxs-lookup"><span data-stu-id="71326-193">You can find some sample content at this URL: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span></span>
  <p>
<span data-ttu-id="71326-194">• Возвращаемые данные также являются массивом.</span><span class="sxs-lookup"><span data-stu-id="71326-194">• The data returned is also an array.</span></span> <span data-ttu-id="71326-195">Здесь также можно использовать цикл For Each.</span><span class="sxs-lookup"><span data-stu-id="71326-195">A For Each loop can be used here as well.</span></span> <span data-ttu-id="71326-196">В этом цикле рабочий процесс получает текущий элемент данных и использует действие Send Data для записи данных в аналитику журнала.</span><span class="sxs-lookup"><span data-stu-id="71326-196">In this loop, the workflow takes the current item of data and uses the Send Data action to write the data to Log Analytics.</span></span>
  <p>
<span data-ttu-id="71326-197">• Так как в доступном содержимом может быть несколько страниц, условие проверяет, что параметру NextPageUri не присвоено значение NULL.</span><span class="sxs-lookup"><span data-stu-id="71326-197">• Since there may be multiple pages of available content, a condition checks if the NextPageUri is not NULL.</span></span> <span data-ttu-id="71326-198">Если он имеет значение NULL, параметру NextPage присваивается значение 0, что завершает цикл Until.</span><span class="sxs-lookup"><span data-stu-id="71326-198">If it is NULL, or empty, NextPage is set to 0, which ends the Until loop.</span></span> <span data-ttu-id="71326-199">Если в нем есть URL-адрес, переменная AvaibleUri обновляется с использованием этого URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="71326-199">If it contains a URL, the AvaibleUri variable is updated to that URL.</span></span> <span data-ttu-id="71326-200">В этом случае при следующем запуске цикла Until используется следующий доступный URL-адрес, а не начальный URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="71326-200">This way, the next run of the Until loop uses a next available URL, and not the starting URL.</span></span>

  </details>

> [!TIP]
> <span data-ttu-id="71326-201">Вместо этого вы можете использовать *функцию Azure*, чтобы принять эти журналы. В этом случае см. сведения о развертывании [здесь](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20Data) или [здесь](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20DataCSharp) в зависимости от предпочтений.</span><span class="sxs-lookup"><span data-stu-id="71326-201">You may choose to use an *Azure Function* to ingest those logs, instead, and if you do, the information on how to deploy is [here](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20Data), or [here](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20DataCSharp), depending on your preference.</span></span>

<span data-ttu-id="71326-202">При запущенном соединителе (независимо от выбранных выше вариантов) вы должны увидеть настраиваемую таблицу O365API_CL в рабочей области Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="71326-202">With the connector (whichever of the options above you chose) running, you should see a custom table called O365API_CL in the Azure Sentinel workspace.</span></span> <span data-ttu-id="71326-203">В ней размещаются ваши журналы Teams.</span><span class="sxs-lookup"><span data-stu-id="71326-203">This will house your Teams logs.</span></span>

## <a name="step-3-use-sentinel-to-monitor-microsoft-teams"></a><span data-ttu-id="71326-204">Шаг 3. Использование Sentinel для мониторинга Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="71326-204">Step 3: Use Sentinel to monitor Microsoft Teams</span></span>

<span data-ttu-id="71326-205">Удостоверение — это важный для отслеживания вектор атаки, связанный с Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="71326-205">Identity is an important attack vector to monitor when it comes to Microsoft Teams.</span></span> <span data-ttu-id="71326-206">Так как Azure Active Directory (Azure AD) — это основа каталога Microsoft 365, включая Teams, сбор и поиск в журналах Azure AD угроз, связанных с проверкой подлинности, облегчает выявление подозрительных действий в отношении удостоверений.</span><span class="sxs-lookup"><span data-stu-id="71326-206">Because Azure Active Directory (Azure AD) is the underpinning of Microsoft 365's directory, including Teams, collecting and hunting for threats in Azure AD logs around authentication will be useful in capturing suspicious behavior around identity.</span></span> <span data-ttu-id="71326-207">Вы можете использовать встроенный соединитель для извлечения данных Azure AD в Azure Sentinel, а также использовать эти запросы [обнаружения](https://github.com/Azure/Azure-Sentinel/tree/master/Detections/SigninLogs) и [поиска](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/SigninLogs) для выявления проблем.</span><span class="sxs-lookup"><span data-stu-id="71326-207">You can use the built-in connector to pull Azure AD data into Azure Sentinel, and use these [detection](https://github.com/Azure/Azure-Sentinel/tree/master/Detections/SigninLogs) and [hunting](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/SigninLogs) queries to look for problems.</span></span>

<span data-ttu-id="71326-208">В отношении специфичных для Microsoft Teams атак, например угроз для данных, в Azure Sentinel также имеются средства для их отслеживания и поиска.</span><span class="sxs-lookup"><span data-stu-id="71326-208">Regarding attacks specific to Microsoft Teams, threats to data, for example, Azure Sentinel also has means to monitor for them and hunt them down.</span></span>

### <a name="create-a-parser-for-your-data"></a><span data-ttu-id="71326-209">Создание средства синтаксического анализа для данных</span><span class="sxs-lookup"><span data-stu-id="71326-209">Create a parser for your data</span></span>

<span data-ttu-id="71326-210">Первое, что нужно сделать, чтобы разобраться в большом наборе собранных данных, — понять их значение с помощью синтаксического анализа.</span><span class="sxs-lookup"><span data-stu-id="71326-210">The first thing to do in order to make sense of the large set of collected data is to give it meaning by parsing it.</span></span> <span data-ttu-id="71326-211">Это осуществляется с помощью функции языка запросов Kusto (KQL), упрощающей работу с данными.</span><span class="sxs-lookup"><span data-stu-id="71326-211">This is done with a Kusto Query Language (KQL) Function that makes the data easier to use.</span></span>

> [!NOTE]
> <span data-ttu-id="71326-212">Функции KQL — это запросы KQL, сохраненные в виде данных под названием "функция".</span><span class="sxs-lookup"><span data-stu-id="71326-212">KQL functions are KQL queries saved as a data-type called 'function'.</span></span> <span data-ttu-id="71326-213">Функции KQL содержат псевдоним, который можно ввести в поле запроса в Sentinel, чтобы быстро повторить запрос.</span><span class="sxs-lookup"><span data-stu-id="71326-213">KQL functions have an alias that can be entered into the query box in Sentinel to quickly run the query again.</span></span> <span data-ttu-id="71326-214">Дополнительные сведения о функциях KQL и создании функции синтаксического анализа см. в [этой статье сообщества Tech Community](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span><span class="sxs-lookup"><span data-stu-id="71326-214">For more about KQL functions and how to build a parser function, read [this Tech Community article](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span></span>
 
 <span data-ttu-id="71326-215">Средство синтаксического анализа ниже — это настраиваемый пример, предназначенный для выбора подмножества полей API управления Office 365, относящихся к *Teams*.</span><span class="sxs-lookup"><span data-stu-id="71326-215">The parser below is a customizable example aimed at selecting a subset of the Office 365 Management API fields relevant to *Teams*.</span></span> <span data-ttu-id="71326-216">Также существует предлагаемое средство синтаксического анализа [GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt), но в примере ниже можно вносить изменения для соблюдения различных потребностей и предпочтений.</span><span class="sxs-lookup"><span data-stu-id="71326-216">There is also a suggested parser [GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt), but the parser below can be modified to fit different needs and preferences.</span></span>

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
 <span data-ttu-id="71326-217">Сохраните средство синтаксического анализа как функцию KQL с псевдонимом TeamsData.</span><span class="sxs-lookup"><span data-stu-id="71326-217">Save the parser as a KQL function, with an alias of TeamsData.</span></span> <span data-ttu-id="71326-218">Она будет использоваться в последующих запросах.</span><span class="sxs-lookup"><span data-stu-id="71326-218">It will be used for the queries to follow.</span></span> <span data-ttu-id="71326-219">Сведения о настройке и использовании функции KQL в качестве средства синтаксического анализа, можно найти в этой [статье сообщества Tech Community](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span><span class="sxs-lookup"><span data-stu-id="71326-219">Details on configuring and using a KQL function as a parser can be found in this [Tech Community article](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span></span>

## <a name="helpful-hunting-kql-queries"></a><span data-ttu-id="71326-220">Полезные запросы KQL для поиска</span><span class="sxs-lookup"><span data-stu-id="71326-220">Helpful hunting KQL queries</span></span>

<span data-ttu-id="71326-221">Используйте эти запросы, чтобы познакомиться с данными и средой Teams.</span><span class="sxs-lookup"><span data-stu-id="71326-221">Use these queries to familiarize yourself with your Teams data and Teams environment.</span></span> <span data-ttu-id="71326-222">Понимание среды и ее поведения — это отличный первый шаг по выявлению подозрительных действий.</span><span class="sxs-lookup"><span data-stu-id="71326-222">Knowing how the environment should look and behave is a good first step in recognizing suspicious activity.</span></span> <span data-ttu-id="71326-223">После этого вы можете перейти к поиску угроз.</span><span class="sxs-lookup"><span data-stu-id="71326-223">From there, you can branch out into threat hunting.</span></span>

#### <a name="federated-external-users-query"></a><span data-ttu-id="71326-224">Запросы федеративных внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="71326-224">Federated external users query</span></span>

<span data-ttu-id="71326-225">Получите список сайтов Teams с федеративными внешними пользователями.</span><span class="sxs-lookup"><span data-stu-id="71326-225">Get the list of Teams sites that have federated external users.</span></span> <span data-ttu-id="71326-226">У этих пользователей будет доменное имя или суффикс UPN, *не* принадлежащие вашей организации.</span><span class="sxs-lookup"><span data-stu-id="71326-226">These users will have a domain name / UPN suffix that *isn't* owned by your organization.</span></span> <span data-ttu-id="71326-227">В этом примере запроса организации принадлежит домен contoso.com.</span><span class="sxs-lookup"><span data-stu-id="71326-227">In this example query, the organization owns contoso.com.</span></span>

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
> <span data-ttu-id="71326-228">Дополнительные сведения о внешнем и гостевом типах доступа в Teams см. в [этой статье](./communicate-with-users-from-other-organizations.md) или в разделе *Типы участников* в [руководстве по безопасности Teams](./teams-security-guide.md).</span><span class="sxs-lookup"><span data-stu-id="71326-228">To learn more about External and Guest access types in Teams see [this article](./communicate-with-users-from-other-organizations.md), or the *Participant Types* section in the [Teams Security Guide](./teams-security-guide.md).</span></span>

#### <a name="who-recently-joined--whose-role-changed"></a><span data-ttu-id="71326-229">Кто недавно присоединился или чья роль изменена</span><span class="sxs-lookup"><span data-stu-id="71326-229">Who recently joined / Whose role changed</span></span>

<span data-ttu-id="71326-230">Запросите определенного пользователя, чтобы проверить, был ли он добавлен в канал Teams за последние 7 дней или в течение недели:</span><span class="sxs-lookup"><span data-stu-id="71326-230">Query a specific user to check if they were added to a Teams channel in the last 7 days, or within a week:</span></span>

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members contains "UserName"
```

<span data-ttu-id="71326-231">Изменилась ли роль пользователя в команде за последние 7 дней:</span><span class="sxs-lookup"><span data-stu-id="71326-231">Was a user's role changed for a Team in the last 7 days:</span></span>

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| where Members contains "Role" and Members contains "1"
```

#### <a name="external-users-from-unknown-or-new-organizations"></a><span data-ttu-id="71326-232">Внешние пользователи из неизвестных или новых организаций</span><span class="sxs-lookup"><span data-stu-id="71326-232">External users from unknown or new organizations</span></span>

<span data-ttu-id="71326-233">В Teams вы можете добавлять внешних пользователей в среду или каналы.</span><span class="sxs-lookup"><span data-stu-id="71326-233">In Teams, you can add external users to your environment or channels.</span></span> <span data-ttu-id="71326-234">Организации часто имеют ограниченное количество ключевых партнеров и добавляют пользователей этих партнеров.</span><span class="sxs-lookup"><span data-stu-id="71326-234">Organizations often have a limited number of key partnerships and add users from among these partners.</span></span> <span data-ttu-id="71326-235">Эта функция KQL ищет добавленных в команды внешних пользователей из организаций, которые раньше отсутствовали или не добавлялись.</span><span class="sxs-lookup"><span data-stu-id="71326-235">This KQL looks at external users added to teams who come from organizations that haven't been seen or added before.</span></span>

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

#### <a name="external-users-who-were-added-and-then-removed"></a><span data-ttu-id="71326-236">Внешние пользователи, которые были добавлены, а затем удалены</span><span class="sxs-lookup"><span data-stu-id="71326-236">External users who were added and then removed</span></span>

<span data-ttu-id="71326-237">Злоумышленники с определенным уровнем доступа могут добавить новую внешнюю учетную запись в Teams, чтобы получить доступ и извлечь данные.</span><span class="sxs-lookup"><span data-stu-id="71326-237">Attackers with some level of existing access may add a new external account to Teams to access and exfiltrate data.</span></span> <span data-ttu-id="71326-238">Они также могут быстро удалить этого пользователя, чтобы скрыть получение доступа.</span><span class="sxs-lookup"><span data-stu-id="71326-238">They may also quickly remove that user to hide that they made access.</span></span> <span data-ttu-id="71326-239">Этот запрос используется для поиска внешних учетных записей, которые добавлены в Teams и быстро удалены, чтобы выявить подозрительное поведение.</span><span class="sxs-lookup"><span data-stu-id="71326-239">This query hunts for external accounts that are added to Teams and swiftly removed to help identify suspicious behavior.</span></span>

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

#### <a name="new-bot-or-application-added"></a><span data-ttu-id="71326-240">Добавлен новый бот или приложение</span><span class="sxs-lookup"><span data-stu-id="71326-240">New bot or application added</span></span>

<span data-ttu-id="71326-241">В Teams можно добавлять приложения или ботов для команды, чтобы расширить набор функций.</span><span class="sxs-lookup"><span data-stu-id="71326-241">Teams has the ability to include apps or bots in a Team to extend the feature set.</span></span> <span data-ttu-id="71326-242">Сюда относятся пользовательские приложения и боты.</span><span class="sxs-lookup"><span data-stu-id="71326-242">This includes custom apps and bots.</span></span> <span data-ttu-id="71326-243">В некоторых случаях приложение или бот могут использоваться для создания присутствия в Teams без необходимости пользовательской учетной записи, а также могут обращаться к файлам и другим данным.</span><span class="sxs-lookup"><span data-stu-id="71326-243">In some cases, an app or bot could be used to establish persistence in Teams without needing a user account, as well as access files and other data.</span></span> <span data-ttu-id="71326-244">Этот запрос используется для поиска новых приложений и ботов в Teams.</span><span class="sxs-lookup"><span data-stu-id="71326-244">This query hunts for apps or bots that are new to Teams.</span></span>

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

#### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a><span data-ttu-id="71326-245">Учетные записи пользователей, являющихся владельцами большого количества команд</span><span class="sxs-lookup"><span data-stu-id="71326-245">User accounts who are Owners of large numbers of Teams</span></span>

<span data-ttu-id="71326-246">Злоумышленники, пытающиеся получить дополнительные права, могут назначать себе права владельцев большого количества разнообразных команд, а пользователи обычно создают и владеют небольшим количеством команд, посвященных определенным темам.</span><span class="sxs-lookup"><span data-stu-id="71326-246">Attackers looking to elevate their privileges may assign themselves Owner privileges of a large number of diverse teams, when, usually, users create and own a small number of teams around specific topics.</span></span> <span data-ttu-id="71326-247">Этот запрос KQL ищет подозрительные действия.</span><span class="sxs-lookup"><span data-stu-id="71326-247">This KQL query looks for suspicious behavior.</span></span>

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

#### <a name="many-team-deletions-by-a-single-user"></a><span data-ttu-id="71326-248">Удаление большого количества команд одним пользователем</span><span class="sxs-lookup"><span data-stu-id="71326-248">Many Team deletions by a single user</span></span>

<span data-ttu-id="71326-249">Злоумышленники могут вызывать нарушения в работе и создавать угрозы проектам и данным, удаляя несколько команд.</span><span class="sxs-lookup"><span data-stu-id="71326-249">Attackers can cause disruptions and jeopardize projects and data by deleting multiple teams.</span></span> <span data-ttu-id="71326-250">Так как команды обычно удаляются отдельными владельцами, централизованное удаление нескольких команд может быть признаком проблемы.</span><span class="sxs-lookup"><span data-stu-id="71326-250">Because teams are generally deleted by individual Owners, a central deletion of many teams can be a sign of trouble.</span></span> <span data-ttu-id="71326-251">Этот запрос KQL ищет отдельных пользователей, удаляющих несколько команд.</span><span class="sxs-lookup"><span data-stu-id="71326-251">This KQL looks for single users who delete multiple teams.</span></span>

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

#### <a name="expanding-your-thread-hunting-opportunities"></a><span data-ttu-id="71326-252">Расширение возможностей поиска цепочек</span><span class="sxs-lookup"><span data-stu-id="71326-252">Expanding your thread hunting opportunities</span></span>

<span data-ttu-id="71326-253">Вы можете расширить поиск, объединив запросы из таких ресурсов, как Azure Active Directory (Azure AD) или других рабочих нагрузок Office 365, с запросами Teams.</span><span class="sxs-lookup"><span data-stu-id="71326-253">You can expand your hunting by combining queries from resources like Azure Active Directory (Azure AD), or other Office 365 workloads with your Teams queries.</span></span> <span data-ttu-id="71326-254">Одним из примеров является объединенное обнаружение подозрительных закономерностей в Azure AD SigninLogs и использование этих сведений при поиске владельцев команд.</span><span class="sxs-lookup"><span data-stu-id="71326-254">One example is combining detection of suspicious patterns in Azure AD SigninLogs, and using that information while hunting for Team Owners.</span></span>

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

<span data-ttu-id="71326-255">Вы также можете сделать обнаружения SigninLogs специфичными для Teams, добавив фильтр только для входов Teams:</span><span class="sxs-lookup"><span data-stu-id="71326-255">Also, you can make the SigninLogs detections specific to Teams by adding a filter for only Teams-based sign-ins by using:</span></span>

```kusto
| where AppDisplayName startswith "Microsoft Teams"
```

<span data-ttu-id="71326-256">Для дополнительного разъяснения использования `where AppDisplayName starts with "Microsoft Teams"` запрос KQL ниже демонстрирует успешный вход с одного IP-адреса и неудачный вход с другого IP-адреса применительно только ко входам Teams:</span><span class="sxs-lookup"><span data-stu-id="71326-256">To help explain using `where AppDisplayName starts with "Microsoft Teams"` further, the KQL below demonstrates a successful logon from one IP address with failure from a different IP address, but scoped only to Teams sign-ins:</span></span>

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

## <a name="important-information-and-updates"></a><span data-ttu-id="71326-257">Важная информация и обновления</span><span class="sxs-lookup"><span data-stu-id="71326-257">Important information and updates</span></span>

<span data-ttu-id="71326-258">**Благодарим за совместную работу над контентом Пита Брайана, Николаса Диколу и Мэтью Лоу.**</span><span class="sxs-lookup"><span data-stu-id="71326-258">**Thank you for content collaboration, Pete Bryan, Nicholas DiCola, and Matthew Lowe.**</span></span> <span data-ttu-id="71326-259">Пит Брайан и люди, с которыми он совместно работает, продолжат разрабатывать запросы обнаружения и поиска для Teams, поэтому проверяйте обновления в этом репозитории [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs).</span><span class="sxs-lookup"><span data-stu-id="71326-259">Pete Bryan and the people he collaborates with will continue to develop detection and hunting queries for Teams, so keep in touch with this [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) repository for updates.</span></span>  <span data-ttu-id="71326-260">Отслеживайте обновления для [средства синтаксического анализа](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) и [приложений логики](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data), использовавшихся в этой статье.</span><span class="sxs-lookup"><span data-stu-id="71326-260">Monitor for updates to the [parser](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) and [logic app](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) used in this article.</span></span> <span data-ttu-id="71326-261">Вы также можете присоединиться к [сообществу Azure Sentinel](https://github.com/Azure/Azure-Sentinel/wiki) и участвовать в нем.</span><span class="sxs-lookup"><span data-stu-id="71326-261">You can also join and contribute to the [Azure Sentinel community](https://github.com/Azure/Azure-Sentinel/wiki).</span></span> <span data-ttu-id="71326-262">Спасибо!</span><span class="sxs-lookup"><span data-stu-id="71326-262">Thank you!</span></span> <span data-ttu-id="71326-263">Удачного поиска.</span><span class="sxs-lookup"><span data-stu-id="71326-263">Happy hunting.</span></span>

[<span data-ttu-id="71326-264">Регистрация приложения в Azure AD</span><span class="sxs-lookup"><span data-stu-id="71326-264">Registering your application in Azure AD</span></span>](/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0)

[<span data-ttu-id="71326-265">Включение и отключение поиска в журнале аудита</span><span class="sxs-lookup"><span data-stu-id="71326-265">Turn audit log search on or off</span></span>](/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%c2%a0)

[<span data-ttu-id="71326-266">Что такое Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="71326-266">What is Azure Sentinel</span></span>](/azure/sentinel/overview)
