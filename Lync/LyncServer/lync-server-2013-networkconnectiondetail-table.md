---
title: 'Lync Server 2013: таблица Нетворкконнектиондетаил'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: NetworkConnectionDetail table
ms:assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205185(v=OCS.15)
ms:contentKeyID: 48185170
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 281e2d87088a56fdf46c045171772df00b1d9cf6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826425"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="networkconnectiondetail-table-in-lync-server-2013"></a><span data-ttu-id="283ec-102">Таблица Нетворкконнектиондетаил в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="283ec-102">NetworkConnectionDetail table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="283ec-103">_**Тема последнего изменения:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="283ec-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="283ec-104">Таблица Нетворкконнектиондетаил сопоставляет типы сетевых подключений с идентификаторами сетевых подключений, используемыми в базе данных качества обслуживания.</span><span class="sxs-lookup"><span data-stu-id="283ec-104">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="283ec-105">Эта таблица введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="283ec-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="283ec-106"><strong>Столбец</strong></span><span class="sxs-lookup"><span data-stu-id="283ec-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="283ec-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="283ec-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="283ec-108"><strong>Ключ/индекс</strong></span><span class="sxs-lookup"><span data-stu-id="283ec-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="283ec-109"><strong>Сведения</strong></span><span class="sxs-lookup"><span data-stu-id="283ec-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="283ec-110"><strong>Нетворкконнектиондетаилкэй</strong></span><span class="sxs-lookup"><span data-stu-id="283ec-110"><strong>NetworkConnectionDetailKey</strong></span></span></p></td>
<td><p><span data-ttu-id="283ec-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="283ec-111">tinyint</span></span></p></td>
<td><p><span data-ttu-id="283ec-112">Primary</span><span class="sxs-lookup"><span data-stu-id="283ec-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="283ec-113">Уникальный идентификатор типа сетевого подключения.</span><span class="sxs-lookup"><span data-stu-id="283ec-113">Unique identifier for the network connection type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="283ec-114"><strong>NetworkConnectionDetail</strong></span><span class="sxs-lookup"><span data-stu-id="283ec-114"><strong>NetworkConnectionDetail</strong></span></span></p></td>
<td><p><span data-ttu-id="283ec-115">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="283ec-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="283ec-116">Повторя</span><span class="sxs-lookup"><span data-stu-id="283ec-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="283ec-117">Тип сетевого подключения, соответствующий Нетворкконнектиондетаилкэй.</span><span class="sxs-lookup"><span data-stu-id="283ec-117">Network connection type that corresponds to the NetworkConnectionDetailKey.</span></span> <span data-ttu-id="283ec-118">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="283ec-118">Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="283ec-119">0--проводное подключение</span><span class="sxs-lookup"><span data-stu-id="283ec-119">0 -- Wired</span></span></p></li>
<li><p><span data-ttu-id="283ec-120">1--WiFi</span><span class="sxs-lookup"><span data-stu-id="283ec-120">1 -- WiFi</span></span></p></li>
<li><p><span data-ttu-id="283ec-121">2--Ethernet</span><span class="sxs-lookup"><span data-stu-id="283ec-121">2 -- Ethernet</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

