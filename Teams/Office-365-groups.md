---
title: Группы Microsoft 365 и Microsoft Teams
ms.reviewer: kblevins
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
description: Узнайте, как группы Microsoft 365 и членство в группах работают с Microsoft Teams.
ms.openlocfilehash: d258fa4252f6bbb02d2b9a8211dd5919c2d7a67b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105245"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a><span data-ttu-id="82b30-103">Группы Microsoft 365 и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="82b30-103">Microsoft 365 Groups and Microsoft Teams</span></span>

<span data-ttu-id="82b30-104">Группы Microsoft 365 — это служба, в составная служба для перекрестных приложений Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="82b30-104">Microsoft 365 Groups is the cross-application membership service in Microsoft 365.</span></span> <span data-ttu-id="82b30-105">На базовом уровне группа Microsoft 365 — это объект в Azure Active Directory со списком участников и списком связанных рабочих нагрузок, включая сайт группы SharePoint, общий почтовый ящик Exchange, Планировщик и рабочая область Power BI.</span><span class="sxs-lookup"><span data-stu-id="82b30-105">At a basic level, a Microsoft 365 Group is an object in Azure Active Directory with a list of members and a coupling to related workloads including a SharePoint team site, shared Exchange mailbox, Planner and Power BI workspace.</span></span> <span data-ttu-id="82b30-106">Вы можете добавлять и удалять людей в группе, как и любые другие объекты безопасности на основе группы в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="82b30-106">You can add or remove people to the group just as you would any other group-based security object in Active Directory.</span></span>

