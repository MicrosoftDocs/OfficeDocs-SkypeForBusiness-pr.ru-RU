---
title: 'Lync Server 2013: таблица сервера'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server table
ms:assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398801(v=OCS.15)
ms:contentKeyID: 48184890
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d95ca6af9a3e762a39142fcaf754d810050d83d3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200775"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-table-in-lync-server-2013"></a>Таблица Server в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-02_

Таблица Server является таблицей поддержки. Каждая запись в этой таблице представляет один сервер.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Column</strong></th>
<th><strong>Тип данных</strong></th>
<th><strong>Ключ или индекс</strong></th>
<th><strong>Details</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>серверкэй</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Уникальный номер, идентифицирующий сервер.</p></td>
</tr>
<tr class="even">
<td><p><strong>фкднорип</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>index</p></td>
<td><p>Строка MAC-адреса.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerType</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>1: сервер-посредник</p>
<p>2: сервер аудио- и видеоконференций 16394: пограничная служба аудио- и видеосвязи 32769: шлюз</p></td>
</tr>
<tr class="even">
<td><p><strong>пулнаме</strong></p></td>
<td><p>nvarchar (512)</p></td>
<td></td>
<td><p>Пул, которому принадлежит сервер. Применяется только для серверов аудио- и видеоконференций.</p></td>
</tr>
<tr class="odd">
<td><p><strong>некступдатетс</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

