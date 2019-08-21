---
title: Управление пакетами политик в Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sekrantz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
f1keywords: ms.teamsadmincenter.policypackages.overview
localization_priority: Normal
search.appverid: MET150
description: Сведения о том, как использовать пакеты политик и управлять ими в Microsoft Teams.
ms.openlocfilehash: f4d26caa54e3b3e7643d06f80a160feda561bcb3
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "36483269"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="37821-103">Управление пакетами политик в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="37821-103">Manage policy packages in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="37821-104">Пакет политики в Microsoft Teams — это набор предопределенных политик и параметров политики, которые можно назначить пользователям, имеющим аналогичные роли в Организации.</span><span class="sxs-lookup"><span data-stu-id="37821-104">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="37821-105">Мы создали пакеты политик для упрощения, упрощения и обеспечения согласованности при управлении политиками для групп пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="37821-105">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="37821-106">Когда вы назначаете пакету политики пользователям, будут созданы политики в пакете, и вы можете настроить параметры политик в пакете в соответствии с потребностями Организации.</span><span class="sxs-lookup"><span data-stu-id="37821-106">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of the policies in the package to meet your organization's needs.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="37821-107">Что такое пакет политики?</span><span class="sxs-lookup"><span data-stu-id="37821-107">What is a policy package?</span></span>

<span data-ttu-id="37821-108">Пакеты политик позволяют управлять функциональными возможностями, которые вы хотите разрешить или ограничить для определенных наборов пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="37821-108">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="37821-109">Каждый пакет политики в Teams разработан вокруг роли пользователя и включает стандартные политики и параметры политики, которые поддерживают типичные задачи совместной работы и взаимодействия, которые обычно используются для этой роли.</span><span class="sxs-lookup"><span data-stu-id="37821-109">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="37821-110">В настоящее время команды включают следующие пакеты политик.</span><span class="sxs-lookup"><span data-stu-id="37821-110">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="37821-111">**Имя пакета**</span><span class="sxs-lookup"><span data-stu-id="37821-111">**Package name**</span></span>  |<span data-ttu-id="37821-112">**Описание**</span><span class="sxs-lookup"><span data-stu-id="37821-112">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="37821-113">Пакет Education_Teacher</span><span class="sxs-lookup"><span data-stu-id="37821-113">Education_Teacher package</span></span>     |<span data-ttu-id="37821-114">Создает набор политик и параметров политики, которые применяются для преподавателей.</span><span class="sxs-lookup"><span data-stu-id="37821-114">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="37821-115">Пакет Education_PrimaryStudent</span><span class="sxs-lookup"><span data-stu-id="37821-115">Education_PrimaryStudent package</span></span>    |<span data-ttu-id="37821-116">Создает набор политик и параметров политики, которые применяются к основным учащимся.</span><span class="sxs-lookup"><span data-stu-id="37821-116">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="37821-117">Пакет Education_SecondaryStudent</span><span class="sxs-lookup"><span data-stu-id="37821-117">Education_SecondaryStudent package</span></span>    |<span data-ttu-id="37821-118">Создает набор политик и параметров политики, которые применяются к дополнительным учащимся.</span><span class="sxs-lookup"><span data-stu-id="37821-118">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="37821-119">Пакет Education_HigherEducationStudent</span><span class="sxs-lookup"><span data-stu-id="37821-119">Education_HigherEducationStudent package</span></span>    |<span data-ttu-id="37821-120">Создает набор политик и параметров политики, которые применяются для более производительных учебных учащихся.</span><span class="sxs-lookup"><span data-stu-id="37821-120">Creates a set of policies and policy settings that apply to higher education students.</span></span>|

> [!NOTE]
> <span data-ttu-id="37821-121">В будущих выпусках Teams мы добавим дополнительные пакеты политик, поэтому ознакомьтесь с самыми актуальными сведениями.</span><span class="sxs-lookup"><span data-stu-id="37821-121">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="37821-122">Каждой отдельной политике назначается имя пакета политики, что позволяет легко определять политики, связанные с пакетом политики.</span><span class="sxs-lookup"><span data-stu-id="37821-122">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="37821-123">Например, если вы назначаете пакету политики Education_Teacher для преподавателей в учебном заведении, для каждой политики в пакете создается политика с именем Education_Teacher.</span><span class="sxs-lookup"><span data-stu-id="37821-123">For example, when you assign the Education_Teacher policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![Снимок экрана с пакетом политики Education_Teacher](media/policy-packages-education_teacher.png)

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="37821-125">Использование пакетов политик</span><span class="sxs-lookup"><span data-stu-id="37821-125">How to use policy packages</span></span>

<span data-ttu-id="37821-126">Ниже показано, как использовать пакеты политик в Организации.</span><span class="sxs-lookup"><span data-stu-id="37821-126">The following outlines how to use policy packages in your organization.</span></span>

![Общие сведения об использовании пакетов политик](media/manage-policy-packages-overview.png)

