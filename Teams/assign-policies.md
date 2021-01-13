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
ms.openlocfilehash: 5d213c53de22994d46e7d7faf54a8dfd687806d7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821309"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="bbc57-103">Назначение политик вашим пользователям в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bbc57-103">Assign policies to your users in Microsoft Teams</span></span>

<span data-ttu-id="bbc57-104">Администраторы используют политики для управления функциями Teams, доступными пользователям в организации.</span><span class="sxs-lookup"><span data-stu-id="bbc57-104">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="bbc57-105">Например, есть политики звонков, политики собраний и политики обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="bbc57-105">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="bbc57-106">В организациях есть различные типы пользователей с уникальными потребностями и настраиваемые политики, которые вы создаете и назначаете, позволяя настраивать параметры политики для разных наборов пользователей в зависимости от этих потребностей.</span><span class="sxs-lookup"><span data-stu-id="bbc57-106">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="bbc57-107">Чтобы упростить управление политиками в организации, Teams предлагает несколько способов назначить политики пользователям.</span><span class="sxs-lookup"><span data-stu-id="bbc57-107">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="bbc57-108">Политику можно назначать непосредственно пользователям (по отдельности или в масштабе с помощью пакетного назначения) или группе, в которую они в являются.</span><span class="sxs-lookup"><span data-stu-id="bbc57-108">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="bbc57-109">Вы также можете использовать пакеты политик, чтобы назначить предустановленную коллекцию политик пользователям с похожими ролями.</span><span class="sxs-lookup"><span data-stu-id="bbc57-109">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="bbc57-110">Выбор зависит от количества политик, которые вы управляете, и от количества пользователей, которых вы назначаете.</span><span class="sxs-lookup"><span data-stu-id="bbc57-110">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span> <span data-ttu-id="bbc57-111">Назначив глобальные политики (по умолчанию для всей организации), которые будут применяться к наибольшему числу пользователей в организации, достаточно назначить политики только тем пользователям, для кого требуются специализированные политики.</span><span class="sxs-lookup"><span data-stu-id="bbc57-111">By setting the global (Org-wide default) policies so that they apply to the largest number of users in your organization, you only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="bbc57-112">В этой статье описаны различные способы назначения политик пользователям и рекомендуемые сценарии использования.</span><span class="sxs-lookup"><span data-stu-id="bbc57-112">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="bbc57-113">Какая политика имеет приоритет?</span><span class="sxs-lookup"><span data-stu-id="bbc57-113">Which policy takes precedence?</span></span>

