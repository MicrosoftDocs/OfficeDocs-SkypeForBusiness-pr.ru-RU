---
title: Управление приложением смен для Организации
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu,gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Сведения о том, как настроить и управлять приложением смен в Teams для Firstline работников в Организации.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d89ca8938c80b2afb8c1b32a395ab4a984327dcc
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790511"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="310c4-103">Управление приложением "Смены" для вашей организации в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="310c4-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="310c4-104">Действующий 30 июня 2020 г. Корпорация Microsoft StaffHub устарела.</span><span class="sxs-lookup"><span data-stu-id="310c4-104">Effective June 30, 2020, Microsoft StaffHub has been retired.</span></span> <span data-ttu-id="310c4-105">Мы создаем возможности StaffHub в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="310c4-105">We're building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="310c4-106">Сегодня команды включают в себя приложение смен для управления планированием и дополнительные возможности, которые будут вычислены с течением времени.</span><span class="sxs-lookup"><span data-stu-id="310c4-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="310c4-107">StaffHub перестает работать для всех пользователей 30 июня 2020 г.</span><span class="sxs-lookup"><span data-stu-id="310c4-107">StaffHub stopped working for all users on June 30, 2020.</span></span> <span data-ttu-id="310c4-108">Каждый, кто пытается открыть StaffHub, показывает сообщение, направленное на загрузку групп.</span><span class="sxs-lookup"><span data-stu-id="310c4-108">Anyone who tries to open StaffHub is shown a message directing them to download Teams.</span></span> <span data-ttu-id="310c4-109">Дополнительные сведения можно найти в [статье Microsoft StaffHub](microsoft-staffhub-to-be-retired.md)устарела.</span><span class="sxs-lookup"><span data-stu-id="310c4-109">To learn more, see [Microsoft StaffHub has been retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="310c4-110">Обзор смен</span><span class="sxs-lookup"><span data-stu-id="310c4-110">Overview of Shifts</span></span>

<span data-ttu-id="310c4-111">Приложение "Смена" в Microsoft Teams хранит FIRSTLINE и синхронизированные работники. Она была разработана на мобильных устройствах для быстрого и эффективного управления временем и общения в Teams.</span><span class="sxs-lookup"><span data-stu-id="310c4-111">The Shifts app in Microsoft Teams keeps Firstline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="310c4-112">Смена расписания позволяет Firstline сотрудникам и их руководителям использовать свои мобильные устройства для управления расписаний и поддержания связи.</span><span class="sxs-lookup"><span data-stu-id="310c4-112">Shifts lets Firstline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span>

- <span data-ttu-id="310c4-113">Руководители создают, обновляют и управляют расписаниями смен для групп.</span><span class="sxs-lookup"><span data-stu-id="310c4-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="310c4-114">Они могут отправлять сообщения одному пользователю ("на этаж") или всей группе ("Региональная GM, поступающие в течение 20 минут").</span><span class="sxs-lookup"><span data-stu-id="310c4-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="310c4-115">Кроме того, они могут отправлять документы политики, новостные бюллетени и видеоролики.</span><span class="sxs-lookup"><span data-stu-id="310c4-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="310c4-116">Сотрудники просматривают предстоящие смены, могут узнать, кто уже запланирован на этот день, запросить замену или предложить смену, а также запросить время отключения.</span><span class="sxs-lookup"><span data-stu-id="310c4-116">Employees view their upcoming shifts, can see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="310c4-117">Важно знать, что смена в настоящее время не поддерживает гостевых пользователей.</span><span class="sxs-lookup"><span data-stu-id="310c4-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="310c4-118">Это означает, что гости в команде нельзя добавить в расписание или использовать в качестве расписания смен, когда гостевой доступ включен в Teams.</span><span class="sxs-lookup"><span data-stu-id="310c4-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

