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
ms.openlocfilehash: ddb3a0e781b5f505cb5a63d36eda73b98629e19b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213305"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="gateways-table-in-lync-server-2013"></a><span data-ttu-id="3143f-102">Таблица Gateways в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3143f-102">Gateways table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3143f-103">_**Последнее изменение темы:** 2010-11-05_</span><span class="sxs-lookup"><span data-stu-id="3143f-103">_**Topic Last Modified:** 2010-11-05_</span></span>

<span data-ttu-id="3143f-104">Таблица Gateways это вспомогательная таблица.</span><span class="sxs-lookup"><span data-stu-id="3143f-104">The Gateways table is a supporting table.</span></span> <span data-ttu-id="3143f-105">Каждая запись содержит сведения об одном шлюзе, который участвует в вызовах по телефонной сети общего пользования (PSTN), которые имеют записи в базе данных.</span><span class="sxs-lookup"><span data-stu-id="3143f-105">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3143f-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="3143f-106">Column</span></span></th>
<th><span data-ttu-id="3143f-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="3143f-107">Data Type</span></span></th>
<th><span data-ttu-id="3143f-108">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="3143f-108">Key/Index</span></span></th>
<th><span data-ttu-id="3143f-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="3143f-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3143f-110"><strong>гатевайид</strong></span><span class="sxs-lookup"><span data-stu-id="3143f-110"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="3143f-111">int</span><span class="sxs-lookup"><span data-stu-id="3143f-111">int</span></span></p></td>
<td><p><span data-ttu-id="3143f-112">Primary</span><span class="sxs-lookup"><span data-stu-id="3143f-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="3143f-113">Уникальный номер, идентифицирующий шлюз.</span><span class="sxs-lookup"><span data-stu-id="3143f-113">Unique number identifying this gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3143f-114"><strong>Шлюз</strong></span><span class="sxs-lookup"><span data-stu-id="3143f-114"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="3143f-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3143f-115">nvarchar(256)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3143f-116">Имя шлюза.</span><span class="sxs-lookup"><span data-stu-id="3143f-116">Gateway name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

