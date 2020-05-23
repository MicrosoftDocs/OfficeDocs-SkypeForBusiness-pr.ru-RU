---
title: Перемещение StaffHubных групп в смену
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu, gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Сведения о том, как перемещаться по Microsoft StaffHub Teams и планировать данные для смены в Microsoft Teams.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- SPO_Content
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f449d20f4364629185f719c3217023107f774dd9
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350313"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="d2c76-103">Перемещайте Microsoft StaffHub Teams по сменам в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d2c76-103">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d2c76-104">Действующий 30 июня 2020 г. Корпорация Microsoft StaffHub будет прекращена.</span><span class="sxs-lookup"><span data-stu-id="d2c76-104">Effective June 30, 2020, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="d2c76-105">Мы создаем возможности StaffHub в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d2c76-105">We're building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="d2c76-106">Сегодня команды включают в себя приложение смен для управления планированием и дополнительные возможности, которые будут вычислены с течением времени.</span><span class="sxs-lookup"><span data-stu-id="d2c76-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="d2c76-107">StaffHub перестанет работать для всех пользователей 30 июня 2020 г.</span><span class="sxs-lookup"><span data-stu-id="d2c76-107">StaffHub will stop working for all users on June 30, 2020.</span></span> <span data-ttu-id="d2c76-108">Каждый, кто пытается открыть StaffHub, будет показывать сообщение, направленное на загрузку групп.</span><span class="sxs-lookup"><span data-stu-id="d2c76-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="d2c76-109">Дополнительные сведения можно найти в [статье Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="d2c76-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

<span data-ttu-id="d2c76-110">Приложение «смена» в Teams предоставляет простой подход к управлению расписаниями и постоянным потоком сменных и отменяющих переходов, происходящих в повседневной основе.</span><span class="sxs-lookup"><span data-stu-id="d2c76-110">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="d2c76-111">Участники групп могут получать доступ к своим расписаниям и сменам данных непосредственно в приложении, а также на разных устройствах для настройки их настроек, управления расписаниями и запроса времени.</span><span class="sxs-lookup"><span data-stu-id="d2c76-111">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="d2c76-112">В этой статье рассказывается о том, как переместить StaffHub Teams в Организации и спланировать данные для смены в Teams.</span><span class="sxs-lookup"><span data-stu-id="d2c76-112">This article walks you through how to move your organization's StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="d2c76-113">В нем рассматриваются следующие вопросы:</span><span class="sxs-lookup"><span data-stu-id="d2c76-113">It covers:</span></span>