<span data-ttu-id="bbc57-114">У пользователя есть одна эффективная политика для каждого типа политики.</span><span class="sxs-lookup"><span data-stu-id="bbc57-114">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="bbc57-115">Вполне возможно и даже вероятно, что пользователю непосредственно назначена политика, а также она входит в одну или несколько групп, которые назначены политику того же типа.</span><span class="sxs-lookup"><span data-stu-id="bbc57-115">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="bbc57-116">Какая политика имеет приоритет в подобных сценариях?</span><span class="sxs-lookup"><span data-stu-id="bbc57-116">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="bbc57-117">Эффективная политика пользователя определяется согласно правилам приоритета.</span><span class="sxs-lookup"><span data-stu-id="bbc57-117">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="bbc57-118">Если пользователю непосредственно назначена политика (по отдельности или через пакетное назначение), она имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="bbc57-118">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="bbc57-119">В следующем примере эффективной политикой пользователя является политика собраний "По квадрату1", которая непосредственно назначена пользователю.</span><span class="sxs-lookup"><span data-stu-id="bbc57-119">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![Схема, показывающая приоритет непосредственно назначенной политики](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="bbc57-121">Если пользователю не назначена непосредственно политика заданного типа, политика, назначенная группе, в которую входит пользователь, имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="bbc57-121">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="bbc57-122">Если пользователь входит в несколько групп, приоритет имеет [](#group-assignment-ranking) политика с наивысшим ранжированием назначений для данного типа политики.</span><span class="sxs-lookup"><span data-stu-id="bbc57-122">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="bbc57-123">В этом примере эффективная политика пользователя — это политика Exec Teams и HD, которая имеет наивысший рейтинг назначений по сравнению с другими группами, участником которых является пользователь, и которым назначена политика того же типа политики.</span><span class="sxs-lookup"><span data-stu-id="bbc57-123">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![Схема, показывающая, как политика, наследуемая от группы, имеет приоритет](media/assign-policies-example-group.png)

<span data-ttu-id="bbc57-125">Если пользователю не назначена политика напрямую или он не входит в какие-либо группы, ему предоставляется глобальная политика (по умолчанию в организации).</span><span class="sxs-lookup"><span data-stu-id="bbc57-125">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="bbc57-126">Приведем пример.</span><span class="sxs-lookup"><span data-stu-id="bbc57-126">Here's an example.</span></span>

![Схема, показывающая приоритет глобальной политики](media/assign-policies-example-global.png)

<span data-ttu-id="bbc57-128">Дополнительные информации см. в [правилах приоритета.](#precedence-rules)</span><span class="sxs-lookup"><span data-stu-id="bbc57-128">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="bbc57-129">Способы назначения политик</span><span class="sxs-lookup"><span data-stu-id="bbc57-129">Ways to assign policies</span></span>

<span data-ttu-id="bbc57-130">Ниже представлен обзор способов назначения политик пользователям, а также рекомендуемых сценариев для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="bbc57-130">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="bbc57-131">Щелкните ссылки, чтобы узнать больше.</span><span class="sxs-lookup"><span data-stu-id="bbc57-131">Click the links to learn more.</span></span>

<span data-ttu-id="bbc57-132">Прежде чем назначать политики отдельным пользователям или группам, начните с настройки глобальных (по умолчанию [в организации)](#set-the-global-policies) политик, которые будут применяться к наибольшему числу пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="bbc57-132">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="bbc57-133">После того как будут настроены глобальные политики, вам потребуется назначить политики только тем пользователям, для кого требуются специализированные политики.</span><span class="sxs-lookup"><span data-stu-id="bbc57-133">Once the global policies are set, you will only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="bbc57-134">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="bbc57-134">Do this</span></span>  |<span data-ttu-id="bbc57-135">Если...</span><span class="sxs-lookup"><span data-stu-id="bbc57-135">If...</span></span>  | <span data-ttu-id="bbc57-136">Использование...</span><span class="sxs-lookup"><span data-stu-id="bbc57-136">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="bbc57-137">Назначение политики отдельным пользователям</span><span class="sxs-lookup"><span data-stu-id="bbc57-137">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="bbc57-138">Вы только начали работу в Teams или вам нужно назначить лишь одну или несколько политик небольшому количеству пользователей.</span><span class="sxs-lookup"><span data-stu-id="bbc57-138">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="bbc57-139">Центр администрирования Microsoft Teams или командлеты PowerShell в модуле Skype для бизнеса Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbc57-139">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
|[<span data-ttu-id="bbc57-140">Назначение политики группе</span><span class="sxs-lookup"><span data-stu-id="bbc57-140">Assign a policy to a group</span></span>](#assign-a-policy-to-a-group) |<span data-ttu-id="bbc57-141">Необходимо назначить политики, основанные на членстве пользователя в группах.</span><span class="sxs-lookup"><span data-stu-id="bbc57-141">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="bbc57-142">Например, вы хотите назначить политику всем пользователям в группе безопасности или списке рассылки.</span><span class="sxs-lookup"><span data-stu-id="bbc57-142">For example, you want to assign a policy to all users in a security group or distribution list.</span></span>| <span data-ttu-id="bbc57-143">Центр администрирования Microsoft Teams или командлеты PowerShell в модуле Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbc57-143">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="bbc57-144">Назначение политики для пакета пользователей</span><span class="sxs-lookup"><span data-stu-id="bbc57-144">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="bbc57-145">Политики необходимо назначать большим наборам пользователей.</span><span class="sxs-lookup"><span data-stu-id="bbc57-145">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="bbc57-146">Например, вы хотите назначить политику одновременно сотням или тысячам пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="bbc57-146">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="bbc57-147">Центр администрирования Microsoft Teams или командлеты PowerShell в модуле Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbc57-147">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="bbc57-148">Назначение пакета политики пользователям</span><span class="sxs-lookup"><span data-stu-id="bbc57-148">Assign a policy package to users</span></span>](#assign-a-policy-package-to-users)  | <span data-ttu-id="bbc57-149">Необходимо назначить несколько политик определенным наборам пользователей с одинаковыми или похожими ролями.</span><span class="sxs-lookup"><span data-stu-id="bbc57-149">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="bbc57-150">Например, назначьте пакет политики "Образование (преподаватель)" преподавателям в вашем учебном за учебных заведениях, чтобы предоставить им полный доступ к чатам, звонкам и собраниям, а также к пакету политики "Образование (дополнительное учебное заведения)", чтобы ограничить некоторые возможности, такие как частные вызовы.</span><span class="sxs-lookup"><span data-stu-id="bbc57-150">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="bbc57-151">Центр администрирования Microsoft Teams или командлеты PowerShell в модуле Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbc57-151">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="bbc57-152">[Назначение пакета политики группе (в](#assign-a-policy-package-to-a-group) режиме личной предварительной версии)</span><span class="sxs-lookup"><span data-stu-id="bbc57-152">[Assign a policy package to a group](#assign-a-policy-package-to-a-group) (in private preview)</span></span>   |<span data-ttu-id="bbc57-153">Группе пользователей с одинаковыми или похожими ролями необходимо назначить несколько политик.</span><span class="sxs-lookup"><span data-stu-id="bbc57-153">You need to assign multiple policies to a group of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="bbc57-154">Например, вы хотите назначить пакет политики всем пользователям в группе безопасности или списке рассылки.</span><span class="sxs-lookup"><span data-stu-id="bbc57-154">For example, you want to assign a policy package to all users in a security group or distribution list.</span></span> |<span data-ttu-id="bbc57-155">Центр администрирования Microsoft Teams (скоро появится) или командлеты PowerShell в модуле Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbc57-155">The Microsoft Teams admin center (coming soon) or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="bbc57-156">Назначение пакета политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="bbc57-156">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="bbc57-157">Необходимо назначить несколько политик для пакета пользователей в организации с одинаковыми или похожими ролями.</span><span class="sxs-lookup"><span data-stu-id="bbc57-157">You need to assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="bbc57-158">Например, назначьте пакет политики "Образование (преподаватель)" всем преподавателям в учебном за учебных заведениях с помощью пакетного задания, чтобы предоставить им полный доступ к чатам, звонкам и собраниям, и назначьте пакет политики "Образование (дополнительное учебное заведения)" пакету дополнительных учащихся, чтобы ограничить некоторые возможности, такие как частные вызовы.</span><span class="sxs-lookup"><span data-stu-id="bbc57-158">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings and assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities like private calling.</span></span>|<span data-ttu-id="bbc57-159">Командлеты PowerShell в модуле Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbc57-159">PowerShell cmdlets in the Teams PowerShell module</span></span>|


## <a name="set-the-global-policies"></a><span data-ttu-id="bbc57-160">Настройка глобальных политик</span><span class="sxs-lookup"><span data-stu-id="bbc57-160">Set the global policies</span></span>

<span data-ttu-id="bbc57-161">Выполните эти действия, чтобы настроить глобальные политики (по умолчанию в организации) для каждого типа политики.</span><span class="sxs-lookup"><span data-stu-id="bbc57-161">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="bbc57-162">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bbc57-162">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="bbc57-163">В левой области навигации Центра администрирования Microsoft Teams перейдите на страницу политики для типа политики, который вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="bbc57-163">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="bbc57-164">Например, политики **Teams** Teams, политики собраний для собраний, политики обмена сообщениями или политики  >     >   **голосовых**   >  **звонков.**</span><span class="sxs-lookup"><span data-stu-id="bbc57-164">For example, **Teams** > **Teams policies**, **Meetings** > **Meetings policies**, **Messaging policies**, or **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="bbc57-165">Выберите **глобальную политику (по умолчанию** для всей организации), чтобы просмотреть текущие параметры.</span><span class="sxs-lookup"><span data-stu-id="bbc57-165">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="bbc57-166">Обновив политику, выберите **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="bbc57-166">Update the policy as needed, and then select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="bbc57-167">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbc57-167">Using PowerShell</span></span>

<span data-ttu-id="bbc57-168">Чтобы настроить глобальные политики с помощью PowerShell, используйте глобальный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="bbc57-168">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="bbc57-169">Для начала просмотрите текущую глобальную политику, чтобы определить, какой параметр вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="bbc57-169">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

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

<span data-ttu-id="bbc57-170">Затем при необходимости обновим глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="bbc57-170">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="bbc57-171">Вам нужно только указать значения для параметров, которые вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="bbc57-171">You only need to specify values for the settings that you want to change.</span></span> 
 
```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="bbc57-172">Назначение политики отдельным пользователям</span><span class="sxs-lookup"><span data-stu-id="bbc57-172">Assign a policy to individual users</span></span>

<span data-ttu-id="bbc57-173">Выполните эти действия, чтобы назначить политику отдельному пользователю или небольшому числу пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="bbc57-173">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="bbc57-174">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bbc57-174">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="bbc57-175">Чтобы назначить политику пользователю:</span><span class="sxs-lookup"><span data-stu-id="bbc57-175">To assign a policy to a user:</span></span>

1. <span data-ttu-id="bbc57-176">В Центре администрирования Microsoft Teams в области навигации слева перейдите в раздел **Пользователи**, затем щелкните пользователя.</span><span class="sxs-lookup"><span data-stu-id="bbc57-176">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="bbc57-177">Выберите пользователя, щелкнув слева от его имени, затем нажмите кнопку **Изменить параметры**.</span><span class="sxs-lookup"><span data-stu-id="bbc57-177">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="bbc57-178">Выберите политику, а затем нажмите кнопку **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="bbc57-178">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="bbc57-179">Кроме того, вы можете сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="bbc57-179">Or, you can also do the following:</span></span>

1. <span data-ttu-id="bbc57-180">В левой области навигации Центра администрирования Microsoft Teams перейдите на страницу политики.</span><span class="sxs-lookup"><span data-stu-id="bbc57-180">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="bbc57-181">Выберите политику, которая вы хотите назначить, щелкнув слева от ее имени.</span><span class="sxs-lookup"><span data-stu-id="bbc57-181">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="bbc57-182">Выберите **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="bbc57-182">Select **Manage users**.</span></span>
4. <span data-ttu-id="bbc57-183">В области **Управление пользователями** выполните поиск по отображаемому имени или по имени пользователя, выберите имя и нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="bbc57-183">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="bbc57-184">Повторите это действие для каждого пользователя, которого нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="bbc57-184">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="bbc57-185">Завершив добавление пользователей, выберите **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="bbc57-185">When you're finished adding users, select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="bbc57-186">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbc57-186">Using PowerShell</span></span>

<span data-ttu-id="bbc57-187">У каждого типа политики есть собственный набор cmdlets для управления.</span><span class="sxs-lookup"><span data-stu-id="bbc57-187">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="bbc57-188">Используйте для назначения политики тот или иной тип ```Grant-``` политики с помощью cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bbc57-188">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="bbc57-189">Например, используйте ```Grant-CsTeamsMeetingPolicy``` командлет для назначения пользователям политики собраний Teams.</span><span class="sxs-lookup"><span data-stu-id="bbc57-189">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="bbc57-190">Эти командлеты включены в модуль Skype для бизнеса Online PowerShell и задокументированы в справочнике по [командлетам Skype для бизнеса.](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="bbc57-190">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="bbc57-191">Скачайте и установите модуль Skype для бизнеса [Online PowerShell](https://www.microsoft.com/download/details.aspx?id=39366) (если вы еще этого не сделали), а затем запустите следующую командную запись, чтобы подключиться к Skype для бизнеса Online и начать сеанс:</span><span class="sxs-lookup"><span data-stu-id="bbc57-191">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

> [!NOTE]
> <span data-ttu-id="bbc57-192">Соединитель Skype для бизнеса Online сейчас входит в состав последнего модуля Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bbc57-192">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="bbc57-193">Если вы используете последний общедоступный выпуск [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="bbc57-193">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
Import-Module -Name MicrosoftTeams
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="bbc57-194">В этом примере мы назначаем политику собраний Teams "Политика собраний учащихся" пользователю Reda.</span><span class="sxs-lookup"><span data-stu-id="bbc57-194">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="bbc57-195">Для получения дополнительных информации [ознакомьтесь с управлением политиками с помощью PowerShell.](teams-powershell-managing-teams.md#manage-policies-via-powershell)</span><span class="sxs-lookup"><span data-stu-id="bbc57-195">To learn more, read [Manage policies via PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="bbc57-196">Назначение политики группе</span><span class="sxs-lookup"><span data-stu-id="bbc57-196">Assign a policy to a group</span></span>

<span data-ttu-id="bbc57-197">Назначение политик группам позволяет назначить политику группе пользователей, например группе безопасности или списку рассылки.</span><span class="sxs-lookup"><span data-stu-id="bbc57-197">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="bbc57-198">Назначение политики распространяется на участников группы в соответствии с правилами очередности.</span><span class="sxs-lookup"><span data-stu-id="bbc57-198">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="bbc57-199">При добавлении или удалении участников группы, назначения политик для них обновляются соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="bbc57-199">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="bbc57-200">Назначение политик группам рекомендуется для групп до 50 000 пользователей, но оно также будет работать с более крупными группами.</span><span class="sxs-lookup"><span data-stu-id="bbc57-200">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="bbc57-201">Назначенная политика сразу же назначается группе.</span><span class="sxs-lookup"><span data-stu-id="bbc57-201">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="bbc57-202">Однако имейте в виду, что распространение назначения политики на участников группы выполняется в фоновом режиме и может занять некоторое время в зависимости от размера группы.</span><span class="sxs-lookup"><span data-stu-id="bbc57-202">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="bbc57-203">То же самое происходит, если политика не назначена группе, а также когда участники добавляются в группу или удаляются из нее.</span><span class="sxs-lookup"><span data-stu-id="bbc57-203">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

<span data-ttu-id="bbc57-204">Назначения групповой политики распространяются только на пользователей, которые являются прямыми участниками группы.</span><span class="sxs-lookup"><span data-stu-id="bbc57-204">Group policy assignments are only propagated to users that are direct members of the group.</span></span> <span data-ttu-id="bbc57-205">Назначения не распространяются на участников вложенных групп.</span><span class="sxs-lookup"><span data-stu-id="bbc57-205">The assignments aren't propagated to members of nested groups.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="bbc57-206">Что нужно знать о назначении политик группам</span><span class="sxs-lookup"><span data-stu-id="bbc57-206">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="bbc57-207">Прежде чем начать, важно разобраться в правилах приоритета и ранжирования заданий групп.</span><span class="sxs-lookup"><span data-stu-id="bbc57-207">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="bbc57-208">Правила приоритета</span><span class="sxs-lookup"><span data-stu-id="bbc57-208">Precedence rules</span></span>

<span data-ttu-id="bbc57-209">Для данного типа политики эффективная политика пользователя определяется в соответствии со следующими данными:</span><span class="sxs-lookup"><span data-stu-id="bbc57-209">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="bbc57-210">Политика, которая непосредственно назначена пользователю, имеет приоритет над любой другой политикой того же типа, которая назначена группе.</span><span class="sxs-lookup"><span data-stu-id="bbc57-210">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="bbc57-211">Другими словами, если пользователю непосредственно назначена политика заданного типа, он не наследует политику того же типа от группы.</span><span class="sxs-lookup"><span data-stu-id="bbc57-211">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="bbc57-212">Это также означает, что если пользователю назначена политика заданного типа, необходимо удалить ее, прежде чем он сможет наследовать политику того же типа из группы.</span><span class="sxs-lookup"><span data-stu-id="bbc57-212">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="bbc57-213">Если пользователю не назначена политика напрямую и он входит в несколько групп и каждой группе назначена политика одного и того же типа, то пользователь наследует политику назначения группы с наивысшим рейтингом.</span><span class="sxs-lookup"><span data-stu-id="bbc57-213">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="bbc57-214">Если пользователь не входит в группы, для каких-либо групп назначена политика, к этому типу политики применяется глобальная политика (по умолчанию в организации).</span><span class="sxs-lookup"><span data-stu-id="bbc57-214">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="bbc57-215">При добавлении пользователя в группу, назначенной политике или удалении из нее, политика не назначена группе или политика, которая непосредственно назначена пользователю, обновляется согласно этим правилам.</span><span class="sxs-lookup"><span data-stu-id="bbc57-215">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="bbc57-216">Ранжирование назначений групп</span><span class="sxs-lookup"><span data-stu-id="bbc57-216">Group assignment ranking</span></span>
 
<span data-ttu-id="bbc57-217">При назначении политики группе вы указываете ранжирование для назначения группы.</span><span class="sxs-lookup"><span data-stu-id="bbc57-217">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="bbc57-218">Этот способ используется для определения политики, которая должна наследоваться пользователем как эффективная политика, если пользователь входит в несколько групп и каждой группе назначена политика одного типа.</span><span class="sxs-lookup"><span data-stu-id="bbc57-218">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="bbc57-219">Ранжирование групповых заданий относительно назначений других групп того же типа.</span><span class="sxs-lookup"><span data-stu-id="bbc57-219">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="bbc57-220">Например, если политика звонков назначается двум группам, узначьте ранжирование одному заданию 1, а другому — 2, причем 1 — самый высокий.</span><span class="sxs-lookup"><span data-stu-id="bbc57-220">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="bbc57-221">Ранжирование назначений групп показывает, какие из них более важны или релевантны, чем другие группы в отношении наследования.</span><span class="sxs-lookup"><span data-stu-id="bbc57-221">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="bbc57-222">Например, у вас есть две группы: "Сотрудники магазинов" и "Руководители магазинов".</span><span class="sxs-lookup"><span data-stu-id="bbc57-222">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="bbc57-223">Обе группы имеют политику звонков Teams, политику звонков сотрудников магазина и политику звонков диспетчеров магазинов соответственно.</span><span class="sxs-lookup"><span data-stu-id="bbc57-223">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="bbc57-224">Для руководителя магазина, который относится к обеим группам, его роль руководителя больше релевантна, чем его роль в качестве сотрудника, поэтому политика звонков, назначенная группе "Руководители магазинов", должна иметь более высокий рейтинг.</span><span class="sxs-lookup"><span data-stu-id="bbc57-224">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="bbc57-225">Группа</span><span class="sxs-lookup"><span data-stu-id="bbc57-225">Group</span></span> |<span data-ttu-id="bbc57-226">Название политики звонков Teams</span><span class="sxs-lookup"><span data-stu-id="bbc57-226">Teams calling policy name</span></span>  |<span data-ttu-id="bbc57-227">Rank (Ранг)</span><span class="sxs-lookup"><span data-stu-id="bbc57-227">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="bbc57-228">Руководители магазинов</span><span class="sxs-lookup"><span data-stu-id="bbc57-228">Store Managers</span></span>   |<span data-ttu-id="bbc57-229">Политика звонков для руководителей магазинов</span><span class="sxs-lookup"><span data-stu-id="bbc57-229">Store Managers Calling Policy</span></span>         |<span data-ttu-id="bbc57-230">1</span><span class="sxs-lookup"><span data-stu-id="bbc57-230">1</span></span>|
|<span data-ttu-id="bbc57-231">Сотрудники магазина</span><span class="sxs-lookup"><span data-stu-id="bbc57-231">Store Employees</span></span>    |<span data-ttu-id="bbc57-232">Политика звонков сотрудников магазина</span><span class="sxs-lookup"><span data-stu-id="bbc57-232">Store Employees Calling Policy</span></span>      |<span data-ttu-id="bbc57-233">2</span><span class="sxs-lookup"><span data-stu-id="bbc57-233">2</span></span>|

<span data-ttu-id="bbc57-234">Если не указать ранжирование, назначение политики будет присвоено наименьшему ранжирование.</span><span class="sxs-lookup"><span data-stu-id="bbc57-234">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span> 

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="bbc57-235">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bbc57-235">Using the Microsoft Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="bbc57-236">В настоящее время назначение политик группам с помощью Центра администрирования Microsoft Teams доступно только для политик звонков Teams, политики в парке звонков Teams, политики Teams, политики трансляций Teams, политики собраний Teams и политики обмена сообщениями Teams.</span><span class="sxs-lookup"><span data-stu-id="bbc57-236">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="bbc57-237">Для других типов политик используйте PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bbc57-237">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="bbc57-238">В левой области навигации Центра администрирования Microsoft Teams перейдите на страницу типа политики.</span><span class="sxs-lookup"><span data-stu-id="bbc57-238">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="bbc57-239">Например, перейдите к **политикам**  >  **собраний собраний.**</span><span class="sxs-lookup"><span data-stu-id="bbc57-239">For example, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="bbc57-240">Выберите **вкладку назначения групповой политики.**</span><span class="sxs-lookup"><span data-stu-id="bbc57-240">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="bbc57-241">Выберите **"Добавить группу",** а затем в области "Назначение политики группе" сделайте следующее: </span><span class="sxs-lookup"><span data-stu-id="bbc57-241">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="bbc57-242">Наищите и добавьте группу, для нее нужно назначить политику.</span><span class="sxs-lookup"><span data-stu-id="bbc57-242">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="bbc57-243">Задание ранжирования для группового назначения.</span><span class="sxs-lookup"><span data-stu-id="bbc57-243">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="bbc57-244">Выберите политику, которую вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="bbc57-244">Select the policy that you want to assign.</span></span> 
    4. <span data-ttu-id="bbc57-245">Выберите **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="bbc57-245">Select **Apply**.</span></span>

<span data-ttu-id="bbc57-246">Чтобы удалить назначение групповой  политики, на вкладке назначения групповой политики на странице политики выберите назначение группы и выберите **"Удалить".**</span><span class="sxs-lookup"><span data-stu-id="bbc57-246">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="bbc57-247">Чтобы изменить ранжирование для группового назначения, необходимо сначала удалить назначение групповой политики.</span><span class="sxs-lookup"><span data-stu-id="bbc57-247">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="bbc57-248">Затем следуйте этим шагам, чтобы назначить политику группе.</span><span class="sxs-lookup"><span data-stu-id="bbc57-248">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="bbc57-249">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbc57-249">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="bbc57-250">В настоящее время назначение политик группам с помощью PowerShell доступно не для всех типов политик Teams.</span><span class="sxs-lookup"><span data-stu-id="bbc57-250">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="bbc57-251">Список поддерживаемых типов политик см. в списке [New-CsGroupPolicyAssignment.](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)</span><span class="sxs-lookup"><span data-stu-id="bbc57-251">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="bbc57-252">Установка и подключение к модуле Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbc57-252">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="bbc57-253">Пошаговую инструкцию см. в [руководстве по установке Teams PowerShell.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="bbc57-253">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-to-a-group-of-users"></a><span data-ttu-id="bbc57-254">Назначение политики группе пользователей</span><span class="sxs-lookup"><span data-stu-id="bbc57-254">Assign a policy to a group of users</span></span>

<span data-ttu-id="bbc57-255">Для назначения политики группе используется [cmdlet New-CsGroupPolicyAssignment.](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)</span><span class="sxs-lookup"><span data-stu-id="bbc57-255">You use the [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="bbc57-256">Группу можно указать с помощью ИД объекта, SIP-адреса или адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="bbc57-256">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="bbc57-257">В этом примере мы назначаем политику собраний Teams "Политика собраний розничных менеджеров" группе со ранжированием заданий 1.</span><span class="sxs-lookup"><span data-stu-id="bbc57-257">In this example, we assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="bbc57-258">Получать назначения политик для группы</span><span class="sxs-lookup"><span data-stu-id="bbc57-258">Get policy assignments for a group</span></span>

<span data-ttu-id="bbc57-259">Для получения всех политик, которые назначены группе, используйте [cmdlet Get-CsGroupPolicyAssignment.](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment)</span><span class="sxs-lookup"><span data-stu-id="bbc57-259">Use the [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="bbc57-260">Обратите внимание, что группы всегда перечисляются по их ИД, даже если для назначения политики использовался ее SIP-адрес или адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="bbc57-260">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="bbc57-261">В этом примере мы извлекаем все политики, которые назначены определенной группе.</span><span class="sxs-lookup"><span data-stu-id="bbc57-261">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="bbc57-262">В этом примере возвращаются все группы, которые имеют политику собраний Teams.</span><span class="sxs-lookup"><span data-stu-id="bbc57-262">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="bbc57-263">Удаление политики из группы</span><span class="sxs-lookup"><span data-stu-id="bbc57-263">Remove a policy from a group</span></span>

<span data-ttu-id="bbc57-264">Чтобы удалить политику из группы, [используйте cmdlet Remove-CsGroupPolicyAssignment.](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment)</span><span class="sxs-lookup"><span data-stu-id="bbc57-264">Use the [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="bbc57-265">При этом приоритеты других политик того же типа, которые имеют более низкий рейтинг, обновляются.</span><span class="sxs-lookup"><span data-stu-id="bbc57-265">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="bbc57-266">Например, если удалить политику со ранжированием 2, политики с ранжированием 3 и 4 будут обновлены с учетом нового ранжирования.</span><span class="sxs-lookup"><span data-stu-id="bbc57-266">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="bbc57-267">В следующих двух таблицах приводится пример.</span><span class="sxs-lookup"><span data-stu-id="bbc57-267">The following two tables show this example.</span></span>

<span data-ttu-id="bbc57-268">Вот список назначений и приоритетов политики собраний Teams.</span><span class="sxs-lookup"><span data-stu-id="bbc57-268">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="bbc57-269">Имя группы</span><span class="sxs-lookup"><span data-stu-id="bbc57-269">Group name</span></span>  |<span data-ttu-id="bbc57-270">Название политики</span><span class="sxs-lookup"><span data-stu-id="bbc57-270">Policy name</span></span>  |<span data-ttu-id="bbc57-271">Rank (Ранг)</span><span class="sxs-lookup"><span data-stu-id="bbc57-271">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="bbc57-272">Продажи</span><span class="sxs-lookup"><span data-stu-id="bbc57-272">Sales</span></span>    |<span data-ttu-id="bbc57-273">Политика продаж</span><span class="sxs-lookup"><span data-stu-id="bbc57-273">Sales policy</span></span>       | <span data-ttu-id="bbc57-274">1</span><span class="sxs-lookup"><span data-stu-id="bbc57-274">1</span></span>        |
|<span data-ttu-id="bbc57-275">Западная область</span><span class="sxs-lookup"><span data-stu-id="bbc57-275">West Region</span></span>     |<span data-ttu-id="bbc57-276">Политика западного региона</span><span class="sxs-lookup"><span data-stu-id="bbc57-276">West Region policy</span></span>         |<span data-ttu-id="bbc57-277">2</span><span class="sxs-lookup"><span data-stu-id="bbc57-277">2</span></span>         |
|<span data-ttu-id="bbc57-278">Деление</span><span class="sxs-lookup"><span data-stu-id="bbc57-278">Division</span></span>    |<span data-ttu-id="bbc57-279">Политика деления</span><span class="sxs-lookup"><span data-stu-id="bbc57-279">Division policy</span></span>         |<span data-ttu-id="bbc57-280">3</span><span class="sxs-lookup"><span data-stu-id="bbc57-280">3</span></span>         |
|<span data-ttu-id="bbc57-281">Дочернее подразделение</span><span class="sxs-lookup"><span data-stu-id="bbc57-281">Subsidiary</span></span>   |<span data-ttu-id="bbc57-282">Политика дочернего подразделения</span><span class="sxs-lookup"><span data-stu-id="bbc57-282">Subsidiary policy</span></span>        |<span data-ttu-id="bbc57-283">4</span><span class="sxs-lookup"><span data-stu-id="bbc57-283">4</span></span>         |

<span data-ttu-id="bbc57-284">Если удалить политику западного региона из группы "Запад региона", назначения и приоритеты политики обновляются следующим образом.</span><span class="sxs-lookup"><span data-stu-id="bbc57-284">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="bbc57-285">Имя группы</span><span class="sxs-lookup"><span data-stu-id="bbc57-285">Group name</span></span>  |<span data-ttu-id="bbc57-286">Название политики</span><span class="sxs-lookup"><span data-stu-id="bbc57-286">Policy name</span></span>  |<span data-ttu-id="bbc57-287">Rank (Ранг)</span><span class="sxs-lookup"><span data-stu-id="bbc57-287">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="bbc57-288">Продажи</span><span class="sxs-lookup"><span data-stu-id="bbc57-288">Sales</span></span>    |<span data-ttu-id="bbc57-289">Политика продаж</span><span class="sxs-lookup"><span data-stu-id="bbc57-289">Sales policy</span></span>       | <span data-ttu-id="bbc57-290">1</span><span class="sxs-lookup"><span data-stu-id="bbc57-290">1</span></span>        |
|<span data-ttu-id="bbc57-291">Деление</span><span class="sxs-lookup"><span data-stu-id="bbc57-291">Division</span></span>    |<span data-ttu-id="bbc57-292">Политика деления</span><span class="sxs-lookup"><span data-stu-id="bbc57-292">Division policy</span></span>         |<span data-ttu-id="bbc57-293">2</span><span class="sxs-lookup"><span data-stu-id="bbc57-293">2</span></span>         |
|<span data-ttu-id="bbc57-294">Дочернее подразделение</span><span class="sxs-lookup"><span data-stu-id="bbc57-294">Subsidiary</span></span>   |<span data-ttu-id="bbc57-295">Политика дочернего подразделения</span><span class="sxs-lookup"><span data-stu-id="bbc57-295">Subsidiary policy</span></span>        |<span data-ttu-id="bbc57-296">3</span><span class="sxs-lookup"><span data-stu-id="bbc57-296">3</span></span>        |

<span data-ttu-id="bbc57-297">В этом примере мы удаляем политику собраний Teams из группы.</span><span class="sxs-lookup"><span data-stu-id="bbc57-297">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="bbc57-298">Изменение назначения политики для группы</span><span class="sxs-lookup"><span data-stu-id="bbc57-298">Change a policy assignment for a group</span></span>

> [!NOTE]
> <span data-ttu-id="bbc57-299">В [ближайшее время появится cmdlet Set-CsGroupPolicyAssignment.](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment)</span><span class="sxs-lookup"><span data-stu-id="bbc57-299">The [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet will be available soon.</span></span> <span data-ttu-id="bbc57-300">Тем временем, чтобы изменить назначение групповой политики, вы можете удалить текущее назначение политики из группы, а затем добавить новое назначение политики.</span><span class="sxs-lookup"><span data-stu-id="bbc57-300">In the meantime, to change a group policy assignment, you can remove the current policy assignment from the group, and then add a new policy assignment.</span></span>

<span data-ttu-id="bbc57-301">После назначения политики группе вы можете изменить [](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) назначение политики этой группы с помощью следующим образом:</span><span class="sxs-lookup"><span data-stu-id="bbc57-301">After you assign a policy to a group, you can use the [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="bbc57-302">Изменение ранжирования</span><span class="sxs-lookup"><span data-stu-id="bbc57-302">Change the ranking</span></span>
- <span data-ttu-id="bbc57-303">Изменение политики для заданного типа политики</span><span class="sxs-lookup"><span data-stu-id="bbc57-303">Change the policy of a given policy type</span></span>
- <span data-ttu-id="bbc57-304">Изменение политики для заданного типа политики и ранжирования</span><span class="sxs-lookup"><span data-stu-id="bbc57-304">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="bbc57-305">В этом примере мы меняем политику парка вызовов Teams на политику SupportCallPark и ранжирование назначений на 3.</span><span class="sxs-lookup"><span data-stu-id="bbc57-305">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="bbc57-306">Изменение эффективной политики для пользователя</span><span class="sxs-lookup"><span data-stu-id="bbc57-306">Change the effective policy for a user</span></span>

<span data-ttu-id="bbc57-307">Вот пример изменения эффективной политики для пользователя, которому непосредственно назначена политика.</span><span class="sxs-lookup"><span data-stu-id="bbc57-307">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="bbc57-308">Во-первых, мы используем командлет [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) вместе с параметром, чтобы получить сведения о политиках трансляции собраний Teams, связанных ```PolicySource``` с пользователем.</span><span class="sxs-lookup"><span data-stu-id="bbc57-308">First, we use the [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> 

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="bbc57-309">В выходных данных видно, что пользователю напрямую назначена политика трансляции собраний Teams "События сотрудника", которая имеет приоритет над политикой "Мероприятия Поставщика Live Events", назначенной группе, которой принадлежит пользователь.</span><span class="sxs-lookup"><span data-stu-id="bbc57-309">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="bbc57-310">Теперь мы удалим политику событий сотрудников для пользователя.</span><span class="sxs-lookup"><span data-stu-id="bbc57-310">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="bbc57-311">Это означает, что пользователю больше не назначена прямая политика трансляции собраний Teams, и он наследует политику "Поставщик Live Events", назначенную группе, которой принадлежит пользователь.</span><span class="sxs-lookup"><span data-stu-id="bbc57-311">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="bbc57-312">Для этого используйте следующий командлет в модуле Skype для бизнеса PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bbc57-312">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="bbc57-313">Вы можете использовать следующий командлет в модуле Teams PowerShell, чтобы выполнять это задание в масштабе, хотя назначение пакетной политики$users где $users — это список пользователей, которые вы указали.</span><span class="sxs-lookup"><span data-stu-id="bbc57-313">You can use following cmdlet in the Teams PowerShell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="bbc57-314">Назначение политики для пакета пользователей</span><span class="sxs-lookup"><span data-stu-id="bbc57-314">Assign a policy to a batch of users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="bbc57-315">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bbc57-315">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="bbc57-316">Чтобы массово назначить политику пользователям:</span><span class="sxs-lookup"><span data-stu-id="bbc57-316">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="bbc57-317">В левой области навигации Центра администрирования Microsoft Teams выберите **"Пользователи".**</span><span class="sxs-lookup"><span data-stu-id="bbc57-317">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="bbc57-318">Назначьте политику пользователям или отфильтруем представление, чтобы отфильтровать их.</span><span class="sxs-lookup"><span data-stu-id="bbc57-318">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="bbc57-319">В столбце **&#x2713;** (галочка) выберите пользователей.</span><span class="sxs-lookup"><span data-stu-id="bbc57-319">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="bbc57-320">Чтобы выбрать всех пользователей, щелкните &#x2713; (галочку) в верхней части таблицы.</span><span class="sxs-lookup"><span data-stu-id="bbc57-320">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="bbc57-321">Щелкните **Изменить настройки**, внесите нужные изменения и нажмите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="bbc57-321">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="bbc57-322">Чтобы просмотреть состояние назначения политики, на баннере, который  появляется в  верхней части страницы "Пользователи" после нажатия кнопки "Применить", чтобы отправить назначение политики, щелкните журнал **действий.**</span><span class="sxs-lookup"><span data-stu-id="bbc57-322">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you click **Apply** to submit your policy assignment, click **Activity log**.</span></span> <span data-ttu-id="bbc57-323">Или в левой области навигации Центра администрирования Microsoft Teams перейдите на панель **мониторинга,** а затем в журнале действий щелкните "Просмотреть **сведения".**</span><span class="sxs-lookup"><span data-stu-id="bbc57-323">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, click **View details**.</span></span> <span data-ttu-id="bbc57-324">В журнале действий показаны назначения политик более чем 20 пользователям через Центр администрирования Microsoft Teams за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="bbc57-324">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="bbc57-325">Дополнительные данные см. в [журнале действий.](activity-log.md)</span><span class="sxs-lookup"><span data-stu-id="bbc57-325">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="bbc57-326">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbc57-326">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="bbc57-327">В настоящее время пакетное назначение политики с помощью PowerShell доступно не для всех типов политик Teams.</span><span class="sxs-lookup"><span data-stu-id="bbc57-327">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="bbc57-328">Список поддерживаемых типов политик см. в [new-CsBatchPolicyAssignmentOperation.](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="bbc57-328">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>
 
<span data-ttu-id="bbc57-329">При назначении пакетной политики вы можете назначать политику большому набору пользователей одновременно, не пользуясь сценарием.</span><span class="sxs-lookup"><span data-stu-id="bbc57-329">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="bbc57-330">Для отправки пакета пользователей и политики, которую вы хотите назначить, используется cmdlet [New-CsBatchPolicyAssignmentOperation.](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="bbc57-330">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="bbc57-331">Задания будут обрабатываться в фоновом режиме, а для каждого пакета будет создан идентификатор операции.</span><span class="sxs-lookup"><span data-stu-id="bbc57-331">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="bbc57-332">Затем можно использовать для отслеживания хода выполнения и состояния назначений в пакете с помощью выполнения и выполнения задач [Get-CsBatchPolicyAssignmentOperation.](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="bbc57-332">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="bbc57-333">Вы можете указать пользователей по их ИД объекта или SIP-адресу.</span><span class="sxs-lookup"><span data-stu-id="bbc57-333">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="bbc57-334">Обратите внимание, что SIP-адрес пользователя часто имеет то же значение, что и имя директора-пользователя (UPN) или адрес электронной почты, но это не требуется.</span><span class="sxs-lookup"><span data-stu-id="bbc57-334">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="bbc57-335">Если имя пользователя указано с помощью upN или электронной почты, но его значение отличается от SIP-адреса, назначение политики для пользователя не удастся.</span><span class="sxs-lookup"><span data-stu-id="bbc57-335">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="bbc57-336">Если пакет включает дублирующихся пользователей, повторяющиеся записи удаляются из пакета до обработки, а состояние будет предоставлено только для уникальных пользователей, оставшихся в пакете.</span><span class="sxs-lookup"><span data-stu-id="bbc57-336">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="bbc57-337">Пакет может содержать до 5 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="bbc57-337">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="bbc57-338">Для получения наилучших результатов не от отправьте несколько пакетов за один раз.</span><span class="sxs-lookup"><span data-stu-id="bbc57-338">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="bbc57-339">Разрешить обработку пакетов перед отправкой дополнительных пакетов.</span><span class="sxs-lookup"><span data-stu-id="bbc57-339">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="bbc57-340">Установка и подключение к модуле Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbc57-340">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="bbc57-341">Чтобы установить модуль [Microsoft Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams)запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bbc57-341">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="bbc57-342">Установите версию 1.0.5 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="bbc57-342">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="bbc57-343">Чтобы подключиться к Teams и начать сеанс, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bbc57-343">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="bbc57-344">Когда вам будет предложено, войте учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="bbc57-344">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="bbc57-345">Установка и подключение к модуле Azure AD PowerShell для Graph (необязательно)</span><span class="sxs-lookup"><span data-stu-id="bbc57-345">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="bbc57-346">Вы также можете скачать и установить модуль [Azure AD PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) для Graph (если еще не сделали этого) и подключиться к Azure AD, чтобы получить список пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="bbc57-346">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="bbc57-347">Чтобы подключиться к Azure AD, запустите следующую службу:</span><span class="sxs-lookup"><span data-stu-id="bbc57-347">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="bbc57-348">Когда вам будет предложено, вопишите с помощью учетных данных администратора, которые вы использовали для подключения к Teams.</span><span class="sxs-lookup"><span data-stu-id="bbc57-348">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="bbc57-349">Назначение политики для пакета пользователей</span><span class="sxs-lookup"><span data-stu-id="bbc57-349">Assign a policy to a batch of users</span></span>

<span data-ttu-id="bbc57-350">В этом примере с помощью нового [csBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) назначим политику установки приложений с именем "Политика настройки приложений для управления персоналом" пакету пользователей, указанных в Users_ids.text файле.</span><span class="sxs-lookup"><span data-stu-id="bbc57-350">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="bbc57-351">В этом примере мы подключаемся к Azure AD, чтобы получить коллекцию пользователей, а затем назначаем политику обмена сообщениями с именем "Новая политика для обмена сообщениями о приеме на работу" пакету пользователей, заданным с помощью их SIP-адреса.</span><span class="sxs-lookup"><span data-stu-id="bbc57-351">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="bbc57-352">Состояние пакетного назначения</span><span class="sxs-lookup"><span data-stu-id="bbc57-352">Get the status of a batch assignment</span></span>

<span data-ttu-id="bbc57-353">Чтобы получить состояние пакетного назначения, где OperationId — это код операции, возвращаемой этим cmdlet для данного ```New-CsBatchPolicyAssignmentOperation``` пакета:</span><span class="sxs-lookup"><span data-stu-id="bbc57-353">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="bbc57-354">Если в выходных данных показана ошибка, запустите следующую, чтобы получить дополнительные сведения об ошибках, которые находятся в ```UserState``` свойстве:</span><span class="sxs-lookup"><span data-stu-id="bbc57-354">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="bbc57-355">Подробнее см. в [get-CsBatchPolicyAssignmentOperation.](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="bbc57-355">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-package-to-users"></a><span data-ttu-id="bbc57-356">Назначение пакета политики пользователям</span><span class="sxs-lookup"><span data-stu-id="bbc57-356">Assign a policy package to users</span></span>

<span data-ttu-id="bbc57-357">Пакет политики в Teams — это набор предопределельных политик и параметров политики, которые можно назначать пользователям с одинаковыми или похожими ролями в организации.</span><span class="sxs-lookup"><span data-stu-id="bbc57-357">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="bbc57-358">Каждый пакет политики предназначен для роли пользователя и содержит предопределять политики и параметры политики, которые поддерживают типичные для нее действия.</span><span class="sxs-lookup"><span data-stu-id="bbc57-358">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="bbc57-359">Примерами пакетов политики могут быть пакеты для образовательных учреждений (для преподавателей) и медицинских учреждений (клинические работники).</span><span class="sxs-lookup"><span data-stu-id="bbc57-359">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span> <span data-ttu-id="bbc57-360">Дополнительные узнать см. в [подмносях "Управление пакетами политики в Teams".](manage-policy-packages.md)</span><span class="sxs-lookup"><span data-stu-id="bbc57-360">To learn more, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="bbc57-361">Назначение пакета политики одному пользователю</span><span class="sxs-lookup"><span data-stu-id="bbc57-361">Assign a policy package to one user</span></span>

1. <span data-ttu-id="bbc57-362">В Центре администрирования Microsoft Teams в области навигации слева перейдите в раздел **Пользователи**, затем щелкните пользователя.</span><span class="sxs-lookup"><span data-stu-id="bbc57-362">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="bbc57-363">На странице пользователя щелкните **"Политики",** а затем рядом с пакетом политики **выберите**"Изменить". </span><span class="sxs-lookup"><span data-stu-id="bbc57-363">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="bbc57-364">В области **назначения пакета политики** выберите пакет, который вы хотите назначить, и нажмите кнопку **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="bbc57-364">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="bbc57-365">Назначение пакета политики нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="bbc57-365">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="bbc57-366">В левой области навигации Центра администрирования Microsoft Teams перейдите к пакетам **политики,** а затем выберите пакет политики, который вы хотите назначить, щелкнув слева от его имени.</span><span class="sxs-lookup"><span data-stu-id="bbc57-366">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="bbc57-367">Щелкните **"Управление пользователями".**</span><span class="sxs-lookup"><span data-stu-id="bbc57-367">Click **Manage users**.</span></span>
3. <span data-ttu-id="bbc57-368">В области **Управление пользователями** выполните поиск по отображаемому имени или по имени пользователя, выберите имя и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="bbc57-368">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="bbc57-369">Повторите это действие для каждого пользователя, которого нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="bbc57-369">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="bbc57-370">Завершив добавление пользователей, нажмите кнопку **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="bbc57-370">When you're finished adding users, click **Save**.</span></span>

## <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="bbc57-371">Назначение пакета политики группе</span><span class="sxs-lookup"><span data-stu-id="bbc57-371">Assign a policy package to a group</span></span>

<span data-ttu-id="bbc57-372">**Эта функция доступна в закрытой ознакомительной версии**</span><span class="sxs-lookup"><span data-stu-id="bbc57-372">**This feature is in private preview**</span></span>

<span data-ttu-id="bbc57-373">Назначение пакетов политики группам позволяет назначать несколько политик группе пользователей, например группе безопасности или группе рассылки.</span><span class="sxs-lookup"><span data-stu-id="bbc57-373">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="bbc57-374">Назначение политики распространяется на участников группы в соответствии с правилами очередности.</span><span class="sxs-lookup"><span data-stu-id="bbc57-374">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="bbc57-375">При добавлении или удалении участников группы, назначения политик для них обновляются соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="bbc57-375">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="bbc57-376">Назначение пакетов политики группам рекомендуется для групп до 50 000 пользователей, но оно также будет работать с более крупными группами.</span><span class="sxs-lookup"><span data-stu-id="bbc57-376">Policy package assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span> 

<span data-ttu-id="bbc57-377">Когда вы назначаете пакет политики, он сразу же назначается группе.</span><span class="sxs-lookup"><span data-stu-id="bbc57-377">When you assign the policy package, it's immediately assigned to the group.</span></span> <span data-ttu-id="bbc57-378">Однако имейте в виду, что распространение назначения политики на участников группы выполняется в фоновом режиме и может занять некоторое время в зависимости от размера группы.</span><span class="sxs-lookup"><span data-stu-id="bbc57-378">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="bbc57-379">То же самое происходит, если политика не назначена группе, а также когда участники добавляются в группу или удаляются из нее.</span><span class="sxs-lookup"><span data-stu-id="bbc57-379">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bbc57-380">Прежде чем начать, важно разобраться [](#precedence-rules) в правилах приоритета и ранжирования [заданий групп.](#group-assignment-ranking)</span><span class="sxs-lookup"><span data-stu-id="bbc57-380">Before you get started, it's important to understand [precedence rules](#precedence-rules) and [group assignment ranking](#group-assignment-ranking).</span></span> <span data-ttu-id="bbc57-381">Убедитесь, что вы читаете и понимаете понятия, которые необходимо знать о назначении политик группам ранее в этой статье. [](#what-you-need-to-know-about-policy-assignment-to-groups)</span><span class="sxs-lookup"><span data-stu-id="bbc57-381">Make sure you read and understand the concepts in [What you need to know about policy assignment to groups](#what-you-need-to-know-about-policy-assignment-to-groups) earlier in this article.</span></span>

### <a name="using-the-microsoft-teams-admin-center-coming-soon"></a><span data-ttu-id="bbc57-382">Использование Центра администрирования Microsoft Teams (скоро появится)</span><span class="sxs-lookup"><span data-stu-id="bbc57-382">Using the Microsoft Teams admin center (coming soon)</span></span>

<span data-ttu-id="bbc57-383">Назначение пакета политики группам в Центре администрирования Microsoft Teams будет в ближайшее время.</span><span class="sxs-lookup"><span data-stu-id="bbc57-383">Policy package assignment to groups in the Microsoft Teams admin center is coming soon.</span></span> <span data-ttu-id="bbc57-384">Последние обновления вы можете посмотреть здесь.</span><span class="sxs-lookup"><span data-stu-id="bbc57-384">Check back here for the latest updates.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="bbc57-385">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbc57-385">Using PowerShell</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="bbc57-386">Установка и подключение к модуле Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbc57-386">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="bbc57-387">Пошаговую инструкцию см. в [руководстве по установке Teams PowerShell.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="bbc57-387">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-package-to-a-group-of-users"></a><span data-ttu-id="bbc57-388">Назначение пакета политики группе пользователей</span><span class="sxs-lookup"><span data-stu-id="bbc57-388">Assign a policy package to a group of users</span></span>

<span data-ttu-id="bbc57-389">Для назначения пакета политики группе используется cmdlet [Grant-CsGroupPolicyPackageAssignment.](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment)</span><span class="sxs-lookup"><span data-stu-id="bbc57-389">You use the [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet to assign a policy package to a group.</span></span> <span data-ttu-id="bbc57-390">Группу можно указать с помощью ИД объекта, SIP-адреса или адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="bbc57-390">You can specify a group by using the object Id, SIP address, or email address.</span></span> <span data-ttu-id="bbc57-391">При назначении пакета политики [](#group-assignment-ranking) укажите ранжирование назначений группы для каждого типа политики в пакете политики.</span><span class="sxs-lookup"><span data-stu-id="bbc57-391">When you assign the policy package, specify a [group assignment ranking](#group-assignment-ranking) for each policy type in the policy package.</span></span> 

<span data-ttu-id="bbc57-392">В этом примере пакет политики Education_Teacher назначается группе со ранжированием заданий 1 для TeamsAppSetupPolicy и TeamsMeetingBroadcastPolicy и 2 для TeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="bbc57-392">In this example, we assign the Education_Teacher policy package to a group with an assignment ranking of 1 for TeamsAppSetupPolicy and TeamsMeetingBroadcastPolicy and a ranking of 2 for TeamsMeetingPolicy.</span></span>

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="bbc57-393">Назначение пакета политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="bbc57-393">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="bbc57-394">При назначении пакетов пакетов политики вы можете назначать пакет политики большому набору пользователей одновременно, не пользуясь сценарием.</span><span class="sxs-lookup"><span data-stu-id="bbc57-394">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="bbc57-395">Для отправки пакета пользователей и пакета политики, который вы хотите назначить, используется cmdlet [New-CsBatchPolicyAssignmentOperation.](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="bbc57-395">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="bbc57-396">Задания будут обрабатываться в фоновом режиме, а для каждого пакета будет создан идентификатор операции.</span><span class="sxs-lookup"><span data-stu-id="bbc57-396">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="bbc57-397">Затем можно использовать для отслеживания хода выполнения и состояния назначений в пакете с помощью выполнения и выполнения задач [Get-CsBatchPolicyAssignmentOperation.](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="bbc57-397">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="bbc57-398">Вы можете указать пользователей по их ИД объекта или SIP-адресу.</span><span class="sxs-lookup"><span data-stu-id="bbc57-398">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="bbc57-399">Обратите внимание, что SIP-адрес пользователя часто имеет то же значение, что и имя директора-пользователя (UPN) или адрес электронной почты, но это не требуется.</span><span class="sxs-lookup"><span data-stu-id="bbc57-399">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="bbc57-400">Если имя пользователя указано с помощью upN или электронной почты, но его значение отличается от SIP-адреса, назначение политики для пользователя не удастся.</span><span class="sxs-lookup"><span data-stu-id="bbc57-400">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="bbc57-401">Если пакет включает дублирующихся пользователей, повторяющиеся записи удаляются из пакета до обработки, а состояние будет предоставлено только для уникальных пользователей, оставшихся в пакете.</span><span class="sxs-lookup"><span data-stu-id="bbc57-401">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="bbc57-402">Пакет может содержать до 5 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="bbc57-402">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="bbc57-403">Для получения наилучших результатов не от отправьте несколько пакетов за один раз.</span><span class="sxs-lookup"><span data-stu-id="bbc57-403">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="bbc57-404">Разрешить обработку пакетов перед отправкой дополнительных пакетов.</span><span class="sxs-lookup"><span data-stu-id="bbc57-404">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="bbc57-405">Установка и подключение к модуле Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbc57-405">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="bbc57-406">Чтобы установить модуль [Microsoft Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams) запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bbc57-406">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="bbc57-407">Установите версию 1.0.5 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="bbc57-407">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="bbc57-408">Чтобы подключиться к Teams и начать сеанс, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bbc57-408">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="bbc57-409">Когда вам будет предложено, войте учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="bbc57-409">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="bbc57-410">Назначение пакета политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="bbc57-410">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="bbc57-411">В этом примере с помощью Education_PrimaryStudent пакета политики [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) назначается пакет политики Education_PrimaryStudent пакету пользователей.</span><span class="sxs-lookup"><span data-stu-id="bbc57-411">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="bbc57-412">Состояние пакетного назначения</span><span class="sxs-lookup"><span data-stu-id="bbc57-412">Get the status of a batch assignment</span></span>

<span data-ttu-id="bbc57-413">Чтобы получить состояние пакетного назначения, где OperationId — это код операции, возвращаемой этим cmdlet для данного ```New-CsBatchPolicyAssignmentOperation``` пакета:</span><span class="sxs-lookup"><span data-stu-id="bbc57-413">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="bbc57-414">Если в выходных данных показана ошибка, запустите следующую, чтобы получить дополнительные сведения об ошибках, которые находятся в ```UserState``` свойстве:</span><span class="sxs-lookup"><span data-stu-id="bbc57-414">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="bbc57-415">Подробнее см. в [get-CsBatchPolicyAssignmentOperation.](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="bbc57-415">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="bbc57-416">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="bbc57-416">Related topics</span></span>

[<span data-ttu-id="bbc57-417">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="bbc57-417">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
