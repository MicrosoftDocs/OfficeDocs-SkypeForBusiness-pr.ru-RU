---
title: 'Lync Server 2013: таблица диалоговых окон'
description: 'Lync Server 2013: таблица диалогов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dialogs table
ms:assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425954(v=OCS.15)
ms:contentKeyID: 48184001
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c2c9cf9ec59fc48f7f5ffc6232980e3f8aa68c1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559705"
---
# <a name="dialogs-table-in-lync-server-2013"></a>Таблица диалогов в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-28_

Таблица диалоговых окон это вспомогательная таблица, в которой хранятся сведения о Диалогидс для одноранговых сеансов.


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
<td><p><strong>сессионидтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>Время запроса сеанса; используется совместно с Сессионидсек для уникальной идентификации сеанса.</p></td>
</tr>
<tr class="even">
<td><p><strong>сессионидсек</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Идентификатор сеанса. Используется совместно с Сессионидтиме для уникальной идентификации сеанса.</p></td>
</tr>
<tr class="odd">
<td><p><strong>екстерналчекксум</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Контрольная сумма Екстерналид. Это поле используется для увеличения скорости поиска в базе данных.</p></td>
</tr>
<tr class="even">
<td><p><strong>екстерналид</strong></p></td>
<td><p>varbinary (775)</p></td>
<td><p> </p></td>
<td><p>ИДЕНТИФИКАТОР диалогового окна SIP, сохраненный в виде двоичного файла. Двоичный формат:</p>
<p>диалоговое окно; from — Tag; to – Tag</p>
<p>Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:</p>
<p><code>cast(cast(ExternalId as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

