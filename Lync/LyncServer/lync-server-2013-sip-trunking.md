---
title: 'Lync Server 2013: магистральные линии SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SIP trunking
ms:assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398619(v=OCS.15)
ms:contentKeyID: 48184615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b7103b965c08df66d86eec99722ad03b937e407
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849660"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunking-in-lync-server-2013"></a>Магистральные линии SIP в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-08-13_

С помощью протокола инициирования сеансов (SIP) сеансы связи инициируются и управляются по протоколу VoIP для основной телефонной службы и для таких дополнительных коммуникационных услуг в режиме реального времени, как обмен мгновенными сообщениями, конференц-связь, обнаружение присутствия и мультимедиа. В этом разделе представлены сведения по планированию для реализации *магистралей SIP*, типы подключений SIP, которые распространяется за пределы локальной сети.

<div>

## <a name="what-is-sip-trunking"></a>Что такое транкинг SIP?

Транкинг SIP — это IP-подключение, которое устанавливает коммуникационную связь SIP между вашей организацией и поставщиком услуг интернет-телефонии (ITSP) за пределами брандмауэра организации. Обычно магистраль SIP используется для подключения центрального сайта организации к ITSP. В некоторых случаях вы также можете выбрать транкинг SIP для подключения сайта филиала к ITSP.

<div>

## <a name="sip-trunks-vs-direct-sip-connections"></a>Сравнение магистралей SIP с прямыми SIP-подключениями

Термин *магистраль* происходит технологии коммутируемых каналов. Он относится к выделенной физической линии, соединяющей телефонное коммутационное оборудование. Как и в случае с их предшественниками, мультиплексированием деления времени (ТДМ), магистральные магистрали SIP — это соединения между двумя отдельными сетями SIP — Lync Server 2013 Enterprise и ИТСП. В отличие от коммутируемых каналов, магистрали SIP являются виртуальными подключениями, которые могут быть установлены в любых поддерживаемых типах подключений транкинга SIP. Подробнее о поддерживаемых типах подключений вы узнаете, [как реализовать магистральные линии SIP в Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).

С другой стороны, прямые SIP-подключения — это подключения, которые не пересекают границ локальной сети (т.е. они подключаются к шлюзу ТСОП или УАТС во внутренней сети). Подробнее о том, как использовать прямые подключения по протоколу SIP с Lync Server 2013, можно найти [в разделе прямые подключения SIP в Lync server 2013](lync-server-2013-direct-sip-connections.md).

</div>

</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Обзор распределения каналов SIP в Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md)

  - [Реализация распределения каналов SIP в Lync Server 2013](lync-server-2013-how-do-i-implement-sip-trunking.md)

  - [Компоненты и топологии для распределения каналов SIP в Lync Server 2013](lync-server-2013-components-and-topologies-for-sip-trunking.md)

  - [Branch site SIP trunking in Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md)

  - [Контрольный список развертывания для каналов SIP для Lync Server 2013](lync-server-2013-sip-trunk-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

