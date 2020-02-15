---
title: 'Lync Server 2013: Маршрутизация с магистрали'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Intertrunk routing
ms:assetid: d3a33b4a-8bf4-4a8c-a371-8ef79e740780
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205272(v=OCS.15)
ms:contentKeyID: 48185442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23aab6df352b162f7f389ef56fb2300f01654edb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="intertrunk-routing-in-lync-server-2013"></a>Маршрутизация по межмагистральным каналам в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-20_

Lync Server 2013 может подсоединить IP-УАТС к шлюзу телефонной сети общего пользования (PSTN), чтобы звонки с телефона УАТС могли маршрутизироваться в PSTN, а входящие звонки PSTN могут маршрутизироваться на телефон УАТС. Аналогично, Lync Server 2013 может использовать две или более системы IP-УАТС, чтобы вызовы можно было размещать и принимать между телефонами УАТС из различных систем IP-УАТС.

Эту функцию маршрутизации по межмагистрали можно настроить с помощью командлета командной консоли Lync Server, **Set — CsTrunkConfiguration**с новым параметром PstnUsages. Он определяет набор записей варианта использовании ТСОП, который будет применяться. С помощью этой записи магистраль определяет маршрут и переадресует все вызовы соответствующим образом.

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

На следующей схеме показана платформа Lync Server 2013, обеспечивающая взаимодействие между шлюзом PSTN и IP-УАТС.

**Межмагистральная маршрутизации между шлюзом и IP-УАТС**

![Lync Server с подключением шлюза PSTN/IP-УАТС](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server с подключением шлюза PSTN/IP-УАТС")

На следующей схеме показана платформа Lync Server 2013, соединяющая две системы IP-УАТС.

**Межмагистральная маршрутизации между двумя IP-УАТС**

![Схема IP-PAX для системы связи Lync Server-PAX](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Схема IP-PAX для системы связи Lync Server-PAX")

</div>

<span> </span>

</div>

</div>

</div>

