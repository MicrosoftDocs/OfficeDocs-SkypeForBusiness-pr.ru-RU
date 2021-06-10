---
title: Управление командами в Центре Microsoft Teams администрирования
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: Узнайте, как просматривать и обновлять группы, которые настроены для совместной работы в Microsoft Teams центре администрирования.
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
ms.openlocfilehash: ea81ad854224e08142f9c87725d25176dcc60d44
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237545"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="6a0b8-103">Управление командами в Центре Microsoft Teams администрирования</span><span class="sxs-lookup"><span data-stu-id="6a0b8-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================

## <a name="overview"></a><span data-ttu-id="6a0b8-104">Обзор</span><span class="sxs-lookup"><span data-stu-id="6a0b8-104">Overview</span></span>

<span data-ttu-id="6a0b8-105">В этой статье представлен обзор средств управления для Teams в центре Microsoft Teams администрирования.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-105">This article provides an overview of the management tools for Teams in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="6a0b8-106">Как администратору может потребоваться просмотреть или обновить группы, которые настроены для совместной работы в организации, или выполнить действия по исправлению, например назначить владельцев для команд без владельца.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-106">As an admin, you may need to view or update the teams that your organization set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="6a0b8-107">Вы можете управлять командами, используемыми в организации, с помощью модуля Microsoft Teams PowerShell и Microsoft Teams администрирования.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-107">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="6a0b8-108">Вы можете получить доступ к Центру администрирования в <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="6a0b8-108">You can access the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span> <span data-ttu-id="6a0b8-109">Чтобы использовать эти два средства для полного администрирования, вам должна быть назначена одна из следующих ролей:</span><span class="sxs-lookup"><span data-stu-id="6a0b8-109">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="6a0b8-110">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="6a0b8-110">Global Administrator</span></span>
- <span data-ttu-id="6a0b8-111">Администратор Teams</span><span class="sxs-lookup"><span data-stu-id="6a0b8-111">Teams Administrator</span></span>

<span data-ttu-id="6a0b8-112">Дополнительные информацию о ролях администраторов в Teams см. в справке по использованию ролей администратора Microsoft Teams для управления [Teams](using-admin-roles.md)и о том, как использовать командлеты PowerShell для управления командами, в справочнике по командлетам [Microsoft Teams.](/powershell/teams/?view=teams-ps)</span><span class="sxs-lookup"><span data-stu-id="6a0b8-112">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](/powershell/teams/?view=teams-ps).</span></span>



## <a name="teams-overview-grid"></a><span data-ttu-id="6a0b8-113">Teams обзорной сетки</span><span class="sxs-lookup"><span data-stu-id="6a0b8-113">Teams overview grid</span></span>

<span data-ttu-id="6a0b8-114">Средства управления для команд находятся **в Teams** в центре Microsoft Teams администрирования.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-114">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="6a0b8-115">(В Центре администрирования **выберите** Teams  >  **Управление командами**.) Для каждой группы создается Microsoft 365, и в этом узле можно просмотреть группы, Microsoft Teams в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-115">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by a Microsoft 365 Group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![Снимок экрана: Teams обзорной сетки](media/manage-teams-in-modern-portal-grid.png)  

<span data-ttu-id="6a0b8-117">Сетка отображает следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="6a0b8-117">The grid displays the following properties:</span></span>

