---
title: 'Lync Server 2013: сводка по DNS — масштабируемый пул директоров, аппаратный балансировщик нагрузки'
description: 'Lync Server 2013: сводка по DNS — масштабируемый пул директоров, аппаратный балансировщик нагрузки.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled Director pool, hardware load balancer
ms:assetid: 08ba48e6-bfa1-4ab0-bc89-d58ddb9c20af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204655(v=OCS.15)
ms:contentKeyID: 48183340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7198e6a97feed8ce70cb16753ad1f21d58ef246c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555885"
---
# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a>Сводка по DNS — масштабируемый пул директоров, аппаратный балансировщик нагрузки в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-20_

В следующей таблице приведена сводка DNS-записей, необходимых для поддержки директора аппаратной балансировки нагрузки. Роли директора необходимы аналогичные записи DNS в качестве сервера переднего плана. Количество необходимых записей отражается в альтернативных именах субъектов, необходимых для сертификата директора. От сервера переднего плана директору пула не размещаются учетные записи пользователей или не размещаются службы Mobility Service.

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a>Записи DNS, необходимые для пула директоров с использованием аппаратной подсистемы балансировки нагрузки и балансировки нагрузки на DNS

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
<td><p>Запись узла директора, используемая для обмена данными между репликацией и сервером</p></td>
</tr>
<tr class="even">
<td><p>Внутренняя запись DNS/A</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>Виртуальный IP-адрес пула директоров HLB</p></td>
<td><p>Запись узла для пула директоров с балансировкой нагрузки DNS</p></td>
</tr>
<tr class="odd">
<td><p>Внутренняя запись DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Виртуальный IP-адрес пула директоров HLB</p></td>
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

