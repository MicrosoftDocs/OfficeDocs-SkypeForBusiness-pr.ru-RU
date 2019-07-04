---
title: Управление политиками обратной связи в Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: msedliak
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Узнайте, как использовать политики обратной связи для управления тем, могут ли пользователи Teams в организации отправлять отзывы о Teams в Майкрософт.
ms.openlocfilehash: 3c9d05a3003906377447ee119b8cfc9bd137db81
ms.sourcegitcommit: f26bb86d38c3b45a82e6d77c5aa521360a81ee9b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2019
ms.locfileid: "35540955"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="8b4a8-103">Управление политиками обратной связи в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8b4a8-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="8b4a8-104">Пользователи смогут отправлять свои комментарии и предложения в Microsoft Teams, применяя \*\*\*\* > **обратную связь** с клиентами Teams.</span><span class="sxs-lookup"><span data-stu-id="8b4a8-104">Users can send comments and suggestions about Teams to Microsoft by going to **Help** > **Give feedback** in the Teams clients.</span></span> <span data-ttu-id="8b4a8-105">Мы постоянно улучшаем взаимодействие с Teams, и мы используем эту обратную связь, чтобы улучшить работу Teams.</span><span class="sxs-lookup"><span data-stu-id="8b4a8-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

![Снимок экрана с параметром предоставления отзывов в Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="8b4a8-107">Данные, отправляемые через **обратную связь** , рассматриваются как "данные поддержки" в соответствии с соглашением Office 365, в том числе данные, которые в противном случае будут считаться "данными клиента" или "личными данными".</span><span class="sxs-lookup"><span data-stu-id="8b4a8-107">Data sent through **Give feedback** is considered as "Support Data" under your Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="8b4a8-108">Укажите, могут ли пользователи отправлять отзывы о Teams в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8b4a8-108">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="8b4a8-109">Администраторы могут управлять тем, могут ли пользователи в вашей организации отправлять отзывы о Teams в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8b4a8-109">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft.</span></span> <span data-ttu-id="8b4a8-110">По умолчанию всем пользователям в организации автоматически назначается Глобальная политика (параметр по умолчанию на уровне Организации), и функция включена в политике.</span><span class="sxs-lookup"><span data-stu-id="8b4a8-110">By default, all users in your organization are automatically assigned the global (Org-wide default) policy and the feature is enabled in the policy.</span></span> <span data-ttu-id="8b4a8-111">Исключением является группа для образовательных учреждений, в которой функция включена для преподавателей и отключена для учащихся.</span><span class="sxs-lookup"><span data-stu-id="8b4a8-111">The exception is Teams for Education, where the feature is enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="8b4a8-112">Вы можете изменять глобальную политику или создавать и назначать пользовательские политики.</span><span class="sxs-lookup"><span data-stu-id="8b4a8-112">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="8b4a8-113">Если пользователю назначена настраиваемая политика, эта политика применяется к пользователю.</span><span class="sxs-lookup"><span data-stu-id="8b4a8-113">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="8b4a8-114">Если пользователю не назначена настраиваемая политика, она применяется к глобальной политике.</span><span class="sxs-lookup"><span data-stu-id="8b4a8-114">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span> <span data-ttu-id="8b4a8-115">После изменения глобальной политики или назначения политики для вступления изменений в силу может потребоваться до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="8b4a8-115">After you edit the global policy or assign a policy, it can take up to 24 hours for changes to take effect.</span></span>

<span data-ttu-id="8b4a8-116">Например, вы хотите, чтобы все пользователи в вашей организации могли отправлять отзывы, за исключением новых сотрудников в ходе обучения.</span><span class="sxs-lookup"><span data-stu-id="8b4a8-116">Say, for example, you want to allow all users in your organization to send feedback except for new hires in training.</span></span> <span data-ttu-id="8b4a8-117">В этом сценарии вы создаете специальную политику для отключения функции и назначения ее новым сотрудникам.</span><span class="sxs-lookup"><span data-stu-id="8b4a8-117">In this scenario, you create a custom policy to turn off the feature and assign it to new hires.</span></span> <span data-ttu-id="8b4a8-118">Все остальные пользователи в вашей организации получают глобальную политику с включенной функцией.</span><span class="sxs-lookup"><span data-stu-id="8b4a8-118">All other users in your organization get the global policy with the feature turned on.</span></span>  

<span data-ttu-id="8b4a8-119">Командлет **New-кстеамсфидбаккполици** можно использовать для создания настраиваемой политики и командлета **Grant-кстеамсфидбаккполици** , чтобы назначить их одному или нескольким пользователям или группам пользователей, таким как группа безопасности или группа рассылки.</span><span class="sxs-lookup"><span data-stu-id="8b4a8-119">You use the **New-CsTeamsFeedbackPolicy** cmdlet to create a custom policy and the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span> 

<span data-ttu-id="8b4a8-120">Установите для параметра **усеринитиатедмоде** значение **Enabled** , чтобы пользователи, которым назначена политика, могли получать отзывы.</span><span class="sxs-lookup"><span data-stu-id="8b4a8-120">Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="8b4a8-121">Если отключить этот параметр \*\*\*\* , он будет отключен, а пользователи, которым назначена эта политика, не смогут получать отзывы.</span><span class="sxs-lookup"><span data-stu-id="8b4a8-121">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="8b4a8-122">Создание настраиваемой политики обратной связи</span><span class="sxs-lookup"><span data-stu-id="8b4a8-122">Create a custom feedback policy</span></span>

<span data-ttu-id="8b4a8-123">В этом примере мы создадим политику обратной связи с именем "Новая политика отзывов о найме", и мы отправим отзыв.</span><span class="sxs-lookup"><span data-stu-id="8b4a8-123">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback.</span></span>

```
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled
```

## <a name="assign-a-custom-feedback-policy"></a><span data-ttu-id="8b4a8-124">Назначение настраиваемой политики обратной связи</span><span class="sxs-lookup"><span data-stu-id="8b4a8-124">Assign a custom feedback policy</span></span>

### <a name="assign-a-custom-feedback-policy-to-a-user"></a><span data-ttu-id="8b4a8-125">Назначение пользователю пользовательской политики обратной связи</span><span class="sxs-lookup"><span data-stu-id="8b4a8-125">Assign a custom feedback policy to a user</span></span>

<span data-ttu-id="8b4a8-126">В этом примере мы назначаем специальную политику с именем "Новая политика отзывов о найме" пользователю User1.</span><span class="sxs-lookup"><span data-stu-id="8b4a8-126">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```
### <a name="assign-a-custom-feedback-policy-to-users-in-a-group"></a><span data-ttu-id="8b4a8-127">Назначение настраиваемой политики обратной связи пользователям в группе</span><span class="sxs-lookup"><span data-stu-id="8b4a8-127">Assign a custom feedback policy to users in a group</span></span>

<span data-ttu-id="8b4a8-128">Возможно, вы захотите назначить пользовательскую политику отзывов нескольким пользователям, которые уже были идентифицированы.</span><span class="sxs-lookup"><span data-stu-id="8b4a8-128">You may want to assign a custom feedback policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="8b4a8-129">Например, может потребоваться назначить политику всем пользователям в группе безопасности.</span><span class="sxs-lookup"><span data-stu-id="8b4a8-129">For example, you may want to assign a policy to all users in a security group.</span></span>

<span data-ttu-id="8b4a8-130">В этом примере мы назначаем специальную политику обратной связи, которая называется новой политикой обратной связи для всех пользователей в группе новых сотрудников Contoso.</span><span class="sxs-lookup"><span data-stu-id="8b4a8-130">In this example, we assign a custom feedback policy called New Hire Feedback Policy to all users in the Contoso New Hires group.</span></span>  

<span data-ttu-id="8b4a8-131">Получить Граупобжектид определенной группы.</span><span class="sxs-lookup"><span data-stu-id="8b4a8-131">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso New Hires"
```
<span data-ttu-id="8b4a8-132">Получение участников указанной группы.</span><span class="sxs-lookup"><span data-stu-id="8b4a8-132">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="8b4a8-133">Назначьте для всех пользователей в группе определенную политику обратной связи.</span><span class="sxs-lookup"><span data-stu-id="8b4a8-133">Assign all users in the group to a particular feedback policy.</span></span> <span data-ttu-id="8b4a8-134">В этом примере это новая политика обратной связи для приема на работу.</span><span class="sxs-lookup"><span data-stu-id="8b4a8-134">In this example, it's New Hire Feedback Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsFeedbackPolicy -PolicyName "New Hire Feedback Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="8b4a8-135">Для выполнения этой команды может потребоваться несколько минут в зависимости от количества участников в группе.</span><span class="sxs-lookup"><span data-stu-id="8b4a8-135">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8b4a8-136">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="8b4a8-136">Related topics</span></span>

- [<span data-ttu-id="8b4a8-137">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="8b4a8-137">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)