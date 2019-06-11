---
title: 'Lync Server 2013: Планирование подключений PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for PSTN connectivity
ms:assetid: 280f684a-740a-443d-8ecf-574241382a42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425749(v=OCS.15)
ms:contentKeyID: 48183684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d64089661b5d185362a8e47128e9a890b03edfd8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824584"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-pstn-connectivity-in-lync-server-2013"></a>Планирование подключений PSTN в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-21_

Решение VoIP корпоративного уровня должно предусматривать входящие и исходящие вызовы на телефонную сеть общего пользования (ТСОП) без какого-либо снижения качества обслуживания (QoS). Пользователи, которые размещаются и принимают звонки, не должны знать о базовой технологии: с точки зрения пользователя, Звонок между корпоративной инфраструктурой голосовой связи и PSTN должен казаться просто другим телефонным звонком.

Lync Server 2013 обеспечивает надежную и масштабируемую КОММУТИРУЕМую связь с помощью следующих параметров:

  - **магистрали SIP**, соединяющие с оператором телефонной связи по сети Интернет;

  - **прямые подключения SIP** к шлюзу ТСОП;

  - **прямые подключения SIP** к УАТС.

В зависимости от размеров предприятия, охватываемой территории и существующей инфраструктуры голосовой связи можно применять один и тот же способ на всем предприятии либо два или все три способа в разных подразделениях.

<div>

## <a name="in-this-section"></a>Содержание

  - [Магистральные линии SIP в Lync Server 2013](lync-server-2013-sip-trunking.md)

  - [Прямые подключения по протоколу SIP в Lync Server 2013](lync-server-2013-direct-sip-connections.md)

  - [М:Н магистраль в Lync Server 2013](lync-server-2013-m-n-trunk.md)

  - [Правила перевода в Lync Server 2013](lync-server-2013-translation-rules.md)

  - [Планирование маршрутизации исходящей голосовой почты в Lync Server 2013](lync-server-2013-planning-outbound-voice-routing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

