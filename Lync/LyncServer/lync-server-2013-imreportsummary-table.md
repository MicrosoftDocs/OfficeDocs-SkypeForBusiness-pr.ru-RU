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
ms.openlocfilehash: 287fc0ceff26a5940d717b4efa1ef2c525acb0f1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038691"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="imreportsummary-table-in-lync-server-2013"></a><span data-ttu-id="1f61e-102">Таблица Имрепортсуммари в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f61e-102">IMReportSummary table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f61e-103">_**Последнее изменение темы:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="1f61e-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="1f61e-104">В таблице IMReportSummaryTable приводится общий отчет о сеансах обмена мгновенными сообщениями, которые проводятся в организации.</span><span class="sxs-lookup"><span data-stu-id="1f61e-104">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="1f61e-105">Эта таблица была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1f61e-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f61e-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="1f61e-106">Column</span></span></th>
<th><span data-ttu-id="1f61e-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="1f61e-107">Data Type</span></span></th>
<th><span data-ttu-id="1f61e-108">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="1f61e-108">Key/Index</span></span></th>
<th><span data-ttu-id="1f61e-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="1f61e-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f61e-110"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="1f61e-110"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1f61e-111">datetime</span><span class="sxs-lookup"><span data-stu-id="1f61e-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="1f61e-112">Primary</span><span class="sxs-lookup"><span data-stu-id="1f61e-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="1f61e-113">Дата и время начала сеанса обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="1f61e-113">Date and time that the instant messaging session began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f61e-114"><strong>Время</strong></span><span class="sxs-lookup"><span data-stu-id="1f61e-114"><strong>TimePeriod</strong></span></span></p></td>
<td><p><span data-ttu-id="1f61e-115">char (1)</span><span class="sxs-lookup"><span data-stu-id="1f61e-115">char(1)</span></span></p></td>
<td><p><span data-ttu-id="1f61e-116">Primary</span><span class="sxs-lookup"><span data-stu-id="1f61e-116">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f61e-117"><strong>PoolFQDN</strong></span><span class="sxs-lookup"><span data-stu-id="1f61e-117"><strong>PoolFQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="1f61e-118">nvarchar (257)</span><span class="sxs-lookup"><span data-stu-id="1f61e-118">nvarchar(257)</span></span></p></td>
<td><p><span data-ttu-id="1f61e-119">Primary</span><span class="sxs-lookup"><span data-stu-id="1f61e-119">Primary</span></span></p></td>
<td><p><span data-ttu-id="1f61e-120">Полное доменное имя пула, в котором размещается сеанс.</span><span class="sxs-lookup"><span data-stu-id="1f61e-120">Fully qualified domain name of the pool hosting the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f61e-121"><strong>аустипе</strong></span><span class="sxs-lookup"><span data-stu-id="1f61e-121"><strong>AuthType</strong></span></span></p></td>
<td><p><span data-ttu-id="1f61e-122">int</span><span class="sxs-lookup"><span data-stu-id="1f61e-122">int</span></span></p></td>
<td><p><span data-ttu-id="1f61e-123">Primary</span><span class="sxs-lookup"><span data-stu-id="1f61e-123">Primary</span></span></p></td>
<td><p><span data-ttu-id="1f61e-124">Приоритет звонка (например, срочный или несрочный).</span><span class="sxs-lookup"><span data-stu-id="1f61e-124">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="1f61e-125">Сведения о приоритетах хранятся в <a href="lync-server-2013-callpriorities-table.md">таблице таблица callpriorities в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="1f61e-125">Priority information is stored in the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f61e-126"><strong>сессионкаунт</strong></span><span class="sxs-lookup"><span data-stu-id="1f61e-126"><strong>SessionCount</strong></span></span></p></td>
<td><p><span data-ttu-id="1f61e-127">типу</span><span class="sxs-lookup"><span data-stu-id="1f61e-127">bigint</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f61e-128"><strong>мсгкаунт</strong></span><span class="sxs-lookup"><span data-stu-id="1f61e-128"><strong>MsgCount</strong></span></span></p></td>
<td><p><span data-ttu-id="1f61e-129">типу</span><span class="sxs-lookup"><span data-stu-id="1f61e-129">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1f61e-130">Общее число мгновенных сообщений, отправленных в рамках сеанса.</span><span class="sxs-lookup"><span data-stu-id="1f61e-130">Total number of instant messages exchanged during the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

