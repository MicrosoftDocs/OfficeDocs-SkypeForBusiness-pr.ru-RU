---
title: 'Сводка DNS: интеграция расширяемого обмена сообщениями и протокола присутствия (КСМПП)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 0f720a2a-8ab5-43cc-882a-ab595ed3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618368(v=OCS.15)
ms:contentKeyID: 49105655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 941996ea1167cf9baeee05567a00c71ea5ed4baa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>Общие сведения о DNS — расширяемая Федерация протоколов обмена сообщениями и доступности КСМПП в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-04-08_

Чтобы настроить расширенный протокол обмена сообщениями (КСМПП) для развертывания, вы создаете две записи DNS (Domain Name System) на внешнем DNS-сервере, который будет разрешать записи в службу Edge EDGE на пограничном сервере или пуле Edge.

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a>Сводка DNS по расширенному протоколу обмена сообщениями и присутствием


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Расположение/тип/порт</th>
<th>Полное доменное имя</th>
<th>IP-адрес или полное доменное имя записи узла</th>
<th>Карты и примечания</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Внешние DNS/SRV/5269</p></td>
<td><p>_xmpp-server._tcp.contoso.com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>Внешний интерфейс КСМПП прокси-сервера в службе пограничного доступа или пуле Edge. При необходимости повторите эти действия для всех внутренних доменов SIP, в которых пользователи Lync поддерживают доступ к контактам с контактами КСМПП с помощью глобальной политики, политики сайта, в которой находится пользователь, или политики пользователя, примененной к Пользователь с поддержкой Lync. Разрешенный домен КСМПП также должен быть настроен в политике федеративных партнеров КСМПП. Дополнительные сведения <strong>можно</strong> найти в разделах.</p></td>
</tr>
<tr class="even">
<td><p>Внешние DNS/A</p></td>
<td><p>xmpp.contoso.com (например)</p></td>
<td><p>IP-адрес службы пограничного доступа на пограничном сервере или в пограничном пуле, где размещен прокси-сервер КСМПП</p></td>
<td><p>Указывает на службу пограничного доступа или пул EDGE, на котором размещена служба прокси КСМПП. Как правило, создаваемая SRV-запись будет указывать на эту запись узла (A или AAAA).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>См. также


[Настройка федерации XMPP в Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md)  


[Определение требований DNS для Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

