---
title: Назначение ролей и разрешений в Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dansteve
description: Сведения о назначении разрешений и ролей для владельцев и участников команд в Microsoft Teams, включая права на создание команд.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb5f8d74fbb2d1802bfd96f7c86ffe9786fef827
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2018
---
<a name="assign-roles-and-permissions-in-microsoft-teams"></a><span data-ttu-id="398fe-103">Назначение ролей и разрешений в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="398fe-103">Assign roles and permissions in Microsoft Teams</span></span>
===============================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="398fe-104">В Microsoft Teams доступно две роли: **владелец** и **участник**.</span><span class="sxs-lookup"><span data-stu-id="398fe-104">Within Microsoft Teams there are two roles: **Owner** and **Member**.</span></span> <span data-ttu-id="398fe-105">По умолчанию создающий команду пользователь становится владельцем.</span><span class="sxs-lookup"><span data-stu-id="398fe-105">By default, a user that creates a new team is granted the Owner status.</span></span> <span data-ttu-id="398fe-106">При создании команды из существующей группы Office 365 разрешения наследуются.</span><span class="sxs-lookup"><span data-stu-id="398fe-106">If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="398fe-107">Следующая таблица описывает, чем различаются разрешения владельца и участника:</span><span class="sxs-lookup"><span data-stu-id="398fe-107">The table below shows the difference in permissions between an owner and a member:</span></span>

