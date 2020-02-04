---
title: 'Lync Server 2013: таблица Users'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Users table
ms:assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412791(v=OCS.15)
ms:contentKeyID: 48185032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2be643f8a593af01ee47ad93d3910d44ee86e48
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="users-table-in-lync-server-2013"></a>Таблица Users в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-28_

Таблица Users является вспомогательной таблицей. В каждой записи в таблице хранятся сведения о пользователях, участвующих в звонках или сеансах с записями в базе данных.


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
<td><p><strong>некступдатетс</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Метка времени для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p><strong>Идентификатора пользователя</strong></p></td>
<td><p>целое</p></td>
<td><p>Primary</p></td>
<td><p>Уникальный номер, идентифицирующий этого пользователя.</p></td>
</tr>
<tr class="odd">
<td><p><strong>усерури</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p> </p></td>
<td><p>URI пользователя.</p></td>
</tr>
<tr class="even">
<td><p><strong>TenantId</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Идентификатор клиента этого пользователя. Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>уритипеид</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Тип универсального кода ресурса (URI) этого пользователя. Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

