---
title: 'Lync Server 2013: таблица Сипреспонсеметадата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SIPResponseMetaData table
ms:assetid: cf723737-4a75-4352-829b-f4954aa59716
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205294(v=OCS.15)
ms:contentKeyID: 48185510
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31df563172cce2e6ac9780511665ef563532a7d9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849657"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sipresponsemetadata-table-in-lync-server-2013"></a><span data-ttu-id="5b492-102">Таблица Сипреспонсеметадата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b492-102">SIPResponseMetaData table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b492-103">_**Тема последнего изменения:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="5b492-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="5b492-104">В Сипреспонсеметадататабле содержится список кодов ответов SIP, а также классификация и определение каждого из этих кодов.</span><span class="sxs-lookup"><span data-stu-id="5b492-104">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="5b492-105">Эти коды генерируются в ответ на события, влияющие на устройства SIP и сеансы связи SIP; Например, код ответа 403 генерируется, когда устройство SIP делает запрос, но сервер отклоняет этот запрос.</span><span class="sxs-lookup"><span data-stu-id="5b492-105">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>

<span data-ttu-id="5b492-106">Эта таблица введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5b492-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5b492-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="5b492-107">Column</span></span></th>
<th><span data-ttu-id="5b492-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="5b492-108">Data Type</span></span></th>
<th><span data-ttu-id="5b492-109">Ключ/индекс</span><span class="sxs-lookup"><span data-stu-id="5b492-109">Key/Index</span></span></th>
<th><span data-ttu-id="5b492-110">Сведения</span><span class="sxs-lookup"><span data-stu-id="5b492-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b492-111"><strong>Респонсекоде</strong></span><span class="sxs-lookup"><span data-stu-id="5b492-111"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="5b492-112">целое</span><span class="sxs-lookup"><span data-stu-id="5b492-112">int</span></span></p></td>
<td><p><span data-ttu-id="5b492-113">Primary</span><span class="sxs-lookup"><span data-stu-id="5b492-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="5b492-114">Числовое значение, представляющее код ответа SIP.</span><span class="sxs-lookup"><span data-stu-id="5b492-114">Numeric value that represents the SIP response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b492-115"><strong>Классов</strong></span><span class="sxs-lookup"><span data-stu-id="5b492-115"><strong>Class</strong></span></span></p></td>
<td><p><span data-ttu-id="5b492-116">целое</span><span class="sxs-lookup"><span data-stu-id="5b492-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5b492-117">Общая классификация для кода ответа.</span><span class="sxs-lookup"><span data-stu-id="5b492-117">General classification for the response code.</span></span> <span data-ttu-id="5b492-118">Существуют следующие классификации:</span><span class="sxs-lookup"><span data-stu-id="5b492-118">Classifications include:</span></span></p>
<ul>
<li><p><span data-ttu-id="5b492-119">1 — Информационные ответы</span><span class="sxs-lookup"><span data-stu-id="5b492-119">1 – Informational Responses</span></span></p></li>
<li><p><span data-ttu-id="5b492-120">2 – успешные ответы</span><span class="sxs-lookup"><span data-stu-id="5b492-120">2 – Successful Responses</span></span></p></li>
<li><p><span data-ttu-id="5b492-121">3 – Ответы на перенаправление</span><span class="sxs-lookup"><span data-stu-id="5b492-121">3 – Redirection Responses</span></span></p></li>
<li><p><span data-ttu-id="5b492-122">4 – Ответы на ошибки клиента</span><span class="sxs-lookup"><span data-stu-id="5b492-122">4 – Client Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="5b492-123">5-Ответы на ошибки сервера</span><span class="sxs-lookup"><span data-stu-id="5b492-123">5 -- Server Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="5b492-124">6 – Глобальный ответ на сбой</span><span class="sxs-lookup"><span data-stu-id="5b492-124">6 – Global Failure Response</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b492-125"><strong>Описание</strong></span><span class="sxs-lookup"><span data-stu-id="5b492-125"><strong>Description</strong></span></span></p></td>
<td><p><span data-ttu-id="5b492-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5b492-126">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5b492-127">Описание кода ответа SIP.</span><span class="sxs-lookup"><span data-stu-id="5b492-127">Description of the SIP response code.</span></span> <span data-ttu-id="5b492-128">Например, код ответа 181 имеет следующее описание:</span><span class="sxs-lookup"><span data-stu-id="5b492-128">For example, response code 181 has the following description:</span></span></p>
<p><span data-ttu-id="5b492-129">Переадресация звонка</span><span class="sxs-lookup"><span data-stu-id="5b492-129">Call Is Being Forwarded</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

