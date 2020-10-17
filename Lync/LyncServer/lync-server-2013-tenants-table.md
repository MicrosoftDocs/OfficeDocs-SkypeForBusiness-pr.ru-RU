---
title: 'Lync Server 2013: таблица "клиенты"'
description: 'Lync Server 2013: таблица клиентов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Tenants table
ms:assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412950(v=OCS.15)
ms:contentKeyID: 48185309
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96025dfd9fb42a6083f7f3daca98e243f01a8516
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568535"
---
# <a name="tenants-table-in-lync-server-2013"></a><span data-ttu-id="0507c-103">Таблица клиентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0507c-103">Tenants table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0507c-104">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="0507c-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="0507c-p101">Таблица клиентов является вспомогательной таблицей, в которой хранится список различных клиентов. Каждая запись в таблице представляет одного клиента.</span><span class="sxs-lookup"><span data-stu-id="0507c-p101">The Tenants table is a supporting table that stores a list of the various tenants. Each record in the table represents one tenant.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0507c-107">В локальном развертывании CDR использует встроенный ИД клиента, чтобы показать различные типы проверки подлинности, такие как общедоступное подключение для обмена мгновенными сообщениями, федеративное подключение или анонимное подключение.</span><span class="sxs-lookup"><span data-stu-id="0507c-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span>



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0507c-108">Столбец</span><span class="sxs-lookup"><span data-stu-id="0507c-108">Column</span></span></th>
<th><span data-ttu-id="0507c-109">Тип данных</span><span class="sxs-lookup"><span data-stu-id="0507c-109">Data Type</span></span></th>
<th><span data-ttu-id="0507c-110">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="0507c-110">Key/Index</span></span></th>
<th><span data-ttu-id="0507c-111">Сведения</span><span class="sxs-lookup"><span data-stu-id="0507c-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0507c-112"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="0507c-112"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="0507c-113">int</span><span class="sxs-lookup"><span data-stu-id="0507c-113">int</span></span></p></td>
<td><p><span data-ttu-id="0507c-114">Primary</span><span class="sxs-lookup"><span data-stu-id="0507c-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="0507c-115">Уникальное число, определяющее ИД клиента.</span><span class="sxs-lookup"><span data-stu-id="0507c-115">Unique number identifying this Tenant ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0507c-116"><strong>тенанткэй</strong></span><span class="sxs-lookup"><span data-stu-id="0507c-116"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="0507c-117">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0507c-117">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0507c-118">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="0507c-118">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="0507c-119">00000000-0000-0000-0000-000000000000 — Корпоративное</span><span class="sxs-lookup"><span data-stu-id="0507c-119">00000000-0000-0000-0000-000000000000 – Enterprise</span></span></p></li>
<li><p><span data-ttu-id="0507c-120">00000000-0000-0000-0000-000000000001 — Федеративное</span><span class="sxs-lookup"><span data-stu-id="0507c-120">00000000-0000-0000-0000-000000000001 – Federated</span></span></p></li>
<li><p><span data-ttu-id="0507c-121">00000000-0000-0000-0000-000000000002 — Анонимное</span><span class="sxs-lookup"><span data-stu-id="0507c-121">00000000-0000-0000-0000-000000000002 – Anonymous</span></span></p></li>
<li><p><span data-ttu-id="0507c-122">00000000-0000-0000-0000-000000000003 — Общедоступное подключение для обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="0507c-122">00000000-0000-0000-0000-000000000003 – Public IM connectivity</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

