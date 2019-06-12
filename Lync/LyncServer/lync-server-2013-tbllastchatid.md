---
title: 'Lync Server 2013: tblLastChatId'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblLastChatId
ms:assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558616(v=OCS.15)
ms:contentKeyID: 48183513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bddc89952b544a71c469538cf11f65658e19e38d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbllastchatid-in-lync-server-2013"></a>tblLastChatId в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-12_

Тблластчатид включает последний идентификатор чата, который был создан (и использован в таблице Тблчат) для каждого пользователя.

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
<td><p>Нодеид</p></td>
<td><p>int, NOT NULL</p></td>
<td><p>Идентификатор узла (комната чата — только тип).</p></td>
</tr>
<tr class="even">
<td><p>Ластчатид</p></td>
<td><p>bigint, NOT NULL</p></td>
<td><p>НОМЕР последнего использованного чата.</p></td>
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
<td><p>&lt;Нодеид, Ластчатид&gt;</p></td>
<td><p>Первичный ключ (для обработки достаточно просто Нодеид).</p></td>
</tr>
<tr class="even">
<td><p>Нодеид</p></td>
<td><p>Внешний ключ с подстановкой в таблице Тблноде. Нодеид.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>См. также


[tblChat в Lync Server 2013](lync-server-2013-tblchat.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

