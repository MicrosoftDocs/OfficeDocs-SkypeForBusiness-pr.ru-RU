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
description: Узнайте, как использовать пакеты политики Teams для организации здравоохранения и управлять ими.
ms.openlocfilehash: af6f5923d5c97fc03c77585ba94292264aacc027
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812859"
---
# <a name="teams-policy-packages-for-healthcare"></a><span data-ttu-id="c60df-103">Пакеты политик Teams для здравоохранения</span><span class="sxs-lookup"><span data-stu-id="c60df-103">Teams policy packages for healthcare</span></span>

## <a name="overview"></a><span data-ttu-id="c60df-104">Обзор</span><span class="sxs-lookup"><span data-stu-id="c60df-104">Overview</span></span>

<span data-ttu-id="c60df-105">Пакет [политики](manage-policy-packages.md) в Microsoft Teams — это набор предопределельных политик и параметров политики, которые можно назначать пользователям с похожими ролями в организации.</span><span class="sxs-lookup"><span data-stu-id="c60df-105">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="c60df-106">Пакеты политик упрощают, оптимизируют и помогают обеспечивать согласованность при управлении политиками.</span><span class="sxs-lookup"><span data-stu-id="c60df-106">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="c60df-107">Вы можете настроить параметры политик в пакете в соответствии с потребностями пользователей.</span><span class="sxs-lookup"><span data-stu-id="c60df-107">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="c60df-108">При изменении параметров политик в пакете политики все пользователи, которым он назначен, получают обновленные параметры.</span><span class="sxs-lookup"><span data-stu-id="c60df-108">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="c60df-109">Вы можете управлять пакетами политики с помощью Центра администрирования Microsoft Teams или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c60df-109">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Ht2o]

<span data-ttu-id="c60df-110">Пакеты политик предопределяют политики для следующих пакетов в зависимости от пакета:</span><span class="sxs-lookup"><span data-stu-id="c60df-110">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="c60df-111">Обмен сообщениями</span><span class="sxs-lookup"><span data-stu-id="c60df-111">Messaging</span></span>
- <span data-ttu-id="c60df-112">Собрания</span><span class="sxs-lookup"><span data-stu-id="c60df-112">Meetings</span></span>
- <span data-ttu-id="c60df-113">Звонки</span><span class="sxs-lookup"><span data-stu-id="c60df-113">Calling</span></span>
- <span data-ttu-id="c60df-114">Настройка приложения</span><span class="sxs-lookup"><span data-stu-id="c60df-114">App setup</span></span>
- <span data-ttu-id="c60df-115">Трансляции</span><span class="sxs-lookup"><span data-stu-id="c60df-115">Live events</span></span>

<span data-ttu-id="c60df-116">В настоящее время Teams включает следующие пакеты политики здравоохранения:</span><span class="sxs-lookup"><span data-stu-id="c60df-116">Teams currently includes the following healthcare policy packages.</span></span>

|<span data-ttu-id="c60df-117">Имя пакета в Центре администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c60df-117">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="c60df-118">Кому предназначено</span><span class="sxs-lookup"><span data-stu-id="c60df-118">Best used for</span></span>|<span data-ttu-id="c60df-119">Описание</span><span class="sxs-lookup"><span data-stu-id="c60df-119">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="c60df-120">медицинского медицинского учреждения, медицинского медицинского учреждения</span><span class="sxs-lookup"><span data-stu-id="c60df-120">Healthcare clinical worker</span></span>  |<span data-ttu-id="c60df-121">Медицинские работники</span><span class="sxs-lookup"><span data-stu-id="c60df-121">Clinical workers in your healthcare organization</span></span>  |<span data-ttu-id="c60df-122">Создает набор политик и параметров политики, которые дают сотрудникам, работающим по клиническим исследованиям, таким как зарегистрированные медсестры, медсестры, медицинские работники и социальные работники, имеют полный доступ к чату, звонкам, управлению сменами и собраниям.</span><span class="sxs-lookup"><span data-stu-id="c60df-122">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="c60df-123">Информационный работник в сфере здравоохранения</span><span class="sxs-lookup"><span data-stu-id="c60df-123">Healthcare information worker</span></span>  |<span data-ttu-id="c60df-124">Информационные работники в вашей организации здравоохранения</span><span class="sxs-lookup"><span data-stu-id="c60df-124">Information workers in your healthcare organization</span></span> |<span data-ttu-id="c60df-125">Создает набор политик и параметров политики, которые дают информационным работникам, таким как ИТ-персонал, информирует сотрудников, финансового персонала и сотрудников, которые работают за соблюдение требований, полный доступ к чату, звонкам и собраниям.</span><span class="sxs-lookup"><span data-stu-id="c60df-125">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="c60df-126">Медицинские кабинеты пациентов</span><span class="sxs-lookup"><span data-stu-id="c60df-126">Healthcare patient room</span></span>  |<span data-ttu-id="c60df-127">Устройства пациентов</span><span class="sxs-lookup"><span data-stu-id="c60df-127">Patient room devices</span></span>|<span data-ttu-id="c60df-128">Создает набор политик и параметров политики, которые применяются к комнатам пациентов в вашей организации здравоохранения.</span><span class="sxs-lookup"><span data-stu-id="c60df-128">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|

