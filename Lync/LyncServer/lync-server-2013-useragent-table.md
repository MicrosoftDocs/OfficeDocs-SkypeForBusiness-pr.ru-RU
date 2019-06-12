---
title: 'Lync Server 2013: таблица UserAgent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserAgent table
ms:assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398939(v=OCS.15)
ms:contentKeyID: 48185582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09bb2e3a71f81014bcb08952c03b59c93ac6a62f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849286"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragent-table-in-lync-server-2013"></a>Таблица UserAgent в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-05-25_

Таблица UserAgent является вспомогательной таблицей, в которой хранится список различных агентов пользователей, которые участвовали в сеансах, записанных в базе данных. Каждая запись в таблице представляет одного агента пользователя


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Столбец</strong></th>
<th><strong>Тип данных</strong></th>
<th><strong>Ключ/индекс</strong></th>
<th><strong>Сведения</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Усераженткэй</strong></p></td>
<td><p>целое</p></td>
<td><p>Primary</p></td>
<td><p>Уникальный номер, идентифицирующий агент пользователя.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserAgent</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Повторя</p></td>
<td><p>Строка агента пользователя.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Уатипе</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>1 — сервер исправлений.</p>
<p>2 — это сервер конференц-связи с/V.</p>
<p>4 — Lync.</p>
<p>8 — это IP-телефон.</p>
<p>16 — консоль Live Meeting.</p>
<p>32 — средство проверки развертывания (ДВТ).</p>
<p>64 — Lync на компьютерах Macintosh.</p>
<p>128 – это Office Communications Server 2007 R2.</p>
<p>256 является службой объявлений конференций.</p>
<p>512 — автоматический секретарь конференц-связи.</p>
<p>1024 является приложением группы ответа.</p>
<p>2048 находится за пределами голосового контроля.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

