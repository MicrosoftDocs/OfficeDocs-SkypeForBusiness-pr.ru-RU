---
title: Управление политиками Teams в Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Сведения о том, как использовать политики Teams в Организации и управлять ими, чтобы управлять тем, какие пользователи могут выполнять в Teams и каналах.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
ms.openlocfilehash: 9ed0bd3aadcde76835bb3d435429785ceaf562a2
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938148"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a><span data-ttu-id="65477-103">Управление политиками Teams в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="65477-103">Manage teams policies in Microsoft Teams</span></span>

<span data-ttu-id="65477-104">Администраторы могут использовать политики Teams в Microsoft Teams для управления тем, какие пользователи в организации могут выполнять в Teams и каналах.</span><span class="sxs-lookup"><span data-stu-id="65477-104">As an admin, you can use teams policies in Microsoft Teams to control what users in your organization can do in teams and channels.</span></span> <span data-ttu-id="65477-105">Например, вы можете указать, разрешено ли пользователям находить закрытые команды в результатах поиска и коллекции групп, а также могут ли пользователи создавать закрытые каналы.</span><span class="sxs-lookup"><span data-stu-id="65477-105">For example, you can set whether users are allowed to discover private teams in search results and in the team gallery and whether users are allowed to create private channels.</span></span>

<span data-ttu-id="65477-106">Управление политиками Teams осуществляется путем **перехода в**  >  **политики** Teams в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="65477-106">You manage teams policies by going to **Teams** > **Teams policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="65477-107">Вы можете использовать глобальную политику (по умолчанию на уровне Организации) или создавать и назначать пользовательские политики.</span><span class="sxs-lookup"><span data-stu-id="65477-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="65477-108">Пользователи вашей организации автоматически получают глобальную политику, если вы не создали и не назначили настраиваемую политику.</span><span class="sxs-lookup"><span data-stu-id="65477-108">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="65477-109">Вы можете изменять глобальную политику или создавать и назначать пользовательские политики.</span><span class="sxs-lookup"><span data-stu-id="65477-109">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="65477-110">После изменения глобальной политики или назначения политики может потребоваться несколько часов, чтобы изменения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="65477-110">After you edit the global policy or assign a policy, it can take a few hours for changes to take effect.</span></span>

## <a name="create-a-custom-teams-policy"></a><span data-ttu-id="65477-111">Создание настраиваемой политики рабочих групп</span><span class="sxs-lookup"><span data-stu-id="65477-111">Create a custom teams policy</span></span>

1. <span data-ttu-id="65477-112">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел политики **Teams**Teams  >  **Teams policies**.</span><span class="sxs-lookup"><span data-stu-id="65477-112">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="65477-113">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="65477-113">Click **Add**.</span></span>
3. <span data-ttu-id="65477-114">Введите имя и описание для политики.</span><span class="sxs-lookup"><span data-stu-id="65477-114">Enter a name and description for the policy.</span></span>

    ![Снимок экрана: параметры политики Teams](media/teams-policies.png)
4. <span data-ttu-id="65477-116">Выберите нужные параметры.</span><span class="sxs-lookup"><span data-stu-id="65477-116">Choose the settings that you want:</span></span>

- <span data-ttu-id="65477-117">**Знакомство со закрытыми группами** (в частном<a name="discoverteams"> </a> предварительной версии): Включите этот параметр, чтобы разрешить пользователям находить частные команды в результатах поиска и коллекции групп.</span><span class="sxs-lookup"><span data-stu-id="65477-117">**Discover private teams** (in private preview):<a name="discoverteams"> </a> Turn on this setting to allow users to discover private teams in search results and in the team gallery.</span></span>
- <span data-ttu-id="65477-118">**Создание частных каналов**: <a name="createchannels"> </a>включите этот параметр, чтобы разрешить пользователям создавать закрытые каналы.</span><span class="sxs-lookup"><span data-stu-id="65477-118">**Create private channels**: <a name="createchannels"> </a>Turn on this setting to allow users to create private channels.</span></span>

5. <span data-ttu-id="65477-119">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="65477-119">Click **Save**.</span></span>

## <a name="edit-a-teams-policy"></a><span data-ttu-id="65477-120">Изменение политики Teams</span><span class="sxs-lookup"><span data-stu-id="65477-120">Edit a teams policy</span></span>

<span data-ttu-id="65477-121">Вы можете изменить глобальную политику или созданные вами пользовательские политики.</span><span class="sxs-lookup"><span data-stu-id="65477-121">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="65477-122">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел политики **Teams**Teams  >  **Teams policies**.</span><span class="sxs-lookup"><span data-stu-id="65477-122">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="65477-123">Выберите политику, щелкнув слева от ее имени, а затем нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="65477-123">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="65477-124">Включите или выключите нужные параметры, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="65477-124">Turn on or turn off the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-teams-policy-to-users"></a><span data-ttu-id="65477-125">Назначение пользователям политики групп</span><span class="sxs-lookup"><span data-stu-id="65477-125">Assign a custom teams policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="65477-126">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="65477-126">Related topics</span></span>

[<span data-ttu-id="65477-127">Управление обнаружением приватных команд в Teams</span><span class="sxs-lookup"><span data-stu-id="65477-127">Manage discovery of private teams in Teams</span></span>](manage-discovery-of-private-teams.md)

[<span data-ttu-id="65477-128">Личные каналы в Teams</span><span class="sxs-lookup"><span data-stu-id="65477-128">Private channels in Teams</span></span>](private-channels.md)

[<span data-ttu-id="65477-129">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="65477-129">Assign policies to your users in Teams</span></span>](assign-policies.md)
