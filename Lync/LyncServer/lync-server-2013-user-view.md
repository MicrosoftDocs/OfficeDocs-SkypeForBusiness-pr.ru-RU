---
title: 'Lync Server 2013: представление пользователя'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User view
ms:assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688100(v=OCS.15)
ms:contentKeyID: 49733699
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f978b6acaa1cdfdf6abf2d768c1fb679af260a63
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530156"
---
# <a name="user-view-in-lync-server-2013"></a>Пользовательское представление в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-01_

Представление User хранит информацию о пользователях, участвовавших в звонках или сеансах с записями в базе данных. Это представление было представлено в Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Тип данных</th>
<th>Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UserId</p></td>
<td><p>int</p></td>
<td><p>Уникальный номер, идентифицирующий этого пользователя.</p></td>
</tr>
<tr class="even">
<td><p>UserUri</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI пользователя.</p></td>
</tr>
<tr class="odd">
<td><p>тенанткэй</p></td>
<td><p>идентификатора</p></td>
<td><p>Клиент пользователя. Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>уритипе</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Тип URI пользователя. Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

