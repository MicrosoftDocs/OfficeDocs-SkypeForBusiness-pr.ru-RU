---
title: 'Lync Server 2013: таблица Пуржесеттингс'
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
ms.openlocfilehash: 56ea95d0ba54a34eaa315ff345efb45cd563700c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747029"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-in-lync-server-2013"></a>Таблица Пуржесеттингс в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-28_

В таблице Пуржесеттингс содержатся сведения о том, что (и когда) устаревшая запись о вызовах будет автоматически удалена из базы данных CDR. Обратите внимание, что в командной консоли Microsoft Lync Server 2013 также можно получить сведения об очистке, выполнив следующую команду:

    Get-CsCdrConfiguration

Администраторы должны рассматривать таблицу Пуржесеттингс как доступную только для чтения: изменения в параметрах очистки сведений о вызовах следует вносить только с помощью командлетов [New-кскдрконфигуратион](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) или [Set-кскдрконфигуратион](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) .

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
<th>Столбец</th>
<th>Тип данных</th>
<th>Ключ/индекс</th>
<th>Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Номер</strong></p></td>
<td><p>целое</p></td>
<td><p>Primary</p></td>
<td><p>Уникальный идентификатор коллекции параметров очистки CDR.</p></td>
</tr>
<tr class="even">
<td><p><strong>енаблепурже</strong></p></td>
<td><p>бит</p></td>
<td></td>
<td><p>Если установлено значение true (1), Microsoft Lync Server 2013 будет периодически очищать устаревшие записи из базы данных CDR. Очистка будет выполняться каждый день в томе, указанном в параметре Пуржехаур. Если для этого свойства задано значение false (0), записи не будут автоматически удалены из базы данных. По умолчанию используется значение True.</p></td>
</tr>
<tr class="odd">
<td><p><strong>KeepCallDetailForDays</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Указывает возраст CDR записей (в днях), которые будут очищены из базы данных: Если включена очистка, CDR записи, возраст которых превышает это значение, будут удалены из базы данных. Значение по умолчанию — 60 дней.</p></td>
</tr>
<tr class="even">
<td><p><strong>KeepErrorReportForDays</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Указывает возраст записей отчета об ошибках (в днях), которые будут очищены из базы данных: Если включена очистка, записи отчета об ошибках старше этого значения будут удалены из базы данных. Значение по умолчанию — 60 дней.</p></td>
</tr>
<tr class="odd">
<td><p><strong>пуржехаур</strong></p></td>
<td><p>целое</p></td>
<td></td>
<td><p>Указывает местное время суток, когда будет выполняться очистка базы данных. Время суток задается в 24-часовом формате (0 соответствует полуночи (00:00), а 23 — 23:00 часам вечера). Обратите внимание, что вы можете указать только час дня: значение 10 (указывает на 10:00 AM) разрешено, но значение 10:30 от 10,5 (это означает 10:30 AM) не разрешено. Значение по умолчанию — 2 часа утра (02:00).</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

