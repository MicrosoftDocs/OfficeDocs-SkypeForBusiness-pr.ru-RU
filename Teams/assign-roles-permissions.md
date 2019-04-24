---
title: Назначение владельцев и участников команд в Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/27/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: Сведения о назначении разрешений и ролей для владельцев и участников команд в Microsoft Teams, включая права на создание команд.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0c7343f294f18d5aaacf01059459524cdd2700a2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32195027"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a><span data-ttu-id="78244-103">Назначение владельцев и участников команд в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="78244-103">Assign team owners and members in Microsoft Teams</span></span>
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="78244-104">Внутри групп Майкрософт существует две роли пользователя: **владельца** и **член**.</span><span class="sxs-lookup"><span data-stu-id="78244-104">Within Microsoft Teams there are two user roles: **Owner** and **Member**.</span></span> <span data-ttu-id="78244-105">По умолчанию пользователь, который создает новые группы предоставляется состояния владельца.</span><span class="sxs-lookup"><span data-stu-id="78244-105">By default, a user who creates a new team is granted the Owner status.</span></span> <span data-ttu-id="78244-106">При создании команды из существующей группы Office 365 разрешения наследуются.</span><span class="sxs-lookup"><span data-stu-id="78244-106">If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="78244-107">В следующей таблице показана разница в разрешения от владельца, а также.</span><span class="sxs-lookup"><span data-stu-id="78244-107">The table below shows the difference in permissions between an owner and a member.</span></span>