- <span data-ttu-id="6a0b8-118">**Название группы**</span><span class="sxs-lookup"><span data-stu-id="6a0b8-118">**Team name**</span></span>
- <span data-ttu-id="6a0b8-119">**Каналы —** это количество всех каналов в команде, включая стандартный общий канал.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-119">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="6a0b8-120">**Участники команды** — общее количество пользователей, включая владельцев, гостей и участников из вашего клиента.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-120">**Team members** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="6a0b8-121">**Владельцы** — количество владельцев для этой команды.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-121">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="6a0b8-122">**Гости —** количество гостевых Azure Active Directory B2B, которые являются членами этой команды.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-122">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="6a0b8-123">**Конфиденциальность:** видимость и Тип Доступа для группы Microsoft 365 доступа.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-123">**Privacy** - the Visibility/AccessType of the backing Microsoft 365 group.</span></span>
- <span data-ttu-id="6a0b8-124">**Состояние** — архив или состояние "Активен" для этой группы.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-124">**Status** - the Archived or Active status for this team.</span></span> <span data-ttu-id="6a0b8-125">Узнайте больше о архивовке команд в [архиве или восстановлении команды.](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)</span><span class="sxs-lookup"><span data-stu-id="6a0b8-125">Learn more about archiving teams in [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="6a0b8-126">**Описание:** описание группы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-126">**Description** - the description of the backing Microsoft 365 group.</span></span>
- <span data-ttu-id="6a0b8-127">**Классификация** — классификация (если она используется в организации), назначенная группе Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-127">**Classification** - the classification (if used in your organization) assigned to the backing Microsoft 365 group.</span></span> <span data-ttu-id="6a0b8-128">Дополнительные информацию о классификациях: Создание классификаций [для Office групп в организации.](/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="6a0b8-128">Learn more about classifications at [Create classifications for Office groups in your organization](/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="6a0b8-129">**GroupID** — уникальный groupID группы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-129">**GroupID** - the unique GroupID of the backing Microsoft 365 group.</span></span>

> [!NOTE]
> <span data-ttu-id="6a0b8-130">Если вы не видите все эти свойства в сетке, щелкните значок **Изменить столбцы.**</span><span class="sxs-lookup"><span data-stu-id="6a0b8-130">If you don't see all these properties in the grid, click the **Edit columns** icon.</span></span> <span data-ttu-id="6a0b8-131">В **области Изменение столбцов** можно включить или отключить столбцы в сетке с помощью выключаев.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-131">In the **Edit columns** pane, you can use the toggles to turn on or turn off columns in the grid.</span></span> <span data-ttu-id="6a0b8-132">По завершению нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-132">When you're finished, click **Apply**.</span></span>

### <a name="add"></a><span data-ttu-id="6a0b8-133">Добавить</span><span class="sxs-lookup"><span data-stu-id="6a0b8-133">Add</span></span>

<span data-ttu-id="6a0b8-134">Чтобы добавить новую команду, нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-134">To add a new team, click **Add**.</span></span> <span data-ttu-id="6a0b8-135">В **области Добавление** новой команды укайте имя и описание группы, укайте, хотите ли вы сделать ее закрытой или открытой, и задайте классификацию.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-135">In the **Add a new team** pane, give the team a name and description, set whether you want to make it a private or public team, and set the classification.</span></span>

> [!NOTE]
> <span data-ttu-id="6a0b8-136">Недавно созданными командами можно управлять прямо в Центре администрирования Teams, в отличие от других клиентов, таких как Outlook.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-136">Newly created teams can be managed right away in the Teams Admin Center, unlike the experience in other clients like, Outlook.</span></span>

### <a name="edit"></a><span data-ttu-id="6a0b8-137">Правка</span><span class="sxs-lookup"><span data-stu-id="6a0b8-137">Edit</span></span>

<span data-ttu-id="6a0b8-138">Чтобы изменить параметры группы и группы, выберите ее, щелкнув слева от имени группы и выбрав **изменить**.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-138">To edit group and team-specific settings, select the team by clicking to the left of the team name, and then select **Edit**.</span></span>

### <a name="archive"></a><span data-ttu-id="6a0b8-139">Архивация</span><span class="sxs-lookup"><span data-stu-id="6a0b8-139">Archive</span></span>

<span data-ttu-id="6a0b8-140">Вы можете архивировать команду.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-140">You can archive a team.</span></span> <span data-ttu-id="6a0b8-141">При архивации команда перенаставляется в режим только для чтения Teams.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-141">Archiving a team puts the team into read-only mode within Teams.</span></span> <span data-ttu-id="6a0b8-142">Как администратор вы можете архивировать и ото архивировать команды от имени своей организации в Центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-142">As an admin, you can archive and un-archive teams on behalf of your organization in the admin center.</span></span> 

### <a name="delete"></a><span data-ttu-id="6a0b8-143">Удалить</span><span class="sxs-lookup"><span data-stu-id="6a0b8-143">Delete</span></span>

