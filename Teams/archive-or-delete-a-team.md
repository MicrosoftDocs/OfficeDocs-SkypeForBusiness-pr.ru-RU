---
title: Архивировать или удалять команды в Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: В этой статье вы узнаете, как архивировать или окончательно удалять группы в Microsoft Teams.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 97cce8577c2d3c23e097f5e3bf5d819d51a16b10
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856368"
---
# <a name="archive-or-delete-a-team-in-microsoft-teams"></a><span data-ttu-id="f273b-103">Архивировать или удалять команды в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f273b-103">Archive or delete a team in Microsoft Teams</span></span>

<span data-ttu-id="f273b-104">Со временем команда, созданная в Microsoft Teams, может перестать использоваться, или вы захотите заархивировать или удалить команду в конце проекта.</span><span class="sxs-lookup"><span data-stu-id="f273b-104">Over time, a team created in Microsoft Teams might fall out of use or you might want to archive or delete a team at the end of a project.</span></span> <span data-ttu-id="f273b-105">Если вы являетесь администратором Microsoft Teams, выполните действия, описанные в этой статье, чтобы заархивировать или удалить группу, которая больше не нужна.</span><span class="sxs-lookup"><span data-stu-id="f273b-105">If you're a Microsoft Teams admin, follow the steps in this article to archive or delete a team that's no longer needed.</span></span>

<span data-ttu-id="f273b-106">Когда вы архивируете команду, вся деятельность для этой команды прекращается.</span><span class="sxs-lookup"><span data-stu-id="f273b-106">When you archive a team, all activity for that team ceases.</span></span> <span data-ttu-id="f273b-107">Архивирование команды также архивирует частные каналы в команде и связанные с ними семейства сайтов.</span><span class="sxs-lookup"><span data-stu-id="f273b-107">Archiving a team also archives private channels in the team and their associated site collections.</span></span>  <span data-ttu-id="f273b-108">Однако вы по-прежнему можете добавлять или удалять участников и обновлять роли, а также просматривать все действия группы в стандартных и закрытых каналах, файлах и чатах.</span><span class="sxs-lookup"><span data-stu-id="f273b-108">However, you can still add or remove members and update roles and you can still view all the team activity in standard and private channels, files, and chats.</span></span>

<span data-ttu-id="f273b-109">При удалении команды также удаляется групповая активность в стандартных и частных каналах (и связанных семействах сайтов), файлах и чатах.</span><span class="sxs-lookup"><span data-stu-id="f273b-109">When you delete a team, team activity in standard and private channels (and associated site collections), files, and chats is also deleted.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f273b-110">Архивные группы можно повторно активировать, но вы не можете напрямую восстановить удаленную команду.</span><span class="sxs-lookup"><span data-stu-id="f273b-110">Archived teams can be reactivated, but you can’t directly restore a team that has been deleted.</span></span> <span data-ttu-id="f273b-111">Сначала рассмотрите возможность архивирования команды и отложите удаление до тех пор, пока не убедитесь, что команда вам больше не нужна.</span><span class="sxs-lookup"><span data-stu-id="f273b-111">Consider archiving the team first, and postpone the deletion until you're sure that you no longer need the team.</span></span>

## <a name="archive-a-team"></a><span data-ttu-id="f273b-112">Архивация группы</span><span class="sxs-lookup"><span data-stu-id="f273b-112">Archive a team</span></span>