|  |<span data-ttu-id="398fe-108">Владелец команды</span><span class="sxs-lookup"><span data-stu-id="398fe-108">Team Owner</span></span>  |<span data-ttu-id="398fe-109">Участник команды</span><span class="sxs-lookup"><span data-stu-id="398fe-109">Team Member</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="398fe-110">**Создание команды**</span><span class="sxs-lookup"><span data-stu-id="398fe-110">**Create team**</span></span>     |<span data-ttu-id="398fe-111">Да</span><span class="sxs-lookup"><span data-stu-id="398fe-111">Yes</span></span>        |<span data-ttu-id="398fe-112">Нет</span><span class="sxs-lookup"><span data-stu-id="398fe-112">No</span></span>         |
|<span data-ttu-id="398fe-113">**Выход из команды**</span><span class="sxs-lookup"><span data-stu-id="398fe-113">**Leave team**</span></span>     |<span data-ttu-id="398fe-114">Да</span><span class="sxs-lookup"><span data-stu-id="398fe-114">Yes</span></span>         |<span data-ttu-id="398fe-115">Да</span><span class="sxs-lookup"><span data-stu-id="398fe-115">Yes</span></span>         |
|<span data-ttu-id="398fe-116">**Изменение имени и описания команды**</span><span class="sxs-lookup"><span data-stu-id="398fe-116">**Edit team name/description**</span></span>      |<span data-ttu-id="398fe-117">Да</span><span class="sxs-lookup"><span data-stu-id="398fe-117">Yes</span></span>         |<span data-ttu-id="398fe-118">Нет</span><span class="sxs-lookup"><span data-stu-id="398fe-118">No</span></span>         |
|<span data-ttu-id="398fe-119">**Удаление команды**</span><span class="sxs-lookup"><span data-stu-id="398fe-119">**Delete team**</span></span>      |<span data-ttu-id="398fe-120">Да</span><span class="sxs-lookup"><span data-stu-id="398fe-120">Yes</span></span>         |<span data-ttu-id="398fe-121">Нет</span><span class="sxs-lookup"><span data-stu-id="398fe-121">No</span></span>         |
|<span data-ttu-id="398fe-122">**Добавление канала**</span><span class="sxs-lookup"><span data-stu-id="398fe-122">**Add channel**</span></span>      |<span data-ttu-id="398fe-123">Да</span><span class="sxs-lookup"><span data-stu-id="398fe-123">Yes</span></span>         |<span data-ttu-id="398fe-124">Да\*</span><span class="sxs-lookup"><span data-stu-id="398fe-124">Yes\*</span></span>         |
|<span data-ttu-id="398fe-125">**Изменение имени и описания канала**</span><span class="sxs-lookup"><span data-stu-id="398fe-125">**Edit channel name/description**</span></span>      |<span data-ttu-id="398fe-126">Да</span><span class="sxs-lookup"><span data-stu-id="398fe-126">Yes</span></span>         |<span data-ttu-id="398fe-127">Да\*</span><span class="sxs-lookup"><span data-stu-id="398fe-127">Yes\*</span></span>         |
|<span data-ttu-id="398fe-128">**Удаление канала**</span><span class="sxs-lookup"><span data-stu-id="398fe-128">**Delete channel**</span></span>      |<span data-ttu-id="398fe-129">Да</span><span class="sxs-lookup"><span data-stu-id="398fe-129">Yes</span></span>         |<span data-ttu-id="398fe-130">Да\*</span><span class="sxs-lookup"><span data-stu-id="398fe-130">Yes\*</span></span>         |
|<span data-ttu-id="398fe-131">**Добавление участников**</span><span class="sxs-lookup"><span data-stu-id="398fe-131">**Add members**</span></span>      |<span data-ttu-id="398fe-132">Да**</span><span class="sxs-lookup"><span data-stu-id="398fe-132">Yes**</span></span>         |<span data-ttu-id="398fe-133">Нет</span><span class="sxs-lookup"><span data-stu-id="398fe-133">No</span></span>         |
|<span data-ttu-id="398fe-134">**Добавление вкладок**</span><span class="sxs-lookup"><span data-stu-id="398fe-134">**Add tabs**</span></span>      |<span data-ttu-id="398fe-135">Да</span><span class="sxs-lookup"><span data-stu-id="398fe-135">Yes</span></span>         |<span data-ttu-id="398fe-136">Да\*</span><span class="sxs-lookup"><span data-stu-id="398fe-136">Yes\*</span></span>         |
|<span data-ttu-id="398fe-137">**Добавление соединителей**</span><span class="sxs-lookup"><span data-stu-id="398fe-137">**Add connectors**</span></span>      |<span data-ttu-id="398fe-138">Да</span><span class="sxs-lookup"><span data-stu-id="398fe-138">Yes</span></span>         |<span data-ttu-id="398fe-139">Да\*</span><span class="sxs-lookup"><span data-stu-id="398fe-139">Yes\*</span></span>         |
|<span data-ttu-id="398fe-140">**Добавление ботов**</span><span class="sxs-lookup"><span data-stu-id="398fe-140">**Add bots**</span></span>      |<span data-ttu-id="398fe-141">Да</span><span class="sxs-lookup"><span data-stu-id="398fe-141">Yes</span></span>         |<span data-ttu-id="398fe-142">Да\*</span><span class="sxs-lookup"><span data-stu-id="398fe-142">Yes\*</span></span>         |
<span data-ttu-id="398fe-143">\* Эти функции могут быть отключены владельцем на уровне команды, в случае чего они будут недоступны участникам.</span><span class="sxs-lookup"><span data-stu-id="398fe-143">\* These items can be turned off by an owner at a team level, in which case members would not have access to that.</span></span>

<span data-ttu-id="398fe-144">\*\*Добавив участника в команду, владелец также может повысить его до владельца.</span><span class="sxs-lookup"><span data-stu-id="398fe-144">\*\*After adding a member to a team, an Owner can also promote a Member to Owner status.</span></span> <span data-ttu-id="398fe-145">Кроме того, владелец может понизить себя до участника.</span><span class="sxs-lookup"><span data-stu-id="398fe-145">It is also possible for an Owner to demote their own status to a Member.</span></span>



