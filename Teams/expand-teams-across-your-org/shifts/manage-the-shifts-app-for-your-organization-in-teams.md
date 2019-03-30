---
title: Управление приложением "Смены" для вашей организации в Microsoft Teams
author: kenwith
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Узнайте, как создавать и настраивать приложения смен в группах для Firstline работников в вашей организации.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8b1ef7ee44b1d6318b85461b5d6b9d4173cc8552
ms.sourcegitcommit: 89b866a3c383555f6f89dc77bebd74cddf9e40fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/30/2019
ms.locfileid: "31013211"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="e563f-103">Управление приложением "Смены" для вашей организации в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e563f-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e563f-104">Начиная с 1 октября 2019, Microsoft StaffHub будет из эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="e563f-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="e563f-105">Мы создаем StaffHub возможностей в группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e563f-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="e563f-106">В настоящее время группы включает в себя приложение смены для управление планированием и дополнительные возможности будут развернуты со временем.</span><span class="sxs-lookup"><span data-stu-id="e563f-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="e563f-107">StaffHub перестанет работать для всех пользователей на 1 октября 2019.</span><span class="sxs-lookup"><span data-stu-id="e563f-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="e563f-108">Кто-то пытается открыть StaffHub отображается сообщение, предлагая загрузить групп.</span><span class="sxs-lookup"><span data-stu-id="e563f-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="e563f-109">Для получения дополнительных сведений см [Microsoft StaffHub из эксплуатации](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="e563f-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="e563f-110">Общие сведения о смены</span><span class="sxs-lookup"><span data-stu-id="e563f-110">Overview of Shifts</span></span>
<span data-ttu-id="e563f-111">Приложение смен в группами Майкрософт продолжает Firstline работников подключенными и синхронизации. Изначально мобильных сначала для быстрой и эффективной время управления и обмена данными для групп.</span><span class="sxs-lookup"><span data-stu-id="e563f-111">The Shifts app in Microsoft Teams keeps Firstline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="e563f-112">Смены позволяет сотрудникам Firstline и их менеджеры используют мобильные устройства для управления расписаниями и оставайтесь на связи.</span><span class="sxs-lookup"><span data-stu-id="e563f-112">Shifts lets Firstline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span> 

- <span data-ttu-id="e563f-113">Менеджеры создание, обновление и Управление расписаниями shift для групп.</span><span class="sxs-lookup"><span data-stu-id="e563f-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="e563f-114">Они могут отправлять сообщения одному пользователю («нет сброса в процессе установки») или всей группы («региональных GM попадает в 20 минут»).</span><span class="sxs-lookup"><span data-stu-id="e563f-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="e563f-115">Пользователи также могут отправлять документы политики, последние известия и видео.</span><span class="sxs-lookup"><span data-stu-id="e563f-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="e563f-116">Сотрудникам просматривать их предстоящие смены, видеть, кто еще запланированного за день, запрос на переключение или предлагают shift и время запроса из системы.</span><span class="sxs-lookup"><span data-stu-id="e563f-116">Employees view their upcoming shifts, can see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="e563f-117">Важно знать, что смен в настоящее время не поддерживает гостевая пользователей.</span><span class="sxs-lookup"><span data-stu-id="e563f-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="e563f-118">Это означает, что гости в группе нельзя добавить в или использовать расписания shift при включении гостевого доступа в группах.</span><span class="sxs-lookup"><span data-stu-id="e563f-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

## <a name="availability-of-shifts"></a><span data-ttu-id="e563f-119">Доступность смен</span><span class="sxs-lookup"><span data-stu-id="e563f-119">Availability of Shifts</span></span>

<span data-ttu-id="e563f-120">Смены доступна на всех подписок на Office 365, включая командами, с помощью нескольких исключения.</span><span class="sxs-lookup"><span data-stu-id="e563f-120">Shifts is available in all Office 365 subscriptions that include Teams, with a couple of exceptions.</span></span> <span data-ttu-id="e563f-121">Исключения являются "мне Нравится" государственных облако сообщества (GCC) и бесплатные рабочих групп.</span><span class="sxs-lookup"><span data-stu-id="e563f-121">The exceptions are US Government Cloud Community (GCC) and Teams free.</span></span> <span data-ttu-id="e563f-122">Смены недоступен в Office 365 "мне Нравится" государственных организаций или группами свободного и услуги.</span><span class="sxs-lookup"><span data-stu-id="e563f-122">Shifts isn't available in Office 365 US Government or Teams free offerings.</span></span>

