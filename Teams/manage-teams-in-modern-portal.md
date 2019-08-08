---
title: Управление командами в Центре администрирования Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin
description: Сведения о том, как просматривать и обновлять команды в центре администрирования Microsoft Teams.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f495a9cc5b3bfb1fd270e85b2a1fb17bd5f11e68
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233356"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="c0e51-103">Управление командами в Центре администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c0e51-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================


## <a name="overview"></a><span data-ttu-id="c0e51-104">Обзор</span><span class="sxs-lookup"><span data-stu-id="c0e51-104">Overview</span></span>

<span data-ttu-id="c0e51-105">Администратору ИТ может потребоваться просмотреть или изменить команды, настроенные для совместной работы Организации, или выполнить действия по устранению неполадок, например назначение владельцев для групп без владельца.</span><span class="sxs-lookup"><span data-stu-id="c0e51-105">As an IT admin, you may need to view or update the teams that your organization has set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="c0e51-106">Вы можете управлять командами, используемыми в вашей организации, с помощью обоих модулей Microsoft Teams PowerShell и центра администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c0e51-106">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="c0e51-107">Для обеспечения полного доступа к возможностям администрирования с помощью этих двух наборов инструментов необходимо убедиться в том, что вы назначили одну из следующих ролей:</span><span class="sxs-lookup"><span data-stu-id="c0e51-107">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="c0e51-108">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="c0e51-108">Global Administrator</span></span>
- <span data-ttu-id="c0e51-109">Администратор служб Teams</span><span class="sxs-lookup"><span data-stu-id="c0e51-109">Teams Service Administrator</span></span>

