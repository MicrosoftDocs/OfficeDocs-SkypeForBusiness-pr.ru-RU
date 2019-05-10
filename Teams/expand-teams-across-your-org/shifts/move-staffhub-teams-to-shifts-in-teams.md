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
ms.openlocfilehash: 74a9b23479f5357c0014ef5ef88b3f5da03ace7f
ms.sourcegitcommit: b2acf18ba6487154ebb4ee46938e96dc56cb2c9a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/09/2019
ms.locfileid: "33865055"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="5e77f-103">Перемещение ваших команд Microsoft StaffHub смены в группах Майкрософт</span><span class="sxs-lookup"><span data-stu-id="5e77f-103">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5e77f-104">Начиная с 1 октября 2019, Microsoft StaffHub будет из эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="5e77f-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="5e77f-105">Мы создаем StaffHub возможностей в группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5e77f-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="5e77f-106">В настоящее время группы включает в себя приложение смены для управление планированием и дополнительные возможности будут развернуты со временем.</span><span class="sxs-lookup"><span data-stu-id="5e77f-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="5e77f-107">StaffHub перестанет работать для всех пользователей на 1 октября 2019.</span><span class="sxs-lookup"><span data-stu-id="5e77f-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="5e77f-108">Кто-то пытается открыть StaffHub отображается сообщение, предлагая загрузить групп.</span><span class="sxs-lookup"><span data-stu-id="5e77f-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="5e77f-109">Для получения дополнительных сведений см [Microsoft StaffHub из эксплуатации](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="5e77f-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