|                                   | <span data-ttu-id="78244-108">Владелец команды</span><span class="sxs-lookup"><span data-stu-id="78244-108">Team Owner</span></span> | <span data-ttu-id="78244-109">Участник команды</span><span class="sxs-lookup"><span data-stu-id="78244-109">Team Member</span></span> |
|-----------------------------------|------------|-------------|
|          <span data-ttu-id="78244-110">**Создание команды**</span><span class="sxs-lookup"><span data-stu-id="78244-110">**Create team**</span></span>          |    <span data-ttu-id="78244-111">Да<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="78244-111">Yes<sup>1</sup></span></span>     |     <span data-ttu-id="78244-112">Нет</span><span class="sxs-lookup"><span data-stu-id="78244-112">No</span></span>      |
|          <span data-ttu-id="78244-113">**Выход из команды**</span><span class="sxs-lookup"><span data-stu-id="78244-113">**Leave team**</span></span>           |    <span data-ttu-id="78244-114">Да</span><span class="sxs-lookup"><span data-stu-id="78244-114">Yes</span></span>     |     <span data-ttu-id="78244-115">Да</span><span class="sxs-lookup"><span data-stu-id="78244-115">Yes</span></span>     |
|  <span data-ttu-id="78244-116">**Изменение имени и описания команды**</span><span class="sxs-lookup"><span data-stu-id="78244-116">**Edit team name/description**</span></span>   |    <span data-ttu-id="78244-117">Да</span><span class="sxs-lookup"><span data-stu-id="78244-117">Yes</span></span>     |     <span data-ttu-id="78244-118">Нет</span><span class="sxs-lookup"><span data-stu-id="78244-118">No</span></span>      |
|          <span data-ttu-id="78244-119">**Удаление команды**</span><span class="sxs-lookup"><span data-stu-id="78244-119">**Delete team**</span></span>          |    <span data-ttu-id="78244-120">Да</span><span class="sxs-lookup"><span data-stu-id="78244-120">Yes</span></span>     |     <span data-ttu-id="78244-121">Нет</span><span class="sxs-lookup"><span data-stu-id="78244-121">No</span></span>      |
|          <span data-ttu-id="78244-122">**Добавление канала**</span><span class="sxs-lookup"><span data-stu-id="78244-122">**Add channel**</span></span>          |    <span data-ttu-id="78244-123">Да</span><span class="sxs-lookup"><span data-stu-id="78244-123">Yes</span></span>     |    <span data-ttu-id="78244-124">Да,<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="78244-124">Yes<sup>2</sup></span></span>|
| <span data-ttu-id="78244-125">**Изменение имени и описания канала**</span><span class="sxs-lookup"><span data-stu-id="78244-125">**Edit channel name/description**</span></span> |    <span data-ttu-id="78244-126">Да</span><span class="sxs-lookup"><span data-stu-id="78244-126">Yes</span></span>     |    <span data-ttu-id="78244-127">Да,<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="78244-127">Yes<sup>2</sup></span></span>|
|        <span data-ttu-id="78244-128">**Удаление канала**</span><span class="sxs-lookup"><span data-stu-id="78244-128">**Delete channel**</span></span>         |    <span data-ttu-id="78244-129">Да</span><span class="sxs-lookup"><span data-stu-id="78244-129">Yes</span></span>     |    <span data-ttu-id="78244-130">Да,<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="78244-130">Yes<sup>2</sup></span></span>|
|          <span data-ttu-id="78244-131">**Добавление участников**</span><span class="sxs-lookup"><span data-stu-id="78244-131">**Add members**</span></span>          |  <span data-ttu-id="78244-132">Да,<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="78244-132">Yes<sup>3</sup></span></span>   |     <span data-ttu-id="78244-133">Нет<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="78244-133">No<sup>4</sup></span></span>    |
|          <span data-ttu-id="78244-134">**Запрос на добавление элементов**</span><span class="sxs-lookup"><span data-stu-id="78244-134">**Request to add members**</span></span>          |  <span data-ttu-id="78244-135">Н/Д</span><span class="sxs-lookup"><span data-stu-id="78244-135">N/A</span></span>   |     <span data-ttu-id="78244-136">Да,<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="78244-136">Yes<sup>5</sup></span></span>     |
|           <span data-ttu-id="78244-137">**Добавление вкладок**</span><span class="sxs-lookup"><span data-stu-id="78244-137">**Add tabs**</span></span>            |    <span data-ttu-id="78244-138">Да</span><span class="sxs-lookup"><span data-stu-id="78244-138">Yes</span></span>     |    <span data-ttu-id="78244-139">Да,<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="78244-139">Yes<sup>2</sup></span></span>|
|        <span data-ttu-id="78244-140">**Добавление соединителей**</span><span class="sxs-lookup"><span data-stu-id="78244-140">**Add connectors**</span></span>         |    <span data-ttu-id="78244-141">Да</span><span class="sxs-lookup"><span data-stu-id="78244-141">Yes</span></span>     |    <span data-ttu-id="78244-142">Да,<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="78244-142">Yes<sup>2</sup></span></span>|
|           <span data-ttu-id="78244-143">**Добавление ботов**</span><span class="sxs-lookup"><span data-stu-id="78244-143">**Add bots**</span></span>            |    <span data-ttu-id="78244-144">Да</span><span class="sxs-lookup"><span data-stu-id="78244-144">Yes</span></span>     |    <span data-ttu-id="78244-145">Да,<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="78244-145">Yes<sup>2</sup></span></span>|

<span data-ttu-id="78244-146"><sup>1</sup> владельцев группы можно создать группы, если они были это действие запрещено.</span><span class="sxs-lookup"><span data-stu-id="78244-146"><sup>1</sup> Team owners can create teams unless they've been restricted from doing so.</span></span> <span data-ttu-id="78244-147">Ниже приведены «Разрешения для создания групп».</span><span class="sxs-lookup"><span data-stu-id="78244-147">See "Permissions to create teams" below.</span></span>
>
<span data-ttu-id="78244-148"><sup>2</sup> этих элементов может быть отключена, пользователь с уровнем рабочая группа, в противном случае члены не имеет доступа к ним.</span><span class="sxs-lookup"><span data-stu-id="78244-148"><sup>2</sup> These items can be turned off by an owner at a team level, in which case members would not have access to them.</span></span>

<span data-ttu-id="78244-149"><sup>3</sup> после добавления члена группы, владелец может также повысить члена состояния владельца.</span><span class="sxs-lookup"><span data-stu-id="78244-149"><sup>3</sup> After adding a member to a team, an owner can also promote a member to owner status.</span></span> <span data-ttu-id="78244-150">Можно также для владельца понизить важность следующих узлов собственные в состояние участником.</span><span class="sxs-lookup"><span data-stu-id="78244-150">It is also possible for an owner to demote their own status to a member.</span></span>

<span data-ttu-id="78244-151"><sup>4</sup> участников группы можно добавить других участников общедоступной группы.</span><span class="sxs-lookup"><span data-stu-id="78244-151"><sup>4</sup> Team members can add other members to a public team.</span></span>

<span data-ttu-id="78244-152"><sup>5</sup> в то время как участник группы нельзя непосредственно добавить элементы в частной группы, они могут запрашивать кто-то добавлена, за которые они уже должна быть членом группы.</span><span class="sxs-lookup"><span data-stu-id="78244-152"><sup>5</sup> While a team member can't directly add members to a private team, they can request someone to be added to a team they're already a member of.</span></span> <span data-ttu-id="78244-153">Когда участник запрашивает кто-то будет добавлена в группу, группы владельцев получить оповещение, что у них ожидающий запрос, их можно принять или отклонить.</span><span class="sxs-lookup"><span data-stu-id="78244-153">When a member requests someone to be added to a team, team owners receive an alert that they have a pending request that they can accept or deny.</span></span>



> [!NOTE]
> <span data-ttu-id="78244-154">Владельцы могут назначать других участников владельцами с помощью параметра "Показать команды".</span><span class="sxs-lookup"><span data-stu-id="78244-154">Owners can make other members owners in the View teams option.</span></span> <span data-ttu-id="78244-155">Команда может иметь до 100 владельцев.</span><span class="sxs-lookup"><span data-stu-id="78244-155">A team can have up to 100 owners.</span></span> <span data-ttu-id="78244-156">Рекомендуется иметь хотя бы несколько владельцев для более простого управления командой. Кроме того, в этом случае группы не будут теряться, если их единственный владелец покинет организацию.</span><span class="sxs-lookup"><span data-stu-id="78244-156">It's recommended to have at least a few owners to help manage the team; this will also prevent orphaned groups if the sole owner leaves your organization.</span></span> <span data-ttu-id="78244-157">Дополнительные сведения о потерянных группах см. в разделе [Назначение нового владельца потерянной группе](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span><span class="sxs-lookup"><span data-stu-id="78244-157">For more information about orphaned groups, see [Assign a new owner to an orphaned group](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span></span>


<a name="permissions-to-create-teams"></a><span data-ttu-id="78244-158">Разрешения на создание команд</span><span class="sxs-lookup"><span data-stu-id="78244-158">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="78244-159">По умолчанию все пользователи с почтовым ящиком в Exchange Online обладают правом на создание групп Office 365, а значит, и команды в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="78244-159">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams.</span></span> <span data-ttu-id="78244-160">Вы можете более жестко регулировать или запретить создание команд и групп Office 365, делегировав права на создание и управление некоторому кругу пользователей.</span><span class="sxs-lookup"><span data-stu-id="78244-160">You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span> <span data-ttu-id="78244-161">Сведения содержатся в разделе [Управление, кто может создавать группы Office 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span><span class="sxs-lookup"><span data-stu-id="78244-161">For instructions, see [Manage who can create Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>


||||
|---------|---------|---------|
| ![Значок для точки принятия решений.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="78244-163">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="78244-163">Decision Point</span></span>         |<span data-ttu-id="78244-164">Смогут ли все пользователи Microsoft Teams создавать команды (рекомендуется)?</span><span class="sxs-lookup"><span data-stu-id="78244-164">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![Значок дальнейших действий.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="78244-166">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="78244-166">Next Steps</span></span>         |<span data-ttu-id="78244-167">Измените разрешения по умолчанию для пользователей, которые могут создавать группы Office 365, если хотите ограничить круг лиц, способных создавать команды.</span><span class="sxs-lookup"><span data-stu-id="78244-167">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |
