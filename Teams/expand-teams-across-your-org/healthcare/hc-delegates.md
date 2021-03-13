---
title: Делегирование обмена сообщениями
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
description: Узнайте, как пользователь со статусом "Нет на месте" или "Не беспокоить" может явно настроить другого пользователя в качестве представителя в своей подписи к статусу.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ac23afbea7f452967718a8c2d86fd4d36584492d
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790471"
---
# <a name="message-delegation"></a><span data-ttu-id="ad5fe-103">Делегирование обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="ad5fe-103">Message delegation</span></span>

<span data-ttu-id="ad5fe-104">Пользователь уже может явным образом установить статус "Нет на месте" или "Не беспокоить" и добавить собственный текст.</span><span class="sxs-lookup"><span data-stu-id="ad5fe-104">A user can already explicitly set their status to Away or Do not Disturb, and provide custom text.</span></span> <span data-ttu-id="ad5fe-105">Функция делегирования обмена сообщениями работает следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ad5fe-105">The message delegation feature works as follows:</span></span>

1. <span data-ttu-id="ad5fe-106">Пользователь @имя_пользователя упоминает другого пользователя в подписи к статусу, предлагая в свое отсутствие обращаться вместо себя к указанному пользователю @имя_пользователя.</span><span class="sxs-lookup"><span data-stu-id="ad5fe-106">A user @username mentions another user in part of a text status message, suggesting that while they are unavailable people who want to contact them instead contact the @username mentioned user.</span></span>
2. <span data-ttu-id="ad5fe-107">Пользователь, назначенный в качестве представителя, уведомляется об этом назначении.</span><span class="sxs-lookup"><span data-stu-id="ad5fe-107">The person who has been assigned as a delegate is notified that they were nominated to be a delegate.</span></span>
3. <span data-ttu-id="ad5fe-108">После этого, если кто-то хочет связаться с первым пользователем, он может навести курсор на назначенного представителя и легко отправить ему сообщение.</span><span class="sxs-lookup"><span data-stu-id="ad5fe-108">Someone trying to contact the first user can then hover over the nominated delegate and easily message the delegate instead.</span></span>  

<span data-ttu-id="ad5fe-109">Этот процесс инициируется в клиенте пользователем, и для включения этой функции не требуется участие администратора.</span><span class="sxs-lookup"><span data-stu-id="ad5fe-109">This is a user-initiated process in the client, and no Admin involvement is required to enable the feature.</span></span> 

## <a name="delegation-use-scenario-in-healthcare"></a><span data-ttu-id="ad5fe-110">Сценарий использования делегирования в сфере здравоохранения</span><span class="sxs-lookup"><span data-stu-id="ad5fe-110">Delegation use scenario in Healthcare</span></span>

<span data-ttu-id="ad5fe-111">*Пример использования без назначения представителей.* Доктор Павел Безруков находится на дежурстве в отделении радиологии.</span><span class="sxs-lookup"><span data-stu-id="ad5fe-111">*Usage example without setting delegates:*  Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="ad5fe-112">Он получает срочный личный звонок и должен отлучиться на несколько часов.</span><span class="sxs-lookup"><span data-stu-id="ad5fe-112">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="ad5fe-113">Он просит одного из коллег в отделении радиологии, доктора Марту Артемьеву, подменить его, пока он отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ad5fe-113">He asks one of his peers in the radiology department, Dr. Lena Ehrle, to cover for him while he is gone.</span></span> <span data-ttu-id="ad5fe-114">Он неформально передает свой пейджер доктору Артемьевой, которая в дополнение к собственным обязанностям прослушивает срочные сообщения и вызовы на пейджере, а также отвечает на них от имени доктора Безрукова.</span><span class="sxs-lookup"><span data-stu-id="ad5fe-114">He informally hands over his pager to Dr. Ehrle, who is listening for urgent messages and pings on the pager and responds to them on behalf of Dr. Piccio in addition to her current responsibilities.</span></span> <span data-ttu-id="ad5fe-115">Другие коллеги могут не знать, что произошло неформальное делегирование, и возникает путаница при уходе за пациентами.</span><span class="sxs-lookup"><span data-stu-id="ad5fe-115">Others on the team may not realize the informal delegation happened, and confusion ensues with a patient's care.</span></span>

<span data-ttu-id="ad5fe-116">*Пример использования с назначением представителей.* Доктор Павел Безруков находится на дежурстве в отделении радиологии.</span><span class="sxs-lookup"><span data-stu-id="ad5fe-116">*Usage example with setting delegates:* Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="ad5fe-117">Он получает срочный личный звонок и должен отлучиться на несколько часов.</span><span class="sxs-lookup"><span data-stu-id="ad5fe-117">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="ad5fe-118">Он просит одного из коллег в отделении радиологии, доктора Марту Артемьеву, подменить его, пока он отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ad5fe-118">He asks one of his peers in the radiology department, Dr. Lena Ehrle to cover for him while he is gone.</span></span> <span data-ttu-id="ad5fe-119">Он изменяет свою настраиваемую подпись к статусу на "Я недоступен в течение следующих нескольких часов.</span><span class="sxs-lookup"><span data-stu-id="ad5fe-119">He changes his custom status message to say something similar to "I am unavailable for the next few hours.</span></span> <span data-ttu-id="ad5fe-120">По срочным вопросам связывайтесь с @DrArtemyeva".</span><span class="sxs-lookup"><span data-stu-id="ad5fe-120">Please contact @DrEhrle for any emergencies."</span></span>  <span data-ttu-id="ad5fe-121">Другие коллеги понимают, что произошло делегирование, так как при попытке связаться с доктором Безруковым они связываются с доктором Артемьевой вместо него.</span><span class="sxs-lookup"><span data-stu-id="ad5fe-121">Others on the team realize the delegation happened as they're attempting to contact Dr. Piccio, so they now know to contact Dr. Ehrle in the meantime.</span></span> <span data-ttu-id="ad5fe-122">В результате не возникает путаницы при уходе за пациентами.</span><span class="sxs-lookup"><span data-stu-id="ad5fe-122">Little to no confusion ensues with a patient's care.</span></span>

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a><span data-ttu-id="ad5fe-123">Влияние режимов сосуществования на статус пользователя в клиенте Teams</span><span class="sxs-lookup"><span data-stu-id="ad5fe-123">Impact of co-existence modes on user status in the Teams client</span></span>

<span data-ttu-id="ad5fe-124">Администраторам следует помнить, что поведение подписей к статусу и упоминаний представителей частично зависит от режима сосуществования пользователя.</span><span class="sxs-lookup"><span data-stu-id="ad5fe-124">Admins should be aware that status notes and delegation mention behaviors will depend partly on a user's co-existence mode.</span></span> <span data-ttu-id="ad5fe-125">В этой таблице показаны возможные варианты.</span><span class="sxs-lookup"><span data-stu-id="ad5fe-125">This matrix shows the possibilities:</span></span>

|<span data-ttu-id="ad5fe-126">Режим сосуществования</span><span class="sxs-lookup"><span data-stu-id="ad5fe-126">Co-Existence Mode</span></span> | <span data-ttu-id="ad5fe-127">Ожидаемое поведение</span><span class="sxs-lookup"><span data-stu-id="ad5fe-127">Expected Behavior</span></span>|
|---|---|
|<span data-ttu-id="ad5fe-128">Только Teams</span><span class="sxs-lookup"><span data-stu-id="ad5fe-128">TeamsOnly</span></span> |<span data-ttu-id="ad5fe-129">Пользователи могут устанавливать подпись только из Teams.</span><span class="sxs-lookup"><span data-stu-id="ad5fe-129">Users can set a note only from Teams.</span></span> <br> <span data-ttu-id="ad5fe-130">Подпись из Teams пользователя отображается в Teams и Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="ad5fe-130">User's Teams note is visible in Teams & SfB.</span></span> |
|<span data-ttu-id="ad5fe-131">Острова</span><span class="sxs-lookup"><span data-stu-id="ad5fe-131">Islands</span></span> | <span data-ttu-id="ad5fe-132">Установленная в Teams подпись пользователя отображается только в Teams.</span><span class="sxs-lookup"><span data-stu-id="ad5fe-132">User's note set in Teams visible only in Teams.</span></span> <br> <span data-ttu-id="ad5fe-133">Установленная в Skype для бизнеса подпись пользователя отображается только в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="ad5fe-133">User's note set in SfB visible only in SfB</span></span> |
|<span data-ttu-id="ad5fe-134">Режимы SfB\*</span><span class="sxs-lookup"><span data-stu-id="ad5fe-134">SfB\* modes</span></span> | <span data-ttu-id="ad5fe-135">Пользователи могут устанавливать подпись только из Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="ad5fe-135">Users can set a note only from SfB.</span></span> <br> <span data-ttu-id="ad5fe-136">Подпись из Skype для бизнеса пользователя отображается в Skype для бизнеса и Teams.</span><span class="sxs-lookup"><span data-stu-id="ad5fe-136">User's SfB note is visible in SfB & Teams.</span></span>  |
|||

<span data-ttu-id="ad5fe-137">Пользователь может устанавливать подпись в Teams, только если используется режим "Только Teams" или "Острова".</span><span class="sxs-lookup"><span data-stu-id="ad5fe-137">A user can only set a note in Teams if their mode is TeamsOnly or Islands.</span></span>  

### <a name="displaying-notes-set-in-skype-for-business"></a><span data-ttu-id="ad5fe-138">Отображение подписей, установленных в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="ad5fe-138">Displaying notes set in Skype for Business</span></span>
  
<span data-ttu-id="ad5fe-139">Отсутствует визуальное указание того, что подпись установлена из Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="ad5fe-139">There is no visual indication that a note was set from Skype for Business.</span></span>

<span data-ttu-id="ad5fe-140">В Skype для бизнеса не ограничивается количество символов в подписях к статусу.</span><span class="sxs-lookup"><span data-stu-id="ad5fe-140">Skype for Business doesn't enforce a character limit on status notes.</span></span> <span data-ttu-id="ad5fe-141">В Microsoft Teams отображаются только первые 280 символов подписи, установленной из Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="ad5fe-141">Microsoft Teams will only display the first 280 characters of a note set from Skype for Business.</span></span> <span data-ttu-id="ad5fe-142">Многоточие (...) в конце подписи указывает на усечение.</span><span class="sxs-lookup"><span data-stu-id="ad5fe-142">An ellipse (…) at the end of a note indicates truncation.</span></span>
  
<span data-ttu-id="ad5fe-143">Skype для бизнеса не поддерживает срок действия для подписей.</span><span class="sxs-lookup"><span data-stu-id="ad5fe-143">Skype for Business doesn't support expiry times for notes.</span></span>

<span data-ttu-id="ad5fe-144">Перенос подписей из Skype для бизнеса в Teams не поддерживается при обновлении пользователя до режима "Только Teams".</span><span class="sxs-lookup"><span data-stu-id="ad5fe-144">Migration of notes from Skype for Business to Teams is not supported when a user is upgraded to TeamsOnly mode.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ad5fe-145">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="ad5fe-145">Related topics</span></span>

[<span data-ttu-id="ad5fe-146">Сосуществование со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="ad5fe-146">Coexistence with Skype for Business</span></span>](../../coexistence-chat-calls-presence.md)
