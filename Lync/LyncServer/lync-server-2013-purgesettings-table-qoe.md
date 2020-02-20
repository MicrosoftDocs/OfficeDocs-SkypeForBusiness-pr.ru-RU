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
ms.openlocfilehash: bda217ec2711189439cfe6396faa5ba23872da9d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-qoe-in-lync-server-2013"></a><span data-ttu-id="3b6ed-102">Таблица Таблица purgesettings (QoE) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b6ed-102">PurgeSettings table (QoE) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b6ed-103">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="3b6ed-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="3b6ed-104">В таблице PurgeSettings содержатся сведения о том, должны ли устаревшие записи автоматически удаляться из базы данных качества обслуживания, и когда это должно происходить.</span><span class="sxs-lookup"><span data-stu-id="3b6ed-104">The PurgeSettings table contains information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span> <span data-ttu-id="3b6ed-105">Обратите внимание, что сведения об очистке можно также получить в командной консоли Microsoft Lync Server 2013, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3b6ed-105">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsQoEConfiguration

<span data-ttu-id="3b6ed-106">Эта таблица была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3b6ed-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3b6ed-107"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="3b6ed-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="3b6ed-108"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="3b6ed-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="3b6ed-109"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="3b6ed-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="3b6ed-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="3b6ed-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b6ed-111"><strong>ИД</strong></span><span class="sxs-lookup"><span data-stu-id="3b6ed-111"><strong>ID</strong></span></span></p></td>
<td><p><span data-ttu-id="3b6ed-112">int</span><span class="sxs-lookup"><span data-stu-id="3b6ed-112">int</span></span></p></td>
<td><p><span data-ttu-id="3b6ed-113">Primary</span><span class="sxs-lookup"><span data-stu-id="3b6ed-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="3b6ed-114">Уникальный идентификатор набора параметров, связанных с очисткой записей качества обслуживания.</span><span class="sxs-lookup"><span data-stu-id="3b6ed-114">Unique identifier for the collection of QoE purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b6ed-115"><strong>енаблепурже</strong></span><span class="sxs-lookup"><span data-stu-id="3b6ed-115"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="3b6ed-116">Битовая</span><span class="sxs-lookup"><span data-stu-id="3b6ed-116">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3b6ed-117">Если для этого параметра задано значение true (1), Microsoft Lync Server 2013 будет периодически очищать устаревшие записи из базы данных QoE.</span><span class="sxs-lookup"><span data-stu-id="3b6ed-117">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the QoE database.</span></span> <span data-ttu-id="3b6ed-118">Очистка будет происходить каждый день во время, установленное с помощью параметра PurgeHour.</span><span class="sxs-lookup"><span data-stu-id="3b6ed-118">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="3b6ed-119">Если задано значение False (0), записи не будут очищаться автоматически.</span><span class="sxs-lookup"><span data-stu-id="3b6ed-119">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="3b6ed-120">Значение по умолчанию — True.</span><span class="sxs-lookup"><span data-stu-id="3b6ed-120">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b6ed-121"><strong>KeepQoEDataForDays</strong></span><span class="sxs-lookup"><span data-stu-id="3b6ed-121"><strong>KeepQoEDataForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="3b6ed-122">int</span><span class="sxs-lookup"><span data-stu-id="3b6ed-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3b6ed-p103">Определяет возраст записей качества обслуживания (в днях), которые должны очищаться. Если очистка включена, записи старше этого значения будут удаляться из базы данных. Значение по умолчанию — 60 дней.</span><span class="sxs-lookup"><span data-stu-id="3b6ed-p103">Specifies the age of QoE records (in days) that will be purged from the database: if purging is enabled, QoE records older than this value will be removed from the database. The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b6ed-125"><strong>пуржехаур</strong></span><span class="sxs-lookup"><span data-stu-id="3b6ed-125"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="3b6ed-126">int</span><span class="sxs-lookup"><span data-stu-id="3b6ed-126">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3b6ed-p104">Определяет время суток (по местному времени), когда должна выполняться очистка базы данных. Время суток указывается в 24-часовом формате, где 0 означает полночь, а 23 означает 11 часов вечера. Обратите внимание на то, что вы можете указать только час: значение 10 (соответствующее 10:00 утра) допускается, а значение 10:30 или 10.5 (соответствующее 10:30 утра) — нет. Значение по умолчанию — 1 (1:00 ночи). Определяет время суток (по местному времени), когда должна выполняться очистка базы данных. Время суток указывается в 24-часовом формате, где 0 соответствует полуночи, а 23 соответствует 11:00 вечера. Обратите внимание на то, что вы можете указать только час: значение 10 (соответствующее 10:00 утра) допускается, а значение 10:30 или 10.5 (соответствующее 10:30 утра) — нет. Значение по умолчанию — 1 (1:00 ночи).</span><span class="sxs-lookup"><span data-stu-id="3b6ed-p104">Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM). Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

