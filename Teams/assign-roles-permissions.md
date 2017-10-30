---
title: "Назначение ролей и разрешений в Microsoft Teams | Служба поддержки Майкрософт"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Сведения о назначении разрешений и ролей для владельцев и участников команд в Microsoft Teams, включая права на создание команд."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 1ccb0ff3216464aca5a17c3bebeb0e259929e798
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2017
---
<a name="assign-roles-and-permissions-in-microsoft-teams"></a><span data-ttu-id="daaac-103">Назначение ролей и разрешений в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="daaac-103">Assign roles and permissions in Microsoft Teams</span></span>
===============================================

<span data-ttu-id="daaac-104">В Microsoft Teams доступно две роли: **владелец** и **участник**.</span><span class="sxs-lookup"><span data-stu-id="daaac-104">Within Microsoft Teams there are two roles: **Owner** and **Member**.</span></span> <span data-ttu-id="daaac-105">По умолчанию создающий команду пользователь становится владельцем.</span><span class="sxs-lookup"><span data-stu-id="daaac-105">By default, a user that creates a new team is granted the Owner status.</span></span> <span data-ttu-id="daaac-106">При создании команды из существующей группы Office 365 разрешения наследуются.</span><span class="sxs-lookup"><span data-stu-id="daaac-106">If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="daaac-107">Следующая таблица описывает, чем различаются разрешения владельца и участника:</span><span class="sxs-lookup"><span data-stu-id="daaac-107">The table below shows the difference in permissions between an owner and a member:</span></span>