<span data-ttu-id="c0e51-110">Дополнительные сведения о ролях администратора в Teams можно найти в разделе [Использование ролей администратора Microsoft Teams для управления группами](using-admin-roles.md), а также Узнайте больше о том, как использовать командлеты PowerShell для управления группами в справочнике по [командлетам Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="c0e51-110">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>  

<span data-ttu-id="c0e51-111">В этой статье приводятся общие сведения о средствах управления для Teams в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c0e51-111">This article provides an overview of the management tools for teams in the Microsoft Teams admin center.</span></span>

## <a name="teams-overview-grid"></a><span data-ttu-id="c0e51-112">Сетка обзора групп</span><span class="sxs-lookup"><span data-stu-id="c0e51-112">Teams overview grid</span></span>

<span data-ttu-id="c0e51-113">Средства управления для Teams находятся под \*\*\*\* узлом Teams в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c0e51-113">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="c0e51-114">(В центре администрирования выберите **команды** > **Управление группами**.) Каждая команда помещается в группу Office 365, а этот узел предоставляет представление групп, которые были включены в Microsoft Teams в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c0e51-114">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![Снимок экрана: сетка обзора групп](media/manage-teams-in-modern-portal-image1.png)  

<span data-ttu-id="c0e51-116">В сетке отображаются следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="c0e51-116">The grid displays the following properties:</span></span>

- <span data-ttu-id="c0e51-117">**Название команды**</span><span class="sxs-lookup"><span data-stu-id="c0e51-117">**Team name**</span></span>
- <span data-ttu-id="c0e51-118">**Channels (каналы** ) — общее количество всех каналов в группе, включая стандартный канал по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c0e51-118">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="c0e51-119">**Users (пользователи** ) — общее количество пользователей, включая владельцев, гостей и участников из вашего клиента.</span><span class="sxs-lookup"><span data-stu-id="c0e51-119">**Users** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="c0e51-120">**Owners (владельцы** ) — Количество владельцев группы.</span><span class="sxs-lookup"><span data-stu-id="c0e51-120">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="c0e51-121">**Гости** — количество гостевых пользователей Azure Active Directory B2B, которые являются участниками этой команды.</span><span class="sxs-lookup"><span data-stu-id="c0e51-121">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="c0e51-122">**Privacy (конфиденциальность** ) — это акцесстипе и т. д. в резервной группе Office 365.</span><span class="sxs-lookup"><span data-stu-id="c0e51-122">**Privacy** - the Visibility/AccessType of the backing Office 365 group.</span></span>
- <span data-ttu-id="c0e51-123">**Status (состояние** ) — архивированный или активный статус этой команды.</span><span class="sxs-lookup"><span data-stu-id="c0e51-123">**Status** - the Archived or Active status for this team.</span></span>  <span data-ttu-id="c0e51-124">Узнайте больше о том, как архивировать команды в [архиве или восстановите группу](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span><span class="sxs-lookup"><span data-stu-id="c0e51-124">Learn more about archiving teams in the [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="c0e51-125">**GroupId** — уникальный идентификатор группы резервного копирования Office 365</span><span class="sxs-lookup"><span data-stu-id="c0e51-125">**GroupID** - the unique GroupID of the backing Office 365 group</span></span>
- <span data-ttu-id="c0e51-126">**Классификация** — классификация (если она используется в вашей организации), назначенная резервной группе Office 365.</span><span class="sxs-lookup"><span data-stu-id="c0e51-126">**Classification** - the classification (if used in your organization) assigned to the backing Office 365 group.</span></span>  <span data-ttu-id="c0e51-127">Узнайте больше о классификациях на странице [Создание классификаций для групп Office в Организации](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="c0e51-127">Learn more about classifications at [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="c0e51-128">**Описание** — описание, заданное для группы резервного копирования Office 365</span><span class="sxs-lookup"><span data-stu-id="c0e51-128">**Description** - the description set for the backing Office 365 group</span></span>

### <a name="search"></a><span data-ttu-id="c0e51-129">Поиск</span><span class="sxs-lookup"><span data-stu-id="c0e51-129">Search</span></span>

<span data-ttu-id="c0e51-130">В настоящее время Поиск поддерживает строку "начинается с" и выполняет поиск в поле **имя группы** .</span><span class="sxs-lookup"><span data-stu-id="c0e51-130">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

### <a name="edit"></a><span data-ttu-id="c0e51-131">Правка</span><span class="sxs-lookup"><span data-stu-id="c0e51-131">Edit</span></span>

<span data-ttu-id="c0e51-132">Вы можете изменить параметры группы и группы, выбрав команду в сетке и нажав кнопку " **изменить** ".</span><span class="sxs-lookup"><span data-stu-id="c0e51-132">You can edit group and team-specific settings by selecting a team from the grid and then selecting the **Edit** button.</span></span>

![Снимок экрана с параметрами команды "изменить группу"](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a><span data-ttu-id="c0e51-134">Профиль группы</span><span class="sxs-lookup"><span data-stu-id="c0e51-134">Team profile</span></span>

<span data-ttu-id="c0e51-135">Вы можете перейти на страницу профиля группы в любой команде из главной сетки обзора рабочих групп, щелкнув ее имя.</span><span class="sxs-lookup"><span data-stu-id="c0e51-135">You can navigate to the team profile page of any team from the main teams overview grid by clicking on the team name.</span></span> <span data-ttu-id="c0e51-136">На странице "профиль группы" отображаются участники, владельцы и гости, принадлежащие группе (и резервная группа Office 365), а также каналы и параметры команды.</span><span class="sxs-lookup"><span data-stu-id="c0e51-136">The team profile page shows the members, owners, and guests that belong to the team (and its backing O365 Group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="c0e51-137">На странице "профиль группы" можно выполнять указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="c0e51-137">From the team profile page, you can:</span></span>

- <span data-ttu-id="c0e51-138">Добавление и удаление участников и владельцев.</span><span class="sxs-lookup"><span data-stu-id="c0e51-138">Add or remove members and owners.</span></span>
- <span data-ttu-id="c0e51-139">Добавление и удаление каналов (Обратите внимание на то, что вы не можете удалить общий канал).</span><span class="sxs-lookup"><span data-stu-id="c0e51-139">Add or remove channels (Note that you cannot remove the General channel).</span></span>
- <span data-ttu-id="c0e51-140">Обновление параметров группы и группы.</span><span class="sxs-lookup"><span data-stu-id="c0e51-140">Update team and group settings.</span></span>
 
![Снимок экрана, на котором показан пример профиля группы](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="c0e51-142">Внесение изменений в Teams</span><span class="sxs-lookup"><span data-stu-id="c0e51-142">Making changes to teams</span></span>

<span data-ttu-id="c0e51-143">Вы можете изменять следующие элементы команды:</span><span class="sxs-lookup"><span data-stu-id="c0e51-143">You can change the following elements of a team:</span></span>
- <span data-ttu-id="c0e51-144">**Пользователи в группе** — вы можете добавлять и удалять участников, а также повышать и понижать уровень владельцев</span><span class="sxs-lookup"><span data-stu-id="c0e51-144">**Users in the team** - you can add or remove members, and promote or demote owners</span></span>
- <span data-ttu-id="c0e51-145">**Каналы** — вы можете добавлять новые каналы или удалять существующие.</span><span class="sxs-lookup"><span data-stu-id="c0e51-145">**Channels** - you can add new channels or remove existing channels.</span></span>  <span data-ttu-id="c0e51-146">Вы не можете удалить стандартный канал "Общие", а после его создания вы можете изменить только имя канала, а не описание.</span><span class="sxs-lookup"><span data-stu-id="c0e51-146">You cannot delete the default "General" channel, and once created you can only edit channel name, not description.</span></span>
- <span data-ttu-id="c0e51-147">**Название команды**</span><span class="sxs-lookup"><span data-stu-id="c0e51-147">**Team name**</span></span>
- <span data-ttu-id="c0e51-148">**Описание группы**</span><span class="sxs-lookup"><span data-stu-id="c0e51-148">**Team description**</span></span>
- <span data-ttu-id="c0e51-149">**Конфиденциальность группы** : общедоступная или частная</span><span class="sxs-lookup"><span data-stu-id="c0e51-149">**Team privacy** - public or private</span></span>
- <span data-ttu-id="c0e51-150">**Классификация** групп — поддерживается классификацией групп Office 365</span><span class="sxs-lookup"><span data-stu-id="c0e51-150">**Team classification** - backed by your Office 365 group classifications</span></span>
- <span data-ttu-id="c0e51-151">**Параметры участника команды** -выбор параметров участника группы</span><span class="sxs-lookup"><span data-stu-id="c0e51-151">**Team member settings** - select team member settings</span></span>

## <a name="other-supported-changes-to-teams"></a><span data-ttu-id="c0e51-152">Другие поддерживаемые изменения в Teams</span><span class="sxs-lookup"><span data-stu-id="c0e51-152">Other supported changes to teams</span></span>

- <span data-ttu-id="c0e51-153">**Удаление** команды является мягким удалением группы и соответствующей группой Office 365.</span><span class="sxs-lookup"><span data-stu-id="c0e51-153">**Delete** - Deleting a team is a soft-delete of the team and corresponding Office 365 group.</span></span>  <span data-ttu-id="c0e51-154">Чтобы восстановить удаленную группу по ошибочной удаленной команде, следуйте инструкциям в разделе [Восстановление удаленной группы Office 365](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="c0e51-154">To restore a mistakenly deleted team, follow the instructions at [Restore a deleted Office 365 Group](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span></span>
- <span data-ttu-id="c0e51-155">**Архивация** : в Microsoft Teams группа переводится в режим "только для чтения".</span><span class="sxs-lookup"><span data-stu-id="c0e51-155">**Archive** - Archiving a team puts the team into read-only mode within Microsoft Teams.</span></span>  <span data-ttu-id="c0e51-156">Администраторы могут архивировать и отменять архивацию групп от имени вашей организации с помощью портала администрирования.</span><span class="sxs-lookup"><span data-stu-id="c0e51-156">As an admin, you can archive and unarchive teams on behalf of your organization via the admin portal.</span></span>


<span data-ttu-id="c0e51-157">Изменения, внесенные в команду, регистрируются в журнале.</span><span class="sxs-lookup"><span data-stu-id="c0e51-157">The changes that you make to a team are logged.</span></span> <span data-ttu-id="c0e51-158">Если вы изменяете параметры группы (изменяя имя, описание, фотографию, конфиденциальность, классификацию или участников группы), эти изменения будут назначены вам через конвейер аудита.</span><span class="sxs-lookup"><span data-stu-id="c0e51-158">If you are modifying group settings (changing the name, description, photo, privacy, classification, or team members), these changes will be attributed to you through the audit pipeline.</span></span> <span data-ttu-id="c0e51-159">Если вы выполняете действия с параметрами, специфическими для Teams, ваши изменения будут отслеживаться и применяться к ним в общем канале команды.</span><span class="sxs-lookup"><span data-stu-id="c0e51-159">If you are performing actions against Teams-specific settings, your changes will be tracked and attributed to you in the general channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="c0e51-160">Поиск и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="c0e51-160">Troubleshooting</span></span>

<span data-ttu-id="c0e51-161">**Вопрос: в сетке обзора команды отсутствует Teams**</span><span class="sxs-lookup"><span data-stu-id="c0e51-161">**Issue: Teams missing from the Team Overview Grid**</span></span>

<span data-ttu-id="c0e51-162">При входе в центр администрирования Microsoft Teams в разделе Teams ( **команды** ) некоторые из ваших команд отсутствуют в таблице Обзор групп.</span><span class="sxs-lookup"><span data-stu-id="c0e51-162">When you enter the Microsoft Teams admin center, under the **Teams** option some of your teams are missing from the listing in the Teams Overview Grid.</span></span>

<span data-ttu-id="c0e51-163">**Причина**: Эта проблема возникает, если группа была неправильно (или еще не настроена), которая может привести к распознаванию отсутствующего свойства.</span><span class="sxs-lookup"><span data-stu-id="c0e51-163">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="c0e51-164">**Разрешение: вручную задайте для свойства нужное значение через Microsoft Graph.**</span><span class="sxs-lookup"><span data-stu-id="c0e51-164">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="c0e51-165">Замените **{groupId}** в запросе на вопрос фактического сервера, который можно получить с помощью PowerShell для Exchange Online, с помощью командлета **[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)** , как атрибут "**ExternalDirectoryObjectId**".</span><span class="sxs-lookup"><span data-stu-id="c0e51-165">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="c0e51-166">[Проводник](https://developer.microsoft.com/en-us/graph/graph-explorer) по диаграммам Access</span><span class="sxs-lookup"><span data-stu-id="c0e51-166">Access [Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer)</span></span>

2. <span data-ttu-id="c0e51-167">Вход в проводник Graph в меню слева</span><span class="sxs-lookup"><span data-stu-id="c0e51-167">Sign in to Graph Explorer on the left menu</span></span>

3. <span data-ttu-id="c0e51-168">Измените строку запроса на: PATCH > v 1.0 >https://graph.microsoft.com/v1.0/groups/{groupid}</span><span class="sxs-lookup"><span data-stu-id="c0e51-168">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}</span></span>

4. <span data-ttu-id="c0e51-169">Добавьте в текст запроса следующее значение: {"Ресаурцепровисионингоптионс": ["Team"]}</span><span class="sxs-lookup"><span data-stu-id="c0e51-169">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}</span></span>

5. <span data-ttu-id="c0e51-170">Запустите запрос в правом верхнем углу.</span><span class="sxs-lookup"><span data-stu-id="c0e51-170">Run the query on the top-right.</span></span>

6. <span data-ttu-id="c0e51-171">Убедитесь в том, что команда правильно отображается в центре администрирования Microsoft Teams — Обзор групп</span><span class="sxs-lookup"><span data-stu-id="c0e51-171">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview</span></span>


## <a name="learn-more"></a><span data-ttu-id="c0e51-172">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="c0e51-172">Learn more</span></span>

[<span data-ttu-id="c0e51-173">Справочник по командлетам Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c0e51-173">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[<span data-ttu-id="c0e51-174">Роли администраторов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c0e51-174">Admin roles in Microsoft Teams</span></span>](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

