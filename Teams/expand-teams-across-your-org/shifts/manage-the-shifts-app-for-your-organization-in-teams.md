---
title: Управление приложением "Смены" для организации
author: cichur
ms.author: v-cichur
ms.reviewer: lisawu,gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Узнайте, как настроить приложение "Смены" и управлять им в Teams для сотрудников без компьютеров в вашей организации.
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
ms.openlocfilehash: 218b041d83cde91a23201ab864160ce3b8b7cb6e
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909093"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="6eb84-103">Управление приложением "Смены" для вашей организации в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6eb84-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6eb84-104">С 30 июня 2020 г. больше не будет microsoft StaffHub.</span><span class="sxs-lookup"><span data-stu-id="6eb84-104">Effective June 30, 2020, Microsoft StaffHub has been retired.</span></span> <span data-ttu-id="6eb84-105">Мы строите возможности StaffHub в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6eb84-105">We're building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="6eb84-106">Сегодня в Teams есть приложение "Смены" для управления расписанием, а со временем будут перейти на новые возможности.</span><span class="sxs-lookup"><span data-stu-id="6eb84-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="6eb84-107">StaffHub перестал работать для всех пользователей 30 июня 2020 г.</span><span class="sxs-lookup"><span data-stu-id="6eb84-107">StaffHub stopped working for all users on June 30, 2020.</span></span> <span data-ttu-id="6eb84-108">Всем, кто пытается открыть StaffHub, отображается сообщение с командой для скачивания Teams.</span><span class="sxs-lookup"><span data-stu-id="6eb84-108">Anyone who tries to open StaffHub is shown a message directing them to download Teams.</span></span> <span data-ttu-id="6eb84-109">Подробнее см. в том, [что служба Microsoft StaffHub больше не была установлена.](microsoft-staffhub-to-be-retired.md)</span><span class="sxs-lookup"><span data-stu-id="6eb84-109">To learn more, see [Microsoft StaffHub has been retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="6eb84-110">Общие сведения о сменах</span><span class="sxs-lookup"><span data-stu-id="6eb84-110">Overview of Shifts</span></span>

<span data-ttu-id="6eb84-111">Приложение "Смены" в Microsoft Teams обеспечивает подключение и синхронизацию сотрудников переднего телефонного подключения. Оно сначала встроено в мобильное устройство для быстрого и эффективного управления временем и взаимодействия для команд.</span><span class="sxs-lookup"><span data-stu-id="6eb84-111">The Shifts app in Microsoft Teams keeps Frontline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="6eb84-112">Смены позволяют сотрудникам, работающим с телефоном, и руководителям использовать свои мобильные устройства для управления расписаниями и связи.</span><span class="sxs-lookup"><span data-stu-id="6eb84-112">Shifts lets Frontline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span>

- <span data-ttu-id="6eb84-113">Руководители создают, обновляют и управляют расписаниями смен в командах.</span><span class="sxs-lookup"><span data-stu-id="6eb84-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="6eb84-114">Они могут отправлять сообщения одному человеку ("кто-то пролит на пол") или всей команде ("через 20 минут прибыли директор").</span><span class="sxs-lookup"><span data-stu-id="6eb84-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="6eb84-115">Кроме того, они могут отправлять документы политики, новостные бюллетени и видео.</span><span class="sxs-lookup"><span data-stu-id="6eb84-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="6eb84-116">Сотрудники просматривают свои предстоящие смены, видят, у кого еще запланировано время на этот день, запрашивают обмен сменами или предложения, а также запрашивают отключки.</span><span class="sxs-lookup"><span data-stu-id="6eb84-116">Employees view their upcoming shifts, see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="6eb84-117">Важно знать, что в настоящее время shifts не поддерживает гостевых пользователей.</span><span class="sxs-lookup"><span data-stu-id="6eb84-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="6eb84-118">Это означает, что гостей в команде нельзя добавлять в группы или использовать расписания смен, если гостевой доступ включен в Teams.</span><span class="sxs-lookup"><span data-stu-id="6eb84-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

> [!Note]
> <span data-ttu-id="6eb84-119">Подробные сведения о возможностях Shifts на различных платформах см. в различных [платформах Teams.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)</span><span class="sxs-lookup"><span data-stu-id="6eb84-119">For details about Shifts capabilities on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="availability-of-shifts"></a><span data-ttu-id="6eb84-120">Доступность смен</span><span class="sxs-lookup"><span data-stu-id="6eb84-120">Availability of Shifts</span></span>

<span data-ttu-id="6eb84-121">Смены доступны на всех корпоративных skUs, где доступны Teams.</span><span class="sxs-lookup"><span data-stu-id="6eb84-121">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="6eb84-122">Расположение данных Shifts</span><span class="sxs-lookup"><span data-stu-id="6eb84-122">Location of Shifts data</span></span>

<span data-ttu-id="6eb84-123">В настоящее время данные shifts хранятся в Azure в центрах обработки данных в Северной Америке, Западной Европе и Азиатско-Тихоокеанском регионе.</span><span class="sxs-lookup"><span data-stu-id="6eb84-123">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="6eb84-124">Дополнительные сведения о том, где хранятся данные, см. в [сведениях о том, где хранятся мои данные?](http://o365datacentermap.azurewebsites.net/)</span><span class="sxs-lookup"><span data-stu-id="6eb84-124">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="6eb84-125">Настройка смен</span><span class="sxs-lookup"><span data-stu-id="6eb84-125">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="6eb84-126">Включить или отключить смены в организации</span><span class="sxs-lookup"><span data-stu-id="6eb84-126">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="6eb84-127">Смены по умолчанию включены для всех пользователей Teams в организации.</span><span class="sxs-lookup"><span data-stu-id="6eb84-127">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="6eb84-128">Вы можете отключить или включить приложение на уровне организации на [странице](../../manage-apps.md) "Управление приложениями" в Центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6eb84-128">You can turn off or turn on the app at the org level on the [Manage apps](../../manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="6eb84-129">В левой области навигации Центра администрирования Microsoft Teams перейдите в приложение **Teams**  >  **"Управление приложениями".**</span><span class="sxs-lookup"><span data-stu-id="6eb84-129">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="6eb84-130">В списке приложений сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="6eb84-130">In the list of apps, do one of the following actions:</span></span>

    - <span data-ttu-id="6eb84-131">Чтобы отключить приложение "Смены" для организации, нащите его, выберите и выберите **"Заблокировать".**</span><span class="sxs-lookup"><span data-stu-id="6eb84-131">To turn off Shifts for your organization, search for the Shifts app, select it, and then select **Block**.</span></span>
    - <span data-ttu-id="6eb84-132">Чтобы включить приложение "Смены" для организации, найди приложение "Смены", выберите его и выберите **"Разрешить".**</span><span class="sxs-lookup"><span data-stu-id="6eb84-132">To turn on Shifts for your organization, search for the Shifts app, select it, and then select **Allow**.</span></span>

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="6eb84-133">Включить или отключить смены для определенных пользователей в организации</span><span class="sxs-lookup"><span data-stu-id="6eb84-133">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="6eb84-134">Чтобы разрешить или заблокировать использование смен определенными пользователями в организации, убедитесь, [](../../manage-apps.md) что для вашей организации на странице "Управление приложениями" включено приложение Shifts, а затем создайте настраиваемую политику разрешений для приложений и назначьте ее этим пользователям.</span><span class="sxs-lookup"><span data-stu-id="6eb84-134">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization on the [Manage apps](../../manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="6eb84-135">Дополнительные узнать см. в [управлении политиками разрешений приложений в Teams.](../../teams-app-permission-policies.md)</span><span class="sxs-lookup"><span data-stu-id="6eb84-135">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-frontlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="6eb84-136">Настройка приложения FrontlineWorker с помощью политики закрепления shifts в Teams</span><span class="sxs-lookup"><span data-stu-id="6eb84-136">Use the FrontlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="6eb84-137">С помощью политик настройки приложений можно настроить Teams, чтобы выделить приложения, которые наиболее важны для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="6eb84-137">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="6eb84-138">Приложения, задатые в политике, закреплены на панели приложения сбоку клиента Teams для настольных ПК и в нижней части мобильных клиентов Teams, где пользователи могут быстро и легко получить к &mdash; &mdash; ним доступ.</span><span class="sxs-lookup"><span data-stu-id="6eb84-138">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span>
 
<span data-ttu-id="6eb84-139">В Teams есть встроенная политика настройки приложения FrontlineWorker, которую можно назначить сотрудникам, которые работают с frontline в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="6eb84-139">Teams includes a built-in FrontlineWorker app setup policy that you can assign to Frontline Workers in your organization.</span></span> <span data-ttu-id="6eb84-140">По умолчанию политика включает приложения "Действия", "Смены", "Чат" и "Вызовы".</span><span class="sxs-lookup"><span data-stu-id="6eb84-140">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="6eb84-141">Чтобы просмотреть политику FrontlineWorker, на панели навигации слева в Центре администрирования Microsoft Teams перейдите к политикам настройки приложений **Teams.**  >  </span><span class="sxs-lookup"><span data-stu-id="6eb84-141">To view the FrontlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="6eb84-142">![Снимок экрана: политика настройки приложения FrontlineWorker](../../media/firstline-worker-app-setup-policy.png "Снимок экрана: политика настройки приложения FrontlineWorker в Центре администрирования Microsoft Teams")</span><span class="sxs-lookup"><span data-stu-id="6eb84-142">![Screenshot of the FrontlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FrontlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-frontlineworker-app-setup-policy-to-users"></a><span data-ttu-id="6eb84-143">Назначение пользователям политики настройки приложений FrontlineWorker</span><span class="sxs-lookup"><span data-stu-id="6eb84-143">Assign the FrontlineWorker app setup policy to users</span></span>

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a><span data-ttu-id="6eb84-144">Поиск событий Смены в журнале аудита</span><span class="sxs-lookup"><span data-stu-id="6eb84-144">Search the audit log for Shifts events</span></span>

<span data-ttu-id="6eb84-145">**(Предварительная версия)**</span><span class="sxs-lookup"><span data-stu-id="6eb84-145">**(in preview)**</span></span>

<span data-ttu-id="6eb84-146">Вы можете искать в журнале аудита действия shifts в своей организации.</span><span class="sxs-lookup"><span data-stu-id="6eb84-146">You can search the audit log to view Shifts activity in your organization.</span></span>  <span data-ttu-id="6eb84-147">Чтобы узнать больше о поиске в журнале аудита и увидеть список действий [shifts,](../../audit-log-events.md#shifts-in-teams-activities) которые регистрируются в журнале аудита, см. поиск событий в Teams в журнале [аудита.](../../audit-log-events.md)</span><span class="sxs-lookup"><span data-stu-id="6eb84-147">To learn more about how to search the audit log and to see a list of [Shifts activities](../../audit-log-events.md#shifts-in-teams-activities) that are logged in the audit log, see [Search the audit log for events in Teams](../../audit-log-events.md).</span></span>

<span data-ttu-id="6eb84-148">Чтобы можно было искать в журнале аудита, необходимо сначала включить аудит в Центре & [соответствия требованиям.](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="6eb84-148">Before you can search the audit log, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="6eb84-149">Дополнительные данные см. в записях о включите [или выключите поиск в журнале аудита.](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)</span><span class="sxs-lookup"><span data-stu-id="6eb84-149">To learn more, see [Turn audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span> <span data-ttu-id="6eb84-150">Помните, что данные аудита доступны только с того момента, когда вы включили аудит.</span><span class="sxs-lookup"><span data-stu-id="6eb84-150">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6eb84-151">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="6eb84-151">Related topics</span></span>

- [<span data-ttu-id="6eb84-152">Справка по сменам для сотрудников, не работающих в компании</span><span class="sxs-lookup"><span data-stu-id="6eb84-152">Shifts Help for Frontline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [<span data-ttu-id="6eb84-153">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="6eb84-153">Assign policies to your users in Teams</span></span>](../../assign-policies.md)
