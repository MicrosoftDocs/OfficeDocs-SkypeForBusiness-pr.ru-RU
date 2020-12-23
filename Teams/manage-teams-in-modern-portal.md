---
title: Управление командами в Центре администрирования Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: Узнайте, как просматривать и обновлять группы, настроенные в организации для совместной работы, в Центре администрирования Microsoft Teams.
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
ms.openlocfilehash: c736cf17d263f097e97b32f856bc83cf2fe42a35
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814558"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="549e8-103">Управление командами в Центре администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="549e8-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================

## <a name="overview"></a><span data-ttu-id="549e8-104">Обзор</span><span class="sxs-lookup"><span data-stu-id="549e8-104">Overview</span></span>

<span data-ttu-id="549e8-105">В этой статье представлен обзор средств управления для Teams в Центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="549e8-105">This article provides an overview of the management tools for Teams in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="549e8-106">Администратору может потребоваться просмотреть или обновить группы, настроенные для совместной работы в организации, или выполнить действия по устранению этой ошибки, например назначить владельцев для команд без владельца.</span><span class="sxs-lookup"><span data-stu-id="549e8-106">As an admin, you may need to view or update the teams that your organization set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="549e8-107">Вы можете управлять командами, используемыми в организации, с помощью модуля Microsoft Teams PowerShell и Центра администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="549e8-107">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="549e8-108">Доступ к Центру администрирования можно получить по этой же <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> адресу.</span><span class="sxs-lookup"><span data-stu-id="549e8-108">You can access the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span> <span data-ttu-id="549e8-109">Чтобы использовать эти два инструмента, вам должна быть назначена одна из следующих ролей:</span><span class="sxs-lookup"><span data-stu-id="549e8-109">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="549e8-110">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="549e8-110">Global Administrator</span></span>
- <span data-ttu-id="549e8-111">Администратор служб Teams</span><span class="sxs-lookup"><span data-stu-id="549e8-111">Teams Service Administrator</span></span>

