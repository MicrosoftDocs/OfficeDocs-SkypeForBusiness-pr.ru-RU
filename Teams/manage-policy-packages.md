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
f1keywords: ms.teamsadmincenter.policypackages.overview
localization_priority: Normal
search.appverid: MET150
description: Сведения о том, как использовать пакеты политик и управлять ими в Microsoft Teams.
ms.openlocfilehash: 87fda86d1dbe09858c3850dc92ee5085666d8ba7
ms.sourcegitcommit: 52d924e654909a2017ce42ba9d1b4bbc3efa9262
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2020
ms.locfileid: "41205296"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="c2cb1-103">Управление пакетами политик в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c2cb1-103">Manage policy packages in Microsoft Teams</span></span>

<span data-ttu-id="c2cb1-104">Пакет политики в Microsoft Teams — это набор предопределенных политик и параметров политики, которые можно назначить пользователям, имеющим аналогичные роли в Организации.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-104">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="c2cb1-105">Мы создали пакеты политик для упрощения, упрощения и обеспечения согласованности при управлении политиками для групп пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-105">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="c2cb1-106">Когда вы назначаете пакету политики пользователям, будут созданы политики в пакете, и вы можете настроить параметры политик в пакете в соответствии с потребностями Организации.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-106">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of the policies in the package to meet your organization's needs.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="c2cb1-107">Что такое пакет политики?</span><span class="sxs-lookup"><span data-stu-id="c2cb1-107">What is a policy package?</span></span>

<span data-ttu-id="c2cb1-108">Пакеты политик позволяют управлять функциональными возможностями, которые вы хотите разрешить или ограничить для определенных наборов пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-108">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="c2cb1-109">Каждый пакет политики в Teams разработан вокруг роли пользователя и включает стандартные политики и параметры политики, которые поддерживают типичные задачи совместной работы и взаимодействия, которые обычно используются для этой роли.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-109">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="c2cb1-110">В настоящее время команды включают следующие пакеты политик.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-110">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="c2cb1-111">**Имя пакета**</span><span class="sxs-lookup"><span data-stu-id="c2cb1-111">**Package name**</span></span>  |<span data-ttu-id="c2cb1-112">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c2cb1-112">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="c2cb1-113">Образование (более высокий образовательный учащийся)</span><span class="sxs-lookup"><span data-stu-id="c2cb1-113">Education (Higher education student)</span></span>    |<span data-ttu-id="c2cb1-114">Создает набор политик и параметров политики, которые применяются для более производительных учебных учащихся.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-114">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="c2cb1-115">Образовательные учреждения (учебный учащийся)</span><span class="sxs-lookup"><span data-stu-id="c2cb1-115">Education (Primary school student)</span></span>   |<span data-ttu-id="c2cb1-116">Создает набор политик и параметров политики, которые применяются к основным учащимся.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-116">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="c2cb1-117">Образование (дополнительный учебный учащийся)</span><span class="sxs-lookup"><span data-stu-id="c2cb1-117">Education (Secondary school student)</span></span>    |<span data-ttu-id="c2cb1-118">Создает набор политик и параметров политики, которые применяются к дополнительным учащимся.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-118">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="c2cb1-119">Образование (преподаватель)</span><span class="sxs-lookup"><span data-stu-id="c2cb1-119">Education (Teacher)</span></span>    |<span data-ttu-id="c2cb1-120">Создает набор политик и параметров политики, которые применяются для преподавателей.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-120">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="c2cb1-121">Деловые голоса</span><span class="sxs-lookup"><span data-stu-id="c2cb1-121">Business voice</span></span> |<span data-ttu-id="c2cb1-122">Создание политики настройки приложения, включающей приложения для голосового интерфейса для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-122">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="c2cb1-123">Открытый директор по безопасности</span><span class="sxs-lookup"><span data-stu-id="c2cb1-123">Public safety officer</span></span>   |<span data-ttu-id="c2cb1-124">Создает набор политик и параметров политики, которые применяются для руководителей общедоступной безопасности в Организации.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-124">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|

> [!NOTE]
> <span data-ttu-id="c2cb1-125">В будущих выпусках Teams мы добавим дополнительные пакеты политик, поэтому ознакомьтесь с самыми актуальными сведениями.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-125">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="c2cb1-126">Каждой отдельной политике назначается имя пакета политики, что позволяет легко определять политики, связанные с пакетом политики.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-126">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="c2cb1-127">Например, если назначить пакету политики образования для преподавателей в учебном заведении, для каждой политики в пакете будет создана политика с именем Education_Teacher.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-127">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![Снимок экрана: пакет политики "образование" (для преподавателей)](media/policy-packages-education_teacher.png)

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="c2cb1-129">Использование пакетов политик</span><span class="sxs-lookup"><span data-stu-id="c2cb1-129">How to use policy packages</span></span>

<span data-ttu-id="c2cb1-130">Ниже показано, как использовать пакеты политик в Организации.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-130">The following outlines how to use policy packages in your organization.</span></span>

![Общие сведения об использовании пакетов политик](media/manage-policy-packages-overview.png)

