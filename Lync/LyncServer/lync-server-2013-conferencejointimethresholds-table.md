---
title: 'Lync Server 2013: таблица таблица conferencejointimethresholds'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceJoinTimeThresholds table
ms:assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204809(v=OCS.15)
ms:contentKeyID: 48183855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d6ce43adee4c00a945325cf31c4194816e7ee14
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190311"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a>Таблица Таблица conferencejointimethresholds в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-28_

Таблица ConferenceJoinTimeThresholds содержит границы классификации, которые используются в сводном отчете о времени присоединения к к конференции. В данном отчете представлены сводные данные о времени, которое требуется для пользователей на успешное присоединение к конференции. Приводятся как средние значения, так и значения в одной из следующих категорий:

  - менее 2 секунд;

  - от 2 до 5 секунд;

  - от 5 до 10 секунд;

  - более 10 секунд.

Таблица ConferenceJoinTimeThresholds содержит значения классификации для 2 секунд, 5 секунд и 10 секунд.

Эта таблица была введена в Microsoft Lync Server 2013.


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
<td><p><strong>срешолдид</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Уникальный идентификатор для классификации.</p></td>
</tr>
<tr class="even">
<td><p><strong>срешолдвалуе</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Верхняя граница для классификации. Допустимые значения:</p>
<ol>
<li><p>2</p></li>
<li><p>17:00</p></li>
<li><p>10 </p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

