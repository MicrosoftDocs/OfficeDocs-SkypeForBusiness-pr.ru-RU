---
title: Назначение политик вашим пользователям в Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: tomkau, saragava, ritikag, jastark
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
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: ae007641734b71a34d9021283704d6b210626a28
ms.sourcegitcommit: 86b0956680b867b8bedb2e969220b8006829ee53
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/28/2020
ms.locfileid: "44410464"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="f65ca-103">Назначение политик вашим пользователям в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f65ca-103">Assign policies to your users in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="f65ca-104">**Одна из функций Microsoft Teams, описанных в этой статье, [Назначение политики для групп](#assign-a-policy-to-a-group), в настоящее время доступна только в частном предварительной версии. Командлеты PowerShell для этой функции находятся в предварительной версии модуля PowerShell для Teams.**</span><span class="sxs-lookup"><span data-stu-id="f65ca-104">**One of the Microsoft Teams features discussed in this article, [policy assignment to groups](#assign-a-policy-to-a-group), is currently only available in private preview. The Powershell cmdlets for this feature are in the pre-release Teams PowerShell module.**</span></span> <span data-ttu-id="f65ca-105">Чтобы не отвлекаться от состояния выпусков этой функции, ознакомьтесь с [планом Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185).</span><span class="sxs-lookup"><span data-stu-id="f65ca-105">To stay on top of the release status of this feature, check out the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185).</span></span>

<span data-ttu-id="f65ca-106">Администраторы используют политики для управления возможностями Teams, доступными для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f65ca-106">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="f65ca-107">Например, вы можете присвоить имя только некоторые политики, политики собраний и политики обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="f65ca-107">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="f65ca-108">Организации имеют различные типы пользователей с уникальными потребностями, пользовательские политики, созданные и назначаемые, позволяют настраивать параметры политики для разных наборов пользователей на основе этих нужд.</span><span class="sxs-lookup"><span data-stu-id="f65ca-108">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="f65ca-109">Для упрощения управления политиками в Организации Teams предлагается несколько способов назначения политик пользователям.</span><span class="sxs-lookup"><span data-stu-id="f65ca-109">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="f65ca-110">Политику можно назначить непосредственно пользователям, как по отдельности, так и по масштабу в рамках задания или в группу, в которую входит пользователь.</span><span class="sxs-lookup"><span data-stu-id="f65ca-110">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the user is a member of.</span></span> <span data-ttu-id="f65ca-111">Вы также можете использовать пакеты политик, чтобы назначить набор политик для пользователей в Организации, у которых есть похожие роли.</span><span class="sxs-lookup"><span data-stu-id="f65ca-111">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="f65ca-112">Выбор параметра зависит от количества политик, которые вы управляете, и количества пользователей, которым вы назначаете.</span><span class="sxs-lookup"><span data-stu-id="f65ca-112">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span>

<span data-ttu-id="f65ca-113">В этой статье описаны различные способы назначения политик пользователям и рекомендуемые сценарии для того, когда следует использовать эту возможность.</span><span class="sxs-lookup"><span data-stu-id="f65ca-113">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="f65ca-114">Какая политика имеет приоритет?</span><span class="sxs-lookup"><span data-stu-id="f65ca-114">Which policy takes precedence?</span></span>

