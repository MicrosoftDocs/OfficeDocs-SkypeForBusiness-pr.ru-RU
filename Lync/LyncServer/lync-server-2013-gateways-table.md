---
title: 'Lync Server 2013: таблица Gateways'
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
ms.openlocfilehash: 3a03222cd628466e7d88e8f36adafbf5207f0ef0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="gateways-table-in-lync-server-2013"></a><span data-ttu-id="65058-102">Таблица Gateways в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65058-102">Gateways table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65058-103">_**Последнее изменение темы:** 2010-11-05_</span><span class="sxs-lookup"><span data-stu-id="65058-103">_**Topic Last Modified:** 2010-11-05_</span></span>

<span data-ttu-id="65058-104">Таблица Gateways это вспомогательная таблица.</span><span class="sxs-lookup"><span data-stu-id="65058-104">The Gateways table is a supporting table.</span></span> <span data-ttu-id="65058-105">Каждая запись содержит сведения об одном шлюзе, который участвует в вызовах по телефонной сети общего пользования (PSTN), которые имеют записи в базе данных.</span><span class="sxs-lookup"><span data-stu-id="65058-105">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="65058-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="65058-106">Column</span></span></th>
<th><span data-ttu-id="65058-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="65058-107">Data Type</span></span></th>
<th><span data-ttu-id="65058-108">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="65058-108">Key/Index</span></span></th>
<th><span data-ttu-id="65058-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="65058-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65058-110"><strong>гатевайид</strong></span><span class="sxs-lookup"><span data-stu-id="65058-110"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="65058-111">int</span><span class="sxs-lookup"><span data-stu-id="65058-111">int</span></span></p></td>
<td><p><span data-ttu-id="65058-112">Primary</span><span class="sxs-lookup"><span data-stu-id="65058-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="65058-113">Уникальный номер, идентифицирующий шлюз.</span><span class="sxs-lookup"><span data-stu-id="65058-113">Unique number identifying this gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65058-114"><strong>Шлюз</strong></span><span class="sxs-lookup"><span data-stu-id="65058-114"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="65058-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="65058-115">nvarchar(256)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="65058-116">Имя шлюза.</span><span class="sxs-lookup"><span data-stu-id="65058-116">Gateway name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

