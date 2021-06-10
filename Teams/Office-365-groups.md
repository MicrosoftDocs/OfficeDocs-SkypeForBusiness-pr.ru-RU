---
title: Microsoft 365 Группы и Microsoft Teams
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
description: Узнайте, как Microsoft 365 и членство в группах с Microsoft Teams.
ms.openlocfilehash: d258fa4252f6bbb02d2b9a8211dd5919c2d7a67b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105245"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a><span data-ttu-id="605b1-103">Microsoft 365 Группы и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="605b1-103">Microsoft 365 Groups and Microsoft Teams</span></span>

<span data-ttu-id="605b1-104">Microsoft 365 Groups — это служба, в составной Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="605b1-104">Microsoft 365 Groups is the cross-application membership service in Microsoft 365.</span></span> <span data-ttu-id="605b1-105">На базовом уровне группа Microsoft 365 — это объект в Azure Active Directory со списком участников и связанными рабочими нагрузками, включая сайт группы SharePoint, общий почтовый ящик Exchange, Планировщик и рабочая область Power BI.</span><span class="sxs-lookup"><span data-stu-id="605b1-105">At a basic level, a Microsoft 365 Group is an object in Azure Active Directory with a list of members and a coupling to related workloads including a SharePoint team site, shared Exchange mailbox, Planner and Power BI workspace.</span></span> <span data-ttu-id="605b1-106">В группу можно добавлять и удалять пользователей так же, как любые другие объекты безопасности на основе группы в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="605b1-106">You can add or remove people to the group just as you would any other group-based security object in Active Directory.</span></span>

