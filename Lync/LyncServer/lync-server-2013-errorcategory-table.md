---
title: 'Lync Server 2013: таблица ErrorCategory'
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
ms.openlocfilehash: 3052aa95aa6cd846717aa98c5778531aeee6f7e2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="errorcategory-table-in-lync-server-2013"></a><span data-ttu-id="f2bcc-102">Таблица ErrorCategory в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2bcc-102">ErrorCategory table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2bcc-103">_**Последнее изменение темы:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="f2bcc-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="f2bcc-104">Таблица ErrorCategory содержит понятное имя каждого диагностической классификации Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f2bcc-104">The ErrorCategory table contains the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span> <span data-ttu-id="f2bcc-105">По умолчанию Lync Server 2013 использует следующие классификации:</span><span class="sxs-lookup"><span data-stu-id="f2bcc-105">By default, Lync Server 2013 uses the following classifications:</span></span>

  - <span data-ttu-id="f2bcc-106">0 — успешно</span><span class="sxs-lookup"><span data-stu-id="f2bcc-106">0 -- Success</span></span>

  - <span data-ttu-id="f2bcc-107">1 — ожидаемый сбой</span><span class="sxs-lookup"><span data-stu-id="f2bcc-107">1 -- Expected failure</span></span>

  - <span data-ttu-id="f2bcc-108">2 — неожиданный сбой</span><span class="sxs-lookup"><span data-stu-id="f2bcc-108">2 – Unexpected failure</span></span>

<span data-ttu-id="f2bcc-109">Эта таблица была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f2bcc-109">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2bcc-110">Столбец</span><span class="sxs-lookup"><span data-stu-id="f2bcc-110">Column</span></span></th>
<th><span data-ttu-id="f2bcc-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="f2bcc-111">Data Type</span></span></th>
<th><span data-ttu-id="f2bcc-112">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="f2bcc-112">Key/Index</span></span></th>
<th><span data-ttu-id="f2bcc-113">Сведения</span><span class="sxs-lookup"><span data-stu-id="f2bcc-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2bcc-114"><strong>CategoryId</strong></span><span class="sxs-lookup"><span data-stu-id="f2bcc-114"><strong>CategoryId</strong></span></span></p></td>
<td><p><span data-ttu-id="f2bcc-115">tinyint</span><span class="sxs-lookup"><span data-stu-id="f2bcc-115">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f2bcc-116">Primary</span><span class="sxs-lookup"><span data-stu-id="f2bcc-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="f2bcc-117">Уникальный идентификатор для классификации.</span><span class="sxs-lookup"><span data-stu-id="f2bcc-117">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2bcc-118"><strong>Имя</strong></span><span class="sxs-lookup"><span data-stu-id="f2bcc-118"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="f2bcc-119">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f2bcc-119">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2bcc-p102">Значение и понятное имя, назначенные классификации. Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="f2bcc-p102">Value and friendly name assigned to the classification. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="f2bcc-122">0 — успешно</span><span class="sxs-lookup"><span data-stu-id="f2bcc-122">0 -- Success</span></span></p></li>
<li><p><span data-ttu-id="f2bcc-123">1 — ожидаемый сбой</span><span class="sxs-lookup"><span data-stu-id="f2bcc-123">1 -- Expected failure</span></span></p></li>
<li><p><span data-ttu-id="f2bcc-124">2 — неожиданный сбой</span><span class="sxs-lookup"><span data-stu-id="f2bcc-124">2 – Unexpected failure</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

