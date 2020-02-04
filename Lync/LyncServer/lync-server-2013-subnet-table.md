---
title: 'Lync Server 2013: таблица Subnet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Subnet table
ms:assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398582(v=OCS.15)
ms:contentKeyID: 48184544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d107889b49ec16c51224b075a8fb7f7a7cec1b00
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731739"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="subnet-table-in-lync-server-2013"></a>Таблица Subnet в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-02_

Таблица подсети является вспомогательной таблицей. Каждая запись соответствует одной подсети, определенной в параметрах конфигурации сети.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Столбец</strong></th>
<th><strong>Тип данных</strong></th>
<th><strong>Ключ/индекс</strong></th>
<th><strong>Сведения</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>субнетип</strong></p></td>
<td><p>целое</p></td>
<td><p>Основной, внешний</p></td>
<td><p>Целочисленное представление для IP-адреса подсети.</p></td>
</tr>
<tr class="even">
<td><p><strong>Сети</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Маска подсети.</p></td>
</tr>
<tr class="odd">
<td><p><strong>усерситекэй</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>На которую ссылается <a href="lync-server-2013-usersite-table.md">Таблица усерсите в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>субнетдескриптион</strong></p></td>
<td><p>nvarchar (512)</p></td>
<td></td>
<td><p>Описание подсети.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

