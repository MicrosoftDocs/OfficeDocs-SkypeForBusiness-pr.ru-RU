---
title: 'Lync Server 2013: конфигурация магистралей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring trunks
ms:assetid: 0c339511-a185-484e-94f0-dbe918b7e48a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398170(v=OCS.15)
ms:contentKeyID: 48183389
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1021295b375e4f28294ffb1ca5738d651f9ced2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-trunks-in-lync-server-2013"></a>Конфигурация магистралей в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-01_

В рамках развертывания Enterprise Voice вы можете настроить магистраль между сервером-посредником и одним или несколькими из указанных ниже одноранговых сетей для предоставления подключения по коммутируемой телефонной сети (PSTN) для корпоративных клиентов и мобильных устройств в Организации.

  - Подключение магистрали SIP к поставщику услуг Интернет-телефонии

  - Шлюз ТСОП

  - УАТС

Подробнее смотрите в разделе [Планирование подключений PSTN в Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) в документации по планированию.

<div>


> [!IMPORTANT]  
> Перед началом настройки магистрали убедитесь в том, что топология создана и что сервер исправлений и его одноранговые элементы настроены и связаны друг с другом. Подробности можно найти <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">в разделе определение шлюза в построителе топологии в Lync Server 2013</A> в документации по развертыванию.



</div>

<div>


> [!NOTE]  
> В рамках настройки магистрали вы можете включить функцию обхода мультимедиа Lync Server 2013, которая позволяет мультимедиа обходить сервер-посредник. Магистральные магистрали можно настраивать с включенным параметром "обойти" или без него, но настоятельно рекомендуем включить его. Подробности можно найти <A href="lync-server-2013-planning-for-media-bypass.md">в разделе Планирование обхода мультимедиа в Lync Server 2013</A> в документации по планированию.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Поддержка нескольких каналов в Lync Server 2013](lync-server-2013-multiple-trunk-support.md)

  - [Маршрутизация с межмагистральными организациями в Lync Server 2013](lync-server-2013-inter-trunk-routing.md)

  - [Просмотр сведений о магистральной конфигурации в Lync Server 2013](lync-server-2013-view-trunk-configuration-information.md)

  - [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [Настройка магистрали без обхода мультимедиа в Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [Создание нового набора параметров конфигурации магистрали в Lync Server 2013](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [Удаление существующей коллекции параметров конфигурации магистральной магистрали SIP в Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [Изменение параметров конфигурации магистральной магистрали SIP в Lync Server 2013](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [Проверка параметров конфигурации магистральной магистрали SIP в Lync Server 2013](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [Просмотр сведений об отдельных магистральах SIP в Lync Server 2013](lync-server-2013-view-information-about-individual-sip-trunks.md)

</div>

<div>

## <a name="see-also"></a>См. также


[Определение шлюза в построителе топологии в Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md)  


[Планирование подключений PSTN в Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md)  
[Планирование обхода серверов-посредников в Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

