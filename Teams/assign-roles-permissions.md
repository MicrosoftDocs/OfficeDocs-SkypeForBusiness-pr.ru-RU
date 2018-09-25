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
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1d5b3f52caf7de455d2b579a3360d17e18602450
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014293"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a><span data-ttu-id="8a83b-103">Назначение группы владельцев и членов в группы Microsoft</span><span class="sxs-lookup"><span data-stu-id="8a83b-103">Assign team owners and members in Microsoft Teams</span></span>
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="8a83b-104">Внутри групп Майкрософт существует две роли пользователя: **владельца** и **член**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-104">Within Microsoft Teams there are two user roles: **Owner** and **Member**.</span></span> <span data-ttu-id="8a83b-105">По умолчанию пользователь, который создает новые группы предоставляется состояния владельца.</span><span class="sxs-lookup"><span data-stu-id="8a83b-105">By default, a user who creates a new team is granted the Owner status.</span></span> <span data-ttu-id="8a83b-106">При создании команды из существующей группы Office 365 разрешения наследуются.</span><span class="sxs-lookup"><span data-stu-id="8a83b-106">If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="8a83b-107">Следующая таблица описывает, чем различаются разрешения владельца и участника:</span><span class="sxs-lookup"><span data-stu-id="8a83b-107">The table below shows the difference in permissions between an owner and a member:</span></span>

|  |<span data-ttu-id="8a83b-108">Владелец команды</span><span class="sxs-lookup"><span data-stu-id="8a83b-108">Team Owner</span></span>  |<span data-ttu-id="8a83b-109">Участник команды</span><span class="sxs-lookup"><span data-stu-id="8a83b-109">Team Member</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="8a83b-110">**Создание команды**</span><span class="sxs-lookup"><span data-stu-id="8a83b-110">**Create team**</span></span>     |<span data-ttu-id="8a83b-111">Да</span><span class="sxs-lookup"><span data-stu-id="8a83b-111">Yes</span></span>        |<span data-ttu-id="8a83b-112">Нет</span><span class="sxs-lookup"><span data-stu-id="8a83b-112">No</span></span>         |
|<span data-ttu-id="8a83b-113">**Выход из команды**</span><span class="sxs-lookup"><span data-stu-id="8a83b-113">**Leave team**</span></span>     |<span data-ttu-id="8a83b-114">Да</span><span class="sxs-lookup"><span data-stu-id="8a83b-114">Yes</span></span>         |<span data-ttu-id="8a83b-115">Да</span><span class="sxs-lookup"><span data-stu-id="8a83b-115">Yes</span></span>         |
|<span data-ttu-id="8a83b-116">**Изменение имени и описания команды**</span><span class="sxs-lookup"><span data-stu-id="8a83b-116">**Edit team name/description**</span></span>      |<span data-ttu-id="8a83b-117">Да</span><span class="sxs-lookup"><span data-stu-id="8a83b-117">Yes</span></span>         |<span data-ttu-id="8a83b-118">Нет</span><span class="sxs-lookup"><span data-stu-id="8a83b-118">No</span></span>         |
|<span data-ttu-id="8a83b-119">**Удаление команды**</span><span class="sxs-lookup"><span data-stu-id="8a83b-119">**Delete team**</span></span>      |<span data-ttu-id="8a83b-120">Да</span><span class="sxs-lookup"><span data-stu-id="8a83b-120">Yes</span></span>         |<span data-ttu-id="8a83b-121">Нет</span><span class="sxs-lookup"><span data-stu-id="8a83b-121">No</span></span>         |
|<span data-ttu-id="8a83b-122">**Добавление канала**</span><span class="sxs-lookup"><span data-stu-id="8a83b-122">**Add channel**</span></span>      |<span data-ttu-id="8a83b-123">Да</span><span class="sxs-lookup"><span data-stu-id="8a83b-123">Yes</span></span>         |<span data-ttu-id="8a83b-124">Да\*</span><span class="sxs-lookup"><span data-stu-id="8a83b-124">Yes\*</span></span>         |
|<span data-ttu-id="8a83b-125">**Изменение имени и описания канала**</span><span class="sxs-lookup"><span data-stu-id="8a83b-125">**Edit channel name/description**</span></span>      |<span data-ttu-id="8a83b-126">Да</span><span class="sxs-lookup"><span data-stu-id="8a83b-126">Yes</span></span>         |<span data-ttu-id="8a83b-127">Да\*</span><span class="sxs-lookup"><span data-stu-id="8a83b-127">Yes\*</span></span>         |
|<span data-ttu-id="8a83b-128">**Удаление канала**</span><span class="sxs-lookup"><span data-stu-id="8a83b-128">**Delete channel**</span></span>      |<span data-ttu-id="8a83b-129">Да</span><span class="sxs-lookup"><span data-stu-id="8a83b-129">Yes</span></span>         |<span data-ttu-id="8a83b-130">Да\*</span><span class="sxs-lookup"><span data-stu-id="8a83b-130">Yes\*</span></span>         |
|<span data-ttu-id="8a83b-131">**Добавление участников**</span><span class="sxs-lookup"><span data-stu-id="8a83b-131">**Add members**</span></span>      |<span data-ttu-id="8a83b-132">Да\*\*</span><span class="sxs-lookup"><span data-stu-id="8a83b-132">Yes\*\*</span></span>         |<span data-ttu-id="8a83b-133">Нет</span><span class="sxs-lookup"><span data-stu-id="8a83b-133">No</span></span>         |
|<span data-ttu-id="8a83b-134">**Добавление вкладок**</span><span class="sxs-lookup"><span data-stu-id="8a83b-134">**Add tabs**</span></span>      |<span data-ttu-id="8a83b-135">Да</span><span class="sxs-lookup"><span data-stu-id="8a83b-135">Yes</span></span>         |<span data-ttu-id="8a83b-136">Да\*</span><span class="sxs-lookup"><span data-stu-id="8a83b-136">Yes\*</span></span>         |
|<span data-ttu-id="8a83b-137">**Добавление соединителей**</span><span class="sxs-lookup"><span data-stu-id="8a83b-137">**Add connectors**</span></span>      |<span data-ttu-id="8a83b-138">Да</span><span class="sxs-lookup"><span data-stu-id="8a83b-138">Yes</span></span>         |<span data-ttu-id="8a83b-139">Да\*</span><span class="sxs-lookup"><span data-stu-id="8a83b-139">Yes\*</span></span>         |
|<span data-ttu-id="8a83b-140">**Добавление ботов**</span><span class="sxs-lookup"><span data-stu-id="8a83b-140">**Add bots**</span></span>      |<span data-ttu-id="8a83b-141">Да</span><span class="sxs-lookup"><span data-stu-id="8a83b-141">Yes</span></span>         |<span data-ttu-id="8a83b-142">Да\*</span><span class="sxs-lookup"><span data-stu-id="8a83b-142">Yes\*</span></span>         |
<span data-ttu-id="8a83b-143">\*Эти элементы может быть отключена, пользователь с уровнем рабочая группа, в противном случае члены не имеет доступа к ним.</span><span class="sxs-lookup"><span data-stu-id="8a83b-143">\* These items can be turned off by an owner at a team level, in which case members would not have access to them.</span></span>

