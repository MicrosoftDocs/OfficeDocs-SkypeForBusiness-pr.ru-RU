---
title: Сводка по портам — Федерация Extensible Messaging and Presence Protocol (XMPP)
description: Сводка по портам — Федерации Extensible Messaging and Presence Protocol (XMPP).
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary -  Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 62e98fab-7add-4983-a3fa-dbe74e1c3849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618371(v=OCS.15)
ms:contentKeyID: 49105658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9508bc8b9fbcca6fb6a37478def258a9fa52c373
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543095"
---
# <a name="port-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>Сводка по портам — Федерация протокола XMPP (Extensible Messaging and Presence Protocol) в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-20_

Порты и протоколы, определенные для прокси-сервера Extensible Messaging and Presence Protocol (XMPP), развернутого на пограничном сервере, разрешают обмен данными между федеративным партнером XMPP на пограничный сервер, а также позволяет осуществлять обмен данными от пограничного сервера к федеративным партнеру XMPP. Кроме того, правило определяется на внутреннем брандмауэре от сервера переднего плана или интерфейсного пула до пограничного сервера или пограничного пула.

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a>Сводка по брандмауэру для протокола XMPP


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Протокол/TCP или UDP/порт</th>
<th>Источник (IP-адрес)</th>
<th>Назначение (IP-адрес)</th>
<th>Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Любой</p></td>
<td><p>IP-адрес интерфейса пограничного сервера доступа</p></td>
<td><p>Стандартный порт для связи "сервер-сервер" через XMPP. Разрешает связь с прокси-сервером пограничного сервера XMPP от федеративных партнеров XMPP</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>IP-адрес интерфейса пограничного сервера доступа</p></td>
<td><p>Любой</p></td>
<td><p>Стандартный порт для связи "сервер-сервер" через XMPP. Разрешает обмен данными от прокси-сервера пограничного сервера XMPP к федеративным партнерам XMPP</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/23456</p></td>
<td><p>Любой</p></td>
<td><p>IP-адрес внутреннего интерфейса пограничного сервера</p></td>
<td><p>Внутренний трафик XMPP от шлюза XMPP на сервере переднего плана или интерфейсном пуле к пограничным серверам</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>См. также


[Пример конфигурации XMPP в Lync Server 2013 – XMPP Федерация с Google говорите](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Управление федеративными партнерами XMPP в Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

