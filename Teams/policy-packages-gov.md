---
title: Пакеты политики Teams для государственных организаций
author: lanachin
ms.author: v-lanac
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
description: Сведения о том, как использовать и управлять пакетами политики Teams для вашей организации для государственных организаций.
ms.openlocfilehash: 8ef632689cb52180e8fd18cf4047fb9a25150885
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908598"
---
# <a name="teams-policy-packages-for-government"></a><span data-ttu-id="74939-103">Пакеты политики Teams для государственных организаций</span><span class="sxs-lookup"><span data-stu-id="74939-103">Teams policy packages for government</span></span>

> [!NOTE]
> <span data-ttu-id="74939-104">В настоящее время пакеты политик не поддерживаются в сетях Microsoft 365 для государственных организаций по высококачественной или невысокой развернутости.</span><span class="sxs-lookup"><span data-stu-id="74939-104">Policy packages are currently not available in Microsoft 365 Government GCC High or DoD deployments.</span></span>

## <a name="overview"></a><span data-ttu-id="74939-105">Обзор</span><span class="sxs-lookup"><span data-stu-id="74939-105">Overview</span></span>

<span data-ttu-id="74939-106">[Пакет политики](manage-policy-packages.md) в Microsoft Teams — это набор предопределенных политик и параметров политики, которые можно назначить пользователям, имеющим аналогичные роли в Организации.</span><span class="sxs-lookup"><span data-stu-id="74939-106">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="74939-107">Пакеты политик упрощают, оптимизируют и помогают обеспечивать согласованность при управлении политиками.</span><span class="sxs-lookup"><span data-stu-id="74939-107">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="74939-108">Вы можете настроить параметры политик в пакете в соответствии с потребностями пользователей.</span><span class="sxs-lookup"><span data-stu-id="74939-108">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="74939-109">При изменении параметров политик в пакете политики все пользователи, которым назначен этот пакет, получают обновленные параметры.</span><span class="sxs-lookup"><span data-stu-id="74939-109">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="74939-110">Управление пакетами политики осуществляется с помощью центра администрирования Microsoft Teams или оболочки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74939-110">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="74939-111">Пакеты политик предварительно определяют следующие политики в зависимости от пакета:</span><span class="sxs-lookup"><span data-stu-id="74939-111">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="74939-112">Обмен сообщениями</span><span class="sxs-lookup"><span data-stu-id="74939-112">Messaging</span></span>
- <span data-ttu-id="74939-113">Собрания</span><span class="sxs-lookup"><span data-stu-id="74939-113">Meetings</span></span>
- <span data-ttu-id="74939-114">Звонки</span><span class="sxs-lookup"><span data-stu-id="74939-114">Calling</span></span>
- <span data-ttu-id="74939-115">Настройка приложения</span><span class="sxs-lookup"><span data-stu-id="74939-115">App setup</span></span>
- <span data-ttu-id="74939-116">Трансляции</span><span class="sxs-lookup"><span data-stu-id="74939-116">Live events</span></span>

<span data-ttu-id="74939-117">В настоящее время команды включают следующие пакеты политик для государственных организаций.</span><span class="sxs-lookup"><span data-stu-id="74939-117">Teams currently includes the following policy packages for government.</span></span>

