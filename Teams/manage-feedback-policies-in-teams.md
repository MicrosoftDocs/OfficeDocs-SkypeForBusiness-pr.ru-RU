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
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Узнайте, как использовать политики обратной связи для управления тем, могут ли пользователи Teams в организации отправлять отзывы о Teams в Майкрософт.
ms.openlocfilehash: b016a1d566f15cdabea55913b7fe107d86dee358
ms.sourcegitcommit: b381d8f0b9fc45133d52175fa85901b66e744abd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "44326686"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="94b2b-103">Управление политиками обратной связи в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="94b2b-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="94b2b-104">Пользователи в вашей организации могут отправить отзыв о Teams в Майкрософт, чтобы сообщить нам, как мы делаем прямо в классической и веб-клиентах Teams.</span><span class="sxs-lookup"><span data-stu-id="94b2b-104">Users in your organization can send feedback about Teams to Microsoft let us know how we're doing, directly from within the Teams desktop and web clients.</span></span> <span data-ttu-id="94b2b-105">Мы постоянно улучшаем взаимодействие с Teams, и мы используем эту обратную связь, чтобы улучшить работу Teams.</span><span class="sxs-lookup"><span data-stu-id="94b2b-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

<span data-ttu-id="94b2b-106">**Функция предоставления отзывов**</span><span class="sxs-lookup"><span data-stu-id="94b2b-106">**The Give feedback feature**</span></span>

<span data-ttu-id="94b2b-107">Пользователи могут отправлять свои комментарии и предложения в Teams **, чтобы получить**  >  **отзыв** в Teams.</span><span class="sxs-lookup"><span data-stu-id="94b2b-107">Users can send comments and suggestions about Teams to us by going to **Help** > **Give feedback** in Teams.</span></span> <span data-ttu-id="94b2b-108">Данные, отправляемые через **обратную связь** , рассматриваются как "данные поддержки" в соответствии с соглашением Office 365, в том числе данные, которые в противном случае будут считаться "данными клиента" или "личными данными".</span><span class="sxs-lookup"><span data-stu-id="94b2b-108">Data sent through **Give feedback** is considered as "Support Data" under your Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

