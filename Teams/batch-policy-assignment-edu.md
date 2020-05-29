---
title: Назначение политик большим наборам пользователей в учебном заведении
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: saragava,karsmith
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: В этой статье рассказывается о том, как использовать назначение пакетной политики для крупных наборов пользователей в обучающем учреждении для удаленной школы (теле-учебного заведения).
f1keywords: ''
ms.openlocfilehash: 5772a260642b09232e4df5eec57751a39ec2a74a
ms.sourcegitcommit: 86b0956680b867b8bedb2e969220b8006829ee53
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/28/2020
ms.locfileid: "44410444"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a><span data-ttu-id="52e64-103">Назначение политик большим наборам пользователей в учебном заведении</span><span class="sxs-lookup"><span data-stu-id="52e64-103">Assign policies to large sets of users in your school</span></span>

<span data-ttu-id="52e64-104">Нужно ли предоставлять учащимся и преподавателям доступ к различным функциям в Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="52e64-104">Do you need to give your students and educators access to different features in Microsoft Teams?</span></span> <span data-ttu-id="52e64-105">Вы можете быстро идентифицировать пользователей в своей организации по типу лицензии и назначить им соответствующую политику.</span><span class="sxs-lookup"><span data-stu-id="52e64-105">You can quickly identify the users in your organization by license type and then assign them the appropriate policy.</span></span> <span data-ttu-id="52e64-106">В этом учебнике показано, как использовать [назначение пакетной политики](assign-policies.md#assign-a-policy-to-a-batch-of-users) для назначения пользователям политики собраний для массовой рассылки.</span><span class="sxs-lookup"><span data-stu-id="52e64-106">This tutorial shows you how to use [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users) to assign a meeting policy to users in bulk.</span></span>

<span data-ttu-id="52e64-107">Помните, что в Teams пользователи автоматически получают глобальную политику (по умолчанию на уровне Организации) для типа политики Teams, если вы не создали и не назначаете пользовательскую политику.</span><span class="sxs-lookup"><span data-stu-id="52e64-107">Remember that in Teams, users automatically get the Global (Org-wide default) policy for a Teams policy type unless you create and assign a custom policy.</span></span> <span data-ttu-id="52e64-108">Поскольку заполнение учащихся часто является большим набором пользователей, и они часто получают наиболее строгие параметры, мы рекомендуем сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="52e64-108">Because the student population is often the largest set of users and they often receive the most restrictive settings, we recommend that you do the following:</span></span>

- <span data-ttu-id="52e64-109">Измените и примените глобальную политику (по умолчанию на уровне Организации), чтобы ограничить возможности для учащихся.</span><span class="sxs-lookup"><span data-stu-id="52e64-109">Edit and apply the Global (Org-wide default) policy to restrict capabilities for students.</span></span> 
- <span data-ttu-id="52e64-110">Создание настраиваемой политики, которая позволяет выполнять базовые функции, такие как личное чат и планирование собраний, а также назначать политику сотрудникам и преподавателям.</span><span class="sxs-lookup"><span data-stu-id="52e64-110">Create a custom policy that allows core capabilities such as private chat and meeting scheduling and assign the policy to your staff and educators.</span></span>

<span data-ttu-id="52e64-111">Имейте в виду, что глобальная политика будет применяться ко всем пользователям в вашем учебном заведении, пока не будет создана пользовательская политика, и вы сможете назначить ее вашим сотрудникам и преподавателям.</span><span class="sxs-lookup"><span data-stu-id="52e64-111">Keep in mind that the Global policy will apply to all users in your school until you create a custom policy and assign it to your staff and educators.</span></span>

<span data-ttu-id="52e64-112">В этом учебнике учащиеся получат глобальную политику собраний, и мы используем PowerShell для назначения настраиваемой политики собраний с именем EducatorMeetingPolicy для сотрудников и преподавателей в массовом режиме.</span><span class="sxs-lookup"><span data-stu-id="52e64-112">In this tutorial, students will get the Global meeting policy and we use PowerShell to assign a custom meeting policy named EducatorMeetingPolicy to staff and educators in bulk.</span></span> <span data-ttu-id="52e64-113">Предполагается, что вы изменили глобальную политику для настройки параметров собрания для учащихся и создали специальную политику, которая определяет процесс собрания для персонала и преподавателей.</span><span class="sxs-lookup"><span data-stu-id="52e64-113">We assume that you've edited the Global policy to tailor meeting settings for students and created a custom policy that defines the meeting experience for staff and educators.</span></span>

![Снимок экрана: страница "политики собрания" в центре администрирования Teams](media/edu-batch-policy-assignment.png)

<span data-ttu-id="52e64-115">Выполните указанные ниже действия, чтобы назначить пользовательские политики собраний сотрудникам и преподавателям в массовом режиме.</span><span class="sxs-lookup"><span data-stu-id="52e64-115">Follow these steps to assign a custom meeting policy to staff and educators in bulk.</span></span>

## <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a><span data-ttu-id="52e64-116">Соединение с модулем Azure AD PowerShell для Graph и модулем Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="52e64-116">Connect to the Azure AD PowerShell for Graph module and the Teams PowerShell module</span></span>

<span data-ttu-id="52e64-117">Перед выполнением действий, описанных в этой статье, необходимо установить и подключить модуль Azure AD PowerShell для Graph (для идентификации пользователей по назначенным им лицензиям) и модуль Microsoft Teams PowerShell (для назначения политик этим пользователям).</span><span class="sxs-lookup"><span data-stu-id="52e64-117">Before you perform the steps in this article, you'll need to install and connect to the Azure AD PowerShell for Graph module (to identify users by their assigned licenses) and the Microsoft Teams PowerShell module (to assign the policies to those users).</span></span>

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a><span data-ttu-id="52e64-118">Установка и подключение к модулю Azure AD PowerShell для Graph</span><span class="sxs-lookup"><span data-stu-id="52e64-118">Install and connect to the Azure AD PowerShell for Graph module</span></span>

<span data-ttu-id="52e64-119">Откройте командную команду Windows PowerShell с повышенными привилегиями (запустите Windows PowerShell от имени администратора), а затем выполните указанные ниже действия, чтобы установить модуль Azure Active Directory PowerShell для Graph.</span><span class="sxs-lookup"><span data-stu-id="52e64-119">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator), and then run the following to install the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Install-Module -Name AzureAD
```

<span data-ttu-id="52e64-120">Выполните указанные ниже действия, чтобы подключиться к Azure AD.</span><span class="sxs-lookup"><span data-stu-id="52e64-120">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="52e64-121">Когда вам будет предложено, войдите в систему с помощью учетных данных администратора.</span><span class="sxs-lookup"><span data-stu-id="52e64-121">When you're prompted, sign in using your admin credentials.</span></span>

<span data-ttu-id="52e64-122">Дополнительные сведения можно найти в разделе [подключение с помощью модуля Azure Active Directory PowerShell для Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="52e64-122">To learn more, see [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="52e64-123">Установка и подключение к модулю Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="52e64-123">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="52e64-124">Выполните указанные ниже действия, чтобы установить [модуль PowerShell Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams).</span><span class="sxs-lookup"><span data-stu-id="52e64-124">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="52e64-125">Убедитесь, что вы установили версию 1.0.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="52e64-125">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="52e64-126">Выполните указанные ниже действия, чтобы подключиться к Teams и начать сеанс.</span><span class="sxs-lookup"><span data-stu-id="52e64-126">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```
<span data-ttu-id="52e64-127">Когда вам будет предложено, войдите в систему с помощью учетных данных администратора, используемых для подключения к Azure AD.</span><span class="sxs-lookup"><span data-stu-id="52e64-127">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

