---
title: 'Lync Server 2013: таблица Subnet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Subnet table
ms:assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398582(v=OCS.15)
ms:contentKeyID: 48184544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d684efa2d4bd68880a3838893e5c5cfe2a1a3cc2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519436"
---
# <a name="subnet-table-in-lync-server-2013"></a><span data-ttu-id="290d0-102">Таблица Subnet в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="290d0-102">Subnet table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="290d0-103">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="290d0-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="290d0-p101">Таблица Subnet является вспомогательной. Каждая запись представляет одну подсеть, определенную в параметрах конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="290d0-p101">The Subnet table is a supporting table. Each record represents one subnet defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="290d0-106"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="290d0-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="290d0-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="290d0-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="290d0-108"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="290d0-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="290d0-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="290d0-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="290d0-110"><strong>субнетип</strong></span><span class="sxs-lookup"><span data-stu-id="290d0-110"><strong>SubnetIP</strong></span></span></p></td>
<td><p><span data-ttu-id="290d0-111">int</span><span class="sxs-lookup"><span data-stu-id="290d0-111">int</span></span></p></td>
<td><p><span data-ttu-id="290d0-112">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="290d0-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="290d0-113">Целочисленное представление IP-адреса подсети.</span><span class="sxs-lookup"><span data-stu-id="290d0-113">Integer representation for the subnet IP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="290d0-114"><strong>Сети</strong></span><span class="sxs-lookup"><span data-stu-id="290d0-114"><strong>SubnetMask</strong></span></span></p></td>
<td><p><span data-ttu-id="290d0-115">int</span><span class="sxs-lookup"><span data-stu-id="290d0-115">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="290d0-116">Маска подсети.</span><span class="sxs-lookup"><span data-stu-id="290d0-116">Subnet mask.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="290d0-117"><strong>усерситекэй</strong></span><span class="sxs-lookup"><span data-stu-id="290d0-117"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="290d0-118">int</span><span class="sxs-lookup"><span data-stu-id="290d0-118">int</span></span></p></td>
<td><p><span data-ttu-id="290d0-119">Правительства</span><span class="sxs-lookup"><span data-stu-id="290d0-119">Foreign</span></span></p></td>
<td><p><span data-ttu-id="290d0-120">Ссылка из <a href="lync-server-2013-usersite-table.md">таблицы таблица usersite в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="290d0-120">Referenced from the <a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="290d0-121"><strong>субнетдескриптион</strong></span><span class="sxs-lookup"><span data-stu-id="290d0-121"><strong>SubnetDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="290d0-122">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="290d0-122">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="290d0-123">Описание подсети.</span><span class="sxs-lookup"><span data-stu-id="290d0-123">The description for the subnet.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

