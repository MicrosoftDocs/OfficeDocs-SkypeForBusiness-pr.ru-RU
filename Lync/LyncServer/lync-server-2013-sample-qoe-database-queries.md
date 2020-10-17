---
title: 'Lync Server 2013: примеры запросов к базе данных QoE'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Sample QoE database queries
ms:assetid: 04e6bdd3-bbd1-47ca-8114-94a3db6beeeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398100(v=OCS.15)
ms:contentKeyID: 48183280
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 441384c2ed8dae6f03aa6034ceba2248710e9d3c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511026"
---
# <a name="sample-qoe-database-queries-in-lync-server-2013"></a>Примеры запросов к базам данных QoE в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-17_

В этом разделе содержатся примеры запросов для базы данных качества взаимодействия (QoE).

Используйте следующий пример, чтобы получить значение дрожания и среднюю потерю пакетов для всех аудиопотоков.

    select avg(cast(JitterInterArrival as bigint)) as JitterAvg, avg(PacketLossRate) as PacketLossRateAvg from AudioStream

Используйте следующий пример, чтобы определить общее количество конференций, использовавших консоль Live Meeting.

    select avg(ConversationalMOS)
    from SessionView s
    inner join MediaLineView m
    on s.ConferenceDateTime = m.ConferenceDateTime
       and s.SessionSeq = m.SessionSeq
       and m.MediaLineLabel = 0 -- audio media line
       and s.CallerUserAgentType = 4 -- Lync
       and s.CalleeUserAgentType = 4 -- Lync

Используйте следующий пример, чтобы получить ConversstionalMOS, SendingMOS и ListendingMOS для устройства захвата.

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

</div>

<span> </span>

</div>

</div>

</div>

