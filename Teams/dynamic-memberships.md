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
description: Узнайте, как Microsoft Teams поддерживает команды, связанные с группами Microsoft 365, с помощью динамического участия.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 75bd058d79b1f54a40ad0e42207178c9c29d08cd
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583928"
---
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="5fd34-103">Общие сведения о динамическом членстве в командах</span><span class="sxs-lookup"><span data-stu-id="5fd34-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="5fd34-104">Microsoft Teams поддерживает команды, связанные с группами Microsoft 365, используя *динамическое членство.*</span><span class="sxs-lookup"><span data-stu-id="5fd34-104">Microsoft Teams supports teams associated with Microsoft 365 groups by using *dynamic membership*.</span></span> <span data-ttu-id="5fd34-105">Динамическое членство позволяет определять членство в команде с помощью одного или более правил, которые проверяют на определенные атрибуты пользователей в Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="5fd34-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="5fd34-106">Пользователи автоматически добавляются в правильные группы или удаляются из-за изменения их атрибутов или перейти из клиента.</span><span class="sxs-lookup"><span data-stu-id="5fd34-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="5fd34-107">С помощью динамического участия вы можете настроить команды для определенных групп пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="5fd34-107">With dynamic membership you can set up teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="5fd34-108">Возможные сценарии:</span><span class="sxs-lookup"><span data-stu-id="5fd34-108">Possible scenarios include:</span></span>
- <span data-ttu-id="5fd34-109">В больнице можно создавать отдельные команды для медсестр, врача и медсестр для трансляции коммуникаций.</span><span class="sxs-lookup"><span data-stu-id="5fd34-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="5fd34-110">Это особенно важно, если в больнице работают сотрудники временных служб.</span><span class="sxs-lookup"><span data-stu-id="5fd34-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="5fd34-111">Университет может создать команду для всех преподавателей в рамках определенного учебного заведения, в том числе для adjunct-преподавателей, которые часто меняются.</span><span class="sxs-lookup"><span data-stu-id="5fd34-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="5fd34-112">Авиакомпании хотят создать команду для каждого авиарейса (например, после полудня во вторник от Чикаго до Атланты) и при необходимости часто меняя летную бригаду.</span><span class="sxs-lookup"><span data-stu-id="5fd34-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="5fd34-113">При использовании этой функции участники группы обновляются автоматически на основе определенного набора критериев, а не вручную управляют членством.</span><span class="sxs-lookup"><span data-stu-id="5fd34-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="5fd34-114">Для этого требуются лицензии Azure AD Premium [](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) P1 и членство в группах, которые может на должны быть назначены администратором клиента для свойств Azure AD пользователя при условии, что у вас есть учетная запись клиента и администратора.</span><span class="sxs-lookup"><span data-stu-id="5fd34-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's Azure AD properties provided you have a tenant and an admin account.</span></span>

<span data-ttu-id="5fd34-115">После вступления изменений в группу Microsoft 365 для команды Microsoft Teams может потребоваться от нескольких минут до 2 часов.</span><span class="sxs-lookup"><span data-stu-id="5fd34-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Microsoft 365 group for a team.</span></span>

> [!NOTE]
> - <span data-ttu-id="5fd34-116">Правила определяют, кто является участником команды, а кто — владельцем.</span><span class="sxs-lookup"><span data-stu-id="5fd34-116">Rules can define who is a team member, but not who is a team owner.</span></span>
> - <span data-ttu-id="5fd34-117">Текущие ограничения на размеры групп и каналов см. в спецификации и ограничениях [для Microsoft Teams.](limits-specifications-teams.md)</span><span class="sxs-lookup"><span data-stu-id="5fd34-117">See [Limits and specifications for Microsoft Teams](limits-specifications-teams.md) for current limits on team and channel sizes.</span></span>
> - <span data-ttu-id="5fd34-118">Владельцы не могут добавлять и удалять пользователей в качестве членов команды, поскольку они определяются динамическими правилами группы.</span><span class="sxs-lookup"><span data-stu-id="5fd34-118">Owners will not be able to add or remove users as members of the team, since members are defined by dynamic group rules.</span></span>
> -    <span data-ttu-id="5fd34-119">Участники не смогут оставить команды в динамической группе.</span><span class="sxs-lookup"><span data-stu-id="5fd34-119">Members will not be able to leave teams backed by dynamic groups.</span></span>

## <a name="creating-and-managing-a-microsoft-365-group-with-dynamic-membership"></a><span data-ttu-id="5fd34-120">Создание группы Microsoft 365 и управление ней с динамическим членством</span><span class="sxs-lookup"><span data-stu-id="5fd34-120">Creating and managing a Microsoft 365 group with dynamic membership</span></span>

<span data-ttu-id="5fd34-121">Вы вошли в систему как администратор клиента, следуя инструкциям в окнах "Создание [динамической группы" и проверив состояние.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)</span><span class="sxs-lookup"><span data-stu-id="5fd34-121">While logged in as the tenant admin, follow the instructions in [Create a dynamic group and check status](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span></span> <span data-ttu-id="5fd34-122">При необходимости обратитесь к правилам [динамического участия в группах в Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)</span><span class="sxs-lookup"><span data-stu-id="5fd34-122">As needed, refer to [Dynamic membership rules for groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span></span>

## <a name="create-a-new-team-with-your-microsoft-365-group"></a><span data-ttu-id="5fd34-123">Создание команды с помощью группы Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5fd34-123">Create a new team with your Microsoft 365 group</span></span>

<span data-ttu-id="5fd34-124">Теперь дайте время на вступление изменений в состав и создайте новую команду, как описано в описании в описании функции "Создание команды [из существующей группы".](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)</span><span class="sxs-lookup"><span data-stu-id="5fd34-124">Now allow time for the membership changes to take effect, and create a new team  as described in [Create a team from an existing group](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865).</span></span>

## <a name="apply-dynamic-membership-to-an-existing-team"></a><span data-ttu-id="5fd34-125">Применение динамического участия к существующей команде</span><span class="sxs-lookup"><span data-stu-id="5fd34-125">Apply dynamic membership to an existing team</span></span>

<span data-ttu-id="5fd34-126">Вы также можете использовать существующую команду и изменить ее на динамическое членство, как описано в описании изменения статического членства в группах [в Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)</span><span class="sxs-lookup"><span data-stu-id="5fd34-126">You can also take an existing team and change it to have a dynamic membership, as described in [Change static group membership to dynamic in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).</span></span>

## <a name="changes-in-client-behavior"></a><span data-ttu-id="5fd34-127">Изменения в поведение клиента</span><span class="sxs-lookup"><span data-stu-id="5fd34-127">Changes in client behavior</span></span>

<span data-ttu-id="5fd34-128">После включения динамического участия в команде клиенты Teams больше не позволяют ей использовать управление членами.</span><span class="sxs-lookup"><span data-stu-id="5fd34-128">Once dynamic membership is enabled for a team, Teams clients will no longer allow member management for the team.</span></span> <span data-ttu-id="5fd34-129">Параметры добавления участников, изменения ролей участников, отправки и утверждения запросов на вступление в команду и покидают команду, скрыты.</span><span class="sxs-lookup"><span data-stu-id="5fd34-129">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>
