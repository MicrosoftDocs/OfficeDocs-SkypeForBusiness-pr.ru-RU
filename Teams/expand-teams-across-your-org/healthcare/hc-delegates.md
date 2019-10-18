---
title: Делегирование сообщений
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: Пользователь может явным образом задать в сообщении о состоянии другого пользователя в качестве делегата.
ms.openlocfilehash: 56c0e9bd5394e738170130bab15803e5cb4d741c
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570362"
---
# <a name="message-delegation"></a><span data-ttu-id="adcde-103">Делегирование сообщений</span><span class="sxs-lookup"><span data-stu-id="adcde-103">Message delegation</span></span>

<span data-ttu-id="adcde-104">Пользователь уже может явно задать состояние "нет на месте" или "не беспокоить", а также задать пользовательский текст.</span><span class="sxs-lookup"><span data-stu-id="adcde-104">A user can already explicitly set their status to Away or Do not Disturb, and provide custom text.</span></span> <span data-ttu-id="adcde-105">Функция делегирования сообщений действует следующим образом:</span><span class="sxs-lookup"><span data-stu-id="adcde-105">The message delegation feature works as follows:</span></span>

1. <span data-ttu-id="adcde-106">Пользователь @username упоминает другого пользователя в рамках текстового сообщения о состоянии, предлагая, что, если он не был недоступен пользователям, которые хотят связаться с ними, и связаться с @username указанным пользователем.</span><span class="sxs-lookup"><span data-stu-id="adcde-106">A user @username mentions another user in part of a text status message, suggesting that while they are unavailable people who want to contact them instead contact the @username mentioned user.</span></span>
2. <span data-ttu-id="adcde-107">Пользователь, который был назначен представителем, уведомлен о том, что он является представителем.</span><span class="sxs-lookup"><span data-stu-id="adcde-107">The person who has been assigned as a delegate is notified that they were nominated to be a delegate.</span></span>
3. <span data-ttu-id="adcde-108">Кто-то, кто пытается связаться с первым пользователем, может затем навести указатель мыши на назначенный делегат и просто передать ему сообщение.</span><span class="sxs-lookup"><span data-stu-id="adcde-108">Someone trying to contact the first user can then hover over the nominated delegate and easily message the delegate instead.</span></span>  

<span data-ttu-id="adcde-109">Это процесс, инициированный пользователем, в клиенте, и для включения функции не требуется вмешательства администратора.</span><span class="sxs-lookup"><span data-stu-id="adcde-109">This is a user-initiated process in the client, and no Admin involvement is required to enable the feature.</span></span> 

## <a name="delegation-use-scenario-in-healthcare"></a><span data-ttu-id="adcde-110">Сценарии использования делегирования в здравоохранение</span><span class="sxs-lookup"><span data-stu-id="adcde-110">Delegation use scenario in Healthcare</span></span>

<span data-ttu-id="adcde-111">*Пример использования без настройки делегатов:*  Доктор Франко ПикЦио – это звонок в отделе радиологи.</span><span class="sxs-lookup"><span data-stu-id="adcde-111">*Usage example without setting delegates:*  Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="adcde-112">Он получает срочный звонок и должен выйти за последующие несколько часов.</span><span class="sxs-lookup"><span data-stu-id="adcde-112">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="adcde-113">Он запрашивает у одного из своих коллег в отделе радиологи, Dr. Лена Ехрле, и, если он пропала.</span><span class="sxs-lookup"><span data-stu-id="adcde-113">He asks one of his peers in the radiology department, Dr. Lena Ehrle, to cover for him while he is gone.</span></span> <span data-ttu-id="adcde-114">Он по своему направлению на пейджер в Dr. Ехрле, кто прослушивает срочные сообщения и ping на пейджер и отвечает на них от имени Dr. ПикЦио в дополнение к текущим обязанностям.</span><span class="sxs-lookup"><span data-stu-id="adcde-114">He informally hands over his pager to Dr. Ehrle, who is listening for urgent messages and pings on the pager and responds to them on behalf of Dr. Piccio in addition to her current responsibilities.</span></span> <span data-ttu-id="adcde-115">Другие участники группы могут не реализовать неформального делегирования, и они признаются с осторожностью пациента.</span><span class="sxs-lookup"><span data-stu-id="adcde-115">Others on the team may not realize the informal delegation happened, and confusion ensues with a patient's care.</span></span>

<span data-ttu-id="adcde-116">*Пример использования для настройки делегатов:* Доктор Франко ПикЦио – это звонок в отделе радиологи.</span><span class="sxs-lookup"><span data-stu-id="adcde-116">*Usage example with setting delegates:* Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="adcde-117">Он получает срочный звонок и должен выйти за последующие несколько часов.</span><span class="sxs-lookup"><span data-stu-id="adcde-117">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="adcde-118">Он запрашивает у одного из своих коллег в отделе радиологи, Dr. Лена Ехрле, пока он не пропала.</span><span class="sxs-lookup"><span data-stu-id="adcde-118">He asks one of his peers in the radiology department, Dr. Lena Ehrle to cover for him while he is gone.</span></span> <span data-ttu-id="adcde-119">Он изменяет свое сообщение о состоянии, например "я недоступен в течение следующих нескольких часов".</span><span class="sxs-lookup"><span data-stu-id="adcde-119">He changes his custom status message to say something similar to "I am unavailable for the next few hours.</span></span> <span data-ttu-id="adcde-120">Пожалуйста, свяжитесь с @DrEhrle для всех повременных ситуаций.</span><span class="sxs-lookup"><span data-stu-id="adcde-120">Please contact @DrEhrle for any emergencies."</span></span>  <span data-ttu-id="adcde-121">Другие участники команды узнают о том, что делегирование происходило при попытке связаться с программой Dr. ПикЦио, поэтому теперь они уже знают, как связаться с программой Dr. Ехрле.</span><span class="sxs-lookup"><span data-stu-id="adcde-121">Others on the team realize the delegation happened as they're attempting to contact Dr. Piccio, so they now know to contact Dr. Ehrle in the meantime.</span></span> <span data-ttu-id="adcde-122">Очень просто не достает путаницы с осторожностью пациента.</span><span class="sxs-lookup"><span data-stu-id="adcde-122">Little to no confusion ensues with a patient's care.</span></span>

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a><span data-ttu-id="adcde-123">Влияние режима совместного существования на состояние пользователя в клиенте Teams</span><span class="sxs-lookup"><span data-stu-id="adcde-123">Impact of co-existence modes on user status in the Teams client</span></span>

<span data-ttu-id="adcde-124">Администраторам следует помнить, что заметка о состоянии и поведение упоминания о делегировании будут частично зависеть от режима совместного существования пользователя.</span><span class="sxs-lookup"><span data-stu-id="adcde-124">Admins should be aware that status notes and delegation mention behaviors will depend partly on a user’s co-existence mode.</span></span> <span data-ttu-id="adcde-125">В этой матрице показаны возможности:</span><span class="sxs-lookup"><span data-stu-id="adcde-125">This matrix shows the possibilities:</span></span>

|<span data-ttu-id="adcde-126">Режим совместного существования</span><span class="sxs-lookup"><span data-stu-id="adcde-126">Co-Existence Mode</span></span> | <span data-ttu-id="adcde-127">Ожидаемое поведение</span><span class="sxs-lookup"><span data-stu-id="adcde-127">Expected Behavior</span></span>|
|---|---|
|<span data-ttu-id="adcde-128">TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="adcde-128">TeamsOnly</span></span> |<span data-ttu-id="adcde-129">Пользователи могут устанавливать заметки только из Teams.</span><span class="sxs-lookup"><span data-stu-id="adcde-129">Users can set a note only from Teams.</span></span> <br> <span data-ttu-id="adcde-130">В Teams & SfB отображается Примечание для пользователей Teams.</span><span class="sxs-lookup"><span data-stu-id="adcde-130">User’s Teams note is visible in Teams & SfB.</span></span> |
|<span data-ttu-id="adcde-131">Блоки</span><span class="sxs-lookup"><span data-stu-id="adcde-131">Islands</span></span> | <span data-ttu-id="adcde-132">Заметки пользователя в Teams видны только в Teams.</span><span class="sxs-lookup"><span data-stu-id="adcde-132">User’s note set in Teams visible only in Teams.</span></span> <br> <span data-ttu-id="adcde-133">Примечание пользователя, установленное в SfB, видимо только в SfB</span><span class="sxs-lookup"><span data-stu-id="adcde-133">User’s note set in SfB visible only in SfB</span></span> |
|<span data-ttu-id="adcde-134">Режимы SfB \*</span><span class="sxs-lookup"><span data-stu-id="adcde-134">SfB\* modes</span></span> | <span data-ttu-id="adcde-135">Пользователи могут устанавливать заметку только из SfB.</span><span class="sxs-lookup"><span data-stu-id="adcde-135">Users can set a note only from SfB.</span></span> <br> <span data-ttu-id="adcde-136">SfB Примечание пользователя отображается в SfB & Teams.</span><span class="sxs-lookup"><span data-stu-id="adcde-136">User’s SfB note is visible in SfB & Teams.</span></span>  |
|||

<span data-ttu-id="adcde-137">Пользователь может настроить заметку в Teams только в том случае, если ее режим — Теамсонли или острова.</span><span class="sxs-lookup"><span data-stu-id="adcde-137">A user can only set a note in Teams if their mode is TeamsOnly or Islands.</span></span>  

### <a name="displaying-notes-set-in-skype-for-business"></a><span data-ttu-id="adcde-138">Отображение заметок, заданных в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="adcde-138">Displaying notes set in Skype for Business</span></span>
  
<span data-ttu-id="adcde-139">Не существует визуальной индикации того, что заметка была задана в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="adcde-139">There is no visual indication that a note was set from Skype for Business.</span></span>

<span data-ttu-id="adcde-140">В Skype для бизнеса не используется ограничение на количество символов в заметках о состоянии.</span><span class="sxs-lookup"><span data-stu-id="adcde-140">Skype for Business doesn’t enforce a character limit on status notes.</span></span> <span data-ttu-id="adcde-141">В Microsoft Teams будут отображаться только первые 280 символов набора заметок из Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="adcde-141">Microsoft Teams will only display the first 280 characters of a note set from Skype for Business.</span></span> <span data-ttu-id="adcde-142">Многоточие (...) в конце заметки указывает на усечение.</span><span class="sxs-lookup"><span data-stu-id="adcde-142">An ellipse (…) at the end of a note indicates truncation.</span></span>
  
<span data-ttu-id="adcde-143">В Skype для бизнеса не поддерживаются значения времени окончания заметок.</span><span class="sxs-lookup"><span data-stu-id="adcde-143">Skype for Business doesn’t support expiry times for notes.</span></span>

<span data-ttu-id="adcde-144">Миграция заметок из Skype для бизнеса в Teams не поддерживается, когда пользователь обновляется до Теамсонли Mode.</span><span class="sxs-lookup"><span data-stu-id="adcde-144">Migration of notes from Skype for Business to Teams is not supported when a user is upgraded to TeamsOnly mode.</span></span>

## <a name="related-topics"></a><span data-ttu-id="adcde-145">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="adcde-145">Related topics</span></span>

[<span data-ttu-id="adcde-146">Сосуществование со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="adcde-146">Coexistence with Skype for Business</span></span>](../../coexistence-chat-calls-presence.md)
