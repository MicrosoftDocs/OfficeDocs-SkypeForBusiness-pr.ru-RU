---
title: Назначение пакетов политики пользователям и группам
author: KarliStites
ms.author: kastites
ms.reviewer: tomkau, saragava, ritikag, jastark
manager: serdars
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
description: Узнайте о различных способах назначения пакетов политики пользователям и группам в Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: e70d5e2bf0db6cb7dfd93e35a8207fce61fa75fd
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796833"
---
# <a name="assign-policy-packages-to-users-and-groups"></a><span data-ttu-id="e7396-103">Назначение пакетов политики пользователям и группам</span><span class="sxs-lookup"><span data-stu-id="e7396-103">Assign policy packages to users and groups</span></span>

<span data-ttu-id="e7396-104">В этой статье рассматриваются различные способы назначения пакетов политики пользователям и группам в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e7396-104">This article reviews the different ways to assign policy packages to users and groups in Microsoft Teams.</span></span> <span data-ttu-id="e7396-105">Перед чтением обязательно прочитайте статью Назначение политик в Teams [- начало работы.](policy-assignment-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e7396-105">Before reading, be sure you've read [Assign policies in Teams - getting started](policy-assignment-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e7396-106">Для получения назначения пользовательского пакета политики каждому пользователю потребуется надстройка Advanced Communications.</span><span class="sxs-lookup"><span data-stu-id="e7396-106">Each user will require the Advanced Communications add-on in order to receive a custom policy package assignment.</span></span> <span data-ttu-id="e7396-107">Дополнительные сведения см. в [этой](/microsoftteams/teams-add-on-licensing/advanced-communications)Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e7396-107">For more information, see [Advanced Communications add-on for Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).</span></span>

## <a name="assign-a-policy-package-to-users"></a><span data-ttu-id="e7396-108">Назначение пакета политики пользователям</span><span class="sxs-lookup"><span data-stu-id="e7396-108">Assign a policy package to users</span></span>

<span data-ttu-id="e7396-109">Пакет политики в Teams — это набор предопределевших политик и параметров политики, которые можно назначить пользователям с одинаковыми или похожими ролями в организации.</span><span class="sxs-lookup"><span data-stu-id="e7396-109">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="e7396-110">Каждый пакет политики предназначен для роли пользователя и содержит предварительно заранее задав политики и параметры политики, которые поддерживают типичные для нее действия.</span><span class="sxs-lookup"><span data-stu-id="e7396-110">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="e7396-111">Некоторые примеры пакетов политики: пакет для образования (преподаватель) и пакет для медицинского обслуживания (медицинского работника).</span><span class="sxs-lookup"><span data-stu-id="e7396-111">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span> <span data-ttu-id="e7396-112">Дополнительные информации см. в [этой](manage-policy-packages.md)Teams.</span><span class="sxs-lookup"><span data-stu-id="e7396-112">To learn more, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="e7396-113">Назначение пакета политики одному пользователю</span><span class="sxs-lookup"><span data-stu-id="e7396-113">Assign a policy package to one user</span></span>

1. <span data-ttu-id="e7396-114">В левой области навигации центра администрирования Microsoft Teams перейдите **в** меню Пользователи и выберите пользователя.</span><span class="sxs-lookup"><span data-stu-id="e7396-114">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="e7396-115">На странице пользователя выберите Политики **,** а затем рядом с пакетом **политики** выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="e7396-115">On the user's page, select **Policies**, and then next to **Policy package**, select **Edit**.</span></span>
3. <span data-ttu-id="e7396-116">В области **Назначение пакета политики** выберите пакет, который вы хотите назначить, и выберите сохранить . </span><span class="sxs-lookup"><span data-stu-id="e7396-116">In the **Assign policy package** pane, select the package you want to assign, and then select **Save**.</span></span>

![Teams в Центре администрирования для назначения пользователю пакета политики](media/assign-policypackages-user.png)

### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="e7396-118">Назначение пакета политики нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="e7396-118">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="e7396-119">В левой области навигации Центра администрирования Microsoft Teams перейдите в пакеты политики **,** а затем выберите пакет политики, который вы хотите назначить, щелкнув слева от имени пакета.</span><span class="sxs-lookup"><span data-stu-id="e7396-119">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="e7396-120">Выберите **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="e7396-120">Select **Manage users**.</span></span>
3. <span data-ttu-id="e7396-121">В области **Управление пользователями** выполните поиск по отображаемому имени или по имени пользователя, выберите имя и нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e7396-121">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="e7396-122">Повторите это действие для каждого пользователя, которого нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="e7396-122">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="e7396-123">Завершив добавление пользователей, выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e7396-123">When you're finished adding users, select **Save**.</span></span>

