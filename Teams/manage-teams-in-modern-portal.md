---
title: Управление командами в Центре администрирования Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: Узнайте, как для просмотра и обновления рабочих групп в центре администрирования группами Майкрософт.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2d2903e65e4ef4876f41d367ce961530020e775c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32202748"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="3f7e4-103">Управление командами в Центре администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3f7e4-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================


## <a name="overview"></a><span data-ttu-id="3f7e4-104">Обзор</span><span class="sxs-lookup"><span data-stu-id="3f7e4-104">Overview</span></span>

<span data-ttu-id="3f7e4-105">Как ИТ-администратор может потребоваться просмотр или обновление с группами, которые были настроены для совместной работы, или вашей организации может потребоваться выполнить исправлению действий, таких как назначение владельцев для ownerless групп.</span><span class="sxs-lookup"><span data-stu-id="3f7e4-105">As an IT admin, you may need to view or update the teams that your organization has set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="3f7e4-106">Для управления группами, используемых в вашей организации с помощью модуля Microsoft команды PowerShell и Центр администрирования группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3f7e4-106">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="3f7e4-107">Для полного администрирования возможностей с помощью эти два набора инструментов следует убедиться в том, что назначен один из следующих ролей:</span><span class="sxs-lookup"><span data-stu-id="3f7e4-107">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="3f7e4-108">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="3f7e4-108">Global Administrator</span></span>
- <span data-ttu-id="3f7e4-109">Администратор служб Teams</span><span class="sxs-lookup"><span data-stu-id="3f7e4-109">Teams Service Administrator</span></span>