> [!NOTE]
> <span data-ttu-id="398fe-146">Владельцы могут назначать других участников владельцами с помощью параметра "Показать команды".</span><span class="sxs-lookup"><span data-stu-id="398fe-146">Owners can make other members owners in the View teams option.</span></span> <span data-ttu-id="398fe-147">Команда может иметь до 100 владельцев.</span><span class="sxs-lookup"><span data-stu-id="398fe-147">A team can have up to 100 owners.</span></span> <span data-ttu-id="398fe-148">Рекомендуется иметь хотя бы несколько владельцев для более простого управления командой. Кроме того, в этом случае группы не будут теряться, если их единственный владелец покинет организацию.</span><span class="sxs-lookup"><span data-stu-id="398fe-148">It's recommended to have at least a few owners to help manage the team; this will also prevent orphaned groups if the sole owner leaves your organization.</span></span> <span data-ttu-id="398fe-149">Дополнительные сведения о потерянных группах см. в разделе [Назначение нового владельца потерянной группе](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span><span class="sxs-lookup"><span data-stu-id="398fe-149">For more information about orphaned groups, see [Assign a new owner to an orphaned group](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span></span>


<a name="permissions-to-create-teams"></a><span data-ttu-id="398fe-150">Разрешения на создание команд</span><span class="sxs-lookup"><span data-stu-id="398fe-150">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="398fe-151">По умолчанию все пользователи с почтовым ящиком в Exchange Online обладают правом на создание групп Office 365, а значит, и команды в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="398fe-151">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams.</span></span> <span data-ttu-id="398fe-152">Вы можете более жестко регулировать или запретить создание команд и групп Office 365, делегировав права на создание и управление некоторому кругу пользователей.</span><span class="sxs-lookup"><span data-stu-id="398fe-152">You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span>

<span data-ttu-id="398fe-153">Если вашу организацию интересует именно этот вариант, ознакомьтесь с приведенными ниже инструкциями.</span><span class="sxs-lookup"><span data-stu-id="398fe-153">If your organization is interested in doing this, the instructions below outlines the tasks required to do so.</span></span>