![Снимок экрана: пакеты политик здравоохранения](media/policy-packages-healthcare.png)

<span data-ttu-id="c60df-130">Каждой отдельной политике дается имя пакета политики, чтобы можно было легко определить политики, связанные с пакетом политики.</span><span class="sxs-lookup"><span data-stu-id="c60df-130">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="c60df-131">Например, при назначении пакета политики медицинских учреждений клиникам в организации для каждой политики создается Healthcare_ClinicalWorker, которая будет создаваться для каждой политики в этом пакете.</span><span class="sxs-lookup"><span data-stu-id="c60df-131">For example, when you assign the Healthcare clinical worker policy package to clinicians in your organization, a policy named Healthcare_ClinicalWorker is created for each policy in the package.</span></span>

![Снимок экрана: политики в пакете "Клинические работники здравоохранения"](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a><span data-ttu-id="c60df-133">Начало работы с пакетами политики</span><span class="sxs-lookup"><span data-stu-id="c60df-133">Get started with policy packages</span></span>

<span data-ttu-id="c60df-134">Чтобы начать работу с пакетами политики здравоохранения, в центре платы Центра администрирования Майкрософт выберите "Здравоохранение", а затем выберите "Назначение параметров политики **по роли".**</span><span class="sxs-lookup"><span data-stu-id="c60df-134">To get you started with Healthcare policy packages, on the Microsoft Admin Center onboarding hub, select **Healthcare**, and then select **Assign policy settings by role**.</span></span> <span data-ttu-id="c60df-135">Когда вы будете готовы к началу работы, решите, какие пакеты политики вы хотите назначить отдельным лицам в организации.</span><span class="sxs-lookup"><span data-stu-id="c60df-135">Once you’re ready to get started, decide which policy packages you'd like to assign individuals in your organization to.</span></span>

<span data-ttu-id="c60df-136">Выберите **"Просмотреть сведения о** политике", чтобы получить дополнительные сведения о конкретных политиках в пакете и соответствующих параметрах.</span><span class="sxs-lookup"><span data-stu-id="c60df-136">Select **View policy details** to learn more about the specific policies in a package and their respective settings.</span></span> <span data-ttu-id="c60df-137">Их [можно настроить после](manage-policy-packages.md#customize-policies-in-a-policy-package) назначения в Центре администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="c60df-137">These [can be customized](manage-policy-packages.md#customize-policies-in-a-policy-package) after assignment in the Teams Admin Center.</span></span>

<span data-ttu-id="c60df-138">Выберите один или несколько пакетов для назначения и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="c60df-138">Choose one or multiple packages to assign and then click **Next**.</span></span> <span data-ttu-id="c60df-139">Вы можете искать и добавлять людей в пакет политики, лучше всего подходящий для их роли.</span><span class="sxs-lookup"><span data-stu-id="c60df-139">You can search for and add people to the policy package best suited for their role.</span></span> <span data-ttu-id="c60df-140">Отдельного человека нельзя на назначении сразу несколько пакетов политики.</span><span class="sxs-lookup"><span data-stu-id="c60df-140">An individual can't be assigned to more than one policy package at one time.</span></span>

<span data-ttu-id="c60df-141">После того как вы добавите людей в нужный пакет политики, **finish** завершит выбор.</span><span class="sxs-lookup"><span data-stu-id="c60df-141">Once you’ve added people to the right policy package, **Finish** finalizes your selections.</span></span> <span data-ttu-id="c60df-142">Вы можете продолжать настраивать пакеты политики и управлять ими в Центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c60df-142">You can continue to customize and manage policy packages in the Microsoft Teams admin center.</span></span>

## <a name="manage-policy-packages"></a><span data-ttu-id="c60df-143">Управление пакетами политик</span><span class="sxs-lookup"><span data-stu-id="c60df-143">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="c60df-144">Просмотр</span><span class="sxs-lookup"><span data-stu-id="c60df-144">View</span></span>

<span data-ttu-id="c60df-145">Перед тем как назначать пакет, просмотрите параметры каждой политики в пакете политик.</span><span class="sxs-lookup"><span data-stu-id="c60df-145">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="c60df-146">В левой области навигации Центра администрирования Microsoft Teams перейдите к пакетам **политики,** выберите имя пакета, а затем выберите имя политики.</span><span class="sxs-lookup"><span data-stu-id="c60df-146">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="c60df-147">Решите, соответствуют ли готовые значения вашей организации или нужно настроить их, чтобы они были более или менее строгими, исходя из потребностей организации.</span><span class="sxs-lookup"><span data-stu-id="c60df-147">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="c60df-148">Настройка</span><span class="sxs-lookup"><span data-stu-id="c60df-148">Customize</span></span>

<span data-ttu-id="c60df-149">При необходимости настройте параметры политики в пакете политик, чтобы они соответствовали потребностям вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c60df-149">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="c60df-150">Изменения, внесенные в параметры политики, автоматически применяются к пользователям, которым назначен пакет.</span><span class="sxs-lookup"><span data-stu-id="c60df-150">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="c60df-151">Чтобы изменить параметры политики в пакете политики, в левой области навигации Центра администрирования Microsoft Teams перейдите к пакетам **политики,** выберите пакет политики, выберите имя политики, а затем выберите команду "Изменить". </span><span class="sxs-lookup"><span data-stu-id="c60df-151">To edit the settings of a policy in a policy package, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="c60df-152">Обратите внимание, что также можно изменить параметры политик в пакете после назначения пакета политики.</span><span class="sxs-lookup"><span data-stu-id="c60df-152">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="c60df-153">Дополнительные сведения см. в статье [Настройка политик в пакете политики](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="c60df-153">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span>

### <a name="assign"></a><span data-ttu-id="c60df-154">Назначение</span><span class="sxs-lookup"><span data-stu-id="c60df-154">Assign</span></span>

<span data-ttu-id="c60df-155">Назначение пакета политики пользователям.</span><span class="sxs-lookup"><span data-stu-id="c60df-155">Assign the policy package to users.</span></span> <span data-ttu-id="c60df-156">Если пользователю с назначенной политикой, назначается другая, приоритет будет иметь самое последнее назначение.</span><span class="sxs-lookup"><span data-stu-id="c60df-156">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="c60df-157">Назначение пакета политики для одного или нескольких пользователей</span><span class="sxs-lookup"><span data-stu-id="c60df-157">Assign a policy package to one or several users</span></span>

<span data-ttu-id="c60df-158">Чтобы назначить пакет политики одному или нескольким пользователям, в левой области навигации Центра администрирования Microsoft Teams перейдите в раздел **Пакеты политик**, а затем выберите **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="c60df-158">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select **Manage users**.</span></span>  

![Снимок экрана с назначением пакета политики в центре администрирования](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="c60df-160">Дополнительные сведения см. в статье [Назначение пакета политики](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="c60df-160">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="c60df-161">Если пользователю с назначенной политикой, назначается другая, приоритет будет иметь самое последнее назначение.</span><span class="sxs-lookup"><span data-stu-id="c60df-161">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="c60df-162">Назначение пакета политики группе</span><span class="sxs-lookup"><span data-stu-id="c60df-162">Assign a policy package to a group</span></span>

<span data-ttu-id="c60df-163">**Эта функция доступна в закрытой ознакомительной версии**</span><span class="sxs-lookup"><span data-stu-id="c60df-163">**This feature is in private preview**</span></span>

<span data-ttu-id="c60df-164">Назначение пакетов политики группам позволяет назначать несколько политик группе пользователей, например группе безопасности или группе рассылки.</span><span class="sxs-lookup"><span data-stu-id="c60df-164">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="c60df-165">Назначение политики распространяется на участников группы в соответствии с правилами очередности.</span><span class="sxs-lookup"><span data-stu-id="c60df-165">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="c60df-166">При добавлении или удалении участников группы, назначения политик для них обновляются соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="c60df-166">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="c60df-167">Этот способ рекомендуется для групп, включающих до 50 000 пользователей, но также подойдет и для больших групп.</span><span class="sxs-lookup"><span data-stu-id="c60df-167">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="c60df-168">Дополнительные сведения см. в статье [Назначение пакета политики группе](assign-policies.md#assign-a-policy-package-to-a-group).</span><span class="sxs-lookup"><span data-stu-id="c60df-168">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="c60df-169">Назначение пакета политики множеству (пакету) пользователей</span><span class="sxs-lookup"><span data-stu-id="c60df-169">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="c60df-170">Используйте назначение группового пакета политики, чтобы назначить пакет политики для множества пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="c60df-170">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="c60df-171">Используйте командлет [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation), чтобы отправить множество пользователей и пакет политики, который вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="c60df-171">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="c60df-172">Задания будут обрабатываться в фоновом режиме, а для каждого пакета будет создан идентификатор операции.</span><span class="sxs-lookup"><span data-stu-id="c60df-172">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="c60df-173">Пакет может содержать до 5 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="c60df-173">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="c60df-174">Можно указать пользователей по идентификатору объекта, UPN, адресу протокола SIP или электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c60df-174">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="c60df-175">Дополнительные сведения см. в статье [Назначение пакета политики множеству пользователей](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span><span class="sxs-lookup"><span data-stu-id="c60df-175">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c60df-176">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="c60df-176">Related topics</span></span>

[<span data-ttu-id="c60df-177">Управление пакетами политик в Teams</span><span class="sxs-lookup"><span data-stu-id="c60df-177">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="c60df-178">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="c60df-178">Assign policies to your users in Teams</span></span>](assign-policies.md)