|<span data-ttu-id="74939-118">Имя пакета в центре администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="74939-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="74939-119">Кому предназначено</span><span class="sxs-lookup"><span data-stu-id="74939-119">Best used for</span></span>|<span data-ttu-id="74939-120">Описание</span><span class="sxs-lookup"><span data-stu-id="74939-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="74939-121">Открытый директор по безопасности</span><span class="sxs-lookup"><span data-stu-id="74939-121">Public safety officer</span></span>  |<span data-ttu-id="74939-122">Общедоступные руководителей по безопасности в вашей организации государственных учреждений</span><span class="sxs-lookup"><span data-stu-id="74939-122">Public safety officers in your government organization</span></span>  |<span data-ttu-id="74939-123">Создает набор политик и параметров политики, которые применяются для руководителей общедоступной безопасности в Организации.</span><span class="sxs-lookup"><span data-stu-id="74939-123">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span> |
|<span data-ttu-id="74939-124">Менеджер Firstline</span><span class="sxs-lookup"><span data-stu-id="74939-124">Firstline manager</span></span>  |<span data-ttu-id="74939-125">Руководители Firstline в вашей организации правительственных учреждений</span><span class="sxs-lookup"><span data-stu-id="74939-125">Firstline Managers in your government organization</span></span> |<span data-ttu-id="74939-126">Создает набор политик и применяет эти параметры для руководителей Firstline в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="74939-126">Creates a set of policies and applies those settings to Firstline Managers in your organization.</span></span>|
|<span data-ttu-id="74939-127">Firstline рабочий процесс</span><span class="sxs-lookup"><span data-stu-id="74939-127">Firstline worker</span></span>  |<span data-ttu-id="74939-128">Firstline работников в вашей организации государственной власти</span><span class="sxs-lookup"><span data-stu-id="74939-128">Firstline Workers in your government organization</span></span> |<span data-ttu-id="74939-129">Создает набор политик и применяет эти параметры для Firstlineных сотрудников в Организации.</span><span class="sxs-lookup"><span data-stu-id="74939-129">Creates a set of policies and applies those settings to Firstline Workers in your organization.</span></span>|

![Снимок экрана: пакеты политики здравоохранения](media/policy-packages-gov.png)

<span data-ttu-id="74939-131">Каждой отдельной политике назначается имя пакета политики, что позволяет легко определять политики, связанные с пакетом политики.</span><span class="sxs-lookup"><span data-stu-id="74939-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="74939-132">Например, при назначении общего пакета политики поддиректора безопасности для пользователей в Организации, для каждой политики в пакете создается политика с именем PublicSafety_Officer.</span><span class="sxs-lookup"><span data-stu-id="74939-132">For example, when you assign the Public safety officer policy package to users in your organization, a policy named PublicSafety_Officer is created for each policy in the package.</span></span>

