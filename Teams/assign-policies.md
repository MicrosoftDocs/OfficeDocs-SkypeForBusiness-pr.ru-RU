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
ms.openlocfilehash: 05ed811c38b3f49e21933d575c82128360ca3390
ms.sourcegitcommit: 3840d72f9ad1c0c7803dc3662a0318f558fe92ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739719"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="8886f-103">Назначение политик вашим пользователям в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8886f-103">Assign policies to your users in Microsoft Teams</span></span>

<span data-ttu-id="8886f-104">Администраторы используют политики для управления функциями Teams, доступными пользователям в организации.</span><span class="sxs-lookup"><span data-stu-id="8886f-104">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="8886f-105">Например, существуют политики звонков, политики собраний и политики обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="8886f-105">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="8886f-106">В организациях есть разные типы пользователей с уникальными потребностями.</span><span class="sxs-lookup"><span data-stu-id="8886f-106">Organizations have different types of users with unique needs.</span></span> <span data-ttu-id="8886f-107">Настраиваемые политики, которые вы создаете и назначаете, могут настраивать параметры политики для различных наборов пользователей с учетом этих потребностей.</span><span class="sxs-lookup"><span data-stu-id="8886f-107">Custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="8886f-108">Чтобы легко управлять политиками в организации, Teams предлагает несколько способов назначить политики пользователям.</span><span class="sxs-lookup"><span data-stu-id="8886f-108">To easily manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="8886f-109">Назначьте политику непосредственно пользователям (по отдельности или в масштабе с помощью пакетного назначения) или группе, в которую пользователи являются участниками.</span><span class="sxs-lookup"><span data-stu-id="8886f-109">Assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="8886f-110">Пакеты политик также можно использовать для назначения предварительно заранее задав набор политик для пользователей с похожими ролями.</span><span class="sxs-lookup"><span data-stu-id="8886f-110">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="8886f-111">Выбор параметра зависит от количества политик, которые вы управляете, и от количества пользователей, которых вы назначаете.</span><span class="sxs-lookup"><span data-stu-id="8886f-111">The option that you choose depends on the number of policies that you're managing and the number of users you're assigning policies to.</span></span> <span data-ttu-id="8886f-112">Глобальные политики (по умолчанию для всей организации) применяются к наибольшему числу пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="8886f-112">Global (Org-wide default) policies apply to the largest number of users in your organization.</span></span> <span data-ttu-id="8886f-113">Назначать политики нужно только тем пользователям, для кого требуются специализированные политики.</span><span class="sxs-lookup"><span data-stu-id="8886f-113">You only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="8886f-114">В этой статье описаны различные способы назначения политик пользователям и рекомендуемые сценарии использования.</span><span class="sxs-lookup"><span data-stu-id="8886f-114">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="8886f-115">Какая политика имеет приоритет?</span><span class="sxs-lookup"><span data-stu-id="8886f-115">Which policy takes precedence?</span></span>

<span data-ttu-id="8886f-116">У пользователя есть одна эффективная политика для каждого типа политики.</span><span class="sxs-lookup"><span data-stu-id="8886f-116">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="8886f-117">Возможно, или даже вероятно, что пользователю напрямую назначена политика, а также он входит в одну или несколько групп, которые назначены политике того же типа.</span><span class="sxs-lookup"><span data-stu-id="8886f-117">It's possible, or even likely, that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="8886f-118">В таких сценариях какая политика имеет приоритет?</span><span class="sxs-lookup"><span data-stu-id="8886f-118">In these kinds of scenarios, which policy takes precedence?</span></span> <span data-ttu-id="8886f-119">Эффективная политика пользователя определяется согласно правилам приоритета.</span><span class="sxs-lookup"><span data-stu-id="8886f-119">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="8886f-120">Если пользователю непосредственно назначена политика (по отдельности или с помощью пакетного назначения), она имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="8886f-120">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="8886f-121">В следующем наглядном примере эффективной политикой пользователя является политика собраний "Квадрат По квадрату", которая непосредственно назначена пользователю.</span><span class="sxs-lookup"><span data-stu-id="8886f-121">In the following visual example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![Схема, показывающая приоритет непосредственно назначенной политики](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="8886f-123">Если пользователю не назначена политика заданного типа, приоритет имеет политика, назначенная группе, участником какой-либо из них является пользователь.</span><span class="sxs-lookup"><span data-stu-id="8886f-123">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="8886f-124">Если пользователь входит в несколько групп, приоритет имеет [](#group-assignment-ranking) политика с наивысшим ранжированием назначения для данного типа политики.</span><span class="sxs-lookup"><span data-stu-id="8886f-124">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="8886f-125">В этом наглядном примере эффективной политикой пользователя является политика Exec Teams и HD, которая имеет наивысший рейтинг назначения по отношению к другим группам, участником которых является пользователь, и которым назначена политика того же типа политики.</span><span class="sxs-lookup"><span data-stu-id="8886f-125">In this visual example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![Схема, показывающая, как политика, наследуемая от группы, имеет приоритет](media/assign-policies-example-group.png)

<span data-ttu-id="8886f-127">Если пользователю не назначена политика напрямую или он не является участником какой-либо группы, ему предоставляется глобальная политика (по умолчанию в организации) для этого типа политики.</span><span class="sxs-lookup"><span data-stu-id="8886f-127">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="8886f-128">Вот наглядный пример.</span><span class="sxs-lookup"><span data-stu-id="8886f-128">Here's a visual example.</span></span>

![Схема, показывающая, как глобальная политика имеет приоритет](media/assign-policies-example-global.png)

