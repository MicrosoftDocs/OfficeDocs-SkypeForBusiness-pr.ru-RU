---
title: Общие сведения о динамическом членстве в командах
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: Сведения о том, как Microsoft Teams поддерживает команды, связанные с группами Office 365, с помощью динамического членства.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d325ee076d29ddfe50fd6193ec5755bf2bb51b82
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905801"
---
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="f5c5e-103">Общие сведения о динамическом членстве в командах</span><span class="sxs-lookup"><span data-stu-id="f5c5e-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="f5c5e-104">Microsoft Teams поддерживает команды, связанные с группами Microsoft 365, с помощью *динамического членства*.</span><span class="sxs-lookup"><span data-stu-id="f5c5e-104">Microsoft Teams supports teams associated with Microsoft 365 groups by using *dynamic membership*.</span></span> <span data-ttu-id="f5c5e-105">Динамическое членство позволяет членам команды определяться в одном или нескольких правилах, которые проверяют определенные атрибуты пользователей в Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="f5c5e-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="f5c5e-106">Пользователи автоматически добавляются или удаляются в нужных группах при изменении атрибутов пользователей, а также при присоединении к нему и выходе из него.</span><span class="sxs-lookup"><span data-stu-id="f5c5e-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="f5c5e-107">Динамическое членство можно настроить для некоторых cohorts пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="f5c5e-107">With dynamic membership you can set up teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="f5c5e-108">Ниже перечислены возможные сценарии.</span><span class="sxs-lookup"><span data-stu-id="f5c5e-108">Possible scenarios include:</span></span>
- <span data-ttu-id="f5c5e-109">Больницы могут создавать отдельные команды для Nurses, доктора и Surgeons для широковещательной связи.</span><span class="sxs-lookup"><span data-stu-id="f5c5e-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="f5c5e-110">Это особенно важно, если ваша больницы опирается на временных сотрудников.</span><span class="sxs-lookup"><span data-stu-id="f5c5e-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="f5c5e-111">Университет может создать группу для всего факультета в определенном колледже, в том числе в adjunct факультет, который меняется часто.</span><span class="sxs-lookup"><span data-stu-id="f5c5e-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="f5c5e-112">Авиакомпании хочет создать группу для каждого тестового полета (например, в четверг, не прекращая его с Чикаго на Атланта), и при необходимости в них будет автоматически назначена или удалена Crew тестового полета.</span><span class="sxs-lookup"><span data-stu-id="f5c5e-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="f5c5e-113">С помощью этой функции участники данной группы обновляются автоматически на основе определенного набора условий, вместо того чтобы вручную управлять членством.</span><span class="sxs-lookup"><span data-stu-id="f5c5e-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="f5c5e-114">Для этого необходимы лицензии Azure AD Premium P1, и членство в группе может быть [назначено администратором клиента](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) для всех пользователей Azure AD, предоставленных в качестве клиента и учетной записи администратора.</span><span class="sxs-lookup"><span data-stu-id="f5c5e-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's Azure AD properties provided you have a tenant and an admin account.</span></span>

<span data-ttu-id="f5c5e-115">Microsoft Teams может занять от нескольких минут до 2 часов, чтобы отразить динамические изменения в членстве после их вступления в группу Office 365 для группы.</span><span class="sxs-lookup"><span data-stu-id="f5c5e-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Office 365 group for a team.</span></span>

