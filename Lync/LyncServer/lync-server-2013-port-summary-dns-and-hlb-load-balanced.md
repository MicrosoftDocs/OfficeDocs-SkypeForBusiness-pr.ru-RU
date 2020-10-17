---
title: 'Lync Server 2013: сводка по портам — балансировка нагрузки на DNS и HLB'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - DNS and HLB load balanced
ms:assetid: b07c37e4-820e-46ee-a678-1da95d1b87af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205179(v=OCS.15)
ms:contentKeyID: 48185149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6ba03a73538426b9c820388f65e728c36881148
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527946"
---
# <a name="port-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a>Сводка по портам — балансировка нагрузки на DNS и HLB в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-22_

Требования к портам брандмауэра для одного директора состоят из портов, которые используются для установления связи с директором от внутреннего интерфейса или внутренней сети обратного прокси-сервера. По умолчанию Microsoft Lync Server 2013 ожидает, что порты HTTP/TCP 8080 и HTTPS/TCP 4443 открываются из обратного прокси-сервера в директоре, а также интерфейсный пул и сервер переднего плана. Кроме того, должен быть обмен данными по протоколу SIP от внутреннего интерфейса пограничного сервера к директоре и к интерфейсному пулу и серверу переднего плана. Протокол SIP использует SIP/MTLS/TCP 5061 с пограничного сервера в интерфейсный пул и сервер переднего плана. Необходимо также создать правило, разрешающее передачу данных по протоколу SIP/MTLS/TCP 5061 из директора, интерфейсного пула и сервера переднего плана в внутренний интерфейс пограничного сервера.

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a>Порты и протоколы единого директора для определений брандмауэра

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
<th>Примечания</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP 8080</p></td>
<td><p>Внутренний интерфейс обратного прокси-сервера</p></td>
<td><p>Виртуальный IP-адрес подсистемы балансировки нагрузки для директоров</p></td>
<td><p>По умолчанию полученная внешняя сторона обратного прокси-сервера передается на директор HLB VIP и веб-службы сервера переднего плана.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>Внутренний интерфейс обратного прокси-сервера</p></td>
<td><p>Виртуальный IP-адрес подсистемы балансировки нагрузки для директоров</p></td>
<td><p>По умолчанию полученная внешняя сторона обратного прокси-сервера передается на директор HLB VIP и веб-службы сервера переднего плана.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>Директор</p></td>
<td><p>Интерфейсный пул или сервер переднего плана</p></td>
<td><p>Обмен данными между сервером HLB и сервером переднего плана и серверами переднего плана и серверами переднего плана.</p></td>
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
<td><p>Директор</p></td>
<td><p>Обмен данными SIP от пограничного сервера к директоре, а также к серверам переднего плана.</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Любой</p></td>
<td><p>Директор</p></td>
<td><p>Команды и сбор журналов централизованной службы ведения журналов (ClsController.exe) или агента (ClsAgent.exe)</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Любой</p></td>
<td><p>Директор</p></td>
<td><p>Команды и сбор журналов централизованной службы ведения журналов (ClsController.exe) или агента (ClsAgent.exe)</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Любой</p></td>
<td><p>Директор</p></td>
<td><p>Команды и сбор журналов централизованной службы ведения журналов (ClsController.exe) или агента (ClsAgent.exe)</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

