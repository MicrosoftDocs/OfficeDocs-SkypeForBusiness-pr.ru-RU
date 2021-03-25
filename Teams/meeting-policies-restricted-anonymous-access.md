---
title: Удаление политики собраний RestrictedAnonymousAccess Teams для пользователей
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: cebulnes, anyada
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
description: Узнайте, как удалить политику собраний RestrictedAnonymousAccess Teams для пользователей в вашей организации.
ms.openlocfilehash: aab4b524ee0c9ab5cab3244a0897730fea0361a7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121347"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a><span data-ttu-id="43805-103">Удаление политики собраний RestrictedAnonymousAccess Teams для пользователей</span><span class="sxs-lookup"><span data-stu-id="43805-103">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>

<span data-ttu-id="43805-104">[Политики собраний](meeting-policies-in-teams.md) в Microsoft Teams используются для контроля функций, доступных участникам собрания для собраний, запланированных пользователями в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="43805-104">[Meeting policies](meeting-policies-in-teams.md) in Microsoft Teams are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> 

<span data-ttu-id="43805-105">В Teams есть встроенная политика RestrictedAnonymousAccess, которая содержит предопределяющие параметры, которые ограничивают возможность начинать собрания для анонимных пользователей.</span><span class="sxs-lookup"><span data-stu-id="43805-105">Teams includes a built-in policy named RestrictedAnonymousAccess, which contains pre-defined settings that include restricting anonymous users from starting a meeting.</span></span> <span data-ttu-id="43805-106">(Анонимные пользователи — это пользователи, которые не были аутентификацией.) Администраторы не могут изменять или изменять заранее задав параметры в политике собраний.</span><span class="sxs-lookup"><span data-stu-id="43805-106">(Anonymous users are users who haven't been authenticated.) The predefined settings in the meeting policy can't be edited or changed by admins.</span></span>

<span data-ttu-id="43805-107">В этой статье показано, как с помощью PowerShell удалить политику собраний RestrictedAnonymousAccess для пользователей, которым назначена эта политика.</span><span class="sxs-lookup"><span data-stu-id="43805-107">This article shows you how to use PowerShell to remove the RestrictedAnonymousAccess meeting policy from users who are assigned this policy.</span></span> <span data-ttu-id="43805-108">Дополнительные сведения об управлении Teams с помощью PowerShell см. в обзоре [Teams PowerShell.](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="43805-108">To learn more about how to manage Teams using PowerShell, see [Teams PowerShell overview](teams-powershell-overview.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="43805-109">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="43805-109">Before you start</span></span>

<span data-ttu-id="43805-110">Установите модуль Skype для бизнеса [PowerShell и подключите его.](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="43805-110">Install and connect to the [Skype for Business PowerShell module](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell).</span></span> <span data-ttu-id="43805-111">Пошаговую инструкцию см. в [руководстве по установке Microsoft Teams PowerShell.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="43805-111">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a><span data-ttu-id="43805-112">Получите назначения политики собраний Teams для вашей организации</span><span class="sxs-lookup"><span data-stu-id="43805-112">Get the Teams meeting policy assignments for your organization</span></span>

<span data-ttu-id="43805-113">Чтобы получить задания политики собраний Teams для вашей организации, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="43805-113">Run the following to get the Teams meeting policy assignments for your organization.</span></span>

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

<span data-ttu-id="43805-114">В этом примере возвращается следующий результат, который показывает, что двум пользователям назначена политика собрания RestrictedAnonymousAccess.</span><span class="sxs-lookup"><span data-stu-id="43805-114">In this example, the following output is returned, which shows that two users are assigned the RestrictedAnonymousAccess meeting policy.</span></span>

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a><span data-ttu-id="43805-115">Отогнание от пользователей политики restrictedAnonymous meeting</span><span class="sxs-lookup"><span data-stu-id="43805-115">Unassign the RestrictedAnonymous meeting policy from users</span></span>

<span data-ttu-id="43805-116">Чтобы удалить политику собраний RestrictedAnonymous для пользователей, используйте для этого cmdlet [Grant-CSTeamsMeetingPolicy,](/powershell/module/skype/grant-csteamsmeetingpolicy) если у вас небольшое количество пользователей (например, менее 100).</span><span class="sxs-lookup"><span data-stu-id="43805-116">To remove the the RestrictedAnonymous meeting policy from users, you can use the [Grant-CSTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) cmdlet if you have a small number of users (for example, less than 100 users).</span></span> <span data-ttu-id="43805-117">Если у вас много пользователей (например, более 100 пользователей), для отправки пакетной операции эффективнее использовать новый для [CsBatchPolicyAssignmentOperation.](/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)</span><span class="sxs-lookup"><span data-stu-id="43805-117">If you have a large number of users (for example, more than 100 users), it's more efficient to use the  [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet to submit a batch operation.</span></span>

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a><span data-ttu-id="43805-118">Использование Grant-CsTeamsMeeting политики</span><span class="sxs-lookup"><span data-stu-id="43805-118">Use the Grant-CsTeamsMeeting Policy cmdlet</span></span>

<span data-ttu-id="43805-119">Чтобы удалить политику restrictedAnonymous meeting для пользователей, запустите следующую:</span><span class="sxs-lookup"><span data-stu-id="43805-119">Run the following to remove the RestrictedAnonymous meeting policy from users.</span></span>

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a><span data-ttu-id="43805-120">Использование New-CsBatchPolicyAssignmentOperation управления</span><span class="sxs-lookup"><span data-stu-id="43805-120">Use the New-CsBatchPolicyAssignmentOperation cmdlet</span></span>

<span data-ttu-id="43805-121">При [назначении пакетной](assign-policies.md#assign-a-policy-to-a-batch-of-users)политики максимальное количество пользователей, для которых можно удалить или обновить политики, составляет 5000 за один раз.</span><span class="sxs-lookup"><span data-stu-id="43805-121">With [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users), the maximum number of users for which you can remove or update policies is 5,000 at a time.</span></span> <span data-ttu-id="43805-122">Например, если у вас более 5000 пользователей, необходимо отправить несколько пакетов.</span><span class="sxs-lookup"><span data-stu-id="43805-122">For example, if you have more than 5,000 users, you'll need to submit multiple batches.</span></span> <span data-ttu-id="43805-123">Для лучших результатов не от отправьте несколько пакетов за один раз.</span><span class="sxs-lookup"><span data-stu-id="43805-123">For best results, do not submit multiple batches at a time.</span></span> <span data-ttu-id="43805-124">Разрешить обработку пакетов перед отправкой дополнительных пакетов.</span><span class="sxs-lookup"><span data-stu-id="43805-124">Allow batches to complete processing before submitting more batches.</span></span>

> [!NOTE]
> <span data-ttu-id="43805-125">Командлет [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) находится в модуле Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="43805-125">The [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet is in the Teams PowerShell module.</span></span> <span data-ttu-id="43805-126">Прежде чем выполнять эти действия, установите модуль [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams)и подключите его к ним.</span><span class="sxs-lookup"><span data-stu-id="43805-126">Before you follow these steps, install and connect to the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="43805-127">Пошаговую инструкцию см. в [руководстве по установке Microsoft Teams PowerShell.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="43805-127">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

<span data-ttu-id="43805-128">Чтобы удалить политику собраний RestrictedAnonymousAccess для пакета пользователей, следуя следующим командам:</span><span class="sxs-lookup"><span data-stu-id="43805-128">Run the following commands to remove the RestrictedAnonymousAccess meeting policy from a batch of users.</span></span>

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a><span data-ttu-id="43805-129">Получить состояние назначения пакета</span><span class="sxs-lookup"><span data-stu-id="43805-129">Get the status of the batch assignment</span></span>

<span data-ttu-id="43805-130">Каждое пакетное назначение возвращает номер операции, который можно использовать для отслеживания хода выполнения и состояния назначений, а также выявления сбоев.</span><span class="sxs-lookup"><span data-stu-id="43805-130">Each batch assignment returns an operation ID, which you can use to track the progress and status of the assignments and identify any failures that might occur.</span></span> <span data-ttu-id="43805-131">Например, запустите следующую:</span><span class="sxs-lookup"><span data-stu-id="43805-131">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

<span data-ttu-id="43805-132">Убедитесь, **что значение ErrorCount** **— 0 (ноль)** и **overallStatus** **заполнено.**</span><span class="sxs-lookup"><span data-stu-id="43805-132">Make sure the **ErrorCount** is **0** (zero) and **OverallStatus** is **Completed**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="43805-133">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="43805-133">Related topics</span></span>

- [<span data-ttu-id="43805-134">Управление политиками собраний в Teams</span><span class="sxs-lookup"><span data-stu-id="43805-134">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
- [<span data-ttu-id="43805-135">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="43805-135">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="43805-136">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="43805-136">Assign policies to your users in Teams</span></span>](assign-policies.md)