![Снимок экрана: политики в Clinical рабочего пакета здравоохранения](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="74939-134">Управление пакетами политик</span><span class="sxs-lookup"><span data-stu-id="74939-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="74939-135">Просмотр</span><span class="sxs-lookup"><span data-stu-id="74939-135">View</span></span>

<span data-ttu-id="74939-136">Перед назначением пакета просмотрите параметры каждой политики в пакете политики.</span><span class="sxs-lookup"><span data-stu-id="74939-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="74939-137">В левой области навигации центра администрирования Microsoft Teams выберите **пакеты политики** , выберите имя пакета, а затем выберите имя политики.</span><span class="sxs-lookup"><span data-stu-id="74939-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages** , select the package name, and then select the policy name.</span></span>

<span data-ttu-id="74939-138">Определите, являются ли предопределенные значения подходящими для вашей организации, или настройте их так, чтобы они были более строгими или Lenient в зависимости от потребностей Организации.</span><span class="sxs-lookup"><span data-stu-id="74939-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="74939-139">Настроить</span><span class="sxs-lookup"><span data-stu-id="74939-139">Customize</span></span>

<span data-ttu-id="74939-140">Настройте параметры политик в пакете политики в соответствии с потребностями Организации.</span><span class="sxs-lookup"><span data-stu-id="74939-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="74939-141">Любые изменения, внесенные в параметры политики, автоматически применяются к пользователям, которым назначен пакет.</span><span class="sxs-lookup"><span data-stu-id="74939-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="74939-142">Чтобы изменить параметры политики в пакете политики, в центре администрирования Microsoft Teams выберите пакет политики, выберите имя политики, которую вы хотите изменить, и нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="74939-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="74939-143">Имейте в виду, что вы также можете изменить параметры политик в пакете после назначения пакета политики.</span><span class="sxs-lookup"><span data-stu-id="74939-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="74939-144">Дополнительные сведения можно найти [в разделе Настройка политик в пакете политики](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="74939-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="74939-145">Присваивают</span><span class="sxs-lookup"><span data-stu-id="74939-145">Assign</span></span>

<span data-ttu-id="74939-146">Назначение пакета политики пользователям.</span><span class="sxs-lookup"><span data-stu-id="74939-146">Assign the policy package to users.</span></span> <span data-ttu-id="74939-147">Если пользователю назначена политика, а затем в дальнейшем вы назначаете другую политику, она имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="74939-147">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="74939-148">Назначение пакета политики для одного или нескольких пользователей</span><span class="sxs-lookup"><span data-stu-id="74939-148">Assign a policy package to one or several users</span></span>

<span data-ttu-id="74939-149">Чтобы назначить пакет политики для одного или нескольких пользователей, в левой области навигации центра администрирования Microsoft Teams перейдите в раздел **пакеты политики** и выберите пункт **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="74939-149">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages** , and then select **Manage users**.</span></span>  

![Снимок экрана: назначение пакета политики в центре администрирования](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="74939-151">Дополнительные сведения можно найти в разделе [Назначение пакета политики](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="74939-151">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="74939-152">Если пользователю назначена политика, а затем в дальнейшем вы назначаете другую политику, она имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="74939-152">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="74939-153">Назначение группы пакета политики</span><span class="sxs-lookup"><span data-stu-id="74939-153">Assign a policy package to a group</span></span>

<span data-ttu-id="74939-154">**Эта функция доступна в частном предварительной версии**</span><span class="sxs-lookup"><span data-stu-id="74939-154">**This feature is in private preview**</span></span>

<span data-ttu-id="74939-155">Назначение групп (в том числе группе безопасности или списку рассылки) позволяет назначать несколько политик группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="74939-155">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="74939-156">Назначение политики распространяется на пользователей группы в соответствии с правилами приоритета.</span><span class="sxs-lookup"><span data-stu-id="74939-156">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="74939-157">Когда участники добавляются в группу или удаляются из нее, их унаследованные назначения политик обновляются соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="74939-157">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="74939-158">Этот способ рекомендуется для групп до 50 000 пользователей, но также для работы с более крупными группами.</span><span class="sxs-lookup"><span data-stu-id="74939-158">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="74939-159">Дополнительные сведения можно найти в статье [Назначение пакета политики группе](assign-policies.md#assign-a-policy-package-to-a-group).</span><span class="sxs-lookup"><span data-stu-id="74939-159">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="74939-160">Назначение пакета политики большому набору (пакету) пользователей</span><span class="sxs-lookup"><span data-stu-id="74939-160">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="74939-161">Назначение пакета политики для большого количества пользователей одновременно с помощью задания пакетной политики.</span><span class="sxs-lookup"><span data-stu-id="74939-161">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="74939-162">С помощью командлета [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) вы можете отправить пакет пользователей и пакет политики, который вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="74939-162">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="74939-163">Назначения обрабатываются как фоновая операция, и для каждого пакета создается идентификатор операции.</span><span class="sxs-lookup"><span data-stu-id="74939-163">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="74939-164">Пакет может содержать до 5 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="74939-164">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="74939-165">Вы можете указать пользователей, указав их идентификатор (UPN), адрес SIP или адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="74939-165">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="74939-166">Дополнительные сведения можно найти в разделе [Назначение пакета политики пакету пользователей](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span><span class="sxs-lookup"><span data-stu-id="74939-166">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="74939-167">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="74939-167">Related topics</span></span>

[<span data-ttu-id="74939-168">Управление пакетами политик в Teams</span><span class="sxs-lookup"><span data-stu-id="74939-168">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="74939-169">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="74939-169">Assign policies to your users in Teams</span></span>](assign-policies.md) 
