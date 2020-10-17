---
title: Сводка по DNS — Федерация расширенной службы обмена сообщениями и протокола присутствия (XMPP)
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
ms.openlocfilehash: 7ac2e44382aa75b61ae4e2966b5ef87fd977e798
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532136"
---
# <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>Сводка по DNS — Федерация XMPP (Extensible Messaging and Presence Protocol) в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-04-08_

Чтобы настроить расширенный протокол обмена сообщениями (XMPP) для развертывания, создайте две записи службы доменных имен (DNS) на внешнем DNS-сервере, которые будут разрешать записи в пограничной службе доступа пограничного сервера или пограничного пула.

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a>Сводка по DNS для расширяемого протокола XMPP


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
<th>полное доменное имя;</th>
<th>IP-адрес/запись узла полного доменного имени</th>
<th>Сопоставление/комментарии</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Внешний DNS/SRV/5269</p></td>
<td><p>_xmpp-server._tcp. contoso. com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>Внешний интерфейс прокси-сервера XMPP в пограничной службе доступа или пограничном пуле. При необходимости повторите эти действия для всех внутренних доменов SIP с пользователями Lync, в которых доступ к контактам с контактами XMPP разрешен через конфигурацию политики внешнего доступа через глобальную политику, политику сайта, в которой находится пользователь, или политика пользователей, применяемая к пользователю с поддержкой Lync. Разрешенный домен XMPP также должен быть настроен в политике федеративных партнеров XMPP. Дополнительные сведения можно найти в разделах, <strong>приведенных в разделе</strong> .</p></td>
</tr>
<tr class="even">
<td><p>Внешний DNS/A</p></td>
<td><p>xmpp.contoso.com (пример)</p></td>
<td><p>IP-адрес пограничной службы доступа на пограничном сервере или пограничном пуле, где размещен прокси-сервер XMPP</p></td>
<td><p>Указывает на пограничный сервер доступа или пограничный пул, на котором размещается прокси-служба XMPP. Как правило, созданная запись SRV указывает на эту запись узла (A или AAAA).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>См. также


[Настройка Федерации XMPP в Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md)  


[Определение требований к DNS для Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

