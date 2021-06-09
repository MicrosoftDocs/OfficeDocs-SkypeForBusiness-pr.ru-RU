---
title: Teams пакеты политик для государственных органов
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
description: Узнайте, как использовать пакеты политик Teams для государственных организаций и управлять ими.
ms.openlocfilehash: 41ae937323b37948c03128efd565f40c02bbd6a2
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796873"
---
# <a name="teams-policy-packages-for-government"></a><span data-ttu-id="85550-103">Teams пакеты политик для государственных органов</span><span class="sxs-lookup"><span data-stu-id="85550-103">Teams policy packages for government</span></span>

> [!NOTE]
> <span data-ttu-id="85550-104">Пакеты политик в настоящее время недоступны в Microsoft 365 для государственных GCC или DoD.</span><span class="sxs-lookup"><span data-stu-id="85550-104">Policy packages are currently not available in Microsoft 365 Government GCC High or DoD deployments.</span></span>

## <a name="overview"></a><span data-ttu-id="85550-105">Обзор</span><span class="sxs-lookup"><span data-stu-id="85550-105">Overview</span></span>

<span data-ttu-id="85550-106">[Пакет политики](manage-policy-packages.md) в Microsoft Teams — это набор готовых политик и параметров политик, которые можно назначить пользователям с похожими ролями в организации.</span><span class="sxs-lookup"><span data-stu-id="85550-106">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="85550-107">Пакеты политик упрощают, оптимизируют и помогают обеспечивать согласованность при управлении политиками.</span><span class="sxs-lookup"><span data-stu-id="85550-107">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="85550-108">Вы можете настроить параметры политик в пакете в соответствии с потребностями пользователей.</span><span class="sxs-lookup"><span data-stu-id="85550-108">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="85550-109">При изменении параметров политик в пакете политик все пользователи, которым назначен этот пакет, получают обновленные параметры.</span><span class="sxs-lookup"><span data-stu-id="85550-109">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="85550-110">Вы можете управлять пакетами политик с помощью Центра администрирования Microsoft Teams или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="85550-110">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="85550-111">Пакеты политик предопределяют политики для следующих функций в зависимости от пакета.</span><span class="sxs-lookup"><span data-stu-id="85550-111">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="85550-112">Обмен сообщениями</span><span class="sxs-lookup"><span data-stu-id="85550-112">Messaging</span></span>
- <span data-ttu-id="85550-113">Собрания</span><span class="sxs-lookup"><span data-stu-id="85550-113">Meetings</span></span>
- <span data-ttu-id="85550-114">Звонки</span><span class="sxs-lookup"><span data-stu-id="85550-114">Calling</span></span>
- <span data-ttu-id="85550-115">Настройка приложения</span><span class="sxs-lookup"><span data-stu-id="85550-115">App setup</span></span>
- <span data-ttu-id="85550-116">Трансляции</span><span class="sxs-lookup"><span data-stu-id="85550-116">Live events</span></span>

<span data-ttu-id="85550-117">Teams настоящее время включены следующие пакеты политики для государственных органов.</span><span class="sxs-lookup"><span data-stu-id="85550-117">Teams currently includes the following policy packages for government.</span></span>

