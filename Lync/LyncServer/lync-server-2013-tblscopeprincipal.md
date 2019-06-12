---
title: 'Lync Server 2013: tblScopePrincipal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblScopePrincipal
ms:assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558639(v=OCS.15)
ms:contentKeyID: 48184009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ece5ae542060835aefa05edb6e08b766293e2ac1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849522"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblscopeprincipal-in-lync-server-2013"></a>tblScopePrincipal в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-12_

ТблскопепринЦипал включает области, назначенные узлам.

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
<td><p>Скопенодеид</p></td>
<td><p>int, NOT NULL</p></td>
<td><p>Идентификатор узла, к которому относится область.</p></td>
</tr>
<tr class="even">
<td><p>Скопепринид</p></td>
<td><p>int, NOT NULL</p></td>
<td><p>Идентификатор участника.</p></td>
</tr>
<tr class="odd">
<td><p>Скопеисдениед</p></td>
<td><p>bit, NOT NULL</p></td>
<td><p>Значение true, если тип области — Deny; Значение false, если разрешено.</p></td>
</tr>
<tr class="even">
<td><p>Скопеупдатедби</p></td>
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
<td><p>&lt;Скопенодеид, Скопепринид&gt;</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
<tr class="even">
<td><p>Скопенодеид</p></td>
<td><p>Внешний ключ с подстановкой в таблице Тблноде. Нодеид.</p></td>
</tr>
<tr class="odd">
<td><p>Скопепринид</p></td>
<td><p>Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

