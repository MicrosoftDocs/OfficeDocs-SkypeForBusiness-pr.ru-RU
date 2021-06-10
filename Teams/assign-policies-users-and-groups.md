---
title: Назначение политик пользователям и группам
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
description: Узнайте о различных способах назначения политик пользователям и группам в Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: ce10ead528e2e5615d23bd784131ed04416f1349
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856318"
---
# <a name="assign-policies-to-users-and-groups"></a><span data-ttu-id="eebc7-103">Назначение политик пользователям и группам</span><span class="sxs-lookup"><span data-stu-id="eebc7-103">Assign policies to users and groups</span></span>

<span data-ttu-id="eebc7-104">В этой статье рассматриваются различные способы назначения политик пользователям и группам в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="eebc7-104">This article reviews the different ways to assign policies to users and groups in Microsoft Teams.</span></span> <span data-ttu-id="eebc7-105">Перед чтением убедитесь, что вы прочитали статью Назначение политик в Teams [- начало работы](policy-assignment-overview.md).</span><span class="sxs-lookup"><span data-stu-id="eebc7-105">Before reading, be sure you've read [Assign policies in Teams - getting started](policy-assignment-overview.md).</span></span>

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="eebc7-106">Назначение политики отдельным пользователям</span><span class="sxs-lookup"><span data-stu-id="eebc7-106">Assign a policy to individual users</span></span>

<span data-ttu-id="eebc7-107">Чтобы назначить политику отдельному пользователю или небольшому числу пользователей одновременно, выполните указанные здесь действия.</span><span class="sxs-lookup"><span data-stu-id="eebc7-107">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="use-the-microsoft-teams-admin-center"></a><span data-ttu-id="eebc7-108">Использование центра Microsoft Teams администрирования</span><span class="sxs-lookup"><span data-stu-id="eebc7-108">Use the Microsoft Teams admin center</span></span>

<span data-ttu-id="eebc7-109">Чтобы назначить политику пользователю:</span><span class="sxs-lookup"><span data-stu-id="eebc7-109">To assign a policy to a user:</span></span>

1. <span data-ttu-id="eebc7-110">В левой области навигации центра администрирования Microsoft Teams перейдите **в** меню Пользователи и выберите пользователя.</span><span class="sxs-lookup"><span data-stu-id="eebc7-110">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="eebc7-111">Выберите пользователя, щелкнув слева от его имени и выбрав изменить **параметры**.</span><span class="sxs-lookup"><span data-stu-id="eebc7-111">Select the user by clicking to the left of the user name, and then select **Edit settings**.</span></span>
3. <span data-ttu-id="eebc7-112">Выберите политику, которая вы хотите назначить, и выберите **применить**.</span><span class="sxs-lookup"><span data-stu-id="eebc7-112">Select the policy you want to assign, and then select **Apply**.</span></span>

![Назначение политики пользователю в Центре Teams администрирования](media/assign-policy-user.png)

<span data-ttu-id="eebc7-114">Кроме того, можно сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="eebc7-114">Or, you can also do the following:</span></span>

1. <span data-ttu-id="eebc7-115">В левой области навигации центра администрирования Microsoft Teams перейдите на страницу политики.</span><span class="sxs-lookup"><span data-stu-id="eebc7-115">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="eebc7-116">Выберите политику, которая вы хотите назначить, щелкнув слева от ее имени.</span><span class="sxs-lookup"><span data-stu-id="eebc7-116">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="eebc7-117">Выберите **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="eebc7-117">Select **Manage users**.</span></span>
4. <span data-ttu-id="eebc7-118">В области **Управление пользователями** выполните поиск по отображаемому имени или по имени пользователя, выберите имя и нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="eebc7-118">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="eebc7-119">Повторите это действие для каждого пользователя, которого нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="eebc7-119">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="eebc7-120">Завершив добавление пользователей, выберите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="eebc7-120">When you're finished adding users, select **Apply**.</span></span>

![Назначение политики пользователю в Центре администрирования Teams с помощью второго метода](media/assign-policy-user2.png)

### <a name="use-powershell"></a><span data-ttu-id="eebc7-122">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="eebc7-122">Use PowerShell</span></span>

