---
title: Назначение политик большим наборам пользователей в учебном заведении
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: karsmith, angch, cebulnes
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
description: Научитесь назначать политики большим наборам пользователей в обучающем учреждении на основе членства в группе или непосредственно с помощью назначения пакетов для удаленной школы (теле-учебного заведения).
f1keywords: ''
ms.openlocfilehash: 0b4fd804b51fef9537d30230aed400bb0cb7e0aa
ms.sourcegitcommit: dc3e8ae454c42981f037f4de2e48005428b6078e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/31/2020
ms.locfileid: "46534134"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a><span data-ttu-id="4a595-103">Назначение политик большим наборам пользователей в учебном заведении</span><span class="sxs-lookup"><span data-stu-id="4a595-103">Assign policies to large sets of users in your school</span></span>

> [!NOTE]
> <span data-ttu-id="4a595-104">Более подробные сведения о назначении политик в Microsoft Teams можно найти [в статье назначение политик для пользователей в Teams](assign-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4a595-104">For the larger story on assigning policies in Microsoft Teams, see [Assign policies to your users in Teams](assign-policies.md).</span></span>

## <a name="overview"></a><span data-ttu-id="4a595-105">Обзор</span><span class="sxs-lookup"><span data-stu-id="4a595-105">Overview</span></span>

<span data-ttu-id="4a595-106">Нужно ли предоставлять учащимся и преподавателям доступ к различным функциям в Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="4a595-106">Do you need to give your students and educators access to different features in Microsoft Teams?</span></span> <span data-ttu-id="4a595-107">Вы можете быстро идентифицировать пользователей в своей организации по типу лицензии и назначить им соответствующую политику.</span><span class="sxs-lookup"><span data-stu-id="4a595-107">You can quickly identify the users in your organization by license type and then assign them the appropriate policy.</span></span> <span data-ttu-id="4a595-108">В этом учебнике показано, как назначить политику собраний большим наборам пользователей в вашем учебном заведении.</span><span class="sxs-lookup"><span data-stu-id="4a595-108">This tutorial shows you how to assign a meeting policy to large sets of users in your school.</span></span> <span data-ttu-id="4a595-109">Вы можете назначать политики с помощью центра администрирования Microsoft Teams и PowerShell, и мы покажем вам оба способа.</span><span class="sxs-lookup"><span data-stu-id="4a595-109">You can assign policies using the Microsoft Teams admin center and PowerShell and we'll show you both ways.</span></span>

<span data-ttu-id="4a595-110">Вы можете назначить политику собраний группе безопасности, в которую пользователи входят или непосредственно для пользователей при изменении масштаба с помощью задания пакетной политики.</span><span class="sxs-lookup"><span data-stu-id="4a595-110">You can assign a meeting policy to a security group that the users are members of or directly to users at scale through a batch policy assignment.</span></span> <span data-ttu-id="4a595-111">После прочтения этой статьи вы сможете следующее.</span><span class="sxs-lookup"><span data-stu-id="4a595-111">You'll learn how to:</span></span>

- <span data-ttu-id="4a595-112">\*\*Назначение политики собрания группе безопасности (рекомендуется) с помощью [назначения политик для групп](#assign-a-policy-to-a-group) \*\*.</span><span class="sxs-lookup"><span data-stu-id="4a595-112">**Use [policy assignment to groups](#assign-a-policy-to-a-group) to assign a meeting policy to a security group (recommended)**.</span></span> <span data-ttu-id="4a595-113">Этот метод позволяет назначить политику, основанную на членстве в группах.</span><span class="sxs-lookup"><span data-stu-id="4a595-113">This method lets you assign a policy based on group membership.</span></span> <span data-ttu-id="4a595-114">Вы можете назначить политику группе безопасности или списку рассылки.</span><span class="sxs-lookup"><span data-stu-id="4a595-114">You can assign a policy to a security group or distribution list.</span></span> <span data-ttu-id="4a595-115">Когда участники добавляются в группу или удаляются из нее, их унаследованные назначения политик обновляются соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="4a595-115">As members are added to or removed from the group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="4a595-116">Мы рекомендуем использовать этот метод, так как он сокращает время управления политиками для новых пользователей или изменения ролей пользователей.</span><span class="sxs-lookup"><span data-stu-id="4a595-116">We recommend you use this method because it reduces the time to manage policies for new users or when users' roles change.</span></span> <span data-ttu-id="4a595-117">Этот метод наилучшим образом подходит для групп до 50 000 пользователей, но также для работы с более крупными группами.</span><span class="sxs-lookup"><span data-stu-id="4a595-117">This method works best for groups of up to 50,000 users but will also work with larger groups.</span></span>

- <span data-ttu-id="4a595-118">**Используйте [назначение пакетной политики](assign-policies.md#assign-a-policy-to-a-batch-of-users) для назначения политики собраний непосредственно пользователям**.</span><span class="sxs-lookup"><span data-stu-id="4a595-118">**Use [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users) to assign a meeting policy directly to users in bulk**.</span></span> <span data-ttu-id="4a595-119">Вы можете назначить политику до 5 000 пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="4a595-119">You can assign a policy for up to 5,000 users at a time.</span></span> <span data-ttu-id="4a595-120">Если у вас более 5 000 пользователей, вы можете отправить несколько пакетов.</span><span class="sxs-lookup"><span data-stu-id="4a595-120">If you have more than 5,000 users, you can submit multiple batches.</span></span> <span data-ttu-id="4a595-121">При использовании этого метода для новых пользователей потребуется повторное выполнение задания, чтобы назначить политику новым пользователям.</span><span class="sxs-lookup"><span data-stu-id="4a595-121">With this method, when you have new users, you'll need to re-run the batch assignment to assign the policy to those new users.</span></span>

<span data-ttu-id="4a595-122">Помните, что в Teams пользователи автоматически получают глобальную политику (по умолчанию на уровне Организации) для типа политики Teams, если вы не создали и не назначаете пользовательскую политику.</span><span class="sxs-lookup"><span data-stu-id="4a595-122">Remember that in Teams, users automatically get the Global (Org-wide default) policy for a Teams policy type unless you create and assign a custom policy.</span></span> <span data-ttu-id="4a595-123">Поскольку заполнение учащихся часто является большим набором пользователей, и они часто получают наиболее строгие параметры, мы рекомендуем сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="4a595-123">Because the student population is often the largest set of users and they often receive the most restrictive settings, we recommend that you do the following:</span></span>

- <span data-ttu-id="4a595-124">Создание настраиваемой политики, которая позволяет выполнять базовые функции, такие как личное чат и планирование собраний, а также назначать политику сотрудникам и преподавателям.</span><span class="sxs-lookup"><span data-stu-id="4a595-124">Create a custom policy that allows core capabilities such as private chat and meeting scheduling and assign the policy to your staff and educators.</span></span>
- <span data-ttu-id="4a595-125">Назначение настраиваемой политики вашим сотрудникам и преподавателям.</span><span class="sxs-lookup"><span data-stu-id="4a595-125">Assign the custom policy to your staff and educators.</span></span>
- <span data-ttu-id="4a595-126">Измените и примените глобальную политику (по умолчанию на уровне Организации), чтобы ограничить возможности для учащихся.</span><span class="sxs-lookup"><span data-stu-id="4a595-126">Edit and apply the Global (Org-wide default) policy to restrict capabilities for students.</span></span>

<span data-ttu-id="4a595-127">Имейте в виду, что глобальная политика будет применяться ко всем пользователям в вашем учебном заведении, пока не будет создана пользовательская политика, и вы сможете назначить ее вашим сотрудникам и преподавателям.</span><span class="sxs-lookup"><span data-stu-id="4a595-127">Keep in mind that the Global policy will apply to all users in your school until you create a custom policy and assign it to your staff and educators.</span></span>

<span data-ttu-id="4a595-128">В этом учебнике учащиеся получат глобальную политику собраний, и мы назначением настраиваемой политики собраний с именем EducatorMeetingPolicy для сотрудников и преподавателей.</span><span class="sxs-lookup"><span data-stu-id="4a595-128">In this tutorial, students will get the Global meeting policy and we'll assign a custom meeting policy named EducatorMeetingPolicy to staff and educators.</span></span> <span data-ttu-id="4a595-129">Предполагается, что вы изменили глобальную политику для настройки параметров собрания для учащихся и [создали специальную политику](policy-packages-edu.md) , которая определяет процесс собрания для персонала и преподавателей.</span><span class="sxs-lookup"><span data-stu-id="4a595-129">We assume that you've edited the Global policy to tailor meeting settings for students and [created a custom policy](policy-packages-edu.md) that defines the meeting experience for staff and educators.</span></span>

![Снимок экрана: страница "политики собрания" в центре администрирования Teams](media/batch-group-policy-assignment-edu-meeting-policies.png)

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="4a595-131">Назначение политики группе</span><span class="sxs-lookup"><span data-stu-id="4a595-131">Assign a policy to a group</span></span>

<span data-ttu-id="4a595-132">Выполните указанные ниже действия, чтобы создать группу безопасности для сотрудников и преподавателей, а затем назначить специальную политику собраний с именем EducatorMeetingPolicy в эту группу безопасности.</span><span class="sxs-lookup"><span data-stu-id="4a595-132">Follow these steps to create a security group for your staff and educators, and then assign a custom meeting policy named EducatorMeetingPolicy to that security group.</span></span>

### <a name="before-you-get-started"></a><span data-ttu-id="4a595-133">С чего начать</span><span class="sxs-lookup"><span data-stu-id="4a595-133">Before you get started</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4a595-134">При назначении политики группе Назначение политики распространяется на пользователей группы в соответствии с правилами приоритета.</span><span class="sxs-lookup"><span data-stu-id="4a595-134">When you assign a policy to a group, the policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="4a595-135">Например, если пользователю напрямую назначается политика (отдельно или по назначению), эта политика имеет приоритет над политикой, унаследованной от группы.</span><span class="sxs-lookup"><span data-stu-id="4a595-135">For example, if a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence over a policy that's inherited from a group.</span></span> <span data-ttu-id="4a595-136">Кроме того, это означает, что если пользователю назначена политика собрания, которой вы непосредственно назначили, вам придется удалить эту политику для этого пользователя, прежде чем она сможет наследовать политику собраний из группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="4a595-136">This also means that if a user has a meeting policy that was directly assigned to them, you'll have to remove that meeting policy from the user before they can inherit a meeting policy from a security group.</span></span>

<span data-ttu-id="4a595-137">Прежде чем приступить к работе, важно понимать [правила приоритета](assign-policies.md#precedence-rules) и [ранжирование назначения групп](assign-policies.md#group-assignment-ranking).</span><span class="sxs-lookup"><span data-stu-id="4a595-137">Before you get started, it's important to understand [precedence rules](assign-policies.md#precedence-rules) and [group assignment ranking](assign-policies.md#group-assignment-ranking).</span></span> <span data-ttu-id="4a595-138">**Убедитесь, что вы прочитали и понимаете принципы, необходимые для [назначения политик группам](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)**.</span><span class="sxs-lookup"><span data-stu-id="4a595-138">**Make sure that you read and understand the concepts in [What you need to know about policy assignment to groups](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)**.</span></span>

<span data-ttu-id="4a595-139">Вам потребуется выполнить все эти действия для сотрудников и преподавателей, чтобы наследовать политику собраний из группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="4a595-139">You'll need to complete all these steps for your staff and educators to inherit a meeting policy from a security group.</span></span>

1. <span data-ttu-id="4a595-140">[Создание групп безопасности](#create-security-groups).</span><span class="sxs-lookup"><span data-stu-id="4a595-140">[Create security groups](#create-security-groups).</span></span>
2. <span data-ttu-id="4a595-141">[Назначение политики группе безопасности](#assign-a-policy-to-a-security-group).</span><span class="sxs-lookup"><span data-stu-id="4a595-141">[Assign a policy to a security group](#assign-a-policy-to-a-security-group).</span></span>
3. <span data-ttu-id="4a595-142">[Удаление политики, назначенной пользователям напрямую](#remove-a-policy-that-was-directly-assigned-to-users).</span><span class="sxs-lookup"><span data-stu-id="4a595-142">[Remove a policy that was directly assigned to users](#remove-a-policy-that-was-directly-assigned-to-users).</span></span>

### <a name="create-security-groups"></a><span data-ttu-id="4a595-143">Создание групп безопасности</span><span class="sxs-lookup"><span data-stu-id="4a595-143">Create security groups</span></span>

<span data-ttu-id="4a595-144">Сначала создайте группу безопасности для своих сотрудников и преподавателей.</span><span class="sxs-lookup"><span data-stu-id="4a595-144">First, create a security group for your staff and educators.</span></span>

<span data-ttu-id="4a595-145">С помощью [School Data Sync](https://docs.microsoft.com/SchoolDataSync/) (SDS) вы можете легко создавать в учебном заведении [преподавателей и студентов групп безопасности](https://docs.microsoft.com/SchoolDataSync/edu-security-groups) .</span><span class="sxs-lookup"><span data-stu-id="4a595-145">With [School Data Sync](https://docs.microsoft.com/SchoolDataSync/) (SDS), you can [easily create security groups educators and students](https://docs.microsoft.com/SchoolDataSync/edu-security-groups) in your school.</span></span> <span data-ttu-id="4a595-146">Рекомендуется использовать SDS для создания групп безопасности, необходимых для управления политиками для учебного заведения.</span><span class="sxs-lookup"><span data-stu-id="4a595-146">We recommend that you use SDS to create the security groups you need to manage policies for your school.</span></span>

<span data-ttu-id="4a595-147">Если вы не можете развернуть SDS в среде, используйте [этот сценарий PowerShell](scripts/powershell-script-security-groups-edu.md) для создания двух групп безопасности: для всех сотрудников и преподавателей, которым назначена лицензия факультета, а другая — для всех студентов, у которых есть лицензия на учащийся.</span><span class="sxs-lookup"><span data-stu-id="4a595-147">If you're unable to deploy SDS within your environment, use [this PowerShell script](scripts/powershell-script-security-groups-edu.md) to create two security groups, one for all staff and educators who have a Faculty license assigned and another for all students who have a Student license assigned.</span></span> <span data-ttu-id="4a595-148">Для обеспечения актуальности и актуальности групп вам потребуется выполнить этот сценарий регулярно.</span><span class="sxs-lookup"><span data-stu-id="4a595-148">You'll need to run this script routinely to keep the groups fresh and up to date.</span></span>

### <a name="assign-a-policy-to-a-security-group"></a><span data-ttu-id="4a595-149">Назначение политики группе безопасности</span><span class="sxs-lookup"><span data-stu-id="4a595-149">Assign a policy to a security group</span></span>

#### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="4a595-150">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4a595-150">Using the Microsoft Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="4a595-151">В настоящее время назначение политики для групп, использующих центр администрирования Microsoft Teams, доступно только для политики звонков в Teams, политики для приема звонков в Teams, политики Teams, политики собрания Teams и политики обмена сообщениями в группе Teams.</span><span class="sxs-lookup"><span data-stu-id="4a595-151">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="4a595-152">Для других типов политик используйте PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4a595-152">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="4a595-153">В левой области навигации центра администрирования Microsoft Teams **перейдите в раздел**  >  **политики собраний по собраниям**.</span><span class="sxs-lookup"><span data-stu-id="4a595-153">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="4a595-154">Перейдите на вкладку **назначение групповой политики** .</span><span class="sxs-lookup"><span data-stu-id="4a595-154">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="4a595-155">Нажмите кнопку **Добавить группу**, а затем в области **Назначение политики для группировки** выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="4a595-155">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>

    ![Снимок экрана: область "Редактирование параметров" с политикой собраний](media/batch-group-policy-assignment-edu-group.png)
    1. <span data-ttu-id="4a595-157">В диалоговом окне **Выбор группы** найдите и добавьте группу безопасности, которая включает в себя ваших сотрудников и преподавателей.</span><span class="sxs-lookup"><span data-stu-id="4a595-157">In the **Select a group** box, search for and add the security group that contains your staff and educators.</span></span>
    2. <span data-ttu-id="4a595-158">В поле **выберите ранг** введите **1**.</span><span class="sxs-lookup"><span data-stu-id="4a595-158">In the **Select rank** box, enter **1**.</span></span>
    3. <span data-ttu-id="4a595-159">В диалоговом окне **Выбор политики** выберите **EducatorMeetingPolicy**.</span><span class="sxs-lookup"><span data-stu-id="4a595-159">In the **Select a policy** box, select **EducatorMeetingPolicy**.</span></span>
    4. <span data-ttu-id="4a595-160">Нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="4a595-160">Select **Apply**.</span></span>

<span data-ttu-id="4a595-161">Чтобы удалить назначение групповой политики, на вкладке **назначение групповой политики** на странице Политика выберите назначение группы и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="4a595-161">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="4a595-162">Чтобы изменить ранжирование назначения группы, необходимо сначала удалить назначение групповой политики.</span><span class="sxs-lookup"><span data-stu-id="4a595-162">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="4a595-163">Затем выполните описанные выше действия, чтобы назначить политику группе.</span><span class="sxs-lookup"><span data-stu-id="4a595-163">Then, follow the steps above to assign the policy to a group.</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="4a595-164">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a595-164">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="4a595-165">В настоящее время назначение политики для групп, использующих PowerShell, недоступно для всех типов политики Teams.</span><span class="sxs-lookup"><span data-stu-id="4a595-165">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="4a595-166">Ознакомьтесь со списком " [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) " для списка поддерживаемых типов политики.</span><span class="sxs-lookup"><span data-stu-id="4a595-166">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="4a595-167">Установка и подключение к модулю Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a595-167">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="4a595-168">Выполните указанные ниже действия, чтобы установить [модуль PowerShell Teams](https://www.powershellgallery.com/packages/MicrosoftTeams) (если он еще не установлен).</span><span class="sxs-lookup"><span data-stu-id="4a595-168">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="4a595-169">Убедитесь, что вы установили версию 1.0.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="4a595-169">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="4a595-170">Выполните указанные ниже действия, чтобы подключиться к Teams и начать сеанс.</span><span class="sxs-lookup"><span data-stu-id="4a595-170">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="4a595-171">Когда вам будет предложено, войдите в систему с помощью учетных данных администратора.</span><span class="sxs-lookup"><span data-stu-id="4a595-171">When you're prompted, sign in using your admin credentials.</span></span>

##### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="4a595-172">Назначение политики группе</span><span class="sxs-lookup"><span data-stu-id="4a595-172">Assign a policy to a group</span></span>

<span data-ttu-id="4a595-173">Выполните указанные ниже действия, чтобы назначить политику собраний с именем EducatorMeetingPolicy группе безопасности, которая включает в себя ваших сотрудников и преподавателей, и установите для ранжирования назначение значение 1.</span><span class="sxs-lookup"><span data-stu-id="4a595-173">Run the following to assign the meeting policy named EducatorMeetingPolicy to the security group that contains your staff and educators and set the assignment ranking to 1.</span></span> <span data-ttu-id="4a595-174">Вы можете указать группу безопасности, используя идентификатор объекта, адрес SIP или адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="4a595-174">You can specify a security group by using the object Id, Session Initiation Protocol (SIP) address, or email address.</span></span> <span data-ttu-id="4a595-175">В этом примере мы используем адрес электронной почты (staff-faculty@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="4a595-175">In this example, we use an email address (staff-faculty@contoso.com).</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com -PolicyType TeamsMeetingPolicy -PolicyName "EducatorMeetingPolicy" -Rank 1
```

### <a name="remove-a-policy-that-was-directly-assigned-to-users"></a><span data-ttu-id="4a595-176">Удаление политики, назначенной пользователям напрямую</span><span class="sxs-lookup"><span data-stu-id="4a595-176">Remove a policy that was directly assigned to users</span></span>

<span data-ttu-id="4a595-177">Следует помнить, что если пользователю явно назначена политика (отдельно или по назначению), она имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="4a595-177">Remember that if a user was directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="4a595-178">Это означает, что если пользователю назначена политика собраний, которой вы непосредственно назначили, вам придется удалить эту политику на собрании от пользователя, прежде чем она сможет наследовать политику собраний из группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="4a595-178">This means that if a user has a meeting policy that was directly assigned to them, you'll have to remove that meeting policy from the user before they can inherit a meeting policy from a security group.</span></span>

<span data-ttu-id="4a595-179">Чтобы узнать больше, ознакомьтесь [со статьей что нужно знать о назначении политики группам](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups).</span><span class="sxs-lookup"><span data-stu-id="4a595-179">To learn more, see [What you need to know about policy assignment to groups](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups).</span></span>

<span data-ttu-id="4a595-180">Выполните указанные ниже действия, чтобы удалить политику собраний, которая была непосредственно назначена вашим сотрудникам и преподавателям.</span><span class="sxs-lookup"><span data-stu-id="4a595-180">Follow these steps to remove the meeting policy that was directly assigned to your staff and educators.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="4a595-181">Установка и подключение к модулю Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a595-181">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="4a595-182">Выполните указанные ниже действия, чтобы установить [модуль PowerShell Teams](https://www.powershellgallery.com/packages/MicrosoftTeams) (если он еще не установлен).</span><span class="sxs-lookup"><span data-stu-id="4a595-182">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="4a595-183">Убедитесь, что вы установили версию 1.0.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="4a595-183">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="4a595-184">Выполните указанные ниже действия, чтобы подключиться к Teams и начать сеанс.</span><span class="sxs-lookup"><span data-stu-id="4a595-184">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```
<span data-ttu-id="4a595-185">Когда вам будет предложено, войдите в систему с помощью учетных данных администратора, используемых для подключения к Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4a595-185">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

#### <a name="unassign-a-policy-that-was-directly-assigned-to-users"></a><span data-ttu-id="4a595-186">Отмена назначения политики, непосредственно назначенной пользователям</span><span class="sxs-lookup"><span data-stu-id="4a595-186">Unassign a policy that was directly assigned to users</span></span>

<span data-ttu-id="4a595-187">Выполните описанные ниже действия, чтобы удалить политику собраний для пользователей, которым назначена эта политика напрямую.</span><span class="sxs-lookup"><span data-stu-id="4a595-187">Run the following to remove a meeting policy from users who were directly assigned that policy.</span></span> <span data-ttu-id="4a595-188">Вы можете указать пользователей по адресу электронной почты или ИДЕНТИФИКАТОРу объекта.</span><span class="sxs-lookup"><span data-stu-id="4a595-188">You can specify users by email address or object ID.</span></span>

<span data-ttu-id="4a595-189">В этом примере политика собраний удаляется от пользователей, заданных их адресом электронной почты.</span><span class="sxs-lookup"><span data-stu-id="4a595-189">In this example, the meeting policy is removed from users specified by their email address.</span></span>

```powershell
$users_ids = @("reda@contoso.com", "nikica@contoso.com", "jamie@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

<span data-ttu-id="4a595-190">В этом примере политика собраний удаляется из списка пользователей в текстовом файле с именем user_ids.txt.</span><span class="sxs-lookup"><span data-stu-id="4a595-190">In this example, the meeting policy is removed from the list of users in a text file named user_ids.txt.</span></span> 

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

##### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="4a595-191">Получение назначений политики для группы</span><span class="sxs-lookup"><span data-stu-id="4a595-191">Get policy assignments for a group</span></span>

<span data-ttu-id="4a595-192">Выполните указанные ниже действия, чтобы просмотреть все политики, назначенные определенной группе безопасности.</span><span class="sxs-lookup"><span data-stu-id="4a595-192">Run the following to see all the policies assigned to a specific security group.</span></span> <span data-ttu-id="4a595-193">Обратите внимание, что группы всегда записываются в соответствии с их идентификатором группы, даже если для назначения политики был использован адрес SIP или адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="4a595-193">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com

```

##### <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="4a595-194">Получение политик, назначенных пользователю</span><span class="sxs-lookup"><span data-stu-id="4a595-194">Get the policies assigned to a user</span></span>

<span data-ttu-id="4a595-195">Выполните указанные ниже действия, чтобы просмотреть все политики, назначенные определенному пользователю.</span><span class="sxs-lookup"><span data-stu-id="4a595-195">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="4a595-196">В следующем примере показано, как получить политики, назначенные reda@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="4a595-196">The following example shows you how to get the policies that are assigned to reda@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity reda@contoso.com
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="4a595-197">Назначение политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="4a595-197">Assign a policy to a batch of users</span></span>

<span data-ttu-id="4a595-198">Выполните эти действия, чтобы назначить настраиваемую политику собраний с именем EducatorMeetingPolicy непосредственно сотрудникам и преподавателям в массовом режиме.</span><span class="sxs-lookup"><span data-stu-id="4a595-198">Follow these steps to assign a custom meeting policy named EducatorMeetingPolicy directly to your staff and educators in bulk.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="4a595-199">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a595-199">Using PowerShell</span></span>

#### <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a><span data-ttu-id="4a595-200">Соединение с модулем Azure AD PowerShell для Graph и модулем Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a595-200">Connect to the Azure AD PowerShell for Graph module and the Teams PowerShell module</span></span>

<span data-ttu-id="4a595-201">Перед выполнением действий, описанных в этой статье, необходимо установить и подключить модуль Azure AD PowerShell для Graph (для идентификации пользователей по назначенным им лицензиям) и модуль Microsoft Teams PowerShell (для назначения политик этим пользователям).</span><span class="sxs-lookup"><span data-stu-id="4a595-201">Before you perform the steps in this article, you'll need to install and connect to the Azure AD PowerShell for Graph module (to identify users by their assigned licenses) and the Microsoft Teams PowerShell module (to assign the policies to those users).</span></span>

##### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a><span data-ttu-id="4a595-202">Установка и подключение к модулю Azure AD PowerShell для Graph</span><span class="sxs-lookup"><span data-stu-id="4a595-202">Install and connect to the Azure AD PowerShell for Graph module</span></span>

<span data-ttu-id="4a595-203">Откройте командную команду Windows PowerShell с повышенными привилегиями (запустите Windows PowerShell от имени администратора), а затем выполните указанные ниже действия, чтобы установить модуль Azure Active Directory PowerShell для Graph.</span><span class="sxs-lookup"><span data-stu-id="4a595-203">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator), and then run the following to install the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Install-Module -Name AzureAD
```

<span data-ttu-id="4a595-204">Выполните указанные ниже действия, чтобы подключиться к Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4a595-204">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="4a595-205">Когда вам будет предложено, войдите в систему с помощью учетных данных администратора.</span><span class="sxs-lookup"><span data-stu-id="4a595-205">When you're prompted, sign in using your admin credentials.</span></span>

<span data-ttu-id="4a595-206">Дополнительные сведения можно найти в разделе [подключение с помощью модуля Azure Active Directory PowerShell для Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="4a595-206">To learn more, see [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="4a595-207">Установка и подключение к модулю Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a595-207">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="4a595-208">Выполните указанные ниже действия, чтобы установить [модуль PowerShell Teams](https://www.powershellgallery.com/packages/MicrosoftTeams) (если он еще не установлен).</span><span class="sxs-lookup"><span data-stu-id="4a595-208">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="4a595-209">Убедитесь, что вы установили версию 1.0.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="4a595-209">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="4a595-210">Выполните указанные ниже действия, чтобы подключиться к Teams и начать сеанс.</span><span class="sxs-lookup"><span data-stu-id="4a595-210">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```
<span data-ttu-id="4a595-211">Когда вам будет предложено, войдите в систему с помощью учетных данных администратора, используемых для подключения к Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4a595-211">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

#### <a name="identify-your-users"></a><span data-ttu-id="4a595-212">Определение пользователей</span><span class="sxs-lookup"><span data-stu-id="4a595-212">Identify your users</span></span>

<span data-ttu-id="4a595-213">Сначала выполните указанные ниже действия, чтобы идентифицировать сотрудников и преподавателей по типу лицензии.</span><span class="sxs-lookup"><span data-stu-id="4a595-213">First, run the following to identify your staff and educators by license type.</span></span> <span data-ttu-id="4a595-214">В этой статье рассказывается о том, какие SKU используются в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="4a595-214">This tells you what SKUs are in use in your organization.</span></span> <span data-ttu-id="4a595-215">Затем вы можете идентифицировать сотрудников и преподавателей, которым назначены номера SKU факультета.</span><span class="sxs-lookup"><span data-stu-id="4a595-215">You can then identify staff and educators that have a Faculty SKU assigned.</span></span>

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

<span data-ttu-id="4a595-216">Возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="4a595-216">Which returns:</span></span>

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

<span data-ttu-id="4a595-217">В этом примере вывод показывает, что лицензия факультета SkuId — "e97c048c-37a4-45fb-AB50-922fbf07a370".</span><span class="sxs-lookup"><span data-stu-id="4a595-217">In this example, the output shows that the Faculty license SkuId is "e97c048c-37a4-45fb-ab50-922fbf07a370".</span></span>

> [!NOTE]
> <span data-ttu-id="4a595-218">Список материалов для образования и номер SKU можно найти в [справочнике по образованию SKU](sku-reference-edu.md).</span><span class="sxs-lookup"><span data-stu-id="4a595-218">To see a list of Education SKUs and SKU IDs, see [Education SKU reference](sku-reference-edu.md).</span></span>

<span data-ttu-id="4a595-219">Затем выполните указанные ниже действия, чтобы идентифицировать пользователей, у которых есть лицензия, и собирать их вместе.</span><span class="sxs-lookup"><span data-stu-id="4a595-219">Next, we run the following to identify the users that have this license and collect them all together.</span></span>

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

#### <a name="assign-a-policy-in-bulk"></a><span data-ttu-id="4a595-220">Массовое назначение политики</span><span class="sxs-lookup"><span data-stu-id="4a595-220">Assign a policy in bulk</span></span>

<span data-ttu-id="4a595-221">Теперь пользователям можно назначать соответствующие политики.</span><span class="sxs-lookup"><span data-stu-id="4a595-221">Now, we assign the appropriate policies to users in bulk.</span></span> <span data-ttu-id="4a595-222">Максимальное количество пользователей, которым можно назначить или обновлять политики, составляет 5 000 за один раз.</span><span class="sxs-lookup"><span data-stu-id="4a595-222">The maximum number of users for which you can assign or update policies is 5,000 at a time.</span></span> <span data-ttu-id="4a595-223">Например, если у вас более 5 000 сотрудников и преподавателей, вам нужно будет отправить несколько пакетов.</span><span class="sxs-lookup"><span data-stu-id="4a595-223">For example, if you have more than 5,000 staff and educators, you'll need to submit multiple batches.</span></span>

<span data-ttu-id="4a595-224">Выполните указанные ниже действия, чтобы назначить настраиваемую политику собраний с именем EducatorMeetingPolicy для сотрудников и преподавателей.</span><span class="sxs-lookup"><span data-stu-id="4a595-224">Run the following to assign a custom meeting policy named EducatorMeetingPolicy to your staff and educators.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> <span data-ttu-id="4a595-225">Чтобы назначить другой тип политики в массовом режиме, например TeamsMessagingPolicy, необходимо изменить ```PolicyType``` политику, которую вы назначаете, и присвоить ей ```PolicyName``` имя политики.</span><span class="sxs-lookup"><span data-stu-id="4a595-225">To assign a different policy type in bulk, like TeamsMessagingPolicy, you'll need to change ```PolicyType``` to the policy that you're assigning and ```PolicyName``` to the policy name.</span></span>

#### <a name="get-the-status-of-a-bulk-assignment"></a><span data-ttu-id="4a595-226">Получение состояния массового назначения</span><span class="sxs-lookup"><span data-stu-id="4a595-226">Get the status of a bulk assignment</span></span>

<span data-ttu-id="4a595-227">Каждое массовое назначение возвращает идентификатор операции, который можно использовать для отслеживания хода выполнения назначений политики или определения возможных сбоев.</span><span class="sxs-lookup"><span data-stu-id="4a595-227">Each bulk assignment returns an operation ID, which you can use to track the progress of the policy assignments or identify any failures that might occur.</span></span> <span data-ttu-id="4a595-228">Например, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="4a595-228">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

<span data-ttu-id="4a595-229">Чтобы просмотреть состояние назначения каждого пользователя в пакетной операции, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="4a595-229">To view the assignment status of each user in the batch operation, run the following.</span></span> <span data-ttu-id="4a595-230">Сведения о каждом пользователе находятся в ```UserState``` свойстве.</span><span class="sxs-lookup"><span data-stu-id="4a595-230">Details of each user are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

#### <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a><span data-ttu-id="4a595-231">Назначение политики в массовом режиме, если у вас более 5 000 пользователей</span><span class="sxs-lookup"><span data-stu-id="4a595-231">Assign a policy in bulk if you have more than 5,000 users</span></span>

<span data-ttu-id="4a595-232">Сначала выполните указанные ниже действия, чтобы узнать, сколько у вас сотрудников и преподавателей.</span><span class="sxs-lookup"><span data-stu-id="4a595-232">First, run the following to see how many staff and educators you have:</span></span>

```powershell
$faculty.count
```

<span data-ttu-id="4a595-233">Вместо того чтобы предоставлять весь список идентификаторов пользователей, выполните указанные ниже действия, чтобы указать первые 5 000, а затем следующие 5 000 и т. д.</span><span class="sxs-lookup"><span data-stu-id="4a595-233">Instead of providing the whole list of user IDs, run the following to specify the first 5,000, and then the next 5,000, and so on.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

<span data-ttu-id="4a595-234">Вы можете изменить диапазон идентификаторов пользователей, пока не дойдете до полного списка пользователей.</span><span class="sxs-lookup"><span data-stu-id="4a595-234">You can change the range of user IDs until you reach the full list of users.</span></span> <span data-ttu-id="4a595-235">Например, введите ```$faculty[0..4999``` первый пакет, ```$faculty[5000..9999``` который используется для второго пакета, введите ```$faculty[10000..14999``` третий пакет и т. д.</span><span class="sxs-lookup"><span data-stu-id="4a595-235">For example, enter ```$faculty[0..4999``` for the first batch, use ```$faculty[5000..9999``` for the second batch, enter ```$faculty[10000..14999``` for the third batch, and so on.</span></span>

#### <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="4a595-236">Получение политик, назначенных пользователю</span><span class="sxs-lookup"><span data-stu-id="4a595-236">Get the policies assigned to a user</span></span>

<span data-ttu-id="4a595-237">Выполните указанные ниже действия, чтобы просмотреть все политики, назначенные определенному пользователю.</span><span class="sxs-lookup"><span data-stu-id="4a595-237">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="4a595-238">В следующем примере показано, как получить политики, назначенные hannah@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="4a595-238">The following example shows you how to get the policies that are assigned to hannah@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a><span data-ttu-id="4a595-239">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="4a595-239">FAQ</span></span>

<span data-ttu-id="4a595-240">**Я не знаком с оболочкой PowerShell для Teams. Где можно найти дополнительные сведения?**</span><span class="sxs-lookup"><span data-stu-id="4a595-240">**I'm not familiar with PowerShell for Teams. Where can I learn more?**</span></span>

<span data-ttu-id="4a595-241">Общие сведения об использовании PowerShell для управления группами можно найти в разделе [Общие сведения о Teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4a595-241">For an overview of using PowerShell to manage Teams, see [Teams PowerShell overview](teams-powershell-overview.md).</span></span> <span data-ttu-id="4a595-242">Дополнительные сведения о командлетах, использованных в этой статье, можно найти в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="4a595-242">For more information about the cmdlets used in this article, see:</span></span>

- [<span data-ttu-id="4a595-243">New-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="4a595-243">New-CsGroupPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)
- [<span data-ttu-id="4a595-244">Get-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="4a595-244">Get-CsGroupPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment)
- [<span data-ttu-id="4a595-245">New-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="4a595-245">New-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="4a595-246">Get-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="4a595-246">Get-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="4a595-247">Get-CsUserPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="4a595-247">Get-CsUserPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)

## <a name="related-topics"></a><span data-ttu-id="4a595-248">См. также</span><span class="sxs-lookup"><span data-stu-id="4a595-248">Related topics</span></span>

- [<span data-ttu-id="4a595-249">Назначение политик пользователям</span><span class="sxs-lookup"><span data-stu-id="4a595-249">Assign policies to your users</span></span>](assign-policies.md)
- [<span data-ttu-id="4a595-250">Политики групп и пакеты политик для образовательных учреждений</span><span class="sxs-lookup"><span data-stu-id="4a595-250">Teams policies and policy packages for Education</span></span>](policy-packages-edu.md)
- [<span data-ttu-id="4a595-251">Управление политиками собраний в Teams</span><span class="sxs-lookup"><span data-stu-id="4a595-251">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
