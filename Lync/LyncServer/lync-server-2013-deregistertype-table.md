---
title: 'Lync Server 2013: таблица таблица deregistertype'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DeRegisterType table
ms:assetid: 09148118-6209-4fd7-a494-99118689a245
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398142(v=OCS.15)
ms:contentKeyID: 48183346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c4aa5ea27cdf86d9c8e0c0cdf7260b20cca4478
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498966"
---
# <a name="deregistertype-table-in-lync-server-2013"></a>Таблица Таблица deregistertype в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-28_

Таблица DeRegisterType — это статическая таблица, в которой хранится список возможных типов отмены регистрации пользователей, например «Инициируется клиентом», «Срок действия регистрации истек», «Клиент перестал отвечать».


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
<td><p><strong>дерегистертипеид</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>дерегистерреасон</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>Допустимые значения:</p>
<ul>
<li><p>0 — неизвестно</p></li>
<li><p>1 — клиент инициировал отмену регистрации</p></li>
<li><p>2 — срок действия регистрации истек</p></li>
<li><p>3 — аварийное завершение клиента</p></li>
<li><p>4 — атрибуты пользователя изменены</p></li>
<li><p>5 — предпочтительный регистратор изменен</p></li>
<li><p>6 — устаревший клиент в режиме сохранения</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

