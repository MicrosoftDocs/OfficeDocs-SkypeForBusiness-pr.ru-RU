---
title: Классификация потоков в Панели мониторинга качества звонка
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: gageames
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: Узнайте, как качество потока классифицируется в панели мониторинга качества звонка для команд Microsoft и Skype для бизнеса Online.
ms.openlocfilehash: b3b63ff8ac89ed0ad1d88893913fa89af769e078
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2019
ms.locfileid: "30641036"
---
# <a name="stream-classification-in-call-quality-dashboard"></a>Классификация потоков в Панели мониторинга качества звонка

The Call Quality Dashboard (CQD) for Microsoft Teams and Skype for Business Online allows you to gain insights into the quality of calls made using Microsoft Teams and Skype for Business services. This topic provides detailed information about the quality classification of media streams. To learn more about CQD and how to enable it, see [Turning on and using Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md).

## <a name="classifier-definitions"></a>Определения классификатора

Streams in CQD are classified as good, poor, or unclassified based on the values of the available key quality metrics. The metrics and conditions used to classify stream are shown in the tables below. CQD's "Poor Due To" dimensions can be used to understand which metric is responsible for a poor classification. See [Dimensions and measures available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md) for more information on these dimensions.

### <a name="audio-classifier"></a>Звуковой классификатор

Звуковой поток считается плохим, если выполняется одно или несколько из следующих условий:

|**Показатель**|**Условие**|**Пояснение**|
|:-----|:-----|:-----|
|Audio Degradation Avg|> 1,0|Average Network Mean Opinion Score degradation for stream. Represents how much the network loss and jitter has impacted the quality of received audio.|
|Round Trip|>500|Среднее время кругового пути при распространении по сети, вычисляемое в миллисекундах в соответствии со стандартом RFC3550.|
|Packet Loss Rate|>0,1|Средний коэффициент потерь пакетов для потока.|
|Искажение|> 30|Среднее дрожание для потока в миллисекундах.|
|Ratio Concealed Samples Avg|> 0,07|Среднее отношение числа звука кадров с скрытых образцов, созданных функцией восстановления, общее количество кадров, звуковых потери пакетов.|

### <a name="video-classifier"></a>Видео классификатор

Видеопоток помечен как хороший или плохой на основе значения первой доступной метрики в следующем порядке:

|**Этап #**|**Показатель**|**Условие**|**Классификация, если условие верно**|**Классификация, если условие ложно**|**Классификация, если метрика недоступна**|**Пояснение**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|> 50% |Poor|Good|Перейти к шагу 2|Average percentage of video frames lost as displayed to the user. This includes frames recovered from network losses.|
|2|Video Frame Rate Avg|<7|Poor|Good|Перейти к шагу 3|Среднее число кадров в секунду, принимаемых для видеопотока, вычисленное за период сеанса.|
|3|Video Post FECPLR|> 0,15|Poor|Good|Unclassified|Коэффициент потерь пакетов после применения FEC агрегируются по всем потоковое видео и кодеков.|

### <a name="vbss-classifier"></a>VBSS классификатор

VBSS поток помечен как хороший или плохой на основе значения первой доступной метрики в следующем порядке:

|**Этап #**|**Показатель**|**Условие**|**Классификация, если условие верно**|**Классификация, если условие ложно**|**Классификация, если метрика недоступна**|**Пояснение**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|> 50% |Poor|Good|Перейти к шагу 2|Average percentage of video frames lost as displayed to the user. This includes frames recovered from network losses.|
|2|Video Frame Rate Avg|< 2|Poor|Good|Перейти к шагу 3|Среднее число кадров в секунду, принимаемых для видеопотока, вычисленное за период сеанса.|
|3|Video Post FECPLR|> 0,15|Poor|Good|Unclassified|Коэффициент потерь пакетов после применения FEC агрегируются по всем потоковое видео и кодеков.|

### <a name="application-sharing-classifier"></a>Классификатор совместного использования приложений

Звуковой поток помечается плохим, если выполняется одно или несколько из следующих условий:


| **Показатель**                                     | **Условие** | **Пояснение**                                                                                                                                                                                                        |
|:-----------------------------------------------|:--------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Spoiled Tile Percent Total                     | > 36          | Percentage of tiles that are discarded instead of being sent to a remote peer (for example, from the MCU to a viewer). Discarded (or spoiled) tiles may be caused by bandwidth restrictions between client and server. |
| AppSharing RDP Tile Processing Latency Average | > 400         | Средняя задержка в миллисекундах при обработке фрагментов в стеке RDP на сервере конференции.                                                                                                                          |
| AppSharing Relative OneWay Average             | > 1,75        | Средняя относительный Односторонняя задержка между конечными точками в секундах для потоков общего доступа к приложениям.                                                                                                                       |

## <a name="unclassified-streams"></a>Неклассифицированные потоки

В ПМКЗ поток помечен как неклассифицированный при сбое соединения ICE или когда все метрики, необходимые для вычисления классификации потока, не сообщаются.

To check for ICE connectivity failures, examine the dimensions "First Connectivity Ice" and "Second Connectivity Ice" for a "FAILED" value. If either value indicates a failure, the stream will be marked as unclassified.

If ICE connectivity succeeded for an unclassified stream, the stream is likely considered unclassified because key stream metrics were not reported. There are a few reasons these metrics may not be reported:

- **QoE reports were not received** - The metrics used for classification are reported in a QoE report sent at the end of a call. If this report is not produced (e.g., because some third-party endpoints may not send QoE) or was not able to be sent (e.g., because of a network outage), CQD is unable to classify the stream.

> [!TIP]
> The "QoE Record Available" dimension can be used to determine whether a QoE report was received for a stream. Note that this dimension will have a value of "True" if a QoE report was received from either endpoint. A QoE report from both endpoints is required for the most accurate reporting of metrics.

- **Short calls** - Short calls may not have enough media activity to compute key stream metrics. Without these metrics, CQD is unable to classify the stream.

> [!TIP]
> The dimensions "Duration (Seconds)", "Duration (Minutes)", "Duration 5 seconds or less", and "Duration 60 seconds or more" can be used to determine the duration of a stream. The measurement "Avg Call Duration" can also be used to compute the average duration for a set of streams.

- **Low packet utilization** - Like the "short call" scenario, sufficient packet utilization is required for computation of key stream metrics. Without these metrics, CQD is unable to classify the stream.
    - A common low packet utilization scenario occurs when a user joins a meeting to listen to the presenter but never speaks (likely muting the microphone for most of the call). In such a scenario, one audio stream will have high packet utilization (inbound to the client) while the other will have little to no packet utilization (outbound from the client). In this scenario, the duration of the stream may be an hour or longer but the packet utilization on the stream from the client to the server will be extremely low due to the microphone being muted, resulting in an unclassified stream.

> [!TIP]
> Измерение «Утилизация пакета» и измерение «Среднее использование пакета» могут использоваться для определения активности пакета в потоке.


## <a name="related-topics"></a>Связанные разделы
[Включение и использование вызова панели мониторинга качества (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Измерения и меры на панели мониторинга качества звонков](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Использование аналитики звонков для устранения проблем с качеством звонка](use-call-analytics-to-troubleshoot-poor-call-quality.md)
