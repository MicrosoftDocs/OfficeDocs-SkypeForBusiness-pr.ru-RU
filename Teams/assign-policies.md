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
ms.openlocfilehash: cb1c5fd43379388327de5e517409f01f7f52ed1b
ms.sourcegitcommit: d7be89019dd5a3b88b0840bddf1b88fea8598ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "42170765"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="d8c4b-103">Назначение политик пользователям в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d8c4b-103">Assign policies to your users in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="d8c4b-104">**В настоящее время доступны два компонента Microsoft Teams, описанные в этой статье, [Назначение политики](#assign-a-policy-to-a-batch-of-users) и [Назначение политики для групп](#assign-a-policy-to-a-group).**</span><span class="sxs-lookup"><span data-stu-id="d8c4b-104">**Two of the Microsoft Teams features discussed in this article, [batch policy assignment](#assign-a-policy-to-a-batch-of-users) and [policy assignment to groups](#assign-a-policy-to-a-group), are currently in preview.**</span></span>

<span data-ttu-id="d8c4b-105">Администраторы используют политики для управления возможностями Teams, доступными для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-105">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="d8c4b-106">Например, вы можете присвоить имя только некоторые политики, политики собраний и политики обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-106">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="d8c4b-107">Организации имеют различные типы пользователей с уникальными потребностями, пользовательские политики, созданные и назначаемые, позволяют настраивать параметры политики для разных наборов пользователей на основе этих нужд.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-107">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="d8c4b-108">Для упрощения управления политиками в Организации Teams предлагается несколько способов назначения политик пользователям.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-108">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="d8c4b-109">Политику можно назначить непосредственно пользователям, как по отдельности, так и по масштабу в рамках задания или в группу, в которую входит пользователь.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-109">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the user is a member of.</span></span> <span data-ttu-id="d8c4b-110">Вы также можете использовать пакеты политик, чтобы назначить набор политик для пользователей в Организации, у которых есть похожие роли.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-110">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="d8c4b-111">Выбор параметра зависит от количества политик, которые вы управляете, и количества пользователей, которым вы назначаете.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-111">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span>

<span data-ttu-id="d8c4b-112">В этой статье описаны различные способы назначения политик пользователям и рекомендуемые сценарии для того, когда следует использовать эту возможность.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-112">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="d8c4b-113">Какая политика имеет приоритет?</span><span class="sxs-lookup"><span data-stu-id="d8c4b-113">Which policy takes precedence?</span></span>

