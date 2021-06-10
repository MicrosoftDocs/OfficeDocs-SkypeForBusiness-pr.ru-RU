---
title: Управление пакетами политик в Microsoft Teams
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
ms.openlocfilehash: 63900f301a8b3a48a8c17c6278808cd52e2445da
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/07/2021
ms.locfileid: "52810178"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="5aec0-103">Управление пакетами политик в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5aec0-103">Manage policy packages in Microsoft Teams</span></span>

<span data-ttu-id="5aec0-104">Пакет политики в Microsoft Teams — это набор готовых политик и параметров политик, которые можно назначить пользователям с похожими ролями в организации.</span><span class="sxs-lookup"><span data-stu-id="5aec0-104">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="5aec0-105">Мы создали пакеты политик, которые упрощают, упрощают и обеспечивают единообразие при управлении политиками для групп пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="5aec0-105">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="5aec0-106">Вы можете использовать [пакеты политики,](#policy-packages-included-in-teams) включенные в Teams, или создать [собственные настраиваемые пакеты политики.](#custom-policy-packages)</span><span class="sxs-lookup"><span data-stu-id="5aec0-106">You can use the [policy packages included in Teams](#policy-packages-included-in-teams) or [create your own custom policy packages](#custom-policy-packages).</span></span>

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="Снимок экрана: страница пакетов политики в Центре администрирования":::

<span data-ttu-id="5aec0-108">Вы можете настроить параметры политик в пакете политики в соответствии с потребностями пользователей.</span><span class="sxs-lookup"><span data-stu-id="5aec0-108">You can customize the settings of the policies in a policy package to suit the needs of your users.</span></span> <span data-ttu-id="5aec0-109">При изменении параметров политик в пакете все пользователи, которым он назначен, получают обновленные параметры.</span><span class="sxs-lookup"><span data-stu-id="5aec0-109">When you change the settings of policies in a package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="5aec0-110">Пакеты политик можно управлять с помощью Microsoft Teams или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5aec0-110">You manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="5aec0-111">Для получения назначенного пользовательского пакета политик каждому пользователю будет необходима надстройка Advanced Communications.</span><span class="sxs-lookup"><span data-stu-id="5aec0-111">Each user will require the Advanced Communications add-on in order to receive a custom policy package assignment.</span></span> <span data-ttu-id="5aec0-112">Дополнительные сведения см. в статье [Надстройка Advanced Communications для Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).</span><span class="sxs-lookup"><span data-stu-id="5aec0-112">For more information, see [Advanced Communications add-on for Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="5aec0-113">Что такое пакет политики?</span><span class="sxs-lookup"><span data-stu-id="5aec0-113">What is a policy package?</span></span>

<span data-ttu-id="5aec0-114">Пакеты политик позволяют управлять Teams определенными функциями, которые вы хотите разрешить или ограничить для определенных наборов людей в организации.</span><span class="sxs-lookup"><span data-stu-id="5aec0-114">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="5aec0-115">Каждый пакет Teams предназначен для роли пользователя и содержит предопределяющую политику и параметры политики, которые поддерживают типичные для нее действия для совместной работы и связи.</span><span class="sxs-lookup"><span data-stu-id="5aec0-115">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="5aec0-116">Пакеты политик поддерживают следующие Teams политики:</span><span class="sxs-lookup"><span data-stu-id="5aec0-116">Policy packages support the following Teams policy types:</span></span>

- <span data-ttu-id="5aec0-117">Политика обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="5aec0-117">Messaging policy</span></span>
- <span data-ttu-id="5aec0-118">Политика собраний</span><span class="sxs-lookup"><span data-stu-id="5aec0-118">Meeting policy</span></span>
- <span data-ttu-id="5aec0-119">Политика настройки приложений</span><span class="sxs-lookup"><span data-stu-id="5aec0-119">App setup policy</span></span>
- <span data-ttu-id="5aec0-120">Политика звонков</span><span class="sxs-lookup"><span data-stu-id="5aec0-120">Calling policy</span></span>
- <span data-ttu-id="5aec0-121">Политика живых событий</span><span class="sxs-lookup"><span data-stu-id="5aec0-121">Live events policy</span></span>

## <a name="policy-packages-included-in-teams"></a><span data-ttu-id="5aec0-122">Пакеты политик, включенные в Teams</span><span class="sxs-lookup"><span data-stu-id="5aec0-122">Policy packages included in Teams</span></span>

<span data-ttu-id="5aec0-123">Teams настоящее время включены следующие пакеты политики.</span><span class="sxs-lookup"><span data-stu-id="5aec0-123">Teams currently includes the following policy packages.</span></span>

| <span data-ttu-id="5aec0-124">Имя пакета</span><span class="sxs-lookup"><span data-stu-id="5aec0-124">Package name</span></span> | <span data-ttu-id="5aec0-125">Описание</span><span class="sxs-lookup"><span data-stu-id="5aec0-125">Description</span></span> |
|---------|---------|
|<span data-ttu-id="5aec0-126">Образование (учащийся с более высоким образованием)</span><span class="sxs-lookup"><span data-stu-id="5aec0-126">Education (Higher education student)</span></span>    |<span data-ttu-id="5aec0-127">Создает набор политик и параметров политики, которые применяются к учащимся более высокого уровня.</span><span class="sxs-lookup"><span data-stu-id="5aec0-127">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="5aec0-128">Образование (учащийся основной школы)</span><span class="sxs-lookup"><span data-stu-id="5aec0-128">Education (Primary school student)</span></span>   |<span data-ttu-id="5aec0-129">Создает набор политик и параметров политики, которые применяются к основным учащимся.</span><span class="sxs-lookup"><span data-stu-id="5aec0-129">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="5aec0-130">Образование (учащийся дополнительного учебного заведения)</span><span class="sxs-lookup"><span data-stu-id="5aec0-130">Education (Secondary school student)</span></span>    |<span data-ttu-id="5aec0-131">Создает набор политик и параметров политики, которые применяются к дополнительным учащимся.</span><span class="sxs-lookup"><span data-stu-id="5aec0-131">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="5aec0-132">Образование (преподаватель)</span><span class="sxs-lookup"><span data-stu-id="5aec0-132">Education (Teacher)</span></span>    |<span data-ttu-id="5aec0-133">Создает набор политик и параметров политики, которые применяются к преподавателям.</span><span class="sxs-lookup"><span data-stu-id="5aec0-133">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="5aec0-134">Образование (преподаватель начальной школы, использующий дистанционное обучение)</span><span class="sxs-lookup"><span data-stu-id="5aec0-134">Education (Primary school teacher using remote learning)</span></span>    |<span data-ttu-id="5aec0-135">Создает набор политик, применимых к учителям начальных классов, для обеспечения максимальной безопасности и совместной работы учащихся при использовании дистанционного обучения.</span><span class="sxs-lookup"><span data-stu-id="5aec0-135">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="5aec0-136">Образование (учащийся начального учебного заведения, использующий дистанционное обучение)</span><span class="sxs-lookup"><span data-stu-id="5aec0-136">Education (Primary school student using remote learning)</span></span>    |<span data-ttu-id="5aec0-137">Создает набор политик, применимых к учащимся начальных классов, для обеспечения максимальной безопасности и совместной работы учащихся при использовании дистанционного обучения.</span><span class="sxs-lookup"><span data-stu-id="5aec0-137">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="5aec0-138">Диспетчер переднего звена</span><span class="sxs-lookup"><span data-stu-id="5aec0-138">Frontline manager</span></span> |<span data-ttu-id="5aec0-139">Создает набор политик и применяет эти параметры к руководителям frontline в организации.</span><span class="sxs-lookup"><span data-stu-id="5aec0-139">Creates a set of policies and applies those settings to Frontline managers in your organization.</span></span> |
|<span data-ttu-id="5aec0-140">Фронтальная сотрудница</span><span class="sxs-lookup"><span data-stu-id="5aec0-140">Frontline worker</span></span> |<span data-ttu-id="5aec0-141">Создает набор политик и применяет эти параметры к сотрудникам, работающим с frontline в организации.</span><span class="sxs-lookup"><span data-stu-id="5aec0-141">Creates a set of policies and applies those settings to Frontline workers in your organization.</span></span> |
|<span data-ttu-id="5aec0-142">Медицинский работник в учреждении здравоохранения</span><span class="sxs-lookup"><span data-stu-id="5aec0-142">Healthcare clinical worker</span></span>  |<span data-ttu-id="5aec0-143">Создает набор политик и параметров политик, предоставляющий медицинским работникам, таким как медсестры, старшие сестры, терапевты и социальные работники, полный доступ к чатам, звонкам, управлению сменами и собраниям.</span><span class="sxs-lookup"><span data-stu-id="5aec0-143">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="5aec0-144">Информационный работник в учреждении здравоохранения</span><span class="sxs-lookup"><span data-stu-id="5aec0-144">Healthcare information worker</span></span>  |<span data-ttu-id="5aec0-145">Создает набор политик и параметров политик, предоставляющий информационным сотрудникам, таким как ИТ-персонал, информационный персонал, финансовый персонал и сотрудники по обеспечению соответствия требованиям, полный доступ к чатам, звонкам и собраниям.</span><span class="sxs-lookup"><span data-stu-id="5aec0-145">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="5aec0-146">Палата для пациентов в учреждении здравоохранения</span><span class="sxs-lookup"><span data-stu-id="5aec0-146">Healthcare patient room</span></span>  |<span data-ttu-id="5aec0-147">Создает набор политик и параметров политик, применяемый к палатам для пациентов в медицинской организации.</span><span class="sxs-lookup"><span data-stu-id="5aec0-147">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|
|<span data-ttu-id="5aec0-148">Малый и средний бизнес (голосовая почта)</span><span class="sxs-lookup"><span data-stu-id="5aec0-148">Small and medium business user (Business Voice)</span></span> |<span data-ttu-id="5aec0-149">Создает политику настройки приложений, которая включает приложения для работы с деловыми голосами.</span><span class="sxs-lookup"><span data-stu-id="5aec0-149">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="5aec0-150">Малый и средний бизнес (без голосовой почты)</span><span class="sxs-lookup"><span data-stu-id="5aec0-150">Small and medium business user (without Business Voice)</span></span> |<span data-ttu-id="5aec0-151">Создает политику настройки приложений, релевантную для пользователей небольших и средних Teams (голосовая почта не для бизнеса).</span><span class="sxs-lookup"><span data-stu-id="5aec0-151">Creates an app setup policy relevant for a small and medium sized business Teams users (non-Business Voice experience).</span></span>
|<span data-ttu-id="5aec0-152">Сотрудник по обеспечению безопасности</span><span class="sxs-lookup"><span data-stu-id="5aec0-152">Public safety officer</span></span>   |<span data-ttu-id="5aec0-153">Создает набор политик и параметров политики, которые применяются к сотрудникам, которые работают с политикой безопасности в организации.</span><span class="sxs-lookup"><span data-stu-id="5aec0-153">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|

> [!NOTE]
> <span data-ttu-id="5aec0-154">Мы добавим дополнительные пакеты политик в будущих выпусках Teams, поэтому ознакомьтесь с самыми последние сведениями.</span><span class="sxs-lookup"><span data-stu-id="5aec0-154">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="5aec0-155">Каждой отдельной политике присваивается имя пакета политики, чтобы легко определять политики, связанные с пакетом.</span><span class="sxs-lookup"><span data-stu-id="5aec0-155">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="5aec0-156">Например, при назначении пакета политики для образования (преподавателя) преподавателям в учебном замещаемом пакете для каждой политики создается Education_Teacher для каждой политики в пакете.</span><span class="sxs-lookup"><span data-stu-id="5aec0-156">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![Снимок экрана: пакет политики для образования (преподавателя)](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a><span data-ttu-id="5aec0-158">Настраиваемые пакеты политик</span><span class="sxs-lookup"><span data-stu-id="5aec0-158">Custom policy packages</span></span>

<span data-ttu-id="5aec0-159">**Настраиваемые пакеты политик пока недоступны для облако сообщества для государственных организаций (GCC)**</span><span class="sxs-lookup"><span data-stu-id="5aec0-159">**Custom policy packages is not yet available for the Government Community Cloud (GCC)**</span></span>

<span data-ttu-id="5aec0-160">Настраиваемые пакеты политик можно объединить в пакет собственные политики для пользователей с похожими ролями в организации.</span><span class="sxs-lookup"><span data-stu-id="5aec0-160">Custom policy packages let you bundle your own set of policies for users with similar roles in you organization.</span></span> <span data-ttu-id="5aec0-161">Создайте собственные пакеты политик, добавив необходимые типы политик и политики.</span><span class="sxs-lookup"><span data-stu-id="5aec0-161">Create your own policy packages by adding the policy types and policies that you need.</span></span>

<span data-ttu-id="5aec0-162">Чтобы создать новый пакет настраиваемой политики:</span><span class="sxs-lookup"><span data-stu-id="5aec0-162">To create a new custom policy package:</span></span>

1. <span data-ttu-id="5aec0-163">В левой области навигации Центра администрирования Microsoft Teams выберите **Пакеты** политики и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="5aec0-163">In the left navigation of the Microsoft Teams admin center,  select **Policy packages**, and then click **Add**.</span></span>

    :::image type="content" source="media/policy-packages-add.png" alt-text="Снимок экрана: кнопка "Добавить" на странице пакетов политики в Центре администрирования":::

2. <span data-ttu-id="5aec0-165">Введите имя и описание пакета.</span><span class="sxs-lookup"><span data-stu-id="5aec0-165">Enter a name and description for your package.</span></span>

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="Снимок экрана: добавление нового пакета настраиваемой политики":::

3. <span data-ttu-id="5aec0-167">Выберите типы политик и имена политик, которые нужно включить в пакет.</span><span class="sxs-lookup"><span data-stu-id="5aec0-167">Select the policy types and policy names to include in the package.</span></span>

4. <span data-ttu-id="5aec0-168">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="5aec0-168">Click **Save**.</span></span>

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="5aec0-169">Использование пакетов политики</span><span class="sxs-lookup"><span data-stu-id="5aec0-169">How to use policy packages</span></span>

<span data-ttu-id="5aec0-170">Ниже описано, как использовать пакеты политик в организации.</span><span class="sxs-lookup"><span data-stu-id="5aec0-170">The following outlines how to use policy packages in your organization.</span></span>

![Общие сведения об использовании пакетов политик](media/manage-policy-packages-overview.png)

- <span data-ttu-id="5aec0-172">**[Просмотр.](#view-the-settings-of-a-policy-in-a-policy-package)** Просмотр политик в пакете политики.</span><span class="sxs-lookup"><span data-stu-id="5aec0-172">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the policies in a policy package.</span></span> <span data-ttu-id="5aec0-173">Затем перед назначением пакета необходимо просмотреть параметры каждой политики в пакете.</span><span class="sxs-lookup"><span data-stu-id="5aec0-173">Then, view the settings of each policy in a package before you assign the package.</span></span> <span data-ttu-id="5aec0-174">Убедитесь, что вы понимаете каждый из параметров.</span><span class="sxs-lookup"><span data-stu-id="5aec0-174">Make sure that you understand each setting.</span></span> <span data-ttu-id="5aec0-175">Решите, подходят ли готовые значения для вашей организации или нужно изменить их на более строгие или менее строгие в зависимости от потребностей организации.</span><span class="sxs-lookup"><span data-stu-id="5aec0-175">Decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="5aec0-176">При удалении политики вы по-прежнему сможете просматривать параметры, но не сможете изменить их.</span><span class="sxs-lookup"><span data-stu-id="5aec0-176">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="5aec0-177">Удаленная политика создается повторно с заранее задав пакет политики.</span><span class="sxs-lookup"><span data-stu-id="5aec0-177">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="5aec0-178">**[Настройка.](#customize-policies-in-a-policy-package)** Настройте параметры политик в пакете политики в нужном для организации месте.</span><span class="sxs-lookup"><span data-stu-id="5aec0-178">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span>

- <span data-ttu-id="5aec0-179">**[Назначить:](#assign-a-policy-package)** назначьте пакет политики пользователям.</span><span class="sxs-lookup"><span data-stu-id="5aec0-179">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span>  

> [!NOTE]
> <span data-ttu-id="5aec0-180">Вы также можете изменить параметры политик в пакете политики после назначения пакета.</span><span class="sxs-lookup"><span data-stu-id="5aec0-180">You can also change the settings of policies in a policy package after you assign a package.</span></span> <span data-ttu-id="5aec0-181">Изменения, внесенные в параметры политики, автоматически применяются к пользователям, которым назначен пакет.</span><span class="sxs-lookup"><span data-stu-id="5aec0-181">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="5aec0-182">Ниже вы можете просмотреть, назначить и настроить пакеты политики в центре Microsoft Teams администрирования.</span><span class="sxs-lookup"><span data-stu-id="5aec0-182">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="5aec0-183">Просмотр параметров политики в пакете политики</span><span class="sxs-lookup"><span data-stu-id="5aec0-183">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="5aec0-184">В левой области навигации Центра администрирования Microsoft Teams выберите Пакеты политики **,** а затем выберите пакет политики, щелкнув слева от имени пакета.</span><span class="sxs-lookup"><span data-stu-id="5aec0-184">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>

2. <span data-ttu-id="5aec0-185">Выберите политику, которая вы хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="5aec0-185">Click the policy you want to view.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="5aec0-186">Настройка политик в пакете политики</span><span class="sxs-lookup"><span data-stu-id="5aec0-186">Customize policies in a policy package</span></span>

<span data-ttu-id="5aec0-187">Вы можете изменить параметры политики  на странице Пакеты политики или непосредственно на странице политики в центре администрирования Microsoft Teams политики.</span><span class="sxs-lookup"><span data-stu-id="5aec0-187">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="5aec0-188">В левой области навигации Центра Microsoft Teams администрирования сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="5aec0-188">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="5aec0-189">Щелкните **Пакеты** политики и выберите пакет политики, щелкнув слева от его имени.</span><span class="sxs-lookup"><span data-stu-id="5aec0-189">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="5aec0-190">Выберите тип политики.</span><span class="sxs-lookup"><span data-stu-id="5aec0-190">Click the policy type.</span></span>  <span data-ttu-id="5aec0-191">Например, щелкните **Политики обмена сообщениями**.</span><span class="sxs-lookup"><span data-stu-id="5aec0-191">For example, click **Messaging policies**.</span></span>

2. <span data-ttu-id="5aec0-192">Выберите политику, которая вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="5aec0-192">Select the policy you want to edit.</span></span> <span data-ttu-id="5aec0-193">Политики, связанные с пакетом политики, имеют то же имя, что и пакет политики.</span><span class="sxs-lookup"><span data-stu-id="5aec0-193">Policies that are linked to a policy package have the same name as the policy package.</span></span>

3. <span data-ttu-id="5aec0-194">Внести нужные изменения и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="5aec0-194">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="5aec0-195">Назначение пакета политики</span><span class="sxs-lookup"><span data-stu-id="5aec0-195">Assign a policy package</span></span>

<span data-ttu-id="5aec0-196">Пакет политики можно назначить отдельному пользователю, группе или группе пользователей.</span><span class="sxs-lookup"><span data-stu-id="5aec0-196">You can assign a policy package to an individual user, a group, or a batch of users.</span></span> <span data-ttu-id="5aec0-197">Дополнительные сведения о назначении пакетов политики см. в этой [теме.](assign-policy-packages.md)</span><span class="sxs-lookup"><span data-stu-id="5aec0-197">For more information on how to assign policy packages, see [Assign policy packages to users and groups](assign-policy-packages.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="5aec0-198">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="5aec0-198">Related topics</span></span>

- [<span data-ttu-id="5aec0-199">Назначение пакетов политики</span><span class="sxs-lookup"><span data-stu-id="5aec0-199">Assign policy packages</span></span>](assign-policy-packages.md)
- [<span data-ttu-id="5aec0-200">Teams пакеты политик для администраторов EDU</span><span class="sxs-lookup"><span data-stu-id="5aec0-200">Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)
- [<span data-ttu-id="5aec0-201">Пакеты политик Teams для здравоохранения</span><span class="sxs-lookup"><span data-stu-id="5aec0-201">Teams policy packages for healthcare</span></span>](policy-packages-healthcare.md)
- [<span data-ttu-id="5aec0-202">Teams пакеты политик для государственных органов</span><span class="sxs-lookup"><span data-stu-id="5aec0-202">Teams policy packages for government</span></span>](policy-packages-gov.md)
