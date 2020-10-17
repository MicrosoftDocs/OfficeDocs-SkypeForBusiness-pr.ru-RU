---
title: 'Lync Server 2013: таблица MCUs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mcus table
ms:assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425742(v=OCS.15)
ms:contentKeyID: 48183674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 696a32ec4329b06c67dc8c54ba3ff2c1f15486d5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524666"
---
# <a name="mcus-table-in-lync-server-2013"></a>Таблица MCUs в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-28_

Таблица MCUs является вспомогательной таблицей. Каждая запись содержит сведения об одной службе конференц-связи. Они могут включать службу конференц-связи для обмена мгновенными сообщениями и службу конференц-связи, выполняемую как процессы на интерфейсных серверах, а также службу веб-конференций и службу аудио-и видеоконференций.


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
<td><p><strong>мкуид</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Уникальный номер, идентифицирующий этот сервер конференц-связи.</p></td>
</tr>
<tr class="even">
<td><p><strong>мкуури</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><strong>мкутипеид</strong></p></td>
<td><p>ининт</p></td>
<td><p> Правительства</p></td>
<td><p>Тип сервера конференций, например conf: Chat (для мгновенных сообщений) или conf: Audio-Video. Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

