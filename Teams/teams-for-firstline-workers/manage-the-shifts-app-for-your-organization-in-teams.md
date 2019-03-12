---
title: Управление приложением "Смены" для вашей организации в Microsoft Teams
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Узнайте, как создавать и настраивать приложения смен в группах для firstline сотрудников в вашей организации.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 994d83645c272b2beed4752c7cdaaeaef6c9cd0f
ms.sourcegitcommit: 3d3a296f225ecbbee0b4cea67664ad7ab31ed1c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "30537734"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="df89b-103">Управление приложением "Смены" для вашей организации в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="df89b-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="df89b-104">Начиная с 1 октября 2019, Microsoft StaffHub будет из эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="df89b-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="df89b-105">Мы создаем StaffHub возможностями, включая расписание и задачи управления в группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="df89b-105">We're building StaffHub capabilities, including schedule and task management, into Microsoft Teams.</span></span> <span data-ttu-id="df89b-106">Дополнительные возможности для работников firstline будут развернуты в группы по времени.</span><span class="sxs-lookup"><span data-stu-id="df89b-106">Additional capabilities for firstline workers will roll out to Teams over time.</span></span> <span data-ttu-id="df89b-107">Для получения дополнительных сведений см [Microsoft StaffHub из эксплуатации](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="df89b-107">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="df89b-108">Общие сведения о смены</span><span class="sxs-lookup"><span data-stu-id="df89b-108">Overview of Shifts</span></span>
<span data-ttu-id="df89b-109">Приложение смен в группами Майкрософт продолжает firstline работников подключенными и синхронизации. Изначально мобильных сначала для быстрой и эффективной время управления и обмена данными для групп.</span><span class="sxs-lookup"><span data-stu-id="df89b-109">The Shifts app in Microsoft Teams keeps firstline workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="df89b-110">Смены позволяет сотрудникам firstline и их менеджеры используют мобильные устройства для управления расписаниями и оставайтесь на связи.</span><span class="sxs-lookup"><span data-stu-id="df89b-110">Shifts lets firstline workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span> 

- <span data-ttu-id="df89b-111">Менеджеры создание, обновление и Управление расписаниями shift для групп.</span><span class="sxs-lookup"><span data-stu-id="df89b-111">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="df89b-112">Они могут отправлять сообщения одному пользователю («нет сброса в процессе установки») или всей группы («региональных GM попадает в 20 минут»).</span><span class="sxs-lookup"><span data-stu-id="df89b-112">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="df89b-113">Пользователи также могут отправлять документы политики, последние известия и видео.</span><span class="sxs-lookup"><span data-stu-id="df89b-113">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="df89b-114">Сотрудникам просматривать их предстоящие смены, видеть, кто еще запланированного за день, запрос на переключение или предлагают shift и время запроса из системы.</span><span class="sxs-lookup"><span data-stu-id="df89b-114">Employees view their upcoming shifts, can see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="df89b-115">Важно знать, что смен в настоящее время не поддерживает гостевая пользователей.</span><span class="sxs-lookup"><span data-stu-id="df89b-115">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="df89b-116">Это означает, что гости в группе нельзя добавить в или использовать расписания shift при включении гостевого доступа в группах.</span><span class="sxs-lookup"><span data-stu-id="df89b-116">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

## <a name="availability-of-shifts"></a><span data-ttu-id="df89b-117">Доступность смен</span><span class="sxs-lookup"><span data-stu-id="df89b-117">Availability of Shifts</span></span>

<span data-ttu-id="df89b-118">Смены доступна на всех подписок на Office 365, включая командами, с помощью нескольких исключения.</span><span class="sxs-lookup"><span data-stu-id="df89b-118">Shifts is available in all Office 365 subscriptions that include Teams, with a couple of exceptions.</span></span> <span data-ttu-id="df89b-119">Исключения являются "мне Нравится" государственных облако сообщества (GCC) и бесплатные рабочих групп.</span><span class="sxs-lookup"><span data-stu-id="df89b-119">The exceptions are US Government Cloud Community (GCC) and Teams free.</span></span> <span data-ttu-id="df89b-120">Смены недоступен в Office 365 "мне Нравится" государственных организаций или группами свободного и услуги.</span><span class="sxs-lookup"><span data-stu-id="df89b-120">Shifts isn't available in Office 365 US Government or Teams free offerings.</span></span>

