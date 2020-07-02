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
ms.openlocfilehash: c7522bc4bffeafeef4d194f5e4ad24ec9648a91a
ms.sourcegitcommit: 4099da7b1db7663e63ef5bece16e3090c33ea207
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "45021757"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="da5ed-103">Назначение политик вашим пользователям в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="da5ed-103">Assign policies to your users in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="da5ed-104">**Обратите внимание на одну из описанных в этой статье функций и назначение политики группам**.</span><span class="sxs-lookup"><span data-stu-id="da5ed-104">**Note the following about one of the features discussed in this article, policy assignment to groups**:</span></span> 
> - <span data-ttu-id="da5ed-105">[Назначение политики для групп, использующих центр администрирования Microsoft Teams](#using-the-microsoft-teams-admin-center-3), пока не выпущено.</span><span class="sxs-lookup"><span data-stu-id="da5ed-105">[Policy assignment to groups using the Microsoft Teams admin center](#using-the-microsoft-teams-admin-center-3), hasn't yet been released.</span></span> <span data-ttu-id="da5ed-106">Она была объявлена, и вскоре она скоро появится.</span><span class="sxs-lookup"><span data-stu-id="da5ed-106">It's been announced, and it's coming soon.</span></span> 
> - <span data-ttu-id="da5ed-107">[Назначение политики для групп с помощью PowerShell](#using-powershell-3)в настоящее время доступно только в частном предварительном просмотре.</span><span class="sxs-lookup"><span data-stu-id="da5ed-107">[Policy assignment to groups using PowerShell](#using-powershell-3), is currently only available in private preview.</span></span> <span data-ttu-id="da5ed-108">Командлеты для этой функции находятся в общедоступном модуле предварительного просмотра Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="da5ed-108">The cmdlets for this feature are in the Teams PowerShell public preview module.</span></span>
>
> <span data-ttu-id="da5ed-109">Чтобы не отвлекаться от состояния выпусков этой функции, ознакомьтесь с [планом Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185).</span><span class="sxs-lookup"><span data-stu-id="da5ed-109">To stay on top of the release status of this feature, check out the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185).</span></span>

<span data-ttu-id="da5ed-110">Администраторы используют политики для управления возможностями Teams, доступными для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="da5ed-110">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="da5ed-111">Например, вы можете присвоить имя только некоторые политики, политики собраний и политики обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="da5ed-111">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="da5ed-112">Организации имеют различные типы пользователей с уникальными потребностями, пользовательские политики, созданные и назначаемые, позволяют настраивать параметры политики для разных наборов пользователей на основе этих нужд.</span><span class="sxs-lookup"><span data-stu-id="da5ed-112">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="da5ed-113">Для упрощения управления политиками в Организации Teams предлагается несколько способов назначения политик пользователям.</span><span class="sxs-lookup"><span data-stu-id="da5ed-113">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="da5ed-114">Политику можно назначить непосредственно пользователям, как по отдельности, так и по масштабу в рамках задания или в группу, в которую входят пользователи.</span><span class="sxs-lookup"><span data-stu-id="da5ed-114">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="da5ed-115">Вы также можете использовать пакеты политик, чтобы назначить набор политик для пользователей в Организации, у которых есть похожие роли.</span><span class="sxs-lookup"><span data-stu-id="da5ed-115">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="da5ed-116">Выбор параметра зависит от количества политик, которые вы управляете, и количества пользователей, которым вы назначаете.</span><span class="sxs-lookup"><span data-stu-id="da5ed-116">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span> <span data-ttu-id="da5ed-117">Настроив глобальные политики (параметры по умолчанию на уровне Организации) таким образом, чтобы они применялись к максимальному количеству пользователей в Организации, вам нужно будет назначать политики только тем пользователям, которым требуются специализированные политики.</span><span class="sxs-lookup"><span data-stu-id="da5ed-117">By setting the global (Org-wide default) policies so that they apply to the largest number of users in your organization, you only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="da5ed-118">В этой статье описаны различные способы назначения политик пользователям и рекомендуемые сценарии для того, когда следует использовать эту возможность.</span><span class="sxs-lookup"><span data-stu-id="da5ed-118">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="da5ed-119">Какая политика имеет приоритет?</span><span class="sxs-lookup"><span data-stu-id="da5ed-119">Which policy takes precedence?</span></span>

<span data-ttu-id="da5ed-120">У пользователя есть одна действующая политика для каждого типа политики.</span><span class="sxs-lookup"><span data-stu-id="da5ed-120">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="da5ed-121">Возможно или даже, что пользователю явно назначена политика, и он также является членом одной или нескольких групп, которым назначена политика того же типа.</span><span class="sxs-lookup"><span data-stu-id="da5ed-121">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="da5ed-122">В сценариях такого типа приоритет имеет политика.</span><span class="sxs-lookup"><span data-stu-id="da5ed-122">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="da5ed-123">Действующая политика пользователя определяется в соответствии с правилами приоритета, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="da5ed-123">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="da5ed-124">Если пользователю назначена политика (отдельно или по назначению), она имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="da5ed-124">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="da5ed-125">В приведенном ниже примере действующая политика пользователя — это Lincoln квадратная политика для собраний, которая непосредственно назначается пользователю.</span><span class="sxs-lookup"><span data-stu-id="da5ed-125">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![Схема, показывающая, как имеет приоритет более прямую назначенную политику](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="da5ed-127">Если пользователь не назначил политике определенного типа, политика, назначенная группе, членом которой является пользователь, имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="da5ed-127">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="da5ed-128">Если пользователь является членом нескольких групп, политика, имеющая наивысший [рейтинг назначения группы](#group-assignment-ranking) для данного типа политики, имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="da5ed-128">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="da5ed-129">В этом примере действующая политика пользователя — это политика Exec Teams и HD, которая имеет наивысший рейтинг назначения относительно других групп, участником которых является этот пользователь, и которым также назначена политика того же типа политики.</span><span class="sxs-lookup"><span data-stu-id="da5ed-129">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![Схема, на которой показано, как действует политика, унаследованная от группы](media/assign-policies-example-group.png)

<span data-ttu-id="da5ed-131">Если пользователь не назначил политику или не является участником ни одной из групп, которым назначена политика, пользователь получает глобальную политику (по умолчанию для всей организации) для этого типа политики.</span><span class="sxs-lookup"><span data-stu-id="da5ed-131">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="da5ed-132">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="da5ed-132">Here's an example.</span></span>

![Схема, показывающая, как Глобальная политика имеет приоритет](media/assign-policies-example-global.png)

<span data-ttu-id="da5ed-134">Дополнительные сведения можно найти в разделе [правила приоритета](#precedence-rules).</span><span class="sxs-lookup"><span data-stu-id="da5ed-134">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="da5ed-135">Способы назначения политик</span><span class="sxs-lookup"><span data-stu-id="da5ed-135">Ways to assign policies</span></span>

<span data-ttu-id="da5ed-136">Ниже приведены общие сведения о способах назначения политик пользователям и рекомендуемых сценариях для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="da5ed-136">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="da5ed-137">Чтобы получить дополнительные сведения, щелкните ссылки.</span><span class="sxs-lookup"><span data-stu-id="da5ed-137">Click the links to learn more.</span></span>

<span data-ttu-id="da5ed-138">Прежде чем назначать политики отдельным пользователям или группам, начните с [настройки глобальных политик (по умолчанию в масштабах организации)](#set-the-global-policies) , чтобы они применялись к максимальному числу пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="da5ed-138">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="da5ed-139">После настройки глобальных политик вам потребуется назначать политики только тем пользователям, которым требуются специализированные политики.</span><span class="sxs-lookup"><span data-stu-id="da5ed-139">Once the global policies are set, you will only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="da5ed-140">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="da5ed-140">Do this</span></span>  |<span data-ttu-id="da5ed-141">Если...</span><span class="sxs-lookup"><span data-stu-id="da5ed-141">If...</span></span>  | <span data-ttu-id="da5ed-142">Использование...</span><span class="sxs-lookup"><span data-stu-id="da5ed-142">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="da5ed-143">Назначение политики отдельным пользователям</span><span class="sxs-lookup"><span data-stu-id="da5ed-143">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="da5ed-144">Вы не знакомы с Teams и просто приступите к работе или вам нужно назначить одну или несколько политик небольшим числам пользователей.</span><span class="sxs-lookup"><span data-stu-id="da5ed-144">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="da5ed-145">Центр администрирования Microsoft Teams или командлеты PowerShell в модуле PowerShell Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="da5ed-145">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
| [<span data-ttu-id="da5ed-146">Назначение пакета политики</span><span class="sxs-lookup"><span data-stu-id="da5ed-146">Assign a policy package</span></span>](#assign-a-policy-package)   | <span data-ttu-id="da5ed-147">Необходимо назначить несколько политик определенным наборам пользователей организации, которые имеют одинаковые или аналогичные роли.</span><span class="sxs-lookup"><span data-stu-id="da5ed-147">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="da5ed-148">Например, назначьте в учебном заведении пакет политики образования для преподавателей, чтобы предоставить им полный доступ к беседам, звонку, собраниям и пакету политики образования (дополнительный учебный учащийся), чтобы ограничить некоторые возможности, такие как частный звонок.</span><span class="sxs-lookup"><span data-stu-id="da5ed-148">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="da5ed-149">Центр администрирования Microsoft Teams или командлеты PowerShell из модуля Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="da5ed-149">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="da5ed-150">Назначение политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="da5ed-150">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="da5ed-151">Вы должны назначать политики большим наборам пользователей.</span><span class="sxs-lookup"><span data-stu-id="da5ed-151">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="da5ed-152">Например, вы хотите назначить политику для сотен или тысяч пользователей в Организации одновременно.</span><span class="sxs-lookup"><span data-stu-id="da5ed-152">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="da5ed-153">Центр администрирования Microsoft Teams или командлеты PowerShell из модуля Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="da5ed-153">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|<span data-ttu-id="da5ed-154">[Назначение политики группе](#assign-a-policy-to-a-group) (в предварительной версии и на скором)</span><span class="sxs-lookup"><span data-stu-id="da5ed-154">[Assign a policy to a group](#assign-a-policy-to-a-group) (in preview/coming soon)</span></span>|<span data-ttu-id="da5ed-155">Необходимо назначить политики, основанные на членстве в группе пользователя.</span><span class="sxs-lookup"><span data-stu-id="da5ed-155">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="da5ed-156">Например, вы хотите назначить политику для всех пользователей в группе безопасности или подразделении.</span><span class="sxs-lookup"><span data-stu-id="da5ed-156">For example, you want to assign a policy to all users in a security group or organizational unit.</span></span>| <span data-ttu-id="da5ed-157">Центр администрирования Microsoft Teams (ожидается в ближайшее время) или командлеты PowerShell из модуля Teams PowerShell (в предварительной версии)</span><span class="sxs-lookup"><span data-stu-id="da5ed-157">The Microsoft Teams admin center (coming soon) or PowerShell cmdlets in the Teams PowerShell module (in preview)</span></span>|
| [<span data-ttu-id="da5ed-158">Назначение пакета политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="da5ed-158">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="da5ed-159">Необходимо назначить несколько политик для пакета пользователей в Организации с одинаковыми или аналогичными ролями.</span><span class="sxs-lookup"><span data-stu-id="da5ed-159">You need to assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="da5ed-160">Например, вы можете назначить пакету политики образования для всех преподавателей в учебном заведении с помощью пакетного задания, чтобы предоставить им полный доступ к разговорам, звонкам и собраниям, а также назначить пакету политики образования (дополнительный учебный учащийся) пакету вспомогательных учащихся, чтобы ограничить некоторые возможности, такие как частный звонок.</span><span class="sxs-lookup"><span data-stu-id="da5ed-160">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings and assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities like private calling.</span></span>|<span data-ttu-id="da5ed-161">Командлеты PowerShell в модуле PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="da5ed-161">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="da5ed-162">Назначение пакета политики группе (ожидается в ближайшее время)</span><span class="sxs-lookup"><span data-stu-id="da5ed-162">Assign a policy package to a group (coming soon)</span></span>   | ||

## <a name="set-the-global-policies"></a><span data-ttu-id="da5ed-163">Настройка глобальных политик</span><span class="sxs-lookup"><span data-stu-id="da5ed-163">Set the global policies</span></span>

<span data-ttu-id="da5ed-164">Выполните указанные ниже действия, чтобы настроить глобальные политики (параметры по умолчанию для всей организации) для каждого типа политики.</span><span class="sxs-lookup"><span data-stu-id="da5ed-164">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="da5ed-165">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="da5ed-165">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="da5ed-166">В левой области навигации центра администрирования Microsoft Teams перейдите на страницу политики для типа политики, которую вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="da5ed-166">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="da5ed-167">Например, политики **Teams**  >  **Teams**, политики собраний по **собраниям**,  >  **Meetings policies** **политики обмена сообщениями**и политики **голосовой связи**  >  **Calling policies**.</span><span class="sxs-lookup"><span data-stu-id="da5ed-167">For example, **Teams** > **Teams policies**, **Meetings** > **Meetings policies**, **Messaging policies**, or **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="da5ed-168">Выберите **глобальную политику (по умолчанию на уровне Организации)** для просмотра текущих параметров.</span><span class="sxs-lookup"><span data-stu-id="da5ed-168">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="da5ed-169">При необходимости обновите политику и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="da5ed-169">Update the policy as needed, and then select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="da5ed-170">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="da5ed-170">Using PowerShell</span></span>

<span data-ttu-id="da5ed-171">Чтобы настроить глобальные политики с помощью PowerShell, используйте глобальный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="da5ed-171">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="da5ed-172">Сначала просмотрите текущую глобальную политику, чтобы определить, какую настройку нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="da5ed-172">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

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

<span data-ttu-id="da5ed-173">Затем при необходимости обновите глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="da5ed-173">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="da5ed-174">Для параметров, которые вы хотите изменить, нужно указать только значения.</span><span class="sxs-lookup"><span data-stu-id="da5ed-174">You only need to specify values for the settings that you want to change.</span></span> 
 
```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="da5ed-175">Назначение политики отдельным пользователям</span><span class="sxs-lookup"><span data-stu-id="da5ed-175">Assign a policy to individual users</span></span>

<span data-ttu-id="da5ed-176">Выполните указанные ниже действия, чтобы назначить политику для отдельного пользователя или для небольшого количества пользователей за один раз.</span><span class="sxs-lookup"><span data-stu-id="da5ed-176">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="da5ed-177">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="da5ed-177">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="da5ed-178">Чтобы назначить пользователю политику, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="da5ed-178">To assign a policy to a user:</span></span>

1. <span data-ttu-id="da5ed-179">В Центре администрирования Microsoft Teams в области навигации слева перейдите в раздел **Пользователи**, затем щелкните пользователя.</span><span class="sxs-lookup"><span data-stu-id="da5ed-179">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="da5ed-180">Выберите пользователя, щелкнув слева от его имени, затем нажмите кнопку **Изменить параметры**.</span><span class="sxs-lookup"><span data-stu-id="da5ed-180">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="da5ed-181">Выберите политику, которую вы хотите назначить, и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="da5ed-181">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="da5ed-182">Кроме того, вы можете сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="da5ed-182">Or, you can also do the following:</span></span>

1. <span data-ttu-id="da5ed-183">В левой области навигации центра администрирования Microsoft Teams перейдите на страницу "политика".</span><span class="sxs-lookup"><span data-stu-id="da5ed-183">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="da5ed-184">Выберите политику, которую вы хотите назначить, щелкнув слева от ее имени.</span><span class="sxs-lookup"><span data-stu-id="da5ed-184">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="da5ed-185">Выберите **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="da5ed-185">Select **Manage users**.</span></span>
4. <span data-ttu-id="da5ed-186">В области **Управление пользователями** выполните поиск по отображаемому имени или по имени пользователя, выберите имя и нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="da5ed-186">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="da5ed-187">Повторите это действие для каждого пользователя, которого нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="da5ed-187">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="da5ed-188">Завершив добавление пользователей, нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="da5ed-188">When you're finished adding users, select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="da5ed-189">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="da5ed-189">Using PowerShell</span></span>

<span data-ttu-id="da5ed-190">У каждого типа политики есть собственный набор командлетов для управления ею.</span><span class="sxs-lookup"><span data-stu-id="da5ed-190">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="da5ed-191">Используйте ```Grant-``` командлет для определенного типа политики, чтобы назначить политику.</span><span class="sxs-lookup"><span data-stu-id="da5ed-191">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="da5ed-192">Например, ```Grant-CsTeamsMeetingPolicy``` можно использовать командлет для назначения пользователям политики собрания Teams.</span><span class="sxs-lookup"><span data-stu-id="da5ed-192">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="da5ed-193">Эти командлеты включены в модуль PowerShell Skype для бизнеса Online и описаны в [справочной документации по командлетам Skype для бизнеса](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="da5ed-193">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="da5ed-194">Скачайте и установите [модуль PowerShell Skype для бизнеса Online](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (если вы еще этого не сделали), а затем выполните указанные ниже действия, чтобы подключиться к Skype для бизнеса Online и начать сеанс.</span><span class="sxs-lookup"><span data-stu-id="da5ed-194">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="da5ed-195">В этом примере мы назначаем политику собраний Teams, которая называется политикой собраний учащихся, пользователю с именем Reda.</span><span class="sxs-lookup"><span data-stu-id="da5ed-195">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="da5ed-196">Дополнительные сведения можно найти в статье [Управление политиками с помощью PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span><span class="sxs-lookup"><span data-stu-id="da5ed-196">To learn more, read [Managing policies via PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

## <a name="assign-a-policy-package"></a><span data-ttu-id="da5ed-197">Назначение пакета политики</span><span class="sxs-lookup"><span data-stu-id="da5ed-197">Assign a policy package</span></span>

<span data-ttu-id="da5ed-198">Пакет политики в Teams — это набор предопределенных политик и параметров политики, которые можно назначить пользователям, имеющим такие же или аналогичные роли в Организации.</span><span class="sxs-lookup"><span data-stu-id="da5ed-198">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="da5ed-199">Каждый пакет политики разработан вокруг роли пользователя и включает стандартные политики и параметры политики, которые поддерживают действия, характерные для этой роли.</span><span class="sxs-lookup"><span data-stu-id="da5ed-199">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="da5ed-200">Некоторые примеры пакетов политики — это пакет для образования (преподаватель) и Здравоохранение (Clinical Worker).</span><span class="sxs-lookup"><span data-stu-id="da5ed-200">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span>

<span data-ttu-id="da5ed-201">Когда вы назначаете пакету политики пользователям, будут созданы политики в пакете, и вы сможете настраивать параметры каждой из них в пакете в соответствии с потребностями пользователей.</span><span class="sxs-lookup"><span data-stu-id="da5ed-201">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of each policy in the package to meet users' needs.</span></span>

<span data-ttu-id="da5ed-202">Дополнительные сведения о пакетах политик, включая пошаговые инструкции по их назначению и управлению, можно найти [в разделе Управление пакетами политики в Teams](manage-policy-packages.md).</span><span class="sxs-lookup"><span data-stu-id="da5ed-202">To learn more about policy packages, including step-by-step guidance on how to assign and manage them, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="da5ed-203">Назначение политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="da5ed-203">Assign a policy to a batch of users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="da5ed-204">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="da5ed-204">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="da5ed-205">Чтобы назначить политику для пользователей, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="da5ed-205">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="da5ed-206">В левой области навигации центра администрирования Microsoft Teams выберите пункт **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="da5ed-206">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="da5ed-207">Найдите пользователей, которым вы хотите назначить политику, или отфильтруйте представление, чтобы отобразить нужных пользователей.</span><span class="sxs-lookup"><span data-stu-id="da5ed-207">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="da5ed-208">В столбце **&#x2713;** (галочка) выберите пользователей.</span><span class="sxs-lookup"><span data-stu-id="da5ed-208">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="da5ed-209">Чтобы выбрать всех пользователей, щелкните &#x2713; (галочку) в верхней части таблицы.</span><span class="sxs-lookup"><span data-stu-id="da5ed-209">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="da5ed-210">Щелкните **Изменить настройки**, внесите нужные изменения и нажмите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="da5ed-210">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="da5ed-211">Чтобы просмотреть состояние назначения политики, в заголовке, который появляется в верхней части страницы **пользователей** после нажатия кнопки **Применить** для отправки назначения политики, щелкните **Журнал активности**.</span><span class="sxs-lookup"><span data-stu-id="da5ed-211">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you click **Apply** to submit your policy assignment, click **Activity log**.</span></span> <span data-ttu-id="da5ed-212">Либо в левой области навигации центра администрирования Microsoft Teams перейдите на **панель мониторинга**, а затем в разделе **Журнал активности**щелкните **Просмотреть сведения**.</span><span class="sxs-lookup"><span data-stu-id="da5ed-212">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, click **View details**.</span></span> <span data-ttu-id="da5ed-213">Журнал активности показывает назначения политики для пакетов более чем из 20 пользователей в центре администрирования Microsoft Teams за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="da5ed-213">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="da5ed-214">Дополнительные сведения можно найти [в статье Просмотр назначенных политик в журнале событий](activity-log.md).</span><span class="sxs-lookup"><span data-stu-id="da5ed-214">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="da5ed-215">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="da5ed-215">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="da5ed-216">В настоящее время назначение пакетной политики с помощью PowerShell недоступно для всех типов политики Teams.</span><span class="sxs-lookup"><span data-stu-id="da5ed-216">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="da5ed-217">Ознакомьтесь со списком " [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) " для списка поддерживаемых типов политики.</span><span class="sxs-lookup"><span data-stu-id="da5ed-217">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>
 
<span data-ttu-id="da5ed-218">С помощью назначения пакетной политики вы можете назначить политику большим наборам пользователей за один раз, не прибегая к использованию сценария.</span><span class="sxs-lookup"><span data-stu-id="da5ed-218">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="da5ed-219">```New-CsBatchPolicyAssignmentOperation```С помощью командлета вы можете отправить пакет пользователей и политику, которую вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="da5ed-219">You use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="da5ed-220">Назначения обрабатываются как фоновая операция, и для каждого пакета создается идентификатор операции.</span><span class="sxs-lookup"><span data-stu-id="da5ed-220">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="da5ed-221">Затем вы можете использовать этот ```Get-CsBatchPolicyAssignmentOperation``` командлет для отслеживания хода выполнения и состояния заданий в пакете.</span><span class="sxs-lookup"><span data-stu-id="da5ed-221">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="da5ed-222">Вы можете указать пользователей по идентификатору объекта или по протоколу SIP.</span><span class="sxs-lookup"><span data-stu-id="da5ed-222">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="da5ed-223">Обратите внимание, что адрес SIP пользователя часто имеет то же значение, что и имя участника-пользователя (UPN) или адрес электронной почты, но это не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="da5ed-223">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="da5ed-224">Если пользователь указан с использованием имени участника-пользователя или почтового сообщения, но его значение отличается от адреса SIP, для пользователя не будет установлено назначение политики.</span><span class="sxs-lookup"><span data-stu-id="da5ed-224">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="da5ed-225">Если пакет включает повторяющиеся пользователи, дубликаты удаляются из пакета перед обработкой и состоянием будут предоставляться только для уникальных пользователей, остающихся в пакете.</span><span class="sxs-lookup"><span data-stu-id="da5ed-225">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="da5ed-226">Пакет может содержать до 5 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="da5ed-226">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="da5ed-227">Для достижения наилучших результатов не отправляйте более нескольких пакетов одновременно.</span><span class="sxs-lookup"><span data-stu-id="da5ed-227">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="da5ed-228">Разрешите пакетам завершить обработку перед отправкой пакетов.</span><span class="sxs-lookup"><span data-stu-id="da5ed-228">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="da5ed-229">Установка и подключение к модулю Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="da5ed-229">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="da5ed-230">Выполните указанные ниже действия, чтобы установить [модуль PowerShell Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams).</span><span class="sxs-lookup"><span data-stu-id="da5ed-230">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="da5ed-231">Убедитесь, что вы установили версию 1.0.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="da5ed-231">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="da5ed-232">Выполните указанные ниже действия, чтобы подключиться к Teams и начать сеанс.</span><span class="sxs-lookup"><span data-stu-id="da5ed-232">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="da5ed-233">Когда вам будет предложено, войдите в систему с помощью учетных данных администратора.</span><span class="sxs-lookup"><span data-stu-id="da5ed-233">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="da5ed-234">Установка и подключение к модулю Azure AD PowerShell для Graph (необязательно)</span><span class="sxs-lookup"><span data-stu-id="da5ed-234">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="da5ed-235">Кроме того, вам может потребоваться [загрузить и установить модуль Azure AD PowerShell для Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (если вы еще не сделали этого) и подключиться к Azure AD, чтобы получить список пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="da5ed-235">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="da5ed-236">Выполните указанные ниже действия, чтобы подключиться к Azure AD.</span><span class="sxs-lookup"><span data-stu-id="da5ed-236">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="da5ed-237">Когда вам будет предложено, войдите в систему с помощью учетных данных администратора, используемых для подключения к Teams.</span><span class="sxs-lookup"><span data-stu-id="da5ed-237">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="da5ed-238">Назначение политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="da5ed-238">Assign a policy to a batch of users</span></span>

<span data-ttu-id="da5ed-239">В этом примере мы используем командлет, ```New-CsBatchPolicyAssignmentOperation``` чтобы назначить политику настройки приложения с именем "Политика настройки приложения" для пакета пользователей, перечисленных в файле Users_ids. Text.</span><span class="sxs-lookup"><span data-stu-id="da5ed-239">In this example, we use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="da5ed-240">В этом примере мы подключаем подключение к Azure AD, чтобы получить доступ к коллекции пользователей, а затем назначить политику сообщений с именем "Новая политика для приема на работу" для пакета пользователей, указанного с помощью их SIP-адресов.</span><span class="sxs-lookup"><span data-stu-id="da5ed-240">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

<span data-ttu-id="da5ed-241">Дополнительные сведения можно найти в статье [Создание и CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="da5ed-241">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="da5ed-242">Получение статуса задания пакетной обработки</span><span class="sxs-lookup"><span data-stu-id="da5ed-242">Get the status of a batch assignment</span></span>

<span data-ttu-id="da5ed-243">Выполните указанные ниже действия, чтобы получить сведения о состоянии задания пакета, где идентификатор операции — это значение, возвращаемое ```New-CsBatchPolicyAssignmentOperation``` командлетом для данного пакета.</span><span class="sxs-lookup"><span data-stu-id="da5ed-243">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="da5ed-244">Если в выходных данных показано, что произошла ошибка, выполните указанные ниже действия, чтобы получить дополнительные сведения об ошибках, которые находятся в ```UserState``` свойстве.</span><span class="sxs-lookup"><span data-stu-id="da5ed-244">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="da5ed-245">Дополнительные сведения можно найти в [статьях Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="da5ed-245">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="da5ed-246">Назначение политики группе</span><span class="sxs-lookup"><span data-stu-id="da5ed-246">Assign a policy to a group</span></span>

<span data-ttu-id="da5ed-247">Назначение политики для групп позволяет назначить политику группе пользователей, например группе безопасности или подразделению.</span><span class="sxs-lookup"><span data-stu-id="da5ed-247">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or organizational unit.</span></span> <span data-ttu-id="da5ed-248">Назначение политики распространяется на пользователей группы в соответствии с правилами приоритета.</span><span class="sxs-lookup"><span data-stu-id="da5ed-248">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="da5ed-249">Когда участники добавляются в группу или удаляются из нее, их унаследованные назначения политик обновляются соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="da5ed-249">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="da5ed-250">Назначение политики для групп рекомендовано для групп до 50 000 пользователей, но оно также работает с более крупными группами.</span><span class="sxs-lookup"><span data-stu-id="da5ed-250">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="da5ed-251">После назначения политики она немедленно назначается группе.</span><span class="sxs-lookup"><span data-stu-id="da5ed-251">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="da5ed-252">Однако обратите внимание, что распространение назначения политики для участников группы выполняется в фоновом режиме и может занять некоторое время, в зависимости от размера группы.</span><span class="sxs-lookup"><span data-stu-id="da5ed-252">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="da5ed-253">Это справедливо, если политика не назначена группе, а также при добавлении пользователей в группу или удалении ее из нее.</span><span class="sxs-lookup"><span data-stu-id="da5ed-253">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="da5ed-254">Что необходимо знать о назначении политики группам</span><span class="sxs-lookup"><span data-stu-id="da5ed-254">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="da5ed-255">Прежде чем приступить к работе, важно понимать правила приоритета и ранжирование назначения групп.</span><span class="sxs-lookup"><span data-stu-id="da5ed-255">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="da5ed-256">Правила приоритета</span><span class="sxs-lookup"><span data-stu-id="da5ed-256">Precedence rules</span></span>

<span data-ttu-id="da5ed-257">Для определенного типа политики действующая политика пользователя определяется в соответствии с приведенными ниже сведениями.</span><span class="sxs-lookup"><span data-stu-id="da5ed-257">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="da5ed-258">Политика, непосредственно назначенная пользователю, имеет приоритет над любыми другими политиками того же типа, которые назначены группе.</span><span class="sxs-lookup"><span data-stu-id="da5ed-258">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="da5ed-259">Другими словами, если пользователю явно назначена политика определенного типа, этот пользователь не наследует политику того же типа из группы.</span><span class="sxs-lookup"><span data-stu-id="da5ed-259">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="da5ed-260">Это также означает, что если пользователь имеет политику, назначенную определенному типу, вы должны удалить ее от пользователя, прежде чем она сможет наследовать политику того же типа из группы.</span><span class="sxs-lookup"><span data-stu-id="da5ed-260">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="da5ed-261">Если пользователь не имеет назначенной им политики и является членом двух или более групп, а каждая группа имеет политику с таким же типом, пользователь наследует политику назначения группы, имеющую наивысший рейтинг.</span><span class="sxs-lookup"><span data-stu-id="da5ed-261">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="da5ed-262">Если пользователь не является членом ни одной из групп, которым назначена политика, для него применяется Глобальная политика (по умолчанию на уровне Организации) для этого типа политики.</span><span class="sxs-lookup"><span data-stu-id="da5ed-262">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="da5ed-263">Действующая политика пользователя обновляется согласно этим правилам, когда пользователь добавляется или удаляется из группы, которой назначена политика, политика не назначается группе, или политика, непосредственно назначенная пользователю, удаляется.</span><span class="sxs-lookup"><span data-stu-id="da5ed-263">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="da5ed-264">Ранжирование назначения групп</span><span class="sxs-lookup"><span data-stu-id="da5ed-264">Group assignment ranking</span></span>
 
<span data-ttu-id="da5ed-265">Когда вы назначаете группе политику, вы указываете рейтинг для назначения группы.</span><span class="sxs-lookup"><span data-stu-id="da5ed-265">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="da5ed-266">Этот параметр используется для определения политики, которую пользователь должен наследовать в качестве действующей политики, если пользователь является членом двух или более групп, и каждой группе назначена политика одного и того же типа.</span><span class="sxs-lookup"><span data-stu-id="da5ed-266">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="da5ed-267">Ранжирование назначения групп определяется относительно других назначений групп того же типа.</span><span class="sxs-lookup"><span data-stu-id="da5ed-267">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="da5ed-268">Например, если вы назначаете политику вызовов двум группам, задайте для ранжирования одного задания значение 1, а для другого — 2, где 1 — наивысший рейтинг.</span><span class="sxs-lookup"><span data-stu-id="da5ed-268">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="da5ed-269">Ранжирование назначения групп указывает на то, что участие в группах является более важным или более релевантным по сравнению с наследованием в других группах.</span><span class="sxs-lookup"><span data-stu-id="da5ed-269">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="da5ed-270">Например, предположим, что у вас есть две группы, магазин сотрудников и руководителей магазина.</span><span class="sxs-lookup"><span data-stu-id="da5ed-270">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="da5ed-271">Обеим группам назначается политика вызова Teams, в котором хранятся политики вызова для сотрудников и политики звонков руководителей магазина соответственно.</span><span class="sxs-lookup"><span data-stu-id="da5ed-271">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="da5ed-272">Для руководителя магазина, который находится в обеих группах, роль руководителя больше важна, чем роль сотрудника, поэтому политика звонков, назначенная группе руководителей магазина, должна иметь более высокий рейтинг.</span><span class="sxs-lookup"><span data-stu-id="da5ed-272">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="da5ed-273">Сгруппирован</span><span class="sxs-lookup"><span data-stu-id="da5ed-273">Group</span></span> |<span data-ttu-id="da5ed-274">Имя политики вызова Teams</span><span class="sxs-lookup"><span data-stu-id="da5ed-274">Teams calling policy name</span></span>  |<span data-ttu-id="da5ed-275">Rank (Ранг)</span><span class="sxs-lookup"><span data-stu-id="da5ed-275">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="da5ed-276">Руководители магазина</span><span class="sxs-lookup"><span data-stu-id="da5ed-276">Store Managers</span></span>   |<span data-ttu-id="da5ed-277">Политика звонков руководителей магазина</span><span class="sxs-lookup"><span data-stu-id="da5ed-277">Store Managers Calling Policy</span></span>         |<span data-ttu-id="da5ed-278">1</span><span class="sxs-lookup"><span data-stu-id="da5ed-278">1</span></span>|
|<span data-ttu-id="da5ed-279">Магазин сотрудников</span><span class="sxs-lookup"><span data-stu-id="da5ed-279">Store Employees</span></span>    |<span data-ttu-id="da5ed-280">Хранение политики звонка для сотрудников</span><span class="sxs-lookup"><span data-stu-id="da5ed-280">Store Employees Calling Policy</span></span>      |<span data-ttu-id="da5ed-281">2</span><span class="sxs-lookup"><span data-stu-id="da5ed-281">2</span></span>|

<span data-ttu-id="da5ed-282">Если вы не укажете ранжирование, для назначения политики будет задан самый низкий рейтинг.</span><span class="sxs-lookup"><span data-stu-id="da5ed-282">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="da5ed-283">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="da5ed-283">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="da5ed-284">**Эта функция еще не выпущена. Она была объявлена, и вскоре она скоро появится.**</span><span class="sxs-lookup"><span data-stu-id="da5ed-284">**This feature hasn't yet been released. It's been announced, and it's coming soon.**</span></span>

> [!NOTE]
> <span data-ttu-id="da5ed-285">В настоящее время назначение политики для групп, использующих центр администрирования Microsoft Teams, доступно только для политики вызова Teams, политики собрания Teams и политики обмена сообщениями в Teams.</span><span class="sxs-lookup"><span data-stu-id="da5ed-285">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="da5ed-286">Для других типов политик используйте PowerShell.</span><span class="sxs-lookup"><span data-stu-id="da5ed-286">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="da5ed-287">В левой области навигации центра администрирования Microsoft Teams перейдите на страницу тип политики.</span><span class="sxs-lookup"><span data-stu-id="da5ed-287">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="da5ed-288">Например, **перейдите к разделу**  >  **политики собраний по собраниям**.</span><span class="sxs-lookup"><span data-stu-id="da5ed-288">For example, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="da5ed-289">Перейдите на вкладку **назначение групповой политики** .</span><span class="sxs-lookup"><span data-stu-id="da5ed-289">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="da5ed-290">Нажмите кнопку **Добавить группу**, а затем в области **Назначение политики для группировки** выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="da5ed-290">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="da5ed-291">Найдите и добавьте группу, которой вы хотите назначить политику.</span><span class="sxs-lookup"><span data-stu-id="da5ed-291">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="da5ed-292">Задайте рейтинг для назначения групп.</span><span class="sxs-lookup"><span data-stu-id="da5ed-292">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="da5ed-293">Выберите политику, которую вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="da5ed-293">Select the policy that you want to assign.</span></span> 
    4. <span data-ttu-id="da5ed-294">Нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="da5ed-294">Select **Apply**.</span></span>

<span data-ttu-id="da5ed-295">Чтобы удалить назначение групповой политики, на вкладке **назначение групповой политики** на странице Политика выберите назначение группы и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="da5ed-295">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="da5ed-296">Чтобы изменить ранжирование назначения группы, необходимо сначала удалить назначение групповой политики.</span><span class="sxs-lookup"><span data-stu-id="da5ed-296">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="da5ed-297">Затем выполните описанные выше действия, чтобы назначить политику группе.</span><span class="sxs-lookup"><span data-stu-id="da5ed-297">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="da5ed-298">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="da5ed-298">Using PowerShell</span></span>

<span data-ttu-id="da5ed-299">**В настоящее время эта функция доступна только в частном предварительной версии. Командлеты для этой функции находятся в общедоступном модуле предварительного просмотра Teams PowerShell.**</span><span class="sxs-lookup"><span data-stu-id="da5ed-299">**This feature is currently only available in private preview. The cmdlets for this feature are in the Teams PowerShell public preview module.**</span></span>

> [!NOTE]
> <span data-ttu-id="da5ed-300">В настоящее время назначение политики для групп, использующих PowerShell, недоступно для всех типов политики Teams.</span><span class="sxs-lookup"><span data-stu-id="da5ed-300">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="da5ed-301">Ознакомьтесь со списком " [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) " для списка поддерживаемых типов политики.</span><span class="sxs-lookup"><span data-stu-id="da5ed-301">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="da5ed-302">Установка и подключение к модулю Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="da5ed-302">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="da5ed-303">Эти командлеты являются частью общедоступного модуля предварительного просмотра Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="da5ed-303">These cmdlets are part of the Teams PowerShell public preview module.</span></span> <span data-ttu-id="da5ed-304">Пошаговые инструкции по установке читайте в статье [Установка PowerShell Teams](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="da5ed-304">For step-by-step guidance, read [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="da5ed-305">Назначение политики группе</span><span class="sxs-lookup"><span data-stu-id="da5ed-305">Assign a policy to a group</span></span>

<span data-ttu-id="da5ed-306">С помощью ```New-CsGroupPolicyAssignment``` командлета вы можете назначить политику группе.</span><span class="sxs-lookup"><span data-stu-id="da5ed-306">You use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="da5ed-307">Вы можете указать группу, используя идентификатор объекта, адрес SIP или адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="da5ed-307">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="da5ed-308">В этом примере мы используем ```New-CsGroupPolicyAssignment``` командлет для назначения политики собрания Team Manager в группе с рейтингом назначения 1.</span><span class="sxs-lookup"><span data-stu-id="da5ed-308">In this example, we use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

<span data-ttu-id="da5ed-309">Дополнительные сведения можно найти в статье [Создание и CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="da5ed-309">To learn more, see [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span></span>

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="da5ed-310">Получение назначений политики для группы</span><span class="sxs-lookup"><span data-stu-id="da5ed-310">Get policy assignments for a group</span></span>

<span data-ttu-id="da5ed-311">Используйте ```Get-CsGroupPolicyAssignment``` командлет, чтобы получить все политики, назначенные группе.</span><span class="sxs-lookup"><span data-stu-id="da5ed-311">Use the ```Get-CsGroupPolicyAssignment``` cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="da5ed-312">Обратите внимание, что группы всегда записываются в соответствии с их идентификатором группы, даже если для назначения политики был использован адрес SIP или адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="da5ed-312">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="da5ed-313">В этом примере мы извлекаем все политики, назначенные определенной группе.</span><span class="sxs-lookup"><span data-stu-id="da5ed-313">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="da5ed-314">В этом примере мы возвращаем все группы, которым назначена политика для собрания Teams.</span><span class="sxs-lookup"><span data-stu-id="da5ed-314">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

<span data-ttu-id="da5ed-315">Дополнительные сведения можно найти в [статьях Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="da5ed-315">To learn more, see [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span></span>

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="da5ed-316">Удаление политики из группы</span><span class="sxs-lookup"><span data-stu-id="da5ed-316">Remove a policy from a group</span></span>

<span data-ttu-id="da5ed-317">Используйте ```Remove-CsGroupPolicyAssignment``` командлет для удаления политики из группы.</span><span class="sxs-lookup"><span data-stu-id="da5ed-317">Use the ```Remove-CsGroupPolicyAssignment``` cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="da5ed-318">При удалении политики из группы приоритеты других политик того же типа, которым назначена эта группа, и которые имеют более низкий рейтинг, будут обновлены.</span><span class="sxs-lookup"><span data-stu-id="da5ed-318">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="da5ed-319">Например, если вы удалите политику с рангом 2, то политики с рейтингом 3 и 4 будут обновляться в соответствии с их новым рейтингом.</span><span class="sxs-lookup"><span data-stu-id="da5ed-319">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="da5ed-320">Этот пример показан в двух приведенных ниже таблицах.</span><span class="sxs-lookup"><span data-stu-id="da5ed-320">The following two tables show this example.</span></span>

<span data-ttu-id="da5ed-321">Ниже приведен список назначений и приоритетов политики для собраний Teams.</span><span class="sxs-lookup"><span data-stu-id="da5ed-321">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="da5ed-322">Имя группы</span><span class="sxs-lookup"><span data-stu-id="da5ed-322">Group name</span></span>  |<span data-ttu-id="da5ed-323">Название политики</span><span class="sxs-lookup"><span data-stu-id="da5ed-323">Policy name</span></span>  |<span data-ttu-id="da5ed-324">Rank (Ранг)</span><span class="sxs-lookup"><span data-stu-id="da5ed-324">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="da5ed-325">Продажи</span><span class="sxs-lookup"><span data-stu-id="da5ed-325">Sales</span></span>    |<span data-ttu-id="da5ed-326">Политика продаж</span><span class="sxs-lookup"><span data-stu-id="da5ed-326">Sales policy</span></span>       | <span data-ttu-id="da5ed-327">1</span><span class="sxs-lookup"><span data-stu-id="da5ed-327">1</span></span>        |
|<span data-ttu-id="da5ed-328">Западная область</span><span class="sxs-lookup"><span data-stu-id="da5ed-328">West Region</span></span>     |<span data-ttu-id="da5ed-329">Политика "Западная область"</span><span class="sxs-lookup"><span data-stu-id="da5ed-329">West Region policy</span></span>         |<span data-ttu-id="da5ed-330">2</span><span class="sxs-lookup"><span data-stu-id="da5ed-330">2</span></span>         |
|<span data-ttu-id="da5ed-331">Умножен</span><span class="sxs-lookup"><span data-stu-id="da5ed-331">Division</span></span>    |<span data-ttu-id="da5ed-332">Политика деления</span><span class="sxs-lookup"><span data-stu-id="da5ed-332">Division policy</span></span>         |<span data-ttu-id="da5ed-333">3</span><span class="sxs-lookup"><span data-stu-id="da5ed-333">3</span></span>         |
|<span data-ttu-id="da5ed-334">Отделения</span><span class="sxs-lookup"><span data-stu-id="da5ed-334">Subsidiary</span></span>   |<span data-ttu-id="da5ed-335">Политика для дочерних компаний</span><span class="sxs-lookup"><span data-stu-id="da5ed-335">Subsidiary policy</span></span>        |<span data-ttu-id="da5ed-336">4</span><span class="sxs-lookup"><span data-stu-id="da5ed-336">4</span></span>         |

<span data-ttu-id="da5ed-337">Если удалить политику западных областей из группы Западная область, то назначения и приоритеты политики будут обновляться следующим образом.</span><span class="sxs-lookup"><span data-stu-id="da5ed-337">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="da5ed-338">Имя группы</span><span class="sxs-lookup"><span data-stu-id="da5ed-338">Group name</span></span>  |<span data-ttu-id="da5ed-339">Название политики</span><span class="sxs-lookup"><span data-stu-id="da5ed-339">Policy name</span></span>  |<span data-ttu-id="da5ed-340">Rank (Ранг)</span><span class="sxs-lookup"><span data-stu-id="da5ed-340">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="da5ed-341">Продажи</span><span class="sxs-lookup"><span data-stu-id="da5ed-341">Sales</span></span>    |<span data-ttu-id="da5ed-342">Политика продаж</span><span class="sxs-lookup"><span data-stu-id="da5ed-342">Sales policy</span></span>       | <span data-ttu-id="da5ed-343">1</span><span class="sxs-lookup"><span data-stu-id="da5ed-343">1</span></span>        |
|<span data-ttu-id="da5ed-344">Умножен</span><span class="sxs-lookup"><span data-stu-id="da5ed-344">Division</span></span>    |<span data-ttu-id="da5ed-345">Политика деления</span><span class="sxs-lookup"><span data-stu-id="da5ed-345">Division policy</span></span>         |<span data-ttu-id="da5ed-346">2</span><span class="sxs-lookup"><span data-stu-id="da5ed-346">2</span></span>         |
|<span data-ttu-id="da5ed-347">Отделения</span><span class="sxs-lookup"><span data-stu-id="da5ed-347">Subsidiary</span></span>   |<span data-ttu-id="da5ed-348">Политика для дочерних компаний</span><span class="sxs-lookup"><span data-stu-id="da5ed-348">Subsidiary policy</span></span>        |<span data-ttu-id="da5ed-349">3</span><span class="sxs-lookup"><span data-stu-id="da5ed-349">3</span></span>        |

<span data-ttu-id="da5ed-350">В данном примере политика для собрания Teams удаляется из группы.</span><span class="sxs-lookup"><span data-stu-id="da5ed-350">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

<span data-ttu-id="da5ed-351">Дополнительные сведения можно найти в разделе [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="da5ed-351">To learn more, see [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span></span>

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="da5ed-352">Изменение назначения политики для группы</span><span class="sxs-lookup"><span data-stu-id="da5ed-352">Change a policy assignment for a group</span></span>

<span data-ttu-id="da5ed-353">После назначения политики группе вы можете использовать ```Set-CsGroupPolicyAssignment``` командлет, чтобы изменить назначение политики этой группы следующим образом:</span><span class="sxs-lookup"><span data-stu-id="da5ed-353">After you assign a policy to a group, you can use the ```Set-CsGroupPolicyAssignment``` cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="da5ed-354">Изменение ранжирования</span><span class="sxs-lookup"><span data-stu-id="da5ed-354">Change the ranking</span></span>
- <span data-ttu-id="da5ed-355">Изменение политики для определенного типа политики</span><span class="sxs-lookup"><span data-stu-id="da5ed-355">Change the policy of a given policy type</span></span>
- <span data-ttu-id="da5ed-356">Изменение политики для определенного типа политики и ранжирования</span><span class="sxs-lookup"><span data-stu-id="da5ed-356">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="da5ed-357">В этом примере мы изменим политику приостановки вызовов групп для группы на политику с именем SupportCallPark и рейтинг назначения 3.</span><span class="sxs-lookup"><span data-stu-id="da5ed-357">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

<span data-ttu-id="da5ed-358">Дополнительные сведения можно найти в статье [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="da5ed-358">To learn more, see [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span></span>

#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="da5ed-359">Изменение действующей политики для пользователя</span><span class="sxs-lookup"><span data-stu-id="da5ed-359">Change the effective policy for a user</span></span>

<span data-ttu-id="da5ed-360">Ниже приведен пример изменения действующей политики для пользователя, которому непосредственно назначена политика.</span><span class="sxs-lookup"><span data-stu-id="da5ed-360">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="da5ed-361">Сначала мы используем ```Get-CsUserPolicyAssignment``` командлет вместе с ```PolicySource``` параметром, чтобы получить подробные сведения о политиках широковещательного показа собраний Teams, связанных с пользователем.</span><span class="sxs-lookup"><span data-stu-id="da5ed-361">First, we use the ```Get-CsUserPolicyAssignment``` cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> <span data-ttu-id="da5ed-362">Дополнительные сведения можно найти в [статьях Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="da5ed-362">To learn more, see [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="da5ed-363">В выходных данных показано, что пользователю непосредственно назначена политика широковещательного показа собрания Teams, которая имеет приоритет над политикой "события поставщика", назначенной группе, в которую входит пользователь.</span><span class="sxs-lookup"><span data-stu-id="da5ed-363">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="da5ed-364">Теперь мы удаляем политику событий сотрудников от пользователя.</span><span class="sxs-lookup"><span data-stu-id="da5ed-364">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="da5ed-365">Это означает, что пользователь больше не имеет политики широковещательного показа собраний Teams, которой они назначены, и будет наследовать политику Live Events поставщика, назначенную группе, которой принадлежит пользователь.</span><span class="sxs-lookup"><span data-stu-id="da5ed-365">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="da5ed-366">Для этого используйте следующий командлет в модуле Skype для бизнеса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="da5ed-366">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="da5ed-367">Вы можете использовать следующий командлет в модуле Teams PowerShell для выполнения этой задачи при масштабировании при использовании задания пакетной политики, где $users — это список пользователей, которые вы указали.</span><span class="sxs-lookup"><span data-stu-id="da5ed-367">You can use following cmdlet in the Teams Powershell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="da5ed-368">Назначение пакета политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="da5ed-368">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="da5ed-369">С помощью задания пакетной политики можно назначить пакету политики большим наборам пользователей за один раз без использования сценария.</span><span class="sxs-lookup"><span data-stu-id="da5ed-369">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="da5ed-370">```New-CsBatchPolicyPackageAssignmentOperation```С помощью командлета вы можете отправить пакет пользователей и пакет политики, который вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="da5ed-370">You use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="da5ed-371">Назначения обрабатываются как фоновая операция, и для каждого пакета создается идентификатор операции.</span><span class="sxs-lookup"><span data-stu-id="da5ed-371">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="da5ed-372">Затем вы можете использовать этот ```Get-CsBatchPolicyAssignmentOperation``` командлет для отслеживания хода выполнения и состояния заданий в пакете.</span><span class="sxs-lookup"><span data-stu-id="da5ed-372">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="da5ed-373">Вы можете указать пользователей по идентификатору объекта или по протоколу SIP.</span><span class="sxs-lookup"><span data-stu-id="da5ed-373">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="da5ed-374">Обратите внимание, что адрес SIP пользователя часто имеет то же значение, что и имя участника-пользователя (UPN) или адрес электронной почты, но это не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="da5ed-374">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="da5ed-375">Если пользователь указан с использованием имени участника-пользователя или почтового сообщения, но его значение отличается от адреса SIP, для пользователя не будет установлено назначение политики.</span><span class="sxs-lookup"><span data-stu-id="da5ed-375">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="da5ed-376">Если пакет включает повторяющиеся пользователи, дубликаты удаляются из пакета перед обработкой и состоянием будут предоставляться только для уникальных пользователей, остающихся в пакете.</span><span class="sxs-lookup"><span data-stu-id="da5ed-376">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="da5ed-377">Пакет может содержать до 5 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="da5ed-377">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="da5ed-378">Для достижения наилучших результатов не отправляйте более нескольких пакетов одновременно.</span><span class="sxs-lookup"><span data-stu-id="da5ed-378">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="da5ed-379">Разрешите пакетам завершить обработку перед отправкой пакетов.</span><span class="sxs-lookup"><span data-stu-id="da5ed-379">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="da5ed-380">Установка и подключение к модулю Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="da5ed-380">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="da5ed-381">Выполните указанные ниже действия, чтобы установить [модуль Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (если вы еще этого не сделали).</span><span class="sxs-lookup"><span data-stu-id="da5ed-381">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="da5ed-382">Убедитесь, что вы установили версию 1.0.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="da5ed-382">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="da5ed-383">Выполните указанные ниже действия, чтобы подключиться к Teams и начать сеанс.</span><span class="sxs-lookup"><span data-stu-id="da5ed-383">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="da5ed-384">Когда вам будет предложено, войдите в систему с помощью учетных данных администратора.</span><span class="sxs-lookup"><span data-stu-id="da5ed-384">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="da5ed-385">Назначение пакета политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="da5ed-385">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="da5ed-386">В этом примере мы используем ```New-CsBatchPolicyPackageAssignmentOperation``` командлет для назначения пакета политики Education_PrimaryStudent пакету пользователей.</span><span class="sxs-lookup"><span data-stu-id="da5ed-386">In this example, we use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

<span data-ttu-id="da5ed-387">Дополнительные сведения можно найти в статье [Создание и CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="da5ed-387">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="da5ed-388">Получение статуса задания пакетной обработки</span><span class="sxs-lookup"><span data-stu-id="da5ed-388">Get the status of a batch assignment</span></span>

<span data-ttu-id="da5ed-389">Выполните указанные ниже действия, чтобы получить сведения о состоянии задания пакета, где идентификатор операции — это значение, возвращаемое ```New-CsBatchPolicyAssignmentOperation``` командлетом для данного пакета.</span><span class="sxs-lookup"><span data-stu-id="da5ed-389">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="da5ed-390">Если в выходных данных показано, что произошла ошибка, выполните указанные ниже действия, чтобы получить дополнительные сведения об ошибках, которые находятся в ```UserState``` свойстве.</span><span class="sxs-lookup"><span data-stu-id="da5ed-390">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="da5ed-391">Дополнительные сведения можно найти в [статьях Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="da5ed-391">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="da5ed-392">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="da5ed-392">Related topics</span></span>

[<span data-ttu-id="da5ed-393">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="da5ed-393">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
