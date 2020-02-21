---
title: 'Lync Server 2013: требования к DNS для серверов сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Persistent Chat Servers
ms:assetid: f7531374-d7ed-4b63-ae81-02294cb4496a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205391(v=OCS.15)
ms:contentKeyID: 48185857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea581eb04f2899ecafd49364b38a1064303bdcdc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-persistent-chat-servers-in-lync-server-2013"></a>Требования DNS для серверов сохраняемого чата в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-06-28_

В этом разделе описываются записи службы доменных имен (DNS), необходимые для развертывания серверов сохраняемого чата.

<div>

## <a name="dns-records-for-persistent-chat-servers"></a>Записи DNS для серверов сохраняемых чатов

В следующей таблице указаны требования к DNS для развертывания сервера сохраняемого чата.

### <a name="dns-requirements-for-a-persistent-chat-server"></a>Требования DNS для серверов сохраняемых чатов

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Сценарий развертывания</th>
<th>Требование DNS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Один сервер сохраняемого чата</p></td>
<td><p>Внутренняя запись A, разрешающая полное доменное имя сервера в IP-адрес.</p></td>
</tr>
<tr class="even">
<td><p>Пул сохраняемого чата</p></td>
<td><p>Внутренняя запись A, разрешающая полное доменное имя сервера в IP-адрес.</p>
<p><strong>Пример</strong></p>
<p>PersistentChatServer01.contoso.com 10.10.10.1</p>
<p>PersistentChatServer02.contoso.com 10.10.10.2</p>
<p>Внутренняя запись A, разрешающая полное доменное имя сервера в IP-адрес.</p>
<p><strong>Пример</strong></p>
<p>PersistentChatPool.contoso.com 10.10.10.1</p>
<p>PersistentChatPool.contoso.com 10.10.10.2</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

