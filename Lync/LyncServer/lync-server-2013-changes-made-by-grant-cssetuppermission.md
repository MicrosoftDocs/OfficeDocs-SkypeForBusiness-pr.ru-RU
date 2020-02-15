---
title: 'Lync Server 2013: изменения, внесенные с помощью GRANT — CsSetupPermission'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsSetupPermission
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205250(v=OCS.15)
ms:contentKeyID: 48185360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23547ebc7faf594ee3ea72ef7d0c094846ac94b3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043921"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a>Изменения, внесенные с помощью GRANT – CsSetupPermission в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-06-20_

Чтобы делегировать установку, можно предоставить разрешения универсальной группе RTCUniversalServerAdmins для определенного подразделения Active Directory (OU), разрешив членам группы RTCUniversalServerAdmins в этом подразделении установить Lync Server 2013 в заданном домен, не являющийся членом группы администраторов домена.

Командлет **Grant-CsSetupPermission** предоставляет группе RTCUniversalServerAdmins разрешения на подразделение, как показано в следующей таблице.

### <a name="permissions-granted-to-objects-in-the-ou"></a>Разрешения. предоставляемые на объекты в подразделении

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Разрешения применяются к</th>
<th>Предоставляемые разрешения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalServerAdmins</p></td>
<td><p>Особый доступ на:</p>
<ul>
<li><p>чтение в servicePrincipalName;</p></li>
<li><p>запись в servicePrincipalName;</p></li>
<li><p>удаление дерева;</p></li>
<li><p>репликацию изменений каталога.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Объектам-потомкам serviceConnectionPoint</p></td>
<td><p>Особый доступ на:</p>
<ul>
<li><p>чтение;</p></li>
<li><p>запись;</p></li>
<li><p>создание дочерних объектов;</p></li>
<li><p>удаление дочерних объектов;</p></li>
<li><p>перечень содержимого;</p></li>
<li><p>запись свойства;</p></li>
<li><p>чтение свойства;</p></li>
<li><p>удаление дерева.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Объектам-потомкам msRTCSIP-Server</p></td>
<td><p>Особый доступ на:</p>
<ul>
<li><p>запись свойства;</p></li>
<li><p>чтение свойства;</p></li>
<li><p>удаление дерева.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Объектам-потомкам msRTCSIP-WebComponents</p></td>
<td><p>Особый доступ на:</p>
<ul>
<li><p>запись свойства;</p></li>
<li><p>чтение свойства;</p></li>
<li><p>удаление дерева.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Объектам-потомкам msRTCSIP-MCU</p></td>
<td><p>Особый доступ на:</p>
<ul>
<li><p>запись свойства;</p></li>
<li><p>чтение свойства;</p></li>
<li><p>удаление дерева.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Объектам-потомкам msRTCSIP-MediationServer</p></td>
<td><p>Особый доступ на:</p>
<ul>
<li><p>запись свойства;</p></li>
<li><p>чтение свойства;</p></li>
<li><p>удаление дерева.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Объектам-потомкам msRTCSIP-ApplicationServer</p></td>
<td><p>Особый доступ на:</p>
<ul>
<li><p>запись свойства;</p></li>
<li><p>чтение свойства;</p></li>
<li><p>удаление дерева.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Объектам-потомкам msRTCSIP-ConnectionPoint</p></td>
<td><p>Особый доступ на:</p>
<ul>
<li><p>запись свойства;</p></li>
<li><p>чтение свойства;</p></li>
<li><p>удаление дерева.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Объектам-потомкам Computer</p></td>
<td><p>Особый доступ для serviceConnectionPoint на:</p>
<ul>
<li><p>создание дочерних объектов;</p></li>
<li><p>удаление дочерних объектов;</p></li>
<li><p>удаление дерева.</p></li>
</ul>
<p>Специальный доступ для общедоступных сведений на:</p>
<ul>
<li><p>чтение свойства.</p></li>
</ul>
<p>Специальный доступ для имени узла DNS на:</p>
<ul>
<li><p>чтение свойства.</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

