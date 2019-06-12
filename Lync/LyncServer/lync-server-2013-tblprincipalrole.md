---
title: 'Lync Server 2013: tblPrincipalRole'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalRole
ms:assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615039(v=OCS.15)
ms:contentKeyID: 48185597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 560f454531060a8458c8c920a1e4c5921867f3e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalrole-in-lync-server-2013"></a>tblPrincipalRole в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-12_

ТблпринЦипалроле включает явные роли, назначенные узлам.

### <a name="columns"></a>Столбцов

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
<td><p>Принроленодеид</p></td>
<td><p>int, NOT NULL</p></td>
<td><p>Идентификатор узла, к которому относится роль.</p></td>
</tr>
<tr class="even">
<td><p>Принролепринид</p></td>
<td><p>int, NOT NULL</p></td>
<td><p>Идентификатор участника.</p></td>
</tr>
<tr class="odd">
<td><p>Принролетипеид</p></td>
<td><p>int, NOT NULL</p></td>
<td><p>Идентификатор типа роли (из Тблролетипе).</p></td>
</tr>
<tr class="even">
<td><p>Принролеупдатедби</p></td>
<td><p>int, NOT NULL</p></td>
<td><p>Идентификатор участника, который последним обновил эту запись.</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>Параметры

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
<td><p>Первичный ключ.</p></td>
</tr>
<tr class="even">
<td><p>Принроленодеид</p></td>
<td><p>Внешний ключ с подстановкой в таблице Тблноде. Нодеид.</p></td>
</tr>
<tr class="odd">
<td><p>Принролепринид</p></td>
<td><p>Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.</p></td>
</tr>
<tr class="even">
<td><p>Принролетипеид</p></td>
<td><p>Внешний ключ с подстановкой в таблице Тблролетипе. Ртипеид.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

