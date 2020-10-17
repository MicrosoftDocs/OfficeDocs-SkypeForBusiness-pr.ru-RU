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
ms.openlocfilehash: 508e9c8e030de7aeb496a1285ff7b965e43c2a6b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501436"
---
# <a name="dns-requirements-for-mobility-with-lync-server-2013"></a>Требования DNS для мобильных устройств с Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-13_

При развертывании компонента Lync Server 2013 Mobility можно использовать новые URL-адреса, доступные в службе автообнаружения Microsoft Lync Server 2013, или использовать существующие URL-адреса веб-служб. Если вы используете существующие URL-адреса, пользователям необходимо вручную вводить эти URL-адреса в параметрах мобильного устройства. Данный вариант обычно используется для поиска и устранения неполадок. При использовании новых URL-адресов мобильные клиенты могут автоматически обнаруживать ресурсы Lync Server 2013. В случае обеспечения поддержки автоматического обнаружения вам требуется добавить новые DNS-записи. В этом разделе описаны те DNS-записи, которые требуются для автоматического обнаружения.

Чтобы обеспечить поддержку автоматического обнаружения, вам необходимо создать следующие DNS-записи для каждого домена SIP:

  - Внутренняя DNS-запись для поддержки мобильных пользователей, которые подключаются изнутри сети организации

  - Внешняя ? или общая ? DNS-запись для поддержки мобильных пользователей, которые подключаются из Интернета

Внутренний URL-адрес автообнаружения не должен поддерживать обращение извне сети. Внешний URL-адрес автообнаружения не должен поддерживать обращение из вашей сети. Однако если вы не можете выполнить данное условие для внешнего URL-адреса, это не окажет негативного влияния на функциональные возможности мобильного клиента.

DNS-записи могут быть либо записями CNAME, либо A (узла).

**Внутренние DNS-записи**

Вам необходимо создать одну из следующих внутренних DNS-записей:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Тип записи</th>
<th>Имя узла или определение SRV</th>
<th>Разрешается в</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscoverinternal. &lt; sipdomain&gt;</p></td>
<td><p>Полное доменное имя внутренних веб-служб (полное доменное имя) для пула директоров (если у вас есть) или для пула переднего плана, если у вас нет директора</p></td>
</tr>
<tr class="even">
<td><p>A (узел)</p></td>
<td><p>lyncdiscoverinternal. &lt; sipdomain&gt;</p></td>
<td><p>IP-адрес внутренних веб-служб (виртуальный IP-адрес, если вы используете подсистему балансировки нагрузки) пула директоров (если у вас есть один или из интерфейсного пула, если у вас нет директора)</p></td>
</tr>
</tbody>
</table>


**Внешние DNS-записи**

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
<td><p>lyncdiscover. &lt;sipdomain&gt;</p></td>
<td><p>Полное доменное имя внешних веб-служб для пула директоров, если таковой имеется, или для пула переднего плана, если у вас нет директора</p></td>
</tr>
<tr class="even">
<td><p>A (узел)</p></td>
<td><p>lyncdiscover. &lt;sipdomain&gt;</p></td>
<td><p>Внешний или общий IP-адрес (виртуальный IP-адрес, если вы используете подсистему балансировки нагрузки) обратного прокси-сервера</p></td>
</tr>
<tr class="odd">
<td><p>SRV</p></td>
<td><p>_sipfederationtls _sipfederationtls._tcp. &lt;sipdomain&gt;</p>
<p>Разрешается в запись узла (A или AAAA) для службы пограничного доступа</p></td>
<td><p>Чтобы поддерживать службу push-уведомлений и службу push-уведомлений Apple, создайте одну запись SRV для каждого домена SIP с клиентами Microsoft Lync Mobile.</p>
<div>

> [!IMPORTANT]  
> Это требование относится только к клиентам Microsoft Lync Mobile на мобильных устройствах Apple и Майкрософт. Устройства Android и Nokia Symbian не используют push-уведомления.


</div></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Lyncdiscover, также называемый автообнаружением, трафик проходит через обратный прокси-сервер. Запись SRV указывает на запись, которая разрешается через пограничный сервер доступа.



</div>

</div>

<span> </span>

</div>

</div>

</div>

