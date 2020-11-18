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
ms.openlocfilehash: ada58a9abf07e606f91d48b7ac71ba06d4c1496a
ms.sourcegitcommit: b282acc1633c2d62bbff0ea77b6b647775ae6dfe
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "49085703"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="fddcc-103">Назначение политик вашим пользователям в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fddcc-103">Assign policies to your users in Microsoft Teams</span></span>

<span data-ttu-id="fddcc-104">Администраторы используют политики для управления возможностями Teams, доступными для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="fddcc-104">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="fddcc-105">Например, вы можете присвоить имя только некоторые политики, политики собраний и политики обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="fddcc-105">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="fddcc-106">Организации имеют различные типы пользователей с уникальными потребностями, пользовательские политики, созданные и назначаемые, позволяют настраивать параметры политики для разных наборов пользователей на основе этих нужд.</span><span class="sxs-lookup"><span data-stu-id="fddcc-106">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="fddcc-107">Для упрощения управления политиками в Организации Teams предлагается несколько способов назначения политик пользователям.</span><span class="sxs-lookup"><span data-stu-id="fddcc-107">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="fddcc-108">Политику можно назначить непосредственно пользователям, как по отдельности, так и по масштабу в рамках задания или в группу, в которую входят пользователи.</span><span class="sxs-lookup"><span data-stu-id="fddcc-108">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="fddcc-109">Вы также можете использовать пакеты политик, чтобы назначить набор политик для пользователей в Организации, у которых есть похожие роли.</span><span class="sxs-lookup"><span data-stu-id="fddcc-109">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="fddcc-110">Выбор параметра зависит от количества политик, которые вы управляете, и количества пользователей, которым вы назначаете.</span><span class="sxs-lookup"><span data-stu-id="fddcc-110">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span> <span data-ttu-id="fddcc-111">Настроив глобальные политики (параметры по умолчанию на уровне Организации) таким образом, чтобы они применялись к максимальному количеству пользователей в Организации, вам нужно будет назначать политики только тем пользователям, которым требуются специализированные политики.</span><span class="sxs-lookup"><span data-stu-id="fddcc-111">By setting the global (Org-wide default) policies so that they apply to the largest number of users in your organization, you only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="fddcc-112">В этой статье описаны различные способы назначения политик пользователям и рекомендуемые сценарии для того, когда следует использовать эту возможность.</span><span class="sxs-lookup"><span data-stu-id="fddcc-112">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="fddcc-113">Какая политика имеет приоритет?</span><span class="sxs-lookup"><span data-stu-id="fddcc-113">Which policy takes precedence?</span></span>

