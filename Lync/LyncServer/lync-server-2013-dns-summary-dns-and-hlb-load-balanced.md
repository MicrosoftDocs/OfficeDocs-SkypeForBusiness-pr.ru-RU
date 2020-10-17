---
title: 'Lync Server 2013: сводка по DNS — балансировка нагрузки на DNS и HLB'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - DNS and HLB load balanced
ms:assetid: d2132695-1956-4190-a98e-cd7255cbded6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205273(v=OCS.15)
ms:contentKeyID: 48185447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6a3dc04856e1727c3982864995494cee751f457
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532156"
---
# <a name="dns-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a>Сводка по DNS — балансировка нагрузки на DNS и HLB в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-20_

В следующей таблице приведена сводка DNS-записей, необходимых для поддержки директора балансировки нагрузки на DNS и аппаратного директора балансировки нагрузки. Роли директора необходимы аналогичные записи DNS в качестве сервера переднего плана. Количество необходимых записей отражается в альтернативных именах субъектов, необходимых для сертификата директора. От сервера переднего плана директору пула не размещаются учетные записи пользователей или не размещаются службы Mobility Service.

### <a name="dns-records-required-for-the-director-pool-using-dns-load-balancing-and-hardware-load-balancer"></a>DNS-записи, обязательные для пула каталогов, использующего балансировщик нагрузки DNS и аппаратный балансировщик нагрузки

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
<th>Полное доменное имя/Запись DNS</th>
<th>IP-адрес/Полное доменное имя</th>
<th>Сопоставляется с/комментарии</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Внутренняя запись DNS/A</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Директор</p></td>
<td><p>Запись узла директора, используемая для репликации и сервера на сервер</p></td>
</tr>
<tr class="even">
<td><p>Внутренняя запись DNS/A</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>Пул директоров</p></td>
<td><p>Запись узла для пула пула балансировки нагрузки DNS для сервера на сервер</p></td>
</tr>
<tr class="odd">
<td><p>Внутренняя запись DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Пул директоров</p></td>
<td><p>Входящий протокол SIP из внутреннего интерфейса пограничного сервера</p></td>
</tr>
<tr class="even">
<td><p>Внутренняя запись DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Виртуальный IP-адрес пула директоров HLB</p></td>
<td><p>Аппаратный балансировщик нагрузки, опубликованный веб-службами dialin с обратного прокси-сервера</p></td>
</tr>
<tr class="odd">
<td><p>Внутренняя запись DNS/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Виртуальный IP-адрес пула директоров HLB</p></td>
<td><p>Аппаратный балансировщик нагрузки, опубликованный веб-службами meet с обратного прокси-сервера</p></td>
</tr>
<tr class="even">
<td><p>Внутренняя запись DNS/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>Виртуальный IP-адрес пула директоров HLB</p></td>
<td><p>Аппаратный балансировщик нагрузки, опубликованный и определенный внешними службами веб-билетов обратного прокси-сервера для пула директора</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