<span data-ttu-id="f273b-113">Выполните следующие шаги, чтобы заархивировать команду.</span><span class="sxs-lookup"><span data-stu-id="f273b-113">Follow these steps to archive a team.</span></span> <span data-ttu-id="f273b-114">Вы должны быть администратором службы Teams, чтобы вносить эти изменения.</span><span class="sxs-lookup"><span data-stu-id="f273b-114">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="f273b-115">Сведения о получении ролей и разрешений администратора см. в статье [Управление Teams с помощью ролей администратора Teams](./using-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="f273b-115">See [Use Teams administrator roles to manage Teams](./using-admin-roles.md) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="f273b-116">В Центре администрирования **выберите** Teams .</span><span class="sxs-lookup"><span data-stu-id="f273b-116">In the admin center, select **Teams**.</span></span>
2. <span data-ttu-id="f273b-117">Выберите команду, нажав на название команды.</span><span class="sxs-lookup"><span data-stu-id="f273b-117">Select a team by clicking the team name.</span></span>
3. <span data-ttu-id="f273b-118">Выберите **Архивировать**.</span><span class="sxs-lookup"><span data-stu-id="f273b-118">Select **Archive**.</span></span> <span data-ttu-id="f273b-119">Появится следующее сообщение.</span><span class="sxs-lookup"><span data-stu-id="f273b-119">The following message will appear.</span></span>

    ![Скриншот сообщения архива команд](media/teams-archive-message.png)

4. <span data-ttu-id="f273b-121">Чтобы запретить редактирование контента на сайте SharePoint и вкладки Вики, связанных с командой, выберите сделать сайт SharePoint только для чтения **для участников группы**.</span><span class="sxs-lookup"><span data-stu-id="f273b-121">To prevent people from editing the content in the SharePoint site and Wiki tab associated with the team, select **Make the SharePoint site read-only for team members**.</span></span> <span data-ttu-id="f273b-122">(Teams владельцы по-прежнему смогут редактировать это содержимое.)</span><span class="sxs-lookup"><span data-stu-id="f273b-122">(Teams owners will still be able to edit this content.)</span></span>
5. <span data-ttu-id="f273b-123">Выберите **Архив**, чтобы архивировать команду.</span><span class="sxs-lookup"><span data-stu-id="f273b-123">Select **Archive** to archive the team.</span></span> <span data-ttu-id="f273b-124">Статус команды изменится на **Архивирован**.</span><span class="sxs-lookup"><span data-stu-id="f273b-124">The team’s status will change to **Archived**.</span></span>

## <a name="make-an-archived-team-active"></a><span data-ttu-id="f273b-125">Сделайте архивную команду активной</span><span class="sxs-lookup"><span data-stu-id="f273b-125">Make an archived team active</span></span>

<span data-ttu-id="f273b-126">Выполните следующие действия, чтобы снова активировать архивную команду.</span><span class="sxs-lookup"><span data-stu-id="f273b-126">Follow these steps to make an archived team active again.</span></span>

1. <span data-ttu-id="f273b-127">В Центре администрирования **выберите** Teams .</span><span class="sxs-lookup"><span data-stu-id="f273b-127">In the admin center, select **Teams**.</span></span>
2. <span data-ttu-id="f273b-128">Выберите команду, нажав на название команды.</span><span class="sxs-lookup"><span data-stu-id="f273b-128">Select a team by clicking the team name.</span></span>
3. <span data-ttu-id="f273b-129">Выберите **Разархивировать**.</span><span class="sxs-lookup"><span data-stu-id="f273b-129">Select **Unarchive**.</span></span> <span data-ttu-id="f273b-130">Статус команды изменится на **Активный**.</span><span class="sxs-lookup"><span data-stu-id="f273b-130">The team’s status will change to **Active**.</span></span>

## <a name="delete-a-team"></a><span data-ttu-id="f273b-131">Удаление команды</span><span class="sxs-lookup"><span data-stu-id="f273b-131">Delete a team</span></span>

<span data-ttu-id="f273b-132">Если в будущем команда не потребуется, вы можете удалить ее, а не архивировать.</span><span class="sxs-lookup"><span data-stu-id="f273b-132">If the team will not be required in the future, then you can delete it rather than archiving it.</span></span> <span data-ttu-id="f273b-133">Выполните следующие действия, чтобы удалить команду.</span><span class="sxs-lookup"><span data-stu-id="f273b-133">Follow these steps to delete a team.</span></span>

1.  <span data-ttu-id="f273b-134">В Центре администрирования **выберите** Teams .</span><span class="sxs-lookup"><span data-stu-id="f273b-134">In the admin center, select **Teams**.</span></span>
2.  <span data-ttu-id="f273b-135">Выберите команду, нажав на название команды.</span><span class="sxs-lookup"><span data-stu-id="f273b-135">Select a team by clicking the team name.</span></span>
3.  <span data-ttu-id="f273b-136">Выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f273b-136">Select **Delete**.</span></span> <span data-ttu-id="f273b-137">Появится подтверждающее сообщение.</span><span class="sxs-lookup"><span data-stu-id="f273b-137">A confirmation message will appear.</span></span>
4.  <span data-ttu-id="f273b-138">Выберите **Удалить**, чтобы окончательно удалить команду.</span><span class="sxs-lookup"><span data-stu-id="f273b-138">Select **Delete** to permanently delete the team.</span></span>

## <a name="restore-a-deleted-team"></a><span data-ttu-id="f273b-139">Восстановить удаленную команду</span><span class="sxs-lookup"><span data-stu-id="f273b-139">Restore a deleted team</span></span>

<span data-ttu-id="f273b-140">Выполните эти действия, чтобы восстановить удаленную команду, Microsoft 365 группу, связанную с ней.</span><span class="sxs-lookup"><span data-stu-id="f273b-140">Follow these steps to restore a deleted team by restoring the Microsoft 365 group that's associated with the team.</span></span> <span data-ttu-id="f273b-141">При восстановлении Microsoft 365 группы восстанавливается содержимое группы, включая вкладки, стандартные каналы, частные каналы и связанные с ними коллекции веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="f273b-141">Restoring the Microsoft 365 group for a team restores team content, including tabs, standard channels, and private channels and their associated site collections.</span></span>

<span data-ttu-id="f273b-142">По умолчанию удаленная группа Microsoft 365 сохраняется в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="f273b-142">By default, a deleted Microsoft 365 group is retained for 30 days.</span></span> <span data-ttu-id="f273b-143">Этот 30-дневный период называется «мягким удалением», потому что вы можете восстановить группу.</span><span class="sxs-lookup"><span data-stu-id="f273b-143">This 30-day period is called "soft-delete" because you can restore the group.</span></span> <span data-ttu-id="f273b-144">Дополнительные данные см. [в этой теме.](/microsoft-365/admin/create-groups/restore-deleted-group)</span><span class="sxs-lookup"><span data-stu-id="f273b-144">To learn more, see [Restore a deleted Group](/microsoft-365/admin/create-groups/restore-deleted-group).</span></span>

### <a name="install-the-azureadpreview-module"></a><span data-ttu-id="f273b-145">Установите модуль AzureADPreview</span><span class="sxs-lookup"><span data-stu-id="f273b-145">Install the AzureADPreview module</span></span>

1. <span data-ttu-id="f273b-146">Откройте Windows PowerShell от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="f273b-146">Open Windows PowerShell as an admin.</span></span>
2. <span data-ttu-id="f273b-147">Если у вас установлена более ранняя версия модуля AzureADPreview или установлен модуль AzureAD, удалите его, выполнив одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="f273b-147">If you have an earlier version of the AzureADPreview module installed or the AzureAD module installed, uninstall it by running one of the following:</span></span>

    ```PowerShell
    Uninstall-Module AzureADPreview
    ```

    ```PowerShell
    Uninstall-Module AzureAD
    ```
3. <span data-ttu-id="f273b-148">Установите последнюю версию модуля AzureADPreview, выполнив следующее:</span><span class="sxs-lookup"><span data-stu-id="f273b-148">Install the latest version of the AzureADPreview module by running the following:</span></span>

    ```PowerShell
    Install-Module AzureADPreview
    ```

### <a name="restore-the-deleted-microsoft-365-group"></a><span data-ttu-id="f273b-149">Восстановление удаленной Microsoft 365 группы</span><span class="sxs-lookup"><span data-stu-id="f273b-149">Restore the deleted Microsoft 365 group</span></span>

1. <span data-ttu-id="f273b-150">Подключитесь к Azure AD, выполнив следующее:</span><span class="sxs-lookup"><span data-stu-id="f273b-150">Connect to Azure AD by running the following:</span></span>
    ```PowerShell
    Connect-AzureAD
    ```
    <span data-ttu-id="f273b-151">При появлении запроса войдите в систему, используя свою учетную запись администратора и пароль.</span><span class="sxs-lookup"><span data-stu-id="f273b-151">When you're prompted, sign in using your admin account and password.</span></span>  
2. <span data-ttu-id="f273b-152">Чтобы отобразить список всех неявных Microsoft 365, которые по-прежнему находятся в течение 30-дневного периода хранения, запустите следующее:</span><span class="sxs-lookup"><span data-stu-id="f273b-152">Run the following to display a list of all soft-deleted Microsoft 365 groups that are still within the 30-day retention period.</span></span> <span data-ttu-id="f273b-153">Используйте параметр -**-All $True**, если у вас много групп.</span><span class="sxs-lookup"><span data-stu-id="f273b-153">Use the **-All $True** parameter if you have a lot of groups.</span></span>
    ```PowerShell
    Get-AzureADMSDeletedGroup
    ```
3. <span data-ttu-id="f273b-154">Найдите группу, которую вы хотите восстановить, и запишите Id.</span><span class="sxs-lookup"><span data-stu-id="f273b-154">Find the group that you want to restore, and then make a note of the Id.</span></span>
4. <span data-ttu-id="f273b-155">Выполните следующее, чтобы восстановить группу, где [Id] - идентификатор группы.</span><span class="sxs-lookup"><span data-stu-id="f273b-155">Run the following to restore the group, where [Id] is the group Id.</span></span>
    ```PowerShell
    Restore-AzureADMSDeletedDirectoryObject -Id [Id]
    ```
5.  <span data-ttu-id="f273b-156">Выполните следующее, чтобы убедиться, что группа была успешно восстановлена, где [Id] - идентификатор группы.</span><span class="sxs-lookup"><span data-stu-id="f273b-156">Run the following to verify the group was successfully restored, where [Id] is the group Id.</span></span>
    ```PowerShell
    Get-AzureADGroup -ObjectId [Id]
    ```

    <span data-ttu-id="f273b-157">Процесс восстановления может занять до 24 часов, после чего команда и контент, связанный с командой, включая вкладки и каналы, отображаются в командах.</span><span class="sxs-lookup"><span data-stu-id="f273b-157">It can take up to 24 hours for the restore process to complete, after which the team and content associated with the team, including tabs and channels, is displayed in Teams.</span></span>