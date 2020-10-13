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
ms.openlocfilehash: 0bece4515825a0d7ddf7e547f1607fbd6cf205cc
ms.sourcegitcommit: c79b83e03a89649e2b6e494a741a392819baf2d2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "48433042"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="99cca-103">Управление политиками обратной связи в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="99cca-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="99cca-104">Пользователи в вашей организации могут отправить отзыв о Teams в Майкрософт, чтобы сообщить нам, как мы делаем прямо в классической и веб-клиентах Teams.</span><span class="sxs-lookup"><span data-stu-id="99cca-104">Users in your organization can send feedback about Teams to Microsoft let us know how we're doing, directly from within the Teams desktop and web clients.</span></span> <span data-ttu-id="99cca-105">Мы постоянно улучшаем взаимодействие с Teams, и мы используем эту обратную связь, чтобы улучшить работу Teams.</span><span class="sxs-lookup"><span data-stu-id="99cca-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

> [!NOTE]
> <span data-ttu-id="99cca-106">Политики обратной связи недоступны в развертываниях GCC, GCC High или DOD.</span><span class="sxs-lookup"><span data-stu-id="99cca-106">Feedback policies aren't available in GCC, GCC High, or DOD deployments.</span></span>

<span data-ttu-id="99cca-107">**Функция предоставления отзывов**</span><span class="sxs-lookup"><span data-stu-id="99cca-107">**The Give feedback feature**</span></span>

<span data-ttu-id="99cca-108">Пользователи могут отправлять свои комментарии и предложения в Teams **, чтобы получить**  >  **отзыв** в Teams.</span><span class="sxs-lookup"><span data-stu-id="99cca-108">Users can send comments and suggestions about Teams to us by going to **Help** > **Give feedback** in Teams.</span></span> <span data-ttu-id="99cca-109">Данные, отправляемые через **обратную связь** , рассматриваются как "данные поддержки" в соответствии с соглашением Microsoft 365 или Office 365, в том числе данные, которые в противном случае будут считаться "данными клиента" или "личными данными".</span><span class="sxs-lookup"><span data-stu-id="99cca-109">Data sent through **Give feedback** is considered as "Support Data" under your Microsoft 365 or Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