![Схема, показывающая Группы Microsoft 365 и связанные службы](/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

<span data-ttu-id="82b30-108">По умолчанию пользователи в Microsoft 365 могут создавать группы и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="82b30-108">By default, users in Microsoft 365 can create and manage groups.</span></span> <span data-ttu-id="82b30-109">Дополнительные сведения о Группах Microsoft 365 см. в плакате "Группы [Microsoft 365](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) и Группы [в Microsoft 365 для ИТ-архитекторов".](teams-architecture-solutions-posters.md#groups-in-microsoft-365)</span><span class="sxs-lookup"><span data-stu-id="82b30-109">For more information about Microsoft 365 Groups, see [Learn about Microsoft 365 Groups](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) and the [Groups in Microsoft 365 for IT Architects](teams-architecture-solutions-posters.md#groups-in-microsoft-365) poster.</span></span>

## <a name="how-microsoft-365-groups-work-with-teams"></a><span data-ttu-id="82b30-110">Работа групп Microsoft 365 с Teams</span><span class="sxs-lookup"><span data-stu-id="82b30-110">How Microsoft 365 Groups work with Teams</span></span>

<span data-ttu-id="82b30-111">При создании команды создается группа Microsoft 365, которая будет управлять членством в них.</span><span class="sxs-lookup"><span data-stu-id="82b30-111">When you create a team, a Microsoft 365 group is created to manage team membership.</span></span> <span data-ttu-id="82b30-112">Связанные службы группы, такие как сайт SharePoint, рабочая область Power BI и т. д., создаются одновременно.</span><span class="sxs-lookup"><span data-stu-id="82b30-112">The group's related services, such as a SharePoint site, Power BI workspace, etc. are created at the same time.</span></span>

<span data-ttu-id="82b30-113">Люди, которые создают команды, могут использовать существующую группу Microsoft 365, если они являются ее владельцем.</span><span class="sxs-lookup"><span data-stu-id="82b30-113">People who create teams can choose to use an existing Microsoft 365 group if they are an owner of that group.</span></span> <span data-ttu-id="82b30-114">У каждого канала команды есть отдельная папка в библиотеке документов.</span><span class="sxs-lookup"><span data-stu-id="82b30-114">Each channel in the team has a separate folder in the document library.</span></span> <span data-ttu-id="82b30-115">При создании папок непосредственно в библиотеке документов каналы в команде не создаются.</span><span class="sxs-lookup"><span data-stu-id="82b30-115">Creating folders directly in the document library does not create channels in the team.</span></span>

<span data-ttu-id="82b30-116">При создании группы Microsoft 365 в Outlook или SharePoint почтовый ящик группы отображается в Outlook.</span><span class="sxs-lookup"><span data-stu-id="82b30-116">When creating a Microsoft 365 group in Outlook or SharePoint, the group mailbox is visible in Outlook.</span></span> <span data-ttu-id="82b30-117">При создании команды в Teams почтовый ящик группы по умолчанию скрыт.</span><span class="sxs-lookup"><span data-stu-id="82b30-117">When creating a team in Teams, the group mailbox is hidden by default.</span></span> <span data-ttu-id="82b30-118">Чтобы сделать почтовый ящик видимым, можно использовать cmdlet [Set-UnifiedGroup](/powershell/module/exchange/users-and-groups/set-unifiedgroup) с параметром **HiddenFromExchangeClientsEnabled.**</span><span class="sxs-lookup"><span data-stu-id="82b30-118">You can use the [Set-UnifiedGroup](/powershell/module/exchange/users-and-groups/set-unifiedgroup) cmdlet with the **HiddenFromExchangeClientsEnabled** parameter to make a mailbox visible.</span></span>

## <a name="group-membership"></a><span data-ttu-id="82b30-119">Членство в группах</span><span class="sxs-lookup"><span data-stu-id="82b30-119">Group membership</span></span>

<span data-ttu-id="82b30-120">При удалении участника команды он также удаляется из группы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="82b30-120">If you remove a member of a team, they are removed from the Microsoft 365 group as well.</span></span> <span data-ttu-id="82b30-121">При удалении из группы сразу же удаляются команда и каналы из клиента Teams.</span><span class="sxs-lookup"><span data-stu-id="82b30-121">Removal from the group immediately removes the team and channels from the Teams client.</span></span> <span data-ttu-id="82b30-122">Если удалить человека из группы с помощью Центра администрирования Microsoft 365, у него больше не будет доступа к другим аспектам совместной работы, таким как библиотека документов SharePoint Online, группа Yammer или общий доступ к OneNote.</span><span class="sxs-lookup"><span data-stu-id="82b30-122">If you remove a person from a group using the Microsoft 365 admin center, they will no longer have access to the other collaborative aspects such as SharePoint Online document library, Yammer group, or shared OneNote.</span></span> <span data-ttu-id="82b30-123">Однако у него по-прежнему будет доступ к функциям чата группы в течение приблизительно двух часов.</span><span class="sxs-lookup"><span data-stu-id="82b30-123">However, they will still have access to the team's chat functionality for approximately two hours.</span></span>

<span data-ttu-id="82b30-124">Чтобы обеспечить быстрое обновление разрешений для других подключенных к группе рабочих нагрузок, добавьте их в клиент Teams и удалите из него.</span><span class="sxs-lookup"><span data-stu-id="82b30-124">As a best practice for managing team members, add and remove them from the Teams client to ensure that permissions updates for other group-connected workloads occur quickly.</span></span> <span data-ttu-id="82b30-125">Если вы добавите или удалите участников команды за пределами клиента Teams (с помощью Центра администрирования Microsoft 365, Azure AD или Exchange Online PowerShell), для отражения изменений в Teams может занять до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="82b30-125">If you add or remove team members outside of the Teams client (by using the Microsoft 365 admin center, Azure AD, or Exchange Online PowerShell), it can take up to 24 hours for changes to be reflected in Teams.</span></span>

## <a name="deleting-groups-and-teams"></a><span data-ttu-id="82b30-126">Удаление групп и групп</span><span class="sxs-lookup"><span data-stu-id="82b30-126">Deleting groups and teams</span></span>

<span data-ttu-id="82b30-127">При удалении группы Microsoft 365 удаляется псевдоним почтового ящика для сохраняемой беседы Outlook/OWA и приглашения на собрания Teams, а сайт SharePoint пометка для удаления.</span><span class="sxs-lookup"><span data-stu-id="82b30-127">Deleting a Microsoft 365 group will remove the mailbox alias for persistent Outlook/OWA conversations and Teams meeting invites, and mark the SharePoint site for deletion.</span></span> <span data-ttu-id="82b30-128">Удаление команды и ее действие в Outlook занимает около 20 минут.</span><span class="sxs-lookup"><span data-stu-id="82b30-128">It takes approximately 20 minutes between the removal of a team and its effect on Outlook.</span></span> <span data-ttu-id="82b30-129">При удалении команды из клиента Teams она сразу же удаляется из представления для всех участников команды.</span><span class="sxs-lookup"><span data-stu-id="82b30-129">Deleting a team from the Teams client will remove it immediately from view to all who are members of the team.</span></span> <span data-ttu-id="82b30-130">При удалении участников группы Microsoft 365, для которых были включены функции Teams, в течение приблизительно двух часов команда может быть удалена из представления в клиенте Teams для затронутых людей.</span><span class="sxs-lookup"><span data-stu-id="82b30-130">If you remove members of a Microsoft 365 Group that has had Teams functionality enabled on it, there could be a delay of approximately two hours before the team is removed from view in the Teams client for the affected people who were removed.</span></span>

<span data-ttu-id="82b30-131">Подробные сведения о параметрах окончания жизненного цикла групп и команд см. в параметрах окончания жизненного цикла [групп, групп, Yammer](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) и архива либо удаления команды [в Microsoft Teams.](./archive-or-delete-a-team.md)</span><span class="sxs-lookup"><span data-stu-id="82b30-131">For details about groups and teams end of lifecycle options, see  [End of lifecycle options for groups, teams, and Yammer](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) and [Archive or delete a team in Microsoft Teams](./archive-or-delete-a-team.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="82b30-132">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="82b30-132">Related topics</span></span>

[<span data-ttu-id="82b30-133">Основы Microsoft Teams (видео)</span><span class="sxs-lookup"><span data-stu-id="82b30-133">Foundations of Microsoft Teams (video)</span></span>](https://aka.ms/teams-foundations)

[<span data-ttu-id="82b30-134">Восстановление удаленной группы</span><span class="sxs-lookup"><span data-stu-id="82b30-134">Restore a deleted Group</span></span>](/microsoft-365/admin/create-groups/restore-deleted-group)