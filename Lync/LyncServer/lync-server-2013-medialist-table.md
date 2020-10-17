---
title: 'Lync Server 2013: таблица таблица medialist'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaList table
ms:assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398279(v=OCS.15)
ms:contentKeyID: 48183579
ms.date: 07/12/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a22ef9b9e0ef429fcac96a7f7d5c87093f79a02
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505726"
---
# <a name="medialist-table-in-lync-server-2013"></a>Таблица Таблица medialist в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2016-07-12_

Таблица MediaList — это статическая таблица, в которой хранится список различных типов мультимедиа.


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
<td><p><strong>медиаид</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p>Значения: 1-7</p></td>
</tr>
<tr class="even">
<td><p><strong>Media</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>Статическое сопоставление значений Медиаид и мультимедиа:</p>
<ul>
<li><p>1 — ОБМЕН МГНОВЕННЫМИ СООБЩЕНИЯМИ</p></li>
<li><p>2 — передача файла</p></li>
<li><p>3 — удаленный помощник</p></li>
<li><p>4 — совместный доступ к приложению</p></li>
<li><p>5 — звук</p></li>
<li><p>6 — видео</p></li>
<li><p>7 — приглашение из приложения</p></li>
</ul></td>
</tr>
</tbody>
</table>


Если вы пытаетесь определить тип модальности для значений в LcsCDR. SessionDetailsView. MediaTypes, необходимо использовать следующий фрагмент соединения:

    LEFT JOIN on Media.MediaId = MediaList.MediaId

</div>

<span> </span>

</div>

</div>

</div>

