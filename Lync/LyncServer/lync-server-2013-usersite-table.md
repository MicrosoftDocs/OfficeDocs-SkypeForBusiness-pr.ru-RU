---
title: 'Lync Server 2013: таблица таблица usersite'
description: 'Lync Server 2013: таблица таблица usersite.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserSite table
ms:assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398256(v=OCS.15)
ms:contentKeyID: 48183552
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e0fb3149b9378bbfd3f14da8176eed226e4f57f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548625"
---
# <a name="usersite-table-in-lync-server-2013"></a>Таблица Таблица usersite в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2010-11-09_

Таблица Таблица usersite является вспомогательной таблицей. Каждая запись представляет один сайт пользователя, определенный в параметрах конфигурации сети.


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
<td><p><strong>усерситекэй</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Уникальный номер, идентифицирующий сайт пользователя.</p></td>
</tr>
<tr class="even">
<td><p><strong>усерситенаме</strong></p></td>
<td><p>nvarchar(128</p></td>
<td><p>Уникальные</p></td>
<td><p>Имя сайта пользователя.</p></td>
</tr>
<tr class="odd">
<td><p><strong>регионкэй</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Ссылка из <a href="lync-server-2013-region-table.md">таблицы Region в Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

