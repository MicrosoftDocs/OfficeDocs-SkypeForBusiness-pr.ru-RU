---
title: 'Lync Server 2013: таблица MonitoredRegionLink'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MonitoredRegionLink table
ms:assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398874(v=OCS.15)
ms:contentKeyID: 48185487
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e5608aa36a76fe59743ed8bb24e88514822a893e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoredregionlink-table-in-lync-server-2013"></a><span data-ttu-id="28840-102">Таблица MonitoredRegionLink в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28840-102">MonitoredRegionLink table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28840-103">_**Тема последнего изменения:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="28840-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="28840-104">Таблица Мониторедрегионлинк является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="28840-104">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="28840-105">Каждая запись представляет одну связь между двумя странами и областями.</span><span class="sxs-lookup"><span data-stu-id="28840-105">Each record represents one link between two countries/regions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="28840-106"><strong>Столбец</strong></span><span class="sxs-lookup"><span data-stu-id="28840-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="28840-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="28840-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="28840-108"><strong>Ключ/индекс</strong></span><span class="sxs-lookup"><span data-stu-id="28840-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="28840-109"><strong>Сведения</strong></span><span class="sxs-lookup"><span data-stu-id="28840-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="28840-110"><strong>Region1Key</strong></span><span class="sxs-lookup"><span data-stu-id="28840-110"><strong>Region1Key</strong></span></span></p></td>
<td><p><span data-ttu-id="28840-111">целое</span><span class="sxs-lookup"><span data-stu-id="28840-111">int</span></span></p></td>
<td><p><span data-ttu-id="28840-112">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="28840-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="28840-113">Ссылка на который указан в <a href="lync-server-2013-region-table.md">таблице Region в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="28840-113">Referenced from the <a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28840-114"><strong>Region2Key</strong></span><span class="sxs-lookup"><span data-stu-id="28840-114"><strong>Region2Key</strong></span></span></p></td>
<td><p><span data-ttu-id="28840-115">целое</span><span class="sxs-lookup"><span data-stu-id="28840-115">int</span></span></p></td>
<td><p><span data-ttu-id="28840-116">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="28840-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="28840-117">Ссылка на который указан в <a href="lync-server-2013-region-table.md">таблице Region в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="28840-117">Referenced from the <a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

