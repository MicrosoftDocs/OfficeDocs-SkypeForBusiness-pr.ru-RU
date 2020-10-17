---
title: 'Lync Server 2013: таблица Нетворкконнектиондетаил'
description: 'Lync Server 2013: таблица Нетворкконнектиондетаил.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: NetworkConnectionDetail table
ms:assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205185(v=OCS.15)
ms:contentKeyID: 48185170
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcd0f429999b6629826a9f9369d154afe3c1af2f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561405"
---
# <a name="networkconnectiondetail-table-in-lync-server-2013"></a>Таблица Нетворкконнектиондетаил в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-02_

В таблице NetworkConnectionDetail сопоставляются типы сетевых подключений с идентификаторами сетевых подключений, используемых в базе данных качества взаимодействия. Эта таблица была введена в Microsoft Lync Server 2013.


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
<td><p><strong>нетворкконнектиондетаилкэй</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p>Уникальный идентификатор типа сетевого подключения.</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkConnectionDetail</strong></p></td>
<td><p>varchar (256)</p></td>
<td><p>Уникальные</p></td>
<td><p>Тип сетевого подключения, который соответствует значению NetworkConnectionDetailKey. Допускаются следующие значения:</p>
<ol>
<li><p>0 — проводное</p></li>
<li><p>1 — беспроводное</p></li>
<li><p>2 — Ethernet</p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

