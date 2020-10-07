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
ms.openlocfilehash: 866183442d21ad91a83f3e9460ccd257902a0972
ms.sourcegitcommit: f4f5ad1391b472d64390180c81c2680f011a8a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2020
ms.locfileid: "48370578"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="1b03e-103">Управление пакетами политик в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1b03e-103">Manage policy packages in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="1b03e-104">Одна из функций, описанных в этой статье, — [пользовательские пакеты политик](#custom-policy-packages), еще не выпущены.</span><span class="sxs-lookup"><span data-stu-id="1b03e-104">One of the features discussed in this article, [custom policy packages](#custom-policy-packages), hasn't been released yet.</span></span> <span data-ttu-id="1b03e-105">Скоро это будет быть закрыто для предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="1b03e-105">It's coming soon to private preview.</span></span>

<span data-ttu-id="1b03e-106">Пакет политики в Microsoft Teams — это набор предопределенных политик и параметров политики, которые можно назначить пользователям, имеющим аналогичные роли в Организации.</span><span class="sxs-lookup"><span data-stu-id="1b03e-106">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="1b03e-107">Мы создали пакеты политик для упрощения, упрощения и обеспечения согласованности при управлении политиками для групп пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="1b03e-107">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="1b03e-108">Вы можете использовать [пакеты политик, включенные в Teams](#policy-packages-included-in-teams) , или [создать собственные пакеты политик](#custom-policy-packages) (в частном предварительной версии).</span><span class="sxs-lookup"><span data-stu-id="1b03e-108">You can use the [policy packages included in Teams](#policy-packages-included-in-teams) or [create your own custom policy packages](#custom-policy-packages) (in private preview).</span></span>

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="Снимок экрана: страница "пакеты политики" в центре администрирования":::

<span data-ttu-id="1b03e-110">Вы можете настроить параметры политик в пакете политики таким образом, чтобы они соответствовали требованиям пользователей.</span><span class="sxs-lookup"><span data-stu-id="1b03e-110">You can customize the settings of the policies in a policy package to suit the needs of your users.</span></span> <span data-ttu-id="1b03e-111">При изменении параметров политик в пакете все пользователи, которым назначен этот пакет, получают обновленные параметры.</span><span class="sxs-lookup"><span data-stu-id="1b03e-111">When you change the settings of policies in a package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="1b03e-112">Управление пакетами политики осуществляется с помощью центра администрирования Microsoft Teams или оболочки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1b03e-112">You manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="1b03e-113">Что такое пакет политики?</span><span class="sxs-lookup"><span data-stu-id="1b03e-113">What is a policy package?</span></span>

<span data-ttu-id="1b03e-114">Пакеты политик позволяют управлять функциональными возможностями, которые вы хотите разрешить или ограничить для определенных наборов пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="1b03e-114">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="1b03e-115">Каждый пакет политики в Teams разработан вокруг роли пользователя и включает стандартные политики и параметры политики, которые поддерживают типичные задачи совместной работы и взаимодействия, которые обычно используются для этой роли.</span><span class="sxs-lookup"><span data-stu-id="1b03e-115">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="1b03e-116">Пакеты политик поддерживают следующие типы политик teams:</span><span class="sxs-lookup"><span data-stu-id="1b03e-116">Policy packages support the following Teams policy types:</span></span>

- <span data-ttu-id="1b03e-117">Политика обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="1b03e-117">Messaging policy</span></span>
- <span data-ttu-id="1b03e-118">Политика встречи</span><span class="sxs-lookup"><span data-stu-id="1b03e-118">Meeting policy</span></span>
- <span data-ttu-id="1b03e-119">Политика настройки приложения</span><span class="sxs-lookup"><span data-stu-id="1b03e-119">App setup policy</span></span>
- <span data-ttu-id="1b03e-120">Политика звонков</span><span class="sxs-lookup"><span data-stu-id="1b03e-120">Calling policy</span></span>
- <span data-ttu-id="1b03e-121">Политика живых событий</span><span class="sxs-lookup"><span data-stu-id="1b03e-121">Live events policy</span></span>

## <a name="policy-packages-included-in-teams"></a><span data-ttu-id="1b03e-122">Пакеты политики, включенные в Teams</span><span class="sxs-lookup"><span data-stu-id="1b03e-122">Policy packages included in Teams</span></span>

<span data-ttu-id="1b03e-123">В настоящее время команды включают следующие пакеты политик.</span><span class="sxs-lookup"><span data-stu-id="1b03e-123">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="1b03e-124">**Имя пакета**</span><span class="sxs-lookup"><span data-stu-id="1b03e-124">**Package name**</span></span>  |<span data-ttu-id="1b03e-125">**Описание**</span><span class="sxs-lookup"><span data-stu-id="1b03e-125">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="1b03e-126">Образование (более высокий образовательный учащийся)</span><span class="sxs-lookup"><span data-stu-id="1b03e-126">Education (Higher education student)</span></span>    |<span data-ttu-id="1b03e-127">Создает набор политик и параметров политики, которые применяются для более производительных учебных учащихся.</span><span class="sxs-lookup"><span data-stu-id="1b03e-127">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="1b03e-128">Образовательные учреждения (учебный учащийся)</span><span class="sxs-lookup"><span data-stu-id="1b03e-128">Education (Primary school student)</span></span>   |<span data-ttu-id="1b03e-129">Создает набор политик и параметров политики, которые применяются к основным учащимся.</span><span class="sxs-lookup"><span data-stu-id="1b03e-129">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="1b03e-130">Образование (дополнительный учебный учащийся)</span><span class="sxs-lookup"><span data-stu-id="1b03e-130">Education (Secondary school student)</span></span>    |<span data-ttu-id="1b03e-131">Создает набор политик и параметров политики, которые применяются к дополнительным учащимся.</span><span class="sxs-lookup"><span data-stu-id="1b03e-131">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="1b03e-132">Образование (преподаватель)</span><span class="sxs-lookup"><span data-stu-id="1b03e-132">Education (Teacher)</span></span>    |<span data-ttu-id="1b03e-133">Создает набор политик и параметров политики, которые применяются для преподавателей.</span><span class="sxs-lookup"><span data-stu-id="1b03e-133">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="1b03e-134">Образование (основной преподаватель учебного заведения, использующий удаленное обучение)</span><span class="sxs-lookup"><span data-stu-id="1b03e-134">Education (Primary school teacher using remote learning)</span></span>    |<span data-ttu-id="1b03e-135">Создает набор политик, применимых к учителям начальных классов, для обеспечения максимальной безопасности и совместной работы учащихся при использовании дистанционного обучения.</span><span class="sxs-lookup"><span data-stu-id="1b03e-135">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="1b03e-136">Образование (учебный учащийся с удаленным обучением)</span><span class="sxs-lookup"><span data-stu-id="1b03e-136">Education (Primary school student using remote learning)</span></span>    |<span data-ttu-id="1b03e-137">Создает набор политик, применимых к учащимся начальных классов, для обеспечения максимальной безопасности и совместной работы учащихся при использовании дистанционного обучения.</span><span class="sxs-lookup"><span data-stu-id="1b03e-137">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="1b03e-138">Менеджер Firstline</span><span class="sxs-lookup"><span data-stu-id="1b03e-138">Firstline manager</span></span> |<span data-ttu-id="1b03e-139">Создает набор политик и применяет эти параметры для руководителей Firstline в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="1b03e-139">Creates a set of policies and applies those settings to Firstline Managers in your organization.</span></span> |
|<span data-ttu-id="1b03e-140">Firstline рабочий процесс</span><span class="sxs-lookup"><span data-stu-id="1b03e-140">Firstline worker</span></span> |<span data-ttu-id="1b03e-141">Создает набор политик и применяет эти параметры для Firstlineных сотрудников в Организации.</span><span class="sxs-lookup"><span data-stu-id="1b03e-141">Creates a set of policies and applies those settings to Firstline Workers in your organization.</span></span> |
|<span data-ttu-id="1b03e-142">Сотрудник по здравоохранение Clinical</span><span class="sxs-lookup"><span data-stu-id="1b03e-142">Healthcare clinical worker</span></span>  |<span data-ttu-id="1b03e-143">Создает набор политик и параметров политики, которые предоставляют Clinical сотрудникам, таким как зарегистрированные Nurses, начисление Nurses, врача и социальных работников, полный доступ к разговору, звонку, управлению сменой и собраниям.</span><span class="sxs-lookup"><span data-stu-id="1b03e-143">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="1b03e-144">Сотрудник "сведения о здравоохранение"</span><span class="sxs-lookup"><span data-stu-id="1b03e-144">Healthcare information worker</span></span>  |<span data-ttu-id="1b03e-145">Создание набора политик и параметров политики, предназначаемых сотрудникам, таким как ИТ-персонал, informatics сотрудников, финансовых сотрудников и руководителей соответствия требованиям, полного доступа к разговору, звонку и собранию.</span><span class="sxs-lookup"><span data-stu-id="1b03e-145">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="1b03e-146">Комната пациента на здравоохранение</span><span class="sxs-lookup"><span data-stu-id="1b03e-146">Healthcare patient room</span></span>  |<span data-ttu-id="1b03e-147">Создает набор политик и параметров политики, которые применяются к комнатам пациентам в вашей организации здравоохранения.</span><span class="sxs-lookup"><span data-stu-id="1b03e-147">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|
|<span data-ttu-id="1b03e-148">Малый и средний бизнес-пользователь (деловой голосовой звонок)</span><span class="sxs-lookup"><span data-stu-id="1b03e-148">Small and medium business user (Business Voice)</span></span> |<span data-ttu-id="1b03e-149">Создание политики настройки приложения, включающей приложения для голосового интерфейса для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="1b03e-149">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="1b03e-150">Малый и средний бизнес-пользователь (без деловой голосовой связи)</span><span class="sxs-lookup"><span data-stu-id="1b03e-150">Small and medium business user (without Business Voice)</span></span> |<span data-ttu-id="1b03e-151">Создание политики настройки приложения, относящейся к малому и среднему бизнес-группам пользователей (для некоммерческой голосовой связи).</span><span class="sxs-lookup"><span data-stu-id="1b03e-151">Creates an app setup policy relevant for a small and medium sized business Teams users (non-Business Voice experience).</span></span>
|<span data-ttu-id="1b03e-152">Открытый директор по безопасности</span><span class="sxs-lookup"><span data-stu-id="1b03e-152">Public safety officer</span></span>   |<span data-ttu-id="1b03e-153">Создает набор политик и параметров политики, которые применяются для руководителей общедоступной безопасности в Организации.</span><span class="sxs-lookup"><span data-stu-id="1b03e-153">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|

> [!NOTE]
> <span data-ttu-id="1b03e-154">В будущих выпусках Teams мы добавим дополнительные пакеты политик, поэтому ознакомьтесь с самыми актуальными сведениями.</span><span class="sxs-lookup"><span data-stu-id="1b03e-154">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="1b03e-155">Каждой отдельной политике назначается имя пакета политики, что позволяет легко определять политики, связанные с пакетом политики.</span><span class="sxs-lookup"><span data-stu-id="1b03e-155">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="1b03e-156">Например, если назначить пакету политики образования для преподавателей в учебном заведении, для каждой политики в пакете будет создана политика с именем Education_Teacher.</span><span class="sxs-lookup"><span data-stu-id="1b03e-156">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![Снимок экрана: пакет политики "образование" (для преподавателей)](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a><span data-ttu-id="1b03e-158">Пользовательские пакеты политик</span><span class="sxs-lookup"><span data-stu-id="1b03e-158">Custom policy packages</span></span>

<span data-ttu-id="1b03e-159">**Эта функция доступна в частном предварительной версии**</span><span class="sxs-lookup"><span data-stu-id="1b03e-159">**This feature is in private preview**</span></span>

<span data-ttu-id="1b03e-160">Пользовательские пакеты политик позволяют объединять собственные наборы политик для пользователей с аналогичными ролями в Организации.</span><span class="sxs-lookup"><span data-stu-id="1b03e-160">Custom policy packages let you bundle your own set of policies for users with similar roles in you organization.</span></span> <span data-ttu-id="1b03e-161">Создайте собственные пакеты политики, добавив необходимые типы политик и политики.</span><span class="sxs-lookup"><span data-stu-id="1b03e-161">Create your own policy packages by adding the policy types and policies that you need.</span></span>

<span data-ttu-id="1b03e-162">Чтобы создать настраиваемый пакет политики, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="1b03e-162">To create a new custom policy package:</span></span>

1. <span data-ttu-id="1b03e-163">В левой области навигации центра администрирования Microsoft Teams выберите пункт **пакеты политики**и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="1b03e-163">In the left navigation of the Microsoft Teams admin center,  select **Policy packages**, and then click **Add**.</span></span>
    :::image type="content" source="media/policy-packages-add.png" alt-text="Снимок экрана: кнопка "Добавить" на странице "пакеты политики" в центре администрирования":::
2. <span data-ttu-id="1b03e-165">Введите имя и описание пакета.</span><span class="sxs-lookup"><span data-stu-id="1b03e-165">Enter a name and description for your package.</span></span>
    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="Снимок экрана: Добавление нового настраиваемого пакета политики":::
3. <span data-ttu-id="1b03e-167">Выберите типы политик и имена политик, которые нужно включить в пакет.</span><span class="sxs-lookup"><span data-stu-id="1b03e-167">Select the policy types and policy names to include in the package.</span></span>
4. <span data-ttu-id="1b03e-168">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1b03e-168">Click **Save**.</span></span>

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="1b03e-169">Использование пакетов политик</span><span class="sxs-lookup"><span data-stu-id="1b03e-169">How to use policy packages</span></span>

<span data-ttu-id="1b03e-170">Ниже показано, как использовать пакеты политик в Организации.</span><span class="sxs-lookup"><span data-stu-id="1b03e-170">The following outlines how to use policy packages in your organization.</span></span>

![Общие сведения об использовании пакетов политик](media/manage-policy-packages-overview.png)

- <span data-ttu-id="1b03e-172">**[Представление](#view-the-settings-of-a-policy-in-a-policy-package)**: Просмотр политик в пакете политики.</span><span class="sxs-lookup"><span data-stu-id="1b03e-172">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the policies in a policy package.</span></span> <span data-ttu-id="1b03e-173">Затем просмотрите параметры каждой политики в пакете перед тем, как назначить пакет.</span><span class="sxs-lookup"><span data-stu-id="1b03e-173">Then, view the settings of each policy in a package before you assign the package.</span></span> <span data-ttu-id="1b03e-174">Убедитесь, что вы понимаете каждый из параметров.</span><span class="sxs-lookup"><span data-stu-id="1b03e-174">Make sure that you understand each setting.</span></span> <span data-ttu-id="1b03e-175">Определите, являются ли предопределенные значения подходящими для вашей организации, или измените их так, чтобы они были более строгими или Lenient в зависимости от потребностей Организации.</span><span class="sxs-lookup"><span data-stu-id="1b03e-175">Decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="1b03e-176">Если политика удалена, вы по-прежнему можете просматривать параметры, но вы не сможете изменить параметры.</span><span class="sxs-lookup"><span data-stu-id="1b03e-176">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="1b03e-177">Удаленная политика создается повторно с параметрами, предопределенными при назначении пакета политики.</span><span class="sxs-lookup"><span data-stu-id="1b03e-177">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="1b03e-178">**[Настройка](#customize-policies-in-a-policy-package)**: Настройка параметров политик в пакете политики в соответствии с потребностями Организации.</span><span class="sxs-lookup"><span data-stu-id="1b03e-178">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span>

- <span data-ttu-id="1b03e-179">**[Назначение](#assign-a-policy-package)**: назначение пакета политики пользователям.</span><span class="sxs-lookup"><span data-stu-id="1b03e-179">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span>  

> [!NOTE]
> <span data-ttu-id="1b03e-180">Вы также можете изменить параметры политик в пакете политики после назначения пакета.</span><span class="sxs-lookup"><span data-stu-id="1b03e-180">You can also change the settings of policies in a policy package after you assign a package.</span></span> <span data-ttu-id="1b03e-181">Любые изменения, внесенные в параметры политики, автоматически применяются к пользователям, которым назначен пакет.</span><span class="sxs-lookup"><span data-stu-id="1b03e-181">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="1b03e-182">Ниже описаны действия, которые необходимо выполнить, чтобы просмотреть, назначить и настроить пакеты политики в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1b03e-182">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="1b03e-183">Просмотр параметров политики в пакете политики</span><span class="sxs-lookup"><span data-stu-id="1b03e-183">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="1b03e-184">В левой области навигации центра администрирования Microsoft Teams выберите пункт **пакеты политики**, а затем выберите пакет политики, щелкнув слева от имени пакета.</span><span class="sxs-lookup"><span data-stu-id="1b03e-184">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="1b03e-185">Выберите политику, которую вы хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="1b03e-185">Click the policy you want to view.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="1b03e-186">Настройка политик в пакете политики</span><span class="sxs-lookup"><span data-stu-id="1b03e-186">Customize policies in a policy package</span></span>

<span data-ttu-id="1b03e-187">Вы можете изменить параметры политики на странице **пакеты политики** или непосредственно на страницу политики в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1b03e-187">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="1b03e-188">В левой области навигации центра администрирования Microsoft Teams выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="1b03e-188">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="1b03e-189">Щелкните **пакеты политики**, а затем выберите пакет политики, щелкнув слева от его имени.</span><span class="sxs-lookup"><span data-stu-id="1b03e-189">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="1b03e-190">Выберите тип политики.</span><span class="sxs-lookup"><span data-stu-id="1b03e-190">Click the policy type.</span></span>  <span data-ttu-id="1b03e-191">Например, выберите **политики обмена сообщениями**.</span><span class="sxs-lookup"><span data-stu-id="1b03e-191">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="1b03e-192">Выберите политику, которую вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="1b03e-192">Select the policy you want to edit.</span></span> <span data-ttu-id="1b03e-193">Политики, связанные с пакетом политики, имеют то же имя, что и пакет политики.</span><span class="sxs-lookup"><span data-stu-id="1b03e-193">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="1b03e-194">Внесите нужные изменения и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1b03e-194">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="1b03e-195">Назначение пакета политики</span><span class="sxs-lookup"><span data-stu-id="1b03e-195">Assign a policy package</span></span>

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="1b03e-196">Назначение пакета политики для одного пользователя</span><span class="sxs-lookup"><span data-stu-id="1b03e-196">Assign a policy package to one user</span></span>

1. <span data-ttu-id="1b03e-197">В Центре администрирования Microsoft Teams в области навигации слева перейдите в раздел **Пользователи**, затем щелкните пользователя.</span><span class="sxs-lookup"><span data-stu-id="1b03e-197">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="1b03e-198">На странице пользователя нажмите **политики**, а затем рядом с пунктом **Политика**выберите команду **изменить**.</span><span class="sxs-lookup"><span data-stu-id="1b03e-198">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="1b03e-199">В области **Назначение пакета политики** выберите пакет, который вы хотите назначить, и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1b03e-199">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="1b03e-200">Назначение пакета политики нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="1b03e-200">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="1b03e-201">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел **пакеты политики**, а затем выберите пакет политики, который вы хотите назначить, щелкнув слева от его имени.</span><span class="sxs-lookup"><span data-stu-id="1b03e-201">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="1b03e-202">Щелкните **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="1b03e-202">Click **Manage users**.</span></span>
3. <span data-ttu-id="1b03e-203">В области **Управление пользователями** выполните поиск по отображаемому имени или по имени пользователя, выберите имя и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="1b03e-203">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="1b03e-204">Повторите это действие для каждого пользователя, которого нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="1b03e-204">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="1b03e-205">Завершив добавление пользователей, нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1b03e-205">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="1b03e-206">Назначение пакета политики большому набору (пакету) пользователей</span><span class="sxs-lookup"><span data-stu-id="1b03e-206">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="1b03e-207">Назначение пакета политики для большого количества пользователей одновременно с помощью задания пакетной политики.</span><span class="sxs-lookup"><span data-stu-id="1b03e-207">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="1b03e-208">С помощью командлета [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) вы можете отправить пакет пользователей и пакет политики, который вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="1b03e-208">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="1b03e-209">Назначения обрабатываются как фоновая операция, и для каждого пакета создается идентификатор операции.</span><span class="sxs-lookup"><span data-stu-id="1b03e-209">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="1b03e-210">Пакет может содержать до 5 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="1b03e-210">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="1b03e-211">Вы можете указать пользователей, указав их идентификатор (UPN), адрес SIP или адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="1b03e-211">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="1b03e-212">Дополнительные сведения можно найти в разделе [Назначение пакета политики пакету пользователей](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span><span class="sxs-lookup"><span data-stu-id="1b03e-212">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="1b03e-213">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="1b03e-213">Troubleshooting</span></span>

<span data-ttu-id="1b03e-214">**При назначении пакета политики появляется сообщение об ошибке**</span><span class="sxs-lookup"><span data-stu-id="1b03e-214">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="1b03e-215">Это может произойти, если одна или несколько политик в пакете не были успешно созданы или применены.</span><span class="sxs-lookup"><span data-stu-id="1b03e-215">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="1b03e-216">Переназначение пакета политики пользователям.</span><span class="sxs-lookup"><span data-stu-id="1b03e-216">Reassign the policy package to your users.</span></span> <span data-ttu-id="1b03e-217">Повторное выполнение операции обычно решает эту проблему.</span><span class="sxs-lookup"><span data-stu-id="1b03e-217">Retrying the operation typically fixes this issue.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1b03e-218">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="1b03e-218">Related topics</span></span>

[<span data-ttu-id="1b03e-219">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="1b03e-219">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="1b03e-220">Пакеты политики Teams для администраторов EDU</span><span class="sxs-lookup"><span data-stu-id="1b03e-220">Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)

[<span data-ttu-id="1b03e-221">Пакеты политики Teams для здравоохранения</span><span class="sxs-lookup"><span data-stu-id="1b03e-221">Teams policy packages for healthcare</span></span>](policy-packages-healthcare.md)

[<span data-ttu-id="1b03e-222">Пакеты политики Teams для государственных организаций</span><span class="sxs-lookup"><span data-stu-id="1b03e-222">Teams policy packages for government</span></span>](policy-packages-gov.md)
