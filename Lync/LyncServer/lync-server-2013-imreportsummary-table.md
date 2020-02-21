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
ms.openlocfilehash: 5d13401f38677d75bc40cbb4c1bd56f2fbb7fbb4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196692"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="imreportsummary-table-in-lync-server-2013"></a><span data-ttu-id="d1f59-102">Таблица Имрепортсуммари в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1f59-102">IMReportSummary table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1f59-103">_**Последнее изменение темы:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="d1f59-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="d1f59-104">В таблице IMReportSummaryTable приводится общий отчет о сеансах обмена мгновенными сообщениями, которые проводятся в организации.</span><span class="sxs-lookup"><span data-stu-id="d1f59-104">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="d1f59-105">Эта таблица была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d1f59-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1f59-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="d1f59-106">Column</span></span></th>
<th><span data-ttu-id="d1f59-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="d1f59-107">Data Type</span></span></th>
<th><span data-ttu-id="d1f59-108">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="d1f59-108">Key/Index</span></span></th>
<th><span data-ttu-id="d1f59-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="d1f59-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1f59-110"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="d1f59-110"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d1f59-111">datetime</span><span class="sxs-lookup"><span data-stu-id="d1f59-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="d1f59-112">Primary</span><span class="sxs-lookup"><span data-stu-id="d1f59-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="d1f59-113">Дата и время начала сеанса обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="d1f59-113">Date and time that the instant messaging session began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1f59-114"><strong>Время</strong></span><span class="sxs-lookup"><span data-stu-id="d1f59-114"><strong>TimePeriod</strong></span></span></p></td>
<td><p><span data-ttu-id="d1f59-115">char (1)</span><span class="sxs-lookup"><span data-stu-id="d1f59-115">char(1)</span></span></p></td>
<td><p><span data-ttu-id="d1f59-116">Primary</span><span class="sxs-lookup"><span data-stu-id="d1f59-116">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1f59-117"><strong>PoolFQDN</strong></span><span class="sxs-lookup"><span data-stu-id="d1f59-117"><strong>PoolFQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="d1f59-118">nvarchar (257)</span><span class="sxs-lookup"><span data-stu-id="d1f59-118">nvarchar(257)</span></span></p></td>
<td><p><span data-ttu-id="d1f59-119">Primary</span><span class="sxs-lookup"><span data-stu-id="d1f59-119">Primary</span></span></p></td>
<td><p><span data-ttu-id="d1f59-120">Полное доменное имя пула, в котором размещается сеанс.</span><span class="sxs-lookup"><span data-stu-id="d1f59-120">Fully qualified domain name of the pool hosting the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1f59-121"><strong>аустипе</strong></span><span class="sxs-lookup"><span data-stu-id="d1f59-121"><strong>AuthType</strong></span></span></p></td>
<td><p><span data-ttu-id="d1f59-122">int</span><span class="sxs-lookup"><span data-stu-id="d1f59-122">int</span></span></p></td>
<td><p><span data-ttu-id="d1f59-123">Primary</span><span class="sxs-lookup"><span data-stu-id="d1f59-123">Primary</span></span></p></td>
<td><p><span data-ttu-id="d1f59-124">Приоритет звонка (например, срочный или несрочный).</span><span class="sxs-lookup"><span data-stu-id="d1f59-124">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="d1f59-125">Сведения о приоритетах хранятся в <a href="lync-server-2013-callpriorities-table.md">таблице таблица callpriorities в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d1f59-125">Priority information is stored in the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1f59-126"><strong>сессионкаунт</strong></span><span class="sxs-lookup"><span data-stu-id="d1f59-126"><strong>SessionCount</strong></span></span></p></td>
<td><p><span data-ttu-id="d1f59-127">типу</span><span class="sxs-lookup"><span data-stu-id="d1f59-127">bigint</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1f59-128"><strong>мсгкаунт</strong></span><span class="sxs-lookup"><span data-stu-id="d1f59-128"><strong>MsgCount</strong></span></span></p></td>
<td><p><span data-ttu-id="d1f59-129">типу</span><span class="sxs-lookup"><span data-stu-id="d1f59-129">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d1f59-130">Общее число мгновенных сообщений, отправленных в рамках сеанса.</span><span class="sxs-lookup"><span data-stu-id="d1f59-130">Total number of instant messages exchanged during the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

