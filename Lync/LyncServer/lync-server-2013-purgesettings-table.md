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

# <a name="purgesettings-table-in-lync-server-2013"></a><span data-ttu-id="bc5ec-102">Таблица Таблица purgesettings в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc5ec-102">PurgeSettings table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc5ec-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="bc5ec-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="bc5ec-104">Таблица параметров очистки PurgeSettings содержит сведения, указывающие, следует ли автоматически удалять устаревшие записи регистрации вызовов из базы данных CDR, и когда это следует делать.</span><span class="sxs-lookup"><span data-stu-id="bc5ec-104">The PurgeSettings table contains information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span> <span data-ttu-id="bc5ec-105">Обратите внимание, что сведения об очистке можно также получить в командной консоли Microsoft Lync Server 2013, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bc5ec-105">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsCdrConfiguration

<span data-ttu-id="bc5ec-106">Администраторы должны рассматривать таблицу таблица purgesettings как доступную только для чтения: изменения параметров очистки сведений о вызовах следует вносить только с помощью командлетов [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) и [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="bc5ec-106">Administrators should treat the PurgeSettings table as read-only: changes to the call detail purge settings should only be made using the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) or [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlets.</span></span>

<span data-ttu-id="bc5ec-107">Эта таблица была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bc5ec-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc5ec-108">Столбец</span><span class="sxs-lookup"><span data-stu-id="bc5ec-108">Column</span></span></th>
<th><span data-ttu-id="bc5ec-109">Тип данных</span><span class="sxs-lookup"><span data-stu-id="bc5ec-109">Data Type</span></span></th>
<th><span data-ttu-id="bc5ec-110">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="bc5ec-110">Key/Index</span></span></th>
<th><span data-ttu-id="bc5ec-111">Сведения</span><span class="sxs-lookup"><span data-stu-id="bc5ec-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc5ec-112"><strong>Id</strong></span><span class="sxs-lookup"><span data-stu-id="bc5ec-112"><strong>Id</strong></span></span></p></td>
<td><p><span data-ttu-id="bc5ec-113">int</span><span class="sxs-lookup"><span data-stu-id="bc5ec-113">int</span></span></p></td>
<td><p><span data-ttu-id="bc5ec-114">Primary</span><span class="sxs-lookup"><span data-stu-id="bc5ec-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="bc5ec-115">Уникальный идентификатор для набора параметров очистки CDR.</span><span class="sxs-lookup"><span data-stu-id="bc5ec-115">Unique identifier for the collection of CDR purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc5ec-116"><strong>енаблепурже</strong></span><span class="sxs-lookup"><span data-stu-id="bc5ec-116"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="bc5ec-117">Битовая</span><span class="sxs-lookup"><span data-stu-id="bc5ec-117">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bc5ec-118">Если для этого параметра задано значение true (1), Microsoft Lync Server 2013 будет периодически очищать устаревшие записи из базы данных CDR.</span><span class="sxs-lookup"><span data-stu-id="bc5ec-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the CDR database.</span></span> <span data-ttu-id="bc5ec-119">Очистка будет происходить каждый день во время, установленное с помощью параметра PurgeHour.</span><span class="sxs-lookup"><span data-stu-id="bc5ec-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="bc5ec-120">Если задано значение False (0), записи не будут очищаться автоматически.</span><span class="sxs-lookup"><span data-stu-id="bc5ec-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="bc5ec-121">Значение по умолчанию — True.</span><span class="sxs-lookup"><span data-stu-id="bc5ec-121">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc5ec-122"><strong>кипкаллдетаилфордайс</strong></span><span class="sxs-lookup"><span data-stu-id="bc5ec-122"><strong>KeepCallDetailForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="bc5ec-123">int</span><span class="sxs-lookup"><span data-stu-id="bc5ec-123">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bc5ec-p103">Задает возраст записей CDR (в днях), которые будут удаляться из базы данных: если очистка включена, то все записи, возраст которых больше указанного, будут удаляться из базы данных. Значение по умолчанию — 60 дней.</span><span class="sxs-lookup"><span data-stu-id="bc5ec-p103">Specifies the age of CDR records (in days) that will be purged from the database: if purging is enabled, CDR records older than this value will be removed from the database. The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc5ec-126"><strong>киперроррепортфордайс</strong></span><span class="sxs-lookup"><span data-stu-id="bc5ec-126"><strong>KeepErrorReportForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="bc5ec-127">int</span><span class="sxs-lookup"><span data-stu-id="bc5ec-127">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bc5ec-p104">Задает возраст записей отчета об ошибках (в днях), которые будут удаляться из базы данных: если очистка включена, то все записи отчета об ошибках, возраст которых больше указанного, будут удаляться из базы данных. Значение по умолчанию — 60 дней.</span><span class="sxs-lookup"><span data-stu-id="bc5ec-p104">Specifies the age of error report records (in days) that will be purged from the database: if purging is enabled, error report records older than this value will be removed from the database. The default value is 60 days.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc5ec-130"><strong>пуржехаур</strong></span><span class="sxs-lookup"><span data-stu-id="bc5ec-130"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="bc5ec-131">int</span><span class="sxs-lookup"><span data-stu-id="bc5ec-131">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bc5ec-p105">Задает местное время суток, когда будет выполняться очистка базы данных. Время суток указывается в 24-часовом формате, где 0 соответствует полуночи, а 23 соответствует 11 часам вечера. Обратите внимание, что можно указывать только часы: значение 10 (задающее 10 утра) разрешено, а значение 10:30 (задающее 10:30 утра) не разрешено. Значение по умолчанию - 2 (2:00 ночи).</span><span class="sxs-lookup"><span data-stu-id="bc5ec-p105">Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 2 (2:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