|  |<span data-ttu-id="daaac-108">Владелец команды</span><span class="sxs-lookup"><span data-stu-id="daaac-108">Team Owner</span></span>  |<span data-ttu-id="daaac-109">Участник команды</span><span class="sxs-lookup"><span data-stu-id="daaac-109">Team Member</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="daaac-110">**Создание команды**</span><span class="sxs-lookup"><span data-stu-id="daaac-110">**Create team**</span></span>     |<span data-ttu-id="daaac-111">Да</span><span class="sxs-lookup"><span data-stu-id="daaac-111">Yes</span></span>        |<span data-ttu-id="daaac-112">Нет</span><span class="sxs-lookup"><span data-stu-id="daaac-112">No</span></span>         |
|<span data-ttu-id="daaac-113">**Выход из команды**</span><span class="sxs-lookup"><span data-stu-id="daaac-113">**Leave team**</span></span>     |<span data-ttu-id="daaac-114">Да</span><span class="sxs-lookup"><span data-stu-id="daaac-114">Yes</span></span>         |<span data-ttu-id="daaac-115">Да</span><span class="sxs-lookup"><span data-stu-id="daaac-115">Yes</span></span>         |
|<span data-ttu-id="daaac-116">**Изменение имени и описания команды**</span><span class="sxs-lookup"><span data-stu-id="daaac-116">**Edit team name/description**</span></span>      |<span data-ttu-id="daaac-117">Да</span><span class="sxs-lookup"><span data-stu-id="daaac-117">Yes</span></span>         |<span data-ttu-id="daaac-118">Нет</span><span class="sxs-lookup"><span data-stu-id="daaac-118">No</span></span>         |
|<span data-ttu-id="daaac-119">**Удаление команды**</span><span class="sxs-lookup"><span data-stu-id="daaac-119">**Delete team**</span></span>      |<span data-ttu-id="daaac-120">Да</span><span class="sxs-lookup"><span data-stu-id="daaac-120">Yes</span></span>         |<span data-ttu-id="daaac-121">Нет</span><span class="sxs-lookup"><span data-stu-id="daaac-121">No</span></span>         |
|<span data-ttu-id="daaac-122">**Добавление канала**</span><span class="sxs-lookup"><span data-stu-id="daaac-122">**Add channel**</span></span>      |<span data-ttu-id="daaac-123">Да</span><span class="sxs-lookup"><span data-stu-id="daaac-123">Yes</span></span>         |<span data-ttu-id="daaac-124">Да*</span><span class="sxs-lookup"><span data-stu-id="daaac-124">Yes*</span></span>         |
|<span data-ttu-id="daaac-125">**Изменение имени и описания канала**</span><span class="sxs-lookup"><span data-stu-id="daaac-125">**Edit channel name/description**</span></span>      |<span data-ttu-id="daaac-126">Да</span><span class="sxs-lookup"><span data-stu-id="daaac-126">Yes</span></span>         |<span data-ttu-id="daaac-127">Да*</span><span class="sxs-lookup"><span data-stu-id="daaac-127">Yes*</span></span>         |
|<span data-ttu-id="daaac-128">**Удаление канала**</span><span class="sxs-lookup"><span data-stu-id="daaac-128">**Delete channel**</span></span>      |<span data-ttu-id="daaac-129">Да</span><span class="sxs-lookup"><span data-stu-id="daaac-129">Yes</span></span>         |<span data-ttu-id="daaac-130">Да*</span><span class="sxs-lookup"><span data-stu-id="daaac-130">Yes*</span></span>         |
|<span data-ttu-id="daaac-131">**Добавление участников**</span><span class="sxs-lookup"><span data-stu-id="daaac-131">**Add members**</span></span>      |<span data-ttu-id="daaac-132">Да**</span><span class="sxs-lookup"><span data-stu-id="daaac-132">Yes</span></span>         |<span data-ttu-id="daaac-133">Нет</span><span class="sxs-lookup"><span data-stu-id="daaac-133">No</span></span>         |
|<span data-ttu-id="daaac-134">**Добавление вкладок**</span><span class="sxs-lookup"><span data-stu-id="daaac-134">**Add tabs**</span></span>      |<span data-ttu-id="daaac-135">Да</span><span class="sxs-lookup"><span data-stu-id="daaac-135">Yes</span></span>         |<span data-ttu-id="daaac-136">Да*</span><span class="sxs-lookup"><span data-stu-id="daaac-136">Yes*</span></span>         |
|<span data-ttu-id="daaac-137">**Добавление соединителей**</span><span class="sxs-lookup"><span data-stu-id="daaac-137">**Add connectors**</span></span>      |<span data-ttu-id="daaac-138">Да</span><span class="sxs-lookup"><span data-stu-id="daaac-138">Yes</span></span>         |<span data-ttu-id="daaac-139">Да*</span><span class="sxs-lookup"><span data-stu-id="daaac-139">Yes*</span></span>         |
|<span data-ttu-id="daaac-140">**Добавление ботов**</span><span class="sxs-lookup"><span data-stu-id="daaac-140">**Add bots**</span></span>      |<span data-ttu-id="daaac-141">Да</span><span class="sxs-lookup"><span data-stu-id="daaac-141">Yes</span></span>         |<span data-ttu-id="daaac-142">Да*</span><span class="sxs-lookup"><span data-stu-id="daaac-142">Yes*</span></span>         |
<span data-ttu-id="daaac-143">\* Эти функции могут быть отключены владельцем на уровне команды, в случае чего они будут недоступны участникам.</span><span class="sxs-lookup"><span data-stu-id="daaac-143">\* These items can be turned off by an owner at a team level, in which case members would not have access to that.</span></span>

<span data-ttu-id="daaac-144">\*\*Добавив участника в команду, владелец также может повысить его до владельца.</span><span class="sxs-lookup"><span data-stu-id="daaac-144">\*\*After adding a member to a team, an Owner can also promote a Member to Owner status.</span></span> <span data-ttu-id="daaac-145">Кроме того, владелец может понизить себя до участника.</span><span class="sxs-lookup"><span data-stu-id="daaac-145">It is also possible for an Owner to demote their own status to a Member.</span></span>

| | |
|---------|---------|
|![](media/Assign_roles_and_permissions_in_Microsoft_Teams_image1.png) <br></br><span data-ttu-id="daaac-146">Примечание.</span><span class="sxs-lookup"><span data-stu-id="daaac-146">Note:</span></span>     |<span data-ttu-id="daaac-147">Владельцы могут назначать других участников владельцами с помощью параметра "Показать команды".</span><span class="sxs-lookup"><span data-stu-id="daaac-147">Owners can make other members owners in the View teams option.</span></span> <span data-ttu-id="daaac-148">Команда может иметь до 10 владельцев.</span><span class="sxs-lookup"><span data-stu-id="daaac-148">A team can have up to 10 owners.</span></span>         |

