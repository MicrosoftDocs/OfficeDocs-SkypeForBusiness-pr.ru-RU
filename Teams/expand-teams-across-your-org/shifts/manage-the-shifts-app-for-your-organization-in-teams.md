---
title: Управление приложением смен для Организации
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Сведения о том, как настроить и управлять приложением смен в Teams для Firstline работников в Организации.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 745644c7a6cf2207412faacd78e7b5a26d7b754d
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2020
ms.locfileid: "44349663"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="b4564-103">Управление приложением "Смены" для вашей организации в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b4564-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b4564-104">Действующий 30 июня 2020 г. Корпорация Microsoft StaffHub будет прекращена.</span><span class="sxs-lookup"><span data-stu-id="b4564-104">Effective June 30, 2020, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="b4564-105">Мы создаем возможности StaffHub в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b4564-105">We're building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="b4564-106">Сегодня команды включают в себя приложение смен для управления планированием и дополнительные возможности, которые будут вычислены с течением времени.</span><span class="sxs-lookup"><span data-stu-id="b4564-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="b4564-107">StaffHub перестанет работать для всех пользователей 30 июня 2020 г.</span><span class="sxs-lookup"><span data-stu-id="b4564-107">StaffHub will stop working for all users on June 30, 2020.</span></span> <span data-ttu-id="b4564-108">Каждый, кто пытается открыть StaffHub, будет показывать сообщение, направленное на загрузку групп.</span><span class="sxs-lookup"><span data-stu-id="b4564-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="b4564-109">Дополнительные сведения можно найти в [статье Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="b4564-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="b4564-110">Обзор смен</span><span class="sxs-lookup"><span data-stu-id="b4564-110">Overview of Shifts</span></span>

<span data-ttu-id="b4564-111">Приложение "Смена" в Microsoft Teams хранит FIRSTLINE и синхронизированные работники. Она была разработана на мобильных устройствах для быстрого и эффективного управления временем и общения в Teams.</span><span class="sxs-lookup"><span data-stu-id="b4564-111">The Shifts app in Microsoft Teams keeps Firstline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="b4564-112">Смена расписания позволяет Firstline сотрудникам и их руководителям использовать свои мобильные устройства для управления расписаний и поддержания связи.</span><span class="sxs-lookup"><span data-stu-id="b4564-112">Shifts lets Firstline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span>

- <span data-ttu-id="b4564-113">Руководители создают, обновляют и управляют расписаниями смен для групп.</span><span class="sxs-lookup"><span data-stu-id="b4564-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="b4564-114">Они могут отправлять сообщения одному пользователю ("на этаж") или всей группе ("Региональная GM, поступающие в течение 20 минут").</span><span class="sxs-lookup"><span data-stu-id="b4564-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="b4564-115">Кроме того, они могут отправлять документы политики, новостные бюллетени и видеоролики.</span><span class="sxs-lookup"><span data-stu-id="b4564-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="b4564-116">Сотрудники просматривают предстоящие смены, могут узнать, кто уже запланирован на этот день, запросить замену или предложить смену, а также запросить время отключения.</span><span class="sxs-lookup"><span data-stu-id="b4564-116">Employees view their upcoming shifts, can see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="b4564-117">Важно знать, что смена в настоящее время не поддерживает гостевых пользователей.</span><span class="sxs-lookup"><span data-stu-id="b4564-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="b4564-118">Это означает, что гости в команде нельзя добавить в расписание или использовать в качестве расписания смен, когда гостевой доступ включен в Teams.</span><span class="sxs-lookup"><span data-stu-id="b4564-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

## <a name="availability-of-shifts"></a><span data-ttu-id="b4564-119">Доступность смен</span><span class="sxs-lookup"><span data-stu-id="b4564-119">Availability of Shifts</span></span>

<span data-ttu-id="b4564-120">Смены доступны во всех SKU предприятий, где доступны команды.</span><span class="sxs-lookup"><span data-stu-id="b4564-120">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="b4564-121">Местоположение смен данных</span><span class="sxs-lookup"><span data-stu-id="b4564-121">Location of Shifts data</span></span>

