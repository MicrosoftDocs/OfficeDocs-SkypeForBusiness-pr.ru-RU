---
title: Управление пакетами политик в Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sekrantz, aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policypackages.overview
- seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
description: Сведения о том, как использовать пакеты политик и управлять ими в Microsoft Teams для упрощения, упрощения и обеспечения согласованности при управлении политиками для групп пользователей.
ms.openlocfilehash: b69ce06d01af624ff73386531d7ef2b77bef3b4e
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "43914052"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="ce61a-103">Управление пакетами политик в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ce61a-103">Manage policy packages in Microsoft Teams</span></span>

<span data-ttu-id="ce61a-104">Пакет политики в Microsoft Teams — это набор предопределенных политик и параметров политики, которые можно назначить пользователям, имеющим аналогичные роли в Организации.</span><span class="sxs-lookup"><span data-stu-id="ce61a-104">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="ce61a-105">Мы создали пакеты политик для упрощения, упрощения и обеспечения согласованности при управлении политиками для групп пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="ce61a-105">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="ce61a-106">Когда вы назначаете пакету политики пользователям, будут созданы политики в пакете, и вы можете настроить параметры политик в пакете в соответствии с потребностями Организации.</span><span class="sxs-lookup"><span data-stu-id="ce61a-106">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of the policies in the package to meet your organization's needs.</span></span>

<span data-ttu-id="ce61a-107">Пакеты политик недоступны для организаций-сообществ США (GCC).</span><span class="sxs-lookup"><span data-stu-id="ce61a-107">Policy packages aren't available for US Government Cloud Community (GCC) organizations.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="ce61a-108">Что такое пакет политики?</span><span class="sxs-lookup"><span data-stu-id="ce61a-108">What is a policy package?</span></span>

<span data-ttu-id="ce61a-109">Пакеты политик позволяют управлять функциональными возможностями, которые вы хотите разрешить или ограничить для определенных наборов пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="ce61a-109">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="ce61a-110">Каждый пакет политики в Teams разработан вокруг роли пользователя и включает стандартные политики и параметры политики, которые поддерживают типичные задачи совместной работы и взаимодействия, которые обычно используются для этой роли.</span><span class="sxs-lookup"><span data-stu-id="ce61a-110">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="ce61a-111">В настоящее время команды включают следующие пакеты политик.</span><span class="sxs-lookup"><span data-stu-id="ce61a-111">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="ce61a-112">**Имя пакета**</span><span class="sxs-lookup"><span data-stu-id="ce61a-112">**Package name**</span></span>  |<span data-ttu-id="ce61a-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="ce61a-113">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="ce61a-114">Образование (более высокий образовательный учащийся)</span><span class="sxs-lookup"><span data-stu-id="ce61a-114">Education (Higher education student)</span></span>    |<span data-ttu-id="ce61a-115">Создает набор политик и параметров политики, которые применяются для более производительных учебных учащихся.</span><span class="sxs-lookup"><span data-stu-id="ce61a-115">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="ce61a-116">Образовательные учреждения (учебный учащийся)</span><span class="sxs-lookup"><span data-stu-id="ce61a-116">Education (Primary school student)</span></span>   |<span data-ttu-id="ce61a-117">Создает набор политик и параметров политики, которые применяются к основным учащимся.</span><span class="sxs-lookup"><span data-stu-id="ce61a-117">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="ce61a-118">Образование (дополнительный учебный учащийся)</span><span class="sxs-lookup"><span data-stu-id="ce61a-118">Education (Secondary school student)</span></span>    |<span data-ttu-id="ce61a-119">Создает набор политик и параметров политики, которые применяются к дополнительным учащимся.</span><span class="sxs-lookup"><span data-stu-id="ce61a-119">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="ce61a-120">Образование (преподаватель)</span><span class="sxs-lookup"><span data-stu-id="ce61a-120">Education (Teacher)</span></span>    |<span data-ttu-id="ce61a-121">Создает набор политик и параметров политики, которые применяются для преподавателей.</span><span class="sxs-lookup"><span data-stu-id="ce61a-121">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="ce61a-122">Малый и средний бизнес-пользователь (деловой голосовой звонок)</span><span class="sxs-lookup"><span data-stu-id="ce61a-122">Small and medium business user (Business Voice)</span></span> |<span data-ttu-id="ce61a-123">Создание политики настройки приложения, включающей приложения для голосового интерфейса для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="ce61a-123">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="ce61a-124">Малый и средний бизнес-пользователь (без деловой голосовой связи)</span><span class="sxs-lookup"><span data-stu-id="ce61a-124">Small and medium business user (without Business Voice)</span></span> |<span data-ttu-id="ce61a-125">Этот пакет политики предназначен для создания набора политик и применения этих параметров к пользователям малых и средних предприятий без каких-либо функций голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="ce61a-125">This policy package is designed to create a set of policies and apply those settings to small and medium sized business users without any Business Voice features.</span></span>|
|<span data-ttu-id="ce61a-126">Открытый директор по безопасности</span><span class="sxs-lookup"><span data-stu-id="ce61a-126">Public safety officer</span></span>   |<span data-ttu-id="ce61a-127">Создает набор политик и параметров политики, которые применяются для руководителей общедоступной безопасности в Организации.</span><span class="sxs-lookup"><span data-stu-id="ce61a-127">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|
|<span data-ttu-id="ce61a-128">Здравоохранение (сотрудник Clinical)</span><span class="sxs-lookup"><span data-stu-id="ce61a-128">Healthcare (Clinical worker)</span></span>  |<span data-ttu-id="ce61a-129">Создает набор политик и параметров политики, которые предоставляют Clinical сотрудникам, таким как зарегистрированные Nurses, начисление Nurses, врача и социальных работников, полный доступ к разговору, звонку, управлению сменой и собраниям.</span><span class="sxs-lookup"><span data-stu-id="ce61a-129">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="ce61a-130">Здравоохранение (информационный сотрудник)</span><span class="sxs-lookup"><span data-stu-id="ce61a-130">Healthcare (Information worker)</span></span>  |<span data-ttu-id="ce61a-131">Создание набора политик и параметров политики, предназначаемых сотрудникам, таким как ИТ-персонал, informatics сотрудников, финансовых сотрудников и руководителей соответствия требованиям, полного доступа к разговору, звонку и собранию.</span><span class="sxs-lookup"><span data-stu-id="ce61a-131">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|


