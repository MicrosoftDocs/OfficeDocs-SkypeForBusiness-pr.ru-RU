---
title: Управление группами в центре администрирования Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: Сведения о том, как просматривать или обновлять команды, настроенные для совместной работы в центре администрирования Microsoft Teams.
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
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="71219-103">Управление группами в центре администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="71219-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================

## <a name="overview"></a><span data-ttu-id="71219-104">Обзор</span><span class="sxs-lookup"><span data-stu-id="71219-104">Overview</span></span>

<span data-ttu-id="71219-105">В этой статье приводятся общие сведения о средствах управления для Teams в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="71219-105">This article provides an overview of the management tools for Teams in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="71219-106">Администратору может потребоваться просмотреть или изменить команды, настроенные для совместной работы Организации, или выполнить действия по исправлению, например назначение владельцев для групп без владельца.</span><span class="sxs-lookup"><span data-stu-id="71219-106">As an admin, you may need to view or update the teams that your organization set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="71219-107">Вы можете управлять командами, используемыми в вашей организации, с помощью обоих модулей Microsoft Teams PowerShell и центра администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="71219-107">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="71219-108">Получить доступ к центру администрирования можно по адресу <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="71219-108">You can access the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span> <span data-ttu-id="71219-109">Для обеспечения полного доступа к возможностям администрирования с помощью этих двух наборов инструментов необходимо убедиться в том, что вы назначили одну из следующих ролей:</span><span class="sxs-lookup"><span data-stu-id="71219-109">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="71219-110">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="71219-110">Global Administrator</span></span>
- <span data-ttu-id="71219-111">Администратор служб Teams</span><span class="sxs-lookup"><span data-stu-id="71219-111">Teams Service Administrator</span></span>

