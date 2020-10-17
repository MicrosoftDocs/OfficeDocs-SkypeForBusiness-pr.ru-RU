---
title: 'Lync Server 2013: представление UserAgent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgent view
ms:assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721862(v=OCS.15)
ms:contentKeyID: 49733795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb9e70635fc4c54448f6fe3f549d3d6853612070
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530126"
---
# <a name="useragent-view-in-lync-server-2013"></a>Представление UserAgent в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-03_

В представлении UserAgent хранятся сведения об агентах пользователей, участвовавших в сеансах, для которых в базе данных есть соответствующие записи. Это представление было представлено в Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Тип данных</th>
<th>Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>усераженткэй</p></td>
<td><p>int</p></td>
<td><p>Уникальное число, идентифицирующее этот агент пользователя.</p></td>
</tr>
<tr class="even">
<td><p>UserAgent</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Строка агента пользователя.</p></td>
</tr>
<tr class="odd">
<td><p>UAType</p></td>
<td><p>smallint</p></td>
<td><p>Тип агента пользователя. Дополнительные сведения см. <a href="lync-server-2013-useragent-table.md">в таблице UserAgent в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>уакатегори</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Категория, к которой принадлежит агент пользователя. Например, агент пользователя Conferencing_Attendant_1.0 принадлежит UACategory CAA.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

