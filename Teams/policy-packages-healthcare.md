---
title: Пакеты политик Teams для здравоохранения
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
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Узнайте, как использовать пакеты политик Teams для своей медицинской организации и управлять ими.
ms.openlocfilehash: 830b8fc5f6938f84f188f5f5d732a3ecfd6eb5b1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117767"
---
# <a name="teams-policy-packages-for-healthcare"></a><span data-ttu-id="0a791-103">Пакеты политик Teams для здравоохранения</span><span class="sxs-lookup"><span data-stu-id="0a791-103">Teams policy packages for healthcare</span></span>

## <a name="overview"></a><span data-ttu-id="0a791-104">Обзор</span><span class="sxs-lookup"><span data-stu-id="0a791-104">Overview</span></span>

<span data-ttu-id="0a791-105">[Пакет политики](manage-policy-packages.md) в Microsoft Teams — это набор готовых политик и параметров политик, которые можно назначить пользователям с похожими ролями в организации.</span><span class="sxs-lookup"><span data-stu-id="0a791-105">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="0a791-106">Пакеты политик упрощают, оптимизируют и помогают обеспечивать согласованность при управлении политиками.</span><span class="sxs-lookup"><span data-stu-id="0a791-106">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="0a791-107">Вы можете настроить параметры политик в пакете в соответствии с потребностями пользователей.</span><span class="sxs-lookup"><span data-stu-id="0a791-107">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="0a791-108">При изменении параметров политик в пакете политик все пользователи, которым назначен этот пакет, получают обновленные параметры.</span><span class="sxs-lookup"><span data-stu-id="0a791-108">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="0a791-109">Вы можете управлять пакетами политик с помощью Центра администрирования Microsoft Teams или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0a791-109">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Ht2o]

<span data-ttu-id="0a791-110">Пакеты политик предопределяют политики для следующих функций в зависимости от пакета.</span><span class="sxs-lookup"><span data-stu-id="0a791-110">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="0a791-111">Обмен сообщениями</span><span class="sxs-lookup"><span data-stu-id="0a791-111">Messaging</span></span>
- <span data-ttu-id="0a791-112">Собрания</span><span class="sxs-lookup"><span data-stu-id="0a791-112">Meetings</span></span>
- <span data-ttu-id="0a791-113">Звонки</span><span class="sxs-lookup"><span data-stu-id="0a791-113">Calling</span></span>
- <span data-ttu-id="0a791-114">Настройка приложения</span><span class="sxs-lookup"><span data-stu-id="0a791-114">App setup</span></span>
- <span data-ttu-id="0a791-115">Трансляции</span><span class="sxs-lookup"><span data-stu-id="0a791-115">Live events</span></span>

<span data-ttu-id="0a791-116">В настоящее время Teams включает следующие пакеты политик для здравоохранения.</span><span class="sxs-lookup"><span data-stu-id="0a791-116">Teams currently includes the following healthcare policy packages.</span></span>

|<span data-ttu-id="0a791-117">Имя пакета в Центре администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0a791-117">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="0a791-118">Кому предназначено</span><span class="sxs-lookup"><span data-stu-id="0a791-118">Best used for</span></span>|<span data-ttu-id="0a791-119">Описание</span><span class="sxs-lookup"><span data-stu-id="0a791-119">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="0a791-120">Медицинский работник в учреждении здравоохранения</span><span class="sxs-lookup"><span data-stu-id="0a791-120">Healthcare clinical worker</span></span>  |<span data-ttu-id="0a791-121">Медицинские работники в организации здравоохранения</span><span class="sxs-lookup"><span data-stu-id="0a791-121">Clinical workers in your healthcare organization</span></span>  |<span data-ttu-id="0a791-122">Создает набор политик и параметров политик, предоставляющий медицинским работникам, таким как медсестры, старшие сестры, терапевты и социальные работники, полный доступ к чатам, звонкам, управлению сменами и собраниям.</span><span class="sxs-lookup"><span data-stu-id="0a791-122">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="0a791-123">Информационный работник в учреждении здравоохранения</span><span class="sxs-lookup"><span data-stu-id="0a791-123">Healthcare information worker</span></span>  |<span data-ttu-id="0a791-124">Информационные работники в организации здравоохранения</span><span class="sxs-lookup"><span data-stu-id="0a791-124">Information workers in your healthcare organization</span></span> |<span data-ttu-id="0a791-125">Создает набор политик и параметров политик, предоставляющий информационным сотрудникам, таким как ИТ-персонал, информационный персонал, финансовый персонал и сотрудники по обеспечению соответствия требованиям, полный доступ к чатам, звонкам и собраниям.</span><span class="sxs-lookup"><span data-stu-id="0a791-125">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="0a791-126">Палата для пациентов в учреждении здравоохранения</span><span class="sxs-lookup"><span data-stu-id="0a791-126">Healthcare patient room</span></span>  |<span data-ttu-id="0a791-127">Устройства палат для пациентов</span><span class="sxs-lookup"><span data-stu-id="0a791-127">Patient room devices</span></span>|<span data-ttu-id="0a791-128">Создает набор политик и параметров политик, применяемый к палатам для пациентов в медицинской организации.</span><span class="sxs-lookup"><span data-stu-id="0a791-128">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|

