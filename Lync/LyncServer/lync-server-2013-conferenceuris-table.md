---
title: 'Lync Server 2013: таблица таблица conferenceuris'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceUris table
ms:assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412854(v=OCS.15)
ms:contentKeyID: 48185160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2215eb030f237e8d238310e6f6b7fe223088c02
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140542"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferenceuris-table-in-lync-server-2013"></a>Таблица Таблица conferenceuris в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-05-25_

ConfereneUris — это вспомогательная таблица, в которой хранится список различных URI конференций, используемых в сеансах конференций, записанных в базе данных. Каждая запись в таблице представляет один URI конференции.


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
<th>Ключ или индекс</th>
<th>Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>некступдатетс</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>Метка времени; для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>конференцеуриид</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Уникальный номер, идентифицирующий этот URI конференции.</p></td>
</tr>
<tr class="odd">
<td><p><strong>конференцеури</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td></td>
<td><p>URI конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>Контрольная сумма</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Контрольная сумма ConferenceUri. Используется для повышения скорости поиска в базе данных.</p></td>
</tr>
<tr class="odd">
<td><p><strong>уритипеид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Тип URI, например conf:chat для конференции обмена мгновенными сообщениями или conf:audio-video для аудио- и видеоконференции. Для получения дополнительных сведений ознакомьтесь со статьей <a href="lync-server-2013-uritypes-table.md">таблица таблица uritypes в таблице Lync Server 2013</a> .</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

