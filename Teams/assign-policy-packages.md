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
ms.openlocfilehash: 0266cb5c34a13df0dac62be2258134e553a357d8
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574350"
---
# <a name="assign-policy-packages-to-users-and-groups"></a><span data-ttu-id="15f67-103">Назначение пакетов политики пользователям и группам</span><span class="sxs-lookup"><span data-stu-id="15f67-103">Assign policy packages to users and groups</span></span>

<span data-ttu-id="15f67-104">В этой статье рассматриваются различные способы назначения пакетов политики пользователям и группам в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="15f67-104">This article reviews the different ways to assign policy packages to users and groups in Microsoft Teams.</span></span> <span data-ttu-id="15f67-105">Прежде чем читать, прочитайте статью ["Назначение политик в Teams — начало работы".](policy-assignment-overview.md)</span><span class="sxs-lookup"><span data-stu-id="15f67-105">Before reading, be sure you've read [Assign policies in Teams - getting started](policy-assignment-overview.md).</span></span>

## <a name="assign-a-policy-package-to-users"></a><span data-ttu-id="15f67-106">Назначение пакета политики пользователям</span><span class="sxs-lookup"><span data-stu-id="15f67-106">Assign a policy package to users</span></span>

<span data-ttu-id="15f67-107">Пакет политики в Teams — это набор предопределельных политик и параметров политики, которые можно назначать пользователям с одинаковыми или похожими ролями в организации.</span><span class="sxs-lookup"><span data-stu-id="15f67-107">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="15f67-108">Каждый пакет политики предназначен для роли пользователя и содержит предопределять политики и параметры политики, которые поддерживают типичные для нее действия.</span><span class="sxs-lookup"><span data-stu-id="15f67-108">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="15f67-109">Примерами пакетов политики могут быть пакеты для образовательных учреждений (для преподавателей) и медицинских учреждений (клинические работники).</span><span class="sxs-lookup"><span data-stu-id="15f67-109">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span> <span data-ttu-id="15f67-110">Дополнительные узнать см. в [подмносях "Управление пакетами политики в Teams".](manage-policy-packages.md)</span><span class="sxs-lookup"><span data-stu-id="15f67-110">To learn more, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="15f67-111">Назначение пакета политики одному пользователю</span><span class="sxs-lookup"><span data-stu-id="15f67-111">Assign a policy package to one user</span></span>

1. <span data-ttu-id="15f67-112">В левой области навигации Центра администрирования Microsoft Teams перейдите в меню **"Пользователи"** и выберите пользователя.</span><span class="sxs-lookup"><span data-stu-id="15f67-112">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="15f67-113">На странице пользователя выберите "Политики", а затем рядом с пакетом политики **выберите** **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="15f67-113">On the user's page, select **Policies**, and then next to **Policy package**, select **Edit**.</span></span>
3. <span data-ttu-id="15f67-114">В области **назначения пакета политики** выберите пакет, который вы хотите назначить, и выберите **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="15f67-114">In the **Assign policy package** pane, select the package you want to assign, and then select **Save**.</span></span>

![Снимок экрана Центра администрирования Teams для назначения пакета политики пользователю](media/assign-policypackages-user.png)

### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="15f67-116">Назначение пакета политики нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="15f67-116">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="15f67-117">В левой области навигации Центра администрирования Microsoft Teams перейдите к пакетам **политики,** а затем выберите пакет политики, который вы хотите назначить, щелкнув слева от его имени.</span><span class="sxs-lookup"><span data-stu-id="15f67-117">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="15f67-118">Выберите **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="15f67-118">Select **Manage users**.</span></span>
3. <span data-ttu-id="15f67-119">В области **Управление пользователями** выполните поиск по отображаемому имени или по имени пользователя, выберите имя и нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="15f67-119">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="15f67-120">Повторите это действие для каждого пользователя, которого нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="15f67-120">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="15f67-121">Завершив добавление пользователей, выберите **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="15f67-121">When you're finished adding users, select **Save**.</span></span>

![Снимок экрана Центра администрирования Teams для назначения пакета политики нескольким пользователям](media/assign-policypackages-multipleusers.png)

