---
title: 'Lync Server 2013: Общие сведения о портах — общедоступная служба обмена мгновенными сообщениями'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Public instant messaging connectivity
ms:assetid: f46756ec-1401-4ca2-a4a4-5cd28bcfdc7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618376(v=OCS.15)
ms:contentKeyID: 49105663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5bb6b8d0d9277b7d77440519596da76585b9d91b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824248"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a>Общие сведения о портах — общедоступная служба обмена мгновенными сообщениями в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-16_

Чтобы настроить брандмауэр для порта и протоколов, необходимых для поддержки общедоступной службы обмена мгновенными сообщениями, сначала обратите внимание на то, что SIP/MTLS/TCP 5061 является двунаправленным, чтобы иметь возможность контактам в общедоступном поставщике обмена мгновенными сообщениями для связи с клиентами Lync или Lync для контактам из общедоступного обмена мгновенными сообщениями.

Windows Live Messenger может принимать участие в голосовой и видеосвязи с клиентами Lync. Эти учетные записи похожи на настройки порта и протокола брандмауэра, которые обычно используются в брандмауэре для поддержки клиентов Lync в качестве внешних пользователей.

<div>


> [!IMPORTANT]  
> В некоторых случаях Lync — это мощный инструмент для связи между организациями и людьми по всему миру. Для интеграции с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств, Кроме стандартной клиентской лицензии Lync (CAL). В этот список будет добавлена Федерация Skype, благодаря чему пользователи Lync смогут общаться с сотнями миллионов людей с помощью обмена мгновенными сообщениями и голосовой связью.<BR>Интеграция с контактами клиентов Messenger официально заканчивается 15 марта 2013, за исключением маинланд Китая. Skype станет клиентом Федерации федеративных пользователей, которые ранее использовали Messenger.



</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a>Сводка по брандмауэрам: общедоступная служба обмена мгновенными сообщениями


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
<td><p>Access/SIP (MTLS)/TCP/5061</p></td>
<td><p>Партнеры по подключению общедоступных мгновенных сообщений</p></td>
<td><p>Интерфейс доступа пограничного сервера</p></td>
<td><p>Для Федеративной и общедоступной службы обмена мгновенными сообщениями, использующих SIP.</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP (MTLS)/TCP/5061</p></td>
<td><p>Интерфейс доступа пограничного сервера</p></td>
<td><p>Партнеры по подключению общедоступных мгновенных сообщений</p></td>
<td><p>Для Федеративной и общедоступной службы обмена мгновенными сообщениями, использующих SIP.</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP (TLS)/TCP/443</p></td>
<td><p>Клиенты</p></td>
<td><p>Интерфейс доступа пограничного сервера</p></td>
<td><p>Трафик SIP от клиента к серверу для доступа внешних пользователей.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59,999</p></td>
<td><p>Интерфейс доступа пограничного сервера</p></td>
<td><p>Клиенты Live Messenger</p></td>
<td><p>Используется для сеансов обмена мгновенными сообщениями с помощью Windows Live Messenger, если настроена служба общего доступа к данным.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, МСТУРН/UDP/3478</p></td>
<td><p>Интерфейс доступа пограничного сервера</p></td>
<td><p>Клиенты Live Messenger</p></td>
<td><p>Требуется для общедоступной службы обмена мгновенными сообщениями с Windows Live Messenger.</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, МСТУРН/UDP/3478</p></td>
<td><p>Клиенты Live Messenger</p></td>
<td><p>Интерфейс доступа пограничного сервера</p></td>
<td><p>Требуется для общедоступной службы обмена мгновенными сообщениями с Windows Live Messenger.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>См. также


[Сценарии доступа внешних пользователей в Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Определение требований к внешнему брандмауэру аудио- и видеосвязи и портам для Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

