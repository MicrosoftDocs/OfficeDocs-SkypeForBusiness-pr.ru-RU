---
title: 'Lync Server 2013: таблица Сипреспонсеметадата'
description: 'Lync Server 2013: таблица Сипреспонсеметадата.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIPResponseMetaData table
ms:assetid: cf723737-4a75-4352-829b-f4954aa59716
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205294(v=OCS.15)
ms:contentKeyID: 48185510
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 402cff331f81a9b46028d76de69deeaace8d5ae1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558985"
---
# <a name="sipresponsemetadata-table-in-lync-server-2013"></a><span data-ttu-id="e875f-103">Таблица Сипреспонсеметадата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e875f-103">SIPResponseMetaData table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e875f-104">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="e875f-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="e875f-p101">Таблица SIPResponseMetaDataTable содержит список кодов ответа SIP, а также классификацию и определение каждого из этих кодов. Эти коды генерируются в ответ на события, затрагивающие устройства SIP и сеансы связи SIP; например, код ответа 403 создается, когда устройство SIP выполняет запрос, но сервер отказывается принять его на обработку.</span><span class="sxs-lookup"><span data-stu-id="e875f-p101">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes. These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>

<span data-ttu-id="e875f-107">Эта таблица была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e875f-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e875f-108">Столбец</span><span class="sxs-lookup"><span data-stu-id="e875f-108">Column</span></span></th>
<th><span data-ttu-id="e875f-109">Тип данных</span><span class="sxs-lookup"><span data-stu-id="e875f-109">Data Type</span></span></th>
<th><span data-ttu-id="e875f-110">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="e875f-110">Key/Index</span></span></th>
<th><span data-ttu-id="e875f-111">Сведения</span><span class="sxs-lookup"><span data-stu-id="e875f-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e875f-112"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="e875f-112"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="e875f-113">int</span><span class="sxs-lookup"><span data-stu-id="e875f-113">int</span></span></p></td>
<td><p><span data-ttu-id="e875f-114">Primary</span><span class="sxs-lookup"><span data-stu-id="e875f-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="e875f-115">Числовое значение, которое определяет код ответа SIP.</span><span class="sxs-lookup"><span data-stu-id="e875f-115">Numeric value that represents the SIP response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e875f-116"><strong>Class</strong></span><span class="sxs-lookup"><span data-stu-id="e875f-116"><strong>Class</strong></span></span></p></td>
<td><p><span data-ttu-id="e875f-117">int</span><span class="sxs-lookup"><span data-stu-id="e875f-117">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e875f-p102">Общая классификация кода ответа. Возможные классификации:</span><span class="sxs-lookup"><span data-stu-id="e875f-p102">General classification for the response code. Classifications include:</span></span></p>
<ul>
<li><p><span data-ttu-id="e875f-120">1 — информационные ответы</span><span class="sxs-lookup"><span data-stu-id="e875f-120">1 – Informational Responses</span></span></p></li>
<li><p><span data-ttu-id="e875f-121">2 — успешные ответы</span><span class="sxs-lookup"><span data-stu-id="e875f-121">2 – Successful Responses</span></span></p></li>
<li><p><span data-ttu-id="e875f-122">3 — ответы перенаправления</span><span class="sxs-lookup"><span data-stu-id="e875f-122">3 – Redirection Responses</span></span></p></li>
<li><p><span data-ttu-id="e875f-123">4 — ответы сбоя клиента</span><span class="sxs-lookup"><span data-stu-id="e875f-123">4 – Client Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="e875f-124">5 — ответы об отказах серверов</span><span class="sxs-lookup"><span data-stu-id="e875f-124">5 -- Server Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="e875f-125">6 — ответы глобального сбоя</span><span class="sxs-lookup"><span data-stu-id="e875f-125">6 – Global Failure Response</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e875f-126"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="e875f-126"><strong>Description</strong></span></span></p></td>
<td><p><span data-ttu-id="e875f-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e875f-127">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e875f-p103">Описание кода ответа SIP. Например, для кода ответа 181 доступно следующее описание:</span><span class="sxs-lookup"><span data-stu-id="e875f-p103">Description of the SIP response code. For example, response code 181 has the following description:</span></span></p>
<p><span data-ttu-id="e875f-130">Вызов перенаправляется</span><span class="sxs-lookup"><span data-stu-id="e875f-130">Call Is Being Forwarded</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

