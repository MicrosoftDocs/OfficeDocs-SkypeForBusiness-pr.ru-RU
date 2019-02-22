---
title: Управление командами в Центре администрирования Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/14/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: Узнайте, как для просмотра и обновления рабочих групп в центре администрирования группами Майкрософт.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: cf4d312f8fcb7f9ba509359eaaeed415be3e9662
ms.sourcegitcommit: d3c459dc1304db5f5ba78b5e093b5a4fd797c8ec
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2019
ms.locfileid: "30178679"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="d6c6d-103">Управление командами в Центре администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d6c6d-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

## <a name="overview"></a><span data-ttu-id="d6c6d-104">Обзор</span><span class="sxs-lookup"><span data-stu-id="d6c6d-104">Overview</span></span>

<span data-ttu-id="d6c6d-105">Как ИТ-администратор может потребоваться просмотр или обновление с группами, которые были настроены для совместной работы, или вашей организации может потребоваться выполнить исправлению действий, таких как назначение владельцев для ownerless групп.</span><span class="sxs-lookup"><span data-stu-id="d6c6d-105">As an IT admin, you may need to view or update the teams that your organization has set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="d6c6d-106">Для управления группами, используемых в вашей организации с помощью модуля Microsoft команды PowerShell и Центр администрирования группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d6c6d-106">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="d6c6d-107">Для полного администрирования возможностей с помощью эти два набора инструментов следует убедиться в том, что назначен один из следующих ролей:</span><span class="sxs-lookup"><span data-stu-id="d6c6d-107">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="d6c6d-108">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="d6c6d-108">Global Administrator</span></span>
- <span data-ttu-id="d6c6d-109">Администратор служб Teams</span><span class="sxs-lookup"><span data-stu-id="d6c6d-109">Teams Service Administrator</span></span>

