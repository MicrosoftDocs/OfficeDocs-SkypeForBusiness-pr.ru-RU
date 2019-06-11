---
title: 'Lync Server 2013: маршрутизация между каналами'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Intertrunk routing
ms:assetid: d3a33b4a-8bf4-4a8c-a371-8ef79e740780
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205272(v=OCS.15)
ms:contentKeyID: 48185442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c1b66ea04ed72bab6d33114f52fa9fe96364b48
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="intertrunk-routing-in-lync-server-2013"></a>Маршрутизация между каналами в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-20_

Lync Server 2013 может использовать IP-УАТС с шлюзом коммутируемой телефонной сети (PSTN), чтобы звонки с телефонной АТС могли перенаправляться на телефон, входящий в протокол PSTN. Аналогичным образом Lync Server 2013 может использоваться для объединения двух или более систем УАТС IP и обмена звонками между телефонами УАТС из различных систем IP-УАТС.

Эту функцию маршрутизации по межмагистрали можно настроить с помощью командлета командной консоли Lync Server, **Set-CsTrunkConfiguration**с новым параметром пстнусажес. Этот параметр указывает набор записей использования КТСОП для использования. Магистраль использует это использование PSTN для определения маршрута и для маршрутизации всех входящих вызовов соответственно.

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

На следующей схеме показана интеграция сервера Lync Server 2013, обеспечивающая взаимодействие между шлюзом PSTN и IP-УАТС.

**Межмагистральная маршрутизация между шлюзом и IP-УАТС**

![Lync Server подключение PSTN Gateway/IP-УАТС] (images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server подключение PSTN Gateway/IP-УАТС")

На следующей схеме показана платформа Lync Server 2013, соединяющая две системы IP-УАТС.

**Межмагистральная маршрутизация между двумя IP-АТС**

![Схема IP-схемы для совместного подключения к Lync Server — система PAX] (images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Схема IP-схемы для совместного подключения к Lync Server — система PAX")

</div>

<span> </span>

</div>

</div>

</div>