## <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="15f67-123">Назначение пакета политики группе</span><span class="sxs-lookup"><span data-stu-id="15f67-123">Assign a policy package to a group</span></span>

<span data-ttu-id="15f67-124">Назначение пакетов политики группам позволяет назначать несколько политик группе пользователей, например группе безопасности или группе рассылки.</span><span class="sxs-lookup"><span data-stu-id="15f67-124">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="15f67-125">Назначение политики распространяется на участников группы в соответствии с правилами очередности.</span><span class="sxs-lookup"><span data-stu-id="15f67-125">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="15f67-126">При добавлении или удалении участников группы, назначения политик для них обновляются соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="15f67-126">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="15f67-127">Назначение пакетов политики группам рекомендуется для групп до 50 000 пользователей, но оно также будет работать с более крупными группами.</span><span class="sxs-lookup"><span data-stu-id="15f67-127">Policy package assignment to groups is recommended for groups of up to 50,000 users, but it will also work with larger groups.</span></span>

<span data-ttu-id="15f67-128">Когда вы назначаете пакет политики, он сразу же назначается группе.</span><span class="sxs-lookup"><span data-stu-id="15f67-128">When you assign the policy package, it's immediately assigned to the group.</span></span> <span data-ttu-id="15f67-129">Однако распространение назначения политики на участников группы выполняется в фоновом режиме и может занять некоторое время в зависимости от размера группы.</span><span class="sxs-lookup"><span data-stu-id="15f67-129">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="15f67-130">То же самое происходит, если политика не назначена группе, а также когда участники добавляются в группу или удаляются из нее.</span><span class="sxs-lookup"><span data-stu-id="15f67-130">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="15f67-131">Прежде чем начать, важно понимать (правила[приоритета)](assign-policies-users-and-groups.md#precedence-rules)и (ранжирование[назначений группы).](assign-policies-users-and-groups.md#group-assignment-ranking)</span><span class="sxs-lookup"><span data-stu-id="15f67-131">Before you get started, it's important to understand ([precedence rules](assign-policies-users-and-groups.md#precedence-rules)) and ([group assignment ranking](assign-policies-users-and-groups.md#group-assignment-ranking)).</span></span> <span data-ttu-id="15f67-132">Убедитесь, что вы читаете и понимаете понятия в документе[(что](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)необходимо знать о назначении политик группам) ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="15f67-132">Make sure you read and understand the concepts in ([What you need to know about policy assignment to groups](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)) earlier in this article.</span></span>

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a><span data-ttu-id="15f67-133">Назначение пакета политики группе пользователей в Центре администрирования</span><span class="sxs-lookup"><span data-stu-id="15f67-133">Assign a policy package to a group of users in the admin center</span></span>

1. <span data-ttu-id="15f67-134">Войдите в Центр администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="15f67-134">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="15f67-135">В области навигации слева перейдите на страницу пакета политики.</span><span class="sxs-lookup"><span data-stu-id="15f67-135">In the left navigation, go to the policy package page.</span></span>
3. <span data-ttu-id="15f67-136">Выберите вкладку назначения групповой политики.</span><span class="sxs-lookup"><span data-stu-id="15f67-136">Select the Group policy assignment tab.</span></span>
4. <span data-ttu-id="15f67-137">Выберите **"Добавить** группу", а затем в области "Назначение пакета политики группе" сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="15f67-137">Select **Add group**, and then in the Assign a policy package to group pane, do the following:</span></span>

    <span data-ttu-id="15f67-138">а)</span><span class="sxs-lookup"><span data-stu-id="15f67-138">a.</span></span> <span data-ttu-id="15f67-139">Найщите и добавьте группу, для нее нужно назначить пакет политики.</span><span class="sxs-lookup"><span data-stu-id="15f67-139">Search for and add the group you want to assign the policy package to.</span></span>

    <span data-ttu-id="15f67-140">б)</span><span class="sxs-lookup"><span data-stu-id="15f67-140">b.</span></span> <span data-ttu-id="15f67-141">Выберите пакет политики.</span><span class="sxs-lookup"><span data-stu-id="15f67-141">Select a policy package.</span></span>

    <span data-ttu-id="15f67-142">в.</span><span class="sxs-lookup"><span data-stu-id="15f67-142">c.</span></span> <span data-ttu-id="15f67-143">Заведите ранжирование для каждого типа политики.</span><span class="sxs-lookup"><span data-stu-id="15f67-143">Set the ranking for each policy type.</span></span>

    <span data-ttu-id="15f67-144">г.</span><span class="sxs-lookup"><span data-stu-id="15f67-144">d.</span></span> <span data-ttu-id="15f67-145">Выберите **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="15f67-145">Select **Apply**.</span></span>

