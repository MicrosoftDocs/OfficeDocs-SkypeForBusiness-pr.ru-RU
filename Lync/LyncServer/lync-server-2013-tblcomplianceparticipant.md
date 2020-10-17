---
title: 'Lync Server 2013: ТблкомплианцепартиЦипант'
description: 'Lync Server 2013: ТблкомплианцепартиЦипант.'
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
ms.openlocfilehash: c1385b0a635f003a72de93f10f72642314ad7ebd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569075"
---
# <a name="tblcomplianceparticipant-in-lync-server-2013"></a>ТблкомплианцепартиЦипант в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-12_

Таблица ComplianceParticipant содержит текущих участников по каналам или по серверам.

### <a name="columns"></a>Столбцы

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
<td><p>nvarchar (255), not null</p></td>
<td><p>Универсальный код ресурса (URI) для канала.</p></td>
</tr>
<tr class="even">
<td><p>userId</p></td>
<td><p>int, not null</p></td>
<td><p>Идентификатор участника (в соответствии с таблицей tblPrincipal.prinID).</p></td>
</tr>
<tr class="odd">
<td><p>жоинедат</p></td>
<td><p>bigint, not null</p></td>
<td><p>Метка времени события присоединения.</p></td>
</tr>
<tr class="even">
<td><p>партедат</p></td>
<td><p>типу</p></td>
<td><p>Null, если участник еще присоединен.Если не null, то метка времени события выхода из канала.</p>
<p>Эти записи в конечном итоге удаляются, когда все переводчики обработают событие.</p></td>
</tr>
<tr class="odd">
<td><p>userUri</p></td>
<td><p>nvarchar(255), not null</p></td>
<td><p>URI пользователя.</p></td>
</tr>
<tr class="even">
<td><p>serverID</p></td>
<td><p>int</p></td>
<td><p>Удостоверение сервера (в соответствии с таблицей tblServerIdentity.serverID).</p></td>
</tr>
<tr class="odd">
<td><p>sessionId</p></td>
<td><p>типу</p></td>
<td><p>Сеанс сервера. Это произвольный номер, который создается каждый раз при запуске службы чата. Он используется, чтобы различать сеансы в целях идентификации потерянных участников.</p></td>
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