> [!Note]
> <span data-ttu-id="310c4-119">Дополнительные сведения о возможностях смен на разных платформах можно найти в разделе [функции групп на платформе](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span><span class="sxs-lookup"><span data-stu-id="310c4-119">For details about Shifts capabilities on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="availability-of-shifts"></a><span data-ttu-id="310c4-120">Доступность смен</span><span class="sxs-lookup"><span data-stu-id="310c4-120">Availability of Shifts</span></span>

<span data-ttu-id="310c4-121">Смены доступны во всех SKU предприятий, где доступны команды.</span><span class="sxs-lookup"><span data-stu-id="310c4-121">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="310c4-122">Местоположение смен данных</span><span class="sxs-lookup"><span data-stu-id="310c4-122">Location of Shifts data</span></span>

<span data-ttu-id="310c4-123">Сменные данные в настоящее время хранятся в Azure в центрах обработки данных в Северной Америке, западноевропейских странах и странах Азиатско Тихоокеанский регион.</span><span class="sxs-lookup"><span data-stu-id="310c4-123">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="310c4-124">Дополнительные сведения о том, где хранятся данные, находятся в разделе [где находятся данные](http://o365datacentermap.azurewebsites.net/)?</span><span class="sxs-lookup"><span data-stu-id="310c4-124">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="310c4-125">Настройка смен</span><span class="sxs-lookup"><span data-stu-id="310c4-125">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="310c4-126">Включение и отключение смен в Организации</span><span class="sxs-lookup"><span data-stu-id="310c4-126">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="310c4-127">Смена включается по умолчанию для всех пользователей Teams в Организации.</span><span class="sxs-lookup"><span data-stu-id="310c4-127">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="310c4-128">Вы можете отключить или включить приложение на уровне Организации на странице " [Управление приложениями](../../manage-apps.md) " в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="310c4-128">You can turn off or turn on the app at the org level on the [Manage apps](../../manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="310c4-129">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел **приложения Teams**  >  **Управление приложениями** .</span><span class="sxs-lookup"><span data-stu-id="310c4-129">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps** .</span></span>
2. <span data-ttu-id="310c4-130">В списке приложений выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="310c4-130">In the list of apps, do one of the following:</span></span>

    - <span data-ttu-id="310c4-131">Чтобы отключить смену для Организации, выполните поиск по приложению смены, выделите его, а затем выберите команду **блокировать** .</span><span class="sxs-lookup"><span data-stu-id="310c4-131">To turn off Shifts for your organization, search for the Shifts app, select it, and then click **Block** .</span></span>
    - <span data-ttu-id="310c4-132">Чтобы включить смену для Организации, выполните поиск по приложению смены, выберите его и нажмите кнопку **Разрешить** .</span><span class="sxs-lookup"><span data-stu-id="310c4-132">To turn on Shifts for your organization, search for the Shifts app, select it, and then click **Allow** .</span></span>

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="310c4-133">Включение и отключение смен для отдельных пользователей в Организации</span><span class="sxs-lookup"><span data-stu-id="310c4-133">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="310c4-134">Чтобы разрешить или заблокировать использование смен определенными пользователями в Организации, убедитесь, что на странице [Управление приложениями](../../manage-apps.md) включены сменные элементы для вашей организации, а затем создайте собственную политику разрешений приложений и назначьте ее этим пользователям.</span><span class="sxs-lookup"><span data-stu-id="310c4-134">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization on the [Manage apps](../../manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="310c4-135">Дополнительные сведения можно найти [в разделе Управление политиками разрешений приложений в Teams](../../teams-app-permission-policies.md).</span><span class="sxs-lookup"><span data-stu-id="310c4-135">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="310c4-136">Закрепление смен в Teams с помощью политики настройки приложения FirstlineWorker</span><span class="sxs-lookup"><span data-stu-id="310c4-136">Use the FirstlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="310c4-137">Политики настройки приложений позволяют настроить команды для выбора наиболее важных для пользователей в организации приложений.</span><span class="sxs-lookup"><span data-stu-id="310c4-137">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="310c4-138">Приложения, заданные в политике, закреплены на панели приложения &mdash; , на которой расположена панель на боковой стороне настольного клиента Teams и в нижней части мобильных клиентов Teams, &mdash; где пользователи могут быстро и легко получать к ним доступ.</span><span class="sxs-lookup"><span data-stu-id="310c4-138">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span>
 
<span data-ttu-id="310c4-139">Команды включают встроенную политику настройки приложения FirstlineWorker, которую можно назначить Firstline сотрудникам Организации.</span><span class="sxs-lookup"><span data-stu-id="310c4-139">Teams includes a built-in FirstlineWorker app setup policy that you can assign to Firstline Workers in your organization.</span></span> <span data-ttu-id="310c4-140">По умолчанию политика включает в себя действия, смену, чат и звонки приложений.</span><span class="sxs-lookup"><span data-stu-id="310c4-140">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="310c4-141">Для просмотра политики FirstlineWorker на левой панели навигации центра администрирования Microsoft Teams перейдите в раздел **Teams app**  >  **политики настройки приложения** Teams.</span><span class="sxs-lookup"><span data-stu-id="310c4-141">To view the FirstlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies** .</span></span>

<span data-ttu-id="310c4-142">![Снимок экрана: Политика настройки приложения FirstlineWorker](../../media/firstline-worker-app-setup-policy.png "Снимок экрана: Политика настройки приложения FirstlineWorker в центре администрирования Microsoft Teams")</span><span class="sxs-lookup"><span data-stu-id="310c4-142">![Screenshot of the FirstlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FirstlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a><span data-ttu-id="310c4-143">Назначение пользователям политики настройки приложения FirstlineWorker</span><span class="sxs-lookup"><span data-stu-id="310c4-143">Assign the FirstlineWorker app setup policy to users</span></span>

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a><span data-ttu-id="310c4-144">Поиск событий смен в журнале аудита</span><span class="sxs-lookup"><span data-stu-id="310c4-144">Search the audit log for Shifts events</span></span>

<span data-ttu-id="310c4-145">**(Предварительная версия)**</span><span class="sxs-lookup"><span data-stu-id="310c4-145">**(in preview)**</span></span>

<span data-ttu-id="310c4-146">Вы можете выполнить поиск в журнале аудита, чтобы просмотреть действия по смене в Организации.</span><span class="sxs-lookup"><span data-stu-id="310c4-146">You can search the audit log to view Shifts activity in your organization.</span></span>  <span data-ttu-id="310c4-147">Чтобы узнать больше о том, как искать в журнале аудита и просматривать список [сменных действий](../../audit-log-events.md#shifts-in-teams-activities) , которые регистрируются в журнале аудита, ознакомьтесь со статьей [Поиск событий в журнале аудита для групп](../../audit-log-events.md).</span><span class="sxs-lookup"><span data-stu-id="310c4-147">To learn more about how to search the audit log and to see a list of [Shifts activities](../../audit-log-events.md#shifts-in-teams-activities) that are logged in the audit log, see [Search the audit log for events in Teams](../../audit-log-events.md).</span></span>

<span data-ttu-id="310c4-148">Перед тем как выполнять поиск в журнале аудита, необходимо сначала включить аудит в [центре безопасности & соответствия требованиям](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="310c4-148">Before you can search the audit log, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="310c4-149">Дополнительные сведения можно найти [в разделе Включение и отключение поиска в журнале аудита](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span><span class="sxs-lookup"><span data-stu-id="310c4-149">To learn more, see [Turn audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span> <span data-ttu-id="310c4-150">Имейте в виду, что данные аудита доступны только из той точки, в которой вы включили аудит.</span><span class="sxs-lookup"><span data-stu-id="310c4-150">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="310c4-151">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="310c4-151">Related topics</span></span>

- [<span data-ttu-id="310c4-152">Справка по сменам для Firstline работников</span><span class="sxs-lookup"><span data-stu-id="310c4-152">Shifts Help for Firstline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [<span data-ttu-id="310c4-153">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="310c4-153">Assign policies to your users in Teams</span></span>](../../assign-policies.md)
