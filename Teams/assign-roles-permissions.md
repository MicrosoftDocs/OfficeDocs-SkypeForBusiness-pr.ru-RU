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
ms.openlocfilehash: 423a12e8fce0c9d7508e97c1f57e17a0ba8a0ff0
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/28/2019
ms.locfileid: "34493804"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a><span data-ttu-id="0ee56-103">Назначение владельцев и участников команд в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0ee56-103">Assign team owners and members in Microsoft Teams</span></span>
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="0ee56-104">В Microsoft Teams существует две роли: **владелец** и **участник**.</span><span class="sxs-lookup"><span data-stu-id="0ee56-104">Within Microsoft Teams there are two user roles: **Owner** and **Member**.</span></span> <span data-ttu-id="0ee56-105">По умолчанию пользователю, который создает новую команду, предоставлено состояние "владелец".</span><span class="sxs-lookup"><span data-stu-id="0ee56-105">By default, a user who creates a new team is granted the Owner status.</span></span> <span data-ttu-id="0ee56-106">При создании команды из существующей группы Office 365 разрешения наследуются.</span><span class="sxs-lookup"><span data-stu-id="0ee56-106">If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="0ee56-107">В приведенной ниже таблице показано различие в разрешениях между владельцем и членом.</span><span class="sxs-lookup"><span data-stu-id="0ee56-107">The table below shows the difference in permissions between an owner and a member.</span></span>


