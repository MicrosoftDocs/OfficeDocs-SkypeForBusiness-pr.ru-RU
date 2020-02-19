---
title: 'Lync Server 2013: сводка по портам — один директор'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single Director
ms:assetid: 079c1414-723f-4499-b7d4-a0d7121c1626
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204648(v=OCS.15)
ms:contentKeyID: 48183322
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8515785f66101df3af0d7d35de565ba344e2b91a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139180"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---single-director-in-lync-server-2013"></a>Сводка по портам — единственный директор в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-20_

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
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP 8080</p></td>
<td><p>Внутренний интерфейс обратного прокси-сервера</p></td>
<td><p>Режиссер</p></td>
<td><p>Полученная внешними сторонами обратного прокси-сервера, связь передается в директории и веб-службы сервера переднего плана</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>Внутренний интерфейс обратного прокси-сервера</p></td>
<td><p>Режиссер</p></td>
<td><p>Полученная внешними сторонами обратного прокси-сервера, связь передается в директории и веб-службы сервера переднего плана</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>Режиссер</p></td>
<td><p>Сервер переднего плана или интерфейсный пул</p></td>
<td><p>Межсерверное взаимодействие между директором и сервером переднего плана</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>Внутренние клиенты</p></td>
<td><p>Веб-службы режиссера</p></td>
<td><p>Директор предоставляет веб-службы внутренним и внешним клиентам.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>Внутренние клиенты</p></td>
<td><p>Веб-службы режиссера</p></td>
<td><p>Директор предоставляет веб-службы внутренним и внешним клиентам.</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP 5061</p></td>
<td><p>Внутренний интерфейс пограничного сервера</p></td>
<td><p>Режиссер</p></td>
<td><p>Обмен данными SIP от пограничного сервера к директоре и внешнему серверу.</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Любые</p></td>
<td><p>Внутренний интерфейс пограничного сервера</p></td>
<td><p>Команды и сбор данных журнала для контроллера централизованной службы ведения журналов (ClsController.exe) или агента (ClasAgent.exe)</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Любые</p></td>
<td><p>Внутренний интерфейс пограничного сервера</p></td>
<td><p>Команды и сбор данных журнала для контроллера централизованной службы ведения журналов (ClsController.exe) или агента (ClasAgent.exe)</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Любые</p></td>
<td><p>Внутренний интерфейс пограничного сервера</p></td>
<td><p>Команды и сбор данных журнала для контроллера централизованной службы ведения журналов (ClsController.exe) или агента (ClasAgent.exe)</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