![Снимок экрана: команда "Отправить отзыв" в Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="99cca-111">**Опрос**</span><span class="sxs-lookup"><span data-stu-id="99cca-111">**Surveys**</span></span>

<span data-ttu-id="99cca-112">Пользователи также могут оценить свое взаимодействие с помощью Teams и отправить нам информацию о рейтинге.</span><span class="sxs-lookup"><span data-stu-id="99cca-112">Users can also rate their experience with Teams and send us details about the rating they give.</span></span> <span data-ttu-id="99cca-113">Этот всплывающий опрос отображается для пользователей с временем по времени в Teams.</span><span class="sxs-lookup"><span data-stu-id="99cca-113">This pop-up survey is displayed to users from time-to-time in Teams.</span></span> <span data-ttu-id="99cca-114">Если пользователь щелкнет в уведомлении уведомление о **предоставлении обратной связи** , для него будет отображаться опрос.</span><span class="sxs-lookup"><span data-stu-id="99cca-114">When a user clicks **Provide feedback** in the notification, the survey is displayed for them to complete.</span></span>

![Снимок экрана: уведомление и форма для опроса в Teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="99cca-116">Укажите, могут ли пользователи отправлять отзывы о Teams в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="99cca-116">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="99cca-117">Администраторы могут управлять тем, могут ли пользователи в вашей организации отправлять отзывы о Teams в корпорацию Майкрософт, используя **обратную связь** и получать ли они опрос.</span><span class="sxs-lookup"><span data-stu-id="99cca-117">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft through **Give feedback** and whether they receive the survey.</span></span> <span data-ttu-id="99cca-118">По умолчанию всем пользователям в организации автоматически назначается Глобальная политика (параметры по умолчанию на уровне Организации) и функция **предоставления отзывов** и опрос включены в политике.</span><span class="sxs-lookup"><span data-stu-id="99cca-118">By default, all users in your organization are automatically assigned the global (Org-wide default) policy and the **Give feedback** feature and survey are enabled in the policy.</span></span> <span data-ttu-id="99cca-119">Исключением является группа для образовательных учреждений, в которой функции разрешены для преподавателей и отключены для учащихся.</span><span class="sxs-lookup"><span data-stu-id="99cca-119">The exception is Teams for Education, where the features are enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="99cca-120">Вы можете изменять глобальную политику или создавать и назначать пользовательские политики.</span><span class="sxs-lookup"><span data-stu-id="99cca-120">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="99cca-121">После изменения глобальной политики или назначения настраиваемой политики может потребоваться несколько часов, чтобы изменения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="99cca-121">After you edit the global policy or assign a custom policy, it can take a few hours for changes to take effect.</span></span>

<span data-ttu-id="99cca-122">Например, вы хотите, чтобы все пользователи в вашей организации могли отправлять **Отзывы и предложения, за** исключением новых сотрудников в ходе обучения.</span><span class="sxs-lookup"><span data-stu-id="99cca-122">Say, for example, you want to allow all users in your organization to send feedback through **Give feedback** and receive surveys except for new hires in training.</span></span> <span data-ttu-id="99cca-123">В этом сценарии вы создаете собственную политику для отключения обоих функций и назначения их новым сотрудникам.</span><span class="sxs-lookup"><span data-stu-id="99cca-123">In this scenario, you create a custom policy to turn off both features and assign it to new hires.</span></span> <span data-ttu-id="99cca-124">Все остальные пользователи в вашей организации получают глобальную политику с включенной функциональностью.</span><span class="sxs-lookup"><span data-stu-id="99cca-124">All other users in your organization get the global policy with the features turned on.</span></span>  

<span data-ttu-id="99cca-125">Управление политиками обратной связи осуществляется с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99cca-125">You manage feedback policies by using PowerShell.</span></span> <span data-ttu-id="99cca-126">Используйте командлет **New-CsTeamsFeedbackPolicy** , *который можно [найти здесь](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, чтобы создать настраиваемую политику и командлет **Grant-CsTeamsFeedbackPolicy** , чтобы назначить их одному или нескольким пользователям или группам пользователей, таким как группа безопасности или группа рассылки.</span><span class="sxs-lookup"><span data-stu-id="99cca-126">Use the **New-CsTeamsFeedbackPolicy** cmdlet, *which can be [found here](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, to create a custom policy and the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span>

<span data-ttu-id="99cca-127">Чтобы отключить и включить функции, задайте указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="99cca-127">To turn off and turn on the features, set the following parameters:</span></span>

 - <span data-ttu-id="99cca-128">**Введите отзыв**: установите для параметра **userInitiatedMode** значение **Enabled** , чтобы пользователи, которым назначена политика, могли получать отзывы.</span><span class="sxs-lookup"><span data-stu-id="99cca-128">**Give feedback**: Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="99cca-129">Если отключить этот параметр, **он будет отключен** , а пользователи, которым назначена эта политика, не смогут получать отзывы.</span><span class="sxs-lookup"><span data-stu-id="99cca-129">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>
 - <span data-ttu-id="99cca-130">**Опросы**: установите для параметра **receiveSurveysMode** значение **Enabled** , чтобы пользователи, которым назначена политика, могли получать опрос.</span><span class="sxs-lookup"><span data-stu-id="99cca-130">**Surveys**: Set the **receiveSurveysMode** parameter to **enabled** to allow users who are assigned the policy to receive the survey.</span></span> <span data-ttu-id="99cca-131">Чтобы пользователи получали опрос и могли отказаться от них, установите для параметра значение **enabledUserOverride**.</span><span class="sxs-lookup"><span data-stu-id="99cca-131">To have users receive the survey and allow them to opt out, set the parameter to **enabledUserOverride**.</span></span> <span data-ttu-id="99cca-132">В Teams пользователи могут перейти к **параметрам**  >  **Конфиденциальность** и выбрать, нужно ли принимать участие в опросах.</span><span class="sxs-lookup"><span data-stu-id="99cca-132">In Teams, users can then go to **Settings** > **Privacy** and choose whether they want to participate in surveys.</span></span> <span data-ttu-id="99cca-133">Если отключить этот параметр, **он отключит функцию** , и пользователи, которым назначена политика, не получат опрос.</span><span class="sxs-lookup"><span data-stu-id="99cca-133">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy won't receive the survey.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="99cca-134">Создание настраиваемой политики обратной связи</span><span class="sxs-lookup"><span data-stu-id="99cca-134">Create a custom feedback policy</span></span>

<span data-ttu-id="99cca-135">В этом примере мы создаем политику обратной связи с именем "Новая политика отзывов о найме", и мы отключили возможность отправить отзыв, добрав **отзыв** и опрос.</span><span class="sxs-lookup"><span data-stu-id="99cca-135">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback through **Give feedback** and the survey.</span></span>

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a><span data-ttu-id="99cca-136">Назначение пользователям настраиваемой политики обратной связи</span><span class="sxs-lookup"><span data-stu-id="99cca-136">Assign a custom feedback policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="99cca-137">В этом примере мы назначаем специальную политику с именем "Новая политика отзывов о найме" пользователю User1.</span><span class="sxs-lookup"><span data-stu-id="99cca-137">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a><span data-ttu-id="99cca-138">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="99cca-138">Related topics</span></span>

- [<span data-ttu-id="99cca-139">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="99cca-139">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="99cca-140">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="99cca-140">Assign policies to your users in Teams</span></span>](assign-policies.md)