|<span data-ttu-id="85550-118">Имя пакета в Центре администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="85550-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="85550-119">Кому предназначено</span><span class="sxs-lookup"><span data-stu-id="85550-119">Best used for</span></span>|<span data-ttu-id="85550-120">Описание</span><span class="sxs-lookup"><span data-stu-id="85550-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="85550-121">Сотрудник по обеспечению безопасности</span><span class="sxs-lookup"><span data-stu-id="85550-121">Public safety officer</span></span>  |<span data-ttu-id="85550-122">Сотрудники по обеспечению безопасности в правительственных организациях</span><span class="sxs-lookup"><span data-stu-id="85550-122">Public safety officers in your government organization</span></span>  |<span data-ttu-id="85550-123">Создает набор политик и параметров политики, которые применяются к сотрудникам, которые работают с политикой безопасности в организации.</span><span class="sxs-lookup"><span data-stu-id="85550-123">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span> |
|<span data-ttu-id="85550-124">Диспетчер переднего звена</span><span class="sxs-lookup"><span data-stu-id="85550-124">Frontline manager</span></span>  |<span data-ttu-id="85550-125">Руководители переднего звена в государственных организациях</span><span class="sxs-lookup"><span data-stu-id="85550-125">Frontline Managers in your government organization</span></span> |<span data-ttu-id="85550-126">Создает набор политик и применяет эти параметры к руководителям frontline в организации.</span><span class="sxs-lookup"><span data-stu-id="85550-126">Creates a set of policies and applies those settings to Frontline Managers in your organization.</span></span>|
|<span data-ttu-id="85550-127">Фронтальная сотрудница</span><span class="sxs-lookup"><span data-stu-id="85550-127">Frontline worker</span></span>  |<span data-ttu-id="85550-128">Frontline Workers in your government organization</span><span class="sxs-lookup"><span data-stu-id="85550-128">Frontline Workers in your government organization</span></span> |<span data-ttu-id="85550-129">Создает набор политик и применяет эти параметры к сотрудникам, работающим с frontline в организации.</span><span class="sxs-lookup"><span data-stu-id="85550-129">Creates a set of policies and applies those settings to Frontline Workers in your organization.</span></span>|

![Снимок экрана: пакеты политик для здравоохранения](media/policy-packages-gov.png)

<span data-ttu-id="85550-131">Каждой отдельной политике присваивается имя пакета политики, чтобы легко определять политики, связанные с пакетом.</span><span class="sxs-lookup"><span data-stu-id="85550-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="85550-132">Например, при назначении пакета политики "Сотрудник по обеспечению безопасности" пользователям в организации для каждой политики в пакете создается PublicSafety_Officer политика с именем "Сотрудник по безопасности".</span><span class="sxs-lookup"><span data-stu-id="85550-132">For example, when you assign the Public safety officer policy package to users in your organization, a policy named PublicSafety_Officer is created for each policy in the package.</span></span>

