---
title: 'Lync Server 2013: таблица UserSite'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserSite table
ms:assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398256(v=OCS.15)
ms:contentKeyID: 48183552
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9dfb3e3d99775405ce4a09df706bec8eea59f6f9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849273"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="usersite-table-in-lync-server-2013"></a><span data-ttu-id="c005b-102">Таблица UserSite в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c005b-102">UserSite table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c005b-103">_**Тема последнего изменения:** 2010-11-09_</span><span class="sxs-lookup"><span data-stu-id="c005b-103">_**Topic Last Modified:** 2010-11-09_</span></span>

<span data-ttu-id="c005b-104">Таблица Усерсите является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="c005b-104">The UserSite table is a supporting table.</span></span> <span data-ttu-id="c005b-105">Каждая запись соответствует одному сайту пользователя, определенному в параметрах конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="c005b-105">Each record represents one user site defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c005b-106"><strong>Столбец</strong></span><span class="sxs-lookup"><span data-stu-id="c005b-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="c005b-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="c005b-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="c005b-108"><strong>Ключ/индекс</strong></span><span class="sxs-lookup"><span data-stu-id="c005b-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="c005b-109"><strong>Сведения</strong></span><span class="sxs-lookup"><span data-stu-id="c005b-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c005b-110"><strong>Усерситекэй</strong></span><span class="sxs-lookup"><span data-stu-id="c005b-110"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="c005b-111">целое</span><span class="sxs-lookup"><span data-stu-id="c005b-111">int</span></span></p></td>
<td><p><span data-ttu-id="c005b-112">Primary</span><span class="sxs-lookup"><span data-stu-id="c005b-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="c005b-113">Уникальный номер, идентифицирующий сайт пользователя.</span><span class="sxs-lookup"><span data-stu-id="c005b-113">Unique number identifying the user site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c005b-114"><strong>Усерситенаме</strong></span><span class="sxs-lookup"><span data-stu-id="c005b-114"><strong>UserSiteName</strong></span></span></p></td>
<td><p><span data-ttu-id="c005b-115">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="c005b-115">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="c005b-116">Повторя</span><span class="sxs-lookup"><span data-stu-id="c005b-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="c005b-117">Имя сайта пользователя.</span><span class="sxs-lookup"><span data-stu-id="c005b-117">User site’s name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c005b-118"><strong>Регионкэй</strong></span><span class="sxs-lookup"><span data-stu-id="c005b-118"><strong>RegionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="c005b-119">целое</span><span class="sxs-lookup"><span data-stu-id="c005b-119">int</span></span></p></td>
<td><p><span data-ttu-id="c005b-120">Другом</span><span class="sxs-lookup"><span data-stu-id="c005b-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c005b-121">Ссылка на из <a href="lync-server-2013-region-table.md">таблицы Region в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="c005b-121">Referenced from <a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

