---
title: 'Lync Server 2013: сводка по портам — масштабируемый пул директоров, аппаратный балансировщик нагрузки'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled Director pool, hardware load balancer
ms:assetid: 6ae2f4ac-5b64-4e45-8253-133308f5812d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204983(v=OCS.15)
ms:contentKeyID: 48184434
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18c0957d66d9b877a67819b8fd8d46d4e614cdad
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034059"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a>Сводка по портам — масштабируемый пул директоров, аппаратный балансировщик нагрузки в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-21_

Требования к портам брандмауэра для пула директоров состоят из портов, которые используются для установления связи с директором от внутреннего интерфейса пограничного сервера или внутреннего интерфейса обратного прокси-сервера. По умолчанию Microsoft Lync Server 2013 ожидает, что порты HTTP/TCP 8080 и HTTPS/TCP 4443 открываются из обратного прокси-сервера в директоре, а также интерфейсный пул и сервер переднего плана. Кроме того, должен быть обмен данными по протоколу SIP от внутреннего интерфейса пограничного сервера к директоре и к интерфейсному пулу и серверу переднего плана. Протокол SIP использует SIP/MTLS/TCP 5061 с пограничного сервера в интерфейсный пул и сервер переднего плана. Необходимо также создать правило, разрешающее передачу данных по протоколу SIP/MTLS/TCP 5061 из директора, интерфейсного пула и сервера переднего плана в внутренний интерфейс пограничного сервера.

### <a name="director-ports-and-protocols-for-firewall-definitions"></a>Порты и протоколы Директора для определений брандмауэра

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Роль/протокол/TCP или UDP/порт</th>
<th>Исходный IP-адрес</th>
<th>Конечный IP-адрес</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP 8080</p></td>
<td><p>Внутренний интерфейс обратного прокси-сервера</p></td>
<td><p>Виртуальный IP-адрес подсистемы балансировки нагрузки для директоров</p></td>
<td><p>По умолчанию полученная внешняя сторона обратного прокси-сервера передается на директор HLB VIP и серверы переднего плана.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>Внутренний интерфейс обратного прокси-сервера</p></td>
<td><p>Виртуальный IP-адрес подсистемы балансировки нагрузки для директоров</p></td>
<td><p>По умолчанию полученная внешняя сторона обратного прокси-сервера передается на директор HLB VIP и серверы переднего плана.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>Режиссер</p></td>
<td><p>Сервер переднего плана или интерфейсный пул</p></td>
<td><p>Межсерверное взаимодействие между директором HLB VIP и серверами переднего плана</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>Внутренние клиенты</p></td>
<td><p>Виртуальный IP-адрес подсистемы балансировки нагрузки для директоров</p></td>
<td><p>Директор предоставляет веб-службы внутренним и внешним клиентам.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>Внутренние клиенты</p></td>
<td><p>Виртуальный IP-адрес подсистемы балансировки нагрузки для директоров</p></td>
<td><p>Директор предоставляет веб-службы внутренним и внешним клиентам.</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP 5061</p></td>
<td><p>Внутренний интерфейс пограничного сервера</p></td>
<td><p>Виртуальный IP-адрес подсистемы балансировки нагрузки для директоров</p></td>
<td><p>Обмен данными SIP от пограничного сервера к директоре и серверам переднего плана.</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Любые</p></td>
<td><p>Режиссер</p></td>
<td><p>Команды и коллекция журналов для централизованного ведения журналов (ClsController. exe) или агента (ClsAgent. exe)</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Любые</p></td>
<td><p>Режиссер</p></td>
<td><p>Команды и коллекция журналов для централизованного ведения журналов (ClsController. exe) или агента (ClsAgent. exe)</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Любые</p></td>
<td><p>Режиссер</p></td>
<td><p>Команды и коллекция журналов для централизованного ведения журналов (ClsController. exe) или агента (ClsAgent. exe)</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