<span data-ttu-id="71219-112">Дополнительные сведения о ролях администратора в Teams можно найти в разделе [Использование ролей администратора Microsoft Teams для управления группами](using-admin-roles.md), а также Узнайте больше о том, как использовать командлеты PowerShell для управления группами в [справочнике по командлетам Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="71219-112">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>



## <a name="teams-overview-grid"></a><span data-ttu-id="71219-113">Сетка обзора групп</span><span class="sxs-lookup"><span data-stu-id="71219-113">Teams overview grid</span></span>

<span data-ttu-id="71219-114">Средства управления для Teams находятся под узлом **Teams** в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="71219-114">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="71219-115">(В центре администрирования выберите **команды**  >  **Управление группами**.) Каждая команда помещается в группу Microsoft 365, а этот узел предоставляет представление групп, которые были включены в Microsoft Teams в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="71219-115">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by a Microsoft 365 Group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![Снимок экрана: сетка обзора групп](media/manage-teams-in-modern-portal-grid.png)  

<span data-ttu-id="71219-117">В сетке отображаются следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="71219-117">The grid displays the following properties:</span></span>

- <span data-ttu-id="71219-118">**Название команды**</span><span class="sxs-lookup"><span data-stu-id="71219-118">**Team name**</span></span>
- <span data-ttu-id="71219-119">**Channels (каналы** ) — общее количество всех каналов в группе, включая стандартный канал по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="71219-119">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="71219-120">**Участники групп** — общее количество пользователей, включая владельцев, гостей и участников из вашего клиента.</span><span class="sxs-lookup"><span data-stu-id="71219-120">**Team members** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="71219-121">**Owners (владельцы** ) — Количество владельцев группы.</span><span class="sxs-lookup"><span data-stu-id="71219-121">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="71219-122">**Гости** — количество гостевых пользователей Azure Active Directory B2B, которые являются участниками этой команды.</span><span class="sxs-lookup"><span data-stu-id="71219-122">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="71219-123">**Privacy (конфиденциальность** ) — это AccessType и т. д. для резервного копирования группы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="71219-123">**Privacy** - the Visibility/AccessType of the backing Microsoft 365 group.</span></span>
- <span data-ttu-id="71219-124">**Status (состояние** ) — архивированный или активный статус этой команды.</span><span class="sxs-lookup"><span data-stu-id="71219-124">**Status** - the Archived or Active status for this team.</span></span> <span data-ttu-id="71219-125">Узнайте больше о том, как архивировать команды в [архивации или восстановлении команды](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span><span class="sxs-lookup"><span data-stu-id="71219-125">Learn more about archiving teams in [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="71219-126">**Описание** — описание группы резервных копий Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="71219-126">**Description** - the description of the backing Microsoft 365 group.</span></span>
- <span data-ttu-id="71219-127">**Классификация** — классификация (если она используется в вашей организации), назначенная группе резервного копирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="71219-127">**Classification** - the classification (if used in your organization) assigned to the backing Microsoft 365 group.</span></span> <span data-ttu-id="71219-128">Узнайте больше о классификациях на странице [Создание классификаций для групп Office в Организации](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="71219-128">Learn more about classifications at [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="71219-129">**GroupId** — уникальный идентификатор группы резервного копирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="71219-129">**GroupID** - the unique GroupID of the backing Microsoft 365 group.</span></span>

> [!NOTE]
> <span data-ttu-id="71219-130">Если вы не видите все эти свойства в сетке, щелкните значок **изменить столбцы** .</span><span class="sxs-lookup"><span data-stu-id="71219-130">If you don't see all these properties in the grid, click the **Edit columns** icon.</span></span> <span data-ttu-id="71219-131">В области **изменить столбцы** вы можете включить или отключить столбцы в сетке с помощью переключателей.</span><span class="sxs-lookup"><span data-stu-id="71219-131">In the **Edit columns** pane, you can use the toggles to turn on or turn off columns in the grid.</span></span> <span data-ttu-id="71219-132">Когда все будет готово, нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="71219-132">When you're finished, click **Apply**.</span></span>

### <a name="add"></a><span data-ttu-id="71219-133">Добавлении</span><span class="sxs-lookup"><span data-stu-id="71219-133">Add</span></span>

<span data-ttu-id="71219-134">Чтобы добавить новую команду, нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="71219-134">To add a new team, click **Add**.</span></span> <span data-ttu-id="71219-135">В области **Добавить новую группу** укажите имя и описание группы, укажите, хотите ли вы сделать ее частной или общедоступной, и задайте классификацию.</span><span class="sxs-lookup"><span data-stu-id="71219-135">In the **Add a new team** pane, give the team a name and description, set whether you want to make it a private or public team, and set the classification.</span></span>

> [!NOTE]
> <span data-ttu-id="71219-136">Вы можете управлять только что созданными группами в центре администрирования Teams, в отличие от возможностей других клиентов, например Outlook.</span><span class="sxs-lookup"><span data-stu-id="71219-136">Newly created teams can be managed right away in the Teams Admin Center, unlike the experience in other clients like, Outlook.</span></span>

### <a name="edit"></a><span data-ttu-id="71219-137">Правка</span><span class="sxs-lookup"><span data-stu-id="71219-137">Edit</span></span>

<span data-ttu-id="71219-138">Чтобы изменить параметры группы и группы, выберите группу, щелкнув слева от ее имени, а затем щелкните **изменить**.</span><span class="sxs-lookup"><span data-stu-id="71219-138">To edit group and team-specific settings, select the team by clicking to the left of the team name, and then select **Edit**.</span></span>

### <a name="archive"></a><span data-ttu-id="71219-139">Архивация</span><span class="sxs-lookup"><span data-stu-id="71219-139">Archive</span></span>

<span data-ttu-id="71219-140">Вы можете архивировать группу.</span><span class="sxs-lookup"><span data-stu-id="71219-140">You can archive a team.</span></span> <span data-ttu-id="71219-141">Архивация команды размещает группу в режиме "только для чтения" в Teams.</span><span class="sxs-lookup"><span data-stu-id="71219-141">Archiving a team puts the team into read-only mode within Teams.</span></span> <span data-ttu-id="71219-142">Администраторы могут архивировать и отменять архивацию команд от имени вашей организации в центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="71219-142">As an admin, you can archive and un-archive teams on behalf of your organization in the admin center.</span></span> 

### <a name="delete"></a><span data-ttu-id="71219-143">Удаление</span><span class="sxs-lookup"><span data-stu-id="71219-143">Delete</span></span>

<span data-ttu-id="71219-144">Удаление команды является мягким удалением группы и соответствующей группой Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="71219-144">Deleting a team is a soft-delete of the team and corresponding Microsoft 365 group.</span></span> <span data-ttu-id="71219-145">Чтобы восстановить удаленную группу по ошибочной удаленной команде, следуйте инструкциям в разделе [Восстановление удаленной группы](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group).</span><span class="sxs-lookup"><span data-stu-id="71219-145">To restore a mistakenly deleted team, follow the instructions in [Restore a deleted Group](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group).</span></span>

### <a name="search"></a><span data-ttu-id="71219-146">Поиск</span><span class="sxs-lookup"><span data-stu-id="71219-146">Search</span></span>

<span data-ttu-id="71219-147">В настоящее время Поиск поддерживает строку "начинается с" и выполняет поиск в поле **имя группы** .</span><span class="sxs-lookup"><span data-stu-id="71219-147">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

## <a name="team-profile"></a><span data-ttu-id="71219-148">Профиль группы</span><span class="sxs-lookup"><span data-stu-id="71219-148">Team profile</span></span>

<span data-ttu-id="71219-149">Вы можете перейти на страницу профиля группы в любой команде из главной сетки обзора рабочих групп, щелкнув ее имя.</span><span class="sxs-lookup"><span data-stu-id="71219-149">You can navigate to the team profile page of any team from the main teams overview grid by clicking  the team name.</span></span> <span data-ttu-id="71219-150">На странице "профиль группы" отображаются участники, владельцы и гости, принадлежащие группе (и резервная копия Microsoft 365), а также каналы и параметры команды.</span><span class="sxs-lookup"><span data-stu-id="71219-150">The team profile page shows the members, owners, and guests that belong to the team (and its backing Microsoft 365 group), as well as the team's channels and settings.</span></span> <span data-ttu-id="71219-151">На странице "профиль группы" можно выполнять указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="71219-151">From the team profile page, you can:</span></span>

- <span data-ttu-id="71219-152">Добавление и удаление участников и владельцев.</span><span class="sxs-lookup"><span data-stu-id="71219-152">Add or remove members and owners.</span></span>
- <span data-ttu-id="71219-153">Добавление и удаление каналов (Обратите внимание на то, что вы не можете удалить канал "Общие").</span><span class="sxs-lookup"><span data-stu-id="71219-153">Add or remove channels (note that you can't remove the General channel).</span></span>
- <span data-ttu-id="71219-154">Изменение параметров группы и группы.</span><span class="sxs-lookup"><span data-stu-id="71219-154">Change team and group settings.</span></span>
 
![Снимок экрана: пример профиля группы](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="71219-156">Внесение изменений в Teams</span><span class="sxs-lookup"><span data-stu-id="71219-156">Making changes to teams</span></span>

<span data-ttu-id="71219-157">На странице профиля группы вы можете изменить следующие элементы команды:</span><span class="sxs-lookup"><span data-stu-id="71219-157">On the team's profile page, you can change the following elements of a team:</span></span>

- <span data-ttu-id="71219-158">**Участники** — Добавление и удаление участников и повышение или понижение роли владельцев.</span><span class="sxs-lookup"><span data-stu-id="71219-158">**Members** - add or remove members and promote or demote owners.</span></span>
- <span data-ttu-id="71219-159">**Каналы** — Добавление новых каналов, редактирование и удаление существующих каналов.</span><span class="sxs-lookup"><span data-stu-id="71219-159">**Channels** - add new channels, and edit or remove existing channels.</span></span> <span data-ttu-id="71219-160">Помните о том, что вы не можете удалить канал общего канала по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="71219-160">Remember that you can't delete the default General channel.</span></span>
- <span data-ttu-id="71219-161">**Название команды**</span><span class="sxs-lookup"><span data-stu-id="71219-161">**Team name**</span></span>
- <span data-ttu-id="71219-162">**Описание**</span><span class="sxs-lookup"><span data-stu-id="71219-162">**Description**</span></span>
- <span data-ttu-id="71219-163">**Конфиденциальность** -Настройка общедоступной или закрытой группы.</span><span class="sxs-lookup"><span data-stu-id="71219-163">**Privacy** - set whether the team is public or private.</span></span>
- <span data-ttu-id="71219-164">**Классификация** : это осуществляется с помощью классификаций групп Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="71219-164">**Classification** - this is backed by your Microsoft 365 group classifications.</span></span> <span data-ttu-id="71219-165">Выберите **конфиденциальный**, **очень конфиденциальный**или **Общий**.</span><span class="sxs-lookup"><span data-stu-id="71219-165">Choose **Confidential**, **Highly Confidential**, or **General**.</span></span>
- <span data-ttu-id="71219-166">**Параметры бесед** — Настройка того, могут ли участники изменять и удалять отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="71219-166">**Conversations settings** - set whether members can edit and delete sent messages.</span></span>
- <span data-ttu-id="71219-167">**Параметры каналов** — Настройка возможности создания новых каналов и изменения существующих, а также добавления, изменения и удаления вкладок, соединителей и приложений.</span><span class="sxs-lookup"><span data-stu-id="71219-167">**Channels settings** - set whether members can create new channels and edit existing ones, and add, edit, and remove tabs, connectors, and apps.</span></span>

<span data-ttu-id="71219-168">Изменения, внесенные в команду, регистрируются в журнале.</span><span class="sxs-lookup"><span data-stu-id="71219-168">The changes that you make to a team are logged.</span></span> <span data-ttu-id="71219-169">Если вы изменяете параметры группы (изменяя имя, описание, фотографию, конфиденциальность, классификацию или участников группы), эти изменения подаются с помощью конвейера аудита.</span><span class="sxs-lookup"><span data-stu-id="71219-169">If you're modifying group settings (changing the name, description, photo, privacy, classification, or team members), the changes are attributed to you through the audit pipeline.</span></span> <span data-ttu-id="71219-170">Если вы выполняете действия с параметрами, специфическими для Teams, ваши изменения отслеживаются и наносятся на вас в общем канале команды.</span><span class="sxs-lookup"><span data-stu-id="71219-170">If you're performing actions against Teams-specific settings, your changes are tracked and attributed to you in the General channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="71219-171">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="71219-171">Troubleshooting</span></span>

<span data-ttu-id="71219-172">**Вопрос: в сетке обзора команды отсутствует Teams**</span><span class="sxs-lookup"><span data-stu-id="71219-172">**Issue: Teams missing from the Team overview grid**</span></span>

<span data-ttu-id="71219-173">Некоторые команды отсутствуют в списке групп в сетке Обзор групп.</span><span class="sxs-lookup"><span data-stu-id="71219-173">Some of your teams are missing from the list of teams in the Teams overview grid.</span></span>

<span data-ttu-id="71219-174">**Причина**: Эта проблема возникает, если группа была неправильно (или еще не настроена), которая может привести к распознаванию отсутствующего свойства.</span><span class="sxs-lookup"><span data-stu-id="71219-174">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="71219-175">**Разрешение: вручную задайте для свойства нужное значение через Microsoft Graph.**</span><span class="sxs-lookup"><span data-stu-id="71219-175">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="71219-176">Замените **{groupId}** в запросе на вопрос фактического сервера, который можно получить с помощью PowerShell для Exchange Online, с помощью командлета **[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)** , как атрибут "**ExternalDirectoryObjectId**".</span><span class="sxs-lookup"><span data-stu-id="71219-176">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="71219-177">[Проводник по диаграммам](https://developer.microsoft.com/graph/graph-explorer)Access.</span><span class="sxs-lookup"><span data-stu-id="71219-177">Access [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

2. <span data-ttu-id="71219-178">Войдите в проводник диаграмм в меню слева.</span><span class="sxs-lookup"><span data-stu-id="71219-178">Sign in to Graph Explorer on the left menu.</span></span>

3. <span data-ttu-id="71219-179">Измените строку запроса на: PATCH > v 1.0 > https://graph.microsoft.com/v1.0/groups/{groupid} .</span><span class="sxs-lookup"><span data-stu-id="71219-179">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}.</span></span>

4. <span data-ttu-id="71219-180">Добавьте в текст запроса следующее значение: {"resourceProvisioningOptions": ["Team"]}.</span><span class="sxs-lookup"><span data-stu-id="71219-180">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}.</span></span>

5. <span data-ttu-id="71219-181">Запустите запрос в правом верхнем углу.</span><span class="sxs-lookup"><span data-stu-id="71219-181">Run the query on the top-right.</span></span>

6. <span data-ttu-id="71219-182">Убедитесь в том, что команда правильно отображается в центре администрирования Microsoft Teams — Обзор групп.</span><span class="sxs-lookup"><span data-stu-id="71219-182">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview.</span></span>

## <a name="learn-more"></a><span data-ttu-id="71219-183">Подробнее</span><span class="sxs-lookup"><span data-stu-id="71219-183">Learn more</span></span>

- [<span data-ttu-id="71219-184">Справочник по командлетам Teams</span><span class="sxs-lookup"><span data-stu-id="71219-184">Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
- [<span data-ttu-id="71219-185">Использование ролей администратора Teams для управления группами</span><span class="sxs-lookup"><span data-stu-id="71219-185">Use Teams administrator roles to manage Teams</span></span>](using-admin-roles.md)
- [<span data-ttu-id="71219-186">Планирование управления жизненным циклом в Teams</span><span class="sxs-lookup"><span data-stu-id="71219-186">Plan for lifecycle management in Teams</span></span>](plan-teams-lifecycle.md)
