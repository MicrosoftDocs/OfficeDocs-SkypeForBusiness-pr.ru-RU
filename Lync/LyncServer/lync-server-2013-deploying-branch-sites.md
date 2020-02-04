---
title: 'Lync Server 2013: развертывание сайтов филиалов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying branch sites
ms:assetid: 1475dee0-66ae-4ee5-b6f1-7409b4bbff45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398217(v=OCS.15)
ms:contentKeyID: 48183483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: facfda5d1d7ce67ea08f71cbfb943792eeced7a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-branch-sites-in-lync-server-2013"></a>Развертывание сайтов филиалов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-21_

Пользователи сайтов филиалов получают большинство функций Lync Server 2013 с сервера центрального сайта, с которым связан сайт филиала. Каждый сайт филиала связан только с одним центральным сайтом. Для передачи звонков из коммутируемой телефонной сети с открытым коммутируемым подключением сайт филиала может содержать любые из указанных ниже вариантов.

  - Шлюз PSTN и, возможно, сервер Медитатион

  - Магистральная линия SIP

  - Существующая инфраструктура голосовой связи с частным обменом филиалов (АТС)

  - Бесперебойно работающее устройство филиала

  - Бесперебойный сервер филиала

Сайты филиалов с бесперебойно работающими управляющими системами или работающими серверами филиалов более устойчивы во время многофакторной сети или сбоя центрального сайта, чем для сайтов филиалов без одного из этих решений. Например, на сайте с бесперебойно работающим управляющим устройством филиала или развернутом работающем сервере филиала пользователи по-прежнему могут совершать и принимать звонки PSTN, если сеть, соединяющая сайт ветви с центральным сайтом, не работает. Кроме того, вы можете достичь устойчивости сайта с помощью шлюза PSTN или магистральной магистрали SIP с полным развертыванием Lync Server на сайте филиала.

Сведения о том, какое развертывание сайтов филиалов подходит для вашей организации, в том числе о предварительных требованиях и других вопросах планирования, приведены в разделе [Планирование подключений PSTN в Lync server 2013](lync-server-2013-planning-for-pstn-connectivity.md) и [Планирование обеспечения устойчивости голоса на филиалах в Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) в документации по планированию.

<div>

## <a name="in-this-section"></a>Содержание

  - [Обеспечение подключения ТСОП в сайте филиала в Lync Server 2013](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [Развертывание устройства или сервера обеспечения связи в филиалах с Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

