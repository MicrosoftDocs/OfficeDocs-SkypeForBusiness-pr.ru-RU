---
title: 'Lync Server 2013: таблица Ерроркатегори'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ErrorCategory table
ms:assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204675(v=OCS.15)
ms:contentKeyID: 48183425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9bd9cebf26a147b00873c17372eca77f0a11f2d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834207"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorcategory-table-in-lync-server-2013"></a>Таблица Ерроркатегори в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-08-20_

В таблице Ерроркатегори содержится понятное имя для каждого диагностического классификация Microsoft Lync Server 2013. По умолчанию Lync Server 2013 использует следующие классификации:

  - 0 — успех

  - 1 — ожидаемый сбой

  - 2 — непредвиденный сбой

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
<td><p><strong>КодТипа</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p>Уникальный идентификатор для классификации.</p></td>
</tr>
<tr class="even">
<td><p><strong>Имя</strong>.</p></td>
<td><p>nvarchar(256)</p></td>
<td></td>
<td><p>Значение и понятное имя, присвоенное классификации. Допустимые значения:</p>
<ul>
<li><p>0 — успех</p></li>
<li><p>1 — ожидаемый сбой</p></li>
<li><p>2 — непредвиденный сбой</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