<span data-ttu-id="d6c6d-110">Также следует убедиться в том, что учетной записи была назначена лицензия не пробной группы для управления.</span><span class="sxs-lookup"><span data-stu-id="d6c6d-110">You should also make sure that your account has been assigned a non-trial Teams license for management.</span></span> <span data-ttu-id="d6c6d-111">Как часть известная проблема следует убедиться в том, что учетная запись имеет только **один** назначенный роль администратора.</span><span class="sxs-lookup"><span data-stu-id="d6c6d-111">As part of a known issue, you should make sure that your account has only **one** admin role assigned.</span></span>  <span data-ttu-id="d6c6d-112">Дополнительные сведения о роли администратора в группах Майкрософт в [роли администраторов используйте группами Майкрософт для управления группами](using-admin-roles.md), и можно получить дополнительные сведения об использовании командлеты PowerShell для управления группами в [Справочник командлетов группами Майкрософт](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="d6c6d-112">You can learn more about admin roles in Microsoft Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>  

<span data-ttu-id="d6c6d-113">В этой статье Обзор средств управления для групп в центре администрирования группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d6c6d-113">This article provides an overview of the management tools for teams in the Microsoft Teams admin center.</span></span>

## <a name="teams-overview-grid"></a><span data-ttu-id="d6c6d-114">Обзор групп сетки</span><span class="sxs-lookup"><span data-stu-id="d6c6d-114">Teams overview grid</span></span>

<span data-ttu-id="d6c6d-115">Средства управления для групп, в разделе узел **группы** в центре администрирования группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d6c6d-115">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="d6c6d-116">(В центре администрирования выберите **команды** > **Управление группами**.) Каждой группы реализуется группы с Office 365, и этот узел содержит сведения о групп, которые были включены группами в организации Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d6c6d-116">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="d6c6d-117">Мы находятся в процессе backfilling ранее созданные группы, чтобы убедиться, что они будут отображаться в этом представлении.</span><span class="sxs-lookup"><span data-stu-id="d6c6d-117">We are in the process of backfilling previously created Teams to ensure that they will show up in this view.</span></span>

![Обзор групп сетки](media/manage-teams-in-modern-portal-image1.png)  

<span data-ttu-id="d6c6d-119">В сетке отображаются следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="d6c6d-119">The grid displays the following properties:</span></span>

- <span data-ttu-id="d6c6d-120">**Название команды**</span><span class="sxs-lookup"><span data-stu-id="d6c6d-120">**Team name**</span></span>
- <span data-ttu-id="d6c6d-121">**Каналы** - количество все каналы в группе, включая общие канала по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d6c6d-121">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="d6c6d-122">**Пользователи** — количество всего пользователей, включая владельцев, Гости и члены от клиента.</span><span class="sxs-lookup"><span data-stu-id="d6c6d-122">**Users** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="d6c6d-123">**Владельцы** - count владельцев для этой группы.</span><span class="sxs-lookup"><span data-stu-id="d6c6d-123">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="d6c6d-124">**Гости** - count Azure Active Directory B2B гостевых пользователей, которые являются участниками этой группы.</span><span class="sxs-lookup"><span data-stu-id="d6c6d-124">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="d6c6d-125">**Конфиденциальность** - AccessType группе резервного Office 365.</span><span class="sxs-lookup"><span data-stu-id="d6c6d-125">**Privacy** - the AccessType of the backing Office 365 group.</span></span>

### <a name="search"></a><span data-ttu-id="d6c6d-126">Поиск</span><span class="sxs-lookup"><span data-stu-id="d6c6d-126">Search</span></span>

<span data-ttu-id="d6c6d-127">Поиск в настоящее время поддерживает строка «Начинается с» и выполняет поиск в поле **имя группы** .</span><span class="sxs-lookup"><span data-stu-id="d6c6d-127">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

### <a name="edit"></a><span data-ttu-id="d6c6d-128">Правка</span><span class="sxs-lookup"><span data-stu-id="d6c6d-128">Edit</span></span>

<span data-ttu-id="d6c6d-129">Можно изменить группу и параметры групп, выбор команды из сетки и нажмите кнопку **Изменить** .</span><span class="sxs-lookup"><span data-stu-id="d6c6d-129">You can edit group and team-specific settings by selecting a team from the grid and then selecting the **Edit** button.</span></span>

![Изменение группы](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a><span data-ttu-id="d6c6d-131">Группа профилей</span><span class="sxs-lookup"><span data-stu-id="d6c6d-131">Team profile</span></span>

<span data-ttu-id="d6c6d-132">Вы может перейдите на страницу профиля группы любые группы из сетки Обзор основных групп, щелкнув имя группы.</span><span class="sxs-lookup"><span data-stu-id="d6c6d-132">You can navigate to the team profile page of any team from the main teams overview grid by clicking on the team name.</span></span> <span data-ttu-id="d6c6d-133">Страница профиля группы представлены члены, владельцев и Гости, относящихся к группе (и его резервное O365 группы), а также каналы команды и параметры.</span><span class="sxs-lookup"><span data-stu-id="d6c6d-133">The team profile page shows the members, owners, and guests that belong to the team (and its backing O365 Group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="d6c6d-134">На странице профиля группы можно:</span><span class="sxs-lookup"><span data-stu-id="d6c6d-134">From the team profile page, you can:</span></span>

- <span data-ttu-id="d6c6d-135">Добавление или удаление участников и владельцев.</span><span class="sxs-lookup"><span data-stu-id="d6c6d-135">Add or remove members and owners.</span></span>
- <span data-ttu-id="d6c6d-136">Добавление или удаление каналы (Обратите внимание, что вы не можете удалить общие канала).</span><span class="sxs-lookup"><span data-stu-id="d6c6d-136">Add or remove channels (Note that you cannot remove the General channel).</span></span>
- <span data-ttu-id="d6c6d-137">Обновление группы и параметры группы.</span><span class="sxs-lookup"><span data-stu-id="d6c6d-137">Update team and group settings.</span></span>
 
![Группа профилей](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="d6c6d-139">Внесение изменений в группы</span><span class="sxs-lookup"><span data-stu-id="d6c6d-139">Making changes to teams</span></span>

<span data-ttu-id="d6c6d-140">Можно изменить следующие элементы команды:</span><span class="sxs-lookup"><span data-stu-id="d6c6d-140">You can change the following elements of a team:</span></span>
- <span data-ttu-id="d6c6d-141">**Пользователи в группе** — можно добавлять или удалять участников и повысить или понизить важность следующих узлов владельцев</span><span class="sxs-lookup"><span data-stu-id="d6c6d-141">**Users in the team** - you can add or remove members, and promote or demote owners</span></span>
- <span data-ttu-id="d6c6d-142">**Каналы** - можно добавить новые каналы или удаление существующих каналов.</span><span class="sxs-lookup"><span data-stu-id="d6c6d-142">**Channels** - you can add new channels or remove existing channels.</span></span>  <span data-ttu-id="d6c6d-143">Не удается удалить канал «Общие» по умолчанию и после создания вы может только редактировать имя канала, не описание.</span><span class="sxs-lookup"><span data-stu-id="d6c6d-143">You cannot delete the default "General" channel, and once created you can only edit channel name, not description.</span></span>
- <span data-ttu-id="d6c6d-144">**Название команды**</span><span class="sxs-lookup"><span data-stu-id="d6c6d-144">**Team name**</span></span>
- <span data-ttu-id="d6c6d-145">**Описание группы**</span><span class="sxs-lookup"><span data-stu-id="d6c6d-145">**Team description**</span></span>
- <span data-ttu-id="d6c6d-146">**Группа конфиденциальности** - public или private</span><span class="sxs-lookup"><span data-stu-id="d6c6d-146">**Team privacy** - public or private</span></span>
- <span data-ttu-id="d6c6d-147">**Группа классификации** - резервные с классификации группы Office 365</span><span class="sxs-lookup"><span data-stu-id="d6c6d-147">**Team classification** - backed by your Office 365 group classifications</span></span>
- <span data-ttu-id="d6c6d-148">**Параметры члена группы** — параметры элемента выберите группы</span><span class="sxs-lookup"><span data-stu-id="d6c6d-148">**Team member settings** - select team member settings</span></span>


<span data-ttu-id="d6c6d-149">Записываются изменения, вносимые в группу.</span><span class="sxs-lookup"><span data-stu-id="d6c6d-149">The changes that you make to a team are logged.</span></span> <span data-ttu-id="d6c6d-150">Если выполняется изменение параметров группы (изменение имя, описание, фотографии, конфиденциальности, классификации или участников группы), эти изменения будут использоваться атрибуты вы по конвейеру аудита.</span><span class="sxs-lookup"><span data-stu-id="d6c6d-150">If you are modifying group settings (changing the name, description, photo, privacy, classification, or team members), these changes will be attributed to you through the audit pipeline.</span></span> <span data-ttu-id="d6c6d-151">При выполнении действий параметры, относящиеся к группам изменения отслеживаются и атрибутами в общие канала рабочей группы.</span><span class="sxs-lookup"><span data-stu-id="d6c6d-151">If you are performing actions against Teams-specific settings, your changes will be tracked and attributed to you in the general channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="d6c6d-152">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="d6c6d-152">Troubleshooting</span></span>

<span data-ttu-id="d6c6d-153">**Проблема: Групп, пропускаются в сетке обзора группы**</span><span class="sxs-lookup"><span data-stu-id="d6c6d-153">**Issue: Teams missing from the Team Overview Grid**</span></span>

<span data-ttu-id="d6c6d-154">При вводе группами Майкрософт центра администрирования в разделе **группы** ваших команд отсутствуют некоторые из списка в сетке Обзор групп.</span><span class="sxs-lookup"><span data-stu-id="d6c6d-154">When you enter the Microsoft Teams admin center, under the **Teams** option some of your teams are missing from the listing in the Teams Overview Grid.</span></span>

<span data-ttu-id="d6c6d-155">**Причина**: Эта проблема возникает, когда группа был неправильно (или еще не) профилирования в системе, что может привести к отсутствующие свойства для его распознавания.</span><span class="sxs-lookup"><span data-stu-id="d6c6d-155">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="d6c6d-156">**Решение: Вручную задайте свойство правильное значение с помощью Microsoft Graph**</span><span class="sxs-lookup"><span data-stu-id="d6c6d-156">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="d6c6d-157">Замените **{groupid}** в запрос для фактического GroupId интересующую, который можно получить через Exchange Online powershell с помощью командлета **«[Get-UnifiedGroup](https://docs.microsoft.com/en-us/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)»** , как атрибут «**ExternalDirectoryObjectId**».</span><span class="sxs-lookup"><span data-stu-id="d6c6d-157">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/en-us/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="d6c6d-158">Access [графическое представление проводника](https://developer.microsoft.com/en-us/graph/graph-explorer)</span><span class="sxs-lookup"><span data-stu-id="d6c6d-158">Access [Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer)</span></span>

2. <span data-ttu-id="d6c6d-159">Войдите в обозревателе график в левом меню</span><span class="sxs-lookup"><span data-stu-id="d6c6d-159">Sign in to Graph Explorer on the left menu</span></span>

3. <span data-ttu-id="d6c6d-160">Изменение в командной строке запроса: > версии 1.0 > ИСПРАВЛЕНИЙhttps://graph.microsoft.com/v1.0/groups/{groupid}</span><span class="sxs-lookup"><span data-stu-id="d6c6d-160">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}</span></span>

4. <span data-ttu-id="d6c6d-161">Добавьте следующее значение в тексте запроса: {«resourceProvisioningOptions»: [«Группа»]}</span><span class="sxs-lookup"><span data-stu-id="d6c6d-161">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}</span></span>

5. <span data-ttu-id="d6c6d-162">Выполните запрос на верхнем правом.</span><span class="sxs-lookup"><span data-stu-id="d6c6d-162">Run the query on the top-right.</span></span>

6. <span data-ttu-id="d6c6d-163">Убедитесь, что группа правильно отображается в центре администрирования группами Майкрософт - Обзор групп</span><span class="sxs-lookup"><span data-stu-id="d6c6d-163">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview</span></span>


## <a name="learn-more"></a><span data-ttu-id="d6c6d-164">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="d6c6d-164">Learn more</span></span>

[<span data-ttu-id="d6c6d-165">Справочник командлетов группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="d6c6d-165">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[<span data-ttu-id="d6c6d-166">Роли администратора в группах Майкрософт</span><span class="sxs-lookup"><span data-stu-id="d6c6d-166">Admin roles in Microsoft Teams</span></span>](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

