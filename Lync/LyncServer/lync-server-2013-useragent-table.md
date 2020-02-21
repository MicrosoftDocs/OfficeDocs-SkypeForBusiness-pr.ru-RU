---
title: 'Lync Server 2013: таблица UserAgent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgent table
ms:assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398939(v=OCS.15)
ms:contentKeyID: 48185582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b9abca1aaaff164759f195f8f60de335e279335
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212975"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="useragent-table-in-lync-server-2013"></a>Таблица UserAgent в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-05-25_

Таблица UserAgent это вспомогательная таблица, в которой хранится список различных агентов пользователей, которые участвовали в сеансах, записанных в базе данных. Каждая запись в таблице представляет одного агента пользователя


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
<td><p><strong>усераженткэй</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Уникальное число, идентифицирующее этот агент пользователя.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserAgent</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Уникальные</p></td>
<td><p>Строка агента пользователя.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UAType</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>1 — сервер-посредник.</p>
<p>2 это сервер аудио-и видеоконференций.</p>
<p>4 — Lync.</p>
<p>8 — IP-телефон.</p>
<p>16 — консоль Live Meeting.</p>
<p>32 — средство проверки развертывания (ДВТ).</p>
<p>64 — Lync на компьютерах Macintosh.</p>
<p>128 это Office Communications Server 2007 R2 Attendant.</p>
<p>256 — служба извещений конференц-связи.</p>
<p>512 является автосекретарем конференц-связи.</p>
<p>1024 — приложение группы ответа.</p>
<p>2048 находится за преноски управления голосовой связью.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

