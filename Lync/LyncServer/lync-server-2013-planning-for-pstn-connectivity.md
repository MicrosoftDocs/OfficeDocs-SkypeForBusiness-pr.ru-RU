---
title: 'Lync Server 2013: планирование подключения PSTN'
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
ms.openlocfilehash: 18bb8818ab0ea44574736202f2f0a3a41e73b22e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184132"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-pstn-connectivity-in-lync-server-2013"></a>Планирование подключения по протоколу PSTN в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-21_

Решение VoIP корпоративного уровня должно обеспечивать вызовы в телефонную сеть общего пользования (ТСОП) и обратно без ухудшения качества обслуживания (QoS). Пользователи, получающие и принимающие звонки, не должны знать о базовой технологии: с точки зрения пользователя, вызов между инфраструктурой корпоративной голосовой связи и PSTN должен выглядеть так же, как и другой телефонный звонок.

Lync Server 2013 обеспечивает надежное, масштабируемая возможность подключения по протоколу PSTN с помощью следующих параметров:

  - **SIP-магистрали** для поставщика услуг Интернет-телефонии (ITSP);

  - **прямые SIP-подключения** для шлюза ТСОП;

  - **прямые SIP-подключения** для УАТС.

В зависимости от размера, географического покрытия и существующей инфраструктуры системы голосовой связи предприятия могут использовать один, два или даже все три этих варианта в различных местоположениях.

<div>

## <a name="in-this-section"></a>Содержание

  - [Распределение каналов SIP в Lync Server 2013](lync-server-2013-sip-trunking.md)

  - [Прямые подключения SIP в Lync Server 2013](lync-server-2013-direct-sip-connections.md)

  - [Магистраль M:N в Lync Server 2013](lync-server-2013-m-n-trunk.md)

  - [Правила преобразования в Lync Server 2013](lync-server-2013-translation-rules.md)

  - [Планирование маршрутизации исходящих голосовых вызовов в Lync Server 2013](lync-server-2013-planning-outbound-voice-routing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

