---
title: Назначение политик вашим пользователям в Microsoft Teams
author: cichur
ms.author: v-cichur
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
description: Узнайте о различных способах назначения политик пользователям в Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: a77e1cd6a6caf562edcdca0a49f200e6678bd6f5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111415"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="74ba3-103">Назначение политик вашим пользователям в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="74ba3-103">Assign policies to your users in Microsoft Teams</span></span>

<span data-ttu-id="74ba3-104">Администраторы используют политики для управления функциями Teams, доступными пользователям в организации.</span><span class="sxs-lookup"><span data-stu-id="74ba3-104">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="74ba3-105">Например, есть политики звонков, политики собраний и политики обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="74ba3-105">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="74ba3-106">В организациях есть различные типы пользователей с уникальными потребностями.</span><span class="sxs-lookup"><span data-stu-id="74ba3-106">Organizations have different types of users with unique needs.</span></span> <span data-ttu-id="74ba3-107">Настраиваемые политики, которые вы создаете и назначаете, по возможности настраивают параметры политики для различных наборов пользователей с учетом этих потребностей.</span><span class="sxs-lookup"><span data-stu-id="74ba3-107">Custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="74ba3-108">Чтобы легко управлять политиками в организации, Teams предлагает несколько способов назначить политики пользователям.</span><span class="sxs-lookup"><span data-stu-id="74ba3-108">To easily manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="74ba3-109">Назначьте политику непосредственно пользователям (по отдельности или в масштабе с помощью пакетного назначения) или группе, в которую они в являются участниками.</span><span class="sxs-lookup"><span data-stu-id="74ba3-109">Assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="74ba3-110">Вы также можете использовать пакеты политик, чтобы назначить предустановленную коллекцию политик пользователям с похожими ролями.</span><span class="sxs-lookup"><span data-stu-id="74ba3-110">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="74ba3-111">Выбор варианта зависит от количества политик, которые вы управляете, и от количества пользователей, которых вы назначаете.</span><span class="sxs-lookup"><span data-stu-id="74ba3-111">The option that you choose depends on the number of policies that you're managing and the number of users you're assigning policies to.</span></span> <span data-ttu-id="74ba3-112">Глобальные политики (по умолчанию для всей организации) применяются к наибольшему числу пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="74ba3-112">Global (Org-wide default) policies apply to the largest number of users in your organization.</span></span> <span data-ttu-id="74ba3-113">Политики нужно назначать только тем пользователям, для кого требуются специализированные политики.</span><span class="sxs-lookup"><span data-stu-id="74ba3-113">You only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="74ba3-114">В этой статье описаны различные способы назначения политик пользователям и рекомендуемые сценарии использования.</span><span class="sxs-lookup"><span data-stu-id="74ba3-114">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="74ba3-115">Какая политика имеет приоритет?</span><span class="sxs-lookup"><span data-stu-id="74ba3-115">Which policy takes precedence?</span></span>

<span data-ttu-id="74ba3-116">У пользователя есть одна эффективная политика для каждого типа политики.</span><span class="sxs-lookup"><span data-stu-id="74ba3-116">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="74ba3-117">Вполне возможно, что пользователю напрямую назначена политика, а также она входит в одну или несколько групп, политика того же типа.</span><span class="sxs-lookup"><span data-stu-id="74ba3-117">It's possible, or even likely, that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="74ba3-118">Какая политика имеет приоритет в подобных сценариях?</span><span class="sxs-lookup"><span data-stu-id="74ba3-118">In these kinds of scenarios, which policy takes precedence?</span></span> <span data-ttu-id="74ba3-119">Эффективная политика пользователя определяется согласно правилам приоритета.</span><span class="sxs-lookup"><span data-stu-id="74ba3-119">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="74ba3-120">Если пользователю непосредственно назначена политика (по отдельности или через пакетное назначение), она имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="74ba3-120">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="74ba3-121">В следующем наглядном примере эффективной политикой пользователя является политика собраний "По квадрату1", которая непосредственно назначена пользователю.</span><span class="sxs-lookup"><span data-stu-id="74ba3-121">In the following visual example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![Схема, показывающая, как приоритет имеет непосредственно назначенная политика](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="74ba3-123">Если пользователю не назначена непосредственно политика заданного типа, политика, назначенная группе, в которую входит пользователь, имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="74ba3-123">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="74ba3-124">Если пользователь входит в несколько групп, приоритет имеет [](#group-assignment-ranking) политика с наивысшим ранжированием назначений для данного типа политики.</span><span class="sxs-lookup"><span data-stu-id="74ba3-124">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="74ba3-125">В этом наглядном примере эффективной политикой пользователя является политика Exec Teams и HD с наивысшим ранжированием назначений по сравнению с другими группами, в которые входит пользователь, и которым назначена политика того же типа политики.</span><span class="sxs-lookup"><span data-stu-id="74ba3-125">In this visual example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![Схема, показывающая, как политика, наследуемая от группы, имеет приоритет](media/assign-policies-example-group.png)

<span data-ttu-id="74ba3-127">Если пользователю не назначена политика напрямую или он не входит в какие-либо группы, ему предоставляется глобальная политика (по умолчанию в организации).</span><span class="sxs-lookup"><span data-stu-id="74ba3-127">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="74ba3-128">Вот наглядный пример.</span><span class="sxs-lookup"><span data-stu-id="74ba3-128">Here's a visual example.</span></span>

![Схема, показывающая приоритет глобальной политики](media/assign-policies-example-global.png)