- [<span data-ttu-id="d2c76-114">Что нужно знать о переходе в Teams</span><span class="sxs-lookup"><span data-stu-id="d2c76-114">What you need to know about the move to Teams</span></span>](#what-you-need-to-know-about-the-move-to-teams)
- [<span data-ttu-id="d2c76-115">Подготовку</span><span class="sxs-lookup"><span data-stu-id="d2c76-115">Prepare</span></span>](#prepare)
- [<span data-ttu-id="d2c76-116">Проведение пилотной программы</span><span class="sxs-lookup"><span data-stu-id="d2c76-116">Conduct a pilot</span></span>](#conduct-a-pilot) 
- [<span data-ttu-id="d2c76-117">Переход за пределы пилотной версии и перемещение всех StaffHub Teams</span><span class="sxs-lookup"><span data-stu-id="d2c76-117">Go beyond your pilot and move all StaffHub teams</span></span>](#go-beyond-your-pilot-and-move-all-staffhub-teams)
- [<span data-ttu-id="d2c76-118">Мониторинг использования групп</span><span class="sxs-lookup"><span data-stu-id="d2c76-118">Monitor Teams usage</span></span>](#monitor-teams-usage)
- [<span data-ttu-id="d2c76-119">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="d2c76-119">Troubleshooting</span></span>](#troubleshooting)

<span data-ttu-id="d2c76-120">Если вы занимаетесь малым предприятием из одной или двух групп StaffHub или крупного предприятия с сотнями StaffHub Teams, здесь вы найдете инструкции для администраторов, которые помогут вам успешно выполнить переход в Teams.</span><span class="sxs-lookup"><span data-stu-id="d2c76-120">Whether you're a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you'll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="d2c76-121">Для выполнения действий, описанных в этой статье, необходимо быть глобальным администратором.</span><span class="sxs-lookup"><span data-stu-id="d2c76-121">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="d2c76-122">Если вы еще не сделали этого, ознакомьтесь с разделами " [вопросы и ответы" в StaffHub о выбытиех](microsoft-staffhub-to-be-retired.md) для получения ответов на любые возникающие вопросы.</span><span class="sxs-lookup"><span data-stu-id="d2c76-122">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span>

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="d2c76-123">Что нужно знать о переходе в Teams</span><span class="sxs-lookup"><span data-stu-id="d2c76-123">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="d2c76-124">Переход в Teams</span><span class="sxs-lookup"><span data-stu-id="d2c76-124">When to move to Teams</span></span>

<span data-ttu-id="d2c76-125">Действующий 30 июня 2020 г. StaffHub будет прекращена.</span><span class="sxs-lookup"><span data-stu-id="d2c76-125">Effective June 30, 2020, StaffHub will be retired.</span></span> <span data-ttu-id="d2c76-126">Мы рекомендуем вам приступить к работе с Teams сегодня и начать переход с групп и пользователей вашей организации из StaffHub.</span><span class="sxs-lookup"><span data-stu-id="d2c76-126">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="d2c76-127">Управление расписаниями является наиболее часто используемой функцией StaffHub, поэтому мы рекомендуем использовать приложение "смены" в Teams для перемещения вперед.</span><span class="sxs-lookup"><span data-stu-id="d2c76-127">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="d2c76-128">Что перемещается в Teams</span><span class="sxs-lookup"><span data-stu-id="d2c76-128">What is moved to Teams</span></span>

<span data-ttu-id="d2c76-129">Когда вы перемещаете группу StaffHub, сведения о членстве в группах, пользовательские расписания и данные чата перемещаются в Teams.</span><span class="sxs-lookup"><span data-stu-id="d2c76-129">When you move a StaffHub team, team membership, user details, team schedules, and chat data are moved to Teams.</span></span> <span data-ttu-id="d2c76-130">Файлы не перемещаются при перемещении команды StaffHub.</span><span class="sxs-lookup"><span data-stu-id="d2c76-130">Files aren't moved when you move a StaffHub team.</span></span> <span data-ttu-id="d2c76-131">Если группа StaffHub включает файлы, которые вы также хотите переместить в Teams, вы можете переместить их на отдельном этапе.</span><span class="sxs-lookup"><span data-stu-id="d2c76-131">If a StaffHub team contains files that you also want to move to teams, you move the files in a separate step.</span></span>

<span data-ttu-id="d2c76-132">Каждой команде StaffHub нужна соответствующая группа Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="d2c76-132">Every StaffHub team needs a corresponding Microsoft 365 or Office 365 Group.</span></span> <span data-ttu-id="d2c76-133">Если группа StaffHub связана с группой Microsoft 365, параметр конфиденциальности группы сохраняется при перемещении команды.</span><span class="sxs-lookup"><span data-stu-id="d2c76-133">If a StaffHub team is associated with a Microsoft 365 Group, the privacy setting of the group is retained when you move the team.</span></span> <span data-ttu-id="d2c76-134">Если у группы StaffHub нет группы Microsoft 365, связанной с ней, автоматически создается группа с параметром конфиденциальности Private, позволяющая вам поддерживать переход.</span><span class="sxs-lookup"><span data-stu-id="d2c76-134">If a StaffHub team doesn't have a Microsoft 365 Group associated with it, a group with a privacy setting of Private is automatically created for you to support the transition.</span></span>  <span data-ttu-id="d2c76-135">С учетом различий в именовании групп и групп между группами и StaffHub в Teams может быть указано другое имя группы.</span><span class="sxs-lookup"><span data-stu-id="d2c76-135">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span> 

<span data-ttu-id="d2c76-136">По мере перевода групп из StaffHub в Teams пользователи больше не смогут получать доступ к своим расписаниям в StaffHub и перенаправляться на смены в Teams.</span><span class="sxs-lookup"><span data-stu-id="d2c76-136">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="d2c76-137">Мы рекомендуем вам сообщать об этом изменении в своей организации, чтобы свести к минимуму перерывы и предоставить пользователям возможность принимать и изучать команды.</span><span class="sxs-lookup"><span data-stu-id="d2c76-137">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span> <span data-ttu-id="d2c76-138">Если у вас есть Azure AD Premium, вы можете [запустить отчет](run-report-to-show-staffhub-usage.md) , чтобы получить список пользователей StaffHub в вашей организации, которым нужно знать об этом изменении.</span><span class="sxs-lookup"><span data-stu-id="d2c76-138">If you have Azure AD Premium, you can [run a report](run-report-to-show-staffhub-usage.md) to get a list of StaffHub users in your organization who need to know about this change.</span></span>  

<span data-ttu-id="d2c76-139">После того как вы перемещаете группу StaffHub в Teams, вы не сможете выполнить откат.</span><span class="sxs-lookup"><span data-stu-id="d2c76-139">There's no rollback option after you move a StaffHub team to Teams.</span></span>

### <a name="user-experience-when-you-move-a-team"></a><span data-ttu-id="d2c76-140">Взаимодействие с пользователем при перемещении команды</span><span class="sxs-lookup"><span data-stu-id="d2c76-140">User experience when you move a team</span></span>

<span data-ttu-id="d2c76-141">Минимальная продолжительность простоя (менее чем секунда, если она есть) для пользователей при переключении с StaffHub на смену в Teams.</span><span class="sxs-lookup"><span data-stu-id="d2c76-141">There's minimal downtime (less than a second, if any at all) for users when their team is switched from StaffHub to Shifts in Teams.</span></span> <span data-ttu-id="d2c76-142">Пользователи могут продолжать пользоваться StaffHub, пока не завершится переход в Teams.</span><span class="sxs-lookup"><span data-stu-id="d2c76-142">Users can continue using StaffHub until the move to Teams is completed.</span></span> <span data-ttu-id="d2c76-143">После завершения перемещения участники команды увидят сообщение о том, что они должны приступить к использованию смен в Teams, чтобы получить доступ к своему календарному плану.</span><span class="sxs-lookup"><span data-stu-id="d2c76-143">When the move is completed, team members will see a message to let them know that they need to start using Shifts in Teams to access their team schedule.</span></span> <span data-ttu-id="d2c76-144">Ниже приведен пример сообщения, которое пользователи видят в StaffHub после перемещения группы StaffHub в Teams.</span><span class="sxs-lookup"><span data-stu-id="d2c76-144">Here's an example of the message that users see in StaffHub after the StaffHub team is moved to Teams.</span></span>

<span data-ttu-id="d2c76-145">![Пример сообщения, которое видят пользователи.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Пример сообщения, которое пользователи видят в StaffHub после перемещения группы StaffHub в Teams")</span><span class="sxs-lookup"><span data-stu-id="d2c76-145">![Example of the message that users see.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Example of the message that users see in StaffHub after the StaffHub team is moved to Teams")</span></span>

## <a name="prepare"></a><span data-ttu-id="d2c76-146">Подготовку</span><span class="sxs-lookup"><span data-stu-id="d2c76-146">Prepare</span></span>

<span data-ttu-id="d2c76-147">Вот как можно подготовиться к переходу на Teams.</span><span class="sxs-lookup"><span data-stu-id="d2c76-147">Here's how to prepare for the move to Teams.</span></span>

### <a name="check-that-prerequisites-are-met"></a><span data-ttu-id="d2c76-148">Проверка соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="d2c76-148">Check that prerequisites are met</span></span>

<span data-ttu-id="d2c76-149">Перед перемещением группы StaffHub в Teams убедитесь в том, что:</span><span class="sxs-lookup"><span data-stu-id="d2c76-149">Before you move a StaffHub team to Teams, make sure that:</span></span>

- <span data-ttu-id="d2c76-150">Вход пользователя в систему является глобальным администратором.</span><span class="sxs-lookup"><span data-stu-id="d2c76-150">The signed-in user is a global admin.</span></span>
- <span data-ttu-id="d2c76-151">Teams включена для всех пользователей в клиенте.</span><span class="sxs-lookup"><span data-stu-id="d2c76-151">Teams is enabled for all users in the tenant.</span></span>
- <span data-ttu-id="d2c76-152">Поддержка создания групп Microsoft 365 в клиенте включена.</span><span class="sxs-lookup"><span data-stu-id="d2c76-152">Microsoft 365 Groups creation is enabled in the tenant.</span></span>
- <span data-ttu-id="d2c76-153">StaffHub teamId является допустимым.</span><span class="sxs-lookup"><span data-stu-id="d2c76-153">The StaffHub teamId is valid.</span></span>
- <span data-ttu-id="d2c76-154">У группы StaffHub есть по крайней мере один владелец группы.</span><span class="sxs-lookup"><span data-stu-id="d2c76-154">The StaffHub team has at least one team owner.</span></span>
- <span data-ttu-id="d2c76-155">Группа StaffHub включает в себя участников.</span><span class="sxs-lookup"><span data-stu-id="d2c76-155">The StaffHub team contains members.</span></span>
- <span data-ttu-id="d2c76-156">Все участники группы StaffHub связаны с учетной записью Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d2c76-156">All StaffHub team members are linked to an Azure AD account.</span></span>
- <span data-ttu-id="d2c76-157">Всем участникам группы StaffHub назначается лицензия на команды Teams.</span><span class="sxs-lookup"><span data-stu-id="d2c76-157">All StaffHub team members are assigned a Teams license.</span></span>  

<span data-ttu-id="d2c76-158">Если эти условия не соблюдаются, запрос на перемещение завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="d2c76-158">If these prerequisites aren't met, the move request will fail.</span></span>

### <a name="assign-teams-licenses"></a><span data-ttu-id="d2c76-159">Назначение лицензий Teams</span><span class="sxs-lookup"><span data-stu-id="d2c76-159">Assign Teams licenses</span></span>

<span data-ttu-id="d2c76-160">Каждый пользователь должен иметь действующую лицензию Microsoft 365 или Office 365 из [подходящего плана](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) , и ему должна быть назначена лицензия Teams.</span><span class="sxs-lookup"><span data-stu-id="d2c76-160">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="d2c76-161">Назначение лицензии на команды пользователям предоставляет им доступ к Teams.</span><span class="sxs-lookup"><span data-stu-id="d2c76-161">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="d2c76-162">Вы управляете лицензиями Teams в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d2c76-162">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="d2c76-163">Дополнительные сведения см. в статье [Управление доступом пользователей к Teams](../../user-access.md).</span><span class="sxs-lookup"><span data-stu-id="d2c76-163">To learn more, see [Manage user access to Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d2c76-164">Если в вашей организации используется Skype для бизнеса, и вы не готовы переместить всех пользователей в Teams, вы можете включить команды для сотрудников Firstline, которые смогут запускать команды вместе со Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="d2c76-164">If your organization uses Skype for Business and you're not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="d2c76-165">В режиме совместного существования под названием *острова*все клиентские приложения работают как отдельные решения.</span><span class="sxs-lookup"><span data-stu-id="d2c76-165">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="d2c76-166">Дополнительные сведения можно найти в статье [понимание групп, а также взаимодействие и совместимость Skype для бизнеса](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="d2c76-166">To learn more, see [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="install-the-prerelease-version-of-the-staffhub-powershell-module"></a><span data-ttu-id="d2c76-167">Установка предварительной версии модуля PowerShell StaffHub</span><span class="sxs-lookup"><span data-stu-id="d2c76-167">Install the prerelease version of the StaffHub PowerShell module</span></span>

<span data-ttu-id="d2c76-168">Установите предварительную [версию модуля PowerShell StaffHub](install-the-staffhub-powershell-module.md), если вы еще не сделали этого.</span><span class="sxs-lookup"><span data-stu-id="d2c76-168">If you haven't already, [install the prerelease version of the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span>

<span data-ttu-id="d2c76-169">Для перемещения групп StaffHub в Teams необходимо установить предварительную версию модуля.</span><span class="sxs-lookup"><span data-stu-id="d2c76-169">You must have the prerelease version of the module installed to move your StaffHub teams to Teams.</span></span>

### <a name="link-an-azure-ad-account-for-staffhub-team-members-who-dont-have-one"></a><span data-ttu-id="d2c76-170">Связывание учетной записи Azure AD с участниками группы StaffHub, у которых нет одной</span><span class="sxs-lookup"><span data-stu-id="d2c76-170">Link an Azure AD account for StaffHub team members who don't have one</span></span>

<span data-ttu-id="d2c76-171">Каждый участник группы StaffHub должен быть связан с учетной записью Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="d2c76-171">Each StaffHub team member must be linked to an Azure Active Directory (Azure AD) account.</span></span> <span data-ttu-id="d2c76-172">Пользователи в вашей организации не будут связаны с учетной записью Azure AD, если применимы следующие сценарии:</span><span class="sxs-lookup"><span data-stu-id="d2c76-172">Users in your organization won't be linked to an Azure AD account if any of the following scenarios apply:</span></span>

- <span data-ttu-id="d2c76-173">Владелец команды добавил пользователя, у которого нет учетной записи Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d2c76-173">A team owner added a user who doesn't have an Azure AD account.</span></span>
- <span data-ttu-id="d2c76-174">Владелец команды пригласил пользователя в группу StaffHub, и этот пользователь не пригласится на приглашение.</span><span class="sxs-lookup"><span data-stu-id="d2c76-174">A team owner invited a user to a StaffHub team and that user didn't accept the invitation.</span></span>

<span data-ttu-id="d2c76-175">Эти пользователи имеют неактивные учетные записи и показывают состояние пользователя "неизвестно", "приглашены" или "InviteRejected".</span><span class="sxs-lookup"><span data-stu-id="d2c76-175">These users have inactive accounts and show a user state of Unknown, Invited, or InviteRejected.</span></span> <span data-ttu-id="d2c76-176">Вы можете связать учетную запись Azure AD для этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="d2c76-176">You can link an Azure AD account for these users.</span></span>  <span data-ttu-id="d2c76-177">Ниже описано, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="d2c76-177">Here's how.</span></span>

#### <a name="get-a-list-of-all-inactive-accounts-on-staffhub-teams"></a><span data-ttu-id="d2c76-178">Получение списка всех неактивных учетных записей в StaffHub Teams</span><span class="sxs-lookup"><span data-stu-id="d2c76-178">Get a list of all inactive accounts on StaffHub teams</span></span>

<span data-ttu-id="d2c76-179">Выполните следующую последовательность команд, чтобы получить список всех неактивных учетных записей в StaffHub Teams и экспортировать список в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="d2c76-179">Run the following series of commands to get a list of all inactive accounts on StaffHub teams and export the list to a CSV file.</span></span> <span data-ttu-id="d2c76-180">Каждая команда должна выполняться отдельно.</span><span class="sxs-lookup"><span data-stu-id="d2c76-180">Each command should be run separately.</span></span>

```PowerShell
$InvitedUsersObject = @()

$StaffHubTeams = Get-StaffHubTeamsForTenant

$StaffHubTeams[0] = $StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq 'StaffHub' }

foreach($team in $StaffHubTeams[0])
{ 
    Write-host $team.name
    $StaffHubUsers = Get-StaffHubMember -TeamId $team.Id | where {$_.State -eq "Invited"}
    foreach($StaffHubUser in $StaffHubUsers) {
        $InvitedUsersObject  += New-Object PsObject -Property @{
          "TeamID"="$($team.Id)"
          "TeamName"="$($team.name)"
          "MemberID"="$($StaffHubUser.Id)"
            }
    }
}

$InvitedUsersObject | SELECT * | export-csv InvitedUsers.csv -NoTypeInformation  
```

#### <a name="link-the-account"></a><span data-ttu-id="d2c76-181">Связывание учетной записи</span><span class="sxs-lookup"><span data-stu-id="d2c76-181">Link the account</span></span>

<span data-ttu-id="d2c76-182">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="d2c76-182">Do one of the following:</span></span>

- <span data-ttu-id="d2c76-183">Преобразуйте учетную запись и свяжите ее с ней.</span><span class="sxs-lookup"><span data-stu-id="d2c76-183">Convert and link the account.</span></span>

  <span data-ttu-id="d2c76-184">StaffHub владельцы и руководители групп могут преобразовать неактивную учетную запись и связать ее с учетной записью Azure AD в StaffHub, изменив адрес электронной почты пользователя на действительный UPN на странице StaffHub параметры группы.</span><span class="sxs-lookup"><span data-stu-id="d2c76-184">StaffHub team owners and managers can convert an inactive account and link it to an Azure AD account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="d2c76-185">Удалите несвязанную учетную запись, а затем снова добавьте ее с помощью UPN.</span><span class="sxs-lookup"><span data-stu-id="d2c76-185">Remove the unlinked account and then re-add the account by using the UPN.</span></span>
    1. <span data-ttu-id="d2c76-186">Запустите командлет [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubMember?view=staffhub-ps) , чтобы удалить неподготовленную учетную запись из группы StaffHub.</span><span class="sxs-lookup"><span data-stu-id="d2c76-186">Run the [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubMember?view=staffhub-ps) cmdlet to remove the non-provisioned account from the StaffHub team.</span></span>
    2. <span data-ttu-id="d2c76-187">Запустите командлет [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) , чтобы добавить учетную запись обратно в группу StaffHub с помощью UPN.</span><span class="sxs-lookup"><span data-stu-id="d2c76-187">Run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) cmdlet to add the account back to the StaffHub team by using the UPN.</span></span>

- <span data-ttu-id="d2c76-188">Удалите неактивную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="d2c76-188">Remove the inactive account.</span></span> <span data-ttu-id="d2c76-189">Используйте этот параметр, если учетная запись пользователя больше не нужна.</span><span class="sxs-lookup"><span data-stu-id="d2c76-189">Use this option if the user account is no longer needed.</span></span>

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a><span data-ttu-id="d2c76-190">Назначение пользователям политики настройки приложения FirstlineWorker</span><span class="sxs-lookup"><span data-stu-id="d2c76-190">Assign the FirstlineWorker app setup policy to users</span></span>

<span data-ttu-id="d2c76-191">Teams включает встроенную политику настройки приложений FirstlineWorker, которую можно использовать для настройки групп, чтобы выделиться наиболее важными приложениями для Firstline сотрудников вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d2c76-191">Teams includes a built-in FirstlineWorker app setup policy that you can use to customize Teams to highlight the apps that are most important for the Firstline Workers in your organization.</span></span> <span data-ttu-id="d2c76-192">Когда вы назначаете эту политику пользователям, приложения в этой политике будут закреплены на панели приложения в Teams для быстрого и удобного доступа.</span><span class="sxs-lookup"><span data-stu-id="d2c76-192">When you assign this policy to users, the apps in the policy are pinned to the app bar in Teams for quick and easy access.</span></span> <span data-ttu-id="d2c76-193">Другие приложения, добавленные в Teams, можно найти на панели приложения, нажав **... Другие приложения** в классической и веб-клиентах Teams и прокрутка вверх в клиенте Teams Mobile.</span><span class="sxs-lookup"><span data-stu-id="d2c76-193">Other apps added to Teams can be found in the app bar by clicking **... More apps** in the Teams desktop and web clients and by swiping up in the Teams mobile client.</span></span> <span data-ttu-id="d2c76-194">По умолчанию политика настройки приложения FirstlineWorker включает в себя действия, смены, чат и звонки приложений.</span><span class="sxs-lookup"><span data-stu-id="d2c76-194">By default, the FirstlineWorker app setup policy includes the Activity, Shifts, Chat, and Calling apps.</span></span>

<span data-ttu-id="d2c76-195">Инструкции по назначению пользователям политики настройки приложения FirstlineWorker приведены в статье [Использование политики настройки приложения FirstlineWorker для закрепления смен в Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams).</span><span class="sxs-lookup"><span data-stu-id="d2c76-195">For steps on how to assign the FirstlineWorker app setup policy to users, see [Use the FirstlineWorker app setup policy to pin Shifts to Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams).</span></span> <span data-ttu-id="d2c76-196">После назначения политики для вступления в силу может потребоваться несколько часов.</span><span class="sxs-lookup"><span data-stu-id="d2c76-196">After you assign a policy, it can take a few hours to take effect.</span></span>

<span data-ttu-id="d2c76-197">Мы рекомендуем выполнить этот шаг не менее чем за неделю, прежде чем вы сможете переместить StaffHub Teams и пользователей в Teams.</span><span class="sxs-lookup"><span data-stu-id="d2c76-197">We recommend you complete this step at least a week before you move your StaffHub teams and users to Teams.</span></span> <span data-ttu-id="d2c76-198">Когда пользователи находятся в Teams, убедитесь, что они могут просматривать и получать доступ к приложению смены.</span><span class="sxs-lookup"><span data-stu-id="d2c76-198">When users are on Teams, confirm that they can see and access the Shifts app.</span></span>

<span data-ttu-id="d2c76-199">Вы также можете создать пользовательские политики настройки приложений и изменить параметры в политике настройки глобального приложения.</span><span class="sxs-lookup"><span data-stu-id="d2c76-199">You can also create custom app setup policies and edit the settings in the global app setup policy.</span></span> <span data-ttu-id="d2c76-200">Дополнительные сведения можно найти в статье [Управление политиками настройки приложений в Teams](../../teams-app-setup-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d2c76-200">To learn more, check out [Manage app setup policies in Teams](../../teams-app-setup-policies.md).</span></span>

### <a name="onboard-users-to-teams"></a><span data-ttu-id="d2c76-201">Встроенные пользователи в Teams</span><span class="sxs-lookup"><span data-stu-id="d2c76-201">Onboard users to Teams</span></span>

<span data-ttu-id="d2c76-202">В рамках стратегии выставления настольных систем вы можете получать учебные материалы и рекомендации для пользователей, которые помогут им ознакомиться с группами.</span><span class="sxs-lookup"><span data-stu-id="d2c76-202">As part of your onboarding strategy, provide training and guidance for users to help them get familiar with Teams.</span></span> <span data-ttu-id="d2c76-203">Поделитесь следующими ресурсами с пользователями, чтобы они знали, где можно получить клиентов Teams, обучение и поддержку.</span><span class="sxs-lookup"><span data-stu-id="d2c76-203">Share the following resources with users so they know where to get Teams clients, training, and support:</span></span>

- [<span data-ttu-id="d2c76-204">Веб-клиент Teams</span><span class="sxs-lookup"><span data-stu-id="d2c76-204">Teams web client</span></span>](https://teams.microsoft.com)
- [<span data-ttu-id="d2c76-205">Ссылки для скачивания настольной и мобильной версий клиента</span><span class="sxs-lookup"><span data-stu-id="d2c76-205">Desktop and mobile client download links</span></span>](https://teams.microsoft.com/downloads)
- [<span data-ttu-id="d2c76-206">Обучающие видео для Teams</span><span class="sxs-lookup"><span data-stu-id="d2c76-206">Teams training videos</span></span>](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [<span data-ttu-id="d2c76-207">Справочная документация для Teams</span><span class="sxs-lookup"><span data-stu-id="d2c76-207">Teams Help documentation</span></span>](https://support.office.com/teams)

<span data-ttu-id="d2c76-208">Рекомендации по развертыванию групп и внедрению групп можно найти [в разделе Развертывание групп](../../How-to-roll-out-teams.md) и [принятие групп](../../adopt-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="d2c76-208">For guidance on deploying Teams and driving Teams adoption, see [How to roll out Teams](../../How-to-roll-out-teams.md) and [Adopt Teams](../../adopt-microsoft-teams-landing-page.md).</span></span>

## <a name="conduct-a-pilot"></a><span data-ttu-id="d2c76-209">Проведение пилотной программы</span><span class="sxs-lookup"><span data-stu-id="d2c76-209">Conduct a pilot</span></span>

<span data-ttu-id="d2c76-210">Мы рекомендуем начать с перемещения двух или трех групп StaffHub, чтобы выбрать группу ранних переходов.</span><span class="sxs-lookup"><span data-stu-id="d2c76-210">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="d2c76-211">Работа с пилотной версией поможет вам уточнить план перехода и убедиться, что вы готовы переместить все StaffHub Teams вашей организации в Teams.</span><span class="sxs-lookup"><span data-stu-id="d2c76-211">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="d2c76-212">Кроме того, он определяет лидерами, которые помогут вам облегчить внедрение в рамках своей организации.</span><span class="sxs-lookup"><span data-stu-id="d2c76-212">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="d2c76-213">Если вы работаете в малом бизнесе, для которого не требуется поэтапный подход, действия, описанные в этом разделе, могут быть все, что нужно сделать, чтобы перейти с StaffHub на Teams.</span><span class="sxs-lookup"><span data-stu-id="d2c76-213">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="d2c76-214">Определение пилотных команд</span><span class="sxs-lookup"><span data-stu-id="d2c76-214">Identify pilot teams</span></span>

<span data-ttu-id="d2c76-215">Для идентификации двух или трех пилотных команд.</span><span class="sxs-lookup"><span data-stu-id="d2c76-215">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="d2c76-216">Все участники группы должны использовать смены в Teams для управления их расписаниями, общения и совместной работы друг с другом.</span><span class="sxs-lookup"><span data-stu-id="d2c76-216">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="d2c76-217">Определение группы лидерами</span><span class="sxs-lookup"><span data-stu-id="d2c76-217">Identify team champions</span></span>

<span data-ttu-id="d2c76-218">Определите лидерами между пилотными группами и закрепите их, чтобы упростить evangelize смены.</span><span class="sxs-lookup"><span data-stu-id="d2c76-218">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="d2c76-219">Лидерами Teams – это то, что они делают, и делитесь своими опытом для предоставления поддержки и руководств для участников группы.</span><span class="sxs-lookup"><span data-stu-id="d2c76-219">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="d2c76-220">Командные лидерами могут быть владельцами группы или руководителями.</span><span class="sxs-lookup"><span data-stu-id="d2c76-220">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="d2c76-221">Команда лидерами должна обеспечивать настройку для участников группы, выделять время для [получения клиентов](../../get-clients.md)Teams, входить в Teams и проверять расписания в сменах и начинать общение друг с другом.</span><span class="sxs-lookup"><span data-stu-id="d2c76-221">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="d2c76-222">Пользователи, уже знакомые с StaffHub, будут быстро выполняться в сменах.</span><span class="sxs-lookup"><span data-stu-id="d2c76-222">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="d2c76-223">Вы также можете навести на них указатель мыши [, чтобы получить дополнительную помощь.](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)</span><span class="sxs-lookup"><span data-stu-id="d2c76-223">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team"></a><span data-ttu-id="d2c76-224">Перемещение команды StaffHub</span><span class="sxs-lookup"><span data-stu-id="d2c76-224">Move a StaffHub team</span></span>

<span data-ttu-id="d2c76-225">Воспользуйтесь этими инструкциями для перемещения одной команды StaffHub на один раз.</span><span class="sxs-lookup"><span data-stu-id="d2c76-225">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="d2c76-226">Мы рекомендуем этот подход для ваших пилотных команд.</span><span class="sxs-lookup"><span data-stu-id="d2c76-226">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="d2c76-227">Позже, когда вы будете готовы к перемещению всех StaffHubных групп своей организации, читайте в статье [Перемещение групп StaffHub](#move-your-staffhub-teams) , чтобы узнать, как переместить несколько команд за один раз.</span><span class="sxs-lookup"><span data-stu-id="d2c76-227">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="d2c76-228">Чтобы переместить группу StaffHub, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d2c76-228">Run the following to move a StaffHub team.</span></span>

```PowerShell
Move-StaffHubTeam -TeamId <String>
```
<span data-ttu-id="d2c76-229">Образом</span><span class="sxs-lookup"><span data-stu-id="d2c76-229">Example:</span></span>

```PowerShell
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

<span data-ttu-id="d2c76-230">Ниже приведен пример ответа, который вы получаете, когда вы отправляете запрос на перемещение группы StaffHub в Teams.</span><span class="sxs-lookup"><span data-stu-id="d2c76-230">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```console
 jobId                                      teamId                                      teamAlreadyInMicrosofteams  
---------------------------------------    ----------------------------------------    ---------------------------          
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

<span data-ttu-id="d2c76-231">Чтобы проверить состояние запроса на перемещение, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d2c76-231">To check the status of a move request, run the following.</span></span>

```PowerShell
Get-TeamMigrationJobStatus <String>
```
<span data-ttu-id="d2c76-232">Образом</span><span class="sxs-lookup"><span data-stu-id="d2c76-232">Example:</span></span>

```PowerShell
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

<span data-ttu-id="d2c76-233">Ниже приведен пример ответа, который вы получаете при выполнении перемещения.</span><span class="sxs-lookup"><span data-stu-id="d2c76-233">Here's an example of the response you get when a move is in progress.</span></span>

```console
jobId                                     status       teamId                                     isO365GroupCreated  Error
----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a><span data-ttu-id="d2c76-234">Перемещение файлов из группы StaffHub в группы</span><span class="sxs-lookup"><span data-stu-id="d2c76-234">Move files from a StaffHub team to Teams</span></span>

<span data-ttu-id="d2c76-235">Это действие применимо только в том случае, если команда StaffHub, перемещенная в Teams, содержит файлы, которые вы хотите также перейти в группу Teams.</span><span class="sxs-lookup"><span data-stu-id="d2c76-235">This step only applies if the StaffHub team that you moved to Teams has files that you want to also move to Teams.</span></span> <span data-ttu-id="d2c76-236">Вы можете перемещать файлы непосредственно в SharePoint Online или с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d2c76-236">You can move files directly in SharePoint Online or by using PowerShell.</span></span>

#### <a name="in-sharepoint-online"></a><span data-ttu-id="d2c76-237">В SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d2c76-237">In SharePoint Online</span></span>

<span data-ttu-id="d2c76-238">Узнайте [, как перемещать файлы в SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).</span><span class="sxs-lookup"><span data-stu-id="d2c76-238">See [How to move files in SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="d2c76-239">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="d2c76-239">Using PowerShell</span></span>

<span data-ttu-id="d2c76-240">Скачайте и установите [командную консоль SharePoint Online](https://www.microsoft.com/download/details.aspx?id=35588), если вы еще этого не сделали.</span><span class="sxs-lookup"><span data-stu-id="d2c76-240">Download and install the [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588), if you haven't already.</span></span> <span data-ttu-id="d2c76-241">Она включает командлеты, необходимые для перемещения файлов.</span><span class="sxs-lookup"><span data-stu-id="d2c76-241">It contains the cmdlets you need to move files.</span></span>  

<span data-ttu-id="d2c76-242">С помощью командлета [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) подключитесь к сайту группы SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d2c76-242">Use the [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) cmdlet to connect to the SharePoint Online team site.</span></span>

```PowerShell
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

<span data-ttu-id="d2c76-243">Для каждого файла, который вы хотите переместить из StaffHub в Teams, используйте командлет [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) , чтобы переместить файл.</span><span class="sxs-lookup"><span data-stu-id="d2c76-243">For each file that you want to move from StaffHub to Teams, use the [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) cmdlet to move the file.</span></span>

```PowerShell
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

<span data-ttu-id="d2c76-244">Чтобы переместить несколько файлов, выполните цикл по файлам и запустите вторую команду в цикле.</span><span class="sxs-lookup"><span data-stu-id="d2c76-244">To move multiple files, loop over the files and run the second command on the loop.</span></span> <span data-ttu-id="d2c76-245">Если сеанс остается активным, вам не нужно повторять первую команду.</span><span class="sxs-lookup"><span data-stu-id="d2c76-245">You don't need to repeat the first command if the session remains active.</span></span>

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a><span data-ttu-id="d2c76-246">Переход за пределы пилотной версии и перемещение всех StaffHub Teams</span><span class="sxs-lookup"><span data-stu-id="d2c76-246">Go beyond your pilot and move all StaffHub teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="d2c76-247">Формирование сведений о состоянии</span><span class="sxs-lookup"><span data-stu-id="d2c76-247">Raise awareness</span></span>

<span data-ttu-id="d2c76-248">Когда вы будете готовы к переходу за пределы пилотных групп и перемещайте StaffHub Teams вашей организации в Teams, важно сначала сообщить о них в рамках своей организации.</span><span class="sxs-lookup"><span data-stu-id="d2c76-248">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="d2c76-249">Разработайте Word по сменам и переходам в Teams, чтобы привлечь внимание к осведомленности, создать особенности и внедрять диски.</span><span class="sxs-lookup"><span data-stu-id="d2c76-249">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams"></a><span data-ttu-id="d2c76-250">Перемещение StaffHubных групп</span><span class="sxs-lookup"><span data-stu-id="d2c76-250">Move your StaffHub teams</span></span>

<span data-ttu-id="d2c76-251">Чтобы переместить StaffHub Teams, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d2c76-251">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="d2c76-252">Вы можете переместить все группы StaffHub организации или переместить определенные StaffHub команды.</span><span class="sxs-lookup"><span data-stu-id="d2c76-252">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="d2c76-253">Если вы хотите переместить StaffHub команды по одной, ознакомьтесь со сведениями в разделе [Перемещение группы StaffHub](#move-a-staffhub-team).</span><span class="sxs-lookup"><span data-stu-id="d2c76-253">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team).</span></span>

#### <a name="move-all-staffhub-teams"></a><span data-ttu-id="d2c76-254">Перемещение всех StaffHub Teams</span><span class="sxs-lookup"><span data-stu-id="d2c76-254">Move all StaffHub teams</span></span>

<span data-ttu-id="d2c76-255">Выполните указанные ниже действия, чтобы получить список всех групп StaffHub в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d2c76-255">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```PowerShell
$StaffHubTeams = Get-StaffHubTeamsForTenant

$StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq 'StaffHub' }
```

<span data-ttu-id="d2c76-256">Затем выполните указанные ниже действия, чтобы переместить все команды.</span><span class="sxs-lookup"><span data-stu-id="d2c76-256">Then, run the following to move all teams.</span></span>

```PowerShell
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

<span data-ttu-id="d2c76-257">Вот пример ответа.</span><span class="sxs-lookup"><span data-stu-id="d2c76-257">Here's an example of the response.</span></span>

<span data-ttu-id="d2c76-258">Для любой команды, которая уже была перемещена в Teams или уже существует в Teams, идентификатором jobId будет "null", так как задание не нужно отправлять для перемещения этой команды.</span><span class="sxs-lookup"><span data-stu-id="d2c76-258">For any team that was already moved to Teams or already exists in Teams, the jobId will be "null" as a job doesn't need to be submitted to move that team.</span></span>

```console
jobId                                      teamId                                      teamAlreadyInMicrosofteams  
----------------------------------------   -----------------------------------------   --------------------------         
null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a><span data-ttu-id="d2c76-259">Перемещение конкретных StaffHubных групп</span><span class="sxs-lookup"><span data-stu-id="d2c76-259">Move specific StaffHub teams</span></span>

<span data-ttu-id="d2c76-260">Выполните указанные ниже действия, чтобы получить список всех идентификаторов участников группы StaffHub в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d2c76-260">Run the following to get a list of all StaffHub team Ids in your organization.</span></span>

```PowerShell
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="d2c76-261">В результатах, возвращенных `Get-StaffHubteamsForTenant` командлетом, который вы выполняли раньше, выберите идентификаторы, которые вы хотите переместить, а затем добавьте их в CSV-файл, в котором значения разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="d2c76-261">In the results returned by the `Get-StaffHubteamsForTenant` cmdlet you ran earlier, select the Team Ids you want to move, and then add them to a comma-separated values (CSV) file.</span></span>

<span data-ttu-id="d2c76-262">Ниже приведен пример форматирования CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="d2c76-262">Here's an example of how the CSV file should be formatted.</span></span>

|<span data-ttu-id="d2c76-263">Номер</span><span class="sxs-lookup"><span data-stu-id="d2c76-263">Id</span></span>  |
|---------|
|<span data-ttu-id="d2c76-264">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="d2c76-264">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="d2c76-265">TEAM_81b1f191-3e19-45ce-AB32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="d2c76-265">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="d2c76-266">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="d2c76-266">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="d2c76-267">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="d2c76-267">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="d2c76-268">Создав CSV-файл, выполните указанные ниже действия, чтобы переместить указанные в CSV-файл команды.</span><span class="sxs-lookup"><span data-stu-id="d2c76-268">After you create the CSV file, run the following to move the teams you specified in the CSV file.</span></span>

```PowerShell
$StaffHubTeams = Import-Csv .\teams.csv

foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a><span data-ttu-id="d2c76-269">Убедитесь в том, что StaffHub Teams переместились в Teams</span><span class="sxs-lookup"><span data-stu-id="d2c76-269">Confirm that your StaffHub teams have moved to Teams</span></span>

<span data-ttu-id="d2c76-270">Выполните указанные ниже действия, чтобы получить список всех команд в сменах в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d2c76-270">Run the following to get a list of all teams in Shifts in your organization.</span></span> 

```PowerShell
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a><span data-ttu-id="d2c76-271">Перемещение файлов из StaffHub Teams в Teams</span><span class="sxs-lookup"><span data-stu-id="d2c76-271">Move files from your StaffHub teams to Teams</span></span>

<span data-ttu-id="d2c76-272">Если перемещенные команды StaffHub содержат файлы, которые вы также хотите переместить в Teams, ознакомьтесь с разметкой [Перемещение файлов из группы StaffHub в команды](#move-files-from-a-staffhub-team-to-teams).</span><span class="sxs-lookup"><span data-stu-id="d2c76-272">If the StaffHub teams that you moved contain files that you also want to move to Teams, see [Move files from a StaffHub team to Teams](#move-files-from-a-staffhub-team-to-teams).</span></span>

## <a name="monitor-teams-usage"></a><span data-ttu-id="d2c76-273">Мониторинг использования групп</span><span class="sxs-lookup"><span data-stu-id="d2c76-273">Monitor Teams usage</span></span>

<span data-ttu-id="d2c76-274">С помощью отчетов об использовании вы сможете лучше разобраться в использовании шаблонов использования и получить информацию о том, где следует определять приоритетные обучающие и коммуникационные возможности в Организации.</span><span class="sxs-lookup"><span data-stu-id="d2c76-274">Usage reports can help you better understand usage patterns and give you insights on where to prioritize training and communication efforts across your organization.</span></span> <span data-ttu-id="d2c76-275">Вы можете запускать отчеты, которые показывают общее использование Teams, типы действий, выполняемых пользователями в Teams, способы подключения пользователей к Teams и многое другое.</span><span class="sxs-lookup"><span data-stu-id="d2c76-275">You can run reports that show you overall Teams usage, the types of activities that users perform in Teams, how users connect to Teams, and more.</span></span> <span data-ttu-id="d2c76-276">Дополнительные сведения можно найти в разделе Отчеты [Teams в центре администрирования Microsoft Teams](../../teams-analytics-and-reports/teams-reporting-reference.md) и в [отчетах об активности в Teams в центре администрирования Microsoft 365](../../teams-activity-reports.md).</span><span class="sxs-lookup"><span data-stu-id="d2c76-276">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="d2c76-277">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="d2c76-277">Troubleshooting</span></span>

<span data-ttu-id="d2c76-278">**Получение дополнительных сведений об ошибках сбоя**</span><span class="sxs-lookup"><span data-stu-id="d2c76-278">**How to get more information about failure errors**</span></span>

<span data-ttu-id="d2c76-279">Чтобы получить дополнительные сведения об ошибках, возникающих при попытке переместить группу, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d2c76-279">Run the following to get more information about "Failure" errors that occur when you try to move a team:</span></span>

```PowerShell
Move-StaffHubTeam -TeamId <TeamId>

$res = Get-TeamMigrationJobStatus -JobId <JobId>

$res.Status
```

<span data-ttu-id="d2c76-280">Вы увидите одно из следующих возвращенных состояний: успешное выполнение, сбой, в очереди.</span><span class="sxs-lookup"><span data-stu-id="d2c76-280">You'll see one of the following statuses returned: Success, Failure, InProgress, Queued.</span></span>

<span data-ttu-id="d2c76-281">Если возвращено значение "сбой", выполните указанные ниже действия, чтобы получить дополнительные сведения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="d2c76-281">If "Failure" is returned, run the following to get more information about the error:</span></span>

```PowerShell
$res.Result.Error.Innererror
```

<span data-ttu-id="d2c76-282">**При попытке переместить группу StaffHub появляется сообщение об ошибке "не удалось получить категории соответствующих КОНФИГУРАЦИй для пользователя".**</span><span class="sxs-lookup"><span data-stu-id="d2c76-282">**When you try to move a StaffHub team, the status shows as "Failure" and you receive a "Failed to retrieve applicable SKU categories for the user" error message**</span></span>

<span data-ttu-id="d2c76-283">Это может быть вызвано тем, что у одного или нескольких участников команды нет лицензии на команды.</span><span class="sxs-lookup"><span data-stu-id="d2c76-283">This can occur if one or more team members don't have a Teams license.</span></span> <span data-ttu-id="d2c76-284">Перейдите на portal.office.com, найдите группу и убедитесь, что участникам группы назначена лицензия на команды.</span><span class="sxs-lookup"><span data-stu-id="d2c76-284">Go to portal.office.com, find the group, and then confirm that group members are assigned a Teams license.</span></span>

<span data-ttu-id="d2c76-285">**При попытке переместить группу StaffHub отображается состояние "сбой", и появляется сообщение об ошибке "владелец группы не найден"**</span><span class="sxs-lookup"><span data-stu-id="d2c76-285">**When you try to move a StaffHub team, the status shows as "Failure" and you receive a "Team owner not found" error message**</span></span>

<span data-ttu-id="d2c76-286">Это может произойти, если группа, связанная с командой StaffHub, не имеет владельца команды.</span><span class="sxs-lookup"><span data-stu-id="d2c76-286">This can occur if the group that's associated with the StaffHub team doesn't have a team owner.</span></span> <span data-ttu-id="d2c76-287">Перейдите в portal.office.com, найдите группу и добавьте в нее одного или нескольких владельцев.</span><span class="sxs-lookup"><span data-stu-id="d2c76-287">Go to portal.office.com, find the group, and then add one or more owners to the group.</span></span>

<span data-ttu-id="d2c76-288">**При попытке переместить файлы из StaffHub в Teams появляется сообщение об ошибке "отказано в доступе".**</span><span class="sxs-lookup"><span data-stu-id="d2c76-288">**When you try to move files from StaffHub to Teams, you get a "Permission denied" error message.**</span></span>

<span data-ttu-id="d2c76-289">Это может происходить, если вы пытаетесь переместить файлы в закрытой группе Microsoft 365, в которой вы не являетесь участником.</span><span class="sxs-lookup"><span data-stu-id="d2c76-289">This may occur if you're trying to move files in a private Microsoft 365 group that you're not a member of.</span></span> <span data-ttu-id="d2c76-290">Если это так, добавьте себя в группу StaffHub с помощью командлета [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) , а затем переместите файлы.</span><span class="sxs-lookup"><span data-stu-id="d2c76-290">If this is the case, use the [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) cmdlet to add yourself to the StaffHub team, and then move the files.</span></span> <span data-ttu-id="d2c76-291">После перемещения файлов используйте командлет [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) , чтобы удалить себя из команды.</span><span class="sxs-lookup"><span data-stu-id="d2c76-291">After you move the files, use the [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) cmdlet to remove yourself from the team.</span></span> 

<span data-ttu-id="d2c76-292">**При попытке переместить файлы из StaffHub в Teams появляется сообщение об ошибке, в котором говорится, что общая папка не существует.**</span><span class="sxs-lookup"><span data-stu-id="d2c76-292">**When you try to move files from StaffHub to Teams, you get an error that says the General folder doesn't exist.**</span></span>

<span data-ttu-id="d2c76-293">Выполните следующую команду, чтобы добавить общую папку в SharePoint, а затем повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="d2c76-293">Run the following command to add the General folder to SharePoint, and then try again:</span></span>

  ```PowerShell
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a><span data-ttu-id="d2c76-294">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="d2c76-294">Related topics</span></span>
- [<span data-ttu-id="d2c76-295">Как выполнить развертывание Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d2c76-295">How to roll out Microsoft Teams</span></span>](../../How-to-roll-out-teams.md)
- [<span data-ttu-id="d2c76-296">Прекращение поддержки Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="d2c76-296">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="d2c76-297">Управление приложением "Смены" для вашей организации в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d2c76-297">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="d2c76-298">Справочник по StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="d2c76-298">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
