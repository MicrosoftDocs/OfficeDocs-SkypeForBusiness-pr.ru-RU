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
ms.openlocfilehash: 8d25f37f94a514b83bd37e44d1b022bac064a839
ms.sourcegitcommit: 3840d72f9ad1c0c7803dc3662a0318f558fe92ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739659"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a><span data-ttu-id="6f7f2-103">Политики записи трансляций в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6f7f2-103">Live event recording policies in Microsoft Teams</span></span>

<span data-ttu-id="6f7f2-104">У вас есть несколько вариантов записи Microsoft Teams трансляции.</span><span class="sxs-lookup"><span data-stu-id="6f7f2-104">You have several options for recording a Microsoft Teams live event.</span></span> <span data-ttu-id="6f7f2-105">Параметры записи настроены с помощью политик записи.</span><span class="sxs-lookup"><span data-stu-id="6f7f2-105">The recording options are set using recording policies.</span></span> <span data-ttu-id="6f7f2-106">В этой статье описаны различные параметры.</span><span class="sxs-lookup"><span data-stu-id="6f7f2-106">This article describes the various settings.</span></span>

<span data-ttu-id="6f7f2-107">Параметры записи задаются с помощью команды [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f7f2-107">The recording options are set using the PowerShell command [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps).</span></span>

## <a name="scheduling-and-option-behaviors"></a><span data-ttu-id="6f7f2-108">Планирование и поведение вариантов</span><span class="sxs-lookup"><span data-stu-id="6f7f2-108">Scheduling and option behaviors</span></span>

<span data-ttu-id="6f7f2-109">При планировании трансляции можно запланировать запись двух организаторов:</span><span class="sxs-lookup"><span data-stu-id="6f7f2-109">There are two organizer options while scheduling a live event recording:</span></span>

- <span data-ttu-id="6f7f2-110">Запись доступна для звукозаписей и звукозаписей</span><span class="sxs-lookup"><span data-stu-id="6f7f2-110">Recording available for producers and presenters</span></span>

  - <span data-ttu-id="6f7f2-111">Файл записи: предоставляет файл записи, который организаторы и организаторы могут скачать после окончания события.</span><span class="sxs-lookup"><span data-stu-id="6f7f2-111">Recording file: Provides a recording file that producers and presenters can download after the event is over.</span></span>

- <span data-ttu-id="6f7f2-112">Запись доступна для участников</span><span class="sxs-lookup"><span data-stu-id="6f7f2-112">Recording available for attendees</span></span>

  - <span data-ttu-id="6f7f2-113">DVR: DVR позволяет участникам перемотать и приостанавлить во время события</span><span class="sxs-lookup"><span data-stu-id="6f7f2-113">DVR: A digital video recorder (DVR) allows attendees to rewind and pause during the event</span></span>

  - <span data-ttu-id="6f7f2-114">VOD: видео по запросу (VOD) позволяет участникам смотреть после окончания события</span><span class="sxs-lookup"><span data-stu-id="6f7f2-114">VOD: A video on demand (VOD) allows attendees to watch after the event is over</span></span>

## <a name="broadcast-recording-policy-setting"></a><span data-ttu-id="6f7f2-115">Параметр политики трансляции записи</span><span class="sxs-lookup"><span data-stu-id="6f7f2-115">Broadcast recording policy setting</span></span>

<span data-ttu-id="6f7f2-116">В рамках политики трансляции можно включить или отключить запись для трансляции.</span><span class="sxs-lookup"><span data-stu-id="6f7f2-116">As part of the broadcast policy, there's a setting that you can toggle to turn recording on or off for a live event.</span></span>

|                                 | <span data-ttu-id="6f7f2-117">Запись доступна для звукозаписей и звукозаписей</span><span class="sxs-lookup"><span data-stu-id="6f7f2-117">Recording available for producers and presenters</span></span> | <span data-ttu-id="6f7f2-118">Запись доступна для участников</span><span class="sxs-lookup"><span data-stu-id="6f7f2-118">Recording available for attendees</span></span> |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| <span data-ttu-id="6f7f2-119">Всегда записывать</span><span class="sxs-lookup"><span data-stu-id="6f7f2-119">Always record</span></span>               | <span data-ttu-id="6f7f2-120">Отключено и выбрано</span><span class="sxs-lookup"><span data-stu-id="6f7f2-120">Disabled and selected</span></span>                                | <span data-ttu-id="6f7f2-121">Включено и выбрано</span><span class="sxs-lookup"><span data-stu-id="6f7f2-121">Enabled and selected</span></span>         |
| <span data-ttu-id="6f7f2-122">Организатор может записывать или нет</span><span class="sxs-lookup"><span data-stu-id="6f7f2-122">Organizer can record or not</span></span> | <span data-ttu-id="6f7f2-123">Включено и выбрано по умолчанию</span><span class="sxs-lookup"><span data-stu-id="6f7f2-123">Enabled and selected by default</span></span>                  | <span data-ttu-id="6f7f2-124">Включено и выбрано по умолчанию</span><span class="sxs-lookup"><span data-stu-id="6f7f2-124">Enabled and selected by default</span></span>   |
| <span data-ttu-id="6f7f2-125">Никогда не записый</span><span class="sxs-lookup"><span data-stu-id="6f7f2-125">Never record</span></span>               | <span data-ttu-id="6f7f2-126">Отключено и не выбрано</span><span class="sxs-lookup"><span data-stu-id="6f7f2-126">Disabled and not selected</span></span>                            | <span data-ttu-id="6f7f2-127">Отключено и не выбрано</span><span class="sxs-lookup"><span data-stu-id="6f7f2-127">Disabled and not selected</span></span>      |

## <a name="storage-and-persistence-behavior"></a><span data-ttu-id="6f7f2-128">служба хранилища и сохранение</span><span class="sxs-lookup"><span data-stu-id="6f7f2-128">Storage and persistence behavior</span></span>

| <span data-ttu-id="6f7f2-129">Действие</span><span class="sxs-lookup"><span data-stu-id="6f7f2-129">Option</span></span>                                       | <span data-ttu-id="6f7f2-130">State</span><span class="sxs-lookup"><span data-stu-id="6f7f2-130">State</span></span>   | <span data-ttu-id="6f7f2-131">Dvr</span><span class="sxs-lookup"><span data-stu-id="6f7f2-131">DVR</span></span>                                                   | <span data-ttu-id="6f7f2-132">Vod</span><span class="sxs-lookup"><span data-stu-id="6f7f2-132">VOD</span></span>                                                     | <span data-ttu-id="6f7f2-133">Запись</span><span class="sxs-lookup"><span data-stu-id="6f7f2-133">Recording</span></span>                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| <span data-ttu-id="6f7f2-134">Запись доступна для участников</span><span class="sxs-lookup"><span data-stu-id="6f7f2-134">Recording available for attendees</span></span> | <span data-ttu-id="6f7f2-135">выбрано</span><span class="sxs-lookup"><span data-stu-id="6f7f2-135">Selected</span></span>     | <span data-ttu-id="6f7f2-136">Доступен DVR, актив Службы мультимедиа Azure amS хранится в течение 180 дней</span><span class="sxs-lookup"><span data-stu-id="6f7f2-136">DVR is available and the Azure Media Services (AMS) asset is stored for 180 days</span></span> | <span data-ttu-id="6f7f2-137">Участники могут получать доступ к событию и смотреть его</span><span class="sxs-lookup"><span data-stu-id="6f7f2-137">Attendee can access and watch the event</span></span>                     |                              |
|                                                  | <span data-ttu-id="6f7f2-138">Не выбрано</span><span class="sxs-lookup"><span data-stu-id="6f7f2-138">Not Selected</span></span> | <span data-ttu-id="6f7f2-139">DVR доступен, а актив AMS хранится в течение 180 дней</span><span class="sxs-lookup"><span data-stu-id="6f7f2-139">DVR is available and the AMS asset is stored for 180 days</span></span> | <span data-ttu-id="6f7f2-140">Участник не получит доступ к событию после его окончания</span><span class="sxs-lookup"><span data-stu-id="6f7f2-140">Attendee won't get access into the event after it's over</span></span> |                              |
||<span data-ttu-id="6f7f2-141">Отключено (не выбрано)</span><span class="sxs-lookup"><span data-stu-id="6f7f2-141">Disabled (Not selected)</span></span>|<span data-ttu-id="6f7f2-142">DVR доступен, а актив AMS удаляется после события</span><span class="sxs-lookup"><span data-stu-id="6f7f2-142">DVR is available and the AMS asset is deleted after the event</span></span>|<span data-ttu-id="6f7f2-143">Участник не получит доступ к событию после его окончания</span><span class="sxs-lookup"><span data-stu-id="6f7f2-143">Attendee won't get access into the event after it's over</span></span>||
| <span data-ttu-id="6f7f2-144">Запись доступна для звукозаписей и звукозаписей</span><span class="sxs-lookup"><span data-stu-id="6f7f2-144">Recording available to producers and presenters</span></span> | <span data-ttu-id="6f7f2-145">выбрано</span><span class="sxs-lookup"><span data-stu-id="6f7f2-145">Selected</span></span>     |                                                           |                                                             | <span data-ttu-id="6f7f2-146">Создается и сохраняется MP4-</span><span class="sxs-lookup"><span data-stu-id="6f7f2-146">An MP4 is created and stored</span></span> |
|                                                  | <span data-ttu-id="6f7f2-147">Не выбрано</span><span class="sxs-lookup"><span data-stu-id="6f7f2-147">Not Selected</span></span> |                                                           |                                                             | <span data-ttu-id="6f7f2-148">Файл не создается</span><span class="sxs-lookup"><span data-stu-id="6f7f2-148">No file is created</span></span>           |

### <a name="related-topics"></a><span data-ttu-id="6f7f2-149">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="6f7f2-149">Related topics</span></span>

- [<span data-ttu-id="6f7f2-150">Что такое трансляции Teams?</span><span class="sxs-lookup"><span data-stu-id="6f7f2-150">What is Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="6f7f2-151">Планирование трансляций Teams</span><span class="sxs-lookup"><span data-stu-id="6f7f2-151">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="6f7f2-152">Настройка параметров трансляций в Teams</span><span class="sxs-lookup"><span data-stu-id="6f7f2-152">Configure live events settings in Teams</span></span>](configure-teams-live-events.md)
- [<span data-ttu-id="6f7f2-153">Teams записи собраний в облаке</span><span class="sxs-lookup"><span data-stu-id="6f7f2-153">Teams clouds meeting recording</span></span>](../cloud-recording.md)
