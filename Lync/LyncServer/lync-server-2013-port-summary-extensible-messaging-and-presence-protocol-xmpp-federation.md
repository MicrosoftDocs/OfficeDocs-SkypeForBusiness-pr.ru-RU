---
title: Сводка по порту — расширяемая Федерация протоколов обмена сообщениями и присутствия (КСМПП)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary -  Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 62e98fab-7add-4983-a3fa-dbe74e1c3849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618371(v=OCS.15)
ms:contentKeyID: 49105658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b36a74393a8c61d5281bb009d212ee0bb12cf0a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824192"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>Сводка по порту — расширяемая Федерация протоколов обмена сообщениями и присутствия (КСМПП) в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-20_

Порты и протоколы, определенные для прокси-сервера расширяемых сообщений и протоколов КСМПП, развернутых на пограничном сервере, разрешают обмен данными между сервером пограничного сервера КСМПП и допускает передачу данных с пограничного сервера в КСМПП Федеративный партнер. Правило также определяется во внутреннем брандмауэре, доступном на сервере переднего плана или на пограничном пуле, к внешнему и внешнему интерфейсу.

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a>Сводка брандмауэра по протоколу расширенного обмена сообщениями и присутствия


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


[Пример конфигурации XMPP в Lync Server 2013 — федерация XMPP с Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Управление федеративными XMPP-партнерами в Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