![Teams в Центре администрирования для назначения пакета политики нескольким пользователям](media/assign-policypackages-multipleusers.png)

## <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="e7396-125">Назначение пакета политики группе</span><span class="sxs-lookup"><span data-stu-id="e7396-125">Assign a policy package to a group</span></span>

<span data-ttu-id="e7396-126">Назначение пакетов политики группам позволяет назначать несколько политик группе пользователей, например группе безопасности или группе рассылки.</span><span class="sxs-lookup"><span data-stu-id="e7396-126">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="e7396-127">Назначение политики распространяется на участников группы в соответствии с правилами очередности.</span><span class="sxs-lookup"><span data-stu-id="e7396-127">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="e7396-128">При добавлении или удалении участников группы, назначения политик для них обновляются соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="e7396-128">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="e7396-129">Назначение пакетов политики группам рекомендуется для групп до 50 000 пользователей, но оно также будет работать с более крупными группами.</span><span class="sxs-lookup"><span data-stu-id="e7396-129">Policy package assignment to groups is recommended for groups of up to 50,000 users, but it will also work with larger groups.</span></span>

<span data-ttu-id="e7396-130">При назначении пакета политики он сразу же назначается группе.</span><span class="sxs-lookup"><span data-stu-id="e7396-130">When you assign the policy package, it's immediately assigned to the group.</span></span> <span data-ttu-id="e7396-131">Однако распространение назначения политики на участников группы выполняется в фоновом режиме и может занять некоторое время в зависимости от размера группы.</span><span class="sxs-lookup"><span data-stu-id="e7396-131">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="e7396-132">То же самое происходит, если политика не назначена группе, а участники добавляются в нее или удаляются из нее.</span><span class="sxs-lookup"><span data-stu-id="e7396-132">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e7396-133">Перед началом работы важно понимать[(правила](assign-policies-users-and-groups.md#precedence-rules)приоритета) и ([ранжирование назначений группы).](assign-policies-users-and-groups.md#group-assignment-ranking)</span><span class="sxs-lookup"><span data-stu-id="e7396-133">Before you get started, it's important to understand ([precedence rules](assign-policies-users-and-groups.md#precedence-rules)) and ([group assignment ranking](assign-policies-users-and-groups.md#group-assignment-ranking)).</span></span> <span data-ttu-id="e7396-134">Убедитесь, что вы читаете и понимаете понятия[в](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)( Что необходимо знать о назначении политик группам) ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="e7396-134">Make sure you read and understand the concepts in ([What you need to know about policy assignment to groups](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)) earlier in this article.</span></span>

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a><span data-ttu-id="e7396-135">Назначение пакета политики группе пользователей в Центре администрирования</span><span class="sxs-lookup"><span data-stu-id="e7396-135">Assign a policy package to a group of users in the admin center</span></span>

1. <span data-ttu-id="e7396-136">Войдите в Центр администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="e7396-136">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="e7396-137">На левой странице навигации перейдите на страницу пакета политики.</span><span class="sxs-lookup"><span data-stu-id="e7396-137">In the left navigation, go to the policy package page.</span></span>
3. <span data-ttu-id="e7396-138">Выберите вкладку Назначение групповой политики.</span><span class="sxs-lookup"><span data-stu-id="e7396-138">Select the Group policy assignment tab.</span></span>
4. <span data-ttu-id="e7396-139">Выберите **Добавить группу,** а затем в области Назначение пакета политики группе сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="e7396-139">Select **Add group**, and then in the Assign a policy package to group pane, do the following:</span></span>

    <span data-ttu-id="e7396-140">а)</span><span class="sxs-lookup"><span data-stu-id="e7396-140">a.</span></span> <span data-ttu-id="e7396-141">Найщите и добавьте группу, для нее нужно назначить пакет политики.</span><span class="sxs-lookup"><span data-stu-id="e7396-141">Search for and add the group you want to assign the policy package to.</span></span>

    <span data-ttu-id="e7396-142">б)</span><span class="sxs-lookup"><span data-stu-id="e7396-142">b.</span></span> <span data-ttu-id="e7396-143">Выберите пакет политики.</span><span class="sxs-lookup"><span data-stu-id="e7396-143">Select a policy package.</span></span>

    <span data-ttu-id="e7396-144">в.</span><span class="sxs-lookup"><span data-stu-id="e7396-144">c.</span></span> <span data-ttu-id="e7396-145">Заведите ранжирование для каждого типа политики.</span><span class="sxs-lookup"><span data-stu-id="e7396-145">Set the ranking for each policy type.</span></span>

    <span data-ttu-id="e7396-146">г.</span><span class="sxs-lookup"><span data-stu-id="e7396-146">d.</span></span> <span data-ttu-id="e7396-147">Выберите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="e7396-147">Select **Apply**.</span></span>