- <span data-ttu-id="37821-128">**[Просмотр](#view-the-settings-of-a-policy-in-a-policy-package)**: Просмотр параметров каждой политики в пакете политики перед тем, как назначить пакет.</span><span class="sxs-lookup"><span data-stu-id="37821-128">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="37821-129">Убедитесь, что вы понимаете каждый параметр, а затем решите, должны ли предопределенные значения подходящими для вашей организации или нужно изменить их, чтобы они были более строгими или лениент в зависимости от потребностей Организации.</span><span class="sxs-lookup"><span data-stu-id="37821-129">Make sure that you understand each setting and then decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="37821-130">Если политика удалена, вы по-прежнему можете просматривать параметры, но вы не сможете изменить параметры.</span><span class="sxs-lookup"><span data-stu-id="37821-130">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="37821-131">Удаленная политика создается повторно с параметрами, предопределенными при назначении пакета политики.</span><span class="sxs-lookup"><span data-stu-id="37821-131">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="37821-132">**[Назначение](#assign-a-policy-package)**: назначение пакета политики пользователям.</span><span class="sxs-lookup"><span data-stu-id="37821-132">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span> <span data-ttu-id="37821-133">Помните о том, что политики в пакете политики не создаются, пока вы не назначьте пакет, после чего вы можете изменить параметры отдельных политик в пакете.</span><span class="sxs-lookup"><span data-stu-id="37821-133">Remember that policies in a policy package aren't created until you assign the package, after which you can change the settings of individual policies in the package.</span></span>  

- <span data-ttu-id="37821-134">**[Настройка](#customize-policies-in-a-policy-package)**: Настройка параметров политик в пакете политики в соответствии с потребностями Организации.</span><span class="sxs-lookup"><span data-stu-id="37821-134">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span> <span data-ttu-id="37821-135">Любые изменения, внесенные в параметры политики, автоматически применяются к пользователям, которым назначен пакет.</span><span class="sxs-lookup"><span data-stu-id="37821-135">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="37821-136">Ниже описаны действия, которые необходимо выполнить, чтобы просмотреть, назначить и настроить пакеты политики в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="37821-136">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="37821-137">Просмотр параметров политики в пакете политики</span><span class="sxs-lookup"><span data-stu-id="37821-137">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="37821-138">В левой области навигации центра администрирования Microsoft Teams щелкните **пакеты политики**, а затем выберите пакет политики, щелкнув слева от его имени.</span><span class="sxs-lookup"><span data-stu-id="37821-138">In the left navigation of the Microsoft Teams admin center, click **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="37821-139">Выберите политику, которую вы хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="37821-139">Click the policy you want to view.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="37821-140">Назначение пакета политики</span><span class="sxs-lookup"><span data-stu-id="37821-140">Assign a policy package</span></span>

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="37821-141">Назначение пакета политики для одного пользователя</span><span class="sxs-lookup"><span data-stu-id="37821-141">Assign a policy package to one user</span></span>

1. <span data-ttu-id="37821-142">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел **Пользователи**и выберите пользователя.</span><span class="sxs-lookup"><span data-stu-id="37821-142">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="37821-143">На странице пользователя нажмите **политики**, а затем рядом с пунктом **Политика**выберите команду **изменить**.</span><span class="sxs-lookup"><span data-stu-id="37821-143">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="37821-144">В области **Назначение пакета политики** выберите пакет, который вы хотите назначить, и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="37821-144">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="37821-145">Назначение пакета политики нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="37821-145">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="37821-146">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел **пакеты политики**, а затем выберите пакет политики, который вы хотите назначить, щелкнув слева от его имени.</span><span class="sxs-lookup"><span data-stu-id="37821-146">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="37821-147">Щелкните **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="37821-147">Click **Manage users**.</span></span>
3. <span data-ttu-id="37821-148">В области **Управление пользователями** найдите пользователя по отображаемому имени или по имени пользователя, выберите имя и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="37821-148">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="37821-149">Повторите этот шаг для каждого пользователя, которого вы хотите добавить.</span><span class="sxs-lookup"><span data-stu-id="37821-149">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="37821-150">Завершив добавление пользователей, нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="37821-150">When you're finished adding users, click **Save**.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="37821-151">Настройка политик в пакете политики</span><span class="sxs-lookup"><span data-stu-id="37821-151">Customize policies in a policy package</span></span>

<span data-ttu-id="37821-152">Вы можете изменить параметры политики на странице **пакеты политики** или непосредственно на страницу политики в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="37821-152">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="37821-153">В левой области навигации центра администрирования Microsoft Teams выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="37821-153">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="37821-154">Щелкните **пакеты политики**, а затем выберите пакет политики, щелкнув слева от его имени.</span><span class="sxs-lookup"><span data-stu-id="37821-154">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="37821-155">Выберите тип политики.</span><span class="sxs-lookup"><span data-stu-id="37821-155">Click the policy type.</span></span>  <span data-ttu-id="37821-156">Например, выберите **политики обмена сообщениями**.</span><span class="sxs-lookup"><span data-stu-id="37821-156">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="37821-157">Выберите политику, которую вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="37821-157">Click the policy you want to edit.</span></span> <span data-ttu-id="37821-158">Политики, связанные с пакетом политики, имеют то же имя, что и пакет политики.</span><span class="sxs-lookup"><span data-stu-id="37821-158">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="37821-159">Внесите нужные изменения и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="37821-159">Make the changes that you want, and then click **Save**.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="37821-160">Поиск и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="37821-160">Troubleshooting</span></span>

<span data-ttu-id="37821-161">**При назначении пакета политики появляется сообщение об ошибке**</span><span class="sxs-lookup"><span data-stu-id="37821-161">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="37821-162">Это может произойти, если одна или несколько политик в пакете не были успешно созданы или применены.</span><span class="sxs-lookup"><span data-stu-id="37821-162">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="37821-163">Переназначение пакета политики пользователям.</span><span class="sxs-lookup"><span data-stu-id="37821-163">Reassign the policy package to your users.</span></span> <span data-ttu-id="37821-164">Повторное выполнение операции обычно решает эту проблему.</span><span class="sxs-lookup"><span data-stu-id="37821-164">Retrying the operation typically fixes this issue.</span></span>
