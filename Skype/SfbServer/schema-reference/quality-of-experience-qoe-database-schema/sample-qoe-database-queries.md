---
title: Образцы запросов к базе данных качества взаимодействия
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 04e6bdd3-bbd1-47ca-8114-94a3db6beeeb
description: В этом разделе содержатся примеры запросов для базы данных качества взаимодействия (QoE).
ms.openlocfilehash: 099e0ed179ab22e3610aaf8b00d3745a315bb734
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888658"
---
# <a name="sample-qoe-database-queries"></a><span data-ttu-id="55637-103">Образцы запросов к базе данных качества взаимодействия</span><span class="sxs-lookup"><span data-stu-id="55637-103">Sample QoE database queries</span></span>
 
<span data-ttu-id="55637-104">В этом разделе содержатся примеры запросов для базы данных качества взаимодействия (QoE).</span><span class="sxs-lookup"><span data-stu-id="55637-104">This section contains sample queries for the Quality of Experience (QoE) database.</span></span> 
  
<span data-ttu-id="55637-105">В следующем примере показано, как получить значение нарушения колебаний и потери пакетов для всех звуковых потоков.</span><span class="sxs-lookup"><span data-stu-id="55637-105">Use the following example to get the jitter and packet loss average for all audio streams.</span></span>
  
```SQL
select avg(cast(JitterInterArrival as bigint)) as JitterAvg, avg(PacketLossRate) as PacketLossRateAvg from AudioStream
```

<span data-ttu-id="55637-106">В следующем примере показано, как найти общее количество конференций, в которых использовалась консоль собрания.</span><span class="sxs-lookup"><span data-stu-id="55637-106">Use the following example to find the total numbers of conferences that used Meeting Console.</span></span>
  
```SQL
select avg(ConversationalMOS)
from SessionView s
inner join MediaLineView m
on s.ConferenceDateTime = m.ConferenceDateTime
   and s.SessionSeq = m.SessionSeq
   and m.MediaLineLabel = 0 -- audio media line
   and s.CallerUserAgentType = 4 -- Lync
   and s.CalleeUserAgentType = 4 -- Lync
```

<span data-ttu-id="55637-107">Следующий пример используется для получения Конверсстионалмос, Сендингмос и Листендингмос для каждого устройства захвата.</span><span class="sxs-lookup"><span data-stu-id="55637-107">Use the following example to get ConversstionalMOS, SendingMOS and ListendingMOS per capture device.</span></span>
  
```SQL
select t.DeviceName as Device, count(*) as SampleNum, avg(ConversationalMOS) as ConversationalMOS, avg(SendListenMOS) SendingMOS, avg(RecvListenMOS) as ListendingMOS
from
(
   select m.CallerCaptureDev as DeviceName, m.ConferenceDateTime, m.SessionSeq, a.StreamID, m.ConversationalMOS,a.SendListenMOS, a.RecvListenMOS
   from MediaLineView m
   inner join AudioStream a
   on m.ConferenceDateTime = a.ConferenceDateTime
      and m.SessionSeq = a.SessionSeq
      and m.MediaLineLabel = 0

   union

   select m.CalleeCaptureDev as DeviceName, m.ConferenceDateTime, m.SessionSeq, a.StreamID, m.ConversationalMOS,a.SendListenMOS, a.RecvListenMOS
   from MediaLineView m
   inner join AudioStream a
   on m.ConferenceDateTime = a.ConferenceDateTime
      and m.SessionSeq = a.SessionSeq
      and m.MediaLineLabel = 0

)as t
group by t.DeviceName
order by SampleNum desc
```
