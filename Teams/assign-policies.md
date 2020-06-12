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
ms.openlocfilehash: 1c8c6700ced98cad815c0e30a3afe3e40ae85b33
ms.sourcegitcommit: 862ba1d2b3bd4622b1b0baa15096c29c591cc6c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2020
ms.locfileid: "44702734"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="73560-103">Назначение политик вашим пользователям в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="73560-103">Assign policies to your users in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="73560-104">**Одна из функций Microsoft Teams, описанных в этой статье, [Назначение политики для групп](#assign-a-policy-to-a-group), в настоящее время доступна только в частном предварительной версии. Командлеты PowerShell для этой функции находятся в предварительной версии модуля PowerShell для Teams.**</span><span class="sxs-lookup"><span data-stu-id="73560-104">**One of the Microsoft Teams features discussed in this article, [policy assignment to groups](#assign-a-policy-to-a-group), is currently only available in private preview. The Powershell cmdlets for this feature are in the pre-release Teams PowerShell module.**</span></span> <span data-ttu-id="73560-105">Чтобы не отвлекаться от состояния выпусков этой функции, ознакомьтесь с [планом Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185).</span><span class="sxs-lookup"><span data-stu-id="73560-105">To stay on top of the release status of this feature, check out the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185).</span></span>

<span data-ttu-id="73560-106">Администраторы используют политики для управления возможностями Teams, доступными для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="73560-106">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="73560-107">Например, вы можете присвоить имя только некоторые политики, политики собраний и политики обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="73560-107">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="73560-108">Организации имеют различные типы пользователей с уникальными потребностями, пользовательские политики, созданные и назначаемые, позволяют настраивать параметры политики для разных наборов пользователей на основе этих нужд.</span><span class="sxs-lookup"><span data-stu-id="73560-108">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="73560-109">Для упрощения управления политиками в Организации Teams предлагается несколько способов назначения политик пользователям.</span><span class="sxs-lookup"><span data-stu-id="73560-109">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="73560-110">Политику можно назначить непосредственно пользователям, как по отдельности, так и по масштабу в рамках задания или в группу, в которую входят пользователи.</span><span class="sxs-lookup"><span data-stu-id="73560-110">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="73560-111">Вы также можете использовать пакеты политик, чтобы назначить набор политик для пользователей в Организации, у которых есть похожие роли.</span><span class="sxs-lookup"><span data-stu-id="73560-111">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="73560-112">Выбор параметра зависит от количества политик, которые вы управляете, и количества пользователей, которым вы назначаете.</span><span class="sxs-lookup"><span data-stu-id="73560-112">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span> <span data-ttu-id="73560-113">Настроив глобальные политики (параметры по умолчанию на уровне Организации) таким образом, чтобы они применялись к максимальному количеству пользователей в Организации, вам нужно будет назначать политики только тем пользователям, которым требуются специализированные политики.</span><span class="sxs-lookup"><span data-stu-id="73560-113">By setting the global (Org-wide default) policies so that they apply to the largest number of users in your organization, you only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="73560-114">В этой статье описаны различные способы назначения политик пользователям и рекомендуемые сценарии для того, когда следует использовать эту возможность.</span><span class="sxs-lookup"><span data-stu-id="73560-114">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="73560-115">Какая политика имеет приоритет?</span><span class="sxs-lookup"><span data-stu-id="73560-115">Which policy takes precedence?</span></span>

<span data-ttu-id="73560-116">У пользователя есть одна действующая политика для каждого типа политики.</span><span class="sxs-lookup"><span data-stu-id="73560-116">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="73560-117">Возможно или даже, что пользователю явно назначена политика, и он также является членом одной или нескольких групп, которым назначена политика того же типа.</span><span class="sxs-lookup"><span data-stu-id="73560-117">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="73560-118">В сценариях такого типа приоритет имеет политика.</span><span class="sxs-lookup"><span data-stu-id="73560-118">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="73560-119">Действующая политика пользователя определяется в соответствии с правилами приоритета, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="73560-119">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="73560-120">Если пользователю назначена политика (отдельно или по назначению), она имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="73560-120">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="73560-121">В приведенном ниже примере действующая политика пользователя — это Lincoln квадратная политика для собраний, которая непосредственно назначается пользователю.</span><span class="sxs-lookup"><span data-stu-id="73560-121">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![Схема, показывающая, как имеет приоритет более прямую назначенную политику](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="73560-123">Если пользователь не назначил политике определенного типа, политика, назначенная группе, членом которой является пользователь, имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="73560-123">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="73560-124">Если пользователь является членом нескольких групп, политика, имеющая наивысший [рейтинг назначения группы](#group-assignment-ranking) для данного типа политики, имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="73560-124">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="73560-125">В этом примере действующая политика пользователя — это политика Exec Teams и HD, которая имеет наивысший рейтинг назначения относительно других групп, участником которых является этот пользователь, и которым также назначена политика того же типа политики.</span><span class="sxs-lookup"><span data-stu-id="73560-125">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![Схема, на которой показано, как действует политика, унаследованная от группы](media/assign-policies-example-group.png)

<span data-ttu-id="73560-127">Если пользователь не назначил политику или не является участником ни одной из групп, которым назначена политика, пользователь получает глобальную политику (по умолчанию для всей организации) для этого типа политики.</span><span class="sxs-lookup"><span data-stu-id="73560-127">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="73560-128">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="73560-128">Here's an example.</span></span>

![Схема, показывающая, как Глобальная политика имеет приоритет](media/assign-policies-example-global.png)

<span data-ttu-id="73560-130">Дополнительные сведения можно найти в разделе [правила приоритета](#precedence-rules).</span><span class="sxs-lookup"><span data-stu-id="73560-130">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="73560-131">Способы назначения политик</span><span class="sxs-lookup"><span data-stu-id="73560-131">Ways to assign policies</span></span>

<span data-ttu-id="73560-132">Ниже приведены общие сведения о способах назначения политик пользователям и рекомендуемых сценариях для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="73560-132">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="73560-133">Чтобы получить дополнительные сведения, щелкните ссылки.</span><span class="sxs-lookup"><span data-stu-id="73560-133">Click the links to learn more.</span></span>

<span data-ttu-id="73560-134">Прежде чем назначать политики отдельным пользователям или группам, начните с [настройки глобальных политик (по умолчанию в масштабах организации)](#set-the-global-policies) , чтобы они применялись к максимальному числу пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="73560-134">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="73560-135">После настройки глобальных политик вам потребуется назначать политики только тем пользователям, которым требуются специализированные политики.</span><span class="sxs-lookup"><span data-stu-id="73560-135">Once the global policies are set, you will only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="73560-136">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="73560-136">Do this</span></span>  |<span data-ttu-id="73560-137">Если...</span><span class="sxs-lookup"><span data-stu-id="73560-137">If...</span></span>  | <span data-ttu-id="73560-138">Использование...</span><span class="sxs-lookup"><span data-stu-id="73560-138">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="73560-139">Назначение политики отдельным пользователям</span><span class="sxs-lookup"><span data-stu-id="73560-139">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="73560-140">Вы не знакомы с Teams и просто приступите к работе или вам нужно назначить одну или несколько политик небольшим числам пользователей.</span><span class="sxs-lookup"><span data-stu-id="73560-140">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="73560-141">Центр администрирования Microsoft Teams или командлеты PowerShell в модуле PowerShell Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="73560-141">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
| [<span data-ttu-id="73560-142">Назначение пакета политики</span><span class="sxs-lookup"><span data-stu-id="73560-142">Assign a policy package</span></span>](#assign-a-policy-package)   | <span data-ttu-id="73560-143">Необходимо назначить несколько политик определенным наборам пользователей организации, которые имеют одинаковые или аналогичные роли.</span><span class="sxs-lookup"><span data-stu-id="73560-143">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="73560-144">Например, назначьте в учебном заведении пакет политики образования для преподавателей, чтобы предоставить им полный доступ к беседам, звонку, собраниям и пакету политики образования (дополнительный учебный учащийся), чтобы ограничить некоторые возможности, такие как частный звонок.</span><span class="sxs-lookup"><span data-stu-id="73560-144">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="73560-145">Центр администрирования Microsoft Teams или командлеты PowerShell из модуля Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="73560-145">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="73560-146">Назначение политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="73560-146">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="73560-147">Вы должны назначать политики большим наборам пользователей.</span><span class="sxs-lookup"><span data-stu-id="73560-147">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="73560-148">Например, вы хотите назначить политику для сотен или тысяч пользователей в Организации одновременно.</span><span class="sxs-lookup"><span data-stu-id="73560-148">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="73560-149">Центр администрирования Microsoft Teams или командлеты PowerShell из модуля Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="73560-149">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|<span data-ttu-id="73560-150">[Назначение политики группе](#assign-a-policy-to-a-group) (в предварительной версии)</span><span class="sxs-lookup"><span data-stu-id="73560-150">[Assign a policy to a group](#assign-a-policy-to-a-group) (in preview)</span></span>   |<span data-ttu-id="73560-151">Необходимо назначить политики, основанные на членстве в группе пользователя.</span><span class="sxs-lookup"><span data-stu-id="73560-151">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="73560-152">Например, вы хотите назначить политику для всех пользователей в группе безопасности или подразделении.</span><span class="sxs-lookup"><span data-stu-id="73560-152">For example, you want to assign a policy to all users in a security group or organizational unit.</span></span>| <span data-ttu-id="73560-153">Командлеты PowerShell в модуле PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="73560-153">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="73560-154">Назначение пакета политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="73560-154">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="73560-155">Необходимо назначить несколько политик для пакета пользователей в Организации с одинаковыми или аналогичными ролями.</span><span class="sxs-lookup"><span data-stu-id="73560-155">You need to assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="73560-156">Например, вы можете назначить пакету политики образования для всех преподавателей в учебном заведении с помощью пакетного задания, чтобы предоставить им полный доступ к разговорам, звонкам и собраниям, а также назначить пакету политики образования (дополнительный учебный учащийся) пакету вспомогательных учащихся, чтобы ограничить некоторые возможности, такие как частный звонок.</span><span class="sxs-lookup"><span data-stu-id="73560-156">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings and assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities like private calling.</span></span>|<span data-ttu-id="73560-157">Командлеты PowerShell в модуле PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="73560-157">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="73560-158">Назначение пакета политики группе (ожидается в ближайшее время)</span><span class="sxs-lookup"><span data-stu-id="73560-158">Assign a policy package to a group (coming soon)</span></span>   | ||

## <a name="set-the-global-policies"></a><span data-ttu-id="73560-159">Настройка глобальных политик</span><span class="sxs-lookup"><span data-stu-id="73560-159">Set the global policies</span></span>

<span data-ttu-id="73560-160">Выполните указанные ниже действия, чтобы настроить глобальные политики (параметры по умолчанию для всей организации) для каждого типа политики.</span><span class="sxs-lookup"><span data-stu-id="73560-160">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="73560-161">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="73560-161">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="73560-162">В левой области навигации центра администрирования Microsoft Teams перейдите на страницу политики для типа политики, которую вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="73560-162">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="73560-163">Например, *teams > политики* или *собрания > политики собраний* или политики *обмена сообщениями* или *голосовые >*.</span><span class="sxs-lookup"><span data-stu-id="73560-163">For example, *Teams > Teams policies* or *Meetings > Meetings policies* or *Messaging policies* or *Voice > Calling policies*.</span></span>
2. <span data-ttu-id="73560-164">Выберите **глобальную политику (по умолчанию на уровне Организации)** для просмотра текущих параметров.</span><span class="sxs-lookup"><span data-stu-id="73560-164">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="73560-165">При необходимости обновите политику и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="73560-165">Update the policy as needed, and then select **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="73560-166">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="73560-166">Using PowerShell</span></span>

<span data-ttu-id="73560-167">Чтобы настроить глобальные политики с помощью PowerShell, используйте глобальный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="73560-167">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="73560-168">Сначала просмотрите текущую глобальную политику, чтобы определить, какую настройку нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="73560-168">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

```powershell
Get-CsTeamsMessagingPolicy -Identity Global
 
Identity                      : Global
Description                   :
AllowUrlPreviews              : True
AllowOwnerDeleteMessage       : False
AllowUserEditMessage          : True
AllowUserDeleteMessage        : True
AllowUserChat                 : True
AllowRemoveUser               : True
AllowGiphy                    : True
GiphyRatingType               : Moderate
AllowMemes                    : True
AllowImmersiveReader          : True
AllowStickers                 : True
AllowUserTranslation          : False
ReadReceiptsEnabledType       : UserPreference
AllowPriorityMessages         : True
ChannelsInChatListEnabledType : DisabledUserOverride
AudioMessageEnabledType       : ChatsAndChannels
Expand (20 lines) Collapse 
```

<span data-ttu-id="73560-169">Затем при необходимости обновите глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="73560-169">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="73560-170">Для параметров, которые вы хотите изменить, нужно указать только значения.</span><span class="sxs-lookup"><span data-stu-id="73560-170">You only need to specify values for the settings that you want to change.</span></span> 
 
```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="73560-171">Назначение политики отдельным пользователям</span><span class="sxs-lookup"><span data-stu-id="73560-171">Assign a policy to individual users</span></span>

<span data-ttu-id="73560-172">Выполните указанные ниже действия, чтобы назначить политику для отдельного пользователя или для небольшого количества пользователей за один раз.</span><span class="sxs-lookup"><span data-stu-id="73560-172">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="73560-173">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="73560-173">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="73560-174">Чтобы назначить пользователю политику, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="73560-174">To assign a policy to a user:</span></span>

1. <span data-ttu-id="73560-175">В Центре администрирования Microsoft Teams в области навигации слева перейдите в раздел **Пользователи**, затем щелкните пользователя.</span><span class="sxs-lookup"><span data-stu-id="73560-175">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="73560-176">Выберите пользователя, щелкнув слева от его имени, затем нажмите кнопку **Изменить параметры**.</span><span class="sxs-lookup"><span data-stu-id="73560-176">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="73560-177">Выберите политику, которую вы хотите назначить, и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="73560-177">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="73560-178">Кроме того, вы можете сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="73560-178">Or, you can also do the following:</span></span>

1. <span data-ttu-id="73560-179">В левой области навигации центра администрирования Microsoft Teams перейдите на страницу "политика".</span><span class="sxs-lookup"><span data-stu-id="73560-179">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="73560-180">Выберите политику, которую вы хотите назначить, щелкнув слева от ее имени.</span><span class="sxs-lookup"><span data-stu-id="73560-180">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="73560-181">Выберите **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="73560-181">Select **Manage users**.</span></span>
4. <span data-ttu-id="73560-182">В области **Управление пользователями** выполните поиск по отображаемому имени или по имени пользователя, выберите имя и нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="73560-182">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="73560-183">Повторите это действие для каждого пользователя, которого нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="73560-183">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="73560-184">Завершив добавление пользователей, нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="73560-184">When you're finished adding users, select **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="73560-185">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="73560-185">Using PowerShell</span></span>

<span data-ttu-id="73560-186">У каждого типа политики есть собственный набор командлетов для управления ею.</span><span class="sxs-lookup"><span data-stu-id="73560-186">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="73560-187">Используйте ```Grant-``` командлет для определенного типа политики, чтобы назначить политику.</span><span class="sxs-lookup"><span data-stu-id="73560-187">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="73560-188">Например, ```Grant-CsTeamsMeetingPolicy``` можно использовать командлет для назначения пользователям политики собрания Teams.</span><span class="sxs-lookup"><span data-stu-id="73560-188">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="73560-189">Эти командлеты включены в модуль PowerShell Skype для бизнеса Online и описаны в [справочной документации по командлетам Skype для бизнеса](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="73560-189">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="73560-190">Скачайте и установите [модуль PowerShell Skype для бизнеса Online](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (если вы еще этого не сделали), а затем выполните указанные ниже действия, чтобы подключиться к Skype для бизнеса Online и начать сеанс.</span><span class="sxs-lookup"><span data-stu-id="73560-190">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="73560-191">В этом примере мы назначаем политику собраний Teams, которая называется политикой собраний учащихся, пользователю с именем Reda.</span><span class="sxs-lookup"><span data-stu-id="73560-191">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="73560-192">Дополнительные сведения можно найти в разделе [Управление политиками через PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).</span><span class="sxs-lookup"><span data-stu-id="73560-192">To learn more, see [Managing policies via PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).</span></span>

## <a name="assign-a-policy-package"></a><span data-ttu-id="73560-193">Назначение пакета политики</span><span class="sxs-lookup"><span data-stu-id="73560-193">Assign a policy package</span></span>

<span data-ttu-id="73560-194">Пакет политики в Teams — это набор предопределенных политик и параметров политики, которые можно назначить пользователям, имеющим такие же или аналогичные роли в Организации.</span><span class="sxs-lookup"><span data-stu-id="73560-194">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="73560-195">Каждый пакет политики разработан вокруг роли пользователя и включает стандартные политики и параметры политики, которые поддерживают действия, характерные для этой роли.</span><span class="sxs-lookup"><span data-stu-id="73560-195">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="73560-196">Некоторые примеры пакетов политики — это пакет для образования (преподаватель) и Здравоохранение (Clinical Worker).</span><span class="sxs-lookup"><span data-stu-id="73560-196">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span>

<span data-ttu-id="73560-197">Когда вы назначаете пакету политики пользователям, будут созданы политики в пакете, и вы сможете настраивать параметры каждой из них в пакете в соответствии с потребностями пользователей.</span><span class="sxs-lookup"><span data-stu-id="73560-197">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of each policy in the package to meet users' needs.</span></span>

<span data-ttu-id="73560-198">Дополнительные сведения о пакетах политик, включая пошаговые инструкции по их назначению и управлению, можно найти [в разделе Управление пакетами политики в Teams](manage-policy-packages.md).</span><span class="sxs-lookup"><span data-stu-id="73560-198">To learn more about policy packages, including step-by-step guidance on how to assign and manage them, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="73560-199">Назначение политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="73560-199">Assign a policy to a batch of users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="73560-200">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="73560-200">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="73560-201">Чтобы назначить политику для пользователей, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="73560-201">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="73560-202">В левой области навигации центра администрирования Microsoft Teams выберите пункт **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="73560-202">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="73560-203">Найдите пользователей, которым вы хотите назначить политику, или отфильтруйте представление, чтобы отобразить нужных пользователей.</span><span class="sxs-lookup"><span data-stu-id="73560-203">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="73560-204">В столбце **&#x2713;** (галочка) выберите пользователей.</span><span class="sxs-lookup"><span data-stu-id="73560-204">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="73560-205">Чтобы выбрать всех пользователей, щелкните &#x2713; (галочку) в верхней части таблицы.</span><span class="sxs-lookup"><span data-stu-id="73560-205">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="73560-206">Щелкните **Изменить настройки**, внесите нужные изменения и нажмите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="73560-206">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="73560-207">Чтобы просмотреть состояние назначения политики, в заголовке, который появляется в верхней части страницы **пользователей** после нажатия кнопки **Применить** для отправки назначения политики, щелкните **Журнал активности**.</span><span class="sxs-lookup"><span data-stu-id="73560-207">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you click **Apply** to submit your policy assignment, click **Activity log**.</span></span> <span data-ttu-id="73560-208">Либо в левой области навигации центра администрирования Microsoft Teams перейдите на **панель мониторинга**, а затем в разделе **Журнал активности**щелкните **Просмотреть сведения**.</span><span class="sxs-lookup"><span data-stu-id="73560-208">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, click **View details**.</span></span> <span data-ttu-id="73560-209">Журнал активности показывает назначения политики для пакетов более чем из 20 пользователей в центре администрирования Microsoft Teams за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="73560-209">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="73560-210">Дополнительные сведения можно найти [в статье Просмотр назначенных политик в журнале событий](activity-log.md).</span><span class="sxs-lookup"><span data-stu-id="73560-210">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="73560-211">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="73560-211">Using PowerShell</span></span>
 
<span data-ttu-id="73560-212">С помощью назначения пакетной политики вы можете назначить политику большим наборам пользователей за один раз, не прибегая к использованию сценария.</span><span class="sxs-lookup"><span data-stu-id="73560-212">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="73560-213">```New-CsBatchPolicyAssignmentOperation```С помощью командлета вы можете отправить пакет пользователей и политику, которую вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="73560-213">You use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="73560-214">Назначения обрабатываются как фоновая операция, и для каждого пакета создается идентификатор операции.</span><span class="sxs-lookup"><span data-stu-id="73560-214">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="73560-215">Затем вы можете использовать этот ```Get-CsBatchPolicyAssignmentOperation``` командлет для отслеживания хода выполнения и состояния заданий в пакете.</span><span class="sxs-lookup"><span data-stu-id="73560-215">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span> 

<span data-ttu-id="73560-216">Вы можете указать пользователей по идентификатору объекта или по протоколу SIP.</span><span class="sxs-lookup"><span data-stu-id="73560-216">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="73560-217">Обратите внимание, что адрес SIP пользователя часто имеет то же значение, что и имя участника-пользователя (UPN) или адрес электронной почты, но это не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="73560-217">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="73560-218">Если пользователь указан с использованием имени участника-пользователя или почтового сообщения, но его значение отличается от адреса SIP, для пользователя не будет установлено назначение политики.</span><span class="sxs-lookup"><span data-stu-id="73560-218">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="73560-219">Если пакет включает повторяющиеся пользователи, дубликаты удаляются из пакета перед обработкой и состоянием будут предоставляться только для уникальных пользователей, остающихся в пакете.</span><span class="sxs-lookup"><span data-stu-id="73560-219">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="73560-220">Пакет может содержать до 5 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="73560-220">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="73560-221">Для достижения наилучших результатов не отправляйте более нескольких пакетов одновременно.</span><span class="sxs-lookup"><span data-stu-id="73560-221">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="73560-222">Разрешите пакетам завершить обработку перед отправкой пакетов.</span><span class="sxs-lookup"><span data-stu-id="73560-222">Allow batches to complete processing before submitting more batches.</span></span>

> [!NOTE]
> <span data-ttu-id="73560-223">В настоящее время назначение пакетной политики недоступно для всех типов политики Teams.</span><span class="sxs-lookup"><span data-stu-id="73560-223">Currently, batch policy assignment isn't available for all Teams policy types.</span></span> <span data-ttu-id="73560-224">Ознакомьтесь со списком " [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) " для списка поддерживаемых типов политики.</span><span class="sxs-lookup"><span data-stu-id="73560-224">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="73560-225">Установка и подключение к модулю Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="73560-225">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="73560-226">Выполните указанные ниже действия, чтобы установить [модуль PowerShell Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams).</span><span class="sxs-lookup"><span data-stu-id="73560-226">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="73560-227">Убедитесь, что вы установили версию 1.0.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="73560-227">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="73560-228">Выполните указанные ниже действия, чтобы подключиться к Teams и начать сеанс.</span><span class="sxs-lookup"><span data-stu-id="73560-228">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="73560-229">Когда вам будет предложено, войдите в систему с помощью учетных данных администратора.</span><span class="sxs-lookup"><span data-stu-id="73560-229">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="73560-230">Установка и подключение к модулю Azure AD PowerShell для Graph (необязательно)</span><span class="sxs-lookup"><span data-stu-id="73560-230">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="73560-231">Кроме того, вам может потребоваться [загрузить и установить модуль Azure AD PowerShell для Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (если вы еще не сделали этого) и подключиться к Azure AD, чтобы получить список пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="73560-231">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="73560-232">Выполните указанные ниже действия, чтобы подключиться к Azure AD.</span><span class="sxs-lookup"><span data-stu-id="73560-232">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="73560-233">Когда вам будет предложено, войдите в систему с помощью учетных данных администратора, используемых для подключения к Teams.</span><span class="sxs-lookup"><span data-stu-id="73560-233">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="73560-234">Назначение политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="73560-234">Assign a policy to a batch of users</span></span>

<span data-ttu-id="73560-235">В этом примере мы используем командлет, ```New-CsBatchPolicyAssignmentOperation``` чтобы назначить политику настройки приложения с именем "Политика настройки приложения" для пакета пользователей, перечисленных в файле Users_ids. Text.</span><span class="sxs-lookup"><span data-stu-id="73560-235">In this example, we use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="73560-236">В этом примере мы подключаем подключение к Azure AD, чтобы получить доступ к коллекции пользователей, а затем назначить политику сообщений с именем "Новая политика для приема на работу" для пакета пользователей, указанного с помощью их SIP-адресов.</span><span class="sxs-lookup"><span data-stu-id="73560-236">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

<span data-ttu-id="73560-237">Дополнительные сведения можно найти в статье [Создание и CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="73560-237">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="73560-238">Получение статуса задания пакетной обработки</span><span class="sxs-lookup"><span data-stu-id="73560-238">Get the status of a batch assignment</span></span>

<span data-ttu-id="73560-239">Выполните указанные ниже действия, чтобы получить сведения о состоянии задания пакета, где идентификатор операции — это значение, возвращаемое ```New-CsBatchPolicyAssignmentOperation``` командлетом для данного пакета.</span><span class="sxs-lookup"><span data-stu-id="73560-239">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="73560-240">Если в выходных данных показано, что произошла ошибка, выполните указанные ниже действия, чтобы получить дополнительные сведения об ошибках, которые находятся в ```UserState``` свойстве.</span><span class="sxs-lookup"><span data-stu-id="73560-240">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="73560-241">Дополнительные сведения можно найти в [статьях Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="73560-241">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="73560-242">Назначение политики группе</span><span class="sxs-lookup"><span data-stu-id="73560-242">Assign a policy to a group</span></span>

<span data-ttu-id="73560-243">**Назначение политики для групп в настоящее время доступно только в частном предварительной версии. Командлеты для этой функции находятся в предварительной версии модуля PowerShell для Teams.**</span><span class="sxs-lookup"><span data-stu-id="73560-243">**Policy assignment to groups is currently only available in private preview. The cmdlets for this feature are in the pre-release Teams PowerShell module.**</span></span>

<span data-ttu-id="73560-244">Назначение политики для групп позволяет назначить политику группе пользователей, например группе безопасности или подразделению.</span><span class="sxs-lookup"><span data-stu-id="73560-244">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or organizational unit.</span></span> <span data-ttu-id="73560-245">Назначение политики распространяется на пользователей группы в соответствии с правилами приоритета.</span><span class="sxs-lookup"><span data-stu-id="73560-245">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="73560-246">Когда участники добавляются в группу или удаляются из нее, их унаследованные назначения политик обновляются соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="73560-246">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="73560-247">С помощью ```New-CsGroupPolicyAssignment``` командлета вы можете назначить политику группе.</span><span class="sxs-lookup"><span data-stu-id="73560-247">You use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="73560-248">Вы можете указать группу, используя идентификатор объекта, адрес SIP или адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="73560-248">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="73560-249">После назначения политики она немедленно назначается группе.</span><span class="sxs-lookup"><span data-stu-id="73560-249">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="73560-250">Однако обратите внимание, что распространение назначения политики для участников группы выполняется в фоновом режиме и может занять некоторое время, в зависимости от размера группы.</span><span class="sxs-lookup"><span data-stu-id="73560-250">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="73560-251">Это справедливо, если политика не назначена группе, а также при добавлении пользователей в группу или удалении ее из нее.</span><span class="sxs-lookup"><span data-stu-id="73560-251">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!NOTE]
> <span data-ttu-id="73560-252">В настоящее время назначение политики для групп недоступно для всех типов политики Teams.</span><span class="sxs-lookup"><span data-stu-id="73560-252">Currently, policy assignment to groups isn't available for all Teams policy types.</span></span> <span data-ttu-id="73560-253">Ознакомьтесь со списком " [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) " для списка поддерживаемых типов политики.</span><span class="sxs-lookup"><span data-stu-id="73560-253">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="73560-254">Что необходимо знать о назначении политики группам</span><span class="sxs-lookup"><span data-stu-id="73560-254">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="73560-255">Прежде чем приступить к работе, важно понимать правила приоритета и ранжирование назначения групп.</span><span class="sxs-lookup"><span data-stu-id="73560-255">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="73560-256">Правила приоритета</span><span class="sxs-lookup"><span data-stu-id="73560-256">Precedence rules</span></span>

<span data-ttu-id="73560-257">Для определенного типа политики действующая политика пользователя определяется в соответствии с приведенными ниже сведениями.</span><span class="sxs-lookup"><span data-stu-id="73560-257">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="73560-258">Политика, непосредственно назначенная пользователю, имеет приоритет над любыми другими политиками того же типа, которые назначены группе.</span><span class="sxs-lookup"><span data-stu-id="73560-258">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="73560-259">Другими словами, если пользователю явно назначена политика определенного типа, этот пользователь не наследует политику того же типа из группы.</span><span class="sxs-lookup"><span data-stu-id="73560-259">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="73560-260">Это также означает, что если пользователь имеет политику, назначенную определенному типу, вы должны удалить ее от пользователя, прежде чем она сможет наследовать политику того же типа из группы.</span><span class="sxs-lookup"><span data-stu-id="73560-260">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="73560-261">Если пользователь не имеет назначенной им политики и является членом двух или более групп, а каждая группа имеет политику с таким же типом, пользователь наследует политику назначения группы, имеющую наивысший рейтинг.</span><span class="sxs-lookup"><span data-stu-id="73560-261">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="73560-262">Если пользователь не является членом ни одной из групп, которым назначена политика, для него применяется Глобальная политика (по умолчанию на уровне Организации) для этого типа политики.</span><span class="sxs-lookup"><span data-stu-id="73560-262">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="73560-263">Действующая политика пользователя обновляется согласно этим правилам, когда пользователь добавляется или удаляется из группы, которой назначена политика, политика не назначается группе, или политика, непосредственно назначенная пользователю, удаляется.</span><span class="sxs-lookup"><span data-stu-id="73560-263">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="73560-264">Ранжирование назначения групп</span><span class="sxs-lookup"><span data-stu-id="73560-264">Group assignment ranking</span></span>
 
<span data-ttu-id="73560-265">Когда вы назначаете группе политику, вы указываете рейтинг для назначения группы.</span><span class="sxs-lookup"><span data-stu-id="73560-265">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="73560-266">Этот параметр используется для определения политики, которую пользователь должен наследовать в качестве действующей политики, если пользователь является членом двух или более групп, и каждой группе назначена политика одного и того же типа.</span><span class="sxs-lookup"><span data-stu-id="73560-266">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="73560-267">Ранжирование назначения групп определяется относительно других назначений групп того же типа.</span><span class="sxs-lookup"><span data-stu-id="73560-267">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="73560-268">Например, если вы назначаете политику вызовов двум группам, задайте для ранжирования одного задания значение 1, а для другого — 2, где 1 — наивысший рейтинг.</span><span class="sxs-lookup"><span data-stu-id="73560-268">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="73560-269">Ранжирование назначения групп указывает на то, что участие в группах является более важным или более релевантным по сравнению с наследованием в других группах.</span><span class="sxs-lookup"><span data-stu-id="73560-269">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="73560-270">Например, предположим, что у вас есть две группы, магазин сотрудников и руководителей магазина.</span><span class="sxs-lookup"><span data-stu-id="73560-270">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="73560-271">Обеим группам назначается политика вызова Teams, в котором хранятся политики вызова для сотрудников и политики звонков руководителей магазина соответственно.</span><span class="sxs-lookup"><span data-stu-id="73560-271">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="73560-272">Для руководителя магазина, который находится в обеих группах, роль руководителя больше важна, чем роль сотрудника, поэтому политика звонков, назначенная группе руководителей магазина, должна иметь более высокий рейтинг.</span><span class="sxs-lookup"><span data-stu-id="73560-272">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="73560-273">Сгруппирован</span><span class="sxs-lookup"><span data-stu-id="73560-273">Group</span></span> |<span data-ttu-id="73560-274">Имя политики вызова Teams</span><span class="sxs-lookup"><span data-stu-id="73560-274">Teams calling policy name</span></span>  |<span data-ttu-id="73560-275">Rank (Ранг)</span><span class="sxs-lookup"><span data-stu-id="73560-275">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="73560-276">Руководители магазина</span><span class="sxs-lookup"><span data-stu-id="73560-276">Store Managers</span></span>   |<span data-ttu-id="73560-277">Политика звонков руководителей магазина</span><span class="sxs-lookup"><span data-stu-id="73560-277">Store Managers Calling Policy</span></span>         |<span data-ttu-id="73560-278">1</span><span class="sxs-lookup"><span data-stu-id="73560-278">1</span></span>|
|<span data-ttu-id="73560-279">Магазин сотрудников</span><span class="sxs-lookup"><span data-stu-id="73560-279">Store Employees</span></span>    |<span data-ttu-id="73560-280">Хранение политики звонка для сотрудников</span><span class="sxs-lookup"><span data-stu-id="73560-280">Store Employees Calling Policy</span></span>      |<span data-ttu-id="73560-281">2</span><span class="sxs-lookup"><span data-stu-id="73560-281">2</span></span>|

<span data-ttu-id="73560-282">Если вы не укажете ранжирование, для назначения политики будет задан самый низкий рейтинг.</span><span class="sxs-lookup"><span data-stu-id="73560-282">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="73560-283">Установка и подключение к модулю Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="73560-283">Install and connect to the Microsoft Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="73560-284">Командлеты находятся в предварительной версии модуля PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="73560-284">The cmdlets are in the pre-release version of the Teams PowerShell module.</span></span> <span data-ttu-id="73560-285">Выполните эти действия, чтобы сначала удалить общедоступную версию модуля Teams PowerShell (если он установлен), а затем установите самую последнюю версию модуля из коллекции тестов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="73560-285">Follow these steps to first uninstall the Generally Available version of the Teams PowerShell module (if it's installed), and then install the latest pre-release version of the module from the PowerShell Test Gallery.</span></span>

<span data-ttu-id="73560-286">Если вы еще не сделали этого, выполните указанные ниже действия, чтобы зарегистрировать коллекцию тестов PowerShell в качестве надежного источника.</span><span class="sxs-lookup"><span data-stu-id="73560-286">If you haven't already, run the following to register the PowerShell Test Gallery as a trusted source.</span></span>

```powershell
Register-PSRepository -SourceLocation https://www.poshtestgallery.com/api/v2 -Name PsTestGallery -InstallationPolicy Trusted
```

<span data-ttu-id="73560-287">Если вы установили общедоступную версию модуля Teams PowerShell, выполните указанные ниже действия, чтобы удалить его.</span><span class="sxs-lookup"><span data-stu-id="73560-287">If you have the Generally Available version of the Teams PowerShell module installed, run the following to uninstall it.</span></span>

```powershell
Uninstall-Module MicrosoftTeams -AllVersions
```

<span data-ttu-id="73560-288">Выполните указанные ниже действия, чтобы установить последнюю версию модуля PowerShell для Microsoft Teams из коллекции тестов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="73560-288">Run the following to install the latest Microsoft Teams PowerShell module from the PowerShell Test Gallery.</span></span>

```powershell
Install-Module MicrosoftTeams -Repository PSTestGallery
```

<span data-ttu-id="73560-289">Выполните указанные ниже действия, чтобы подключиться к Teams и начать сеанс.</span><span class="sxs-lookup"><span data-stu-id="73560-289">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="73560-290">Когда вам будет предложено, войдите в систему с помощью учетных данных администратора.</span><span class="sxs-lookup"><span data-stu-id="73560-290">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="73560-291">Назначение политики группе</span><span class="sxs-lookup"><span data-stu-id="73560-291">Assign a policy to a group</span></span>

<span data-ttu-id="73560-292">В этом примере мы используем ```New-CsGroupPolicyAssignment``` командлет для назначения политики собрания Team Manager в группе с рейтингом назначения 1.</span><span class="sxs-lookup"><span data-stu-id="73560-292">In this example, we use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

<span data-ttu-id="73560-293">Дополнительные сведения можно найти в статье [Создание и CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="73560-293">To learn more, see [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span></span>

### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="73560-294">Получение назначений политики для группы</span><span class="sxs-lookup"><span data-stu-id="73560-294">Get policy assignments for a group</span></span>

<span data-ttu-id="73560-295">Используйте ```Get-CsGroupPolicyAssignment``` командлет, чтобы получить все политики, назначенные группе.</span><span class="sxs-lookup"><span data-stu-id="73560-295">Use the ```Get-CsGroupPolicyAssignment``` cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="73560-296">Обратите внимание, что группы всегда записываются в соответствии с их идентификатором группы, даже если для назначения политики был использован адрес SIP или адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="73560-296">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="73560-297">В этом примере мы извлекаем все политики, назначенные определенной группе.</span><span class="sxs-lookup"><span data-stu-id="73560-297">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="73560-298">В этом примере мы возвращаем все группы, которым назначена политика для собрания Teams.</span><span class="sxs-lookup"><span data-stu-id="73560-298">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

<span data-ttu-id="73560-299">Дополнительные сведения можно найти в [статьях Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="73560-299">To learn more, see [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span></span>

### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="73560-300">Удаление политики из группы</span><span class="sxs-lookup"><span data-stu-id="73560-300">Remove a policy from a group</span></span>

<span data-ttu-id="73560-301">Используйте ```Remove-CsGroupPolicyAssignment``` командлет для удаления политики из группы.</span><span class="sxs-lookup"><span data-stu-id="73560-301">Use the ```Remove-CsGroupPolicyAssignment``` cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="73560-302">При удалении политики из группы приоритеты других политик того же типа, которым назначена эта группа, и которые имеют более низкий рейтинг, будут обновлены.</span><span class="sxs-lookup"><span data-stu-id="73560-302">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="73560-303">Например, если вы удалите политику с рангом 2, то политики с рейтингом 3 и 4 будут обновляться в соответствии с их новым рейтингом.</span><span class="sxs-lookup"><span data-stu-id="73560-303">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="73560-304">Этот пример показан в двух приведенных ниже таблицах.</span><span class="sxs-lookup"><span data-stu-id="73560-304">The following two tables show this example.</span></span>

<span data-ttu-id="73560-305">Ниже приведен список назначений и приоритетов политики для собраний Teams.</span><span class="sxs-lookup"><span data-stu-id="73560-305">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="73560-306">Имя группы</span><span class="sxs-lookup"><span data-stu-id="73560-306">Group name</span></span>  |<span data-ttu-id="73560-307">Название политики</span><span class="sxs-lookup"><span data-stu-id="73560-307">Policy name</span></span>  |<span data-ttu-id="73560-308">Rank (Ранг)</span><span class="sxs-lookup"><span data-stu-id="73560-308">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="73560-309">Продажи</span><span class="sxs-lookup"><span data-stu-id="73560-309">Sales</span></span>    |<span data-ttu-id="73560-310">Политика продаж</span><span class="sxs-lookup"><span data-stu-id="73560-310">Sales policy</span></span>       | <span data-ttu-id="73560-311">1</span><span class="sxs-lookup"><span data-stu-id="73560-311">1</span></span>        |
|<span data-ttu-id="73560-312">Западная область</span><span class="sxs-lookup"><span data-stu-id="73560-312">West Region</span></span>     |<span data-ttu-id="73560-313">Политика "Западная область"</span><span class="sxs-lookup"><span data-stu-id="73560-313">West Region policy</span></span>         |<span data-ttu-id="73560-314">2</span><span class="sxs-lookup"><span data-stu-id="73560-314">2</span></span>         |
|<span data-ttu-id="73560-315">Умножен</span><span class="sxs-lookup"><span data-stu-id="73560-315">Division</span></span>    |<span data-ttu-id="73560-316">Политика деления</span><span class="sxs-lookup"><span data-stu-id="73560-316">Division policy</span></span>         |<span data-ttu-id="73560-317">3</span><span class="sxs-lookup"><span data-stu-id="73560-317">3</span></span>         |
|<span data-ttu-id="73560-318">Отделения</span><span class="sxs-lookup"><span data-stu-id="73560-318">Subsidiary</span></span>   |<span data-ttu-id="73560-319">Политика для дочерних компаний</span><span class="sxs-lookup"><span data-stu-id="73560-319">Subsidiary policy</span></span>        |<span data-ttu-id="73560-320">4</span><span class="sxs-lookup"><span data-stu-id="73560-320">4</span></span>         |

<span data-ttu-id="73560-321">Если удалить политику западных областей из группы Западная область, то назначения и приоритеты политики будут обновляться следующим образом.</span><span class="sxs-lookup"><span data-stu-id="73560-321">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="73560-322">Имя группы</span><span class="sxs-lookup"><span data-stu-id="73560-322">Group name</span></span>  |<span data-ttu-id="73560-323">Название политики</span><span class="sxs-lookup"><span data-stu-id="73560-323">Policy name</span></span>  |<span data-ttu-id="73560-324">Rank (Ранг)</span><span class="sxs-lookup"><span data-stu-id="73560-324">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="73560-325">Продажи</span><span class="sxs-lookup"><span data-stu-id="73560-325">Sales</span></span>    |<span data-ttu-id="73560-326">Политика продаж</span><span class="sxs-lookup"><span data-stu-id="73560-326">Sales policy</span></span>       | <span data-ttu-id="73560-327">1</span><span class="sxs-lookup"><span data-stu-id="73560-327">1</span></span>        |
|<span data-ttu-id="73560-328">Умножен</span><span class="sxs-lookup"><span data-stu-id="73560-328">Division</span></span>    |<span data-ttu-id="73560-329">Политика деления</span><span class="sxs-lookup"><span data-stu-id="73560-329">Division policy</span></span>         |<span data-ttu-id="73560-330">2</span><span class="sxs-lookup"><span data-stu-id="73560-330">2</span></span>         |
|<span data-ttu-id="73560-331">Отделения</span><span class="sxs-lookup"><span data-stu-id="73560-331">Subsidiary</span></span>   |<span data-ttu-id="73560-332">Политика для дочерних компаний</span><span class="sxs-lookup"><span data-stu-id="73560-332">Subsidiary policy</span></span>        |<span data-ttu-id="73560-333">3</span><span class="sxs-lookup"><span data-stu-id="73560-333">3</span></span>        |

<span data-ttu-id="73560-334">В данном примере политика для собрания Teams удаляется из группы.</span><span class="sxs-lookup"><span data-stu-id="73560-334">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

<span data-ttu-id="73560-335">Дополнительные сведения можно найти в разделе [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="73560-335">To learn more, see [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span></span>

### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="73560-336">Изменение назначения политики для группы</span><span class="sxs-lookup"><span data-stu-id="73560-336">Change a policy assignment for a group</span></span>

<span data-ttu-id="73560-337">После назначения политики группе вы можете использовать ```Set-CsGroupPolicyAssignmentd``` командлет, чтобы изменить назначение политики этой группы следующим образом:</span><span class="sxs-lookup"><span data-stu-id="73560-337">After you assign a policy to a group, you can use the ```Set-CsGroupPolicyAssignmentd``` cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="73560-338">Изменение ранжирования</span><span class="sxs-lookup"><span data-stu-id="73560-338">Change the ranking</span></span>
- <span data-ttu-id="73560-339">Изменение политики для определенного типа политики</span><span class="sxs-lookup"><span data-stu-id="73560-339">Change the policy of a given policy type</span></span>
- <span data-ttu-id="73560-340">Изменение политики для определенного типа политики и ранжирования</span><span class="sxs-lookup"><span data-stu-id="73560-340">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="73560-341">В этом примере мы изменим политику приостановки вызовов групп для группы на политику с именем SupportCallPark и рейтинг назначения 3.</span><span class="sxs-lookup"><span data-stu-id="73560-341">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

<span data-ttu-id="73560-342">Дополнительные сведения можно найти в статье [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="73560-342">To learn more, see [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span></span>

### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="73560-343">Изменение действующей политики для пользователя</span><span class="sxs-lookup"><span data-stu-id="73560-343">Change the effective policy for a user</span></span>

<span data-ttu-id="73560-344">Ниже приведен пример изменения действующей политики для пользователя, которому непосредственно назначена политика.</span><span class="sxs-lookup"><span data-stu-id="73560-344">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="73560-345">Сначала мы используем ```Get-CsUserPolicyAssignment``` командлет вместе с ```PolicySource``` параметром, чтобы получить подробные сведения о политиках широковещательного показа собраний Teams, связанных с пользователем.</span><span class="sxs-lookup"><span data-stu-id="73560-345">First, we use the ```Get-CsUserPolicyAssignment``` cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> <span data-ttu-id="73560-346">Дополнительные сведения можно найти в [статьях Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="73560-346">To learn more, see [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="73560-347">В выходных данных показано, что пользователю непосредственно назначена политика широковещательного показа собрания Teams, которая имеет приоритет над политикой "события поставщика", назначенной группе, в которую входит пользователь.</span><span class="sxs-lookup"><span data-stu-id="73560-347">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="73560-348">Теперь мы удаляем политику событий сотрудников от пользователя.</span><span class="sxs-lookup"><span data-stu-id="73560-348">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="73560-349">Это означает, что пользователь больше не имеет политики широковещательного показа собраний Teams, которой они назначены, и будет наследовать политику Live Events поставщика, назначенную группе, которой принадлежит пользователь.</span><span class="sxs-lookup"><span data-stu-id="73560-349">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="73560-350">Для этого используйте следующий командлет в модуле Skype для бизнеса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="73560-350">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="73560-351">Вы можете использовать следующий командлет в модуле Teams PowerShell для выполнения этой задачи при масштабировании при использовании задания пакетной политики, где $users — это список пользователей, которые вы указали.</span><span class="sxs-lookup"><span data-stu-id="73560-351">You can use following cmdlet in the Teams Powershell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="73560-352">Назначение пакета политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="73560-352">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="73560-353">С помощью задания пакетной политики можно назначить пакету политики большим наборам пользователей за один раз без использования сценария.</span><span class="sxs-lookup"><span data-stu-id="73560-353">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="73560-354">```New-CsBatchPolicyPackageAssignmentOperation```С помощью командлета вы можете отправить пакет пользователей и пакет политики, который вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="73560-354">You use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="73560-355">Назначения обрабатываются как фоновая операция, и для каждого пакета создается идентификатор операции.</span><span class="sxs-lookup"><span data-stu-id="73560-355">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="73560-356">Затем вы можете использовать этот ```Get-CsBatchPolicyAssignmentOperation``` командлет для отслеживания хода выполнения и состояния заданий в пакете.</span><span class="sxs-lookup"><span data-stu-id="73560-356">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="73560-357">Вы можете указать пользователей по идентификатору объекта или по протоколу SIP.</span><span class="sxs-lookup"><span data-stu-id="73560-357">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="73560-358">Обратите внимание, что адрес SIP пользователя часто имеет то же значение, что и имя участника-пользователя (UPN) или адрес электронной почты, но это не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="73560-358">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="73560-359">Если пользователь указан с использованием имени участника-пользователя или почтового сообщения, но его значение отличается от адреса SIP, для пользователя не будет установлено назначение политики.</span><span class="sxs-lookup"><span data-stu-id="73560-359">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="73560-360">Если пакет включает повторяющиеся пользователи, дубликаты удаляются из пакета перед обработкой и состоянием будут предоставляться только для уникальных пользователей, остающихся в пакете.</span><span class="sxs-lookup"><span data-stu-id="73560-360">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="73560-361">Пакет может содержать до 5 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="73560-361">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="73560-362">Для достижения наилучших результатов не отправляйте более нескольких пакетов одновременно.</span><span class="sxs-lookup"><span data-stu-id="73560-362">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="73560-363">Разрешите пакетам завершить обработку перед отправкой пакетов.</span><span class="sxs-lookup"><span data-stu-id="73560-363">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="73560-364">Установка и подключение к модулю Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="73560-364">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="73560-365">Выполните указанные ниже действия, чтобы установить [модуль Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (если вы еще этого не сделали).</span><span class="sxs-lookup"><span data-stu-id="73560-365">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="73560-366">Убедитесь, что вы установили версию 1.0.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="73560-366">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="73560-367">Выполните указанные ниже действия, чтобы подключиться к Teams и начать сеанс.</span><span class="sxs-lookup"><span data-stu-id="73560-367">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="73560-368">Когда вам будет предложено, войдите в систему с помощью учетных данных администратора.</span><span class="sxs-lookup"><span data-stu-id="73560-368">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="73560-369">Назначение пакета политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="73560-369">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="73560-370">В этом примере мы используем ```New-CsBatchPolicyPackageAssignmentOperation``` командлет для назначения пакета политики Education_PrimaryStudent пакету пользователей.</span><span class="sxs-lookup"><span data-stu-id="73560-370">In this example, we use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

<span data-ttu-id="73560-371">Дополнительные сведения можно найти в статье [Создание и CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="73560-371">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="73560-372">Получение статуса задания пакетной обработки</span><span class="sxs-lookup"><span data-stu-id="73560-372">Get the status of a batch assignment</span></span>

<span data-ttu-id="73560-373">Выполните указанные ниже действия, чтобы получить сведения о состоянии задания пакета, где идентификатор операции — это значение, возвращаемое ```New-CsBatchPolicyAssignmentOperation``` командлетом для данного пакета.</span><span class="sxs-lookup"><span data-stu-id="73560-373">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="73560-374">Если в выходных данных показано, что произошла ошибка, выполните указанные ниже действия, чтобы получить дополнительные сведения об ошибках, которые находятся в ```UserState``` свойстве.</span><span class="sxs-lookup"><span data-stu-id="73560-374">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="73560-375">Дополнительные сведения можно найти в [статьях Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="73560-375">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="73560-376">См. также</span><span class="sxs-lookup"><span data-stu-id="73560-376">Related topics</span></span>

- [<span data-ttu-id="73560-377">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="73560-377">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
