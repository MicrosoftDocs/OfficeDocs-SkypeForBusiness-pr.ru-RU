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

# <a name="purgesettings-table-qoe-in-lync-server-2013"></a><span data-ttu-id="30e50-102">Пуржесеттингс Table (QoE) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30e50-102">PurgeSettings table (QoE) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30e50-103">_**Тема последнего изменения:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="30e50-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="30e50-104">В таблице Пуржесеттингс содержатся сведения о том, что (и когда) устаревшие записи качества обслуживания будут автоматически удалены из базы данных QoE.</span><span class="sxs-lookup"><span data-stu-id="30e50-104">The PurgeSettings table contains information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span> <span data-ttu-id="30e50-105">Обратите внимание, что в командной консоли Microsoft Lync Server 2013 также можно получить сведения об очистке, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="30e50-105">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsQoEConfiguration

<span data-ttu-id="30e50-106">Эта таблица введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="30e50-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="30e50-107"><strong>Столбец</strong></span><span class="sxs-lookup"><span data-stu-id="30e50-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="30e50-108"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="30e50-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="30e50-109"><strong>Ключ/индекс</strong></span><span class="sxs-lookup"><span data-stu-id="30e50-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="30e50-110"><strong>Сведения</strong></span><span class="sxs-lookup"><span data-stu-id="30e50-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30e50-111"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="30e50-111"><strong>ID</strong></span></span></p></td>
<td><p><span data-ttu-id="30e50-112">целое</span><span class="sxs-lookup"><span data-stu-id="30e50-112">int</span></span></p></td>
<td><p><span data-ttu-id="30e50-113">Primary</span><span class="sxs-lookup"><span data-stu-id="30e50-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="30e50-114">Уникальный идентификатор коллекции параметров очистки QoE.</span><span class="sxs-lookup"><span data-stu-id="30e50-114">Unique identifier for the collection of QoE purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30e50-115"><strong>Енаблепурже</strong></span><span class="sxs-lookup"><span data-stu-id="30e50-115"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="30e50-116">бит</span><span class="sxs-lookup"><span data-stu-id="30e50-116">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="30e50-117">Если установлено значение true (1), Microsoft Lync Server 2013 будет периодически очищать устаревшие записи из базы данных QoE.</span><span class="sxs-lookup"><span data-stu-id="30e50-117">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the QoE database.</span></span> <span data-ttu-id="30e50-118">Очистка будет выполняться каждый день в томе, указанном в параметре Пуржехаур.</span><span class="sxs-lookup"><span data-stu-id="30e50-118">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="30e50-119">Если для этого свойства задано значение false (0), записи не будут автоматически удалены из базы данных.</span><span class="sxs-lookup"><span data-stu-id="30e50-119">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="30e50-120">По умолчанию используется значение True.</span><span class="sxs-lookup"><span data-stu-id="30e50-120">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30e50-121"><strong>KeepQoEDataForDays</strong></span><span class="sxs-lookup"><span data-stu-id="30e50-121"><strong>KeepQoEDataForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="30e50-122">целое</span><span class="sxs-lookup"><span data-stu-id="30e50-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="30e50-123">Указывает возраст QoE записей (в днях), которые будут очищены из базы данных: Если включена очистка, QoE записи, возраст которых превышает это значение, будут удалены из базы данных.</span><span class="sxs-lookup"><span data-stu-id="30e50-123">Specifies the age of QoE records (in days) that will be purged from the database: if purging is enabled, QoE records older than this value will be removed from the database.</span></span> <span data-ttu-id="30e50-124">Значение по умолчанию — 60 дней.</span><span class="sxs-lookup"><span data-stu-id="30e50-124">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30e50-125"><strong>Пуржехаур</strong></span><span class="sxs-lookup"><span data-stu-id="30e50-125"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="30e50-126">целое</span><span class="sxs-lookup"><span data-stu-id="30e50-126">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="30e50-127">Указывает местное время суток, когда будет выполняться очистка базы данных.</span><span class="sxs-lookup"><span data-stu-id="30e50-127">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="30e50-128">Время суток задается в 24-часовом формате (0 соответствует полуночи (00:00), а 23 — 23:00 часам вечера).</span><span class="sxs-lookup"><span data-stu-id="30e50-128">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="30e50-129">Обратите внимание, что вы можете указать только час дня: значение 10 (указывает на 10:00 AM) разрешено, но значение 10:30 от 10,5 (это означает 10:30 AM) не разрешено.</span><span class="sxs-lookup"><span data-stu-id="30e50-129">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="30e50-130">Значение по умолчанию — 1 (1:00 AM).</span><span class="sxs-lookup"><span data-stu-id="30e50-130">The default value is 1 (1:00 AM).</span></span> <span data-ttu-id="30e50-131">Указывает местное время суток, когда будет выполняться очистка базы данных.</span><span class="sxs-lookup"><span data-stu-id="30e50-131">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="30e50-132">Время суток задается в 24-часовом формате (0 соответствует полуночи (00:00), а 23 — 23:00 часам вечера).</span><span class="sxs-lookup"><span data-stu-id="30e50-132">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="30e50-133">Обратите внимание, что вы можете указать только час дня: значение 10 (указывает на 10:00 AM) разрешено, но значение 10:30 от 10,5 (это означает 10:30 AM) не разрешено.</span><span class="sxs-lookup"><span data-stu-id="30e50-133">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="30e50-134">Значение по умолчанию — 1 (1:00 AM).</span><span class="sxs-lookup"><span data-stu-id="30e50-134">The default value is 1 (1:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

