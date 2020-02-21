---
title: 'Lync Server 2013: tblPrincipalInvites'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalInvites
ms:assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558650(v=OCS.15)
ms:contentKeyID: 48184141
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5165adf5b9cb5ddeefe80895217e6b2265784855
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalinvites-in-lync-server-2013"></a>tblPrincipalInvites в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-06-25_

tblPrincipalInvites содержит приглашения для всех подготовленных пользователей для всех узлов с включенным автоматическим приглашением.

### <a name="columns"></a>Columns

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Тип</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>prinID</p></td>
<td><p>int, не равно null</p></td>
<td><p>Код участника</p></td>
</tr>
<tr class="even">
<td><p>инвид</p></td>
<td><p>int, not null</p></td>
<td><p>Уникальный порядковый номер (на код участника), созданный для таблицы tblLastInviteId.</p></td>
</tr>
<tr class="odd">
<td><p>nodeID</p></td>
<td><p>int, не null</p></td>
<td><p>Код узла (только комната чата).</p></td>
</tr>
<tr class="even">
<td><p>креатедон</p></td>
<td><p>datetime, не null</p></td>
<td><p>Время создания.</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>Keys

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;prinID, nodeID&gt;</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
<tr class="even">
<td><p>prinID</p></td>
<td><p>Внешний ключ с подстановкой в таблице tblPrincipal.prinID.</p></td>
</tr>
<tr class="odd">
<td><p>nodeID</p></td>
<td><p>Внешний ключ с подстановкой в таблице tblNode.nodeID.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