![Снимок экрана: политики в пакете "Медицинский работник в учреждении здравоохранения"](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="85550-134">Управление пакетами политик</span><span class="sxs-lookup"><span data-stu-id="85550-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="85550-135">Просмотр</span><span class="sxs-lookup"><span data-stu-id="85550-135">View</span></span>

<span data-ttu-id="85550-136">Перед тем как назначать пакет, просмотрите параметры каждой политики в пакете политик.</span><span class="sxs-lookup"><span data-stu-id="85550-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="85550-137">В левой области навигации Центра администрирования Microsoft Teams нажмите **Пакеты политик**, выберите имя пакета, а затем имя политики.</span><span class="sxs-lookup"><span data-stu-id="85550-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="85550-138">Решите, соответствуют ли готовые значения вашей организации или нужно настроить их, чтобы они были более или менее строгими, исходя из потребностей организации.</span><span class="sxs-lookup"><span data-stu-id="85550-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="85550-139">Настройка</span><span class="sxs-lookup"><span data-stu-id="85550-139">Customize</span></span>

<span data-ttu-id="85550-140">При необходимости настройте параметры политики в пакете политик, чтобы они соответствовали потребностям вашей организации.</span><span class="sxs-lookup"><span data-stu-id="85550-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="85550-141">Изменения, внесенные в параметры политики, автоматически применяются к пользователям, которым назначен пакет.</span><span class="sxs-lookup"><span data-stu-id="85550-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="85550-142">Чтобы изменить параметры политики в пакете политик, в Центре администрирования Microsoft Teams выберите пакет политики, нажмите имя политики, которую вы хотите изменить, а затем щелкните **Правка**.</span><span class="sxs-lookup"><span data-stu-id="85550-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="85550-143">Обратите внимание, что также можно изменить параметры политик в пакете после назначения пакета политики.</span><span class="sxs-lookup"><span data-stu-id="85550-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="85550-144">Дополнительные сведения см. в статье [Настройка политик в пакете политики](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="85550-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="85550-145">Назначение</span><span class="sxs-lookup"><span data-stu-id="85550-145">Assign</span></span>

<span data-ttu-id="85550-p106">Назначение пакета политики пользователям. Если пользователю с назначенной политикой назначается другая, приоритет будет иметь самое последнее назначение.</span><span class="sxs-lookup"><span data-stu-id="85550-p106">Assign the policy package to users. If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

> [!NOTE]
> <span data-ttu-id="85550-148">Для получения назначения пользовательского пакета политики каждому пользователю потребуется надстройка Advanced Communications.</span><span class="sxs-lookup"><span data-stu-id="85550-148">Each user will require the Advanced Communications add-on in order to receive a custom policy package assignment.</span></span> <span data-ttu-id="85550-149">Дополнительные сведения см. в [этой](/microsoftteams/teams-add-on-licensing/advanced-communications)Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="85550-149">For more information, see [Advanced Communications add-on for Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="85550-150">Назначение пакета политики для одного или нескольких пользователей</span><span class="sxs-lookup"><span data-stu-id="85550-150">Assign a policy package to one or several users</span></span>

<span data-ttu-id="85550-151">Чтобы назначить пакет политики одному или нескольким пользователям, в левой области навигации Центра администрирования Microsoft Teams перейдите в раздел **Пакеты политик**, а затем выберите **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="85550-151">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select **Manage users**.</span></span>  

![Снимок экрана с назначением пакета политики в центре администрирования](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="85550-153">Дополнительные сведения см. в статье [Назначение пакета политики](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="85550-153">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="85550-154">Если пользователю с назначенной политикой, назначается другая, приоритет будет иметь самое последнее назначение.</span><span class="sxs-lookup"><span data-stu-id="85550-154">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="85550-155">Назначение пакета политики группе</span><span class="sxs-lookup"><span data-stu-id="85550-155">Assign a policy package to a group</span></span>

<span data-ttu-id="85550-156">**Эта функция доступна в закрытой ознакомительной версии**</span><span class="sxs-lookup"><span data-stu-id="85550-156">**This feature is in private preview**</span></span>

<span data-ttu-id="85550-157">Назначение пакетов политики группам позволяет назначать несколько политик группе пользователей, например группе безопасности или группе рассылки.</span><span class="sxs-lookup"><span data-stu-id="85550-157">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="85550-158">Назначение политики распространяется на участников группы в соответствии с правилами очередности.</span><span class="sxs-lookup"><span data-stu-id="85550-158">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="85550-159">При добавлении или удалении участников группы, назначения политик для них обновляются соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="85550-159">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="85550-160">Этот способ рекомендуется для групп, включающих до 50 000 пользователей, но также подойдет и для больших групп.</span><span class="sxs-lookup"><span data-stu-id="85550-160">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="85550-161">Дополнительные сведения см. в статье [Назначение пакета политики группе](assign-policies.md#assign-a-policy-package-to-a-group).</span><span class="sxs-lookup"><span data-stu-id="85550-161">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="85550-162">Назначение пакета политики множеству (пакету) пользователей</span><span class="sxs-lookup"><span data-stu-id="85550-162">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="85550-163">Используйте назначение группового пакета политики, чтобы назначить пакет политики для множества пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="85550-163">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="85550-164">Используйте командлет [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation), чтобы отправить множество пользователей и пакет политики, который вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="85550-164">You use the [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="85550-165">Задания будут обрабатываться в фоновом режиме, а для каждого пакета будет создан идентификатор операции.</span><span class="sxs-lookup"><span data-stu-id="85550-165">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="85550-166">Пакет может содержать до 5 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="85550-166">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="85550-167">Можно указать пользователей по идентификатору объекта, UPN, адресу протокола SIP или электронной почты.</span><span class="sxs-lookup"><span data-stu-id="85550-167">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="85550-168">Дополнительные сведения см. в статье [Назначение пакета политики множеству пользователей](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span><span class="sxs-lookup"><span data-stu-id="85550-168">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="85550-169">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="85550-169">Related topics</span></span>

[<span data-ttu-id="85550-170">Управление пакетами политик в Teams</span><span class="sxs-lookup"><span data-stu-id="85550-170">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="85550-171">Назначение пакетов политики пользователям и группам</span><span class="sxs-lookup"><span data-stu-id="85550-171">Assign policy packages to users and groups</span></span>](assign-policy-packages.md)