![показывает назначение групповой политики.](media/group-pkg-assignment.png)

5. <span data-ttu-id="15f67-147">Чтобы управлять ранжированием для определенного типа политики, перейдите на страницу политики.</span><span class="sxs-lookup"><span data-stu-id="15f67-147">To manage ranking for a specific policy type, navigate to the specific policy page.</span></span>
6. <span data-ttu-id="15f67-148">Чтобы перена назначение пакета политики группе, сначала удалите назначение групповой политики.</span><span class="sxs-lookup"><span data-stu-id="15f67-148">To reassign a policy package to a group, first remove the group policy assignment.</span></span> <span data-ttu-id="15f67-149">Затем следуйте этим шагам, чтобы назначить пакет политики группе.</span><span class="sxs-lookup"><span data-stu-id="15f67-149">Then, follow the steps above to assign the policy package to a group.</span></span>

### <a name="work-with-powershell"></a><span data-ttu-id="15f67-150">Работа с PowerShell</span><span class="sxs-lookup"><span data-stu-id="15f67-150">Work with PowerShell</span></span>

#### <a name="get-the-teams-powershell-module"></a><span data-ttu-id="15f67-151">Получить модуль Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="15f67-151">Get the Teams PowerShell module</span></span>

<span data-ttu-id="15f67-152">Пошаговую инструкцию см. в [руководстве по установке Teams PowerShell.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="15f67-152">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-package-to-a-group-of-users"></a><span data-ttu-id="15f67-153">Назначение пакета политики группе пользователей</span><span class="sxs-lookup"><span data-stu-id="15f67-153">Assign a policy package to a group of users</span></span>

<span data-ttu-id="15f67-154">Для назначения пакета политики группе используйте cmdlet [Grant-CsGroupPolicyPackageAssignment.](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment)</span><span class="sxs-lookup"><span data-stu-id="15f67-154">Use the [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet to assign a policy package to a group.</span></span> <span data-ttu-id="15f67-155">Группу можно указать с помощью ИД объекта, SIP-адреса или адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="15f67-155">You can specify a group by using the object ID, SIP address, or email address.</span></span> <span data-ttu-id="15f67-156">При назначении пакета политики укажите[](assign-policies-users-and-groups.md#group-assignment-ranking)(ранжирование назначений групп) для каждого типа политики в пакете политики.</span><span class="sxs-lookup"><span data-stu-id="15f67-156">When you assign the policy package, specify a ([group assignment ranking](assign-policies-users-and-groups.md#group-assignment-ranking)) for each policy type in the policy package.</span></span>

<span data-ttu-id="15f67-157">В этом примере пакет политики Education_Teacher назначается группе со ранжированием заданий 1 для TeamsAppSetupPolicy и TeamsMeetingBroadcastPolicy и 2 для TeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="15f67-157">In this example, we assign the Education_Teacher policy package to a group with an assignment ranking of 1 for TeamsAppSetupPolicy and TeamsMeetingBroadcastPolicy and a ranking of 2 for TeamsMeetingPolicy.</span></span>

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="15f67-158">Назначение пакета политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="15f67-158">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="15f67-159">При назначении пакетов пакетов политики вы можете назначать пакет политики большому набору пользователей одновременно, не пользуясь сценарием.</span><span class="sxs-lookup"><span data-stu-id="15f67-159">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="15f67-160">Для отправки пакета пользователей и пакета политики, который вы хотите назначить, используется cmdlet [New-CsBatchPolicyAssignmentOperation.](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="15f67-160">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="15f67-161">Задания будут обрабатываться в фоновом режиме, а для каждого пакета будет создан идентификатор операции.</span><span class="sxs-lookup"><span data-stu-id="15f67-161">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="15f67-162">Затем можно использовать для отслеживания хода выполнения и состояния назначений в пакете с помощью выполнения и выполнения задач [Get-CsBatchPolicyAssignmentOperation.](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="15f67-162">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="15f67-163">Укажите пользователей по их ИД объекта или SIP-адресу.</span><span class="sxs-lookup"><span data-stu-id="15f67-163">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="15f67-164">SIP-адрес пользователя часто имеет то же значение, что и имя пользователя-пользователя (UPN) или адрес электронной почты, но это не требуется.</span><span class="sxs-lookup"><span data-stu-id="15f67-164">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this isn't required.</span></span> <span data-ttu-id="15f67-165">Если имя пользователя указано с помощью upN или электронной почты, но его значение отличается от SIP-адреса, назначение политики для пользователя не удастся.</span><span class="sxs-lookup"><span data-stu-id="15f67-165">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="15f67-166">Если пакет включает дублирующихся пользователей, повторяющиеся записи удаляются из пакета до обработки, а состояние будет предоставлено только для уникальных пользователей, оставшихся в пакете.</span><span class="sxs-lookup"><span data-stu-id="15f67-166">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="15f67-167">Пакет содержит до 5000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="15f67-167">A batch contains up to 5,000 users.</span></span> <span data-ttu-id="15f67-168">Для получения наилучших результатов не от отправьте несколько пакетов за один раз.</span><span class="sxs-lookup"><span data-stu-id="15f67-168">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="15f67-169">Разрешить обработку пакетов перед отправкой дополнительных пакетов.</span><span class="sxs-lookup"><span data-stu-id="15f67-169">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="use-the-teams-powershell-module"></a><span data-ttu-id="15f67-170">Использование модуля Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="15f67-170">Use the Teams PowerShell module</span></span>

<span data-ttu-id="15f67-171">Чтобы установить модуль [Microsoft Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams) запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="15f67-171">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="15f67-172">Установите версию 1.0.5 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="15f67-172">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="15f67-173">Чтобы подключиться к Teams и начать сеанс, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="15f67-173">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="15f67-174">Когда вам будет предложено, войте учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="15f67-174">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-policy-packages-to-a-batch-of-users"></a><span data-ttu-id="15f67-175">Назначение пакетов политики для пакета пользователей</span><span class="sxs-lookup"><span data-stu-id="15f67-175">Assign policy packages to a batch of users</span></span>

<span data-ttu-id="15f67-176">В этом примере с помощью Education_PrimaryStudent пакета политики [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) назначается пакет политики Education_PrimaryStudent пакету пользователей.</span><span class="sxs-lookup"><span data-stu-id="15f67-176">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a><span data-ttu-id="15f67-177">См. состояние пакета назначения</span><span class="sxs-lookup"><span data-stu-id="15f67-177">See the status of a batch assignment</span></span>

<span data-ttu-id="15f67-178">Чтобы получить состояние пакета назначения, где OperationId — это код операции, возвращаемой этим cmdlet для данного пакета, запустите ```New-CsBatchPolicyAssignmentOperation``` следующую операцию:</span><span class="sxs-lookup"><span data-stu-id="15f67-178">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="15f67-179">Если в результате будет показана ошибка, запустите следующую статью, чтобы получить дополнительные сведения об ошибках, которые находятся в ```UserState``` свойстве.</span><span class="sxs-lookup"><span data-stu-id="15f67-179">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="15f67-180">Подробнее см. в [get-CsBatchPolicyAssignmentOperation.](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="15f67-180">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="related-topics"></a><span data-ttu-id="15f67-181">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="15f67-181">Related topics</span></span>

- [<span data-ttu-id="15f67-182">Управление teams с помощью политик</span><span class="sxs-lookup"><span data-stu-id="15f67-182">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
- [<span data-ttu-id="15f67-183">Управление пакетами политики в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="15f67-183">Manage policy packages in Microsoft Teams</span></span>](manage-policy-packages.md)
- [<span data-ttu-id="15f67-184">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="15f67-184">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="15f67-185">Назначение политик в Teams — начало работы</span><span class="sxs-lookup"><span data-stu-id="15f67-185">Assign policies in Teams - getting started</span></span>](policy-assignment-overview.md)