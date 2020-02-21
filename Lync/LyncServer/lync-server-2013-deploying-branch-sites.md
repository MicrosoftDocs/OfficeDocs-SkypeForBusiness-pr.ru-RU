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
ms.openlocfilehash: 617503a26a326f9fa089f3ee2de8a5163765920f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200082"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-branch-sites-in-lync-server-2013"></a>Развертывание сайтов филиалов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-21_

Пользователи сайта филиала получают большинство функций Lync Server 2013 с сервера на центральном сайте, с которым связан сайт филиала. Каждый узел филиала связан ровно с одним центральным узлом. Чтобы позволить совершать вызовы по ТСОП, узел филиала может содержать следующие компоненты:

  - шлюз ТСОП и, возможно, сервер-посредник;

  - SIP-магистраль;

  - существующая инфраструктура голосовой связи с УАТС;

  - Устройство для обеспечения связи в филиалах

  - Сервер для обеспечения связи в филиалах

Сайты филиалов с устройством для обеспечения связи в филиалах или сервером для обеспечения связи в филиалах являются более устойчивыми во время сбоев в глобальной сети или центральных сайтах, чем для сайтов филиалов без одного из этих решений. Например, на сайте с устройством для обеспечения связи в филиале или с развернутым сервером для обеспечения связи в филиалах пользователи по-прежнему могут совершать и принимать звонки PSTN, если сеть, соединяющую сайт филиала, с центральным сайтом отключена. Другой способ достижения устойчивости сайта филиала заключается в использовании шлюза PSTN или магистральной линии SIP с полным развертыванием Lync Server на сайте филиала.

Сведения о том, какое развертывание сайта филиала подходит для вашей организации, в том числе необходимые условия и другие рекомендации по планированию, приведены в статье [Планирование подключения PSTN в Lync server 2013](lync-server-2013-planning-for-pstn-connectivity.md) и [Планирование устойчивости голосовой связи на сайте филиала в Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) в документации по планированию.

<div>

## <a name="in-this-section"></a>Содержание

  - [Обеспечение подключения PSTN на сайте филиала в Lync Server 2013](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [Развертывание устройства или сервера для обеспечения связи в филиалах с помощью Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

