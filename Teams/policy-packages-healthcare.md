---
title: Пакеты политики Teams для здравоохранения
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
description: Сведения о том, как использовать и управлять пакетами политики Teams для организации здравоохранения.
ms.openlocfilehash: dbbc0956f339760bedf1ce9cc2c5012cc317e152
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2020
ms.locfileid: "46803979"
---
# <a name="teams-policy-packages-for-healthcare"></a><span data-ttu-id="9307f-103">Пакеты политики Teams для здравоохранения</span><span class="sxs-lookup"><span data-stu-id="9307f-103">Teams policy packages for healthcare</span></span>

## <a name="overview"></a><span data-ttu-id="9307f-104">Обзор</span><span class="sxs-lookup"><span data-stu-id="9307f-104">Overview</span></span>

<span data-ttu-id="9307f-105">[Пакет политики](manage-policy-packages.md) в Microsoft Teams — это набор предопределенных политик и параметров политики, которые можно назначить пользователям, имеющим аналогичные роли в Организации.</span><span class="sxs-lookup"><span data-stu-id="9307f-105">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="9307f-106">Пакеты политик упрощают, оптимизируют и помогают обеспечивать согласованность при управлении политиками.</span><span class="sxs-lookup"><span data-stu-id="9307f-106">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="9307f-107">Вы можете настроить параметры политик в пакете в соответствии с потребностями пользователей.</span><span class="sxs-lookup"><span data-stu-id="9307f-107">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="9307f-108">При изменении параметров политик в пакете политики все пользователи, которым назначен этот пакет, получают обновленные параметры.</span><span class="sxs-lookup"><span data-stu-id="9307f-108">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="9307f-109">Управление пакетами политики осуществляется с помощью центра администрирования Microsoft Teams или оболочки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9307f-109">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="9307f-110">Пакеты политик предварительно определяют следующие политики в зависимости от пакета:</span><span class="sxs-lookup"><span data-stu-id="9307f-110">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="9307f-111">Обмен сообщениями</span><span class="sxs-lookup"><span data-stu-id="9307f-111">Messaging</span></span>
- <span data-ttu-id="9307f-112">Собрания</span><span class="sxs-lookup"><span data-stu-id="9307f-112">Meetings</span></span>
- <span data-ttu-id="9307f-113">Звонки</span><span class="sxs-lookup"><span data-stu-id="9307f-113">Calling</span></span>
- <span data-ttu-id="9307f-114">Настройка приложения</span><span class="sxs-lookup"><span data-stu-id="9307f-114">App setup</span></span>
- <span data-ttu-id="9307f-115">Трансляции</span><span class="sxs-lookup"><span data-stu-id="9307f-115">Live events</span></span>

<span data-ttu-id="9307f-116">В настоящее время команды включают в себя следующие пакеты политик здравоохранения.</span><span class="sxs-lookup"><span data-stu-id="9307f-116">Teams currently includes the following healthcare policy packages.</span></span>

|<span data-ttu-id="9307f-117">Имя пакета в центре администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9307f-117">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="9307f-118">Кому предназначено</span><span class="sxs-lookup"><span data-stu-id="9307f-118">Best used for</span></span>|<span data-ttu-id="9307f-119">Описание</span><span class="sxs-lookup"><span data-stu-id="9307f-119">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="9307f-120">Сотрудник по здравоохранение Clinical</span><span class="sxs-lookup"><span data-stu-id="9307f-120">Healthcare clinical worker</span></span>  |<span data-ttu-id="9307f-121">Clinical работников в вашей организации здравоохранения</span><span class="sxs-lookup"><span data-stu-id="9307f-121">Clinical workers in your healthcare organization</span></span>  |<span data-ttu-id="9307f-122">Создает набор политик и параметров политики, которые предоставляют Clinical сотрудникам, таким как зарегистрированные Nurses, начисление Nurses, врача и социальных работников, полный доступ к разговору, звонку, управлению сменой и собраниям.</span><span class="sxs-lookup"><span data-stu-id="9307f-122">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="9307f-123">Сотрудник "сведения о здравоохранение"</span><span class="sxs-lookup"><span data-stu-id="9307f-123">Healthcare information worker</span></span>  |<span data-ttu-id="9307f-124">Информационные работники в вашей организации здравоохранения</span><span class="sxs-lookup"><span data-stu-id="9307f-124">Information workers in your healthcare organization</span></span> |<span data-ttu-id="9307f-125">Создание набора политик и параметров политики, предназначаемых сотрудникам, таким как ИТ-персонал, informatics сотрудников, финансовых сотрудников и руководителей соответствия требованиям, полного доступа к разговору, звонку и собранию.</span><span class="sxs-lookup"><span data-stu-id="9307f-125">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="9307f-126">Комната пациента на здравоохранение</span><span class="sxs-lookup"><span data-stu-id="9307f-126">Healthcare patient room</span></span>  |<span data-ttu-id="9307f-127">Устройства с комнатой пациента</span><span class="sxs-lookup"><span data-stu-id="9307f-127">Patient room devices</span></span>|<span data-ttu-id="9307f-128">Создает набор политик и параметров политики, которые применяются к комнатам пациентам в вашей организации здравоохранения.</span><span class="sxs-lookup"><span data-stu-id="9307f-128">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|

