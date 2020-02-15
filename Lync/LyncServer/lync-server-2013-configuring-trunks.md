---
title: 'Lync Server 2013: Настройка магистральных каналов'
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
ms.openlocfilehash: 123535ae3e14669e343c881869304e95ce666040
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "41996184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-trunks-in-lync-server-2013"></a>Настройка магистральных линий в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

При развертывании корпоративной голосовой связи вы можете настроить магистраль между сервером-посредником и одним или несколькими из следующих одноранговых узлов, чтобы обеспечить подключение к телефонной сети общего пользования (PSTN) для клиентов и устройств корпоративной голосовой связи в Организации:

  - Подключение магистрали SIP к поставщику услуг Интернет-телефонии

  - Шлюз ТСОП

  - УАТС

Дополнительные сведения приведены в статье [Планирование подключения PSTN в Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) в документации по планированию.

<div>


> [!IMPORTANT]  
> Прежде чем приступать к настройке магистрали, убедитесь что создана топология и что сервер-посредник и его одноранговый узел настроены и связаны друг с другом. Дополнительные сведения приведены в разделе <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">определение шлюза в построителе топологий в Lync Server 2013</A> в документации по развертыванию.



</div>

<div>


> [!NOTE]  
> В рамках настройки магистрали можно включить функцию обхода сервера-посредника Lync Server 2013, что позволяет мультимедиа обходить сервер-посредник. Магистрали можно настроить как с включенной, так и с выключенной функцией медиа-посредника, но мы настоятельно рекомендуем включить эту функцию. Дополнительные сведения приведены в статье <A href="lync-server-2013-planning-for-media-bypass.md">Планирование обхода сервера мультимедиа в Lync Server 2013</A> в документации по планированию.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Поддержка нескольких магистральных каналов в Lync Server 2013](lync-server-2013-multiple-trunk-support.md)

  - [Маршрутизация между магистрали в Lync Server 2013](lync-server-2013-inter-trunk-routing.md)

  - [Просмотр сведений о конфигурации магистрали в Lync Server 2013](lync-server-2013-view-trunk-configuration-information.md)

  - [Настройка магистрали с обходом сервера мультимедиа в Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [Настройка магистрали без обхода сервера мультимедиа в Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [Создание новой коллекции параметров конфигурации магистрали в Lync Server 2013](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [Удаление существующей коллекции параметров конфигурации магистрали SIP в Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [Изменение параметров конфигурации магистрали SIP в Lync Server 2013](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [Проверка параметров конфигурации магистрали SIP в Lync Server 2013](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [Просмотр сведений об отдельных магистральных магистральных каналах SIP в Lync Server 2013](lync-server-2013-view-information-about-individual-sip-trunks.md)

</div>

<div>

## <a name="see-also"></a>См. также


[Определение шлюза в построителе топологий в Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md)  


[Планирование подключения по протоколу PSTN в Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md)  
[Планирование обхода сервера мультимедиа в Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

