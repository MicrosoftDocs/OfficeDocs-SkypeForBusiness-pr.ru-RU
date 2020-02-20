---
title: 'Lync Server 2013: tblPrincipalRole'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalRole
ms:assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615039(v=OCS.15)
ms:contentKeyID: 48185597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4da9525e81856989c5d5046e43b2277ca6a8b2a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141985"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalrole-in-lync-server-2013"></a>tblPrincipalRole в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-12_

tblPrincipalRole содержит явные роли, назначенные узлам.

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
<td><p>принроленодеид</p></td>
<td><p>int, not null</p></td>
<td><p>ИД узла, к которому применяется роль.</p></td>
</tr>
<tr class="even">
<td><p>принролепринид</p></td>
<td><p>int, не равно null</p></td>
<td><p>ИД субъекта.</p></td>
</tr>
<tr class="odd">
<td><p>принролетипеид</p></td>
<td><p>int, not null</p></td>
<td><p>ИД типа роли (из tblRoleType).</p></td>
</tr>
<tr class="even">
<td><p>принролеупдатедби</p></td>
<td><p>int, not null</p></td>
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
<td><p>&lt;Принроленодеид, Принролепринид, Принролетипеид&gt;</p></td>
<td><p>Основной ключ.</p></td>
</tr>
<tr class="even">
<td><p>принроленодеид</p></td>
<td><p>Внешний ключ с поиском в таблице tblNode.nodeID.</p></td>
</tr>
<tr class="odd">
<td><p>принролепринид</p></td>
<td><p>Внешний ключ с поиском в таблице tblPrincipal.prinID.</p></td>
</tr>
<tr class="even">
<td><p>принролетипеид</p></td>
<td><p>Внешний ключ с поиском в таблице tblRoleType.rtypeID.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

