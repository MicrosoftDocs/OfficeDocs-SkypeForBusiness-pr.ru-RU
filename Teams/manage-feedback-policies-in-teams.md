---
title: Управление политиками отзывов в Microsoft Teams
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
description: Узнайте, как с помощью политик отзывов управлять тем, могут ли пользователи Teams в вашей организации отправлять отзывы о Teams в корпорацию Майкрософт.
ms.openlocfilehash: 0bece4515825a0d7ddf7e547f1607fbd6cf205cc
ms.sourcegitcommit: c79b83e03a89649e2b6e494a741a392819baf2d2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "48433042"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="edc96-103">Управление политиками отзывов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="edc96-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="edc96-104">Пользователи в вашей организации могут отправлять отзывы о Teams в корпорацию Майкрософт прямо из классических и веб-клиентов Teams.</span><span class="sxs-lookup"><span data-stu-id="edc96-104">Users in your organization can send feedback about Teams to Microsoft let us know how we're doing, directly from within the Teams desktop and web clients.</span></span> <span data-ttu-id="edc96-105">Мы постоянно улучшаем teams и используем эти отзывы, чтобы сделать Teams еще лучше.</span><span class="sxs-lookup"><span data-stu-id="edc96-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

> [!NOTE]
> <span data-ttu-id="edc96-106">Политики отзывов недоступны в развертываниях GCC, GCC High и DOD.</span><span class="sxs-lookup"><span data-stu-id="edc96-106">Feedback policies aren't available in GCC, GCC High, or DOD deployments.</span></span>

<span data-ttu-id="edc96-107">**Функция "Обратная связь"**</span><span class="sxs-lookup"><span data-stu-id="edc96-107">**The Give feedback feature**</span></span>

<span data-ttu-id="edc96-108">Пользователи могут отправлять нам свои комментарии и предложения о Teams, помогая  >  **отправлять отзывы** в Teams.</span><span class="sxs-lookup"><span data-stu-id="edc96-108">Users can send comments and suggestions about Teams to us by going to **Help** > **Give feedback** in Teams.</span></span> <span data-ttu-id="edc96-109">В соответствии  с соглашением о Microsoft 365 или Office 365 данные, относясь к отзывам с помощью предложения "Предоставить отзыв", считаются "Данными поддержки", включая сведения, которые в противном случае рассматриваются как "Данные клиента" или "Личные данные".</span><span class="sxs-lookup"><span data-stu-id="edc96-109">Data sent through **Give feedback** is considered as "Support Data" under your Microsoft 365 or Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