<span data-ttu-id="df89b-121">Для получения дополнительных сведений о лицензировании для групп, включая список подписок на Office 365, которая включает в себя командами, видеть [лицензирования Office 365 для групп](../Office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="df89b-121">To learn more about licensing for Teams, including a list of Office 365 subscriptions that includes Teams, see [Office 365 licensing for Teams](../Office-365-licensing.md).</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="df89b-122">Расположение данных смены</span><span class="sxs-lookup"><span data-stu-id="df89b-122">Location of Shifts data</span></span>

<span data-ttu-id="df89b-123">В настоящее время смены данные хранятся в Azure в центрах обработки данных в Северной Америке, Западная Европа и Азиатско-Тихоокеанский регион.</span><span class="sxs-lookup"><span data-stu-id="df89b-123">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="df89b-124">Дополнительные сведения о котором хранятся данные отображаются [личных данных](http://o365datacentermap.azurewebsites.net/)?</span><span class="sxs-lookup"><span data-stu-id="df89b-124">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="df89b-125">Настроить смены</span><span class="sxs-lookup"><span data-stu-id="df89b-125">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="df89b-126">Включение или отключение смен в вашей организации</span><span class="sxs-lookup"><span data-stu-id="df89b-126">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="df89b-127">Смены включен по умолчанию для всех групп пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="df89b-127">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="df89b-128">Можно отключить или включить приложение для вашей организации в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="df89b-128">You can turn off or turn on the app for your organization in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="df89b-129">Войдите Центр администрирования Microsoft 365 с помощью учетной записи администратора Office 365.</span><span class="sxs-lookup"><span data-stu-id="df89b-129">Sign in to the Microsoft 365 admin center with your Office 365 admin account.</span></span>
2. <span data-ttu-id="df89b-130">Перейдите на страницу **Параметры** > **надстроек & служб** > **Группами Майкрософт**.</span><span class="sxs-lookup"><span data-stu-id="df89b-130">Go to **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span> 
3. <span data-ttu-id="df89b-131">В разделе **Параметры на уровне клиента**выберите **приложения**и в разделе **Приложения по умолчанию**, снимите или установите флажок **смены** , чтобы отключить или включить приложение.</span><span class="sxs-lookup"><span data-stu-id="df89b-131">Under **Tenant-wide settings**, select **Apps**, and then under **Default Apps**, clear or select the **Shifts** check box to turn off or turn on the app.</span></span> 

    <span data-ttu-id="df89b-132">![Снимок экрана в разделе приложения по умолчанию] (../media/firstline-worker-enable-disable-shifts.png "Снимок экрана раздела приложений по умолчанию в центре администрирования Microsoft 365, отображение списка приложений, включая приложения смены")</span><span class="sxs-lookup"><span data-stu-id="df89b-132">![Screen shot of the Default Apps section](../media/firstline-worker-enable-disable-shifts.png "Screen shot of the Default Apps section in the Microsoft 365 admin center, showing the list of apps, including the Shifts app")</span></span>

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="df89b-133">С помощью политики программы установки приложения FirstLineWorker для смены ПИН-кода для групп</span><span class="sxs-lookup"><span data-stu-id="df89b-133">Use the FirstLineWorker app setup policy to pin Shifts to Teams</span></span>

> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

<span data-ttu-id="df89b-134">Настройка политики в отношении приложений позволяют настраивать группам выделите пункт приложения, которые наиболее важные для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="df89b-134">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="df89b-135">Указать в политике почтовых приложений связанные с панели приложения&mdash;полосы прокрутки на стороне клиента рабочего стола группами и в нижней части мобильных клиентов группами&mdash;которой пользователи могут быстро и легко получить доступ к их.</span><span class="sxs-lookup"><span data-stu-id="df89b-135">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span> 
 
<span data-ttu-id="df89b-136">Команды включает в себя встроенной политики FirstLineWorker программы установки приложения, которое можно назначить firstline сотрудников в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="df89b-136">Teams includes a built-in FirstLineWorker app setup policy that you can assign to firstline workers in your organization.</span></span> <span data-ttu-id="df89b-137">По умолчанию политики включает действия, смены, беседы и вызова приложения.</span><span class="sxs-lookup"><span data-stu-id="df89b-137">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="df89b-138">Чтобы просмотреть политики FirstLineWorker в левой области переходов центра администрирования группами Майкрософт, перейдите к **приложения группы** > **политики в отношении установки приложений**.</span><span class="sxs-lookup"><span data-stu-id="df89b-138">To view the FirstLineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="df89b-139">![Снимок экрана политики программы установки приложения FirstLineWorker в центре администрирования группами Майкрософт] (../media/firstline-worker-app-setup-policy.png "Снимок экрана политики программы установки приложения FirstLineWorker в центре администрирования группами Майкрософт")</span><span class="sxs-lookup"><span data-stu-id="df89b-139">![Screen shot of the FirstLineWorker app setup policy in the Microsoft Teams admin center](../media/firstline-worker-app-setup-policy.png "Screen shot of the FirstLineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-firstlineworker-policy-to-individual-users"></a><span data-ttu-id="df89b-140">Назначение политики FirstLineWorker для отдельных пользователей</span><span class="sxs-lookup"><span data-stu-id="df89b-140">Assign the FirstLineWorker policy to individual users</span></span>

1. <span data-ttu-id="df89b-141">В левой области переходов центра администрирования группами Майкрософт перейдите к **пользователям**и нажмите кнопку пользователя.</span><span class="sxs-lookup"><span data-stu-id="df89b-141">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="df89b-142">Рядом с пунктом **назначения политик**и выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="df89b-142">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="df89b-143">В разделе **политика установки приложения группы**выберите **FirstLineWorker**и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="df89b-143">Under **Teams App Setup policy**, select **FirstLineWorker**, and then choose **Save**.</span></span>

#### <a name="assign-the-firstlineworker-app-setup-policy-to-users-in-a-group"></a><span data-ttu-id="df89b-144">Назначение политики программы установки приложения FirstLineWorker пользователям в группе</span><span class="sxs-lookup"><span data-stu-id="df89b-144">Assign the FirstLineWorker app setup policy to users in a group</span></span>

<span data-ttu-id="df89b-145">Можно назначить политики программы установки приложения FirstLineWorker пользователей в группы, например группы безопасности, с помощью подключения к Azure Active Directory PowerShell для модуля график и Скайп для модуль Business PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df89b-145">You can assign the FirstLineWorker app setup policy to users in a group, such as a security group, by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="df89b-146">Дополнительные сведения об использовании PowerShell для управления группами см [Команды PowerShell](../teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="df89b-146">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](../teams-powershell-overview.md).</span></span>

<span data-ttu-id="df89b-147">В этом примере мы назначение политики FirstLineWorker приложения программы установки для всех пользователей в группе Группа Firstline Contoso.</span><span class="sxs-lookup"><span data-stu-id="df89b-147">In this example, we assign the FirstLineWorker app setup policy to all users in the Contoso Firstline Team group.</span></span>

> [!NOTE]
> <span data-ttu-id="df89b-148">Убедитесь, что подключение сначала для Azure Active Directory PowerShell для модуля график и Скайп для модуль Business PowerShell, выполнив действия, описанные в [подключиться ко всем службам Office 365 в одном окне Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="df89b-148">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="df89b-149">Получите GroupObjectId конкретной группы.</span><span class="sxs-lookup"><span data-stu-id="df89b-149">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
<span data-ttu-id="df89b-150">Получение элементов из указанной группы.</span><span class="sxs-lookup"><span data-stu-id="df89b-150">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="df89b-151">Назначьте политики программы установки приложения FirstLineWorker всех пользователей в группе.</span><span class="sxs-lookup"><span data-stu-id="df89b-151">Assign all users in the group to the FirstLineWorker app setup policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "FirstLineWorker" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="df89b-152">В зависимости от числа членов группы эта команда может занять несколько минут для выполнения.</span><span class="sxs-lookup"><span data-stu-id="df89b-152">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="df89b-153">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="df89b-153">Related topics</span></span>
- [<span data-ttu-id="df89b-154">Сдвигает справки для firstline работников и менеджеров</span><span class="sxs-lookup"><span data-stu-id="df89b-154">Shifts Help for firstline workers and managers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)