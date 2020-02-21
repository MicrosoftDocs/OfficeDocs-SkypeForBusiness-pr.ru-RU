---
title: 'Lync Server 2013: Тблфилетокен'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblFileToken
ms:assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558646(v=OCS.15)
ms:contentKeyID: 48184073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23240588fae3895c7d4aa5b0ecbf642bd2db51a5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208115"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblfiletoken-in-lync-server-2013"></a>Тблфилетокен в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-12_

Таблица tblFileToken содержит временные маркеры для передачи файлов.

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
<td><p>филетокен</p></td>
<td><p>nvarchar (50), NOT NULL</p></td>
<td><p>Уникальный маркер (GUID).</p></td>
</tr>
<tr class="even">
<td><p>филетокенусерид</p></td>
<td><p>int, NOT NULL</p></td>
<td><p>Идентификатор субъекта, который передает файл.</p></td>
</tr>
<tr class="odd">
<td><p>филетокенчаннелид</p></td>
<td><p>GUID, не NULL</p></td>
<td><p>GUID узла комнаты чата.</p></td>
</tr>
<tr class="even">
<td><p>филетокенекспиредате</p></td>
<td><p>datetime, NOT NULL</p></td>
<td><p>Срок действия. (Срок действия маркеров истекает через 30 минут, если они не были закреплены; см. описания в этом столбце.)</p></td>
</tr>
<tr class="odd">
<td><p>филетокенкомплианцефилеурл</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>URL-адрес переданного файла (для использования службой соответствия).</p></td>
</tr>
<tr class="even">
<td><p>филетокенкомплианцесумбнаилурл</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>URL-адрес эскиза переданного файла (для использования службой соответствия).</p></td>
</tr>
<tr class="odd">
<td><p>филетокенкомплианцетиме</p></td>
<td><p>datetime2</p></td>
<td><p>Метка времени для фактической операции передачи файла (для использования службой соответствия).</p></td>
</tr>
<tr class="even">
<td><p>филетокенкомплианцеисуплоад</p></td>
<td><p>Битовая</p></td>
<td><p>True при отправке; False при загрузке (для использования службой соответствия).</p></td>
</tr>
<tr class="odd">
<td><p>филетокенкомплианцепиннед</p></td>
<td><p>bit, NOT NULL</p></td>
<td><p>True, если маркер закреплен. Используется для сохранения маркера в таблице, пока служба соответствия не получит возможность извлечь из него соответствующие поля.</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>Keys

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
<td><p>филетокен</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
<tr class="even">
<td><p>филетокенчаннелид</p></td>
<td><p>Внешний ключ для поиска в таблице tblNode.nodeGuid.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

