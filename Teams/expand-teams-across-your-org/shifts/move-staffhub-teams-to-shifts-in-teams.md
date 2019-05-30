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
description: Сведения о том, как перемещаться по Microsoft StaffHub Teams и планировать данные для смены в Microsoft Teams.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: b6354c2edd4d8504aeb2c84715b982f6bf793d33
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548296"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="3b3f7-103">Перемещайте Microsoft StaffHub Teams по сменам в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3b3f7-103">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3b3f7-104">Начиная с 1 октября 2019 г. Корпорация Microsoft StaffHub будет прекращена.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="3b3f7-105">Мы создаем возможности StaffHub в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="3b3f7-106">Сегодня команды включают в себя приложение смен для управления планированием и дополнительные возможности, которые будут вычислены с течением времени.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="3b3f7-107">StaffHub перестанет работать для всех пользователей 1 октября 2019 г.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="3b3f7-108">Каждый, кто пытается открыть StaffHub, будет показывать сообщение, направленное на загрузку групп.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="3b3f7-109">Дополнительные сведения можно найти в [статье Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="3b3f7-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

> <span data-ttu-id="3b3f7-110">Возможности, описанные в этой статье, пока не были выпущены.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-110">The capability discussed in this article hasn't yet been released.</span></span> <span data-ttu-id="3b3f7-111">Это сообщение было объявлено и скоро вскоре будет выпущено в начале 2019 июня.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-111">It's been announced, and is coming soon, in early June 2019.</span></span> <span data-ttu-id="3b3f7-112">Если вы являетесь администратором, вы можете узнать, когда это будет доступно в центре сообщений (в [центре администрирования Microsoft 365](https://portal.office.com/adminportal/home)).</span><span class="sxs-lookup"><span data-stu-id="3b3f7-112">If you're an admin, you can find out when this will be available in the Message Center (in the [Microsoft 365 admin center](https://portal.office.com/adminportal/home)).</span></span>

<span data-ttu-id="3b3f7-113">Приложение «смена» в Teams предоставляет простой подход к управлению расписаниями и постоянным потоком сменных и отменяющих переходов, происходящих в повседневной основе.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-113">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="3b3f7-114">Участники групп могут получать доступ к своим расписаниям и сменам данных непосредственно в приложении, а также на разных устройствах для настройки их настроек, управления расписаниями и запроса времени.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-114">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="3b3f7-115">В этой статье рассказывается о том, как переместить StaffHub Teams в Организации и спланировать данные для смены в Teams.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-115">This article walks you through how to move your organization’s StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="3b3f7-116">Если вы занимаетесь малым предприятием из одной или двух групп StaffHub или крупного предприятия с сотнями StaffHub Teams, здесь вы найдете инструкции для администраторов, которые помогут вам успешно выполнить переход в Teams.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-116">Whether you’re a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you’ll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="3b3f7-117">Для выполнения действий, описанных в этой статье, необходимо быть глобальным администратором.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-117">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="3b3f7-118">Если вы еще не сделали этого, ознакомьтесь с разделами " [вопросы и](microsoft-staffhub-to-be-retired.md) ответы" в StaffHub о выбытиех для получения ответов на любые возникающие вопросы.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-118">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span> 

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="3b3f7-119">Что нужно знать о переходе в Teams</span><span class="sxs-lookup"><span data-stu-id="3b3f7-119">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="3b3f7-120">Переход в Teams</span><span class="sxs-lookup"><span data-stu-id="3b3f7-120">When to move to Teams</span></span>

<span data-ttu-id="3b3f7-121">Действующий 1 октября 2019 г. StaffHub будет прекращена.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-121">Effective October 1, 2019, StaffHub will be retired.</span></span> <span data-ttu-id="3b3f7-122">Мы рекомендуем вам приступить к работе с Teams сегодня и начать переход с групп и пользователей вашей организации из StaffHub.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-122">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="3b3f7-123">Управление расписаниями является наиболее часто используемой функцией StaffHub, поэтому мы рекомендуем использовать приложение "смены" в Teams для перемещения вперед.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-123">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="3b3f7-124">Что перемещается в Teams</span><span class="sxs-lookup"><span data-stu-id="3b3f7-124">What is moved to Teams</span></span>

<span data-ttu-id="3b3f7-125">Сведения о пользователе, сведения о расписании, а так же чат и данные файлов перемещаются в Teams.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-125">User details, schedule information, and chat and file data are transitioned to Teams.</span></span> <span data-ttu-id="3b3f7-126">Сюда входят участники рабочей группы, расписания групп, а также разговоры и файлы за последние 90 дней.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-126">This includes team membership, team schedules, and chats and files from the last 90 days.</span></span>

<span data-ttu-id="3b3f7-127">Каждой команде StaffHub нужна соответствующая группа Office 365.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-127">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="3b3f7-128">Если с группой StaffHub не связана группа Office 365, она будет автоматически создана для поддержки перехода.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-128">If a StaffHub team doesn't have an Office 365 Group associated with it, one is automatically created for you to support the transition.</span></span> <span data-ttu-id="3b3f7-129">С учетом различий в именовании групп и групп между группами и StaffHub в Teams может быть указано другое имя группы.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-129">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span>

<span data-ttu-id="3b3f7-130">По мере перевода групп из StaffHub в Teams пользователи больше не смогут получать доступ к своим расписаниям в StaffHub и перенаправляться на смены в Teams.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-130">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="3b3f7-131">Мы рекомендуем вам сообщать об этом изменении в своей организации, чтобы свести к минимуму перерывы и предоставить пользователям возможность принимать и изучать команды.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-131">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span> <span data-ttu-id="3b3f7-132">Если у вас есть Azure AD Premium, вы можете [запустить отчет](run-report-to-show-staffhub-usage.md) , чтобы получить список пользователей StaffHub в вашей организации, которым нужно знать об этом изменении.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-132">If you have Azure AD Premium, you can [run a report](run-report-to-show-staffhub-usage.md) to get a list of StaffHub users in your organization who need to know about this change.</span></span>  

<span data-ttu-id="3b3f7-133">После того как вы перемещаете группу StaffHub в Teams, вы не сможете выполнить откат.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-133">There's no rollback option after you move a StaffHub team to Teams.</span></span>

### <a name="user-experience-when-you-move-a-team"></a><span data-ttu-id="3b3f7-134">Взаимодействие с пользователем при перемещении команды</span><span class="sxs-lookup"><span data-stu-id="3b3f7-134">User experience when you move a team</span></span>

<span data-ttu-id="3b3f7-135">Минимальная продолжительность простоя (менее чем секунда, если она есть) для пользователей при переключении с StaffHub на смену в Teams.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-135">There's minimal downtime (less than a second, if any at all) for users when their team is switched from StaffHub to Shifts in Teams.</span></span> <span data-ttu-id="3b3f7-136">Пользователи могут продолжать пользоваться StaffHub, пока не завершится переход в Teams.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-136">Users can continue using StaffHub until the move to Teams is completed.</span></span> <span data-ttu-id="3b3f7-137">После завершения перемещения участники команды увидят сообщение о том, что они должны приступить к использованию смен в Teams, чтобы получить доступ к своему календарному плану.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-137">When the move is completed, team members will see a message to let them know that they need to start using Shifts in Teams to access their team schedule.</span></span> <span data-ttu-id="3b3f7-138">Ниже приведен пример сообщения, которое пользователи видят в StaffHub после перемещения группы StaffHub в Teams.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-138">Here's an example of the message that users see in StaffHub after the StaffHub team is moved to Teams.</span></span>

<span data-ttu-id="3b3f7-139">![Пример сообщения, которое видят пользователи.] (../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Пример сообщения, которое пользователи видят в StaffHub после перемещения группы StaffHub в Teams")</span><span class="sxs-lookup"><span data-stu-id="3b3f7-139">![Example of the message that users see.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Example of the message that users see in StaffHub after the StaffHub team is moved to Teams")</span></span>

## <a name="prepare"></a><span data-ttu-id="3b3f7-140">Подготовку</span><span class="sxs-lookup"><span data-stu-id="3b3f7-140">Prepare</span></span>

<span data-ttu-id="3b3f7-141">Вот как можно подготовиться к переходу на Teams.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-141">Here's how to prepare for the move to Teams.</span></span>

### <a name="assign-teams-licenses"></a><span data-ttu-id="3b3f7-142">Назначение лицензий Teams</span><span class="sxs-lookup"><span data-stu-id="3b3f7-142">Assign Teams licenses</span></span>

<span data-ttu-id="3b3f7-143">Каждый пользователь должен иметь действующую лицензию Microsoft 365 или Office 365 из [подходящего плана](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) , и ему должна быть назначена лицензия Teams.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-143">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan ](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="3b3f7-144">Назначение лицензии на команды пользователям предоставляет им доступ к Teams.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-144">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="3b3f7-145">Вы управляете лицензиями Teams в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-145">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="3b3f7-146">Дополнительные сведения можно найти в разделе [Управление доступом пользователей к Teams](../../user-access.md).</span><span class="sxs-lookup"><span data-stu-id="3b3f7-146">To learn more, see [Manage user access to Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3b3f7-147">Если в вашей организации используется Skype для бизнеса, и вы не готовы переместить всех пользователей в Teams, вы можете включить команды для сотрудников Firstline, которые смогут запускать команды вместе со Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-147">If your organization uses Skype for Business and you’re not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="3b3f7-148">В режиме совместного существования под названием *острова*все клиентские приложения работают как отдельные решения.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-148">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="3b3f7-149">Дополнительные сведения можно найти в статье [понимание групп, а также взаимодействие и совместимость Skype для бизнеса](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="3b3f7-149">To learn more, see [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a><span data-ttu-id="3b3f7-150">Подготовка учетных записей для пользователей StaffHub, у которых нет удостоверения в Azure AD</span><span class="sxs-lookup"><span data-stu-id="3b3f7-150">Provision accounts for StaffHub users who don't have an identity in Azure AD</span></span>

<span data-ttu-id="3b3f7-151">Каждый руководитель и участник команды должны иметь удостоверение в Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="3b3f7-151">Each manager and team member must have an identity in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="3b3f7-152">Если пользователь еще не имеет удостоверения в Azure AD, предоставьте для него учетную запись.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-152">If a user doesn't already have an identity in Azure AD, provision an account for them.</span></span> <span data-ttu-id="3b3f7-153">Выполните описанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-153">Here's how.</span></span>

- <span data-ttu-id="3b3f7-154">StaffHub владельцы и руководители групп могут преобразовать фиктивную или неактивную учетную запись и связать ее с учетной записью для подготовки в StaffHub, изменив адрес электронной почты пользователя на действительный UPN на странице StaffHub параметры группы.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-154">StaffHub team owners and managers can convert a dummy or inactive account and link it to a provisioned account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="3b3f7-155">Администраторы могут выполнять командлеты [Add-стаффхубмембер](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) и [Remove-стаффхубусер](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) для удаления неподготовленной учетной записи из группы StaffHub и повторного добавления учетной записи с помощью UPN.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-155">Admins can run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) and [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) cmdlets to remove a non-provisioned account from a StaffHub team and add the account back by using the UPN.</span></span>

### <a name="install-the-staffhub-powershell-module"></a><span data-ttu-id="3b3f7-156">Установка модуля StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="3b3f7-156">Install the StaffHub PowerShell module</span></span>

<span data-ttu-id="3b3f7-157">[Установите модуль PowerShell StaffHub](install-the-staffhub-powershell-module.md), если вы еще не сделали этого.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-157">If you haven't already, [install the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span>

<span data-ttu-id="3b3f7-158">Когда вы перемещаете группу StaffHub, запрос на перемещение проверяет наличие необходимых компонентов.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-158">When you move a StaffHub team, the move request checks for prerequisites.</span></span> <span data-ttu-id="3b3f7-159">Ниже приведены причины, по которым может произойти сбой запроса на перемещение.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-159">Here's reasons why a move request may fail:</span></span>

- <span data-ttu-id="3b3f7-160">Вошедшего в систему пользователя не является глобальным администратором</span><span class="sxs-lookup"><span data-stu-id="3b3f7-160">The signed-in user is not a global admin</span></span>
- <span data-ttu-id="3b3f7-161">Teams отключены для всех пользователей в клиенте</span><span class="sxs-lookup"><span data-stu-id="3b3f7-161">Teams is disabled for all users in the tenant</span></span>
- <span data-ttu-id="3b3f7-162">Создание групп Office 365 отключено в клиенте</span><span class="sxs-lookup"><span data-stu-id="3b3f7-162">Office 365 Groups creation is disabled in the tenant</span></span>
- <span data-ttu-id="3b3f7-163">Теамид StaffHub не является допустимым или не имеет пользователей</span><span class="sxs-lookup"><span data-stu-id="3b3f7-163">The StaffHub teamId is not valid or has no members</span></span>
- <span data-ttu-id="3b3f7-164">Группа StaffHub включает в себя пользователей, которые не связаны с учетной записью Azure AD</span><span class="sxs-lookup"><span data-stu-id="3b3f7-164">The StaffHub team includes members that aren't linked to an Azure AD account</span></span>  

## <a name="run-a-pilot"></a><span data-ttu-id="3b3f7-165">Запуск пилотного проекта</span><span class="sxs-lookup"><span data-stu-id="3b3f7-165">Run a pilot</span></span>

<span data-ttu-id="3b3f7-166">Мы рекомендуем начать с перемещения двух или трех групп StaffHub, чтобы выбрать группу ранних переходов.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-166">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="3b3f7-167">Работа с пилотной версией поможет вам уточнить план перехода и убедиться, что вы готовы переместить все StaffHub Teams вашей организации в Teams.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-167">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="3b3f7-168">Кроме того, он определяет лидерами, которые помогут вам облегчить внедрение в рамках своей организации.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-168">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="3b3f7-169">Если вы работаете в малом бизнесе, для которого не требуется поэтапный подход, действия, описанные в этом разделе, могут быть все, что нужно сделать, чтобы перейти с StaffHub на Teams.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-169">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="3b3f7-170">Определение пилотных команд</span><span class="sxs-lookup"><span data-stu-id="3b3f7-170">Identify pilot teams</span></span>

<span data-ttu-id="3b3f7-171">Для идентификации двух или трех пилотных команд.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-171">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="3b3f7-172">Все участники группы должны использовать смены в Teams для управления их расписаниями, общения и совместной работы друг с другом.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-172">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="3b3f7-173">Определение группы лидерами</span><span class="sxs-lookup"><span data-stu-id="3b3f7-173">Identify team champions</span></span>

<span data-ttu-id="3b3f7-174">Определите лидерами между пилотными группами и закрепите их, чтобы упростить еванжелизе смены.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-174">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="3b3f7-175">Лидерами Teams – это то, что они делают, и делитесь своими опытом для предоставления поддержки и руководств для участников группы.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-175">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="3b3f7-176">Командные лидерами могут быть владельцами группы или руководителями.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-176">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="3b3f7-177">Команда лидерами должна обеспечивать настройку для участников группы, выделять время для [получения клиентов](../../get-clients.md)Teams, входить в Teams и проверять расписания в сменах и начинать общение друг с другом.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-177">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="3b3f7-178">Пользователи, уже знакомые с StaffHub, будут быстро выполняться в сменах.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-178">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="3b3f7-179">Вы также можете навести на [](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) них указатель мыши, чтобы получить дополнительную помощь.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-179">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team-coming-soon"></a><span data-ttu-id="3b3f7-180">Переместить StaffHub группу (скоро)</span><span class="sxs-lookup"><span data-stu-id="3b3f7-180">Move a StaffHub team (coming soon)</span></span>

<span data-ttu-id="3b3f7-181">Воспользуйтесь этими инструкциями для перемещения одной команды StaffHub на один раз.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-181">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="3b3f7-182">Мы рекомендуем этот подход для ваших пилотных команд.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-182">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="3b3f7-183">Позже, когда вы будете готовы к перемещению всех StaffHubных групп своей организации, читайте в статье [Перемещение групп StaffHub](#move-your-staffhub-teams-coming-soon) , чтобы узнать, как переместить несколько команд за один раз.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-183">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams-coming-soon) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="3b3f7-184">Чтобы переместить группу StaffHub, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-184">Run the following to move a StaffHub team.</span></span>

```
Move-StaffHubTeam -TeamId <String>

Sample:

Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

<span data-ttu-id="3b3f7-185">Ниже приведен пример ответа, который вы получаете, когда вы отправляете запрос на перемещение группы StaffHub в Teams.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-185">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

<span data-ttu-id="3b3f7-186">Чтобы проверить состояние запроса на перемещение, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-186">To check the status of a move request, run the following.</span></span>

```
Get-TeamMigrationJobStatus <String>

Sample:
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"

```

<span data-ttu-id="3b3f7-187">Ниже приведен пример ответа, который вы получаете при выполнении перемещения.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-187">Here's an example of the response you get when a move is in progress.</span></span>

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

## <a name="make-the-transition-from-staffhub-to-teams"></a><span data-ttu-id="3b3f7-188">Преобразование из StaffHub в Teams</span><span class="sxs-lookup"><span data-stu-id="3b3f7-188">Make the transition from StaffHub to Teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="3b3f7-189">Формирование сведений о состоянии</span><span class="sxs-lookup"><span data-stu-id="3b3f7-189">Raise awareness</span></span>

<span data-ttu-id="3b3f7-190">Когда вы будете готовы к переходу за пределы пилотных групп и перемещайте StaffHub Teams вашей организации в Teams, важно сначала сообщить о них в рамках своей организации.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-190">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="3b3f7-191">Разработайте Word по сменам и переходам в Teams, чтобы привлечь внимание к осведомленности, создать особенности и внедрять диски.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-191">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams-coming-soon"></a><span data-ttu-id="3b3f7-192">Перемещение StaffHub Teams (скоро)</span><span class="sxs-lookup"><span data-stu-id="3b3f7-192">Move your StaffHub teams (coming soon)</span></span>

<span data-ttu-id="3b3f7-193">Чтобы переместить StaffHub Teams, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-193">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="3b3f7-194">Вы можете переместить все группы StaffHub организации или переместить определенные StaffHub команды.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-194">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="3b3f7-195">Если вы хотите переместить StaffHub команды по одной, ознакомьтесь со сведениями в разделе [Перемещение группы StaffHub](#move-a-staffhub-team-coming-soon).</span><span class="sxs-lookup"><span data-stu-id="3b3f7-195">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team-coming-soon).</span></span>

#### <a name="move-all-staffhub-teams-coming-soon"></a><span data-ttu-id="3b3f7-196">Перемещение всех StaffHub Teams (ожидается в ближайшее время)</span><span class="sxs-lookup"><span data-stu-id="3b3f7-196">Move all StaffHub teams (coming soon)</span></span>

<span data-ttu-id="3b3f7-197">Выполните указанные ниже действия, чтобы получить список всех групп StaffHub в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-197">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="3b3f7-198">Затем выполните указанные ниже действия, чтобы переместить все команды.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-198">Then, run the following to move all teams.</span></span>

```
$StaffHubTeams | foreach {Move-StaffHubTeam -TeamId {$_.Id}}
```

<span data-ttu-id="3b3f7-199">Вот пример ответа.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-199">Here's an example of the response.</span></span>

<span data-ttu-id="3b3f7-200">Для любой команды, которая уже была перемещена в Teams или уже существует в Teams, идентификатором jobId будет "null", так как задание не нужно отправлять для перемещения этой команды.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-200">For any team that was already moved to Teams or already exists in Teams, the jobId will be "null" as a job doesn't need to be submitted to move that team.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams-coming-soon"></a><span data-ttu-id="3b3f7-201">Переместить определенные группы StaffHub (скоро)</span><span class="sxs-lookup"><span data-stu-id="3b3f7-201">Move specific StaffHub teams (coming soon)</span></span>

<span data-ttu-id="3b3f7-202">Выполните указанные ниже действия, чтобы получить список всех идентификаторов участников группы StaffHub в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-202">Run the following to get a list of all StaffHub team Ids in your organization.</span></span>

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="3b3f7-203">В результатах, возвращенных `Get-StaffHubteamsForTenant` командлетом, который вы выполняли раньше, выберите идентификаторы, которые вы хотите переместить, а затем добавьте их в CSV-файл, в котором значения разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-203">In the results returned by the `Get-StaffHubteamsForTenant` cmdlet you ran earlier, select the Team Ids you want to move, and then add them to a comma-separated values (CSV) file.</span></span>

<span data-ttu-id="3b3f7-204">Ниже приведен пример форматирования CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-204">Here's an example of how the CSV file should be formatted.</span></span>

|<span data-ttu-id="3b3f7-205">Номер</span><span class="sxs-lookup"><span data-stu-id="3b3f7-205">Id</span></span>  |
|---------|
|<span data-ttu-id="3b3f7-206">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="3b3f7-206">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="3b3f7-207">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="3b3f7-207">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="3b3f7-208">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="3b3f7-208">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="3b3f7-209">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="3b3f7-209">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="3b3f7-210">Создав CSV-файл, выполните указанные ниже действия, чтобы переместить указанные в CSV-файл команды.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-210">After you create the CSV file, run the following to move the teams you specified in the CSV file.</span></span>

```
Import-Csv .\teams.txt | foreach {Move-StaffHubTeam -TeamdId {$_.Id}}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams-coming-soon"></a><span data-ttu-id="3b3f7-211">Убедитесь в том, что ваши StaffHub Teams переместились в Teams (скоро)</span><span class="sxs-lookup"><span data-stu-id="3b3f7-211">Confirm that your StaffHub teams have moved to Teams (coming soon)</span></span>

<span data-ttu-id="3b3f7-212">Выполните указанные ниже действия, чтобы получить список всех команд в сменах в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-212">Run the following to get a list of all teams in Shifts in your organization.</span></span> 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

## <a name="monitor-teams-usage"></a><span data-ttu-id="3b3f7-213">Мониторинг использования групп</span><span class="sxs-lookup"><span data-stu-id="3b3f7-213">Monitor Teams usage</span></span>

<span data-ttu-id="3b3f7-214">С помощью отчетов об использовании вы сможете лучше разобраться в использовании шаблонов использования и получить информацию о том, где следует определять приоритетные обучающие и коммуникационные возможности в Организации.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-214">Usage reports can help you better understand usage patterns and give you insights on where to prioritize training and communication efforts across your organization.</span></span> <span data-ttu-id="3b3f7-215">Поскольку смена является приложением в Teams, вы можете просматривать использование с помощью отчетов Teams.</span><span class="sxs-lookup"><span data-stu-id="3b3f7-215">Because Shifts is an app in Teams, you can view usage through Teams reports.</span></span> <span data-ttu-id="3b3f7-216">Дополнительные сведения можно найти в разделе Отчеты [Teams в центре администрирования Microsoft Teams](../../teams-analytics-and-reports/teams-reporting-reference.md) и в [отчетах об активности в Teams в центре администрирования Microsoft 365](../../teams-activity-reports.md).</span><span class="sxs-lookup"><span data-stu-id="3b3f7-216">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3b3f7-217">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="3b3f7-217">Related topics</span></span>
- [<span data-ttu-id="3b3f7-218">Прекращение поддержки Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="3b3f7-218">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="3b3f7-219">Управление приложением "Смены" для вашей организации в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3b3f7-219">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="3b3f7-220">Справочник по StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="3b3f7-220">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