![Снимок экрана: пакеты политик для здравоохранения](media/policy-packages-healthcare.png)

<span data-ttu-id="0a791-130">Каждой отдельной политике присваивается имя пакета политики, чтобы легко определять политики, связанные с пакетом.</span><span class="sxs-lookup"><span data-stu-id="0a791-130">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="0a791-131">Например, когда вы назначаете пакет политик "Медицинский работник в учреждении здравоохранения" медицинским работникам в своей организации, для каждой политики в пакете создается политика с именем Healthcare_ClinicalWorker.</span><span class="sxs-lookup"><span data-stu-id="0a791-131">For example, when you assign the Healthcare clinical worker policy package to clinicians in your organization, a policy named Healthcare_ClinicalWorker is created for each policy in the package.</span></span>

![Снимок экрана: политики в пакете "Медицинский работник в учреждении здравоохранения"](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a><span data-ttu-id="0a791-133">Начало работы с пакетами политик</span><span class="sxs-lookup"><span data-stu-id="0a791-133">Get started with policy packages</span></span>

<span data-ttu-id="0a791-134">Чтобы начать работу с пакетами политик для здравоохранения, в центре подключения Центра администрирования Майкрософт выберите **Здравоохранение**, а затем — **Назначить параметры политики по роли**.</span><span class="sxs-lookup"><span data-stu-id="0a791-134">To get you started with Healthcare policy packages, on the Microsoft Admin Center onboarding hub, select **Healthcare**, and then select **Assign policy settings by role**.</span></span> <span data-ttu-id="0a791-135">Когда будете готовы начать, решите, какие пакеты политик нужно назначить пользователям в организации.</span><span class="sxs-lookup"><span data-stu-id="0a791-135">Once you’re ready to get started, decide which policy packages you'd like to assign individuals in your organization to.</span></span>

<span data-ttu-id="0a791-136">Выберите **Просмотреть сведения политики**, чтобы узнать больше об определенных политиках в пакете и соответствующих параметрах.</span><span class="sxs-lookup"><span data-stu-id="0a791-136">Select **View policy details** to learn more about the specific policies in a package and their respective settings.</span></span> <span data-ttu-id="0a791-137">Их [можно настроить](manage-policy-packages.md#customize-policies-in-a-policy-package) после назначения в Центре администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="0a791-137">These [can be customized](manage-policy-packages.md#customize-policies-in-a-policy-package) after assignment in the Teams Admin Center.</span></span>

<span data-ttu-id="0a791-138">Выберите один или несколько пакетов, которые нужно назначить, и нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0a791-138">Choose one or multiple packages to assign and then click **Next**.</span></span> <span data-ttu-id="0a791-139">Вы можете искать и добавлять людей в пакет политик, наиболее подходящий для их роли.</span><span class="sxs-lookup"><span data-stu-id="0a791-139">You can search for and add people to the policy package best suited for their role.</span></span> <span data-ttu-id="0a791-140">Отдельного человека нельзя назначить в несколько пакетов политик одновременно.</span><span class="sxs-lookup"><span data-stu-id="0a791-140">An individual can't be assigned to more than one policy package at one time.</span></span>

<span data-ttu-id="0a791-141">Добавив людей в нужный пакет политик, нажмите **Завершить**, чтобы подтвердить выбор.</span><span class="sxs-lookup"><span data-stu-id="0a791-141">Once you’ve added people to the right policy package, **Finish** finalizes your selections.</span></span> <span data-ttu-id="0a791-142">Вы можете продолжить настройку пакетов политик и управлять ими в Центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0a791-142">You can continue to customize and manage policy packages in the Microsoft Teams admin center.</span></span>

## <a name="manage-policy-packages"></a><span data-ttu-id="0a791-143">Управление пакетами политик</span><span class="sxs-lookup"><span data-stu-id="0a791-143">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="0a791-144">Просмотр</span><span class="sxs-lookup"><span data-stu-id="0a791-144">View</span></span>

<span data-ttu-id="0a791-145">Перед тем как назначать пакет, просмотрите параметры каждой политики в пакете политик.</span><span class="sxs-lookup"><span data-stu-id="0a791-145">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="0a791-146">В левой области навигации Центра администрирования Microsoft Teams нажмите **Пакеты политик**, выберите имя пакета, а затем — имя политики.</span><span class="sxs-lookup"><span data-stu-id="0a791-146">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="0a791-147">Решите, соответствуют ли готовые значения вашей организации или нужно настроить их, чтобы они были более или менее строгими, исходя из потребностей организации.</span><span class="sxs-lookup"><span data-stu-id="0a791-147">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="0a791-148">Настройка</span><span class="sxs-lookup"><span data-stu-id="0a791-148">Customize</span></span>

<span data-ttu-id="0a791-149">При необходимости настройте параметры политики в пакете политик, чтобы они соответствовали потребностям вашей организации.</span><span class="sxs-lookup"><span data-stu-id="0a791-149">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="0a791-150">Изменения, внесенные в параметры политики, автоматически применяются к пользователям, которым назначен пакет.</span><span class="sxs-lookup"><span data-stu-id="0a791-150">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="0a791-151">Чтобы изменить параметры политики в пакете политик, в левой области навигации Центра администрирования Microsoft Teams нажмите **Пакеты политик**, выберите пакет политики, нажмите имя политики, которую нужно изменить, а затем щелкните **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="0a791-151">To edit the settings of a policy in a policy package, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="0a791-152">Обратите внимание, что также можно изменить параметры политик в пакете после назначения пакета политики.</span><span class="sxs-lookup"><span data-stu-id="0a791-152">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="0a791-153">Дополнительные сведения см. в статье [Настройка политик в пакете политики](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="0a791-153">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span>

### <a name="assign"></a><span data-ttu-id="0a791-154">Назначение</span><span class="sxs-lookup"><span data-stu-id="0a791-154">Assign</span></span>

<span data-ttu-id="0a791-155">Назначение пакета политики пользователям.</span><span class="sxs-lookup"><span data-stu-id="0a791-155">Assign the policy package to users.</span></span> <span data-ttu-id="0a791-156">Если пользователю с назначенной политикой, назначается другая, приоритет будет иметь самое последнее назначение.</span><span class="sxs-lookup"><span data-stu-id="0a791-156">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="0a791-157">Назначение пакета политики для одного или нескольких пользователей</span><span class="sxs-lookup"><span data-stu-id="0a791-157">Assign a policy package to one or several users</span></span>

<span data-ttu-id="0a791-158">Чтобы назначить пакет политики одному или нескольким пользователям, в левой области навигации Центра администрирования Microsoft Teams перейдите в раздел **Пакеты политик**, а затем выберите **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="0a791-158">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select **Manage users**.</span></span>  

![Снимок экрана с назначением пакета политики в центре администрирования](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="0a791-160">Дополнительные сведения см. в статье [Назначение пакета политики](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="0a791-160">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="0a791-161">Если пользователю с назначенной политикой, назначается другая, приоритет будет иметь самое последнее назначение.</span><span class="sxs-lookup"><span data-stu-id="0a791-161">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="0a791-162">Назначение пакета политики группе</span><span class="sxs-lookup"><span data-stu-id="0a791-162">Assign a policy package to a group</span></span>

<span data-ttu-id="0a791-163">**Эта функция доступна в закрытой ознакомительной версии**</span><span class="sxs-lookup"><span data-stu-id="0a791-163">**This feature is in private preview**</span></span>

<span data-ttu-id="0a791-164">Назначение пакетов политики группам позволяет назначать несколько политик группе пользователей, например группе безопасности или группе рассылки.</span><span class="sxs-lookup"><span data-stu-id="0a791-164">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="0a791-165">Назначение политики распространяется на участников группы в соответствии с правилами очередности.</span><span class="sxs-lookup"><span data-stu-id="0a791-165">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="0a791-166">При добавлении или удалении участников группы, назначения политик для них обновляются соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="0a791-166">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="0a791-167">Этот способ рекомендуется для групп, включающих до 50 000 пользователей, но также подойдет и для больших групп.</span><span class="sxs-lookup"><span data-stu-id="0a791-167">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="0a791-168">Дополнительные сведения см. в статье [Назначение пакета политики группе](assign-policies.md#assign-a-policy-package-to-a-group).</span><span class="sxs-lookup"><span data-stu-id="0a791-168">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="0a791-169">Назначение пакета политики множеству (пакету) пользователей</span><span class="sxs-lookup"><span data-stu-id="0a791-169">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="0a791-170">Используйте назначение группового пакета политики, чтобы назначить пакет политики для множества пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="0a791-170">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="0a791-171">Используйте командлет [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation), чтобы отправить множество пользователей и пакет политики, который вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="0a791-171">You use the [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="0a791-172">Задания будут обрабатываться в фоновом режиме, а для каждого пакета будет создан идентификатор операции.</span><span class="sxs-lookup"><span data-stu-id="0a791-172">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="0a791-173">Пакет может содержать до 5 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="0a791-173">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="0a791-174">Можно указать пользователей по идентификатору объекта, UPN, адресу протокола SIP или электронной почты.</span><span class="sxs-lookup"><span data-stu-id="0a791-174">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="0a791-175">Дополнительные сведения см. в статье [Назначение пакета политики множеству пользователей](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span><span class="sxs-lookup"><span data-stu-id="0a791-175">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="0a791-176">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="0a791-176">Related topics</span></span>

[<span data-ttu-id="0a791-177">Управление пакетами политик в Teams</span><span class="sxs-lookup"><span data-stu-id="0a791-177">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="0a791-178">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="0a791-178">Assign policies to your users in Teams</span></span>](assign-policies.md)