---
title: 'Lync Server 2013: сводка по сертификатам — Федерация XMPP (Extensible Messaging and Presence Protocol)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: b059a34e-99df-40af-91fe-fe2aa52841f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618374(v=OCS.15)
ms:contentKeyID: 49105661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45758175a04bad0cc673242087c0a4751c1b01bc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187432"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>Сводка по сертификатам — Федерация протокола XMPP (Extensible Messaging and Presence Protocol) в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-12-23_

В сертификатах, которые используются для обеспечения связи с партнерами XMPP, требуются дополнительные записи, содержащие сведения о доменах XMPP. Запись, включаемая в сертификат в виде альтернативного имени субъекта (SAN), содержит имя домена, который может участвовать в обмене данными по протоколу XMPP. Домен может представлять собой домен корневого уровня (например, contoso.com), если вы хотите включить протокол XMPP для всего домена, или набор дочерних доменов (например, corp.contoso.com, finance.contoso.com), если включаете протокол XMPP для подмножества пользователей.

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a>Требования к сертификатам для использования протокола XMPP


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Компонент</th>
<th>Имя субъекта</th>
<th>Альтернативные имена субъекта (SAN)/порядок</th>
<th>Комментарии</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Назначение доступа к пограничной службе пограничного сервера или пограничного пула</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p>
<p>contoso.com</p></td>
<td><p>Первые три записи SAN — это обычные записи SAN для полного пограничного сервера. Contoso.com — это запись, необходимая для федерации с партнером XMPP на корневом уровне домена. Эта запись позволит XMPP для всех доменов с суффиксом contoso.com.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>См. также


[Пример конфигурации XMPP в Lync Server 2013 – XMPP Федерация с Google говорите](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Планирование сертификатов пограничного сервера в Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  


[Настройка пограничных сертификатов для Lync Server 2013](lync-server-2013-set-up-edge-certificates.md)  
[Request — CsCertificate](https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate)  
[Set — CsCertificate](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

