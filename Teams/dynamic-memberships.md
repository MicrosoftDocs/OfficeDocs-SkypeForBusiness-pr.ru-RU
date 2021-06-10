---
title: Общие сведения о динамическом членстве в командах
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: Узнайте, Microsoft Teams поддерживает группы, связанные с Microsoft 365 с помощью динамического участия.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 74974f7b94a5d1bcadb340e132dae9e3b39a7704
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856328"
---
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="7a5fe-103">Общие сведения о динамическом членстве в командах</span><span class="sxs-lookup"><span data-stu-id="7a5fe-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="7a5fe-104">Microsoft Teams поддерживает группы, связанные с группами Microsoft 365 с помощью *динамического участия.*</span><span class="sxs-lookup"><span data-stu-id="7a5fe-104">Microsoft Teams supports teams associated with Microsoft 365 groups by using *dynamic membership*.</span></span> <span data-ttu-id="7a5fe-105">Динамическое членство позволяет определять членство в группе с помощью одного или двух правил, которые проверяют определенные атрибуты пользователей в Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="7a5fe-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="7a5fe-106">Пользователи автоматически добавляются или удаляются в правильные группы по мере изменения их атрибутов или перейти в клиент и выйти из нее.</span><span class="sxs-lookup"><span data-stu-id="7a5fe-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="7a5fe-107">С динамическим членством вы можете настроить команды для определенных групп пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="7a5fe-107">With dynamic membership you can set up teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="7a5fe-108">Возможные сценарии:</span><span class="sxs-lookup"><span data-stu-id="7a5fe-108">Possible scenarios include:</span></span>
- <span data-ttu-id="7a5fe-109">В больнице можно создавать отдельные команды для медсестр, врача и врача для трансляции коммуникаций.</span><span class="sxs-lookup"><span data-stu-id="7a5fe-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="7a5fe-110">Это особенно важно, если в больнице работают сотрудники временных служб.</span><span class="sxs-lookup"><span data-stu-id="7a5fe-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="7a5fe-111">Университет может создать команду для всех преподавателей в конкретном вузе, включая сотрудников, которые часто меняются.</span><span class="sxs-lookup"><span data-stu-id="7a5fe-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="7a5fe-112">Авиакомпании хотят создать группу для каждого рейса (например, во вторник после полудня без остановки из Чикаго в Чикаго в Чикаго) и при необходимости автоматически получить или удалить из нее часто меняющийся авиарейс.</span><span class="sxs-lookup"><span data-stu-id="7a5fe-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="7a5fe-113">При использовании этой функции участники группы обновляются автоматически на основе определенного набора критериев, а не вручную управляют членством.</span><span class="sxs-lookup"><span data-stu-id="7a5fe-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="7a5fe-114">Для этого администратор клиента может на Premium Azure AD лицензии P1 и членство в группах для любых свойств Azure AD пользователя при условии, что у вас есть клиент и учетная запись администратора. [](/azure/active-directory/users-groups-roles/groups-dynamic-membership)</span><span class="sxs-lookup"><span data-stu-id="7a5fe-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's Azure AD properties provided you have a tenant and an admin account.</span></span>

<span data-ttu-id="7a5fe-115">Microsoft Teams от нескольких минут до 2 часов для отражения динамических изменений состава в группе Microsoft 365 группы.</span><span class="sxs-lookup"><span data-stu-id="7a5fe-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Microsoft 365 group for a team.</span></span>

<span data-ttu-id="7a5fe-116">При использовании команд с динамическими группами:</span><span class="sxs-lookup"><span data-stu-id="7a5fe-116">When using teams with dynamic groups:</span></span>

- <span data-ttu-id="7a5fe-117">Правила определяют, кто является участником команды, но не владелец команды.</span><span class="sxs-lookup"><span data-stu-id="7a5fe-117">Rules can define who is a team member, but not who is a team owner.</span></span>
- <span data-ttu-id="7a5fe-118">Владельцы не смогут добавлять или удалять пользователей в качестве участников команды, так как участники определяются динамическими правилами группы.</span><span class="sxs-lookup"><span data-stu-id="7a5fe-118">Owners will not be able to add or remove users as members of the team, since members are defined by dynamic group rules.</span></span>
- <span data-ttu-id="7a5fe-119">Teams не разрешает управление членами команды.</span><span class="sxs-lookup"><span data-stu-id="7a5fe-119">Teams clients don't allow member management for the team.</span></span> <span data-ttu-id="7a5fe-120">Параметры добавления участников, изменения ролей участников, отправки и утверждения запросов на присоединиться и оставить команду скрытыми.</span><span class="sxs-lookup"><span data-stu-id="7a5fe-120">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>

<span data-ttu-id="7a5fe-121">Чтобы создать команду с динамическим [](/azure/active-directory/users-groups-roles/groups-create-rule) членством, сначала создайте динамическую группу Microsoft 365, а затем создайте [группу из нее.](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)</span><span class="sxs-lookup"><span data-stu-id="7a5fe-121">To create a team that uses dynamic membership, start by [creating a dynamic Microsoft 365 group](/azure/active-directory/users-groups-roles/groups-create-rule) and then [create a team from that group](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865).</span></span>

<span data-ttu-id="7a5fe-122">Вы можете изменить существующую команду на динамическое членство.</span><span class="sxs-lookup"><span data-stu-id="7a5fe-122">You can change an existing team to have a dynamic membership.</span></span> <span data-ttu-id="7a5fe-123">Сведения см. в Azure Active Directory [статических Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type) группах.</span><span class="sxs-lookup"><span data-stu-id="7a5fe-123">See [Change static group membership to dynamic in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type) for information.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7a5fe-124">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="7a5fe-124">Related topics</span></span>

[<span data-ttu-id="7a5fe-125">Ограничения и спецификации для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7a5fe-125">Limits and specifications for Microsoft Teams</span></span>](limits-specifications-teams.md)

[<span data-ttu-id="7a5fe-126">Правила динамического участия в группах в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7a5fe-126">Dynamic membership rules for groups in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/groups-dynamic-membership)
