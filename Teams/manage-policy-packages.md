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
ms.openlocfilehash: 395b0f2c05278224bf024c1cf3e453a2f51bd725
ms.sourcegitcommit: de7d0807186a64dfe1cca15d34c39bdbad6af836
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2021
ms.locfileid: "50085189"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="96c7c-103">Управление пакетами политики в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="96c7c-103">Manage policy packages in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="96c7c-104">Одна из функций, рассмотренных в этой [статье,](#custom-policy-packages)— настраиваемые пакеты политики — в настоящее время находится в режиме предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="96c7c-104">One of the features discussed in this article, [custom policy packages](#custom-policy-packages), is currently in private preview.</span></span>

<span data-ttu-id="96c7c-105">Пакет политики в Microsoft Teams — это набор предопределельных политик и параметров политики, которые можно назначать пользователям с похожими ролями в организации.</span><span class="sxs-lookup"><span data-stu-id="96c7c-105">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="96c7c-106">Мы создали пакеты политик, которые упрощают, упрощают и обеспечивают единообразие при управлении политиками для групп пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="96c7c-106">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="96c7c-107">Вы можете использовать [пакеты](#policy-packages-included-in-teams) политики, включенные в Teams, или создать собственные [пакеты](#custom-policy-packages) политики (в режиме личной предварительной версии).</span><span class="sxs-lookup"><span data-stu-id="96c7c-107">You can use the [policy packages included in Teams](#policy-packages-included-in-teams) or [create your own custom policy packages](#custom-policy-packages) (in private preview).</span></span>

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="Снимок экрана: страница пакетов политики в Центре администрирования":::

<span data-ttu-id="96c7c-109">Параметры политик в пакете политики можно настроить в соответствии с потребностями пользователей.</span><span class="sxs-lookup"><span data-stu-id="96c7c-109">You can customize the settings of the policies in a policy package to suit the needs of your users.</span></span> <span data-ttu-id="96c7c-110">При изменении параметров политик в пакете все пользователи, которым он назначен, получают обновленные параметры.</span><span class="sxs-lookup"><span data-stu-id="96c7c-110">When you change the settings of policies in a package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="96c7c-111">Вы управляете пакетами политики с помощью Центра администрирования Microsoft Teams или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="96c7c-111">You manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="96c7c-112">Что такое пакет политики?</span><span class="sxs-lookup"><span data-stu-id="96c7c-112">What is a policy package?</span></span>

<span data-ttu-id="96c7c-113">Пакеты политики позволяют управлять функциями Teams, которые вы хотите разрешить или ограничить для определенных наборов людей в организации.</span><span class="sxs-lookup"><span data-stu-id="96c7c-113">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="96c7c-114">Каждый пакет политики в Teams разработан на основе роли пользователя и содержит предопределные политики и параметры политики, которые поддерживают типичные для нее действия по совместной работе и связи.</span><span class="sxs-lookup"><span data-stu-id="96c7c-114">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="96c7c-115">Пакеты политики поддерживают следующие типы политик Teams:</span><span class="sxs-lookup"><span data-stu-id="96c7c-115">Policy packages support the following Teams policy types:</span></span>

- <span data-ttu-id="96c7c-116">Политика обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="96c7c-116">Messaging policy</span></span>
- <span data-ttu-id="96c7c-117">Политика встречи</span><span class="sxs-lookup"><span data-stu-id="96c7c-117">Meeting policy</span></span>
- <span data-ttu-id="96c7c-118">Политика настройки приложений</span><span class="sxs-lookup"><span data-stu-id="96c7c-118">App setup policy</span></span>
- <span data-ttu-id="96c7c-119">Политика звонков</span><span class="sxs-lookup"><span data-stu-id="96c7c-119">Calling policy</span></span>
- <span data-ttu-id="96c7c-120">Политика живых событий</span><span class="sxs-lookup"><span data-stu-id="96c7c-120">Live events policy</span></span>

## <a name="policy-packages-included-in-teams"></a><span data-ttu-id="96c7c-121">Пакеты политики, включенные в Teams</span><span class="sxs-lookup"><span data-stu-id="96c7c-121">Policy packages included in Teams</span></span>

<span data-ttu-id="96c7c-122">В настоящее время Teams содержит следующие пакеты политики:</span><span class="sxs-lookup"><span data-stu-id="96c7c-122">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="96c7c-123">**Имя пакета**</span><span class="sxs-lookup"><span data-stu-id="96c7c-123">**Package name**</span></span>  |<span data-ttu-id="96c7c-124">**Описание**</span><span class="sxs-lookup"><span data-stu-id="96c7c-124">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="96c7c-125">Образование (учащийся с высшим образованием)</span><span class="sxs-lookup"><span data-stu-id="96c7c-125">Education (Higher education student)</span></span>    |<span data-ttu-id="96c7c-126">Создает набор политик и параметров политики, которые применяются к учащимся более высокого уровня.</span><span class="sxs-lookup"><span data-stu-id="96c7c-126">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="96c7c-127">Образование (учащийся основной школы)</span><span class="sxs-lookup"><span data-stu-id="96c7c-127">Education (Primary school student)</span></span>   |<span data-ttu-id="96c7c-128">Создает набор политик и параметров политики, которые применяются к основным учащимся.</span><span class="sxs-lookup"><span data-stu-id="96c7c-128">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="96c7c-129">Образование (учащийся дополнительного учебного заведения)</span><span class="sxs-lookup"><span data-stu-id="96c7c-129">Education (Secondary school student)</span></span>    |<span data-ttu-id="96c7c-130">Создает набор политик и параметров политики, которые применяются к дополнительным учащимся.</span><span class="sxs-lookup"><span data-stu-id="96c7c-130">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="96c7c-131">Образование (преподаватель)</span><span class="sxs-lookup"><span data-stu-id="96c7c-131">Education (Teacher)</span></span>    |<span data-ttu-id="96c7c-132">Создает набор политик и параметров политики, которые применяются к преподавателям.</span><span class="sxs-lookup"><span data-stu-id="96c7c-132">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="96c7c-133">Образование (преподаватель начальной школы, использующий дистанционное обучение)</span><span class="sxs-lookup"><span data-stu-id="96c7c-133">Education (Primary school teacher using remote learning)</span></span>    |<span data-ttu-id="96c7c-134">Создает набор политик, применимых к учителям начальных классов, для обеспечения максимальной безопасности и совместной работы учащихся при использовании дистанционного обучения.</span><span class="sxs-lookup"><span data-stu-id="96c7c-134">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="96c7c-135">Образование (учащийся начальной школы, использующий дистанционное обучение)</span><span class="sxs-lookup"><span data-stu-id="96c7c-135">Education (Primary school student using remote learning)</span></span>    |<span data-ttu-id="96c7c-136">Создает набор политик, применимых к учащимся начальных классов, для обеспечения максимальной безопасности и совместной работы учащихся при использовании дистанционного обучения.</span><span class="sxs-lookup"><span data-stu-id="96c7c-136">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="96c7c-137">Frontline Manager</span><span class="sxs-lookup"><span data-stu-id="96c7c-137">Frontline manager</span></span> |<span data-ttu-id="96c7c-138">Создает набор политик и применяет их к руководителям frontline в организации.</span><span class="sxs-lookup"><span data-stu-id="96c7c-138">Creates a set of policies and applies those settings to Frontline managers in your organization.</span></span> |
|<span data-ttu-id="96c7c-139">Фронтальная работяга</span><span class="sxs-lookup"><span data-stu-id="96c7c-139">Frontline worker</span></span> |<span data-ttu-id="96c7c-140">Создает набор политик и применяет эти параметры к сотрудникам, работающим с frontline в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="96c7c-140">Creates a set of policies and applies those settings to Frontline workers in your organization.</span></span> |
|<span data-ttu-id="96c7c-141">медицинского медицинского учреждения, медицинского медицинского учреждения</span><span class="sxs-lookup"><span data-stu-id="96c7c-141">Healthcare clinical worker</span></span>  |<span data-ttu-id="96c7c-142">Создает набор политик и параметров политики, которые дают сотрудникам, работающим в медицинской области, например, медсестрам, врачам и социальным работникам полный доступ к чату, звонкам, управлению сменами и собраниям.</span><span class="sxs-lookup"><span data-stu-id="96c7c-142">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="96c7c-143">Информационный работник в сфере здравоохранения</span><span class="sxs-lookup"><span data-stu-id="96c7c-143">Healthcare information worker</span></span>  |<span data-ttu-id="96c7c-144">Создает набор политик и параметров политики, который дает информационным работникам, таким как ИТ-персонал, информирует сотрудников, финансового персонала и сотрудников, которые работают за соблюдение требований, полный доступ к чату, звонкам и собраниям.</span><span class="sxs-lookup"><span data-stu-id="96c7c-144">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="96c7c-145">Медицинские кабинеты пациентов</span><span class="sxs-lookup"><span data-stu-id="96c7c-145">Healthcare patient room</span></span>  |<span data-ttu-id="96c7c-146">Создает набор политик и параметров политики, которые применяются к комнатам пациентов в вашей организации здравоохранения.</span><span class="sxs-lookup"><span data-stu-id="96c7c-146">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|
|<span data-ttu-id="96c7c-147">Малый и средний бизнес (голосовая почта)</span><span class="sxs-lookup"><span data-stu-id="96c7c-147">Small and medium business user (Business Voice)</span></span> |<span data-ttu-id="96c7c-148">Создает политику настройки приложений, которая включает приложения для работы с деловым голосом.</span><span class="sxs-lookup"><span data-stu-id="96c7c-148">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="96c7c-149">Малый и средний бизнес(без бизнес-голосовой почты)</span><span class="sxs-lookup"><span data-stu-id="96c7c-149">Small and medium business user (without Business Voice)</span></span> |<span data-ttu-id="96c7c-150">Создает политику настройки приложения, релевантную для пользователей Teams малого и среднего размера (не для голосовой связи).</span><span class="sxs-lookup"><span data-stu-id="96c7c-150">Creates an app setup policy relevant for a small and medium sized business Teams users (non-Business Voice experience).</span></span>
|<span data-ttu-id="96c7c-151">Сотрудник службы безопасности</span><span class="sxs-lookup"><span data-stu-id="96c7c-151">Public safety officer</span></span>   |<span data-ttu-id="96c7c-152">Создает набор политик и параметров политики, которые применяются к сотрудникам, которые работают с политикой безопасности других лиц в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="96c7c-152">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|

> [!NOTE]
> <span data-ttu-id="96c7c-153">Мы добавим дополнительные пакеты политик в будущих выпусках Teams, поэтому проверяйте их на самые последние сведения.</span><span class="sxs-lookup"><span data-stu-id="96c7c-153">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="96c7c-154">Каждой отдельной политике дается имя пакета политики, чтобы можно было легко определить политики, связанные с пакетом политики.</span><span class="sxs-lookup"><span data-stu-id="96c7c-154">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="96c7c-155">Например, когда вы назначаете пакет политики "Образование (преподаватель)" преподавателям в вашем учебном за учебных заведениях, для каждой политики в пакете создается Education_Teacher политика.</span><span class="sxs-lookup"><span data-stu-id="96c7c-155">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![Снимок экрана: пакет политики "Образование (преподаватель)"](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a><span data-ttu-id="96c7c-157">Настраиваемые пакеты политики</span><span class="sxs-lookup"><span data-stu-id="96c7c-157">Custom policy packages</span></span>

<span data-ttu-id="96c7c-158">**Эта функция доступна в закрытой ознакомительной версии**</span><span class="sxs-lookup"><span data-stu-id="96c7c-158">**This feature is in private preview**</span></span>

<span data-ttu-id="96c7c-159">Пакеты настраиваемой политики можно объединить в пакет собственные политики для пользователей с похожими ролями в организации.</span><span class="sxs-lookup"><span data-stu-id="96c7c-159">Custom policy packages let you bundle your own set of policies for users with similar roles in you organization.</span></span> <span data-ttu-id="96c7c-160">Создайте собственные пакеты политики, добавив необходимые типы политик и политики.</span><span class="sxs-lookup"><span data-stu-id="96c7c-160">Create your own policy packages by adding the policy types and policies that you need.</span></span>

<span data-ttu-id="96c7c-161">Чтобы создать настраиваемый пакет политики:</span><span class="sxs-lookup"><span data-stu-id="96c7c-161">To create a new custom policy package:</span></span>

1. <span data-ttu-id="96c7c-162">В левой области навигации Центра администрирования Microsoft Teams выберите пакеты политики **и** нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="96c7c-162">In the left navigation of the Microsoft Teams admin center,  select **Policy packages**, and then click **Add**.</span></span>
    :::image type="content" source="media/policy-packages-add.png" alt-text="Снимок экрана: кнопка "Добавить" на странице пакетов политики в Центре администрирования":::
2. <span data-ttu-id="96c7c-164">Введите имя и описание пакета.</span><span class="sxs-lookup"><span data-stu-id="96c7c-164">Enter a name and description for your package.</span></span>
    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="Снимок экрана: добавление нового пакета настраиваемой политики":::
3. <span data-ttu-id="96c7c-166">Выберите типы политик и имена политик, которые нужно включить в пакет.</span><span class="sxs-lookup"><span data-stu-id="96c7c-166">Select the policy types and policy names to include in the package.</span></span>
4. <span data-ttu-id="96c7c-167">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="96c7c-167">Click **Save**.</span></span>

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="96c7c-168">Использование пакетов политики</span><span class="sxs-lookup"><span data-stu-id="96c7c-168">How to use policy packages</span></span>

<span data-ttu-id="96c7c-169">Ниже описано, как использовать пакеты политики в организации.</span><span class="sxs-lookup"><span data-stu-id="96c7c-169">The following outlines how to use policy packages in your organization.</span></span>

![Общие сведения об использовании пакетов политики](media/manage-policy-packages-overview.png)

- <span data-ttu-id="96c7c-171">**[Просмотр:](#view-the-settings-of-a-policy-in-a-policy-package)** просмотр политик в пакете политики.</span><span class="sxs-lookup"><span data-stu-id="96c7c-171">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the policies in a policy package.</span></span> <span data-ttu-id="96c7c-172">Затем перед назначением пакета можно просмотреть параметры каждой политики в пакете.</span><span class="sxs-lookup"><span data-stu-id="96c7c-172">Then, view the settings of each policy in a package before you assign the package.</span></span> <span data-ttu-id="96c7c-173">Убедитесь, что вы понимаете каждый из параметров.</span><span class="sxs-lookup"><span data-stu-id="96c7c-173">Make sure that you understand each setting.</span></span> <span data-ttu-id="96c7c-174">Решите, подходят ли готовые значения для вашей организации и нужно ли изменить их на более строгие или ограниченные в зависимости от потребностей организации.</span><span class="sxs-lookup"><span data-stu-id="96c7c-174">Decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="96c7c-175">При удалении политики вы по-прежнему сможете просматривать параметры, но не сможете изменить их.</span><span class="sxs-lookup"><span data-stu-id="96c7c-175">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="96c7c-176">При назначении пакета политики удаленная политика создается повторно с заранее задав ее параметры.</span><span class="sxs-lookup"><span data-stu-id="96c7c-176">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="96c7c-177">**[Настройка:](#customize-policies-in-a-policy-package)** настройка параметров политик в пакете политики в потребностям вашей организации.</span><span class="sxs-lookup"><span data-stu-id="96c7c-177">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span>

- <span data-ttu-id="96c7c-178">**[Назначить:](#assign-a-policy-package)** назначьте пакет политики пользователям.</span><span class="sxs-lookup"><span data-stu-id="96c7c-178">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span>  

> [!NOTE]
> <span data-ttu-id="96c7c-179">Вы также можете изменить параметры политик в пакете политики после назначения пакета.</span><span class="sxs-lookup"><span data-stu-id="96c7c-179">You can also change the settings of policies in a policy package after you assign a package.</span></span> <span data-ttu-id="96c7c-180">Изменения, внесенные в параметры политики, автоматически применяются к пользователям, которым назначен пакет.</span><span class="sxs-lookup"><span data-stu-id="96c7c-180">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="96c7c-181">Ниже вы можете просмотреть, назначить и настроить пакеты политики в Центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="96c7c-181">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="96c7c-182">Просмотр параметров политики в пакете политики</span><span class="sxs-lookup"><span data-stu-id="96c7c-182">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="96c7c-183">В левой области навигации Центра администрирования Microsoft Teams выберите пакеты **политики,** а затем выберите пакет политики, щелкнув слева от его имени.</span><span class="sxs-lookup"><span data-stu-id="96c7c-183">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="96c7c-184">Выберите политику, которая вы хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="96c7c-184">Click the policy you want to view.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="96c7c-185">Настройка политик в пакете политики</span><span class="sxs-lookup"><span data-stu-id="96c7c-185">Customize policies in a policy package</span></span>

<span data-ttu-id="96c7c-186">Вы можете изменить параметры политики  на странице пакетов политики или непосредственно на странице политики в Центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="96c7c-186">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="96c7c-187">В левой области навигации Центра администрирования Microsoft Teams сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="96c7c-187">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="96c7c-188">Щелкните **пакеты** политики, а затем выберите пакет политики, щелкнув слева от его имени.</span><span class="sxs-lookup"><span data-stu-id="96c7c-188">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="96c7c-189">Выберите тип политики.</span><span class="sxs-lookup"><span data-stu-id="96c7c-189">Click the policy type.</span></span>  <span data-ttu-id="96c7c-190">Например, щелкните **"Политики обмена сообщениями".**</span><span class="sxs-lookup"><span data-stu-id="96c7c-190">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="96c7c-191">Выберите политику, которая вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="96c7c-191">Select the policy you want to edit.</span></span> <span data-ttu-id="96c7c-192">Политики, связанные с пакетом политики, имеют то же имя, что и пакет политики.</span><span class="sxs-lookup"><span data-stu-id="96c7c-192">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="96c7c-193">Внести нужные изменения и нажмите кнопку **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="96c7c-193">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="96c7c-194">Назначение пакета политики</span><span class="sxs-lookup"><span data-stu-id="96c7c-194">Assign a policy package</span></span> 

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="96c7c-195">Назначение пакета политики одному пользователю</span><span class="sxs-lookup"><span data-stu-id="96c7c-195">Assign a policy package to one user</span></span>

1. <span data-ttu-id="96c7c-196">В Центре администрирования Microsoft Teams в области навигации слева перейдите в раздел **Пользователи**, затем щелкните пользователя.</span><span class="sxs-lookup"><span data-stu-id="96c7c-196">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="96c7c-197">На странице пользователя щелкните **"Политики",** а затем рядом с пакетом политики **выберите**"Изменить". </span><span class="sxs-lookup"><span data-stu-id="96c7c-197">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="96c7c-198">В области **назначения пакета политики** выберите пакет, который вы хотите назначить, и нажмите кнопку **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="96c7c-198">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="96c7c-199">Назначение пакета политики нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="96c7c-199">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="96c7c-200">В левой области навигации Центра администрирования Microsoft Teams перейдите к пакетам **политики,** а затем выберите пакет политики, который вы хотите назначить, щелкнув слева от его имени.</span><span class="sxs-lookup"><span data-stu-id="96c7c-200">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="96c7c-201">Щелкните **"Управление пользователями".**</span><span class="sxs-lookup"><span data-stu-id="96c7c-201">Click **Manage users**.</span></span>
3. <span data-ttu-id="96c7c-202">В области **Управление пользователями** выполните поиск по отображаемому имени или по имени пользователя, выберите имя и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="96c7c-202">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="96c7c-203">Повторите это действие для каждого пользователя, которого нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="96c7c-203">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="96c7c-204">Завершив добавление пользователей, нажмите кнопку **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="96c7c-204">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="96c7c-205">Назначение пакета политики группе</span><span class="sxs-lookup"><span data-stu-id="96c7c-205">Assign a policy package to a group</span></span>

<span data-ttu-id="96c7c-206">**Эта функция доступна в закрытой ознакомительной версии**</span><span class="sxs-lookup"><span data-stu-id="96c7c-206">**This feature is in private preview**</span></span>

<span data-ttu-id="96c7c-207">Назначение пакетов политики группам позволяет назначать несколько политик группе пользователей, например группе безопасности или группе рассылки.</span><span class="sxs-lookup"><span data-stu-id="96c7c-207">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="96c7c-208">Назначение политики распространяется на участников группы в соответствии с правилами очередности.</span><span class="sxs-lookup"><span data-stu-id="96c7c-208">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="96c7c-209">При добавлении или удалении участников группы, назначения политик для них обновляются соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="96c7c-209">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="96c7c-210">Этот способ рекомендуется для групп, включающих до 50 000 пользователей, но также подойдет и для больших групп.</span><span class="sxs-lookup"><span data-stu-id="96c7c-210">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="96c7c-211">Дополнительные сведения см. в статье [Назначение пакета политики группе](assign-policies.md#assign-a-policy-package-to-a-group).</span><span class="sxs-lookup"><span data-stu-id="96c7c-211">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="96c7c-212">Назначение пакета политики множеству (пакету) пользователей</span><span class="sxs-lookup"><span data-stu-id="96c7c-212">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="96c7c-213">Используйте назначение группового пакета политики, чтобы назначить пакет политики для множества пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="96c7c-213">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="96c7c-214">Используйте командлет [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation), чтобы отправить множество пользователей и пакет политики, который вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="96c7c-214">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="96c7c-215">Задания будут обрабатываться в фоновом режиме, а для каждого пакета будет создан идентификатор операции.</span><span class="sxs-lookup"><span data-stu-id="96c7c-215">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="96c7c-216">Пакет может содержать до 5 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="96c7c-216">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="96c7c-217">Можно указать пользователей по идентификатору объекта, UPN, адресу протокола SIP или электронной почты.</span><span class="sxs-lookup"><span data-stu-id="96c7c-217">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="96c7c-218">Дополнительные сведения см. в статье [Назначение пакета политики множеству пользователей](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span><span class="sxs-lookup"><span data-stu-id="96c7c-218">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="96c7c-219">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="96c7c-219">Troubleshooting</span></span>

<span data-ttu-id="96c7c-220">**При назначении пакета политики вы получаете сообщение об ошибке**</span><span class="sxs-lookup"><span data-stu-id="96c7c-220">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="96c7c-221">Это может произойти, если одна или несколько политик в пакете не были созданы или применены успешно.</span><span class="sxs-lookup"><span data-stu-id="96c7c-221">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="96c7c-222">Перенанаменуйте пакет политики для пользователей.</span><span class="sxs-lookup"><span data-stu-id="96c7c-222">Reassign the policy package to your users.</span></span> <span data-ttu-id="96c7c-223">Эта проблема обычно устраняется повторно.</span><span class="sxs-lookup"><span data-stu-id="96c7c-223">Retrying the operation typically fixes this issue.</span></span>

## <a name="related-topics"></a><span data-ttu-id="96c7c-224">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="96c7c-224">Related topics</span></span>

[<span data-ttu-id="96c7c-225">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="96c7c-225">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="96c7c-226">Пакеты политики Teams для администраторов EDU</span><span class="sxs-lookup"><span data-stu-id="96c7c-226">Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)

[<span data-ttu-id="96c7c-227">Пакеты политик Teams для здравоохранения</span><span class="sxs-lookup"><span data-stu-id="96c7c-227">Teams policy packages for healthcare</span></span>](policy-packages-healthcare.md)

[<span data-ttu-id="96c7c-228">Пакеты политики Teams для государственных органов</span><span class="sxs-lookup"><span data-stu-id="96c7c-228">Teams policy packages for government</span></span>](policy-packages-gov.md)