<span data-ttu-id="6a0b8-144">Удаление команды — это неявное удаление команды и соответствующей Microsoft 365 группы.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-144">Deleting a team is a soft-delete of the team and corresponding Microsoft 365 group.</span></span> <span data-ttu-id="6a0b8-145">Чтобы восстановить группу, удаленную по ошибке, следуйте инструкциям в оке Восстановление [удаленной группы.](/microsoft-365/admin/create-groups/restore-deleted-group)</span><span class="sxs-lookup"><span data-stu-id="6a0b8-145">To restore a mistakenly deleted team, follow the instructions in [Restore a deleted Group](/microsoft-365/admin/create-groups/restore-deleted-group).</span></span>

### <a name="search"></a><span data-ttu-id="6a0b8-146">Поиск</span><span class="sxs-lookup"><span data-stu-id="6a0b8-146">Search</span></span>

<span data-ttu-id="6a0b8-147">В настоящее время поиск поддерживает строку "Начинается с" и выполняет поиск **в поле Имя** группы.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-147">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

## <a name="team-profile"></a><span data-ttu-id="6a0b8-148">Профиль группы</span><span class="sxs-lookup"><span data-stu-id="6a0b8-148">Team profile</span></span>

<span data-ttu-id="6a0b8-149">Вы можете перейти на страницу профиля любой команды из сетки обзора основных команд, щелкнув ее имя.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-149">You can navigate to the team profile page of any team from the main teams overview grid by clicking  the team name.</span></span> <span data-ttu-id="6a0b8-150">На странице профиля команды показаны участники, владельцы и гости, которые относятся к команде (и ее Microsoft 365 группе), а также каналы и параметры команды.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-150">The team profile page shows the members, owners, and guests that belong to the team (and its backing Microsoft 365 group), as well as the team's channels and settings.</span></span> <span data-ttu-id="6a0b8-151">На странице профиля группы вы можете:</span><span class="sxs-lookup"><span data-stu-id="6a0b8-151">From the team profile page, you can:</span></span>

