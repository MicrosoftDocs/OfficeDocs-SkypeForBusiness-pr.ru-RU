---
title: 'Lync Server 2013: tblFileToken'
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
ms.openlocfilehash: b469b79e680c202654024d1ac20a55b9929e4b10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblfiletoken-in-lync-server-2013"></a>tblFileToken в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-12_

Тблфилетокен включает временные маркеры для целей обмена файлами.

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
<td><p>филетокен</p></td>
<td><p>nvarchar (50), NOT NULL</p></td>
<td><p>Уникальный маркер (GUID).</p></td>
</tr>
<tr class="even">
<td><p>филетокенусерид</p></td>
<td><p>int, NOT NULL</p></td>
<td><p>Идентификатор участника, который передает файл.</p></td>
</tr>
<tr class="odd">
<td><p>филетокенчаннелид</p></td>
<td><p>GUID, а не NULL</p></td>
<td><p>GUID узла комнаты чата.</p></td>
</tr>
<tr class="even">
<td><p>филетокенекспиредате</p></td>
<td><p>DateTime, NOT NULL</p></td>
<td><p>Время окончания срока действия. (Срок действия токенов истекает через 30 минут, за исключением случаев, когда они закреплены (в этой статье описаны следующие описания).</p></td>
</tr>
<tr class="odd">
<td><p>филетокенкомплианцефилеурл</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>URL-адрес перенесенного файла (для использования службы соответствия требованиям).</p></td>
</tr>
<tr class="even">
<td><p>филетокенкомплианцесумбнаилурл</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>URL-адрес миниатюры перенесенного файла (для использования службой соответствия требованиям).</p></td>
</tr>
<tr class="odd">
<td><p>филетокенкомплианцетиме</p></td>
<td><p>datetime2</p></td>
<td><p>Метка времени для фактической операции передачи файлов (для использования службой соответствия требованиям).</p></td>
</tr>
<tr class="even">
<td><p>филетокенкомплианцеисуплоад</p></td>
<td><p>бит</p></td>
<td><p>Значение true, если отправка; Значение false, если Download (для использования службы соответствия требованиям).</p></td>
</tr>
<tr class="odd">
<td><p>филетокенкомплианцепиннед</p></td>
<td><p>bit, NOT NULL</p></td>
<td><p>Значение true, если маркер закреплен. Она используется для хранения токенов в таблице до тех пор, пока служба соответствия требованиям не сможет получить из нее нужные поля.</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>Параметры

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
<td><p>Внешний ключ с подстановкой в таблице Тблноде. Нодегуид.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

