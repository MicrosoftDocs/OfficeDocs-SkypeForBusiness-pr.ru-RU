---
title: 'Lync Server 2013: таблица Сипреспонсеметадата'
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
ms.openlocfilehash: 5bbfec0e3d1dae6d4799fbb109e081a8f7a1a299
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142795"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sipresponsemetadata-table-in-lync-server-2013"></a><span data-ttu-id="27fd7-102">Таблица Сипреспонсеметадата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27fd7-102">SIPResponseMetaData table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27fd7-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="27fd7-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="27fd7-p101">Таблица SIPResponseMetaDataTable содержит список кодов ответа SIP, а также классификацию и определение каждого из этих кодов. Эти коды генерируются в ответ на события, затрагивающие устройства SIP и сеансы связи SIP; например, код ответа 403 создается, когда устройство SIP выполняет запрос, но сервер отказывается принять его на обработку.</span><span class="sxs-lookup"><span data-stu-id="27fd7-p101">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes. These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>

<span data-ttu-id="27fd7-106">Эта таблица была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="27fd7-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27fd7-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="27fd7-107">Column</span></span></th>
<th><span data-ttu-id="27fd7-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="27fd7-108">Data Type</span></span></th>
<th><span data-ttu-id="27fd7-109">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="27fd7-109">Key/Index</span></span></th>
<th><span data-ttu-id="27fd7-110">Сведения</span><span class="sxs-lookup"><span data-stu-id="27fd7-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27fd7-111"><strong>респонсекоде</strong></span><span class="sxs-lookup"><span data-stu-id="27fd7-111"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="27fd7-112">int</span><span class="sxs-lookup"><span data-stu-id="27fd7-112">int</span></span></p></td>
<td><p><span data-ttu-id="27fd7-113">Primary</span><span class="sxs-lookup"><span data-stu-id="27fd7-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="27fd7-114">Числовое значение, которое определяет код ответа SIP.</span><span class="sxs-lookup"><span data-stu-id="27fd7-114">Numeric value that represents the SIP response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27fd7-115"><strong>Класс</strong></span><span class="sxs-lookup"><span data-stu-id="27fd7-115"><strong>Class</strong></span></span></p></td>
<td><p><span data-ttu-id="27fd7-116">int</span><span class="sxs-lookup"><span data-stu-id="27fd7-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="27fd7-p102">Общая классификация кода ответа. Возможные классификации:</span><span class="sxs-lookup"><span data-stu-id="27fd7-p102">General classification for the response code. Classifications include:</span></span></p>
<ul>
<li><p><span data-ttu-id="27fd7-119">1 — информационные ответы</span><span class="sxs-lookup"><span data-stu-id="27fd7-119">1 – Informational Responses</span></span></p></li>
<li><p><span data-ttu-id="27fd7-120">2 — успешные ответы</span><span class="sxs-lookup"><span data-stu-id="27fd7-120">2 – Successful Responses</span></span></p></li>
<li><p><span data-ttu-id="27fd7-121">3 — ответы перенаправления</span><span class="sxs-lookup"><span data-stu-id="27fd7-121">3 – Redirection Responses</span></span></p></li>
<li><p><span data-ttu-id="27fd7-122">4 — ответы сбоя клиента</span><span class="sxs-lookup"><span data-stu-id="27fd7-122">4 – Client Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="27fd7-123">5 — ответы об отказах серверов</span><span class="sxs-lookup"><span data-stu-id="27fd7-123">5 -- Server Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="27fd7-124">6 — ответы глобального сбоя</span><span class="sxs-lookup"><span data-stu-id="27fd7-124">6 – Global Failure Response</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27fd7-125"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="27fd7-125"><strong>Description</strong></span></span></p></td>
<td><p><span data-ttu-id="27fd7-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="27fd7-126">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="27fd7-p103">Описание кода ответа SIP. Например, для кода ответа 181 доступно следующее описание:</span><span class="sxs-lookup"><span data-stu-id="27fd7-p103">Description of the SIP response code. For example, response code 181 has the following description:</span></span></p>
<p><span data-ttu-id="27fd7-129">Вызов перенаправляется</span><span class="sxs-lookup"><span data-stu-id="27fd7-129">Call Is Being Forwarded</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