<span data-ttu-id="eebc7-123">У каждого типа политики есть собственный набор cmdlets для управления.</span><span class="sxs-lookup"><span data-stu-id="eebc7-123">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="eebc7-124">Используйте для назначения политики тот или иной ```Grant-``` тип.</span><span class="sxs-lookup"><span data-stu-id="eebc7-124">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="eebc7-125">Например, используйте его для назначения пользователям политики Teams ```Grant-CsTeamsMeetingPolicy``` собраний.</span><span class="sxs-lookup"><span data-stu-id="eebc7-125">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="eebc7-126">Эти командлеты включены в модуль Teams PowerShell и задокументированы в Skype для бизнеса [командлета](/powershell/skype).</span><span class="sxs-lookup"><span data-stu-id="eebc7-126">These cmdlets are included in the Teams PowerShell module and are documented in the [Skype for Business cmdlet reference](/powershell/skype).</span></span>

 <span data-ttu-id="eebc7-127">Скачайте и установите [общедоступный Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) (если вы еще не сделали этого), а затем запустите следующую версию, чтобы подключиться:</span><span class="sxs-lookup"><span data-stu-id="eebc7-127">Download and install the [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) (if you haven't already), and then run the following to connect.</span></span>

> [!NOTE]
> <span data-ttu-id="eebc7-128">Skype для бизнеса В настоящее время Online Connector является частью последней версии Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eebc7-128">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="eebc7-129">Если вы используете последний общедоступный [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать Skype для бизнеса Online Connector.</span><span class="sxs-lookup"><span data-stu-id="eebc7-129">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="eebc7-130">В этом примере мы назначим пользователю с именем Reda Teams политику собраний учащихся.</span><span class="sxs-lookup"><span data-stu-id="eebc7-130">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="eebc7-131">Подробнее об этом можно узнать в [документе Управление политиками с помощью PowerShell.](teams-powershell-managing-teams.md#manage-policies-via-powershell)</span><span class="sxs-lookup"><span data-stu-id="eebc7-131">To learn more, read [Manage policies via PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="eebc7-132">Назначение политики группе</span><span class="sxs-lookup"><span data-stu-id="eebc7-132">Assign a policy to a group</span></span>

<span data-ttu-id="eebc7-133">Назначение политик группам позволяет назначить политику группе пользователей, например группе безопасности или списку рассылки.</span><span class="sxs-lookup"><span data-stu-id="eebc7-133">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="eebc7-134">Назначение политики распространяется на участников группы в соответствии с правилами очередности.</span><span class="sxs-lookup"><span data-stu-id="eebc7-134">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="eebc7-135">При добавлении или удалении участников группы, назначения политик для них обновляются соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="eebc7-135">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="eebc7-136">Назначение политик группам рекомендуется для групп до 50 000 пользователей, но оно также будет работать с более крупными группами.</span><span class="sxs-lookup"><span data-stu-id="eebc7-136">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="eebc7-137">При назначении политики она сразу же назначается группе.</span><span class="sxs-lookup"><span data-stu-id="eebc7-137">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="eebc7-138">Однако распространение назначения политики на участников группы выполняется в фоновом режиме и может занять некоторое время в зависимости от размера группы.</span><span class="sxs-lookup"><span data-stu-id="eebc7-138">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="eebc7-139">То же самое происходит, если политика не назначена группе, а участники добавляются в нее или удаляются из нее.</span><span class="sxs-lookup"><span data-stu-id="eebc7-139">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

<span data-ttu-id="eebc7-140">Назначения групповой политики распространяются только на пользователей, которые являются прямыми участниками группы.</span><span class="sxs-lookup"><span data-stu-id="eebc7-140">Group policy assignments are only propagated to users who are direct members of the group.</span></span> <span data-ttu-id="eebc7-141">Назначения не распространяются на участников вложенных групп.</span><span class="sxs-lookup"><span data-stu-id="eebc7-141">The assignments aren't propagated to members of nested groups.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="eebc7-142">Что необходимо знать о назначении политик группам</span><span class="sxs-lookup"><span data-stu-id="eebc7-142">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="eebc7-143">Перед началом работы важно разобраться в правилах приоритета и ранжирования заданий групп.</span><span class="sxs-lookup"><span data-stu-id="eebc7-143">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="eebc7-144">Правила приоритета</span><span class="sxs-lookup"><span data-stu-id="eebc7-144">Precedence rules</span></span>

<span data-ttu-id="eebc7-145">Для данного типа политики эффективная политика пользователя определяется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="eebc7-145">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="eebc7-146">Политика, которая непосредственно назначена пользователю, имеет приоритет над любой другой политикой того же типа, которая назначена группе.</span><span class="sxs-lookup"><span data-stu-id="eebc7-146">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="eebc7-147">Другими словами, если пользователю непосредственно назначена политика заданного типа, он не наследует политику того же типа от группы.</span><span class="sxs-lookup"><span data-stu-id="eebc7-147">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="eebc7-148">Это также означает, что если пользователю назначена политика того или иного типа, необходимо удалить ее у пользователя, прежде чем он сможет наследовать политику того же типа от группы.</span><span class="sxs-lookup"><span data-stu-id="eebc7-148">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="eebc7-149">Если пользователю не назначена политика, а он входит в несколько групп и каждой группе назначена политика одного и того же типа, пользователь наследует политику назначения группы с наивысшим рейтингом.</span><span class="sxs-lookup"><span data-stu-id="eebc7-149">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="eebc7-150">Если пользователь не входит в группы, для каких-либо групп назначена политика, к этому типу политики применяется глобальная политика (по умолчанию в организации).</span><span class="sxs-lookup"><span data-stu-id="eebc7-150">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="eebc7-151">Эффективная политика пользователя обновляется в соответствии с этими правилами:</span><span class="sxs-lookup"><span data-stu-id="eebc7-151">A user's effective policy is updated according to these rules:</span></span>

- <span data-ttu-id="eebc7-152">при добавлении пользователя в группу, которая назначена политике, или удален из нее.</span><span class="sxs-lookup"><span data-stu-id="eebc7-152">when a user is added to or removed from a group that's assigned a policy.</span></span>
- <span data-ttu-id="eebc7-153">политика не назначена группе.</span><span class="sxs-lookup"><span data-stu-id="eebc7-153">a policy is unassigned from a group.</span></span>
- <span data-ttu-id="eebc7-154">Политика, которая непосредственно назначена пользователю, удаляется.</span><span class="sxs-lookup"><span data-stu-id="eebc7-154">a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="eebc7-155">Ранжирование заданий группы</span><span class="sxs-lookup"><span data-stu-id="eebc7-155">Group assignment ranking</span></span>

<span data-ttu-id="eebc7-156">При назначении группе политики указывается ранжирование для назначения группы.</span><span class="sxs-lookup"><span data-stu-id="eebc7-156">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="eebc7-157">Он используется для определения политики, которая должна наследоваться пользователем как эффективная политика, если пользователь входит в несколько групп и каждой группе назначена политика одного типа.</span><span class="sxs-lookup"><span data-stu-id="eebc7-157">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="eebc7-158">Ранжирование заданий группы является относительно других назначений группы того же типа.</span><span class="sxs-lookup"><span data-stu-id="eebc7-158">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="eebc7-159">Например, если вы назначаете политику звонков двум группам, установите для ранжирования одно задание 1, а для другого — 2, причем 1 является самым высоким.</span><span class="sxs-lookup"><span data-stu-id="eebc7-159">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="eebc7-160">Ранжирование назначений групп показывает, какая группа является более важной или релевантной, чем другие группы в отношении наследования.</span><span class="sxs-lookup"><span data-stu-id="eebc7-160">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>

<span data-ttu-id="eebc7-161">Например, у вас есть две группы: "Сотрудники магазинов" и "Руководители магазинов".</span><span class="sxs-lookup"><span data-stu-id="eebc7-161">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="eebc7-162">Обеим группам назначена политика Teams звонков, политика звонков сотрудников магазинов и политика звонков диспетчеров магазинов соответственно.</span><span class="sxs-lookup"><span data-stu-id="eebc7-162">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="eebc7-163">Для руководителя магазина, который относится к обеим группам, его роль руководителя больше релевантна, чем роль сотрудника, поэтому политика звонков, назначенная группе "Руководители магазинов", должна иметь более высокий рейтинг.</span><span class="sxs-lookup"><span data-stu-id="eebc7-163">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="eebc7-164">Группы</span><span class="sxs-lookup"><span data-stu-id="eebc7-164">Group</span></span> |<span data-ttu-id="eebc7-165">Teams политики звонков</span><span class="sxs-lookup"><span data-stu-id="eebc7-165">Teams calling policy name</span></span>  |<span data-ttu-id="eebc7-166">Rank (Ранг)</span><span class="sxs-lookup"><span data-stu-id="eebc7-166">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="eebc7-167">Руководители магазинов</span><span class="sxs-lookup"><span data-stu-id="eebc7-167">Store Managers</span></span>   |<span data-ttu-id="eebc7-168">Политика звонков диспетчеров магазинов</span><span class="sxs-lookup"><span data-stu-id="eebc7-168">Store Managers Calling Policy</span></span>         |<span data-ttu-id="eebc7-169">1</span><span class="sxs-lookup"><span data-stu-id="eebc7-169">1</span></span>|
|<span data-ttu-id="eebc7-170">Сотрудники магазина</span><span class="sxs-lookup"><span data-stu-id="eebc7-170">Store Employees</span></span>    |<span data-ttu-id="eebc7-171">Политика звонков сотрудников магазина</span><span class="sxs-lookup"><span data-stu-id="eebc7-171">Store Employees Calling Policy</span></span>      |<span data-ttu-id="eebc7-172">2</span><span class="sxs-lookup"><span data-stu-id="eebc7-172">2</span></span>|

<span data-ttu-id="eebc7-173">Если не указать ранжирование, назначение политики будет присвоено наименьшее ранжирование.</span><span class="sxs-lookup"><span data-stu-id="eebc7-173">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="in-the-teams-admin-center"></a><span data-ttu-id="eebc7-174">В центре Teams администрирования</span><span class="sxs-lookup"><span data-stu-id="eebc7-174">In the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="eebc7-175">В настоящее время назначение политик группам, использующим Центр администрирования Microsoft Teams, доступно только для политик звонков Teams, политики парков звонков Teams, политики Teams, политики трансляций Teams, политики Teams собраний и политики Teams сообщений.</span><span class="sxs-lookup"><span data-stu-id="eebc7-175">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="eebc7-176">Для других типов политик используйте PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eebc7-176">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="eebc7-177">В левой области навигации центра администрирования Microsoft Teams перейдите на страницу типа политики.</span><span class="sxs-lookup"><span data-stu-id="eebc7-177">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="eebc7-178">Например, перейдите к **политике собраний**  >  **собраний**.</span><span class="sxs-lookup"><span data-stu-id="eebc7-178">For example, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="eebc7-179">Выберите **вкладку Назначение групповой** политики.</span><span class="sxs-lookup"><span data-stu-id="eebc7-179">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="eebc7-180">Выберите **Добавить группу,** а затем в области **Назначение** политики группе сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="eebc7-180">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="eebc7-181">Найщите и добавьте группу, для нее нужно назначить политику.</span><span class="sxs-lookup"><span data-stu-id="eebc7-181">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="eebc7-182">Задание ранжирования для задания группы.</span><span class="sxs-lookup"><span data-stu-id="eebc7-182">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="eebc7-183">Выберите политику, которую вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="eebc7-183">Select the policy that you want to assign.</span></span>
    4. <span data-ttu-id="eebc7-184">Выберите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="eebc7-184">Select **Apply**.</span></span>
    
![Назначение политики группе в Центре Teams администрирования](media/assign-policy-group.png)

<span data-ttu-id="eebc7-186">Чтобы удалить назначение групповой  политики, на вкладке Назначение групповой политики страницы политики выберите назначение группы и выберите **удалить**.</span><span class="sxs-lookup"><span data-stu-id="eebc7-186">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="eebc7-187">Чтобы изменить ранжирование назначения группы, необходимо сначала удалить назначение групповой политики.</span><span class="sxs-lookup"><span data-stu-id="eebc7-187">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="eebc7-188">Затем, следуя этим шагам, назначьте политику группе.</span><span class="sxs-lookup"><span data-stu-id="eebc7-188">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="use-the-powershell-option"></a><span data-ttu-id="eebc7-189">Использование параметра PowerShell</span><span class="sxs-lookup"><span data-stu-id="eebc7-189">Use the PowerShell option</span></span>

> [!NOTE]
> <span data-ttu-id="eebc7-190">В настоящее время назначения политик группам, использующим PowerShell, доступны не для Teams типов политик.</span><span class="sxs-lookup"><span data-stu-id="eebc7-190">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="eebc7-191">Список поддерживаемых типов политик см. в списке [New-CsGroupPolicyAssignment.](/powershell/module/teams/new-csgrouppolicyassignment)</span><span class="sxs-lookup"><span data-stu-id="eebc7-191">See [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="eebc7-192">Установка и подключение к Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="eebc7-192">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="eebc7-193">Пошаговую инструкцию см. в [Teams PowerShell.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="eebc7-193">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-to-a-group-of-users"></a><span data-ttu-id="eebc7-194">Назначение политики группе пользователей</span><span class="sxs-lookup"><span data-stu-id="eebc7-194">Assign a policy to a group of users</span></span>

<span data-ttu-id="eebc7-195">Чтобы назначить группу политику, воспользуйтесь [cmdlet New-CsGroupPolicyAssignment.](/powershell/module/teams/new-csgrouppolicyassignment)</span><span class="sxs-lookup"><span data-stu-id="eebc7-195">Use the [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="eebc7-196">Группу можно указать с помощью ИД объекта, SIP-адреса или адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="eebc7-196">You can specify a group by using the object ID, SIP address, or email address.</span></span>

<span data-ttu-id="eebc7-197">В этом примере мы назначаем политику Teams собраний с именем "Политика собраний менеджеров розничной торговли" группе со ранжированием назначения 1.</span><span class="sxs-lookup"><span data-stu-id="eebc7-197">In this example, we assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="eebc7-198">Получить назначения политик для группы</span><span class="sxs-lookup"><span data-stu-id="eebc7-198">Get policy assignments for a group</span></span>

<span data-ttu-id="eebc7-199">Чтобы получить все политики, которые назначены группе, используйте для этого [cmdlet Get-CsGroupPolicyAssignment.](/powershell/module/teams/get-csgrouppolicyassignment)</span><span class="sxs-lookup"><span data-stu-id="eebc7-199">Use the [Get-CsGroupPolicyAssignment](/powershell/module/teams/get-csgrouppolicyassignment) cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="eebc7-200">Обратите внимание, что группы всегда указаны по их групповому ИД, даже если для назначения политики использовался SIP-адрес или адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="eebc7-200">Note that groups are always listed by their group ID even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="eebc7-201">В этом примере мы извлекаем все политики, которые назначены определенной группе.</span><span class="sxs-lookup"><span data-stu-id="eebc7-201">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="eebc7-202">В этом примере возвращаются все группы, для Teams политики собраний.</span><span class="sxs-lookup"><span data-stu-id="eebc7-202">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="eebc7-203">Удаление политики из группы</span><span class="sxs-lookup"><span data-stu-id="eebc7-203">Remove a policy from a group</span></span>

<span data-ttu-id="eebc7-204">Чтобы удалить политику из группы, используйте [cmdlet Remove-CsGroupPolicyAssignment.](/powershell/module/teams/remove-csgrouppolicyassignment)</span><span class="sxs-lookup"><span data-stu-id="eebc7-204">Use the [Remove-CsGroupPolicyAssignment](/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="eebc7-205">При этом обновляются приоритеты других политик того же типа, которые имеют более низкий рейтинг.</span><span class="sxs-lookup"><span data-stu-id="eebc7-205">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group, and that have a lower ranking, are updated.</span></span> <span data-ttu-id="eebc7-206">Например, если удалить политику со ранжированием 2, политики со ранжированием 3 и 4 будут обновлены с учетом их нового ранжирования.</span><span class="sxs-lookup"><span data-stu-id="eebc7-206">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="eebc7-207">В следующих двух таблицах приводится пример.</span><span class="sxs-lookup"><span data-stu-id="eebc7-207">The following two tables show this example.</span></span>

<span data-ttu-id="eebc7-208">Вот список назначений и приоритетов политики для Teams собраний.</span><span class="sxs-lookup"><span data-stu-id="eebc7-208">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="eebc7-209">Имя группы</span><span class="sxs-lookup"><span data-stu-id="eebc7-209">Group name</span></span>  |<span data-ttu-id="eebc7-210">Название политики</span><span class="sxs-lookup"><span data-stu-id="eebc7-210">Policy name</span></span>  |<span data-ttu-id="eebc7-211">Rank (Ранг)</span><span class="sxs-lookup"><span data-stu-id="eebc7-211">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="eebc7-212">Продажи</span><span class="sxs-lookup"><span data-stu-id="eebc7-212">Sales</span></span>    |<span data-ttu-id="eebc7-213">Политика продаж</span><span class="sxs-lookup"><span data-stu-id="eebc7-213">Sales policy</span></span>       | <span data-ttu-id="eebc7-214">1</span><span class="sxs-lookup"><span data-stu-id="eebc7-214">1</span></span>        |
|<span data-ttu-id="eebc7-215">Западная область</span><span class="sxs-lookup"><span data-stu-id="eebc7-215">West Region</span></span>     |<span data-ttu-id="eebc7-216">Политика западного региона</span><span class="sxs-lookup"><span data-stu-id="eebc7-216">West Region policy</span></span>         |<span data-ttu-id="eebc7-217">2</span><span class="sxs-lookup"><span data-stu-id="eebc7-217">2</span></span>         |
|<span data-ttu-id="eebc7-218">Отдел</span><span class="sxs-lookup"><span data-stu-id="eebc7-218">Division</span></span>    |<span data-ttu-id="eebc7-219">Политика деления</span><span class="sxs-lookup"><span data-stu-id="eebc7-219">Division policy</span></span>         |<span data-ttu-id="eebc7-220">3</span><span class="sxs-lookup"><span data-stu-id="eebc7-220">3</span></span>         |
|<span data-ttu-id="eebc7-221">Дочерней компании</span><span class="sxs-lookup"><span data-stu-id="eebc7-221">Subsidiary</span></span>   |<span data-ttu-id="eebc7-222">Политика дочернего подразделения</span><span class="sxs-lookup"><span data-stu-id="eebc7-222">Subsidiary policy</span></span>        |<span data-ttu-id="eebc7-223">4</span><span class="sxs-lookup"><span data-stu-id="eebc7-223">4</span></span>         |

<span data-ttu-id="eebc7-224">Если удалить политику западного региона из группы "Запад", назначения и приоритеты политики будут обновлены следующим образом.</span><span class="sxs-lookup"><span data-stu-id="eebc7-224">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="eebc7-225">Имя группы</span><span class="sxs-lookup"><span data-stu-id="eebc7-225">Group name</span></span>  |<span data-ttu-id="eebc7-226">Название политики</span><span class="sxs-lookup"><span data-stu-id="eebc7-226">Policy name</span></span>  |<span data-ttu-id="eebc7-227">Rank (Ранг)</span><span class="sxs-lookup"><span data-stu-id="eebc7-227">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="eebc7-228">Продажи</span><span class="sxs-lookup"><span data-stu-id="eebc7-228">Sales</span></span>    |<span data-ttu-id="eebc7-229">Политика продаж</span><span class="sxs-lookup"><span data-stu-id="eebc7-229">Sales policy</span></span>       | <span data-ttu-id="eebc7-230">1</span><span class="sxs-lookup"><span data-stu-id="eebc7-230">1</span></span>        |
|<span data-ttu-id="eebc7-231">Отдел</span><span class="sxs-lookup"><span data-stu-id="eebc7-231">Division</span></span>    |<span data-ttu-id="eebc7-232">Политика деления</span><span class="sxs-lookup"><span data-stu-id="eebc7-232">Division policy</span></span>         |<span data-ttu-id="eebc7-233">2</span><span class="sxs-lookup"><span data-stu-id="eebc7-233">2</span></span>         |
|<span data-ttu-id="eebc7-234">Дочерней компании</span><span class="sxs-lookup"><span data-stu-id="eebc7-234">Subsidiary</span></span>   |<span data-ttu-id="eebc7-235">Политика дочернего подразделения</span><span class="sxs-lookup"><span data-stu-id="eebc7-235">Subsidiary policy</span></span>        |<span data-ttu-id="eebc7-236">3</span><span class="sxs-lookup"><span data-stu-id="eebc7-236">3</span></span>        |

<span data-ttu-id="eebc7-237">В этом примере мы удаляем политику Teams собраний из группы.</span><span class="sxs-lookup"><span data-stu-id="eebc7-237">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="eebc7-238">Изменение назначения политики для группы</span><span class="sxs-lookup"><span data-stu-id="eebc7-238">Change a policy assignment for a group</span></span>

> [!NOTE]
> <span data-ttu-id="eebc7-239">В ближайшее время появится [cmdlet Set-CsGroupPolicyAssignment.](/powershell/module/teams/set-csgrouppolicyassignment)</span><span class="sxs-lookup"><span data-stu-id="eebc7-239">The [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) cmdlet will be available soon.</span></span> <span data-ttu-id="eebc7-240">Тем временем, чтобы изменить назначение групповой политики, вы можете удалить текущее назначение политики из группы, а затем добавить новое назначение политики.</span><span class="sxs-lookup"><span data-stu-id="eebc7-240">In the meantime, to change a group policy assignment, you can remove the current policy assignment from the group, and then add a new policy assignment.</span></span>

<span data-ttu-id="eebc7-241">После назначения группе политики вы можете изменить назначение политики этой группы с помощью cmdlet [Set-CsGroupPolicyAssignment:](/powershell/module/teams/set-csgrouppolicyassignment)</span><span class="sxs-lookup"><span data-stu-id="eebc7-241">After you assign a policy to a group, you can use the [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="eebc7-242">Изменение ранжирования</span><span class="sxs-lookup"><span data-stu-id="eebc7-242">Change the ranking</span></span>
- <span data-ttu-id="eebc7-243">Изменение политики для заданного типа политики</span><span class="sxs-lookup"><span data-stu-id="eebc7-243">Change the policy of a given policy type</span></span>
- <span data-ttu-id="eebc7-244">Изменение политики для заданного типа политики и ранжирования</span><span class="sxs-lookup"><span data-stu-id="eebc7-244">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="eebc7-245">В этом примере мы меняем политику Teams жков группы на политику SupportCallPark и ранжирование заданий на 3.</span><span class="sxs-lookup"><span data-stu-id="eebc7-245">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="eebc7-246">Изменение эффективной политики для пользователя</span><span class="sxs-lookup"><span data-stu-id="eebc7-246">Change the effective policy for a user</span></span>

<span data-ttu-id="eebc7-247">Вот пример изменения эффективной политики для пользователя, которому назначена политика напрямую.</span><span class="sxs-lookup"><span data-stu-id="eebc7-247">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="eebc7-248">Во-первых, для получения сведений о политиках трансляции собраний, связанных с пользователем, используется Teams [Get-CsUserPolicyAssignment.](/powershell/module/teams/get-csuserpolicyassignment) ```PolicySource```</span><span class="sxs-lookup"><span data-stu-id="eebc7-248">First, we use the [Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment) cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="eebc7-249">Выходные данные показывают, что пользователю напрямую назначена политика Teams трансляций собраний с названием "События сотрудника", которая имеет приоритет над политикой "Мероприятия поставщиков", назначенной группе, которой он принадлежит.</span><span class="sxs-lookup"><span data-stu-id="eebc7-249">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="eebc7-250">Теперь мы удалим политику "События сотрудников" для пользователя.</span><span class="sxs-lookup"><span data-stu-id="eebc7-250">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="eebc7-251">Это означает, что пользователю больше не назначена политика Teams трансляций собраний, и наследует политику "Мероприятия поставщиков", назначенную группе, которой принадлежит пользователь.</span><span class="sxs-lookup"><span data-stu-id="eebc7-251">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span>

<span data-ttu-id="eebc7-252">Для этого используйте следующий командлет Skype для бизнеса PowerShell:</span><span class="sxs-lookup"><span data-stu-id="eebc7-252">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="eebc7-253">Используйте следующий командлет в модуле Teams PowerShell, чтобы сделать это в масштабе, хотя назначение пакетной политики $users список пользователей, которые вы указали.</span><span class="sxs-lookup"><span data-stu-id="eebc7-253">Use following cmdlet in the Teams PowerShell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="eebc7-254">Назначение политики для пакета пользователей</span><span class="sxs-lookup"><span data-stu-id="eebc7-254">Assign a policy to a batch of users</span></span>

### <a name="use-the-admin-center"></a><span data-ttu-id="eebc7-255">Использование Центра администрирования</span><span class="sxs-lookup"><span data-stu-id="eebc7-255">Use the admin center</span></span>

<span data-ttu-id="eebc7-256">Чтобы массово назначить политику пользователям:</span><span class="sxs-lookup"><span data-stu-id="eebc7-256">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="eebc7-257">В левой области навигации центра администрирования Microsoft Teams выберите **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="eebc7-257">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="eebc7-258">Найщите пользователей, для них нужно назначить политику, или отфильтруем представление, чтобы отфильтровать нужных пользователей.</span><span class="sxs-lookup"><span data-stu-id="eebc7-258">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="eebc7-259">В столбце **&#x2713;** (галочка) выберите пользователей.</span><span class="sxs-lookup"><span data-stu-id="eebc7-259">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="eebc7-260">Чтобы выбрать всех пользователей, щелкните &#x2713; (галочку) в верхней части таблицы.</span><span class="sxs-lookup"><span data-stu-id="eebc7-260">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="eebc7-261">Выберите **Изменить параметры**, внесите нужные изменения и выберите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="eebc7-261">Select **Edit settings**, make the changes that you want, and then select **Apply**.</span></span>

<span data-ttu-id="eebc7-262">Чтобы просмотреть состояние задания политики, на баннере, который  появляется в  верхней части страницы Пользователи после выбора применить, чтобы отправить задание политики, выберите журнал **действий**.</span><span class="sxs-lookup"><span data-stu-id="eebc7-262">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you select **Apply** to submit your policy assignment, select **Activity log**.</span></span> <span data-ttu-id="eebc7-263">Кроме того, в левой области навигации Центра администрирования Microsoft Teams выберите Панель мониторинга **,** а затем в журнале действий **выберите** **Просмотреть сведения**.</span><span class="sxs-lookup"><span data-stu-id="eebc7-263">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, select **View details**.</span></span> <span data-ttu-id="eebc7-264">В журнале действий показаны назначения политик более чем 20 пользователям через Microsoft Teams центре администрирования за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="eebc7-264">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="eebc7-265">Дополнительные данные см. в записи просмотра заданий политики [в журнале действий.](activity-log.md)</span><span class="sxs-lookup"><span data-stu-id="eebc7-265">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="use-powershell-method"></a><span data-ttu-id="eebc7-266">Использование метода PowerShell</span><span class="sxs-lookup"><span data-stu-id="eebc7-266">Use PowerShell method</span></span>

> [!NOTE]
> <span data-ttu-id="eebc7-267">В настоящее время назначение пакетной политики с помощью PowerShell доступно не для Teams типов политик.</span><span class="sxs-lookup"><span data-stu-id="eebc7-267">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="eebc7-268">Список поддерживаемых типов политик см. в списке [New-CsBatchPolicyAssignmentOperation.](/powershell/module/teams/new-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="eebc7-268">See [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>

<span data-ttu-id="eebc7-269">При назначении пакетной политики вы можете назначать политику большому набору пользователей одновременно, не пользуясь сценарием.</span><span class="sxs-lookup"><span data-stu-id="eebc7-269">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="eebc7-270">Для отправки пакета пользователей и политики, которую вы хотите назначить, используется [cmdlet New-CsBatchPolicyAssignmentOperation.](/powershell/module/teams/new-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="eebc7-270">You use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="eebc7-271">Задания будут обрабатываться в фоновом режиме, а для каждого пакета будет создан идентификатор операции.</span><span class="sxs-lookup"><span data-stu-id="eebc7-271">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="eebc7-272">Затем можно использовать для отслеживания хода выполнения и состояния заданий в пакете с помощью [get-CsBatchPolicyAssignmentOperation.](/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="eebc7-272">You can then use the [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="eebc7-273">Укажите пользователей по их ИД объекта или SIP-адресу.</span><span class="sxs-lookup"><span data-stu-id="eebc7-273">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="eebc7-274">SIP-адрес пользователя часто имеет то же значение, что и имя директора-пользователя (UPN) или адрес электронной почты, но это не обязательно.</span><span class="sxs-lookup"><span data-stu-id="eebc7-274">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="eebc7-275">Если имя пользователя указано с помощью его имя-пользователя или электронной почты, но его значение отличается от SIP-адреса, назначение политики для него не удастся.</span><span class="sxs-lookup"><span data-stu-id="eebc7-275">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="eebc7-276">Если пакет содержит дубликатов пользователей, они будут удалены из пакета до обработки, а состояние будет предоставлено только для уникальных пользователей, оставшихся в пакете.</span><span class="sxs-lookup"><span data-stu-id="eebc7-276">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="eebc7-277">Пакет может содержать до 5 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="eebc7-277">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="eebc7-278">Для получения наилучших результатов не от отправки нескольких пакетов за один раз.</span><span class="sxs-lookup"><span data-stu-id="eebc7-278">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="eebc7-279">Разрешить обработку пакетов перед отправкой дополнительных пакетов.</span><span class="sxs-lookup"><span data-stu-id="eebc7-279">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-teams-powershell-module"></a><span data-ttu-id="eebc7-280">Установка и подключение к Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="eebc7-280">Install and connect to the Teams PowerShell module</span></span>

<span data-ttu-id="eebc7-281">Чтобы установить модуль [Microsoft Teams PowerShell, запустите следующую Microsoft Teams.](https://www.powershellgallery.com/packages/MicrosoftTeams)</span><span class="sxs-lookup"><span data-stu-id="eebc7-281">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="eebc7-282">Установите версию 1.0.5 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="eebc7-282">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="eebc7-283">Чтобы подключиться к Teams и начать сеанс, запустите следующее:</span><span class="sxs-lookup"><span data-stu-id="eebc7-283">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="eebc7-284">Когда вам будет предложено, войте в учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="eebc7-284">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="eebc7-285">Установка и подключение к Azure AD PowerShell для Graph (необязательно)</span><span class="sxs-lookup"><span data-stu-id="eebc7-285">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="eebc7-286">Кроме того, может потребоваться скачать и установить [модуль Azure AD PowerShell](/powershell/azure/active-directory/install-adv2) для Graph (если вы еще не сделали этого) и подключиться к Azure AD, чтобы получить список пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="eebc7-286">You might also want to [download and install the Azure AD PowerShell for Graph module](/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="eebc7-287">Чтобы подключиться к Azure AD, запустите следующую службу:</span><span class="sxs-lookup"><span data-stu-id="eebc7-287">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="eebc7-288">В окне запроса войтесь в учетные данные администратора, которые использовались для подключения к Teams.</span><span class="sxs-lookup"><span data-stu-id="eebc7-288">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-setup-policy-to-a-batch-of-users"></a><span data-ttu-id="eebc7-289">Назначение политики установки для пакета пользователей</span><span class="sxs-lookup"><span data-stu-id="eebc7-289">Assign a setup policy to a batch of users</span></span>

<span data-ttu-id="eebc7-290">В этом примере с помощью нового [CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) назначим политику настройки приложений с названием Политика настройки приложений для отдела кадров пакету пользователей, перечисленных в Users_ids.text file.</span><span class="sxs-lookup"><span data-stu-id="eebc7-290">In this example, we use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="eebc7-291">В этом примере мы подключаемся к Azure AD, чтобы получить набор пользователей, а затем назначим политику обмена сообщениями "Новая политика обмена сообщениями о приеме на работу" пакету пользователей, указанному с помощью их SIP-адреса.</span><span class="sxs-lookup"><span data-stu-id="eebc7-291">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="eebc7-292">Получить состояние пакета назначения</span><span class="sxs-lookup"><span data-stu-id="eebc7-292">Get the status of a batch assignment</span></span>

<span data-ttu-id="eebc7-293">Чтобы получить состояние пакета назначения, где OperationId — это код операции, возвращаемый этим cmdlet для заданного пакета, запустите ```New-CsBatchPolicyAssignmentOperation``` следующую операцию:</span><span class="sxs-lookup"><span data-stu-id="eebc7-293">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="eebc7-294">Если выходные данные показывают, что произошла ошибка, запустите следующую, чтобы получить дополнительные сведения об ошибках, которые находятся в ```UserState``` свойстве.</span><span class="sxs-lookup"><span data-stu-id="eebc7-294">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="eebc7-295">Подробнее см. в [get-CsBatchPolicyAssignmentOperation.](/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="eebc7-295">To learn more, see [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="related-topics"></a><span data-ttu-id="eebc7-296">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="eebc7-296">Related topics</span></span>

- [<span data-ttu-id="eebc7-297">Управление Teams политиками</span><span class="sxs-lookup"><span data-stu-id="eebc7-297">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
- [<span data-ttu-id="eebc7-298">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="eebc7-298">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="eebc7-299">Назначение политик в Teams — начало работы</span><span class="sxs-lookup"><span data-stu-id="eebc7-299">Assign policies in Teams - getting started</span></span>](policy-assignment-overview.md)