> [!NOTE]
> <span data-ttu-id="ce61a-132">В будущих выпусках Teams мы добавим дополнительные пакеты политик, поэтому ознакомьтесь с самыми актуальными сведениями.</span><span class="sxs-lookup"><span data-stu-id="ce61a-132">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="ce61a-133">Каждой отдельной политике назначается имя пакета политики, что позволяет легко определять политики, связанные с пакетом политики.</span><span class="sxs-lookup"><span data-stu-id="ce61a-133">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="ce61a-134">Например, если назначить пакету политики образования для преподавателей в учебном заведении, для каждой политики в пакете будет создана политика с именем Education_Teacher.</span><span class="sxs-lookup"><span data-stu-id="ce61a-134">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![Снимок экрана: пакет политики "образование" (для преподавателей)](media/policy-packages-education_teacher.png)

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="ce61a-136">Использование пакетов политик</span><span class="sxs-lookup"><span data-stu-id="ce61a-136">How to use policy packages</span></span>

<span data-ttu-id="ce61a-137">Ниже показано, как использовать пакеты политик в Организации.</span><span class="sxs-lookup"><span data-stu-id="ce61a-137">The following outlines how to use policy packages in your organization.</span></span>

![Общие сведения об использовании пакетов политик](media/manage-policy-packages-overview.png)

