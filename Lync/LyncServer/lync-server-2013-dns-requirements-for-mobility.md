---
title: 'Lync Server 2013: требования к DNS для мобильных устройств'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for mobility
ms:assetid: df6962bc-2a16-440e-a333-022ebd14f957
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690040(v=OCS.15)
ms:contentKeyID: 48185624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc11c79c291f7db7ad9e9e3228644ee27d42e555
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-mobility-with-lync-server-2013"></a>Требования к DNS для мобильных устройств с помощью Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-13_

При развертывании функции Lync Server 2013 Mobility Service вы можете использовать новые URL-адреса, доступные в службе автообнаружения Microsoft Lync Server 2013, или использовать существующие URL. Если вы используете существующие URL-адреса, пользователи должны вручную ввести URL-адреса в параметры мобильного устройства. Этот параметр обычно используется для устранения неполадок. При использовании новых URL-адресов мобильные клиенты могут автоматически определять ресурсы Lync Server 2013. Если вы поддерживаете автоматическое обнаружение, вам нужно добавить новые записи DNS. В этом разделе описаны записи DNS, необходимые для автоматического обнаружения.

Для поддержки автоматического обнаружения необходимо создать следующие записи DNS для каждого домена SIP:

  - Внутренняя запись DNS для поддержки мобильных пользователей, которые подключаются из сети Организации

  - Внешняя (или общедоступная) запись DNS для поддержки мобильных пользователей, подключающихся из Интернета;

Внутренний URL-адрес автоматического обнаружения не должен быть адресом за пределами вашей сети. URL-адрес внешнего автоматического обнаружения не должен быть адресом в сети. Тем не менее, если вы не можете выполнить это требование для внешнего URL-адреса, не следует повлиять на мобильный клиент.

DNS-записи могут быть либо записями CNAME, либо записями (ведущими).

**Внутренние DNS-записи**

Вам нужно создать одну из следующих внутренних DNS-записей:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Тип записи</th>
<th>Определение имени узла или SRV</th>
<th>Разрешается в</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscoverinternal.&lt;sipdomain&gt;</p></td>
<td><p>Полное доменное имя (FQDN) внутренних веб-служб для пула, если у вас есть один из них или для пула переднего плана, если у вас нет директора</p></td>
</tr>
<tr class="even">
<td><p>A (узел)</p></td>
<td><p>lyncdiscoverinternal.&lt;sipdomain&gt;</p></td>
<td><p>IP-адрес внутренних веб-служб (VIP) (виртуальный IP-адрес) Если вы используете подсистему балансировки нагрузки в вашем пуле, если у вас есть один из них или у вас нет интерфейса, если у вас нет директора</p></td>
</tr>
</tbody>
</table>


**Внешние записи DNS**

Вам необходимо создать одну из следующих внешних DNS-записей:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Тип записи</th>
<th>Имя узла</th>
<th>Разрешается в</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscover. &lt;сипдомаин&gt;</p></td>
<td><p>Внешнее полное доменное имя веб-служб для пула, если у вас есть один из них или для пула переднего плана, если у вас нет директора</p></td>
</tr>
<tr class="even">
<td><p>A (узел)</p></td>
<td><p>lyncdiscover. &lt;сипдомаин&gt;</p></td>
<td><p>Внешний или общий IP-адрес (VIP, если вы используете подсистему балансировки нагрузки) для обратного прокси-сервера.</p></td>
</tr>
<tr class="odd">
<td><p>SRV</p></td>
<td><p>_sipfederationtls._tcp. &lt;сипдомаин&gt;</p>
<p>Разрешение на запись узла (A или AAAA) для службы пограничного доступа</p></td>
<td><p>Для поддержки службы push-уведомлений и службы push-уведомлений Apple вы создаете одну запись SRV для каждого домена SIP с клиентами Microsoft Lync Mobile.</p>
<div>

> [!IMPORTANT]  
> Это требование относится только к клиентам Microsoft Lync Mobile на мобильных устройствах Apple и Microsoft. Устройства андриод и Nokia Symbian не используют push-уведомление.


</div></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Lyncdiscover, также называемый автообнаружением, трафик проходит через обратный прокси-сервер. Запись SRV указывает на запись, которая разрешается службой Edge Access.



</div>

</div>

<span> </span>

</div>

</div>

</div>