<span data-ttu-id="3f7e4-110">Дополнительные сведения о роли администратора в группах в [роли администраторов используйте группами Майкрософт для управления группами](using-admin-roles.md), и можно получить дополнительные сведения об использовании командлеты PowerShell для управления группами в [Справочник командлетов группами Майкрософт](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="3f7e4-110">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>  

<span data-ttu-id="3f7e4-111">В этой статье Обзор средств управления для групп в центре администрирования группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3f7e4-111">This article provides an overview of the management tools for teams in the Microsoft Teams admin center.</span></span>

## <a name="teams-overview-grid"></a><span data-ttu-id="3f7e4-112">Обзор групп сетки</span><span class="sxs-lookup"><span data-stu-id="3f7e4-112">Teams overview grid</span></span>

<span data-ttu-id="3f7e4-113">Средства управления для групп, в разделе узел **группы** в центре администрирования группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3f7e4-113">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="3f7e4-114">(В центре администрирования выберите **команды** > **Управление группами**.) Каждой группы реализуется группы с Office 365, и этот узел содержит сведения о групп, которые были включены группами в организации Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3f7e4-114">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![Обзор групп сетки](media/manage-teams-in-modern-portal-image1.png)  

<span data-ttu-id="3f7e4-116">В сетке отображаются следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="3f7e4-116">The grid displays the following properties:</span></span>

- <span data-ttu-id="3f7e4-117">**Название команды**</span><span class="sxs-lookup"><span data-stu-id="3f7e4-117">**Team name**</span></span>
- <span data-ttu-id="3f7e4-118">**Каналы** - количество все каналы в группе, включая общие канала по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3f7e4-118">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="3f7e4-119">**Пользователи** — количество всего пользователей, включая владельцев, Гости и члены от клиента.</span><span class="sxs-lookup"><span data-stu-id="3f7e4-119">**Users** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="3f7e4-120">**Владельцы** - count владельцев для этой группы.</span><span class="sxs-lookup"><span data-stu-id="3f7e4-120">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="3f7e4-121">**Гости** - count Azure Active Directory B2B гостевых пользователей, которые являются участниками этой группы.</span><span class="sxs-lookup"><span data-stu-id="3f7e4-121">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="3f7e4-122">**Конфиденциальность** - видимости/AccessType группе резервного Office 365.</span><span class="sxs-lookup"><span data-stu-id="3f7e4-122">**Privacy** - the Visibility/AccessType of the backing Office 365 group.</span></span>
- <span data-ttu-id="3f7e4-123">**Состояние** — "архивированы" или активного состояния для данной группы.</span><span class="sxs-lookup"><span data-stu-id="3f7e4-123">**Status** - the Archived or Active status for this team.</span></span>  <span data-ttu-id="3f7e4-124">Дополнительные сведения о архивации группами в [архив или восстановления группы](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span><span class="sxs-lookup"><span data-stu-id="3f7e4-124">Learn more about archiving teams in the [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="3f7e4-125">**GroupID** - уникальный GroupID группе резервного Office 365</span><span class="sxs-lookup"><span data-stu-id="3f7e4-125">**GroupID** - the unique GroupID of the backing Office 365 group</span></span>
- <span data-ttu-id="3f7e4-126">**Классификация** - классификации (если используется в вашей организации), назначенных группе резервного Office 365.</span><span class="sxs-lookup"><span data-stu-id="3f7e4-126">**Classification** - the classification (if used in your organization) assigned to the backing Office 365 group.</span></span>  <span data-ttu-id="3f7e4-127">Дополнительные сведения о классификации на [Создание классификаций для группы Office в вашей организации](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="3f7e4-127">Learn more about classifications at [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="3f7e4-128">**Описание** — описание для группы резервного Office 365</span><span class="sxs-lookup"><span data-stu-id="3f7e4-128">**Description** - the description set for the backing Office 365 group</span></span>

### <a name="search"></a><span data-ttu-id="3f7e4-129">Поиск</span><span class="sxs-lookup"><span data-stu-id="3f7e4-129">Search</span></span>

<span data-ttu-id="3f7e4-130">Поиск в настоящее время поддерживает строка «Начинается с» и выполняет поиск в поле **имя группы** .</span><span class="sxs-lookup"><span data-stu-id="3f7e4-130">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

### <a name="edit"></a><span data-ttu-id="3f7e4-131">Правка</span><span class="sxs-lookup"><span data-stu-id="3f7e4-131">Edit</span></span>

<span data-ttu-id="3f7e4-132">Можно изменить группу и параметры групп, выбор команды из сетки и нажмите кнопку **Изменить** .</span><span class="sxs-lookup"><span data-stu-id="3f7e4-132">You can edit group and team-specific settings by selecting a team from the grid and then selecting the **Edit** button.</span></span>

![Изменение группы](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a><span data-ttu-id="3f7e4-134">Группа профилей</span><span class="sxs-lookup"><span data-stu-id="3f7e4-134">Team profile</span></span>

<span data-ttu-id="3f7e4-135">Вы может перейдите на страницу профиля группы любые группы из сетки Обзор основных групп, щелкнув имя группы.</span><span class="sxs-lookup"><span data-stu-id="3f7e4-135">You can navigate to the team profile page of any team from the main teams overview grid by clicking on the team name.</span></span> <span data-ttu-id="3f7e4-136">Страница профиля группы представлены члены, владельцев и Гости, относящихся к группе (и его резервное O365 группы), а также каналы команды и параметры.</span><span class="sxs-lookup"><span data-stu-id="3f7e4-136">The team profile page shows the members, owners, and guests that belong to the team (and its backing O365 Group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="3f7e4-137">На странице профиля группы можно:</span><span class="sxs-lookup"><span data-stu-id="3f7e4-137">From the team profile page, you can:</span></span>

- <span data-ttu-id="3f7e4-138">Добавление или удаление участников и владельцев.</span><span class="sxs-lookup"><span data-stu-id="3f7e4-138">Add or remove members and owners.</span></span>
- <span data-ttu-id="3f7e4-139">Добавление или удаление каналы (Обратите внимание, что вы не можете удалить общие канала).</span><span class="sxs-lookup"><span data-stu-id="3f7e4-139">Add or remove channels (Note that you cannot remove the General channel).</span></span>
- <span data-ttu-id="3f7e4-140">Обновление группы и параметры группы.</span><span class="sxs-lookup"><span data-stu-id="3f7e4-140">Update team and group settings.</span></span>
 
![Группа профилей](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="3f7e4-142">Внесение изменений в группы</span><span class="sxs-lookup"><span data-stu-id="3f7e4-142">Making changes to teams</span></span>

<span data-ttu-id="3f7e4-143">Можно изменить следующие элементы команды:</span><span class="sxs-lookup"><span data-stu-id="3f7e4-143">You can change the following elements of a team:</span></span>
- <span data-ttu-id="3f7e4-144">**Пользователи в группе** — можно добавлять или удалять участников и повысить или понизить важность следующих узлов владельцев</span><span class="sxs-lookup"><span data-stu-id="3f7e4-144">**Users in the team** - you can add or remove members, and promote or demote owners</span></span>
- <span data-ttu-id="3f7e4-145">**Каналы** - можно добавить новые каналы или удаление существующих каналов.</span><span class="sxs-lookup"><span data-stu-id="3f7e4-145">**Channels** - you can add new channels or remove existing channels.</span></span>  <span data-ttu-id="3f7e4-146">Не удается удалить канал «Общие» по умолчанию и после создания вы может только редактировать имя канала, не описание.</span><span class="sxs-lookup"><span data-stu-id="3f7e4-146">You cannot delete the default "General" channel, and once created you can only edit channel name, not description.</span></span>
- <span data-ttu-id="3f7e4-147">**Название команды**</span><span class="sxs-lookup"><span data-stu-id="3f7e4-147">**Team name**</span></span>
- <span data-ttu-id="3f7e4-148">**Описание группы**</span><span class="sxs-lookup"><span data-stu-id="3f7e4-148">**Team description**</span></span>
- <span data-ttu-id="3f7e4-149">**Группа конфиденциальности** - public или private</span><span class="sxs-lookup"><span data-stu-id="3f7e4-149">**Team privacy** - public or private</span></span>
- <span data-ttu-id="3f7e4-150">**Группа классификации** - резервные с классификации группы Office 365</span><span class="sxs-lookup"><span data-stu-id="3f7e4-150">**Team classification** - backed by your Office 365 group classifications</span></span>
- <span data-ttu-id="3f7e4-151">**Параметры члена группы** — параметры элемента выберите группы</span><span class="sxs-lookup"><span data-stu-id="3f7e4-151">**Team member settings** - select team member settings</span></span>

## <a name="other-supported-changes-to-teams"></a><span data-ttu-id="3f7e4-152">Другие поддерживаемые изменения группы</span><span class="sxs-lookup"><span data-stu-id="3f7e4-152">Other supported changes to teams</span></span>

- <span data-ttu-id="3f7e4-153">**Удаление** - удаление группы — это обратимо удалить из группы и соответствующей группе Office 365.</span><span class="sxs-lookup"><span data-stu-id="3f7e4-153">**Delete** - Deleting a team is a soft-delete of the team and corresponding Office 365 group.</span></span>  <span data-ttu-id="3f7e4-154">Восстановление случайно удаленного командного, следуйте инструкциям в [Восстановить удаленные группы Office 365](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="3f7e4-154">To restore a mistakenly deleted team, follow the instructions at [Restore a deleted Office 365 Group](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span></span>
- <span data-ttu-id="3f7e4-155">**Архив** - архивации команда помещает группа в режиме только для чтения в рамках группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3f7e4-155">**Archive** - Archiving a team puts the team into read-only mode within Microsoft Teams.</span></span>  <span data-ttu-id="3f7e4-156">Как администратора можно архивировать и unarchive команды от имени организации через портал администрирования.</span><span class="sxs-lookup"><span data-stu-id="3f7e4-156">As an admin, you can archive and unarchive teams on behalf of your organization via the admin portal.</span></span>


<span data-ttu-id="3f7e4-157">Записываются изменения, вносимые в группу.</span><span class="sxs-lookup"><span data-stu-id="3f7e4-157">The changes that you make to a team are logged.</span></span> <span data-ttu-id="3f7e4-158">Если выполняется изменение параметров группы (изменение имя, описание, фотографии, конфиденциальности, классификации или участников группы), эти изменения будут использоваться атрибуты вы по конвейеру аудита.</span><span class="sxs-lookup"><span data-stu-id="3f7e4-158">If you are modifying group settings (changing the name, description, photo, privacy, classification, or team members), these changes will be attributed to you through the audit pipeline.</span></span> <span data-ttu-id="3f7e4-159">При выполнении действий параметры, относящиеся к группам изменения отслеживаются и атрибутами в общие канала рабочей группы.</span><span class="sxs-lookup"><span data-stu-id="3f7e4-159">If you are performing actions against Teams-specific settings, your changes will be tracked and attributed to you in the general channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="3f7e4-160">Поиск и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="3f7e4-160">Troubleshooting</span></span>

<span data-ttu-id="3f7e4-161">**Проблема: Групп, пропускаются в сетке обзора группы**</span><span class="sxs-lookup"><span data-stu-id="3f7e4-161">**Issue: Teams missing from the Team Overview Grid**</span></span>

<span data-ttu-id="3f7e4-162">При вводе группами Майкрософт центра администрирования в разделе **группы** ваших команд отсутствуют некоторые из списка в сетке Обзор групп.</span><span class="sxs-lookup"><span data-stu-id="3f7e4-162">When you enter the Microsoft Teams admin center, under the **Teams** option some of your teams are missing from the listing in the Teams Overview Grid.</span></span>

<span data-ttu-id="3f7e4-163">**Причина**: Эта проблема возникает, когда группа был неправильно (или еще не) профилирования в системе, что может привести к отсутствующие свойства для его распознавания.</span><span class="sxs-lookup"><span data-stu-id="3f7e4-163">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="3f7e4-164">**Решение: Вручную задайте свойство правильное значение с помощью Microsoft Graph**</span><span class="sxs-lookup"><span data-stu-id="3f7e4-164">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="3f7e4-165">Замените **{groupid}** в запрос для фактического GroupId интересующую, который можно получить через Exchange Online powershell с помощью командлета **«[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)»** , как атрибут «**ExternalDirectoryObjectId**».</span><span class="sxs-lookup"><span data-stu-id="3f7e4-165">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="3f7e4-166">Access [графическое представление проводника](https://developer.microsoft.com/en-us/graph/graph-explorer)</span><span class="sxs-lookup"><span data-stu-id="3f7e4-166">Access [Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer)</span></span>

2. <span data-ttu-id="3f7e4-167">Войдите в обозревателе график в левом меню</span><span class="sxs-lookup"><span data-stu-id="3f7e4-167">Sign in to Graph Explorer on the left menu</span></span>

3. <span data-ttu-id="3f7e4-168">Изменение в командной строке запроса: > версии 1.0 > ИСПРАВЛЕНИЙhttps://graph.microsoft.com/v1.0/groups/{groupid}</span><span class="sxs-lookup"><span data-stu-id="3f7e4-168">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}</span></span>

4. <span data-ttu-id="3f7e4-169">Добавьте следующее значение в тексте запроса: {«resourceProvisioningOptions»: [«Группа»]}</span><span class="sxs-lookup"><span data-stu-id="3f7e4-169">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}</span></span>

5. <span data-ttu-id="3f7e4-170">Выполните запрос на верхнем правом.</span><span class="sxs-lookup"><span data-stu-id="3f7e4-170">Run the query on the top-right.</span></span>

6. <span data-ttu-id="3f7e4-171">Убедитесь, что группа правильно отображается в центре администрирования группами Майкрософт - Обзор групп</span><span class="sxs-lookup"><span data-stu-id="3f7e4-171">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview</span></span>


## <a name="learn-more"></a><span data-ttu-id="3f7e4-172">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="3f7e4-172">Learn more</span></span>

[<span data-ttu-id="3f7e4-173">Справочник командлетов группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3f7e4-173">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[<span data-ttu-id="3f7e4-174">Роли администратора в группах Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3f7e4-174">Admin roles in Microsoft Teams</span></span>](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

