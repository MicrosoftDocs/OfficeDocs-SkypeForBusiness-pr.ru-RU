---
title: 'Lync Server 2013: tblComplianceData'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceData
ms:assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558606(v=OCS.15)
ms:contentKeyID: 48183308
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f159a71469335cfb2af1401e8693802b3c8d1870
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207195"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblcompliancedata-in-lync-server-2013"></a>tblComplianceData в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-12_

tblComplianceData содержит события соответствия нормативным требованиям, которые еще не были обработаны адаптером соответствия.

### <a name="columns"></a>Columns

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Тип</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>кмплевентид</p></td>
<td><p>bigint, not null</p></td>
<td><p>Идентификатор события.</p></td>
</tr>
<tr class="even">
<td><p>ентридате</p></td>
<td><p>smalldatetime, не NULL</p></td>
<td><p>Время вставки (может относиться к далекому будущему для  cmplType=9, так как в этом случае запись является всего лишь заполнителем).</p></td>
</tr>
<tr class="odd">
<td><p>cmplType</p></td>
<td><p>int, not null</p></td>
<td><p>Типа события соответствия нормативным требованиям:</p>
<ul>
<li><p>1: Чат</p></li>
<li><p>2: Ответ на чат</p></li>
<li><p>3: Загрузка файла</p></li>
<li><p>4: Отправка файла</p></li>
<li><p>9: Промежуточная передача файла</p></li>
<li><p>10: Удаление чата (с заменой)</p></li>
<li><p>11: Очистка чата</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>кмплтиме</p></td>
<td><p>bigint, не NULL</p></td>
<td><p>Метка времени для события.</p></td>
</tr>
<tr class="odd">
<td><p>кмплчаннелури</p></td>
<td><p>nvarchar (255), not null</p></td>
<td><p>Универсальный код ресурса (URI) для канала.</p></td>
</tr>
<tr class="even">
<td><p>кмплчатид</p></td>
<td><p>типу</p></td>
<td><p>Идентификатор чата (в соответствии с таблицей tblChat.chatId).</p></td>
</tr>
<tr class="odd">
<td><p>кмплусерид</p></td>
<td><p>int, не NULL</p></td>
<td><p>Идентификатор субъекта для отправителя (в соответствии с таблицей tblPrincipal.prinID).</p></td>
</tr>
<tr class="even">
<td><p>кмплусерури</p></td>
<td><p>nvarchar (255), не NULL</p></td>
<td><p>Универсальный код ресурса (URI) для пользователя.</p></td>
</tr>
<tr class="odd">
<td><p>кмплмессаже</p></td>
<td><p>nvarchar (max)</p></td>
<td><p>Сообщение (кодировка зависит от cmplType).</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>Key

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>кмплевентид</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

