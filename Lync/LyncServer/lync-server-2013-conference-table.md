---
title: 'Lync Server 2013: таблица конференций'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference table
ms:assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425762(v=OCS.15)
ms:contentKeyID: 48183700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf7b6627f6976001bdb1440db9aa40c33d89cfc7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204445"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-table-in-lync-server-2013"></a>Таблица конференций в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-02_

Таблица Conference является вспомогательной. Каждая запись представляет одну конференцию или одноранговый сеанс.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Column</strong></th>
<th><strong>Тип данных</strong></th>
<th><strong>Ключ или индекс</strong></th>
<th><strong>Details</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>конференцекэй</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Уникальный номер, идентифицирующий эту запись конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>конфури</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>уникальный</p></td>
<td><p>URI для конференции или DialogID для однорангового сеанса.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Контрольная сумма</strong></p></td>
<td><p>int</p></td>
<td><p>index</p></td>
<td><p>Контрольная сумма URI конференции, предназначена для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>некступдатетс</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Только для внутреннего использования.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