<span data-ttu-id="74ba3-130">Дополнительные узнать см. в [правилах приоритета.](#precedence-rules)</span><span class="sxs-lookup"><span data-stu-id="74ba3-130">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="74ba3-131">Способы назначения политик</span><span class="sxs-lookup"><span data-stu-id="74ba3-131">Ways to assign policies</span></span>

<span data-ttu-id="74ba3-132">Ниже представлен обзор способов назначения политик пользователям и рекомендуемых сценариев для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="74ba3-132">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="74ba3-133">Пере выберите ссылки, чтобы узнать больше.</span><span class="sxs-lookup"><span data-stu-id="74ba3-133">Select the links to learn more.</span></span>

<span data-ttu-id="74ba3-134">Прежде чем назначать политики отдельным пользователям или группам, начните с настройки глобальных (по умолчанию [в организации)](#set-the-global-policies) политик, которые будут применяться к наибольшему числу пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="74ba3-134">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="74ba3-135">После того как будут настроены глобальные политики, вам потребуется назначить политики только тем пользователям, для кого требуются специализированные политики.</span><span class="sxs-lookup"><span data-stu-id="74ba3-135">Once the global policies are set, you'll only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="74ba3-136">Сделайте это</span><span class="sxs-lookup"><span data-stu-id="74ba3-136">Do this</span></span>  |<span data-ttu-id="74ba3-137">Если...</span><span class="sxs-lookup"><span data-stu-id="74ba3-137">If...</span></span>  | <span data-ttu-id="74ba3-138">Использование...</span><span class="sxs-lookup"><span data-stu-id="74ba3-138">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="74ba3-139">Назначение политики отдельным пользователям</span><span class="sxs-lookup"><span data-stu-id="74ba3-139">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="74ba3-140">Вы только начинаете работу с Teams или вам нужно назначить лишь одну или несколько политик небольшому количеству пользователей.</span><span class="sxs-lookup"><span data-stu-id="74ba3-140">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="74ba3-141">Центр администрирования Microsoft Teams или командлеты PowerShell в модуле Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="74ba3-141">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>
|[<span data-ttu-id="74ba3-142">Назначение политики группе</span><span class="sxs-lookup"><span data-stu-id="74ba3-142">Assign a policy to a group</span></span>](#assign-a-policy-to-a-group) |<span data-ttu-id="74ba3-143">Назначать политики, основанные на членстве пользователя в группах.</span><span class="sxs-lookup"><span data-stu-id="74ba3-143">Assign policies based on a user's group membership.</span></span> <span data-ttu-id="74ba3-144">Например, назначьте политику всем пользователям в группе безопасности или списке рассылки.</span><span class="sxs-lookup"><span data-stu-id="74ba3-144">For example, assign a policy to all users in a security group or distribution list.</span></span>| <span data-ttu-id="74ba3-145">Центр администрирования Microsoft Teams или командлеты PowerShell в модуле Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="74ba3-145">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="74ba3-146">Назначение политики для пакета пользователей</span><span class="sxs-lookup"><span data-stu-id="74ba3-146">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="74ba3-147">Назначать политики большим наборам пользователей.</span><span class="sxs-lookup"><span data-stu-id="74ba3-147">Assign policies to large sets of users.</span></span> <span data-ttu-id="74ba3-148">Например, можно назначить политику одновременно сотням или тысячам пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="74ba3-148">For example, assign a policy to hundreds or thousands of users in your organization at a time.</span></span> |<span data-ttu-id="74ba3-149">Центр администрирования Microsoft Teams или командлеты PowerShell в модуле Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="74ba3-149">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="74ba3-150">Назначение пакета политики пользователям</span><span class="sxs-lookup"><span data-stu-id="74ba3-150">Assign a policy package to users</span></span>](#assign-a-policy-package-to-users)  |<span data-ttu-id="74ba3-151">Назначьте несколько политик определенным наборам пользователей с одинаковыми или похожими ролями.</span><span class="sxs-lookup"><span data-stu-id="74ba3-151">Assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="74ba3-152">Например, назначьте пакет политики "Образование (преподаватель)" преподавателям в вашем учебном за учебных заведениях, чтобы предоставить им полный доступ к чатам, звонкам и собраниям.</span><span class="sxs-lookup"><span data-stu-id="74ba3-152">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings.</span></span> <span data-ttu-id="74ba3-153">Назначьте пакет политики "Образование (дополнительное учебное заведения)" дополнительным учащимся, чтобы ограничить некоторые возможности, такие как частные вызовы.</span><span class="sxs-lookup"><span data-stu-id="74ba3-153">Assign the Education (Secondary school student) policy package to secondary students to limit certain capabilities such as private calling.</span></span>  |<span data-ttu-id="74ba3-154">Центр администрирования Microsoft Teams или командлеты PowerShell в модуле Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="74ba3-154">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="74ba3-155">[Назначение пакета политики группе (в](#assign-a-policy-package-to-a-group) режиме личной предварительной версии)</span><span class="sxs-lookup"><span data-stu-id="74ba3-155">[Assign a policy package to a group](#assign-a-policy-package-to-a-group) (in private preview)</span></span>   |<span data-ttu-id="74ba3-156">Назначьте несколько политик группе пользователей в организации с одинаковыми или похожими ролями.</span><span class="sxs-lookup"><span data-stu-id="74ba3-156">Assign multiple policies to a group of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="74ba3-157">Например, назначьте пакет политики всем пользователям в группе безопасности или списке рассылки.</span><span class="sxs-lookup"><span data-stu-id="74ba3-157">For example, assign a policy package to all users in a security group or distribution list.</span></span> |<span data-ttu-id="74ba3-158">Центр администрирования Microsoft Teams (скоро появится) или командлеты PowerShell в модуле Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="74ba3-158">The Microsoft Teams admin center (coming soon) or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="74ba3-159">Назначение пакета политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="74ba3-159">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="74ba3-160">Назначьте несколько политик пакету пользователей в организации с одинаковыми или похожими ролями.</span><span class="sxs-lookup"><span data-stu-id="74ba3-160">Assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="74ba3-161">Например, назначьте пакет политики "Образование (преподаватель)" всем преподавателям в учебном за учебных заведениях с помощью пакетного задания, чтобы предоставить им полный доступ к чатам, звонкам и собраниям.</span><span class="sxs-lookup"><span data-stu-id="74ba3-161">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings.</span></span> <span data-ttu-id="74ba3-162">Назначьте пакет политики "Образование (дополнительное учебное заведения)" пакету дополнительных учащихся, чтобы ограничить некоторые возможности, такие как частные вызовы.</span><span class="sxs-lookup"><span data-stu-id="74ba3-162">Assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities such as private calling.</span></span>|<span data-ttu-id="74ba3-163">Командлеты PowerShell в модуле Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="74ba3-163">PowerShell cmdlets in the Teams PowerShell module</span></span>|

## <a name="set-the-global-policies"></a><span data-ttu-id="74ba3-164">Настройка глобальных политик</span><span class="sxs-lookup"><span data-stu-id="74ba3-164">Set the global policies</span></span>

<span data-ttu-id="74ba3-165">Выполните эти действия, чтобы настроить глобальные политики (по умолчанию для всей организации) для каждого типа политики.</span><span class="sxs-lookup"><span data-stu-id="74ba3-165">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="74ba3-166">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="74ba3-166">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="74ba3-167">В левой области навигации Центра администрирования Microsoft Teams перейдите на страницу политики для типа политики, который вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="74ba3-167">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="74ba3-168">Например, политики **Teams** Teams, политики собраний для собраний, политики обмена сообщениями или политики  >     >   **голосовых**   >  **звонков.**</span><span class="sxs-lookup"><span data-stu-id="74ba3-168">For example, **Teams** > **Teams policies**, **Meetings** > **Meetings policies**, **Messaging policies**, or **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="74ba3-169">Выберите **глобальную политику (по умолчанию** для всей организации), чтобы просмотреть текущие параметры.</span><span class="sxs-lookup"><span data-stu-id="74ba3-169">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="74ba3-170">Обновив политику, выберите **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="74ba3-170">Update the policy as needed, and then select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="74ba3-171">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="74ba3-171">Using PowerShell</span></span>

<span data-ttu-id="74ba3-172">Чтобы настроить глобальные политики с помощью PowerShell, используйте глобальный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="74ba3-172">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="74ba3-173">Для начала просмотрите текущую глобальную политику, чтобы определить, какой параметр вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="74ba3-173">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

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

<span data-ttu-id="74ba3-174">Затем при необходимости обновим глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="74ba3-174">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="74ba3-175">Вам нужно только указать значения для параметров, которые вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="74ba3-175">You only need to specify values for the settings that you want to change.</span></span>

```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="74ba3-176">Назначение политики отдельным пользователям</span><span class="sxs-lookup"><span data-stu-id="74ba3-176">Assign a policy to individual users</span></span>

<span data-ttu-id="74ba3-177">Выполните эти действия, чтобы назначить политику отдельному пользователю или небольшому числу пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="74ba3-177">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="use-the-microsoft-teams-admin-center"></a><span data-ttu-id="74ba3-178">Использование Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="74ba3-178">Use the Microsoft Teams admin center</span></span>

<span data-ttu-id="74ba3-179">Чтобы назначить политику пользователю:</span><span class="sxs-lookup"><span data-stu-id="74ba3-179">To assign a policy to a user:</span></span>

1. <span data-ttu-id="74ba3-180">В левой области навигации Центра администрирования Microsoft Teams перейдите в меню **"Пользователи"** и выберите пользователя.</span><span class="sxs-lookup"><span data-stu-id="74ba3-180">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="74ba3-181">Выберите пользователя, щелкнув слева от его имени и выбрав "Изменить **параметры".**</span><span class="sxs-lookup"><span data-stu-id="74ba3-181">Select the user by clicking to the left of the user name, and then select **Edit settings**.</span></span>
3. <span data-ttu-id="74ba3-182">Выберите политику, а затем выберите **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="74ba3-182">Select the policy you want to assign, and then select **Apply**.</span></span>

<span data-ttu-id="74ba3-183">Кроме того, вы можете сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="74ba3-183">Or, you can also do the following:</span></span>

1. <span data-ttu-id="74ba3-184">В левой области навигации Центра администрирования Microsoft Teams перейдите на страницу политики.</span><span class="sxs-lookup"><span data-stu-id="74ba3-184">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="74ba3-185">Выберите политику, которая вы хотите назначить, щелкнув слева от ее имени.</span><span class="sxs-lookup"><span data-stu-id="74ba3-185">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="74ba3-186">Выберите **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="74ba3-186">Select **Manage users**.</span></span>
4. <span data-ttu-id="74ba3-187">В области **Управление пользователями** выполните поиск по отображаемому имени или по имени пользователя, выберите имя и нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="74ba3-187">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="74ba3-188">Повторите это действие для каждого пользователя, которого нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="74ba3-188">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="74ba3-189">Завершив добавление пользователей, выберите **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="74ba3-189">When you're finished adding users, select **Apply**.</span></span>

### <a name="use-powershell"></a><span data-ttu-id="74ba3-190">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="74ba3-190">Use PowerShell</span></span>

<span data-ttu-id="74ba3-191">У каждого типа политики есть собственный набор cmdlets для управления.</span><span class="sxs-lookup"><span data-stu-id="74ba3-191">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="74ba3-192">Используйте для назначения политики тот или иной тип ```Grant-``` политики с помощью cmdlet.</span><span class="sxs-lookup"><span data-stu-id="74ba3-192">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="74ba3-193">Например, используйте ```Grant-CsTeamsMeetingPolicy``` командлет для назначения пользователям политики собраний Teams.</span><span class="sxs-lookup"><span data-stu-id="74ba3-193">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="74ba3-194">Эти командлеты включены в модуль Teams PowerShell и задокументированы в справочнике по [командлету Skype для бизнеса.](/powershell/skype/intro?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="74ba3-194">These cmdlets are included in the Teams PowerShell module and are documented in the [Skype for Business cmdlet reference](/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="74ba3-195">Скачайте и установите общедоступный выпуск [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) (если еще не сделали этого), а затем запустите следующую команду, чтобы подключиться:</span><span class="sxs-lookup"><span data-stu-id="74ba3-195">Download and install the [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) (if you haven't already), and then run the following to connect.</span></span>

> [!NOTE]
> <span data-ttu-id="74ba3-196">Соединитель Skype для бизнеса Online сейчас входит в состав последнего модуля Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74ba3-196">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="74ba3-197">Если вы используете последний общедоступный выпуск [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="74ba3-197">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="74ba3-198">В этом примере мы назначаем политику собраний Teams "Политика собраний учащихся" пользователю Reda.</span><span class="sxs-lookup"><span data-stu-id="74ba3-198">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="74ba3-199">Для получения дополнительных информации [ознакомьтесь с управлением политиками с помощью PowerShell.](teams-powershell-managing-teams.md#manage-policies-via-powershell)</span><span class="sxs-lookup"><span data-stu-id="74ba3-199">To learn more, read [Manage policies via PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="74ba3-200">Назначение политики группе</span><span class="sxs-lookup"><span data-stu-id="74ba3-200">Assign a policy to a group</span></span>

<span data-ttu-id="74ba3-201">Назначение политик группам позволяет назначить политику группе пользователей, например группе безопасности или списку рассылки.</span><span class="sxs-lookup"><span data-stu-id="74ba3-201">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="74ba3-202">Назначение политики распространяется на участников группы в соответствии с правилами очередности.</span><span class="sxs-lookup"><span data-stu-id="74ba3-202">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="74ba3-203">При добавлении или удалении участников группы, назначения политик для них обновляются соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="74ba3-203">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="74ba3-204">Назначение политик группам рекомендуется для групп до 50 000 пользователей, но оно также будет работать с более крупными группами.</span><span class="sxs-lookup"><span data-stu-id="74ba3-204">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="74ba3-205">Назначенная политика сразу же назначается группе.</span><span class="sxs-lookup"><span data-stu-id="74ba3-205">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="74ba3-206">Однако распространение назначения политики на участников группы выполняется в фоновом режиме и может занять некоторое время в зависимости от размера группы.</span><span class="sxs-lookup"><span data-stu-id="74ba3-206">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="74ba3-207">То же самое происходит, если политика не назначена группе, а также когда участники добавляются в группу или удаляются из нее.</span><span class="sxs-lookup"><span data-stu-id="74ba3-207">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

<span data-ttu-id="74ba3-208">Назначения групповой политики распространяются только на пользователей, которые являются прямыми участниками группы.</span><span class="sxs-lookup"><span data-stu-id="74ba3-208">Group policy assignments are only propagated to users who are direct members of the group.</span></span> <span data-ttu-id="74ba3-209">Назначения не распространяются на участников вложенных групп.</span><span class="sxs-lookup"><span data-stu-id="74ba3-209">The assignments aren't propagated to members of nested groups.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="74ba3-210">Что нужно знать о назначении политик группам</span><span class="sxs-lookup"><span data-stu-id="74ba3-210">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="74ba3-211">Прежде чем начать, важно разобраться в правилах приоритета и ранжирования заданий групп.</span><span class="sxs-lookup"><span data-stu-id="74ba3-211">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="74ba3-212">Правила приоритета</span><span class="sxs-lookup"><span data-stu-id="74ba3-212">Precedence rules</span></span>

<span data-ttu-id="74ba3-213">Для данного типа политики эффективная политика пользователя определяется в соответствии со следующими данными:</span><span class="sxs-lookup"><span data-stu-id="74ba3-213">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="74ba3-214">Политика, которая непосредственно назначена пользователю, имеет приоритет над любой другой политикой того же типа, которая назначена группе.</span><span class="sxs-lookup"><span data-stu-id="74ba3-214">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="74ba3-215">Другими словами, если пользователю непосредственно назначена политика заданного типа, он не наследует политику того же типа от группы.</span><span class="sxs-lookup"><span data-stu-id="74ba3-215">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="74ba3-216">Это также означает, что если пользователю назначена политика заданного типа, необходимо удалить ее, прежде чем он сможет наследовать политику того же типа из группы.</span><span class="sxs-lookup"><span data-stu-id="74ba3-216">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="74ba3-217">Если пользователю не назначена политика напрямую и он входит в несколько групп и каждой группе назначена политика одного и того же типа, то пользователь наследует политику назначения группы с наивысшим рейтингом.</span><span class="sxs-lookup"><span data-stu-id="74ba3-217">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="74ba3-218">Если пользователь не входит в группы, для каких-либо групп назначена политика, к этому типу политики применяется глобальная политика (по умолчанию в организации).</span><span class="sxs-lookup"><span data-stu-id="74ba3-218">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="74ba3-219">Эффективная политика пользователя обновляется в соответствии с этими правилами:</span><span class="sxs-lookup"><span data-stu-id="74ba3-219">A user's effective policy is updated according to these rules:</span></span>

- <span data-ttu-id="74ba3-220">при добавлении пользователя в группу, которая назначена политике, или удален из нее.</span><span class="sxs-lookup"><span data-stu-id="74ba3-220">when a user is added to or removed from a group that's assigned a policy.</span></span>
- <span data-ttu-id="74ba3-221">политика не назначена группе.</span><span class="sxs-lookup"><span data-stu-id="74ba3-221">a policy is unassigned from a group.</span></span>
- <span data-ttu-id="74ba3-222">Политика, которая непосредственно назначена пользователю, будет удалена.</span><span class="sxs-lookup"><span data-stu-id="74ba3-222">a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="74ba3-223">Ранжирование назначений групп</span><span class="sxs-lookup"><span data-stu-id="74ba3-223">Group assignment ranking</span></span>

<span data-ttu-id="74ba3-224">При назначении политики группе вы указываете ранжирование для назначения группы.</span><span class="sxs-lookup"><span data-stu-id="74ba3-224">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="74ba3-225">Он используется для определения политики, которая должна наследоваться пользователем как эффективная политика, если пользователь входит в несколько групп и каждой группе назначена политика одного типа.</span><span class="sxs-lookup"><span data-stu-id="74ba3-225">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="74ba3-226">Ранжирование групповых заданий относительно других назначений того же типа.</span><span class="sxs-lookup"><span data-stu-id="74ba3-226">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="74ba3-227">Например, если политика звонков назначается двум группам, узначьте ранжирование одному заданию 1, а другому — 2, причем 1 — самый высокий.</span><span class="sxs-lookup"><span data-stu-id="74ba3-227">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="74ba3-228">Ранжирование назначений групп показывает, какие из них более важны или релевантны, чем другие группы в отношении наследования.</span><span class="sxs-lookup"><span data-stu-id="74ba3-228">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>

<span data-ttu-id="74ba3-229">Например, у вас есть две группы: "Сотрудники магазинов" и "Руководители магазинов".</span><span class="sxs-lookup"><span data-stu-id="74ba3-229">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="74ba3-230">Обе группы имеют политику звонков Teams, политику звонков сотрудников магазина и политику звонков диспетчеров магазинов соответственно.</span><span class="sxs-lookup"><span data-stu-id="74ba3-230">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="74ba3-231">Руководителю магазина, который относится к обеим группам, роль руководителя должна быть больше релевантной, чем роль сотрудника, поэтому политика звонков, назначенная группе "Руководители магазинов", должна иметь более высокий рейтинг.</span><span class="sxs-lookup"><span data-stu-id="74ba3-231">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="74ba3-232">Группа</span><span class="sxs-lookup"><span data-stu-id="74ba3-232">Group</span></span> |<span data-ttu-id="74ba3-233">Название политики звонков Teams</span><span class="sxs-lookup"><span data-stu-id="74ba3-233">Teams calling policy name</span></span>  |<span data-ttu-id="74ba3-234">Rank (Ранг)</span><span class="sxs-lookup"><span data-stu-id="74ba3-234">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="74ba3-235">Руководители магазинов</span><span class="sxs-lookup"><span data-stu-id="74ba3-235">Store Managers</span></span>   |<span data-ttu-id="74ba3-236">Политика звонков для руководителей магазинов</span><span class="sxs-lookup"><span data-stu-id="74ba3-236">Store Managers Calling Policy</span></span>         |<span data-ttu-id="74ba3-237">1</span><span class="sxs-lookup"><span data-stu-id="74ba3-237">1</span></span>|
|<span data-ttu-id="74ba3-238">Сотрудники магазина</span><span class="sxs-lookup"><span data-stu-id="74ba3-238">Store Employees</span></span>    |<span data-ttu-id="74ba3-239">Политика звонков сотрудников магазина</span><span class="sxs-lookup"><span data-stu-id="74ba3-239">Store Employees Calling Policy</span></span>      |<span data-ttu-id="74ba3-240">2</span><span class="sxs-lookup"><span data-stu-id="74ba3-240">2</span></span>|

<span data-ttu-id="74ba3-241">Если не указать ранжирование, назначение политики будет присвоено наименьшему ранжирование.</span><span class="sxs-lookup"><span data-stu-id="74ba3-241">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="in-the-teams-admin-center"></a><span data-ttu-id="74ba3-242">В Центре администрирования Teams</span><span class="sxs-lookup"><span data-stu-id="74ba3-242">In the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="74ba3-243">В настоящее время назначение политик группам с помощью Центра администрирования Microsoft Teams доступно только для политик звонков Teams, политики в парке звонков Teams, политики Teams, политики трансляций Teams, политики собраний Teams и политики обмена сообщениями Teams.</span><span class="sxs-lookup"><span data-stu-id="74ba3-243">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="74ba3-244">Для других типов политик используйте PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74ba3-244">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="74ba3-245">В левой области навигации Центра администрирования Microsoft Teams перейдите на страницу типа политики.</span><span class="sxs-lookup"><span data-stu-id="74ba3-245">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="74ba3-246">Например, перейдите к **политикам**  >  **собраний собраний.**</span><span class="sxs-lookup"><span data-stu-id="74ba3-246">For example, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="74ba3-247">Выберите **вкладку назначения групповой политики.**</span><span class="sxs-lookup"><span data-stu-id="74ba3-247">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="74ba3-248">Выберите **"Добавить группу",** а затем в области "Назначение политики группе" сделайте следующее: </span><span class="sxs-lookup"><span data-stu-id="74ba3-248">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="74ba3-249">Найщите и добавьте группу, для нее нужно назначить политику.</span><span class="sxs-lookup"><span data-stu-id="74ba3-249">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="74ba3-250">Задание ранжирования для группового назначения.</span><span class="sxs-lookup"><span data-stu-id="74ba3-250">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="74ba3-251">Выберите политику, которую вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="74ba3-251">Select the policy that you want to assign.</span></span>
    4. <span data-ttu-id="74ba3-252">Выберите **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="74ba3-252">Select **Apply**.</span></span>

<span data-ttu-id="74ba3-253">Чтобы удалить назначение групповой  политики, на вкладке назначения групповой политики на странице политики выберите назначение группы, а затем выберите **"Удалить".**</span><span class="sxs-lookup"><span data-stu-id="74ba3-253">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="74ba3-254">Чтобы изменить ранжирование для группового назначения, необходимо сначала удалить назначение групповой политики.</span><span class="sxs-lookup"><span data-stu-id="74ba3-254">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="74ba3-255">Затем следуйте этим шагам, чтобы назначить политику группе.</span><span class="sxs-lookup"><span data-stu-id="74ba3-255">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="use-the-powershell-option"></a><span data-ttu-id="74ba3-256">Использование параметра PowerShell</span><span class="sxs-lookup"><span data-stu-id="74ba3-256">Use the PowerShell option</span></span>

> [!NOTE]
> <span data-ttu-id="74ba3-257">В настоящее время назначение политик группам с помощью PowerShell доступно не для всех типов политик Teams.</span><span class="sxs-lookup"><span data-stu-id="74ba3-257">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="74ba3-258">Список поддерживаемых типов политик см. в списке [New-CsGroupPolicyAssignment.](/powershell/module/teams/new-csgrouppolicyassignment)</span><span class="sxs-lookup"><span data-stu-id="74ba3-258">See [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="74ba3-259">Установка и подключение к модуле Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="74ba3-259">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="74ba3-260">Пошаговую инструкцию см. в [руководстве по установке Teams PowerShell.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="74ba3-260">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-to-a-group-of-users"></a><span data-ttu-id="74ba3-261">Назначение политики группе пользователей</span><span class="sxs-lookup"><span data-stu-id="74ba3-261">Assign a policy to a group of users</span></span>

<span data-ttu-id="74ba3-262">Чтобы назначить политику группе, [воспользуйтесь cmdlet New-CsGroupPolicyAssignment.](/powershell/module/teams/new-csgrouppolicyassignment)</span><span class="sxs-lookup"><span data-stu-id="74ba3-262">Use the [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="74ba3-263">Группу можно указать с помощью ИД объекта, SIP-адреса или адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="74ba3-263">You can specify a group by using the object ID, SIP address, or email address.</span></span>

<span data-ttu-id="74ba3-264">В этом примере мы назначаем политику собраний Teams "Политика собраний розничных менеджеров" группе со ранжированием заданий 1.</span><span class="sxs-lookup"><span data-stu-id="74ba3-264">In this example, we assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="74ba3-265">Получать назначения политик для группы</span><span class="sxs-lookup"><span data-stu-id="74ba3-265">Get policy assignments for a group</span></span>

<span data-ttu-id="74ba3-266">Для получения всех политик, которые назначены группе, используйте [cmdlet Get-CsGroupPolicyAssignment.](/powershell/module/teams/get-csgrouppolicyassignment)</span><span class="sxs-lookup"><span data-stu-id="74ba3-266">Use the [Get-CsGroupPolicyAssignment](/powershell/module/teams/get-csgrouppolicyassignment) cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="74ba3-267">Обратите внимание, что группы всегда перечисляются по их ИД, даже если для назначения политики использовался ее SIP-адрес или адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="74ba3-267">Note that groups are always listed by their group ID even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="74ba3-268">В этом примере мы извлекаем все политики, которые назначены определенной группе.</span><span class="sxs-lookup"><span data-stu-id="74ba3-268">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="74ba3-269">В этом примере возвращаются все группы, которые имеют политику собраний Teams.</span><span class="sxs-lookup"><span data-stu-id="74ba3-269">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="74ba3-270">Удаление политики из группы</span><span class="sxs-lookup"><span data-stu-id="74ba3-270">Remove a policy from a group</span></span>

<span data-ttu-id="74ba3-271">Чтобы удалить политику из группы, [используйте cmdlet Remove-CsGroupPolicyAssignment.](/powershell/module/teams/remove-csgrouppolicyassignment)</span><span class="sxs-lookup"><span data-stu-id="74ba3-271">Use the [Remove-CsGroupPolicyAssignment](/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="74ba3-272">При этом приоритеты других политик того же типа, которые имеют более низкий рейтинг, обновляются.</span><span class="sxs-lookup"><span data-stu-id="74ba3-272">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group, and that have a lower ranking, are updated.</span></span> <span data-ttu-id="74ba3-273">Например, если удалить политику со ранжированием 2, политики с ранжированием 3 и 4 будут обновлены с учетом нового ранжирования.</span><span class="sxs-lookup"><span data-stu-id="74ba3-273">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="74ba3-274">В следующих двух таблицах приводится пример.</span><span class="sxs-lookup"><span data-stu-id="74ba3-274">The following two tables show this example.</span></span>

<span data-ttu-id="74ba3-275">Вот список назначений и приоритетов политики собраний Teams.</span><span class="sxs-lookup"><span data-stu-id="74ba3-275">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="74ba3-276">Имя группы</span><span class="sxs-lookup"><span data-stu-id="74ba3-276">Group name</span></span>  |<span data-ttu-id="74ba3-277">Название политики</span><span class="sxs-lookup"><span data-stu-id="74ba3-277">Policy name</span></span>  |<span data-ttu-id="74ba3-278">Rank (Ранг)</span><span class="sxs-lookup"><span data-stu-id="74ba3-278">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="74ba3-279">Продажи</span><span class="sxs-lookup"><span data-stu-id="74ba3-279">Sales</span></span>    |<span data-ttu-id="74ba3-280">Политика продаж</span><span class="sxs-lookup"><span data-stu-id="74ba3-280">Sales policy</span></span>       | <span data-ttu-id="74ba3-281">1</span><span class="sxs-lookup"><span data-stu-id="74ba3-281">1</span></span>        |
|<span data-ttu-id="74ba3-282">Западная область</span><span class="sxs-lookup"><span data-stu-id="74ba3-282">West Region</span></span>     |<span data-ttu-id="74ba3-283">Политика западного региона</span><span class="sxs-lookup"><span data-stu-id="74ba3-283">West Region policy</span></span>         |<span data-ttu-id="74ba3-284">2</span><span class="sxs-lookup"><span data-stu-id="74ba3-284">2</span></span>         |
|<span data-ttu-id="74ba3-285">Деление</span><span class="sxs-lookup"><span data-stu-id="74ba3-285">Division</span></span>    |<span data-ttu-id="74ba3-286">Политика деления</span><span class="sxs-lookup"><span data-stu-id="74ba3-286">Division policy</span></span>         |<span data-ttu-id="74ba3-287">3</span><span class="sxs-lookup"><span data-stu-id="74ba3-287">3</span></span>         |
|<span data-ttu-id="74ba3-288">Дочернее подразделение</span><span class="sxs-lookup"><span data-stu-id="74ba3-288">Subsidiary</span></span>   |<span data-ttu-id="74ba3-289">Политика дочернего подразделения</span><span class="sxs-lookup"><span data-stu-id="74ba3-289">Subsidiary policy</span></span>        |<span data-ttu-id="74ba3-290">4</span><span class="sxs-lookup"><span data-stu-id="74ba3-290">4</span></span>         |

<span data-ttu-id="74ba3-291">Если удалить политику западного региона из группы "Запад региона", назначения и приоритеты политики обновляются следующим образом.</span><span class="sxs-lookup"><span data-stu-id="74ba3-291">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="74ba3-292">Имя группы</span><span class="sxs-lookup"><span data-stu-id="74ba3-292">Group name</span></span>  |<span data-ttu-id="74ba3-293">Название политики</span><span class="sxs-lookup"><span data-stu-id="74ba3-293">Policy name</span></span>  |<span data-ttu-id="74ba3-294">Rank (Ранг)</span><span class="sxs-lookup"><span data-stu-id="74ba3-294">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="74ba3-295">Продажи</span><span class="sxs-lookup"><span data-stu-id="74ba3-295">Sales</span></span>    |<span data-ttu-id="74ba3-296">Политика продаж</span><span class="sxs-lookup"><span data-stu-id="74ba3-296">Sales policy</span></span>       | <span data-ttu-id="74ba3-297">1</span><span class="sxs-lookup"><span data-stu-id="74ba3-297">1</span></span>        |
|<span data-ttu-id="74ba3-298">Деление</span><span class="sxs-lookup"><span data-stu-id="74ba3-298">Division</span></span>    |<span data-ttu-id="74ba3-299">Политика деления</span><span class="sxs-lookup"><span data-stu-id="74ba3-299">Division policy</span></span>         |<span data-ttu-id="74ba3-300">2</span><span class="sxs-lookup"><span data-stu-id="74ba3-300">2</span></span>         |
|<span data-ttu-id="74ba3-301">Дочернее подразделение</span><span class="sxs-lookup"><span data-stu-id="74ba3-301">Subsidiary</span></span>   |<span data-ttu-id="74ba3-302">Политика дочернего подразделения</span><span class="sxs-lookup"><span data-stu-id="74ba3-302">Subsidiary policy</span></span>        |<span data-ttu-id="74ba3-303">3</span><span class="sxs-lookup"><span data-stu-id="74ba3-303">3</span></span>        |

<span data-ttu-id="74ba3-304">В этом примере мы удаляем политику собраний Teams из группы.</span><span class="sxs-lookup"><span data-stu-id="74ba3-304">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="74ba3-305">Изменение назначения политики для группы</span><span class="sxs-lookup"><span data-stu-id="74ba3-305">Change a policy assignment for a group</span></span>

> [!NOTE]
> <span data-ttu-id="74ba3-306">В [ближайшее время появится cmdlet Set-CsGroupPolicyAssignment.](/powershell/module/teams/set-csgrouppolicyassignment)</span><span class="sxs-lookup"><span data-stu-id="74ba3-306">The [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) cmdlet will be available soon.</span></span> <span data-ttu-id="74ba3-307">Тем временем, чтобы изменить назначение групповой политики, вы можете удалить текущее назначение политики из группы, а затем добавить новое назначение политики.</span><span class="sxs-lookup"><span data-stu-id="74ba3-307">In the meantime, to change a group policy assignment, you can remove the current policy assignment from the group, and then add a new policy assignment.</span></span>

<span data-ttu-id="74ba3-308">После назначения политики группе вы можете изменить [](/powershell/module/teams/set-csgrouppolicyassignment) назначение политики этой группы с помощью следующим образом:</span><span class="sxs-lookup"><span data-stu-id="74ba3-308">After you assign a policy to a group, you can use the [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="74ba3-309">Изменение ранжирования</span><span class="sxs-lookup"><span data-stu-id="74ba3-309">Change the ranking</span></span>
- <span data-ttu-id="74ba3-310">Изменение политики для заданного типа политики</span><span class="sxs-lookup"><span data-stu-id="74ba3-310">Change the policy of a given policy type</span></span>
- <span data-ttu-id="74ba3-311">Изменение политики для заданного типа политики и ранжирования</span><span class="sxs-lookup"><span data-stu-id="74ba3-311">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="74ba3-312">В этом примере мы меняем политику в парке вызовов Teams на политику SupportCallPark и ранжирование назначений на 3.</span><span class="sxs-lookup"><span data-stu-id="74ba3-312">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="74ba3-313">Изменение эффективной политики для пользователя</span><span class="sxs-lookup"><span data-stu-id="74ba3-313">Change the effective policy for a user</span></span>

<span data-ttu-id="74ba3-314">Вот пример изменения эффективной политики для пользователя, которому непосредственно назначена политика.</span><span class="sxs-lookup"><span data-stu-id="74ba3-314">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="74ba3-315">Во-первых, мы используем командлет [Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment) вместе с параметром, чтобы получить сведения о политиках трансляции собраний Teams, связанных ```PolicySource``` с пользователем.</span><span class="sxs-lookup"><span data-stu-id="74ba3-315">First, we use the [Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment) cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="74ba3-316">В выходных данных видно, что пользователю напрямую назначена политика трансляции собраний Teams "События сотрудника", которая имеет приоритет над политикой "Мероприятия в жизни поставщика", назначенной группе, которой принадлежит пользователь.</span><span class="sxs-lookup"><span data-stu-id="74ba3-316">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="74ba3-317">Теперь мы удалим политику событий сотрудников для пользователя.</span><span class="sxs-lookup"><span data-stu-id="74ba3-317">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="74ba3-318">Это означает, что пользователю больше не назначена прямая политика трансляции собраний Teams, и он наследует политику "Поставщик Live Events", назначенную группе, которой принадлежит пользователь.</span><span class="sxs-lookup"><span data-stu-id="74ba3-318">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span>

<span data-ttu-id="74ba3-319">Для этого используйте следующий командлет в модуле Skype для бизнеса PowerShell:</span><span class="sxs-lookup"><span data-stu-id="74ba3-319">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="74ba3-320">Используйте следующий командлет в модуле Teams PowerShell, чтобы выполнять это в масштабе, хотя назначение пакетной политики$users где $users — это список пользователей, которых вы указали.</span><span class="sxs-lookup"><span data-stu-id="74ba3-320">Use following cmdlet in the Teams PowerShell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="74ba3-321">Назначение политики для пакета пользователей</span><span class="sxs-lookup"><span data-stu-id="74ba3-321">Assign a policy to a batch of users</span></span>

### <a name="use-the-admin-center"></a><span data-ttu-id="74ba3-322">Использование Центра администрирования</span><span class="sxs-lookup"><span data-stu-id="74ba3-322">Use the admin center</span></span>

<span data-ttu-id="74ba3-323">Чтобы массово назначить политику пользователям:</span><span class="sxs-lookup"><span data-stu-id="74ba3-323">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="74ba3-324">В левой области навигации Центра администрирования Microsoft Teams выберите **"Пользователи".**</span><span class="sxs-lookup"><span data-stu-id="74ba3-324">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="74ba3-325">Назначьте политику пользователям или отфильтруем представление, чтобы отфильтровать нужных пользователей.</span><span class="sxs-lookup"><span data-stu-id="74ba3-325">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="74ba3-326">В столбце **&#x2713;** (галочка) выберите пользователей.</span><span class="sxs-lookup"><span data-stu-id="74ba3-326">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="74ba3-327">Чтобы выбрать всех пользователей, щелкните &#x2713; (галочку) в верхней части таблицы.</span><span class="sxs-lookup"><span data-stu-id="74ba3-327">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="74ba3-328">Выберите **"Изменить параметры",** внесите нужные изменения и выберите "Применить". </span><span class="sxs-lookup"><span data-stu-id="74ba3-328">Select **Edit settings**, make the changes that you want, and then select **Apply**.</span></span>

<span data-ttu-id="74ba3-329">Чтобы просмотреть состояние назначения политики, на баннере, который  появляется в  верхней части страницы "Пользователи" после выбора "Применить" для отправки задания политики, выберите журнал **действий.**</span><span class="sxs-lookup"><span data-stu-id="74ba3-329">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you select **Apply** to submit your policy assignment, select **Activity log**.</span></span> <span data-ttu-id="74ba3-330">Или на панели навигации слева в Центре администрирования Microsoft Teams перейдите на панель **мониторинга,** а затем в журнале действий выберите "Просмотреть **сведения".**</span><span class="sxs-lookup"><span data-stu-id="74ba3-330">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, select **View details**.</span></span> <span data-ttu-id="74ba3-331">В журнале действий показаны назначения политик более чем 20 пользователям через Центр администрирования Microsoft Teams за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="74ba3-331">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="74ba3-332">Дополнительные данные см. в [журнале действий.](activity-log.md)</span><span class="sxs-lookup"><span data-stu-id="74ba3-332">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="use-powershell-method"></a><span data-ttu-id="74ba3-333">Использование метода PowerShell</span><span class="sxs-lookup"><span data-stu-id="74ba3-333">Use PowerShell method</span></span>

> [!NOTE]
> <span data-ttu-id="74ba3-334">В настоящее время пакетное назначение политики с помощью PowerShell доступно не для всех типов политик Teams.</span><span class="sxs-lookup"><span data-stu-id="74ba3-334">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="74ba3-335">Список поддерживаемых типов политик см. в [new-CsBatchPolicyAssignmentOperation.](/powershell/module/teams/new-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="74ba3-335">See [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>

<span data-ttu-id="74ba3-336">При назначении пакетной политики вы можете назначать политику большому набору пользователей одновременно, не пользуясь сценарием.</span><span class="sxs-lookup"><span data-stu-id="74ba3-336">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="74ba3-337">Для отправки пакета пользователей и политики, которую вы хотите назначить, используется cmdlet [New-CsBatchPolicyAssignmentOperation.](/powershell/module/teams/new-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="74ba3-337">You use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="74ba3-338">Задания будут обрабатываться в фоновом режиме, а для каждого пакета будет создан идентификатор операции.</span><span class="sxs-lookup"><span data-stu-id="74ba3-338">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="74ba3-339">Затем можно использовать для отслеживания хода выполнения и состояния назначений в пакете с помощью выполнения и выполнения задач [Get-CsBatchPolicyAssignmentOperation.](/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="74ba3-339">You can then use the [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="74ba3-340">Укажите пользователей по их ИД объекта или SIP-адресу.</span><span class="sxs-lookup"><span data-stu-id="74ba3-340">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="74ba3-341">SIP-адрес пользователя часто имеет то же значение, что и имя директора-пользователя (UPN) или адрес электронной почты, но это не требуется.</span><span class="sxs-lookup"><span data-stu-id="74ba3-341">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="74ba3-342">Если имя пользователя указано с помощью upN или электронной почты, но его значение отличается от SIP-адреса, назначение политики для пользователя не удастся.</span><span class="sxs-lookup"><span data-stu-id="74ba3-342">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="74ba3-343">Если пакет включает дубликатов пользователей, они будут удалены из пакета до обработки, а состояние будет предоставлено только для уникальных пользователей, оставшихся в пакете.</span><span class="sxs-lookup"><span data-stu-id="74ba3-343">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="74ba3-344">Пакет может содержать до 5 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="74ba3-344">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="74ba3-345">Для получения наилучших результатов не от отправьте несколько пакетов за один раз.</span><span class="sxs-lookup"><span data-stu-id="74ba3-345">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="74ba3-346">Разрешить обработку пакетам перед отправкой дополнительных пакетов.</span><span class="sxs-lookup"><span data-stu-id="74ba3-346">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-teams-powershell-module"></a><span data-ttu-id="74ba3-347">Установка и подключение к модуле Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="74ba3-347">Install and connect to the Teams PowerShell module</span></span>

<span data-ttu-id="74ba3-348">Чтобы установить модуль [Microsoft Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams)запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="74ba3-348">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="74ba3-349">Установите версию 1.0.5 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="74ba3-349">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="74ba3-350">Чтобы подключиться к Teams и начать сеанс, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="74ba3-350">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="74ba3-351">Когда вам будет предложено, войте учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="74ba3-351">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="74ba3-352">Установка и подключение к модуле Azure AD PowerShell для Graph (необязательно)</span><span class="sxs-lookup"><span data-stu-id="74ba3-352">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="74ba3-353">Вы также можете скачать и установить модуль [Azure AD PowerShell](/powershell/azure/active-directory/install-adv2) для Graph (если еще не сделали этого) и подключиться к Azure AD, чтобы получить список пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="74ba3-353">You might also want to [download and install the Azure AD PowerShell for Graph module](/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="74ba3-354">Чтобы подключиться к Azure AD, запустите следующую службу:</span><span class="sxs-lookup"><span data-stu-id="74ba3-354">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="74ba3-355">Когда вам будет предложено, вопишите с помощью учетных данных администратора, которые вы использовали для подключения к Teams.</span><span class="sxs-lookup"><span data-stu-id="74ba3-355">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-setup-policy-to-a-batch-of-users"></a><span data-ttu-id="74ba3-356">Назначение политики установки для пакета пользователей</span><span class="sxs-lookup"><span data-stu-id="74ba3-356">Assign a setup policy to a batch of users</span></span>

<span data-ttu-id="74ba3-357">В этом примере с помощью нового [csBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) назначим политику установки приложений с именем "Политика настройки приложений для отдела кадров" пакету пользователей, указанных в Users_ids.text файле.</span><span class="sxs-lookup"><span data-stu-id="74ba3-357">In this example, we use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="74ba3-358">В этом примере мы подключаемся к Azure AD, чтобы получить коллекцию пользователей, а затем назначаем политику обмена сообщениями с именем "Новая политика для обмена сообщениями о приеме на работу" пакету пользователей, заданным с помощью их SIP-адреса.</span><span class="sxs-lookup"><span data-stu-id="74ba3-358">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="74ba3-359">Состояние пакетного назначения</span><span class="sxs-lookup"><span data-stu-id="74ba3-359">Get the status of a batch assignment</span></span>

<span data-ttu-id="74ba3-360">Чтобы получить состояние пакета назначения, где OperationId — это код операции, возвращаемой этим cmdlet для данного пакета, запустите ```New-CsBatchPolicyAssignmentOperation``` следующую операцию:</span><span class="sxs-lookup"><span data-stu-id="74ba3-360">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="74ba3-361">Если в результате будет показана ошибка, запустите следующую статью, чтобы получить дополнительные сведения об ошибках, которые находятся в ```UserState``` свойстве.</span><span class="sxs-lookup"><span data-stu-id="74ba3-361">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="74ba3-362">Подробнее см. в [get-CsBatchPolicyAssignmentOperation.](/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="74ba3-362">To learn more, see [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-package-to-users"></a><span data-ttu-id="74ba3-363">Назначение пакета политики пользователям</span><span class="sxs-lookup"><span data-stu-id="74ba3-363">Assign a policy package to users</span></span>

<span data-ttu-id="74ba3-364">Пакет политики в Teams — это набор предопределельных политик и параметров политики, которые можно назначать пользователям с одинаковыми или похожими ролями в организации.</span><span class="sxs-lookup"><span data-stu-id="74ba3-364">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="74ba3-365">Каждый пакет политики предназначен для роли пользователя и содержит предопределные политики и параметры политики, которые поддерживают типичные для нее действия.</span><span class="sxs-lookup"><span data-stu-id="74ba3-365">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="74ba3-366">Примерами пакетов политики могут быть пакеты для образовательных учреждений (для преподавателей) и медицинских учреждений (клинические работники).</span><span class="sxs-lookup"><span data-stu-id="74ba3-366">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span> <span data-ttu-id="74ba3-367">Дополнительные узнать см. в [подмносях "Управление пакетами политики в Teams".](manage-policy-packages.md)</span><span class="sxs-lookup"><span data-stu-id="74ba3-367">To learn more, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="74ba3-368">Назначение пакета политики одному пользователю</span><span class="sxs-lookup"><span data-stu-id="74ba3-368">Assign a policy package to one user</span></span>

1. <span data-ttu-id="74ba3-369">В левой области навигации Центра администрирования Microsoft Teams перейдите в меню **"Пользователи"** и выберите пользователя.</span><span class="sxs-lookup"><span data-stu-id="74ba3-369">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="74ba3-370">На странице пользователя выберите "Политики", а затем рядом с пакетом политики **выберите** **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="74ba3-370">On the user's page, select **Policies**, and then next to **Policy package**, select **Edit**.</span></span>
3. <span data-ttu-id="74ba3-371">В области **назначения пакета политики** выберите пакет, который вы хотите назначить, и выберите **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="74ba3-371">In the **Assign policy package** pane, select the package you want to assign, and then select **Save**.</span></span>

### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="74ba3-372">Назначение пакета политики нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="74ba3-372">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="74ba3-373">В левой области навигации Центра администрирования Microsoft Teams перейдите к пакетам **политики,** а затем выберите пакет политики, который вы хотите назначить, щелкнув слева от его имени.</span><span class="sxs-lookup"><span data-stu-id="74ba3-373">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="74ba3-374">Выберите **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="74ba3-374">Select **Manage users**.</span></span>
3. <span data-ttu-id="74ba3-375">В области **Управление пользователями** выполните поиск по отображаемому имени или по имени пользователя, выберите имя и нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="74ba3-375">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="74ba3-376">Повторите это действие для каждого пользователя, которого нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="74ba3-376">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="74ba3-377">Завершив добавление пользователей, выберите **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="74ba3-377">When you're finished adding users, select **Save**.</span></span>

## <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="74ba3-378">Назначение пакета политики группе</span><span class="sxs-lookup"><span data-stu-id="74ba3-378">Assign a policy package to a group</span></span>

<span data-ttu-id="74ba3-379">Назначение пакетов политики группам позволяет назначать несколько политик группе пользователей, например группе безопасности или группе рассылки.</span><span class="sxs-lookup"><span data-stu-id="74ba3-379">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="74ba3-380">Назначение политики распространяется на участников группы в соответствии с правилами очередности.</span><span class="sxs-lookup"><span data-stu-id="74ba3-380">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="74ba3-381">При добавлении или удалении участников группы, назначения политик для них обновляются соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="74ba3-381">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="74ba3-382">Назначение пакетов политики группам рекомендуется для групп до 50 000 пользователей, но оно также будет работать с более крупными группами.</span><span class="sxs-lookup"><span data-stu-id="74ba3-382">Policy package assignment to groups is recommended for groups of up to 50,000 users, but it will also work with larger groups.</span></span>

<span data-ttu-id="74ba3-383">Когда вы назначаете пакет политики, он сразу же назначается группе.</span><span class="sxs-lookup"><span data-stu-id="74ba3-383">When you assign the policy package, it's immediately assigned to the group.</span></span> <span data-ttu-id="74ba3-384">Однако распространение назначения политики на участников группы выполняется в фоновом режиме и может занять некоторое время в зависимости от размера группы.</span><span class="sxs-lookup"><span data-stu-id="74ba3-384">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="74ba3-385">То же самое происходит, если политика не назначена группе, а также когда участники добавляются в группу или удаляются из нее.</span><span class="sxs-lookup"><span data-stu-id="74ba3-385">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="74ba3-386">Прежде чем начать, важно разобраться [](#precedence-rules) в правилах приоритета и ранжирования [заданий групп.](#group-assignment-ranking)</span><span class="sxs-lookup"><span data-stu-id="74ba3-386">Before you get started, it's important to understand [precedence rules](#precedence-rules) and [group assignment ranking](#group-assignment-ranking).</span></span> <span data-ttu-id="74ba3-387">Убедитесь, что вы читаете и понимаете понятия, которые необходимо знать о назначении политик группам ранее в этой статье. [](#what-you-need-to-know-about-policy-assignment-to-groups)</span><span class="sxs-lookup"><span data-stu-id="74ba3-387">Make sure you read and understand the concepts in [What you need to know about policy assignment to groups](#what-you-need-to-know-about-policy-assignment-to-groups) earlier in this article.</span></span>

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a><span data-ttu-id="74ba3-388">Назначение пакета политики группе пользователей в Центре администрирования</span><span class="sxs-lookup"><span data-stu-id="74ba3-388">Assign a policy package to a group of users in the admin center</span></span>

1. <span data-ttu-id="74ba3-389">Войдите в Центр администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="74ba3-389">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="74ba3-390">В области навигации слева перейдите на страницу пакета политики.</span><span class="sxs-lookup"><span data-stu-id="74ba3-390">In the left navigation, go to the policy package page.</span></span>
3. <span data-ttu-id="74ba3-391">Выберите вкладку назначения групповой политики.</span><span class="sxs-lookup"><span data-stu-id="74ba3-391">Select the Group policy assignment tab.</span></span>
4. <span data-ttu-id="74ba3-392">Выберите **"Добавить** группу", а затем в области "Назначение пакета политики группе" сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="74ba3-392">Select **Add group**, and then in the Assign a policy package to group pane, do the following:</span></span>

    <span data-ttu-id="74ba3-393">а)</span><span class="sxs-lookup"><span data-stu-id="74ba3-393">a.</span></span> <span data-ttu-id="74ba3-394">Найщите и добавьте группу, для нее нужно назначить пакет политики.</span><span class="sxs-lookup"><span data-stu-id="74ba3-394">Search for and add the group you want to assign the policy package to.</span></span>

    <span data-ttu-id="74ba3-395">б)</span><span class="sxs-lookup"><span data-stu-id="74ba3-395">b.</span></span> <span data-ttu-id="74ba3-396">Выберите пакет политики.</span><span class="sxs-lookup"><span data-stu-id="74ba3-396">Select a policy package.</span></span>

    <span data-ttu-id="74ba3-397">в.</span><span class="sxs-lookup"><span data-stu-id="74ba3-397">c.</span></span> <span data-ttu-id="74ba3-398">Заведите ранжирование для каждого типа политики.</span><span class="sxs-lookup"><span data-stu-id="74ba3-398">Set the ranking for each policy type.</span></span>

    <span data-ttu-id="74ba3-399">г.</span><span class="sxs-lookup"><span data-stu-id="74ba3-399">d.</span></span> <span data-ttu-id="74ba3-400">Выберите **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="74ba3-400">Select **Apply**.</span></span>

    ![показывает назначение групповой политики](media/group-pkg-assignment.png)

5. <span data-ttu-id="74ba3-402">Чтобы управлять ранжированием для определенного типа политики, перейдите на страницу политики.</span><span class="sxs-lookup"><span data-stu-id="74ba3-402">To manage ranking for a specific policy type, navigate to the specific policy page.</span></span>
6. <span data-ttu-id="74ba3-403">Чтобы перенананастить пакет политики группе, сначала удалите назначение групповой политики.</span><span class="sxs-lookup"><span data-stu-id="74ba3-403">To reassign a policy package to a group, first remove the group policy assignment.</span></span> <span data-ttu-id="74ba3-404">Затем следуйте этим шагам, чтобы назначить пакет политики группе.</span><span class="sxs-lookup"><span data-stu-id="74ba3-404">Then, follow the steps above to assign the policy package to a group.</span></span>

### <a name="work-with-powershell"></a><span data-ttu-id="74ba3-405">Работа с PowerShell</span><span class="sxs-lookup"><span data-stu-id="74ba3-405">Work with PowerShell</span></span>

#### <a name="get-the-teams-powershell-module"></a><span data-ttu-id="74ba3-406">Получить модуль Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="74ba3-406">Get the Teams PowerShell module</span></span>

<span data-ttu-id="74ba3-407">Пошаговую инструкцию см. в [руководстве по установке Teams PowerShell.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="74ba3-407">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-package-to-a-group-of-users"></a><span data-ttu-id="74ba3-408">Назначение пакета политики группе пользователей</span><span class="sxs-lookup"><span data-stu-id="74ba3-408">Assign a policy package to a group of users</span></span>

<span data-ttu-id="74ba3-409">Для назначения пакета политики группе используйте cmdlet [Grant-CsGroupPolicyPackageAssignment.](/powershell/module/teams/grant-csgrouppolicypackageassignment)</span><span class="sxs-lookup"><span data-stu-id="74ba3-409">Use the [Grant-CsGroupPolicyPackageAssignment](/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet to assign a policy package to a group.</span></span> <span data-ttu-id="74ba3-410">Группу можно указать с помощью ИД объекта, SIP-адреса или адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="74ba3-410">You can specify a group by using the object ID, SIP address, or email address.</span></span> <span data-ttu-id="74ba3-411">При назначении пакета политики [](#group-assignment-ranking) укажите ранжирование назначений группы для каждого типа политики в пакете политики.</span><span class="sxs-lookup"><span data-stu-id="74ba3-411">When you assign the policy package, specify a [group assignment ranking](#group-assignment-ranking) for each policy type in the policy package.</span></span>

<span data-ttu-id="74ba3-412">В этом примере пакет политики Education_Teacher назначается группе со ранжированием заданий 1 для TeamsAppSetupPolicy и TeamsMeetingBroadcastPolicy и 2 для TeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="74ba3-412">In this example, we assign the Education_Teacher policy package to a group with an assignment ranking of 1 for TeamsAppSetupPolicy and TeamsMeetingBroadcastPolicy and a ranking of 2 for TeamsMeetingPolicy.</span></span>

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="74ba3-413">Назначение пакета политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="74ba3-413">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="74ba3-414">При назначении пакетов пакетов политики вы можете назначать пакет политики большому набору пользователей одновременно, не пользуясь сценарием.</span><span class="sxs-lookup"><span data-stu-id="74ba3-414">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="74ba3-415">Для отправки пакета пользователей и пакета политики, который вы хотите назначить, используется cmdlet [New-CsBatchPolicyAssignmentOperation.](/powershell/module/teams/new-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="74ba3-415">You use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="74ba3-416">Задания будут обрабатываться в фоновом режиме, а для каждого пакета будет создан идентификатор операции.</span><span class="sxs-lookup"><span data-stu-id="74ba3-416">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="74ba3-417">Затем можно использовать для отслеживания хода выполнения и состояния назначений в пакете с помощью выполнения и выполнения задач [Get-CsBatchPolicyAssignmentOperation.](/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="74ba3-417">You can then use the [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="74ba3-418">Укажите пользователей по их ИД объекта или SIP-адресу.</span><span class="sxs-lookup"><span data-stu-id="74ba3-418">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="74ba3-419">SIP-адрес пользователя часто имеет то же значение, что и имя пользователя-пользователя (UPN) или адрес электронной почты, но это не требуется.</span><span class="sxs-lookup"><span data-stu-id="74ba3-419">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this isn't required.</span></span> <span data-ttu-id="74ba3-420">Если имя пользователя указано с помощью upN или электронной почты, но его значение отличается от SIP-адреса, назначение политики для пользователя не удастся.</span><span class="sxs-lookup"><span data-stu-id="74ba3-420">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="74ba3-421">Если пакет включает дубликатов пользователей, они будут удалены из пакета до обработки, а состояние будет предоставлено только для уникальных пользователей, оставшихся в пакете.</span><span class="sxs-lookup"><span data-stu-id="74ba3-421">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="74ba3-422">Пакет содержит до 5000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="74ba3-422">A batch contains up to 5,000 users.</span></span> <span data-ttu-id="74ba3-423">Для получения наилучших результатов не от отправьте несколько пакетов за один раз.</span><span class="sxs-lookup"><span data-stu-id="74ba3-423">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="74ba3-424">Разрешить обработку пакетам перед отправкой дополнительных пакетов.</span><span class="sxs-lookup"><span data-stu-id="74ba3-424">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="use-the-teams-powershell-module"></a><span data-ttu-id="74ba3-425">Использование модуля Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="74ba3-425">Use the Teams PowerShell module</span></span>

<span data-ttu-id="74ba3-426">Чтобы установить модуль [Microsoft Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams) запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="74ba3-426">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="74ba3-427">Установите версию 1.0.5 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="74ba3-427">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="74ba3-428">Чтобы подключиться к Teams и начать сеанс, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="74ba3-428">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="74ba3-429">Когда вам будет предложено, войте учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="74ba3-429">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-policy-packages-to-a-batch-of-users"></a><span data-ttu-id="74ba3-430">Назначение пакетов политики для пакета пользователей</span><span class="sxs-lookup"><span data-stu-id="74ba3-430">Assign policy packages to a batch of users</span></span>

<span data-ttu-id="74ba3-431">В этом примере с помощью Education_PrimaryStudent пакета политики [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) назначается пакет политики Education_PrimaryStudent пакету пользователей.</span><span class="sxs-lookup"><span data-stu-id="74ba3-431">In this example, we use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a><span data-ttu-id="74ba3-432">См. состояние пакетного назначения</span><span class="sxs-lookup"><span data-stu-id="74ba3-432">See the status of a batch assignment</span></span>

<span data-ttu-id="74ba3-433">Чтобы получить состояние пакета назначения, где OperationId — это код операции, возвращаемой этим cmdlet для данного пакета, запустите ```New-CsBatchPolicyAssignmentOperation``` следующую операцию:</span><span class="sxs-lookup"><span data-stu-id="74ba3-433">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="74ba3-434">Если в результате будет показана ошибка, запустите следующую статью, чтобы получить дополнительные сведения об ошибках, которые находятся в ```UserState``` свойстве.</span><span class="sxs-lookup"><span data-stu-id="74ba3-434">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="74ba3-435">Подробнее см. в [get-CsBatchPolicyAssignmentOperation.](/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="74ba3-435">To learn more, see [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="related-topics"></a><span data-ttu-id="74ba3-436">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="74ba3-436">Related topics</span></span>

[<span data-ttu-id="74ba3-437">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="74ba3-437">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)