<span data-ttu-id="fddcc-114">У пользователя есть одна действующая политика для каждого типа политики.</span><span class="sxs-lookup"><span data-stu-id="fddcc-114">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="fddcc-115">Возможно или даже, что пользователю явно назначена политика, и он также является членом одной или нескольких групп, которым назначена политика того же типа.</span><span class="sxs-lookup"><span data-stu-id="fddcc-115">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="fddcc-116">В сценариях такого типа приоритет имеет политика.</span><span class="sxs-lookup"><span data-stu-id="fddcc-116">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="fddcc-117">Действующая политика пользователя определяется в соответствии с правилами приоритета, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="fddcc-117">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="fddcc-118">Если пользователю назначена политика (отдельно или по назначению), она имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="fddcc-118">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="fddcc-119">В приведенном ниже примере действующая политика пользователя — это Lincoln квадратная политика для собраний, которая непосредственно назначается пользователю.</span><span class="sxs-lookup"><span data-stu-id="fddcc-119">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![Схема, показывающая, как имеет приоритет более прямую назначенную политику](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="fddcc-121">Если пользователь не назначил политике определенного типа, политика, назначенная группе, членом которой является пользователь, имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="fddcc-121">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="fddcc-122">Если пользователь является членом нескольких групп, политика, имеющая наивысший [рейтинг назначения группы](#group-assignment-ranking) для данного типа политики, имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="fddcc-122">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="fddcc-123">В этом примере действующая политика пользователя — это политика Exec Teams и HD, которая имеет наивысший рейтинг назначения относительно других групп, участником которых является этот пользователь, и которым также назначена политика того же типа политики.</span><span class="sxs-lookup"><span data-stu-id="fddcc-123">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![Схема, на которой показано, как действует политика, унаследованная от группы](media/assign-policies-example-group.png)

<span data-ttu-id="fddcc-125">Если пользователь не назначил политику или не является участником ни одной из групп, которым назначена политика, пользователь получает глобальную политику (по умолчанию для всей организации) для этого типа политики.</span><span class="sxs-lookup"><span data-stu-id="fddcc-125">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="fddcc-126">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="fddcc-126">Here's an example.</span></span>

![Схема, показывающая, как Глобальная политика имеет приоритет](media/assign-policies-example-global.png)

<span data-ttu-id="fddcc-128">Дополнительные сведения можно найти в разделе [правила приоритета](#precedence-rules).</span><span class="sxs-lookup"><span data-stu-id="fddcc-128">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="fddcc-129">Способы назначения политик</span><span class="sxs-lookup"><span data-stu-id="fddcc-129">Ways to assign policies</span></span>

<span data-ttu-id="fddcc-130">Ниже приведены общие сведения о способах назначения политик пользователям и рекомендуемых сценариях для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="fddcc-130">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="fddcc-131">Чтобы получить дополнительные сведения, щелкните ссылки.</span><span class="sxs-lookup"><span data-stu-id="fddcc-131">Click the links to learn more.</span></span>

<span data-ttu-id="fddcc-132">Прежде чем назначать политики отдельным пользователям или группам, начните с [настройки глобальных политик (по умолчанию в масштабах организации)](#set-the-global-policies) , чтобы они применялись к максимальному числу пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="fddcc-132">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="fddcc-133">После настройки глобальных политик вам потребуется назначать политики только тем пользователям, которым требуются специализированные политики.</span><span class="sxs-lookup"><span data-stu-id="fddcc-133">Once the global policies are set, you will only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="fddcc-134">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="fddcc-134">Do this</span></span>  |<span data-ttu-id="fddcc-135">Если...</span><span class="sxs-lookup"><span data-stu-id="fddcc-135">If...</span></span>  | <span data-ttu-id="fddcc-136">Использование...</span><span class="sxs-lookup"><span data-stu-id="fddcc-136">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="fddcc-137">Назначение политики отдельным пользователям</span><span class="sxs-lookup"><span data-stu-id="fddcc-137">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="fddcc-138">Вы не знакомы с Teams и просто приступите к работе или вам нужно назначить одну или несколько политик небольшим числам пользователей.</span><span class="sxs-lookup"><span data-stu-id="fddcc-138">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="fddcc-139">Центр администрирования Microsoft Teams или командлеты PowerShell в модуле PowerShell Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="fddcc-139">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
|[<span data-ttu-id="fddcc-140">Назначение политики группе</span><span class="sxs-lookup"><span data-stu-id="fddcc-140">Assign a policy to a group</span></span>](#assign-a-policy-to-a-group) |<span data-ttu-id="fddcc-141">Необходимо назначить политики, основанные на членстве в группе пользователя.</span><span class="sxs-lookup"><span data-stu-id="fddcc-141">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="fddcc-142">Например, вы хотите назначить политику для всех пользователей в группе безопасности или списке рассылки.</span><span class="sxs-lookup"><span data-stu-id="fddcc-142">For example, you want to assign a policy to all users in a security group or distribution list.</span></span>| <span data-ttu-id="fddcc-143">Центр администрирования Microsoft Teams или командлеты PowerShell из модуля Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="fddcc-143">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="fddcc-144">Назначение политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="fddcc-144">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="fddcc-145">Вы должны назначать политики большим наборам пользователей.</span><span class="sxs-lookup"><span data-stu-id="fddcc-145">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="fddcc-146">Например, вы хотите назначить политику для сотен или тысяч пользователей в Организации одновременно.</span><span class="sxs-lookup"><span data-stu-id="fddcc-146">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="fddcc-147">Центр администрирования Microsoft Teams или командлеты PowerShell из модуля Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="fddcc-147">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="fddcc-148">Назначение пользователю пакета политики</span><span class="sxs-lookup"><span data-stu-id="fddcc-148">Assign a policy package to users</span></span>](#assign-a-policy-package-to-users)  | <span data-ttu-id="fddcc-149">Необходимо назначить несколько политик определенным наборам пользователей организации, которые имеют одинаковые или аналогичные роли.</span><span class="sxs-lookup"><span data-stu-id="fddcc-149">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="fddcc-150">Например, назначьте в учебном заведении пакет политики образования для преподавателей, чтобы предоставить им полный доступ к беседам, звонку, собраниям и пакету политики образования (дополнительный учебный учащийся), чтобы ограничить некоторые возможности, такие как частный звонок.</span><span class="sxs-lookup"><span data-stu-id="fddcc-150">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="fddcc-151">Центр администрирования Microsoft Teams или командлеты PowerShell из модуля Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="fddcc-151">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="fddcc-152">[Назначение пакета политики группе](#assign-a-policy-package-to-a-group) (в частном предварительной версии)</span><span class="sxs-lookup"><span data-stu-id="fddcc-152">[Assign a policy package to a group](#assign-a-policy-package-to-a-group) (in private preview)</span></span>   |<span data-ttu-id="fddcc-153">Вы должны назначить несколько политик для группы пользователей в вашей организации с одинаковыми или аналогичными ролями.</span><span class="sxs-lookup"><span data-stu-id="fddcc-153">You need to assign multiple policies to a group of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="fddcc-154">Например, вы хотите назначить пакет политики всем пользователям в группе безопасности или списке рассылки.</span><span class="sxs-lookup"><span data-stu-id="fddcc-154">For example, you want to assign a policy package to all users in a security group or distribution list.</span></span> |<span data-ttu-id="fddcc-155">Центр администрирования Microsoft Teams (ожидается в ближайшее время) или командлеты PowerShell из модуля Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="fddcc-155">The Microsoft Teams admin center (coming soon) or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="fddcc-156">Назначение пакета политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="fddcc-156">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="fddcc-157">Необходимо назначить несколько политик для пакета пользователей в Организации с одинаковыми или аналогичными ролями.</span><span class="sxs-lookup"><span data-stu-id="fddcc-157">You need to assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="fddcc-158">Например, вы можете назначить пакету политики образования для всех преподавателей в учебном заведении с помощью пакетного задания, чтобы предоставить им полный доступ к разговорам, звонкам и собраниям, а также назначить пакету политики образования (дополнительный учебный учащийся) пакету вспомогательных учащихся, чтобы ограничить некоторые возможности, такие как частный звонок.</span><span class="sxs-lookup"><span data-stu-id="fddcc-158">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings and assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities like private calling.</span></span>|<span data-ttu-id="fddcc-159">Командлеты PowerShell в модуле PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="fddcc-159">PowerShell cmdlets in the Teams PowerShell module</span></span>|


## <a name="set-the-global-policies"></a><span data-ttu-id="fddcc-160">Настройка глобальных политик</span><span class="sxs-lookup"><span data-stu-id="fddcc-160">Set the global policies</span></span>

<span data-ttu-id="fddcc-161">Выполните указанные ниже действия, чтобы настроить глобальные политики (параметры по умолчанию для всей организации) для каждого типа политики.</span><span class="sxs-lookup"><span data-stu-id="fddcc-161">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="fddcc-162">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fddcc-162">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="fddcc-163">В левой области навигации центра администрирования Microsoft Teams перейдите на страницу политики для типа политики, которую вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="fddcc-163">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="fddcc-164">Например, политики **Teams**  >  **Teams**, политики собраний по **собраниям**,  >  **Meetings policies** **политики обмена сообщениями** и политики **голосовой связи**  >  **Calling policies**.</span><span class="sxs-lookup"><span data-stu-id="fddcc-164">For example, **Teams** > **Teams policies**, **Meetings** > **Meetings policies**, **Messaging policies**, or **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="fddcc-165">Выберите **глобальную политику (по умолчанию на уровне Организации)** для просмотра текущих параметров.</span><span class="sxs-lookup"><span data-stu-id="fddcc-165">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="fddcc-166">При необходимости обновите политику и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="fddcc-166">Update the policy as needed, and then select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="fddcc-167">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="fddcc-167">Using PowerShell</span></span>

<span data-ttu-id="fddcc-168">Чтобы настроить глобальные политики с помощью PowerShell, используйте глобальный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="fddcc-168">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="fddcc-169">Сначала просмотрите текущую глобальную политику, чтобы определить, какую настройку нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="fddcc-169">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

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

<span data-ttu-id="fddcc-170">Затем при необходимости обновите глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="fddcc-170">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="fddcc-171">Для параметров, которые вы хотите изменить, нужно указать только значения.</span><span class="sxs-lookup"><span data-stu-id="fddcc-171">You only need to specify values for the settings that you want to change.</span></span> 
 
```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="fddcc-172">Назначение политики отдельным пользователям</span><span class="sxs-lookup"><span data-stu-id="fddcc-172">Assign a policy to individual users</span></span>

<span data-ttu-id="fddcc-173">Выполните указанные ниже действия, чтобы назначить политику для отдельного пользователя или для небольшого количества пользователей за один раз.</span><span class="sxs-lookup"><span data-stu-id="fddcc-173">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="fddcc-174">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fddcc-174">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="fddcc-175">Чтобы назначить пользователю политику, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="fddcc-175">To assign a policy to a user:</span></span>

1. <span data-ttu-id="fddcc-176">В Центре администрирования Microsoft Teams в области навигации слева перейдите в раздел **Пользователи**, затем щелкните пользователя.</span><span class="sxs-lookup"><span data-stu-id="fddcc-176">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="fddcc-177">Выберите пользователя, щелкнув слева от его имени, затем нажмите кнопку **Изменить параметры**.</span><span class="sxs-lookup"><span data-stu-id="fddcc-177">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="fddcc-178">Выберите политику, которую вы хотите назначить, и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="fddcc-178">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="fddcc-179">Кроме того, вы можете сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="fddcc-179">Or, you can also do the following:</span></span>

1. <span data-ttu-id="fddcc-180">В левой области навигации центра администрирования Microsoft Teams перейдите на страницу "политика".</span><span class="sxs-lookup"><span data-stu-id="fddcc-180">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="fddcc-181">Выберите политику, которую вы хотите назначить, щелкнув слева от ее имени.</span><span class="sxs-lookup"><span data-stu-id="fddcc-181">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="fddcc-182">Выберите **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="fddcc-182">Select **Manage users**.</span></span>
4. <span data-ttu-id="fddcc-183">В области **Управление пользователями** выполните поиск по отображаемому имени или по имени пользователя, выберите имя и нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="fddcc-183">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="fddcc-184">Повторите это действие для каждого пользователя, которого нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="fddcc-184">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="fddcc-185">Завершив добавление пользователей, нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="fddcc-185">When you're finished adding users, select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="fddcc-186">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="fddcc-186">Using PowerShell</span></span>

<span data-ttu-id="fddcc-187">У каждого типа политики есть собственный набор командлетов для управления ею.</span><span class="sxs-lookup"><span data-stu-id="fddcc-187">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="fddcc-188">Используйте ```Grant-``` командлет для определенного типа политики, чтобы назначить политику.</span><span class="sxs-lookup"><span data-stu-id="fddcc-188">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="fddcc-189">Например, ```Grant-CsTeamsMeetingPolicy``` можно использовать командлет для назначения пользователям политики собрания Teams.</span><span class="sxs-lookup"><span data-stu-id="fddcc-189">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="fddcc-190">Эти командлеты включены в модуль PowerShell Skype для бизнеса Online и описаны в [справочной документации по командлетам Skype для бизнеса](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="fddcc-190">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="fddcc-191">Скачайте и установите [модуль PowerShell Skype для бизнеса Online](https://www.microsoft.com/download/details.aspx?id=39366) (если вы еще этого не сделали), а затем выполните указанные ниже действия, чтобы подключиться к Skype для бизнеса Online и начать сеанс.</span><span class="sxs-lookup"><span data-stu-id="fddcc-191">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

> [!NOTE]
> <span data-ttu-id="fddcc-192">Skype для бизнеса Online уже входит в состав последнего модуля PowerShell для Teams.</span><span class="sxs-lookup"><span data-stu-id="fddcc-192">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="fddcc-193">Если вы используете последнюю версию [общедоступной оболочки для Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), вам не нужно устанавливать соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="fddcc-193">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
Import-Module -Name MicrosoftTeams
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="fddcc-194">В этом примере мы назначаем политику собраний Teams, которая называется политикой собраний учащихся, пользователю с именем Reda.</span><span class="sxs-lookup"><span data-stu-id="fddcc-194">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="fddcc-195">Дополнительные сведения можно найти в статье [Управление политиками с помощью PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span><span class="sxs-lookup"><span data-stu-id="fddcc-195">To learn more, read [Manage policies via PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="fddcc-196">Назначение политики группе</span><span class="sxs-lookup"><span data-stu-id="fddcc-196">Assign a policy to a group</span></span>

<span data-ttu-id="fddcc-197">Назначение политики для групп позволяет назначить политику группе пользователей, например к группе безопасности или списку рассылки.</span><span class="sxs-lookup"><span data-stu-id="fddcc-197">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="fddcc-198">Назначение политики распространяется на участников группы в соответствии с правилами очередности.</span><span class="sxs-lookup"><span data-stu-id="fddcc-198">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="fddcc-199">При добавлении или удалении участников группы, назначения политик для них обновляются соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="fddcc-199">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="fddcc-200">Назначение политики для групп рекомендовано для групп до 50 000 пользователей, но оно также работает с более крупными группами.</span><span class="sxs-lookup"><span data-stu-id="fddcc-200">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="fddcc-201">После назначения политики она немедленно назначается группе.</span><span class="sxs-lookup"><span data-stu-id="fddcc-201">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="fddcc-202">Однако обратите внимание, что распространение назначения политики для участников группы выполняется в фоновом режиме и может занять некоторое время, в зависимости от размера группы.</span><span class="sxs-lookup"><span data-stu-id="fddcc-202">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="fddcc-203">Это справедливо, если политика не назначена группе, а также при добавлении пользователей в группу или удалении ее из нее.</span><span class="sxs-lookup"><span data-stu-id="fddcc-203">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

<span data-ttu-id="fddcc-204">Назначение групповой политики распространяется только на пользователей, которые являются прямыми участниками группы.</span><span class="sxs-lookup"><span data-stu-id="fddcc-204">Group policy assignments are only propagated to users that are direct members of the group.</span></span> <span data-ttu-id="fddcc-205">Назначения не распространяются на пользователей вложенных групп.</span><span class="sxs-lookup"><span data-stu-id="fddcc-205">The assignments aren't propagated to members of nested groups.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="fddcc-206">Что необходимо знать о назначении политики группам</span><span class="sxs-lookup"><span data-stu-id="fddcc-206">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="fddcc-207">Прежде чем приступить к работе, важно понимать правила приоритета и ранжирование назначения групп.</span><span class="sxs-lookup"><span data-stu-id="fddcc-207">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="fddcc-208">Правила приоритета</span><span class="sxs-lookup"><span data-stu-id="fddcc-208">Precedence rules</span></span>

<span data-ttu-id="fddcc-209">Для определенного типа политики действующая политика пользователя определяется в соответствии с приведенными ниже сведениями.</span><span class="sxs-lookup"><span data-stu-id="fddcc-209">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="fddcc-210">Политика, непосредственно назначенная пользователю, имеет приоритет над любыми другими политиками того же типа, которые назначены группе.</span><span class="sxs-lookup"><span data-stu-id="fddcc-210">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="fddcc-211">Другими словами, если пользователю явно назначена политика определенного типа, этот пользователь не наследует политику того же типа из группы.</span><span class="sxs-lookup"><span data-stu-id="fddcc-211">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="fddcc-212">Это также означает, что если пользователь имеет политику, назначенную определенному типу, вы должны удалить ее от пользователя, прежде чем она сможет наследовать политику того же типа из группы.</span><span class="sxs-lookup"><span data-stu-id="fddcc-212">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="fddcc-213">Если пользователь не имеет назначенной им политики и является членом двух или более групп, а каждая группа имеет политику с таким же типом, пользователь наследует политику назначения группы, имеющую наивысший рейтинг.</span><span class="sxs-lookup"><span data-stu-id="fddcc-213">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="fddcc-214">Если пользователь не является членом ни одной из групп, которым назначена политика, для него применяется Глобальная политика (по умолчанию на уровне Организации) для этого типа политики.</span><span class="sxs-lookup"><span data-stu-id="fddcc-214">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="fddcc-215">Действующая политика пользователя обновляется согласно этим правилам, когда пользователь добавляется или удаляется из группы, которой назначена политика, политика не назначается группе, или политика, непосредственно назначенная пользователю, удаляется.</span><span class="sxs-lookup"><span data-stu-id="fddcc-215">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="fddcc-216">Ранжирование назначения групп</span><span class="sxs-lookup"><span data-stu-id="fddcc-216">Group assignment ranking</span></span>
 
<span data-ttu-id="fddcc-217">Когда вы назначаете группе политику, вы указываете рейтинг для назначения группы.</span><span class="sxs-lookup"><span data-stu-id="fddcc-217">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="fddcc-218">Этот параметр используется для определения политики, которую пользователь должен наследовать в качестве действующей политики, если пользователь является членом двух или более групп, и каждой группе назначена политика одного и того же типа.</span><span class="sxs-lookup"><span data-stu-id="fddcc-218">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="fddcc-219">Ранжирование назначения групп определяется относительно других назначений групп того же типа.</span><span class="sxs-lookup"><span data-stu-id="fddcc-219">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="fddcc-220">Например, если вы назначаете политику вызовов двум группам, задайте для ранжирования одного задания значение 1, а для другого — 2, где 1 — наивысший рейтинг.</span><span class="sxs-lookup"><span data-stu-id="fddcc-220">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="fddcc-221">Ранжирование назначения групп указывает на то, что участие в группах является более важным или более релевантным по сравнению с наследованием в других группах.</span><span class="sxs-lookup"><span data-stu-id="fddcc-221">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="fddcc-222">Например, предположим, что у вас есть две группы, магазин сотрудников и руководителей магазина.</span><span class="sxs-lookup"><span data-stu-id="fddcc-222">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="fddcc-223">Обеим группам назначается политика вызова Teams, в котором хранятся политики вызова для сотрудников и политики звонков руководителей магазина соответственно.</span><span class="sxs-lookup"><span data-stu-id="fddcc-223">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="fddcc-224">Для руководителя магазина, который находится в обеих группах, роль руководителя больше важна, чем роль сотрудника, поэтому политика звонков, назначенная группе руководителей магазина, должна иметь более высокий рейтинг.</span><span class="sxs-lookup"><span data-stu-id="fddcc-224">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="fddcc-225">Сгруппирован</span><span class="sxs-lookup"><span data-stu-id="fddcc-225">Group</span></span> |<span data-ttu-id="fddcc-226">Имя политики вызова Teams</span><span class="sxs-lookup"><span data-stu-id="fddcc-226">Teams calling policy name</span></span>  |<span data-ttu-id="fddcc-227">Rank (Ранг)</span><span class="sxs-lookup"><span data-stu-id="fddcc-227">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="fddcc-228">Руководители магазина</span><span class="sxs-lookup"><span data-stu-id="fddcc-228">Store Managers</span></span>   |<span data-ttu-id="fddcc-229">Политика звонков руководителей магазина</span><span class="sxs-lookup"><span data-stu-id="fddcc-229">Store Managers Calling Policy</span></span>         |<span data-ttu-id="fddcc-230">1</span><span class="sxs-lookup"><span data-stu-id="fddcc-230">1</span></span>|
|<span data-ttu-id="fddcc-231">Магазин сотрудников</span><span class="sxs-lookup"><span data-stu-id="fddcc-231">Store Employees</span></span>    |<span data-ttu-id="fddcc-232">Хранение политики звонка для сотрудников</span><span class="sxs-lookup"><span data-stu-id="fddcc-232">Store Employees Calling Policy</span></span>      |<span data-ttu-id="fddcc-233">2</span><span class="sxs-lookup"><span data-stu-id="fddcc-233">2</span></span>|

<span data-ttu-id="fddcc-234">Если вы не укажете ранжирование, для назначения политики будет задан самый низкий рейтинг.</span><span class="sxs-lookup"><span data-stu-id="fddcc-234">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span> 

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="fddcc-235">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fddcc-235">Using the Microsoft Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="fddcc-236">В настоящее время назначение политики для групп, использующих центр администрирования Microsoft Teams, доступно только для политики звонков в Teams, политики для приема звонков в Teams, политики Teams, политики собрания Teams и политики обмена сообщениями в группе Teams.</span><span class="sxs-lookup"><span data-stu-id="fddcc-236">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="fddcc-237">Для других типов политик используйте PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fddcc-237">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="fddcc-238">В левой области навигации центра администрирования Microsoft Teams перейдите на страницу тип политики.</span><span class="sxs-lookup"><span data-stu-id="fddcc-238">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="fddcc-239">Например, **перейдите к разделу**  >  **политики собраний по собраниям**.</span><span class="sxs-lookup"><span data-stu-id="fddcc-239">For example, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="fddcc-240">Перейдите на вкладку **назначение групповой политики** .</span><span class="sxs-lookup"><span data-stu-id="fddcc-240">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="fddcc-241">Нажмите кнопку **Добавить группу**, а затем в области **Назначение политики для группировки** выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="fddcc-241">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="fddcc-242">Найдите и добавьте группу, которой вы хотите назначить политику.</span><span class="sxs-lookup"><span data-stu-id="fddcc-242">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="fddcc-243">Задайте рейтинг для назначения групп.</span><span class="sxs-lookup"><span data-stu-id="fddcc-243">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="fddcc-244">Выберите политику, которую вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="fddcc-244">Select the policy that you want to assign.</span></span> 
    4. <span data-ttu-id="fddcc-245">Нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="fddcc-245">Select **Apply**.</span></span>

<span data-ttu-id="fddcc-246">Чтобы удалить назначение групповой политики, на вкладке **назначение групповой политики** на странице Политика выберите назначение группы и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="fddcc-246">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="fddcc-247">Чтобы изменить ранжирование назначения группы, необходимо сначала удалить назначение групповой политики.</span><span class="sxs-lookup"><span data-stu-id="fddcc-247">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="fddcc-248">Затем выполните описанные выше действия, чтобы назначить политику группе.</span><span class="sxs-lookup"><span data-stu-id="fddcc-248">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="fddcc-249">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="fddcc-249">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="fddcc-250">В настоящее время назначение политики для групп, использующих PowerShell, недоступно для всех типов политики Teams.</span><span class="sxs-lookup"><span data-stu-id="fddcc-250">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="fddcc-251">Ознакомьтесь со списком " [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) " для списка поддерживаемых типов политики.</span><span class="sxs-lookup"><span data-stu-id="fddcc-251">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="fddcc-252">Установка и подключение к модулю Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="fddcc-252">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="fddcc-253">Пошаговые инструкции можно найти в статье [Установка оболочки PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="fddcc-253">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-to-a-group-of-users"></a><span data-ttu-id="fddcc-254">Назначение политики группе пользователей</span><span class="sxs-lookup"><span data-stu-id="fddcc-254">Assign a policy to a group of users</span></span>

<span data-ttu-id="fddcc-255">С помощью командлета [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) можно назначить политику группе.</span><span class="sxs-lookup"><span data-stu-id="fddcc-255">You use the [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="fddcc-256">Вы можете указать группу, используя идентификатор объекта, адрес SIP или адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="fddcc-256">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="fddcc-257">В этом примере для группы с рейтингом назначения 1 назначается политика для собраний группы с названием политики собраний из Retail Manager.</span><span class="sxs-lookup"><span data-stu-id="fddcc-257">In this example, we assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="fddcc-258">Получение назначений политики для группы</span><span class="sxs-lookup"><span data-stu-id="fddcc-258">Get policy assignments for a group</span></span>

<span data-ttu-id="fddcc-259">Используйте командлет [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) , чтобы получить все политики, назначенные группе.</span><span class="sxs-lookup"><span data-stu-id="fddcc-259">Use the [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="fddcc-260">Обратите внимание, что группы всегда записываются в соответствии с их идентификатором группы, даже если для назначения политики был использован адрес SIP или адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="fddcc-260">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="fddcc-261">В этом примере мы извлекаем все политики, назначенные определенной группе.</span><span class="sxs-lookup"><span data-stu-id="fddcc-261">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="fddcc-262">В этом примере мы возвращаем все группы, которым назначена политика для собрания Teams.</span><span class="sxs-lookup"><span data-stu-id="fddcc-262">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="fddcc-263">Удаление политики из группы</span><span class="sxs-lookup"><span data-stu-id="fddcc-263">Remove a policy from a group</span></span>

<span data-ttu-id="fddcc-264">Удаление политики из группы с помощью командлета [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) .</span><span class="sxs-lookup"><span data-stu-id="fddcc-264">Use the [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="fddcc-265">При удалении политики из группы приоритеты других политик того же типа, которым назначена эта группа, и которые имеют более низкий рейтинг, будут обновлены.</span><span class="sxs-lookup"><span data-stu-id="fddcc-265">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="fddcc-266">Например, если вы удалите политику с рангом 2, то политики с рейтингом 3 и 4 будут обновляться в соответствии с их новым рейтингом.</span><span class="sxs-lookup"><span data-stu-id="fddcc-266">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="fddcc-267">Этот пример показан в двух приведенных ниже таблицах.</span><span class="sxs-lookup"><span data-stu-id="fddcc-267">The following two tables show this example.</span></span>

<span data-ttu-id="fddcc-268">Ниже приведен список назначений и приоритетов политики для собраний Teams.</span><span class="sxs-lookup"><span data-stu-id="fddcc-268">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="fddcc-269">Имя группы</span><span class="sxs-lookup"><span data-stu-id="fddcc-269">Group name</span></span>  |<span data-ttu-id="fddcc-270">Название политики</span><span class="sxs-lookup"><span data-stu-id="fddcc-270">Policy name</span></span>  |<span data-ttu-id="fddcc-271">Rank (Ранг)</span><span class="sxs-lookup"><span data-stu-id="fddcc-271">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="fddcc-272">Продажи</span><span class="sxs-lookup"><span data-stu-id="fddcc-272">Sales</span></span>    |<span data-ttu-id="fddcc-273">Политика продаж</span><span class="sxs-lookup"><span data-stu-id="fddcc-273">Sales policy</span></span>       | <span data-ttu-id="fddcc-274">1</span><span class="sxs-lookup"><span data-stu-id="fddcc-274">1</span></span>        |
|<span data-ttu-id="fddcc-275">Западная область</span><span class="sxs-lookup"><span data-stu-id="fddcc-275">West Region</span></span>     |<span data-ttu-id="fddcc-276">Политика "Западная область"</span><span class="sxs-lookup"><span data-stu-id="fddcc-276">West Region policy</span></span>         |<span data-ttu-id="fddcc-277">2</span><span class="sxs-lookup"><span data-stu-id="fddcc-277">2</span></span>         |
|<span data-ttu-id="fddcc-278">Умножен</span><span class="sxs-lookup"><span data-stu-id="fddcc-278">Division</span></span>    |<span data-ttu-id="fddcc-279">Политика деления</span><span class="sxs-lookup"><span data-stu-id="fddcc-279">Division policy</span></span>         |<span data-ttu-id="fddcc-280">3</span><span class="sxs-lookup"><span data-stu-id="fddcc-280">3</span></span>         |
|<span data-ttu-id="fddcc-281">Отделения</span><span class="sxs-lookup"><span data-stu-id="fddcc-281">Subsidiary</span></span>   |<span data-ttu-id="fddcc-282">Политика для дочерних компаний</span><span class="sxs-lookup"><span data-stu-id="fddcc-282">Subsidiary policy</span></span>        |<span data-ttu-id="fddcc-283">4</span><span class="sxs-lookup"><span data-stu-id="fddcc-283">4</span></span>         |

<span data-ttu-id="fddcc-284">Если удалить политику западных областей из группы Западная область, то назначения и приоритеты политики будут обновляться следующим образом.</span><span class="sxs-lookup"><span data-stu-id="fddcc-284">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="fddcc-285">Имя группы</span><span class="sxs-lookup"><span data-stu-id="fddcc-285">Group name</span></span>  |<span data-ttu-id="fddcc-286">Название политики</span><span class="sxs-lookup"><span data-stu-id="fddcc-286">Policy name</span></span>  |<span data-ttu-id="fddcc-287">Rank (Ранг)</span><span class="sxs-lookup"><span data-stu-id="fddcc-287">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="fddcc-288">Продажи</span><span class="sxs-lookup"><span data-stu-id="fddcc-288">Sales</span></span>    |<span data-ttu-id="fddcc-289">Политика продаж</span><span class="sxs-lookup"><span data-stu-id="fddcc-289">Sales policy</span></span>       | <span data-ttu-id="fddcc-290">1</span><span class="sxs-lookup"><span data-stu-id="fddcc-290">1</span></span>        |
|<span data-ttu-id="fddcc-291">Умножен</span><span class="sxs-lookup"><span data-stu-id="fddcc-291">Division</span></span>    |<span data-ttu-id="fddcc-292">Политика деления</span><span class="sxs-lookup"><span data-stu-id="fddcc-292">Division policy</span></span>         |<span data-ttu-id="fddcc-293">2</span><span class="sxs-lookup"><span data-stu-id="fddcc-293">2</span></span>         |
|<span data-ttu-id="fddcc-294">Отделения</span><span class="sxs-lookup"><span data-stu-id="fddcc-294">Subsidiary</span></span>   |<span data-ttu-id="fddcc-295">Политика для дочерних компаний</span><span class="sxs-lookup"><span data-stu-id="fddcc-295">Subsidiary policy</span></span>        |<span data-ttu-id="fddcc-296">3</span><span class="sxs-lookup"><span data-stu-id="fddcc-296">3</span></span>        |

<span data-ttu-id="fddcc-297">В данном примере политика для собрания Teams удаляется из группы.</span><span class="sxs-lookup"><span data-stu-id="fddcc-297">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="fddcc-298">Изменение назначения политики для группы</span><span class="sxs-lookup"><span data-stu-id="fddcc-298">Change a policy assignment for a group</span></span>

> [!NOTE]
> <span data-ttu-id="fddcc-299">Командлет [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) скоро будет доступен.</span><span class="sxs-lookup"><span data-stu-id="fddcc-299">The [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet will be available soon.</span></span> <span data-ttu-id="fddcc-300">В то же время, чтобы изменить назначение групповой политики, вы можете удалить текущее назначение политики из группы, а затем добавить новое назначение политики.</span><span class="sxs-lookup"><span data-stu-id="fddcc-300">In the meantime, to change a group policy assignment, you can remove the current policy assignment from the group, and then add a new policy assignment.</span></span>

<span data-ttu-id="fddcc-301">После назначения политики группе вы можете воспользоваться командлетом [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) , чтобы изменить назначение политики этой группы, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="fddcc-301">After you assign a policy to a group, you can use the [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="fddcc-302">Изменение ранжирования</span><span class="sxs-lookup"><span data-stu-id="fddcc-302">Change the ranking</span></span>
- <span data-ttu-id="fddcc-303">Изменение политики для определенного типа политики</span><span class="sxs-lookup"><span data-stu-id="fddcc-303">Change the policy of a given policy type</span></span>
- <span data-ttu-id="fddcc-304">Изменение политики для определенного типа политики и ранжирования</span><span class="sxs-lookup"><span data-stu-id="fddcc-304">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="fddcc-305">В этом примере мы изменим политику приостановки вызовов групп для группы на политику с именем SupportCallPark и рейтинг назначения 3.</span><span class="sxs-lookup"><span data-stu-id="fddcc-305">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="fddcc-306">Изменение действующей политики для пользователя</span><span class="sxs-lookup"><span data-stu-id="fddcc-306">Change the effective policy for a user</span></span>

<span data-ttu-id="fddcc-307">Ниже приведен пример изменения действующей политики для пользователя, которому непосредственно назначена политика.</span><span class="sxs-lookup"><span data-stu-id="fddcc-307">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="fddcc-308">Сначала мы используем командлет [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) вместе с ```PolicySource``` параметром, чтобы получить подробные сведения о политиках широковещательного показа собраний Teams, связанных с пользователем.</span><span class="sxs-lookup"><span data-stu-id="fddcc-308">First, we use the [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> 

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="fddcc-309">В выходных данных показано, что пользователю непосредственно назначена политика широковещательного показа собрания Teams, которая имеет приоритет над политикой "события поставщика", назначенной группе, в которую входит пользователь.</span><span class="sxs-lookup"><span data-stu-id="fddcc-309">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="fddcc-310">Теперь мы удаляем политику событий сотрудников от пользователя.</span><span class="sxs-lookup"><span data-stu-id="fddcc-310">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="fddcc-311">Это означает, что пользователь больше не имеет политики широковещательного показа собраний Teams, которой они назначены, и будет наследовать политику Live Events поставщика, назначенную группе, которой принадлежит пользователь.</span><span class="sxs-lookup"><span data-stu-id="fddcc-311">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="fddcc-312">Для этого используйте следующий командлет в модуле Skype для бизнеса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fddcc-312">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="fddcc-313">Вы можете использовать следующий командлет в модуле Teams PowerShell для выполнения этой задачи при масштабировании при использовании задания пакетной политики, где $users — это список пользователей, которые вы указали.</span><span class="sxs-lookup"><span data-stu-id="fddcc-313">You can use following cmdlet in the Teams PowerShell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="fddcc-314">Назначение политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="fddcc-314">Assign a policy to a batch of users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="fddcc-315">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fddcc-315">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="fddcc-316">Чтобы назначить политику для пользователей, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="fddcc-316">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="fddcc-317">В левой области навигации центра администрирования Microsoft Teams выберите пункт **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="fddcc-317">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="fddcc-318">Найдите пользователей, которым вы хотите назначить политику, или отфильтруйте представление, чтобы отобразить нужных пользователей.</span><span class="sxs-lookup"><span data-stu-id="fddcc-318">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="fddcc-319">В столбце **&#x2713;** (галочка) выберите пользователей.</span><span class="sxs-lookup"><span data-stu-id="fddcc-319">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="fddcc-320">Чтобы выбрать всех пользователей, щелкните &#x2713; (галочку) в верхней части таблицы.</span><span class="sxs-lookup"><span data-stu-id="fddcc-320">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="fddcc-321">Щелкните **Изменить настройки**, внесите нужные изменения и нажмите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="fddcc-321">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="fddcc-322">Чтобы просмотреть состояние назначения политики, в заголовке, который появляется в верхней части страницы **пользователей** после нажатия кнопки **Применить** для отправки назначения политики, щелкните **Журнал активности**.</span><span class="sxs-lookup"><span data-stu-id="fddcc-322">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you click **Apply** to submit your policy assignment, click **Activity log**.</span></span> <span data-ttu-id="fddcc-323">Либо в левой области навигации центра администрирования Microsoft Teams перейдите на **панель мониторинга**, а затем в разделе **Журнал активности** щелкните **Просмотреть сведения**.</span><span class="sxs-lookup"><span data-stu-id="fddcc-323">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, click **View details**.</span></span> <span data-ttu-id="fddcc-324">Журнал активности показывает назначения политики для пакетов более чем из 20 пользователей в центре администрирования Microsoft Teams за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="fddcc-324">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="fddcc-325">Дополнительные сведения можно найти [в статье Просмотр назначенных политик в журнале событий](activity-log.md).</span><span class="sxs-lookup"><span data-stu-id="fddcc-325">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="fddcc-326">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="fddcc-326">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="fddcc-327">В настоящее время назначение пакетной политики с помощью PowerShell недоступно для всех типов политики Teams.</span><span class="sxs-lookup"><span data-stu-id="fddcc-327">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="fddcc-328">Ознакомьтесь со списком " [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) " для списка поддерживаемых типов политики.</span><span class="sxs-lookup"><span data-stu-id="fddcc-328">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>
 
<span data-ttu-id="fddcc-329">С помощью назначения пакетной политики вы можете назначить политику большим наборам пользователей за один раз, не прибегая к использованию сценария.</span><span class="sxs-lookup"><span data-stu-id="fddcc-329">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="fddcc-330">С помощью командлета [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) вы можете отправить пакет пользователей и политику, которую вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="fddcc-330">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="fddcc-331">Задания будут обрабатываться в фоновом режиме, а для каждого пакета будет создан идентификатор операции.</span><span class="sxs-lookup"><span data-stu-id="fddcc-331">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="fddcc-332">Затем вы можете использовать командлет [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) для отслеживания хода выполнения и состояния заданий в пакете.</span><span class="sxs-lookup"><span data-stu-id="fddcc-332">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="fddcc-333">Вы можете указать пользователей по идентификатору объекта или по протоколу SIP.</span><span class="sxs-lookup"><span data-stu-id="fddcc-333">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="fddcc-334">Обратите внимание, что адрес SIP пользователя часто имеет то же значение, что и имя участника-пользователя (UPN) или адрес электронной почты, но это не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="fddcc-334">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="fddcc-335">Если пользователь указан с использованием имени участника-пользователя или почтового сообщения, но его значение отличается от адреса SIP, для пользователя не будет установлено назначение политики.</span><span class="sxs-lookup"><span data-stu-id="fddcc-335">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="fddcc-336">Если пакет включает повторяющиеся пользователи, дубликаты удаляются из пакета перед обработкой и состоянием будут предоставляться только для уникальных пользователей, остающихся в пакете.</span><span class="sxs-lookup"><span data-stu-id="fddcc-336">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="fddcc-337">Пакет может содержать до 5 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="fddcc-337">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="fddcc-338">Для достижения наилучших результатов не отправляйте более нескольких пакетов одновременно.</span><span class="sxs-lookup"><span data-stu-id="fddcc-338">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="fddcc-339">Разрешите пакетам завершить обработку перед отправкой пакетов.</span><span class="sxs-lookup"><span data-stu-id="fddcc-339">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="fddcc-340">Установка и подключение к модулю Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="fddcc-340">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="fddcc-341">Выполните указанные ниже действия, чтобы установить [модуль PowerShell Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams).</span><span class="sxs-lookup"><span data-stu-id="fddcc-341">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="fddcc-342">Убедитесь, что вы установили версию 1.0.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="fddcc-342">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="fddcc-343">Выполните указанные ниже действия, чтобы подключиться к Teams и начать сеанс.</span><span class="sxs-lookup"><span data-stu-id="fddcc-343">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="fddcc-344">Когда вам будет предложено, войдите в систему с помощью учетных данных администратора.</span><span class="sxs-lookup"><span data-stu-id="fddcc-344">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="fddcc-345">Установка и подключение к модулю Azure AD PowerShell для Graph (необязательно)</span><span class="sxs-lookup"><span data-stu-id="fddcc-345">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="fddcc-346">Кроме того, вам может потребоваться [загрузить и установить модуль Azure AD PowerShell для Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (если вы еще не сделали этого) и подключиться к Azure AD, чтобы получить список пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="fddcc-346">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="fddcc-347">Выполните указанные ниже действия, чтобы подключиться к Azure AD.</span><span class="sxs-lookup"><span data-stu-id="fddcc-347">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="fddcc-348">Когда вам будет предложено, войдите в систему с помощью учетных данных администратора, используемых для подключения к Teams.</span><span class="sxs-lookup"><span data-stu-id="fddcc-348">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="fddcc-349">Назначение политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="fddcc-349">Assign a policy to a batch of users</span></span>

<span data-ttu-id="fddcc-350">В этом примере мы используем командлет [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) , чтобы назначить политику настройки приложения с именем "Политика настройки приложений" для пакета пользователей, перечисленных в файле Users_ids. Text.</span><span class="sxs-lookup"><span data-stu-id="fddcc-350">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="fddcc-351">В этом примере мы подключаем подключение к Azure AD, чтобы получить доступ к коллекции пользователей, а затем назначить политику сообщений с именем "Новая политика для приема на работу" для пакета пользователей, указанного с помощью их SIP-адресов.</span><span class="sxs-lookup"><span data-stu-id="fddcc-351">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="fddcc-352">Получение статуса задания пакетной обработки</span><span class="sxs-lookup"><span data-stu-id="fddcc-352">Get the status of a batch assignment</span></span>

<span data-ttu-id="fddcc-353">Выполните указанные ниже действия, чтобы получить сведения о состоянии задания пакета, где идентификатор операции — это значение, возвращаемое ```New-CsBatchPolicyAssignmentOperation``` командлетом для данного пакета.</span><span class="sxs-lookup"><span data-stu-id="fddcc-353">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="fddcc-354">Если в выходных данных показано, что произошла ошибка, выполните указанные ниже действия, чтобы получить дополнительные сведения об ошибках, которые находятся в ```UserState``` свойстве.</span><span class="sxs-lookup"><span data-stu-id="fddcc-354">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="fddcc-355">Дополнительные сведения можно найти в [статьях Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="fddcc-355">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-package-to-users"></a><span data-ttu-id="fddcc-356">Назначение пользователю пакета политики</span><span class="sxs-lookup"><span data-stu-id="fddcc-356">Assign a policy package to users</span></span>

<span data-ttu-id="fddcc-357">Пакет политики в Teams — это набор предопределенных политик и параметров политики, которые можно назначить пользователям, имеющим такие же или аналогичные роли в Организации.</span><span class="sxs-lookup"><span data-stu-id="fddcc-357">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="fddcc-358">Каждый пакет политики разработан вокруг роли пользователя и включает стандартные политики и параметры политики, которые поддерживают действия, характерные для этой роли.</span><span class="sxs-lookup"><span data-stu-id="fddcc-358">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="fddcc-359">Некоторые примеры пакетов политики — это пакет для образования (преподаватель) и Здравоохранение (Clinical Worker).</span><span class="sxs-lookup"><span data-stu-id="fddcc-359">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span> <span data-ttu-id="fddcc-360">Дополнительные сведения можно найти [в разделе Управление пакетами политики в Teams](manage-policy-packages.md).</span><span class="sxs-lookup"><span data-stu-id="fddcc-360">To learn more, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="fddcc-361">Назначение пакета политики для одного пользователя</span><span class="sxs-lookup"><span data-stu-id="fddcc-361">Assign a policy package to one user</span></span>

1. <span data-ttu-id="fddcc-362">В Центре администрирования Microsoft Teams в области навигации слева перейдите в раздел **Пользователи**, затем щелкните пользователя.</span><span class="sxs-lookup"><span data-stu-id="fddcc-362">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="fddcc-363">На странице пользователя нажмите **политики**, а затем рядом с пунктом **Политика** выберите команду **изменить**.</span><span class="sxs-lookup"><span data-stu-id="fddcc-363">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="fddcc-364">В области **Назначение пакета политики** выберите пакет, который вы хотите назначить, и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="fddcc-364">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="fddcc-365">Назначение пакета политики нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="fddcc-365">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="fddcc-366">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел **пакеты политики**, а затем выберите пакет политики, который вы хотите назначить, щелкнув слева от его имени.</span><span class="sxs-lookup"><span data-stu-id="fddcc-366">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="fddcc-367">Щелкните **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="fddcc-367">Click **Manage users**.</span></span>
3. <span data-ttu-id="fddcc-368">В области **Управление пользователями** выполните поиск по отображаемому имени или по имени пользователя, выберите имя и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="fddcc-368">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="fddcc-369">Повторите это действие для каждого пользователя, которого нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="fddcc-369">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="fddcc-370">Завершив добавление пользователей, нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="fddcc-370">When you're finished adding users, click **Save**.</span></span>

## <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="fddcc-371">Назначение пакета политики группе</span><span class="sxs-lookup"><span data-stu-id="fddcc-371">Assign a policy package to a group</span></span>

<span data-ttu-id="fddcc-372">**Эта функция доступна в закрытой ознакомительной версии**</span><span class="sxs-lookup"><span data-stu-id="fddcc-372">**This feature is in private preview**</span></span>

<span data-ttu-id="fddcc-373">Назначение пакетов политики группам позволяет назначать несколько политик группе пользователей, например группе безопасности или группе рассылки.</span><span class="sxs-lookup"><span data-stu-id="fddcc-373">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="fddcc-374">Назначение политики распространяется на участников группы в соответствии с правилами очередности.</span><span class="sxs-lookup"><span data-stu-id="fddcc-374">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="fddcc-375">При добавлении или удалении участников группы, назначения политик для них обновляются соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="fddcc-375">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="fddcc-376">Назначение пакета политики для групп рекомендовано для групп до 50 000 пользователей, но оно также работает с более крупными группами.</span><span class="sxs-lookup"><span data-stu-id="fddcc-376">Policy package assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span> 

<span data-ttu-id="fddcc-377">Когда вы назначаете пакет политики, он сразу же назначается группе.</span><span class="sxs-lookup"><span data-stu-id="fddcc-377">When you assign the policy package, it's immediately assigned to the group.</span></span> <span data-ttu-id="fddcc-378">Однако обратите внимание, что распространение назначения политики для участников группы выполняется в фоновом режиме и может занять некоторое время, в зависимости от размера группы.</span><span class="sxs-lookup"><span data-stu-id="fddcc-378">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="fddcc-379">Это справедливо, если политика не назначена группе, а также при добавлении пользователей в группу или удалении ее из нее.</span><span class="sxs-lookup"><span data-stu-id="fddcc-379">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fddcc-380">Прежде чем приступить к работе, важно понимать [правила приоритета](#precedence-rules) и [ранжирование назначения групп](#group-assignment-ranking).</span><span class="sxs-lookup"><span data-stu-id="fddcc-380">Before you get started, it's important to understand [precedence rules](#precedence-rules) and [group assignment ranking](#group-assignment-ranking).</span></span> <span data-ttu-id="fddcc-381">Убедитесь в том, [что вы знаете, что нужно знать о назначении политики для групп,](#what-you-need-to-know-about-policy-assignment-to-groups) описанных ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="fddcc-381">Make sure you read and understand the concepts in [What you need to know about policy assignment to groups](#what-you-need-to-know-about-policy-assignment-to-groups) earlier in this article.</span></span>

### <a name="using-the-microsoft-teams-admin-center-coming-soon"></a><span data-ttu-id="fddcc-382">Использование центра администрирования Microsoft Teams (ожидается в ближайшее время)</span><span class="sxs-lookup"><span data-stu-id="fddcc-382">Using the Microsoft Teams admin center (coming soon)</span></span>

<span data-ttu-id="fddcc-383">Назначение пакета политики для групп в центре администрирования Microsoft Teams вскоре скоро будет.</span><span class="sxs-lookup"><span data-stu-id="fddcc-383">Policy package assignment to groups in the Microsoft Teams admin center is coming soon.</span></span> <span data-ttu-id="fddcc-384">Вернитесь сюда, чтобы узнать о последних обновлениях.</span><span class="sxs-lookup"><span data-stu-id="fddcc-384">Check back here for the latest updates.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="fddcc-385">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="fddcc-385">Using PowerShell</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="fddcc-386">Установка и подключение к модулю Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="fddcc-386">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="fddcc-387">Пошаговые инструкции можно найти в статье [Установка оболочки PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="fddcc-387">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-package-to-a-group-of-users"></a><span data-ttu-id="fddcc-388">Назначение пакета политики группе пользователей</span><span class="sxs-lookup"><span data-stu-id="fddcc-388">Assign a policy package to a group of users</span></span>

<span data-ttu-id="fddcc-389">Командлет [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) можно использовать для назначения пакета политики группе.</span><span class="sxs-lookup"><span data-stu-id="fddcc-389">You use the [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet to assign a policy package to a group.</span></span> <span data-ttu-id="fddcc-390">Вы можете указать группу, используя идентификатор объекта, адрес SIP или адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="fddcc-390">You can specify a group by using the object Id, SIP address, or email address.</span></span> <span data-ttu-id="fddcc-391">Когда вы назначаете пакет политики, укажите [ранжирование назначения группы](#group-assignment-ranking) для каждого типа политики в пакете политики.</span><span class="sxs-lookup"><span data-stu-id="fddcc-391">When you assign the policy package, specify a [group assignment ranking](#group-assignment-ranking) for each policy type in the policy package.</span></span> 

<span data-ttu-id="fddcc-392">В этом примере мы назначаем пакету политики Education_Teacher группе с рейтингом назначения 1 для TeamsAppSetupPolicy и TeamsMeetingBroadcastPolicy и рейтингом 2 для TeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="fddcc-392">In this example, we assign the Education_Teacher policy package to a group with an assignment ranking of 1 for TeamsAppSetupPolicy and TeamsMeetingBroadcastPolicy and a ranking of 2 for TeamsMeetingPolicy.</span></span>

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="fddcc-393">Назначение пакета политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="fddcc-393">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="fddcc-394">С помощью задания пакетной политики можно назначить пакету политики большим наборам пользователей за один раз без использования сценария.</span><span class="sxs-lookup"><span data-stu-id="fddcc-394">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="fddcc-395">С помощью командлета [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) вы можете отправить пакет пользователей и пакет политики, который вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="fddcc-395">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="fddcc-396">Задания будут обрабатываться в фоновом режиме, а для каждого пакета будет создан идентификатор операции.</span><span class="sxs-lookup"><span data-stu-id="fddcc-396">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="fddcc-397">Затем вы можете использовать командлет [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) для отслеживания хода выполнения и состояния заданий в пакете.</span><span class="sxs-lookup"><span data-stu-id="fddcc-397">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="fddcc-398">Вы можете указать пользователей по идентификатору объекта или по протоколу SIP.</span><span class="sxs-lookup"><span data-stu-id="fddcc-398">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="fddcc-399">Обратите внимание, что адрес SIP пользователя часто имеет то же значение, что и имя участника-пользователя (UPN) или адрес электронной почты, но это не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="fddcc-399">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="fddcc-400">Если пользователь указан с использованием имени участника-пользователя или почтового сообщения, но его значение отличается от адреса SIP, для пользователя не будет установлено назначение политики.</span><span class="sxs-lookup"><span data-stu-id="fddcc-400">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="fddcc-401">Если пакет включает повторяющиеся пользователи, дубликаты удаляются из пакета перед обработкой и состоянием будут предоставляться только для уникальных пользователей, остающихся в пакете.</span><span class="sxs-lookup"><span data-stu-id="fddcc-401">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="fddcc-402">Пакет может содержать до 5 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="fddcc-402">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="fddcc-403">Для достижения наилучших результатов не отправляйте более нескольких пакетов одновременно.</span><span class="sxs-lookup"><span data-stu-id="fddcc-403">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="fddcc-404">Разрешите пакетам завершить обработку перед отправкой пакетов.</span><span class="sxs-lookup"><span data-stu-id="fddcc-404">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="fddcc-405">Установка и подключение к модулю Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="fddcc-405">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="fddcc-406">Выполните указанные ниже действия, чтобы установить [модуль Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (если вы еще этого не сделали).</span><span class="sxs-lookup"><span data-stu-id="fddcc-406">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="fddcc-407">Убедитесь, что вы установили версию 1.0.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="fddcc-407">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="fddcc-408">Выполните указанные ниже действия, чтобы подключиться к Teams и начать сеанс.</span><span class="sxs-lookup"><span data-stu-id="fddcc-408">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="fddcc-409">Когда вам будет предложено, войдите в систему с помощью учетных данных администратора.</span><span class="sxs-lookup"><span data-stu-id="fddcc-409">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="fddcc-410">Назначение пакета политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="fddcc-410">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="fddcc-411">В этом примере мы используем командлет [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) для назначения пакета политики Education_PrimaryStudent пакету пользователей.</span><span class="sxs-lookup"><span data-stu-id="fddcc-411">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="fddcc-412">Получение статуса задания пакетной обработки</span><span class="sxs-lookup"><span data-stu-id="fddcc-412">Get the status of a batch assignment</span></span>

<span data-ttu-id="fddcc-413">Выполните указанные ниже действия, чтобы получить сведения о состоянии задания пакета, где идентификатор операции — это значение, возвращаемое ```New-CsBatchPolicyAssignmentOperation``` командлетом для данного пакета.</span><span class="sxs-lookup"><span data-stu-id="fddcc-413">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="fddcc-414">Если в выходных данных показано, что произошла ошибка, выполните указанные ниже действия, чтобы получить дополнительные сведения об ошибках, которые находятся в ```UserState``` свойстве.</span><span class="sxs-lookup"><span data-stu-id="fddcc-414">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="fddcc-415">Дополнительные сведения можно найти в [статьях Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="fddcc-415">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="fddcc-416">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="fddcc-416">Related topics</span></span>

[<span data-ttu-id="fddcc-417">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="fddcc-417">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