<span data-ttu-id="d8c4b-114">У пользователя есть одна действующая политика для каждого типа политики.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-114">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="d8c4b-115">Возможно или даже, что пользователю явно назначена политика, и он также является членом одной или нескольких групп, которым назначена политика того же типа.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-115">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="d8c4b-116">В сценариях такого типа приоритет имеет политика.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-116">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="d8c4b-117">Действующая политика пользователя определяется в соответствии с правилами приоритета, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-117">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="d8c4b-118">Если пользователю назначена политика (отдельно или по назначению), она имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-118">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="d8c4b-119">В приведенном ниже примере действующая политика пользователя — это Линколн квадратная политика для собраний, которая непосредственно назначается пользователю.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-119">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![Схема, показывающая, как имеет приоритет более прямую назначенную политику](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="d8c4b-121">Если пользователь не назначил политике определенного типа, политика, назначенная группе, членом которой является пользователь, имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-121">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="d8c4b-122">Если пользователь является членом нескольких групп, политика, имеющая наивысший [рейтинг назначения группы](#group-assignment-ranking) для данного типа политики, имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-122">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="d8c4b-123">В этом примере действующая политика пользователя — это политика Exec Teams и HD, которая имеет наивысший рейтинг назначения относительно других групп, участником которых является этот пользователь, и которым также назначена политика того же типа политики.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-123">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![Схема, на которой показано, как действует политика, унаследованная от группы](media/assign-policies-example-group.png)

<span data-ttu-id="d8c4b-125">Если пользователь не назначил политику или не является участником ни одной из групп, которым назначена политика, пользователь получает глобальную политику (по умолчанию для всей организации) для этого типа политики.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-125">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="d8c4b-126">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-126">Here's an example.</span></span>

![Схема, показывающая, как Глобальная политика имеет приоритет](media/assign-policies-example-global.png)

<span data-ttu-id="d8c4b-128">Дополнительные сведения можно найти в разделе [правила приоритета](#precedence-rules).</span><span class="sxs-lookup"><span data-stu-id="d8c4b-128">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="d8c4b-129">Способы назначения политик</span><span class="sxs-lookup"><span data-stu-id="d8c4b-129">Ways to assign policies</span></span>

<span data-ttu-id="d8c4b-130">Ниже приведены общие сведения о способах назначения политик пользователям и рекомендуемых сценариях для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-130">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="d8c4b-131">Чтобы получить дополнительные сведения, щелкните ссылки.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-131">Click the links to learn more.</span></span>

|<span data-ttu-id="d8c4b-132">Действие</span><span class="sxs-lookup"><span data-stu-id="d8c4b-132">Do this</span></span>  |<span data-ttu-id="d8c4b-133">Если...</span><span class="sxs-lookup"><span data-stu-id="d8c4b-133">If...</span></span>  | <span data-ttu-id="d8c4b-134">Использование...</span><span class="sxs-lookup"><span data-stu-id="d8c4b-134">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="d8c4b-135">Назначение политики отдельным пользователям</span><span class="sxs-lookup"><span data-stu-id="d8c4b-135">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="d8c4b-136">Вы не знакомы с Teams и просто приступите к работе или вам нужно назначить одну или несколько политик небольшим числам пользователей.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-136">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="d8c4b-137">Центр администрирования Microsoft Teams или командлеты PowerShell в модуле PowerShell Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="d8c4b-137">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
| [<span data-ttu-id="d8c4b-138">Назначение пакета политики</span><span class="sxs-lookup"><span data-stu-id="d8c4b-138">Assign a policy package</span></span>](#assign-a-policy-package)   | <span data-ttu-id="d8c4b-139">Необходимо назначить несколько политик определенным наборам пользователей организации, которые имеют одинаковые или аналогичные роли.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-139">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="d8c4b-140">Например, вы можете назначить пакету политики образования для преподавателей в учебном заведении, чтобы предоставить им полный доступ к беседам, звонку, собраниям и пакету политики образования (дополнительный учебный учащийся) для дополнительных студентов, которые ограничивают некоторые возможности, такие как частный звонок.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-140">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="d8c4b-141">Центр администрирования Microsoft Teams или командлеты PowerShell из модуля Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="d8c4b-141">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|<span data-ttu-id="d8c4b-142">[Назначение политики пакету пользователей](#assign-a-policy-to-a-batch-of-users) (в предварительной версии)</span><span class="sxs-lookup"><span data-stu-id="d8c4b-142">[Assign a policy to a batch of users](#assign-a-policy-to-a-batch-of-users) (in preview)</span></span>   | <span data-ttu-id="d8c4b-143">Вы должны назначать политики большим наборам пользователей.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-143">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="d8c4b-144">Например, вы хотите назначить политику для сотен или тысяч пользователей в Организации одновременно.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-144">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="d8c4b-145">Командлеты PowerShell в модуле PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="d8c4b-145">PowerShell cmdlets in the Teams PowerShell module</span></span>|
|<span data-ttu-id="d8c4b-146">[Назначение политики группе](#assign-a-policy-to-a-group) (в предварительной версии)</span><span class="sxs-lookup"><span data-stu-id="d8c4b-146">[Assign a policy to a group](#assign-a-policy-to-a-group) (in preview)</span></span>   |<span data-ttu-id="d8c4b-147">Необходимо назначить политики, основанные на членстве в группе пользователя.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-147">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="d8c4b-148">Например, вы хотите назначить политику для всех пользователей в группе безопасности или подразделении.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-148">For example, you want to assign a policy to all users in a security group or organizational unit.</span></span>| <span data-ttu-id="d8c4b-149">Командлеты PowerShell в модуле PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="d8c4b-149">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="d8c4b-150">Назначение пакета политики пакету пользователей (ожидается в ближайшее время)</span><span class="sxs-lookup"><span data-stu-id="d8c4b-150">Assign a policy package to a batch of users (coming soon)</span></span> |||
| <span data-ttu-id="d8c4b-151">Назначение пакета политики группе (ожидается в ближайшее время)</span><span class="sxs-lookup"><span data-stu-id="d8c4b-151">Assign a policy package to a group (coming soon)</span></span>   | ||

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="d8c4b-152">Назначение политики отдельным пользователям</span><span class="sxs-lookup"><span data-stu-id="d8c4b-152">Assign a policy to individual users</span></span>

<span data-ttu-id="d8c4b-153">Выполните указанные ниже действия, чтобы назначить политику для отдельного пользователя или для небольшого количества пользователей за один раз.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-153">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="d8c4b-154">Использование центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d8c4b-154">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="d8c4b-155">Чтобы назначить пользователю политику, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-155">To assign a policy to a user:</span></span>

1. <span data-ttu-id="d8c4b-156">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел **Пользователи**и выберите пользователя.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-156">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="d8c4b-157">Выберите пользователя, щелкнув слева от его имени, а затем щелкните **изменить параметры**.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-157">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="d8c4b-158">Выберите политику, которую вы хотите назначить, и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-158">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="d8c4b-159">Чтобы назначить политику до 20 пользователей за один раз, ознакомьтесь с [разгруппым изменением параметров пользователей Teams](edit-user-settings-in-bulk.md).</span><span class="sxs-lookup"><span data-stu-id="d8c4b-159">To assign a policy to up to 20 users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="d8c4b-160">Кроме того, вы можете сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="d8c4b-160">Or, you can also do the following:</span></span>

1. <span data-ttu-id="d8c4b-161">В левой области навигации центра администрирования Microsoft Teams перейдите на страницу "политика".</span><span class="sxs-lookup"><span data-stu-id="d8c4b-161">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="d8c4b-162">Выберите политику, которую вы хотите назначить, щелкнув слева от ее имени.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-162">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="d8c4b-163">Выберите **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-163">Select **Manage users**.</span></span>
4. <span data-ttu-id="d8c4b-164">В области **Управление пользователями** найдите пользователя по отображаемому имени или по имени пользователя, выберите имя и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-164">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="d8c4b-165">Повторите этот шаг для каждого пользователя, которого вы хотите добавить.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-165">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="d8c4b-166">Завершив добавление пользователей, нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-166">When you're finished adding users, select **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="d8c4b-167">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="d8c4b-167">Using PowerShell</span></span>

<span data-ttu-id="d8c4b-168">У каждого типа политики есть собственный набор командлетов для управления ею.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-168">Each policy type has it's own set of cmdlets for managing it.</span></span> <span data-ttu-id="d8c4b-169">Используйте ```Grant-``` командлет для определенного типа политики, чтобы назначить политику.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-169">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="d8c4b-170">Например, можно использовать ```Grant-CsTeamsMeetingPolicy``` командлет для назначения пользователям политики собрания Teams.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-170">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="d8c4b-171">Эти командлеты включены в модуль PowerShell Skype для бизнеса Online и описаны в [справочной документации по командлетам Skype для бизнеса](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="d8c4b-171">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="d8c4b-172">Скачайте и установите [модуль PowerShell Skype для бизнеса Online](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (если вы еще этого не сделали), а затем выполните указанные ниже действия, чтобы подключиться к Skype для бизнеса Online и начать сеанс.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-172">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="d8c4b-173">В этом примере мы назначаем политику собраний Teams, которая называется политикой собраний учащихся, пользователю с именем Реда.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-173">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="d8c4b-174">Дополнительные сведения можно найти в разделе [Управление политиками через PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).</span><span class="sxs-lookup"><span data-stu-id="d8c4b-174">To learn more, see [Managing policies via PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).</span></span>

## <a name="assign-a-policy-package"></a><span data-ttu-id="d8c4b-175">Назначение пакета политики</span><span class="sxs-lookup"><span data-stu-id="d8c4b-175">Assign a policy package</span></span>

<span data-ttu-id="d8c4b-176">Пакет политики в Teams — это набор предопределенных политик и параметров политики, которые можно назначить пользователям, имеющим такие же или аналогичные роли в Организации.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-176">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="d8c4b-177">Каждый пакет политики разработан вокруг роли пользователя и включает стандартные политики и параметры политики, которые поддерживают действия, характерные для этой роли.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-177">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="d8c4b-178">Некоторые примеры пакетов политики — это пакет для образования (преподаватель) и Здравоохранение (Клиникал Worker).</span><span class="sxs-lookup"><span data-stu-id="d8c4b-178">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span>

<span data-ttu-id="d8c4b-179">Когда вы назначаете пакету политики пользователям, будут созданы политики в пакете, и вы сможете настраивать параметры каждой из них в пакете в соответствии с потребностями пользователей.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-179">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of each policy in the package to meet users' needs.</span></span>

<span data-ttu-id="d8c4b-180">Дополнительные сведения о пакетах политик, включая пошаговые инструкции по их назначению и управлению, можно найти [в разделе Управление пакетами политики в Teams](manage-policy-packages.md).</span><span class="sxs-lookup"><span data-stu-id="d8c4b-180">To learn more about policy packages, including step-by-step guidance on how to assign and manage them, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="d8c4b-181">Назначение политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="d8c4b-181">Assign a policy to a batch of users</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]
 
<span data-ttu-id="d8c4b-182">С помощью назначения пакетной политики вы можете назначить политику большим наборам пользователей за один раз, не прибегая к использованию сценария.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-182">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="d8c4b-183">С помощью ```New-CsBatchPolicyAssignmentOperationd``` командлета вы можете отправить пакет пользователей и политику, которую вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-183">You use the ```New-CsBatchPolicyAssignmentOperationd``` cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="d8c4b-184">Назначения обрабатываются как фоновая операция, и для каждого пакета создается идентификатор операции.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-184">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="d8c4b-185">Затем вы можете использовать этот ```Get-CsBatchPolicyAssignmentOperation``` командлет для отслеживания хода выполнения и состояния заданий в пакете.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-185">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="d8c4b-186">Пакет может содержать до 20 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-186">A batch can contain up to 20,000 users.</span></span> <span data-ttu-id="d8c4b-187">Вы можете указать пользователей по идентификатору объекта, имени участника-пользователя (UPN), адресу протокола инициации сеансов (SIP) или адресу электронной почты.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-187">You can specify users by their object Id, user principal name (UPN), Session Initiation Protocol (SIP) address, or email address.</span></span>

> [!NOTE]
> <span data-ttu-id="d8c4b-188">В настоящее время назначение пакетной политики недоступно для всех типов политики Teams.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-188">Currently, batch policy assignment isn't available for all Teams policy types.</span></span> <span data-ttu-id="d8c4b-189">Ознакомьтесь со списком " [New-ксбатчполициассигнментоператион](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) " для списка поддерживаемых типов политики.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-189">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="d8c4b-190">Установка и подключение к модулю Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="d8c4b-190">Install and connect to the Microsoft Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="d8c4b-191">Командлеты находятся в предварительной версии модуля PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-191">The cmdlets are in the pre-release version of the Teams PowerShell module.</span></span> <span data-ttu-id="d8c4b-192">Выполните эти действия, чтобы сначала удалить общедоступную версию модуля Teams PowerShell (если он установлен), а затем установите самую последнюю версию модуля из коллекции тестов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-192">Follow these steps to first uninstall the Generally Available version of the Teams PowerShell module (if it's installed), and then install the latest pre-release version of the module from the PowerShell Test Gallery.</span></span>

<span data-ttu-id="d8c4b-193">Если вы еще не сделали этого, выполните указанные ниже действия, чтобы зарегистрировать коллекцию тестов PowerShell в качестве надежного источника.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-193">If you haven't already, run the following to register the PowerShell Test Gallery as a trusted source.</span></span>

```powershell
Register-PSRepository -SourceLocation https://www.poshtestgallery.com/api/v2 -Name PsTestGallery -InstallationPolicy Trusted
```

<span data-ttu-id="d8c4b-194">Если вы установили общедоступную версию модуля Teams PowerShell, выполните указанные ниже действия, чтобы удалить его.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-194">If you have the Generally Available version of the Teams PowerShell module installed, run the following to uninstall it.</span></span>

```powershell
Uninstall-Module MicrosoftTeams -AllVersions
```

<span data-ttu-id="d8c4b-195">Выполните указанные ниже действия, чтобы установить последнюю версию модуля PowerShell для Microsoft Teams из коллекции тестов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-195">Run the following to install the latest Microsoft Teams PowerShell module from the PowerShell Test Gallery.</span></span>

```powershell
Install-Module MicrosoftTeams -Repository PSTestGallery
```

<span data-ttu-id="d8c4b-196">Выполните указанные ниже действия, чтобы подключиться к Teams и начать сеанс.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-196">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="d8c4b-197">Когда вам будет предложено, войдите в систему с помощью учетных данных администратора.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-197">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="d8c4b-198">Установка и подключение к модулю Azure AD PowerShell для Graph (необязательно)</span><span class="sxs-lookup"><span data-stu-id="d8c4b-198">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="d8c4b-199">Кроме того, вам может потребоваться [загрузить и установить модуль Azure AD PowerShell для Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (если вы еще не сделали этого) и подключиться к Azure AD, чтобы получить список пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-199">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="d8c4b-200">Выполните указанные ниже действия, чтобы подключиться к Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-200">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="d8c4b-201">Когда вам будет предложено, войдите в систему с помощью учетных данных администратора, используемых для подключения к Teams.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-201">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="d8c4b-202">Назначение политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="d8c4b-202">Assign a policy to a batch of users</span></span>

<span data-ttu-id="d8c4b-203">В этом примере мы используем ```New-CsBatchPolicyAssignmentOperation``` командлет, чтобы назначить политику настройки приложения с именем "Политика настройки приложения" для пакета пользователей, перечисленных в файле Users_ids. Text.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-203">In this example, we use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="d8c4b-204">В этом примере мы подключаем подключение к Azure AD, чтобы получить доступ к коллекции пользователей, а затем назначить политику сообщений с именем "Новая политика для приема на работу" для пакета пользователей, указанных в их доменных именах.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-204">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their UPNs.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.UserPrincipalName -OperationName "Example 2 batch"
```

<span data-ttu-id="d8c4b-205">Дополнительные сведения можно найти в статье [Создание и ксбатчполициассигнментоператион](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="d8c4b-205">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="d8c4b-206">Получение статуса задания пакетной обработки</span><span class="sxs-lookup"><span data-stu-id="d8c4b-206">Get the status of a batch assignment</span></span>

<span data-ttu-id="d8c4b-207">Выполните указанные ниже действия, чтобы получить сведения о состоянии задания пакета, где идентификатор операции — это значение, возвращаемое ```New-CsBatchPolicyAssignmentOperation``` командлетом для данного пакета.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-207">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="d8c4b-208">Если в выходных данных показано, что произошла ошибка, выполните указанные ниже действия, чтобы получить дополнительные сведения об ошибках ```UserState``` , которые находятся в свойстве.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-208">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="d8c4b-209">Дополнительные сведения можно найти в [статьях Get-ксбатчполициассигнментоператион](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="d8c4b-209">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="d8c4b-210">Назначение политики группе</span><span class="sxs-lookup"><span data-stu-id="d8c4b-210">Assign a policy to a group</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="d8c4b-211">Назначение политики для групп позволяет назначить политику группе пользователей, например группе безопасности или подразделению.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-211">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or organizational unit.</span></span> <span data-ttu-id="d8c4b-212">Назначение политики распространяется на пользователей группы в соответствии с правилами приоритета.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-212">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="d8c4b-213">Когда участники добавляются в группу или удаляются из нее, их унаследованные назначения политик обновляются соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-213">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="d8c4b-214">С помощью ```New-CsGroupPolicyAssignment``` командлета вы можете назначить политику группе.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-214">You use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="d8c4b-215">Вы можете указать группу, используя идентификатор объекта, адрес SIP или адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-215">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="d8c4b-216">После назначения политики она немедленно назначается группе.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-216">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="d8c4b-217">Однако обратите внимание, что распространение назначения политики для участников группы выполняется в фоновом режиме и может занять некоторое время, в зависимости от размера группы.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-217">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="d8c4b-218">Это справедливо, если политика не назначена группе, а также при добавлении пользователей в группу или удалении ее из нее.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-218">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!NOTE]
> <span data-ttu-id="d8c4b-219">В настоящее время назначение политики для групп недоступно для всех типов политики Teams.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-219">Currently, policy assignment to groups isn't available for all Teams policy types.</span></span> <span data-ttu-id="d8c4b-220">Ознакомьтесь со списком " [New-ксграупполициассигнмент](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) " для списка поддерживаемых типов политики.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-220">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="d8c4b-221">Что необходимо знать о назначении политики группам</span><span class="sxs-lookup"><span data-stu-id="d8c4b-221">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="d8c4b-222">Прежде чем приступить к работе, важно понимать правила приоритета и ранжирование назначения групп.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-222">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="d8c4b-223">Правила приоритета</span><span class="sxs-lookup"><span data-stu-id="d8c4b-223">Precedence rules</span></span>

<span data-ttu-id="d8c4b-224">Для определенного типа политики действующая политика пользователя определяется в соответствии с приведенными ниже сведениями.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-224">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="d8c4b-225">Политика, непосредственно назначенная пользователю, имеет приоритет над любыми другими политиками того же типа, которые назначены группе.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-225">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="d8c4b-226">Другими словами, если пользователю явно назначена политика определенного типа, этот пользователь не наследует политику того же типа из группы.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-226">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="d8c4b-227">Это также означает, что если пользователь имеет политику, назначенную определенному типу, вы должны удалить ее от пользователя, прежде чем она сможет наследовать политику того же типа из группы.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-227">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="d8c4b-228">Если пользователь не имеет назначенной им политики и является членом двух или более групп, а каждая группа имеет политику с таким же типом, пользователь наследует политику назначения группы, имеющую наивысший рейтинг.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-228">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="d8c4b-229">Если пользователь не является членом ни одной из групп, которым назначена политика, для него применяется Глобальная политика (по умолчанию на уровне Организации) для этого типа политики.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-229">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="d8c4b-230">Действующая политика пользователя обновляется согласно этим правилам, когда пользователь добавляется или удаляется из группы, которой назначена политика, политика не назначается группе, или политика, непосредственно назначенная пользователю, удаляется.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-230">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="d8c4b-231">Ранжирование назначения групп</span><span class="sxs-lookup"><span data-stu-id="d8c4b-231">Group assignment ranking</span></span>
 
<span data-ttu-id="d8c4b-232">Когда вы назначаете группе политику, вы указываете рейтинг для назначения группы.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-232">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="d8c4b-233">Этот параметр используется для определения политики, которую пользователь должен наследовать в качестве действующей политики, если пользователь является членом двух или более групп, и каждой группе назначена политика одного и того же типа.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-233">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="d8c4b-234">Ранжирование назначения групп определяется относительно других назначений групп того же типа.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-234">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="d8c4b-235">Например, если вы назначаете политику вызовов двум группам, задайте для ранжирования одного задания значение 1, а для другого — 2, где 1 — наивысший рейтинг.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-235">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="d8c4b-236">Ранжирование назначения групп указывает на то, что участие в группах является более важным или более релевантным по сравнению с наследованием в других группах.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-236">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="d8c4b-237">Например, предположим, что у вас есть две группы, магазин сотрудников и руководителей магазина.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-237">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="d8c4b-238">Обеим группам назначается политика вызова Teams, в котором хранятся политики вызова для сотрудников и политики звонков руководителей магазина соответственно.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-238">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="d8c4b-239">Для руководителя магазина, который находится в обеих группах, роль руководителя больше важна, чем роль сотрудника, поэтому политика звонков, назначенная группе руководителей магазина, должна иметь более высокий рейтинг.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-239">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="d8c4b-240">Сгруппирован</span><span class="sxs-lookup"><span data-stu-id="d8c4b-240">Group</span></span> |<span data-ttu-id="d8c4b-241">Имя политики вызова Teams</span><span class="sxs-lookup"><span data-stu-id="d8c4b-241">Teams calling policy name</span></span>  |<span data-ttu-id="d8c4b-242">Rank (Ранг)</span><span class="sxs-lookup"><span data-stu-id="d8c4b-242">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="d8c4b-243">Руководители магазина</span><span class="sxs-lookup"><span data-stu-id="d8c4b-243">Store Managers</span></span>   |<span data-ttu-id="d8c4b-244">Политика звонков руководителей магазина</span><span class="sxs-lookup"><span data-stu-id="d8c4b-244">Store Managers Calling Policy</span></span>         |<span data-ttu-id="d8c4b-245">1</span><span class="sxs-lookup"><span data-stu-id="d8c4b-245">1</span></span>|
|<span data-ttu-id="d8c4b-246">Магазин сотрудников</span><span class="sxs-lookup"><span data-stu-id="d8c4b-246">Store Employees</span></span>    |<span data-ttu-id="d8c4b-247">Хранение политики звонка для сотрудников</span><span class="sxs-lookup"><span data-stu-id="d8c4b-247">Store Employees Calling Policy</span></span>      |<span data-ttu-id="d8c4b-248">2</span><span class="sxs-lookup"><span data-stu-id="d8c4b-248">2</span></span>|

<span data-ttu-id="d8c4b-249">Если вы не укажете ранжирование, для назначения политики будет задан самый низкий рейтинг.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-249">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="d8c4b-250">Установка и подключение к модулю Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="d8c4b-250">Install and connect to the Microsoft Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="d8c4b-251">Командлеты находятся в предварительной версии модуля PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-251">The cmdlets are in the pre-release version of the Teams PowerShell module.</span></span> <span data-ttu-id="d8c4b-252">Выполните эти действия, чтобы сначала удалить общедоступную версию модуля Teams PowerShell (если он установлен), а затем установите самую последнюю версию модуля из коллекции тестов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-252">Follow these steps to first uninstall the Generally Available version of the Teams PowerShell module (if it's installed), and then install the latest pre-release version of the module from the PowerShell Test Gallery.</span></span>

<span data-ttu-id="d8c4b-253">Если вы еще не сделали этого, выполните указанные ниже действия, чтобы зарегистрировать коллекцию тестов PowerShell в качестве надежного источника.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-253">If you haven't already, run the following to register the PowerShell Test Gallery as a trusted source.</span></span>

```powershell
Register-PSRepository -SourceLocation https://www.poshtestgallery.com/api/v2 -Name PsTestGallery -InstallationPolicy Trusted
```

<span data-ttu-id="d8c4b-254">Если вы установили общедоступную версию модуля Teams PowerShell, выполните указанные ниже действия, чтобы удалить его.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-254">If you have the Generally Available version of the Teams PowerShell module installed, run the following to uninstall it.</span></span>

```powershell
Uninstall-Module MicrosoftTeams -AllVersions
```

<span data-ttu-id="d8c4b-255">Выполните указанные ниже действия, чтобы установить последнюю версию модуля PowerShell для Microsoft Teams из коллекции тестов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-255">Run the following to install the latest Microsoft Teams PowerShell module from the PowerShell Test Gallery.</span></span>

```powershell
Install-Module MicrosoftTeams -Repository PSTestGallery
```

<span data-ttu-id="d8c4b-256">Выполните указанные ниже действия, чтобы подключиться к Teams и начать сеанс.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-256">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="d8c4b-257">Когда вам будет предложено, войдите в систему с помощью учетных данных администратора.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-257">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="d8c4b-258">Назначение политики группе</span><span class="sxs-lookup"><span data-stu-id="d8c4b-258">Assign a policy to a group</span></span>

<span data-ttu-id="d8c4b-259">В этом примере мы используем ```New-CsGroupPolicyAssignment``` командлет для назначения политики собрания Team Manager в группе с рейтингом назначения 1.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-259">In this example, we use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

<span data-ttu-id="d8c4b-260">Дополнительные сведения можно найти в статье [Создание и ксграупполициассигнмент](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="d8c4b-260">To learn more, see [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span></span>

### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="d8c4b-261">Получение назначений политики для группы</span><span class="sxs-lookup"><span data-stu-id="d8c4b-261">Get policy assignments for a group</span></span>

<span data-ttu-id="d8c4b-262">Используйте командлет ```Get-CsGroupPolicyAssignment``` , чтобы получить все политики, назначенные группе.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-262">Use the ```Get-CsGroupPolicyAssignment``` cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="d8c4b-263">Обратите внимание, что группы всегда записываются в соответствии с их идентификатором группы, даже если для назначения политики был использован адрес SIP или адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-263">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="d8c4b-264">В этом примере мы извлекаем все политики, назначенные определенной группе.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-264">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="d8c4b-265">В этом примере мы возвращаем все группы, которым назначена политика для собрания Teams.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-265">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

<span data-ttu-id="d8c4b-266">Дополнительные сведения можно найти в [статьях Get-ксграупполициассигнмент](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="d8c4b-266">To learn more, see [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span></span>

### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="d8c4b-267">Удаление политики из группы</span><span class="sxs-lookup"><span data-stu-id="d8c4b-267">Remove a policy from a group</span></span>

<span data-ttu-id="d8c4b-268">Используйте ```Remove-CsGroupPolicyAssignment``` командлет для удаления политики из группы.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-268">Use the ```Remove-CsGroupPolicyAssignment``` cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="d8c4b-269">При удалении политики из группы приоритеты других политик того же типа, которым назначена эта группа, и которые имеют более низкий рейтинг, будут обновлены.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-269">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="d8c4b-270">Например, если вы удалите политику с рангом 2, то политики с рейтингом 3 и 4 будут обновляться в соответствии с их новым рейтингом.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-270">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="d8c4b-271">Этот пример показан в двух приведенных ниже таблицах.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-271">The following two tables show this example.</span></span>

<span data-ttu-id="d8c4b-272">Ниже приведен список назначений и приоритетов политики для собраний Teams.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-272">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="d8c4b-273">Имя группы</span><span class="sxs-lookup"><span data-stu-id="d8c4b-273">Group name</span></span>  |<span data-ttu-id="d8c4b-274">Название политики</span><span class="sxs-lookup"><span data-stu-id="d8c4b-274">Policy name</span></span>  |<span data-ttu-id="d8c4b-275">Rank (Ранг)</span><span class="sxs-lookup"><span data-stu-id="d8c4b-275">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="d8c4b-276">Продажи</span><span class="sxs-lookup"><span data-stu-id="d8c4b-276">Sales</span></span>    |<span data-ttu-id="d8c4b-277">Политика продаж</span><span class="sxs-lookup"><span data-stu-id="d8c4b-277">Sales policy</span></span>       | <span data-ttu-id="d8c4b-278">1</span><span class="sxs-lookup"><span data-stu-id="d8c4b-278">1</span></span>        |
|<span data-ttu-id="d8c4b-279">Западная область</span><span class="sxs-lookup"><span data-stu-id="d8c4b-279">West Region</span></span>     |<span data-ttu-id="d8c4b-280">Политика "Западная область"</span><span class="sxs-lookup"><span data-stu-id="d8c4b-280">West Region policy</span></span>         |<span data-ttu-id="d8c4b-281">2</span><span class="sxs-lookup"><span data-stu-id="d8c4b-281">2</span></span>         |
|<span data-ttu-id="d8c4b-282">Умножен</span><span class="sxs-lookup"><span data-stu-id="d8c4b-282">Division</span></span>    |<span data-ttu-id="d8c4b-283">Политика деления</span><span class="sxs-lookup"><span data-stu-id="d8c4b-283">Division policy</span></span>         |<span data-ttu-id="d8c4b-284">3</span><span class="sxs-lookup"><span data-stu-id="d8c4b-284">3</span></span>         |
|<span data-ttu-id="d8c4b-285">Отделения</span><span class="sxs-lookup"><span data-stu-id="d8c4b-285">Subsidiary</span></span>   |<span data-ttu-id="d8c4b-286">Политика для дочерних компаний</span><span class="sxs-lookup"><span data-stu-id="d8c4b-286">Subsidiary policy</span></span>        |<span data-ttu-id="d8c4b-287">4</span><span class="sxs-lookup"><span data-stu-id="d8c4b-287">4</span></span>         |

<span data-ttu-id="d8c4b-288">Если удалить политику западных областей из группы Западная область, то назначения и приоритеты политики будут обновляться следующим образом.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-288">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="d8c4b-289">Имя группы</span><span class="sxs-lookup"><span data-stu-id="d8c4b-289">Group name</span></span>  |<span data-ttu-id="d8c4b-290">Название политики</span><span class="sxs-lookup"><span data-stu-id="d8c4b-290">Policy name</span></span>  |<span data-ttu-id="d8c4b-291">Rank (Ранг)</span><span class="sxs-lookup"><span data-stu-id="d8c4b-291">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="d8c4b-292">Продажи</span><span class="sxs-lookup"><span data-stu-id="d8c4b-292">Sales</span></span>    |<span data-ttu-id="d8c4b-293">Политика продаж</span><span class="sxs-lookup"><span data-stu-id="d8c4b-293">Sales policy</span></span>       | <span data-ttu-id="d8c4b-294">1</span><span class="sxs-lookup"><span data-stu-id="d8c4b-294">1</span></span>        |
|<span data-ttu-id="d8c4b-295">Умножен</span><span class="sxs-lookup"><span data-stu-id="d8c4b-295">Division</span></span>    |<span data-ttu-id="d8c4b-296">Политика деления</span><span class="sxs-lookup"><span data-stu-id="d8c4b-296">Division policy</span></span>         |<span data-ttu-id="d8c4b-297">2</span><span class="sxs-lookup"><span data-stu-id="d8c4b-297">2</span></span>         |
|<span data-ttu-id="d8c4b-298">Отделения</span><span class="sxs-lookup"><span data-stu-id="d8c4b-298">Subsidiary</span></span>   |<span data-ttu-id="d8c4b-299">Политика для дочерних компаний</span><span class="sxs-lookup"><span data-stu-id="d8c4b-299">Subsidiary policy</span></span>        |<span data-ttu-id="d8c4b-300">3</span><span class="sxs-lookup"><span data-stu-id="d8c4b-300">3</span></span>        |

<span data-ttu-id="d8c4b-301">В данном примере политика для собрания Teams удаляется из группы.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-301">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

<span data-ttu-id="d8c4b-302">Дополнительные сведения можно найти в разделе [Remove-ксграупполициассигнмент](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="d8c4b-302">To learn more, see [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span></span>

### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="d8c4b-303">Изменение назначения политики для группы</span><span class="sxs-lookup"><span data-stu-id="d8c4b-303">Change a policy assignment for a group</span></span>

<span data-ttu-id="d8c4b-304">После назначения политики группе вы можете использовать ```Set-CsGroupPolicyAssignmentd``` командлет, чтобы изменить назначение политики этой группы следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d8c4b-304">After you assign a policy to a group, you can use the ```Set-CsGroupPolicyAssignmentd``` cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="d8c4b-305">Изменение ранжирования</span><span class="sxs-lookup"><span data-stu-id="d8c4b-305">Change the ranking</span></span>
- <span data-ttu-id="d8c4b-306">Изменение политики для определенного типа политики</span><span class="sxs-lookup"><span data-stu-id="d8c4b-306">Change the policy of a given policy type</span></span>
- <span data-ttu-id="d8c4b-307">Изменение политики для определенного типа политики и ранжирования</span><span class="sxs-lookup"><span data-stu-id="d8c4b-307">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="d8c4b-308">В этом примере мы изменим политику приостановки вызовов групп для группы на политику с именем Суппорткаллпарк и рейтинг назначения 3.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-308">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

<span data-ttu-id="d8c4b-309">Дополнительные сведения можно найти в статье [Set-ксграупполициассигнмент](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="d8c4b-309">To learn more, see [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span></span>

### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="d8c4b-310">Изменение действующей политики для пользователя</span><span class="sxs-lookup"><span data-stu-id="d8c4b-310">Change the effective policy for a user</span></span>

<span data-ttu-id="d8c4b-311">Ниже приведен пример изменения действующей политики для пользователя, которому непосредственно назначена политика.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-311">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="d8c4b-312">Сначала мы используем ```Get-CsUserPolicyAssignment``` командлет вместе с ```PolicySource``` параметром, чтобы получить подробные сведения о политиках широковещательного показа собраний Teams, связанных с пользователем.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-312">First, we use the ```Get-CsUserPolicyAssignment``` cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> <span data-ttu-id="d8c4b-313">Дополнительные сведения можно найти в [статьях Get-ксусерполициассигнмент](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="d8c4b-313">To learn more, see [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="d8c4b-314">В выходных данных показано, что пользователю непосредственно назначена политика широковещательного показа собрания Teams, которая имеет приоритет над политикой "события поставщика", назначенной группе, в которую входит пользователь.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-314">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="d8c4b-315">Теперь мы удаляем политику событий сотрудников от пользователя.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-315">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="d8c4b-316">Это означает, что пользователь больше не имеет политики широковещательного показа собраний Teams, которой они назначены, и будет наследовать политику Live Events поставщика, назначенную группе, которой принадлежит пользователь.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-316">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="d8c4b-317">Для этого используйте следующий командлет в модуле Skype для бизнеса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-317">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="d8c4b-318">Вы можете использовать следующий командлет в модуле Teams PowerShell для выполнения этой задачи при масштабировании при использовании задания пакетной политики, где $users — это список пользователей, которые вы указали.</span><span class="sxs-lookup"><span data-stu-id="d8c4b-318">You can use following cmdlet in the Teams Powershell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="related-topics"></a><span data-ttu-id="d8c4b-319">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="d8c4b-319">Related topics</span></span>

- [<span data-ttu-id="d8c4b-320">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="d8c4b-320">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)