## <a name="identify-your-users"></a><span data-ttu-id="52e64-128">Определение пользователей</span><span class="sxs-lookup"><span data-stu-id="52e64-128">Identify your users</span></span>

<span data-ttu-id="52e64-129">Сначала выполните указанные ниже действия, чтобы идентифицировать сотрудников и преподавателей по типу лицензии.</span><span class="sxs-lookup"><span data-stu-id="52e64-129">First, run the following to identify your staff and educators by license type.</span></span> <span data-ttu-id="52e64-130">В этой статье рассказывается о том, какие SKU используются в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="52e64-130">This tells you what SKUs are in use in your organization.</span></span> <span data-ttu-id="52e64-131">Затем вы можете идентифицировать сотрудников и преподавателей, которым назначены номера SKU факультета.</span><span class="sxs-lookup"><span data-stu-id="52e64-131">You can then identify staff and educators that have a Faculty SKU assigned.</span></span>

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

<span data-ttu-id="52e64-132">Возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="52e64-132">Which returns:</span></span>

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

<span data-ttu-id="52e64-133">В этом примере вывод показывает, что лицензия факультета SkuId — "e97c048c-37a4-45fb-AB50-922fbf07a370".</span><span class="sxs-lookup"><span data-stu-id="52e64-133">In this example, the output shows that the Faculty license SkuId is "e97c048c-37a4-45fb-ab50-922fbf07a370".</span></span>

> [!NOTE]
> <span data-ttu-id="52e64-134">Список материалов для образования и номер SKU можно найти в [справочнике по образованию SKU](sku-reference-edu.md).</span><span class="sxs-lookup"><span data-stu-id="52e64-134">To see a list of Education SKUs and SKU IDs, see [Education SKU reference](sku-reference-edu.md).</span></span>

<span data-ttu-id="52e64-135">Затем выполните указанные ниже действия, чтобы идентифицировать пользователей, у которых есть лицензия, и собирать их вместе.</span><span class="sxs-lookup"><span data-stu-id="52e64-135">Next, we run the following to identify the users that have this license and collect them all together.</span></span>

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

## <a name="assign-a-policy-in-bulk"></a><span data-ttu-id="52e64-136">Массовое назначение политики</span><span class="sxs-lookup"><span data-stu-id="52e64-136">Assign a policy in bulk</span></span>

<span data-ttu-id="52e64-137">Теперь пользователям можно назначать соответствующие политики.</span><span class="sxs-lookup"><span data-stu-id="52e64-137">Now, we assign the appropriate policies to users in bulk.</span></span> <span data-ttu-id="52e64-138">Максимальное количество пользователей, которым можно назначить или обновлять политики, составляет 5 000 за один раз.</span><span class="sxs-lookup"><span data-stu-id="52e64-138">The maximum number of users for which you can assign or update policies is 5,000 at a time.</span></span> <span data-ttu-id="52e64-139">Например, если у вас более 5 000 сотрудников и преподавателей, вам нужно будет отправить несколько пакетов.</span><span class="sxs-lookup"><span data-stu-id="52e64-139">For example, if you have more than 5,000 staff and educators, you'll need to submit multiple batches.</span></span>


<span data-ttu-id="52e64-140">Выполните указанные ниже действия, чтобы назначить политику собраний с именем EducatorMeetingPolicy вашим сотрудникам и преподавателям.</span><span class="sxs-lookup"><span data-stu-id="52e64-140">Run the following to assign the meeting policy named EducatorMeetingPolicy to your staff and educators.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> <span data-ttu-id="52e64-141">Чтобы назначить другой тип политики в массовом режиме, например TeamsMessagingPolicy, необходимо изменить ```PolicyType``` политику, которую вы назначаете, и присвоить ей ```PolicyName``` имя политики.</span><span class="sxs-lookup"><span data-stu-id="52e64-141">To assign a different policy type in bulk, like TeamsMessagingPolicy, you'll need to change ```PolicyType``` to the policy that you're assigning and ```PolicyName``` to the policy name.</span></span>

## <a name="get-the-status-of-a-bulk-assignment"></a><span data-ttu-id="52e64-142">Получение состояния массового назначения</span><span class="sxs-lookup"><span data-stu-id="52e64-142">Get the status of a bulk assignment</span></span>

<span data-ttu-id="52e64-143">Каждое массовое назначение возвращает идентификатор операции, который можно использовать для отслеживания хода выполнения назначений политики или определения возможных сбоев.</span><span class="sxs-lookup"><span data-stu-id="52e64-143">Each bulk assignment returns an operation ID, which you can use to track the progress of the policy assignments or identify any failures that might occur.</span></span> <span data-ttu-id="52e64-144">Например, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="52e64-144">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

<span data-ttu-id="52e64-145">Чтобы просмотреть состояние назначения каждого пользователя в пакетной операции, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="52e64-145">To view the assignment status of each user in the batch operation, run the following.</span></span> <span data-ttu-id="52e64-146">Сведения о каждом пользователе находятся в ```UserState``` свойстве.</span><span class="sxs-lookup"><span data-stu-id="52e64-146">Details of each user are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

## <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a><span data-ttu-id="52e64-147">Назначение политики в массовом режиме, если у вас более 5 000 пользователей</span><span class="sxs-lookup"><span data-stu-id="52e64-147">Assign a policy in bulk if you have more than 5,000 users</span></span>

<span data-ttu-id="52e64-148">Сначала выполните указанные ниже действия, чтобы узнать, сколько у вас сотрудников и преподавателей.</span><span class="sxs-lookup"><span data-stu-id="52e64-148">First, run the following to see how many staff and educators you have:</span></span>

```powershell
$faculty.count
```