<span data-ttu-id="e563f-123">Для получения дополнительных сведений о лицензировании для групп, включая список подписок на Office 365, которая включает в себя командами, видеть [лицензирования Office 365 для групп](../../Office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="e563f-123">To learn more about licensing for Teams, including a list of Office 365 subscriptions that includes Teams, see [Office 365 licensing for Teams](../../Office-365-licensing.md).</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="e563f-124">Расположение данных смены</span><span class="sxs-lookup"><span data-stu-id="e563f-124">Location of Shifts data</span></span>

<span data-ttu-id="e563f-125">В настоящее время смены данные хранятся в Azure в центрах обработки данных в Северной Америке, Западная Европа и Азиатско-Тихоокеанский регион.</span><span class="sxs-lookup"><span data-stu-id="e563f-125">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="e563f-126">Дополнительные сведения о котором хранятся данные отображаются [личных данных](http://o365datacentermap.azurewebsites.net/)?</span><span class="sxs-lookup"><span data-stu-id="e563f-126">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="e563f-127">Настроить смены</span><span class="sxs-lookup"><span data-stu-id="e563f-127">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="e563f-128">Включение или отключение смен в вашей организации</span><span class="sxs-lookup"><span data-stu-id="e563f-128">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="e563f-129">Смены включен по умолчанию для всех групп пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e563f-129">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="e563f-130">Можно отключить или включить приложение для вашей организации в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e563f-130">You can turn off or turn on the app for your organization in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="e563f-131">Войдите Центр администрирования Microsoft 365 с помощью учетной записи администратора Office 365.</span><span class="sxs-lookup"><span data-stu-id="e563f-131">Sign in to the Microsoft 365 admin center with your Office 365 admin account.</span></span>
2. <span data-ttu-id="e563f-132">Перейдите на страницу **Параметры** > **надстроек & служб** > **Группами Майкрософт**.</span><span class="sxs-lookup"><span data-stu-id="e563f-132">Go to **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span> 
3. <span data-ttu-id="e563f-133">В разделе **Параметры на уровне клиента**выберите **приложения**и в разделе **Приложения по умолчанию**, снимите или установите флажок **смены** , чтобы отключить или включить приложение.</span><span class="sxs-lookup"><span data-stu-id="e563f-133">Under **Tenant-wide settings**, select **Apps**, and then under **Default Apps**, clear or select the **Shifts** check box to turn off or turn on the app.</span></span> 

    <span data-ttu-id="e563f-134">![Снимок экрана в разделе приложения по умолчанию] (../../media/firstline-worker-enable-disable-shifts.png "Снимок экрана раздела приложений по умолчанию в центре администрирования Microsoft 365, отображение списка приложений, включая приложения смены")</span><span class="sxs-lookup"><span data-stu-id="e563f-134">![Screen shot of the Default Apps section](../../media/firstline-worker-enable-disable-shifts.png "Screen shot of the Default Apps section in the Microsoft 365 admin center, showing the list of apps, including the Shifts app")</span></span>

### <a name="use-the-firstline-worker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="e563f-135">С помощью политики программы установки приложения Firstline работников для смены ПИН-кода для групп</span><span class="sxs-lookup"><span data-stu-id="e563f-135">Use the Firstline Worker app setup policy to pin Shifts to Teams</span></span>

> [!INCLUDE [Preview customer token](../../includes/preview-feature.md)]

<span data-ttu-id="e563f-136">Настройка политики в отношении приложений позволяют настраивать группам выделите пункт приложения, которые наиболее важные для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e563f-136">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="e563f-137">Указать в политике почтовых приложений связанные с панели приложения&mdash;полосы прокрутки на стороне клиента рабочего стола группами и в нижней части мобильных клиентов группами&mdash;которой пользователи могут быстро и легко получить доступ к их.</span><span class="sxs-lookup"><span data-stu-id="e563f-137">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span> 
 
<span data-ttu-id="e563f-138">Команды включает в себя встроенной политики рабочих Firstline программы установки приложения, которое можно назначить Firstline сотрудников в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e563f-138">Teams includes a built-in Firstline Worker app setup policy that you can assign to Firstline Workers in your organization.</span></span> <span data-ttu-id="e563f-139">По умолчанию политики включает действия, смены, беседы и вызова приложения.</span><span class="sxs-lookup"><span data-stu-id="e563f-139">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="e563f-140">Ознакомиться с политикой Firstline работников в левой области переходов центра администрирования группами Майкрософт, перейдите к **группам приложения** > **политики в отношении установки приложений**.</span><span class="sxs-lookup"><span data-stu-id="e563f-140">To view the Firstline Worker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="e563f-141">![Снимок экрана политики программы установки приложения Firstline работников в центре администрирования группами Майкрософт] (../../media/firstline-worker-app-setup-policy.png "Снимок экрана политики программы установки приложения Firstline работников в центре администрирования группами Майкрософт")</span><span class="sxs-lookup"><span data-stu-id="e563f-141">![Screen shot of the Firstline Worker app setup policy in the Microsoft Teams admin center](../../media/firstline-worker-app-setup-policy.png "Screen shot of the Firstline Worker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-firstline-worker-policy-to-individual-users"></a><span data-ttu-id="e563f-142">Назначение политики Firstline работников для отдельных пользователей</span><span class="sxs-lookup"><span data-stu-id="e563f-142">Assign the Firstline Worker policy to individual users</span></span>

1. <span data-ttu-id="e563f-143">В левой области переходов центра администрирования группами Майкрософт перейдите к **пользователям**и нажмите кнопку пользователя.</span><span class="sxs-lookup"><span data-stu-id="e563f-143">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="e563f-144">Рядом с пунктом **назначения политик**и выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="e563f-144">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="e563f-145">В разделе **политика установки приложения группы**выберите **FirstlineWorker**и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e563f-145">Under **Teams App Setup policy**, select **FirstlineWorker**, and then choose **Save**.</span></span>

#### <a name="assign-the-firstline-worker-app-setup-policy-to-users-in-a-group"></a><span data-ttu-id="e563f-146">Назначение политики программы установки приложения работников Firstline пользователям в группе</span><span class="sxs-lookup"><span data-stu-id="e563f-146">Assign the Firstline Worker app setup policy to users in a group</span></span>

<span data-ttu-id="e563f-147">Можно назначить работников Firstline политики программы установки приложений для пользователей в группы, например группы безопасности, подключившись к Azure Active Directory PowerShell для модуля график и Скайп для модуль Business PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e563f-147">You can assign the Firstline Worker app setup policy to users in a group, such as a security group, by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="e563f-148">Дополнительные сведения об использовании PowerShell для управления группами см [Команды PowerShell](../../teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e563f-148">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](../../teams-powershell-overview.md).</span></span>

<span data-ttu-id="e563f-149">В этом примере мы назначить Firstline работника политики программы установки приложения для всех пользователей в группе Группа Firstline Contoso.</span><span class="sxs-lookup"><span data-stu-id="e563f-149">In this example, we assign the Firstline Worker app setup policy to all users in the Contoso Firstline Team group.</span></span>

> [!NOTE]
> <span data-ttu-id="e563f-150">Убедитесь, что подключение сначала для Azure Active Directory PowerShell для модуля график и Скайп для модуль Business PowerShell, выполнив действия, описанные в [подключиться ко всем службам Office 365 в одном окне Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="e563f-150">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="e563f-151">Получите GroupObjectId конкретной группы.</span><span class="sxs-lookup"><span data-stu-id="e563f-151">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
<span data-ttu-id="e563f-152">Получение элементов из указанной группы.</span><span class="sxs-lookup"><span data-stu-id="e563f-152">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="e563f-153">Назначьте политики программы установки приложения FirstlineWorker всех пользователей в группе.</span><span class="sxs-lookup"><span data-stu-id="e563f-153">Assign all users in the group to the FirstlineWorker app setup policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "FirstlineWorker" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="e563f-154">В зависимости от числа членов группы эта команда может занять несколько минут для выполнения.</span><span class="sxs-lookup"><span data-stu-id="e563f-154">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e563f-155">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="e563f-155">Related topics</span></span>
- [<span data-ttu-id="e563f-156">Сдвигает справки для работников Firstline</span><span class="sxs-lookup"><span data-stu-id="e563f-156">Shifts Help for Firstline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