<span data-ttu-id="8886f-130">Дополнительные узнать см. в [оке Правила приоритета.](#precedence-rules)</span><span class="sxs-lookup"><span data-stu-id="8886f-130">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="8886f-131">Способы назначения политик</span><span class="sxs-lookup"><span data-stu-id="8886f-131">Ways to assign policies</span></span>

<span data-ttu-id="8886f-132">Ниже представлен обзор способов назначения политик пользователям и рекомендуемых сценариев для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="8886f-132">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="8886f-133">Выберите ссылки, чтобы узнать больше.</span><span class="sxs-lookup"><span data-stu-id="8886f-133">Select the links to learn more.</span></span>

<span data-ttu-id="8886f-134">Прежде чем назначать политики отдельным пользователям или группам, сначала задайте глобальные [(стандартные)](#set-the-global-policies) политики для всей организации, чтобы они применялись к наибольшему числу пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="8886f-134">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="8886f-135">После того как глобальные политики будут настроены, вам потребуется назначить политики только тем пользователям, для кого требуются специализированные политики.</span><span class="sxs-lookup"><span data-stu-id="8886f-135">Once the global policies are set, you'll only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="8886f-136">Сделайте это</span><span class="sxs-lookup"><span data-stu-id="8886f-136">Do this</span></span>  |<span data-ttu-id="8886f-137">Если...</span><span class="sxs-lookup"><span data-stu-id="8886f-137">If...</span></span>  | <span data-ttu-id="8886f-138">Используя...</span><span class="sxs-lookup"><span data-stu-id="8886f-138">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="8886f-139">Назначение политики отдельным пользователям</span><span class="sxs-lookup"><span data-stu-id="8886f-139">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="8886f-140">Вы только Teams и только начинаете работу или вам нужно назначить одну или несколько политик небольшому количеству пользователей.</span><span class="sxs-lookup"><span data-stu-id="8886f-140">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="8886f-141">Командлеты Microsoft Teams или PowerShell в модуле Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="8886f-141">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>
|[<span data-ttu-id="8886f-142">Назначение политики группе</span><span class="sxs-lookup"><span data-stu-id="8886f-142">Assign a policy to a group</span></span>](#assign-a-policy-to-a-group) |<span data-ttu-id="8886f-143">Назначать политики на основе участия пользователя в группах.</span><span class="sxs-lookup"><span data-stu-id="8886f-143">Assign policies based on a user's group membership.</span></span> <span data-ttu-id="8886f-144">Например, назначьте политику всем пользователям в группе безопасности или списке рассылки.</span><span class="sxs-lookup"><span data-stu-id="8886f-144">For example, assign a policy to all users in a security group or distribution list.</span></span>| <span data-ttu-id="8886f-145">Командлеты Microsoft Teams или PowerShell в модуле Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="8886f-145">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="8886f-146">Назначение политики для пакета пользователей</span><span class="sxs-lookup"><span data-stu-id="8886f-146">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="8886f-147">Назначьте политики большому набору пользователей.</span><span class="sxs-lookup"><span data-stu-id="8886f-147">Assign policies to large sets of users.</span></span> <span data-ttu-id="8886f-148">Например, назначьте политику сотням или тысячам пользователей организации за один раз.</span><span class="sxs-lookup"><span data-stu-id="8886f-148">For example, assign a policy to hundreds or thousands of users in your organization at a time.</span></span> |<span data-ttu-id="8886f-149">Командлеты Microsoft Teams или PowerShell в модуле Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="8886f-149">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="8886f-150">Назначение пакета политики пользователям</span><span class="sxs-lookup"><span data-stu-id="8886f-150">Assign a policy package to users</span></span>](#assign-a-policy-package-to-users)  |<span data-ttu-id="8886f-151">Назначьте несколько политик определенным наборам пользователей в организации с одинаковыми или похожими ролями.</span><span class="sxs-lookup"><span data-stu-id="8886f-151">Assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="8886f-152">Например, назначьте пакет политики образования (преподаватель) преподавателям в вашем учебном за учебных заведениях, чтобы предоставить им полный доступ к чатам, звонкам и собраниям.</span><span class="sxs-lookup"><span data-stu-id="8886f-152">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings.</span></span> <span data-ttu-id="8886f-153">Назначьте пакет политики для образовательных звонков (дополнительного учебного заведения) дополнительным учащимся, чтобы ограничить некоторые возможности, например частные вызовы.</span><span class="sxs-lookup"><span data-stu-id="8886f-153">Assign the Education (Secondary school student) policy package to secondary students to limit certain capabilities such as private calling.</span></span>  |<span data-ttu-id="8886f-154">Командлеты Microsoft Teams или PowerShell в модуле Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="8886f-154">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="8886f-155">[Назначение пакета политики группе](#assign-a-policy-package-to-a-group) (в закрытой предварительной версии)</span><span class="sxs-lookup"><span data-stu-id="8886f-155">[Assign a policy package to a group](#assign-a-policy-package-to-a-group) (in private preview)</span></span>   |<span data-ttu-id="8886f-156">Назначьте несколько политик группе пользователей в организации с одинаковыми или похожими ролями.</span><span class="sxs-lookup"><span data-stu-id="8886f-156">Assign multiple policies to a group of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="8886f-157">Например, назначьте пакет политики всем пользователям в группе безопасности или списке рассылки.</span><span class="sxs-lookup"><span data-stu-id="8886f-157">For example, assign a policy package to all users in a security group or distribution list.</span></span> |<span data-ttu-id="8886f-158">Центр Microsoft Teams (скоро) или командлеты PowerShell в модуле Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="8886f-158">The Microsoft Teams admin center (coming soon) or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="8886f-159">Назначение пакета политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="8886f-159">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="8886f-160">Назначьте несколько политик для нескольких пользователей организации с одинаковыми или похожими ролями.</span><span class="sxs-lookup"><span data-stu-id="8886f-160">Assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="8886f-161">Например, назначьте пакет политики Образования (преподаватель) всем преподавателям в учебном замещаемом наборе с помощью пакетного задания, чтобы предоставить им полный доступ к чатам, звонкам и собраниям.</span><span class="sxs-lookup"><span data-stu-id="8886f-161">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings.</span></span> <span data-ttu-id="8886f-162">Назначьте пакет политики образования (учащемуся дополнительного образования) пакету дополнительных учащихся, чтобы ограничить некоторые возможности, например частные вызовы.</span><span class="sxs-lookup"><span data-stu-id="8886f-162">Assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities such as private calling.</span></span>|<span data-ttu-id="8886f-163">Командлеты PowerShell в модуле Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="8886f-163">PowerShell cmdlets in the Teams PowerShell module</span></span>|

## <a name="set-the-global-policies"></a><span data-ttu-id="8886f-164">Настройка глобальных политик</span><span class="sxs-lookup"><span data-stu-id="8886f-164">Set the global policies</span></span>

<span data-ttu-id="8886f-165">Выполните эти действия, чтобы настроить глобальные политики (по умолчанию в организации) для каждого типа политики.</span><span class="sxs-lookup"><span data-stu-id="8886f-165">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="8886f-166">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8886f-166">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="8886f-167">В левой области навигации центра администрирования Microsoft Teams перейдите на страницу политики для типа политики, который вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="8886f-167">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="8886f-168">Например, Teams Teams, политики собраний собраний, политики обмена сообщениями или политики  >     >   **голосовых**   >  **звонков**.</span><span class="sxs-lookup"><span data-stu-id="8886f-168">For example, **Teams** > **Teams policies**, **Meetings** > **Meetings policies**, **Messaging policies**, or **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="8886f-169">Выберите **глобальную политику (по** умолчанию в организации), чтобы просмотреть текущие параметры.</span><span class="sxs-lookup"><span data-stu-id="8886f-169">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="8886f-170">Обновив политику, выберите **применить**.</span><span class="sxs-lookup"><span data-stu-id="8886f-170">Update the policy as needed, and then select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="8886f-171">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="8886f-171">Using PowerShell</span></span>

<span data-ttu-id="8886f-172">Чтобы настроить глобальные политики с помощью PowerShell, используйте глобальный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="8886f-172">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="8886f-173">Сначала просмотрите текущую глобальную политику, чтобы определить, какой параметр вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="8886f-173">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

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

<span data-ttu-id="8886f-174">Затем при необходимости обновим глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="8886f-174">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="8886f-175">Вам нужно указать только значения для параметров, которые вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="8886f-175">You only need to specify values for the settings that you want to change.</span></span>

```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="8886f-176">Назначение политики отдельным пользователям</span><span class="sxs-lookup"><span data-stu-id="8886f-176">Assign a policy to individual users</span></span>

<span data-ttu-id="8886f-177">Чтобы назначить политику отдельному пользователю или небольшому числу пользователей одновременно, выполните указанные здесь действия.</span><span class="sxs-lookup"><span data-stu-id="8886f-177">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="use-the-microsoft-teams-admin-center"></a><span data-ttu-id="8886f-178">Использование центра Microsoft Teams администрирования</span><span class="sxs-lookup"><span data-stu-id="8886f-178">Use the Microsoft Teams admin center</span></span>

<span data-ttu-id="8886f-179">Чтобы назначить политику пользователю:</span><span class="sxs-lookup"><span data-stu-id="8886f-179">To assign a policy to a user:</span></span>

1. <span data-ttu-id="8886f-180">В левой области навигации центра администрирования Microsoft Teams перейдите **в** меню Пользователи и выберите пользователя.</span><span class="sxs-lookup"><span data-stu-id="8886f-180">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="8886f-181">Выберите пользователя, щелкнув слева от его имени и выбрав изменить **параметры**.</span><span class="sxs-lookup"><span data-stu-id="8886f-181">Select the user by clicking to the left of the user name, and then select **Edit settings**.</span></span>
3. <span data-ttu-id="8886f-182">Выберите политику, которая вы хотите назначить, и выберите **применить**.</span><span class="sxs-lookup"><span data-stu-id="8886f-182">Select the policy you want to assign, and then select **Apply**.</span></span>

<span data-ttu-id="8886f-183">Кроме того, можно сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="8886f-183">Or, you can also do the following:</span></span>

1. <span data-ttu-id="8886f-184">В левой области навигации центра администрирования Microsoft Teams перейдите на страницу политики.</span><span class="sxs-lookup"><span data-stu-id="8886f-184">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="8886f-185">Выберите политику, которая вы хотите назначить, щелкнув слева от ее имени.</span><span class="sxs-lookup"><span data-stu-id="8886f-185">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="8886f-186">Выберите **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="8886f-186">Select **Manage users**.</span></span>
4. <span data-ttu-id="8886f-187">В области **Управление пользователями** выполните поиск по отображаемому имени или по имени пользователя, выберите имя и нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="8886f-187">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="8886f-188">Повторите это действие для каждого пользователя, которого нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="8886f-188">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="8886f-189">Завершив добавление пользователей, выберите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="8886f-189">When you're finished adding users, select **Apply**.</span></span>

### <a name="use-powershell"></a><span data-ttu-id="8886f-190">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="8886f-190">Use PowerShell</span></span>

<span data-ttu-id="8886f-191">У каждого типа политики есть собственный набор cmdlets для управления.</span><span class="sxs-lookup"><span data-stu-id="8886f-191">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="8886f-192">Используйте для назначения политики тот или иной ```Grant-``` тип.</span><span class="sxs-lookup"><span data-stu-id="8886f-192">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="8886f-193">Например, используйте его для назначения пользователям политики Teams ```Grant-CsTeamsMeetingPolicy``` собраний.</span><span class="sxs-lookup"><span data-stu-id="8886f-193">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="8886f-194">Эти командлеты включены в модуль Teams PowerShell и задокументированы в справочнике Skype для бизнеса [командлетов](/powershell/skype/intro?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="8886f-194">These cmdlets are included in the Teams PowerShell module and are documented in the [Skype for Business cmdlet reference](/powershell/skype/intro?view=skype-ps).</span></span>

<span data-ttu-id="8886f-195">Скачайте и установите [общедоступный Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) (если вы еще не сделали этого), а затем запустите следующую версию, чтобы подключиться:</span><span class="sxs-lookup"><span data-stu-id="8886f-195">Download and install the [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) (if you haven't already), and then run the following to connect.</span></span>

> [!NOTE]
> <span data-ttu-id="8886f-196">Skype для бизнеса Online Connector в настоящее время является частью последней версии Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8886f-196">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="8886f-197">Если вы используете последний общедоступный [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать Skype для бизнеса Online Connector.</span><span class="sxs-lookup"><span data-stu-id="8886f-197">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
# When using Teams PowerShell Module

Import-Module MicrosoftTeams
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="8886f-198">В этом примере мы назначим пользователю с именем Reda Teams политику собраний учащихся.</span><span class="sxs-lookup"><span data-stu-id="8886f-198">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="8886f-199">Подробнее об этом можно узнать в [документе Управление политиками с помощью PowerShell.](teams-powershell-managing-teams.md#manage-policies-via-powershell)</span><span class="sxs-lookup"><span data-stu-id="8886f-199">To learn more, read [Manage policies via PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="8886f-200">Назначение политики группе</span><span class="sxs-lookup"><span data-stu-id="8886f-200">Assign a policy to a group</span></span>

<span data-ttu-id="8886f-201">Назначение политик группам позволяет назначить политику группе пользователей, например группе безопасности или списку рассылки.</span><span class="sxs-lookup"><span data-stu-id="8886f-201">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="8886f-202">Назначение политики распространяется на участников группы в соответствии с правилами очередности.</span><span class="sxs-lookup"><span data-stu-id="8886f-202">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="8886f-203">При добавлении или удалении участников группы, назначения политик для них обновляются соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="8886f-203">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="8886f-204">Назначение политик группам рекомендуется для групп до 50 000 пользователей, но оно также будет работать с более крупными группами.</span><span class="sxs-lookup"><span data-stu-id="8886f-204">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="8886f-205">При назначении политики она сразу же назначается группе.</span><span class="sxs-lookup"><span data-stu-id="8886f-205">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="8886f-206">Однако распространение назначения политики на участников группы выполняется в фоновом режиме и может занять некоторое время в зависимости от размера группы.</span><span class="sxs-lookup"><span data-stu-id="8886f-206">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="8886f-207">То же самое происходит, если политика не назначена группе, а участники добавляются в нее или удаляются из нее.</span><span class="sxs-lookup"><span data-stu-id="8886f-207">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

<span data-ttu-id="8886f-208">Назначения групповой политики распространяются только на пользователей, которые являются прямыми участниками группы.</span><span class="sxs-lookup"><span data-stu-id="8886f-208">Group policy assignments are only propagated to users who are direct members of the group.</span></span> <span data-ttu-id="8886f-209">Назначения не распространяются на участников вложенных групп.</span><span class="sxs-lookup"><span data-stu-id="8886f-209">The assignments aren't propagated to members of nested groups.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="8886f-210">Что необходимо знать о назначении политик группам</span><span class="sxs-lookup"><span data-stu-id="8886f-210">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="8886f-211">Перед началом работы важно разобраться в правилах приоритета и ранжирования заданий групп.</span><span class="sxs-lookup"><span data-stu-id="8886f-211">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="8886f-212">Правила приоритета</span><span class="sxs-lookup"><span data-stu-id="8886f-212">Precedence rules</span></span>

<span data-ttu-id="8886f-213">Для данного типа политики эффективная политика пользователя определяется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8886f-213">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="8886f-214">Политика, которая непосредственно назначена пользователю, имеет приоритет над любой другой политикой того же типа, которая назначена группе.</span><span class="sxs-lookup"><span data-stu-id="8886f-214">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="8886f-215">Другими словами, если пользователю непосредственно назначена политика заданного типа, он не наследует политику того же типа от группы.</span><span class="sxs-lookup"><span data-stu-id="8886f-215">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="8886f-216">Это также означает, что если пользователю назначена политика того или иного типа, необходимо удалить ее у пользователя, прежде чем он сможет наследовать политику того же типа от группы.</span><span class="sxs-lookup"><span data-stu-id="8886f-216">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>

- <span data-ttu-id="8886f-217">Если пользователю не назначена политика, а он входит в несколько групп и каждой группе назначена политика одного и того же типа, пользователь наследует политику назначения группы с наивысшим рейтингом.</span><span class="sxs-lookup"><span data-stu-id="8886f-217">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>

- <span data-ttu-id="8886f-218">Если пользователь не входит в группы, для каких-либо групп назначена политика, к этому типу политики применяется глобальная политика (по умолчанию в организации).</span><span class="sxs-lookup"><span data-stu-id="8886f-218">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="8886f-219">Эффективная политика пользователя обновляется в соответствии с этими правилами:</span><span class="sxs-lookup"><span data-stu-id="8886f-219">A user's effective policy is updated according to these rules:</span></span>

- <span data-ttu-id="8886f-220">при добавлении пользователя в группу, которая назначена политике, или удален из нее.</span><span class="sxs-lookup"><span data-stu-id="8886f-220">when a user is added to or removed from a group that's assigned a policy.</span></span>
- <span data-ttu-id="8886f-221">политика не назначена группе.</span><span class="sxs-lookup"><span data-stu-id="8886f-221">a policy is unassigned from a group.</span></span>
- <span data-ttu-id="8886f-222">Политика, которая непосредственно назначена пользователю, удаляется.</span><span class="sxs-lookup"><span data-stu-id="8886f-222">a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="8886f-223">Ранжирование заданий группы</span><span class="sxs-lookup"><span data-stu-id="8886f-223">Group assignment ranking</span></span>

<span data-ttu-id="8886f-224">При назначении группе политики указывается ранжирование для назначения группы.</span><span class="sxs-lookup"><span data-stu-id="8886f-224">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="8886f-225">Он используется для определения политики, которая должна наследоваться пользователем как эффективная политика, если пользователь входит в несколько групп и каждой группе назначена политика одного типа.</span><span class="sxs-lookup"><span data-stu-id="8886f-225">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="8886f-226">Ранжирование заданий группы является относительно других назначений группы того же типа.</span><span class="sxs-lookup"><span data-stu-id="8886f-226">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="8886f-227">Например, если вы назначаете политику звонков двум группам, установите для ранжирования одно задание 1, а для другого — 2, причем 1 является самым высоким.</span><span class="sxs-lookup"><span data-stu-id="8886f-227">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="8886f-228">Ранжирование назначений групп показывает, какое членство в группах является более важным или релевантным, чем другие группы, касающиеся наследования.</span><span class="sxs-lookup"><span data-stu-id="8886f-228">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships regarding inheritance.</span></span>

<span data-ttu-id="8886f-229">Например, у вас есть две группы: "Сотрудники магазинов" и "Руководители магазинов".</span><span class="sxs-lookup"><span data-stu-id="8886f-229">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="8886f-230">Обеим группам назначена политика Teams звонков, политика звонков сотрудников магазинов и политика звонков диспетчеров магазинов соответственно.</span><span class="sxs-lookup"><span data-stu-id="8886f-230">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="8886f-231">Для руководителя магазина, который относится к обеим группам, его роль руководителя больше релевантна, чем роль сотрудника, поэтому политика звонков, назначенная группе "Руководители магазинов", должна иметь более высокий рейтинг.</span><span class="sxs-lookup"><span data-stu-id="8886f-231">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="8886f-232">Группы</span><span class="sxs-lookup"><span data-stu-id="8886f-232">Group</span></span> |<span data-ttu-id="8886f-233">Teams политики звонков</span><span class="sxs-lookup"><span data-stu-id="8886f-233">Teams calling policy name</span></span>  |<span data-ttu-id="8886f-234">Rank (Ранг)</span><span class="sxs-lookup"><span data-stu-id="8886f-234">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="8886f-235">Руководители магазинов</span><span class="sxs-lookup"><span data-stu-id="8886f-235">Store Managers</span></span>   |<span data-ttu-id="8886f-236">Политика звонков диспетчеров магазинов</span><span class="sxs-lookup"><span data-stu-id="8886f-236">Store Managers Calling Policy</span></span>         |<span data-ttu-id="8886f-237">1</span><span class="sxs-lookup"><span data-stu-id="8886f-237">1</span></span>|
|<span data-ttu-id="8886f-238">Сотрудники магазина</span><span class="sxs-lookup"><span data-stu-id="8886f-238">Store Employees</span></span>    |<span data-ttu-id="8886f-239">Политика звонков сотрудников магазина</span><span class="sxs-lookup"><span data-stu-id="8886f-239">Store Employees Calling Policy</span></span>      |<span data-ttu-id="8886f-240">2</span><span class="sxs-lookup"><span data-stu-id="8886f-240">2</span></span>|

<span data-ttu-id="8886f-241">Если не указать ранжирование, назначение политики будет присвоено наименьшее ранжирование.</span><span class="sxs-lookup"><span data-stu-id="8886f-241">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="in-the-teams-admin-center"></a><span data-ttu-id="8886f-242">В центре Teams администрирования</span><span class="sxs-lookup"><span data-stu-id="8886f-242">In the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="8886f-243">В настоящее время назначение политик группам, использующим Центр администрирования Microsoft Teams, доступно только для политик звонков Teams, политики парков звонков Teams, политики Teams, политики трансляций Teams, политики Teams собраний и политики Teams сообщений.</span><span class="sxs-lookup"><span data-stu-id="8886f-243">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="8886f-244">Для других типов политик используйте PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8886f-244">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="8886f-245">В левой области навигации центра администрирования Microsoft Teams перейдите на страницу типа политики.</span><span class="sxs-lookup"><span data-stu-id="8886f-245">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="8886f-246">Например, перейдите к **политике собраний**  >  **собраний**.</span><span class="sxs-lookup"><span data-stu-id="8886f-246">For example, go to **Meetings** > **Meeting policies**.</span></span>

2. <span data-ttu-id="8886f-247">Выберите **вкладку Назначение групповой** политики.</span><span class="sxs-lookup"><span data-stu-id="8886f-247">Select the **Group policy assignment** tab.</span></span>

3. <span data-ttu-id="8886f-248">Выберите **Добавить группу,** а затем в области **Назначение** политики группе сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="8886f-248">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="8886f-249">Найщите и добавьте группу, для нее нужно назначить политику.</span><span class="sxs-lookup"><span data-stu-id="8886f-249">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="8886f-250">Задание ранжирования для задания группы.</span><span class="sxs-lookup"><span data-stu-id="8886f-250">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="8886f-251">Выберите политику, которую вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="8886f-251">Select the policy that you want to assign.</span></span>
    4. <span data-ttu-id="8886f-252">Выберите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="8886f-252">Select **Apply**.</span></span>

<span data-ttu-id="8886f-253">Чтобы удалить назначение групповой  политики, на вкладке Назначение групповой политики страницы политики выберите назначение группы и выберите **удалить**.</span><span class="sxs-lookup"><span data-stu-id="8886f-253">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="8886f-254">Чтобы изменить ранжирование назначения группы, необходимо сначала удалить назначение групповой политики.</span><span class="sxs-lookup"><span data-stu-id="8886f-254">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="8886f-255">Затем, следуя этим шагам, назначьте политику группе.</span><span class="sxs-lookup"><span data-stu-id="8886f-255">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="use-the-powershell-option"></a><span data-ttu-id="8886f-256">Использование параметра PowerShell</span><span class="sxs-lookup"><span data-stu-id="8886f-256">Use the PowerShell option</span></span>

> [!NOTE]
> <span data-ttu-id="8886f-257">В настоящее время назначения политик группам, использующим PowerShell, доступны не для Teams типов политик.</span><span class="sxs-lookup"><span data-stu-id="8886f-257">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="8886f-258">Список поддерживаемых типов политик см. в списке [New-CsGroupPolicyAssignment.](/powershell/module/teams/new-csgrouppolicyassignment)</span><span class="sxs-lookup"><span data-stu-id="8886f-258">See [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="8886f-259">Установка и подключение к Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="8886f-259">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="8886f-260">Пошаговую инструкцию см. в [Teams PowerShell.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="8886f-260">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-to-a-group-of-users"></a><span data-ttu-id="8886f-261">Назначение политики группе пользователей</span><span class="sxs-lookup"><span data-stu-id="8886f-261">Assign a policy to a group of users</span></span>

<span data-ttu-id="8886f-262">Чтобы назначить группу политику, воспользуйтесь [cmdlet New-CsGroupPolicyAssignment.](/powershell/module/teams/new-csgrouppolicyassignment)</span><span class="sxs-lookup"><span data-stu-id="8886f-262">Use the [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="8886f-263">Группу можно указать с помощью ИД объекта, SIP-адреса или адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="8886f-263">You can specify a group by using the object ID, SIP address, or email address.</span></span>

<span data-ttu-id="8886f-264">В этом примере мы назначаем политику Teams собраний с именем "Политика собраний менеджеров розничной торговли" группе со ранжированием назначения 1.</span><span class="sxs-lookup"><span data-stu-id="8886f-264">In this example, we assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="8886f-265">Получить назначения политик для группы</span><span class="sxs-lookup"><span data-stu-id="8886f-265">Get policy assignments for a group</span></span>

<span data-ttu-id="8886f-266">Чтобы получить все политики, которые назначены группе, используйте для этого [cmdlet Get-CsGroupPolicyAssignment.](/powershell/module/teams/get-csgrouppolicyassignment)</span><span class="sxs-lookup"><span data-stu-id="8886f-266">Use the [Get-CsGroupPolicyAssignment](/powershell/module/teams/get-csgrouppolicyassignment) cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="8886f-267">Обратите внимание, что группы всегда указаны по их групповому ИД, даже если для назначения политики использовался SIP-адрес или адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="8886f-267">Note that groups are always listed by their group ID even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="8886f-268">В этом примере мы извлекаем все политики, которые назначены определенной группе.</span><span class="sxs-lookup"><span data-stu-id="8886f-268">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="8886f-269">В этом примере возвращаются все группы, для Teams политики собраний.</span><span class="sxs-lookup"><span data-stu-id="8886f-269">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="8886f-270">Удаление политики из группы</span><span class="sxs-lookup"><span data-stu-id="8886f-270">Remove a policy from a group</span></span>

<span data-ttu-id="8886f-271">Чтобы удалить политику из группы, используйте [cmdlet Remove-CsGroupPolicyAssignment.](/powershell/module/teams/remove-csgrouppolicyassignment)</span><span class="sxs-lookup"><span data-stu-id="8886f-271">Use the [Remove-CsGroupPolicyAssignment](/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="8886f-272">При этом обновляются приоритеты других политик того же типа, которые имеют более низкий рейтинг.</span><span class="sxs-lookup"><span data-stu-id="8886f-272">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group, and that have a lower ranking, are updated.</span></span> <span data-ttu-id="8886f-273">Например, если удалить политику со ранжированием 2, политики с ранжированием 3 и 4 будут обновлены с учетом их нового ранжирования.</span><span class="sxs-lookup"><span data-stu-id="8886f-273">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="8886f-274">В следующих двух таблицах приводится пример.</span><span class="sxs-lookup"><span data-stu-id="8886f-274">The following two tables show this example.</span></span>

<span data-ttu-id="8886f-275">Вот список назначений и приоритетов политики для Teams собраний.</span><span class="sxs-lookup"><span data-stu-id="8886f-275">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="8886f-276">Имя группы</span><span class="sxs-lookup"><span data-stu-id="8886f-276">Group name</span></span>  |<span data-ttu-id="8886f-277">Название политики</span><span class="sxs-lookup"><span data-stu-id="8886f-277">Policy name</span></span>  |<span data-ttu-id="8886f-278">Rank (Ранг)</span><span class="sxs-lookup"><span data-stu-id="8886f-278">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="8886f-279">Продажи</span><span class="sxs-lookup"><span data-stu-id="8886f-279">Sales</span></span>    |<span data-ttu-id="8886f-280">Политика продаж</span><span class="sxs-lookup"><span data-stu-id="8886f-280">Sales policy</span></span>       | <span data-ttu-id="8886f-281">1</span><span class="sxs-lookup"><span data-stu-id="8886f-281">1</span></span>        |
|<span data-ttu-id="8886f-282">Западная область</span><span class="sxs-lookup"><span data-stu-id="8886f-282">West Region</span></span>     |<span data-ttu-id="8886f-283">Политика западного региона</span><span class="sxs-lookup"><span data-stu-id="8886f-283">West Region policy</span></span>         |<span data-ttu-id="8886f-284">2</span><span class="sxs-lookup"><span data-stu-id="8886f-284">2</span></span>         |
|<span data-ttu-id="8886f-285">Отдел</span><span class="sxs-lookup"><span data-stu-id="8886f-285">Division</span></span>    |<span data-ttu-id="8886f-286">Политика деления</span><span class="sxs-lookup"><span data-stu-id="8886f-286">Division policy</span></span>         |<span data-ttu-id="8886f-287">3</span><span class="sxs-lookup"><span data-stu-id="8886f-287">3</span></span>         |
|<span data-ttu-id="8886f-288">Дочерней компании</span><span class="sxs-lookup"><span data-stu-id="8886f-288">Subsidiary</span></span>   |<span data-ttu-id="8886f-289">Политика дочернего подразделения</span><span class="sxs-lookup"><span data-stu-id="8886f-289">Subsidiary policy</span></span>        |<span data-ttu-id="8886f-290">4</span><span class="sxs-lookup"><span data-stu-id="8886f-290">4</span></span>         |

<span data-ttu-id="8886f-291">Если удалить политику западного региона из группы "Запад", назначения и приоритеты политики будут обновлены следующим образом.</span><span class="sxs-lookup"><span data-stu-id="8886f-291">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="8886f-292">Имя группы</span><span class="sxs-lookup"><span data-stu-id="8886f-292">Group name</span></span>  |<span data-ttu-id="8886f-293">Название политики</span><span class="sxs-lookup"><span data-stu-id="8886f-293">Policy name</span></span>  |<span data-ttu-id="8886f-294">Rank (Ранг)</span><span class="sxs-lookup"><span data-stu-id="8886f-294">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="8886f-295">Продажи</span><span class="sxs-lookup"><span data-stu-id="8886f-295">Sales</span></span>    |<span data-ttu-id="8886f-296">Политика продаж</span><span class="sxs-lookup"><span data-stu-id="8886f-296">Sales policy</span></span>       | <span data-ttu-id="8886f-297">1</span><span class="sxs-lookup"><span data-stu-id="8886f-297">1</span></span>        |
|<span data-ttu-id="8886f-298">Отдел</span><span class="sxs-lookup"><span data-stu-id="8886f-298">Division</span></span>    |<span data-ttu-id="8886f-299">Политика деления</span><span class="sxs-lookup"><span data-stu-id="8886f-299">Division policy</span></span>         |<span data-ttu-id="8886f-300">2</span><span class="sxs-lookup"><span data-stu-id="8886f-300">2</span></span>         |
|<span data-ttu-id="8886f-301">Дочерней компании</span><span class="sxs-lookup"><span data-stu-id="8886f-301">Subsidiary</span></span>   |<span data-ttu-id="8886f-302">Политика дочернего подразделения</span><span class="sxs-lookup"><span data-stu-id="8886f-302">Subsidiary policy</span></span>        |<span data-ttu-id="8886f-303">3</span><span class="sxs-lookup"><span data-stu-id="8886f-303">3</span></span>        |

<span data-ttu-id="8886f-304">В этом примере мы удаляем политику Teams собраний из группы.</span><span class="sxs-lookup"><span data-stu-id="8886f-304">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="8886f-305">Изменение назначения политики для группы</span><span class="sxs-lookup"><span data-stu-id="8886f-305">Change a policy assignment for a group</span></span>

> [!NOTE]
> <span data-ttu-id="8886f-306">В ближайшее время появится [cmdlet Set-CsGroupPolicyAssignment.](/powershell/module/teams/set-csgrouppolicyassignment)</span><span class="sxs-lookup"><span data-stu-id="8886f-306">The [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) cmdlet will be available soon.</span></span> <span data-ttu-id="8886f-307">Тем временем, чтобы изменить назначение групповой политики, вы можете удалить текущее назначение политики из группы, а затем добавить новое назначение политики.</span><span class="sxs-lookup"><span data-stu-id="8886f-307">In the meantime, to change a group policy assignment, you can remove the current policy assignment from the group, and then add a new policy assignment.</span></span>

<span data-ttu-id="8886f-308">После назначения группе политики вы можете изменить назначение политики этой группы с помощью cmdlet [Set-CsGroupPolicyAssignment:](/powershell/module/teams/set-csgrouppolicyassignment)</span><span class="sxs-lookup"><span data-stu-id="8886f-308">After you assign a policy to a group, you can use the [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="8886f-309">Изменение ранжирования</span><span class="sxs-lookup"><span data-stu-id="8886f-309">Change the ranking</span></span>
- <span data-ttu-id="8886f-310">Изменение политики для заданного типа политики</span><span class="sxs-lookup"><span data-stu-id="8886f-310">Change the policy of a given policy type</span></span>
- <span data-ttu-id="8886f-311">Изменение политики для заданного типа политики и ранжирования</span><span class="sxs-lookup"><span data-stu-id="8886f-311">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="8886f-312">В этом примере мы меняем политику Teams жков группы на политику SupportCallPark и ранжирование заданий на 3.</span><span class="sxs-lookup"><span data-stu-id="8886f-312">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="8886f-313">Изменение эффективной политики для пользователя</span><span class="sxs-lookup"><span data-stu-id="8886f-313">Change the effective policy for a user</span></span>

<span data-ttu-id="8886f-314">Вот пример изменения эффективной политики для пользователя, которому назначена политика напрямую.</span><span class="sxs-lookup"><span data-stu-id="8886f-314">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="8886f-315">Во-первых, для получения сведений о политиках трансляции собраний, связанных с пользователем, используется Teams [Get-CsUserPolicyAssignment.](/powershell/module/teams/get-csuserpolicyassignment) `PolicySource`</span><span class="sxs-lookup"><span data-stu-id="8886f-315">First, we use the [Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment) cmdlet together with the `PolicySource` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="8886f-316">Выходные данные показывают, что пользователю напрямую назначена политика Teams трансляций собраний с названием "События сотрудника", которая имеет приоритет над политикой "Мероприятия поставщиков", назначенной группе, которой он принадлежит.</span><span class="sxs-lookup"><span data-stu-id="8886f-316">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="8886f-317">Теперь мы удалим политику "События сотрудников" для пользователя.</span><span class="sxs-lookup"><span data-stu-id="8886f-317">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="8886f-318">Это означает, что пользователю больше не назначена политика Teams трансляций собраний, и наследует политику "Мероприятия поставщиков", назначенную группе, которой принадлежит пользователь.</span><span class="sxs-lookup"><span data-stu-id="8886f-318">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span>

<span data-ttu-id="8886f-319">Для этого используйте следующий командлет Skype для бизнеса PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8886f-319">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="8886f-320">Используйте следующий командлет в модуле Teams PowerShell, чтобы сделать это в масштабе, хотя назначение пакетной политики $users список пользователей, которые вы указали.</span><span class="sxs-lookup"><span data-stu-id="8886f-320">Use following cmdlet in the Teams PowerShell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="8886f-321">Назначение политики для пакета пользователей</span><span class="sxs-lookup"><span data-stu-id="8886f-321">Assign a policy to a batch of users</span></span>

### <a name="use-the-admin-center"></a><span data-ttu-id="8886f-322">Использование Центра администрирования</span><span class="sxs-lookup"><span data-stu-id="8886f-322">Use the admin center</span></span>

<span data-ttu-id="8886f-323">Чтобы массово назначить политику пользователям:</span><span class="sxs-lookup"><span data-stu-id="8886f-323">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="8886f-324">В левой области навигации центра администрирования Microsoft Teams выберите **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="8886f-324">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>

2. <span data-ttu-id="8886f-325">Найщите пользователей, для них нужно назначить политику, или отфильтруем представление, чтобы отфильтровать нужных пользователей.</span><span class="sxs-lookup"><span data-stu-id="8886f-325">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>

3. <span data-ttu-id="8886f-326">В столбце **&#x2713;** (галочка) выберите пользователей.</span><span class="sxs-lookup"><span data-stu-id="8886f-326">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="8886f-327">Чтобы выбрать всех пользователей, щелкните &#x2713; (галочку) в верхней части таблицы.</span><span class="sxs-lookup"><span data-stu-id="8886f-327">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>

4. <span data-ttu-id="8886f-328">Выберите **Изменить параметры**, внесите нужные изменения и выберите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="8886f-328">Select **Edit settings**, make the changes that you want, and then select **Apply**.</span></span>

<span data-ttu-id="8886f-329">Чтобы просмотреть состояние задания политики, на баннере, который  появляется в  верхней части страницы Пользователи после выбора применить, чтобы отправить задание политики, выберите журнал **действий**.</span><span class="sxs-lookup"><span data-stu-id="8886f-329">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you select **Apply** to submit your policy assignment, select **Activity log**.</span></span> <span data-ttu-id="8886f-330">Кроме того, в левой области навигации Центра администрирования Microsoft Teams выберите Панель мониторинга **,** а затем в журнале действий **выберите** **Просмотреть сведения**.</span><span class="sxs-lookup"><span data-stu-id="8886f-330">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, select **View details**.</span></span> <span data-ttu-id="8886f-331">В журнале действий показаны назначения политик более чем 20 пользователям через Microsoft Teams центре администрирования за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="8886f-331">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="8886f-332">Дополнительные данные см. в записи просмотра заданий политики [в журнале действий.](activity-log.md)</span><span class="sxs-lookup"><span data-stu-id="8886f-332">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="use-powershell-method"></a><span data-ttu-id="8886f-333">Использование метода PowerShell</span><span class="sxs-lookup"><span data-stu-id="8886f-333">Use PowerShell method</span></span>

> [!NOTE]
> <span data-ttu-id="8886f-334">В настоящее время назначение пакетной политики с помощью PowerShell доступно не для Teams типов политик.</span><span class="sxs-lookup"><span data-stu-id="8886f-334">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="8886f-335">Список поддерживаемых типов политик см. в списке [New-CsBatchPolicyAssignmentOperation.](/powershell/module/teams/new-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="8886f-335">See [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>

<span data-ttu-id="8886f-336">При назначении пакетной политики вы можете назначать политику большому набору пользователей одновременно, не пользуясь сценарием.</span><span class="sxs-lookup"><span data-stu-id="8886f-336">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="8886f-337">Для отправки пакета пользователей и политики, которую вы хотите назначить, используется [cmdlet New-CsBatchPolicyAssignmentOperation.](/powershell/module/teams/new-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="8886f-337">You use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="8886f-338">Задания будут обрабатываться в фоновом режиме, а для каждого пакета будет создан идентификатор операции.</span><span class="sxs-lookup"><span data-stu-id="8886f-338">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="8886f-339">Затем можно использовать для отслеживания хода выполнения и состояния заданий в пакете с помощью [get-CsBatchPolicyAssignmentOperation.](/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="8886f-339">You can then use the [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="8886f-340">Укажите пользователей по их ИД объекта или SIP-адресу.</span><span class="sxs-lookup"><span data-stu-id="8886f-340">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="8886f-341">SIP-адрес пользователя часто имеет то же значение, что и имя пользователя (UPN) или адрес электронной почты, но это не обязательно.</span><span class="sxs-lookup"><span data-stu-id="8886f-341">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="8886f-342">Если имя пользователя указано с помощью его имя-пользователя или электронной почты, но его значение отличается от SIP-адреса, назначение политики для него не удастся.</span><span class="sxs-lookup"><span data-stu-id="8886f-342">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="8886f-343">Если пакет содержит дубликатов пользователей, они будут удалены из пакета до обработки, а состояние будет предоставлено только для уникальных пользователей, оставшихся в пакете.</span><span class="sxs-lookup"><span data-stu-id="8886f-343">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="8886f-344">Пакет может содержать до 5 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="8886f-344">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="8886f-345">Для получения наилучших результатов не от отправки нескольких пакетов за один раз.</span><span class="sxs-lookup"><span data-stu-id="8886f-345">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="8886f-346">Разрешить обработку пакетов перед отправкой дополнительных пакетов.</span><span class="sxs-lookup"><span data-stu-id="8886f-346">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-teams-powershell-module"></a><span data-ttu-id="8886f-347">Установка и подключение к Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="8886f-347">Install and connect to the Teams PowerShell module</span></span>

<span data-ttu-id="8886f-348">Чтобы установить модуль [Microsoft Teams PowerShell, запустите следующую Microsoft Teams.](https://www.powershellgallery.com/packages/MicrosoftTeams)</span><span class="sxs-lookup"><span data-stu-id="8886f-348">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="8886f-349">Установите версию 1.0.5 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="8886f-349">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="8886f-350">Чтобы подключиться к Teams и начать сеанс, запустите следующее:</span><span class="sxs-lookup"><span data-stu-id="8886f-350">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="8886f-351">Когда вам будет предложено, войте в учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="8886f-351">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="8886f-352">Установка и подключение к Azure AD PowerShell для Graph (необязательно)</span><span class="sxs-lookup"><span data-stu-id="8886f-352">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="8886f-353">Кроме того, может потребоваться скачать и установить [модуль Azure AD PowerShell](/powershell/azure/active-directory/install-adv2) для Graph (если вы еще не сделали этого) и подключиться к Azure AD, чтобы получить список пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="8886f-353">You might also want to [download and install the Azure AD PowerShell for Graph module](/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="8886f-354">Чтобы подключиться к Azure AD, запустите следующую службу:</span><span class="sxs-lookup"><span data-stu-id="8886f-354">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="8886f-355">В окне запроса войтесь в учетные данные администратора, которые использовались для подключения к Teams.</span><span class="sxs-lookup"><span data-stu-id="8886f-355">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-setup-policy-to-a-batch-of-users"></a><span data-ttu-id="8886f-356">Назначение политики установки для пакета пользователей</span><span class="sxs-lookup"><span data-stu-id="8886f-356">Assign a setup policy to a batch of users</span></span>

<span data-ttu-id="8886f-357">В этом примере с помощью нового [CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) назначим политику установки приложений с названием Политика настройки приложений для отдела кадров пакету пользователей, перечисленных в Users_ids.txt.</span><span class="sxs-lookup"><span data-stu-id="8886f-357">In this example, we use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.txt file.</span></span>

```powershell
$users_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="8886f-358">В этом примере мы подключаемся к Azure AD, чтобы получить набор пользователей, а затем назначим политику обмена сообщениями "Новая политика обмена сообщениями о приеме на работу" пакету пользователей, указанному с помощью их SIP-адреса.</span><span class="sxs-lookup"><span data-stu-id="8886f-358">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="8886f-359">Получить состояние пакета назначения</span><span class="sxs-lookup"><span data-stu-id="8886f-359">Get the status of a batch assignment</span></span>

<span data-ttu-id="8886f-360">Чтобы получить состояние пакета назначения, где OperationId — это код операции, возвращаемый этим cmdlet для заданного пакета, запустите `New-CsBatchPolicyAssignmentOperation` следующую операцию:</span><span class="sxs-lookup"><span data-stu-id="8886f-360">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the `New-CsBatchPolicyAssignmentOperation` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="8886f-361">Если выходные данные показывают, что произошла ошибка, запустите следующую, чтобы получить дополнительные сведения об ошибках, которые находятся в `UserState` свойстве.</span><span class="sxs-lookup"><span data-stu-id="8886f-361">If the output shows that an error occurred, run the following to get more information about errors, which are in the `UserState` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="8886f-362">Подробнее см. в [get-CsBatchPolicyAssignmentOperation.](/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="8886f-362">To learn more, see [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-package-to-users"></a><span data-ttu-id="8886f-363">Назначение пакета политики пользователям</span><span class="sxs-lookup"><span data-stu-id="8886f-363">Assign a policy package to users</span></span>

<span data-ttu-id="8886f-364">Пакет политики в Teams — это набор предопределевших политик и параметров политики, которые можно назначить пользователям с одинаковыми или похожими ролями в организации.</span><span class="sxs-lookup"><span data-stu-id="8886f-364">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="8886f-365">Каждый пакет политики предназначен для роли пользователя и содержит предварительно заранее задав политики и параметры политики, которые поддерживают типичные для нее действия.</span><span class="sxs-lookup"><span data-stu-id="8886f-365">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="8886f-366">Некоторые примеры пакетов политики: пакет для образовательных учреждений (преподаватель) и пакет для медицинского обслуживания (медицинского работника).</span><span class="sxs-lookup"><span data-stu-id="8886f-366">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span> <span data-ttu-id="8886f-367">Дополнительные информации см. в [Teams.](manage-policy-packages.md)</span><span class="sxs-lookup"><span data-stu-id="8886f-367">To learn more, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="8886f-368">Назначение пакета политики одному пользователю</span><span class="sxs-lookup"><span data-stu-id="8886f-368">Assign a policy package to one user</span></span>

1. <span data-ttu-id="8886f-369">В левой области навигации центра администрирования Microsoft Teams перейдите **в** меню Пользователи и выберите пользователя.</span><span class="sxs-lookup"><span data-stu-id="8886f-369">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>

2. <span data-ttu-id="8886f-370">На странице пользователя выберите Политики **,** а затем рядом с пакетом **политики** выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="8886f-370">On the user's page, select **Policies**, and then next to **Policy package**, select **Edit**.</span></span>

3. <span data-ttu-id="8886f-371">В **области Назначение пакета политики** выберите пакет, который вы хотите назначить, и выберите **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8886f-371">In the **Assign policy package** pane, select the package you want to assign, and then select **Save**.</span></span>

### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="8886f-372">Назначение пакета политики нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="8886f-372">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="8886f-373">В левой области навигации Центра администрирования Microsoft Teams перейдите в пакеты политики **,** а затем выберите пакет политики, который вы хотите назначить, щелкнув слева от имени пакета.</span><span class="sxs-lookup"><span data-stu-id="8886f-373">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>

2. <span data-ttu-id="8886f-374">Выберите **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="8886f-374">Select **Manage users**.</span></span>

3. <span data-ttu-id="8886f-375">В области **Управление пользователями** выполните поиск по отображаемому имени или по имени пользователя, выберите имя и нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="8886f-375">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="8886f-376">Повторите это действие для каждого пользователя, которого нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="8886f-376">Repeat this step for each user that you want to add.</span></span>

4. <span data-ttu-id="8886f-377">Завершив добавление пользователей, выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8886f-377">When you're finished adding users, select **Save**.</span></span>

## <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="8886f-378">Назначение пакета политики группе</span><span class="sxs-lookup"><span data-stu-id="8886f-378">Assign a policy package to a group</span></span>

<span data-ttu-id="8886f-379">Назначение пакетов политики группам позволяет назначать несколько политик группе пользователей, например группе безопасности или группе рассылки.</span><span class="sxs-lookup"><span data-stu-id="8886f-379">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="8886f-380">Назначение политики распространяется на участников группы в соответствии с правилами очередности.</span><span class="sxs-lookup"><span data-stu-id="8886f-380">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="8886f-381">При добавлении или удалении участников группы, назначения политик для них обновляются соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="8886f-381">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="8886f-382">Назначение пакетов политики группам рекомендуется для групп до 50 000 пользователей, но оно также будет работать с более крупными группами.</span><span class="sxs-lookup"><span data-stu-id="8886f-382">Policy package assignment to groups is recommended for groups of up to 50,000 users, but it will also work with larger groups.</span></span>

<span data-ttu-id="8886f-383">При назначении пакета политики он сразу же назначается группе.</span><span class="sxs-lookup"><span data-stu-id="8886f-383">When you assign the policy package, it's immediately assigned to the group.</span></span> <span data-ttu-id="8886f-384">Однако распространение назначения политики на участников группы выполняется в фоновом режиме и может занять некоторое время в зависимости от размера группы.</span><span class="sxs-lookup"><span data-stu-id="8886f-384">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="8886f-385">То же самое происходит, если политика не назначена группе, а участники добавляются в нее или удаляются из нее.</span><span class="sxs-lookup"><span data-stu-id="8886f-385">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8886f-386">Перед началом работы важно разобраться [](#precedence-rules) в правилах приоритета и ранжирования [заданий групп.](#group-assignment-ranking)</span><span class="sxs-lookup"><span data-stu-id="8886f-386">Before you get started, it's important to understand [precedence rules](#precedence-rules) and [group assignment ranking](#group-assignment-ranking).</span></span> <span data-ttu-id="8886f-387">Ознакомьтесь с понятиями в [](#what-you-need-to-know-about-policy-assignment-to-groups) статье Что необходимо знать о назначении политик группам ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="8886f-387">Make sure you read and understand the concepts in [What you need to know about policy assignment to groups](#what-you-need-to-know-about-policy-assignment-to-groups) earlier in this article.</span></span>

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a><span data-ttu-id="8886f-388">Назначение пакета политики группе пользователей в Центре администрирования</span><span class="sxs-lookup"><span data-stu-id="8886f-388">Assign a policy package to a group of users in the admin center</span></span>

1. <span data-ttu-id="8886f-389">Войдите в Центр администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="8886f-389">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="8886f-390">На левой странице навигации перейдите на страницу пакета политики.</span><span class="sxs-lookup"><span data-stu-id="8886f-390">In the left navigation, go to the policy package page.</span></span>

3. <span data-ttu-id="8886f-391">Выберите вкладку Назначение групповой политики.</span><span class="sxs-lookup"><span data-stu-id="8886f-391">Select the Group policy assignment tab.</span></span>

4. <span data-ttu-id="8886f-392">Выберите **Добавить группу,** а затем в области Назначение пакета политики группе сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="8886f-392">Select **Add group**, and then in the Assign a policy package to group pane, do the following:</span></span>

    1. <span data-ttu-id="8886f-393">Найщите и добавьте группу, для нее нужно назначить пакет политики.</span><span class="sxs-lookup"><span data-stu-id="8886f-393">Search for and add the group you want to assign the policy package to.</span></span>
    
    1. <span data-ttu-id="8886f-394">Выберите пакет политики.</span><span class="sxs-lookup"><span data-stu-id="8886f-394">Select a policy package.</span></span>
    
    1. <span data-ttu-id="8886f-395">Заведите ранжирование для каждого типа политики.</span><span class="sxs-lookup"><span data-stu-id="8886f-395">Set the ranking for each policy type.</span></span>
    
    1. <span data-ttu-id="8886f-396">Выберите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="8886f-396">Select **Apply**.</span></span>
    
    ![показывает назначение групповой политики](media/group-pkg-assignment.png)

5. <span data-ttu-id="8886f-398">Чтобы управлять ранжированием для определенного типа политики, перейдите на страницу политики.</span><span class="sxs-lookup"><span data-stu-id="8886f-398">To manage ranking for a specific policy type, navigate to the specific policy page.</span></span>

6. <span data-ttu-id="8886f-399">Чтобы перена назначение пакета политики группе, сначала удалите назначение групповой политики.</span><span class="sxs-lookup"><span data-stu-id="8886f-399">To reassign a policy package to a group, first remove the group policy assignment.</span></span> <span data-ttu-id="8886f-400">Затем следуйте этим шагам, чтобы назначить пакет политики группе.</span><span class="sxs-lookup"><span data-stu-id="8886f-400">Then, follow the steps above to assign the policy package to a group.</span></span>

### <a name="work-with-powershell"></a><span data-ttu-id="8886f-401">Работа с PowerShell</span><span class="sxs-lookup"><span data-stu-id="8886f-401">Work with PowerShell</span></span>

#### <a name="get-the-teams-powershell-module"></a><span data-ttu-id="8886f-402">Получить модуль Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="8886f-402">Get the Teams PowerShell module</span></span>

<span data-ttu-id="8886f-403">Пошаговую инструкцию см. в [Teams PowerShell.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="8886f-403">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-package-to-a-group-of-users"></a><span data-ttu-id="8886f-404">Назначение пакета политики группе пользователей</span><span class="sxs-lookup"><span data-stu-id="8886f-404">Assign a policy package to a group of users</span></span>

<span data-ttu-id="8886f-405">Чтобы назначить группе пакет политики, используйте [cmdlet Grant-CsGroupPolicyPackageAssignment.](/powershell/module/teams/grant-csgrouppolicypackageassignment)</span><span class="sxs-lookup"><span data-stu-id="8886f-405">Use the [Grant-CsGroupPolicyPackageAssignment](/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet to assign a policy package to a group.</span></span> <span data-ttu-id="8886f-406">Группу можно указать с помощью ИД объекта, SIP-адреса или адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="8886f-406">You can specify a group by using the object ID, SIP address, or email address.</span></span> <span data-ttu-id="8886f-407">При назначении пакета политики укажите ранжирование [назначений](#group-assignment-ranking) группы для каждого типа политики в пакете политики.</span><span class="sxs-lookup"><span data-stu-id="8886f-407">When you assign the policy package, specify a [group assignment ranking](#group-assignment-ranking) for each policy type in the policy package.</span></span>

<span data-ttu-id="8886f-408">В этом примере пакет политики Education_Teacher назначается группе со ранжированием заданий 1 для TeamsAppSetupPolicy и TeamsMeetingBroadcastPolicy и ранжированием 2 для TeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="8886f-408">In this example, we assign the Education_Teacher policy package to a group with an assignment ranking of 1 for TeamsAppSetupPolicy and TeamsMeetingBroadcastPolicy and a ranking of 2 for TeamsMeetingPolicy.</span></span>

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="8886f-409">Назначение пакета политики пакету пользователей</span><span class="sxs-lookup"><span data-stu-id="8886f-409">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="8886f-410">При назначении пакетного пакета политики вы можете одновременно назначить пакет политики большому набору пользователей, не пользуясь сценарием.</span><span class="sxs-lookup"><span data-stu-id="8886f-410">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="8886f-411">Для отправки пакета пользователей и пакета политики, который вы хотите назначить, используется cmdlet [New-CsBatchPolicyAssignmentOperation.](/powershell/module/teams/new-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="8886f-411">You use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="8886f-412">Задания будут обрабатываться в фоновом режиме, а для каждого пакета будет создан идентификатор операции.</span><span class="sxs-lookup"><span data-stu-id="8886f-412">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="8886f-413">Затем можно использовать для отслеживания хода выполнения и состояния заданий в пакете с помощью [get-CsBatchPolicyAssignmentOperation.](/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="8886f-413">You can then use the [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="8886f-414">Укажите пользователей по их ИД объекта или SIP-адресу.</span><span class="sxs-lookup"><span data-stu-id="8886f-414">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="8886f-415">SIP-адрес пользователя часто имеет то же значение, что и имя пользователя (UPN) или адрес электронной почты, но это не обязательно.</span><span class="sxs-lookup"><span data-stu-id="8886f-415">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this isn't required.</span></span> <span data-ttu-id="8886f-416">Если имя пользователя указано с помощью его имя-пользователя или электронной почты, но его значение отличается от SIP-адреса, назначение политики для него не удастся.</span><span class="sxs-lookup"><span data-stu-id="8886f-416">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="8886f-417">Если пакет содержит дубликатов пользователей, они будут удалены из пакета до обработки, а состояние будет предоставлено только для уникальных пользователей, оставшихся в пакете.</span><span class="sxs-lookup"><span data-stu-id="8886f-417">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="8886f-418">Пакет содержит до 5000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="8886f-418">A batch contains up to 5,000 users.</span></span> <span data-ttu-id="8886f-419">Для получения наилучших результатов не от отправьте несколько пакетов за один раз.</span><span class="sxs-lookup"><span data-stu-id="8886f-419">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="8886f-420">Разрешить обработку пакетов перед отправкой дополнительных пакетов.</span><span class="sxs-lookup"><span data-stu-id="8886f-420">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="use-the-teams-powershell-module"></a><span data-ttu-id="8886f-421">Использование модуля Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="8886f-421">Use the Teams PowerShell module</span></span>

<span data-ttu-id="8886f-422">Чтобы установить модуль [PowerShell Microsoft Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams) запустите следующую:</span><span class="sxs-lookup"><span data-stu-id="8886f-422">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="8886f-423">Установите версию 1.0.5 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="8886f-423">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="8886f-424">Чтобы подключиться к Teams и начать сеанс, запустите следующее:</span><span class="sxs-lookup"><span data-stu-id="8886f-424">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="8886f-425">Когда вам будет предложено, войте в учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="8886f-425">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-policy-packages-to-a-batch-of-users"></a><span data-ttu-id="8886f-426">Назначение пакетов политик для пакета пользователей</span><span class="sxs-lookup"><span data-stu-id="8886f-426">Assign policy packages to a batch of users</span></span>

<span data-ttu-id="8886f-427">В этом примере для назначения пакета политики пакету пользователей используется Education_PrimaryStudent [New-CsBatchPolicyAssignmentOperation.](/powershell/module/teams/new-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="8886f-427">In this example, we use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a><span data-ttu-id="8886f-428">См. состояние пакета назначения</span><span class="sxs-lookup"><span data-stu-id="8886f-428">See the status of a batch assignment</span></span>

<span data-ttu-id="8886f-429">Чтобы получить состояние пакета назначения, где OperationId — это код операции, возвращаемый этим cmdlet для заданного пакета, запустите `New-CsBatchPolicyAssignmentOperation` следующую операцию:</span><span class="sxs-lookup"><span data-stu-id="8886f-429">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the `New-CsBatchPolicyAssignmentOperation` cmdlet for a given batch.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="8886f-430">Если выходные данные показывают, что произошла ошибка, запустите следующую, чтобы получить дополнительные сведения об ошибках, которые находятся в `UserState` свойстве.</span><span class="sxs-lookup"><span data-stu-id="8886f-430">If the output shows that an error occurred, run the following to get more information about errors, which are in the `UserState` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="8886f-431">Подробнее см. в [get-CsBatchPolicyAssignmentOperation.](/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="8886f-431">To learn more, see [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="related-topics"></a><span data-ttu-id="8886f-432">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="8886f-432">Related topics</span></span>

[<span data-ttu-id="8886f-433">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="8886f-433">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
