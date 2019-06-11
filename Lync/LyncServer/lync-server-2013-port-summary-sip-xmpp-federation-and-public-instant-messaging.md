---
title: 'Общие сведения о портах: SIP, Федерация КСМПП и общедоступная служба обмена мгновенными сообщениями'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - SIP, XMPP federation, and public instant messaging
ms:assetid: ab05bdd6-e9b0-4b1b-9dd9-29ab88e8befe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618373(v=OCS.15)
ms:contentKeyID: 49105660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2edcad9806c5e6c8714f3face301211633a53fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824318"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Общие сведения о портах: SIP, Федерация КСМПП и общедоступная служба обмена мгновенными сообщениями в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-03-15_

Требования к портам, протоколам и брандмауэрам для Федерации с Microsoft Lync Server 2013, Lync Server 2010 и Office Communications Server похожи на развернутый пограничный сервер. Клиенты инициируют связь с службой Edge Access через TLS/SIP/TCP 443. Федеративные партнеры тем не менее, будут инициировать связь с службой Edge Access через MTLS/SIP/TCP 5061.

Чтобы настроить брандмауэр для порта и протоколов, необходимых для поддержки общедоступной службы обмена мгновенными сообщениями, сначала обратите внимание на то, что SIP/MTLS/TCP 5061 является двунаправленным, чтобы иметь возможность контактам в общедоступном поставщике обмена мгновенными сообщениями для связи с клиентами Lync или Lync для контактам из общедоступного обмена мгновенными сообщениями.

Windows Live Messenger может принимать участие в голосовой и видеосвязи с клиентами Lync. Эти учетные записи похожи на настройки порта и протокола брандмауэра, которые обычно используются в брандмауэре для поддержки клиентов Lync в качестве внешних пользователей.

<div>


> [!IMPORTANT]
> В некоторых случаях Lync — это мощный инструмент для связи между организациями и людьми по всему миру. Для интеграции с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств, Кроме стандартной клиентской лицензии Lync (CAL). В этот список будет добавлена Федерация Skype, благодаря чему пользователи Lync смогут общаться с сотнями миллионов людей с помощью обмена мгновенными сообщениями и голосовой связью.<BR>Интеграция с контактами клиентов Messenger официально заканчивается 15 марта 2013, за исключением маинланд Китая. Skype станет клиентом Федерации федеративных пользователей, которые ранее использовали Messenger.



</div>

Порты и протоколы, определенные для прокси-сервера расширяемых сообщений и протоколов КСМПП, развернутых на пограничном сервере, разрешают обмен данными между сервером пограничного сервера КСМПП и допускает передачу данных с пограничного сервера в КСМПП Федеративный партнер. Правило также определяется во внутреннем брандмауэре, доступном на сервере переднего плана или на пограничном пуле, к внешнему и внешнему интерфейсу.

<div>

## <a name="firewall-summary---sip-federation"></a>Сводка по межсетевому экрану — Федерация SIP


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
<td><p>Общедоступный IP-адрес службы пограничного доступа</p></td>
<td><p>Любой</p></td>
<td><p>Для Федеративной и общедоступной службы обмена мгновенными сообщениями с помощью SIP</p></td>
</tr>
</tbody>
</table>


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

## <a name="firewall-summary---extensible-messaging-and-presence-protocol-xmpp"></a>Сводка по межсетевому экрану — расширяемый протокол для обмена сообщениями и присутствия (КСМПП)


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
<th>Комментарии</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>КСМПП/TCP/5269</p></td>
<td><p>Любой</p></td>
<td><p>IP-адрес интерфейса службы Edge Access</p></td>
<td><p>Стандартный коммуникационный порт "сервер-сервер" для КСМПП. Разрешает связь с прокси-сервером пограничного сервера КСМПП от федеративных КСМПП партнеров</p></td>
</tr>
<tr class="even">
<td><p>КСМПП/TCP/5269</p></td>
<td><p>IP-адрес интерфейса службы Edge Access</p></td>
<td><p>Любой</p></td>
<td><p>Стандартный коммуникационный порт "сервер-сервер" для КСМПП. Разрешает взаимодействие с КСМПП прокси-сервером для федеративных КСМПП партнеров</p></td>
</tr>
<tr class="odd">
<td><p>КСМПП/MTLS/23456</p></td>
<td><p>Любой</p></td>
<td><p>IP-адрес внутреннего интерфейса пограничного сервера</p></td>
<td><p>Внутренний КСМПП трафик из шлюза КСМПП на сервере переднего плана или в пуле переднего плана на пограничный сервер</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>См. также


[Сценарии доступа внешних пользователей в Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Определение требований к внешнему брандмауэру аудио- и видеосвязи и портам для Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[Управление федеративными XMPP-партнерами в Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

