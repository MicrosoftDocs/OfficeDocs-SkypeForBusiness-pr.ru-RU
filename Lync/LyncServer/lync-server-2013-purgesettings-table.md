---
title: 'Lync Server 2013: таблица Пуржесеттингс'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PurgeSettings table
ms:assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205121(v=OCS.15)
ms:contentKeyID: 48184932
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18b9fc0aa03596677cb73641ed46e86ea133f308
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823772"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-in-lync-server-2013"></a><span data-ttu-id="299c7-102">Таблица Пуржесеттингс в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="299c7-102">PurgeSettings table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="299c7-103">_**Тема последнего изменения:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="299c7-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="299c7-104">В таблице Пуржесеттингс содержатся сведения о том, что (и когда) устаревшая запись о вызовах будет автоматически удалена из базы данных CDR.</span><span class="sxs-lookup"><span data-stu-id="299c7-104">The PurgeSettings table contains information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span> <span data-ttu-id="299c7-105">Обратите внимание, что в командной консоли Microsoft Lync Server 2013 также можно получить сведения об очистке, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="299c7-105">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsCdrConfiguration

<span data-ttu-id="299c7-106">Администраторы должны рассматривать таблицу Пуржесеттингс как доступную только для чтения: изменения в параметрах очистки сведений о вызовах следует вносить только с помощью командлетов [New-кскдрконфигуратион](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) или [Set-кскдрконфигуратион](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="299c7-106">Administrators should treat the PurgeSettings table as read-only: changes to the call detail purge settings should only be made using the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) or [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlets.</span></span>

<span data-ttu-id="299c7-107">Эта таблица введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="299c7-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="299c7-108">Столбец</span><span class="sxs-lookup"><span data-stu-id="299c7-108">Column</span></span></th>
<th><span data-ttu-id="299c7-109">Тип данных</span><span class="sxs-lookup"><span data-stu-id="299c7-109">Data Type</span></span></th>
<th><span data-ttu-id="299c7-110">Ключ/индекс</span><span class="sxs-lookup"><span data-stu-id="299c7-110">Key/Index</span></span></th>
<th><span data-ttu-id="299c7-111">Сведения</span><span class="sxs-lookup"><span data-stu-id="299c7-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="299c7-112"><strong>Номер</strong></span><span class="sxs-lookup"><span data-stu-id="299c7-112"><strong>Id</strong></span></span></p></td>
<td><p><span data-ttu-id="299c7-113">целое</span><span class="sxs-lookup"><span data-stu-id="299c7-113">int</span></span></p></td>
<td><p><span data-ttu-id="299c7-114">Primary</span><span class="sxs-lookup"><span data-stu-id="299c7-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="299c7-115">Уникальный идентификатор коллекции параметров очистки CDR.</span><span class="sxs-lookup"><span data-stu-id="299c7-115">Unique identifier for the collection of CDR purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="299c7-116"><strong>Енаблепурже</strong></span><span class="sxs-lookup"><span data-stu-id="299c7-116"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="299c7-117">бит</span><span class="sxs-lookup"><span data-stu-id="299c7-117">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="299c7-118">Если установлено значение true (1), Microsoft Lync Server 2013 будет периодически очищать устаревшие записи из базы данных CDR.</span><span class="sxs-lookup"><span data-stu-id="299c7-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the CDR database.</span></span> <span data-ttu-id="299c7-119">Очистка будет выполняться каждый день в томе, указанном в параметре Пуржехаур.</span><span class="sxs-lookup"><span data-stu-id="299c7-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="299c7-120">Если для этого свойства задано значение false (0), записи не будут автоматически удалены из базы данных.</span><span class="sxs-lookup"><span data-stu-id="299c7-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="299c7-121">По умолчанию используется значение True.</span><span class="sxs-lookup"><span data-stu-id="299c7-121">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="299c7-122"><strong>KeepCallDetailForDays</strong></span><span class="sxs-lookup"><span data-stu-id="299c7-122"><strong>KeepCallDetailForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="299c7-123">целое</span><span class="sxs-lookup"><span data-stu-id="299c7-123">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="299c7-124">Указывает возраст CDR записей (в днях), которые будут очищены из базы данных: Если включена очистка, CDR записи, возраст которых превышает это значение, будут удалены из базы данных.</span><span class="sxs-lookup"><span data-stu-id="299c7-124">Specifies the age of CDR records (in days) that will be purged from the database: if purging is enabled, CDR records older than this value will be removed from the database.</span></span> <span data-ttu-id="299c7-125">Значение по умолчанию — 60 дней.</span><span class="sxs-lookup"><span data-stu-id="299c7-125">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="299c7-126"><strong>KeepErrorReportForDays</strong></span><span class="sxs-lookup"><span data-stu-id="299c7-126"><strong>KeepErrorReportForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="299c7-127">целое</span><span class="sxs-lookup"><span data-stu-id="299c7-127">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="299c7-128">Указывает возраст записей отчета об ошибках (в днях), которые будут очищены из базы данных: Если включена очистка, записи отчета об ошибках старше этого значения будут удалены из базы данных.</span><span class="sxs-lookup"><span data-stu-id="299c7-128">Specifies the age of error report records (in days) that will be purged from the database: if purging is enabled, error report records older than this value will be removed from the database.</span></span> <span data-ttu-id="299c7-129">Значение по умолчанию — 60 дней.</span><span class="sxs-lookup"><span data-stu-id="299c7-129">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="299c7-130"><strong>Пуржехаур</strong></span><span class="sxs-lookup"><span data-stu-id="299c7-130"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="299c7-131">целое</span><span class="sxs-lookup"><span data-stu-id="299c7-131">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="299c7-132">Указывает местное время суток, когда будет выполняться очистка базы данных.</span><span class="sxs-lookup"><span data-stu-id="299c7-132">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="299c7-133">Время суток задается в 24-часовом формате (0 соответствует полуночи (00:00), а 23 — 23:00 часам вечера).</span><span class="sxs-lookup"><span data-stu-id="299c7-133">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="299c7-134">Обратите внимание, что вы можете указать только час дня: значение 10 (указывает на 10:00 AM) разрешено, но значение 10:30 от 10,5 (это означает 10:30 AM) не разрешено.</span><span class="sxs-lookup"><span data-stu-id="299c7-134">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="299c7-135">Значение по умолчанию — 2 часа утра (02:00).</span><span class="sxs-lookup"><span data-stu-id="299c7-135">The default value is 2 (2:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