<span data-ttu-id="8a83b-144">\*\*Добавив участника в команду, владелец также может повысить его до владельца.</span><span class="sxs-lookup"><span data-stu-id="8a83b-144">\*\*After adding a member to a team, an Owner can also promote a Member to Owner status.</span></span> <span data-ttu-id="8a83b-145">Кроме того, владелец может понизить себя до участника.</span><span class="sxs-lookup"><span data-stu-id="8a83b-145">It is also possible for an Owner to demote their own status to a Member.</span></span>



> [!NOTE]
> <span data-ttu-id="8a83b-146">Владельцы могут назначать других участников владельцами с помощью параметра "Показать команды".</span><span class="sxs-lookup"><span data-stu-id="8a83b-146">Owners can make other members owners in the View teams option.</span></span> <span data-ttu-id="8a83b-147">Команда может иметь до 100 владельцев.</span><span class="sxs-lookup"><span data-stu-id="8a83b-147">A team can have up to 100 owners.</span></span> <span data-ttu-id="8a83b-148">Рекомендуется иметь хотя бы несколько владельцев для более простого управления командой. Кроме того, в этом случае группы не будут теряться, если их единственный владелец покинет организацию.</span><span class="sxs-lookup"><span data-stu-id="8a83b-148">It's recommended to have at least a few owners to help manage the team; this will also prevent orphaned groups if the sole owner leaves your organization.</span></span> <span data-ttu-id="8a83b-149">Дополнительные сведения о потерянных группах см. в разделе [Назначение нового владельца потерянной группе](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span><span class="sxs-lookup"><span data-stu-id="8a83b-149">For more information about orphaned groups, see [Assign a new owner to an orphaned group](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span></span>


<a name="permissions-to-create-teams"></a><span data-ttu-id="8a83b-150">Разрешения на создание команд</span><span class="sxs-lookup"><span data-stu-id="8a83b-150">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="8a83b-151">По умолчанию все пользователи с почтовым ящиком в Exchange Online обладают правом на создание групп Office 365, а значит, и команды в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8a83b-151">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams.</span></span> <span data-ttu-id="8a83b-152">Вы можете более жестко регулировать или запретить создание команд и групп Office 365, делегировав права на создание и управление некоторому кругу пользователей.</span><span class="sxs-lookup"><span data-stu-id="8a83b-152">You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span> <span data-ttu-id="8a83b-153">Сведения содержатся в разделе [Управление, кто может создавать группы Office 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span><span class="sxs-lookup"><span data-stu-id="8a83b-153">For instructions, see [Manage who can create Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>


||||
|---------|---------|---------|
| ![Значок для точки принятия решений.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="8a83b-155">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="8a83b-155">Decision Point</span></span>         |<span data-ttu-id="8a83b-156">Смогут ли все пользователи Microsoft Teams создавать команды (рекомендуется)?</span><span class="sxs-lookup"><span data-stu-id="8a83b-156">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![Значок дальнейших действий.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="8a83b-158">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="8a83b-158">Next Steps</span></span>         |<span data-ttu-id="8a83b-159">Измените разрешения по умолчанию для пользователей, которые могут создавать группы Office 365, если хотите ограничить круг лиц, способных создавать команды.</span><span class="sxs-lookup"><span data-stu-id="8a83b-159">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |
