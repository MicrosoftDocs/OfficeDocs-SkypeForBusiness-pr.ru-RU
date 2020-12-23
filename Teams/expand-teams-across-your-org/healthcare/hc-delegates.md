---
title: Делегирование сообщений
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: Узнайте, как пользователь с состоянием "Нет на сети" или "Не беспокоить" может явно настроить другого пользователя в качестве делегата в сообщении о состоянии.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ac23afbea7f452967718a8c2d86fd4d36584492d
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790471"
---
# <a name="message-delegation"></a><span data-ttu-id="019d2-103">Делегирование сообщений</span><span class="sxs-lookup"><span data-stu-id="019d2-103">Message delegation</span></span>

<span data-ttu-id="019d2-104">Пользователь уже может явно установить состояние "Нет на сети" или "Не беспокоить" и предоставить настраиваемый текст.</span><span class="sxs-lookup"><span data-stu-id="019d2-104">A user can already explicitly set their status to Away or Do not Disturb, and provide custom text.</span></span> <span data-ttu-id="019d2-105">Функция делегирования сообщений работает следующим образом:</span><span class="sxs-lookup"><span data-stu-id="019d2-105">The message delegation feature works as follows:</span></span>

1. <span data-ttu-id="019d2-106">Пользователь @username упомянул другого пользователя в текстовом сообщении о состоянии, указав, что, хотя он и не может связаться с ним, вместо этого обратитесь к @username пользователя.</span><span class="sxs-lookup"><span data-stu-id="019d2-106">A user @username mentions another user in part of a text status message, suggesting that while they are unavailable people who want to contact them instead contact the @username mentioned user.</span></span>
2. <span data-ttu-id="019d2-107">Человек, назначенный в качестве делегата, будет уведомлен о том, что его назначили делегатом.</span><span class="sxs-lookup"><span data-stu-id="019d2-107">The person who has been assigned as a delegate is notified that they were nominated to be a delegate.</span></span>
3. <span data-ttu-id="019d2-108">После этого пользователь, который пытается связаться с первым пользователем, может наведите курсор на кандидата на должность представителя и легко наведите на него сообщение.</span><span class="sxs-lookup"><span data-stu-id="019d2-108">Someone trying to contact the first user can then hover over the nominated delegate and easily message the delegate instead.</span></span>  

<span data-ttu-id="019d2-109">Этот процесс в клиенте инициировался пользователем, и для того чтобы включить эту функцию, не требуется участие администратора.</span><span class="sxs-lookup"><span data-stu-id="019d2-109">This is a user-initiated process in the client, and no Admin involvement is required to enable the feature.</span></span> 

## <a name="delegation-use-scenario-in-healthcare"></a><span data-ttu-id="019d2-110">Сценарий делегирования в сфере здравоохранения</span><span class="sxs-lookup"><span data-stu-id="019d2-110">Delegation use scenario in Healthcare</span></span>

<span data-ttu-id="019d2-111">*Пример использования без настройки делегатов:*  Г-н Йет Пикто (Dr.Cio) находится на вызове в отделе радиологии.</span><span class="sxs-lookup"><span data-stu-id="019d2-111">*Usage example without setting delegates:*  Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="019d2-112">Он принимает экстренный личный звонок, и ему необходимо отойти на несколько часов.</span><span class="sxs-lookup"><span data-stu-id="019d2-112">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="019d2-113">Он просит одного из своих коллег из отдела радиологии, д-р Лену Эрле, охватить его, пока он не будет на нем под управлением.</span><span class="sxs-lookup"><span data-stu-id="019d2-113">He asks one of his peers in the radiology department, Dr. Lena Ehrle, to cover for him while he is gone.</span></span> <span data-ttu-id="019d2-114">Он неформальных образом передает свой pager dr. Ehrle, who is listening for urgent messages and pings on the pager and respond to them forhalf of Dr. Piccio in addition to her current responsibilities.</span><span class="sxs-lookup"><span data-stu-id="019d2-114">He informally hands over his pager to Dr. Ehrle, who is listening for urgent messages and pings on the pager and responds to them on behalf of Dr. Piccio in addition to her current responsibilities.</span></span> <span data-ttu-id="019d2-115">Возможно, другие члены команды не поняли, что неформальная делегирования произошла, и за уходом за пациентом следует путаница.</span><span class="sxs-lookup"><span data-stu-id="019d2-115">Others on the team may not realize the informal delegation happened, and confusion ensues with a patient's care.</span></span>

<span data-ttu-id="019d2-116">*Пример использования с настройками делегатов:* Г-н Йет Пикто (Dr.Cio) находится на вызове в отделе радиологии.</span><span class="sxs-lookup"><span data-stu-id="019d2-116">*Usage example with setting delegates:* Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="019d2-117">Он принимает экстренный личный звонок, и ему необходимо отойти на несколько часов.</span><span class="sxs-lookup"><span data-stu-id="019d2-117">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="019d2-118">Он просит одного из своих коллег из отдела радиологии Лену Эрле охватить его, пока он не будет на нем под управлением.</span><span class="sxs-lookup"><span data-stu-id="019d2-118">He asks one of his peers in the radiology department, Dr. Lena Ehrle to cover for him while he is gone.</span></span> <span data-ttu-id="019d2-119">Он изменяет свое пользовательское сообщение о состоянии на примерно следующее: "В течение следующих нескольких часов я недоступен.</span><span class="sxs-lookup"><span data-stu-id="019d2-119">He changes his custom status message to say something similar to "I am unavailable for the next few hours.</span></span> <span data-ttu-id="019d2-120">Обратитесь в @DrEhrle на любые экстренные ситуации".</span><span class="sxs-lookup"><span data-stu-id="019d2-120">Please contact @DrEhrle for any emergencies."</span></span>  <span data-ttu-id="019d2-121">Другие члены команды понимают, что делегирования произошла из-за того, что они пытаются связаться с dr. Piccio, поэтому теперь они знают, что нужно связаться с д-ном Артемом.</span><span class="sxs-lookup"><span data-stu-id="019d2-121">Others on the team realize the delegation happened as they're attempting to contact Dr. Piccio, so they now know to contact Dr. Ehrle in the meantime.</span></span> <span data-ttu-id="019d2-122">Отсутствие путаницы с уходом за пациентом практически не спутает.</span><span class="sxs-lookup"><span data-stu-id="019d2-122">Little to no confusion ensues with a patient's care.</span></span>

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a><span data-ttu-id="019d2-123">Влияние режимов совместной работы на состояние пользователей в клиенте Teams</span><span class="sxs-lookup"><span data-stu-id="019d2-123">Impact of co-existence modes on user status in the Teams client</span></span>

<span data-ttu-id="019d2-124">Администраторам следует знать, что заметки о состоянии и упоминания о делегирования отчасти зависят от режима совместной работы пользователя.</span><span class="sxs-lookup"><span data-stu-id="019d2-124">Admins should be aware that status notes and delegation mention behaviors will depend partly on a user's co-existence mode.</span></span> <span data-ttu-id="019d2-125">В этой матрице показаны возможные варианты.</span><span class="sxs-lookup"><span data-stu-id="019d2-125">This matrix shows the possibilities:</span></span>

|<span data-ttu-id="019d2-126">Co-Existence режиме</span><span class="sxs-lookup"><span data-stu-id="019d2-126">Co-Existence Mode</span></span> | <span data-ttu-id="019d2-127">Ожидаемое поведение</span><span class="sxs-lookup"><span data-stu-id="019d2-127">Expected Behavior</span></span>|
|---|---|
|<span data-ttu-id="019d2-128">TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="019d2-128">TeamsOnly</span></span> |<span data-ttu-id="019d2-129">Пользователи могут устанавливать заметки только из Teams.</span><span class="sxs-lookup"><span data-stu-id="019d2-129">Users can set a note only from Teams.</span></span> <br> <span data-ttu-id="019d2-130">Заметка пользователя в Teams отображается в Teams & SfB.</span><span class="sxs-lookup"><span data-stu-id="019d2-130">User's Teams note is visible in Teams & SfB.</span></span> |
|<span data-ttu-id="019d2-131">Острова</span><span class="sxs-lookup"><span data-stu-id="019d2-131">Islands</span></span> | <span data-ttu-id="019d2-132">Набор заметок пользователя в Teams отображается только в Teams.</span><span class="sxs-lookup"><span data-stu-id="019d2-132">User's note set in Teams visible only in Teams.</span></span> <br> <span data-ttu-id="019d2-133">Набор заметок пользователя в SfB, видимый только в SfB</span><span class="sxs-lookup"><span data-stu-id="019d2-133">User's note set in SfB visible only in SfB</span></span> |
|<span data-ttu-id="019d2-134">Режимы SFB\*</span><span class="sxs-lookup"><span data-stu-id="019d2-134">SfB\* modes</span></span> | <span data-ttu-id="019d2-135">Пользователи могут установить заметку только из SfB.</span><span class="sxs-lookup"><span data-stu-id="019d2-135">Users can set a note only from SfB.</span></span> <br> <span data-ttu-id="019d2-136">Заметка пользователя sfB отображается в SfB & Teams.</span><span class="sxs-lookup"><span data-stu-id="019d2-136">User's SfB note is visible in SfB & Teams.</span></span>  |
|||

<span data-ttu-id="019d2-137">Пользователь может настроить заметку в Teams только в том случае, если в его режиме настроена TeamsOnly или Islands.</span><span class="sxs-lookup"><span data-stu-id="019d2-137">A user can only set a note in Teams if their mode is TeamsOnly or Islands.</span></span>  

### <a name="displaying-notes-set-in-skype-for-business"></a><span data-ttu-id="019d2-138">Отображение заметок, установленных в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="019d2-138">Displaying notes set in Skype for Business</span></span>
  
<span data-ttu-id="019d2-139">Визуальный признак того, что заметка создана из Skype для бизнеса, не указывается.</span><span class="sxs-lookup"><span data-stu-id="019d2-139">There is no visual indication that a note was set from Skype for Business.</span></span>

<span data-ttu-id="019d2-140">Skype для бизнеса не применяет ограничение на количество символов в заметках о состоянии.</span><span class="sxs-lookup"><span data-stu-id="019d2-140">Skype for Business doesn't enforce a character limit on status notes.</span></span> <span data-ttu-id="019d2-141">Microsoft Teams отображает только первые 280 символов заметок из Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="019d2-141">Microsoft Teams will only display the first 280 characters of a note set from Skype for Business.</span></span> <span data-ttu-id="019d2-142">Многоразовая (...) в конце заметки означает обрезку.</span><span class="sxs-lookup"><span data-stu-id="019d2-142">An ellipse (…) at the end of a note indicates truncation.</span></span>
  
<span data-ttu-id="019d2-143">Skype для бизнеса не поддерживает срок действия заметок.</span><span class="sxs-lookup"><span data-stu-id="019d2-143">Skype for Business doesn't support expiry times for notes.</span></span>

<span data-ttu-id="019d2-144">Перенос заметок из Skype для бизнеса в Teams не поддерживается при обновлении пользователя до режима TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="019d2-144">Migration of notes from Skype for Business to Teams is not supported when a user is upgraded to TeamsOnly mode.</span></span>

## <a name="related-topics"></a><span data-ttu-id="019d2-145">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="019d2-145">Related topics</span></span>

[<span data-ttu-id="019d2-146">Сосуществование со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="019d2-146">Coexistence with Skype for Business</span></span>](../../coexistence-chat-calls-presence.md)