<span data-ttu-id="b4564-122">Сменные данные в настоящее время хранятся в Azure в центрах обработки данных в Северной Америке, западноевропейских странах и странах Азиатско Тихоокеанский регион.</span><span class="sxs-lookup"><span data-stu-id="b4564-122">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="b4564-123">Дополнительные сведения о том, где хранятся данные, находятся в разделе [где находятся данные](http://o365datacentermap.azurewebsites.net/)?</span><span class="sxs-lookup"><span data-stu-id="b4564-123">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="b4564-124">Настройка смен</span><span class="sxs-lookup"><span data-stu-id="b4564-124">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="b4564-125">Включение и отключение смен в Организации</span><span class="sxs-lookup"><span data-stu-id="b4564-125">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="b4564-126">Смена включается по умолчанию для всех пользователей Teams в Организации.</span><span class="sxs-lookup"><span data-stu-id="b4564-126">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="b4564-127">Вы можете отключить или включить приложение на уровне Организации на странице " [Управление приложениями](../../manage-apps.md) " в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b4564-127">You can turn off or turn on the app at the org level on the [Manage apps](../../manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="b4564-128">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел **приложения Teams**  >  **Управление приложениями** .</span><span class="sxs-lookup"><span data-stu-id="b4564-128">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps** .</span></span>
2. <span data-ttu-id="b4564-129">В списке приложений выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="b4564-129">In the list of apps, do one of the following:</span></span>

    - <span data-ttu-id="b4564-130">Чтобы отключить смену для Организации, выполните поиск по приложению смены, выделите его, а затем выберите команду **блокировать**.</span><span class="sxs-lookup"><span data-stu-id="b4564-130">To turn off Shifts for your organization, search for the Shifts app, select it, and then click **Block**.</span></span>
    - <span data-ttu-id="b4564-131">Чтобы включить смену для Организации, выполните поиск по приложению смены, выберите его и нажмите кнопку **Разрешить**.</span><span class="sxs-lookup"><span data-stu-id="b4564-131">To turn on Shifts for your organization, search for the Shifts app, select it, and then click **Allow**.</span></span>

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="b4564-132">Включение и отключение смен для отдельных пользователей в Организации</span><span class="sxs-lookup"><span data-stu-id="b4564-132">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="b4564-133">Чтобы разрешить или заблокировать использование смен определенными пользователями в Организации, убедитесь, что на странице [Управление приложениями](../../manage-apps.md) включены сменные элементы для вашей организации, а затем создайте собственную политику разрешений приложений и назначьте ее этим пользователям.</span><span class="sxs-lookup"><span data-stu-id="b4564-133">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization on the [Manage apps](../../manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="b4564-134">Дополнительные сведения можно найти [в разделе Управление политиками разрешений приложений в Teams](../../teams-app-permission-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b4564-134">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="b4564-135">Закрепление смен в Teams с помощью политики настройки приложения FirstlineWorker</span><span class="sxs-lookup"><span data-stu-id="b4564-135">Use the FirstlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="b4564-136">Политики настройки приложений позволяют настроить команды для выбора наиболее важных для пользователей в организации приложений.</span><span class="sxs-lookup"><span data-stu-id="b4564-136">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="b4564-137">Приложения, заданные в политике, закреплены на панели приложения &mdash; , на которой расположена панель на боковой стороне настольного клиента Teams и в нижней части мобильных клиентов Teams, &mdash; где пользователи могут быстро и легко получать к ним доступ.</span><span class="sxs-lookup"><span data-stu-id="b4564-137">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span> 
 
<span data-ttu-id="b4564-138">Команды включают встроенную политику настройки приложения FirstlineWorker, которую можно назначить Firstline сотрудникам Организации.</span><span class="sxs-lookup"><span data-stu-id="b4564-138">Teams includes a built-in FirstlineWorker app setup policy that you can assign to Firstline Workers in your organization.</span></span> <span data-ttu-id="b4564-139">По умолчанию политика включает в себя действия, смену, чат и звонки приложений.</span><span class="sxs-lookup"><span data-stu-id="b4564-139">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="b4564-140">Для просмотра политики FirstlineWorker на левой панели навигации центра администрирования Microsoft Teams перейдите в раздел **Teams app**  >  **политики настройки приложения**Teams.</span><span class="sxs-lookup"><span data-stu-id="b4564-140">To view the FirstlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="b4564-141">![Снимок экрана: Политика настройки приложения FirstlineWorker](../../media/firstline-worker-app-setup-policy.png "Снимок экрана: Политика настройки приложения FirstlineWorker в центре администрирования Microsoft Teams")</span><span class="sxs-lookup"><span data-stu-id="b4564-141">![Screenshot of the FirstlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FirstlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-firstlineworker-policy-to-individual-users"></a><span data-ttu-id="b4564-142">Назначение политики FirstlineWorker отдельным пользователям</span><span class="sxs-lookup"><span data-stu-id="b4564-142">Assign the FirstlineWorker policy to individual users</span></span>

1. <span data-ttu-id="b4564-143">В Центре администрирования Microsoft Teams в области навигации слева перейдите в раздел **Пользователи**, затем щелкните пользователя.</span><span class="sxs-lookup"><span data-stu-id="b4564-143">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="b4564-144">Рядом с пунктом **Назначенные политики** выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="b4564-144">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="b4564-145">В разделе **Политика настройки приложения Teams**выберите **FirstlineWorker**и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b4564-145">Under **Teams App Setup policy**, select **FirstlineWorker**, and then choose **Save**.</span></span>

#### <a name="assign-the-firstlineworker-app-setup-policy-to-user-members-of-a-group"></a><span data-ttu-id="b4564-146">Назначение политики настройки приложения FirstlineWorker пользователям группы</span><span class="sxs-lookup"><span data-stu-id="b4564-146">Assign the FirstlineWorker app setup policy to user members of a group</span></span>

<span data-ttu-id="b4564-147">Вы можете назначить политику настройки приложения FirstlineWorker пользователям группы, например группе безопасности, подключився к модулю Azure Active Directory PowerShell для Graph и в модуль Skype для бизнеса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b4564-147">You can assign the FirstlineWorker app setup policy to user members of a group, such as a security group, by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="b4564-148">Дополнительные сведения об использовании PowerShell для управления группами можно найти в разделе [Общие сведения о Teams PowerShell](../../teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b4564-148">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](../../teams-powershell-overview.md).</span></span>

<span data-ttu-id="b4564-149">В этом примере мы назначаем политику настройки приложения FirstlineWorker всем пользователям группы группы Contoso FIRSTLINE.</span><span class="sxs-lookup"><span data-stu-id="b4564-149">In this example, we assign the FirstlineWorker app setup policy to all user members of the Contoso Firstline Team group.</span></span>

> [!NOTE]
> <span data-ttu-id="b4564-150">Убедитесь, что вы подключаетесь к модулю Azure Active Directory PowerShell для модуля Graph и Skype для бизнеса PowerShell, выполнив действия, описанные в разделе [подключение ко всем службам Office 365 в одном окне Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="b4564-150">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="b4564-151">Получить GroupObjectId определенной группы.</span><span class="sxs-lookup"><span data-stu-id="b4564-151">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
<span data-ttu-id="b4564-152">Получение участников указанной группы.</span><span class="sxs-lookup"><span data-stu-id="b4564-152">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="b4564-153">Назначьте политику настройки приложения FirstlineWorker всем пользователям группы.</span><span class="sxs-lookup"><span data-stu-id="b4564-153">Assign the FirstlineWorker app setup policy to all user members of the group.</span></span>
```PowerShell
$members | ForEach-Object {Grant-CsTeamsAppSetupPolicy -PolicyName "FirstlineWorker" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="b4564-154">Для выполнения этой команды может потребоваться несколько минут в зависимости от количества участников в группе.</span><span class="sxs-lookup"><span data-stu-id="b4564-154">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b4564-155">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="b4564-155">Related topics</span></span>
- [<span data-ttu-id="b4564-156">Справка по сменам для Firstline работников</span><span class="sxs-lookup"><span data-stu-id="b4564-156">Shifts Help for Firstline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