![Снимок экрана: команда "Обратная связь" в Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="edc96-111">**Опросы**</span><span class="sxs-lookup"><span data-stu-id="edc96-111">**Surveys**</span></span>

<span data-ttu-id="edc96-112">Пользователи также могут оценить свои впечатления от Работы в Teams и отправить нам сведения о оценке, которая они дают.</span><span class="sxs-lookup"><span data-stu-id="edc96-112">Users can also rate their experience with Teams and send us details about the rating they give.</span></span> <span data-ttu-id="edc96-113">Это всплывающее опрос постоянно отображается для пользователей в Teams.</span><span class="sxs-lookup"><span data-stu-id="edc96-113">This pop-up survey is displayed to users from time-to-time in Teams.</span></span> <span data-ttu-id="edc96-114">Когда пользователь нажимает **кнопку "Предоставить отзыв"** в уведомлении, для его завершения отображается опрос.</span><span class="sxs-lookup"><span data-stu-id="edc96-114">When a user clicks **Provide feedback** in the notification, the survey is displayed for them to complete.</span></span>

![Снимок экрана: уведомление и форма опроса в Teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="edc96-116">Настройка того, могут ли пользователи отправлять отзывы о Teams в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="edc96-116">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="edc96-117">Как администратор вы можете управлять тем, могут ли пользователи в  вашей организации отправлять отзывы о Teams в корпорацию Майкрософт с помощью отзыва и получения опроса.</span><span class="sxs-lookup"><span data-stu-id="edc96-117">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft through **Give feedback** and whether they receive the survey.</span></span> <span data-ttu-id="edc96-118">По умолчанию всем пользователям в организации автоматически назначена глобальная политика (по  умолчанию в организации), а в политике включены функция "Обратная связь" и опрос.</span><span class="sxs-lookup"><span data-stu-id="edc96-118">By default, all users in your organization are automatically assigned the global (Org-wide default) policy and the **Give feedback** feature and survey are enabled in the policy.</span></span> <span data-ttu-id="edc96-119">Исключением является Teams для образовательных сфере, где функции включены для преподавателей и отключены для учащихся.</span><span class="sxs-lookup"><span data-stu-id="edc96-119">The exception is Teams for Education, where the features are enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="edc96-120">Вы можете изменить глобальную политику или создать и назначить настраиваемую политику.</span><span class="sxs-lookup"><span data-stu-id="edc96-120">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="edc96-121">После изменения глобальной политики или назначения настраиваемой политики может занять несколько часов, чтобы изменения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="edc96-121">After you edit the global policy or assign a custom policy, it can take a few hours for changes to take effect.</span></span>

<span data-ttu-id="edc96-122">Например, вы хотите разрешить всем пользователям в организации отправлять  отзывы с помощью функции "Обратная связь" и получать опросы, кроме новых сотрудников, обучающих.</span><span class="sxs-lookup"><span data-stu-id="edc96-122">Say, for example, you want to allow all users in your organization to send feedback through **Give feedback** and receive surveys except for new hires in training.</span></span> <span data-ttu-id="edc96-123">В этом сценарии создается настраиваемая политика, которая отключает обе функции и назначает ее новым найма.</span><span class="sxs-lookup"><span data-stu-id="edc96-123">In this scenario, you create a custom policy to turn off both features and assign it to new hires.</span></span> <span data-ttu-id="edc96-124">Все остальные пользователи в организации получают глобальную политику с включенными функциями.</span><span class="sxs-lookup"><span data-stu-id="edc96-124">All other users in your organization get the global policy with the features turned on.</span></span>  

<span data-ttu-id="edc96-125">Вы управляете политиками отзывов с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="edc96-125">You manage feedback policies by using PowerShell.</span></span> <span data-ttu-id="edc96-126">С помощью **cmdlet new-CsTeamsFeedbackPolicy,** который можно найти *здесь, [](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)* создайте настраиваемую политику и с помощью cmdlet **Grant-CsTeamsFeedbackPolicy** назначьте ее одному или несколько пользователям или группам пользователей, например группе безопасности или группе рассылки.</span><span class="sxs-lookup"><span data-stu-id="edc96-126">Use the **New-CsTeamsFeedbackPolicy** cmdlet, *which can be [found here](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, to create a custom policy and the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span>

<span data-ttu-id="edc96-127">Чтобы отключить и включить функции, заданы следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="edc96-127">To turn off and turn on the features, set the following parameters:</span></span>

 - <span data-ttu-id="edc96-128">**Обратная связь:** задайте параметр **userInitiatedMode,** чтобы разрешить пользователям, которым назначена политика, давать отзывы. </span><span class="sxs-lookup"><span data-stu-id="edc96-128">**Give feedback**: Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="edc96-129">Если параметр **отключен,** функция отключается, а пользователи, которым назначена политика, не могут давать отзывы.</span><span class="sxs-lookup"><span data-stu-id="edc96-129">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>
 - <span data-ttu-id="edc96-130">**Опросы:** задайте параметр **receiveSurveysMode,** чтобы разрешить пользователям, которым назначена политика, получать опросы. </span><span class="sxs-lookup"><span data-stu-id="edc96-130">**Surveys**: Set the **receiveSurveysMode** parameter to **enabled** to allow users who are assigned the policy to receive the survey.</span></span> <span data-ttu-id="edc96-131">Чтобы пользователи получили опрос и разрешили им отказаться, задайте для параметра **enabledUserOverride.**</span><span class="sxs-lookup"><span data-stu-id="edc96-131">To have users receive the survey and allow them to opt out, set the parameter to **enabledUserOverride**.</span></span> <span data-ttu-id="edc96-132">В Teams пользователи затем могут перейти в параметры конфиденциальности и выбрать, нужно ли участвовать  >   в опросах.</span><span class="sxs-lookup"><span data-stu-id="edc96-132">In Teams, users can then go to **Settings** > **Privacy** and choose whether they want to participate in surveys.</span></span> <span data-ttu-id="edc96-133">Если отключить этот **параметр,** функция будет отключена, и пользователи, которым назначена политика, не будут получать опрос.</span><span class="sxs-lookup"><span data-stu-id="edc96-133">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy won't receive the survey.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="edc96-134">Создание настраиваемой политики отзывов</span><span class="sxs-lookup"><span data-stu-id="edc96-134">Create a custom feedback policy</span></span>

<span data-ttu-id="edc96-135">В этом примере мы создали политику обратной связи под названием "Политика  обратной связи для новых сотрудников" и отключаем возможность обратной связи с помощью функции "Обратная связь" и опроса.</span><span class="sxs-lookup"><span data-stu-id="edc96-135">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback through **Give feedback** and the survey.</span></span>

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a><span data-ttu-id="edc96-136">Назначение пользовательской политики отзывов пользователям</span><span class="sxs-lookup"><span data-stu-id="edc96-136">Assign a custom feedback policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="edc96-137">В этом примере пользователю с именем "Пользователь1" назначается настраиваемая политика с именем "Новая политика отзывов о наеме".</span><span class="sxs-lookup"><span data-stu-id="edc96-137">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a><span data-ttu-id="edc96-138">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="edc96-138">Related topics</span></span>

- [<span data-ttu-id="edc96-139">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="edc96-139">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="edc96-140">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="edc96-140">Assign policies to your users in Teams</span></span>](assign-policies.md)