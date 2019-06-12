---
title: 'Lync Server 2013: tblComplianceData'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblComplianceData
ms:assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558606(v=OCS.15)
ms:contentKeyID: 48183308
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 044a57645a8c49ea74ec4e003f9e12720d0b2268
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849545"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancedata-in-lync-server-2013"></a>tblComplianceData в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-12_

Тблкомплианцедата содержит события соответствия требованиям, которые пока не обрабатывались адаптером соответствия требованиям.

### <a name="columns"></a>Столбцов

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
<td><p>Кмплевентид</p></td>
<td><p>bigint, NOT NULL</p></td>
<td><p>Код события.</p></td>
</tr>
<tr class="even">
<td><p>Ентридате</p></td>
<td><p>smalldatetime, NOT NULL</p></td>
<td><p>Время вставки (может быть в будущем для Кмплтипе = 9, так как в этом случае запись является заполнителем в этом случае).</p></td>
</tr>
<tr class="odd">
<td><p>Кмплтипе</p></td>
<td><p>int, NOT NULL</p></td>
<td><p>Тип события соответствия:</p>
<ul>
<li><p>1: чат</p></li>
<li><p>2: чат</p></li>
<li><p>3: Загрузка файла</p></li>
<li><p>4: Отправка файлов</p></li>
<li><p>9: подготовка к передаче файлов</p></li>
<li><p>10: удаление чата (с заменой)</p></li>
<li><p>11: Очистка чата</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Кмплтиме</p></td>
<td><p>bigint, NOT NULL</p></td>
<td><p>Метка времени для события.</p></td>
</tr>
<tr class="odd">
<td><p>Кмплчаннелури</p></td>
<td><p>nvarchar (255), NOT NULL</p></td>
<td><p>Универсальный код ресурса (URI) канала.</p></td>
</tr>
<tr class="even">
<td><p>Кмплчатид</p></td>
<td><p>bigint</p></td>
<td><p>ИДЕНТИФИКАТОР чата (соответствующая таблице Тблчат. Чатид).</p></td>
</tr>
<tr class="odd">
<td><p>Кмплусерид</p></td>
<td><p>int, NOT NULL</p></td>
<td><p>Идентификатор участника афиши (соответствующий таблице ТблпринЦипал. Принид).</p></td>
</tr>
<tr class="even">
<td><p>Кмплусерури</p></td>
<td><p>nvarchar (255), NOT NULL</p></td>
<td><p>URI пользователя.</p></td>
</tr>
<tr class="odd">
<td><p>Кмплмессаже</p></td>
<td><p>nvarchar (max)</p></td>
<td><p>Сообщение (Кодировка зависит от Кмплтипе).</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>Ключ

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
<td><p>Кмплевентид</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

