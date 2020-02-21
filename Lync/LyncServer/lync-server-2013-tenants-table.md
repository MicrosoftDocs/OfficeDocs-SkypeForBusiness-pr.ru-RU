---
title: 'Lync Server 2013: таблица "клиенты"'
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
ms.openlocfilehash: 0d33f9138267cd26ff58fb32fc06c33c8b793c6d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tenants-table-in-lync-server-2013"></a><span data-ttu-id="6089f-102">Таблица клиентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6089f-102">Tenants table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6089f-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="6089f-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="6089f-p101">Таблица клиентов является вспомогательной таблицей, в которой хранится список различных клиентов. Каждая запись в таблице представляет одного клиента.</span><span class="sxs-lookup"><span data-stu-id="6089f-p101">The Tenants table is a supporting table that stores a list of the various tenants. Each record in the table represents one tenant.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6089f-106">В локальном развертывании CDR использует встроенный ИД клиента, чтобы показать различные типы проверки подлинности, такие как общедоступное подключение для обмена мгновенными сообщениями, федеративное подключение или анонимное подключение.</span><span class="sxs-lookup"><span data-stu-id="6089f-106">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span>



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
<th><span data-ttu-id="6089f-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="6089f-107">Column</span></span></th>
<th><span data-ttu-id="6089f-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="6089f-108">Data Type</span></span></th>
<th><span data-ttu-id="6089f-109">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="6089f-109">Key/Index</span></span></th>
<th><span data-ttu-id="6089f-110">Сведения</span><span class="sxs-lookup"><span data-stu-id="6089f-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6089f-111"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="6089f-111"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="6089f-112">int</span><span class="sxs-lookup"><span data-stu-id="6089f-112">int</span></span></p></td>
<td><p><span data-ttu-id="6089f-113">Primary</span><span class="sxs-lookup"><span data-stu-id="6089f-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="6089f-114">Уникальное число, определяющее ИД клиента.</span><span class="sxs-lookup"><span data-stu-id="6089f-114">Unique number identifying this Tenant ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6089f-115"><strong>тенанткэй</strong></span><span class="sxs-lookup"><span data-stu-id="6089f-115"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="6089f-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6089f-116">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6089f-117">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="6089f-117">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="6089f-118">00000000-0000-0000-0000-000000000000 — Корпоративное</span><span class="sxs-lookup"><span data-stu-id="6089f-118">00000000-0000-0000-0000-000000000000 – Enterprise</span></span></p></li>
<li><p><span data-ttu-id="6089f-119">00000000-0000-0000-0000-000000000001 — Федеративное</span><span class="sxs-lookup"><span data-stu-id="6089f-119">00000000-0000-0000-0000-000000000001 – Federated</span></span></p></li>
<li><p><span data-ttu-id="6089f-120">00000000-0000-0000-0000-000000000002 — Анонимное</span><span class="sxs-lookup"><span data-stu-id="6089f-120">00000000-0000-0000-0000-000000000002 – Anonymous</span></span></p></li>
<li><p><span data-ttu-id="6089f-121">00000000-0000-0000-0000-000000000003 — Общедоступное подключение для обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="6089f-121">00000000-0000-0000-0000-000000000003 – Public IM connectivity</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