<span data-ttu-id="52e64-149">Вместо того чтобы предоставлять весь список идентификаторов пользователей, выполните указанные ниже действия, чтобы указать первые 5 000, а затем следующие 5 000 и т. д.</span><span class="sxs-lookup"><span data-stu-id="52e64-149">Instead of providing the whole list of user IDs, run the following to specify the first 5,000, and then the next 5,000, and so on.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

<span data-ttu-id="52e64-150">Вы можете изменить диапазон идентификаторов пользователей, пока не дойдете до полного списка пользователей.</span><span class="sxs-lookup"><span data-stu-id="52e64-150">You can change the range of user IDs until you reach the full list of users.</span></span> <span data-ttu-id="52e64-151">Например, введите ```$faculty[0..4999``` первый пакет, ```$faculty[5000..9999``` который используется для второго пакета, введите ```$faculty[10000..14999``` третий пакет и т. д.</span><span class="sxs-lookup"><span data-stu-id="52e64-151">For example, enter ```$faculty[0..4999``` for the first batch, use ```$faculty[5000..9999``` for the second batch, enter ```$faculty[10000..14999``` for the third batch, and so on.</span></span>

## <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="52e64-152">Получение политик, назначенных пользователю</span><span class="sxs-lookup"><span data-stu-id="52e64-152">Get the policies assigned to a user</span></span>

<span data-ttu-id="52e64-153">Выполните указанные ниже действия, чтобы просмотреть все политики, назначенные определенному пользователю.</span><span class="sxs-lookup"><span data-stu-id="52e64-153">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="52e64-154">В следующем примере показано, как получить политики, назначенные hannah@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="52e64-154">The following example shows you how to get the policies that are assigned to hannah@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a><span data-ttu-id="52e64-155">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="52e64-155">FAQ</span></span>

<span data-ttu-id="52e64-156">**Я хочу убедиться, что все пользователи, которые являются студентами, сотрудниками и преподавателями, автоматически получают назначенные политики. Как это можно сделать?**</span><span class="sxs-lookup"><span data-stu-id="52e64-156">**I want to make sure that all users that are students, staff, and educators automatically get policies assigned. How can I do that?**</span></span>

<span data-ttu-id="52e64-157">Группа разработчиков Teams работает над тем, чтобы поддерживать назначение политик группам безопасности.</span><span class="sxs-lookup"><span data-stu-id="52e64-157">The Teams product team is doing work to support assigning policies to security groups.</span></span> <span data-ttu-id="52e64-158">В это время вы сможете создавать группы для учащихся и преподавателей, а затем соответствующие политики для этих групп.</span><span class="sxs-lookup"><span data-stu-id="52e64-158">At that time, you'll be able to create groups for your students and teachers, and then the appropriate policies to those groups.</span></span> <span data-ttu-id="52e64-159">Обратите внимание на то, что явные назначения пользователей (например, политики, назначенные с помощью этого учебника) переопределяют политики, наследуемые от группы.</span><span class="sxs-lookup"><span data-stu-id="52e64-159">Note that explicit user assignments (such as the policies that you've assigned using this tutorial) will override policies inherited from a group.</span></span> <span data-ttu-id="52e64-160">Если эта функция поддерживается, мы предоставляем дополнительные инструкции по использованию назначения политики для групп и обновления пользователей, чтобы убедиться, что они получают унаследованные групповые политики.</span><span class="sxs-lookup"><span data-stu-id="52e64-160">When this feature is supported, we'll provide more instructions on how to use policy assignment to groups and update your users to ensure they get the inherited group policies.</span></span>

<span data-ttu-id="52e64-161">**Я не знаком с оболочкой PowerShell для Teams. Где можно найти дополнительные сведения?**</span><span class="sxs-lookup"><span data-stu-id="52e64-161">**I'm not familiar with PowerShell for Teams. Where can I learn more?**</span></span>

<span data-ttu-id="52e64-162">Ознакомьтесь со статьей [Общие сведения о Teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="52e64-162">See [Teams Powershell overview](teams-powershell-overview.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="52e64-163">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="52e64-163">Related topics</span></span>

- [<span data-ttu-id="52e64-164">Назначение политик пользователям</span><span class="sxs-lookup"><span data-stu-id="52e64-164">Assign policies to your users</span></span>](assign-policies.md)
- [<span data-ttu-id="52e64-165">New-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="52e64-165">New-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="52e64-166">Get-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="52e64-166">Get-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="52e64-167">Get-CsUserPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="52e64-167">Get-CsUserPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)
