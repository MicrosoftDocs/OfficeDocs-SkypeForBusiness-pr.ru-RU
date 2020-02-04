---
title: 'Lync Server 2013: Планирование подключений PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for PSTN connectivity
ms:assetid: 280f684a-740a-443d-8ecf-574241382a42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425749(v=OCS.15)
ms:contentKeyID: 48183684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec12aa5e579aed30e61c7cd34eab444e807c628f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725259"
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