> <span data-ttu-id="5e77f-110">Возможности, описанные в этой статье еще не была выпущена.</span><span class="sxs-lookup"><span data-stu-id="5e77f-110">The capability discussed in this article hasn't yet been released.</span></span> <span data-ttu-id="5e77f-111">— Это была объявлена и в ближайшее время, в середину мая 2019.</span><span class="sxs-lookup"><span data-stu-id="5e77f-111">It's been announced, and is coming soon, towards the middle of May 2019.</span></span> <span data-ttu-id="5e77f-112">Если вы являетесь администратором, вы можете узнать при этом будут доступны в центре сообщений (в [центре администрирования Microsoft 365](https://portal.office.com/adminportal/home)).</span><span class="sxs-lookup"><span data-stu-id="5e77f-112">If you're an admin, you can find out when this will be available in the Message Center (in the [Microsoft 365 admin center](https://portal.office.com/adminportal/home)).</span></span>

<span data-ttu-id="5e77f-113">Приложение смен в группах предоставляет простой подход к управлению расписания и постоянного потока меняет местами shift и отмены собраний, которые происходят на ежедневной основе.</span><span class="sxs-lookup"><span data-stu-id="5e77f-113">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="5e77f-114">Участники группы могут получить доступ к их расписание и сведения о shift непосредственно в приложении и на их устройств, чтобы задать свои параметры управлять своим расписаниям и время запроса из системы.</span><span class="sxs-lookup"><span data-stu-id="5e77f-114">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="5e77f-115">В этой статье описывается перемещение групп StaffHub вашей организации и планирование данных для смены в группах.</span><span class="sxs-lookup"><span data-stu-id="5e77f-115">This article walks you through how to move your organization’s StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="5e77f-116">Будет ли вы малого бизнеса с одним или двумя группами StaffHub или крупном предприятии сотни StaffHub группам, здесь вы найдете рекомендации администратора, необходимые для перехода к группам успешно.</span><span class="sxs-lookup"><span data-stu-id="5e77f-116">Whether you’re a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you’ll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="5e77f-117">Должен быть глобального администратора, чтобы выполнить действия, описанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="5e77f-117">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="5e77f-118">Если это еще не сделано, нужно получить ответы на вопросы, которые могут возникнуть со всеми [пенсионного обеспечения StaffHub вопросы и ответы](microsoft-staffhub-to-be-retired.md) .</span><span class="sxs-lookup"><span data-stu-id="5e77f-118">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span> 

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="5e77f-119">Что нужно знать о переход к группам</span><span class="sxs-lookup"><span data-stu-id="5e77f-119">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="5e77f-120">Когда следует переместить в группы</span><span class="sxs-lookup"><span data-stu-id="5e77f-120">When to move to Teams</span></span>

<span data-ttu-id="5e77f-121">Начиная с 1 октября 2019, StaffHub будет из эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="5e77f-121">Effective October 1, 2019, StaffHub will be retired.</span></span> <span data-ttu-id="5e77f-122">Мы рекомендуем вам начать работу с группами сегодня и начните для переноса групп и пользователей из StaffHub вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5e77f-122">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="5e77f-123">С помощью которого компонент наиболее часто используемые в StaffHub управление планированием мы рекомендуем использовать приложение смен в группах Переход вперед.</span><span class="sxs-lookup"><span data-stu-id="5e77f-123">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="5e77f-124">Что изменилось по группам</span><span class="sxs-lookup"><span data-stu-id="5e77f-124">What is moved to Teams</span></span>

<span data-ttu-id="5e77f-125">Сведения о пользователе, сведения о расписаниях и чата и файловых данных выполнившим переход к группам.</span><span class="sxs-lookup"><span data-stu-id="5e77f-125">User details, schedule information, and chat and file data are transitioned to Teams.</span></span> <span data-ttu-id="5e77f-126">Это включает в себя членства группы, группы расписаний и конференции и файлы из за последние 90 дней.</span><span class="sxs-lookup"><span data-stu-id="5e77f-126">This includes team membership, team schedules, and chats and files from the last 90 days.</span></span>

<span data-ttu-id="5e77f-127">Для любой группы StaffHub должно соответствующие группы Office 365.</span><span class="sxs-lookup"><span data-stu-id="5e77f-127">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="5e77f-128">Если группа StaffHub не имеет группу Office 365, связанные с ним, одно для автоматически создается для поддержки перехода.</span><span class="sxs-lookup"><span data-stu-id="5e77f-128">If a StaffHub team doesn't have an Office 365 Group associated with it, one is automatically created for you to support the transition.</span></span> <span data-ttu-id="5e77f-129">Учитывая разница в группы и группы имен между рабочими группами и StaffHub, может отображаться имя разные группы в группах.</span><span class="sxs-lookup"><span data-stu-id="5e77f-129">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span>

<span data-ttu-id="5e77f-130">При переходе группам из StaffHub групп пользователи больше не будут иметь доступ к своим расписаниям в StaffHub и перенаправляются на смены в группах.</span><span class="sxs-lookup"><span data-stu-id="5e77f-130">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="5e77f-131">Мы рекомендуем это изменение связи между организациями для сведения к минимуму нарушения нормального функционирования и рекомендация для освоения и их изучение группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="5e77f-131">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span> <span data-ttu-id="5e77f-132">Если у вас есть Azure AD Premium, можно [выполнить отчет,](run-report-to-show-staffhub-usage.md) Чтобы получить список StaffHub пользователей в вашей организации, которые необходимо знать об этом изменении.</span><span class="sxs-lookup"><span data-stu-id="5e77f-132">If you have Azure AD Premium, you can [run a report](run-report-to-show-staffhub-usage.md) to get a list of StaffHub users in your organization who need to know about this change.</span></span>  

<span data-ttu-id="5e77f-133">Нет параметр не отката после перемещения групп StaffHub группами.</span><span class="sxs-lookup"><span data-stu-id="5e77f-133">There's no rollback option after you move a StaffHub team to Teams.</span></span>

### <a name="user-experience-when-you-move-a-team"></a><span data-ttu-id="5e77f-134">Взаимодействие с пользователем при перемещении группы</span><span class="sxs-lookup"><span data-stu-id="5e77f-134">User experience when you move a team</span></span>

<span data-ttu-id="5e77f-135">Нет минимальное время простоя (менее одной секунды, если они существуют для всех) для пользователей при их команды переключения с StaffHub смены в группах.</span><span class="sxs-lookup"><span data-stu-id="5e77f-135">There's minimal downtime (less than a second, if any at all) for users when their team is switched from StaffHub to Shifts in Teams.</span></span> <span data-ttu-id="5e77f-136">Пользователи по-прежнему с помощью StaffHub вплоть до завершения перемещения по группам.</span><span class="sxs-lookup"><span data-stu-id="5e77f-136">Users can continue using StaffHub until the move to Teams is completed.</span></span> <span data-ttu-id="5e77f-137">После завершения перемещения участники группы будут видеть сообщения, чтобы сообщить им о необходимости начать работу с использованием смен в группах для доступа к своим расписание команды.</span><span class="sxs-lookup"><span data-stu-id="5e77f-137">When the move is completed, team members will see a message to let them know that they need to start using Shifts in Teams to access their team schedule.</span></span> <span data-ttu-id="5e77f-138">Ниже приведен пример сообщения, которые пользователи увидят.</span><span class="sxs-lookup"><span data-stu-id="5e77f-138">Here's an example of the message that users see.</span></span>

<span data-ttu-id="5e77f-139">![Пример сообщения, которое будут видеть пользователи в StaffHub после перемещения групп StaffHub группами.] (../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Пример сообщения, которые пользователи увидят в StaffHub после перемещения групп StaffHub групп")</span><span class="sxs-lookup"><span data-stu-id="5e77f-139">![Example of the message that users see in StaffHub after the StaffHub team is moved to Teams. ](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Example of the message that users see in StaffHub after the StaffHub team is moved to Teams")</span></span>

## <a name="prepare"></a><span data-ttu-id="5e77f-140">Подготовка</span><span class="sxs-lookup"><span data-stu-id="5e77f-140">Prepare</span></span>

<span data-ttu-id="5e77f-141">Вот как подготовить для перемещения по группам.</span><span class="sxs-lookup"><span data-stu-id="5e77f-141">Here's how to prepare for the move to Teams.</span></span>

### <a name="assign-teams-licenses"></a><span data-ttu-id="5e77f-142">Назначение лицензий Teams</span><span class="sxs-lookup"><span data-stu-id="5e77f-142">Assign Teams licenses</span></span>

<span data-ttu-id="5e77f-143">Каждый пользователь должен иметь лицензию Microsoft 365 или Office 365, активных с [подходящими плана](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) и должны быть назначены лицензии групп.</span><span class="sxs-lookup"><span data-stu-id="5e77f-143">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan ](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="5e77f-144">Назначение групп лицензии пользователям предоставляет их доступ к группам.</span><span class="sxs-lookup"><span data-stu-id="5e77f-144">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="5e77f-145">Управление лицензиями групп в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5e77f-145">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="5e77f-146">Для получения дополнительных сведений см. [Управление доступом пользователей к группам](../../user-access.md).</span><span class="sxs-lookup"><span data-stu-id="5e77f-146">To learn more, see [Manage user access to Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5e77f-147">Если организация использует Скайп для бизнеса и вы не можете переместить всех пользователей в группы, можно включить группами для сотрудники организации Firstline пользователей, которые можно выполнять команды наряду с Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="5e77f-147">If your organization uses Skype for Business and you’re not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="5e77f-148">В этом режиме сосуществования называется *острова*каждого клиентского приложения действует как отдельное решение.</span><span class="sxs-lookup"><span data-stu-id="5e77f-148">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="5e77f-149">Для получения дополнительных сведений см [понять, групп и Скайп для взаимодействие и сосуществование бизнеса](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="5e77f-149">To learn more, see [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a><span data-ttu-id="5e77f-150">Предоставления учетных записей для StaffHub пользователей, у которых нет удостоверение в Azure AD</span><span class="sxs-lookup"><span data-stu-id="5e77f-150">Provision accounts for StaffHub users who don't have an identity in Azure AD</span></span>

<span data-ttu-id="5e77f-151">Каждый член рабочей группы и диспетчера должна иметь удостоверение в Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="5e77f-151">Each manager and team member must have an identity in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="5e77f-152">Если пользователь еще не имеет удостоверение в Azure AD, Подготовка учетной записи для них.</span><span class="sxs-lookup"><span data-stu-id="5e77f-152">If a user doesn't already have an identity in Azure AD, provision an account for them.</span></span> <span data-ttu-id="5e77f-153">Выполните описанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="5e77f-153">Here's how.</span></span>

- <span data-ttu-id="5e77f-154">StaffHub группы владельцев и руководителей проектов можно преобразовать пустой, так и неактивных учетной записи и связать его подготовленных учетной записи в StaffHub, изменив адрес электронной почты пользователя допустимое имя участника-пользователя на странице параметров группы StaffHub.</span><span class="sxs-lookup"><span data-stu-id="5e77f-154">StaffHub team owners and managers can convert a dummy or inactive account and link it to a provisioned account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="5e77f-155">"Администраторы" можно запустить [Add StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) и [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) командлетов для удаления учетной записи не подготовлен из группы StaffHub и добавьте учетную запись обратно с помощью имени участника-пользователя.</span><span class="sxs-lookup"><span data-stu-id="5e77f-155">Admins can run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) and [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) cmdlets to remove a non-provisioned account from a StaffHub team and add the account back by using the UPN.</span></span>

### <a name="install-the-staffhub-powershell-module"></a><span data-ttu-id="5e77f-156">Установка модуля StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="5e77f-156">Install the StaffHub PowerShell module</span></span>

<span data-ttu-id="5e77f-157">Если вы еще не установлен, [установите модуль StaffHub PowerShell](install-the-staffhub-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="5e77f-157">If you haven't already, [install the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span>

<span data-ttu-id="5e77f-158">При перемещении группы StaffHub запроса на перемещение проверяет наличие необходимых компонентов.</span><span class="sxs-lookup"><span data-stu-id="5e77f-158">When you move a StaffHub team, the move request checks for prerequisites.</span></span> <span data-ttu-id="5e77f-159">Вот причины при запрос на перемещение:</span><span class="sxs-lookup"><span data-stu-id="5e77f-159">Here's reasons why a move request may fail:</span></span>

- <span data-ttu-id="5e77f-160">Пользователь выполнил вход не глобального администратора</span><span class="sxs-lookup"><span data-stu-id="5e77f-160">The signed-in user is not a global admin</span></span>
- <span data-ttu-id="5e77f-161">Команды отключена для всех пользователей в клиента</span><span class="sxs-lookup"><span data-stu-id="5e77f-161">Teams is disabled for all users in the tenant</span></span>
- <span data-ttu-id="5e77f-162">Создание группы Office 365 отключен в клиента</span><span class="sxs-lookup"><span data-stu-id="5e77f-162">Office 365 Groups creation is disabled in the tenant</span></span>
- <span data-ttu-id="5e77f-163">StaffHub teamId не является допустимым или не имеет членов</span><span class="sxs-lookup"><span data-stu-id="5e77f-163">The StaffHub teamId is not valid or has no members</span></span>
- <span data-ttu-id="5e77f-164">Группа StaffHub содержит элементы, которые не связаны учетную запись Azure AD</span><span class="sxs-lookup"><span data-stu-id="5e77f-164">The StaffHub team includes members that aren't linked to an Azure AD account</span></span>  

## <a name="run-a-pilot"></a><span data-ttu-id="5e77f-165">Запуск пилотного проекта</span><span class="sxs-lookup"><span data-stu-id="5e77f-165">Run a pilot</span></span>

<span data-ttu-id="5e77f-166">Мы рекомендуем запустить путем перемещения два или три StaffHub группами для выбранных групп первыми.</span><span class="sxs-lookup"><span data-stu-id="5e77f-166">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="5e77f-167">Пилотных помогает уточнение плана перехода и убедитесь, что вы готовы для перемещения групп StaffHub вашей организации по группам.</span><span class="sxs-lookup"><span data-stu-id="5e77f-167">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="5e77f-168">Он также определяет чемпионатов, которые могут помочь обеспечить принятие внутри организации.</span><span class="sxs-lookup"><span data-stu-id="5e77f-168">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="5e77f-169">Если вы малого бизнеса, кто может не поэтапный подход, действия, описанные в этом разделе может быть необходимо переход от StaffHub на группы.</span><span class="sxs-lookup"><span data-stu-id="5e77f-169">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="5e77f-170">Определение пилотных групп</span><span class="sxs-lookup"><span data-stu-id="5e77f-170">Identify pilot teams</span></span>

<span data-ttu-id="5e77f-171">Доступ к идентификации два или три пилотных рабочих групп.</span><span class="sxs-lookup"><span data-stu-id="5e77f-171">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="5e77f-172">Всем участникам группы следует сохранить, используя смен в группах для управления своим расписаниям и общения и совместной работы друг с другом.</span><span class="sxs-lookup"><span data-stu-id="5e77f-172">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="5e77f-173">Определение группы чемпионатов</span><span class="sxs-lookup"><span data-stu-id="5e77f-173">Identify team champions</span></span>

<span data-ttu-id="5e77f-174">Определение чемпионатов в пилотном командах и прикрепления их помогут Пропаганда смены.</span><span class="sxs-lookup"><span data-stu-id="5e77f-174">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="5e77f-175">Группа чемпионатов отношусь они выполните общего доступа к собственные предназначены для предложения поддержка и рекомендации для участников группы.</span><span class="sxs-lookup"><span data-stu-id="5e77f-175">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="5e77f-176">Группа чемпионатов может быть группы владельцев и руководителей.</span><span class="sxs-lookup"><span data-stu-id="5e77f-176">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="5e77f-177">Группы чемпионатов убедитесь, участники группы: настройка по времени, выделенного для все, чтобы [получить группам клиентов](../../get-clients.md), войти в группы и извлечение своих расписаний смены и начать разговор с друг с другом.</span><span class="sxs-lookup"><span data-stu-id="5e77f-177">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="5e77f-178">Пользователи, имеющие опыт работы с StaffHub будет запущено и работает быстро смены.</span><span class="sxs-lookup"><span data-stu-id="5e77f-178">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="5e77f-179">Можно также указать их для [Смены](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) для получения дополнительной поддержки.</span><span class="sxs-lookup"><span data-stu-id="5e77f-179">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team-coming-soon"></a><span data-ttu-id="5e77f-180">Перемещение группы StaffHub (ожидается в ближайшее время)</span><span class="sxs-lookup"><span data-stu-id="5e77f-180">Move a StaffHub team (coming soon)</span></span>

<span data-ttu-id="5e77f-181">Используйте следующие действия для перемещения одного StaffHub группы за раз.</span><span class="sxs-lookup"><span data-stu-id="5e77f-181">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="5e77f-182">Мы рекомендуем этот подход для пилотного групп.</span><span class="sxs-lookup"><span data-stu-id="5e77f-182">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="5e77f-183">Более поздних версий когда вы будете готовы продолжить группами StaffHub вашей организации, просмотрите [Перемещение ваших команд StaffHub](#move-your-staffhub-teams-coming-soon) инструкции по перемещения нескольких групп за раз.</span><span class="sxs-lookup"><span data-stu-id="5e77f-183">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams-coming-soon) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="5e77f-184">Выполните следующие действия, чтобы переместить StaffHub группы.</span><span class="sxs-lookup"><span data-stu-id="5e77f-184">Run the following to move a StaffHub team.</span></span>

```
Move-StaffHubTeam -TeamId <String>

Sample:

Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

<span data-ttu-id="5e77f-185">Ниже приведен пример, вы получаете при отправке запрос на перемещение группы StaffHub группы ответа.</span><span class="sxs-lookup"><span data-stu-id="5e77f-185">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

<span data-ttu-id="5e77f-186">Чтобы проверить состояние запроса на перемещение, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="5e77f-186">To check the status of a move request, run the following.</span></span>

```
Get-TeamMigrationJobStatus <String>

Sample:
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"

```

<span data-ttu-id="5e77f-187">Ниже приведен пример ответа, которые будут выдаваться при перемещении находится в стадии разработки.</span><span class="sxs-lookup"><span data-stu-id="5e77f-187">Here's an example of the response you get when a move is in progress.</span></span>

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

## <a name="make-the-transition-from-staffhub-to-teams"></a><span data-ttu-id="5e77f-188">Переход от StaffHub по группам</span><span class="sxs-lookup"><span data-stu-id="5e77f-188">Make the transition from StaffHub to Teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="5e77f-189">Сведения о вызовет</span><span class="sxs-lookup"><span data-stu-id="5e77f-189">Raise awareness</span></span>

<span data-ttu-id="5e77f-190">При вы готовы к выходит за пределы пилотных групп и перемещение групп StaffHub вашей организации командами, важно сначала передачи изменения в организации.</span><span class="sxs-lookup"><span data-stu-id="5e77f-190">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="5e77f-191">Распространение слов о смены и перехода к группам для возведения сведения о, создания волнение и внедрения.</span><span class="sxs-lookup"><span data-stu-id="5e77f-191">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams-coming-soon"></a><span data-ttu-id="5e77f-192">Перемещение ваших команд StaffHub (ожидается в ближайшее время)</span><span class="sxs-lookup"><span data-stu-id="5e77f-192">Move your StaffHub teams (coming soon)</span></span>

<span data-ttu-id="5e77f-193">Используйте следующие действия для перемещения групп StaffHub в пакетном режиме.</span><span class="sxs-lookup"><span data-stu-id="5e77f-193">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="5e77f-194">Можно переместить группами StaffHub вашей организации, либо переместите определенными группами StaffHub.</span><span class="sxs-lookup"><span data-stu-id="5e77f-194">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="5e77f-195">Если вы хотите переместить StaffHub групп по одному, ознакомьтесь со [Перемещение группы StaffHub](#move-a-staffhub-team-coming-soon).</span><span class="sxs-lookup"><span data-stu-id="5e77f-195">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team-coming-soon).</span></span>

#### <a name="move-all-staffhub-teams-coming-soon"></a><span data-ttu-id="5e77f-196">Переместите все группы StaffHub (ожидается в ближайшее время)</span><span class="sxs-lookup"><span data-stu-id="5e77f-196">Move all StaffHub teams (coming soon)</span></span>

<span data-ttu-id="5e77f-197">Выполните следующие действия, чтобы получить список всех групп StaffHub в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5e77f-197">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="5e77f-198">Затем выполните следующие действия, чтобы переместить все группы.</span><span class="sxs-lookup"><span data-stu-id="5e77f-198">Then, run the following to move all teams.</span></span>

```
$StaffHubTeams | foreach {Move-StaffHubTeam -TeamId {$_.Id}}
```

<span data-ttu-id="5e77f-199">Ниже приведен пример ответа.</span><span class="sxs-lookup"><span data-stu-id="5e77f-199">Here's an example of the response.</span></span>

<span data-ttu-id="5e77f-200">Любой рабочей группы, который уже был перемещен в группы или уже существует в группах jobId будет иметь значение «null» задание не требуется отправить для перемещения этой группы.</span><span class="sxs-lookup"><span data-stu-id="5e77f-200">For any team that was already moved to Teams or already exists in Teams, the jobId will be "null" as a job doesn't need to be submitted to move that team.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams-coming-soon"></a><span data-ttu-id="5e77f-201">Перемещение определенными группами StaffHub (ожидается в ближайшее время)</span><span class="sxs-lookup"><span data-stu-id="5e77f-201">Move specific StaffHub teams (coming soon)</span></span>

<span data-ttu-id="5e77f-202">Выполните следующие действия, чтобы получить список всех групп StaffHub идентификаторы в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5e77f-202">Run the following to get a list of all StaffHub team Ids in your organization.</span></span>

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="5e77f-203">В списке результатов, возвращаемых `Get-StaffHubteamsForTenant` командлет вы выполнили ранее идентификаторы группы, которую нужно переместить и добавить их в файл с разделителями-запятыми (CSV).</span><span class="sxs-lookup"><span data-stu-id="5e77f-203">In the results returned by the `Get-StaffHubteamsForTenant` cmdlet you ran earlier, select the Team Ids you want to move, and then add them to a comma-separated values (CSV) file.</span></span>

<span data-ttu-id="5e77f-204">Ниже приведен пример форматирования CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="5e77f-204">Here's an example of how the CSV file should be formatted.</span></span>

|<span data-ttu-id="5e77f-205">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="5e77f-205">Id</span></span>  |
|---------|
|<span data-ttu-id="5e77f-206">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="5e77f-206">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="5e77f-207">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="5e77f-207">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="5e77f-208">9 TEAM_b42d0fa2 - 0fc-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="5e77f-208">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="5e77f-209">9 TEAM_b42d0fa2 - 0fc-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="5e77f-209">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="5e77f-210">После создания CSV-файл, выполните следующие действия, чтобы переместить команды, указанной в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="5e77f-210">After you create the CSV file, run the following to move the teams you specified in the CSV file.</span></span>

```
Import-Csv .\teams.txt | foreach {Move-StaffHubTeam -TeamdId {$_.Id}}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams-coming-soon"></a><span data-ttu-id="5e77f-211">Убедитесь, что группа разработчиков StaffHub будут перемещены в группы (ожидается в ближайшее время)</span><span class="sxs-lookup"><span data-stu-id="5e77f-211">Confirm that your StaffHub teams have moved to Teams (coming soon)</span></span>

<span data-ttu-id="5e77f-212">Выполните следующие действия, чтобы получить список всех групп в смен в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5e77f-212">Run the following to get a list of all teams in Shifts in your organization.</span></span> 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

## <a name="monitor-teams-usage"></a><span data-ttu-id="5e77f-213">Наблюдение за использованием групп</span><span class="sxs-lookup"><span data-stu-id="5e77f-213">Monitor Teams usage</span></span>

<span data-ttu-id="5e77f-214">Отчеты об использовании помогут вам лучше понять особенности использования и предоставить дополнительная информация о том, куда определять приоритеты обучения и обмена данными между организациями.</span><span class="sxs-lookup"><span data-stu-id="5e77f-214">Usage reports can help you better understand usage patterns and give you insights on where to prioritize training and communication efforts across your organization.</span></span> <span data-ttu-id="5e77f-215">Поскольку смены приложения в группах, можно просмотреть использования по группам отчетов.</span><span class="sxs-lookup"><span data-stu-id="5e77f-215">Because Shifts is an app in Teams, you can view usage through Teams reports.</span></span> <span data-ttu-id="5e77f-216">Для получения дополнительных сведений см [групп отчетов в центре администрирования группами Майкрософт](../../teams-analytics-and-reports/teams-reporting-reference.md) и [отчеты об активности групп в центре администрирования Microsoft 365](../../teams-activity-reports.md).</span><span class="sxs-lookup"><span data-stu-id="5e77f-216">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="5e77f-217">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="5e77f-217">Related topics</span></span>
- [<span data-ttu-id="5e77f-218">Прекращение поддержки Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="5e77f-218">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="5e77f-219">Управление приложением "Смены" для вашей организации в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5e77f-219">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="5e77f-220">Справочник по StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="5e77f-220">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
