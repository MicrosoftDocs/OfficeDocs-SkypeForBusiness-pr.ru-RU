---
title: 'Lync Server 2013: tblScopePrincipal'
description: 'Lync Server 2013: tblScopePrincipal.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblScopePrincipal
ms:assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558639(v=OCS.15)
ms:contentKeyID: 48184009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63315f8525e5c2f05fe54a0f9ed9e8a97b9e8bce
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555615"
---
# <a name="tblscopeprincipal-in-lync-server-2013"></a>tblScopePrincipal в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-12_

tblScopePrincipal содержит области, назначенные узлам.

### <a name="columns"></a>Столбцы

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
<td><p>скопенодеид</p></td>
<td><p>int, не null</p></td>
<td><p>Код узла, к которой применяется область.</p></td>
</tr>
<tr class="even">
<td><p>скопепринид</p></td>
<td><p>int, не null</p></td>
<td><p>Код участника</p></td>
</tr>
<tr class="odd">
<td><p>скопеисдениед</p></td>
<td><p>bit, не null</p></td>
<td><p>Значение true, если тип области — Deny; значение false, если тип области — Allow.</p></td>
</tr>
<tr class="even">
<td><p>скопеупдатедби</p></td>
<td><p>int, не null</p></td>
<td><p>Код участника, который последним обновил эту запись.</p></td>
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
<td><p>&lt;Скопенодеид, Скопепринид&gt;</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
<tr class="even">
<td><p>скопенодеид</p></td>
<td><p>Внешний ключ с подстановкой в таблице tblNode.nodeID.</p></td>
</tr>
<tr class="odd">
<td><p>скопепринид</p></td>
<td><p>Внешний ключ с подстановкой в таблице tblPrincipal.prinID.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

