---
title: Управление политиками отзывов в Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: heprecel
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
description: Узнайте, как с помощью политик отзывов управлять тем, Teams пользователи в вашей организации могут отправлять отзывы Teams в корпорацию Майкрософт.
ms.openlocfilehash: 66f14467e66456f244664a8273e0ff962297c05f
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656725"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="be8f7-103">Управление политиками отзывов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="be8f7-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="be8f7-104">Пользователи в вашей организации могут отправлять отзывы о Teams в корпорацию Майкрософт, чтобы мы знали, как это делается, непосредственно в клиенте Teams и веб-клиентах.</span><span class="sxs-lookup"><span data-stu-id="be8f7-104">Users in your organization can send feedback about Teams to Microsoft let us know how we're doing, directly from within the Teams desktop and web clients.</span></span> <span data-ttu-id="be8f7-105">Мы постоянно улучшаем Teams и используем этот отзыв, чтобы Teams улучшения.</span><span class="sxs-lookup"><span data-stu-id="be8f7-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

> [!NOTE]
> <span data-ttu-id="be8f7-106">Политики отзывов недоступны в GCC, GCC high или DOD.</span><span class="sxs-lookup"><span data-stu-id="be8f7-106">Feedback policies aren't available in GCC, GCC High, or DOD deployments.</span></span>

<span data-ttu-id="be8f7-107">**Функция "Обратная связь"**</span><span class="sxs-lookup"><span data-stu-id="be8f7-107">**The Give feedback feature**</span></span>

<span data-ttu-id="be8f7-108">Пользователи могут отправлять нам свои комментарии и предложения о Teams в разделе Помощь в отправке отзывов  >   в Teams.</span><span class="sxs-lookup"><span data-stu-id="be8f7-108">Users can send comments and suggestions about Teams to us by going to **Help** > **Give feedback** in Teams.</span></span> <span data-ttu-id="be8f7-109">В соответствии  с вашим соглашением о Microsoft 365 или Office 365 отзывами, данные, от отправленные с помощью предложения Предоставить отзыв, рассматриваются как "Данные клиента" или "Личные данные".</span><span class="sxs-lookup"><span data-stu-id="be8f7-109">Data sent through **Give feedback** is considered as "Support Data" under your Microsoft 365 or Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