<span data-ttu-id="f65ca-115">У пользователя есть одна действующая политика для каждого типа политики.</span><span class="sxs-lookup"><span data-stu-id="f65ca-115">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="f65ca-116">Возможно или даже, что пользователю явно назначена политика, и он также является членом одной или нескольких групп, которым назначена политика того же типа.</span><span class="sxs-lookup"><span data-stu-id="f65ca-116">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="f65ca-117">В сценариях такого типа приоритет имеет политика.</span><span class="sxs-lookup"><span data-stu-id="f65ca-117">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="f65ca-118">Действующая политика пользователя определяется в соответствии с правилами приоритета, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="f65ca-118">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="f65ca-119">Если пользователю назначена политика (отдельно или по назначению), она имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="f65ca-119">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="f65ca-120">В приведенном ниже примере действующая политика пользователя — это Lincoln квадратная политика для собраний, которая непосредственно назначается пользователю.</span><span class="sxs-lookup"><span data-stu-id="f65ca-120">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![Схема, показывающая, как имеет приоритет более прямую назначенную политику](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="f65ca-122">Если пользователь не назначил политике определенного типа, политика, назначенная группе, членом которой является пользователь, имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="f65ca-122">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="f65ca-123">Если пользователь является членом нескольких групп, политика, имеющая наивысший [рейтинг назначения группы](#group-assignment-ranking) для данного типа политики, имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="f65ca-123">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="f65ca-124">В этом примере действующая политика пользователя — это политика Exec Teams и HD, которая имеет наивысший рейтинг назначения относительно других групп, участником которых является этот пользователь, и которым также назначена политика того же типа политики.</span><span class="sxs-lookup"><span data-stu-id="f65ca-124">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![Схема, на которой показано, как действует политика, унаследованная от группы](media/assign-policies-example-group.png)

<span data-ttu-id="f65ca-126">Если пользователь не назначил политику или не является участником ни одной из групп, которым назначена политика, пользователь получает глобальную политику (по умолчанию для всей организации) для этого типа политики.</span><span class="sxs-lookup"><span data-stu-id="f65ca-126">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="f65ca-127">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="f65ca-127">Here's an example.</span></span>

![Схема, показывающая, как Глобальная политика имеет приоритет](media/assign-policies-example-global.png)

<span data-ttu-id="f65ca-129">Дополнительные сведения можно найти в разделе [правила приоритета](#precedence-rules).</span><span class="sxs-lookup"><span data-stu-id="f65ca-129">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="f65ca-130">Способы назначения политик</span><span class="sxs-lookup"><span data-stu-id="f65ca-130">Ways to assign policies</span></span>

<span data-ttu-id="f65ca-131">Ниже приведены общие сведения о способах назначения политик пользователям и рекомендуемых сценариях для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="f65ca-131">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="f65ca-132">Чтобы получить дополнительные сведения, щелкните ссылки.</span><span class="sxs-lookup"><span data-stu-id="f65ca-132">Click the links to learn more.</span></span>

|<span data-ttu-id="f65ca-133">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="f65ca-133">Do this</span></span>  |<span data-ttu-id="f65ca-134">Если...</span><span class="sxs-lookup"><span data-stu-id="f65ca-134">If...</span></span>  | <span data-ttu-id="f65ca-135">Использование...</span><span class="sxs-lookup"><span data-stu-id="f65ca-135">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="f65ca-136">Назначение политики отдельным пользователям</span><span class="sxs-lookup"><span data-stu-id="f65ca-136">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="f65ca-137">Вы не знакомы с Teams и просто приступите к работе или вам нужно назначить одну или несколько политик небольшим числам пользователей.</span><span class="sxs-lookup"><span data-stu-id="f65ca-137">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="f65ca-138">Центр администрирования Microsoft Teams или командлеты PowerShell в модуле PowerShell Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="f65ca-138">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
| [<span data-ttu-id="f65ca-139">Назначение пакета политики</span><span class="sxs-lookup"><span data-stu-id="f65ca-139">Assign a policy package</span></span>](#assign-a-policy-package)   | <span data-ttu-id="f65ca-140">Необходимо назначить несколько политик определенным наборам пользователей организации, которые имеют одинаковые или аналогичные роли.</span><span class="sxs-lookup"><span data-stu-id="f65ca-140">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="f65ca-141">Например, назначьте в учебном заведении пакет политики образования для преподавателей, чтобы предоставить им полный доступ к беседам, звонку, собраниям и пакету политики образования (дополнительный учебный учащийся), чтобы ограничить некоторые возможности, такие как частный звонок.</span><span class="sxs-lookup"><span data-stu-id="f65ca-141">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="f65ca-142">Центр администрирования Microsoft Teams или командлеты PowerShell из модуля Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="f65ca-142">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="f65ca-143">Назначение политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="f65ca-143">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="f65ca-144">Вы должны назначать политики большим наборам пользователей.</span><span class="sxs-lookup"><span data-stu-id="f65ca-144">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="f65ca-145">Например, вы хотите назначить политику для сотен или тысяч пользователей в Организации одновременно.</span><span class="sxs-lookup"><span data-stu-id="f65ca-145">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="f65ca-146">Центр администрирования Microsoft Teams или командлеты PowerShell из модуля Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="f65ca-146">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|<span data-ttu-id="f65ca-147">[Назначение политики группе](#assign-a-policy-to-a-group) (в предварительной версии)</span><span class="sxs-lookup"><span data-stu-id="f65ca-147">[Assign a policy to a group](#assign-a-policy-to-a-group) (in preview)</span></span>   |<span data-ttu-id="f65ca-148">Необходимо назначить политики, основанные на членстве в группе пользователя.</span><span class="sxs-lookup"><span data-stu-id="f65ca-148">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="f65ca-149">Например, вы хотите назначить политику для всех пользователей в группе безопасности или подразделении.</span><span class="sxs-lookup"><span data-stu-id="f65ca-149">For example, you want to assign a policy to all users in a security group or organizational unit.</span></span>| <span data-ttu-id="f65ca-150">Командлеты PowerShell в модуле PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="f65ca-150">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="f65ca-151">Назначение пакета политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="f65ca-151">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="f65ca-152">Необходимо назначить несколько политик для пакета пользователей в Организации с одинаковыми или аналогичными ролями.</span><span class="sxs-lookup"><span data-stu-id="f65ca-152">You need to assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="f65ca-153">Например, вы можете назначить пакету политики образования для всех преподавателей в учебном заведении с помощью пакетного задания, чтобы предоставить им полный доступ к разговорам, звонкам и собраниям, а также назначить пакету политики образования (дополнительный учебный учащийся) пакету вспомогательных учащихся, чтобы ограничить некоторые возможности, такие как частный звонок.</span><span class="sxs-lookup"><span data-stu-id="f65ca-153">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings and assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities like private calling.</span></span>|<span data-ttu-id="f65ca-154">Командлеты PowerShell в модуле PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="f65ca-154">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="f65ca-155">Назначение пакета политики группе (ожидается в ближайшее время)</span><span class="sxs-lookup"><span data-stu-id="f65ca-155">Assign a policy package to a group (coming soon)</span></span>   | ||

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="f65ca-156">Назначение политики отдельным пользователям</span><span class="sxs-lookup"><span data-stu-id="f65ca-156">Assign a policy to individual users</span></span>

<span data-ttu-id="f65ca-157">Выполните указанные ниже действия, чтобы назначить политику для отдельного пользователя или для небольшого количества пользователей за один раз.</span><span class="sxs-lookup"><span data-stu-id="f65ca-157">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="f65ca-158">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f65ca-158">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="f65ca-159">Чтобы назначить пользователю политику, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="f65ca-159">To assign a policy to a user:</span></span>

1. <span data-ttu-id="f65ca-160">В Центре администрирования Microsoft Teams в области навигации слева перейдите в раздел **Пользователи**, затем щелкните пользователя.</span><span class="sxs-lookup"><span data-stu-id="f65ca-160">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="f65ca-161">Выберите пользователя, щелкнув слева от его имени, затем нажмите кнопку **Изменить параметры**.</span><span class="sxs-lookup"><span data-stu-id="f65ca-161">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="f65ca-162">Выберите политику, которую вы хотите назначить, и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="f65ca-162">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="f65ca-163">Кроме того, вы можете сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="f65ca-163">Or, you can also do the following:</span></span>

1. <span data-ttu-id="f65ca-164">В левой области навигации центра администрирования Microsoft Teams перейдите на страницу "политика".</span><span class="sxs-lookup"><span data-stu-id="f65ca-164">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="f65ca-165">Выберите политику, которую вы хотите назначить, щелкнув слева от ее имени.</span><span class="sxs-lookup"><span data-stu-id="f65ca-165">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="f65ca-166">Выберите **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="f65ca-166">Select **Manage users**.</span></span>
4. <span data-ttu-id="f65ca-167">В области **Управление пользователями** выполните поиск по отображаемому имени или по имени пользователя, выберите имя и нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="f65ca-167">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="f65ca-168">Повторите это действие для каждого пользователя, которого нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="f65ca-168">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="f65ca-169">Завершив добавление пользователей, нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f65ca-169">When you're finished adding users, select **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="f65ca-170">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="f65ca-170">Using PowerShell</span></span>

<span data-ttu-id="f65ca-171">У каждого типа политики есть собственный набор командлетов для управления ею.</span><span class="sxs-lookup"><span data-stu-id="f65ca-171">Each policy type has it's own set of cmdlets for managing it.</span></span> <span data-ttu-id="f65ca-172">Используйте ```Grant-``` командлет для определенного типа политики, чтобы назначить политику.</span><span class="sxs-lookup"><span data-stu-id="f65ca-172">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="f65ca-173">Например, ```Grant-CsTeamsMeetingPolicy``` можно использовать командлет для назначения пользователям политики собрания Teams.</span><span class="sxs-lookup"><span data-stu-id="f65ca-173">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="f65ca-174">Эти командлеты включены в модуль PowerShell Skype для бизнеса Online и описаны в [справочной документации по командлетам Skype для бизнеса](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f65ca-174">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="f65ca-175">Скачайте и установите [модуль PowerShell Skype для бизнеса Online](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (если вы еще этого не сделали), а затем выполните указанные ниже действия, чтобы подключиться к Skype для бизнеса Online и начать сеанс.</span><span class="sxs-lookup"><span data-stu-id="f65ca-175">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="f65ca-176">В этом примере мы назначаем политику собраний Teams, которая называется политикой собраний учащихся, пользователю с именем Reda.</span><span class="sxs-lookup"><span data-stu-id="f65ca-176">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="f65ca-177">Дополнительные сведения можно найти в разделе [Управление политиками через PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).</span><span class="sxs-lookup"><span data-stu-id="f65ca-177">To learn more, see [Managing policies via PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).</span></span>

## <a name="assign-a-policy-package"></a><span data-ttu-id="f65ca-178">Назначение пакета политики</span><span class="sxs-lookup"><span data-stu-id="f65ca-178">Assign a policy package</span></span>

<span data-ttu-id="f65ca-179">Пакет политики в Teams — это набор предопределенных политик и параметров политики, которые можно назначить пользователям, имеющим такие же или аналогичные роли в Организации.</span><span class="sxs-lookup"><span data-stu-id="f65ca-179">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="f65ca-180">Каждый пакет политики разработан вокруг роли пользователя и включает стандартные политики и параметры политики, которые поддерживают действия, характерные для этой роли.</span><span class="sxs-lookup"><span data-stu-id="f65ca-180">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="f65ca-181">Некоторые примеры пакетов политики — это пакет для образования (преподаватель) и Здравоохранение (Clinical Worker).</span><span class="sxs-lookup"><span data-stu-id="f65ca-181">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span>

<span data-ttu-id="f65ca-182">Когда вы назначаете пакету политики пользователям, будут созданы политики в пакете, и вы сможете настраивать параметры каждой из них в пакете в соответствии с потребностями пользователей.</span><span class="sxs-lookup"><span data-stu-id="f65ca-182">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of each policy in the package to meet users' needs.</span></span>

<span data-ttu-id="f65ca-183">Дополнительные сведения о пакетах политик, включая пошаговые инструкции по их назначению и управлению, можно найти [в разделе Управление пакетами политики в Teams](manage-policy-packages.md).</span><span class="sxs-lookup"><span data-stu-id="f65ca-183">To learn more about policy packages, including step-by-step guidance on how to assign and manage them, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="f65ca-184">Назначение политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="f65ca-184">Assign a policy to a batch of users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="f65ca-185">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f65ca-185">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="f65ca-186">Чтобы назначить политику для пользователей, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="f65ca-186">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="f65ca-187">В левой области навигации центра администрирования Microsoft Teams выберите пункт **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="f65ca-187">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="f65ca-188">Найдите пользователей, которым вы хотите назначить политику, или отфильтруйте представление, чтобы отобразить нужных пользователей.</span><span class="sxs-lookup"><span data-stu-id="f65ca-188">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="f65ca-189">В столбце **&#x2713;** (галочка) выберите пользователей.</span><span class="sxs-lookup"><span data-stu-id="f65ca-189">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="f65ca-190">Чтобы выбрать всех пользователей, щелкните &#x2713; (галочку) в верхней части таблицы.</span><span class="sxs-lookup"><span data-stu-id="f65ca-190">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="f65ca-191">Щелкните **Изменить настройки**, внесите нужные изменения и нажмите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="f65ca-191">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="f65ca-192">Чтобы просмотреть состояние назначения политики, в заголовке, который появляется в верхней части страницы **пользователей** после нажатия кнопки **Применить** для отправки назначения политики, щелкните **Журнал активности**.</span><span class="sxs-lookup"><span data-stu-id="f65ca-192">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you click **Apply** to submit your policy assignment, click **Activity log**.</span></span> <span data-ttu-id="f65ca-193">Либо в левой области навигации центра администрирования Microsoft Teams перейдите на **панель мониторинга**, а затем в разделе **Журнал активности**щелкните **Просмотреть сведения**.</span><span class="sxs-lookup"><span data-stu-id="f65ca-193">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, click **View details**.</span></span> <span data-ttu-id="f65ca-194">Журнал активности показывает назначения политики для пакетов более чем из 20 пользователей в центре администрирования Microsoft Teams за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="f65ca-194">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="f65ca-195">Дополнительные сведения можно найти [в статье Просмотр назначенных политик в журнале событий](activity-log.md).</span><span class="sxs-lookup"><span data-stu-id="f65ca-195">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="f65ca-196">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="f65ca-196">Using PowerShell</span></span>
 
<span data-ttu-id="f65ca-197">С помощью назначения пакетной политики вы можете назначить политику большим наборам пользователей за один раз, не прибегая к использованию сценария.</span><span class="sxs-lookup"><span data-stu-id="f65ca-197">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="f65ca-198">```New-CsBatchPolicyAssignmentOperationd```С помощью командлета вы можете отправить пакет пользователей и политику, которую вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="f65ca-198">You use the ```New-CsBatchPolicyAssignmentOperationd``` cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="f65ca-199">Назначения обрабатываются как фоновая операция, и для каждого пакета создается идентификатор операции.</span><span class="sxs-lookup"><span data-stu-id="f65ca-199">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="f65ca-200">Затем вы можете использовать этот ```Get-CsBatchPolicyAssignmentOperation``` командлет для отслеживания хода выполнения и состояния заданий в пакете.</span><span class="sxs-lookup"><span data-stu-id="f65ca-200">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span> 

<span data-ttu-id="f65ca-201">Вы можете указать пользователей по идентификатору объекта, имени участника-пользователя (UPN), адресу протокола инициации сеансов (SIP) или адресу электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f65ca-201">You can specify users by their object Id, user principal name (UPN), Session Initiation Protocol (SIP) address, or email address.</span></span> <span data-ttu-id="f65ca-202">Если пакет включает повторяющиеся пользователи, дубликаты удаляются из пакета перед обработкой и состоянием будут предоставляться только для уникальных пользователей, остающихся в пакете.</span><span class="sxs-lookup"><span data-stu-id="f65ca-202">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="f65ca-203">Пакет может содержать до 5 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="f65ca-203">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="f65ca-204">Для достижения наилучших результатов не отправляйте более нескольких пакетов одновременно.</span><span class="sxs-lookup"><span data-stu-id="f65ca-204">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="f65ca-205">Разрешите пакетам завершить обработку перед отправкой пакетов.</span><span class="sxs-lookup"><span data-stu-id="f65ca-205">Allow batches to complete processing before submitting more batches.</span></span>

> [!NOTE]
> <span data-ttu-id="f65ca-206">В настоящее время назначение пакетной политики недоступно для всех типов политики Teams.</span><span class="sxs-lookup"><span data-stu-id="f65ca-206">Currently, batch policy assignment isn't available for all Teams policy types.</span></span> <span data-ttu-id="f65ca-207">Ознакомьтесь со списком " [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) " для списка поддерживаемых типов политики.</span><span class="sxs-lookup"><span data-stu-id="f65ca-207">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="f65ca-208">Установка и подключение к модулю Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="f65ca-208">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="f65ca-209">Выполните указанные ниже действия, чтобы установить [модуль PowerShell Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams).</span><span class="sxs-lookup"><span data-stu-id="f65ca-209">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="f65ca-210">Убедитесь, что вы установили версию 1.0.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="f65ca-210">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="f65ca-211">Выполните указанные ниже действия, чтобы подключиться к Teams и начать сеанс.</span><span class="sxs-lookup"><span data-stu-id="f65ca-211">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="f65ca-212">Когда вам будет предложено, войдите в систему с помощью учетных данных администратора.</span><span class="sxs-lookup"><span data-stu-id="f65ca-212">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="f65ca-213">Установка и подключение к модулю Azure AD PowerShell для Graph (необязательно)</span><span class="sxs-lookup"><span data-stu-id="f65ca-213">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="f65ca-214">Кроме того, вам может потребоваться [загрузить и установить модуль Azure AD PowerShell для Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (если вы еще не сделали этого) и подключиться к Azure AD, чтобы получить список пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="f65ca-214">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="f65ca-215">Выполните указанные ниже действия, чтобы подключиться к Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f65ca-215">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="f65ca-216">Когда вам будет предложено, войдите в систему с помощью учетных данных администратора, используемых для подключения к Teams.</span><span class="sxs-lookup"><span data-stu-id="f65ca-216">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="f65ca-217">Назначение политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="f65ca-217">Assign a policy to a batch of users</span></span>

<span data-ttu-id="f65ca-218">В этом примере мы используем командлет, ```New-CsBatchPolicyAssignmentOperation``` чтобы назначить политику настройки приложения с именем "Политика настройки приложения" для пакета пользователей, перечисленных в файле Users_ids. Text.</span><span class="sxs-lookup"><span data-stu-id="f65ca-218">In this example, we use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="f65ca-219">В этом примере мы подключаем подключение к Azure AD, чтобы получить доступ к коллекции пользователей, а затем назначить политику сообщений с именем "Новая политика для приема на работу" для пакета пользователей, указанных в их доменных именах.</span><span class="sxs-lookup"><span data-stu-id="f65ca-219">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their UPNs.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.UserPrincipalName -OperationName "Example 2 batch"
```

<span data-ttu-id="f65ca-220">Дополнительные сведения можно найти в статье [Создание и CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="f65ca-220">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="f65ca-221">Получение статуса задания пакетной обработки</span><span class="sxs-lookup"><span data-stu-id="f65ca-221">Get the status of a batch assignment</span></span>

<span data-ttu-id="f65ca-222">Выполните указанные ниже действия, чтобы получить сведения о состоянии задания пакета, где идентификатор операции — это значение, возвращаемое ```New-CsBatchPolicyAssignmentOperation``` командлетом для данного пакета.</span><span class="sxs-lookup"><span data-stu-id="f65ca-222">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="f65ca-223">Если в выходных данных показано, что произошла ошибка, выполните указанные ниже действия, чтобы получить дополнительные сведения об ошибках, которые находятся в ```UserState``` свойстве.</span><span class="sxs-lookup"><span data-stu-id="f65ca-223">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="f65ca-224">Дополнительные сведения можно найти в [статьях Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="f65ca-224">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="f65ca-225">Назначение политики группе</span><span class="sxs-lookup"><span data-stu-id="f65ca-225">Assign a policy to a group</span></span>

<span data-ttu-id="f65ca-226">**Назначение политики для групп в настоящее время доступно только в частном предварительной версии. Командлеты для этой функции находятся в предварительной версии модуля PowerShell для Teams.**</span><span class="sxs-lookup"><span data-stu-id="f65ca-226">**Policy assignment to groups is currently only available in private preview. The cmdlets for this feature are in the pre-release Teams PowerShell module.**</span></span>

<span data-ttu-id="f65ca-227">Назначение политики для групп позволяет назначить политику группе пользователей, например группе безопасности или подразделению.</span><span class="sxs-lookup"><span data-stu-id="f65ca-227">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or organizational unit.</span></span> <span data-ttu-id="f65ca-228">Назначение политики распространяется на пользователей группы в соответствии с правилами приоритета.</span><span class="sxs-lookup"><span data-stu-id="f65ca-228">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="f65ca-229">Когда участники добавляются в группу или удаляются из нее, их унаследованные назначения политик обновляются соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="f65ca-229">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="f65ca-230">С помощью ```New-CsGroupPolicyAssignment``` командлета вы можете назначить политику группе.</span><span class="sxs-lookup"><span data-stu-id="f65ca-230">You use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="f65ca-231">Вы можете указать группу, используя идентификатор объекта, адрес SIP или адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f65ca-231">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="f65ca-232">После назначения политики она немедленно назначается группе.</span><span class="sxs-lookup"><span data-stu-id="f65ca-232">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="f65ca-233">Однако обратите внимание, что распространение назначения политики для участников группы выполняется в фоновом режиме и может занять некоторое время, в зависимости от размера группы.</span><span class="sxs-lookup"><span data-stu-id="f65ca-233">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="f65ca-234">Это справедливо, если политика не назначена группе, а также при добавлении пользователей в группу или удалении ее из нее.</span><span class="sxs-lookup"><span data-stu-id="f65ca-234">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!NOTE]
> <span data-ttu-id="f65ca-235">В настоящее время назначение политики для групп недоступно для всех типов политики Teams.</span><span class="sxs-lookup"><span data-stu-id="f65ca-235">Currently, policy assignment to groups isn't available for all Teams policy types.</span></span> <span data-ttu-id="f65ca-236">Ознакомьтесь со списком " [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) " для списка поддерживаемых типов политики.</span><span class="sxs-lookup"><span data-stu-id="f65ca-236">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="f65ca-237">Что необходимо знать о назначении политики группам</span><span class="sxs-lookup"><span data-stu-id="f65ca-237">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="f65ca-238">Прежде чем приступить к работе, важно понимать правила приоритета и ранжирование назначения групп.</span><span class="sxs-lookup"><span data-stu-id="f65ca-238">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="f65ca-239">Правила приоритета</span><span class="sxs-lookup"><span data-stu-id="f65ca-239">Precedence rules</span></span>

<span data-ttu-id="f65ca-240">Для определенного типа политики действующая политика пользователя определяется в соответствии с приведенными ниже сведениями.</span><span class="sxs-lookup"><span data-stu-id="f65ca-240">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="f65ca-241">Политика, непосредственно назначенная пользователю, имеет приоритет над любыми другими политиками того же типа, которые назначены группе.</span><span class="sxs-lookup"><span data-stu-id="f65ca-241">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="f65ca-242">Другими словами, если пользователю явно назначена политика определенного типа, этот пользователь не наследует политику того же типа из группы.</span><span class="sxs-lookup"><span data-stu-id="f65ca-242">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="f65ca-243">Это также означает, что если пользователь имеет политику, назначенную определенному типу, вы должны удалить ее от пользователя, прежде чем она сможет наследовать политику того же типа из группы.</span><span class="sxs-lookup"><span data-stu-id="f65ca-243">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="f65ca-244">Если пользователь не имеет назначенной им политики и является членом двух или более групп, а каждая группа имеет политику с таким же типом, пользователь наследует политику назначения группы, имеющую наивысший рейтинг.</span><span class="sxs-lookup"><span data-stu-id="f65ca-244">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="f65ca-245">Если пользователь не является членом ни одной из групп, которым назначена политика, для него применяется Глобальная политика (по умолчанию на уровне Организации) для этого типа политики.</span><span class="sxs-lookup"><span data-stu-id="f65ca-245">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="f65ca-246">Действующая политика пользователя обновляется согласно этим правилам, когда пользователь добавляется или удаляется из группы, которой назначена политика, политика не назначается группе, или политика, непосредственно назначенная пользователю, удаляется.</span><span class="sxs-lookup"><span data-stu-id="f65ca-246">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="f65ca-247">Ранжирование назначения групп</span><span class="sxs-lookup"><span data-stu-id="f65ca-247">Group assignment ranking</span></span>
 
<span data-ttu-id="f65ca-248">Когда вы назначаете группе политику, вы указываете рейтинг для назначения группы.</span><span class="sxs-lookup"><span data-stu-id="f65ca-248">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="f65ca-249">Этот параметр используется для определения политики, которую пользователь должен наследовать в качестве действующей политики, если пользователь является членом двух или более групп, и каждой группе назначена политика одного и того же типа.</span><span class="sxs-lookup"><span data-stu-id="f65ca-249">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="f65ca-250">Ранжирование назначения групп определяется относительно других назначений групп того же типа.</span><span class="sxs-lookup"><span data-stu-id="f65ca-250">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="f65ca-251">Например, если вы назначаете политику вызовов двум группам, задайте для ранжирования одного задания значение 1, а для другого — 2, где 1 — наивысший рейтинг.</span><span class="sxs-lookup"><span data-stu-id="f65ca-251">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="f65ca-252">Ранжирование назначения групп указывает на то, что участие в группах является более важным или более релевантным по сравнению с наследованием в других группах.</span><span class="sxs-lookup"><span data-stu-id="f65ca-252">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="f65ca-253">Например, предположим, что у вас есть две группы, магазин сотрудников и руководителей магазина.</span><span class="sxs-lookup"><span data-stu-id="f65ca-253">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="f65ca-254">Обеим группам назначается политика вызова Teams, в котором хранятся политики вызова для сотрудников и политики звонков руководителей магазина соответственно.</span><span class="sxs-lookup"><span data-stu-id="f65ca-254">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="f65ca-255">Для руководителя магазина, который находится в обеих группах, роль руководителя больше важна, чем роль сотрудника, поэтому политика звонков, назначенная группе руководителей магазина, должна иметь более высокий рейтинг.</span><span class="sxs-lookup"><span data-stu-id="f65ca-255">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="f65ca-256">Сгруппирован</span><span class="sxs-lookup"><span data-stu-id="f65ca-256">Group</span></span> |<span data-ttu-id="f65ca-257">Имя политики вызова Teams</span><span class="sxs-lookup"><span data-stu-id="f65ca-257">Teams calling policy name</span></span>  |<span data-ttu-id="f65ca-258">Rank (Ранг)</span><span class="sxs-lookup"><span data-stu-id="f65ca-258">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="f65ca-259">Руководители магазина</span><span class="sxs-lookup"><span data-stu-id="f65ca-259">Store Managers</span></span>   |<span data-ttu-id="f65ca-260">Политика звонков руководителей магазина</span><span class="sxs-lookup"><span data-stu-id="f65ca-260">Store Managers Calling Policy</span></span>         |<span data-ttu-id="f65ca-261">1</span><span class="sxs-lookup"><span data-stu-id="f65ca-261">1</span></span>|
|<span data-ttu-id="f65ca-262">Магазин сотрудников</span><span class="sxs-lookup"><span data-stu-id="f65ca-262">Store Employees</span></span>    |<span data-ttu-id="f65ca-263">Хранение политики звонка для сотрудников</span><span class="sxs-lookup"><span data-stu-id="f65ca-263">Store Employees Calling Policy</span></span>      |<span data-ttu-id="f65ca-264">2</span><span class="sxs-lookup"><span data-stu-id="f65ca-264">2</span></span>|

<span data-ttu-id="f65ca-265">Если вы не укажете ранжирование, для назначения политики будет задан самый низкий рейтинг.</span><span class="sxs-lookup"><span data-stu-id="f65ca-265">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="f65ca-266">Установка и подключение к модулю Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="f65ca-266">Install and connect to the Microsoft Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="f65ca-267">Командлеты находятся в предварительной версии модуля PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="f65ca-267">The cmdlets are in the pre-release version of the Teams PowerShell module.</span></span> <span data-ttu-id="f65ca-268">Выполните эти действия, чтобы сначала удалить общедоступную версию модуля Teams PowerShell (если он установлен), а затем установите самую последнюю версию модуля из коллекции тестов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f65ca-268">Follow these steps to first uninstall the Generally Available version of the Teams PowerShell module (if it's installed), and then install the latest pre-release version of the module from the PowerShell Test Gallery.</span></span>

<span data-ttu-id="f65ca-269">Если вы еще не сделали этого, выполните указанные ниже действия, чтобы зарегистрировать коллекцию тестов PowerShell в качестве надежного источника.</span><span class="sxs-lookup"><span data-stu-id="f65ca-269">If you haven't already, run the following to register the PowerShell Test Gallery as a trusted source.</span></span>

```powershell
Register-PSRepository -SourceLocation https://www.poshtestgallery.com/api/v2 -Name PsTestGallery -InstallationPolicy Trusted
```

<span data-ttu-id="f65ca-270">Если вы установили общедоступную версию модуля Teams PowerShell, выполните указанные ниже действия, чтобы удалить его.</span><span class="sxs-lookup"><span data-stu-id="f65ca-270">If you have the Generally Available version of the Teams PowerShell module installed, run the following to uninstall it.</span></span>

```powershell
Uninstall-Module MicrosoftTeams -AllVersions
```

<span data-ttu-id="f65ca-271">Выполните указанные ниже действия, чтобы установить последнюю версию модуля PowerShell для Microsoft Teams из коллекции тестов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f65ca-271">Run the following to install the latest Microsoft Teams PowerShell module from the PowerShell Test Gallery.</span></span>

```powershell
Install-Module MicrosoftTeams -Repository PSTestGallery
```

<span data-ttu-id="f65ca-272">Выполните указанные ниже действия, чтобы подключиться к Teams и начать сеанс.</span><span class="sxs-lookup"><span data-stu-id="f65ca-272">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="f65ca-273">Когда вам будет предложено, войдите в систему с помощью учетных данных администратора.</span><span class="sxs-lookup"><span data-stu-id="f65ca-273">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="f65ca-274">Назначение политики группе</span><span class="sxs-lookup"><span data-stu-id="f65ca-274">Assign a policy to a group</span></span>

<span data-ttu-id="f65ca-275">В этом примере мы используем ```New-CsGroupPolicyAssignment``` командлет для назначения политики собрания Team Manager в группе с рейтингом назначения 1.</span><span class="sxs-lookup"><span data-stu-id="f65ca-275">In this example, we use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

<span data-ttu-id="f65ca-276">Дополнительные сведения можно найти в статье [Создание и CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="f65ca-276">To learn more, see [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span></span>

### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="f65ca-277">Получение назначений политики для группы</span><span class="sxs-lookup"><span data-stu-id="f65ca-277">Get policy assignments for a group</span></span>

<span data-ttu-id="f65ca-278">Используйте ```Get-CsGroupPolicyAssignment``` командлет, чтобы получить все политики, назначенные группе.</span><span class="sxs-lookup"><span data-stu-id="f65ca-278">Use the ```Get-CsGroupPolicyAssignment``` cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="f65ca-279">Обратите внимание, что группы всегда записываются в соответствии с их идентификатором группы, даже если для назначения политики был использован адрес SIP или адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f65ca-279">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="f65ca-280">В этом примере мы извлекаем все политики, назначенные определенной группе.</span><span class="sxs-lookup"><span data-stu-id="f65ca-280">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="f65ca-281">В этом примере мы возвращаем все группы, которым назначена политика для собрания Teams.</span><span class="sxs-lookup"><span data-stu-id="f65ca-281">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

<span data-ttu-id="f65ca-282">Дополнительные сведения можно найти в [статьях Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="f65ca-282">To learn more, see [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span></span>

### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="f65ca-283">Удаление политики из группы</span><span class="sxs-lookup"><span data-stu-id="f65ca-283">Remove a policy from a group</span></span>

<span data-ttu-id="f65ca-284">Используйте ```Remove-CsGroupPolicyAssignment``` командлет для удаления политики из группы.</span><span class="sxs-lookup"><span data-stu-id="f65ca-284">Use the ```Remove-CsGroupPolicyAssignment``` cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="f65ca-285">При удалении политики из группы приоритеты других политик того же типа, которым назначена эта группа, и которые имеют более низкий рейтинг, будут обновлены.</span><span class="sxs-lookup"><span data-stu-id="f65ca-285">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="f65ca-286">Например, если вы удалите политику с рангом 2, то политики с рейтингом 3 и 4 будут обновляться в соответствии с их новым рейтингом.</span><span class="sxs-lookup"><span data-stu-id="f65ca-286">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="f65ca-287">Этот пример показан в двух приведенных ниже таблицах.</span><span class="sxs-lookup"><span data-stu-id="f65ca-287">The following two tables show this example.</span></span>

<span data-ttu-id="f65ca-288">Ниже приведен список назначений и приоритетов политики для собраний Teams.</span><span class="sxs-lookup"><span data-stu-id="f65ca-288">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="f65ca-289">Имя группы</span><span class="sxs-lookup"><span data-stu-id="f65ca-289">Group name</span></span>  |<span data-ttu-id="f65ca-290">Название политики</span><span class="sxs-lookup"><span data-stu-id="f65ca-290">Policy name</span></span>  |<span data-ttu-id="f65ca-291">Rank (Ранг)</span><span class="sxs-lookup"><span data-stu-id="f65ca-291">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="f65ca-292">Продажи</span><span class="sxs-lookup"><span data-stu-id="f65ca-292">Sales</span></span>    |<span data-ttu-id="f65ca-293">Политика продаж</span><span class="sxs-lookup"><span data-stu-id="f65ca-293">Sales policy</span></span>       | <span data-ttu-id="f65ca-294">1</span><span class="sxs-lookup"><span data-stu-id="f65ca-294">1</span></span>        |
|<span data-ttu-id="f65ca-295">Западная область</span><span class="sxs-lookup"><span data-stu-id="f65ca-295">West Region</span></span>     |<span data-ttu-id="f65ca-296">Политика "Западная область"</span><span class="sxs-lookup"><span data-stu-id="f65ca-296">West Region policy</span></span>         |<span data-ttu-id="f65ca-297">2</span><span class="sxs-lookup"><span data-stu-id="f65ca-297">2</span></span>         |
|<span data-ttu-id="f65ca-298">Умножен</span><span class="sxs-lookup"><span data-stu-id="f65ca-298">Division</span></span>    |<span data-ttu-id="f65ca-299">Политика деления</span><span class="sxs-lookup"><span data-stu-id="f65ca-299">Division policy</span></span>         |<span data-ttu-id="f65ca-300">3</span><span class="sxs-lookup"><span data-stu-id="f65ca-300">3</span></span>         |
|<span data-ttu-id="f65ca-301">Отделения</span><span class="sxs-lookup"><span data-stu-id="f65ca-301">Subsidiary</span></span>   |<span data-ttu-id="f65ca-302">Политика для дочерних компаний</span><span class="sxs-lookup"><span data-stu-id="f65ca-302">Subsidiary policy</span></span>        |<span data-ttu-id="f65ca-303">4</span><span class="sxs-lookup"><span data-stu-id="f65ca-303">4</span></span>         |

<span data-ttu-id="f65ca-304">Если удалить политику западных областей из группы Западная область, то назначения и приоритеты политики будут обновляться следующим образом.</span><span class="sxs-lookup"><span data-stu-id="f65ca-304">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="f65ca-305">Имя группы</span><span class="sxs-lookup"><span data-stu-id="f65ca-305">Group name</span></span>  |<span data-ttu-id="f65ca-306">Название политики</span><span class="sxs-lookup"><span data-stu-id="f65ca-306">Policy name</span></span>  |<span data-ttu-id="f65ca-307">Rank (Ранг)</span><span class="sxs-lookup"><span data-stu-id="f65ca-307">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="f65ca-308">Продажи</span><span class="sxs-lookup"><span data-stu-id="f65ca-308">Sales</span></span>    |<span data-ttu-id="f65ca-309">Политика продаж</span><span class="sxs-lookup"><span data-stu-id="f65ca-309">Sales policy</span></span>       | <span data-ttu-id="f65ca-310">1</span><span class="sxs-lookup"><span data-stu-id="f65ca-310">1</span></span>        |
|<span data-ttu-id="f65ca-311">Умножен</span><span class="sxs-lookup"><span data-stu-id="f65ca-311">Division</span></span>    |<span data-ttu-id="f65ca-312">Политика деления</span><span class="sxs-lookup"><span data-stu-id="f65ca-312">Division policy</span></span>         |<span data-ttu-id="f65ca-313">2</span><span class="sxs-lookup"><span data-stu-id="f65ca-313">2</span></span>         |
|<span data-ttu-id="f65ca-314">Отделения</span><span class="sxs-lookup"><span data-stu-id="f65ca-314">Subsidiary</span></span>   |<span data-ttu-id="f65ca-315">Политика для дочерних компаний</span><span class="sxs-lookup"><span data-stu-id="f65ca-315">Subsidiary policy</span></span>        |<span data-ttu-id="f65ca-316">3</span><span class="sxs-lookup"><span data-stu-id="f65ca-316">3</span></span>        |

<span data-ttu-id="f65ca-317">В данном примере политика для собрания Teams удаляется из группы.</span><span class="sxs-lookup"><span data-stu-id="f65ca-317">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

<span data-ttu-id="f65ca-318">Дополнительные сведения можно найти в разделе [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="f65ca-318">To learn more, see [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span></span>

### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="f65ca-319">Изменение назначения политики для группы</span><span class="sxs-lookup"><span data-stu-id="f65ca-319">Change a policy assignment for a group</span></span>

<span data-ttu-id="f65ca-320">После назначения политики группе вы можете использовать ```Set-CsGroupPolicyAssignmentd``` командлет, чтобы изменить назначение политики этой группы следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f65ca-320">After you assign a policy to a group, you can use the ```Set-CsGroupPolicyAssignmentd``` cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="f65ca-321">Изменение ранжирования</span><span class="sxs-lookup"><span data-stu-id="f65ca-321">Change the ranking</span></span>
- <span data-ttu-id="f65ca-322">Изменение политики для определенного типа политики</span><span class="sxs-lookup"><span data-stu-id="f65ca-322">Change the policy of a given policy type</span></span>
- <span data-ttu-id="f65ca-323">Изменение политики для определенного типа политики и ранжирования</span><span class="sxs-lookup"><span data-stu-id="f65ca-323">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="f65ca-324">В этом примере мы изменим политику приостановки вызовов групп для группы на политику с именем SupportCallPark и рейтинг назначения 3.</span><span class="sxs-lookup"><span data-stu-id="f65ca-324">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

<span data-ttu-id="f65ca-325">Дополнительные сведения можно найти в статье [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="f65ca-325">To learn more, see [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span></span>

### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="f65ca-326">Изменение действующей политики для пользователя</span><span class="sxs-lookup"><span data-stu-id="f65ca-326">Change the effective policy for a user</span></span>

<span data-ttu-id="f65ca-327">Ниже приведен пример изменения действующей политики для пользователя, которому непосредственно назначена политика.</span><span class="sxs-lookup"><span data-stu-id="f65ca-327">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="f65ca-328">Сначала мы используем ```Get-CsUserPolicyAssignment``` командлет вместе с ```PolicySource``` параметром, чтобы получить подробные сведения о политиках широковещательного показа собраний Teams, связанных с пользователем.</span><span class="sxs-lookup"><span data-stu-id="f65ca-328">First, we use the ```Get-CsUserPolicyAssignment``` cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> <span data-ttu-id="f65ca-329">Дополнительные сведения можно найти в [статьях Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="f65ca-329">To learn more, see [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="f65ca-330">В выходных данных показано, что пользователю непосредственно назначена политика широковещательного показа собрания Teams, которая имеет приоритет над политикой "события поставщика", назначенной группе, в которую входит пользователь.</span><span class="sxs-lookup"><span data-stu-id="f65ca-330">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="f65ca-331">Теперь мы удаляем политику событий сотрудников от пользователя.</span><span class="sxs-lookup"><span data-stu-id="f65ca-331">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="f65ca-332">Это означает, что пользователь больше не имеет политики широковещательного показа собраний Teams, которой они назначены, и будет наследовать политику Live Events поставщика, назначенную группе, которой принадлежит пользователь.</span><span class="sxs-lookup"><span data-stu-id="f65ca-332">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="f65ca-333">Для этого используйте следующий командлет в модуле Skype для бизнеса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f65ca-333">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="f65ca-334">Вы можете использовать следующий командлет в модуле Teams PowerShell для выполнения этой задачи при масштабировании при использовании задания пакетной политики, где $users — это список пользователей, которые вы указали.</span><span class="sxs-lookup"><span data-stu-id="f65ca-334">You can use following cmdlet in the Teams Powershell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="f65ca-335">Назначение пакета политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="f65ca-335">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="f65ca-336">С помощью задания пакетной политики можно назначить пакету политики большим наборам пользователей за один раз без использования сценария.</span><span class="sxs-lookup"><span data-stu-id="f65ca-336">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="f65ca-337">```New-CsBatchPolicyPackageAssignmentOperation```С помощью командлета вы можете отправить пакет пользователей и пакет политики, который вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="f65ca-337">You use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="f65ca-338">Назначения обрабатываются как фоновая операция, и для каждого пакета создается идентификатор операции.</span><span class="sxs-lookup"><span data-stu-id="f65ca-338">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="f65ca-339">Затем вы можете использовать этот ```Get-CsBatchPolicyAssignmentOperation``` командлет для отслеживания хода выполнения и состояния заданий в пакете.</span><span class="sxs-lookup"><span data-stu-id="f65ca-339">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="f65ca-340">Пакет может содержать до 20 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="f65ca-340">A batch can contain up to 20,000 users.</span></span> <span data-ttu-id="f65ca-341">Вы можете указать пользователей, указав их идентификатор (UPN), адрес SIP или адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f65ca-341">You can specify users by their object Id, UPN, SIP address, or email address.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f65ca-342">В настоящее время мы рекомендуем назначать пакеты политик в пакетах пользователей 5 000 за один раз.</span><span class="sxs-lookup"><span data-stu-id="f65ca-342">We're currently recommending that you assign policy packages in batches of 5,000 users at a time.</span></span> <span data-ttu-id="f65ca-343">В это время вы можете столкнуться с задержкой во время обработки.</span><span class="sxs-lookup"><span data-stu-id="f65ca-343">During these times of increased demand, you may experience delays in processing times.</span></span> <span data-ttu-id="f65ca-344">Чтобы свести к минимуму влияние этих увеличенных времен обработки, мы рекомендуем вам отправлять меньшие размеры пакета до 5 000 пользователей и отправлять каждый пакет только после того, как вы закончите предыдущий.</span><span class="sxs-lookup"><span data-stu-id="f65ca-344">To minimize the impact of these increased processing times, we suggest that you submit smaller batch sizes of up to 5,000 users, and submit each batch only after the previous one is completed.</span></span> <span data-ttu-id="f65ca-345">Вы также можете отправлять пакеты за пределы обычных рабочих часов.</span><span class="sxs-lookup"><span data-stu-id="f65ca-345">Submitting batches outside your regular business hours can also help.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="f65ca-346">Установка и подключение к модулю Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="f65ca-346">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="f65ca-347">Выполните указанные ниже действия, чтобы установить [модуль Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (если вы еще этого не сделали).</span><span class="sxs-lookup"><span data-stu-id="f65ca-347">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="f65ca-348">Убедитесь, что вы установили версию 1.0.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="f65ca-348">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="f65ca-349">Выполните указанные ниже действия, чтобы подключиться к Teams и начать сеанс.</span><span class="sxs-lookup"><span data-stu-id="f65ca-349">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="f65ca-350">Когда вам будет предложено, войдите в систему с помощью учетных данных администратора.</span><span class="sxs-lookup"><span data-stu-id="f65ca-350">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="f65ca-351">Назначение пакета политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="f65ca-351">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="f65ca-352">В этом примере мы используем ```New-CsBatchPolicyPackageAssignmentOperation``` командлет для назначения пакета политики Education_PrimaryStudent пакету пользователей.</span><span class="sxs-lookup"><span data-stu-id="f65ca-352">In this example, we use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

<span data-ttu-id="f65ca-353">Дополнительные сведения можно найти в статье [Создание и CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="f65ca-353">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="f65ca-354">Получение статуса задания пакетной обработки</span><span class="sxs-lookup"><span data-stu-id="f65ca-354">Get the status of a batch assignment</span></span>

<span data-ttu-id="f65ca-355">Выполните указанные ниже действия, чтобы получить сведения о состоянии задания пакета, где идентификатор операции — это значение, возвращаемое ```New-CsBatchPolicyAssignmentOperation``` командлетом для данного пакета.</span><span class="sxs-lookup"><span data-stu-id="f65ca-355">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="f65ca-356">Если в выходных данных показано, что произошла ошибка, выполните указанные ниже действия, чтобы получить дополнительные сведения об ошибках, которые находятся в ```UserState``` свойстве.</span><span class="sxs-lookup"><span data-stu-id="f65ca-356">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="f65ca-357">Дополнительные сведения можно найти в [статьях Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="f65ca-357">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="f65ca-358">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="f65ca-358">Related topics</span></span>

- [<span data-ttu-id="f65ca-359">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="f65ca-359">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
