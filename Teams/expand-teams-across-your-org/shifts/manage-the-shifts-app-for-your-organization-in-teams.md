---
title: Управление приложением "Смены" в организации
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
description: Узнайте, как настроить приложение "Смены" и управлять им в Teams для сотрудников без компьютеров в организации.
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
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909093"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="b577e-103">Управление приложением "Смены" для вашей организации в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b577e-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b577e-104">Поддержка Microsoft StaffHub прекращена с 30 июня 2020 г.</span><span class="sxs-lookup"><span data-stu-id="b577e-104">Effective June 30, 2020, Microsoft StaffHub has been retired.</span></span> <span data-ttu-id="b577e-105">Мы встраиваем возможности StaffHub в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b577e-105">We're building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="b577e-106">В настоящее время в состав Teams входит приложение "Смены" для управления расписанием, и со временем будут развернуты дополнительные возможности.</span><span class="sxs-lookup"><span data-stu-id="b577e-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="b577e-107">Приложение StaffHub перестало работать для всех пользователей 30 июня 2020 г.</span><span class="sxs-lookup"><span data-stu-id="b577e-107">StaffHub stopped working for all users on June 30, 2020.</span></span> <span data-ttu-id="b577e-108">При любой попытке открыть StaffHub отображается сообщение, ведущее на скачивание Teams.</span><span class="sxs-lookup"><span data-stu-id="b577e-108">Anyone who tries to open StaffHub is shown a message directing them to download Teams.</span></span> <span data-ttu-id="b577e-109">Дополнительные сведения см. в статье [Поддержка Microsoft StaffHub прекращена](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="b577e-109">To learn more, see [Microsoft StaffHub has been retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="b577e-110">Обзор Смен</span><span class="sxs-lookup"><span data-stu-id="b577e-110">Overview of Shifts</span></span>

<span data-ttu-id="b577e-111">Приложение "Смены" в Microsoft Teams обеспечивает связь и синхронизацию сотрудников без компьютеров. Оно изначально создано для мобильных устройств для быстрого и эффективного управления временем и общения команд.</span><span class="sxs-lookup"><span data-stu-id="b577e-111">The Shifts app in Microsoft Teams keeps Frontline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="b577e-112">Приложение "Смены" позволяет сотрудникам без компьютеров и руководителям использовать свои мобильные устройства для управления рабочими расписаниями и отправки уведомлений.</span><span class="sxs-lookup"><span data-stu-id="b577e-112">Shifts lets Frontline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span>

- <span data-ttu-id="b577e-113">Руководители могут создавать, обновлять и настраивать расписания смен для команд.</span><span class="sxs-lookup"><span data-stu-id="b577e-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="b577e-114">Они могут отправлять сообщения одному человеку ("кто-то пролил воду на пол") или всей команде ("через 20 минут приезжает директор").</span><span class="sxs-lookup"><span data-stu-id="b577e-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="b577e-115">Также можно отправлять нормативные документы, новостные бюллетени и видео.</span><span class="sxs-lookup"><span data-stu-id="b577e-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="b577e-116">Сотрудники могут видеть все свои предстоящие смены, кто еще работает в тот же день, просить коллег поменяться сменами или предложить смены, а также запросить отгул.</span><span class="sxs-lookup"><span data-stu-id="b577e-116">Employees view their upcoming shifts, see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="b577e-117">Важно знать, что в настоящее время Смены не поддерживают гостевых пользователей.</span><span class="sxs-lookup"><span data-stu-id="b577e-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="b577e-118">Это означает, что гостей команды нельзя добавить и они не могут использовать расписания смен, если в Teams включен гостевой доступ.</span><span class="sxs-lookup"><span data-stu-id="b577e-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

> [!Note]
> <span data-ttu-id="b577e-119">Подробные сведения о возможностях приложения "Смены" на разных платформах см. в статье [Возможности Teams на разных платформах](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span><span class="sxs-lookup"><span data-stu-id="b577e-119">For details about Shifts capabilities on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="availability-of-shifts"></a><span data-ttu-id="b577e-120">Доступность приложения "Смены"</span><span class="sxs-lookup"><span data-stu-id="b577e-120">Availability of Shifts</span></span>

<span data-ttu-id="b577e-121">Смены доступны во всех корпоративных SKU, где доступно приложение Teams.</span><span class="sxs-lookup"><span data-stu-id="b577e-121">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="b577e-122">Расположение данных Смен</span><span class="sxs-lookup"><span data-stu-id="b577e-122">Location of Shifts data</span></span>

<span data-ttu-id="b577e-123">В настоящее время данные Смен хранятся в центрах обработки данных Azure в Северной Америке, Западной Европе и Азиатско-Тихоокеанском регионе.</span><span class="sxs-lookup"><span data-stu-id="b577e-123">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="b577e-124">Дополнительные сведения о месте хранения данных см. в статье [Где находятся мои данные?](http://o365datacentermap.azurewebsites.net/)</span><span class="sxs-lookup"><span data-stu-id="b577e-124">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="b577e-125">Настройка Смен</span><span class="sxs-lookup"><span data-stu-id="b577e-125">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="b577e-126">Включение и отключение Смен в организации</span><span class="sxs-lookup"><span data-stu-id="b577e-126">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="b577e-127">По умолчанию приложение "Смены" включено для всех пользователей Teams в организации.</span><span class="sxs-lookup"><span data-stu-id="b577e-127">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="b577e-128">Вы можете отключить или включить приложение на уровне организации на странице [Управление приложениями](../../manage-apps.md) в Центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b577e-128">You can turn off or turn on the app at the org level on the [Manage apps](../../manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="b577e-129">В левой панели навигации Центра администрирования Microsoft Teams выберите **Приложения Teams** > **Управление приложениями**.</span><span class="sxs-lookup"><span data-stu-id="b577e-129">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="b577e-130">В списке приложений выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="b577e-130">In the list of apps, do one of the following actions:</span></span>

    - <span data-ttu-id="b577e-131">Чтобы отключить Смены для организации, найдите приложение "Смены", выделите его и нажмите **Заблокировать**.</span><span class="sxs-lookup"><span data-stu-id="b577e-131">To turn off Shifts for your organization, search for the Shifts app, select it, and then select **Block**.</span></span>
    - <span data-ttu-id="b577e-132">Чтобы включить Смены для организации, найдите приложение "Смены", выделите его и нажмите **Разрешить**.</span><span class="sxs-lookup"><span data-stu-id="b577e-132">To turn on Shifts for your organization, search for the Shifts app, select it, and then select **Allow**.</span></span>

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="b577e-133">Включение и отключение Смен для определенных пользователей в организации</span><span class="sxs-lookup"><span data-stu-id="b577e-133">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="b577e-134">Чтобы разрешить или запретить определенным пользователям в организации использовать Смены, включите приложение "Смены" в своей организации на странице [Управление приложениями](../../manage-apps.md), а затем создайте настраиваемую политику разрешений приложения и назначьте ее пользователям.</span><span class="sxs-lookup"><span data-stu-id="b577e-134">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization on the [Manage apps](../../manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="b577e-135">Дополнительные сведения см. в статье [Управление политиками и параметрами пользовательских приложений в Teams](../../teams-app-permission-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b577e-135">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-frontlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="b577e-136">Использование политики настройки приложений FrontlineWorker для закрепления Смен в Teams</span><span class="sxs-lookup"><span data-stu-id="b577e-136">Use the FrontlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="b577e-137">Политики настройки приложений позволяют настроить Teams, чтобы выделить приложения, которые наиболее важны для пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="b577e-137">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="b577e-138">Приложения, настроенные в политике, закрепляются на панели приложения&mdash;панели сбоку классического клиента Teams и в нижней части мобильных клиентов Teams,&mdash;где пользователи могут быстро и легко получить к ним доступ.</span><span class="sxs-lookup"><span data-stu-id="b577e-138">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span>
 
<span data-ttu-id="b577e-139">Teams включает встроенную политику настройки приложений FrontlineWorker, которую можно назначить сотрудникам без компьютеров в организации.</span><span class="sxs-lookup"><span data-stu-id="b577e-139">Teams includes a built-in FrontlineWorker app setup policy that you can assign to Frontline Workers in your organization.</span></span> <span data-ttu-id="b577e-140">По умолчанию политика включает приложения "Действия", "Смены", "Чат" и "Звонки".</span><span class="sxs-lookup"><span data-stu-id="b577e-140">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="b577e-141">Чтобы просмотреть политику FrontlineWorker, в левой области навигации Центра администрирования Microsoft Teams выберите **Приложения Teams** > **Политика настройки приложений**.</span><span class="sxs-lookup"><span data-stu-id="b577e-141">To view the FrontlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="b577e-142">![Снимок экрана: политика настройки приложений FrontlineWorker](../../media/firstline-worker-app-setup-policy.png "Снимок экрана: политика настройки приложений FrontlineWorker в Центре администрирования Microsoft Teams")</span><span class="sxs-lookup"><span data-stu-id="b577e-142">![Screenshot of the FrontlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FrontlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-frontlineworker-app-setup-policy-to-users"></a><span data-ttu-id="b577e-143">Назначение пользователям политики настройки приложений FrontlineWorker</span><span class="sxs-lookup"><span data-stu-id="b577e-143">Assign the FrontlineWorker app setup policy to users</span></span>

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a><span data-ttu-id="b577e-144">Поиск событий Смен в журнале аудита</span><span class="sxs-lookup"><span data-stu-id="b577e-144">Search the audit log for Shifts events</span></span>

<span data-ttu-id="b577e-145">**(предварительная версия)**</span><span class="sxs-lookup"><span data-stu-id="b577e-145">**(in preview)**</span></span>

<span data-ttu-id="b577e-146">Вы можете выполнять поиск в журнале аудита для просмотра действий Смен в организации.</span><span class="sxs-lookup"><span data-stu-id="b577e-146">You can search the audit log to view Shifts activity in your organization.</span></span>  <span data-ttu-id="b577e-147">Дополнительные сведения о поиске в журнале аудита и просмотре списка [действий Смен](../../audit-log-events.md#shifts-in-teams-activities), регистрируемых в журнале аудита, см. в статье [Поиск событий Teams в журнале аудита](../../audit-log-events.md).</span><span class="sxs-lookup"><span data-stu-id="b577e-147">To learn more about how to search the audit log and to see a list of [Shifts activities](../../audit-log-events.md#shifts-in-teams-activities) that are logged in the audit log, see [Search the audit log for events in Teams](../../audit-log-events.md).</span></span>

<span data-ttu-id="b577e-148">Прежде чем выполнять поиск в журнале аудита, необходимо сначала включить функцию аудита в [Центре безопасности и соответствия требованиям](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="b577e-148">Before you can search the audit log, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="b577e-149">Дополнительные сведения см. в статье [Включение и отключение поиска в журнале аудита](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span><span class="sxs-lookup"><span data-stu-id="b577e-149">To learn more, see [Turn audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span> <span data-ttu-id="b577e-150">Обратите внимание, что данные аудита доступны только с момента его включения.</span><span class="sxs-lookup"><span data-stu-id="b577e-150">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b577e-151">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="b577e-151">Related topics</span></span>

- [<span data-ttu-id="b577e-152">Справка по Сменам для сотрудников без компьютеров</span><span class="sxs-lookup"><span data-stu-id="b577e-152">Shifts Help for Frontline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [<span data-ttu-id="b577e-153">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="b577e-153">Assign policies to your users in Teams</span></span>](../../assign-policies.md)