- <span data-ttu-id="6a0b8-152">Добавление и удаление участников и владельцев.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-152">Add or remove members and owners.</span></span>
- <span data-ttu-id="6a0b8-153">Добавление и удаление каналов (обратите внимание, что удалить канал Общий нельзя).</span><span class="sxs-lookup"><span data-stu-id="6a0b8-153">Add or remove channels (note that you can't remove the General channel).</span></span>
- <span data-ttu-id="6a0b8-154">Изменение параметров группы и группы.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-154">Change team and group settings.</span></span>
 
![Снимок экрана: пример профиля группы](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="6a0b8-156">Внесение изменений в команды</span><span class="sxs-lookup"><span data-stu-id="6a0b8-156">Making changes to teams</span></span>

<span data-ttu-id="6a0b8-157">На странице профиля группы можно изменить следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="6a0b8-157">On the team's profile page, you can change the following elements of a team:</span></span>

- <span data-ttu-id="6a0b8-158">**Участники:** добавление и удаление участников, а также продвижение или понижение владельцев.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-158">**Members** - add or remove members and promote or demote owners.</span></span>
- <span data-ttu-id="6a0b8-159">**Каналы:** добавление новых каналов, изменение и удаление существующих каналов.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-159">**Channels** - add new channels, and edit or remove existing channels.</span></span> <span data-ttu-id="6a0b8-160">Помните, что стандартный канал Общий удалить нельзя.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-160">Remember that you can't delete the default General channel.</span></span>
- <span data-ttu-id="6a0b8-161">**Название группы**</span><span class="sxs-lookup"><span data-stu-id="6a0b8-161">**Team name**</span></span>
- <span data-ttu-id="6a0b8-162">**Описание**</span><span class="sxs-lookup"><span data-stu-id="6a0b8-162">**Description**</span></span>
- <span data-ttu-id="6a0b8-163">**Конфиденциальность—** укайл, является ли группа открытой или закрытой.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-163">**Privacy** - set whether the team is public or private.</span></span>
- <span data-ttu-id="6a0b8-164">**Классификация—** это можно сделать на Microsoft 365 групп.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-164">**Classification** - this is backed by your Microsoft 365 group classifications.</span></span> <span data-ttu-id="6a0b8-165">Выберите **Конфиденциальная,** **Строго конфиденциальная** информация или **Общие**.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-165">Choose **Confidential**, **Highly Confidential**, or **General**.</span></span>
- <span data-ttu-id="6a0b8-166">**Параметры бесед —** настройка того, могут ли участники редактировать и удалять отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-166">**Conversations settings** - set whether members can edit and delete sent messages.</span></span>
- <span data-ttu-id="6a0b8-167">**Параметры каналов—** настройка того, могут ли участники создавать новые каналы и редактировать существующие, а также добавлять, изменять и удалять вкладки, соединители и приложения.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-167">**Channels settings** - set whether members can create new channels and edit existing ones, and add, edit, and remove tabs, connectors, and apps.</span></span>

<span data-ttu-id="6a0b8-168">Изменения, внесенные в команду, регистрируются.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-168">The changes that you make to a team are logged.</span></span> <span data-ttu-id="6a0b8-169">При изменении параметров группы (изменение имени, описания, фотографии, конфиденциальности, классификации или участников группы) изменения связываются с вами через канал аудита.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-169">If you're modifying group settings (changing the name, description, photo, privacy, classification, or team members), the changes are attributed to you through the audit pipeline.</span></span> <span data-ttu-id="6a0b8-170">Если вы выполняете действия в Teams параметров, изменения отслеживаются и связываются с вами в канале Общий команды.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-170">If you're performing actions against Teams-specific settings, your changes are tracked and attributed to you in the General channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="6a0b8-171">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="6a0b8-171">Troubleshooting</span></span>

<span data-ttu-id="6a0b8-172">**Проблема: Teams отсутствует в сетке обзора группы**</span><span class="sxs-lookup"><span data-stu-id="6a0b8-172">**Issue: Teams missing from the Team overview grid**</span></span>

<span data-ttu-id="6a0b8-173">Некоторые из ваших команд отсутствуют в списке команд в Teams обзоре.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-173">Some of your teams are missing from the list of teams in the Teams overview grid.</span></span>

<span data-ttu-id="6a0b8-174">**Причина:** эта проблема возникает, если система неправильно профилирует команду (или нет), из-за чего может не распознаться ее свойство.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-174">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="6a0b8-175">**Разрешение: вручную за установите для свойства правильное значение через MS Graph**</span><span class="sxs-lookup"><span data-stu-id="6a0b8-175">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="6a0b8-176">Замените **{groupid}** в запросе для фактического groupId, который вы можете получить с помощью Exchange Online powershell, на **["Get-UnifiedGroup](/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)" "** в качестве атрибута "**ExternalDirectoryObjectId**" .</span><span class="sxs-lookup"><span data-stu-id="6a0b8-176">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="6a0b8-177">Access [Graph explorer](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="6a0b8-177">Access [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

2. <span data-ttu-id="6a0b8-178">Во Graph проводнике в меню слева.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-178">Sign in to Graph Explorer on the left menu.</span></span>

3. <span data-ttu-id="6a0b8-179">Измените строку запроса на: исправление > 1.0 https://graph.microsoft.com/v1.0/groups/{groupid} >.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-179">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}.</span></span>

4. <span data-ttu-id="6a0b8-180">Добавьте в запрос следующее значение: {"resourceProvisioningOptions": ["Team"]}.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-180">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}.</span></span>

5. <span data-ttu-id="6a0b8-181">Запустите запрос справа вверху.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-181">Run the query on the top-right.</span></span>

6. <span data-ttu-id="6a0b8-182">Подтвердим, что команда правильно отображается в Microsoft Teams центре администрирования — Обзор группы.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-182">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview.</span></span>

## <a name="learn-more"></a><span data-ttu-id="6a0b8-183">Подробнее</span><span class="sxs-lookup"><span data-stu-id="6a0b8-183">Learn more</span></span>

- [<span data-ttu-id="6a0b8-184">Teams ссылки на cmdlet</span><span class="sxs-lookup"><span data-stu-id="6a0b8-184">Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)  
- [<span data-ttu-id="6a0b8-185">Использование Teams администраторов для управления Teams</span><span class="sxs-lookup"><span data-stu-id="6a0b8-185">Use Teams administrator roles to manage Teams</span></span>](using-admin-roles.md)
- [<span data-ttu-id="6a0b8-186">Планирование управления жизненным циклом в Teams</span><span class="sxs-lookup"><span data-stu-id="6a0b8-186">Plan for lifecycle management in Teams</span></span>](plan-teams-lifecycle.md)