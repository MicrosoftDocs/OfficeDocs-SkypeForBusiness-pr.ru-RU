---
title: 'Lync Server 2013: ТблпринЦипалаффилиатионс'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalAffiliations
ms:assetid: 45fd8484-5837-44d2-85bb-45c83546607c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558642(v=OCS.15)
ms:contentKeyID: 48183993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2900a2ca780cfc239cb7045ea564bbba581f2f55
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142035"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalaffiliations-in-lync-server-2013"></a>ТблпринЦипалаффилиатионс в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-12_

ТблпринЦипалаффилиатионс содержит основные сведения о членстве в расположениях, включая группы безопасности доменных служб Active Directory, в контейнерах Active Directory в доменах.

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
<td><p>принЦипалид</p></td>
<td><p>int, not null</p></td>
<td><p>Идентификатор присоединенного субъекта.</p></td>
</tr>
<tr class="even">
<td><p>аффилиатионид</p></td>
<td><p>int, not null</p></td>
<td><p>Идентификатор субъекта, представляющего присоединение. Каждый субъект (за исключением типов пользователей системы) также присоединен сам к себе.</p></td>
</tr>
<tr class="odd">
<td><p>index</p></td>
<td><p>int, NOT NULL</p></td>
<td><p>Индекса. Значение для самоназначений равно-1, а для других присоединений он последовательно увеличивается от 1 в каждом &lt;сегменте ПринЦипалид, аффилиатионид.&gt;</p></td>
</tr>
<tr class="even">
<td><p>упдатедби</p></td>
<td><p>int, NOT NULL</p></td>
<td><p>Субъект, выполнивший последнее обновление. Обычно это 1, что означает синхронизацию с Active Directory.</p></td>
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
<th>Columns</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;ПринЦипалид, index, Аффилиатионид&gt;</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
<tr class="even">
<td><p>принЦипалид</p></td>
<td><p>Внешний ключ с поиском в таблице tblPrincipal.prinID.</p></td>
</tr>
<tr class="odd">
<td><p>аффилиатионид</p></td>
<td><p>Внешний ключ с поиском в таблице tblPrincipal.prinID.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

