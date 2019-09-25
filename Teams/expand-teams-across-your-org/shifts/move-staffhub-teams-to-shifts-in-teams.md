---
title: Перемещение групп StaffHub в приложение "Смены" в Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Сведения о том, как перемещаться по Microsoft StaffHub Teams и планировать данные для смены в Microsoft Teams.
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5bf9776dbf5a5992354f542436b4904d53d58508
ms.sourcegitcommit: 6ba9eeb81b7d55ffc319d6d6658d0ecac83c2159
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2019
ms.locfileid: "37142049"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="b7634-103">Перемещайте Microsoft StaffHub Teams по сменам в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b7634-103">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b7634-104">Начиная с 1 октября 2019 г. Корпорация Microsoft StaffHub будет прекращена.</span><span class="sxs-lookup"><span data-stu-id="b7634-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="b7634-105">Мы создаем возможности StaffHub в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b7634-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="b7634-106">Сегодня команды включают в себя приложение смен для управления планированием и дополнительные возможности, которые будут вычислены с течением времени.</span><span class="sxs-lookup"><span data-stu-id="b7634-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="b7634-107">StaffHub перестанет работать для всех пользователей 1 октября 2019 г.</span><span class="sxs-lookup"><span data-stu-id="b7634-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="b7634-108">Каждый, кто пытается открыть StaffHub, будет показывать сообщение, направленное на загрузку групп.</span><span class="sxs-lookup"><span data-stu-id="b7634-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="b7634-109">Дополнительные сведения можно найти в [статье Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="b7634-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

<span data-ttu-id="b7634-110">Приложение «смена» в Teams предоставляет простой подход к управлению расписаниями и постоянным потоком сменных и отменяющих переходов, происходящих в повседневной основе.</span><span class="sxs-lookup"><span data-stu-id="b7634-110">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="b7634-111">Участники групп могут получать доступ к своим расписаниям и сменам данных непосредственно в приложении, а также на разных устройствах для настройки их настроек, управления расписаниями и запроса времени.</span><span class="sxs-lookup"><span data-stu-id="b7634-111">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="b7634-112">В этой статье рассказывается о том, как переместить StaffHub Teams в Организации и спланировать данные для смены в Teams.</span><span class="sxs-lookup"><span data-stu-id="b7634-112">This article walks you through how to move your organization’s StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="b7634-113">В нем рассматриваются следующие вопросы:</span><span class="sxs-lookup"><span data-stu-id="b7634-113">It covers:</span></span>

- [<span data-ttu-id="b7634-114">Что нужно знать о переходе в Teams</span><span class="sxs-lookup"><span data-stu-id="b7634-114">What you need to know about the move to Teams</span></span>](#what-you-need-to-know-about-the-move-to-teams)
- [<span data-ttu-id="b7634-115">Подготовку</span><span class="sxs-lookup"><span data-stu-id="b7634-115">Prepare</span></span>](#prepare)
- [<span data-ttu-id="b7634-116">Проведение пилотной программы</span><span class="sxs-lookup"><span data-stu-id="b7634-116">Conduct a pilot</span></span>](#conduct-a-pilot) 
- [<span data-ttu-id="b7634-117">Переход за пределы пилотной версии и перемещение всех StaffHub Teams</span><span class="sxs-lookup"><span data-stu-id="b7634-117">Go beyond your pilot and move all StaffHub teams</span></span>](#go-beyond-your-pilot-and-move-all-staffhub-teams)
- [<span data-ttu-id="b7634-118">Мониторинг использования групп</span><span class="sxs-lookup"><span data-stu-id="b7634-118">Monitor Teams usage</span></span>](#monitor-teams-usage)
- [<span data-ttu-id="b7634-119">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="b7634-119">Troubleshooting</span></span>](#troubleshooting)

<span data-ttu-id="b7634-120">Если вы занимаетесь малым предприятием из одной или двух групп StaffHub или крупного предприятия с сотнями StaffHub Teams, здесь вы найдете инструкции для администраторов, которые помогут вам успешно выполнить переход в Teams.</span><span class="sxs-lookup"><span data-stu-id="b7634-120">Whether you’re a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you’ll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="b7634-121">Для выполнения действий, описанных в этой статье, необходимо быть глобальным администратором.</span><span class="sxs-lookup"><span data-stu-id="b7634-121">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="b7634-122">Если вы еще не сделали этого, ознакомьтесь с разделами " [вопросы и ответы" в StaffHub о выбытиех](microsoft-staffhub-to-be-retired.md) для получения ответов на любые возникающие вопросы.</span><span class="sxs-lookup"><span data-stu-id="b7634-122">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span>

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="b7634-123">Что нужно знать о переходе в Teams</span><span class="sxs-lookup"><span data-stu-id="b7634-123">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="b7634-124">Переход в Teams</span><span class="sxs-lookup"><span data-stu-id="b7634-124">When to move to Teams</span></span>

<span data-ttu-id="b7634-125">Действующий 1 октября 2019 г. StaffHub будет прекращена.</span><span class="sxs-lookup"><span data-stu-id="b7634-125">Effective October 1, 2019, StaffHub will be retired.</span></span> <span data-ttu-id="b7634-126">Мы рекомендуем вам приступить к работе с Teams сегодня и начать переход с групп и пользователей вашей организации из StaffHub.</span><span class="sxs-lookup"><span data-stu-id="b7634-126">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="b7634-127">Управление расписаниями является наиболее часто используемой функцией StaffHub, поэтому мы рекомендуем использовать приложение "смены" в Teams для перемещения вперед.</span><span class="sxs-lookup"><span data-stu-id="b7634-127">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="b7634-128">Что перемещается в Teams</span><span class="sxs-lookup"><span data-stu-id="b7634-128">What is moved to Teams</span></span>

<span data-ttu-id="b7634-129">Когда вы перемещаете группу StaffHub, сведения о членстве в группах, пользовательские расписания и данные чата перемещаются в Teams.</span><span class="sxs-lookup"><span data-stu-id="b7634-129">When you move a StaffHub team, team membership, user details, team schedules, and chat data are moved to Teams.</span></span> <span data-ttu-id="b7634-130">Файлы не перемещаются при перемещении команды StaffHub.</span><span class="sxs-lookup"><span data-stu-id="b7634-130">Files aren't moved when you move a StaffHub team.</span></span> <span data-ttu-id="b7634-131">Если группа StaffHub включает файлы, которые вы также хотите переместить в Teams, вы можете переместить их на отдельном этапе.</span><span class="sxs-lookup"><span data-stu-id="b7634-131">If a StaffHub team contains files that you also want to move to teams, you move the files in a separate step.</span></span>

<span data-ttu-id="b7634-132">Каждой команде StaffHub нужна соответствующая группа Office 365.</span><span class="sxs-lookup"><span data-stu-id="b7634-132">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="b7634-133">Если с группой StaffHub не связана группа Office 365, она будет автоматически создана для поддержки перехода.</span><span class="sxs-lookup"><span data-stu-id="b7634-133">If a StaffHub team doesn't have an Office 365 Group associated with it, one is automatically created for you to support the transition.</span></span> <span data-ttu-id="b7634-134">С учетом различий в именовании групп и групп между группами и StaffHub в Teams может быть указано другое имя группы.</span><span class="sxs-lookup"><span data-stu-id="b7634-134">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span>

<span data-ttu-id="b7634-135">По мере перевода групп из StaffHub в Teams пользователи больше не смогут получать доступ к своим расписаниям в StaffHub и перенаправляться на смены в Teams.</span><span class="sxs-lookup"><span data-stu-id="b7634-135">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="b7634-136">Мы рекомендуем вам сообщать об этом изменении в своей организации, чтобы свести к минимуму перерывы и предоставить пользователям возможность принимать и изучать команды.</span><span class="sxs-lookup"><span data-stu-id="b7634-136">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span> <span data-ttu-id="b7634-137">Если у вас есть Azure AD Premium, вы можете [запустить отчет](run-report-to-show-staffhub-usage.md) , чтобы получить список пользователей StaffHub в вашей организации, которым нужно знать об этом изменении.</span><span class="sxs-lookup"><span data-stu-id="b7634-137">If you have Azure AD Premium, you can [run a report](run-report-to-show-staffhub-usage.md) to get a list of StaffHub users in your organization who need to know about this change.</span></span>  

<span data-ttu-id="b7634-138">После того как вы перемещаете группу StaffHub в Teams, вы не сможете выполнить откат.</span><span class="sxs-lookup"><span data-stu-id="b7634-138">There's no rollback option after you move a StaffHub team to Teams.</span></span>

### <a name="user-experience-when-you-move-a-team"></a><span data-ttu-id="b7634-139">Взаимодействие с пользователем при перемещении команды</span><span class="sxs-lookup"><span data-stu-id="b7634-139">User experience when you move a team</span></span>

<span data-ttu-id="b7634-140">Минимальная продолжительность простоя (менее чем секунда, если она есть) для пользователей при переключении с StaffHub на смену в Teams.</span><span class="sxs-lookup"><span data-stu-id="b7634-140">There's minimal downtime (less than a second, if any at all) for users when their team is switched from StaffHub to Shifts in Teams.</span></span> <span data-ttu-id="b7634-141">Пользователи могут продолжать пользоваться StaffHub, пока не завершится переход в Teams.</span><span class="sxs-lookup"><span data-stu-id="b7634-141">Users can continue using StaffHub until the move to Teams is completed.</span></span> <span data-ttu-id="b7634-142">После завершения перемещения участники команды увидят сообщение о том, что они должны приступить к использованию смен в Teams, чтобы получить доступ к своему календарному плану.</span><span class="sxs-lookup"><span data-stu-id="b7634-142">When the move is completed, team members will see a message to let them know that they need to start using Shifts in Teams to access their team schedule.</span></span> <span data-ttu-id="b7634-143">Ниже приведен пример сообщения, которое пользователи видят в StaffHub после перемещения группы StaffHub в Teams.</span><span class="sxs-lookup"><span data-stu-id="b7634-143">Here's an example of the message that users see in StaffHub after the StaffHub team is moved to Teams.</span></span>

<span data-ttu-id="b7634-144">![Пример сообщения, которое видят пользователи.] (../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Пример сообщения, которое пользователи видят в StaffHub после перемещения группы StaffHub в Teams")</span><span class="sxs-lookup"><span data-stu-id="b7634-144">![Example of the message that users see.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Example of the message that users see in StaffHub after the StaffHub team is moved to Teams")</span></span>

## <a name="prepare"></a><span data-ttu-id="b7634-145">Подготовку</span><span class="sxs-lookup"><span data-stu-id="b7634-145">Prepare</span></span>

<span data-ttu-id="b7634-146">Вот как можно подготовиться к переходу на Teams.</span><span class="sxs-lookup"><span data-stu-id="b7634-146">Here's how to prepare for the move to Teams.</span></span>

### <a name="check-that-prerequisites-are-met"></a><span data-ttu-id="b7634-147">Проверка соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="b7634-147">Check that prerequisites are met</span></span>

<span data-ttu-id="b7634-148">Перед перемещением группы StaffHub в Teams убедитесь в том, что:</span><span class="sxs-lookup"><span data-stu-id="b7634-148">Before you move a StaffHub team to Teams, make sure that:</span></span>

- <span data-ttu-id="b7634-149">Вход пользователя в систему является глобальным администратором.</span><span class="sxs-lookup"><span data-stu-id="b7634-149">The signed-in user is a global admin.</span></span>
- <span data-ttu-id="b7634-150">Teams включена для всех пользователей в клиенте.</span><span class="sxs-lookup"><span data-stu-id="b7634-150">Teams is enabled for all users in the tenant.</span></span>
- <span data-ttu-id="b7634-151">Создание групп Office 365 включена в клиенте.</span><span class="sxs-lookup"><span data-stu-id="b7634-151">Office 365 Groups creation is enabled in the tenant.</span></span>
- <span data-ttu-id="b7634-152">StaffHub Теамид является допустимым.</span><span class="sxs-lookup"><span data-stu-id="b7634-152">The StaffHub teamId is valid.</span></span>
- <span data-ttu-id="b7634-153">Группа StaffHub включает в себя участников.</span><span class="sxs-lookup"><span data-stu-id="b7634-153">The StaffHub team contains members.</span></span>
- <span data-ttu-id="b7634-154">Все участники группы StaffHub связаны с учетной записью Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b7634-154">All StaffHub team members are linked to an Azure AD account.</span></span>

<span data-ttu-id="b7634-155">Если эти условия не соблюдаются, запрос на перемещение завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="b7634-155">If these prerequisites aren't met, the move request will fail.</span></span>

### <a name="assign-teams-licenses"></a><span data-ttu-id="b7634-156">Назначение лицензий Teams</span><span class="sxs-lookup"><span data-stu-id="b7634-156">Assign Teams licenses</span></span>

<span data-ttu-id="b7634-157">Каждый пользователь должен иметь действующую лицензию Microsoft 365 или Office 365 из [подходящего плана](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) , и ему должна быть назначена лицензия Teams.</span><span class="sxs-lookup"><span data-stu-id="b7634-157">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="b7634-158">Назначение лицензии на команды пользователям предоставляет им доступ к Teams.</span><span class="sxs-lookup"><span data-stu-id="b7634-158">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="b7634-159">Вы управляете лицензиями Teams в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b7634-159">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="b7634-160">Дополнительные сведения можно найти в разделе [Управление доступом пользователей к Teams](../../user-access.md).</span><span class="sxs-lookup"><span data-stu-id="b7634-160">To learn more, see [Manage user access to Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b7634-161">Если в вашей организации используется Skype для бизнеса, и вы не готовы переместить всех пользователей в Teams, вы можете включить команды для сотрудников Firstline, которые смогут запускать команды вместе со Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="b7634-161">If your organization uses Skype for Business and you’re not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="b7634-162">В режиме совместного существования под названием *острова*все клиентские приложения работают как отдельные решения.</span><span class="sxs-lookup"><span data-stu-id="b7634-162">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="b7634-163">Дополнительные сведения можно найти в статье [понимание групп, а также взаимодействие и совместимость Skype для бизнеса](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="b7634-163">To learn more, see [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="install-the-prerelease-version-of-the-staffhub-powershell-module"></a><span data-ttu-id="b7634-164">Установка предварительной версии модуля PowerShell StaffHub</span><span class="sxs-lookup"><span data-stu-id="b7634-164">Install the prerelease version of the StaffHub PowerShell module</span></span>

<span data-ttu-id="b7634-165">Установите предварительную [версию модуля PowerShell StaffHub](install-the-staffhub-powershell-module.md), если вы еще не сделали этого.</span><span class="sxs-lookup"><span data-stu-id="b7634-165">If you haven't already, [install the prerelease version of the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span> 

<span data-ttu-id="b7634-166">Для перемещения групп StaffHub в Teams необходимо установить предварительную версию модуля.</span><span class="sxs-lookup"><span data-stu-id="b7634-166">You must have the prerelease version of the module installed to move your StaffHub teams to Teams.</span></span>

### <a name="link-an-azure-ad-account-for-staffhub-team-members-who-dont-have-one"></a><span data-ttu-id="b7634-167">Связывание учетной записи Azure AD с участниками группы StaffHub, у которых нет одной</span><span class="sxs-lookup"><span data-stu-id="b7634-167">Link an Azure AD account for StaffHub team members who don't have one</span></span>

<span data-ttu-id="b7634-168">Каждый участник группы StaffHub должен быть связан с учетной записью Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="b7634-168">Each StaffHub team member must be linked to an Azure Active Directory (Azure AD) account.</span></span> <span data-ttu-id="b7634-169">Пользователи в вашей организации не будут связаны с учетной записью Azure AD, если применимы следующие сценарии:</span><span class="sxs-lookup"><span data-stu-id="b7634-169">Users in your organization won't be linked to an Azure AD account if any of the following scenarios apply:</span></span>

- <span data-ttu-id="b7634-170">Владелец команды добавил пользователя, у которого нет учетной записи Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b7634-170">A team owner added a user who doesn't have an Azure AD account.</span></span>
- <span data-ttu-id="b7634-171">Владелец команды пригласил пользователя в группу StaffHub, и этот пользователь не пригласится на приглашение.</span><span class="sxs-lookup"><span data-stu-id="b7634-171">A team owner invited a user to a StaffHub team and that user didn't accept the invitation.</span></span>

<span data-ttu-id="b7634-172">Вы можете связать учетную запись Azure AD для этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="b7634-172">You can link an Azure AD account for these users.</span></span>  <span data-ttu-id="b7634-173">Выполните описанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="b7634-173">Here's how.</span></span>

#### <a name="get-a-list-of-all-users-on-staffhub-teams-that-have-team-members-that-arent-linked-to-an-azure-ad-account"></a><span data-ttu-id="b7634-174">Получение списка всех пользователей для StaffHub Teams, у которых есть члены группы, не связанные с учетной записью Azure AD</span><span class="sxs-lookup"><span data-stu-id="b7634-174">Get a list of all users on StaffHub teams that have team members that aren't linked to an Azure AD account</span></span>

<span data-ttu-id="b7634-175">Выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="b7634-175">Run the following:</span></span>
```
$StaffHubTeams = Get-StaffHubTeamsForTenant
$StaffHubTeams[0] = $StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq 'StaffHub' }
foreach($team in $StaffHubTeams[0]) {Get-StaffHubMember -TeamId $team.Id | where {$_.Email -eq $null -or $_.State -eq "Invited"}}
```

#### <a name="link-the-account"></a><span data-ttu-id="b7634-176">Связывание учетной записи</span><span class="sxs-lookup"><span data-stu-id="b7634-176">Link the account</span></span>

<span data-ttu-id="b7634-177">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="b7634-177">Do one of the following:</span></span>

- <span data-ttu-id="b7634-178">Преобразуйте учетную запись и свяжите ее с ней.</span><span class="sxs-lookup"><span data-stu-id="b7634-178">Convert and link the account.</span></span>

  <span data-ttu-id="b7634-179">StaffHub владельцы и руководители групп могут преобразовать неактивную учетную запись и связать ее с учетной записью Azure AD в StaffHub, изменив адрес электронной почты пользователя на действительный UPN на странице StaffHub параметры группы.</span><span class="sxs-lookup"><span data-stu-id="b7634-179">StaffHub team owners and managers can convert an inactive account and link it to an Azure AD account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="b7634-180">Удалите несвязанную учетную запись, а затем снова добавьте ее с помощью UPN.</span><span class="sxs-lookup"><span data-stu-id="b7634-180">Remove the unlinked account and then re-add the account by using the UPN.</span></span>
    1. <span data-ttu-id="b7634-181">Запустите командлет [Remove-стаффхубмембер](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubMember?view=staffhub-ps) , чтобы удалить неподготовленную учетную запись из группы StaffHub.</span><span class="sxs-lookup"><span data-stu-id="b7634-181">Run the [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubMember?view=staffhub-ps) cmdlet to remove the non-provisioned account from the StaffHub team.</span></span>
    2. <span data-ttu-id="b7634-182">Запустите командлет [Add-стаффхубмембер](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) , чтобы добавить учетную запись обратно в группу StaffHub с помощью UPN.</span><span class="sxs-lookup"><span data-stu-id="b7634-182">Run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) cmdlet to add the account back to the StaffHub team by using the UPN.</span></span>

- <span data-ttu-id="b7634-183">Удалите несвязанную учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="b7634-183">Remove the unlinked user account.</span></span> <span data-ttu-id="b7634-184">Использовать этот параметр Учетная запись пользователя больше не нужна.</span><span class="sxs-lookup"><span data-stu-id="b7634-184">Use this option the user account is no longer needed.</span></span>

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a><span data-ttu-id="b7634-185">Назначение пользователям политики настройки приложения Фирстлиневоркер</span><span class="sxs-lookup"><span data-stu-id="b7634-185">Assign the FirstlineWorker app setup policy to users</span></span>

<span data-ttu-id="b7634-186">Teams включает встроенную политику настройки приложений Фирстлиневоркер, которую можно использовать для настройки групп, чтобы выделиться наиболее важными приложениями для Firstline сотрудников вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b7634-186">Teams includes a built-in FirstlineWorker app setup policy that you can use to customize Teams to highlight the apps that are most important for the Firstline Workers in your organization.</span></span> <span data-ttu-id="b7634-187">Когда вы назначаете эту политику пользователям, приложения в этой политике будут закреплены на панели приложения в Teams для быстрого и удобного доступа.</span><span class="sxs-lookup"><span data-stu-id="b7634-187">When you assign this policy to users, the apps in the policy are pinned to the app bar in Teams for quick and easy access.</span></span> <span data-ttu-id="b7634-188">Другие приложения, добавленные в Teams, можно найти на панели приложения, нажав **... Другие приложения** в классической и веб-клиентах Teams и прокрутка вверх в клиенте Teams Mobile.</span><span class="sxs-lookup"><span data-stu-id="b7634-188">Other apps added to Teams can be found in the app bar by clicking **... More apps** in the Teams desktop and web clients and by swiping up in the Teams mobile client.</span></span> <span data-ttu-id="b7634-189">По умолчанию политика настройки приложения Фирстлиневоркер включает в себя действия, смены, чат и звонки приложений.</span><span class="sxs-lookup"><span data-stu-id="b7634-189">By default, the FirstlineWorker app setup policy includes the Activity, Shifts, Chat, and Calling apps.</span></span>

<span data-ttu-id="b7634-190">Инструкции по назначению пользователям политики настройки приложения Фирстлиневоркер приведены в статье [Использование политики настройки приложения фирстлиневоркер для закрепления смен в Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams).</span><span class="sxs-lookup"><span data-stu-id="b7634-190">For steps on how to assign the FirstlineWorker app setup policy to users, see [Use the FirstlineWorker app setup policy to pin Shifts to Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams).</span></span> <span data-ttu-id="b7634-191">После назначения политики для вступления в силу может потребоваться до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="b7634-191">After you assign a policy, it can take up to 24 hours to take effect.</span></span>

<span data-ttu-id="b7634-192">Мы рекомендуем выполнить этот шаг не менее чем за неделю, прежде чем вы сможете переместить StaffHub Teams и пользователей в Teams.</span><span class="sxs-lookup"><span data-stu-id="b7634-192">We recommend you complete this step at least a week before you move your StaffHub teams and users to Teams.</span></span> <span data-ttu-id="b7634-193">Когда пользователи находятся в Teams, убедитесь, что они могут просматривать и получать доступ к приложению смены.</span><span class="sxs-lookup"><span data-stu-id="b7634-193">When users are on Teams, confirm that they can see and access the Shifts app.</span></span>

<span data-ttu-id="b7634-194">Вы также можете создать пользовательские политики настройки приложений и изменить параметры в политике настройки глобального приложения.</span><span class="sxs-lookup"><span data-stu-id="b7634-194">You can also create custom app setup policies and edit the settings in the global app setup policy.</span></span> <span data-ttu-id="b7634-195">Дополнительные сведения можно найти в статье [Управление политиками настройки приложений в Teams](../../teams-app-setup-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b7634-195">To learn more, check out [Manage app setup policies in Teams](../../teams-app-setup-policies.md).</span></span>

### <a name="onboard-users-to-teams"></a><span data-ttu-id="b7634-196">Встроенные пользователи в Teams</span><span class="sxs-lookup"><span data-stu-id="b7634-196">Onboard users to Teams</span></span>

<span data-ttu-id="b7634-197">В рамках стратегии выставления настольных систем вы можете получать учебные материалы и рекомендации для пользователей, которые помогут им ознакомиться с группами.</span><span class="sxs-lookup"><span data-stu-id="b7634-197">As part of your onboarding strategy, provide training and guidance for users to help them get familiar with Teams.</span></span> <span data-ttu-id="b7634-198">Поделитесь следующими ресурсами с пользователями, чтобы они знали, где можно получить клиентов Teams, обучение и поддержку.</span><span class="sxs-lookup"><span data-stu-id="b7634-198">Share the following resources with users so they know where to get Teams clients, training, and support:</span></span>

- [<span data-ttu-id="b7634-199">Веб-клиент Teams</span><span class="sxs-lookup"><span data-stu-id="b7634-199">Teams web client</span></span>](https://teams.microsoft.com)
- [<span data-ttu-id="b7634-200">Ссылки для скачивания настольной и мобильной версий клиента</span><span class="sxs-lookup"><span data-stu-id="b7634-200">Desktop and mobile client download links</span></span>](https://teams.microsoft.com/downloads)
- [<span data-ttu-id="b7634-201">Обучающие видео для Teams</span><span class="sxs-lookup"><span data-stu-id="b7634-201">Teams training videos</span></span>](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [<span data-ttu-id="b7634-202">Справочная документация для Teams</span><span class="sxs-lookup"><span data-stu-id="b7634-202">Teams Help documentation</span></span>](https://support.office.com/teams)

<span data-ttu-id="b7634-203">Рекомендации по развертыванию групп и внедрению групп можно найти [в разделе Развертывание групп](../../How-to-roll-out-teams.md) и [принятие групп](../../adopt-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="b7634-203">For guidance on deploying Teams and driving Teams adoption, see [How to roll out Teams](../../How-to-roll-out-teams.md) and [Adopt Teams](../../adopt-microsoft-teams-landing-page.md).</span></span>

## <a name="conduct-a-pilot"></a><span data-ttu-id="b7634-204">Проведение пилотной программы</span><span class="sxs-lookup"><span data-stu-id="b7634-204">Conduct a pilot</span></span>

<span data-ttu-id="b7634-205">Мы рекомендуем начать с перемещения двух или трех групп StaffHub, чтобы выбрать группу ранних переходов.</span><span class="sxs-lookup"><span data-stu-id="b7634-205">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="b7634-206">Работа с пилотной версией поможет вам уточнить план перехода и убедиться, что вы готовы переместить все StaffHub Teams вашей организации в Teams.</span><span class="sxs-lookup"><span data-stu-id="b7634-206">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="b7634-207">Кроме того, он определяет лидерами, которые помогут вам облегчить внедрение в рамках своей организации.</span><span class="sxs-lookup"><span data-stu-id="b7634-207">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="b7634-208">Если вы работаете в малом бизнесе, для которого не требуется поэтапный подход, действия, описанные в этом разделе, могут быть все, что нужно сделать, чтобы перейти с StaffHub на Teams.</span><span class="sxs-lookup"><span data-stu-id="b7634-208">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="b7634-209">Определение пилотных команд</span><span class="sxs-lookup"><span data-stu-id="b7634-209">Identify pilot teams</span></span>

<span data-ttu-id="b7634-210">Для идентификации двух или трех пилотных команд.</span><span class="sxs-lookup"><span data-stu-id="b7634-210">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="b7634-211">Все участники группы должны использовать смены в Teams для управления их расписаниями, общения и совместной работы друг с другом.</span><span class="sxs-lookup"><span data-stu-id="b7634-211">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="b7634-212">Определение группы лидерами</span><span class="sxs-lookup"><span data-stu-id="b7634-212">Identify team champions</span></span>

<span data-ttu-id="b7634-213">Определите лидерами между пилотными группами и закрепите их, чтобы упростить еванжелизе смены.</span><span class="sxs-lookup"><span data-stu-id="b7634-213">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="b7634-214">Лидерами Teams – это то, что они делают, и делитесь своими опытом для предоставления поддержки и руководств для участников группы.</span><span class="sxs-lookup"><span data-stu-id="b7634-214">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="b7634-215">Командные лидерами могут быть владельцами группы или руководителями.</span><span class="sxs-lookup"><span data-stu-id="b7634-215">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="b7634-216">Команда лидерами должна обеспечивать настройку для участников группы, выделять время для [получения клиентов](../../get-clients.md)Teams, входить в Teams и проверять расписания в сменах и начинать общение друг с другом.</span><span class="sxs-lookup"><span data-stu-id="b7634-216">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="b7634-217">Пользователи, уже знакомые с StaffHub, будут быстро выполняться в сменах.</span><span class="sxs-lookup"><span data-stu-id="b7634-217">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="b7634-218">Вы также можете навести на них указатель мыши [, чтобы получить дополнительную помощь.](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)</span><span class="sxs-lookup"><span data-stu-id="b7634-218">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team"></a><span data-ttu-id="b7634-219">Перемещение команды StaffHub</span><span class="sxs-lookup"><span data-stu-id="b7634-219">Move a StaffHub team</span></span>

<span data-ttu-id="b7634-220">Воспользуйтесь этими инструкциями для перемещения одной команды StaffHub на один раз.</span><span class="sxs-lookup"><span data-stu-id="b7634-220">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="b7634-221">Мы рекомендуем этот подход для ваших пилотных команд.</span><span class="sxs-lookup"><span data-stu-id="b7634-221">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="b7634-222">Позже, когда вы будете готовы к перемещению всех StaffHubных групп своей организации, читайте в статье [Перемещение групп StaffHub](#move-your-staffhub-teams) , чтобы узнать, как переместить несколько команд за один раз.</span><span class="sxs-lookup"><span data-stu-id="b7634-222">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="b7634-223">Чтобы переместить группу StaffHub, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="b7634-223">Run the following to move a StaffHub team.</span></span>

```
Move-StaffHubTeam -TeamId <String>
```
<span data-ttu-id="b7634-224">Образом</span><span class="sxs-lookup"><span data-stu-id="b7634-224">Example:</span></span>

```
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

<span data-ttu-id="b7634-225">Ниже приведен пример ответа, который вы получаете, когда вы отправляете запрос на перемещение группы StaffHub в Teams.</span><span class="sxs-lookup"><span data-stu-id="b7634-225">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

<span data-ttu-id="b7634-226">Чтобы проверить состояние запроса на перемещение, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="b7634-226">To check the status of a move request, run the following.</span></span>

```
Get-TeamMigrationJobStatus <String>
```
<span data-ttu-id="b7634-227">Образом</span><span class="sxs-lookup"><span data-stu-id="b7634-227">Example:</span></span>

```
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

<span data-ttu-id="b7634-228">Ниже приведен пример ответа, который вы получаете при выполнении перемещения.</span><span class="sxs-lookup"><span data-stu-id="b7634-228">Here's an example of the response you get when a move is in progress.</span></span>

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a><span data-ttu-id="b7634-229">Перемещение файлов из группы StaffHub в группы</span><span class="sxs-lookup"><span data-stu-id="b7634-229">Move files from a StaffHub team to Teams</span></span>

<span data-ttu-id="b7634-230">Это действие применимо только в том случае, если команда StaffHub, перемещенная в Teams, содержит файлы, которые вы хотите также перейти в группу Teams.</span><span class="sxs-lookup"><span data-stu-id="b7634-230">This step only applies if the StaffHub team that you moved to Teams has files that you want to also move to Teams.</span></span> <span data-ttu-id="b7634-231">Вы можете перемещать файлы непосредственно в SharePoint Online или с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7634-231">You can move files directly in SharePoint Online or by using PowerShell.</span></span>

#### <a name="in-sharepoint-online"></a><span data-ttu-id="b7634-232">В SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b7634-232">In SharePoint Online</span></span>

<span data-ttu-id="b7634-233">Узнайте [, как перемещать файлы в SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).</span><span class="sxs-lookup"><span data-stu-id="b7634-233">See [How to move files in SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="b7634-234">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7634-234">Using PowerShell</span></span>

<span data-ttu-id="b7634-235">Скачайте и установите [командную консоль SharePoint Online](https://www.microsoft.com/download/details.aspx?id=35588), если вы еще этого не сделали.</span><span class="sxs-lookup"><span data-stu-id="b7634-235">Download and install the [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588), if you haven't already.</span></span> <span data-ttu-id="b7634-236">Она включает командлеты, необходимые для перемещения файлов.</span><span class="sxs-lookup"><span data-stu-id="b7634-236">It contains the cmdlets you need to move files.</span></span>  

<span data-ttu-id="b7634-237">С помощью командлета [Connect-пнпонлине](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) подключитесь к сайту группы SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b7634-237">Use the [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) cmdlet to connect to the SharePoint Online team site.</span></span>

```
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

<span data-ttu-id="b7634-238">Для каждого файла, который вы хотите переместить из StaffHub в Teams, используйте командлет [Move-пнпфиле](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) , чтобы переместить файл.</span><span class="sxs-lookup"><span data-stu-id="b7634-238">For each file that you want to move from StaffHub to Teams, use the [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) cmdlet to move the file.</span></span>

```
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

<span data-ttu-id="b7634-239">Чтобы переместить несколько файлов, выполните цикл по файлам и запустите вторую команду в цикле.</span><span class="sxs-lookup"><span data-stu-id="b7634-239">To move multiple files, loop over the files and run the second command on the loop.</span></span> <span data-ttu-id="b7634-240">Если сеанс остается активным, вам не нужно повторять первую команду.</span><span class="sxs-lookup"><span data-stu-id="b7634-240">You don't need to repeat the first command if the session remains active.</span></span>

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a><span data-ttu-id="b7634-241">Переход за пределы пилотной версии и перемещение всех StaffHub Teams</span><span class="sxs-lookup"><span data-stu-id="b7634-241">Go beyond your pilot and move all StaffHub teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="b7634-242">Формирование сведений о состоянии</span><span class="sxs-lookup"><span data-stu-id="b7634-242">Raise awareness</span></span>

<span data-ttu-id="b7634-243">Когда вы будете готовы к переходу за пределы пилотных групп и перемещайте StaffHub Teams вашей организации в Teams, важно сначала сообщить о них в рамках своей организации.</span><span class="sxs-lookup"><span data-stu-id="b7634-243">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="b7634-244">Разработайте Word по сменам и переходам в Teams, чтобы привлечь внимание к осведомленности, создать особенности и внедрять диски.</span><span class="sxs-lookup"><span data-stu-id="b7634-244">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams"></a><span data-ttu-id="b7634-245">Перемещение StaffHubных групп</span><span class="sxs-lookup"><span data-stu-id="b7634-245">Move your StaffHub teams</span></span>

<span data-ttu-id="b7634-246">Чтобы переместить StaffHub Teams, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="b7634-246">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="b7634-247">Вы можете переместить все группы StaffHub организации или переместить определенные StaffHub команды.</span><span class="sxs-lookup"><span data-stu-id="b7634-247">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="b7634-248">Если вы хотите переместить StaffHub команды по одной, ознакомьтесь со сведениями в разделе [Перемещение группы StaffHub](#move-a-staffhub-team).</span><span class="sxs-lookup"><span data-stu-id="b7634-248">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team).</span></span>

#### <a name="move-all-staffhub-teams"></a><span data-ttu-id="b7634-249">Перемещение всех StaffHub Teams</span><span class="sxs-lookup"><span data-stu-id="b7634-249">Move all StaffHub teams</span></span>

<span data-ttu-id="b7634-250">Выполните указанные ниже действия, чтобы получить список всех групп StaffHub в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b7634-250">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```
$StaffHubTeams = Get-StaffHubTeamsForTenant
$StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq ‘StaffHub’ }
```

<span data-ttu-id="b7634-251">Затем выполните указанные ниже действия, чтобы переместить все команды.</span><span class="sxs-lookup"><span data-stu-id="b7634-251">Then, run the following to move all teams.</span></span>

```
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

<span data-ttu-id="b7634-252">Вот пример ответа.</span><span class="sxs-lookup"><span data-stu-id="b7634-252">Here's an example of the response.</span></span>

<span data-ttu-id="b7634-253">Для любой команды, которая уже была перемещена в Teams или уже существует в Teams, идентификатором jobId будет "null", так как задание не нужно отправлять для перемещения этой команды.</span><span class="sxs-lookup"><span data-stu-id="b7634-253">For any team that was already moved to Teams or already exists in Teams, the jobId will be "null" as a job doesn't need to be submitted to move that team.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a><span data-ttu-id="b7634-254">Перемещение конкретных StaffHubных групп</span><span class="sxs-lookup"><span data-stu-id="b7634-254">Move specific StaffHub teams</span></span>

<span data-ttu-id="b7634-255">Выполните указанные ниже действия, чтобы получить список всех идентификаторов участников группы StaffHub в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b7634-255">Run the following to get a list of all StaffHub team Ids in your organization.</span></span>

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="b7634-256">В результатах, возвращенных `Get-StaffHubteamsForTenant` командлетом, который вы выполняли раньше, выберите идентификаторы, которые вы хотите переместить, а затем добавьте их в CSV-файл, в котором значения разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="b7634-256">In the results returned by the `Get-StaffHubteamsForTenant` cmdlet you ran earlier, select the Team Ids you want to move, and then add them to a comma-separated values (CSV) file.</span></span>

<span data-ttu-id="b7634-257">Ниже приведен пример форматирования CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="b7634-257">Here's an example of how the CSV file should be formatted.</span></span>

|<span data-ttu-id="b7634-258">Номер</span><span class="sxs-lookup"><span data-stu-id="b7634-258">Id</span></span>  |
|---------|
|<span data-ttu-id="b7634-259">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="b7634-259">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="b7634-260">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="b7634-260">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="b7634-261">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="b7634-261">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="b7634-262">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="b7634-262">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="b7634-263">Создав CSV-файл, выполните указанные ниже действия, чтобы переместить указанные в CSV-файл команды.</span><span class="sxs-lookup"><span data-stu-id="b7634-263">After you create the CSV file, run the following to move the teams you specified in the CSV file.</span></span>

```
$StaffHubTeams = Import-Csv .\teams.csv
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a><span data-ttu-id="b7634-264">Убедитесь в том, что StaffHub Teams переместились в Teams</span><span class="sxs-lookup"><span data-stu-id="b7634-264">Confirm that your StaffHub teams have moved to Teams</span></span>

<span data-ttu-id="b7634-265">Выполните указанные ниже действия, чтобы получить список всех команд в сменах в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b7634-265">Run the following to get a list of all teams in Shifts in your organization.</span></span> 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a><span data-ttu-id="b7634-266">Перемещение файлов из StaffHub Teams в Teams</span><span class="sxs-lookup"><span data-stu-id="b7634-266">Move files from your StaffHub teams to Teams</span></span>

<span data-ttu-id="b7634-267">Если перемещенные команды StaffHub содержат файлы, которые вы также хотите переместить в Teams, ознакомьтесь с разметкой [Перемещение файлов из группы StaffHub в команды](#move-files-from-a-staffhub-team-to-teams).</span><span class="sxs-lookup"><span data-stu-id="b7634-267">If the StaffHub teams that you moved contain files that you also want to move to Teams, see [Move files from a StaffHub team to Teams](#move-files-from-a-staffhub-team-to-teams).</span></span>

## <a name="monitor-teams-usage"></a><span data-ttu-id="b7634-268">Мониторинг использования групп</span><span class="sxs-lookup"><span data-stu-id="b7634-268">Monitor Teams usage</span></span>

<span data-ttu-id="b7634-269">С помощью отчетов об использовании вы сможете лучше разобраться в использовании шаблонов использования и получить информацию о том, где следует определять приоритетные обучающие и коммуникационные возможности в Организации.</span><span class="sxs-lookup"><span data-stu-id="b7634-269">Usage reports can help you better understand usage patterns and give you insights on where to prioritize training and communication efforts across your organization.</span></span> <span data-ttu-id="b7634-270">Вы можете запускать отчеты, которые показывают общее использование Teams, типы действий, выполняемых пользователями в Teams, способы подключения пользователей к Teams и многое другое.</span><span class="sxs-lookup"><span data-stu-id="b7634-270">You can run reports that show you overall Teams usage, the types of activities that users perform in Teams, how users connect to Teams, and more.</span></span> <span data-ttu-id="b7634-271">Дополнительные сведения можно найти в разделе Отчеты [Teams в центре администрирования Microsoft Teams](../../teams-analytics-and-reports/teams-reporting-reference.md) и в [отчетах об активности в Teams в центре администрирования Microsoft 365](../../teams-activity-reports.md).</span><span class="sxs-lookup"><span data-stu-id="b7634-271">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="b7634-272">Поиск и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="b7634-272">Troubleshooting</span></span>

<span data-ttu-id="b7634-273">**При попытке переместить файлы из StaffHub в Teams появляется сообщение об ошибке "отказано в доступе".**</span><span class="sxs-lookup"><span data-stu-id="b7634-273">**When you try to move files from StaffHub to Teams, you get a "Permission denied" error message.**</span></span>

<span data-ttu-id="b7634-274">Это может происходить, если вы пытаетесь переместить файлы в закрытой группе Office 365, которую вы не являетесь участником.</span><span class="sxs-lookup"><span data-stu-id="b7634-274">This may occur if you're trying to move files in a private Office 365 group that you're not a member of.</span></span> <span data-ttu-id="b7634-275">Если это так, добавьте себя в группу StaffHub с помощью командлета [аддстаффхубмембер](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) , а затем переместите файлы.</span><span class="sxs-lookup"><span data-stu-id="b7634-275">If this is the case, use the [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) cmdlet to add yourself to the StaffHub team, and then move the files.</span></span> <span data-ttu-id="b7634-276">После перемещения файлов используйте командлет [Remove-стаффхубмембер](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) , чтобы удалить себя из команды.</span><span class="sxs-lookup"><span data-stu-id="b7634-276">After you move the files, use the [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) cmdlet to remove yourself from the team.</span></span> 

<span data-ttu-id="b7634-277">**При попытке переместить файлы из StaffHub в Teams появляется сообщение об ошибке, в котором говорится, что общая папка не существует.**</span><span class="sxs-lookup"><span data-stu-id="b7634-277">**When you try to move files from StaffHub to Teams, you get an error that says the General folder doesn't exist.**</span></span>

<span data-ttu-id="b7634-278">Выполните следующую команду, чтобы добавить общую папку в SharePoint, а затем повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="b7634-278">Run the following command to add the General folder to SharePoint, and then try again:</span></span>

  ```
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a><span data-ttu-id="b7634-279">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="b7634-279">Related topics</span></span>
- [<span data-ttu-id="b7634-280">Как выполнить развертывание Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b7634-280">How to roll out Microsoft Teams</span></span>](../../How-to-roll-out-teams.md)
- [<span data-ttu-id="b7634-281">Прекращение поддержки Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="b7634-281">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="b7634-282">Управление приложением "Смены" для вашей организации в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b7634-282">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="b7634-283">Справочник по StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7634-283">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
