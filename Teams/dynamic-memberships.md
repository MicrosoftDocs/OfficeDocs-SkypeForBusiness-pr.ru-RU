---
title: Общие сведения о динамическом членстве в командах
author: jambirk
ms.author: jambirk
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Сведения о членстве динамических групп на основании AAD.
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7a96205f1971207f81d6191ef46e1be25e063f4c
ms.sourcegitcommit: 160ced7013c1c46595c4362c2f32c5769b082294
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/27/2018
ms.locfileid: "26699774"
---
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="92207-103">Общие сведения о динамическом членстве в командах</span><span class="sxs-lookup"><span data-stu-id="92207-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="92207-104">Группами Майкрософт поддерживает команды, связанные с Office 365 групп с помощью динамических членства.</span><span class="sxs-lookup"><span data-stu-id="92207-104">Microsoft Teams supports teams associated with Office 365 groups using dynamic membership.</span></span> <span data-ttu-id="92207-105">Динамическое членство позволяет членство в группе определяться с одно или несколько правил, которые проверки определенных атрибутов пользователя в Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="92207-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (AAD).</span></span> <span data-ttu-id="92207-106">Пользователи автоматически при добавлении или удалении на соответствующие команды, как изменения атрибутов пользователя или пользователей присоединении и выходе из клиента.</span><span class="sxs-lookup"><span data-stu-id="92207-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="92207-107">С помощью динамических членство, можно программы установки для определенных групп последователей пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="92207-107">With dynamic membership you can setup teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="92207-108">Возможны следующие сценарии обновления:</span><span class="sxs-lookup"><span data-stu-id="92207-108">Possible scenarios include:</span></span>
- <span data-ttu-id="92207-109">Больницы можно создать четкие группы конструкторов медсестры врачи и surgeons вещание коммуникаций.</span><span class="sxs-lookup"><span data-stu-id="92207-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="92207-110">Это особенно важно, если больница зависит от временных сотрудников.</span><span class="sxs-lookup"><span data-stu-id="92207-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="92207-111">Для студентов можно создать группу для всех факультета в пределах определенного колледжа, включая вспомогательных факультета, часто меняется.</span><span class="sxs-lookup"><span data-stu-id="92207-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="92207-112">Авиакомпании нужны для создания группы для каждой полетов (например, вторник днем работу из Чикаго для Atlanta) и часто изменяемым экипажа полетов автоматически назначен или удалены при необходимости.</span><span class="sxs-lookup"><span data-stu-id="92207-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="92207-113">С помощью этой функции обновления членов указанной группы автоматически на основании определенного набора условий, вместо ручного управления членства.</span><span class="sxs-lookup"><span data-stu-id="92207-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="92207-114">Потребуется лицензий P1 Azure AD Premium и быть членом группы может быть [назначаться администратор клиента](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) для свойства AAD любой пользователь, если у вас есть клиента и учетная запись администратора.</span><span class="sxs-lookup"><span data-stu-id="92207-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's AAD properties provided you have a tenant and an admin account.</span></span> 

<span data-ttu-id="92207-115">Группами Майкрософт может занять от нескольких минут до 2 часов для отражения изменений динамическое членство, когда они вступили в силу в группе Office 365 для команды.</span><span class="sxs-lookup"><span data-stu-id="92207-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Office 365 group for a team.</span></span> 

> [!NOTE]
> - <span data-ttu-id="92207-116">Правила можно определить участников группы, но не группы владельцев.</span><span class="sxs-lookup"><span data-stu-id="92207-116">Rules can define team members, but not team Owners.</span></span>
> - <span data-ttu-id="92207-117">В разделе [ограничения и характеристики для групп Майкрософт](limits-specifications-teams.md) ограничения на размеры группы и канала.</span><span class="sxs-lookup"><span data-stu-id="92207-117">See [Limits and specifications for Microsoft Teams](limits-specifications-teams.md) for current limits on Team and channel sizes.</span></span>

## <a name="creating-and-managing-an-office-365-group-with-dynamic-membership"></a><span data-ttu-id="92207-118">Создание и управление с помощью динамических членства группы с Office 365</span><span class="sxs-lookup"><span data-stu-id="92207-118">Creating and managing an Office 365 group with dynamic membership</span></span>
<span data-ttu-id="92207-119">При входе в систему клиента администрирования, следуйте инструкциям в [Создание динамической группы и проверьте состояние](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span><span class="sxs-lookup"><span data-stu-id="92207-119">While logged in as the tenant Admin, follow the instructions in [Create a dynamic group and check status](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span></span> <span data-ttu-id="92207-120">При необходимости, обратитесь к [динамические правила для групп в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span><span class="sxs-lookup"><span data-stu-id="92207-120">As needed, refer to [Dynamic membership rules for groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span></span>

## <a name="create-a-new-team-with-your-o365-group"></a><span data-ttu-id="92207-121">Создание новой группы с его группе O365</span><span class="sxs-lookup"><span data-stu-id="92207-121">Create a new team with your O365 group</span></span>

<span data-ttu-id="92207-122">Теперь разрешить времени, чтобы вступили в силу изменения членства и создайте новые группы, как описано в [группах улучшения существующих Office 365 с группами Майкрософт](enhance-office-365-groups.md).</span><span class="sxs-lookup"><span data-stu-id="92207-122">Now allow time for the membership changes to take effect, and create a new team  as described in [Enhance Existing Office 365 groups with Microsoft Teams](enhance-office-365-groups.md).</span></span>

## <a name="apply-dynamic-membership-to-an-existing-team"></a><span data-ttu-id="92207-123">Применение динамическое членство для существующих групп</span><span class="sxs-lookup"><span data-stu-id="92207-123">Apply dynamic membership to an existing team</span></span>

<span data-ttu-id="92207-124">Можно использовать существующие группы и изменить его динамических членство, как описано в [изменить членство в группах static для динамического в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).</span><span class="sxs-lookup"><span data-stu-id="92207-124">You can also take an existing team and change it to have a dynamic membership, as described in [Change static group membership to dynamic in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).</span></span>

## <a name="changes-in-client-behavior"></a><span data-ttu-id="92207-125">Изменения в поведении клиента</span><span class="sxs-lookup"><span data-stu-id="92207-125">Changes in client behavior</span></span>

<span data-ttu-id="92207-126">После включения динамической членства для группы группами клиенты больше не позволит элемента управления для группы.</span><span class="sxs-lookup"><span data-stu-id="92207-126">Once dynamic membership is enabled for a team, Teams clients will no longer allow member management for the team.</span></span> <span data-ttu-id="92207-127">Параметры, чтобы добавить элементы, изменить член роли, отправлять и утверждение запросов присоединения и оставьте группа все скрыты.</span><span class="sxs-lookup"><span data-stu-id="92207-127">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>