|                                   | <span data-ttu-id="0ee56-108">Владелец команды</span><span class="sxs-lookup"><span data-stu-id="0ee56-108">Team Owner</span></span> | <span data-ttu-id="0ee56-109">Участник команды</span><span class="sxs-lookup"><span data-stu-id="0ee56-109">Team Member</span></span> |
|-----------------------------------|------------|-------------|
|          <span data-ttu-id="0ee56-110">**Создание команды**</span><span class="sxs-lookup"><span data-stu-id="0ee56-110">**Create team**</span></span>          |    <span data-ttu-id="0ee56-111">Да,<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0ee56-111">Yes<sup>1</sup></span></span>     |     <span data-ttu-id="0ee56-112">Нет</span><span class="sxs-lookup"><span data-stu-id="0ee56-112">No</span></span>      |
|          <span data-ttu-id="0ee56-113">**Выход из команды**</span><span class="sxs-lookup"><span data-stu-id="0ee56-113">**Leave team**</span></span>           |    <span data-ttu-id="0ee56-114">Да</span><span class="sxs-lookup"><span data-stu-id="0ee56-114">Yes</span></span>     |     <span data-ttu-id="0ee56-115">Да</span><span class="sxs-lookup"><span data-stu-id="0ee56-115">Yes</span></span>     |
|  <span data-ttu-id="0ee56-116">**Изменение имени и описания команды**</span><span class="sxs-lookup"><span data-stu-id="0ee56-116">**Edit team name/description**</span></span>   |    <span data-ttu-id="0ee56-117">Да</span><span class="sxs-lookup"><span data-stu-id="0ee56-117">Yes</span></span>     |     <span data-ttu-id="0ee56-118">Нет</span><span class="sxs-lookup"><span data-stu-id="0ee56-118">No</span></span>      |
|          <span data-ttu-id="0ee56-119">**Удаление команды**</span><span class="sxs-lookup"><span data-stu-id="0ee56-119">**Delete team**</span></span>          |    <span data-ttu-id="0ee56-120">Да</span><span class="sxs-lookup"><span data-stu-id="0ee56-120">Yes</span></span>     |     <span data-ttu-id="0ee56-121">Нет</span><span class="sxs-lookup"><span data-stu-id="0ee56-121">No</span></span>      |
|          <span data-ttu-id="0ee56-122">**Добавление канала**</span><span class="sxs-lookup"><span data-stu-id="0ee56-122">**Add channel**</span></span>          |    <span data-ttu-id="0ee56-123">Да</span><span class="sxs-lookup"><span data-stu-id="0ee56-123">Yes</span></span>     |    <span data-ttu-id="0ee56-124">Да,<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="0ee56-124">Yes<sup>2</sup></span></span>|
| <span data-ttu-id="0ee56-125">**Изменение имени и описания канала**</span><span class="sxs-lookup"><span data-stu-id="0ee56-125">**Edit channel name/description**</span></span> |    <span data-ttu-id="0ee56-126">Да</span><span class="sxs-lookup"><span data-stu-id="0ee56-126">Yes</span></span>     |    <span data-ttu-id="0ee56-127">Да,<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="0ee56-127">Yes<sup>2</sup></span></span>|
|        <span data-ttu-id="0ee56-128">**Удаление канала**</span><span class="sxs-lookup"><span data-stu-id="0ee56-128">**Delete channel**</span></span>         |    <span data-ttu-id="0ee56-129">Да</span><span class="sxs-lookup"><span data-stu-id="0ee56-129">Yes</span></span>     |    <span data-ttu-id="0ee56-130">Да,<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="0ee56-130">Yes<sup>2</sup></span></span>|
|          <span data-ttu-id="0ee56-131">**Добавление участников**</span><span class="sxs-lookup"><span data-stu-id="0ee56-131">**Add members**</span></span>          |  <span data-ttu-id="0ee56-132">Да,<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="0ee56-132">Yes<sup>3</sup></span></span>   |     <span data-ttu-id="0ee56-133">No<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="0ee56-133">No<sup>4</sup></span></span>    |
|          <span data-ttu-id="0ee56-134">**Запрос на добавление участников**</span><span class="sxs-lookup"><span data-stu-id="0ee56-134">**Request to add members**</span></span>          |  <span data-ttu-id="0ee56-135">Н/Д</span><span class="sxs-lookup"><span data-stu-id="0ee56-135">N/A</span></span>   |     <span data-ttu-id="0ee56-136">Да,<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="0ee56-136">Yes<sup>5</sup></span></span>     |
|           <span data-ttu-id="0ee56-137">**Добавление вкладок**</span><span class="sxs-lookup"><span data-stu-id="0ee56-137">**Add tabs**</span></span>            |    <span data-ttu-id="0ee56-138">Да</span><span class="sxs-lookup"><span data-stu-id="0ee56-138">Yes</span></span>     |    <span data-ttu-id="0ee56-139">Да,<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="0ee56-139">Yes<sup>2</sup></span></span>|
|        <span data-ttu-id="0ee56-140">**Добавление соединителей**</span><span class="sxs-lookup"><span data-stu-id="0ee56-140">**Add connectors**</span></span>         |    <span data-ttu-id="0ee56-141">Да</span><span class="sxs-lookup"><span data-stu-id="0ee56-141">Yes</span></span>     |    <span data-ttu-id="0ee56-142">Да,<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="0ee56-142">Yes<sup>2</sup></span></span>|
|           <span data-ttu-id="0ee56-143">**Добавление ботов**</span><span class="sxs-lookup"><span data-stu-id="0ee56-143">**Add bots**</span></span>            |    <span data-ttu-id="0ee56-144">Да</span><span class="sxs-lookup"><span data-stu-id="0ee56-144">Yes</span></span>     |    <span data-ttu-id="0ee56-145">Да,<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="0ee56-145">Yes<sup>2</sup></span></span>|

<span data-ttu-id="0ee56-146"><sup>1</sup> владельцы группы могут создавать группы, если это не было запрещено.</span><span class="sxs-lookup"><span data-stu-id="0ee56-146"><sup>1</sup> Team owners can create teams unless they've been restricted from doing so.</span></span> <span data-ttu-id="0ee56-147">Сведения о разрешениях для создания групп ниже.</span><span class="sxs-lookup"><span data-stu-id="0ee56-147">See "Permissions to create teams" below.</span></span>
>
<span data-ttu-id="0ee56-148"><sup>2</sup> эти элементы могут быть отключены владельцем на уровне группы, в этом случае участники не смогут получить к ним доступ.</span><span class="sxs-lookup"><span data-stu-id="0ee56-148"><sup>2</sup> These items can be turned off by an owner at a team level, in which case members would not have access to them.</span></span>

