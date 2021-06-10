---
title: Управление политиками команд в Microsoft Teams
author: cichur
ms.author: v-cichur
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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
description: Узнайте, как использовать политики команд в организации и управлять ими, чтобы контролировать то, что пользователи могут делать в командах и каналах.
ms.openlocfilehash: 81541c08ac963f0bcef18ba589b2341915c20d5d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094209"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a><span data-ttu-id="96197-103">Управление политиками команд в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="96197-103">Manage teams policies in Microsoft Teams</span></span>

<span data-ttu-id="96197-104">Как администратор вы можете использовать политики команд в Microsoft Teams управлять тем, что пользователи в вашей организации могут делать в командах и каналах.</span><span class="sxs-lookup"><span data-stu-id="96197-104">As an admin, you can use teams policies in Microsoft Teams to control what users in your organization can do in teams and channels.</span></span> <span data-ttu-id="96197-105">Например, вы можете разрешить пользователям создавать частные каналы.</span><span class="sxs-lookup"><span data-stu-id="96197-105">For example, you can set whether users are allowed to create private channels.</span></span>

<span data-ttu-id="96197-106">Вы управляете политиками команд, **Teams** Teams политики в  >   Microsoft Teams администрирования.</span><span class="sxs-lookup"><span data-stu-id="96197-106">You manage teams policies by going to **Teams** > **Teams policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="96197-107">Вы можете использовать глобальную (по умолчанию в пределах организации) политику или создавать и присваивать настраиваемые политики.</span><span class="sxs-lookup"><span data-stu-id="96197-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="96197-108">Пользователи вашей организации автоматически получают глобальную политику, если вы не создали и не назначили настраиваемую политику.</span><span class="sxs-lookup"><span data-stu-id="96197-108">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="96197-109">Вы можете изменить глобальную политику или создать и назначить настраиваемую политику.</span><span class="sxs-lookup"><span data-stu-id="96197-109">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="96197-110">После изменения глобальной политики или назначения политики может занять несколько часов, чтобы изменения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="96197-110">After you edit the global policy or assign a policy, it can take a few hours for changes to take effect.</span></span>

## <a name="create-a-custom-teams-policy"></a><span data-ttu-id="96197-111">Создание настраиваемой политики teams</span><span class="sxs-lookup"><span data-stu-id="96197-111">Create a custom teams policy</span></span>

1. <span data-ttu-id="96197-112">В левой области навигации Центра администрирования Microsoft Teams перейдите к **Teams**  >  **Teams политики**.</span><span class="sxs-lookup"><span data-stu-id="96197-112">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="96197-113">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="96197-113">Click **Add**.</span></span>
3. <span data-ttu-id="96197-114">Введите имя и описание для политики.</span><span class="sxs-lookup"><span data-stu-id="96197-114">Enter a name and description for the policy.</span></span>

    ![Снимок экрана: параметры политики teams](media/teams-policies.png)
4. <span data-ttu-id="96197-116">Включите или отключите <a name="createchannels"></a> **создание** частных каналов в зависимости от того, хотите ли вы разрешить пользователям создавать частные каналы.</span><span class="sxs-lookup"><span data-stu-id="96197-116">Turn on or turn off **Create private channels**, <a name="createchannels"> </a> depending on whether you want to allow users to create private channels.</span></span>

5. <span data-ttu-id="96197-117">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="96197-117">Click **Save**.</span></span>

## <a name="edit-a-teams-policy"></a><span data-ttu-id="96197-118">Изменение политики teams</span><span class="sxs-lookup"><span data-stu-id="96197-118">Edit a teams policy</span></span>

<span data-ttu-id="96197-119">Вы можете изменить глобальную политику или любые настраиваемые политики, которые вы создаете.</span><span class="sxs-lookup"><span data-stu-id="96197-119">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="96197-120">В левой области навигации Центра администрирования Microsoft Teams перейдите к **Teams**  >  **Teams политики**.</span><span class="sxs-lookup"><span data-stu-id="96197-120">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="96197-121">Выберите политику, щелкнув слева от ее имени, а затем нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="96197-121">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="96197-122">Включите или отключите нужные параметры, а затем нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="96197-122">Turn on or turn off the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-teams-policy-to-users"></a><span data-ttu-id="96197-123">Назначение настраиваемой политики teams пользователям</span><span class="sxs-lookup"><span data-stu-id="96197-123">Assign a custom teams policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="96197-124">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="96197-124">Related topics</span></span>

[<span data-ttu-id="96197-125">Закрытые каналы в Teams</span><span class="sxs-lookup"><span data-stu-id="96197-125">Private channels in Teams</span></span>](private-channels.md)

[<span data-ttu-id="96197-126">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="96197-126">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="96197-127">New-CsTeamsChannelsPolicy</span><span class="sxs-lookup"><span data-stu-id="96197-127">New-CsTeamsChannelsPolicy</span></span>](/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)