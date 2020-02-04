---
title: 'Lync Server 2013: таблица Region'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Region table
ms:assetid: 1751a6aa-a6e8-4f16-8eb7-ae731c2e3ee3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398235(v=OCS.15)
ms:contentKeyID: 48183518
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 005722b28b6ea93d89873d45e7a9284f44643bde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724429"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="region-table-in-lync-server-2013"></a><span data-ttu-id="93280-102">Таблица Region в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93280-102">Region table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93280-103">_**Тема последнего изменения:** 2010-11-09_</span><span class="sxs-lookup"><span data-stu-id="93280-103">_**Topic Last Modified:** 2010-11-09_</span></span>

<span data-ttu-id="93280-104">Таблица Region является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="93280-104">The Region table is a supporting table.</span></span> <span data-ttu-id="93280-105">Каждая запись представляет одну страну/регион, определенные в параметрах конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="93280-105">Each record represents one country/region defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93280-106"><strong>Столбец</strong></span><span class="sxs-lookup"><span data-stu-id="93280-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="93280-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="93280-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="93280-108"><strong>Ключ/индекс</strong></span><span class="sxs-lookup"><span data-stu-id="93280-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="93280-109"><strong>Сведения</strong></span><span class="sxs-lookup"><span data-stu-id="93280-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93280-110"><strong>регионкэй</strong></span><span class="sxs-lookup"><span data-stu-id="93280-110"><strong>RegionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="93280-111">целое</span><span class="sxs-lookup"><span data-stu-id="93280-111">int</span></span></p></td>
<td><p><span data-ttu-id="93280-112">Primary</span><span class="sxs-lookup"><span data-stu-id="93280-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="93280-113">Уникальный номер, идентифицирующий страну или регион.</span><span class="sxs-lookup"><span data-stu-id="93280-113">Unique number identifying the country/region.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93280-114"><strong>регионнаме</strong></span><span class="sxs-lookup"><span data-stu-id="93280-114"><strong>RegionName</strong></span></span></p></td>
<td><p><span data-ttu-id="93280-115">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="93280-115">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="93280-116">Повторя</span><span class="sxs-lookup"><span data-stu-id="93280-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="93280-117">Название страны/региона.</span><span class="sxs-lookup"><span data-stu-id="93280-117">The name of the country/region.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

