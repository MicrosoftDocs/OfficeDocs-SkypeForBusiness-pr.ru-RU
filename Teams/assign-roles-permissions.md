---
title: Назначение группы владельцев и членов в группы Microsoft
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
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: a2fd9f611d616f368973ced432e886bf4ba9d8f5
ms.sourcegitcommit: ab4476127222d9f0aa9ee503132ff9bdabcaf9bc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "24021812"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a><span data-ttu-id="0f1b6-103">Назначение группы владельцев и членов в группы Microsoft</span><span class="sxs-lookup"><span data-stu-id="0f1b6-103">Assign team owners and members in Microsoft Teams</span></span>
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="0f1b6-104">Внутри групп Майкрософт существует две роли пользователя: **владельца** и **член**.</span><span class="sxs-lookup"><span data-stu-id="0f1b6-104">Within Microsoft Teams there are two user roles: **Owner** and **Member**.</span></span> <span data-ttu-id="0f1b6-105">По умолчанию пользователь, который создает новые группы предоставляется состояния владельца.</span><span class="sxs-lookup"><span data-stu-id="0f1b6-105">By default, a user who creates a new team is granted the Owner status.</span></span> <span data-ttu-id="0f1b6-106">При создании команды из существующей группы Office 365 разрешения наследуются.</span><span class="sxs-lookup"><span data-stu-id="0f1b6-106">If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="0f1b6-107">Следующая таблица описывает, чем различаются разрешения владельца и участника:</span><span class="sxs-lookup"><span data-stu-id="0f1b6-107">The table below shows the difference in permissions between an owner and a member:</span></span>

|  |<span data-ttu-id="0f1b6-108">Владелец команды</span><span class="sxs-lookup"><span data-stu-id="0f1b6-108">Team Owner</span></span>  |<span data-ttu-id="0f1b6-109">Участник команды</span><span class="sxs-lookup"><span data-stu-id="0f1b6-109">Team Member</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="0f1b6-110">**Создание команды**</span><span class="sxs-lookup"><span data-stu-id="0f1b6-110">**Create team**</span></span>     |<span data-ttu-id="0f1b6-111">Да</span><span class="sxs-lookup"><span data-stu-id="0f1b6-111">Yes</span></span>        |<span data-ttu-id="0f1b6-112">Нет</span><span class="sxs-lookup"><span data-stu-id="0f1b6-112">No</span></span>         |
|<span data-ttu-id="0f1b6-113">**Выход из команды**</span><span class="sxs-lookup"><span data-stu-id="0f1b6-113">**Leave team**</span></span>     |<span data-ttu-id="0f1b6-114">Да</span><span class="sxs-lookup"><span data-stu-id="0f1b6-114">Yes</span></span>         |<span data-ttu-id="0f1b6-115">Да</span><span class="sxs-lookup"><span data-stu-id="0f1b6-115">Yes</span></span>         |
|<span data-ttu-id="0f1b6-116">**Изменение имени и описания команды**</span><span class="sxs-lookup"><span data-stu-id="0f1b6-116">**Edit team name/description**</span></span>      |<span data-ttu-id="0f1b6-117">Да</span><span class="sxs-lookup"><span data-stu-id="0f1b6-117">Yes</span></span>         |<span data-ttu-id="0f1b6-118">Нет</span><span class="sxs-lookup"><span data-stu-id="0f1b6-118">No</span></span>         |
|<span data-ttu-id="0f1b6-119">**Удаление команды**</span><span class="sxs-lookup"><span data-stu-id="0f1b6-119">**Delete team**</span></span>      |<span data-ttu-id="0f1b6-120">Да</span><span class="sxs-lookup"><span data-stu-id="0f1b6-120">Yes</span></span>         |<span data-ttu-id="0f1b6-121">Нет</span><span class="sxs-lookup"><span data-stu-id="0f1b6-121">No</span></span>         |
|<span data-ttu-id="0f1b6-122">**Добавление канала**</span><span class="sxs-lookup"><span data-stu-id="0f1b6-122">**Add channel**</span></span>      |<span data-ttu-id="0f1b6-123">Да</span><span class="sxs-lookup"><span data-stu-id="0f1b6-123">Yes</span></span>         |<span data-ttu-id="0f1b6-124">Да\*</span><span class="sxs-lookup"><span data-stu-id="0f1b6-124">Yes\*</span></span>         |
|<span data-ttu-id="0f1b6-125">**Изменение имени и описания канала**</span><span class="sxs-lookup"><span data-stu-id="0f1b6-125">**Edit channel name/description**</span></span>      |<span data-ttu-id="0f1b6-126">Да</span><span class="sxs-lookup"><span data-stu-id="0f1b6-126">Yes</span></span>         |<span data-ttu-id="0f1b6-127">Да\*</span><span class="sxs-lookup"><span data-stu-id="0f1b6-127">Yes\*</span></span>         |
|<span data-ttu-id="0f1b6-128">**Удаление канала**</span><span class="sxs-lookup"><span data-stu-id="0f1b6-128">**Delete channel**</span></span>      |<span data-ttu-id="0f1b6-129">Да</span><span class="sxs-lookup"><span data-stu-id="0f1b6-129">Yes</span></span>         |<span data-ttu-id="0f1b6-130">Да\*</span><span class="sxs-lookup"><span data-stu-id="0f1b6-130">Yes\*</span></span>         |
|<span data-ttu-id="0f1b6-131">**Добавление участников**</span><span class="sxs-lookup"><span data-stu-id="0f1b6-131">**Add members**</span></span>      |<span data-ttu-id="0f1b6-132">Да\*\*</span><span class="sxs-lookup"><span data-stu-id="0f1b6-132">Yes\*\*</span></span>         |<span data-ttu-id="0f1b6-133">Нет</span><span class="sxs-lookup"><span data-stu-id="0f1b6-133">No</span></span>         |
|<span data-ttu-id="0f1b6-134">**Добавление вкладок**</span><span class="sxs-lookup"><span data-stu-id="0f1b6-134">**Add tabs**</span></span>      |<span data-ttu-id="0f1b6-135">Да</span><span class="sxs-lookup"><span data-stu-id="0f1b6-135">Yes</span></span>         |<span data-ttu-id="0f1b6-136">Да\*</span><span class="sxs-lookup"><span data-stu-id="0f1b6-136">Yes\*</span></span>         |
|<span data-ttu-id="0f1b6-137">**Добавление соединителей**</span><span class="sxs-lookup"><span data-stu-id="0f1b6-137">**Add connectors**</span></span>      |<span data-ttu-id="0f1b6-138">Да</span><span class="sxs-lookup"><span data-stu-id="0f1b6-138">Yes</span></span>         |<span data-ttu-id="0f1b6-139">Да\*</span><span class="sxs-lookup"><span data-stu-id="0f1b6-139">Yes\*</span></span>         |
|<span data-ttu-id="0f1b6-140">**Добавление ботов**</span><span class="sxs-lookup"><span data-stu-id="0f1b6-140">**Add bots**</span></span>      |<span data-ttu-id="0f1b6-141">Да</span><span class="sxs-lookup"><span data-stu-id="0f1b6-141">Yes</span></span>         |<span data-ttu-id="0f1b6-142">Да\*</span><span class="sxs-lookup"><span data-stu-id="0f1b6-142">Yes\*</span></span>         |
<span data-ttu-id="0f1b6-143">\*Эти элементы может быть отключена, пользователь с уровнем рабочая группа, в противном случае члены не имеет доступа к ним.</span><span class="sxs-lookup"><span data-stu-id="0f1b6-143">\* These items can be turned off by an owner at a team level, in which case members would not have access to them.</span></span>

