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
ms.openlocfilehash: d107889b49ec16c51224b075a8fb7f7a7cec1b00
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731739"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="subnet-table-in-lync-server-2013"></a><span data-ttu-id="d8712-102">Таблица Subnet в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8712-102">Subnet table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8712-103">_**Тема последнего изменения:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="d8712-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="d8712-104">Таблица подсети является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="d8712-104">The Subnet table is a supporting table.</span></span> <span data-ttu-id="d8712-105">Каждая запись соответствует одной подсети, определенной в параметрах конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="d8712-105">Each record represents one subnet defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d8712-106"><strong>Столбец</strong></span><span class="sxs-lookup"><span data-stu-id="d8712-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d8712-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="d8712-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d8712-108"><strong>Ключ/индекс</strong></span><span class="sxs-lookup"><span data-stu-id="d8712-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d8712-109"><strong>Сведения</strong></span><span class="sxs-lookup"><span data-stu-id="d8712-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d8712-110"><strong>субнетип</strong></span><span class="sxs-lookup"><span data-stu-id="d8712-110"><strong>SubnetIP</strong></span></span></p></td>
<td><p><span data-ttu-id="d8712-111">целое</span><span class="sxs-lookup"><span data-stu-id="d8712-111">int</span></span></p></td>
<td><p><span data-ttu-id="d8712-112">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="d8712-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8712-113">Целочисленное представление для IP-адреса подсети.</span><span class="sxs-lookup"><span data-stu-id="d8712-113">Integer representation for the subnet IP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8712-114"><strong>Сети</strong></span><span class="sxs-lookup"><span data-stu-id="d8712-114"><strong>SubnetMask</strong></span></span></p></td>
<td><p><span data-ttu-id="d8712-115">целое</span><span class="sxs-lookup"><span data-stu-id="d8712-115">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d8712-116">Маска подсети.</span><span class="sxs-lookup"><span data-stu-id="d8712-116">Subnet mask.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8712-117"><strong>усерситекэй</strong></span><span class="sxs-lookup"><span data-stu-id="d8712-117"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="d8712-118">целое</span><span class="sxs-lookup"><span data-stu-id="d8712-118">int</span></span></p></td>
<td><p><span data-ttu-id="d8712-119">Другом</span><span class="sxs-lookup"><span data-stu-id="d8712-119">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8712-120">На которую ссылается <a href="lync-server-2013-usersite-table.md">Таблица усерсите в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d8712-120">Referenced from the <a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8712-121"><strong>субнетдескриптион</strong></span><span class="sxs-lookup"><span data-stu-id="d8712-121"><strong>SubnetDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="d8712-122">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="d8712-122">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d8712-123">Описание подсети.</span><span class="sxs-lookup"><span data-stu-id="d8712-123">The description for the subnet.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

