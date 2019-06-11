---
title: 'Lync Server 2013: таблица Конференцежоинтимесрешолдс'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceJoinTimeThresholds table
ms:assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204809(v=OCS.15)
ms:contentKeyID: 48183855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66793cc3bd545d343198d00f7fb477c1f9b88fac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841489"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a>Таблица Конференцежоинтимесрешолдс в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-28_

В таблице Конференцежоинтимесрешолдс содержатся ограничители классификации, используемые в сводном отчете "время присоединения к Конференции". Сводный отчет о времени присоединения к Конференции суммирует количество времени, необходимого для успешного присоединения пользователей к Конференции; Эти значения времени выводятся как среднее значение и в одной из следующих категорий:

  - Менее 2 секунд.

  - От 2 секунды до 5 секунд.

  - От 5 секунд до 10 секунд.

  - Более 10 секунд.

В таблице Конференцежоинтимесрешолдс содержатся значения классификации 2 секунды, 5 секунд и 10 секунд.

Эта таблица введена в Microsoft Lync Server 2013.


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
<td><p><strong>Срешолдид</strong></p></td>
<td><p>целое</p></td>
<td><p>Primary</p></td>
<td><p>Уникальный идентификатор для классификации.</p></td>
</tr>
<tr class="even">
<td><p><strong>Срешолдвалуе</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Верхний предел для классификации. Допустимые значения:</p>
<ol>
<li><p>2</p></li>
<li><p>5</p></li>
<li><p>5-10</p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

