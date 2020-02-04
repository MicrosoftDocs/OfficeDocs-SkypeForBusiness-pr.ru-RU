---
title: 'Lync Server 2013: таблица Ерроркатегори'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorCategory table
ms:assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204675(v=OCS.15)
ms:contentKeyID: 48183425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5da1da6f54fa9099cc455040a71fb11c4fe070e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735429"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorcategory-table-in-lync-server-2013"></a><span data-ttu-id="6da7b-102">Таблица Ерроркатегори в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6da7b-102">ErrorCategory table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6da7b-103">_**Тема последнего изменения:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="6da7b-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="6da7b-104">В таблице Ерроркатегори содержится понятное имя для каждого диагностического классификация Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6da7b-104">The ErrorCategory table contains the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span> <span data-ttu-id="6da7b-105">По умолчанию Lync Server 2013 использует следующие классификации:</span><span class="sxs-lookup"><span data-stu-id="6da7b-105">By default, Lync Server 2013 uses the following classifications:</span></span>

  - <span data-ttu-id="6da7b-106">0 — успех</span><span class="sxs-lookup"><span data-stu-id="6da7b-106">0 -- Success</span></span>

  - <span data-ttu-id="6da7b-107">1 — ожидаемый сбой</span><span class="sxs-lookup"><span data-stu-id="6da7b-107">1 -- Expected failure</span></span>

  - <span data-ttu-id="6da7b-108">2 — непредвиденный сбой</span><span class="sxs-lookup"><span data-stu-id="6da7b-108">2 – Unexpected failure</span></span>

<span data-ttu-id="6da7b-109">Эта таблица введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6da7b-109">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6da7b-110">Столбец</span><span class="sxs-lookup"><span data-stu-id="6da7b-110">Column</span></span></th>
<th><span data-ttu-id="6da7b-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="6da7b-111">Data Type</span></span></th>
<th><span data-ttu-id="6da7b-112">Ключ/индекс</span><span class="sxs-lookup"><span data-stu-id="6da7b-112">Key/Index</span></span></th>
<th><span data-ttu-id="6da7b-113">Сведения</span><span class="sxs-lookup"><span data-stu-id="6da7b-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6da7b-114"><strong>КодТипа</strong></span><span class="sxs-lookup"><span data-stu-id="6da7b-114"><strong>CategoryId</strong></span></span></p></td>
<td><p><span data-ttu-id="6da7b-115">tinyint</span><span class="sxs-lookup"><span data-stu-id="6da7b-115">tinyint</span></span></p></td>
<td><p><span data-ttu-id="6da7b-116">Primary</span><span class="sxs-lookup"><span data-stu-id="6da7b-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="6da7b-117">Уникальный идентификатор для классификации.</span><span class="sxs-lookup"><span data-stu-id="6da7b-117">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6da7b-118"><strong>Имя</strong></span><span class="sxs-lookup"><span data-stu-id="6da7b-118"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="6da7b-119">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6da7b-119">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6da7b-120">Значение и понятное имя, присвоенное классификации.</span><span class="sxs-lookup"><span data-stu-id="6da7b-120">Value and friendly name assigned to the classification.</span></span> <span data-ttu-id="6da7b-121">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="6da7b-121">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="6da7b-122">0 — успех</span><span class="sxs-lookup"><span data-stu-id="6da7b-122">0 -- Success</span></span></p></li>
<li><p><span data-ttu-id="6da7b-123">1 — ожидаемый сбой</span><span class="sxs-lookup"><span data-stu-id="6da7b-123">1 -- Expected failure</span></span></p></li>
<li><p><span data-ttu-id="6da7b-124">2 — непредвиденный сбой</span><span class="sxs-lookup"><span data-stu-id="6da7b-124">2 – Unexpected failure</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

