---
title: 'Lync Server 2013: представление UserAgent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserAgent view
ms:assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721862(v=OCS.15)
ms:contentKeyID: 49733795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f7d4cf6d79bdd69b28fb88f9a7d6c6a2095ba99
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849285"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragent-view-in-lync-server-2013"></a>Представление "UserAgent" в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-03_

В представлении UserAgent хранятся сведения о агентах пользователей, которые были вовлечены в сеансы с записями в базе данных. Это представление было представлено в Microsoft Lync Server 2013.


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
<th>Подробности</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Усераженткэй</p></td>
<td><p>целое</p></td>
<td><p>Уникальный номер, идентифицирующий агент пользователя.</p></td>
</tr>
<tr class="even">
<td><p>UserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Строка агента пользователя.</p></td>
</tr>
<tr class="odd">
<td><p>Уатипе</p></td>
<td><p>smallint</p></td>
<td><p>Тип агента пользователя. Дополнительные сведения приведены <a href="lync-server-2013-useragent-table.md">в таблице UserAgent в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>Уакатегори</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Категория, к которой принадлежит агент пользователя. Например, агент пользователя КонференЦинг_аттендант_ 1.0 принадлежит к Уакатегори Каа.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

