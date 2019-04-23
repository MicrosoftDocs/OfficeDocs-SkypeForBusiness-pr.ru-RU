---
title: Перемещение групп StaffHub в приложение "Смены" в Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 3/29/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Узнайте, как перемещение ваших команд Microsoft StaffHub и планирование данных для смены в группах Майкрософт.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 14f94428ddeba7b5a648b4b8dbd7bd5ef8fae0e4
ms.sourcegitcommit: 3000a661ac420eecd825a8285bdac7b744bd25da
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "31959484"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="7b002-103">Перемещение ваших команд Microsoft StaffHub смены в группах Майкрософт</span><span class="sxs-lookup"><span data-stu-id="7b002-103">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7b002-104">Начиная с 1 октября 2019, Microsoft StaffHub будет из эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="7b002-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="7b002-105">Мы создаем StaffHub возможностей в группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7b002-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="7b002-106">В настоящее время группы включает в себя приложение смены для управление планированием и дополнительные возможности будут развернуты со временем.</span><span class="sxs-lookup"><span data-stu-id="7b002-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="7b002-107">StaffHub перестанет работать для всех пользователей на 1 октября 2019.</span><span class="sxs-lookup"><span data-stu-id="7b002-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="7b002-108">Кто-то пытается открыть StaffHub отображается сообщение, предлагая загрузить групп.</span><span class="sxs-lookup"><span data-stu-id="7b002-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="7b002-109">Для получения дополнительных сведений см [Microsoft StaffHub из эксплуатации](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="7b002-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

