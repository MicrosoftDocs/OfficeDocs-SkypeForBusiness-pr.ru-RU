---
title: 'Сводка по портам: SIP, Федерация XMPP и общедоступная служба обмена мгновенными сообщениями'
description: 'Сводка по портам: SIP, Федерация XMPP и общедоступные мгновенные сообщения.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - SIP, XMPP federation, and public instant messaging
ms:assetid: ab05bdd6-e9b0-4b1b-9dd9-29ab88e8befe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618373(v=OCS.15)
ms:contentKeyID: 49105660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c58dbf7bdd56b4678d56f96a11332219bb40c17
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566363"
---
# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Сводка по портам: SIP, Федерация XMPP и общедоступные службы обмена мгновенными сообщениями в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-03-15_

Требования к портам, протоколам и брандмауэрам для Федерации с Microsoft Lync Server 2013, Lync Server 2010 и Office Communications Server схожи с развернутым пограничным сервером. Клиенты инициируют связь с пограничной службой доступа через TLS/SIP/TCP 443. Федеративные партнеры тем не менее инициируют связь с службой пограничного доступа через MTLS/SIP/TCP 5061.

Чтобы настроить брандмауэр для поддержки портов и протоколов, необходимых для поддержки подключения к общедоступным службам обмена мгновенными сообщениями, сначала обратите внимание на то, что SIP/MTLS/TCP 5061 является двунаправленной учетной записью для связи с контактами в общедоступном поставщике IM для связи с клиентами Lync

Windows Live Messenger может участвовать в аудио-и видеосвязи с клиентами Lync. Эти учетные записи для похожих портов брандмауэра и протоколов, которые, как правило, находятся на брандмауэре для поддержки клиентов Lync как внешних пользователей.

<div>


> [!IMPORTANT]
> Lync — это мощное средство для связи между организациями и пользователями мира. Для Федерации с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств, не относящихся к стандартной клиентской лицензии Lync (CAL). В этот список будет добавлена Федерация Skype, что позволит пользователям Lync достичь сотен миллионов людей с помощью обмена мгновенными сообщениями и голосовой связью.<BR>Федерация с контактами клиентов Messenger официально заканчивается 15 марта 2013, за исключением континентальная Китая. Skype станет клиентом Федерации для федеративных пользователей, которые ранее использовали Messenger.



</div>

Порты и протоколы, определенные для прокси-сервера Extensible Messaging and Presence Protocol (XMPP), развернутого на пограничном сервере, разрешают обмен данными между федеративным партнером XMPP на пограничный сервер, а также позволяет осуществлять обмен данными от пограничного сервера к федеративным партнеру XMPP. Кроме того, правило определяется на внутреннем брандмауэре от сервера переднего плана или интерфейсного пула до пограничного сервера или пограничного пула.

<div>

## <a name="firewall-summary---sip-federation"></a>Сводка по брандмауэру: Федерация SIP


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
<td><p>Доступ/SIP (MTLS)/TCP/5061</p></td>
<td><p>Общедоступный IP-адрес пограничной службы доступа</p></td>
<td><p>Любой</p></td>
<td><p>Для федеративного подключения и подключения к общедоступным службам обмена мгновенными сообщениями с помощью SIP</p></td>
</tr>
</tbody>
</table>


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
<th>Примечания</th>
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

## <a name="firewall-summary---extensible-messaging-and-presence-protocol-xmpp"></a>Сводка по брандмауэру: расширенный протокол обмена сообщениями и присутствия (XMPP)


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


[Сценарии доступа внешних пользователей в Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Определение требований к внешнему брандмауэру аудио-и видеоданных для Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[Управление федеративными партнерами XMPP в Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

