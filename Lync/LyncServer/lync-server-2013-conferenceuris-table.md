---
title: 'Lync Server 2013: таблица ConferenceUris'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceUris table
ms:assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412854(v=OCS.15)
ms:contentKeyID: 48185160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2b1ab44b564d649b6c8fb812077645c6dc13093
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferenceuris-table-in-lync-server-2013"></a>Таблица ConferenceUris в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-05-25_

Таблица Конференеурис является вспомогательной таблицей, в которой хранится список различных URI конференций, участвующих в сеансах конференц-связи, записанных в базу данных. Каждая запись в таблице представляет один URI конференции.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Тип данных</th>
<th>Ключ/индекс</th>
<th>Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Некступдатетс</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>Метка времени, используемая в качестве внутренней.</p></td>
</tr>
<tr class="even">
<td><p><strong>Конференцеуриид</strong></p></td>
<td><p>целое</p></td>
<td><p>Primary</p></td>
<td><p>Уникальный номер, идентифицирующий этот URI конференции.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td></td>
<td><p>Универсальный код ресурса (URI) Конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>Счет</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Контрольная сумма для Конференцеури. Используется для увеличения скорости поиска в базе данных.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Уритипеид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Тип URI, например conf: чат для Конференции с помощью мгновенных сообщений или conf: аудио-видео для голосовой и видеоконференции. Более подробную информацию вы увидите в <a href="lync-server-2013-uritypes-table.md">таблице уритипес в таблице Lync Server 2013</a> .</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