> <span data-ttu-id="7b002-110">Возможности, описанные в этой статье еще не была выпущена.</span><span class="sxs-lookup"><span data-stu-id="7b002-110">The capability discussed in this article hasn't yet been released.</span></span> <span data-ttu-id="7b002-111">— Это была объявлена и в ближайшее время, в конце апреля 2019.</span><span class="sxs-lookup"><span data-stu-id="7b002-111">It's been announced, and is coming soon, towards the end of April 2019.</span></span> <span data-ttu-id="7b002-112">Если вы являетесь администратором, вы можете узнать при этом будут доступны в центре сообщений (в [центре администрирования Microsoft 365](https://portal.office.com/adminportal/home)).</span><span class="sxs-lookup"><span data-stu-id="7b002-112">If you're an admin, you can find out when this will be available in the Message Center (in the [Microsoft 365 admin center](https://portal.office.com/adminportal/home)).</span></span>

<span data-ttu-id="7b002-113">Приложение смен в группах предоставляет простой подход к управлению расписания и постоянного потока меняет местами shift и отмены собраний, которые происходят на ежедневной основе.</span><span class="sxs-lookup"><span data-stu-id="7b002-113">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="7b002-114">Участники группы могут получить доступ к их расписание и сведения о shift непосредственно в приложении и на их устройств, чтобы задать свои параметры управлять своим расписаниям и время запроса из системы.</span><span class="sxs-lookup"><span data-stu-id="7b002-114">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="7b002-115">В этой статье описывается перемещение групп StaffHub вашей организации и планирование данных для смены в группах.</span><span class="sxs-lookup"><span data-stu-id="7b002-115">This article walks you through how to move your organization’s StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="7b002-116">Будет ли вы малого бизнеса с одним или двумя группами StaffHub или крупном предприятии сотни StaffHub группам, здесь вы найдете рекомендации администратора, необходимые для перехода к группам успешно.</span><span class="sxs-lookup"><span data-stu-id="7b002-116">Whether you’re a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you’ll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="7b002-117">Должен быть глобального администратора, чтобы выполнить действия, описанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="7b002-117">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="7b002-118">Если это еще не сделано, нужно получить ответы на вопросы, которые могут возникнуть со всеми [пенсионного обеспечения StaffHub вопросы и ответы](microsoft-staffhub-to-be-retired.md) .</span><span class="sxs-lookup"><span data-stu-id="7b002-118">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span> 

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="7b002-119">Что нужно знать о переход к группам</span><span class="sxs-lookup"><span data-stu-id="7b002-119">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="7b002-120">Когда следует переместить в группы</span><span class="sxs-lookup"><span data-stu-id="7b002-120">When to move to Teams</span></span>

<span data-ttu-id="7b002-121">Начиная с 1 октября 2019, StaffHub будет из эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="7b002-121">Effective October 1, 2019, StaffHub will be retired.</span></span> <span data-ttu-id="7b002-122">Мы рекомендуем вам начать работу с группами сегодня и начните для переноса групп и пользователей из StaffHub вашей организации.</span><span class="sxs-lookup"><span data-stu-id="7b002-122">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="7b002-123">С помощью которого компонент наиболее часто используемые в StaffHub управление планированием мы рекомендуем использовать приложение смен в группах Переход вперед.</span><span class="sxs-lookup"><span data-stu-id="7b002-123">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="7b002-124">Что изменилось по группам</span><span class="sxs-lookup"><span data-stu-id="7b002-124">What is moved to Teams</span></span>

<span data-ttu-id="7b002-125">Сведения о пользователе, сведения о расписаниях и чата и файловых данных выполнившим переход к группам.</span><span class="sxs-lookup"><span data-stu-id="7b002-125">User details, schedule information, and chat and file data are transitioned to Teams.</span></span> <span data-ttu-id="7b002-126">Это включает в себя членства группы, группы расписаний и конференции и файлы из за последние 90 дней.</span><span class="sxs-lookup"><span data-stu-id="7b002-126">This includes team membership, team schedules, and chats and files from the last 90 days.</span></span>

<span data-ttu-id="7b002-127">Для любой группы StaffHub должно соответствующие группы Office 365.</span><span class="sxs-lookup"><span data-stu-id="7b002-127">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="7b002-128">Если группа StaffHub не имеет группу Office 365, связанные с ним, одно для автоматически создается для поддержки перехода.</span><span class="sxs-lookup"><span data-stu-id="7b002-128">If a StaffHub team doesn't have an Office 365 Group associated with it, one is automatically created for you to support the transition.</span></span> <span data-ttu-id="7b002-129">Учитывая разница в группы и группы имен между рабочими группами и StaffHub, может отображаться имя разные группы в группах.</span><span class="sxs-lookup"><span data-stu-id="7b002-129">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span>

<span data-ttu-id="7b002-130">При переходе группам из StaffHub групп пользователи больше не будут иметь доступ к своим расписаниям в StaffHub и перенаправляются на смены в группах.</span><span class="sxs-lookup"><span data-stu-id="7b002-130">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="7b002-131">Мы рекомендуем это изменение связи между организациями для сведения к минимуму нарушения нормального функционирования и рекомендация для освоения и их изучение группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="7b002-131">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span>

## <a name="prepare"></a><span data-ttu-id="7b002-132">Подготовка</span><span class="sxs-lookup"><span data-stu-id="7b002-132">Prepare</span></span>

<span data-ttu-id="7b002-133">Вот как подготовить для перемещения по группам.</span><span class="sxs-lookup"><span data-stu-id="7b002-133">Here's how to prepare for the move to Teams.</span></span>

### <a name="assign-teams-licenses"></a><span data-ttu-id="7b002-134">Назначение лицензий Teams</span><span class="sxs-lookup"><span data-stu-id="7b002-134">Assign Teams licenses</span></span>

<span data-ttu-id="7b002-135">Каждый пользователь должен иметь лицензию Microsoft 365 или Office 365, активных с [подходящими плана](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) и должны быть назначены лицензии групп.</span><span class="sxs-lookup"><span data-stu-id="7b002-135">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan ](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="7b002-136">Назначение групп лицензии пользователям предоставляет их доступ к группам.</span><span class="sxs-lookup"><span data-stu-id="7b002-136">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="7b002-137">Управление лицензиями групп в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7b002-137">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="7b002-138">Для получения дополнительных сведений см. [Управление доступом пользователей к группам](../../user-access.md).</span><span class="sxs-lookup"><span data-stu-id="7b002-138">To learn more, see [Manage user access to Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7b002-139">Если организация использует Скайп для бизнеса и вы не можете переместить всех пользователей в группы, можно включить группами для сотрудники организации Firstline пользователей, которые можно выполнять команды наряду с Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7b002-139">If your organization uses Skype for Business and you’re not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="7b002-140">В этом режиме сосуществования называется *острова*каждого клиентского приложения действует как отдельное решение.</span><span class="sxs-lookup"><span data-stu-id="7b002-140">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="7b002-141">Для получения дополнительных сведений см [понять, групп и Скайп для взаимодействие и сосуществование бизнеса](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="7b002-141">To learn more, see [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a><span data-ttu-id="7b002-142">Предоставления учетных записей для StaffHub пользователей, у которых нет удостоверение в Azure AD</span><span class="sxs-lookup"><span data-stu-id="7b002-142">Provision accounts for StaffHub users who don't have an identity in Azure AD</span></span>

<span data-ttu-id="7b002-143">Каждый член рабочей группы и диспетчера должна иметь удостоверение в Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="7b002-143">Each manager and team member must have an identity in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="7b002-144">Если пользователь еще не имеет удостоверение в Azure AD, Подготовка учетной записи для них.</span><span class="sxs-lookup"><span data-stu-id="7b002-144">If a user doesn't already have an identity in Azure AD, provision an account for them.</span></span> <span data-ttu-id="7b002-145">Выполните описанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="7b002-145">Here's how.</span></span>

- <span data-ttu-id="7b002-146">StaffHub группы владельцев и руководителей проектов можно преобразовать пустой, так и неактивных учетной записи и связать его подготовленных учетной записи в StaffHub, изменив адрес электронной почты пользователя допустимое имя участника-пользователя на странице параметров группы StaffHub.</span><span class="sxs-lookup"><span data-stu-id="7b002-146">StaffHub team owners and managers can convert a dummy or inactive account and link it to a provisioned account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="7b002-147">"Администраторы" можно запустить [Add StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) и [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) командлетов для удаления учетной записи не подготовлен из группы StaffHub и добавьте учетную запись обратно с помощью имени участника-пользователя.</span><span class="sxs-lookup"><span data-stu-id="7b002-147">Admins can run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) and [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) cmdlets to remove a non-provisioned account from a StaffHub team and add the account back by using the UPN.</span></span>

### <a name="install-the-staffhub-powershell-module"></a><span data-ttu-id="7b002-148">Установка модуля StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b002-148">Install the StaffHub PowerShell module</span></span>

<span data-ttu-id="7b002-149">Если вы еще не установлен, [установите модуль StaffHub PowerShell](install-the-staffhub-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="7b002-149">If you haven't already, [install the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span>

<span data-ttu-id="7b002-150">При перемещении группы StaffHub запроса на перемещение проверяет наличие необходимых компонентов.</span><span class="sxs-lookup"><span data-stu-id="7b002-150">When you move a StaffHub team, the move request checks for prerequisites.</span></span> <span data-ttu-id="7b002-151">Вот причины при запрос на перемещение:</span><span class="sxs-lookup"><span data-stu-id="7b002-151">Here's reasons why a move request may fail:</span></span>

- <span data-ttu-id="7b002-152">Пользователь выполнил вход не глобального администратора</span><span class="sxs-lookup"><span data-stu-id="7b002-152">The signed-in user is not a global admin</span></span>
- <span data-ttu-id="7b002-153">Команды отключена для всех пользователей в клиента</span><span class="sxs-lookup"><span data-stu-id="7b002-153">Teams is disabled for all users in the tenant</span></span>
- <span data-ttu-id="7b002-154">Создание группы Office 365 отключен в клиента</span><span class="sxs-lookup"><span data-stu-id="7b002-154">Office 365 Groups creation is disabled in the tenant</span></span>
- <span data-ttu-id="7b002-155">StaffHub teamId не является допустимым или не имеет членов</span><span class="sxs-lookup"><span data-stu-id="7b002-155">The StaffHub teamId is not valid or has no members</span></span>
- <span data-ttu-id="7b002-156">Группа StaffHub содержит элементы, которые не связаны учетную запись Azure AD</span><span class="sxs-lookup"><span data-stu-id="7b002-156">The StaffHub team includes members that aren't linked to an Azure AD account</span></span>  

## <a name="run-a-pilot"></a><span data-ttu-id="7b002-157">Запуск пилотного проекта</span><span class="sxs-lookup"><span data-stu-id="7b002-157">Run a pilot</span></span>

<span data-ttu-id="7b002-158">Мы рекомендуем запустить путем перемещения два или три StaffHub группами для выбранных групп первыми.</span><span class="sxs-lookup"><span data-stu-id="7b002-158">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="7b002-159">Пилотных помогает уточнение плана перехода и убедитесь, что вы готовы для перемещения групп StaffHub вашей организации по группам.</span><span class="sxs-lookup"><span data-stu-id="7b002-159">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="7b002-160">Он также определяет чемпионатов, которые могут помочь обеспечить принятие внутри организации.</span><span class="sxs-lookup"><span data-stu-id="7b002-160">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="7b002-161">Если вы малого бизнеса, кто может не поэтапный подход, действия, описанные в этом разделе может быть необходимо переход от StaffHub на группы.</span><span class="sxs-lookup"><span data-stu-id="7b002-161">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="7b002-162">Определение пилотных групп</span><span class="sxs-lookup"><span data-stu-id="7b002-162">Identify pilot teams</span></span>

<span data-ttu-id="7b002-163">Доступ к идентификации два или три пилотных рабочих групп.</span><span class="sxs-lookup"><span data-stu-id="7b002-163">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="7b002-164">Всем участникам группы следует сохранить, используя смен в группах для управления своим расписаниям и общения и совместной работы друг с другом.</span><span class="sxs-lookup"><span data-stu-id="7b002-164">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="7b002-165">Определение группы чемпионатов</span><span class="sxs-lookup"><span data-stu-id="7b002-165">Identify team champions</span></span>

<span data-ttu-id="7b002-166">Определение чемпионатов в пилотном командах и прикрепления их помогут Пропаганда смены.</span><span class="sxs-lookup"><span data-stu-id="7b002-166">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="7b002-167">Группа чемпионатов отношусь они выполните общего доступа к собственные предназначены для предложения поддержка и рекомендации для участников группы.</span><span class="sxs-lookup"><span data-stu-id="7b002-167">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="7b002-168">Группа чемпионатов может быть группы владельцев и руководителей.</span><span class="sxs-lookup"><span data-stu-id="7b002-168">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="7b002-169">Группы чемпионатов убедитесь, участники группы: настройка по времени, выделенного для все, чтобы [получить группам клиентов](../../get-clients.md), войти в группы и извлечение своих расписаний смены и начать разговор с друг с другом.</span><span class="sxs-lookup"><span data-stu-id="7b002-169">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="7b002-170">Пользователи, имеющие опыт работы с StaffHub будет запущено и работает быстро смены.</span><span class="sxs-lookup"><span data-stu-id="7b002-170">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="7b002-171">Можно также указать их для [Смены](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) для получения дополнительной поддержки.</span><span class="sxs-lookup"><span data-stu-id="7b002-171">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team-coming-soon"></a><span data-ttu-id="7b002-172">Перемещение группы StaffHub (ожидается в ближайшее время)</span><span class="sxs-lookup"><span data-stu-id="7b002-172">Move a StaffHub team (coming soon)</span></span>

<span data-ttu-id="7b002-173">Используйте следующие действия для перемещения одного StaffHub группы за раз.</span><span class="sxs-lookup"><span data-stu-id="7b002-173">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="7b002-174">Мы рекомендуем этот подход для пилотного групп.</span><span class="sxs-lookup"><span data-stu-id="7b002-174">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="7b002-175">Более поздних версий когда вы будете готовы продолжить группами StaffHub вашей организации, просмотрите [Перемещение ваших команд StaffHub](#move-your-staffhub-teams-coming-soon) инструкции по перемещения нескольких групп за раз.</span><span class="sxs-lookup"><span data-stu-id="7b002-175">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams-coming-soon) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="7b002-176">Выполните следующие действия, чтобы переместить StaffHub группы.</span><span class="sxs-lookup"><span data-stu-id="7b002-176">Run the following to move a StaffHub team.</span></span>

```
Move-StaffHubTeam -TeamId <String>

Sample:

Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

<span data-ttu-id="7b002-177">Ниже приведен пример, вы получаете при отправке запрос на перемещение группы StaffHub группы ответа.</span><span class="sxs-lookup"><span data-stu-id="7b002-177">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

<span data-ttu-id="7b002-178">Чтобы проверить состояние запроса на перемещение, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="7b002-178">To check the status of a move request, run the following.</span></span>

```
Get-TeamMigrationJobStatus <String>

Sample:
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"

```

<span data-ttu-id="7b002-179">Ниже приведен пример ответа, которые будут выдаваться при перемещении находится в стадии разработки.</span><span class="sxs-lookup"><span data-stu-id="7b002-179">Here's an example of the response you get when a move is in progress.</span></span>

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

## <a name="make-the-transition-from-staffhub-to-teams"></a><span data-ttu-id="7b002-180">Переход от StaffHub по группам</span><span class="sxs-lookup"><span data-stu-id="7b002-180">Make the transition from StaffHub to Teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="7b002-181">Сведения о вызовет</span><span class="sxs-lookup"><span data-stu-id="7b002-181">Raise awareness</span></span>

<span data-ttu-id="7b002-182">При вы готовы к выходит за пределы пилотных групп и перемещение групп StaffHub вашей организации командами, важно сначала передачи изменения в организации.</span><span class="sxs-lookup"><span data-stu-id="7b002-182">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="7b002-183">Распространение слов о смены и перехода к группам для возведения сведения о, создания волнение и внедрения.</span><span class="sxs-lookup"><span data-stu-id="7b002-183">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams-coming-soon"></a><span data-ttu-id="7b002-184">Перемещение ваших команд StaffHub (ожидается в ближайшее время)</span><span class="sxs-lookup"><span data-stu-id="7b002-184">Move your StaffHub teams (coming soon)</span></span>

<span data-ttu-id="7b002-185">Используйте следующие действия для перемещения групп StaffHub в пакетном режиме.</span><span class="sxs-lookup"><span data-stu-id="7b002-185">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="7b002-186">Можно переместить группами StaffHub вашей организации, либо переместите определенными группами StaffHub.</span><span class="sxs-lookup"><span data-stu-id="7b002-186">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="7b002-187">Если вы хотите переместить StaffHub групп по одному, ознакомьтесь со [Перемещение группы StaffHub](#move-a-staffhub-team-coming-soon).</span><span class="sxs-lookup"><span data-stu-id="7b002-187">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team-coming-soon).</span></span>

#### <a name="move-all-staffhub-teams-coming-soon"></a><span data-ttu-id="7b002-188">Переместите все группы StaffHub (ожидается в ближайшее время)</span><span class="sxs-lookup"><span data-stu-id="7b002-188">Move all StaffHub teams (coming soon)</span></span>

<span data-ttu-id="7b002-189">Выполните следующие действия, чтобы получить список всех групп StaffHub в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="7b002-189">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="7b002-190">Затем выполните следующие действия, чтобы переместить все группы.</span><span class="sxs-lookup"><span data-stu-id="7b002-190">Then, run the following to move all teams.</span></span>

```
$StaffHubTeams | foreach {Move-StaffHubTeam -TeamId {$_.Id}}
```

<span data-ttu-id="7b002-191">Ниже приведен пример ответа.</span><span class="sxs-lookup"><span data-stu-id="7b002-191">Here's an example of the response.</span></span>

<span data-ttu-id="7b002-192">Любой рабочей группы, который уже был перемещен в группы или уже существует в группах jobId будет иметь значение «null» задание не требуется отправить для перемещения этой группы.</span><span class="sxs-lookup"><span data-stu-id="7b002-192">For any team that was already moved to Teams or already exists in Teams, the jobId will be "null" as a job doesn't need to be submitted to move that team.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams-coming-soon"></a><span data-ttu-id="7b002-193">Перемещение определенными группами StaffHub (ожидается в ближайшее время)</span><span class="sxs-lookup"><span data-stu-id="7b002-193">Move specific StaffHub teams (coming soon)</span></span>

<span data-ttu-id="7b002-194">Выполните следующие действия, чтобы получить список всех групп StaffHub идентификаторы в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="7b002-194">Run the following to get a list of all StaffHub team Ids in your organization.</span></span>

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="7b002-195">В списке результатов, возвращаемых `Get-StaffHubteamsForTenant` командлет вы выполнили ранее идентификаторы группы, которую нужно переместить и добавить их в файл с разделителями-запятыми (CSV).</span><span class="sxs-lookup"><span data-stu-id="7b002-195">In the results returned by the `Get-StaffHubteamsForTenant` cmdlet you ran earlier, select the Team Ids you want to move, and then add them to a comma-separated values (CSV) file.</span></span>

<span data-ttu-id="7b002-196">Ниже приведен пример форматирования CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="7b002-196">Here's an example of how the CSV file should be formatted.</span></span>

|<span data-ttu-id="7b002-197">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="7b002-197">Id</span></span>  |
|---------|
|<span data-ttu-id="7b002-198">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="7b002-198">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="7b002-199">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="7b002-199">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="7b002-200">9 TEAM_b42d0fa2 - 0fc-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="7b002-200">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="7b002-201">9 TEAM_b42d0fa2 - 0fc-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="7b002-201">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="7b002-202">После создания CSV-файл, выполните следующие действия, чтобы переместить команды, указанной в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="7b002-202">After you create the CSV file, run the following to move the teams you specified in the CSV file.</span></span>

```
Import-Csv .\teams.txt | foreach {Move-StaffHubTeam -TeamdId {$_.Id}}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams-coming-soon"></a><span data-ttu-id="7b002-203">Убедитесь, что группа разработчиков StaffHub будут перемещены в группы (ожидается в ближайшее время)</span><span class="sxs-lookup"><span data-stu-id="7b002-203">Confirm that your StaffHub teams have moved to Teams (coming soon)</span></span>

<span data-ttu-id="7b002-204">Выполните следующие действия, чтобы получить список всех групп в смен в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="7b002-204">Run the following to get a list of all teams in Shifts in your organization.</span></span> 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

## <a name="monitor-teams-usage"></a><span data-ttu-id="7b002-205">Наблюдение за использованием групп</span><span class="sxs-lookup"><span data-stu-id="7b002-205">Monitor Teams usage</span></span>

<span data-ttu-id="7b002-206">Отчеты об использовании помогут вам лучше понять особенности использования и предоставить дополнительная информация о том, куда определять приоритеты обучения и обмена данными между организациями.</span><span class="sxs-lookup"><span data-stu-id="7b002-206">Usage reports can help you better understand usage patterns and give you insights on where to prioritize training and communication efforts across your organization.</span></span> <span data-ttu-id="7b002-207">Поскольку смены приложения в группах, можно просмотреть использования по группам отчетов.</span><span class="sxs-lookup"><span data-stu-id="7b002-207">Because Shifts is an app in Teams, you can view usage through Teams reports.</span></span> <span data-ttu-id="7b002-208">Для получения дополнительных сведений см [групп отчетов в центре администрирования группами Майкрософт](../../teams-analytics-and-reports/teams-reporting-reference.md) и [отчеты об активности групп в центре администрирования Microsoft 365](../../teams-activity-reports.md).</span><span class="sxs-lookup"><span data-stu-id="7b002-208">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="7b002-209">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="7b002-209">Related topics</span></span>
- [<span data-ttu-id="7b002-210">Прекращение поддержки Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="7b002-210">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="7b002-211">Управление приложением "Смены" для вашей организации в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7b002-211">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="7b002-212">Справочник по StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b002-212">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
