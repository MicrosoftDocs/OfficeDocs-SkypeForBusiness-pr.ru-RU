---
title: 'Lync Server 2013: таблица Пуржесеттингс (QoE)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PurgeSettings table (QoE)
ms:assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204788(v=OCS.15)
ms:contentKeyID: 48183777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3cc227d11ee723acb5a49c50d5b8d4d7e819062
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-qoe-in-lync-server-2013"></a>Пуржесеттингс Table (QoE) в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-02_

В таблице Пуржесеттингс содержатся сведения о том, что (и когда) устаревшие записи качества обслуживания будут автоматически удалены из базы данных QoE. Обратите внимание, что в командной консоли Microsoft Lync Server 2013 также можно получить сведения об очистке, выполнив следующую команду:

    Get-CsQoEConfiguration

Эта таблица введена в Microsoft Lync Server 2013.


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
<td><p><strong>ID</strong></p></td>
<td><p>целое</p></td>
<td><p>Primary</p></td>
<td><p>Уникальный идентификатор коллекции параметров очистки QoE.</p></td>
</tr>
<tr class="even">
<td><p><strong>Енаблепурже</strong></p></td>
<td><p>бит</p></td>
<td></td>
<td><p>Если установлено значение true (1), Microsoft Lync Server 2013 будет периодически очищать устаревшие записи из базы данных QoE. Очистка будет выполняться каждый день в томе, указанном в параметре Пуржехаур. Если для этого свойства задано значение false (0), записи не будут автоматически удалены из базы данных. По умолчанию используется значение True.</p></td>
</tr>
<tr class="odd">
<td><p><strong>KeepQoEDataForDays</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Указывает возраст QoE записей (в днях), которые будут очищены из базы данных: Если включена очистка, QoE записи, возраст которых превышает это значение, будут удалены из базы данных. Значение по умолчанию — 60 дней.</p></td>
</tr>
<tr class="even">
<td><p><strong>Пуржехаур</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Указывает местное время суток, когда будет выполняться очистка базы данных. Время суток задается в 24-часовом формате (0 соответствует полуночи (00:00), а 23 — 23:00 часам вечера). Обратите внимание, что вы можете указать только час дня: значение 10 (указывает на 10:00 AM) разрешено, но значение 10:30 от 10,5 (это означает 10:30 AM) не разрешено. Значение по умолчанию — 1 (1:00 AM). Указывает местное время суток, когда будет выполняться очистка базы данных. Время суток задается в 24-часовом формате (0 соответствует полуночи (00:00), а 23 — 23:00 часам вечера). Обратите внимание, что вы можете указать только час дня: значение 10 (указывает на 10:00 AM) разрешено, но значение 10:30 от 10,5 (это означает 10:30 AM) не разрешено. Значение по умолчанию — 1 (1:00 AM).</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

