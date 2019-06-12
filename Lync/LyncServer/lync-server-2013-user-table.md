---
title: 'Lync Server 2013: таблица User'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User table
ms:assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398505(v=OCS.15)
ms:contentKeyID: 48184437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4baaf8b8dea0f9e5aa77986791c82051fc00e90b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849287"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-table-in-lync-server-2013"></a>Таблица User в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-02_

Таблица user — это вспомогательная таблица, в которой хранится список различных пользователей, которые участвовали в сеансах, записанных в базе данных. Каждая запись в таблице представляет одного пользователя.


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
<td><p><strong>Усеркэй</strong></p></td>
<td><p>целое</p></td>
<td><p>Primary</p></td>
<td><p>Уникальный номер, идентифицирующий этого пользователя.</p></td>
</tr>
<tr class="even">
<td><p><strong>КОД</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Повторя</p></td>
<td><p>Строка URI.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Уритипе</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>1 — неизвестный тип URI.</p>
<p>2 — это универсальный код ресурса пользователя.</p>
<p>4 — универсальный код ресурса Конференции.</p>
<p>8 — это универсальный код ресурса (URI) телефона.</p></td>
</tr>
<tr class="even">
<td><p><strong>Тенанткэй</strong></p></td>
<td><p>целое</p></td>
<td><p>Другом</p></td>
<td><p>Клиент для пользователя, на который ссылается таблица "клиент".</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ластпуркаллтиме</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Самая поздняя метка времени, когда пользователь приходил к вызову неудовлетворительного звука.</p></td>
</tr>
<tr class="even">
<td><p><strong>Некступдатетс</strong></p></td>
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