![Снимок экрана: команда "Отправить отзыв" в Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="94b2b-110">**Опрос**</span><span class="sxs-lookup"><span data-stu-id="94b2b-110">**Surveys**</span></span>

<span data-ttu-id="94b2b-111">Пользователи также могут оценить свое взаимодействие с помощью Teams и отправить нам информацию о рейтинге.</span><span class="sxs-lookup"><span data-stu-id="94b2b-111">Users can also rate their experience with Teams and send us details about the rating they give.</span></span> <span data-ttu-id="94b2b-112">Этот всплывающий опрос отображается для пользователей с временем по времени в Teams.</span><span class="sxs-lookup"><span data-stu-id="94b2b-112">This pop-up survey is displayed to users from time-to-time in Teams.</span></span> <span data-ttu-id="94b2b-113">Если пользователь щелкнет в уведомлении уведомление о **предоставлении обратной связи** , для него будет отображаться опрос.</span><span class="sxs-lookup"><span data-stu-id="94b2b-113">When a user clicks **Provide feedback** in the notification, the survey is displayed for them to complete.</span></span>

![Снимок экрана: уведомление и форма для опроса в Teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="94b2b-115">Укажите, могут ли пользователи отправлять отзывы о Teams в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="94b2b-115">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="94b2b-116">Администраторы могут управлять тем, могут ли пользователи в вашей организации отправлять отзывы о Teams в корпорацию Майкрософт, используя **обратную связь** и получать ли они опрос.</span><span class="sxs-lookup"><span data-stu-id="94b2b-116">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft through **Give feedback** and whether they receive the survey.</span></span> <span data-ttu-id="94b2b-117">По умолчанию всем пользователям в организации автоматически назначается Глобальная политика (параметры по умолчанию на уровне Организации) и функция **предоставления отзывов** и опрос включены в политике.</span><span class="sxs-lookup"><span data-stu-id="94b2b-117">By default, all users in your organization are automatically assigned the global (Org-wide default) policy and the **Give feedback** feature and survey are enabled in the policy.</span></span> <span data-ttu-id="94b2b-118">Исключением является группа для образовательных учреждений, в которой функции разрешены для преподавателей и отключены для учащихся.</span><span class="sxs-lookup"><span data-stu-id="94b2b-118">The exception is Teams for Education, where the features are enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="94b2b-119">Вы можете изменять глобальную политику или создавать и назначать пользовательские политики.</span><span class="sxs-lookup"><span data-stu-id="94b2b-119">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="94b2b-120">Если пользователю назначена настраиваемая политика, эта политика применяется к пользователю.</span><span class="sxs-lookup"><span data-stu-id="94b2b-120">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="94b2b-121">Если пользователю не назначена настраиваемая политика, она применяется к глобальной политике.</span><span class="sxs-lookup"><span data-stu-id="94b2b-121">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span> <span data-ttu-id="94b2b-122">После изменения глобальной политики или назначения политики может потребоваться несколько часов, чтобы изменения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="94b2b-122">After you edit the global policy or assign a policy, it can take a few hours for changes to take effect.</span></span>

<span data-ttu-id="94b2b-123">Например, вы хотите, чтобы все пользователи в вашей организации могли отправлять **Отзывы и предложения, за** исключением новых сотрудников в ходе обучения.</span><span class="sxs-lookup"><span data-stu-id="94b2b-123">Say, for example, you want to allow all users in your organization to send feedback through **Give feedback** and receive surveys except for new hires in training.</span></span> <span data-ttu-id="94b2b-124">В этом сценарии вы создаете собственную политику для отключения обоих функций и назначения их новым сотрудникам.</span><span class="sxs-lookup"><span data-stu-id="94b2b-124">In this scenario, you create a custom policy to turn off both features and assign it to new hires.</span></span> <span data-ttu-id="94b2b-125">Все остальные пользователи в вашей организации получают глобальную политику с включенной функциональностью.</span><span class="sxs-lookup"><span data-stu-id="94b2b-125">All other users in your organization get the global policy with the features turned on.</span></span>  

<span data-ttu-id="94b2b-126">Вы можете использовать командлет **New-CsTeamsFeedbackPolicy** , *который можно [найти здесь](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, чтобы создать настраиваемую политику и командлет **Grant-CsTeamsFeedbackPolicy** , чтобы назначить их одному или нескольким пользователям или группам пользователей, таким как группа безопасности или группа рассылки.</span><span class="sxs-lookup"><span data-stu-id="94b2b-126">You use the **New-CsTeamsFeedbackPolicy** cmdlet, *which can be [found here](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, to create a custom policy and the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span>

<span data-ttu-id="94b2b-127">Чтобы отключить и включить функции, задайте указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="94b2b-127">To turn off and turn on the features, set the following parameters:</span></span>

 - <span data-ttu-id="94b2b-128">**Введите отзыв**: установите для параметра **userInitiatedMode** значение **Enabled** , чтобы пользователи, которым назначена политика, могли получать отзывы.</span><span class="sxs-lookup"><span data-stu-id="94b2b-128">**Give feedback**: Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="94b2b-129">Если отключить этот параметр, **он будет отключен** , а пользователи, которым назначена эта политика, не смогут получать отзывы.</span><span class="sxs-lookup"><span data-stu-id="94b2b-129">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>
 - <span data-ttu-id="94b2b-130">**Опросы**: установите для параметра **receiveSurveysMode** значение **Enabled** , чтобы пользователи, которым назначена политика, могли получать опрос.</span><span class="sxs-lookup"><span data-stu-id="94b2b-130">**Surveys**: Set the **receiveSurveysMode** parameter to **enabled** to allow users who are assigned the policy to receive the survey.</span></span> <span data-ttu-id="94b2b-131">Чтобы пользователи получали опрос и могли отказаться от них, установите для параметра значение **enabledUserOverride**.</span><span class="sxs-lookup"><span data-stu-id="94b2b-131">To have users receive the survey and allow them to opt out, set the parameter to **enabledUserOverride**.</span></span> <span data-ttu-id="94b2b-132">В Teams пользователи могут перейти к **параметрам**  >  **Конфиденциальность** и выбрать, нужно ли принимать участие в опросах.</span><span class="sxs-lookup"><span data-stu-id="94b2b-132">In Teams, users can then go to **Settings** > **Privacy** and choose whether they want to participate in surveys.</span></span> <span data-ttu-id="94b2b-133">Если отключить этот параметр, **он отключит функцию** , и пользователи, которым назначена политика, не получат опрос.</span><span class="sxs-lookup"><span data-stu-id="94b2b-133">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy won't receive the survey.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="94b2b-134">Создание настраиваемой политики обратной связи</span><span class="sxs-lookup"><span data-stu-id="94b2b-134">Create a custom feedback policy</span></span>

<span data-ttu-id="94b2b-135">В этом примере мы создаем политику обратной связи с именем "Новая политика отзывов о найме", и мы отключили возможность отправить отзыв, добрав **отзыв** и опрос.</span><span class="sxs-lookup"><span data-stu-id="94b2b-135">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback through **Give feedback** and the survey.</span></span>

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy"></a><span data-ttu-id="94b2b-136">Назначение настраиваемой политики обратной связи</span><span class="sxs-lookup"><span data-stu-id="94b2b-136">Assign a custom feedback policy</span></span>

### <a name="assign-a-custom-feedback-policy-to-a-user"></a><span data-ttu-id="94b2b-137">Назначение пользователю пользовательской политики обратной связи</span><span class="sxs-lookup"><span data-stu-id="94b2b-137">Assign a custom feedback policy to a user</span></span>

<span data-ttu-id="94b2b-138">В этом примере мы назначаем специальную политику с именем "Новая политика отзывов о найме" пользователю User1.</span><span class="sxs-lookup"><span data-stu-id="94b2b-138">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```
### <a name="assign-a-custom-feedback-policy-to-users-in-a-group"></a><span data-ttu-id="94b2b-139">Назначение настраиваемой политики обратной связи пользователям в группе</span><span class="sxs-lookup"><span data-stu-id="94b2b-139">Assign a custom feedback policy to users in a group</span></span>

<span data-ttu-id="94b2b-140">Возможно, вы захотите назначить пользовательскую политику отзывов нескольким пользователям, которые уже были идентифицированы.</span><span class="sxs-lookup"><span data-stu-id="94b2b-140">You may want to assign a custom feedback policy to multiple users that you've already identified.</span></span> <span data-ttu-id="94b2b-141">Например, может потребоваться назначить политику всем пользователям в группе безопасности.</span><span class="sxs-lookup"><span data-stu-id="94b2b-141">For example, you may want to assign a policy to all users in a security group.</span></span>

<span data-ttu-id="94b2b-142">В этом примере мы назначаем специальную политику обратной связи, которая называется новой политикой обратной связи для всех пользователей в группе новых сотрудников Contoso.</span><span class="sxs-lookup"><span data-stu-id="94b2b-142">In this example, we assign a custom feedback policy called New Hire Feedback Policy to all users in the Contoso New Hires group.</span></span>  

<span data-ttu-id="94b2b-143">Получить GroupObjectId определенной группы.</span><span class="sxs-lookup"><span data-stu-id="94b2b-143">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso New Hires"
```
<span data-ttu-id="94b2b-144">Получение участников указанной группы.</span><span class="sxs-lookup"><span data-stu-id="94b2b-144">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="94b2b-145">Назначьте для всех пользователей в группе определенную политику обратной связи.</span><span class="sxs-lookup"><span data-stu-id="94b2b-145">Assign all users in the group to a particular feedback policy.</span></span> <span data-ttu-id="94b2b-146">В этом примере это новая политика обратной связи для приема на работу.</span><span class="sxs-lookup"><span data-stu-id="94b2b-146">In this example, it's New Hire Feedback Policy.</span></span>
```PowerShell
$members | ForEach-Object {Grant-CsTeamsFeedbackPolicy -PolicyName "New Hire Feedback Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="94b2b-147">Для выполнения этой команды может потребоваться несколько минут в зависимости от количества участников в группе.</span><span class="sxs-lookup"><span data-stu-id="94b2b-147">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="94b2b-148">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="94b2b-148">Related topics</span></span>

- [<span data-ttu-id="94b2b-149">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="94b2b-149">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
