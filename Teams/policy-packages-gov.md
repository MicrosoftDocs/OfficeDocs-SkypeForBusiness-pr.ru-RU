---
title: Пакеты политики Teams для государственных органов
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
description: Узнайте, как использовать пакеты политики Teams для государственных организаций и управлять ими.
ms.openlocfilehash: 19e2c692f2b5109e3ef0915ced9fd2b68c56e482
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812889"
---
# <a name="teams-policy-packages-for-government"></a><span data-ttu-id="53079-103">Пакеты политики Teams для государственных органов</span><span class="sxs-lookup"><span data-stu-id="53079-103">Teams policy packages for government</span></span>

> [!NOTE]
> <span data-ttu-id="53079-104">Пакеты политики в настоящее время недоступны в развертываниях Microsoft 365 government GCC High или DoD.</span><span class="sxs-lookup"><span data-stu-id="53079-104">Policy packages are currently not available in Microsoft 365 Government GCC High or DoD deployments.</span></span>

## <a name="overview"></a><span data-ttu-id="53079-105">Обзор</span><span class="sxs-lookup"><span data-stu-id="53079-105">Overview</span></span>

<span data-ttu-id="53079-106">Пакет [политики](manage-policy-packages.md) в Microsoft Teams — это набор предопределельных политик и параметров политики, которые можно назначать пользователям с похожими ролями в организации.</span><span class="sxs-lookup"><span data-stu-id="53079-106">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="53079-107">Пакеты политик упрощают, оптимизируют и помогают обеспечивать согласованность при управлении политиками.</span><span class="sxs-lookup"><span data-stu-id="53079-107">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="53079-108">Вы можете настроить параметры политик в пакете в соответствии с потребностями пользователей.</span><span class="sxs-lookup"><span data-stu-id="53079-108">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="53079-109">При изменении параметров политик в пакете политики все пользователи, которым он назначен, получают обновленные параметры.</span><span class="sxs-lookup"><span data-stu-id="53079-109">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="53079-110">Вы можете управлять пакетами политики с помощью Центра администрирования Microsoft Teams или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="53079-110">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="53079-111">Пакеты политик предопределяют политики для следующих пакетов в зависимости от пакета:</span><span class="sxs-lookup"><span data-stu-id="53079-111">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="53079-112">Обмен сообщениями</span><span class="sxs-lookup"><span data-stu-id="53079-112">Messaging</span></span>
- <span data-ttu-id="53079-113">Собрания</span><span class="sxs-lookup"><span data-stu-id="53079-113">Meetings</span></span>
- <span data-ttu-id="53079-114">Звонки</span><span class="sxs-lookup"><span data-stu-id="53079-114">Calling</span></span>
- <span data-ttu-id="53079-115">Настройка приложения</span><span class="sxs-lookup"><span data-stu-id="53079-115">App setup</span></span>
- <span data-ttu-id="53079-116">Трансляции</span><span class="sxs-lookup"><span data-stu-id="53079-116">Live events</span></span>

<span data-ttu-id="53079-117">В настоящее время Teams содержит следующие пакеты политики для государственных органов.</span><span class="sxs-lookup"><span data-stu-id="53079-117">Teams currently includes the following policy packages for government.</span></span>