1.  <span data-ttu-id="398fe-154">Выберите или создайте группу безопасности, пользователям которой будут делегироваться разрешения на создание групп Office 365.</span><span class="sxs-lookup"><span data-stu-id="398fe-154">Identify or create a security group (SG) of users who will have delegated permissions to create Office 365 groups.</span></span>

    <span data-ttu-id="398fe-155">а.</span><span class="sxs-lookup"><span data-stu-id="398fe-155">a.</span></span>  <span data-ttu-id="398fe-156">**Действие:** настройте группу безопасности в Office 365, куда можно добавить пользователей, способных создавать группы Office 365.</span><span class="sxs-lookup"><span data-stu-id="398fe-156">**Action:** Set up a security group in Office 365 so you can add your users who can create Office 365 groups.</span></span>

    <span data-ttu-id="398fe-157">б.</span><span class="sxs-lookup"><span data-stu-id="398fe-157">b.</span></span>  <span data-ttu-id="398fe-158">Дополнительные сведения см. в статье [Создание, изменение или удаление группы безопасности в Центре администрирования Office 365](https://support.office.com/article/Create-edit-or-delete-a-security-group-in-the-Office-365-admin-center-55c96b32-e086-4c9e-948b-a018b44510cb).</span><span class="sxs-lookup"><span data-stu-id="398fe-158">For more information, see [Create, edit, or delete a security group in the Office 365 admin center](https://support.office.com/article/Create-edit-or-delete-a-security-group-in-the-Office-365-admin-center-55c96b32-e086-4c9e-948b-a018b44510cb).</span></span>

2.  <span data-ttu-id="398fe-159">Реализуйте управление правами на создание групп в рамках всей организации.</span><span class="sxs-lookup"><span data-stu-id="398fe-159">Verify that the company-wide control for users to create groups is enabled.</span></span>

    <span data-ttu-id="398fe-160">а.</span><span class="sxs-lookup"><span data-stu-id="398fe-160">a.</span></span>  <span data-ttu-id="398fe-161">**Действие:** запустите приведенный ниже сценарий PowerShell и убедитесь, что для параметра UsersPermissiontoCreateGroupsEnabled задано значение **True.**</span><span class="sxs-lookup"><span data-stu-id="398fe-161">**Action:** Run the following PowerShell script and verify UsersPermissiontoCreateGroupsEnabled parameter is set to **True.**</span></span>

    ```
    Connect-MsolService

    Get-MsolCompanyInformation
    ```

    <span data-ttu-id="398fe-162">б.</span><span class="sxs-lookup"><span data-stu-id="398fe-162">b.</span></span>  <span data-ttu-id="398fe-163">Если задано другое значение, запустите командлет Set-MsolCompanySettings**, чтобы установить значение True**.</span><span class="sxs-lookup"><span data-stu-id="398fe-163">If this is not true, run the Set-MsolCompanySettings  cmdlet **to set it to True**.</span></span>
<span data-ttu-id="398fe-164">Set-MsolCompanySettings -UsersPermissionToCreateGroupsEnabled $True</span><span class="sxs-lookup"><span data-stu-id="398fe-164">Set-MsolCompanySettings -UsersPermissionToCreateGroupsEnabled $True</span></span>

    <span data-ttu-id="398fe-165">в.</span><span class="sxs-lookup"><span data-stu-id="398fe-165">c.</span></span> <span data-ttu-id="398fe-166">Дополнительные сведения см. в статье: [Управление созданием групп Office 365](https://support.office.com/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-001&ad=US#checkclevelsettings).</span><span class="sxs-lookup"><span data-stu-id="398fe-166">For more information, see: [Manage Office 365 Group Creation](https://support.office.com/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-001&ad=US#checkclevelsettings).</span></span>

3.  <span data-ttu-id="398fe-167">Настройте параметры групп Office 365, чтобы предоставить права на создание групп только указанной группе безопасности.</span><span class="sxs-lookup"><span data-stu-id="398fe-167">Configure Office 365 Group settings to allow only identified security group has permissions to create groups</span></span>

    <span data-ttu-id="398fe-168">а.</span><span class="sxs-lookup"><span data-stu-id="398fe-168">a.</span></span>  <span data-ttu-id="398fe-169">**Действие:** создайте объект параметров, содержащий параметры конфигурации для группы, которой будут назначены делегированные разрешения на создание групп.</span><span class="sxs-lookup"><span data-stu-id="398fe-169">**Action:** Create a group settings object that contains the configuration settings of the group that will be assigned delegated permissions to create groups.</span></span> 

    ```
    Connect-AzureAD

    $Template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b

    $Setting = $template.CreateDirectorySetting()

    $setting["EnableGroupCreation"] = "false"

    $setting["GroupCreationAllowedGroupId"] = "&lt;ObjectId of Group Allowed to Create Groups>"

    New-AzureADDirectorySetting -DirectorySetting $settings
    ```

    <span data-ttu-id="398fe-170">б.</span><span class="sxs-lookup"><span data-stu-id="398fe-170">b.</span></span> <span data-ttu-id="398fe-171">Дополнительные сведения см. в статье: [Управление созданием групп Office 365](https://support.office.com/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-US&ad=US#step3).</span><span class="sxs-lookup"><span data-stu-id="398fe-171">For more information, see: [Manage Office 365 Group Creation](https://support.office.com/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-US&ad=US#step3).</span></span>


||||
|---------|---------|---------|
| ![Значок для точки принятия решений.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="398fe-173">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="398fe-173">Decision Point</span></span>         |<span data-ttu-id="398fe-174">Смогут ли все пользователи Microsoft Teams создавать команды (рекомендуется)?</span><span class="sxs-lookup"><span data-stu-id="398fe-174">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![Значок дальнейших действий.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="398fe-176">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="398fe-176">Next Steps</span></span>         |<span data-ttu-id="398fe-177">Измените разрешения по умолчанию для пользователей, которые могут создавать группы Office 365, если хотите ограничить круг лиц, способных создавать команды.</span><span class="sxs-lookup"><span data-stu-id="398fe-177">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |
