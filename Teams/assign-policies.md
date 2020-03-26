---
title: Назначение политик пользователям в Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: tomkau, saragava, ritikag
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Сведения о различных способах назначения политик пользователям в Microsoft Teams.
f1keywords: ''
ms.openlocfilehash: a3946ab7296603822655ac115ae5826f3f670cea
ms.sourcegitcommit: 4d376449a75928282373598647f2b82127909c4f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2020
ms.locfileid: "42978531"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="f8040-103">Назначение политик пользователям в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f8040-103">Assign policies to your users in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="f8040-104">**Одна из функций Microsoft Teams, описанных в этой статье, [Назначение политики для групп](#assign-a-policy-to-a-group)в настоящее время доступна только в ограниченном предварительном просмотре. Командлеты PowerShell для этой функции находятся в предварительной версии модуля PowerShell для Teams.**</span><span class="sxs-lookup"><span data-stu-id="f8040-104">**One of the Microsoft Teams features discussed in this article, [policy assignment to groups](#assign-a-policy-to-a-group), is currently only available in limited preview. The Powershell cmdlets for this feature are in the pre-release Teams PowerShell module.**</span></span>

<span data-ttu-id="f8040-105">Администраторы используют политики для управления возможностями Teams, доступными для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f8040-105">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="f8040-106">Например, вы можете присвоить имя только некоторые политики, политики собраний и политики обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="f8040-106">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="f8040-107">Организации имеют различные типы пользователей с уникальными потребностями, пользовательские политики, созданные и назначаемые, позволяют настраивать параметры политики для разных наборов пользователей на основе этих нужд.</span><span class="sxs-lookup"><span data-stu-id="f8040-107">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="f8040-108">Для упрощения управления политиками в Организации Teams предлагается несколько способов назначения политик пользователям.</span><span class="sxs-lookup"><span data-stu-id="f8040-108">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="f8040-109">Политику можно назначить непосредственно пользователям, как по отдельности, так и по масштабу в рамках задания или в группу, в которую входит пользователь.</span><span class="sxs-lookup"><span data-stu-id="f8040-109">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the user is a member of.</span></span> <span data-ttu-id="f8040-110">Вы также можете использовать пакеты политик, чтобы назначить набор политик для пользователей в Организации, у которых есть похожие роли.</span><span class="sxs-lookup"><span data-stu-id="f8040-110">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="f8040-111">Выбор параметра зависит от количества политик, которые вы управляете, и количества пользователей, которым вы назначаете.</span><span class="sxs-lookup"><span data-stu-id="f8040-111">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span>

<span data-ttu-id="f8040-112">В этой статье описаны различные способы назначения политик пользователям и рекомендуемые сценарии для того, когда следует использовать эту возможность.</span><span class="sxs-lookup"><span data-stu-id="f8040-112">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="f8040-113">Какая политика имеет приоритет?</span><span class="sxs-lookup"><span data-stu-id="f8040-113">Which policy takes precedence?</span></span>

<span data-ttu-id="f8040-114">У пользователя есть одна действующая политика для каждого типа политики.</span><span class="sxs-lookup"><span data-stu-id="f8040-114">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="f8040-115">Возможно или даже, что пользователю явно назначена политика, и он также является членом одной или нескольких групп, которым назначена политика того же типа.</span><span class="sxs-lookup"><span data-stu-id="f8040-115">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="f8040-116">В сценариях такого типа приоритет имеет политика.</span><span class="sxs-lookup"><span data-stu-id="f8040-116">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="f8040-117">Действующая политика пользователя определяется в соответствии с правилами приоритета, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="f8040-117">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="f8040-118">Если пользователю назначена политика (отдельно или по назначению), она имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="f8040-118">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="f8040-119">В приведенном ниже примере действующая политика пользователя — это Линколн квадратная политика для собраний, которая непосредственно назначается пользователю.</span><span class="sxs-lookup"><span data-stu-id="f8040-119">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![Схема, показывающая, как имеет приоритет более прямую назначенную политику](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="f8040-121">Если пользователь не назначил политике определенного типа, политика, назначенная группе, членом которой является пользователь, имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="f8040-121">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="f8040-122">Если пользователь является членом нескольких групп, политика, имеющая наивысший [рейтинг назначения группы](#group-assignment-ranking) для данного типа политики, имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="f8040-122">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="f8040-123">В этом примере действующая политика пользователя — это политика Exec Teams и HD, которая имеет наивысший рейтинг назначения относительно других групп, участником которых является этот пользователь, и которым также назначена политика того же типа политики.</span><span class="sxs-lookup"><span data-stu-id="f8040-123">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![Схема, на которой показано, как действует политика, унаследованная от группы](media/assign-policies-example-group.png)

<span data-ttu-id="f8040-125">Если пользователь не назначил политику или не является участником ни одной из групп, которым назначена политика, пользователь получает глобальную политику (по умолчанию для всей организации) для этого типа политики.</span><span class="sxs-lookup"><span data-stu-id="f8040-125">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="f8040-126">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="f8040-126">Here's an example.</span></span>

![Схема, показывающая, как Глобальная политика имеет приоритет](media/assign-policies-example-global.png)

<span data-ttu-id="f8040-128">Дополнительные сведения можно найти в разделе [правила приоритета](#precedence-rules).</span><span class="sxs-lookup"><span data-stu-id="f8040-128">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="f8040-129">Способы назначения политик</span><span class="sxs-lookup"><span data-stu-id="f8040-129">Ways to assign policies</span></span>

<span data-ttu-id="f8040-130">Ниже приведены общие сведения о способах назначения политик пользователям и рекомендуемых сценариях для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="f8040-130">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="f8040-131">Чтобы получить дополнительные сведения, щелкните ссылки.</span><span class="sxs-lookup"><span data-stu-id="f8040-131">Click the links to learn more.</span></span>

|<span data-ttu-id="f8040-132">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="f8040-132">Do this</span></span>  |<span data-ttu-id="f8040-133">Если...</span><span class="sxs-lookup"><span data-stu-id="f8040-133">If...</span></span>  | <span data-ttu-id="f8040-134">Использование...</span><span class="sxs-lookup"><span data-stu-id="f8040-134">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="f8040-135">Назначение политики отдельным пользователям</span><span class="sxs-lookup"><span data-stu-id="f8040-135">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="f8040-136">Вы не знакомы с Teams и просто приступите к работе или вам нужно назначить одну или несколько политик небольшим числам пользователей.</span><span class="sxs-lookup"><span data-stu-id="f8040-136">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="f8040-137">Центр администрирования Microsoft Teams или командлеты PowerShell в модуле PowerShell Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="f8040-137">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
| [<span data-ttu-id="f8040-138">Назначение пакета политики</span><span class="sxs-lookup"><span data-stu-id="f8040-138">Assign a policy package</span></span>](#assign-a-policy-package)   | <span data-ttu-id="f8040-139">Необходимо назначить несколько политик определенным наборам пользователей организации, которые имеют одинаковые или аналогичные роли.</span><span class="sxs-lookup"><span data-stu-id="f8040-139">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="f8040-140">Например, вы можете назначить пакету политики образования для преподавателей в учебном заведении, чтобы предоставить им полный доступ к беседам, звонку, собраниям и пакету политики образования (дополнительный учебный учащийся) для дополнительных студентов, которые ограничивают некоторые возможности, такие как частный звонок.</span><span class="sxs-lookup"><span data-stu-id="f8040-140">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="f8040-141">Центр администрирования Microsoft Teams или командлеты PowerShell из модуля Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8040-141">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="f8040-142">Назначение политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="f8040-142">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="f8040-143">Вы должны назначать политики большим наборам пользователей.</span><span class="sxs-lookup"><span data-stu-id="f8040-143">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="f8040-144">Например, вы хотите назначить политику для сотен или тысяч пользователей в Организации одновременно.</span><span class="sxs-lookup"><span data-stu-id="f8040-144">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="f8040-145">Командлеты PowerShell в модуле PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="f8040-145">PowerShell cmdlets in the Teams PowerShell module</span></span>|
|<span data-ttu-id="f8040-146">[Назначение политики группе](#assign-a-policy-to-a-group) (в предварительной версии)</span><span class="sxs-lookup"><span data-stu-id="f8040-146">[Assign a policy to a group](#assign-a-policy-to-a-group) (in preview)</span></span>   |<span data-ttu-id="f8040-147">Необходимо назначить политики, основанные на членстве в группе пользователя.</span><span class="sxs-lookup"><span data-stu-id="f8040-147">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="f8040-148">Например, вы хотите назначить политику для всех пользователей в группе безопасности или подразделении.</span><span class="sxs-lookup"><span data-stu-id="f8040-148">For example, you want to assign a policy to all users in a security group or organizational unit.</span></span>| <span data-ttu-id="f8040-149">Командлеты PowerShell в модуле PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="f8040-149">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="f8040-150">Назначение пакета политики пакету пользователей (ожидается в ближайшее время)</span><span class="sxs-lookup"><span data-stu-id="f8040-150">Assign a policy package to a batch of users (coming soon)</span></span> |||
| <span data-ttu-id="f8040-151">Назначение пакета политики группе (ожидается в ближайшее время)</span><span class="sxs-lookup"><span data-stu-id="f8040-151">Assign a policy package to a group (coming soon)</span></span>   | ||

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="f8040-152">Назначение политики отдельным пользователям</span><span class="sxs-lookup"><span data-stu-id="f8040-152">Assign a policy to individual users</span></span>

<span data-ttu-id="f8040-153">Выполните указанные ниже действия, чтобы назначить политику для отдельного пользователя или для небольшого количества пользователей за один раз.</span><span class="sxs-lookup"><span data-stu-id="f8040-153">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="f8040-154">Использование центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f8040-154">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="f8040-155">Чтобы назначить пользователю политику, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="f8040-155">To assign a policy to a user:</span></span>

1. <span data-ttu-id="f8040-156">В Центре администрирования Microsoft Teams в области навигации слева перейдите в раздел **Пользователи**, затем щелкните пользователя.</span><span class="sxs-lookup"><span data-stu-id="f8040-156">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="f8040-157">Выберите пользователя, щелкнув слева от его имени, затем нажмите кнопку **Изменить параметры**.</span><span class="sxs-lookup"><span data-stu-id="f8040-157">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="f8040-158">Выберите политику, которую вы хотите назначить, и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="f8040-158">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="f8040-159">Чтобы назначить политику до 20 пользователей за один раз, ознакомьтесь с [разгруппым изменением параметров пользователей Teams](edit-user-settings-in-bulk.md).</span><span class="sxs-lookup"><span data-stu-id="f8040-159">To assign a policy to up to 20 users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="f8040-160">Кроме того, вы можете сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="f8040-160">Or, you can also do the following:</span></span>

1. <span data-ttu-id="f8040-161">В левой области навигации центра администрирования Microsoft Teams перейдите на страницу "политика".</span><span class="sxs-lookup"><span data-stu-id="f8040-161">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="f8040-162">Выберите политику, которую вы хотите назначить, щелкнув слева от ее имени.</span><span class="sxs-lookup"><span data-stu-id="f8040-162">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="f8040-163">Выберите **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="f8040-163">Select **Manage users**.</span></span>
4. <span data-ttu-id="f8040-164">В области **Управление пользователями** найдите пользователя по отображаемому имени или по имени пользователя, выберите имя и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="f8040-164">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="f8040-165">Повторите это действие для каждого пользователя, которого нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="f8040-165">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="f8040-166">Завершив добавление пользователей, нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f8040-166">When you're finished adding users, select **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="f8040-167">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8040-167">Using PowerShell</span></span>

<span data-ttu-id="f8040-168">У каждого типа политики есть собственный набор командлетов для управления ею.</span><span class="sxs-lookup"><span data-stu-id="f8040-168">Each policy type has it's own set of cmdlets for managing it.</span></span> <span data-ttu-id="f8040-169">Используйте ```Grant-``` командлет для определенного типа политики, чтобы назначить политику.</span><span class="sxs-lookup"><span data-stu-id="f8040-169">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="f8040-170">Например, можно использовать ```Grant-CsTeamsMeetingPolicy``` командлет для назначения пользователям политики собрания Teams.</span><span class="sxs-lookup"><span data-stu-id="f8040-170">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="f8040-171">Эти командлеты включены в модуль PowerShell Skype для бизнеса Online и описаны в [справочной документации по командлетам Skype для бизнеса](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f8040-171">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="f8040-172">Скачайте и установите [модуль PowerShell Skype для бизнеса Online](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (если вы еще этого не сделали), а затем выполните указанные ниже действия, чтобы подключиться к Skype для бизнеса Online и начать сеанс.</span><span class="sxs-lookup"><span data-stu-id="f8040-172">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="f8040-173">В этом примере мы назначаем политику собраний Teams, которая называется политикой собраний учащихся, пользователю с именем Реда.</span><span class="sxs-lookup"><span data-stu-id="f8040-173">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="f8040-174">Дополнительные сведения можно найти в разделе [Управление политиками через PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).</span><span class="sxs-lookup"><span data-stu-id="f8040-174">To learn more, see [Managing policies via PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).</span></span>

## <a name="assign-a-policy-package"></a><span data-ttu-id="f8040-175">Назначение пакета политики</span><span class="sxs-lookup"><span data-stu-id="f8040-175">Assign a policy package</span></span>

<span data-ttu-id="f8040-176">Пакет политики в Teams — это набор предопределенных политик и параметров политики, которые можно назначить пользователям, имеющим такие же или аналогичные роли в Организации.</span><span class="sxs-lookup"><span data-stu-id="f8040-176">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="f8040-177">Каждый пакет политики разработан вокруг роли пользователя и включает стандартные политики и параметры политики, которые поддерживают действия, характерные для этой роли.</span><span class="sxs-lookup"><span data-stu-id="f8040-177">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="f8040-178">Некоторые примеры пакетов политики — это пакет для образования (преподаватель) и Здравоохранение (Клиникал Worker).</span><span class="sxs-lookup"><span data-stu-id="f8040-178">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span>

<span data-ttu-id="f8040-179">Когда вы назначаете пакету политики пользователям, будут созданы политики в пакете, и вы сможете настраивать параметры каждой из них в пакете в соответствии с потребностями пользователей.</span><span class="sxs-lookup"><span data-stu-id="f8040-179">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of each policy in the package to meet users' needs.</span></span>

<span data-ttu-id="f8040-180">Дополнительные сведения о пакетах политик, включая пошаговые инструкции по их назначению и управлению, можно найти [в разделе Управление пакетами политики в Teams](manage-policy-packages.md).</span><span class="sxs-lookup"><span data-stu-id="f8040-180">To learn more about policy packages, including step-by-step guidance on how to assign and manage them, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="f8040-181">Назначение политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="f8040-181">Assign a policy to a batch of users</span></span>
 
<span data-ttu-id="f8040-182">С помощью назначения пакетной политики вы можете назначить политику большим наборам пользователей за один раз, не прибегая к использованию сценария.</span><span class="sxs-lookup"><span data-stu-id="f8040-182">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="f8040-183">С помощью ```New-CsBatchPolicyAssignmentOperationd``` командлета вы можете отправить пакет пользователей и политику, которую вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="f8040-183">You use the ```New-CsBatchPolicyAssignmentOperationd``` cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="f8040-184">Назначения обрабатываются как фоновая операция, и для каждого пакета создается идентификатор операции.</span><span class="sxs-lookup"><span data-stu-id="f8040-184">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="f8040-185">Затем вы можете использовать этот ```Get-CsBatchPolicyAssignmentOperation``` командлет для отслеживания хода выполнения и состояния заданий в пакете.</span><span class="sxs-lookup"><span data-stu-id="f8040-185">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="f8040-186">Пакет может содержать до 20 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="f8040-186">A batch can contain up to 20,000 users.</span></span> <span data-ttu-id="f8040-187">Вы можете указать пользователей по идентификатору объекта, имени участника-пользователя (UPN), адресу протокола инициации сеансов (SIP) или адресу электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f8040-187">You can specify users by their object Id, user principal name (UPN), Session Initiation Protocol (SIP) address, or email address.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f8040-188">В настоящее время мы рекомендуем назначать политики в пакетах пользователей 5 000 за один раз.</span><span class="sxs-lookup"><span data-stu-id="f8040-188">We're currently recommending that you assign policies in batches of 5,000 users at a time.</span></span> <span data-ttu-id="f8040-189">В это время вы можете столкнуться с задержкой во время обработки.</span><span class="sxs-lookup"><span data-stu-id="f8040-189">During these times of increased demand, you may experience delays in processing times.</span></span> <span data-ttu-id="f8040-190">Чтобы свести к минимуму влияние этих увеличенных времен обработки, мы рекомендуем вам отправлять меньшие размеры пакета до 5 000 пользователей и отправлять каждый пакет только после того, как вы закончите предыдущий.</span><span class="sxs-lookup"><span data-stu-id="f8040-190">To minimize the impact of these increased processing times, we suggest that you submit smaller batch sizes of up to 5,000 users, and submit each batch only after the previous one is completed.</span></span> <span data-ttu-id="f8040-191">Вы также можете отправлять пакеты за пределы обычных рабочих часов.</span><span class="sxs-lookup"><span data-stu-id="f8040-191">Submitting batches outside your regular business hours can also help.</span></span>

> [!NOTE]
> <span data-ttu-id="f8040-192">В настоящее время назначение пакетной политики недоступно для всех типов политики Teams.</span><span class="sxs-lookup"><span data-stu-id="f8040-192">Currently, batch policy assignment isn't available for all Teams policy types.</span></span> <span data-ttu-id="f8040-193">Ознакомьтесь со списком " [New-ксбатчполициассигнментоператион](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) " для списка поддерживаемых типов политики.</span><span class="sxs-lookup"><span data-stu-id="f8040-193">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="f8040-194">Установка и подключение к модулю Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8040-194">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="f8040-195">Выполните указанные ниже действия, чтобы установить [модуль PowerShell Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams).</span><span class="sxs-lookup"><span data-stu-id="f8040-195">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="f8040-196">Убедитесь, что вы установили версию 1.0.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="f8040-196">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="f8040-197">Выполните указанные ниже действия, чтобы подключиться к Teams и начать сеанс.</span><span class="sxs-lookup"><span data-stu-id="f8040-197">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="f8040-198">Когда вам будет предложено, войдите в систему с помощью учетных данных администратора.</span><span class="sxs-lookup"><span data-stu-id="f8040-198">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="f8040-199">Установка и подключение к модулю Azure AD PowerShell для Graph (необязательно)</span><span class="sxs-lookup"><span data-stu-id="f8040-199">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="f8040-200">Кроме того, вам может потребоваться [загрузить и установить модуль Azure AD PowerShell для Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (если вы еще не сделали этого) и подключиться к Azure AD, чтобы получить список пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="f8040-200">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="f8040-201">Выполните указанные ниже действия, чтобы подключиться к Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f8040-201">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="f8040-202">Когда вам будет предложено, войдите в систему с помощью учетных данных администратора, используемых для подключения к Teams.</span><span class="sxs-lookup"><span data-stu-id="f8040-202">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="f8040-203">Назначение политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="f8040-203">Assign a policy to a batch of users</span></span>

<span data-ttu-id="f8040-204">В этом примере мы используем ```New-CsBatchPolicyAssignmentOperation``` командлет, чтобы назначить политику настройки приложения с именем "Политика настройки приложения" для пакета пользователей, перечисленных в файле Users_ids. Text.</span><span class="sxs-lookup"><span data-stu-id="f8040-204">In this example, we use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="f8040-205">В этом примере мы подключаем подключение к Azure AD, чтобы получить доступ к коллекции пользователей, а затем назначить политику сообщений с именем "Новая политика для приема на работу" для пакета пользователей, указанных в их доменных именах.</span><span class="sxs-lookup"><span data-stu-id="f8040-205">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their UPNs.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.UserPrincipalName -OperationName "Example 2 batch"
```

<span data-ttu-id="f8040-206">Дополнительные сведения можно найти в статье [Создание и ксбатчполициассигнментоператион](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="f8040-206">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="f8040-207">Получение статуса задания пакетной обработки</span><span class="sxs-lookup"><span data-stu-id="f8040-207">Get the status of a batch assignment</span></span>

<span data-ttu-id="f8040-208">Выполните указанные ниже действия, чтобы получить сведения о состоянии задания пакета, где идентификатор операции — это значение, возвращаемое ```New-CsBatchPolicyAssignmentOperation``` командлетом для данного пакета.</span><span class="sxs-lookup"><span data-stu-id="f8040-208">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="f8040-209">Если в выходных данных показано, что произошла ошибка, выполните указанные ниже действия, чтобы получить дополнительные сведения об ошибках ```UserState``` , которые находятся в свойстве.</span><span class="sxs-lookup"><span data-stu-id="f8040-209">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="f8040-210">Дополнительные сведения можно найти в [статьях Get-ксбатчполициассигнментоператион](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="f8040-210">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="f8040-211">Назначение политики группе</span><span class="sxs-lookup"><span data-stu-id="f8040-211">Assign a policy to a group</span></span>

<span data-ttu-id="f8040-212">**Назначение политики для групп в настоящее время доступно только в ограниченном предварительном просмотре. Командлеты для этой функции находятся в предварительной версии модуля PowerShell для Teams.**</span><span class="sxs-lookup"><span data-stu-id="f8040-212">**Policy assignment to groups is currently only available in limited preview. The cmdlets for this feature are in the pre-release Teams PowerShell module.**</span></span>

<span data-ttu-id="f8040-213">Назначение политики для групп позволяет назначить политику группе пользователей, например группе безопасности или подразделению.</span><span class="sxs-lookup"><span data-stu-id="f8040-213">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or organizational unit.</span></span> <span data-ttu-id="f8040-214">Назначение политики распространяется на пользователей группы в соответствии с правилами приоритета.</span><span class="sxs-lookup"><span data-stu-id="f8040-214">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="f8040-215">Когда участники добавляются в группу или удаляются из нее, их унаследованные назначения политик обновляются соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="f8040-215">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="f8040-216">С помощью ```New-CsGroupPolicyAssignment``` командлета вы можете назначить политику группе.</span><span class="sxs-lookup"><span data-stu-id="f8040-216">You use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="f8040-217">Вы можете указать группу, используя идентификатор объекта, адрес SIP или адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f8040-217">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="f8040-218">После назначения политики она немедленно назначается группе.</span><span class="sxs-lookup"><span data-stu-id="f8040-218">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="f8040-219">Однако обратите внимание, что распространение назначения политики для участников группы выполняется в фоновом режиме и может занять некоторое время, в зависимости от размера группы.</span><span class="sxs-lookup"><span data-stu-id="f8040-219">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="f8040-220">Это справедливо, если политика не назначена группе, а также при добавлении пользователей в группу или удалении ее из нее.</span><span class="sxs-lookup"><span data-stu-id="f8040-220">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!NOTE]
> <span data-ttu-id="f8040-221">В настоящее время назначение политики для групп недоступно для всех типов политики Teams.</span><span class="sxs-lookup"><span data-stu-id="f8040-221">Currently, policy assignment to groups isn't available for all Teams policy types.</span></span> <span data-ttu-id="f8040-222">Ознакомьтесь со списком " [New-ксграупполициассигнмент](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) " для списка поддерживаемых типов политики.</span><span class="sxs-lookup"><span data-stu-id="f8040-222">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="f8040-223">Что необходимо знать о назначении политики группам</span><span class="sxs-lookup"><span data-stu-id="f8040-223">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="f8040-224">Прежде чем приступить к работе, важно понимать правила приоритета и ранжирование назначения групп.</span><span class="sxs-lookup"><span data-stu-id="f8040-224">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="f8040-225">Правила приоритета</span><span class="sxs-lookup"><span data-stu-id="f8040-225">Precedence rules</span></span>

<span data-ttu-id="f8040-226">Для определенного типа политики действующая политика пользователя определяется в соответствии с приведенными ниже сведениями.</span><span class="sxs-lookup"><span data-stu-id="f8040-226">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="f8040-227">Политика, непосредственно назначенная пользователю, имеет приоритет над любыми другими политиками того же типа, которые назначены группе.</span><span class="sxs-lookup"><span data-stu-id="f8040-227">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="f8040-228">Другими словами, если пользователю явно назначена политика определенного типа, этот пользователь не наследует политику того же типа из группы.</span><span class="sxs-lookup"><span data-stu-id="f8040-228">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="f8040-229">Это также означает, что если пользователь имеет политику, назначенную определенному типу, вы должны удалить ее от пользователя, прежде чем она сможет наследовать политику того же типа из группы.</span><span class="sxs-lookup"><span data-stu-id="f8040-229">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="f8040-230">Если пользователь не имеет назначенной им политики и является членом двух или более групп, а каждая группа имеет политику с таким же типом, пользователь наследует политику назначения группы, имеющую наивысший рейтинг.</span><span class="sxs-lookup"><span data-stu-id="f8040-230">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="f8040-231">Если пользователь не является членом ни одной из групп, которым назначена политика, для него применяется Глобальная политика (по умолчанию на уровне Организации) для этого типа политики.</span><span class="sxs-lookup"><span data-stu-id="f8040-231">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="f8040-232">Действующая политика пользователя обновляется согласно этим правилам, когда пользователь добавляется или удаляется из группы, которой назначена политика, политика не назначается группе, или политика, непосредственно назначенная пользователю, удаляется.</span><span class="sxs-lookup"><span data-stu-id="f8040-232">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="f8040-233">Ранжирование назначения групп</span><span class="sxs-lookup"><span data-stu-id="f8040-233">Group assignment ranking</span></span>
 
<span data-ttu-id="f8040-234">Когда вы назначаете группе политику, вы указываете рейтинг для назначения группы.</span><span class="sxs-lookup"><span data-stu-id="f8040-234">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="f8040-235">Этот параметр используется для определения политики, которую пользователь должен наследовать в качестве действующей политики, если пользователь является членом двух или более групп, и каждой группе назначена политика одного и того же типа.</span><span class="sxs-lookup"><span data-stu-id="f8040-235">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="f8040-236">Ранжирование назначения групп определяется относительно других назначений групп того же типа.</span><span class="sxs-lookup"><span data-stu-id="f8040-236">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="f8040-237">Например, если вы назначаете политику вызовов двум группам, задайте для ранжирования одного задания значение 1, а для другого — 2, где 1 — наивысший рейтинг.</span><span class="sxs-lookup"><span data-stu-id="f8040-237">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="f8040-238">Ранжирование назначения групп указывает на то, что участие в группах является более важным или более релевантным по сравнению с наследованием в других группах.</span><span class="sxs-lookup"><span data-stu-id="f8040-238">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="f8040-239">Например, предположим, что у вас есть две группы, магазин сотрудников и руководителей магазина.</span><span class="sxs-lookup"><span data-stu-id="f8040-239">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="f8040-240">Обеим группам назначается политика вызова Teams, в котором хранятся политики вызова для сотрудников и политики звонков руководителей магазина соответственно.</span><span class="sxs-lookup"><span data-stu-id="f8040-240">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="f8040-241">Для руководителя магазина, который находится в обеих группах, роль руководителя больше важна, чем роль сотрудника, поэтому политика звонков, назначенная группе руководителей магазина, должна иметь более высокий рейтинг.</span><span class="sxs-lookup"><span data-stu-id="f8040-241">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="f8040-242">Сгруппирован</span><span class="sxs-lookup"><span data-stu-id="f8040-242">Group</span></span> |<span data-ttu-id="f8040-243">Имя политики вызова Teams</span><span class="sxs-lookup"><span data-stu-id="f8040-243">Teams calling policy name</span></span>  |<span data-ttu-id="f8040-244">Rank (Ранг)</span><span class="sxs-lookup"><span data-stu-id="f8040-244">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="f8040-245">Руководители магазина</span><span class="sxs-lookup"><span data-stu-id="f8040-245">Store Managers</span></span>   |<span data-ttu-id="f8040-246">Политика звонков руководителей магазина</span><span class="sxs-lookup"><span data-stu-id="f8040-246">Store Managers Calling Policy</span></span>         |<span data-ttu-id="f8040-247">1</span><span class="sxs-lookup"><span data-stu-id="f8040-247">1</span></span>|
|<span data-ttu-id="f8040-248">Магазин сотрудников</span><span class="sxs-lookup"><span data-stu-id="f8040-248">Store Employees</span></span>    |<span data-ttu-id="f8040-249">Хранение политики звонка для сотрудников</span><span class="sxs-lookup"><span data-stu-id="f8040-249">Store Employees Calling Policy</span></span>      |<span data-ttu-id="f8040-250">2</span><span class="sxs-lookup"><span data-stu-id="f8040-250">2</span></span>|

<span data-ttu-id="f8040-251">Если вы не укажете ранжирование, для назначения политики будет задан самый низкий рейтинг.</span><span class="sxs-lookup"><span data-stu-id="f8040-251">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="f8040-252">Установка и подключение к модулю Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8040-252">Install and connect to the Microsoft Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="f8040-253">Командлеты находятся в предварительной версии модуля PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="f8040-253">The cmdlets are in the pre-release version of the Teams PowerShell module.</span></span> <span data-ttu-id="f8040-254">Выполните эти действия, чтобы сначала удалить общедоступную версию модуля Teams PowerShell (если он установлен), а затем установите самую последнюю версию модуля из коллекции тестов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f8040-254">Follow these steps to first uninstall the Generally Available version of the Teams PowerShell module (if it's installed), and then install the latest pre-release version of the module from the PowerShell Test Gallery.</span></span>

<span data-ttu-id="f8040-255">Если вы еще не сделали этого, выполните указанные ниже действия, чтобы зарегистрировать коллекцию тестов PowerShell в качестве надежного источника.</span><span class="sxs-lookup"><span data-stu-id="f8040-255">If you haven't already, run the following to register the PowerShell Test Gallery as a trusted source.</span></span>

```powershell
Register-PSRepository -SourceLocation https://www.poshtestgallery.com/api/v2 -Name PsTestGallery -InstallationPolicy Trusted
```

<span data-ttu-id="f8040-256">Если вы установили общедоступную версию модуля Teams PowerShell, выполните указанные ниже действия, чтобы удалить его.</span><span class="sxs-lookup"><span data-stu-id="f8040-256">If you have the Generally Available version of the Teams PowerShell module installed, run the following to uninstall it.</span></span>

```powershell
Uninstall-Module MicrosoftTeams -AllVersions
```

<span data-ttu-id="f8040-257">Выполните указанные ниже действия, чтобы установить последнюю версию модуля PowerShell для Microsoft Teams из коллекции тестов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f8040-257">Run the following to install the latest Microsoft Teams PowerShell module from the PowerShell Test Gallery.</span></span>

```powershell
Install-Module MicrosoftTeams -Repository PSTestGallery
```

<span data-ttu-id="f8040-258">Выполните указанные ниже действия, чтобы подключиться к Teams и начать сеанс.</span><span class="sxs-lookup"><span data-stu-id="f8040-258">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="f8040-259">Когда вам будет предложено, войдите в систему с помощью учетных данных администратора.</span><span class="sxs-lookup"><span data-stu-id="f8040-259">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="f8040-260">Назначение политики группе</span><span class="sxs-lookup"><span data-stu-id="f8040-260">Assign a policy to a group</span></span>

<span data-ttu-id="f8040-261">В этом примере мы используем ```New-CsGroupPolicyAssignment``` командлет для назначения политики собрания Team Manager в группе с рейтингом назначения 1.</span><span class="sxs-lookup"><span data-stu-id="f8040-261">In this example, we use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

<span data-ttu-id="f8040-262">Дополнительные сведения можно найти в статье [Создание и ксграупполициассигнмент](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="f8040-262">To learn more, see [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span></span>

### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="f8040-263">Получение назначений политики для группы</span><span class="sxs-lookup"><span data-stu-id="f8040-263">Get policy assignments for a group</span></span>

<span data-ttu-id="f8040-264">Используйте командлет ```Get-CsGroupPolicyAssignment``` , чтобы получить все политики, назначенные группе.</span><span class="sxs-lookup"><span data-stu-id="f8040-264">Use the ```Get-CsGroupPolicyAssignment``` cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="f8040-265">Обратите внимание, что группы всегда записываются в соответствии с их идентификатором группы, даже если для назначения политики был использован адрес SIP или адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f8040-265">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="f8040-266">В этом примере мы извлекаем все политики, назначенные определенной группе.</span><span class="sxs-lookup"><span data-stu-id="f8040-266">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="f8040-267">В этом примере мы возвращаем все группы, которым назначена политика для собрания Teams.</span><span class="sxs-lookup"><span data-stu-id="f8040-267">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

<span data-ttu-id="f8040-268">Дополнительные сведения можно найти в [статьях Get-ксграупполициассигнмент](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="f8040-268">To learn more, see [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span></span>

### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="f8040-269">Удаление политики из группы</span><span class="sxs-lookup"><span data-stu-id="f8040-269">Remove a policy from a group</span></span>

<span data-ttu-id="f8040-270">Используйте ```Remove-CsGroupPolicyAssignment``` командлет для удаления политики из группы.</span><span class="sxs-lookup"><span data-stu-id="f8040-270">Use the ```Remove-CsGroupPolicyAssignment``` cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="f8040-271">При удалении политики из группы приоритеты других политик того же типа, которым назначена эта группа, и которые имеют более низкий рейтинг, будут обновлены.</span><span class="sxs-lookup"><span data-stu-id="f8040-271">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="f8040-272">Например, если вы удалите политику с рангом 2, то политики с рейтингом 3 и 4 будут обновляться в соответствии с их новым рейтингом.</span><span class="sxs-lookup"><span data-stu-id="f8040-272">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="f8040-273">Этот пример показан в двух приведенных ниже таблицах.</span><span class="sxs-lookup"><span data-stu-id="f8040-273">The following two tables show this example.</span></span>

<span data-ttu-id="f8040-274">Ниже приведен список назначений и приоритетов политики для собраний Teams.</span><span class="sxs-lookup"><span data-stu-id="f8040-274">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="f8040-275">Имя группы</span><span class="sxs-lookup"><span data-stu-id="f8040-275">Group name</span></span>  |<span data-ttu-id="f8040-276">Название политики</span><span class="sxs-lookup"><span data-stu-id="f8040-276">Policy name</span></span>  |<span data-ttu-id="f8040-277">Rank (Ранг)</span><span class="sxs-lookup"><span data-stu-id="f8040-277">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="f8040-278">Продажи</span><span class="sxs-lookup"><span data-stu-id="f8040-278">Sales</span></span>    |<span data-ttu-id="f8040-279">Политика продаж</span><span class="sxs-lookup"><span data-stu-id="f8040-279">Sales policy</span></span>       | <span data-ttu-id="f8040-280">1</span><span class="sxs-lookup"><span data-stu-id="f8040-280">1</span></span>        |
|<span data-ttu-id="f8040-281">Западная область</span><span class="sxs-lookup"><span data-stu-id="f8040-281">West Region</span></span>     |<span data-ttu-id="f8040-282">Политика "Западная область"</span><span class="sxs-lookup"><span data-stu-id="f8040-282">West Region policy</span></span>         |<span data-ttu-id="f8040-283">2</span><span class="sxs-lookup"><span data-stu-id="f8040-283">2</span></span>         |
|<span data-ttu-id="f8040-284">Умножен</span><span class="sxs-lookup"><span data-stu-id="f8040-284">Division</span></span>    |<span data-ttu-id="f8040-285">Политика деления</span><span class="sxs-lookup"><span data-stu-id="f8040-285">Division policy</span></span>         |<span data-ttu-id="f8040-286">3</span><span class="sxs-lookup"><span data-stu-id="f8040-286">3</span></span>         |
|<span data-ttu-id="f8040-287">Отделения</span><span class="sxs-lookup"><span data-stu-id="f8040-287">Subsidiary</span></span>   |<span data-ttu-id="f8040-288">Политика для дочерних компаний</span><span class="sxs-lookup"><span data-stu-id="f8040-288">Subsidiary policy</span></span>        |<span data-ttu-id="f8040-289">4</span><span class="sxs-lookup"><span data-stu-id="f8040-289">4</span></span>         |

<span data-ttu-id="f8040-290">Если удалить политику западных областей из группы Западная область, то назначения и приоритеты политики будут обновляться следующим образом.</span><span class="sxs-lookup"><span data-stu-id="f8040-290">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="f8040-291">Имя группы</span><span class="sxs-lookup"><span data-stu-id="f8040-291">Group name</span></span>  |<span data-ttu-id="f8040-292">Название политики</span><span class="sxs-lookup"><span data-stu-id="f8040-292">Policy name</span></span>  |<span data-ttu-id="f8040-293">Rank (Ранг)</span><span class="sxs-lookup"><span data-stu-id="f8040-293">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="f8040-294">Продажи</span><span class="sxs-lookup"><span data-stu-id="f8040-294">Sales</span></span>    |<span data-ttu-id="f8040-295">Политика продаж</span><span class="sxs-lookup"><span data-stu-id="f8040-295">Sales policy</span></span>       | <span data-ttu-id="f8040-296">1</span><span class="sxs-lookup"><span data-stu-id="f8040-296">1</span></span>        |
|<span data-ttu-id="f8040-297">Умножен</span><span class="sxs-lookup"><span data-stu-id="f8040-297">Division</span></span>    |<span data-ttu-id="f8040-298">Политика деления</span><span class="sxs-lookup"><span data-stu-id="f8040-298">Division policy</span></span>         |<span data-ttu-id="f8040-299">2</span><span class="sxs-lookup"><span data-stu-id="f8040-299">2</span></span>         |
|<span data-ttu-id="f8040-300">Отделения</span><span class="sxs-lookup"><span data-stu-id="f8040-300">Subsidiary</span></span>   |<span data-ttu-id="f8040-301">Политика для дочерних компаний</span><span class="sxs-lookup"><span data-stu-id="f8040-301">Subsidiary policy</span></span>        |<span data-ttu-id="f8040-302">3</span><span class="sxs-lookup"><span data-stu-id="f8040-302">3</span></span>        |

<span data-ttu-id="f8040-303">В данном примере политика для собрания Teams удаляется из группы.</span><span class="sxs-lookup"><span data-stu-id="f8040-303">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

<span data-ttu-id="f8040-304">Дополнительные сведения можно найти в разделе [Remove-ксграупполициассигнмент](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="f8040-304">To learn more, see [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span></span>

### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="f8040-305">Изменение назначения политики для группы</span><span class="sxs-lookup"><span data-stu-id="f8040-305">Change a policy assignment for a group</span></span>

<span data-ttu-id="f8040-306">После назначения политики группе вы можете использовать ```Set-CsGroupPolicyAssignmentd``` командлет, чтобы изменить назначение политики этой группы следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f8040-306">After you assign a policy to a group, you can use the ```Set-CsGroupPolicyAssignmentd``` cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="f8040-307">Изменение ранжирования</span><span class="sxs-lookup"><span data-stu-id="f8040-307">Change the ranking</span></span>
- <span data-ttu-id="f8040-308">Изменение политики для определенного типа политики</span><span class="sxs-lookup"><span data-stu-id="f8040-308">Change the policy of a given policy type</span></span>
- <span data-ttu-id="f8040-309">Изменение политики для определенного типа политики и ранжирования</span><span class="sxs-lookup"><span data-stu-id="f8040-309">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="f8040-310">В этом примере мы изменим политику приостановки вызовов групп для группы на политику с именем Суппорткаллпарк и рейтинг назначения 3.</span><span class="sxs-lookup"><span data-stu-id="f8040-310">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

<span data-ttu-id="f8040-311">Дополнительные сведения можно найти в статье [Set-ксграупполициассигнмент](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="f8040-311">To learn more, see [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span></span>

### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="f8040-312">Изменение действующей политики для пользователя</span><span class="sxs-lookup"><span data-stu-id="f8040-312">Change the effective policy for a user</span></span>

<span data-ttu-id="f8040-313">Ниже приведен пример изменения действующей политики для пользователя, которому непосредственно назначена политика.</span><span class="sxs-lookup"><span data-stu-id="f8040-313">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="f8040-314">Сначала мы используем ```Get-CsUserPolicyAssignment``` командлет вместе с ```PolicySource``` параметром, чтобы получить подробные сведения о политиках широковещательного показа собраний Teams, связанных с пользователем.</span><span class="sxs-lookup"><span data-stu-id="f8040-314">First, we use the ```Get-CsUserPolicyAssignment``` cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> <span data-ttu-id="f8040-315">Дополнительные сведения можно найти в [статьях Get-ксусерполициассигнмент](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="f8040-315">To learn more, see [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="f8040-316">В выходных данных показано, что пользователю непосредственно назначена политика широковещательного показа собрания Teams, которая имеет приоритет над политикой "события поставщика", назначенной группе, в которую входит пользователь.</span><span class="sxs-lookup"><span data-stu-id="f8040-316">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="f8040-317">Теперь мы удаляем политику событий сотрудников от пользователя.</span><span class="sxs-lookup"><span data-stu-id="f8040-317">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="f8040-318">Это означает, что пользователь больше не имеет политики широковещательного показа собраний Teams, которой они назначены, и будет наследовать политику Live Events поставщика, назначенную группе, которой принадлежит пользователь.</span><span class="sxs-lookup"><span data-stu-id="f8040-318">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="f8040-319">Для этого используйте следующий командлет в модуле Skype для бизнеса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f8040-319">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="f8040-320">Вы можете использовать следующий командлет в модуле Teams PowerShell для выполнения этой задачи при масштабировании при использовании задания пакетной политики, где $users — это список пользователей, которые вы указали.</span><span class="sxs-lookup"><span data-stu-id="f8040-320">You can use following cmdlet in the Teams Powershell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="related-topics"></a><span data-ttu-id="f8040-321">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="f8040-321">Related topics</span></span>

- [<span data-ttu-id="f8040-322">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="f8040-322">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)