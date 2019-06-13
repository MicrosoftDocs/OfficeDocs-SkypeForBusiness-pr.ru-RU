---
title: Перемещение команд StaffHub в приложение "Смены" в Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Узнайте, как перемещать команды Microsoft StaffHub и данные расписания в приложение "Смены" в Microsoft Teams.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e2e8b0ac4f1c4eb0cce2cae97481fc428f588ec5
ms.sourcegitcommit: 8f9bf1acdcdc2104fa8c343c030d64838e2c31eb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/07/2019
ms.locfileid: "34780811"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="b1c71-103">Перемещение команд Microsoft StaffHub в приложение "Смены" в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b1c71-103">Move your StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b1c71-104">С 1 октября 2019 г. прекращается поддержка приложения Microsoft StaffHub.</span><span class="sxs-lookup"><span data-stu-id="b1c71-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="b1c71-105">Мы встраиваем возможности StaffHub в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b1c71-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="b1c71-106">В настоящее время в состав Teams входит приложение "Смены" для управления расписанием, и со временем будут развернуты дополнительные возможности.</span><span class="sxs-lookup"><span data-stu-id="b1c71-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="b1c71-107">Приложение StaffHub перестанет работать для всех пользователей 1 октября 2019 г.</span><span class="sxs-lookup"><span data-stu-id="b1c71-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="b1c71-108">При любой попытке открыть StaffHub будет отображаться сообщение, ведущее на скачивание Teams.</span><span class="sxs-lookup"><span data-stu-id="b1c71-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="b1c71-109">Дополнительные сведения см. в статье [Прекращение поддержки Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="b1c71-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

<span data-ttu-id="b1c71-110">Приложение "Смены" в Teams предоставляет простой способ управления расписаниями, а также постоянный поток изменений и отмен смен, происходящих на повседневной основе.</span><span class="sxs-lookup"><span data-stu-id="b1c71-110">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="b1c71-111">Участники команд могут обращаться к своему расписанию и сведениям о сменах непосредственно в приложении и на других устройствах, чтобы устанавливать свои параметры, управлять расписаниями и запрашивать отгулы.</span><span class="sxs-lookup"><span data-stu-id="b1c71-111">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="b1c71-112">В этой статье описано, как переместить команды StaffHub организации и данные расписания в приложение "Смены" в Teams.</span><span class="sxs-lookup"><span data-stu-id="b1c71-112">This article walks you through how to move your organization’s StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="b1c71-113">Рассматриваются следующие вопросы:</span><span class="sxs-lookup"><span data-stu-id="b1c71-113">It covers:</span></span>

- [<span data-ttu-id="b1c71-114">Что нужно знать о переходе в Teams</span><span class="sxs-lookup"><span data-stu-id="b1c71-114">What you need to know about the move to Teams</span></span>](#what-you-need-to-know-about-the-move-to-teams)
- [<span data-ttu-id="b1c71-115">Подготовка</span><span class="sxs-lookup"><span data-stu-id="b1c71-115">Prepare Schema</span></span>](#prepare)
- [<span data-ttu-id="b1c71-116">Пилотная реализация</span><span class="sxs-lookup"><span data-stu-id="b1c71-116">Conduct a user pilot</span></span>](#conduct-a-pilot) 
- [<span data-ttu-id="b1c71-117">Переход от пилотной реализации к перемещению всех команд StaffHub</span><span class="sxs-lookup"><span data-stu-id="b1c71-117">Go beyond your pilot and move all StaffHub teams</span></span>](#go-beyond-your-pilot-and-move-all-staffhub-teams)
- [<span data-ttu-id="b1c71-118">Отслеживание использования приложения Teams</span><span class="sxs-lookup"><span data-stu-id="b1c71-118">Monitor Teams usage</span></span>](#monitor-teams-usage)
- [<span data-ttu-id="b1c71-119">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="b1c71-119">troubleshooting</span></span>](#troubleshooting)

<span data-ttu-id="b1c71-120">Независимо от того, являетесь ли вы небольшой компанией с одной или двумя командами StaffHub или крупным предприятием с сотнями команд StaffHub, здесь вы найдете инструкции для администраторов, необходимые для успешного перехода в Teams.</span><span class="sxs-lookup"><span data-stu-id="b1c71-120">Whether you’re a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you’ll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="b1c71-121">Для выполнения действий, описанных в этой статье, вы должны быть глобальным администратором.</span><span class="sxs-lookup"><span data-stu-id="b1c71-121">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="b1c71-122">Если вы еще не сделали этого, просмотрите [вопросы и ответы о прекращении поддержки StaffHub](microsoft-staffhub-to-be-retired.md), чтобы получить ответы на возникающие вопросы.</span><span class="sxs-lookup"><span data-stu-id="b1c71-122">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span>

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="b1c71-123">Что нужно знать о переходе в Teams</span><span class="sxs-lookup"><span data-stu-id="b1c71-123">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="b1c71-124">Когда переходить в Teams</span><span class="sxs-lookup"><span data-stu-id="b1c71-124">When to move to Teams</span></span>

<span data-ttu-id="b1c71-125">С 1 октября 2019 г. прекращается поддержка приложения StaffHub.</span><span class="sxs-lookup"><span data-stu-id="b1c71-125">Effective October 1, 2019, StaffHub will be retired.</span></span> <span data-ttu-id="b1c71-126">Мы рекомендуем приступить к использованию Teams уже сегодня и начать перемещение команд и пользователей организации из StaffHub.</span><span class="sxs-lookup"><span data-stu-id="b1c71-126">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="b1c71-127">Так как наиболее часто используется функция управления расписанием, в дальнейшем рекомендуется использовать приложение "Смены" в Teams.</span><span class="sxs-lookup"><span data-stu-id="b1c71-127">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="b1c71-128">Что перемещается в Teams</span><span class="sxs-lookup"><span data-stu-id="b1c71-128">What is moved to Teams</span></span>

<span data-ttu-id="b1c71-129">В Teams переносятся сведения о пользователях, информация о расписании, а так же данные чатов и файлов.</span><span class="sxs-lookup"><span data-stu-id="b1c71-129">User details, schedule information, and chat and file data are transitioned to Teams.</span></span> <span data-ttu-id="b1c71-130">Это включает участие в командах, расписание команд, чаты и файлы за последние 90 дней.</span><span class="sxs-lookup"><span data-stu-id="b1c71-130">This includes team membership, team schedules, and chats and files from the last 90 days.</span></span>

<span data-ttu-id="b1c71-131">Каждой команде StaffHub требуется соответствующая группа Office 365.</span><span class="sxs-lookup"><span data-stu-id="b1c71-131">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="b1c71-132">Если с командой StaffHub не связана группа Office 365, она автоматически создается для поддержки перехода.</span><span class="sxs-lookup"><span data-stu-id="b1c71-132">If a StaffHub team doesn't have an Office 365 Group associated with it, one is automatically created for you to support the transition.</span></span> <span data-ttu-id="b1c71-133">Учитывая разницу в именовании команд и групп в Teams и StaffHub, в Teams может отображаться другое имя команды.</span><span class="sxs-lookup"><span data-stu-id="b1c71-133">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span>

<span data-ttu-id="b1c71-134">При переносе команд из StaffHub в Teams пользователи больше не смогут получать доступ к своим расписаниям в StaffHub и будут перенаправляться в приложение "Смены" в Teams.</span><span class="sxs-lookup"><span data-stu-id="b1c71-134">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="b1c71-135">Мы рекомендуем сообщить об этом изменении в организации, чтобы свести к минимуму перерывы в работе и помочь пользователям с адаптацией и изучением Teams.</span><span class="sxs-lookup"><span data-stu-id="b1c71-135">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span> <span data-ttu-id="b1c71-136">Если вы используете Azure AD Premium, вы можете [запустить отчет](run-report-to-show-staffhub-usage.md), чтобы получить список пользователей StaffHub в организации, которых нужно оповестить об этом изменении.</span><span class="sxs-lookup"><span data-stu-id="b1c71-136">If you have Azure AD Premium, you can [run a report](run-report-to-show-staffhub-usage.md) to get a list of StaffHub users in your organization who need to know about this change.</span></span>  

<span data-ttu-id="b1c71-137">После перемещения команды StaffHub в Teams вы не сможете выполнить откат.</span><span class="sxs-lookup"><span data-stu-id="b1c71-137">There's no rollback option after you move a StaffHub team to Teams.</span></span>

### <a name="user-experience-when-you-move-a-team"></a><span data-ttu-id="b1c71-138">Взаимодействие с пользователем при перемещении команды</span><span class="sxs-lookup"><span data-stu-id="b1c71-138">User experience when you move a team</span></span>

<span data-ttu-id="b1c71-139">При переносе команды из StaffHub в приложение "Смены" в Teams время простоя пользователей минимально (меньше секунды или совсем отсутствует).</span><span class="sxs-lookup"><span data-stu-id="b1c71-139">There's minimal downtime (less than a second, if any at all) for users when their team is switched from StaffHub to Shifts in Teams.</span></span> <span data-ttu-id="b1c71-140">Пользователи могут продолжать использовать StaffHub, пока не завершится перемещение в Teams.</span><span class="sxs-lookup"><span data-stu-id="b1c71-140">Users can continue using StaffHub until the move to Teams is completed.</span></span> <span data-ttu-id="b1c71-141">По завершении перемещения участники команды увидят сообщение, уведомляющее о необходимости использования приложения "Смены" в Teams для доступа к расписанию команды.</span><span class="sxs-lookup"><span data-stu-id="b1c71-141">When the move is completed, team members will see a message to let them know that they need to start using Shifts in Teams to access their team schedule.</span></span> <span data-ttu-id="b1c71-142">Ниже представлен пример сообщения, отображаемого для пользователей в StaffHub после перемещения команды StaffHub в Teams.</span><span class="sxs-lookup"><span data-stu-id="b1c71-142">Here's an example of the message that users see in StaffHub after the StaffHub team is moved to Teams.</span></span>

<span data-ttu-id="b1c71-143">![Пример сообщения, отображаемого для пользователей.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Пример сообщения, отображаемого для пользователей в StaffHub после перемещения команды StaffHub в Teams")</span><span class="sxs-lookup"><span data-stu-id="b1c71-143">![Example of the message that users see.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Example of the message that users see in StaffHub after the StaffHub team is moved to Teams")</span></span>

## <a name="prepare"></a><span data-ttu-id="b1c71-144">Подготовка</span><span class="sxs-lookup"><span data-stu-id="b1c71-144">Prepare Schema</span></span>

<span data-ttu-id="b1c71-145">Ниже описано, как подготовиться к переходу в Teams.</span><span class="sxs-lookup"><span data-stu-id="b1c71-145">Here's how to prepare for the move to Teams.</span></span>

### <a name="check-that-prerequisites-are-met"></a><span data-ttu-id="b1c71-146">Проверка соответствия предварительным требованиям</span><span class="sxs-lookup"><span data-stu-id="b1c71-146">Ensure that deployment prerequisites are met</span></span>

<span data-ttu-id="b1c71-147">Перед перемещением команды StaffHub в Teams убедитесь, что:</span><span class="sxs-lookup"><span data-stu-id="b1c71-147">Before you move a StaffHub team to Teams, make sure that:</span></span>

- <span data-ttu-id="b1c71-148">Вошедший пользователь является глобальным администратором.</span><span class="sxs-lookup"><span data-stu-id="b1c71-148">The signed-in user is a global admin.</span></span>
- <span data-ttu-id="b1c71-149">Приложение Teams включено для всех пользователей в клиенте.</span><span class="sxs-lookup"><span data-stu-id="b1c71-149">Teams is enabled for all users in the tenant.</span></span>
- <span data-ttu-id="b1c71-150">Создание групп Office 365 включено в клиенте.</span><span class="sxs-lookup"><span data-stu-id="b1c71-150">Office 365 Groups creation is enabled in the tenant.</span></span>
- <span data-ttu-id="b1c71-151">Идентификатор команды StaffHub является действительным.</span><span class="sxs-lookup"><span data-stu-id="b1c71-151">The StaffHub teamId is valid.</span></span>
- <span data-ttu-id="b1c71-152">Команда StaffHub содержит участников.</span><span class="sxs-lookup"><span data-stu-id="b1c71-152">The StaffHub team contains members.</span></span> 
- <span data-ttu-id="b1c71-153">Все участники команды StaffHub связаны с учетной записью Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b1c71-153">All StaffHub team members are linked to an Azure AD account.</span></span> 

<span data-ttu-id="b1c71-154">Если эти предварительные требования не соблюдаются, запрос на перемещение завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="b1c71-154">If these prerequisites aren't met, the move request will fail.</span></span> 

### <a name="assign-teams-licenses"></a><span data-ttu-id="b1c71-155">Назначение лицензий Teams</span><span class="sxs-lookup"><span data-stu-id="b1c71-155">Assign Teams licenses</span></span>

<span data-ttu-id="b1c71-156">У каждого пользователя должна быть действующая лицензия Microsoft 365 или Office 365 из [поддерживаемого](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) плана, а также назначенная лицензия Teams.</span><span class="sxs-lookup"><span data-stu-id="b1c71-156">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="b1c71-157">Назначение пользователям лицензии Teams предоставляет им доступ к приложению Teams.</span><span class="sxs-lookup"><span data-stu-id="b1c71-157">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="b1c71-158">Управление лицензиями Teams осуществляется в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b1c71-158">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="b1c71-159">Дополнительные сведения см. в статье [Управление доступом пользователей к Teams](../../user-access.md).</span><span class="sxs-lookup"><span data-stu-id="b1c71-159">To learn more, see [Manage user access to Microsoft Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b1c71-160">Если в вашей организации используется Skype для бизнеса, но вы не готовы перенести всех пользователей в Teams, вы можете включить приложение Teams для сотрудников без компьютера, которые после этого смогут запускать Teams вместе со Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="b1c71-160">If your organization uses Skype for Business and you’re not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="b1c71-161">В этом режиме сосуществования под названием *Острова* каждое клиентское приложение работает как отдельное решение.</span><span class="sxs-lookup"><span data-stu-id="b1c71-161">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="b1c71-162">Дополнительные сведения см. в разделе [Сосуществование и взаимодействие Teams и Skype для бизнеса](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="b1c71-162">To learn more, see [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="install-the-staffhub-powershell-module"></a><span data-ttu-id="b1c71-163">Установка модуля StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1c71-163">Install the StaffHub PowerShell module</span></span>

<span data-ttu-id="b1c71-164">Если вы еще не сделали это, [установите модуль StaffHub PowerShell](install-the-staffhub-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="b1c71-164">If you haven't already, [install the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span> 

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a><span data-ttu-id="b1c71-165">Подготовка учетных записей для пользователей StaffHub, не имеющих удостоверений в Azure AD</span><span class="sxs-lookup"><span data-stu-id="b1c71-165">Provision accounts for StaffHub users who don't have an identity in Azure AD</span></span>

<span data-ttu-id="b1c71-166">У каждого руководителя и участника команды должно быть удостоверение в Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="b1c71-166">Each manager and team member must have an identity in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="b1c71-167">Если у пользователя еще нет удостоверения в Azure AD, подготовьте для него учетную запись.</span><span class="sxs-lookup"><span data-stu-id="b1c71-167">If a user doesn't already have an identity in Azure AD, provision an account for them.</span></span> <span data-ttu-id="b1c71-168">Ниже описано, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="b1c71-168">Here's how.</span></span> 

#### <a name="get-a-list-of-all-users-on-staffhub-teams-that-have-team-members-that-arent-provisioned-with-an-azure-ad-account"></a><span data-ttu-id="b1c71-169">Получение списка всех пользователей из команд StaffHub с участниками, для которых не подготовлены учетные записи Azure AD</span><span class="sxs-lookup"><span data-stu-id="b1c71-169">Get a list of all users on StaffHub teams that have team members that aren't provisioned with an Azure AD account</span></span>

<span data-ttu-id="b1c71-170">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b1c71-170">Run the following:</span></span>
```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
foreach($team in $StaffHubTeams[0]) {Get-StaffHubMember -TeamId $team.Id | where {$_.Email -eq $null -or $_.State -eq "Invited"}}
```

#### <a name="provision-the-account"></a><span data-ttu-id="b1c71-171">Подготовка учетной записи</span><span class="sxs-lookup"><span data-stu-id="b1c71-171">Provision the account</span></span>

<span data-ttu-id="b1c71-172">Выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="b1c71-172">Do one of the following:</span></span>

- <span data-ttu-id="b1c71-173">Преобразуйте и свяжите учетную запись с подготовленной учетной записью.</span><span class="sxs-lookup"><span data-stu-id="b1c71-173">Convert and link the account to a provisioned account.</span></span>

  <span data-ttu-id="b1c71-174">Владельцы и руководители команд StaffHub могут преобразовать фиктивную или неактивную учетную запись и связать ее с подготовленной учетной записью в StaffHub, изменив адрес электронной почты пользователя на действительное имя участника-пользователя на странице параметров команды StaffHub.</span><span class="sxs-lookup"><span data-stu-id="b1c71-174">StaffHub team owners and managers can convert a dummy or inactive account and link it to a provisioned account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="b1c71-175">Удалите неподготовленную учетную запись и повторите добавление учетной записи, используя имя участника-пользователя.</span><span class="sxs-lookup"><span data-stu-id="b1c71-175">Remove the non-provisioned account and then re-add the account by using the UPN.</span></span>
    1. <span data-ttu-id="b1c71-176">Запустите командлет [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps), чтобы удалить неподготовленную учетную запись из команды StaffHub.</span><span class="sxs-lookup"><span data-stu-id="b1c71-176">Run the [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) cmdlet to remove the non-provisioned account from the StaffHub team.</span></span>
    2. <span data-ttu-id="b1c71-177">Запустите командлет [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps), чтобы снова добавить учетную запись в команду StaffHub, используя имя участника-пользователя.</span><span class="sxs-lookup"><span data-stu-id="b1c71-177">Run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) cmdlet to add the account back to the StaffHub team by using the UPN.</span></span> 

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a><span data-ttu-id="b1c71-178">Назначение пользователям политики настройки приложений FirstlineWorker</span><span class="sxs-lookup"><span data-stu-id="b1c71-178">Assign the FirstlineWorker app setup policy to users</span></span>

<span data-ttu-id="b1c71-179">Teams содержит встроенную политику настройки приложений FirstlineWorker, с помощью которой можно настроить Teams для выделения наиболее важных приложений для сотрудников без компьютера в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b1c71-179">Teams includes a built-in FirstlineWorker app setup policy that you can use to customize Teams to highlight the apps that are most important for the Firstline Workers in your organization.</span></span> <span data-ttu-id="b1c71-180">Когда вы назначаете эту политику пользователям, приложения, указанные в политике, закрепляются на панели приложений в Teams для быстрого и удобного доступа.</span><span class="sxs-lookup"><span data-stu-id="b1c71-180">When you assign this policy to users, the apps in the policy are pinned to the app bar in Teams for quick and easy access.</span></span> <span data-ttu-id="b1c71-181">Другие приложения, добавленные в Teams, можно найти на панели приложений, щелкнув пункт **... Другие приложения** в классическом и веб-клиенте Teams или проведя пальцем в мобильном клиенте Teams.</span><span class="sxs-lookup"><span data-stu-id="b1c71-181">Other apps added to Teams can be found in the app bar by clicking **... More apps** in the Teams desktop and web clients and by swiping up in the Teams mobile client.</span></span> <span data-ttu-id="b1c71-182">По умолчанию политика настройки приложений FirstlineWorker включает приложения "Действия", "Смены", "Чат" и "Звонки".</span><span class="sxs-lookup"><span data-stu-id="b1c71-182">By default, the FirstlineWorker app setup policy includes the Activity, Shifts, Chat, and Calling apps.</span></span>

<span data-ttu-id="b1c71-183">Инструкции по назначению пользователям политики настройки приложений FirstlineWorker см. в разделе [Использование политики настройки приложений FirstlineWorker для закрепления приложения "Смены" в Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams).</span><span class="sxs-lookup"><span data-stu-id="b1c71-183">For steps on how to assign the FirstlineWorker app setup policy to users, see [Use the FirstlineWorker app setup policy to pin Shifts to Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams).</span></span> <span data-ttu-id="b1c71-184">После назначения политики может пройти до 24 часов перед ее вступлением в силу.</span><span class="sxs-lookup"><span data-stu-id="b1c71-184">After you assign a policy, it can take up to 24 hours to take effect.</span></span>

<span data-ttu-id="b1c71-185">Рекомендуется выполнять это действие минимум за неделю до перемещения команд и пользователей StaffHub в Teams.</span><span class="sxs-lookup"><span data-stu-id="b1c71-185">We recommend you complete this step at least a week before you move your StaffHub teams and users to Teams.</span></span> <span data-ttu-id="b1c71-186">После перемещения пользователей в Teams убедитесь, что они могут просматривать и использовать приложение "Смены".</span><span class="sxs-lookup"><span data-stu-id="b1c71-186">When users are on Teams, confirm that they can see and access the Shifts app.</span></span>

<span data-ttu-id="b1c71-187">Вы также можете создавать собственные политики настройки приложений и изменять параметры в глобальной политике настройки приложений.</span><span class="sxs-lookup"><span data-stu-id="b1c71-187">You can also create custom app setup policies and edit the settings in the global app setup policy.</span></span> <span data-ttu-id="b1c71-188">Дополнительные сведения см. в статье [Управление политиками настройки приложений в Teams](../../teams-app-setup-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b1c71-188">To learn more, check out [Manage app setup policies in Teams](../../teams-app-setup-policies.md).</span></span>

### <a name="onboard-users-to-teams"></a><span data-ttu-id="b1c71-189">Адаптация пользователей к Teams</span><span class="sxs-lookup"><span data-stu-id="b1c71-189">Onboard users to Teams</span></span>

<span data-ttu-id="b1c71-190">В рамках стратегии адаптации обеспечьте учебные материалы и рекомендации для пользователей с целью знакомства с Teams.</span><span class="sxs-lookup"><span data-stu-id="b1c71-190">As part of your onboarding strategy, provide training and guidance for users to help them get familiar with Teams.</span></span> <span data-ttu-id="b1c71-191">Предоставьте пользователям следующие ресурсы, чтобы они смогли узнать, где можно скачать клиент Teams и учебные материалы или воспользоваться поддержкой:</span><span class="sxs-lookup"><span data-stu-id="b1c71-191">Share the following resources with users so they know where to get Teams clients, training, and support:</span></span>

- [<span data-ttu-id="b1c71-192">Веб-клиент Teams</span><span class="sxs-lookup"><span data-stu-id="b1c71-192">Teams web client</span></span>](https://teams.microsoft.com)
- [<span data-ttu-id="b1c71-193">Ссылки для скачивания настольной и мобильной версий клиента</span><span class="sxs-lookup"><span data-stu-id="b1c71-193">Desktop and mobile client download links</span></span>](https://teams.microsoft.com/downloads)
- [<span data-ttu-id="b1c71-194">Обучающие видео для Teams</span><span class="sxs-lookup"><span data-stu-id="b1c71-194">Teams training videos</span></span>](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [<span data-ttu-id="b1c71-195">Справочная документация для Teams</span><span class="sxs-lookup"><span data-stu-id="b1c71-195">Teams Help documentation</span></span>](https://support.office.com/teams)

<span data-ttu-id="b1c71-196">Рекомендации по развертыванию Teams и управлению внедрением Teams см. в статьях [Способ развертывания Teams](../../How-to-roll-out-teams.md) и [Внедрение Teams](../../adopt-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="b1c71-196">For guidance on deploying Teams and driving Teams adoption, see [How to roll out Teams](../../How-to-roll-out-teams.md) and [Adopt Teams](../../adopt-microsoft-teams-landing-page.md).</span></span>

## <a name="conduct-a-pilot"></a><span data-ttu-id="b1c71-197">Пилотная реализация</span><span class="sxs-lookup"><span data-stu-id="b1c71-197">Conduct a user pilot</span></span>

<span data-ttu-id="b1c71-198">Рекомендуется сначала переместить две или три команды StaffHub для выбранной группы ранних пользователей.</span><span class="sxs-lookup"><span data-stu-id="b1c71-198">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="b1c71-199">Пилотная реализация позволяет уточнить план перехода и обеспечить готовность к перемещению всех команд StaffHub вашей организации в Teams.</span><span class="sxs-lookup"><span data-stu-id="b1c71-199">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="b1c71-200">С ее помощью также определяются лидеры, помогающие выполнять внедрение в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b1c71-200">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="b1c71-201">Если вы относитесь к малому бизнесу, не требующему поэтапной реализации, действия, описанные в этом разделе, могут удовлетворить все ваши потребности для перехода со StaffHub на Teams.</span><span class="sxs-lookup"><span data-stu-id="b1c71-201">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="b1c71-202">Определение пилотных команд</span><span class="sxs-lookup"><span data-stu-id="b1c71-202">Identify pilot teams</span></span>

<span data-ttu-id="b1c71-203">Определите две или три пилотные команды.</span><span class="sxs-lookup"><span data-stu-id="b1c71-203">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="b1c71-204">Все участники команд должны согласиться на использование приложения "Смены" в Teams для управления своими расписаниями и взаимодействия между собой.</span><span class="sxs-lookup"><span data-stu-id="b1c71-204">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="b1c71-205">Выбор лидеров команд</span><span class="sxs-lookup"><span data-stu-id="b1c71-205">Identify team champions</span></span>

<span data-ttu-id="b1c71-206">Определите лидеров пилотных команд, которые будут популяризировать приложение "Смены".</span><span class="sxs-lookup"><span data-stu-id="b1c71-206">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="b1c71-207">Лидерам команд нравится, когда они делятся своими знаниями и предоставляют поддержку и руководство для участников команд.</span><span class="sxs-lookup"><span data-stu-id="b1c71-207">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="b1c71-208">Лидеры команд могут быть владельцами или руководителями команд.</span><span class="sxs-lookup"><span data-stu-id="b1c71-208">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="b1c71-209">Лидеры команд должны обеспечить к назначенному времени готовность участников команд к [получению клиентов Teams](../../get-clients.md), входу в Teams, проверке расписаний в приложении "Смена" и к началу беседы с другими пользователями.</span><span class="sxs-lookup"><span data-stu-id="b1c71-209">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="b1c71-210">Пользователи, уже знакомые со StaffHub, смогут быстро начать работу в приложении "Смены".</span><span class="sxs-lookup"><span data-stu-id="b1c71-210">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="b1c71-211">Кроме того, вы можете направить их за дополнительной помощью в [справку по приложению "Смены"](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b).</span><span class="sxs-lookup"><span data-stu-id="b1c71-211">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team"></a><span data-ttu-id="b1c71-212">Перемещение команды StaffHub</span><span class="sxs-lookup"><span data-stu-id="b1c71-212">Move a StaffHub team</span></span>

<span data-ttu-id="b1c71-213">Чтобы перемещать команды StaffHub по одной, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="b1c71-213">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="b1c71-214">Этот способ рекомендуется для пилотных команд.</span><span class="sxs-lookup"><span data-stu-id="b1c71-214">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="b1c71-215">Когда вы будете готовы переместить все команды StaffHub вашей организации, обратитесь к разделу [Перемещение команд StaffHub](#move-your-staffhub-teams) за инструкциями по одновременному переносу нескольких команд.</span><span class="sxs-lookup"><span data-stu-id="b1c71-215">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="b1c71-216">Чтобы переместить команду StaffHub, выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="b1c71-216">Run the following to move a StaffHub team.</span></span>

```
Move-StaffHubTeam -TeamId <String>
```
<span data-ttu-id="b1c71-217">Пример:</span><span class="sxs-lookup"><span data-stu-id="b1c71-217">Example</span></span>

```
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

<span data-ttu-id="b1c71-218">Ниже приведен пример отклика, получаемого при отправке запроса на перемещение команды StaffHub в Teams.</span><span class="sxs-lookup"><span data-stu-id="b1c71-218">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

<span data-ttu-id="b1c71-219">Чтобы проверить состояние запроса на перемещение, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="b1c71-219">To check the status of a move request, run the following.</span></span>

```
Get-TeamMigrationJobStatus <String>
```
<span data-ttu-id="b1c71-220">Пример:</span><span class="sxs-lookup"><span data-stu-id="b1c71-220">Example</span></span>

```
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

<span data-ttu-id="b1c71-221">Ниже приведен пример отклика, получаемого в ходе перемещения.</span><span class="sxs-lookup"><span data-stu-id="b1c71-221">Here's an example of the response you get when a move is in progress.</span></span>

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a><span data-ttu-id="b1c71-222">Перемещение файлов из команды StaffHub в Teams</span><span class="sxs-lookup"><span data-stu-id="b1c71-222">Move files from a StaffHub team to Teams</span></span>

<span data-ttu-id="b1c71-223">Это действие применяется только в том случае, если команда StaffHub, перемещенная в Teams, содержит файлы, которые также нужно перенести в Teams.</span><span class="sxs-lookup"><span data-stu-id="b1c71-223">This step only applies if the StaffHub team that you moved to Teams has files that you want to also move to Teams.</span></span> <span data-ttu-id="b1c71-224">Вы можете перенести файлы непосредственно в SharePoint Online или с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1c71-224">You can move files directly in SharePoint Online or by using PowerShell.</span></span> 

#### <a name="in-sharepoint-online"></a><span data-ttu-id="b1c71-225">В SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b1c71-225">In SharePoint Online</span></span>

<span data-ttu-id="b1c71-226">См. статью [Как переместить файлы в SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).</span><span class="sxs-lookup"><span data-stu-id="b1c71-226">See [How to move files in SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="b1c71-227">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1c71-227">Using PowerShell</span></span>

<span data-ttu-id="b1c71-228">Скачайте и установите [командную консоль SharePoint Online](https://www.microsoft.com/download/details.aspx?id=35588), если вы еще не сделали это.</span><span class="sxs-lookup"><span data-stu-id="b1c71-228">Download and install the [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588), if you haven't already.</span></span> <span data-ttu-id="b1c71-229">Она содержит командлеты, требующиеся для перемещения файлов.</span><span class="sxs-lookup"><span data-stu-id="b1c71-229">It contains the cmdlets you need to move files.</span></span>  

<span data-ttu-id="b1c71-230">Подключитесь к сайту группы SharePoint Online с помощью командлета [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="b1c71-230">Use the [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) cmdlet to connect to the SharePoint Online team site.</span></span>

```
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

<span data-ttu-id="b1c71-231">Для каждого файла, который нужно переместить из StaffHub в Teams, используйте командлет [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile).</span><span class="sxs-lookup"><span data-stu-id="b1c71-231">For each file that you want to move from StaffHub to Teams, use the [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) cmdlet to move the file.</span></span>

```
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

<span data-ttu-id="b1c71-232">Чтобы переместить несколько файлов, выполните цикл по файлам и запустите вторую команду в цикле.</span><span class="sxs-lookup"><span data-stu-id="b1c71-232">To move multiple files, loop over the files and run the second command on the loop.</span></span> <span data-ttu-id="b1c71-233">Если сеанс остается активным, вам не требуется повторять первую команду.</span><span class="sxs-lookup"><span data-stu-id="b1c71-233">You don't need to repeat the first command if the session remains active.</span></span>

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a><span data-ttu-id="b1c71-234">Переход от пилотной реализации к перемещению всех команд StaffHub</span><span class="sxs-lookup"><span data-stu-id="b1c71-234">Go beyond your pilot and move all StaffHub teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="b1c71-235">Информирование</span><span class="sxs-lookup"><span data-stu-id="b1c71-235">Raise awareness</span></span>

<span data-ttu-id="b1c71-236">Когда вы будете готовы к переходу от пилотных команд к перемещению команд StaffHub вашей организации в Teams, важно сначала сообщить об изменении в своей организации.</span><span class="sxs-lookup"><span data-stu-id="b1c71-236">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="b1c71-237">Расскажите о приложении "Смены" и переходе в Teams, чтобы проинформировать, заинтересовать и поддержать внедрение.</span><span class="sxs-lookup"><span data-stu-id="b1c71-237">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams"></a><span data-ttu-id="b1c71-238">Перемещение команд StaffHub</span><span class="sxs-lookup"><span data-stu-id="b1c71-238">Move your StaffHub teams to Shifts in Microsoft Teams</span></span>

<span data-ttu-id="b1c71-239">Чтобы массово переместить команды StaffHub, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="b1c71-239">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="b1c71-240">Вы можете переместить все команды StaffHub своей организации или определенные команды StaffHub.</span><span class="sxs-lookup"><span data-stu-id="b1c71-240">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="b1c71-241">Если вы хотите перемещать команды StaffHub по одной, см. раздел [Перемещение команды StaffHub](#move-a-staffhub-team).</span><span class="sxs-lookup"><span data-stu-id="b1c71-241">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team).</span></span>

#### <a name="move-all-staffhub-teams"></a><span data-ttu-id="b1c71-242">Перемещение всех команд StaffHub</span><span class="sxs-lookup"><span data-stu-id="b1c71-242">Move all StaffHub teams</span></span>

<span data-ttu-id="b1c71-243">Чтобы получить список всех команд StaffHub в организации, выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="b1c71-243">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="b1c71-244">Затем выполните следующее, чтобы переместить все команды.</span><span class="sxs-lookup"><span data-stu-id="b1c71-244">Then, run the following to move all teams.</span></span>

```
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

<span data-ttu-id="b1c71-245">Ниже приведен пример отклика.</span><span class="sxs-lookup"><span data-stu-id="b1c71-245">Here's an example of the response.</span></span>

<span data-ttu-id="b1c71-246">Для всех команд, уже перемещенных или существующих в Teams, параметр jobId будет иметь значение null, так как не требуется отправлять задание на перемещение команды.</span><span class="sxs-lookup"><span data-stu-id="b1c71-246">For any team that was already moved to Teams or already exists in Teams, the jobId will be "null" as a job doesn't need to be submitted to move that team.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a><span data-ttu-id="b1c71-247">Перемещение определенных команд StaffHub</span><span class="sxs-lookup"><span data-stu-id="b1c71-247">Move specific StaffHub teams</span></span>

<span data-ttu-id="b1c71-248">Чтобы получить список всех идентификаторов команд StaffHub в организации, выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="b1c71-248">Run the following to get a list of all StaffHub team Ids in your organization.</span></span>

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="b1c71-249">В результатах, возвращенных командлетом `Get-StaffHubteamsForTenant`, запущенным ранее, выберите идентификаторы команд, которые нужно переместить, и добавьте их в файл данных с разделителями-запятыми (CSV).</span><span class="sxs-lookup"><span data-stu-id="b1c71-249">In the results returned by the `Get-StaffHubteamsForTenant` cmdlet you ran earlier, select the Team Ids you want to move, and then add them to a comma-separated values (CSV) file.</span></span>

<span data-ttu-id="b1c71-250">Ниже приведен пример формата CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="b1c71-250">Here's an example of how the CSV file should be formatted.</span></span>

|<span data-ttu-id="b1c71-251">Id</span><span class="sxs-lookup"><span data-stu-id="b1c71-251">ID</span></span>  |
|---------|
|<span data-ttu-id="b1c71-252">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="b1c71-252">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="b1c71-253">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="b1c71-253">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="b1c71-254">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="b1c71-254">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="b1c71-255">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="b1c71-255">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="b1c71-256">После создания CSV-файла выполните следующее, чтобы переместить команды, указанные в CSV-файле.</span><span class="sxs-lookup"><span data-stu-id="b1c71-256">After you create the CSV file, run the following to move the teams you specified in the CSV file.</span></span>

```
$StaffHubTeams = Import-Csv .\teams.csv
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a><span data-ttu-id="b1c71-257">Подтверждение перемещения команд StaffHub в Teams</span><span class="sxs-lookup"><span data-stu-id="b1c71-257">Confirm that your StaffHub teams have moved to Teams</span></span>

<span data-ttu-id="b1c71-258">Чтобы получить список всех команд организации в приложении "Смена", выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="b1c71-258">Run the following to get a list of all teams in Shifts in your organization.</span></span> 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a><span data-ttu-id="b1c71-259">Перемещение файлов из команд StaffHub в Teams</span><span class="sxs-lookup"><span data-stu-id="b1c71-259">Move files from your StaffHub teams to Teams</span></span>

<span data-ttu-id="b1c71-260">Если перемещенные команды StaffHub содержат файлы, которые также нужно переместить в Teams, см. раздел [Перемещение файлов из команды StaffHub в Teams](#move-files-from-a-staffhub-team-to-teams).</span><span class="sxs-lookup"><span data-stu-id="b1c71-260">If the StaffHub teams that you moved contain files that you also want to move to Teams, see [Move files from a StaffHub team to Teams](#move-files-from-a-staffhub-team-to-teams).</span></span>

## <a name="monitor-teams-usage"></a><span data-ttu-id="b1c71-261">Отслеживание использования приложения Teams</span><span class="sxs-lookup"><span data-stu-id="b1c71-261">Monitor Teams usage</span></span>

<span data-ttu-id="b1c71-262">Отчеты об использовании помогут вам лучше понять характер использования и получить ценную информацию с целью определения приоритетных областей для обучения и взаимодействия в организации.</span><span class="sxs-lookup"><span data-stu-id="b1c71-262">Usage reports can help you better understand usage patterns, and along with user feedback, give you insights to inform your wider rollout and where to prioritize training and communication efforts.</span></span> <span data-ttu-id="b1c71-263">"Смены" — это приложение в Teams, поэтому вы можете просматривать сведения об использовании с помощью отчетов Teams.</span><span class="sxs-lookup"><span data-stu-id="b1c71-263">Because Shifts is an app in Teams, you can view usage through Teams reports.</span></span> <span data-ttu-id="b1c71-264">Дополнительные сведения см. в статьях о [создании отчетов Teams в Центре администрирования Microsoft Teams](../../teams-analytics-and-reports/teams-reporting-reference.md) и об [отчетах активности Teams в Центре администрирования Microsoft 365](../../teams-activity-reports.md).</span><span class="sxs-lookup"><span data-stu-id="b1c71-264">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="b1c71-265">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="b1c71-265">Troubleshooting</span></span> 

<span data-ttu-id="b1c71-266">**При попытке переместить файлы из StaffHub в Teams возникает сообщение об ошибке "В разрешении отказано".**</span><span class="sxs-lookup"><span data-stu-id="b1c71-266">**When you try to move files from StaffHub to Teams, you get a "Permission denied" error message.**</span></span>

<span data-ttu-id="b1c71-267">Это может произойти, если вы пытаетесь переместить файлы в закрытую группу Office 365, участником которой вы не являетесь.</span><span class="sxs-lookup"><span data-stu-id="b1c71-267">This may occur if you're trying to move files in a private Office 365 group that you're not a member of.</span></span> <span data-ttu-id="b1c71-268">В этом случае используйте командлет [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember), чтобы добавить себя в команду StaffHub, а затем переместите файлы.</span><span class="sxs-lookup"><span data-stu-id="b1c71-268">If this is the case, use the [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) cmdlet to add yourself to the StaffHub team, and then move the files.</span></span> <span data-ttu-id="b1c71-269">После перемещения файлов используйте командлет [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember), чтобы удалить себя из команды.</span><span class="sxs-lookup"><span data-stu-id="b1c71-269">After you move the files, use the [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) cmdlet to remove yourself from the team.</span></span> 

<span data-ttu-id="b1c71-270">**При попытке переместить файлы из StaffHub в Teams возникает ошибка, сообщающая об отсутствии папки General.**</span><span class="sxs-lookup"><span data-stu-id="b1c71-270">**When you try to move files from StaffHub to Teams, you get an error that says the General folder doesn't exist.**</span></span>

<span data-ttu-id="b1c71-271">Выполните следующую команду, чтобы добавить папку General в SharePoint, и повторите попытку:</span><span class="sxs-lookup"><span data-stu-id="b1c71-271">Run the following command to add the General folder to SharePoint, and then try again:</span></span>

  ```
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a><span data-ttu-id="b1c71-272">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="b1c71-272">Related topics</span></span>
- [<span data-ttu-id="b1c71-273">Как выполнить развертывание Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b1c71-273">How to roll out Microsoft Teams</span></span>](../../How-to-roll-out-teams.md)
- [<span data-ttu-id="b1c71-274">Прекращение поддержки Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="b1c71-274">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="b1c71-275">Управление приложением "Смены" для вашей организации в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b1c71-275">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="b1c71-276">Справочник по StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1c71-276">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
