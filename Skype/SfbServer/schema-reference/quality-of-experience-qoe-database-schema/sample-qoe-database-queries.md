---
title: Примеры запросов к базе данных качества взаимодействия
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: efc26064e52464ffc2e92e24d5af8dd848368b56
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834369"
---
# <a name="sample-qoe-database-queries"></a><span data-ttu-id="b4c95-103">Примеры запросов к базе данных качества взаимодействия</span><span class="sxs-lookup"><span data-stu-id="b4c95-103">Sample QoE database queries</span></span>
 
<span data-ttu-id="b4c95-104">В этом разделе содержатся примеры запросов для базы данных качества взаимодействия (QoE).</span><span class="sxs-lookup"><span data-stu-id="b4c95-104">This section contains sample queries for the Quality of Experience (QoE) database.</span></span> 
  
<span data-ttu-id="b4c95-105">Используйте следующий пример, чтобы получить значение дрожания и среднюю потерю пакетов для всех аудиопотоков.</span><span class="sxs-lookup"><span data-stu-id="b4c95-105">Use the following example to get the jitter and packet loss average for all audio streams.</span></span>
  
```SQL
select avg(cast(JitterInterArrival as bigint)) as JitterAvg, avg(PacketLossRate) as PacketLossRateAvg from AudioStream
```

<span data-ttu-id="b4c95-106">Используйте следующий пример, чтобы определить общее количество конференций, использовавших консоль Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="b4c95-106">Use the following example to find the total numbers of conferences that used Meeting Console.</span></span>
  
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

<span data-ttu-id="b4c95-107">Используйте следующий пример, чтобы получить ConversstionalMOS, SendingMOS и ListendingMOS для устройства захвата.</span><span class="sxs-lookup"><span data-stu-id="b4c95-107">Use the following example to get ConversstionalMOS, SendingMOS and ListendingMOS per capture device.</span></span>
  
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