|<span data-ttu-id="53079-118">Имя пакета в Центре администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="53079-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="53079-119">Кому предназначено</span><span class="sxs-lookup"><span data-stu-id="53079-119">Best used for</span></span>|<span data-ttu-id="53079-120">Описание</span><span class="sxs-lookup"><span data-stu-id="53079-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="53079-121">Сотрудница по безопасности</span><span class="sxs-lookup"><span data-stu-id="53079-121">Public safety officer</span></span>  |<span data-ttu-id="53079-122">Сотрудники, которые работают с обеспечением безопасности в правительственных организациях</span><span class="sxs-lookup"><span data-stu-id="53079-122">Public safety officers in your government organization</span></span>  |<span data-ttu-id="53079-123">Создает набор политик и параметров политики, которые применяются к сотрудникам, которые работают с политикой безопасности других лиц в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="53079-123">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span> |
|<span data-ttu-id="53079-124">Firstline Manager</span><span class="sxs-lookup"><span data-stu-id="53079-124">Firstline manager</span></span>  |<span data-ttu-id="53079-125">Руководители firstline в государственных организациях</span><span class="sxs-lookup"><span data-stu-id="53079-125">Firstline Managers in your government organization</span></span> |<span data-ttu-id="53079-126">Создает набор политик и применяет их к руководителям без компьютеров в организации.</span><span class="sxs-lookup"><span data-stu-id="53079-126">Creates a set of policies and applies those settings to Firstline Managers in your organization.</span></span>|
|<span data-ttu-id="53079-127">Сотрудник без телефонов</span><span class="sxs-lookup"><span data-stu-id="53079-127">Firstline worker</span></span>  |<span data-ttu-id="53079-128">Сотрудники без компьютеров в правительственных организациях</span><span class="sxs-lookup"><span data-stu-id="53079-128">Firstline Workers in your government organization</span></span> |<span data-ttu-id="53079-129">Создает набор политик и применяет эти параметры к сотрудникам без компьютеров в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="53079-129">Creates a set of policies and applies those settings to Firstline Workers in your organization.</span></span>|

![Снимок экрана: пакеты политик здравоохранения](media/policy-packages-gov.png)

<span data-ttu-id="53079-131">Каждой отдельной политике дается имя пакета политики, чтобы можно было легко определить политики, связанные с пакетом политики.</span><span class="sxs-lookup"><span data-stu-id="53079-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="53079-132">Например, при назначении пакета политики "Сотрудник по безопасности общедоступных данных" пользователям в организации создается политика с именем PublicSafety_Officer для каждой политики в этом пакете.</span><span class="sxs-lookup"><span data-stu-id="53079-132">For example, when you assign the Public safety officer policy package to users in your organization, a policy named PublicSafety_Officer is created for each policy in the package.</span></span>