![показывает назначение групповой политики](media/group-pkg-assignment.png)

5. <span data-ttu-id="e7396-149">Чтобы управлять ранжированием для определенного типа политики, перейдите на страницу политики.</span><span class="sxs-lookup"><span data-stu-id="e7396-149">To manage ranking for a specific policy type, navigate to the specific policy page.</span></span>
6. <span data-ttu-id="e7396-150">Чтобы перена назначение пакета политики группе, сначала удалите назначение групповой политики.</span><span class="sxs-lookup"><span data-stu-id="e7396-150">To reassign a policy package to a group, first remove the group policy assignment.</span></span> <span data-ttu-id="e7396-151">Затем следуйте этим шагам, чтобы назначить пакет политики группе.</span><span class="sxs-lookup"><span data-stu-id="e7396-151">Then, follow the steps above to assign the policy package to a group.</span></span>

### <a name="work-with-powershell"></a><span data-ttu-id="e7396-152">Работа с PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7396-152">Work with PowerShell</span></span>

#### <a name="get-the-teams-powershell-module"></a><span data-ttu-id="e7396-153">Получить модуль Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7396-153">Get the Teams PowerShell module</span></span>

<span data-ttu-id="e7396-154">Пошаговую инструкцию см. в [Teams PowerShell.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="e7396-154">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-package-to-a-group-of-users"></a><span data-ttu-id="e7396-155">Назначение пакета политики группе пользователей</span><span class="sxs-lookup"><span data-stu-id="e7396-155">Assign a policy package to a group of users</span></span>

<span data-ttu-id="e7396-156">Чтобы назначить группе пакет политики, используйте [cmdlet Grant-CsGroupPolicyPackageAssignment.](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment)</span><span class="sxs-lookup"><span data-stu-id="e7396-156">Use the [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet to assign a policy package to a group.</span></span> <span data-ttu-id="e7396-157">Группу можно указать с помощью ИД объекта, SIP-адреса или адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="e7396-157">You can specify a group by using the object ID, SIP address, or email address.</span></span> <span data-ttu-id="e7396-158">При назначении пакета политики укажите[(ранжирование](assign-policies-users-and-groups.md#group-assignment-ranking)назначений группы) для каждого типа политики в пакете политики.</span><span class="sxs-lookup"><span data-stu-id="e7396-158">When you assign the policy package, specify a ([group assignment ranking](assign-policies-users-and-groups.md#group-assignment-ranking)) for each policy type in the policy package.</span></span>

<span data-ttu-id="e7396-159">В этом примере пакет политики Education_Teacher назначается группе со ранжированием заданий 1 для TeamsAppSetupPolicy и TeamsMeetingBroadcastPolicy и ранжированием 2 для TeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="e7396-159">In this example, we assign the Education_Teacher policy package to a group with an assignment ranking of 1 for TeamsAppSetupPolicy and TeamsMeetingBroadcastPolicy and a ranking of 2 for TeamsMeetingPolicy.</span></span>

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="e7396-160">Назначение пакета политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="e7396-160">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="e7396-161">При назначении пакетного пакета политики вы можете одновременно назначить пакет политики большому набору пользователей, не пользуясь сценарием.</span><span class="sxs-lookup"><span data-stu-id="e7396-161">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="e7396-162">С помощью [нового CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) можно отправить пакет пользователей и пакет политики, который вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="e7396-162">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="e7396-163">Задания будут обрабатываться в фоновом режиме, а для каждого пакета будет создан идентификатор операции.</span><span class="sxs-lookup"><span data-stu-id="e7396-163">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="e7396-164">Затем можно использовать для отслеживания хода выполнения и состояния заданий в пакете с помощью [cmdlet Get-CsBatchPolicyAssignmentOperation.](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="e7396-164">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="e7396-165">Укажите пользователей по их ИД объекта или SIP-адресу.</span><span class="sxs-lookup"><span data-stu-id="e7396-165">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="e7396-166">SIP-адрес пользователя часто имеет то же значение, что и имя директора-пользователя (UPN) или адрес электронной почты, но это не обязательно.</span><span class="sxs-lookup"><span data-stu-id="e7396-166">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this isn't required.</span></span> <span data-ttu-id="e7396-167">Если имя пользователя указано с помощью его имя-пользователя или электронной почты, но его значение отличается от SIP-адреса, назначение политики для него не удастся.</span><span class="sxs-lookup"><span data-stu-id="e7396-167">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="e7396-168">Если пакет содержит дубликатов пользователей, они будут удалены из пакета до обработки, а состояние будет предоставлено только для уникальных пользователей, оставшихся в пакете.</span><span class="sxs-lookup"><span data-stu-id="e7396-168">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="e7396-169">Пакет содержит до 5000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="e7396-169">A batch contains up to 5,000 users.</span></span> <span data-ttu-id="e7396-170">Для получения наилучших результатов не от отправки нескольких пакетов за один раз.</span><span class="sxs-lookup"><span data-stu-id="e7396-170">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="e7396-171">Разрешить обработку пакетов перед отправкой дополнительных пакетов.</span><span class="sxs-lookup"><span data-stu-id="e7396-171">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="use-the-teams-powershell-module"></a><span data-ttu-id="e7396-172">Использование модуля Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7396-172">Use the Teams PowerShell module</span></span>

<span data-ttu-id="e7396-173">Чтобы установить модуль [PowerShell Microsoft Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams) запустите следующую:</span><span class="sxs-lookup"><span data-stu-id="e7396-173">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="e7396-174">Установите версию 1.0.5 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="e7396-174">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="e7396-175">Чтобы подключиться к Teams и начать сеанс, запустите следующее:</span><span class="sxs-lookup"><span data-stu-id="e7396-175">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="e7396-176">Когда вам будет предложено, войте в учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="e7396-176">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-policy-packages-to-a-batch-of-users"></a><span data-ttu-id="e7396-177">Назначение пакетов политики для пакета пользователей</span><span class="sxs-lookup"><span data-stu-id="e7396-177">Assign policy packages to a batch of users</span></span>

<span data-ttu-id="e7396-178">В этом примере для назначения пакета политики пакету пользователей используется Education_PrimaryStudent [New-CsBatchPolicyAssignmentOperation.](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="e7396-178">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a><span data-ttu-id="e7396-179">См. состояние пакета назначения</span><span class="sxs-lookup"><span data-stu-id="e7396-179">See the status of a batch assignment</span></span>

<span data-ttu-id="e7396-180">Чтобы получить состояние пакета назначения, где OperationId — это код операции, возвращаемый этим cmdlet для заданного пакета, запустите ```New-CsBatchPolicyAssignmentOperation``` следующую операцию:</span><span class="sxs-lookup"><span data-stu-id="e7396-180">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="e7396-181">Если выходные данные показывают, что произошла ошибка, запустите следующую, чтобы получить дополнительные сведения об ошибках, которые находятся в ```UserState``` свойстве.</span><span class="sxs-lookup"><span data-stu-id="e7396-181">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="e7396-182">Подробнее см. в [get-CsBatchPolicyAssignmentOperation.](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="e7396-182">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e7396-183">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="e7396-183">Related topics</span></span>

- [<span data-ttu-id="e7396-184">Управление Teams политиками</span><span class="sxs-lookup"><span data-stu-id="e7396-184">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
- [<span data-ttu-id="e7396-185">Управление пакетами политик в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e7396-185">Manage policy packages in Microsoft Teams</span></span>](manage-policy-packages.md)
- [<span data-ttu-id="e7396-186">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="e7396-186">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="e7396-187">Назначение политик в Teams — начало работы</span><span class="sxs-lookup"><span data-stu-id="e7396-187">Assign policies in Teams - getting started</span></span>](policy-assignment-overview.md)
