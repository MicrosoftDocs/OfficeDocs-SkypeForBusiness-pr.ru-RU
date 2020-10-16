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
ms.openlocfilehash: 140b67ae8df01d29b8e6d37c6fe1a36afebbd949
ms.sourcegitcommit: 8a345ca9a8ddc6a84f9e270ab55f1b28f6ba49c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48488390"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="7be30-103">Управление пакетами политик в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7be30-103">Manage policy packages in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="7be30-104">Одна из функций, описанных в этой статье, [пользовательские пакеты политики](#custom-policy-packages), в настоящее время находится в частном предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="7be30-104">One of the features discussed in this article, [custom policy packages](#custom-policy-packages), is currently in private preview.</span></span>

<span data-ttu-id="7be30-105">Пакет политики в Microsoft Teams — это набор предопределенных политик и параметров политики, которые можно назначить пользователям, имеющим аналогичные роли в Организации.</span><span class="sxs-lookup"><span data-stu-id="7be30-105">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="7be30-106">Мы создали пакеты политик для упрощения, упрощения и обеспечения согласованности при управлении политиками для групп пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="7be30-106">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="7be30-107">Вы можете использовать [пакеты политик, включенные в Teams](#policy-packages-included-in-teams) , или [создать собственные пакеты политик](#custom-policy-packages) (в частном предварительной версии).</span><span class="sxs-lookup"><span data-stu-id="7be30-107">You can use the [policy packages included in Teams](#policy-packages-included-in-teams) or [create your own custom policy packages](#custom-policy-packages) (in private preview).</span></span>

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="Снимок экрана: страница "пакеты политики" в центре администрирования":::

<span data-ttu-id="7be30-109">Вы можете настроить параметры политик в пакете политики таким образом, чтобы они соответствовали требованиям пользователей.</span><span class="sxs-lookup"><span data-stu-id="7be30-109">You can customize the settings of the policies in a policy package to suit the needs of your users.</span></span> <span data-ttu-id="7be30-110">При изменении параметров политик в пакете все пользователи, которым назначен этот пакет, получают обновленные параметры.</span><span class="sxs-lookup"><span data-stu-id="7be30-110">When you change the settings of policies in a package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="7be30-111">Управление пакетами политики осуществляется с помощью центра администрирования Microsoft Teams или оболочки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7be30-111">You manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="7be30-112">Что такое пакет политики?</span><span class="sxs-lookup"><span data-stu-id="7be30-112">What is a policy package?</span></span>

<span data-ttu-id="7be30-113">Пакеты политик позволяют управлять функциональными возможностями, которые вы хотите разрешить или ограничить для определенных наборов пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="7be30-113">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="7be30-114">Каждый пакет политики в Teams разработан вокруг роли пользователя и включает стандартные политики и параметры политики, которые поддерживают типичные задачи совместной работы и взаимодействия, которые обычно используются для этой роли.</span><span class="sxs-lookup"><span data-stu-id="7be30-114">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="7be30-115">Пакеты политик поддерживают следующие типы политик teams:</span><span class="sxs-lookup"><span data-stu-id="7be30-115">Policy packages support the following Teams policy types:</span></span>

- <span data-ttu-id="7be30-116">Политика обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="7be30-116">Messaging policy</span></span>
- <span data-ttu-id="7be30-117">Политика встречи</span><span class="sxs-lookup"><span data-stu-id="7be30-117">Meeting policy</span></span>
- <span data-ttu-id="7be30-118">Политика настройки приложения</span><span class="sxs-lookup"><span data-stu-id="7be30-118">App setup policy</span></span>
- <span data-ttu-id="7be30-119">Политика звонков</span><span class="sxs-lookup"><span data-stu-id="7be30-119">Calling policy</span></span>
- <span data-ttu-id="7be30-120">Политика живых событий</span><span class="sxs-lookup"><span data-stu-id="7be30-120">Live events policy</span></span>

## <a name="policy-packages-included-in-teams"></a><span data-ttu-id="7be30-121">Пакеты политики, включенные в Teams</span><span class="sxs-lookup"><span data-stu-id="7be30-121">Policy packages included in Teams</span></span>

<span data-ttu-id="7be30-122">В настоящее время команды включают следующие пакеты политик.</span><span class="sxs-lookup"><span data-stu-id="7be30-122">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="7be30-123">**Имя пакета**</span><span class="sxs-lookup"><span data-stu-id="7be30-123">**Package name**</span></span>  |<span data-ttu-id="7be30-124">**Описание**</span><span class="sxs-lookup"><span data-stu-id="7be30-124">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="7be30-125">Образование (более высокий образовательный учащийся)</span><span class="sxs-lookup"><span data-stu-id="7be30-125">Education (Higher education student)</span></span>    |<span data-ttu-id="7be30-126">Создает набор политик и параметров политики, которые применяются для более производительных учебных учащихся.</span><span class="sxs-lookup"><span data-stu-id="7be30-126">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="7be30-127">Образовательные учреждения (учебный учащийся)</span><span class="sxs-lookup"><span data-stu-id="7be30-127">Education (Primary school student)</span></span>   |<span data-ttu-id="7be30-128">Создает набор политик и параметров политики, которые применяются к основным учащимся.</span><span class="sxs-lookup"><span data-stu-id="7be30-128">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="7be30-129">Образование (дополнительный учебный учащийся)</span><span class="sxs-lookup"><span data-stu-id="7be30-129">Education (Secondary school student)</span></span>    |<span data-ttu-id="7be30-130">Создает набор политик и параметров политики, которые применяются к дополнительным учащимся.</span><span class="sxs-lookup"><span data-stu-id="7be30-130">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="7be30-131">Образование (преподаватель)</span><span class="sxs-lookup"><span data-stu-id="7be30-131">Education (Teacher)</span></span>    |<span data-ttu-id="7be30-132">Создает набор политик и параметров политики, которые применяются для преподавателей.</span><span class="sxs-lookup"><span data-stu-id="7be30-132">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="7be30-133">Образование (основной преподаватель учебного заведения, использующий удаленное обучение)</span><span class="sxs-lookup"><span data-stu-id="7be30-133">Education (Primary school teacher using remote learning)</span></span>    |<span data-ttu-id="7be30-134">Создает набор политик, применимых к учителям начальных классов, для обеспечения максимальной безопасности и совместной работы учащихся при использовании дистанционного обучения.</span><span class="sxs-lookup"><span data-stu-id="7be30-134">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="7be30-135">Образование (учебный учащийся с удаленным обучением)</span><span class="sxs-lookup"><span data-stu-id="7be30-135">Education (Primary school student using remote learning)</span></span>    |<span data-ttu-id="7be30-136">Создает набор политик, применимых к учащимся начальных классов, для обеспечения максимальной безопасности и совместной работы учащихся при использовании дистанционного обучения.</span><span class="sxs-lookup"><span data-stu-id="7be30-136">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="7be30-137">Менеджер Firstline</span><span class="sxs-lookup"><span data-stu-id="7be30-137">Firstline manager</span></span> |<span data-ttu-id="7be30-138">Создает набор политик и применяет эти параметры для руководителей Firstline в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="7be30-138">Creates a set of policies and applies those settings to Firstline Managers in your organization.</span></span> |
|<span data-ttu-id="7be30-139">Firstline рабочий процесс</span><span class="sxs-lookup"><span data-stu-id="7be30-139">Firstline worker</span></span> |<span data-ttu-id="7be30-140">Создает набор политик и применяет эти параметры для Firstlineных сотрудников в Организации.</span><span class="sxs-lookup"><span data-stu-id="7be30-140">Creates a set of policies and applies those settings to Firstline Workers in your organization.</span></span> |
|<span data-ttu-id="7be30-141">Сотрудник по здравоохранение Clinical</span><span class="sxs-lookup"><span data-stu-id="7be30-141">Healthcare clinical worker</span></span>  |<span data-ttu-id="7be30-142">Создает набор политик и параметров политики, которые предоставляют Clinical сотрудникам, таким как зарегистрированные Nurses, начисление Nurses, врача и социальных работников, полный доступ к разговору, звонку, управлению сменой и собраниям.</span><span class="sxs-lookup"><span data-stu-id="7be30-142">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="7be30-143">Сотрудник "сведения о здравоохранение"</span><span class="sxs-lookup"><span data-stu-id="7be30-143">Healthcare information worker</span></span>  |<span data-ttu-id="7be30-144">Создание набора политик и параметров политики, предназначаемых сотрудникам, таким как ИТ-персонал, informatics сотрудников, финансовых сотрудников и руководителей соответствия требованиям, полного доступа к разговору, звонку и собранию.</span><span class="sxs-lookup"><span data-stu-id="7be30-144">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="7be30-145">Комната пациента на здравоохранение</span><span class="sxs-lookup"><span data-stu-id="7be30-145">Healthcare patient room</span></span>  |<span data-ttu-id="7be30-146">Создает набор политик и параметров политики, которые применяются к комнатам пациентам в вашей организации здравоохранения.</span><span class="sxs-lookup"><span data-stu-id="7be30-146">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|
|<span data-ttu-id="7be30-147">Малый и средний бизнес-пользователь (деловой голосовой звонок)</span><span class="sxs-lookup"><span data-stu-id="7be30-147">Small and medium business user (Business Voice)</span></span> |<span data-ttu-id="7be30-148">Создание политики настройки приложения, включающей приложения для голосового интерфейса для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7be30-148">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="7be30-149">Малый и средний бизнес-пользователь (без деловой голосовой связи)</span><span class="sxs-lookup"><span data-stu-id="7be30-149">Small and medium business user (without Business Voice)</span></span> |<span data-ttu-id="7be30-150">Создание политики настройки приложения, относящейся к малому и среднему бизнес-группам пользователей (для некоммерческой голосовой связи).</span><span class="sxs-lookup"><span data-stu-id="7be30-150">Creates an app setup policy relevant for a small and medium sized business Teams users (non-Business Voice experience).</span></span>
|<span data-ttu-id="7be30-151">Открытый директор по безопасности</span><span class="sxs-lookup"><span data-stu-id="7be30-151">Public safety officer</span></span>   |<span data-ttu-id="7be30-152">Создает набор политик и параметров политики, которые применяются для руководителей общедоступной безопасности в Организации.</span><span class="sxs-lookup"><span data-stu-id="7be30-152">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|

> [!NOTE]
> <span data-ttu-id="7be30-153">В будущих выпусках Teams мы добавим дополнительные пакеты политик, поэтому ознакомьтесь с самыми актуальными сведениями.</span><span class="sxs-lookup"><span data-stu-id="7be30-153">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="7be30-154">Каждой отдельной политике назначается имя пакета политики, что позволяет легко определять политики, связанные с пакетом политики.</span><span class="sxs-lookup"><span data-stu-id="7be30-154">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="7be30-155">Например, если назначить пакету политики образования для преподавателей в учебном заведении, для каждой политики в пакете будет создана политика с именем Education_Teacher.</span><span class="sxs-lookup"><span data-stu-id="7be30-155">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![Снимок экрана: пакет политики "образование" (для преподавателей)](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a><span data-ttu-id="7be30-157">Пользовательские пакеты политик</span><span class="sxs-lookup"><span data-stu-id="7be30-157">Custom policy packages</span></span>

<span data-ttu-id="7be30-158">**Эта функция доступна в частном предварительной версии**</span><span class="sxs-lookup"><span data-stu-id="7be30-158">**This feature is in private preview**</span></span>

<span data-ttu-id="7be30-159">Пользовательские пакеты политик позволяют объединять собственные наборы политик для пользователей с аналогичными ролями в Организации.</span><span class="sxs-lookup"><span data-stu-id="7be30-159">Custom policy packages let you bundle your own set of policies for users with similar roles in you organization.</span></span> <span data-ttu-id="7be30-160">Создайте собственные пакеты политики, добавив необходимые типы политик и политики.</span><span class="sxs-lookup"><span data-stu-id="7be30-160">Create your own policy packages by adding the policy types and policies that you need.</span></span>

<span data-ttu-id="7be30-161">Чтобы создать настраиваемый пакет политики, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="7be30-161">To create a new custom policy package:</span></span>

1. <span data-ttu-id="7be30-162">В левой области навигации центра администрирования Microsoft Teams выберите пункт **пакеты политики**и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="7be30-162">In the left navigation of the Microsoft Teams admin center,  select **Policy packages**, and then click **Add**.</span></span>
    :::image type="content" source="media/policy-packages-add.png" alt-text="Снимок экрана: кнопка "Добавить" на странице "пакеты политики" в центре администрирования":::
2. <span data-ttu-id="7be30-164">Введите имя и описание пакета.</span><span class="sxs-lookup"><span data-stu-id="7be30-164">Enter a name and description for your package.</span></span>
    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="Снимок экрана: Добавление нового настраиваемого пакета политики":::
3. <span data-ttu-id="7be30-166">Выберите типы политик и имена политик, которые нужно включить в пакет.</span><span class="sxs-lookup"><span data-stu-id="7be30-166">Select the policy types and policy names to include in the package.</span></span>
4. <span data-ttu-id="7be30-167">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7be30-167">Click **Save**.</span></span>

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="7be30-168">Использование пакетов политик</span><span class="sxs-lookup"><span data-stu-id="7be30-168">How to use policy packages</span></span>

<span data-ttu-id="7be30-169">Ниже показано, как использовать пакеты политик в Организации.</span><span class="sxs-lookup"><span data-stu-id="7be30-169">The following outlines how to use policy packages in your organization.</span></span>

![Общие сведения об использовании пакетов политик](media/manage-policy-packages-overview.png)

- <span data-ttu-id="7be30-171">**[Представление](#view-the-settings-of-a-policy-in-a-policy-package)**: Просмотр политик в пакете политики.</span><span class="sxs-lookup"><span data-stu-id="7be30-171">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the policies in a policy package.</span></span> <span data-ttu-id="7be30-172">Затем просмотрите параметры каждой политики в пакете перед тем, как назначить пакет.</span><span class="sxs-lookup"><span data-stu-id="7be30-172">Then, view the settings of each policy in a package before you assign the package.</span></span> <span data-ttu-id="7be30-173">Убедитесь, что вы понимаете каждый из параметров.</span><span class="sxs-lookup"><span data-stu-id="7be30-173">Make sure that you understand each setting.</span></span> <span data-ttu-id="7be30-174">Определите, являются ли предопределенные значения подходящими для вашей организации, или измените их так, чтобы они были более строгими или Lenient в зависимости от потребностей Организации.</span><span class="sxs-lookup"><span data-stu-id="7be30-174">Decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="7be30-175">Если политика удалена, вы по-прежнему можете просматривать параметры, но вы не сможете изменить параметры.</span><span class="sxs-lookup"><span data-stu-id="7be30-175">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="7be30-176">Удаленная политика создается повторно с параметрами, предопределенными при назначении пакета политики.</span><span class="sxs-lookup"><span data-stu-id="7be30-176">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="7be30-177">**[Настройка](#customize-policies-in-a-policy-package)**: Настройка параметров политик в пакете политики в соответствии с потребностями Организации.</span><span class="sxs-lookup"><span data-stu-id="7be30-177">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span>

- <span data-ttu-id="7be30-178">**[Назначение](#assign-a-policy-package)**: назначение пакета политики пользователям.</span><span class="sxs-lookup"><span data-stu-id="7be30-178">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span>  

> [!NOTE]
> <span data-ttu-id="7be30-179">Вы также можете изменить параметры политик в пакете политики после назначения пакета.</span><span class="sxs-lookup"><span data-stu-id="7be30-179">You can also change the settings of policies in a policy package after you assign a package.</span></span> <span data-ttu-id="7be30-180">Любые изменения, внесенные в параметры политики, автоматически применяются к пользователям, которым назначен пакет.</span><span class="sxs-lookup"><span data-stu-id="7be30-180">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="7be30-181">Ниже описаны действия, которые необходимо выполнить, чтобы просмотреть, назначить и настроить пакеты политики в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7be30-181">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="7be30-182">Просмотр параметров политики в пакете политики</span><span class="sxs-lookup"><span data-stu-id="7be30-182">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="7be30-183">В левой области навигации центра администрирования Microsoft Teams выберите пункт **пакеты политики**, а затем выберите пакет политики, щелкнув слева от имени пакета.</span><span class="sxs-lookup"><span data-stu-id="7be30-183">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="7be30-184">Выберите политику, которую вы хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="7be30-184">Click the policy you want to view.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="7be30-185">Настройка политик в пакете политики</span><span class="sxs-lookup"><span data-stu-id="7be30-185">Customize policies in a policy package</span></span>

<span data-ttu-id="7be30-186">Вы можете изменить параметры политики на странице **пакеты политики** или непосредственно на страницу политики в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7be30-186">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="7be30-187">В левой области навигации центра администрирования Microsoft Teams выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="7be30-187">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="7be30-188">Щелкните **пакеты политики**, а затем выберите пакет политики, щелкнув слева от его имени.</span><span class="sxs-lookup"><span data-stu-id="7be30-188">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="7be30-189">Выберите тип политики.</span><span class="sxs-lookup"><span data-stu-id="7be30-189">Click the policy type.</span></span>  <span data-ttu-id="7be30-190">Например, выберите **политики обмена сообщениями**.</span><span class="sxs-lookup"><span data-stu-id="7be30-190">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="7be30-191">Выберите политику, которую вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="7be30-191">Select the policy you want to edit.</span></span> <span data-ttu-id="7be30-192">Политики, связанные с пакетом политики, имеют то же имя, что и пакет политики.</span><span class="sxs-lookup"><span data-stu-id="7be30-192">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="7be30-193">Внесите нужные изменения и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7be30-193">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="7be30-194">Назначение пакета политики</span><span class="sxs-lookup"><span data-stu-id="7be30-194">Assign a policy package</span></span>

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="7be30-195">Назначение пакета политики для одного пользователя</span><span class="sxs-lookup"><span data-stu-id="7be30-195">Assign a policy package to one user</span></span>

1. <span data-ttu-id="7be30-196">В Центре администрирования Microsoft Teams в области навигации слева перейдите в раздел **Пользователи**, затем щелкните пользователя.</span><span class="sxs-lookup"><span data-stu-id="7be30-196">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="7be30-197">На странице пользователя нажмите **политики**, а затем рядом с пунктом **Политика**выберите команду **изменить**.</span><span class="sxs-lookup"><span data-stu-id="7be30-197">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="7be30-198">В области **Назначение пакета политики** выберите пакет, который вы хотите назначить, и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7be30-198">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="7be30-199">Назначение пакета политики нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="7be30-199">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="7be30-200">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел **пакеты политики**, а затем выберите пакет политики, который вы хотите назначить, щелкнув слева от его имени.</span><span class="sxs-lookup"><span data-stu-id="7be30-200">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="7be30-201">Щелкните **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="7be30-201">Click **Manage users**.</span></span>
3. <span data-ttu-id="7be30-202">В области **Управление пользователями** выполните поиск по отображаемому имени или по имени пользователя, выберите имя и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="7be30-202">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="7be30-203">Повторите это действие для каждого пользователя, которого нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="7be30-203">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="7be30-204">Завершив добавление пользователей, нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7be30-204">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="7be30-205">Назначение пакета политики большому набору (пакету) пользователей</span><span class="sxs-lookup"><span data-stu-id="7be30-205">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="7be30-206">Назначение пакета политики для большого количества пользователей одновременно с помощью задания пакетной политики.</span><span class="sxs-lookup"><span data-stu-id="7be30-206">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="7be30-207">С помощью командлета [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) вы можете отправить пакет пользователей и пакет политики, который вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="7be30-207">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="7be30-208">Назначения обрабатываются как фоновая операция, и для каждого пакета создается идентификатор операции.</span><span class="sxs-lookup"><span data-stu-id="7be30-208">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="7be30-209">Пакет может содержать до 5 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="7be30-209">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="7be30-210">Вы можете указать пользователей, указав их идентификатор (UPN), адрес SIP или адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="7be30-210">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="7be30-211">Дополнительные сведения можно найти в разделе [Назначение пакета политики пакету пользователей](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span><span class="sxs-lookup"><span data-stu-id="7be30-211">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="7be30-212">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="7be30-212">Troubleshooting</span></span>

<span data-ttu-id="7be30-213">**При назначении пакета политики появляется сообщение об ошибке**</span><span class="sxs-lookup"><span data-stu-id="7be30-213">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="7be30-214">Это может произойти, если одна или несколько политик в пакете не были успешно созданы или применены.</span><span class="sxs-lookup"><span data-stu-id="7be30-214">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="7be30-215">Переназначение пакета политики пользователям.</span><span class="sxs-lookup"><span data-stu-id="7be30-215">Reassign the policy package to your users.</span></span> <span data-ttu-id="7be30-216">Повторное выполнение операции обычно решает эту проблему.</span><span class="sxs-lookup"><span data-stu-id="7be30-216">Retrying the operation typically fixes this issue.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7be30-217">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="7be30-217">Related topics</span></span>

[<span data-ttu-id="7be30-218">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="7be30-218">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="7be30-219">Пакеты политики Teams для администраторов EDU</span><span class="sxs-lookup"><span data-stu-id="7be30-219">Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)

[<span data-ttu-id="7be30-220">Пакеты политики Teams для здравоохранения</span><span class="sxs-lookup"><span data-stu-id="7be30-220">Teams policy packages for healthcare</span></span>](policy-packages-healthcare.md)

[<span data-ttu-id="7be30-221">Пакеты политики Teams для государственных организаций</span><span class="sxs-lookup"><span data-stu-id="7be30-221">Teams policy packages for government</span></span>](policy-packages-gov.md)
