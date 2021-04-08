---
title: Управление пакетами политики в Microsoft Teams
author: cichur
ms.author: v-cichur
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
description: Узнайте, как использовать пакеты политик и управлять ими в Microsoft Teams, чтобы упростить, оптимизировать и обеспечить единообразие при управлении политиками для групп пользователей.
ms.openlocfilehash: 1b7e6e5c6311ebd51b0f00b86953291ed4ac63b3
ms.sourcegitcommit: b52b6aba289396c4fc10dd856817137eb1bc1f67
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/07/2021
ms.locfileid: "51634231"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="3c8c7-103">Управление пакетами политики в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3c8c7-103">Manage policy packages in Microsoft Teams</span></span>

<span data-ttu-id="3c8c7-104">Пакет политики в Microsoft Teams — это набор готовых политик и параметров политик, которые можно назначить пользователям с похожими ролями в организации.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-104">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="3c8c7-105">Мы создали пакеты политик, которые упрощают, упрощают и обеспечивают единообразие при управлении политиками для групп пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-105">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="3c8c7-106">Вы можете использовать [пакеты](#policy-packages-included-in-teams) политики, включенные в Teams, или создать собственные [пакеты](#custom-policy-packages) политики (в режиме личной предварительной версии).</span><span class="sxs-lookup"><span data-stu-id="3c8c7-106">You can use the [policy packages included in Teams](#policy-packages-included-in-teams) or [create your own custom policy packages](#custom-policy-packages) (in private preview).</span></span>

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="Снимок экрана: страница пакетов политики в Центре администрирования":::

<span data-ttu-id="3c8c7-108">Параметры политик в пакете политики можно настроить в соответствии с потребностями пользователей.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-108">You can customize the settings of the policies in a policy package to suit the needs of your users.</span></span> <span data-ttu-id="3c8c7-109">При изменении параметров политик в пакете все пользователи, которым он назначен, получают обновленные параметры.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-109">When you change the settings of policies in a package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="3c8c7-110">Вы управляете пакетами политики с помощью Центра администрирования Microsoft Teams или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-110">You manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="3c8c7-111">Что такое пакет политики?</span><span class="sxs-lookup"><span data-stu-id="3c8c7-111">What is a policy package?</span></span>

<span data-ttu-id="3c8c7-112">Пакеты политики позволяют управлять функциями Teams, которые вы хотите разрешить или ограничить для определенных наборов людей в организации.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-112">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="3c8c7-113">Каждый пакет политики в Teams предназначен для роли пользователя и содержит предопределяющую политику и параметры политики, которые поддерживают типичные для нее действия по совместной работе и связи.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-113">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="3c8c7-114">Пакеты политики поддерживают следующие типы политик Teams:</span><span class="sxs-lookup"><span data-stu-id="3c8c7-114">Policy packages support the following Teams policy types:</span></span>

- <span data-ttu-id="3c8c7-115">Политика обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="3c8c7-115">Messaging policy</span></span>
- <span data-ttu-id="3c8c7-116">Политика встречи</span><span class="sxs-lookup"><span data-stu-id="3c8c7-116">Meeting policy</span></span>
- <span data-ttu-id="3c8c7-117">Политика настройки приложений</span><span class="sxs-lookup"><span data-stu-id="3c8c7-117">App setup policy</span></span>
- <span data-ttu-id="3c8c7-118">Политика звонков</span><span class="sxs-lookup"><span data-stu-id="3c8c7-118">Calling policy</span></span>
- <span data-ttu-id="3c8c7-119">Политика живых событий</span><span class="sxs-lookup"><span data-stu-id="3c8c7-119">Live events policy</span></span>

## <a name="policy-packages-included-in-teams"></a><span data-ttu-id="3c8c7-120">Пакеты политики, включенные в Teams</span><span class="sxs-lookup"><span data-stu-id="3c8c7-120">Policy packages included in Teams</span></span>

<span data-ttu-id="3c8c7-121">В настоящее время Teams содержит следующие пакеты политики:</span><span class="sxs-lookup"><span data-stu-id="3c8c7-121">Teams currently includes the following policy packages.</span></span>

| <span data-ttu-id="3c8c7-122">Имя пакета</span><span class="sxs-lookup"><span data-stu-id="3c8c7-122">Package name</span></span> | <span data-ttu-id="3c8c7-123">Описание</span><span class="sxs-lookup"><span data-stu-id="3c8c7-123">Description</span></span> |
|---------|---------|
|<span data-ttu-id="3c8c7-124">Образование (учащийся с высшим образованием)</span><span class="sxs-lookup"><span data-stu-id="3c8c7-124">Education (Higher education student)</span></span>    |<span data-ttu-id="3c8c7-125">Создает набор политик и параметров политики, которые применяются к учащимся более высокого уровня.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-125">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="3c8c7-126">Образование (учащийся основной школы)</span><span class="sxs-lookup"><span data-stu-id="3c8c7-126">Education (Primary school student)</span></span>   |<span data-ttu-id="3c8c7-127">Создает набор политик и параметров политики, которые применяются к основным учащимся.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-127">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="3c8c7-128">Образование (учащийся дополнительного учебного заведения)</span><span class="sxs-lookup"><span data-stu-id="3c8c7-128">Education (Secondary school student)</span></span>    |<span data-ttu-id="3c8c7-129">Создает набор политик и параметров политики, которые применяются к дополнительным учащимся.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-129">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="3c8c7-130">Образование (преподаватель)</span><span class="sxs-lookup"><span data-stu-id="3c8c7-130">Education (Teacher)</span></span>    |<span data-ttu-id="3c8c7-131">Создает набор политик и параметров политики, которые применяются к преподавателям.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-131">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="3c8c7-132">Образование (преподаватель начальной школы, использующий дистанционное обучение)</span><span class="sxs-lookup"><span data-stu-id="3c8c7-132">Education (Primary school teacher using remote learning)</span></span>    |<span data-ttu-id="3c8c7-133">Создает набор политик, применимых к учителям начальных классов, для обеспечения максимальной безопасности и совместной работы учащихся при использовании дистанционного обучения.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-133">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="3c8c7-134">Образование (учащийся начальной школы, использующий дистанционное обучение)</span><span class="sxs-lookup"><span data-stu-id="3c8c7-134">Education (Primary school student using remote learning)</span></span>    |<span data-ttu-id="3c8c7-135">Создает набор политик, применимых к учащимся начальных классов, для обеспечения максимальной безопасности и совместной работы учащихся при использовании дистанционного обучения.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-135">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="3c8c7-136">Frontline Manager</span><span class="sxs-lookup"><span data-stu-id="3c8c7-136">Frontline manager</span></span> |<span data-ttu-id="3c8c7-137">Создает набор политик и применяет их к руководителям frontline в организации.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-137">Creates a set of policies and applies those settings to Frontline managers in your organization.</span></span> |
|<span data-ttu-id="3c8c7-138">Фронтальная работяга</span><span class="sxs-lookup"><span data-stu-id="3c8c7-138">Frontline worker</span></span> |<span data-ttu-id="3c8c7-139">Создает набор политик и применяет эти параметры к сотрудникам, работающим с frontline в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-139">Creates a set of policies and applies those settings to Frontline workers in your organization.</span></span> |
|<span data-ttu-id="3c8c7-140">Медицинский работник в учреждении здравоохранения</span><span class="sxs-lookup"><span data-stu-id="3c8c7-140">Healthcare clinical worker</span></span>  |<span data-ttu-id="3c8c7-141">Создает набор политик и параметров политик, предоставляющий медицинским работникам, таким как медсестры, старшие сестры, терапевты и социальные работники, полный доступ к чатам, звонкам, управлению сменами и собраниям.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-141">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="3c8c7-142">Информационный работник в учреждении здравоохранения</span><span class="sxs-lookup"><span data-stu-id="3c8c7-142">Healthcare information worker</span></span>  |<span data-ttu-id="3c8c7-143">Создает набор политик и параметров политик, предоставляющий информационным сотрудникам, таким как ИТ-персонал, информационный персонал, финансовый персонал и сотрудники по обеспечению соответствия требованиям, полный доступ к чатам, звонкам и собраниям.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-143">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="3c8c7-144">Палата для пациентов в учреждении здравоохранения</span><span class="sxs-lookup"><span data-stu-id="3c8c7-144">Healthcare patient room</span></span>  |<span data-ttu-id="3c8c7-145">Создает набор политик и параметров политик, применяемый к палатам для пациентов в медицинской организации.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-145">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|
|<span data-ttu-id="3c8c7-146">Малый и средний бизнес (бизнес-голос)</span><span class="sxs-lookup"><span data-stu-id="3c8c7-146">Small and medium business user (Business Voice)</span></span> |<span data-ttu-id="3c8c7-147">Создает политику настройки приложений, включаемую в приложения для работы с деловыми голосами.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-147">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="3c8c7-148">Малый и средний бизнес(без бизнес-голосовой почты)</span><span class="sxs-lookup"><span data-stu-id="3c8c7-148">Small and medium business user (without Business Voice)</span></span> |<span data-ttu-id="3c8c7-149">Создает политику настройки приложения, релевантную для пользователей Teams малого и среднего размера (не для голосовой связи).</span><span class="sxs-lookup"><span data-stu-id="3c8c7-149">Creates an app setup policy relevant for a small and medium sized business Teams users (non-Business Voice experience).</span></span>
|<span data-ttu-id="3c8c7-150">Сотрудница по безопасности</span><span class="sxs-lookup"><span data-stu-id="3c8c7-150">Public safety officer</span></span>   |<span data-ttu-id="3c8c7-151">Создает набор политик и параметров политики, которые применяются к сотрудникам, которые работают с политикой безопасности других лиц в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-151">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|

> [!NOTE]
> <span data-ttu-id="3c8c7-152">Мы добавим дополнительные пакеты политик в будущих выпусках Teams, поэтому проверяйте их на самые последние сведения.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-152">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="3c8c7-153">Каждой отдельной политике присваивается имя пакета политики, чтобы легко определять политики, связанные с пакетом.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-153">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="3c8c7-154">Например, когда вы назначаете пакет политики "Образование (преподаватель)" преподавателям в вашем учебном за учебных заведениях, для каждой политики в пакете создается Education_Teacher политика.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-154">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![Снимок экрана: пакет политики "Образование (преподаватель)"](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a><span data-ttu-id="3c8c7-156">Настраиваемые пакеты политики</span><span class="sxs-lookup"><span data-stu-id="3c8c7-156">Custom policy packages</span></span>

<span data-ttu-id="3c8c7-157">**Пакеты настраиваемой политики пока недоступны для облака сообщества государственных организаций (GCC)**</span><span class="sxs-lookup"><span data-stu-id="3c8c7-157">**Custom policy packages is not yet available for the Government Community Cloud (GCC)**</span></span>

<span data-ttu-id="3c8c7-158">Пакеты настраиваемой политики можно объединить в пакет собственные политики для пользователей с похожими ролями в организации.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-158">Custom policy packages let you bundle your own set of policies for users with similar roles in you organization.</span></span> <span data-ttu-id="3c8c7-159">Создайте собственные пакеты политики, добавив необходимые типы политик и политики.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-159">Create your own policy packages by adding the policy types and policies that you need.</span></span>

<span data-ttu-id="3c8c7-160">Чтобы создать настраиваемый пакет политики:</span><span class="sxs-lookup"><span data-stu-id="3c8c7-160">To create a new custom policy package:</span></span>

1. <span data-ttu-id="3c8c7-161">В левой области навигации Центра администрирования Microsoft Teams выберите пакеты политики **и** нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="3c8c7-161">In the left navigation of the Microsoft Teams admin center,  select **Policy packages**, and then click **Add**.</span></span>

    :::image type="content" source="media/policy-packages-add.png" alt-text="Снимок экрана: кнопка "Добавить" на странице пакетов политики в Центре администрирования":::

2. <span data-ttu-id="3c8c7-163">Введите имя и описание пакета.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-163">Enter a name and description for your package.</span></span>

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="Снимок экрана: добавление нового пакета настраиваемой политики":::

3. <span data-ttu-id="3c8c7-165">Выберите типы политик и имена политик, которые нужно включить в пакет.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-165">Select the policy types and policy names to include in the package.</span></span>

4. <span data-ttu-id="3c8c7-166">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-166">Click **Save**.</span></span>

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="3c8c7-167">Использование пакетов политики</span><span class="sxs-lookup"><span data-stu-id="3c8c7-167">How to use policy packages</span></span>

<span data-ttu-id="3c8c7-168">Ниже описано, как использовать пакеты политики в организации.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-168">The following outlines how to use policy packages in your organization.</span></span>

![Общие сведения об использовании пакетов политики](media/manage-policy-packages-overview.png)

- <span data-ttu-id="3c8c7-170">**[Просмотр:](#view-the-settings-of-a-policy-in-a-policy-package)** просмотр политик в пакете политики.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-170">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the policies in a policy package.</span></span> <span data-ttu-id="3c8c7-171">Затем перед назначением пакета можно просмотреть параметры каждой политики в пакете.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-171">Then, view the settings of each policy in a package before you assign the package.</span></span> <span data-ttu-id="3c8c7-172">Убедитесь, что вы понимаете каждый из параметров.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-172">Make sure that you understand each setting.</span></span> <span data-ttu-id="3c8c7-173">Решите, подходят ли готовые значения для вашей организации и нужно ли изменить их на более строгие или ограниченные в зависимости от потребностей организации.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-173">Decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="3c8c7-174">При удалении политики вы по-прежнему сможете просматривать параметры, но не сможете изменить их.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-174">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="3c8c7-175">При назначении пакета политики удаленная политика создается повторно с заранее задав ее параметры.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-175">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="3c8c7-176">**[Настройка:](#customize-policies-in-a-policy-package)** настройка параметров политик в пакете политики в потребностям вашей организации.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-176">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span>

- <span data-ttu-id="3c8c7-177">**[Назначить:](#assign-a-policy-package)** назначьте пакет политики пользователям.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-177">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span>  

> [!NOTE]
> <span data-ttu-id="3c8c7-178">Вы также можете изменить параметры политик в пакете политики после назначения пакета.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-178">You can also change the settings of policies in a policy package after you assign a package.</span></span> <span data-ttu-id="3c8c7-179">Изменения, внесенные в параметры политики, автоматически применяются к пользователям, которым назначен пакет.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-179">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="3c8c7-180">Ниже вы можете просмотреть, назначить и настроить пакеты политики в Центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-180">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="3c8c7-181">Просмотр параметров политики в пакете политики</span><span class="sxs-lookup"><span data-stu-id="3c8c7-181">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="3c8c7-182">В левой области навигации Центра администрирования Microsoft Teams выберите пакеты **политики,** а затем выберите пакет политики, щелкнув слева от его имени.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-182">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>

2. <span data-ttu-id="3c8c7-183">Выберите политику, которая вы хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-183">Click the policy you want to view.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="3c8c7-184">Настройка политик в пакете политики</span><span class="sxs-lookup"><span data-stu-id="3c8c7-184">Customize policies in a policy package</span></span>

<span data-ttu-id="3c8c7-185">Вы можете изменить параметры политики  на странице пакетов политики или непосредственно на странице политики в Центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-185">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="3c8c7-186">В левой области навигации Центра администрирования Microsoft Teams сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="3c8c7-186">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="3c8c7-187">Щелкните **пакеты** политики, а затем выберите пакет политики, щелкнув слева от его имени.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-187">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="3c8c7-188">Выберите тип политики.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-188">Click the policy type.</span></span>  <span data-ttu-id="3c8c7-189">Например, щелкните **"Политики обмена сообщениями".**</span><span class="sxs-lookup"><span data-stu-id="3c8c7-189">For example, click **Messaging policies**.</span></span>

2. <span data-ttu-id="3c8c7-190">Выберите политику, которая вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-190">Select the policy you want to edit.</span></span> <span data-ttu-id="3c8c7-191">Политики, связанные с пакетом политики, имеют то же имя, что и пакет политики.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-191">Policies that are linked to a policy package have the same name as the policy package.</span></span>

3. <span data-ttu-id="3c8c7-192">Внести нужные изменения и нажмите кнопку **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="3c8c7-192">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="3c8c7-193">Назначение пакета политики</span><span class="sxs-lookup"><span data-stu-id="3c8c7-193">Assign a policy package</span></span>

<span data-ttu-id="3c8c7-194">Пакет политики можно назначить отдельному пользователю, группе или пакету пользователей.</span><span class="sxs-lookup"><span data-stu-id="3c8c7-194">You can assign a policy package to an individual user, a group, or a batch of users.</span></span> <span data-ttu-id="3c8c7-195">Дополнительные сведения о назначении пакетов политики см. в сведениях о назначении пакетов политики пользователям [и группам.](assign-policy-packages.md)</span><span class="sxs-lookup"><span data-stu-id="3c8c7-195">For more information on how to assign policy packages, see [Assign policy packages to users and groups](assign-policy-packages.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3c8c7-196">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="3c8c7-196">Related topics</span></span>

- [<span data-ttu-id="3c8c7-197">Назначение пакетов политики</span><span class="sxs-lookup"><span data-stu-id="3c8c7-197">Assign policy packages</span></span>](assign-policy-packages.md)
- [<span data-ttu-id="3c8c7-198">Пакеты политики Teams для администраторов EDU</span><span class="sxs-lookup"><span data-stu-id="3c8c7-198">Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)
- [<span data-ttu-id="3c8c7-199">Пакеты политик Teams для здравоохранения</span><span class="sxs-lookup"><span data-stu-id="3c8c7-199">Teams policy packages for healthcare</span></span>](policy-packages-healthcare.md)
- [<span data-ttu-id="3c8c7-200">Пакеты политики Teams для государственных органов</span><span class="sxs-lookup"><span data-stu-id="3c8c7-200">Teams policy packages for government</span></span>](policy-packages-gov.md)