![Снимок экрана: параметр "Отправить отзыв" в Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="be8f7-111">**Опросы**</span><span class="sxs-lookup"><span data-stu-id="be8f7-111">**Surveys**</span></span>

<span data-ttu-id="be8f7-112">Пользователи также могут оценить свой опыт работы с Teams и отправить нам сведения о своей оценке.</span><span class="sxs-lookup"><span data-stu-id="be8f7-112">Users can also rate their experience with Teams and send us details about the rating they give.</span></span> <span data-ttu-id="be8f7-113">Этот всплывающий опрос отображается для пользователей время от времени в Teams.</span><span class="sxs-lookup"><span data-stu-id="be8f7-113">This pop-up survey is displayed to users from time-to-time in Teams.</span></span> <span data-ttu-id="be8f7-114">Когда пользователь выбирает В **уведомлении** о предоставлении отзыва, для его завершения отображается опрос.</span><span class="sxs-lookup"><span data-stu-id="be8f7-114">When a user selects **Provide feedback** in the notification, the survey is displayed for them to complete.</span></span>

![уведомление опроса и форма в Teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="be8f7-116">Настройка того, могут ли пользователи отправлять отзывы о Teams в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="be8f7-116">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="be8f7-117">Как администратор вы можете управлять тем, могут ли пользователи в вашей организации  отправлять отзывы о Teams в корпорацию Майкрософт с помощью отправки отзывов и получения опроса.</span><span class="sxs-lookup"><span data-stu-id="be8f7-117">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft through **Give feedback** and whether they receive the survey.</span></span> <span data-ttu-id="be8f7-118">По умолчанию всем пользователям в организации автоматически назначена глобальная политика (по умолчанию  в организации), а в политике включены функция "Обратная связь" и опрос.</span><span class="sxs-lookup"><span data-stu-id="be8f7-118">By default, all users in your organization are automatically assigned the global (Org-wide default) policy, and the **Give feedback** feature and survey are enabled in the policy.</span></span> <span data-ttu-id="be8f7-119">Исключением является Teams для образования, где функции включены для преподавателей и отключены для учащихся.</span><span class="sxs-lookup"><span data-stu-id="be8f7-119">The exception is Teams for Education, where the features are enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="be8f7-120">Вы можете изменить глобальную политику или создать и назначить настраиваемую политику.</span><span class="sxs-lookup"><span data-stu-id="be8f7-120">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="be8f7-121">После изменения глобальной политики или назначения настраиваемой политики может занять несколько часов, чтобы изменения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="be8f7-121">After you edit the global policy or assign a custom policy, it can take a few hours for changes to take effect.</span></span>

<span data-ttu-id="be8f7-122">Например, вы хотите разрешить всем пользователям в организации отправлять  отзывы с помощью функции "Отправить отзыв" и получать опросы, кроме новых сотрудников.</span><span class="sxs-lookup"><span data-stu-id="be8f7-122">Say, for example, you want to allow all users in your organization to send feedback through **Give feedback** and receive surveys except for new hires in training.</span></span> <span data-ttu-id="be8f7-123">В этом сценарии создается настраиваемая политика, которая отключает обе функции и назначит ее новым рабочим.</span><span class="sxs-lookup"><span data-stu-id="be8f7-123">In this scenario, you create a custom policy to turn off both features and assign it to new hires.</span></span> <span data-ttu-id="be8f7-124">Все остальные пользователи в организации получают глобальную политику с включенными функциями.</span><span class="sxs-lookup"><span data-stu-id="be8f7-124">All other users in your organization get the global policy with the features turned on.</span></span>  

<span data-ttu-id="be8f7-125">Вы управляете политиками отзывов с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="be8f7-125">You manage feedback policies by using PowerShell.</span></span> <span data-ttu-id="be8f7-126">Создайте настраиваемую политику с помощью **cmdlet New-CsTeamsFeedbackPolicy,** который можно найти здесь. *[](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*</span><span class="sxs-lookup"><span data-stu-id="be8f7-126">Use the **New-CsTeamsFeedbackPolicy** cmdlet, *which can be [found here](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, to create a custom policy.</span></span> <span data-ttu-id="be8f7-127">Чтобы назначить его одному или несколько пользователям или группам пользователей, например группе безопасности или группе рассылки, используйте для этого **cmdlet Grant-CsTeamsFeedbackPolicy.**</span><span class="sxs-lookup"><span data-stu-id="be8f7-127">Use the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span> <span data-ttu-id="be8f7-128">Используйте **Set-CsTeamsFeedbackPolicy,** чтобы установить определенные флажки.</span><span class="sxs-lookup"><span data-stu-id="be8f7-128">Use **Set-CsTeamsFeedbackPolicy** to set specific flags.</span></span>

<span data-ttu-id="be8f7-129">Чтобы отключить и включить функции, заданы следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="be8f7-129">To turn off and turn on the features, set the following parameters:</span></span>

 - <span data-ttu-id="be8f7-130">**Отзывы:** задайте **параметр userInitiatedMode,** чтобы разрешить пользователям, которым назначена политика, обратную связь. </span><span class="sxs-lookup"><span data-stu-id="be8f7-130">**Give feedback**: Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="be8f7-131">Если параметр **отключен,** функция отключается, а пользователи, которым назначена политика, не могут предоставить отзыв.</span><span class="sxs-lookup"><span data-stu-id="be8f7-131">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>
 - <span data-ttu-id="be8f7-132">**Опросы.** Задайте **параметр receiveSurveysMode,** чтобы разрешить пользователям, которым назначена политика, получать опрос. </span><span class="sxs-lookup"><span data-stu-id="be8f7-132">**Surveys**: Set the **receiveSurveysMode** parameter to **enabled** to allow users who are assigned the policy to receive the survey.</span></span> <span data-ttu-id="be8f7-133">Чтобы пользователи получили опрос и разрешили им отказаться, задайте для параметра **enabledUserOverride**.</span><span class="sxs-lookup"><span data-stu-id="be8f7-133">To have users receive the survey and allow them to opt out, set the parameter to **enabledUserOverride**.</span></span> <span data-ttu-id="be8f7-134">В Teams пользователи затем могут перейти в Параметры конфиденциальности и выбрать, следует ли участвовать в  >   опросах.</span><span class="sxs-lookup"><span data-stu-id="be8f7-134">In Teams, users can then go to **Settings** > **Privacy** and choose whether they want to participate in surveys.</span></span> <span data-ttu-id="be8f7-135">Отключение **параметра** отключит эту функцию, и пользователи, которым назначена политика, не будут получать опрос.</span><span class="sxs-lookup"><span data-stu-id="be8f7-135">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy won't receive the survey.</span></span>
 - <span data-ttu-id="be8f7-136">**Электронная** почта: добавьте поле электронной почты с помощью флага **AllowEmailCollection.**</span><span class="sxs-lookup"><span data-stu-id="be8f7-136">**Email**: Use the **AllowEmailCollection** flag to add an email field.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="be8f7-137">Создание настраиваемой политики отзывов</span><span class="sxs-lookup"><span data-stu-id="be8f7-137">Create a custom feedback policy</span></span>

<span data-ttu-id="be8f7-138">В этом примере мы создаем политику отзывов под названием Новая политика отзывов о приеме на работу и отключаем возможность обратной связи с помощью функции "Обратная **связь"** и опроса.</span><span class="sxs-lookup"><span data-stu-id="be8f7-138">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback through **Give feedback** and the survey.</span></span>

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a><span data-ttu-id="be8f7-139">Назначение пользовательской политики отзывов пользователям</span><span class="sxs-lookup"><span data-stu-id="be8f7-139">Assign a custom feedback policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="be8f7-140">В этом примере пользователю с именем "пользователь1" назначается настраиваемая политика "Новая политика обратной связи о приеме на работу".</span><span class="sxs-lookup"><span data-stu-id="be8f7-140">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a><span data-ttu-id="be8f7-141">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="be8f7-141">Related topics</span></span>

- [<span data-ttu-id="be8f7-142">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="be8f7-142">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="be8f7-143">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="be8f7-143">Assign policies to your users in Teams</span></span>](assign-policies.md)
