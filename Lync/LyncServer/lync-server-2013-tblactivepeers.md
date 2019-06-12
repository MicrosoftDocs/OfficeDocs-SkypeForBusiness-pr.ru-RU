---
title: 'Lync Server 2013: tblActivePeers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblActivePeers
ms:assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615030(v=OCS.15)
ms:contentKeyID: 48185176
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceb6089cfa3f3a9da8103dd0d0691031dac05d05
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblactivepeers-in-lync-server-2013"></a>tblActivePeers в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-06-29_

Тблактивепирс включает в себя текущие одноранговые соединения между службами чата.

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
<td><p>Аплсерверид</p></td>
<td><p>int, NOT NULL</p></td>
<td><p>Идентификатор сервера, на котором размещена запись.</p></td>
</tr>
<tr class="even">
<td><p>Аплпирид</p></td>
<td><p>int, NOT NULL</p></td>
<td><p>Идентификатор однорангового узла, к которому подключен сервер публикации.</p></td>
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
<td><p>&lt;Аплсерверид, Аплпирид&gt;</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
<tr class="even">
<td><p>Аплсерверид</p></td>
<td><p>Внешний ключ с подстановкой в таблице Тблсерверидентити. Серверид.</p></td>
</tr>
<tr class="odd">
<td><p>Аплпирид</p></td>
<td><p>Внешний ключ с подстановкой в таблице Тблсерверидентити. Серверид.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

