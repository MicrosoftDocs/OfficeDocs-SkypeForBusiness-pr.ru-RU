---
title: 'Lync Server 2013: магистральная линия SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunking
ms:assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398619(v=OCS.15)
ms:contentKeyID: 48184615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0709bb6e837f536a2c034c239ee08c83f2b36e8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142685"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sip-trunking-in-lync-server-2013"></a>Распределение каналов SIP в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-08-13_

С помощью протокола SIP инициируются и управляются сеансы связи по протоколу VoIP для базовой телефонной связи и для многих дополнительных коммуникационных услуг в режиме реального времени, таких как обмен мгновенными сообщениями, конференц-связь, обнаружение присутствия и мультимедиа. В этом разделе предоставляются сведения по планированию для реализации *каналов SIP*, разновидности подключения SIP, которое распространяется за пределы локальной сети.

<div>

## <a name="what-is-sip-trunking"></a>Что такое распределение каналов SIP?

Распределение каналов SIP — это IP-подключение, которое устанавливает коммуникационную связь SIP между вашей организацией и поставщиком услуг Интернет-телефонии (ITSP) за пределами брандмауэра организации. Обычно канал SIP используется для подключения центрального сайта организации к ITSP. В некоторых случаях вы также можете выбрать использование распределения каналов SIP для подключения к ITSP сайтов филиалов.

<div>

## <a name="sip-trunks-vs-direct-sip-connections"></a>Распределение каналов SIP по сравнению с прямыми подключениями SIP

Термин *канал* пришел из технологии с коммутируемыми каналами. Он относится к выделенной физической линии, соединяющей телефонное коммутационное оборудование. Как и их предшественники, магистральные каналы мультиплексирования (TDM), магистральные линии SIP являются подключениями между двумя отдельными сетями SIP — Lync Server 2013 Enterprise и ITSP. В отличие от коммутируемых каналов, каналы SIP являются виртуальными подключениями, которые могут быть установлены в любых поддерживаемых типах подключений распределения каналов SIP. Дополнительные сведения о поддерживаемых типах подключений приведены [в статье как реализовать магистральные линии SIP в Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).

С другой стороны, прямые подключения SIP — это подключения, которые не пересекают границы локальной сети (т.е. они подключаются к шлюзу ТСОП или УАТС во внутренней сети). Сведения о том, как использовать прямые подключения SIP с Lync Server 2013, можно найти [в разделе Direct SIP Connections in Lync server 2013](lync-server-2013-direct-sip-connections.md).

</div>

</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Обзор распределения каналов SIP в Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md)

  - [Как реализовать магистральные линии SIP в Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md)

  - [Компоненты и топологии для распределения каналов SIP в Lync Server 2013](lync-server-2013-components-and-topologies-for-sip-trunking.md)

  - [Магистральная линия SIP сайта филиала в Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md)

  - [Контрольный список развертывания магистрали SIP для Lync Server 2013](lync-server-2013-sip-trunk-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

