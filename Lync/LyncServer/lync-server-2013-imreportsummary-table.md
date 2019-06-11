---
title: 'Lync Server 2013: таблица Имрепортсуммари'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IMReportSummary table
ms:assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204753(v=OCS.15)
ms:contentKeyID: 48183673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2254bafe059cc1a4bc6436580e9d604711f5fb3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834021"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="imreportsummary-table-in-lync-server-2013"></a><span data-ttu-id="8cbe9-102">Таблица Имрепортсуммари в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cbe9-102">IMReportSummary table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8cbe9-103">_**Тема последнего изменения:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="8cbe9-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="8cbe9-104">Имрепортсуммаритабле предоставляет общий отчет о сеансах обмена мгновенными сообщениями, которые хранятся в Организации.</span><span class="sxs-lookup"><span data-stu-id="8cbe9-104">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="8cbe9-105">Эта таблица введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8cbe9-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8cbe9-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="8cbe9-106">Column</span></span></th>
<th><span data-ttu-id="8cbe9-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="8cbe9-107">Data Type</span></span></th>
<th><span data-ttu-id="8cbe9-108">Ключ/индекс</span><span class="sxs-lookup"><span data-stu-id="8cbe9-108">Key/Index</span></span></th>
<th><span data-ttu-id="8cbe9-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="8cbe9-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8cbe9-110"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="8cbe9-110"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8cbe9-111">datetime</span><span class="sxs-lookup"><span data-stu-id="8cbe9-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="8cbe9-112">Primary</span><span class="sxs-lookup"><span data-stu-id="8cbe9-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="8cbe9-113">Дата и время начала сеанса обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="8cbe9-113">Date and time that the instant messaging session began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cbe9-114"><strong>Тимепериод</strong></span><span class="sxs-lookup"><span data-stu-id="8cbe9-114"><strong>TimePeriod</strong></span></span></p></td>
<td><p><span data-ttu-id="8cbe9-115">char (1)</span><span class="sxs-lookup"><span data-stu-id="8cbe9-115">char(1)</span></span></p></td>
<td><p><span data-ttu-id="8cbe9-116">Primary</span><span class="sxs-lookup"><span data-stu-id="8cbe9-116">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cbe9-117"><strong>Пулфкдн</strong></span><span class="sxs-lookup"><span data-stu-id="8cbe9-117"><strong>PoolFQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="8cbe9-118">nvarchar (257)</span><span class="sxs-lookup"><span data-stu-id="8cbe9-118">nvarchar(257)</span></span></p></td>
<td><p><span data-ttu-id="8cbe9-119">Primary</span><span class="sxs-lookup"><span data-stu-id="8cbe9-119">Primary</span></span></p></td>
<td><p><span data-ttu-id="8cbe9-120">Полное доменное имя пула, на котором размещается сеанс.</span><span class="sxs-lookup"><span data-stu-id="8cbe9-120">Fully qualified domain name of the pool hosting the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cbe9-121"><strong>Аустипе</strong></span><span class="sxs-lookup"><span data-stu-id="8cbe9-121"><strong>AuthType</strong></span></span></p></td>
<td><p><span data-ttu-id="8cbe9-122">целое</span><span class="sxs-lookup"><span data-stu-id="8cbe9-122">int</span></span></p></td>
<td><p><span data-ttu-id="8cbe9-123">Primary</span><span class="sxs-lookup"><span data-stu-id="8cbe9-123">Primary</span></span></p></td>
<td><p><span data-ttu-id="8cbe9-124">Приоритет звонка (например, срочной или несрочный).</span><span class="sxs-lookup"><span data-stu-id="8cbe9-124">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="8cbe9-125">Сведения о приоритетах хранятся в <a href="lync-server-2013-callpriorities-table.md">таблице каллприоритиес в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="8cbe9-125">Priority information is stored in the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cbe9-126"><strong>Сессионкаунт</strong></span><span class="sxs-lookup"><span data-stu-id="8cbe9-126"><strong>SessionCount</strong></span></span></p></td>
<td><p><span data-ttu-id="8cbe9-127">bigint</span><span class="sxs-lookup"><span data-stu-id="8cbe9-127">bigint</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cbe9-128"><strong>Мсгкаунт</strong></span><span class="sxs-lookup"><span data-stu-id="8cbe9-128"><strong>MsgCount</strong></span></span></p></td>
<td><p><span data-ttu-id="8cbe9-129">bigint</span><span class="sxs-lookup"><span data-stu-id="8cbe9-129">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8cbe9-130">Общее количество мгновенных сообщений, пересылаемых во время сеанса.</span><span class="sxs-lookup"><span data-stu-id="8cbe9-130">Total number of instant messages exchanged during the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

