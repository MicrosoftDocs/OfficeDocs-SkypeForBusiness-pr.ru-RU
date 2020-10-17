---
title: 'Lync Server 2013: таблица таблица purgesettings (QoE)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PurgeSettings table (QoE)
ms:assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204788(v=OCS.15)
ms:contentKeyID: 48183777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac236e08f79adbe1ec7cbe92ea04405de46d0055
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512226"
---
# <a name="purgesettings-table-qoe-in-lync-server-2013"></a>Таблица Таблица purgesettings (QoE) в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-02_

В таблице PurgeSettings содержатся сведения о том, должны ли устаревшие записи автоматически удаляться из базы данных качества обслуживания, и когда это должно происходить. Обратите внимание, что сведения об очистке можно также получить в командной консоли Microsoft Lync Server 2013, выполнив следующую команду:

    Get-CsQoEConfiguration

Эта таблица была введена в Microsoft Lync Server 2013.


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
<td><p><strong>ИД</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Уникальный идентификатор набора параметров, связанных с очисткой записей качества обслуживания.</p></td>
</tr>
<tr class="even">
<td><p><strong>енаблепурже</strong></p></td>
<td><p>Битовая</p></td>
<td></td>
<td><p>Если для этого параметра задано значение true (1), Microsoft Lync Server 2013 будет периодически очищать устаревшие записи из базы данных QoE. Очистка будет происходить каждый день во время, установленное с помощью параметра PurgeHour. Если задано значение False (0), записи не будут очищаться автоматически. Значение по умолчанию — True.</p></td>
</tr>
<tr class="odd">
<td><p><strong>KeepQoEDataForDays</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Определяет возраст записей качества обслуживания (в днях), которые должны очищаться. Если очистка включена, записи старше этого значения будут удаляться из базы данных. Значение по умолчанию — 60 дней.</p></td>
</tr>
<tr class="even">
<td><p><strong>пуржехаур</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Определяет время суток (по местному времени), когда должна выполняться очистка базы данных. Время суток указывается в 24-часовом формате, где 0 означает полночь, а 23 означает 11 часов вечера. Обратите внимание на то, что вы можете указать только час: значение 10 (соответствующее 10:00 утра) допускается, а значение 10:30 или 10.5 (соответствующее 10:30 утра) — нет. Значение по умолчанию — 1 (1:00 ночи). Определяет время суток (по местному времени), когда должна выполняться очистка базы данных. Время суток указывается в 24-часовом формате, где 0 соответствует полуночи, а 23 соответствует 11:00 вечера. Обратите внимание на то, что вы можете указать только час: значение 10 (соответствующее 10:00 утра) допускается, а значение 10:30 или 10.5 (соответствующее 10:30 утра) — нет. Значение по умолчанию — 1 (1:00 ночи).</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

