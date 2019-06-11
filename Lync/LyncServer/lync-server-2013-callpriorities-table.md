---
title: 'Lync Server 2013: таблица SessionCorrelation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: CallPriorities table
ms:assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398093(v=OCS.15)
ms:contentKeyID: 48183275
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fdf08f1dfa8cd04b29f6edb6604a57ab5ec9e822
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841691"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="callpriorities-table-in-lync-server-2013"></a>Таблица SessionCorrelation в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-28_

Таблица Каллприоритиес — это статическая таблица, в которой хранится список возможных приоритетов звонков, например "экстренная", "срочно" или "Обычная".


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
<td><p><strong>Приоритид</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>Priority</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td></td>
<td><p>Допустимые значения:</p>
<ul>
<li><p>0 — неизвестно</p></li>
<li><p>1 — не срочно</p></li>
<li><p>2-обычный</p></li>
<li><p>3-Срочный</p></li>
<li><p>4-экстренная ситуация</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