<a name="permissions-to-create-teams"></a><span data-ttu-id="daaac-149">Разрешения на создание команд</span><span class="sxs-lookup"><span data-stu-id="daaac-149">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="daaac-150">По умолчанию все пользователи с почтовым ящиком в Exchange Online обладают правом на создание групп Office 365, а значит, и команды в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="daaac-150">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams.</span></span> <span data-ttu-id="daaac-151">Вы можете более жестко регулировать или запретить создание команд и групп Office 365, делегировав права на создание и управление некоторому кругу пользователей.</span><span class="sxs-lookup"><span data-stu-id="daaac-151">You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span>

<span data-ttu-id="daaac-152">Если вашу организацию интересует именно этот вариант, ознакомьтесь с приведенными ниже инструкциями.</span><span class="sxs-lookup"><span data-stu-id="daaac-152">If your organization is interested in doing this, the instructions below outlines the tasks required to do so.</span></span>

1.  <span data-ttu-id="daaac-153">Выберите или создайте группу безопасности, пользователям которой будут делегироваться разрешения на создание групп Office 365.</span><span class="sxs-lookup"><span data-stu-id="daaac-153">Identify or create a security group (SG) of users who will have delegated permissions to create Office 365 groups.</span></span>

    <span data-ttu-id="daaac-154">а.</span><span class="sxs-lookup"><span data-stu-id="daaac-154">A</span></span>  <span data-ttu-id="daaac-155">**Действие:** настройте группу безопасности в Office 365, куда можно добавить пользователей, способных создавать группы Office 365.</span><span class="sxs-lookup"><span data-stu-id="daaac-155">**Action:** Set up a security group in Office 365 so you can add your users who can create Office 365 groups.</span></span>

    <span data-ttu-id="daaac-156">б.</span><span class="sxs-lookup"><span data-stu-id="daaac-156">B</span></span>  <span data-ttu-id="daaac-157">Дополнительные сведения см. в статье [Создание, изменение или удаление группы безопасности в Центре администрирования Office 365](https://support.office.com/article/Create-edit-or-delete-a-security-group-in-the-Office-365-admin-center-55c96b32-e086-4c9e-948b-a018b44510cb).</span><span class="sxs-lookup"><span data-stu-id="daaac-157">For more information, see [Create, edit, or delete a security group in the Office 365 admin center](https://support.office.com/article/Create-edit-or-delete-a-security-group-in-the-Office-365-admin-center-55c96b32-e086-4c9e-948b-a018b44510cb).</span></span>

2.  <span data-ttu-id="daaac-158">Реализуйте управление правами на создание групп в рамках всей организации.</span><span class="sxs-lookup"><span data-stu-id="daaac-158">Verify that the company-wide control for users to create groups is enabled.</span></span>

    <span data-ttu-id="daaac-159">а.</span><span class="sxs-lookup"><span data-stu-id="daaac-159">A</span></span>  <span data-ttu-id="daaac-160">**Действие:** запустите приведенный ниже сценарий PowerShell и убедитесь, что для параметра UsersPermissiontoCreateGroupsEnabled задано значение **True.**</span><span class="sxs-lookup"><span data-stu-id="daaac-160">**Action:** Run the following PowerShell script and verify UsersPermissiontoCreateGroupsEnabled parameter is set to **True.**</span></span>

    <span data-ttu-id="daaac-161">Connect-MsolService</span><span class="sxs-lookup"><span data-stu-id="daaac-161">Connect-MsolService</span></span>

    <span data-ttu-id="daaac-162">Get-MsolCompanyInformation</span><span class="sxs-lookup"><span data-stu-id="daaac-162">Get-MsolCompanyInformation</span></span>

    <span data-ttu-id="daaac-163">б.</span><span class="sxs-lookup"><span data-stu-id="daaac-163">B</span></span>  <span data-ttu-id="daaac-164">Если задано другое значение, запустите командлет Set-MsolCompanySettings**, чтобы установить значение True**.</span><span class="sxs-lookup"><span data-stu-id="daaac-164">If this is not true, run the Set-MsolCompanySettings  cmdlet **to set it to True**.</span></span>
<span data-ttu-id="daaac-165">Set-MsolCompanySettings -UsersPermissionToCreateGroupsEnabled $True</span><span class="sxs-lookup"><span data-stu-id="daaac-165">Set-MsolCompanySettings -UsersPermissionToCreateGroupsEnabled $True</span></span>

    <span data-ttu-id="daaac-166">в.</span><span class="sxs-lookup"><span data-stu-id="daaac-166">C</span></span> <span data-ttu-id="daaac-167">Дополнительные сведения см. в статье: [Управление созданием групп Office 365](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-001&ad=US#checkclevelsettings).</span><span class="sxs-lookup"><span data-stu-id="daaac-167">For more information, see: [Manage Office 365 Group Creation](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-001&ad=US#checkclevelsettings).</span></span>

3.  <span data-ttu-id="daaac-168">Настройте параметры групп Office 365, чтобы предоставить права на создание групп только указанной группе безопасности.</span><span class="sxs-lookup"><span data-stu-id="daaac-168">Configure Office 365 Group settings to allow only identified security group has permissions to create groups</span></span>

    <span data-ttu-id="daaac-169">а.</span><span class="sxs-lookup"><span data-stu-id="daaac-169">A</span></span>  <span data-ttu-id="daaac-170">**Действие:** создайте объект параметров, содержащий параметры конфигурации для группы, которой будут назначены делегированные разрешения на создание групп.</span><span class="sxs-lookup"><span data-stu-id="daaac-170">**Action:** Create a group settings object that contains the configuration settings of the group that will be assigned delegated permissions to create groups.</span></span> 

    <span data-ttu-id="daaac-171">Connect-AzureAD</span><span class="sxs-lookup"><span data-stu-id="daaac-171">Connect-AzureAD</span></span>

    <span data-ttu-id="daaac-172">$Template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b</span><span class="sxs-lookup"><span data-stu-id="daaac-172">$Template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b</span></span>

    <span data-ttu-id="daaac-173">$Setting = $template.CreateDirectorySetting()</span><span class="sxs-lookup"><span data-stu-id="daaac-173">$Setting = $template.CreateDirectorySetting()</span></span>

    <span data-ttu-id="daaac-174">$setting["EnableGroupCreation"] = "false"</span><span class="sxs-lookup"><span data-stu-id="daaac-174">$setting["EnableGroupCreation"] = "false"</span></span>

    <span data-ttu-id="daaac-175">$setting["GroupCreationAllowedGroupId"] = "&lt;ИД объекта для группы, которой разрешено создавать группы>"</span><span class="sxs-lookup"><span data-stu-id="daaac-175">$setting["GroupCreationAllowedGroupId"] = "&lt;ObjectId of Group Allowed to Create Groups>"</span></span>

    <span data-ttu-id="daaac-176">New-AzureADDirectorySetting -DirectorySetting $settings</span><span class="sxs-lookup"><span data-stu-id="daaac-176">New-AzureADDirectorySetting -DirectorySetting $settings</span></span>

    <span data-ttu-id="daaac-177">б.</span><span class="sxs-lookup"><span data-stu-id="daaac-177">B</span></span> <span data-ttu-id="daaac-178">Дополнительные сведения см. в статье: [Управление созданием групп Office 365](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-US&ad=US#step3)</span><span class="sxs-lookup"><span data-stu-id="daaac-178">For more information, see: [Manage Office 365 Group Creation](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-US&ad=US#step3)</span></span>


||||
|---------|---------|---------|
| ![](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="daaac-179">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="daaac-179">Policy Decision Point</span></span>         |<span data-ttu-id="daaac-180">Смогут ли все пользователи Microsoft Teams создавать команды (рекомендуется)?</span><span class="sxs-lookup"><span data-stu-id="daaac-180">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="daaac-181">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="daaac-181">Next Steps</span></span>         |<span data-ttu-id="daaac-182">Измените разрешения по умолчанию для пользователей, которые могут создавать группы Office 365, если хотите ограничить круг лиц, способных создавать команды.</span><span class="sxs-lookup"><span data-stu-id="daaac-182">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |
