---
title: 'Lync Server 2013: таблица таблица purgesettings'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PurgeSettings table
ms:assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205121(v=OCS.15)
ms:contentKeyID: 48184932
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32522f0818b95e829bbb643dea8749e2f91d1f31
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045831"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-in-lync-server-2013"></a>Таблица Таблица purgesettings в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-28_

Таблица параметров очистки PurgeSettings содержит сведения, указывающие, следует ли автоматически удалять устаревшие записи регистрации вызовов из базы данных CDR, и когда это следует делать. Обратите внимание, что сведения об очистке можно также получить в командной консоли Microsoft Lync Server 2013, выполнив следующую команду:

    Get-CsCdrConfiguration

Администраторы должны рассматривать таблицу таблица purgesettings как доступную только для чтения: изменения параметров очистки сведений о вызовах следует вносить только с помощью командлетов [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) и [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) .

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
<th>Столбец</th>
<th>Тип данных</th>
<th>Ключ или индекс</th>
<th>Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Id</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Уникальный идентификатор для набора параметров очистки CDR.</p></td>
</tr>
<tr class="even">
<td><p><strong>енаблепурже</strong></p></td>
<td><p>Битовая</p></td>
<td></td>
<td><p>Если для этого параметра задано значение true (1), Microsoft Lync Server 2013 будет периодически очищать устаревшие записи из базы данных CDR. Очистка будет происходить каждый день во время, установленное с помощью параметра PurgeHour. Если задано значение False (0), записи не будут очищаться автоматически. Значение по умолчанию — True.</p></td>
</tr>
<tr class="odd">
<td><p><strong>кипкаллдетаилфордайс</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Задает возраст записей CDR (в днях), которые будут удаляться из базы данных: если очистка включена, то все записи, возраст которых больше указанного, будут удаляться из базы данных. Значение по умолчанию — 60 дней.</p></td>
</tr>
<tr class="even">
<td><p><strong>киперроррепортфордайс</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Задает возраст записей отчета об ошибках (в днях), которые будут удаляться из базы данных: если очистка включена, то все записи отчета об ошибках, возраст которых больше указанного, будут удаляться из базы данных. Значение по умолчанию — 60 дней.</p></td>
</tr>
<tr class="odd">
<td><p><strong>пуржехаур</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Задает местное время суток, когда будет выполняться очистка базы данных. Время суток указывается в 24-часовом формате, где 0 соответствует полуночи, а 23 соответствует 11 часам вечера. Обратите внимание, что можно указывать только часы: значение 10 (задающее 10 утра) разрешено, а значение 10:30 (задающее 10:30 утра) не разрешено. Значение по умолчанию - 2 (2:00 ночи).</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

