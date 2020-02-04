---
title: 'Lync Server 2013: таблица EndpointSubnet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: EndpointSubnet table
ms:assetid: d62e51d6-2117-4c41-adce-08f8d9d75ce0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398933(v=OCS.15)
ms:contentKeyID: 48185514
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 055aa9460fb63e96d20472d6102c249ecf71a78b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735599"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="endpointsubnet-table-in-lync-server-2013"></a><span data-ttu-id="ee6e4-102">Таблица EndpointSubnet в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee6e4-102">EndpointSubnet table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee6e4-103">_**Тема последнего изменения:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ee6e4-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ee6e4-104">Таблица Ендпоинтсубнет является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="ee6e4-104">The EndpointSubnet table is a supporting table.</span></span> <span data-ttu-id="ee6e4-105">Каждая запись соответствует одной подсети, захваченной из конечных точек.</span><span class="sxs-lookup"><span data-stu-id="ee6e4-105">Each record represents one subnet captured from endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ee6e4-106"><strong>Столбец</strong></span><span class="sxs-lookup"><span data-stu-id="ee6e4-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ee6e4-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="ee6e4-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ee6e4-108"><strong>Ключ/индекс</strong></span><span class="sxs-lookup"><span data-stu-id="ee6e4-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ee6e4-109"><strong>Сведения</strong></span><span class="sxs-lookup"><span data-stu-id="ee6e4-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee6e4-110"><strong>субнетип</strong></span><span class="sxs-lookup"><span data-stu-id="ee6e4-110"><strong>SubnetIP</strong></span></span></p></td>
<td><p><span data-ttu-id="ee6e4-111">целое</span><span class="sxs-lookup"><span data-stu-id="ee6e4-111">int</span></span></p></td>
<td><p><span data-ttu-id="ee6e4-112">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="ee6e4-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ee6e4-113">Целочисленное представление для подсети.</span><span class="sxs-lookup"><span data-stu-id="ee6e4-113">Integer representation for the subnet.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee6e4-114"><strong>некступдатетс</strong></span><span class="sxs-lookup"><span data-stu-id="ee6e4-114"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="ee6e4-115">datetime</span><span class="sxs-lookup"><span data-stu-id="ee6e4-115">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ee6e4-116">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="ee6e4-116">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