- <span data-ttu-id="ce61a-139">**[Просмотр](#view-the-settings-of-a-policy-in-a-policy-package)**: Просмотр параметров каждой политики в пакете политики перед тем, как назначить пакет.</span><span class="sxs-lookup"><span data-stu-id="ce61a-139">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="ce61a-140">Убедитесь, что вы понимаете каждый параметр, а затем решите, должны ли предопределенные значения подходящими для вашей организации или нужно изменить их, чтобы они были более строгими или Lenient в зависимости от потребностей Организации.</span><span class="sxs-lookup"><span data-stu-id="ce61a-140">Make sure that you understand each setting and then decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="ce61a-141">Если политика удалена, вы по-прежнему можете просматривать параметры, но вы не сможете изменить параметры.</span><span class="sxs-lookup"><span data-stu-id="ce61a-141">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="ce61a-142">Удаленная политика создается повторно с параметрами, предопределенными при назначении пакета политики.</span><span class="sxs-lookup"><span data-stu-id="ce61a-142">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="ce61a-143">**[Назначение](#assign-a-policy-package)**: назначение пакета политики пользователям.</span><span class="sxs-lookup"><span data-stu-id="ce61a-143">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span> <span data-ttu-id="ce61a-144">Помните о том, что политики в пакете политики не создаются, пока вы не назначьте пакет, после чего вы можете изменить параметры отдельных политик в пакете.</span><span class="sxs-lookup"><span data-stu-id="ce61a-144">Remember that policies in a policy package aren't created until you assign the package, after which you can change the settings of individual policies in the package.</span></span>  

- <span data-ttu-id="ce61a-145">**[Настройка](#customize-policies-in-a-policy-package)**: Настройка параметров политик в пакете политики в соответствии с потребностями Организации.</span><span class="sxs-lookup"><span data-stu-id="ce61a-145">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span> <span data-ttu-id="ce61a-146">Любые изменения, внесенные в параметры политики, автоматически применяются к пользователям, которым назначен пакет.</span><span class="sxs-lookup"><span data-stu-id="ce61a-146">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="ce61a-147">Ниже описаны действия, которые необходимо выполнить, чтобы просмотреть, назначить и настроить пакеты политики в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ce61a-147">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="ce61a-148">Просмотр параметров политики в пакете политики</span><span class="sxs-lookup"><span data-stu-id="ce61a-148">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="ce61a-149">В левой области навигации центра администрирования Microsoft Teams щелкните **пакеты политики**, а затем выберите пакет политики, щелкнув слева от его имени.</span><span class="sxs-lookup"><span data-stu-id="ce61a-149">In the left navigation of the Microsoft Teams admin center, click **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="ce61a-150">Выберите политику, которую вы хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="ce61a-150">Click the policy you want to view.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="ce61a-151">Назначение пакета политики</span><span class="sxs-lookup"><span data-stu-id="ce61a-151">Assign a policy package</span></span>

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="ce61a-152">Назначение пакета политики для одного пользователя</span><span class="sxs-lookup"><span data-stu-id="ce61a-152">Assign a policy package to one user</span></span>

1. <span data-ttu-id="ce61a-153">В Центре администрирования Microsoft Teams в области навигации слева перейдите в раздел **Пользователи**, затем щелкните пользователя.</span><span class="sxs-lookup"><span data-stu-id="ce61a-153">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="ce61a-154">На странице пользователя нажмите **политики**, а затем рядом с пунктом **Политика**выберите команду **изменить**.</span><span class="sxs-lookup"><span data-stu-id="ce61a-154">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="ce61a-155">В области **Назначение пакета политики** выберите пакет, который вы хотите назначить, и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ce61a-155">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="ce61a-156">Назначение пакета политики нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="ce61a-156">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="ce61a-157">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел **пакеты политики**, а затем выберите пакет политики, который вы хотите назначить, щелкнув слева от его имени.</span><span class="sxs-lookup"><span data-stu-id="ce61a-157">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="ce61a-158">Щелкните **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="ce61a-158">Click **Manage users**.</span></span>
3. <span data-ttu-id="ce61a-159">В области **Управление пользователями** выполните поиск по отображаемому имени или по имени пользователя, выберите имя и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="ce61a-159">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="ce61a-160">Повторите это действие для каждого пользователя, которого нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="ce61a-160">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="ce61a-161">Завершив добавление пользователей, нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ce61a-161">When you're finished adding users, click **Save**.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="ce61a-162">Настройка политик в пакете политики</span><span class="sxs-lookup"><span data-stu-id="ce61a-162">Customize policies in a policy package</span></span>

<span data-ttu-id="ce61a-163">Вы можете изменить параметры политики на странице **пакеты политики** или непосредственно на страницу политики в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ce61a-163">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="ce61a-164">В левой области навигации центра администрирования Microsoft Teams выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="ce61a-164">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="ce61a-165">Щелкните **пакеты политики**, а затем выберите пакет политики, щелкнув слева от его имени.</span><span class="sxs-lookup"><span data-stu-id="ce61a-165">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="ce61a-166">Выберите тип политики.</span><span class="sxs-lookup"><span data-stu-id="ce61a-166">Click the policy type.</span></span>  <span data-ttu-id="ce61a-167">Например, выберите **политики обмена сообщениями**.</span><span class="sxs-lookup"><span data-stu-id="ce61a-167">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="ce61a-168">Выберите политику, которую вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="ce61a-168">Click the policy you want to edit.</span></span> <span data-ttu-id="ce61a-169">Политики, связанные с пакетом политики, имеют то же имя, что и пакет политики.</span><span class="sxs-lookup"><span data-stu-id="ce61a-169">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="ce61a-170">Внесите нужные изменения и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ce61a-170">Make the changes that you want, and then click **Save**.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="ce61a-171">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="ce61a-171">Troubleshooting</span></span>

<span data-ttu-id="ce61a-172">**При назначении пакета политики появляется сообщение об ошибке**</span><span class="sxs-lookup"><span data-stu-id="ce61a-172">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="ce61a-173">Это может произойти, если одна или несколько политик в пакете не были успешно созданы или применены.</span><span class="sxs-lookup"><span data-stu-id="ce61a-173">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="ce61a-174">Переназначение пакета политики пользователям.</span><span class="sxs-lookup"><span data-stu-id="ce61a-174">Reassign the policy package to your users.</span></span> <span data-ttu-id="ce61a-175">Повторное выполнение операции обычно решает эту проблему.</span><span class="sxs-lookup"><span data-stu-id="ce61a-175">Retrying the operation typically fixes this issue.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ce61a-176">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="ce61a-176">Related topics</span></span>

[<span data-ttu-id="ce61a-177">Пакеты политик Microsoft Teams для администраторов образовательных учреждений</span><span class="sxs-lookup"><span data-stu-id="ce61a-177">Microsoft Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)
