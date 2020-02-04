---
title: 'Lync Server 2013: tblComplianceParticipant'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceParticipant
ms:assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558655(v=OCS.15)
ms:contentKeyID: 48184262
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 484948a01c82dc8ca256e3e50e484c94a9b81de4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcomplianceparticipant-in-lync-server-2013"></a>tblComplianceParticipant в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-12_

ТблкомплианцепартиЦипант включает текущих участников на канал и на сервер.

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
<td><p>чаннелури</p></td>
<td><p>nvarchar (255), NOT NULL</p></td>
<td><p>Универсальный код ресурса (URI) канала.</p></td>
</tr>
<tr class="even">
<td><p>Идентификатора пользователя</p></td>
<td><p>int, NOT NULL</p></td>
<td><p>Идентификатор участника (соответствующий таблице ТблпринЦипал. Принид).</p></td>
</tr>
<tr class="odd">
<td><p>жоинедат</p></td>
<td><p>bigint, NOT NULL</p></td>
<td><p>Метка времени присоединения к событию.</p></td>
</tr>
<tr class="even">
<td><p>партедат</p></td>
<td><p>bigint</p></td>
<td><p>NULL, если участник все еще присоединен. Метка времени события выхода канала, если значение не равно null.</p>
<p>Эти записи в конечном итоге удаляются, когда все переводчики обрабатывают событие.</p></td>
</tr>
<tr class="odd">
<td><p>усерури</p></td>
<td><p>nvarchar (255), NOT NULL</p></td>
<td><p>URI пользователя.</p></td>
</tr>
<tr class="even">
<td><p>серверид</p></td>
<td><p>целое</p></td>
<td><p>Идентификация сервера (как в таблице Тблсерверидентити. Серверид).</p></td>
</tr>
<tr class="odd">
<td><p>Идентификатор</p></td>
<td><p>bigint</p></td>
<td><p>Сеанс сервера. Это случайное число, которое генерируется каждый раз, когда запускается служба чата. Она используется для различения сеансов в целях идентификации потерянных участников.</p></td>
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
<td><p>&lt;Чаннелури, userId, Жоинедат&gt;</p></td>
<td><p>Первичный ключ.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

