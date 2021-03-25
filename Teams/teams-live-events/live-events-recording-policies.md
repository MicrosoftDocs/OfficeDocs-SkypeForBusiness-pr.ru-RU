---
title: Политики записи трансляций
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: christi.balaki
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Узнайте о политиках записи трансляций.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7a5f793230798c68f0a39e2d9a3500eab9791065
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119168"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a><span data-ttu-id="2ba69-103">Политики записи трансляций в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2ba69-103">Live event recording policies in Microsoft Teams</span></span>

<span data-ttu-id="2ba69-104">У вас есть несколько вариантов записи трансляции Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2ba69-104">You have several options for recording a Microsoft Teams live event.</span></span> <span data-ttu-id="2ba69-105">Параметры записи за устанавливаются с помощью политик записи.</span><span class="sxs-lookup"><span data-stu-id="2ba69-105">The recording options are set using recording policies.</span></span> <span data-ttu-id="2ba69-106">В этой статье описаны различные параметры.</span><span class="sxs-lookup"><span data-stu-id="2ba69-106">This article describes the various settings.</span></span>

<span data-ttu-id="2ba69-107">Параметры записи задаются с помощью команды PowerShell [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="2ba69-107">The recording options are set using the PowerShell command [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)</span></span>

## <a name="scheduling-and-option-behaviors"></a><span data-ttu-id="2ba69-108">Планирование и поведение вариантов</span><span class="sxs-lookup"><span data-stu-id="2ba69-108">Scheduling and option behaviors</span></span>

<span data-ttu-id="2ba69-109">При планировании записи трансляции доступны два параметра организатора:</span><span class="sxs-lookup"><span data-stu-id="2ba69-109">There are two organizer options while scheduling a live event recording:</span></span>

- <span data-ttu-id="2ba69-110">Запись доступна для звукозаписей и звукозаписей.</span><span class="sxs-lookup"><span data-stu-id="2ba69-110">Recording available for producers and presenters</span></span>

  - <span data-ttu-id="2ba69-111">Файл записи: предоставляет файл записи, который организаторы и организаторы могут скачать после окончания события.</span><span class="sxs-lookup"><span data-stu-id="2ba69-111">Recording file: Provides a recording file that producers and presenters can download after the event is over.</span></span>

- <span data-ttu-id="2ba69-112">Запись доступна участникам</span><span class="sxs-lookup"><span data-stu-id="2ba69-112">Recording available for attendees</span></span>

  - <span data-ttu-id="2ba69-113">DVR: цифровое видеореференцию позволяет участникам перемотать событие назад и приостановить его</span><span class="sxs-lookup"><span data-stu-id="2ba69-113">DVR: A digital video recorder (DVR) allows attendees to rewind and pause during the event</span></span>

  - <span data-ttu-id="2ba69-114">VOD: видео по запросу (VOD) позволяет участникам следить за событием после его окончания.</span><span class="sxs-lookup"><span data-stu-id="2ba69-114">VOD: A video on demand (VOD) allows attendees to watch after the event is over</span></span>

## <a name="broadcast-recording-policy-setting"></a><span data-ttu-id="2ba69-115">Параметр политики трансляции записи</span><span class="sxs-lookup"><span data-stu-id="2ba69-115">Broadcast recording policy setting</span></span>

<span data-ttu-id="2ba69-116">В рамках политики трансляции можно включить или отключить запись трансляции.</span><span class="sxs-lookup"><span data-stu-id="2ba69-116">As part of the broadcast policy, there's a setting that you can toggle to turn recording on or off for a live event.</span></span>

|                                 | <span data-ttu-id="2ba69-117">Запись доступна для звукозаписей и звукозаписей.</span><span class="sxs-lookup"><span data-stu-id="2ba69-117">Recording available for producers and presenters</span></span> | <span data-ttu-id="2ba69-118">Запись доступна для участников</span><span class="sxs-lookup"><span data-stu-id="2ba69-118">Recording available for attendees</span></span> |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| <span data-ttu-id="2ba69-119">Всегда записывать</span><span class="sxs-lookup"><span data-stu-id="2ba69-119">Always record</span></span>               | <span data-ttu-id="2ba69-120">Отключено и выбрано</span><span class="sxs-lookup"><span data-stu-id="2ba69-120">Disabled and selected</span></span>                                | <span data-ttu-id="2ba69-121">Отключено и выбрано</span><span class="sxs-lookup"><span data-stu-id="2ba69-121">Disabled and selected</span></span>         |
| <span data-ttu-id="2ba69-122">Организатор может записывать или нет</span><span class="sxs-lookup"><span data-stu-id="2ba69-122">Organizer can record or not</span></span> | <span data-ttu-id="2ba69-123">Включена и не выбрана по умолчанию</span><span class="sxs-lookup"><span data-stu-id="2ba69-123">Enabled and not selected by default</span></span>                  | <span data-ttu-id="2ba69-124">Включена и не выбрана по умолчанию</span><span class="sxs-lookup"><span data-stu-id="2ba69-124">Enabled and not selected by default</span></span>   |
| <span data-ttu-id="2ba69-125">Никогда не записывать</span><span class="sxs-lookup"><span data-stu-id="2ba69-125">Never record</span></span>               | <span data-ttu-id="2ba69-126">Отключена и не выбрана</span><span class="sxs-lookup"><span data-stu-id="2ba69-126">Disabled and not selected</span></span>                            | <span data-ttu-id="2ba69-127">Отключена и не выбрана</span><span class="sxs-lookup"><span data-stu-id="2ba69-127">Disabled and not selected</span></span>      |

<span data-ttu-id="2ba69-128">Если для политики установлено параметр **"Всегда записывать",** на странице политики есть следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="2ba69-128">When the policy is set to **Always record**, the policy page has the following selected options:</span></span>

<span data-ttu-id="2ba69-129">![Параметры политики трансляций](../media/live-event-recording-policy.png "Снимок экрана с параметрами политики трансляций в Центре администрирования Microsoft Teams")</span><span class="sxs-lookup"><span data-stu-id="2ba69-129">![live events policy settings](../media/live-event-recording-policy.png "Screen shot of live events policy settings in the Microsoft Teams admin center")</span></span>

## <a name="storage-and-persistence-behavior"></a><span data-ttu-id="2ba69-130">Сохранение и сохранение</span><span class="sxs-lookup"><span data-stu-id="2ba69-130">Storage and persistence behavior</span></span>

| <span data-ttu-id="2ba69-131">Действие</span><span class="sxs-lookup"><span data-stu-id="2ba69-131">Option</span></span>                                       | <span data-ttu-id="2ba69-132">State</span><span class="sxs-lookup"><span data-stu-id="2ba69-132">State</span></span>   | <span data-ttu-id="2ba69-133">DVR</span><span class="sxs-lookup"><span data-stu-id="2ba69-133">DVR</span></span>                                                   | <span data-ttu-id="2ba69-134">VOD</span><span class="sxs-lookup"><span data-stu-id="2ba69-134">VOD</span></span>                                                     | <span data-ttu-id="2ba69-135">Запись</span><span class="sxs-lookup"><span data-stu-id="2ba69-135">Recording</span></span>                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| <span data-ttu-id="2ba69-136">Запись доступна для звукозаписей.</span><span class="sxs-lookup"><span data-stu-id="2ba69-136">Recording available to producers and presenters</span></span> | <span data-ttu-id="2ba69-137">выбрано</span><span class="sxs-lookup"><span data-stu-id="2ba69-137">Selected</span></span>     | <span data-ttu-id="2ba69-138">Доступен DVR, и актив служб мультимедиа Azure (AMS) хранится в течение 180 дней</span><span class="sxs-lookup"><span data-stu-id="2ba69-138">DVR is available and the Azure Media Services (AMS) asset is stored for 180 days</span></span> | <span data-ttu-id="2ba69-139">Участники могут получить доступ к событию и посмотреть его</span><span class="sxs-lookup"><span data-stu-id="2ba69-139">Attendee can access and watch the event</span></span>                     |                              |
|                                                  | <span data-ttu-id="2ba69-140">Не выбрано</span><span class="sxs-lookup"><span data-stu-id="2ba69-140">Not Selected</span></span> | <span data-ttu-id="2ba69-141">Доступен DVR, актив AMS хранится 180 дней</span><span class="sxs-lookup"><span data-stu-id="2ba69-141">DVR is available and the AMS asset is stored for 180 days</span></span> | <span data-ttu-id="2ba69-142">Участник не получит доступ к событию после его окончания</span><span class="sxs-lookup"><span data-stu-id="2ba69-142">Attendee won't get access into the event after it's over</span></span> |                              |
||<span data-ttu-id="2ba69-143">Отключено (не выбрано)</span><span class="sxs-lookup"><span data-stu-id="2ba69-143">Disabled (Not selected)</span></span>|<span data-ttu-id="2ba69-144">Доступен DVR, а актив AMS удаляется после события</span><span class="sxs-lookup"><span data-stu-id="2ba69-144">DVR is available and the AMS asset is deleted after the event</span></span>|<span data-ttu-id="2ba69-145">Участник не получит доступ к событию после его окончания</span><span class="sxs-lookup"><span data-stu-id="2ba69-145">Attendee won't get access into the event after it's over</span></span>||
| <span data-ttu-id="2ba69-146">Запись доступна для звукозаписей.</span><span class="sxs-lookup"><span data-stu-id="2ba69-146">Recording available to producers and presenters</span></span> | <span data-ttu-id="2ba69-147">выбрано</span><span class="sxs-lookup"><span data-stu-id="2ba69-147">Selected</span></span>     |                                                           |                                                             | <span data-ttu-id="2ba69-148">Создается и сохраняется MP4-</span><span class="sxs-lookup"><span data-stu-id="2ba69-148">An MP4 is created and stored</span></span> |
|                                                  | <span data-ttu-id="2ba69-149">Не выбрано</span><span class="sxs-lookup"><span data-stu-id="2ba69-149">Not Selected</span></span> |                                                           |                                                             | <span data-ttu-id="2ba69-150">Файл не создан</span><span class="sxs-lookup"><span data-stu-id="2ba69-150">No file is created</span></span>           |

### <a name="related-topics"></a><span data-ttu-id="2ba69-151">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="2ba69-151">Related topics</span></span>

- [<span data-ttu-id="2ba69-152">Что такое трансляции Teams?</span><span class="sxs-lookup"><span data-stu-id="2ba69-152">What is Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="2ba69-153">Планирование трансляций Teams</span><span class="sxs-lookup"><span data-stu-id="2ba69-153">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="2ba69-154">Настройка параметров трансляций в Teams</span><span class="sxs-lookup"><span data-stu-id="2ba69-154">Configure live events settings in Teams</span></span>](configure-teams-live-events.md)
- [<span data-ttu-id="2ba69-155">Запись собраний в облаке Teams</span><span class="sxs-lookup"><span data-stu-id="2ba69-155">Teams clouds meeting recording</span></span>](../cloud-recording.md)