<span data-ttu-id="549e8-112">Вы можете подробнее узнать о ролях администраторов в Teams в справке по использованию ролей администратора [Microsoft Teams,](using-admin-roles.md)а также о том, как использовать командлеты PowerShell для управления командами, в справочнике по командлетам [Microsoft Teams.](https://docs.microsoft.com/powershell/teams/?view=teams-ps)</span><span class="sxs-lookup"><span data-stu-id="549e8-112">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>



## <a name="teams-overview-grid"></a><span data-ttu-id="549e8-113">Сетка обзора Teams</span><span class="sxs-lookup"><span data-stu-id="549e8-113">Teams overview grid</span></span>

<span data-ttu-id="549e8-114">Средства управления для команд находятся на **узле Teams** в Центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="549e8-114">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="549e8-115">(В Центре администрирования выберите **Teams**  >  **Управление командами**.) У каждой группы есть группа Microsoft 365, и этот узел предоставляет представление групп, которые были включены в Microsoft Teams в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="549e8-115">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by a Microsoft 365 Group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![Снимок экрана: сетка обзора Teams](media/manage-teams-in-modern-portal-grid.png)  

<span data-ttu-id="549e8-117">В сетке отображаются следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="549e8-117">The grid displays the following properties:</span></span>

- <span data-ttu-id="549e8-118">**Название команды**</span><span class="sxs-lookup"><span data-stu-id="549e8-118">**Team name**</span></span>
- <span data-ttu-id="549e8-119">**Каналы —** это количество всех каналов в команде, включая стандартный канал "Общий".</span><span class="sxs-lookup"><span data-stu-id="549e8-119">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="549e8-120">**Участники команды** — общее количество пользователей, включая владельцев, гостей и участников из вашего клиента.</span><span class="sxs-lookup"><span data-stu-id="549e8-120">**Team members** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="549e8-121">**Владельцы** — количество владельцев для этой команды.</span><span class="sxs-lookup"><span data-stu-id="549e8-121">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="549e8-122">**Гости —** количество гостевых пользователей Azure Active Directory B2B, которые являются членами этой команды.</span><span class="sxs-lookup"><span data-stu-id="549e8-122">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="549e8-123">**Конфиденциальность** — видимость/AccessType группы Microsoft 365, которая имеет доступ к службе.</span><span class="sxs-lookup"><span data-stu-id="549e8-123">**Privacy** - the Visibility/AccessType of the backing Microsoft 365 group.</span></span>
- <span data-ttu-id="549e8-124">**Состояние** — состояние "Архив" или "Активна" для этой группы.</span><span class="sxs-lookup"><span data-stu-id="549e8-124">**Status** - the Archived or Active status for this team.</span></span> <span data-ttu-id="549e8-125">Узнайте, как архивировать команды в [архиве или восстановить их.](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)</span><span class="sxs-lookup"><span data-stu-id="549e8-125">Learn more about archiving teams in [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="549e8-126">**Описание** — описание группы, которая является backing Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="549e8-126">**Description** - the description of the backing Microsoft 365 group.</span></span>
- <span data-ttu-id="549e8-127">**Классификация** — классификация (если она используется в вашей организации), назначенная группе Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="549e8-127">**Classification** - the classification (if used in your organization) assigned to the backing Microsoft 365 group.</span></span> <span data-ttu-id="549e8-128">Дополнительные информацию о классификациях можно получить на [сайте Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)(Создание классификаций для групп Office в организации).</span><span class="sxs-lookup"><span data-stu-id="549e8-128">Learn more about classifications at [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="549e8-129">**GroupID** — уникальный groupID группы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="549e8-129">**GroupID** - the unique GroupID of the backing Microsoft 365 group.</span></span>

> [!NOTE]
> <span data-ttu-id="549e8-130">Если в сетке нет этих свойств, щелкните значок "Изменить **столбцы".**</span><span class="sxs-lookup"><span data-stu-id="549e8-130">If you don't see all these properties in the grid, click the **Edit columns** icon.</span></span> <span data-ttu-id="549e8-131">В области **"Изменение** столбцов" можно включить или отключить столбцы в сетке с помощью выключает выключать столбцы.</span><span class="sxs-lookup"><span data-stu-id="549e8-131">In the **Edit columns** pane, you can use the toggles to turn on or turn off columns in the grid.</span></span> <span data-ttu-id="549e8-132">Закончив, нажмите кнопку **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="549e8-132">When you're finished, click **Apply**.</span></span>

### <a name="add"></a><span data-ttu-id="549e8-133">Добавить</span><span class="sxs-lookup"><span data-stu-id="549e8-133">Add</span></span>

<span data-ttu-id="549e8-134">Чтобы добавить новую команду, нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="549e8-134">To add a new team, click **Add**.</span></span> <span data-ttu-id="549e8-135">В области **"Добавление** новой команды" ввести имя и описание команды, у установить ее как частную или общенастройную, так и классификацию.</span><span class="sxs-lookup"><span data-stu-id="549e8-135">In the **Add a new team** pane, give the team a name and description, set whether you want to make it a private or public team, and set the classification.</span></span>

> [!NOTE]
> <span data-ttu-id="549e8-136">Новыми командами можно управлять прямо сейчас в Центре администрирования Teams, в отличие от других клиентов, таких как Outlook.</span><span class="sxs-lookup"><span data-stu-id="549e8-136">Newly created teams can be managed right away in the Teams Admin Center, unlike the experience in other clients like, Outlook.</span></span>

### <a name="edit"></a><span data-ttu-id="549e8-137">Правка</span><span class="sxs-lookup"><span data-stu-id="549e8-137">Edit</span></span>

<span data-ttu-id="549e8-138">Чтобы изменить параметры группы или группы, выберите группу, щелкнув слева от ее названия и выбрав команду **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="549e8-138">To edit group and team-specific settings, select the team by clicking to the left of the team name, and then select **Edit**.</span></span>

### <a name="archive"></a><span data-ttu-id="549e8-139">Архивация</span><span class="sxs-lookup"><span data-stu-id="549e8-139">Archive</span></span>

<span data-ttu-id="549e8-140">Вы можете архивировать команду.</span><span class="sxs-lookup"><span data-stu-id="549e8-140">You can archive a team.</span></span> <span data-ttu-id="549e8-141">При архивации команда перенаставляет ее в режим "только для чтения" в Teams.</span><span class="sxs-lookup"><span data-stu-id="549e8-141">Archiving a team puts the team into read-only mode within Teams.</span></span> <span data-ttu-id="549e8-142">Как администратор вы можете архивировать и отвеять команды от имени своей организации в Центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="549e8-142">As an admin, you can archive and un-archive teams on behalf of your organization in the admin center.</span></span> 

### <a name="delete"></a><span data-ttu-id="549e8-143">Удалить</span><span class="sxs-lookup"><span data-stu-id="549e8-143">Delete</span></span>

<span data-ttu-id="549e8-144">Удаление команды — это неявное удаление команды и соответствующей группы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="549e8-144">Deleting a team is a soft-delete of the team and corresponding Microsoft 365 group.</span></span> <span data-ttu-id="549e8-145">Чтобы восстановить группу, удаленную по ошибке, следуйте инструкциям в окно ["Восстановление удаленной группы".](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)</span><span class="sxs-lookup"><span data-stu-id="549e8-145">To restore a mistakenly deleted team, follow the instructions in [Restore a deleted Group](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group).</span></span>

### <a name="search"></a><span data-ttu-id="549e8-146">Поиск</span><span class="sxs-lookup"><span data-stu-id="549e8-146">Search</span></span>

<span data-ttu-id="549e8-147">В настоящее время поиск поддерживает строку "Начинается с" и выполняет поиск в поле **"Название группы".**</span><span class="sxs-lookup"><span data-stu-id="549e8-147">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

## <a name="team-profile"></a><span data-ttu-id="549e8-148">Профиль группы</span><span class="sxs-lookup"><span data-stu-id="549e8-148">Team profile</span></span>

<span data-ttu-id="549e8-149">Чтобы перейти на страницу профиля любой команды, щелкните ее имя в сетке обзора основных команд.</span><span class="sxs-lookup"><span data-stu-id="549e8-149">You can navigate to the team profile page of any team from the main teams overview grid by clicking  the team name.</span></span> <span data-ttu-id="549e8-150">На странице профиля команды показаны участники, владельцы и гости, которые относятся к команде (и ее группе Microsoft 365), а также ее каналы и параметры.</span><span class="sxs-lookup"><span data-stu-id="549e8-150">The team profile page shows the members, owners, and guests that belong to the team (and its backing Microsoft 365 group), as well as the team's channels and settings.</span></span> <span data-ttu-id="549e8-151">На странице профиля группы вы можете:</span><span class="sxs-lookup"><span data-stu-id="549e8-151">From the team profile page, you can:</span></span>

- <span data-ttu-id="549e8-152">Добавляйте и удаляйте участников и владельцев.</span><span class="sxs-lookup"><span data-stu-id="549e8-152">Add or remove members and owners.</span></span>
- <span data-ttu-id="549e8-153">Добавление и удаление каналов (обратите внимание, что удалить канал «Общее» нельзя).</span><span class="sxs-lookup"><span data-stu-id="549e8-153">Add or remove channels (note that you can't remove the General channel).</span></span>
- <span data-ttu-id="549e8-154">Изменение параметров группы и группы.</span><span class="sxs-lookup"><span data-stu-id="549e8-154">Change team and group settings.</span></span>
 
![Снимок экрана: пример профиля группы](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="549e8-156">Внесение изменений в команды</span><span class="sxs-lookup"><span data-stu-id="549e8-156">Making changes to teams</span></span>

<span data-ttu-id="549e8-157">На странице профиля группы можно изменить следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="549e8-157">On the team's profile page, you can change the following elements of a team:</span></span>

- <span data-ttu-id="549e8-158">**Участники** — добавляют или удаляют участников, а также продвигать или понизить владельцев.</span><span class="sxs-lookup"><span data-stu-id="549e8-158">**Members** - add or remove members and promote or demote owners.</span></span>
- <span data-ttu-id="549e8-159">**Каналы :** добавление новых каналов, изменение или удаление существующих каналов.</span><span class="sxs-lookup"><span data-stu-id="549e8-159">**Channels** - add new channels, and edit or remove existing channels.</span></span> <span data-ttu-id="549e8-160">Помните, что стандартный канал "Общий" удалить нельзя.</span><span class="sxs-lookup"><span data-stu-id="549e8-160">Remember that you can't delete the default General channel.</span></span>
- <span data-ttu-id="549e8-161">**Название команды**</span><span class="sxs-lookup"><span data-stu-id="549e8-161">**Team name**</span></span>
- <span data-ttu-id="549e8-162">**Описание**</span><span class="sxs-lookup"><span data-stu-id="549e8-162">**Description**</span></span>
- <span data-ttu-id="549e8-163">**Конфиденциальность** — укаймка группы: открытой или закрытой.</span><span class="sxs-lookup"><span data-stu-id="549e8-163">**Privacy** - set whether the team is public or private.</span></span>
- <span data-ttu-id="549e8-164">**Классификация** — она может быть за счет классификаций групп Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="549e8-164">**Classification** - this is backed by your Microsoft 365 group classifications.</span></span> <span data-ttu-id="549e8-165">Выберите **"Конфиденциально",** **"Строго конфиденциально"** или **"Общие".**</span><span class="sxs-lookup"><span data-stu-id="549e8-165">Choose **Confidential**, **Highly Confidential**, or **General**.</span></span>
- <span data-ttu-id="549e8-166">**Параметры бесед —** настройка того, могут ли участники редактировать и удалять отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="549e8-166">**Conversations settings** - set whether members can edit and delete sent messages.</span></span>
- <span data-ttu-id="549e8-167">**Параметры каналов** — настройка того, смогут ли участники создавать новые каналы и редактировать существующие, а также добавлять, изменять и удалять вкладки, соединители и приложения.</span><span class="sxs-lookup"><span data-stu-id="549e8-167">**Channels settings** - set whether members can create new channels and edit existing ones, and add, edit, and remove tabs, connectors, and apps.</span></span>

<span data-ttu-id="549e8-168">Изменения, внесенные в команду, регистрируются в журнале.</span><span class="sxs-lookup"><span data-stu-id="549e8-168">The changes that you make to a team are logged.</span></span> <span data-ttu-id="549e8-169">Изменения в параметрах группы (изменение имени, описания, фотографии, конфиденциальности, классификации или участников группы) связываются с вами через канал аудита.</span><span class="sxs-lookup"><span data-stu-id="549e8-169">If you're modifying group settings (changing the name, description, photo, privacy, classification, or team members), the changes are attributed to you through the audit pipeline.</span></span> <span data-ttu-id="549e8-170">Если вы выполняете действия с настройками Teams, изменения отслеживаются и привяются к вам в канале "Общее" команды.</span><span class="sxs-lookup"><span data-stu-id="549e8-170">If you're performing actions against Teams-specific settings, your changes are tracked and attributed to you in the General channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="549e8-171">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="549e8-171">Troubleshooting</span></span>

<span data-ttu-id="549e8-172">**Проблема: в сетке обзора группы отсутствуют команды**</span><span class="sxs-lookup"><span data-stu-id="549e8-172">**Issue: Teams missing from the Team overview grid**</span></span>

<span data-ttu-id="549e8-173">Некоторые из ваших команд отсутствуют в списке команд в сетке обзора Teams.</span><span class="sxs-lookup"><span data-stu-id="549e8-173">Some of your teams are missing from the list of teams in the Teams overview grid.</span></span>

<span data-ttu-id="549e8-174">**Причина:** эта проблема возникает, когда система неправильно (или еще) профилировали команду, из-за чего ее может не распознать.</span><span class="sxs-lookup"><span data-stu-id="549e8-174">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="549e8-175">**Разрешение: вручную за set the property to the correct value via MS Graph**</span><span class="sxs-lookup"><span data-stu-id="549e8-175">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="549e8-176">Замените **{groupid}** в запросе для фактического groupId, который вы можете получить через Exchange Online powershell, на cmdlet **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** в качестве атрибута **"ExternalDirectoryObjectId**".</span><span class="sxs-lookup"><span data-stu-id="549e8-176">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="549e8-177">Проводник Access [Graph Explorer.](https://developer.microsoft.com/graph/graph-explorer)</span><span class="sxs-lookup"><span data-stu-id="549e8-177">Access [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

2. <span data-ttu-id="549e8-178">Во sign in to Graph Explorer on the left menu.</span><span class="sxs-lookup"><span data-stu-id="549e8-178">Sign in to Graph Explorer on the left menu.</span></span>

3. <span data-ttu-id="549e8-179">Измените строку запроса на исправление, > 1.0 https://graph.microsoft.com/v1.0/groups/{groupid} >.</span><span class="sxs-lookup"><span data-stu-id="549e8-179">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}.</span></span>

4. <span data-ttu-id="549e8-180">Добавьте в запрос следующее значение: {"resourceProvisioningOptions": ["Группа"]}.</span><span class="sxs-lookup"><span data-stu-id="549e8-180">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}.</span></span>

5. <span data-ttu-id="549e8-181">Выполнить запрос справа вверху.</span><span class="sxs-lookup"><span data-stu-id="549e8-181">Run the query on the top-right.</span></span>

6. <span data-ttu-id="549e8-182">Подтвердим, что команда правильно отображается в Центре администрирования Microsoft Teams — обзор группы.</span><span class="sxs-lookup"><span data-stu-id="549e8-182">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview.</span></span>

## <a name="learn-more"></a><span data-ttu-id="549e8-183">Подробнее</span><span class="sxs-lookup"><span data-stu-id="549e8-183">Learn more</span></span>

- [<span data-ttu-id="549e8-184">Справочник по командлетам Teams</span><span class="sxs-lookup"><span data-stu-id="549e8-184">Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
- [<span data-ttu-id="549e8-185">Использование ролей администратора Teams для управления Teams</span><span class="sxs-lookup"><span data-stu-id="549e8-185">Use Teams administrator roles to manage Teams</span></span>](using-admin-roles.md)
- [<span data-ttu-id="549e8-186">Планирование управления жизненным циклом в Teams</span><span class="sxs-lookup"><span data-stu-id="549e8-186">Plan for lifecycle management in Teams</span></span>](plan-teams-lifecycle.md)