- <span data-ttu-id="c2cb1-132">**[Просмотр](#view-the-settings-of-a-policy-in-a-policy-package)**: Просмотр параметров каждой политики в пакете политики перед тем, как назначить пакет.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-132">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="c2cb1-133">Убедитесь, что вы понимаете каждый параметр, а затем решите, должны ли предопределенные значения подходящими для вашей организации или нужно изменить их, чтобы они были более строгими или лениент в зависимости от потребностей Организации.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-133">Make sure that you understand each setting and then decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="c2cb1-134">Если политика удалена, вы по-прежнему можете просматривать параметры, но вы не сможете изменить параметры.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-134">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="c2cb1-135">Удаленная политика создается повторно с параметрами, предопределенными при назначении пакета политики.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-135">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="c2cb1-136">**[Назначение](#assign-a-policy-package)**: назначение пакета политики пользователям.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-136">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span> <span data-ttu-id="c2cb1-137">Помните о том, что политики в пакете политики не создаются, пока вы не назначьте пакет, после чего вы можете изменить параметры отдельных политик в пакете.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-137">Remember that policies in a policy package aren't created until you assign the package, after which you can change the settings of individual policies in the package.</span></span>  

- <span data-ttu-id="c2cb1-138">**[Настройка](#customize-policies-in-a-policy-package)**: Настройка параметров политик в пакете политики в соответствии с потребностями Организации.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-138">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span> <span data-ttu-id="c2cb1-139">Любые изменения, внесенные в параметры политики, автоматически применяются к пользователям, которым назначен пакет.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-139">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="c2cb1-140">Ниже описаны действия, которые необходимо выполнить, чтобы просмотреть, назначить и настроить пакеты политики в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-140">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="c2cb1-141">Просмотр параметров политики в пакете политики</span><span class="sxs-lookup"><span data-stu-id="c2cb1-141">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="c2cb1-142">В левой области навигации центра администрирования Microsoft Teams щелкните **пакеты политики**, а затем выберите пакет политики, щелкнув слева от его имени.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-142">In the left navigation of the Microsoft Teams admin center, click **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="c2cb1-143">Выберите политику, которую вы хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-143">Click the policy you want to view.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="c2cb1-144">Назначение пакета политики</span><span class="sxs-lookup"><span data-stu-id="c2cb1-144">Assign a policy package</span></span>

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="c2cb1-145">Назначение пакета политики для одного пользователя</span><span class="sxs-lookup"><span data-stu-id="c2cb1-145">Assign a policy package to one user</span></span>

1. <span data-ttu-id="c2cb1-146">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел **Пользователи**и выберите пользователя.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-146">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="c2cb1-147">На странице пользователя нажмите **политики**, а затем рядом с пунктом **Политика**выберите команду **изменить**.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-147">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="c2cb1-148">В области **Назначение пакета политики** выберите пакет, который вы хотите назначить, и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-148">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="c2cb1-149">Назначение пакета политики нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="c2cb1-149">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="c2cb1-150">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел **пакеты политики**, а затем выберите пакет политики, который вы хотите назначить, щелкнув слева от его имени.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-150">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="c2cb1-151">Щелкните **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-151">Click **Manage users**.</span></span>
3. <span data-ttu-id="c2cb1-152">В области **Управление пользователями** найдите пользователя по отображаемому имени или по имени пользователя, выберите имя и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-152">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="c2cb1-153">Повторите этот шаг для каждого пользователя, которого вы хотите добавить.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-153">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="c2cb1-154">Завершив добавление пользователей, нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-154">When you're finished adding users, click **Save**.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="c2cb1-155">Настройка политик в пакете политики</span><span class="sxs-lookup"><span data-stu-id="c2cb1-155">Customize policies in a policy package</span></span>

<span data-ttu-id="c2cb1-156">Вы можете изменить параметры политики на странице **пакеты политики** или непосредственно на страницу политики в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-156">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="c2cb1-157">В левой области навигации центра администрирования Microsoft Teams выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-157">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="c2cb1-158">Щелкните **пакеты политики**, а затем выберите пакет политики, щелкнув слева от его имени.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-158">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="c2cb1-159">Выберите тип политики.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-159">Click the policy type.</span></span>  <span data-ttu-id="c2cb1-160">Например, выберите **политики обмена сообщениями**.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-160">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="c2cb1-161">Выберите политику, которую вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-161">Click the policy you want to edit.</span></span> <span data-ttu-id="c2cb1-162">Политики, связанные с пакетом политики, имеют то же имя, что и пакет политики.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-162">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="c2cb1-163">Внесите нужные изменения и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-163">Make the changes that you want, and then click **Save**.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="c2cb1-164">Поиск и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="c2cb1-164">Troubleshooting</span></span>

<span data-ttu-id="c2cb1-165">**При назначении пакета политики появляется сообщение об ошибке**</span><span class="sxs-lookup"><span data-stu-id="c2cb1-165">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="c2cb1-166">Это может произойти, если одна или несколько политик в пакете не были успешно созданы или применены.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-166">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="c2cb1-167">Переназначение пакета политики пользователям.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-167">Reassign the policy package to your users.</span></span> <span data-ttu-id="c2cb1-168">Повторное выполнение операции обычно решает эту проблему.</span><span class="sxs-lookup"><span data-stu-id="c2cb1-168">Retrying the operation typically fixes this issue.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c2cb1-169">См. также</span><span class="sxs-lookup"><span data-stu-id="c2cb1-169">Related topics</span></span>

[<span data-ttu-id="c2cb1-170">Пакеты политик Microsoft Teams для администраторов образовательных учреждений</span><span class="sxs-lookup"><span data-stu-id="c2cb1-170">Microsoft Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)
