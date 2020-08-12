---
title: Удаление политики собраний RestrictedAnonymousAccess Teams для пользователей
author: LanaChin
ms.author: v-lanac
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
description: Сведения о том, как удалить политику собраний RestrictedAnonymousAccess Teams для пользователей в вашей организации.
ms.openlocfilehash: 12224ec860552b17b6f7fe50396081943955a88c
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/12/2020
ms.locfileid: "46640999"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a><span data-ttu-id="e856c-103">Удаление политики собраний RestrictedAnonymousAccess Teams для пользователей</span><span class="sxs-lookup"><span data-stu-id="e856c-103">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>

<span data-ttu-id="e856c-104">[Политики собраний](meeting-policies-in-teams.md) в Microsoft Teams используются для управления возможностями, доступными участникам собрания для собраний, запланированных пользователями в Организации.</span><span class="sxs-lookup"><span data-stu-id="e856c-104">[Meeting policies](meeting-policies-in-teams.md) in Microsoft Teams are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> 

<span data-ttu-id="e856c-105">Команды включают встроенную политику с именем RestrictedAnonymousAccess, которая содержит предопределенные параметры, которые включают в себя запрет на запуск собрания анонимными пользователями.</span><span class="sxs-lookup"><span data-stu-id="e856c-105">Teams includes a built-in policy named RestrictedAnonymousAccess, which contains pre-defined settings that include restricting anonymous users from starting a meeting.</span></span> <span data-ttu-id="e856c-106">(Анонимные пользователи — это пользователи, которые не прошли проверку подлинности.) Предопределенные параметры в политике собрания невозможно изменить или изменить с помощью администраторов.</span><span class="sxs-lookup"><span data-stu-id="e856c-106">(Anonymous users are users who haven't been authenticated.) The predefined settings in the meeting policy can't be edited or changed by admins.</span></span>

<span data-ttu-id="e856c-107">В этой статье объясняется, как использовать PowerShell для удаления политики собраний RestrictedAnonymousAccess от пользователей, которым назначена эта политика.</span><span class="sxs-lookup"><span data-stu-id="e856c-107">This article shows you how to use PowerShell to remove the RestrictedAnonymousAccess meeting policy from users who are assigned this policy.</span></span> <span data-ttu-id="e856c-108">Дополнительные сведения о том, как управлять группами с помощью PowerShell, можно найти в разделе [Общие сведения о Teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e856c-108">To learn more about how to manage Teams using PowerShell, see [Teams PowerShell overview](teams-powershell-overview.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="e856c-109">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="e856c-109">Before you start</span></span>

<span data-ttu-id="e856c-110">Установите и подключитесь к [модулю PowerShell Skype для бизнеса](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="e856c-110">Install and connect to the [Skype for Business PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="e856c-111">Пошаговые инструкции можно найти в статье [Установка Microsoft Teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="e856c-111">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a><span data-ttu-id="e856c-112">Получение назначений политики собраний Teams для Организации</span><span class="sxs-lookup"><span data-stu-id="e856c-112">Get the Teams meeting policy assignments for your organization</span></span>

<span data-ttu-id="e856c-113">Выполните указанные ниже действия, чтобы получить назначения политики для собраний Teams для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e856c-113">Run the following to get the Teams meeting policy assignments for your organization.</span></span>

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

<span data-ttu-id="e856c-114">В этом примере возвращается приведенный ниже вывод, в котором показано, что двум пользователям назначена политика собраний RestrictedAnonymousAccess.</span><span class="sxs-lookup"><span data-stu-id="e856c-114">In this example, the following output is returned, which shows that two users are assigned the RestrictedAnonymousAccess meeting policy.</span></span>

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a><span data-ttu-id="e856c-115">Отмена назначения политики собрания RestrictedAnonymous пользователям</span><span class="sxs-lookup"><span data-stu-id="e856c-115">Unassign the RestrictedAnonymous meeting policy from users</span></span>

<span data-ttu-id="e856c-116">Чтобы удалить политику собраний RestrictedAnonymous от пользователей, можно использовать командлет [Grant-CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) , если у вас небольшое количество пользователей (например, менее 100 пользователей).</span><span class="sxs-lookup"><span data-stu-id="e856c-116">To remove the the RestrictedAnonymous meeting policy from users, you can use the [Grant-CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) cmdlet if you have a small number of users (for example, less than 100 users).</span></span> <span data-ttu-id="e856c-117">Если у вас большое количество пользователей (например, более 100 пользователей), более эффективно использовать командлет [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) для отправки пакетной операции.</span><span class="sxs-lookup"><span data-stu-id="e856c-117">If you have a large number of users (for example, more than 100 users), it's more efficient to use the  [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet to submit a batch operation.</span></span>

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a><span data-ttu-id="e856c-118">Использование командлета Grant-CsTeamsMeeting</span><span class="sxs-lookup"><span data-stu-id="e856c-118">Use the Grant-CsTeamsMeeting Policy cmdlet</span></span>

<span data-ttu-id="e856c-119">Выполните указанные ниже действия, чтобы удалить политику собраний RestrictedAnonymous из пользователей.</span><span class="sxs-lookup"><span data-stu-id="e856c-119">Run the following to remove the RestrictedAnonymous meeting policy from users.</span></span>

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a><span data-ttu-id="e856c-120">Использование командлета New-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="e856c-120">Use the New-CsBatchPolicyAssignmentOperation cmdlet</span></span>

<span data-ttu-id="e856c-121">При [назначении пакетной политики](assign-policies.md#assign-a-policy-to-a-batch-of-users)максимальное количество пользователей, для которых можно удалить или изменить политики, составляет 5 000 за один раз.</span><span class="sxs-lookup"><span data-stu-id="e856c-121">With [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users), the maximum number of users for which you can remove or update policies is 5,000 at a time.</span></span> <span data-ttu-id="e856c-122">Например, если у вас более 5 000 пользователей, вам нужно будет отправить несколько пакетов.</span><span class="sxs-lookup"><span data-stu-id="e856c-122">For example, if you have more than 5,000 users, you'll need to submit multiple batches.</span></span> <span data-ttu-id="e856c-123">Для достижения наилучших результатов не отправляйте в каждый момент времени несколько пакетов.</span><span class="sxs-lookup"><span data-stu-id="e856c-123">For best results, do not submit multiple batches at a time.</span></span> <span data-ttu-id="e856c-124">Разрешите пакетам завершить обработку перед отправкой пакетов.</span><span class="sxs-lookup"><span data-stu-id="e856c-124">Allow batches to complete processing before submitting more batches.</span></span>

> [!NOTE]
> <span data-ttu-id="e856c-125">Командлет [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) находится в модуле PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="e856c-125">The [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet is in the Teams PowerShell module.</span></span> <span data-ttu-id="e856c-126">Перед тем как выполнять эти действия, установите и подключитесь к [модулю PowerShell Teams](https://www.powershellgallery.com/packages/MicrosoftTeams).</span><span class="sxs-lookup"><span data-stu-id="e856c-126">Before you follow these steps, install and connect to the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="e856c-127">Пошаговые инструкции можно найти в статье [Установка Microsoft Teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="e856c-127">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

<span data-ttu-id="e856c-128">Чтобы удалить политику собраний RestrictedAnonymousAccess из пакета пользователей, выполните указанные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="e856c-128">Run the following commands to remove the RestrictedAnonymousAccess meeting policy from a batch of users.</span></span>

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a><span data-ttu-id="e856c-129">Получение статуса задания партии</span><span class="sxs-lookup"><span data-stu-id="e856c-129">Get the status of the batch assignment</span></span>

<span data-ttu-id="e856c-130">Каждое назначение партии возвращает идентификатор операции, который можно использовать для отслеживания хода выполнения и состояния назначений, а также для выявления проблем, которые могут возникнуть.</span><span class="sxs-lookup"><span data-stu-id="e856c-130">Each batch assignment returns an operation ID, which you can use to track the progress and status of the assignments and identify any failures that might occur.</span></span> <span data-ttu-id="e856c-131">Например, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="e856c-131">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

<span data-ttu-id="e856c-132">Убедитесь в том, что **ErrorCount** равен **0** (нулю), а **OverallStatus** — **завершено**.</span><span class="sxs-lookup"><span data-stu-id="e856c-132">Make sure the **ErrorCount** is **0** (zero) and **OverallStatus** is **Completed**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e856c-133">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="e856c-133">Related topics</span></span>

- [<span data-ttu-id="e856c-134">Управление политиками собраний в Teams</span><span class="sxs-lookup"><span data-stu-id="e856c-134">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
- [<span data-ttu-id="e856c-135">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="e856c-135">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="e856c-136">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="e856c-136">Assign policies to your users in Teams</span></span>](assign-policies.md)