> [!NOTE]
> - <span data-ttu-id="f5c5e-116">Правила могут определять, кто является участником группы, но не кто является владельцем команды.</span><span class="sxs-lookup"><span data-stu-id="f5c5e-116">Rules can define who is a team member, but not who is a team owner.</span></span>
> - <span data-ttu-id="f5c5e-117">[Ограничения и спецификации для Microsoft Teams](limits-specifications-teams.md) по текущим ограничениям для групп и размеров каналов.</span><span class="sxs-lookup"><span data-stu-id="f5c5e-117">See [Limits and specifications for Microsoft Teams](limits-specifications-teams.md) for current limits on team and channel sizes.</span></span>
> - <span data-ttu-id="f5c5e-118">Владельцы не смогут добавлять или удалять пользователей как участников группы, поскольку они определяются с помощью правил динамической группы.</span><span class="sxs-lookup"><span data-stu-id="f5c5e-118">Owners will not be able to add or remove users as members of the team, since members are defined by dynamic group rules.</span></span>
> -    <span data-ttu-id="f5c5e-119">Участники не смогут оставлять команды, которые поддерживаются динамическими группами.</span><span class="sxs-lookup"><span data-stu-id="f5c5e-119">Members will not be able to leave teams backed by dynamic groups.</span></span>


## <a name="creating-and-managing-an-office-365-group-with-dynamic-membership"></a><span data-ttu-id="f5c5e-120">Создание группы Office 365 и управление ей с помощью динамического членства</span><span class="sxs-lookup"><span data-stu-id="f5c5e-120">Creating and managing an Office 365 group with dynamic membership</span></span>
<span data-ttu-id="f5c5e-121">Войдите в систему как администратор клиента и следуйте инструкциям в разделе [Создание динамической группы и проверка состояния](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span><span class="sxs-lookup"><span data-stu-id="f5c5e-121">While logged in as the tenant admin, follow the instructions in [Create a dynamic group and check status](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span></span> <span data-ttu-id="f5c5e-122">При необходимости ознакомьтесь со статьей [динамические правила членства для групп в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span><span class="sxs-lookup"><span data-stu-id="f5c5e-122">As needed, refer to [Dynamic membership rules for groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span></span>

## <a name="create-a-new-team-with-your-o365-group"></a><span data-ttu-id="f5c5e-123">Создание новой команды с помощью группы Office 365</span><span class="sxs-lookup"><span data-stu-id="f5c5e-123">Create a new team with your O365 group</span></span>

<span data-ttu-id="f5c5e-124">Теперь дождитесь вступления в силу изменений в членстве и создайте новую команду, как описано в разделе [расширение существующих групп microsoft 365 с помощью Microsoft Teams](enhance-office-365-groups.md).</span><span class="sxs-lookup"><span data-stu-id="f5c5e-124">Now allow time for the membership changes to take effect, and create a new team  as described in [Enhance Existing Microsoft 365 groups with Microsoft Teams](enhance-office-365-groups.md).</span></span>

## <a name="apply-dynamic-membership-to-an-existing-team"></a><span data-ttu-id="f5c5e-125">Применение динамического членства к существующей команде</span><span class="sxs-lookup"><span data-stu-id="f5c5e-125">Apply dynamic membership to an existing team</span></span>

<span data-ttu-id="f5c5e-126">Вы также можете сделать существующую команду и изменить ее, чтобы она имела динамическую принадлежность, как описано в разделе [изменение членства статических групп на динамический в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).</span><span class="sxs-lookup"><span data-stu-id="f5c5e-126">You can also take an existing team and change it to have a dynamic membership, as described in [Change static group membership to dynamic in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).</span></span>

## <a name="changes-in-client-behavior"></a><span data-ttu-id="f5c5e-127">Изменения в работе клиента</span><span class="sxs-lookup"><span data-stu-id="f5c5e-127">Changes in client behavior</span></span>

<span data-ttu-id="f5c5e-128">После включения динамического членства в группе клиенты Teams больше не смогут управлять участниками группы.</span><span class="sxs-lookup"><span data-stu-id="f5c5e-128">Once dynamic membership is enabled for a team, Teams clients will no longer allow member management for the team.</span></span> <span data-ttu-id="f5c5e-129">Параметры, чтобы добавить участников, изменить роли участников, отправить и утвердить запросы на присоединение, а затем оставить команду скрытыми.</span><span class="sxs-lookup"><span data-stu-id="f5c5e-129">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>
