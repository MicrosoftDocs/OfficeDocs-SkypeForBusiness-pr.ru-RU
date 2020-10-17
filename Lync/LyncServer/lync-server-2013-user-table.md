---
title: 'Lync Server 2013: пользовательская таблица'
description: 'Lync Server 2013: пользовательская таблица.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User table
ms:assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398505(v=OCS.15)
ms:contentKeyID: 48184437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15d1ac08a229f4afea35a2727ef1105a5f24b826
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558905"
---
# <a name="user-table-in-lync-server-2013"></a>Таблица user в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-02_

Таблица User является таблицей поддержки, в которой хранится список разных пользователей, участвовавших в сеансах, записанных в базе данных. Каждая запись в таблице представляет одного пользователя.


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
<td><p><strong>UserKey</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Уникальный номер, идентифицирующий этого пользователя.</p></td>
</tr>
<tr class="even">
<td><p><strong>URI</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Уникальные</p></td>
<td><p>Строка URI.</p></td>
</tr>
<tr class="odd">
<td><p><strong>уритипе</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>1 — неизвестный тип URI.</p>
<p>2 — URI пользователя.</p>
<p>4 — URI конференции.</p>
<p>8 — URI телефона.</p></td>
</tr>
<tr class="even">
<td><p><strong>тенанткэй</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Клиент пользователя, ссылается на таблицу клиентов.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ластпуркаллтиме</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Последняя метка времени, когда пользователь имел аудиовызов плохого качества.</p></td>
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

