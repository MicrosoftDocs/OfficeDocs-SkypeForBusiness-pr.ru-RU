---
title: 'Lync Server 2013: таблица Gateways'
description: 'Lync Server 2013: таблица Gateways.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Gateways table
ms:assetid: a909daad-d137-45e0-b149-1de9f8e1e029
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412795(v=OCS.15)
ms:contentKeyID: 48185034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 869aee0227c64c17f7bdbbfd82acbd43ae029bac
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567045"
---
# <a name="gateways-table-in-lync-server-2013"></a><span data-ttu-id="30d76-103">Таблица Gateways в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30d76-103">Gateways table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30d76-104">_**Последнее изменение темы:** 2010-11-05_</span><span class="sxs-lookup"><span data-stu-id="30d76-104">_**Topic Last Modified:** 2010-11-05_</span></span>

<span data-ttu-id="30d76-105">Таблица Gateways это вспомогательная таблица.</span><span class="sxs-lookup"><span data-stu-id="30d76-105">The Gateways table is a supporting table.</span></span> <span data-ttu-id="30d76-106">Каждая запись содержит сведения об одном шлюзе, который участвует в вызовах по телефонной сети общего пользования (PSTN), которые имеют записи в базе данных.</span><span class="sxs-lookup"><span data-stu-id="30d76-106">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="30d76-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="30d76-107">Column</span></span></th>
<th><span data-ttu-id="30d76-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="30d76-108">Data Type</span></span></th>
<th><span data-ttu-id="30d76-109">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="30d76-109">Key/Index</span></span></th>
<th><span data-ttu-id="30d76-110">Сведения</span><span class="sxs-lookup"><span data-stu-id="30d76-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30d76-111"><strong>гатевайид</strong></span><span class="sxs-lookup"><span data-stu-id="30d76-111"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="30d76-112">int</span><span class="sxs-lookup"><span data-stu-id="30d76-112">int</span></span></p></td>
<td><p><span data-ttu-id="30d76-113">Primary</span><span class="sxs-lookup"><span data-stu-id="30d76-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="30d76-114">Уникальный номер, идентифицирующий шлюз.</span><span class="sxs-lookup"><span data-stu-id="30d76-114">Unique number identifying this gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30d76-115"><strong>Шлюз</strong></span><span class="sxs-lookup"><span data-stu-id="30d76-115"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="30d76-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="30d76-116">nvarchar(256)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="30d76-117">Имя шлюза.</span><span class="sxs-lookup"><span data-stu-id="30d76-117">Gateway name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

