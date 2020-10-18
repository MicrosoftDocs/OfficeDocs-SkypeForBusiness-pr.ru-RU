---
title: 'Lync Server 2013: таблица таблица appliedbandwidthsource'
description: 'Lync Server 2013: таблица таблица appliedbandwidthsource.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppliedBandwidthSource table
ms:assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425725(v=OCS.15)
ms:contentKeyID: 48183638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dc22d3a978a99cb13317e2a32fdb65382ce106c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573505"
---
# <a name="appliedbandwidthsource-table-in-lync-server-2013"></a>Таблица Таблица appliedbandwidthsource в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-02_

Таблица AppliedBandwidthSource является вспомогательной. Каждая запись представляет один источник.


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
<td><p><strong>апплиедбандвидссаурцекэй</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Уникальный номер, определяющий источник.</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthSource</strong></p></td>
<td><p>varchar (256)</p></td>
<td><p>Уникальные</p></td>
<td><p>Источник применяемого ограничения пропускной способности. Описывает, откуда происходит ограничение (например, "Сервер политик", "Сервер TURN" или "Модальность").</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

