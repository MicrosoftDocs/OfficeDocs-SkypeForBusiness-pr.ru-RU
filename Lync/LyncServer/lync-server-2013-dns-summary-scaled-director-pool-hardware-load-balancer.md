---
title: 'Lync Server 2013: сводка по DNS — масштабируемый пул директоров, аппаратный балансировщик нагрузки'
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
ms.openlocfilehash: 891b69339416c81d81e72e43edf5f09bbf9da3e3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741069"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a>Сводка по DNS — масштабируемый пул директоров, аппаратный балансировщик нагрузки в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-20_

В таблице ниже приведены сведения о DNS-записях, которые необходимы для работы директора аппаратной балансировки нагрузки. Роль режиссера требует наличия аналогичных записей DNS в качестве внешнего сервера. Количество необходимых записей отражается в альтернативных именах тем, необходимых для вашего сертификата в директории. На сервере переднего плана не размещается учетные записи пользователей и не размещается служба Mobility Service.

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a>DNS-записи, необходимые для пула режиссеров с помощью аппаратной подсистемы балансировки нагрузки и балансировки нагрузки DNS

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
<td><p>Запись узла директора, используемая для связи между репликацией и сервером</p></td>
</tr>
<tr class="even">
<td><p>Внутренняя DNS/A</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>Пул ХЛБных ВИРТУАЛЬНЫХ каталогов</p></td>
<td><p>Запись Host для пула пулов балансировки нагрузки DNS</p></td>
</tr>
<tr class="odd">
<td><p>Внутренняя DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Пул ХЛБных ВИРТУАЛЬНЫХ каталогов</p></td>
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

