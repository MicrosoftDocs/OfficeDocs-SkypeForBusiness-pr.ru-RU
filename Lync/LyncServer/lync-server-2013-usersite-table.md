---
title: 'Lync Server 2013: таблица таблица usersite'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserSite table
ms:assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398256(v=OCS.15)
ms:contentKeyID: 48183552
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 656bf8f692617392db02e186fcccebba25a01b0d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530006"
---
# <a name="usersite-table-in-lync-server-2013"></a><span data-ttu-id="e37c0-102">Таблица Таблица usersite в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e37c0-102">UserSite table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e37c0-103">_**Последнее изменение темы:** 2010-11-09_</span><span class="sxs-lookup"><span data-stu-id="e37c0-103">_**Topic Last Modified:** 2010-11-09_</span></span>

<span data-ttu-id="e37c0-104">Таблица Таблица usersite является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="e37c0-104">The UserSite table is a supporting table.</span></span> <span data-ttu-id="e37c0-105">Каждая запись представляет один сайт пользователя, определенный в параметрах конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="e37c0-105">Each record represents one user site defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e37c0-106"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="e37c0-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e37c0-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="e37c0-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e37c0-108"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="e37c0-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e37c0-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="e37c0-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e37c0-110"><strong>усерситекэй</strong></span><span class="sxs-lookup"><span data-stu-id="e37c0-110"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="e37c0-111">int</span><span class="sxs-lookup"><span data-stu-id="e37c0-111">int</span></span></p></td>
<td><p><span data-ttu-id="e37c0-112">Primary</span><span class="sxs-lookup"><span data-stu-id="e37c0-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="e37c0-113">Уникальный номер, идентифицирующий сайт пользователя.</span><span class="sxs-lookup"><span data-stu-id="e37c0-113">Unique number identifying the user site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e37c0-114"><strong>усерситенаме</strong></span><span class="sxs-lookup"><span data-stu-id="e37c0-114"><strong>UserSiteName</strong></span></span></p></td>
<td><p><span data-ttu-id="e37c0-115">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e37c0-115">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e37c0-116">Уникальные</span><span class="sxs-lookup"><span data-stu-id="e37c0-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="e37c0-117">Имя сайта пользователя.</span><span class="sxs-lookup"><span data-stu-id="e37c0-117">User site’s name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e37c0-118"><strong>регионкэй</strong></span><span class="sxs-lookup"><span data-stu-id="e37c0-118"><strong>RegionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="e37c0-119">int</span><span class="sxs-lookup"><span data-stu-id="e37c0-119">int</span></span></p></td>
<td><p><span data-ttu-id="e37c0-120">Правительства</span><span class="sxs-lookup"><span data-stu-id="e37c0-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e37c0-121">Ссылка из <a href="lync-server-2013-region-table.md">таблицы Region в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e37c0-121">Referenced from <a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

