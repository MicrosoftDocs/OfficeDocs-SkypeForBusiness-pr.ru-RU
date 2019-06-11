---
title: 'Lync Server 2013: сводка по DNS — балансировка нагрузки на DNS и аппаратная балансировка нагрузки'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - DNS and HLB load balanced
ms:assetid: d2132695-1956-4190-a98e-cd7255cbded6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205273(v=OCS.15)
ms:contentKeyID: 48185447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceccb52a8ef9fae810821ffe6b52b763dd8904c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a>Сводка по DNS — балансировка нагрузки на DNS и аппаратная балансировка нагрузки в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-20_

В таблице ниже приведены сведения о DNS-записях, которые необходимы для поддержки подкаталога балансировки нагрузки DNS и оборудования. Роль режиссера требует наличия аналогичных записей DNS в качестве внешнего сервера. Количество необходимых записей отражается в альтернативных именах тем, необходимых для вашего сертификата в директории. На сервере переднего плана не размещается учетные записи пользователей и не размещается служба Mobility Service.

### <a name="dns-records-required-for-the-director-pool-using-dns-load-balancing-and-hardware-load-balancer"></a>DNS-записи, необходимые для пула режиссеров с помощью балансировки нагрузки DNS и аппаратной подсистемы балансировки нагрузки

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Расположение/тип/порт</th>
<th>Полное доменное имя/DNS-запись</th>
<th>IP-адрес или полное доменное имя</th>
<th>Карты и примечания</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Внутренняя DNS/A</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Директор</p></td>
<td><p>Запись узла директора, используемая для репликации и сервера на сервер</p></td>
</tr>
<tr class="even">
<td><p>Внутренняя DNS/A</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>директоров</p></td>
<td><p>Запись узла для пула службы каталогов балансировки нагрузки DNS для сервера на сервер</p></td>
</tr>
<tr class="odd">
<td><p>Внутренняя DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>директоров</p></td>
<td><p>Протокол SIP, входящий в внутренний интерфейс пограничного сервера.</p></td>
</tr>
<tr class="even">
<td><p>Внутренняя DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Пул ХЛБных ВИРТУАЛЬНЫХ каталогов</p></td>
<td><p>Подходящими для аппаратной балансировки нагрузки веб-службы, опубликованные из обратного прокси</p></td>
</tr>
<tr class="odd">
<td><p>Внутренняя DNS/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Пул ХЛБных ВИРТУАЛЬНЫХ каталогов</p></td>
<td><p>Служба балансировки нагрузки для оборудования, опубликованная в соответствии с обратной прокси-сервером</p></td>
</tr>
<tr class="even">
<td><p>Внутренняя DNS/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>Пул ХЛБных ВИРТУАЛЬНЫХ каталогов</p></td>
<td><p>Балансировка нагрузки для оборудования, опубликованная и определяемая внешними веб-службами обратного прокси, для директора пула</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

