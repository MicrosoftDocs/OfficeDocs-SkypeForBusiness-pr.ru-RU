---
title: 'Lync Server 2013: сводка по портам — балансировка нагрузки на DNS и аппаратная балансировка нагрузки'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - DNS and HLB load balanced
ms:assetid: b07c37e4-820e-46ee-a678-1da95d1b87af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205179(v=OCS.15)
ms:contentKeyID: 48185149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5bd2a276f9495d314d2a8d4588f027df08978b94
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824066"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a>Сводка по портам — балансировка нагрузки на DNS и аппаратная балансировка нагрузки в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-22_

Требования к порту брандмауэра для единого режиссера состоят из портов, используемых для установления связи с режиссером из внутреннего интерфейса или внутренней сети обратного прокси-сервера. По умолчанию Microsoft Lync Server 2013 ожидает, что порты HTTP/TCP 8080 и HTTPS/TCP 4443 будут открыты из обратного прокси-сервера в директор, а также с интерфейсом пула и сервера переднего плана. Кроме того, между внутренним интерфейсом пограничного сервера и пулом, а также интерфейсом сервера и переднего плана должен быть установлен протокол SIP. Протокол SIP использует интерфейс SIP/MTLS/TCP 5061 с пограничного сервера до пула переднего плана и сервера переднего плана. Кроме того, необходимо также создать правило, которое позволяет использовать интерфейс SIP/MTLS/TCP 5061, входящий в состав внешнего интерфейса пограничного сервера и сервера переднего плана.

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a>Порты и протоколы для отдельных режиссеров для определения брандмауэра

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Role/Protocol/TCP/UDP/порт</th>
<th>IP-адрес источника</th>
<th>IP-адрес назначения</th>
<th>Примечания.</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP 8080</p></td>
<td><p>Внутренний прокси-интерфейс обратной стороне</p></td>
<td><p>IP-адрес подсистемы балансировки нагрузки для режиссера</p></td>
<td><p>По внешнему краю обратного прокси-сервера связь передается в каталог ХЛБ VIP и на сервер переднего плана.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>Внутренний прокси-интерфейс обратной стороне</p></td>
<td><p>IP-адрес подсистемы балансировки нагрузки для режиссера</p></td>
<td><p>По внешнему краю обратного прокси-сервера связь передается в каталог ХЛБ VIP и на сервер переднего плана.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>Директор</p></td>
<td><p>Пул переднего плана или сервер переднего плана</p></td>
<td><p>Межсерверная связь между директором ХЛБ VIP и сервером переднего плана и серверами переднего плана.</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>Внутренние клиенты</p></td>
<td><p>IP-адрес подсистемы балансировки нагрузки для режиссера</p></td>
<td><p>Режиссер предоставляет веб-службы внутренним и внешним клиентам.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>Внутренние клиенты</p></td>
<td><p>IP-адрес подсистемы балансировки нагрузки для режиссера</p></td>
<td><p>Режиссер предоставляет веб-службы внутренним и внешним клиентам.</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP 5061</p></td>
<td><p>Внутренний интерфейс пограничного сервера</p></td>
<td><p>Директор</p></td>
<td><p>Связь SIP от пограничного сервера к директоре, а также к серверам переднего плана.</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Любой</p></td>
<td><p>Директор</p></td>
<td><p>Команды для централизованного ведения журналов (Клсконтроллер. exe) или агента (Клсажент. exe) и сбора журналов</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Любой</p></td>
<td><p>Директор</p></td>
<td><p>Команды для централизованного ведения журналов (Клсконтроллер. exe) или агента (Клсажент. exe) и сбора журналов</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Любой</p></td>
<td><p>Директор</p></td>
<td><p>Команды для централизованного ведения журналов (Клсконтроллер. exe) или агента (Клсажент. exe) и сбора журналов</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