<span data-ttu-id="0ee56-149"><sup>3</sup> после добавления участника в группу владелец также может превратить участника в состояние владельца.</span><span class="sxs-lookup"><span data-stu-id="0ee56-149"><sup>3</sup> After adding a member to a team, an owner can also promote a member to owner status.</span></span> <span data-ttu-id="0ee56-150">Кроме того, владелец может понизить свое состояние до участника.</span><span class="sxs-lookup"><span data-stu-id="0ee56-150">It is also possible for an owner to demote their own status to a member.</span></span>

<span data-ttu-id="0ee56-151"><sup>4</sup> участники группы могут добавлять других участников в общедоступную группу.</span><span class="sxs-lookup"><span data-stu-id="0ee56-151"><sup>4</sup> Team members can add other members to a public team.</span></span>

<span data-ttu-id="0ee56-152"><sup>5</sup> . Если участник группы не может напрямую добавить участников в закрытую группу, он может попросить кого-либо добавить в группу, в которой они уже находятся.</span><span class="sxs-lookup"><span data-stu-id="0ee56-152"><sup>5</sup> While a team member can't directly add members to a private team, they can request someone to be added to a team they're already a member of.</span></span> <span data-ttu-id="0ee56-153">Когда участник запрашивает пользователя, которого нужно добавить в группу, владельцы группы получают оповещение о том, что у него есть ожидающий запрос, который он может принять или отклонить.</span><span class="sxs-lookup"><span data-stu-id="0ee56-153">When a member requests someone to be added to a team, team owners receive an alert that they have a pending request that they can accept or deny.</span></span>



> [!NOTE]
> <span data-ttu-id="0ee56-154">Владельцы могут назначать других участников владельцами с помощью параметра "Показать команды".</span><span class="sxs-lookup"><span data-stu-id="0ee56-154">Owners can make other members owners in the View teams option.</span></span> <span data-ttu-id="0ee56-155">Команда может иметь до 100 владельцев.</span><span class="sxs-lookup"><span data-stu-id="0ee56-155">A team can have up to 100 owners.</span></span> <span data-ttu-id="0ee56-156">Рекомендуется иметь хотя бы несколько владельцев для более простого управления командой. Кроме того, в этом случае группы не будут теряться, если их единственный владелец покинет организацию.</span><span class="sxs-lookup"><span data-stu-id="0ee56-156">It's recommended to have at least a few owners to help manage the team; this will also prevent orphaned groups if the sole owner leaves your organization.</span></span> <span data-ttu-id="0ee56-157">Дополнительные сведения о потерянных группах см. в разделе [Назначение нового владельца потерянной группе](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span><span class="sxs-lookup"><span data-stu-id="0ee56-157">For more information about orphaned groups, see [Assign a new owner to an orphaned group](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span></span>


<a name="permissions-to-create-teams"></a><span data-ttu-id="0ee56-158">Разрешения на создание команд</span><span class="sxs-lookup"><span data-stu-id="0ee56-158">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="0ee56-159">По умолчанию все пользователи с почтовым ящиком в Exchange Online обладают правом на создание групп Office 365, а значит, и команды в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0ee56-159">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams.</span></span> <span data-ttu-id="0ee56-160">Вы можете более жестко регулировать или запретить создание команд и групп Office 365, делегировав права на создание и управление некоторому кругу пользователей.</span><span class="sxs-lookup"><span data-stu-id="0ee56-160">You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span> <span data-ttu-id="0ee56-161">Инструкции можно найти в разделе Управление разрешениями на [Создание групп Office 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span><span class="sxs-lookup"><span data-stu-id="0ee56-161">For instructions, see [Manage who can create Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>


||||
|---------|---------|---------|
| ![Значок, представляющий точку принятия решения](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="0ee56-163">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="0ee56-163">Decision Point</span></span>         |<span data-ttu-id="0ee56-164">Смогут ли все пользователи Microsoft Teams создавать команды (рекомендуется)?</span><span class="sxs-lookup"><span data-stu-id="0ee56-164">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![Значок, представляющий следующие шаги](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="0ee56-166">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="0ee56-166">Next Steps</span></span>         |<span data-ttu-id="0ee56-167">Измените разрешения по умолчанию для пользователей, которые могут создавать группы Office 365, если хотите ограничить круг лиц, способных создавать команды.</span><span class="sxs-lookup"><span data-stu-id="0ee56-167">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |
