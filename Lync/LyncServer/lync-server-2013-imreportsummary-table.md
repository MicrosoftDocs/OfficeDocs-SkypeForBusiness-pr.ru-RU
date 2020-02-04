---
title: 'Lync Server 2013: таблица Имрепортсуммари'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IMReportSummary table
ms:assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204753(v=OCS.15)
ms:contentKeyID: 48183673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7a6be73d31892b5a0d5a3a5b10ad136f92afbf5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763823"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="imreportsummary-table-in-lync-server-2013"></a><span data-ttu-id="e9629-102">Таблица Имрепортсуммари в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9629-102">IMReportSummary table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9629-103">_**Тема последнего изменения:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="e9629-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="e9629-104">Имрепортсуммаритабле предоставляет общий отчет о сеансах обмена мгновенными сообщениями, которые хранятся в Организации.</span><span class="sxs-lookup"><span data-stu-id="e9629-104">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="e9629-105">Эта таблица введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e9629-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9629-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="e9629-106">Column</span></span></th>
<th><span data-ttu-id="e9629-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="e9629-107">Data Type</span></span></th>
<th><span data-ttu-id="e9629-108">Ключ/индекс</span><span class="sxs-lookup"><span data-stu-id="e9629-108">Key/Index</span></span></th>
<th><span data-ttu-id="e9629-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="e9629-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9629-110"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="e9629-110"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e9629-111">datetime</span><span class="sxs-lookup"><span data-stu-id="e9629-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="e9629-112">Primary</span><span class="sxs-lookup"><span data-stu-id="e9629-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="e9629-113">Дата и время начала сеанса обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="e9629-113">Date and time that the instant messaging session began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9629-114"><strong>тимепериод</strong></span><span class="sxs-lookup"><span data-stu-id="e9629-114"><strong>TimePeriod</strong></span></span></p></td>
<td><p><span data-ttu-id="e9629-115">char (1)</span><span class="sxs-lookup"><span data-stu-id="e9629-115">char(1)</span></span></p></td>
<td><p><span data-ttu-id="e9629-116">Primary</span><span class="sxs-lookup"><span data-stu-id="e9629-116">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9629-117"><strong>пулфкдн</strong></span><span class="sxs-lookup"><span data-stu-id="e9629-117"><strong>PoolFQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="e9629-118">nvarchar (257)</span><span class="sxs-lookup"><span data-stu-id="e9629-118">nvarchar(257)</span></span></p></td>
<td><p><span data-ttu-id="e9629-119">Primary</span><span class="sxs-lookup"><span data-stu-id="e9629-119">Primary</span></span></p></td>
<td><p><span data-ttu-id="e9629-120">Полное доменное имя пула, на котором размещается сеанс.</span><span class="sxs-lookup"><span data-stu-id="e9629-120">Fully qualified domain name of the pool hosting the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9629-121"><strong>аустипе</strong></span><span class="sxs-lookup"><span data-stu-id="e9629-121"><strong>AuthType</strong></span></span></p></td>
<td><p><span data-ttu-id="e9629-122">целое</span><span class="sxs-lookup"><span data-stu-id="e9629-122">int</span></span></p></td>
<td><p><span data-ttu-id="e9629-123">Primary</span><span class="sxs-lookup"><span data-stu-id="e9629-123">Primary</span></span></p></td>
<td><p><span data-ttu-id="e9629-124">Приоритет звонка (например, срочной или несрочный).</span><span class="sxs-lookup"><span data-stu-id="e9629-124">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="e9629-125">Сведения о приоритетах хранятся в <a href="lync-server-2013-callpriorities-table.md">таблице каллприоритиес в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e9629-125">Priority information is stored in the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9629-126"><strong>сессионкаунт</strong></span><span class="sxs-lookup"><span data-stu-id="e9629-126"><strong>SessionCount</strong></span></span></p></td>
<td><p><span data-ttu-id="e9629-127">bigint</span><span class="sxs-lookup"><span data-stu-id="e9629-127">bigint</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9629-128"><strong>мсгкаунт</strong></span><span class="sxs-lookup"><span data-stu-id="e9629-128"><strong>MsgCount</strong></span></span></p></td>
<td><p><span data-ttu-id="e9629-129">bigint</span><span class="sxs-lookup"><span data-stu-id="e9629-129">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e9629-130">Общее количество мгновенных сообщений, пересылаемых во время сеанса.</span><span class="sxs-lookup"><span data-stu-id="e9629-130">Total number of instant messages exchanged during the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