<span data-ttu-id="0f1b6-144">\*\*Добавив участника в команду, владелец также может повысить его до владельца.</span><span class="sxs-lookup"><span data-stu-id="0f1b6-144">\*\*After adding a member to a team, an Owner can also promote a Member to Owner status.</span></span> <span data-ttu-id="0f1b6-145">Кроме того, владелец может понизить себя до участника.</span><span class="sxs-lookup"><span data-stu-id="0f1b6-145">It is also possible for an Owner to demote their own status to a Member.</span></span>



> [!NOTE]
> <span data-ttu-id="0f1b6-146">Владельцы могут назначать других участников владельцами с помощью параметра "Показать команды".</span><span class="sxs-lookup"><span data-stu-id="0f1b6-146">Owners can make other members owners in the View teams option.</span></span> <span data-ttu-id="0f1b6-147">Команда может иметь до 100 владельцев.</span><span class="sxs-lookup"><span data-stu-id="0f1b6-147">A team can have up to 100 owners.</span></span> <span data-ttu-id="0f1b6-148">Рекомендуется иметь хотя бы несколько владельцев для более простого управления командой. Кроме того, в этом случае группы не будут теряться, если их единственный владелец покинет организацию.</span><span class="sxs-lookup"><span data-stu-id="0f1b6-148">It's recommended to have at least a few owners to help manage the team; this will also prevent orphaned groups if the sole owner leaves your organization.</span></span> <span data-ttu-id="0f1b6-149">Дополнительные сведения о потерянных группах см. в разделе [Назначение нового владельца потерянной группе](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span><span class="sxs-lookup"><span data-stu-id="0f1b6-149">For more information about orphaned groups, see [Assign a new owner to an orphaned group](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span></span>


<a name="permissions-to-create-teams"></a><span data-ttu-id="0f1b6-150">Разрешения на создание команд</span><span class="sxs-lookup"><span data-stu-id="0f1b6-150">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="0f1b6-151">По умолчанию все пользователи с почтовым ящиком в Exchange Online обладают правом на создание групп Office 365, а значит, и команды в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0f1b6-151">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams.</span></span> <span data-ttu-id="0f1b6-152">Вы можете более жестко регулировать или запретить создание команд и групп Office 365, делегировав права на создание и управление некоторому кругу пользователей.</span><span class="sxs-lookup"><span data-stu-id="0f1b6-152">You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span> <span data-ttu-id="0f1b6-153">Сведения содержатся в разделе [Управление, кто может создавать группы Office 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span><span class="sxs-lookup"><span data-stu-id="0f1b6-153">For instructions, see [Manage who can create Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>


||||
|---------|---------|---------|
| ![Значок для точки принятия решений.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="0f1b6-155">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="0f1b6-155">Decision Point</span></span>         |<span data-ttu-id="0f1b6-156">Смогут ли все пользователи Microsoft Teams создавать команды (рекомендуется)?</span><span class="sxs-lookup"><span data-stu-id="0f1b6-156">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![Значок дальнейших действий.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="0f1b6-158">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="0f1b6-158">Next Steps</span></span>         |<span data-ttu-id="0f1b6-159">Измените разрешения по умолчанию для пользователей, которые могут создавать группы Office 365, если хотите ограничить круг лиц, способных создавать команды.</span><span class="sxs-lookup"><span data-stu-id="0f1b6-159">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |
