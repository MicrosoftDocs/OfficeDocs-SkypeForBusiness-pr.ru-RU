---
title: Назначение владельцев и участников команд в Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/27/2018
ms.topic: article
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
ms.openlocfilehash: 4887cb129242473da46a611c4f873e79384e5e32
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/07/2019
ms.locfileid: "30460342"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a><span data-ttu-id="80311-103">Назначение владельцев и участников команд в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="80311-103">Assign team owners and members in Microsoft Teams</span></span>
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="80311-104">Внутри групп Майкрософт существует две роли пользователя: **владельца** и **член**.</span><span class="sxs-lookup"><span data-stu-id="80311-104">Within Microsoft Teams there are two user roles: **Owner** and **Member**.</span></span> <span data-ttu-id="80311-105">По умолчанию пользователь, который создает новые группы предоставляется состояния владельца.</span><span class="sxs-lookup"><span data-stu-id="80311-105">By default, a user who creates a new team is granted the Owner status.</span></span> <span data-ttu-id="80311-106">При создании команды из существующей группы Office 365 разрешения наследуются.</span><span class="sxs-lookup"><span data-stu-id="80311-106">If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="80311-107">В следующей таблице показана разница в разрешения от владельца, а также.</span><span class="sxs-lookup"><span data-stu-id="80311-107">The table below shows the difference in permissions between an owner and a member.</span></span>


|                                   | <span data-ttu-id="80311-108">Владелец команды</span><span class="sxs-lookup"><span data-stu-id="80311-108">Team Owner</span></span> | <span data-ttu-id="80311-109">Участник команды</span><span class="sxs-lookup"><span data-stu-id="80311-109">Team Member</span></span> |
|-----------------------------------|------------|-------------|
|          <span data-ttu-id="80311-110">**Создание команды**</span><span class="sxs-lookup"><span data-stu-id="80311-110">**Create team**</span></span>          |    <span data-ttu-id="80311-111">Да<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="80311-111">Yes<sup>1</sup></span></span>     |     <span data-ttu-id="80311-112">Нет</span><span class="sxs-lookup"><span data-stu-id="80311-112">No</span></span>      |
|          <span data-ttu-id="80311-113">**Выход из команды**</span><span class="sxs-lookup"><span data-stu-id="80311-113">**Leave team**</span></span>           |    <span data-ttu-id="80311-114">Да</span><span class="sxs-lookup"><span data-stu-id="80311-114">Yes</span></span>     |     <span data-ttu-id="80311-115">Да</span><span class="sxs-lookup"><span data-stu-id="80311-115">Yes</span></span>     |
|  <span data-ttu-id="80311-116">**Изменение имени и описания команды**</span><span class="sxs-lookup"><span data-stu-id="80311-116">**Edit team name/description**</span></span>   |    <span data-ttu-id="80311-117">Да</span><span class="sxs-lookup"><span data-stu-id="80311-117">Yes</span></span>     |     <span data-ttu-id="80311-118">Нет</span><span class="sxs-lookup"><span data-stu-id="80311-118">No</span></span>      |
|          <span data-ttu-id="80311-119">**Удаление команды**</span><span class="sxs-lookup"><span data-stu-id="80311-119">**Delete team**</span></span>          |    <span data-ttu-id="80311-120">Да</span><span class="sxs-lookup"><span data-stu-id="80311-120">Yes</span></span>     |     <span data-ttu-id="80311-121">Нет</span><span class="sxs-lookup"><span data-stu-id="80311-121">No</span></span>      |
|          <span data-ttu-id="80311-122">**Добавление канала**</span><span class="sxs-lookup"><span data-stu-id="80311-122">**Add channel**</span></span>          |    <span data-ttu-id="80311-123">Да</span><span class="sxs-lookup"><span data-stu-id="80311-123">Yes</span></span>     |    <span data-ttu-id="80311-124">Да,<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="80311-124">Yes<sup>2</sup></span></span>|
| <span data-ttu-id="80311-125">**Изменение имени и описания канала**</span><span class="sxs-lookup"><span data-stu-id="80311-125">**Edit channel name/description**</span></span> |    <span data-ttu-id="80311-126">Да</span><span class="sxs-lookup"><span data-stu-id="80311-126">Yes</span></span>     |    <span data-ttu-id="80311-127">Да,<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="80311-127">Yes<sup>2</sup></span></span>|
|        <span data-ttu-id="80311-128">**Удаление канала**</span><span class="sxs-lookup"><span data-stu-id="80311-128">**Delete channel**</span></span>         |    <span data-ttu-id="80311-129">Да</span><span class="sxs-lookup"><span data-stu-id="80311-129">Yes</span></span>     |    <span data-ttu-id="80311-130">Да,<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="80311-130">Yes<sup>2</sup></span></span>|
|          <span data-ttu-id="80311-131">**Добавление участников**</span><span class="sxs-lookup"><span data-stu-id="80311-131">**Add members**</span></span>          |  <span data-ttu-id="80311-132">Да,<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="80311-132">Yes<sup>3</sup></span></span>   |     <span data-ttu-id="80311-133">Нет</span><span class="sxs-lookup"><span data-stu-id="80311-133">No</span></span>      |
|           <span data-ttu-id="80311-134">**Добавление вкладок**</span><span class="sxs-lookup"><span data-stu-id="80311-134">**Add tabs**</span></span>            |    <span data-ttu-id="80311-135">Да</span><span class="sxs-lookup"><span data-stu-id="80311-135">Yes</span></span>     |    <span data-ttu-id="80311-136">Да,<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="80311-136">Yes<sup>2</sup></span></span>|
|        <span data-ttu-id="80311-137">**Добавление соединителей**</span><span class="sxs-lookup"><span data-stu-id="80311-137">**Add connectors**</span></span>         |    <span data-ttu-id="80311-138">Да</span><span class="sxs-lookup"><span data-stu-id="80311-138">Yes</span></span>     |    <span data-ttu-id="80311-139">Да,<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="80311-139">Yes<sup>2</sup></span></span>|
|           <span data-ttu-id="80311-140">**Добавление ботов**</span><span class="sxs-lookup"><span data-stu-id="80311-140">**Add bots**</span></span>            |    <span data-ttu-id="80311-141">Да</span><span class="sxs-lookup"><span data-stu-id="80311-141">Yes</span></span>     |    <span data-ttu-id="80311-142">Да,<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="80311-142">Yes<sup>2</sup></span></span>|

<span data-ttu-id="80311-143"><sup>1</sup> владельцев группы можно создать группы, если они были это действие запрещено.</span><span class="sxs-lookup"><span data-stu-id="80311-143"><sup>1</sup> Team owners can create teams unless they've been restricted from doing so.</span></span> <span data-ttu-id="80311-144">Ниже приведены «Разрешения для создания групп».</span><span class="sxs-lookup"><span data-stu-id="80311-144">See "Permissions to create teams" below.</span></span>
>
<span data-ttu-id="80311-145"><sup>2</sup> этих элементов может быть отключена, пользователь с уровнем рабочая группа, в противном случае члены не имеет доступа к ним.</span><span class="sxs-lookup"><span data-stu-id="80311-145"><sup>2</sup> These items can be turned off by an owner at a team level, in which case members would not have access to them.</span></span>

<span data-ttu-id="80311-146"><sup>3</sup> после добавления члена группы, владелец может также повысить члена состояния владельца.</span><span class="sxs-lookup"><span data-stu-id="80311-146"><sup>3</sup> After adding a member to a team, an owner can also promote a member to owner status.</span></span> <span data-ttu-id="80311-147">Можно также для владельца понизить важность следующих узлов собственные в состояние участником.</span><span class="sxs-lookup"><span data-stu-id="80311-147">It is also possible for an owner to demote their own status to a member.</span></span>



> [!NOTE]
> <span data-ttu-id="80311-148">Владельцы могут назначать других участников владельцами с помощью параметра "Показать команды".</span><span class="sxs-lookup"><span data-stu-id="80311-148">Owners can make other members owners in the View teams option.</span></span> <span data-ttu-id="80311-149">Команда может иметь до 100 владельцев.</span><span class="sxs-lookup"><span data-stu-id="80311-149">A team can have up to 100 owners.</span></span> <span data-ttu-id="80311-150">Рекомендуется иметь хотя бы несколько владельцев для более простого управления командой. Кроме того, в этом случае группы не будут теряться, если их единственный владелец покинет организацию.</span><span class="sxs-lookup"><span data-stu-id="80311-150">It's recommended to have at least a few owners to help manage the team; this will also prevent orphaned groups if the sole owner leaves your organization.</span></span> <span data-ttu-id="80311-151">Дополнительные сведения о потерянных группах см. в разделе [Назначение нового владельца потерянной группе](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span><span class="sxs-lookup"><span data-stu-id="80311-151">For more information about orphaned groups, see [Assign a new owner to an orphaned group](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span></span>


<a name="permissions-to-create-teams"></a><span data-ttu-id="80311-152">Разрешения на создание команд</span><span class="sxs-lookup"><span data-stu-id="80311-152">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="80311-153">По умолчанию все пользователи с почтовым ящиком в Exchange Online обладают правом на создание групп Office 365, а значит, и команды в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="80311-153">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams.</span></span> <span data-ttu-id="80311-154">Вы можете более жестко регулировать или запретить создание команд и групп Office 365, делегировав права на создание и управление некоторому кругу пользователей.</span><span class="sxs-lookup"><span data-stu-id="80311-154">You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span> <span data-ttu-id="80311-155">Сведения содержатся в разделе [Управление, кто может создавать группы Office 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span><span class="sxs-lookup"><span data-stu-id="80311-155">For instructions, see [Manage who can create Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>


||||
|---------|---------|---------|
| ![Значок для точки принятия решений.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="80311-157">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="80311-157">Decision Point</span></span>         |<span data-ttu-id="80311-158">Смогут ли все пользователи Microsoft Teams создавать команды (рекомендуется)?</span><span class="sxs-lookup"><span data-stu-id="80311-158">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![Значок дальнейших действий.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="80311-160">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="80311-160">Next Steps</span></span>         |<span data-ttu-id="80311-161">Измените разрешения по умолчанию для пользователей, которые могут создавать группы Office 365, если хотите ограничить круг лиц, способных создавать команды.</span><span class="sxs-lookup"><span data-stu-id="80311-161">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |
