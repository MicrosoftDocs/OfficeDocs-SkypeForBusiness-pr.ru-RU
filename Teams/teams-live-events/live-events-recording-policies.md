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
ms.openlocfilehash: 9fd67ce67d31effdba0d152a3d5920bb17f23b25
ms.sourcegitcommit: 31a585cc0fe6350efacf3a7771d1e590d5e4233c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/10/2021
ms.locfileid: "50615178"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a><span data-ttu-id="b08e1-103">Политики записи трансляций в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b08e1-103">Live event recording policies in Microsoft Teams</span></span>

<span data-ttu-id="b08e1-104">У вас есть несколько вариантов записи трансляции Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b08e1-104">You have several options for recording a Microsoft Teams live event.</span></span> <span data-ttu-id="b08e1-105">Параметры записи за устанавливаются с помощью политик записи.</span><span class="sxs-lookup"><span data-stu-id="b08e1-105">The recording options are set using recording policies.</span></span> <span data-ttu-id="b08e1-106">В этой статье описаны различные параметры.</span><span class="sxs-lookup"><span data-stu-id="b08e1-106">This article describes the various settings.</span></span>

<span data-ttu-id="b08e1-107">Параметры записи задаются с помощью команды PowerShell [Set-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="b08e1-107">The recording options are set using the PowerShell command [Set-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)</span></span>

## <a name="scheduling-and-option-behaviors"></a><span data-ttu-id="b08e1-108">Планирование и поведение вариантов</span><span class="sxs-lookup"><span data-stu-id="b08e1-108">Scheduling and option behaviors</span></span>

<span data-ttu-id="b08e1-109">При планировании записи трансляции доступны два параметра организатора:</span><span class="sxs-lookup"><span data-stu-id="b08e1-109">There are two organizer options while scheduling a live event recording:</span></span>

- <span data-ttu-id="b08e1-110">Запись доступна для звукозаписей и звукозаписей.</span><span class="sxs-lookup"><span data-stu-id="b08e1-110">Recording available for producers and presenters</span></span>

  - <span data-ttu-id="b08e1-111">Файл записи: предоставляет файл записи, который организаторы и организаторы могут скачать после окончания события.</span><span class="sxs-lookup"><span data-stu-id="b08e1-111">Recording file: Provides a recording file that producers and presenters can download after the event is over.</span></span>

- <span data-ttu-id="b08e1-112">Запись доступна участникам</span><span class="sxs-lookup"><span data-stu-id="b08e1-112">Recording available for attendees</span></span>

  - <span data-ttu-id="b08e1-113">DVR: цифровое видеосъемка позволяет участникам перемотать и приостанавлить время события.</span><span class="sxs-lookup"><span data-stu-id="b08e1-113">DVR: A digital video recorder (DVR) allows attendees to rewind and pause during the event</span></span>

  - <span data-ttu-id="b08e1-114">VOD: видео по запросу (VOD) позволяет участникам следить за событием после его окончания.</span><span class="sxs-lookup"><span data-stu-id="b08e1-114">VOD: A video on demand (VOD) allows attendees to watch after the event is over</span></span>

## <a name="broadcast-recording-policy-setting"></a><span data-ttu-id="b08e1-115">Параметр политики трансляции записи</span><span class="sxs-lookup"><span data-stu-id="b08e1-115">Broadcast recording policy setting</span></span>

<span data-ttu-id="b08e1-116">В рамках политики трансляции можно включить или отключить запись трансляции.</span><span class="sxs-lookup"><span data-stu-id="b08e1-116">As part of the broadcast policy, there's a setting that you can toggle to turn recording on or off for a live event.</span></span>

|                                 | <span data-ttu-id="b08e1-117">Запись доступна для звукозаписей и звукозаписей.</span><span class="sxs-lookup"><span data-stu-id="b08e1-117">Recording available for producers and presenters</span></span> | <span data-ttu-id="b08e1-118">Запись доступна участникам</span><span class="sxs-lookup"><span data-stu-id="b08e1-118">Recording available for attendees</span></span> |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| <span data-ttu-id="b08e1-119">Всегда записывать</span><span class="sxs-lookup"><span data-stu-id="b08e1-119">Always record</span></span>               | <span data-ttu-id="b08e1-120">Отключено и выбрано</span><span class="sxs-lookup"><span data-stu-id="b08e1-120">Disabled and selected</span></span>                                | <span data-ttu-id="b08e1-121">Отключено и выбрано</span><span class="sxs-lookup"><span data-stu-id="b08e1-121">Disabled and selected</span></span>         |
| <span data-ttu-id="b08e1-122">Организатор может записывать или нет</span><span class="sxs-lookup"><span data-stu-id="b08e1-122">Organizer can record or not</span></span> | <span data-ttu-id="b08e1-123">Включена и не выбрана по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b08e1-123">Enabled and not selected by default</span></span>                  | <span data-ttu-id="b08e1-124">Включена и не выбрана по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b08e1-124">Enabled and not selected by default</span></span>   |
| <span data-ttu-id="b08e1-125">Никогда не записывать</span><span class="sxs-lookup"><span data-stu-id="b08e1-125">Never record</span></span>               | <span data-ttu-id="b08e1-126">Отключена и не выбрана</span><span class="sxs-lookup"><span data-stu-id="b08e1-126">Disabled and not selected</span></span>                            | <span data-ttu-id="b08e1-127">Отключена и не выбрана</span><span class="sxs-lookup"><span data-stu-id="b08e1-127">Disabled and not selected</span></span>      |

<span data-ttu-id="b08e1-128">Если для политики установлено параметр **"Всегда записывать",** на странице политики есть следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="b08e1-128">When the policy is set to **Always record**, the policy page has the following selected options:</span></span>

<span data-ttu-id="b08e1-129">![Параметры политики трансляций](../media/live-event-recording-policy.png "Снимок экрана с параметрами политики трансляций в Центре администрирования Microsoft Teams")</span><span class="sxs-lookup"><span data-stu-id="b08e1-129">![live events policy settings](../media/live-event-recording-policy.png "Screen shot of live events policy settings in the Microsoft Teams admin center")</span></span>

## <a name="storage-and-persistence-behavior"></a><span data-ttu-id="b08e1-130">Сохранение и сохранение</span><span class="sxs-lookup"><span data-stu-id="b08e1-130">Storage and persistence behavior</span></span>

| <span data-ttu-id="b08e1-131">Действие</span><span class="sxs-lookup"><span data-stu-id="b08e1-131">Option</span></span>                                       | <span data-ttu-id="b08e1-132">State</span><span class="sxs-lookup"><span data-stu-id="b08e1-132">State</span></span>   | <span data-ttu-id="b08e1-133">DVR</span><span class="sxs-lookup"><span data-stu-id="b08e1-133">DVR</span></span>                                                   | <span data-ttu-id="b08e1-134">VOD</span><span class="sxs-lookup"><span data-stu-id="b08e1-134">VOD</span></span>                                                     | <span data-ttu-id="b08e1-135">Запись</span><span class="sxs-lookup"><span data-stu-id="b08e1-135">Recording</span></span>                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| <span data-ttu-id="b08e1-136">Запись доступна для звукозаписей.</span><span class="sxs-lookup"><span data-stu-id="b08e1-136">Recording available to producers and presenters</span></span> | <span data-ttu-id="b08e1-137">выбрано</span><span class="sxs-lookup"><span data-stu-id="b08e1-137">Selected</span></span>     | <span data-ttu-id="b08e1-138">Доступен DVR, и актив служб мультимедиа Azure (AMS) хранится в течение 180 дней</span><span class="sxs-lookup"><span data-stu-id="b08e1-138">DVR is available and the Azure Media Services (AMS) asset is stored for 180 days</span></span> | <span data-ttu-id="b08e1-139">Участники могут получить доступ к событию и посмотреть его</span><span class="sxs-lookup"><span data-stu-id="b08e1-139">Attendee can access and watch the event</span></span>                     |                              |
|                                                  | <span data-ttu-id="b08e1-140">Не выбрано</span><span class="sxs-lookup"><span data-stu-id="b08e1-140">Not Selected</span></span> | <span data-ttu-id="b08e1-141">Доступен DVR, а актив AMS хранится 180 дней</span><span class="sxs-lookup"><span data-stu-id="b08e1-141">DVR is available and the AMS asset is stored for 180 days</span></span> | <span data-ttu-id="b08e1-142">Участник не получит доступ к событию после его окончания</span><span class="sxs-lookup"><span data-stu-id="b08e1-142">Attendee won't get access into the event after it's over</span></span> |                              |
||<span data-ttu-id="b08e1-143">Отключено (не выбрано)</span><span class="sxs-lookup"><span data-stu-id="b08e1-143">Disabled (Not selected)</span></span>|<span data-ttu-id="b08e1-144">В этом случае актив AMS будет удален после события.</span><span class="sxs-lookup"><span data-stu-id="b08e1-144">DVR is available and the AMS asset is deleted after the event</span></span>|<span data-ttu-id="b08e1-145">Участник не получит доступ к событию после его окончания</span><span class="sxs-lookup"><span data-stu-id="b08e1-145">Attendee won't get access into the event after it's over</span></span>||
| <span data-ttu-id="b08e1-146">Запись доступна для звукозаписей.</span><span class="sxs-lookup"><span data-stu-id="b08e1-146">Recording available to producers and presenters</span></span> | <span data-ttu-id="b08e1-147">выбрано</span><span class="sxs-lookup"><span data-stu-id="b08e1-147">Selected</span></span>     |                                                           |                                                             | <span data-ttu-id="b08e1-148">Создается и сохраняется MP4-</span><span class="sxs-lookup"><span data-stu-id="b08e1-148">An MP4 is created and stored</span></span> |
|                                                  | <span data-ttu-id="b08e1-149">Не выбрано</span><span class="sxs-lookup"><span data-stu-id="b08e1-149">Not Selected</span></span> |                                                           |                                                             | <span data-ttu-id="b08e1-150">Файл не создан</span><span class="sxs-lookup"><span data-stu-id="b08e1-150">No file is created</span></span>           |

### <a name="related-topics"></a><span data-ttu-id="b08e1-151">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="b08e1-151">Related topics</span></span>

- [<span data-ttu-id="b08e1-152">Что такое трансляции Teams?</span><span class="sxs-lookup"><span data-stu-id="b08e1-152">What is Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="b08e1-153">Планирование трансляций Teams</span><span class="sxs-lookup"><span data-stu-id="b08e1-153">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="b08e1-154">Настройка параметров трансляций в Teams</span><span class="sxs-lookup"><span data-stu-id="b08e1-154">Configure live events settings in Teams</span></span>](configure-teams-live-events.md)
- [<span data-ttu-id="b08e1-155">Запись собраний в облаке Teams</span><span class="sxs-lookup"><span data-stu-id="b08e1-155">Teams clouds meeting recording</span></span>](../cloud-recording.md)
