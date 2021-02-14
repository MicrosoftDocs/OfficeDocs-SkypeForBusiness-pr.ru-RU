---
title: Назначение политик большому набору пользователей в учебном за учебных заведениях
author: cichur
ms.author: v-cichur
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
description: Узнайте, как назначать политики большому набору пользователей в вашем учебном заведении на основе членства в группах или прямо с помощью пакетного задания для удаленного учебного заведения (teleschool, tele-school).
f1keywords: ''
ms.openlocfilehash: afcaba9df0ff745977b84e34683c1bdfcaca0d01
ms.sourcegitcommit: 07afc959fec802db583e7111280d0035fdb6e412
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616943"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a><span data-ttu-id="fd663-103">Назначение политик большому набору пользователей в учебном за учебных заведениях</span><span class="sxs-lookup"><span data-stu-id="fd663-103">Assign policies to large sets of users in your school</span></span>

[!INCLUDE [policy-wizard-edu](includes/policy-wizard-edu.md)]

> [!NOTE]
> <span data-ttu-id="fd663-104">Более крупные истории о назначении политик в Microsoft Teams см. в теме "Назначение политик [пользователям в Teams".](assign-policies.md)</span><span class="sxs-lookup"><span data-stu-id="fd663-104">For the larger story on assigning policies in Microsoft Teams, see [Assign policies to your users in Teams](assign-policies.md).</span></span>

## <a name="overview"></a><span data-ttu-id="fd663-105">Обзор</span><span class="sxs-lookup"><span data-stu-id="fd663-105">Overview</span></span>

<span data-ttu-id="fd663-106">Нужно ли предоставить своим учащимся и преподавателям доступ к различным функциям Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="fd663-106">Do you need to give your students and educators access to different features in Microsoft Teams?</span></span> <span data-ttu-id="fd663-107">Вы можете быстро определить пользователей в организации по типу лицензии, а затем назначить им соответствующую политику.</span><span class="sxs-lookup"><span data-stu-id="fd663-107">You can quickly identify the users in your organization by license type and then assign them the appropriate policy.</span></span> <span data-ttu-id="fd663-108">В этом учебнике показано, как назначить политику собраний большому набору пользователей в вашем учебном за учебных заведениях.</span><span class="sxs-lookup"><span data-stu-id="fd663-108">This tutorial shows you how to assign a meeting policy to large sets of users in your school.</span></span> <span data-ttu-id="fd663-109">Вы можете назначать политики с помощью Центра администрирования Microsoft Teams и PowerShell, и мы покажем вам оба способа.</span><span class="sxs-lookup"><span data-stu-id="fd663-109">You can assign policies using the Microsoft Teams admin center and PowerShell and we'll show you both ways.</span></span>

<span data-ttu-id="fd663-110">Политику собраний можно назначить группе безопасности, участниками или непосредственно пользователями в масштабе с помощью пакетного назначения политики.</span><span class="sxs-lookup"><span data-stu-id="fd663-110">You can assign a meeting policy to a security group that the users are members of or directly to users at scale through a batch policy assignment.</span></span> <span data-ttu-id="fd663-111">После прочтения этой статьи вы сможете следующее.</span><span class="sxs-lookup"><span data-stu-id="fd663-111">You'll learn how to:</span></span>

- <span data-ttu-id="fd663-112">**Назначение [политик группам используется](#assign-a-policy-to-a-group)** для назначения политики собраний группе безопасности (рекомендуется).</span><span class="sxs-lookup"><span data-stu-id="fd663-112">**Use [policy assignment to groups](#assign-a-policy-to-a-group) to assign a meeting policy to a security group (recommended)**.</span></span> <span data-ttu-id="fd663-113">Этот метод позволяет назначать политику на основе членства в группах.</span><span class="sxs-lookup"><span data-stu-id="fd663-113">This method lets you assign a policy based on group membership.</span></span> <span data-ttu-id="fd663-114">Политику можно назначить группе безопасности или списку рассылки.</span><span class="sxs-lookup"><span data-stu-id="fd663-114">You can assign a policy to a security group or distribution list.</span></span> <span data-ttu-id="fd663-115">По мере того как участники добавляются в группу или удаляются из нее, унаследованные назначения политики обновляются соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="fd663-115">As members are added to or removed from the group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="fd663-116">Мы рекомендуем использовать этот метод, так как он сокращает время на управление политиками для новых пользователей или изменение ролей пользователей.</span><span class="sxs-lookup"><span data-stu-id="fd663-116">We recommend you use this method because it reduces the time to manage policies for new users or when users' roles change.</span></span> <span data-ttu-id="fd663-117">Этот метод лучше всего работает для групп до 50 000 пользователей, но также работает с более крупными группами.</span><span class="sxs-lookup"><span data-stu-id="fd663-117">This method works best for groups of up to 50,000 users but will also work with larger groups.</span></span>

- <span data-ttu-id="fd663-118">**Используйте [назначение пакетной политики](assign-policies.md#assign-a-policy-to-a-batch-of-users) для массового назначения политики собраний пользователям.**</span><span class="sxs-lookup"><span data-stu-id="fd663-118">**Use [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users) to assign a meeting policy directly to users in bulk**.</span></span> <span data-ttu-id="fd663-119">Одновременно можно назначить политику для 5000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="fd663-119">You can assign a policy for up to 5,000 users at a time.</span></span> <span data-ttu-id="fd663-120">Если у вас более 5000 пользователей, можно отправить несколько пакетов.</span><span class="sxs-lookup"><span data-stu-id="fd663-120">If you have more than 5,000 users, you can submit multiple batches.</span></span> <span data-ttu-id="fd663-121">При этом способе при новых пользователях потребуется повторно запустить пакетное назначение, чтобы назначить политику новым пользователям.</span><span class="sxs-lookup"><span data-stu-id="fd663-121">With this method, when you have new users, you'll need to re-run the batch assignment to assign the policy to those new users.</span></span>

<span data-ttu-id="fd663-122">Помните, что в Teams пользователи автоматически получают глобальную (по умолчанию в организации) политику для типа политики Teams, если вы не создали и не назначили ее.</span><span class="sxs-lookup"><span data-stu-id="fd663-122">Remember that in Teams, users automatically get the Global (Org-wide default) policy for a Teams policy type unless you create and assign a custom policy.</span></span> <span data-ttu-id="fd663-123">Так как среди учащихся часто самый большой набор пользователей и они часто получают самые строгие параметры, рекомендуем сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="fd663-123">Because the student population is often the largest set of users and they often receive the most restrictive settings, we recommend that you do the following:</span></span>

- <span data-ttu-id="fd663-124">Создайте настраиваемую политику, которая обеспечивает основные возможности, например приватный чат и планирование собраний, и назначьте ее сотрудникам и преподавателям.</span><span class="sxs-lookup"><span data-stu-id="fd663-124">Create a custom policy that allows core capabilities such as private chat and meeting scheduling and assign the policy to your staff and educators.</span></span>
- <span data-ttu-id="fd663-125">Назначьте настраиваемую политику своим сотрудникам и преподавателям.</span><span class="sxs-lookup"><span data-stu-id="fd663-125">Assign the custom policy to your staff and educators.</span></span>
- <span data-ttu-id="fd663-126">Изменение и применение глобальной политики (по умолчанию в организации) для ограничения возможностей учащихся.</span><span class="sxs-lookup"><span data-stu-id="fd663-126">Edit and apply the Global (Org-wide default) policy to restrict capabilities for students.</span></span>

<span data-ttu-id="fd663-127">Имейте в виду, что глобальная политика будет применяться для всех пользователей в вашем учебном за учебных заведениях, пока вы не создайте настраиваемую политику и не назначите ее сотрудникам и преподавателям.</span><span class="sxs-lookup"><span data-stu-id="fd663-127">Keep in mind that the Global policy will apply to all users in your school until you create a custom policy and assign it to your staff and educators.</span></span>

<span data-ttu-id="fd663-128">В этом учебнике учащиеся получат глобальную политику собраний, и мы назначим сотрудникам и преподавателям настраиваемую политику собраний с именем EducatorMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="fd663-128">In this tutorial, students will get the Global meeting policy and we'll assign a custom meeting policy named EducatorMeetingPolicy to staff and educators.</span></span> <span data-ttu-id="fd663-129">Мы предполагаем, что вы вировали глобальную политику для [](policy-packages-edu.md) настройки параметров собраний для учащихся и создали настраиваемую политику, которая определяет возможности проведения собраний для персонала и преподавателей.</span><span class="sxs-lookup"><span data-stu-id="fd663-129">We assume that you've edited the Global policy to tailor meeting settings for students and [created a custom policy](policy-packages-edu.md) that defines the meeting experience for staff and educators.</span></span>

![Снимок экрана: страница "Политики собраний" в Центре администрирования Teams](media/batch-group-policy-assignment-edu-meeting-policies.png)

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="fd663-131">Назначение политики группе</span><span class="sxs-lookup"><span data-stu-id="fd663-131">Assign a policy to a group</span></span>

<span data-ttu-id="fd663-132">Выполните эти действия, чтобы создать группу безопасности для преподавателей и преподавателей, а затем назначить для нее настраиваемую политику собраний с именем EducatorMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="fd663-132">Follow these steps to create a security group for your staff and educators, and then assign a custom meeting policy named EducatorMeetingPolicy to that security group.</span></span>

### <a name="before-you-get-started"></a><span data-ttu-id="fd663-133">С чего начать</span><span class="sxs-lookup"><span data-stu-id="fd663-133">Before you get started</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fd663-134">При назначении политики группе назначение политики распространяется на ее участников в соответствии с правилами приоритета.</span><span class="sxs-lookup"><span data-stu-id="fd663-134">When you assign a policy to a group, the policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="fd663-135">Например, если пользователю непосредственно назначена политика (по отдельности или через пакетное назначение), она имеет приоритет над политикой, наследуемой от группы.</span><span class="sxs-lookup"><span data-stu-id="fd663-135">For example, if a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence over a policy that's inherited from a group.</span></span> <span data-ttu-id="fd663-136">Это также означает, что если пользователю назначена политика собрания, необходимо удалить ее, прежде чем он сможет наследовать политику собрания от группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="fd663-136">This also means that if a user has a meeting policy that was directly assigned to them, you'll have to remove that meeting policy from the user before they can inherit a meeting policy from a security group.</span></span>

<span data-ttu-id="fd663-137">Прежде чем начать, важно разобраться [](assign-policies.md#precedence-rules) в правилах приоритета и ранжирования [заданий групп.](assign-policies.md#group-assignment-ranking)</span><span class="sxs-lookup"><span data-stu-id="fd663-137">Before you get started, it's important to understand [precedence rules](assign-policies.md#precedence-rules) and [group assignment ranking](assign-policies.md#group-assignment-ranking).</span></span> <span data-ttu-id="fd663-138">**Обязательно ознакомьтесь с понятиями, [](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)** которые необходимо знать о назначении политик группам.</span><span class="sxs-lookup"><span data-stu-id="fd663-138">**Make sure that you read and understand the concepts in [What you need to know about policy assignment to groups](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)**.</span></span>

<span data-ttu-id="fd663-139">Вам потребуется выполнить все эти действия, чтобы наследовать политику собрания от группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="fd663-139">You'll need to complete all these steps for your staff and educators to inherit a meeting policy from a security group.</span></span>

1. <span data-ttu-id="fd663-140">[Создание групп безопасности.](#create-security-groups)</span><span class="sxs-lookup"><span data-stu-id="fd663-140">[Create security groups](#create-security-groups).</span></span>
2. <span data-ttu-id="fd663-141">[Назначьте политику группе безопасности.](#assign-a-policy-to-a-security-group)</span><span class="sxs-lookup"><span data-stu-id="fd663-141">[Assign a policy to a security group](#assign-a-policy-to-a-security-group).</span></span>
3. <span data-ttu-id="fd663-142">[Удаление политики, которая была непосредственно назначена пользователям.](#remove-a-policy-that-was-directly-assigned-to-users)</span><span class="sxs-lookup"><span data-stu-id="fd663-142">[Remove a policy that was directly assigned to users](#remove-a-policy-that-was-directly-assigned-to-users).</span></span>

### <a name="create-security-groups"></a><span data-ttu-id="fd663-143">Создание групп безопасности</span><span class="sxs-lookup"><span data-stu-id="fd663-143">Create security groups</span></span>

<span data-ttu-id="fd663-144">Сначала создайте группу безопасности для сотрудников и преподавателей.</span><span class="sxs-lookup"><span data-stu-id="fd663-144">First, create a security group for your staff and educators.</span></span>

<span data-ttu-id="fd663-145">С [помощью School Data Sync](https://docs.microsoft.com/SchoolDataSync/) (SDS) вы можете легко создавать группы безопасности для преподавателей и [учащихся](https://docs.microsoft.com/SchoolDataSync/edu-security-groups) в вашем учебном за учебных заведениях.</span><span class="sxs-lookup"><span data-stu-id="fd663-145">With [School Data Sync](https://docs.microsoft.com/SchoolDataSync/) (SDS), you can [easily create security groups educators and students](https://docs.microsoft.com/SchoolDataSync/edu-security-groups) in your school.</span></span> <span data-ttu-id="fd663-146">Мы рекомендуем использовать SDS для создания групп безопасности, необходимых для управления политиками для вашего учебного заведения.</span><span class="sxs-lookup"><span data-stu-id="fd663-146">We recommend that you use SDS to create the security groups you need to manage policies for your school.</span></span>

<span data-ttu-id="fd663-147">Если вам не удается развернуть SDS в своей среде, используйте этот сценарий [PowerShell,](scripts/powershell-script-security-groups-edu.md) чтобы создать две группы безопасности: одну для всех сотрудников и преподавателей, которым назначена преподавательская лицензия, а другую — для всех студентов, которым назначена лицензия.</span><span class="sxs-lookup"><span data-stu-id="fd663-147">If you're unable to deploy SDS within your environment, use [this PowerShell script](scripts/powershell-script-security-groups-edu.md) to create two security groups, one for all staff and educators who have a Faculty license assigned and another for all students who have a Student license assigned.</span></span> <span data-ttu-id="fd663-148">Вам потребуется регулярно запускать этот сценарий, чтобы группы всегда были в курсе всех.</span><span class="sxs-lookup"><span data-stu-id="fd663-148">You'll need to run this script routinely to keep the groups fresh and up to date.</span></span>

### <a name="assign-a-policy-to-a-security-group"></a><span data-ttu-id="fd663-149">Назначение политики группе безопасности</span><span class="sxs-lookup"><span data-stu-id="fd663-149">Assign a policy to a security group</span></span>

#### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="fd663-150">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fd663-150">Using the Microsoft Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="fd663-151">В настоящее время назначение политик группам с помощью Центра администрирования Microsoft Teams доступно только для политик звонков Teams, политики в парке звонков Teams, политики Teams, политики трансляций Teams, политики собраний Teams и политики обмена сообщениями Teams.</span><span class="sxs-lookup"><span data-stu-id="fd663-151">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="fd663-152">Для других типов политик используйте PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd663-152">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="fd663-153">В левой области навигации Центра администрирования Microsoft Teams перейдите **к** политикам собраний  >  **собраний.**</span><span class="sxs-lookup"><span data-stu-id="fd663-153">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="fd663-154">Выберите **вкладку назначения групповой политики.**</span><span class="sxs-lookup"><span data-stu-id="fd663-154">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="fd663-155">Выберите **"Добавить группу",** а затем в области "Назначение политики группе" сделайте следующее: </span><span class="sxs-lookup"><span data-stu-id="fd663-155">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>

    ![Снимок экрана: области "Изменение параметров" с политикой собрания](media/batch-group-policy-assignment-edu-group.png)
    1. <span data-ttu-id="fd663-157">В поле **"Выберите группу"** найщите и добавьте группу безопасности, в которую входят ваши сотрудники и преподаватели.</span><span class="sxs-lookup"><span data-stu-id="fd663-157">In the **Select a group** box, search for and add the security group that contains your staff and educators.</span></span>
    2. <span data-ttu-id="fd663-158">В поле **"Выбрать ранг"** введите **1.**</span><span class="sxs-lookup"><span data-stu-id="fd663-158">In the **Select rank** box, enter **1**.</span></span>
    3. <span data-ttu-id="fd663-159">В **окне "Выберите политику"** выберите **EducatorMeetingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="fd663-159">In the **Select a policy** box, select **EducatorMeetingPolicy**.</span></span>
    4. <span data-ttu-id="fd663-160">Выберите **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="fd663-160">Select **Apply**.</span></span>

<span data-ttu-id="fd663-161">Чтобы удалить назначение групповой  политики, на вкладке назначения групповой политики на странице политики выберите назначение группы, а затем выберите **"Удалить".**</span><span class="sxs-lookup"><span data-stu-id="fd663-161">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="fd663-162">Чтобы изменить ранжирование для группового назначения, необходимо сначала удалить назначение групповой политики.</span><span class="sxs-lookup"><span data-stu-id="fd663-162">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="fd663-163">Затем следуйте этим шагам, чтобы назначить политику группе.</span><span class="sxs-lookup"><span data-stu-id="fd663-163">Then, follow the steps above to assign the policy to a group.</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="fd663-164">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd663-164">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="fd663-165">В настоящее время назначение политик группам с помощью PowerShell доступно не для всех типов политик Teams.</span><span class="sxs-lookup"><span data-stu-id="fd663-165">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="fd663-166">Список поддерживаемых типов политик см. в списке [New-CsGroupPolicyAssignment.](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)</span><span class="sxs-lookup"><span data-stu-id="fd663-166">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="fd663-167">Установка и подключение к модуле Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd663-167">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="fd663-168">Чтобы установить модуль [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (если он еще не установлен), запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fd663-168">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="fd663-169">Установите версию 1.0.5 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="fd663-169">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="fd663-170">Чтобы подключиться к Teams и начать сеанс, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fd663-170">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="fd663-171">Когда вам будет предложено, войте учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="fd663-171">When you're prompted, sign in using your admin credentials.</span></span>

##### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="fd663-172">Назначение политики группе</span><span class="sxs-lookup"><span data-stu-id="fd663-172">Assign a policy to a group</span></span>

<span data-ttu-id="fd663-173">Чтобы назначить политику собрания EducatorMeetingPolicy группе безопасности, в которую входят ваши сотрудники и преподаватели, и установите для ранжирования заданий 1 следующую:</span><span class="sxs-lookup"><span data-stu-id="fd663-173">Run the following to assign the meeting policy named EducatorMeetingPolicy to the security group that contains your staff and educators and set the assignment ranking to 1.</span></span> <span data-ttu-id="fd663-174">Группу безопасности можно указать с помощью ИД объекта, SIP-адреса или адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="fd663-174">You can specify a security group by using the object Id, Session Initiation Protocol (SIP) address, or email address.</span></span> <span data-ttu-id="fd663-175">В этом примере используется адрес электронной почты (staff-faculty@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="fd663-175">In this example, we use an email address (staff-faculty@contoso.com).</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com -PolicyType TeamsMeetingPolicy -PolicyName "EducatorMeetingPolicy" -Rank 1
```

### <a name="remove-a-policy-that-was-directly-assigned-to-users"></a><span data-ttu-id="fd663-176">Удаление политики, которая была непосредственно назначена пользователям</span><span class="sxs-lookup"><span data-stu-id="fd663-176">Remove a policy that was directly assigned to users</span></span>

<span data-ttu-id="fd663-177">Помните, что если пользователю была непосредственно назначена политика (по отдельности или с помощью пакетного назначения), она имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="fd663-177">Remember that if a user was directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="fd663-178">Это означает, что если пользователю назначена политика собрания, ее необходимо удалить, прежде чем наследовать политику собрания от группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="fd663-178">This means that if a user has a meeting policy that was directly assigned to them, you'll have to remove that meeting policy from the user before they can inherit a meeting policy from a security group.</span></span>

<span data-ttu-id="fd663-179">Чтобы узнать больше, узнайте, [что вам нужно знать о назначении](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)политик группам.</span><span class="sxs-lookup"><span data-stu-id="fd663-179">To learn more, see [What you need to know about policy assignment to groups](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups).</span></span>

<span data-ttu-id="fd663-180">Выполните эти действия, чтобы удалить политику собраний, которая была непосредственно назначена вашим сотрудникам и преподавателям.</span><span class="sxs-lookup"><span data-stu-id="fd663-180">Follow these steps to remove the meeting policy that was directly assigned to your staff and educators.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="fd663-181">Установка и подключение к модуле Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd663-181">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="fd663-182">Чтобы установить модуль [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (если он еще не установлен), запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fd663-182">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="fd663-183">Установите версию 1.0.5 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="fd663-183">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="fd663-184">Чтобы подключиться к Teams и начать сеанс, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fd663-184">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="fd663-185">Когда вам будет предложено, вопишите с помощью учетных данных администратора, которые вы использовали для подключения к Azure AD.</span><span class="sxs-lookup"><span data-stu-id="fd663-185">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

#### <a name="unassign-a-policy-that-was-directly-assigned-to-users"></a><span data-ttu-id="fd663-186">Отоменить политику, которая была непосредственно назначена пользователям</span><span class="sxs-lookup"><span data-stu-id="fd663-186">Unassign a policy that was directly assigned to users</span></span>

<span data-ttu-id="fd663-187">Чтобы удалить политику для собраний пользователей, которым она напрямую назначена, следуя следующей политике:</span><span class="sxs-lookup"><span data-stu-id="fd663-187">Run the following to remove a meeting policy from users who were directly assigned that policy.</span></span> <span data-ttu-id="fd663-188">Вы можете указать пользователей по адресу электронной почты или ИД объекта.</span><span class="sxs-lookup"><span data-stu-id="fd663-188">You can specify users by email address or object ID.</span></span>

<span data-ttu-id="fd663-189">В этом примере политика собрания удаляется для пользователей, указанных их адресами электронной почты.</span><span class="sxs-lookup"><span data-stu-id="fd663-189">In this example, the meeting policy is removed from users specified by their email address.</span></span>

```powershell
$users_ids = @("reda@contoso.com", "nikica@contoso.com", "jamie@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

<span data-ttu-id="fd663-190">В этом примере политика собрания удаляется из списка пользователей в текстовом файле с user_ids.txt.</span><span class="sxs-lookup"><span data-stu-id="fd663-190">In this example, the meeting policy is removed from the list of users in a text file named user_ids.txt.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

##### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="fd663-191">Назначение политик для группы</span><span class="sxs-lookup"><span data-stu-id="fd663-191">Get policy assignments for a group</span></span>

<span data-ttu-id="fd663-192">Чтобы увидеть все политики, которые назначены определенной группе безопасности, запустите следующую:</span><span class="sxs-lookup"><span data-stu-id="fd663-192">Run the following to see all the policies assigned to a specific security group.</span></span> <span data-ttu-id="fd663-193">Обратите внимание, что группы всегда перечисляются по их ИД, даже если для назначения политики использовался ее SIP-адрес или адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="fd663-193">Note that groups are always listed by their group ID even if its SIP address or email address was used to assign the policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com

```

##### <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="fd663-194">Получить политики, которые назначены пользователю</span><span class="sxs-lookup"><span data-stu-id="fd663-194">Get the policies assigned to a user</span></span>

<span data-ttu-id="fd663-195">Чтобы увидеть все политики, которые назначены конкретному пользователю, запустите следующую:</span><span class="sxs-lookup"><span data-stu-id="fd663-195">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="fd663-196">В следующем примере показано, как получить политики, которые назначены reda@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="fd663-196">The following example shows you how to get the policies that are assigned to reda@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity reda@contoso.com
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="fd663-197">Назначение политики для пакета пользователей</span><span class="sxs-lookup"><span data-stu-id="fd663-197">Assign a policy to a batch of users</span></span>

<span data-ttu-id="fd663-198">Выполните эти действия, чтобы массово назначить настраиваемую политику собраний educatorMeetingPolicy своим сотрудникам и преподавателям.</span><span class="sxs-lookup"><span data-stu-id="fd663-198">Follow these steps to assign a custom meeting policy named EducatorMeetingPolicy directly to your staff and educators in bulk.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="fd663-199">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd663-199">Using PowerShell</span></span>

#### <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a><span data-ttu-id="fd663-200">Подключите модуль Azure AD PowerShell для Graph и модуль Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd663-200">Connect to the Azure AD PowerShell for Graph module and the Teams PowerShell module</span></span>

<span data-ttu-id="fd663-201">Перед выполнением действий, приведенных в этой статье, необходимо установить модуль Azure AD PowerShell для Graph (чтобы определить пользователей по их лицензиям) и модуль Microsoft Teams PowerShell (чтобы назначить им политики).</span><span class="sxs-lookup"><span data-stu-id="fd663-201">Before you perform the steps in this article, you'll need to install and connect to the Azure AD PowerShell for Graph module (to identify users by their assigned licenses) and the Microsoft Teams PowerShell module (to assign the policies to those users).</span></span>

##### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a><span data-ttu-id="fd663-202">Установка и подключение к модуле Azure AD PowerShell для Graph</span><span class="sxs-lookup"><span data-stu-id="fd663-202">Install and connect to the Azure AD PowerShell for Graph module</span></span>

<span data-ttu-id="fd663-203">Откройте командную Windows PowerShell с повышенными Windows PowerShell (запустите ее от администратора) и запустите следующую команду, чтобы установить модуль Azure Active Directory PowerShell для Graph:</span><span class="sxs-lookup"><span data-stu-id="fd663-203">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator), and then run the following to install the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Install-Module -Name AzureAD
```

<span data-ttu-id="fd663-204">Чтобы подключиться к Azure AD, запустите следующую службу:</span><span class="sxs-lookup"><span data-stu-id="fd663-204">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="fd663-205">Когда вам будет предложено, войте учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="fd663-205">When you're prompted, sign in using your admin credentials.</span></span>

<span data-ttu-id="fd663-206">Дополнительные данные [см. в модуле Graph "Подключение с помощью Azure Active Directory PowerShell".](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="fd663-206">To learn more, see [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="fd663-207">Установка и подключение к модуле Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd663-207">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="fd663-208">Чтобы установить модуль [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (если он еще не установлен), запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fd663-208">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="fd663-209">Установите версию 1.0.5 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="fd663-209">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="fd663-210">Чтобы подключиться к Teams и начать сеанс, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fd663-210">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="fd663-211">Когда вам будет предложено, вопишите с помощью учетных данных администратора, которые вы использовали для подключения к Azure AD.</span><span class="sxs-lookup"><span data-stu-id="fd663-211">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

#### <a name="identify-your-users"></a><span data-ttu-id="fd663-212">Определение пользователей</span><span class="sxs-lookup"><span data-stu-id="fd663-212">Identify your users</span></span>

<span data-ttu-id="fd663-213">Сначала запустите следующую, чтобы определить сотрудников и преподавателей по типу лицензии.</span><span class="sxs-lookup"><span data-stu-id="fd663-213">First, run the following to identify your staff and educators by license type.</span></span> <span data-ttu-id="fd663-214">Это указывает, какие skus используются в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="fd663-214">This tells you what SKUs are in use in your organization.</span></span> <span data-ttu-id="fd663-215">После этого вы сможете определить сотрудников и преподавателей, которые имеют SKU преподавателей.</span><span class="sxs-lookup"><span data-stu-id="fd663-215">You can then identify staff and educators that have a Faculty SKU assigned.</span></span>

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

<span data-ttu-id="fd663-216">Возвращаемая возвращаемая</span><span class="sxs-lookup"><span data-stu-id="fd663-216">Which returns:</span></span>

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

<span data-ttu-id="fd663-217">В этом примере показано, что лицензия для преподавателей SKUId — "e97c048c-37a4-45fb-ab50-922fbf07a370".</span><span class="sxs-lookup"><span data-stu-id="fd663-217">In this example, the output shows that the Faculty license SkuId is "e97c048c-37a4-45fb-ab50-922fbf07a370".</span></span>

> [!NOTE]
> <span data-ttu-id="fd663-218">Список номеров SKU и SKU для образовательных сфере см. в справке [по номеру SKU для образовательных сфере.](sku-reference-edu.md)</span><span class="sxs-lookup"><span data-stu-id="fd663-218">To see a list of Education SKUs and SKU IDs, see [Education SKU reference](sku-reference-edu.md).</span></span>

<span data-ttu-id="fd663-219">Затем мы запускаем следующую, чтобы определить пользователей, у которых есть эта лицензия, и собрать их вместе.</span><span class="sxs-lookup"><span data-stu-id="fd663-219">Next, we run the following to identify the users that have this license and collect them all together.</span></span>

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

#### <a name="assign-a-policy-in-bulk"></a><span data-ttu-id="fd663-220">Массовое назначение политики</span><span class="sxs-lookup"><span data-stu-id="fd663-220">Assign a policy in bulk</span></span>

<span data-ttu-id="fd663-221">Теперь мы массово назначаем пользователям подходящие политики.</span><span class="sxs-lookup"><span data-stu-id="fd663-221">Now, we assign the appropriate policies to users in bulk.</span></span> <span data-ttu-id="fd663-222">Максимальное количество пользователей, для которых можно назначить или обновить политики, составляет 5000 за раз.</span><span class="sxs-lookup"><span data-stu-id="fd663-222">The maximum number of users for which you can assign or update policies is 5,000 at a time.</span></span> <span data-ttu-id="fd663-223">Например, если в компании более 5000 сотрудников и преподавателей, необходимо отправить несколько пакетов.</span><span class="sxs-lookup"><span data-stu-id="fd663-223">For example, if you have more than 5,000 staff and educators, you'll need to submit multiple batches.</span></span>

<span data-ttu-id="fd663-224">Чтобы назначить сотрудникам и преподавателям настраиваемую политику собрания EducatorMeetingPolicy, следуйте следующей пометке:</span><span class="sxs-lookup"><span data-stu-id="fd663-224">Run the following to assign a custom meeting policy named EducatorMeetingPolicy to your staff and educators.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> <span data-ttu-id="fd663-225">Чтобы массово назначить другой тип политики, например TeamsMessagingPolicy, необходимо изменить политику и ее ```PolicyType``` ```PolicyName``` имя.</span><span class="sxs-lookup"><span data-stu-id="fd663-225">To assign a different policy type in bulk, like TeamsMessagingPolicy, you'll need to change ```PolicyType``` to the policy that you're assigning and ```PolicyName``` to the policy name.</span></span>

#### <a name="get-the-status-of-a-bulk-assignment"></a><span data-ttu-id="fd663-226">Состояние массовой рассылки заданий</span><span class="sxs-lookup"><span data-stu-id="fd663-226">Get the status of a bulk assignment</span></span>

<span data-ttu-id="fd663-227">Каждое массовое назначение возвращает ИД операции, который можно использовать для отслеживания хода выполнения назначений политики или выявления сбоев.</span><span class="sxs-lookup"><span data-stu-id="fd663-227">Each bulk assignment returns an operation ID, which you can use to track the progress of the policy assignments or identify any failures that might occur.</span></span> <span data-ttu-id="fd663-228">Например, запустите следующую:</span><span class="sxs-lookup"><span data-stu-id="fd663-228">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

<span data-ttu-id="fd663-229">Чтобы просмотреть состояние назначения каждого пользователя в пакетной операции, запустите следующую операцию:</span><span class="sxs-lookup"><span data-stu-id="fd663-229">To view the assignment status of each user in the batch operation, run the following.</span></span> <span data-ttu-id="fd663-230">Сведения о каждом пользователе находятся в ```UserState``` свойстве.</span><span class="sxs-lookup"><span data-stu-id="fd663-230">Details of each user are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

#### <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a><span data-ttu-id="fd663-231">Массовое назначение политики, если у вас более 5000 пользователей</span><span class="sxs-lookup"><span data-stu-id="fd663-231">Assign a policy in bulk if you have more than 5,000 users</span></span>

<span data-ttu-id="fd663-232">Сначала запустите следующую, чтобы узнать, сколько у вас сотрудников и преподавателей:</span><span class="sxs-lookup"><span data-stu-id="fd663-232">First, run the following to see how many staff and educators you have:</span></span>

```powershell
$faculty.count
```

<span data-ttu-id="fd663-233">Вместо того чтобы предоставлять весь список ИД пользователей, укажите первые 5000, а затем следующие 5000 и другие следующие 5000 и так далее.</span><span class="sxs-lookup"><span data-stu-id="fd663-233">Instead of providing the whole list of user IDs, run the following to specify the first 5,000, and then the next 5,000, and so on.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

<span data-ttu-id="fd663-234">Вы можете изменять диапазон ид пользователей, пока не достигнете полного списка пользователей.</span><span class="sxs-lookup"><span data-stu-id="fd663-234">You can change the range of user IDs until you reach the full list of users.</span></span> <span data-ttu-id="fd663-235">Например, можно ввести первый пакет, использовать второй пакет, второй — для третьего и так ```$faculty[0..4999``` ```$faculty[5000..9999``` ```$faculty[10000..14999``` далее.</span><span class="sxs-lookup"><span data-stu-id="fd663-235">For example, enter ```$faculty[0..4999``` for the first batch, use ```$faculty[5000..9999``` for the second batch, enter ```$faculty[10000..14999``` for the third batch, and so on.</span></span>

#### <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="fd663-236">Получить политики, которые назначены пользователю</span><span class="sxs-lookup"><span data-stu-id="fd663-236">Get the policies assigned to a user</span></span>

<span data-ttu-id="fd663-237">Чтобы увидеть все политики, которые назначены конкретному пользователю, запустите следующую:</span><span class="sxs-lookup"><span data-stu-id="fd663-237">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="fd663-238">В следующем примере показано, как получить политики, которые назначены hannah@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="fd663-238">The following example shows you how to get the policies that are assigned to hannah@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a><span data-ttu-id="fd663-239">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="fd663-239">FAQ</span></span>

<span data-ttu-id="fd663-240">**Я не знаю, как работать с PowerShell для Teams. Где можно узнать больше?**</span><span class="sxs-lookup"><span data-stu-id="fd663-240">**I'm not familiar with PowerShell for Teams. Where can I learn more?**</span></span>

<span data-ttu-id="fd663-241">Обзор использования PowerShell для управления Teams см. в обзоре [Teams PowerShell.](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="fd663-241">For an overview of using PowerShell to manage Teams, see [Teams PowerShell overview](teams-powershell-overview.md).</span></span> <span data-ttu-id="fd663-242">Дополнительные сведения о используемых в этой статье cmdlets см. в статьях:</span><span class="sxs-lookup"><span data-stu-id="fd663-242">For more information about the cmdlets used in this article, see:</span></span>

- [<span data-ttu-id="fd663-243">New-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="fd663-243">New-CsGroupPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)
- [<span data-ttu-id="fd663-244">Get-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="fd663-244">Get-CsGroupPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment)
- [<span data-ttu-id="fd663-245">New-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="fd663-245">New-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="fd663-246">Get-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="fd663-246">Get-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="fd663-247">Get-CsUserPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="fd663-247">Get-CsUserPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)

## <a name="related-topics"></a><span data-ttu-id="fd663-248">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="fd663-248">Related topics</span></span>

- [<span data-ttu-id="fd663-249">Назначение политик пользователям</span><span class="sxs-lookup"><span data-stu-id="fd663-249">Assign policies to your users</span></span>](assign-policies.md)
- [<span data-ttu-id="fd663-250">Политики и пакеты политик Teams для образовательных сфере</span><span class="sxs-lookup"><span data-stu-id="fd663-250">Teams policies and policy packages for Education</span></span>](policy-packages-edu.md)
- [<span data-ttu-id="fd663-251">Управление политиками собраний в Teams</span><span class="sxs-lookup"><span data-stu-id="fd663-251">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