![Снимок экрана: политики в пакете "Клинические работники здравоохранения"](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="53079-134">Управление пакетами политик</span><span class="sxs-lookup"><span data-stu-id="53079-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="53079-135">Просмотр</span><span class="sxs-lookup"><span data-stu-id="53079-135">View</span></span>

<span data-ttu-id="53079-136">Перед тем как назначать пакет, просмотрите параметры каждой политики в пакете политик.</span><span class="sxs-lookup"><span data-stu-id="53079-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="53079-137">В левой области навигации Центра администрирования Microsoft Teams нажмите **Пакеты политик**, выберите имя пакета, а затем имя политики.</span><span class="sxs-lookup"><span data-stu-id="53079-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="53079-138">Решите, соответствуют ли готовые значения вашей организации или нужно настроить их, чтобы они были более или менее строгими, исходя из потребностей организации.</span><span class="sxs-lookup"><span data-stu-id="53079-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="53079-139">Настройка</span><span class="sxs-lookup"><span data-stu-id="53079-139">Customize</span></span>

<span data-ttu-id="53079-140">При необходимости настройте параметры политики в пакете политик, чтобы они соответствовали потребностям вашей организации.</span><span class="sxs-lookup"><span data-stu-id="53079-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="53079-141">Изменения, внесенные в параметры политики, автоматически применяются к пользователям, которым назначен пакет.</span><span class="sxs-lookup"><span data-stu-id="53079-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="53079-142">Чтобы изменить параметры политики в пакете политик, в Центре администрирования Microsoft Teams выберите пакет политики, нажмите имя политики, которую вы хотите изменить, а затем щелкните **Правка**.</span><span class="sxs-lookup"><span data-stu-id="53079-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="53079-143">Обратите внимание, что также можно изменить параметры политик в пакете после назначения пакета политики.</span><span class="sxs-lookup"><span data-stu-id="53079-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="53079-144">Дополнительные сведения см. в статье [Настройка политик в пакете политики](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="53079-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="53079-145">Назначение</span><span class="sxs-lookup"><span data-stu-id="53079-145">Assign</span></span>

<span data-ttu-id="53079-146">Назначение пакета политики пользователям.</span><span class="sxs-lookup"><span data-stu-id="53079-146">Assign the policy package to users.</span></span> <span data-ttu-id="53079-147">Если пользователю с назначенной политикой, назначается другая, приоритет будет иметь самое последнее назначение.</span><span class="sxs-lookup"><span data-stu-id="53079-147">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="53079-148">Назначение пакета политики для одного или нескольких пользователей</span><span class="sxs-lookup"><span data-stu-id="53079-148">Assign a policy package to one or several users</span></span>

<span data-ttu-id="53079-149">Чтобы назначить пакет политики одному или нескольким пользователям, в левой области навигации Центра администрирования Microsoft Teams перейдите в раздел **Пакеты политик**, а затем выберите **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="53079-149">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select **Manage users**.</span></span>  

![Снимок экрана с назначением пакета политики в центре администрирования](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="53079-151">Дополнительные сведения см. в статье [Назначение пакета политики](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="53079-151">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="53079-152">Если пользователю с назначенной политикой, назначается другая, приоритет будет иметь самое последнее назначение.</span><span class="sxs-lookup"><span data-stu-id="53079-152">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="53079-153">Назначение пакета политики группе</span><span class="sxs-lookup"><span data-stu-id="53079-153">Assign a policy package to a group</span></span>

<span data-ttu-id="53079-154">**Эта функция доступна в закрытой ознакомительной версии**</span><span class="sxs-lookup"><span data-stu-id="53079-154">**This feature is in private preview**</span></span>

<span data-ttu-id="53079-155">Назначение пакетов политики группам позволяет назначать несколько политик группе пользователей, например группе безопасности или группе рассылки.</span><span class="sxs-lookup"><span data-stu-id="53079-155">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="53079-156">Назначение политики распространяется на участников группы в соответствии с правилами очередности.</span><span class="sxs-lookup"><span data-stu-id="53079-156">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="53079-157">При добавлении или удалении участников группы, назначения политик для них обновляются соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="53079-157">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="53079-158">Этот способ рекомендуется для групп, включающих до 50 000 пользователей, но также подойдет и для больших групп.</span><span class="sxs-lookup"><span data-stu-id="53079-158">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="53079-159">Дополнительные сведения см. в статье [Назначение пакета политики группе](assign-policies.md#assign-a-policy-package-to-a-group).</span><span class="sxs-lookup"><span data-stu-id="53079-159">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="53079-160">Назначение пакета политики множеству (пакету) пользователей</span><span class="sxs-lookup"><span data-stu-id="53079-160">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="53079-161">Используйте назначение группового пакета политики, чтобы назначить пакет политики для множества пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="53079-161">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="53079-162">Используйте командлет [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation), чтобы отправить множество пользователей и пакет политики, который вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="53079-162">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="53079-163">Задания будут обрабатываться в фоновом режиме, а для каждого пакета будет создан идентификатор операции.</span><span class="sxs-lookup"><span data-stu-id="53079-163">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="53079-164">Пакет может содержать до 5 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="53079-164">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="53079-165">Можно указать пользователей по идентификатору объекта, UPN, адресу протокола SIP или электронной почты.</span><span class="sxs-lookup"><span data-stu-id="53079-165">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="53079-166">Дополнительные сведения см. в статье [Назначение пакета политики множеству пользователей](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span><span class="sxs-lookup"><span data-stu-id="53079-166">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="53079-167">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="53079-167">Related topics</span></span>

[<span data-ttu-id="53079-168">Управление пакетами политик в Teams</span><span class="sxs-lookup"><span data-stu-id="53079-168">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="53079-169">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="53079-169">Assign policies to your users in Teams</span></span>](assign-policies.md) 
