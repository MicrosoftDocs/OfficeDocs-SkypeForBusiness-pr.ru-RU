---
title: 'Lync Server 2013: сводка по портам — общедоступная служба обмена мгновенными сообщениями'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Public instant messaging connectivity
ms:assetid: f46756ec-1401-4ca2-a4a4-5cd28bcfdc7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618376(v=OCS.15)
ms:contentKeyID: 49105663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87a51e2030c17e7ed228a75b474b168a74924cb2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a>Сводка по портам — общедоступная служба обмена мгновенными сообщениями в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-16_

Чтобы настроить брандмауэр для поддержки портов и протоколов, необходимых для поддержки подключения к общедоступным службам обмена мгновенными сообщениями, сначала обратите внимание на то, что SIP/MTLS/TCP 5061 является двунаправленной учетной записью для связи с контактами в общедоступном поставщике IM для связи с клиентами Lync

Windows Live Messenger может участвовать в аудио-и видеосвязи с клиентами Lync. Эти учетные записи для похожих портов брандмауэра и протоколов, которые, как правило, находятся на брандмауэре для поддержки клиентов Lync как внешних пользователей.

<div>


> [!IMPORTANT]  
> Lync — это мощное средство для связи между организациями и пользователями мира. Для Федерации с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств, не относящихся к стандартной клиентской лицензии Lync (CAL). В этот список будет добавлена Федерация Skype, что позволит пользователям Lync достичь сотен миллионов людей с помощью обмена мгновенными сообщениями и голосовой связью.<BR>Федерация с контактами клиентов Messenger официально заканчивается 15 марта 2013, за исключением континентальная Китая. Skype станет клиентом Федерации для федеративных пользователей, которые ранее использовали Messenger.



</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a>Сводка по брандмауэру — связь с общедоступной службой обмена мгновенными сообщениями


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
<td><p>Доступ/SIP (MTLS)/TCP/5061</p></td>
<td><p>Партнеры по связи с общедоступной службой обмена мгновенными сообщениями</p></td>
<td><p>Интерфейс доступа пограничного сервера</p></td>
<td><p>Для федеративного и общедоступной службы обмена мгновенными сообщениями, использующей SIP.</p></td>
</tr>
<tr class="even">
<td><p>Доступ/SIP (MTLS)/TCP/5061</p></td>
<td><p>Интерфейс доступа пограничного сервера</p></td>
<td><p>Партнеры по связи с общедоступной службой обмена мгновенными сообщениями</p></td>
<td><p>Для федеративного и общедоступной службы обмена мгновенными сообщениями, использующей SIP.</p></td>
</tr>
<tr class="odd">
<td><p>/TCP/443 доступа и SIP (TLS)</p></td>
<td><p>Клиенты</p></td>
<td><p>Интерфейс доступа пограничного сервера</p></td>
<td><p>Трафик SIP от клиента к серверу для доступа внешних пользователей.</p></td>
</tr>
<tr class="even">
<td><p>АУДИО-И ВИДЕОДАННЫЕ/RTP/TCP/50000-– 999</p></td>
<td><p>Интерфейс доступа пограничного сервера</p></td>
<td><p>Клиенты Live Messenger</p></td>
<td><p>Используется для сеансов аудио- и видеоконференций с использованием Windows Live Messenger, если настроена связь с общедоступной службой обмена мгновенными сообщениями.</p></td>
</tr>
<tr class="odd">
<td><p>АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</p></td>
<td><p>Интерфейс доступа пограничного сервера</p></td>
<td><p>Клиенты Live Messenger</p></td>
<td><p>Необходимо для связи с общедоступной службой обмена мгновенными сообщениями с Windows Live Messenger.</p></td>
</tr>
<tr class="even">
<td><p>АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</p></td>
<td><p>Клиенты Live Messenger</p></td>
<td><p>Интерфейс доступа пограничного сервера</p></td>
<td><p>Необходимо для связи с общедоступной службой обмена мгновенными сообщениями с Windows Live Messenger.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>См. также


[Сценарии доступа внешних пользователей в Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Определение требований к внешнему брандмауэру аудио-и видеоданных для Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