![Схема, показывающая Microsoft 365 групп и связанных служб](/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

<span data-ttu-id="605b1-108">По умолчанию пользователи в Microsoft 365 могут создавать группы и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="605b1-108">By default, users in Microsoft 365 can create and manage groups.</span></span> <span data-ttu-id="605b1-109">Дополнительные сведения о группах Microsoft 365 см. в Microsoft 365 [группы](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) и группы Microsoft 365 для [ИТ-архитекторов.](teams-architecture-solutions-posters.md#groups-in-microsoft-365)</span><span class="sxs-lookup"><span data-stu-id="605b1-109">For more information about Microsoft 365 Groups, see [Learn about Microsoft 365 Groups](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) and the [Groups in Microsoft 365 for IT Architects](teams-architecture-solutions-posters.md#groups-in-microsoft-365) poster.</span></span>

## <a name="how-microsoft-365-groups-work-with-teams"></a><span data-ttu-id="605b1-110">Как Microsoft 365 группы работают с Teams</span><span class="sxs-lookup"><span data-stu-id="605b1-110">How Microsoft 365 Groups work with Teams</span></span>

<span data-ttu-id="605b1-111">При создании команды создается Microsoft 365 для управления членством в них.</span><span class="sxs-lookup"><span data-stu-id="605b1-111">When you create a team, a Microsoft 365 group is created to manage team membership.</span></span> <span data-ttu-id="605b1-112">Одновременно создаются связанные службы группы, такие как сайт SharePoint, Power BI рабочая область и т. д.</span><span class="sxs-lookup"><span data-stu-id="605b1-112">The group's related services, such as a SharePoint site, Power BI workspace, etc. are created at the same time.</span></span>

<span data-ttu-id="605b1-113">Люди, которые создают команды, могут использовать существующую группу Microsoft 365, если они являются ее владельцем.</span><span class="sxs-lookup"><span data-stu-id="605b1-113">People who create teams can choose to use an existing Microsoft 365 group if they are an owner of that group.</span></span> <span data-ttu-id="605b1-114">У каждого канала группы есть отдельная папка в библиотеке документов.</span><span class="sxs-lookup"><span data-stu-id="605b1-114">Each channel in the team has a separate folder in the document library.</span></span> <span data-ttu-id="605b1-115">При создании папок непосредственно в библиотеке документов каналы в группе не создаются.</span><span class="sxs-lookup"><span data-stu-id="605b1-115">Creating folders directly in the document library does not create channels in the team.</span></span>

<span data-ttu-id="605b1-116">При создании группы Microsoft 365 в Outlook или SharePoint, почтовый ящик группы отображается в Outlook.</span><span class="sxs-lookup"><span data-stu-id="605b1-116">When creating a Microsoft 365 group in Outlook or SharePoint, the group mailbox is visible in Outlook.</span></span> <span data-ttu-id="605b1-117">При создании группы в Teams почтовый ящик группы по умолчанию скрыт.</span><span class="sxs-lookup"><span data-stu-id="605b1-117">When creating a team in Teams, the group mailbox is hidden by default.</span></span> <span data-ttu-id="605b1-118">Чтобы сделать почтовый ящик видимым, можно использовать cmdlet [Set-UnifiedGroup](/powershell/module/exchange/users-and-groups/set-unifiedgroup) с параметром **HiddenFromExchangeClientsEnabled.**</span><span class="sxs-lookup"><span data-stu-id="605b1-118">You can use the [Set-UnifiedGroup](/powershell/module/exchange/users-and-groups/set-unifiedgroup) cmdlet with the **HiddenFromExchangeClientsEnabled** parameter to make a mailbox visible.</span></span>

## <a name="group-membership"></a><span data-ttu-id="605b1-119">Членство в группах</span><span class="sxs-lookup"><span data-stu-id="605b1-119">Group membership</span></span>

<span data-ttu-id="605b1-120">При удалении участника команды он также удаляется из Microsoft 365 группы.</span><span class="sxs-lookup"><span data-stu-id="605b1-120">If you remove a member of a team, they are removed from the Microsoft 365 group as well.</span></span> <span data-ttu-id="605b1-121">Удаление из группы немедленно удаляет группу и каналы из Teams клиента.</span><span class="sxs-lookup"><span data-stu-id="605b1-121">Removal from the group immediately removes the team and channels from the Teams client.</span></span> <span data-ttu-id="605b1-122">Если удалить человека из группы с помощью Центра администрирования Microsoft 365, он больше не будет иметь доступа к другим аспектам совместной работы, таким как библиотека документов SharePoint Online, группа Yammer или общий доступ OneNote.</span><span class="sxs-lookup"><span data-stu-id="605b1-122">If you remove a person from a group using the Microsoft 365 admin center, they will no longer have access to the other collaborative aspects such as SharePoint Online document library, Yammer group, or shared OneNote.</span></span> <span data-ttu-id="605b1-123">Однако у него по-прежнему будет доступ к функциям чата группы в течение примерно двух часов.</span><span class="sxs-lookup"><span data-stu-id="605b1-123">However, they will still have access to the team's chat functionality for approximately two hours.</span></span>

<span data-ttu-id="605b1-124">Чтобы обеспечить быстрое обновление разрешений для других подключенных к группе рабочих нагрузок, добавьте их в клиент Teams и удалите из него.</span><span class="sxs-lookup"><span data-stu-id="605b1-124">As a best practice for managing team members, add and remove them from the Teams client to ensure that permissions updates for other group-connected workloads occur quickly.</span></span> <span data-ttu-id="605b1-125">Если вы добавляете или удаляете участников группы за пределами клиента Teams (с помощью Центра администрирования Microsoft 365, Azure AD или Exchange Online PowerShell), на их отражение в Teams может быть до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="605b1-125">If you add or remove team members outside of the Teams client (by using the Microsoft 365 admin center, Azure AD, or Exchange Online PowerShell), it can take up to 24 hours for changes to be reflected in Teams.</span></span>

## <a name="deleting-groups-and-teams"></a><span data-ttu-id="605b1-126">Удаление групп и команд</span><span class="sxs-lookup"><span data-stu-id="605b1-126">Deleting groups and teams</span></span>

<span data-ttu-id="605b1-127">При удалении Microsoft 365 группы удаляются псевдонимы почтовых ящиков для бесед Outlook/OWA и Teams приглашений на собрания, а также пометка сайта SharePoint для удаления.</span><span class="sxs-lookup"><span data-stu-id="605b1-127">Deleting a Microsoft 365 group will remove the mailbox alias for persistent Outlook/OWA conversations and Teams meeting invites, and mark the SharePoint site for deletion.</span></span> <span data-ttu-id="605b1-128">Удаление команды и ее влияние на удаление команды занимает около 20 минут Outlook.</span><span class="sxs-lookup"><span data-stu-id="605b1-128">It takes approximately 20 minutes between the removal of a team and its effect on Outlook.</span></span> <span data-ttu-id="605b1-129">Удаление команды из клиента Teams сразу же удаляет ее из представления для всех участников группы.</span><span class="sxs-lookup"><span data-stu-id="605b1-129">Deleting a team from the Teams client will remove it immediately from view to all who are members of the team.</span></span> <span data-ttu-id="605b1-130">При удалении участников группы Microsoft 365, для которых включена функциональность Teams, может быть около двух часов, прежде чем группа будет удалена из представления в клиенте Teams для затронутых людей, которые были удалены.</span><span class="sxs-lookup"><span data-stu-id="605b1-130">If you remove members of a Microsoft 365 Group that has had Teams functionality enabled on it, there could be a delay of approximately two hours before the team is removed from view in the Teams client for the affected people who were removed.</span></span>

<span data-ttu-id="605b1-131">Подробные сведения о группах и вариантах окончания жизненного цикла групп см. в параметрах окончания жизненного цикла [групп,](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) групп и Yammer а также Архивировать и [удалять группы в Microsoft Teams.](./archive-or-delete-a-team.md)</span><span class="sxs-lookup"><span data-stu-id="605b1-131">For details about groups and teams end of lifecycle options, see  [End of lifecycle options for groups, teams, and Yammer](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) and [Archive or delete a team in Microsoft Teams](./archive-or-delete-a-team.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="605b1-132">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="605b1-132">Related topics</span></span>

[<span data-ttu-id="605b1-133">Основы Microsoft Teams (видео)</span><span class="sxs-lookup"><span data-stu-id="605b1-133">Foundations of Microsoft Teams (video)</span></span>](https://aka.ms/teams-foundations)

[<span data-ttu-id="605b1-134">Восстановление удаленной группы</span><span class="sxs-lookup"><span data-stu-id="605b1-134">Restore a deleted Group</span></span>](/microsoft-365/admin/create-groups/restore-deleted-group)