![Снимок экрана: пакеты политики здравоохранения](media/policy-packages-healthcare.png)

<span data-ttu-id="9307f-130">Каждой отдельной политике назначается имя пакета политики, что позволяет легко определять политики, связанные с пакетом политики.</span><span class="sxs-lookup"><span data-stu-id="9307f-130">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="9307f-131">Например, при назначении пакету политики Clinical работников на здравоохранение для clinicians в Организации, для каждой политики в пакете создается политика с именем Healthcare_ClinicalWorker.</span><span class="sxs-lookup"><span data-stu-id="9307f-131">For example, when you assign the Healthcare clinical worker policy package to clinicians in your organization, a policy named Healthcare_ClinicalWorker is created for each policy in the package.</span></span>

![Снимок экрана: политики в Clinical рабочего пакета здравоохранения](media/policy-packages-healthcare-clinical-worker.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="9307f-133">Управление пакетами политик</span><span class="sxs-lookup"><span data-stu-id="9307f-133">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="9307f-134">Просмотр</span><span class="sxs-lookup"><span data-stu-id="9307f-134">View</span></span>

<span data-ttu-id="9307f-135">Перед назначением пакета просмотрите параметры каждой политики в пакете политики.</span><span class="sxs-lookup"><span data-stu-id="9307f-135">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="9307f-136">В левой области навигации центра администрирования Microsoft Teams выберите **пакеты политики**, выберите имя пакета, а затем выберите имя политики.</span><span class="sxs-lookup"><span data-stu-id="9307f-136">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="9307f-137">Определите, являются ли предопределенные значения подходящими для вашей организации, или настройте их так, чтобы они были более строгими или Lenient в зависимости от потребностей Организации.</span><span class="sxs-lookup"><span data-stu-id="9307f-137">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="9307f-138">Настроить</span><span class="sxs-lookup"><span data-stu-id="9307f-138">Customize</span></span>

<span data-ttu-id="9307f-139">Настройте параметры политик в пакете политики в соответствии с потребностями Организации.</span><span class="sxs-lookup"><span data-stu-id="9307f-139">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="9307f-140">Любые изменения, внесенные в параметры политики, автоматически применяются к пользователям, которым назначен пакет.</span><span class="sxs-lookup"><span data-stu-id="9307f-140">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="9307f-141">Чтобы изменить параметры политики в пакете политики, в центре администрирования Microsoft Teams выберите пакет политики, выберите имя политики, которую вы хотите изменить, и нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="9307f-141">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="9307f-142">Имейте в виду, что вы также можете изменить параметры политик в пакете после назначения пакета политики.</span><span class="sxs-lookup"><span data-stu-id="9307f-142">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="9307f-143">Дополнительные сведения можно найти [в разделе Настройка политик в пакете политики](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="9307f-143">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="9307f-144">Присваивают</span><span class="sxs-lookup"><span data-stu-id="9307f-144">Assign</span></span>

<span data-ttu-id="9307f-145">Назначение пакета политики пользователям.</span><span class="sxs-lookup"><span data-stu-id="9307f-145">Assign the policy package to users.</span></span> <span data-ttu-id="9307f-146">Чтобы назначить пакет политики для одного или нескольких пользователей, нажмите кнопку **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="9307f-146">To assign a policy package to one or multiple users, click **Manage users**.</span></span> <span data-ttu-id="9307f-147">Вы также можете [использовать PowerShell](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) для назначения пакета политики большим пакетам пользователей.</span><span class="sxs-lookup"><span data-stu-id="9307f-147">You can also [use PowerShell](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) to assign a policy package to large batches of users.</span></span> 

<span data-ttu-id="9307f-148">Инструкции по назначению пакета политики с помощью центра администрирования Microsoft Teams или оболочки PowerShell приведены в статье [Назначение пакета политики](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="9307f-148">For steps on how to assign a policy package using the Microsoft Teams admin center or PowerShell, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

![Снимок экрана: назначение пакета политики в центре администрирования](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="9307f-150">Если пользователю назначена политика, а затем в дальнейшем вы назначаете другую политику, она имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="9307f-150">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9307f-151">См. также</span><span class="sxs-lookup"><span data-stu-id="9307f-151">Related topics</span></span>

[<span data-ttu-id="9307f-152">Управление пакетами политик в Teams</span><span class="sxs-lookup"><span data-stu-id="9307f-152">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="9307f-153">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="9307f-153">Assign policies to your users in Teams</span></span>](assign-policies.md)
