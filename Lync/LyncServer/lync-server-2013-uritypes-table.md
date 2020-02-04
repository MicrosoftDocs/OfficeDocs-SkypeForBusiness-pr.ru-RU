---
title: 'Lync Server 2013: таблица UriTypes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UriTypes table
ms:assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398587(v=OCS.15)
ms:contentKeyID: 48184553
ms.date: 06/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6f1de8d9ae54a71a04e90a914edbd779aa3e41d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744649"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="uritypes-table-in-lync-server-2013"></a><span data-ttu-id="86035-102">Таблица UriTypes в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86035-102">UriTypes table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86035-103">_**Тема последнего изменения:** 2015-06-16_</span><span class="sxs-lookup"><span data-stu-id="86035-103">_**Topic Last Modified:** 2015-06-16_</span></span>

<span data-ttu-id="86035-104">В таблице Уритипес содержатся различные типы URI (универсального идентификатора ресурса), отслеживаемые в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="86035-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86035-105">Столбец</span><span class="sxs-lookup"><span data-stu-id="86035-105">Column</span></span></th>
<th><span data-ttu-id="86035-106">Тип данных</span><span class="sxs-lookup"><span data-stu-id="86035-106">Data Type</span></span></th>
<th><span data-ttu-id="86035-107">Ключ/индекс</span><span class="sxs-lookup"><span data-stu-id="86035-107">Key/Index</span></span></th>
<th><span data-ttu-id="86035-108">Сведения</span><span class="sxs-lookup"><span data-stu-id="86035-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86035-109"><strong>уритипеид</strong></span><span class="sxs-lookup"><span data-stu-id="86035-109"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="86035-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="86035-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="86035-111">Primary</span><span class="sxs-lookup"><span data-stu-id="86035-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="86035-112">Уникальный идентификатор, присвоенный типу URI.</span><span class="sxs-lookup"><span data-stu-id="86035-112">Unique identifier assigned to a URI type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86035-113"><strong>уритипе</strong></span><span class="sxs-lookup"><span data-stu-id="86035-113"><strong>UriType</strong></span></span></p></td>
<td><p><span data-ttu-id="86035-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="86035-114">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86035-115">Описание различных типов URI.</span><span class="sxs-lookup"><span data-stu-id="86035-115">Descriptions of the different URI types.</span></span> <span data-ttu-id="86035-116">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="86035-116">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="86035-117">1 – универсальный код ресурса (URI)</span><span class="sxs-lookup"><span data-stu-id="86035-117">1 – Phone Uri</span></span></p></li>
<li><p><span data-ttu-id="86035-118">0 — URI пользователя</span><span class="sxs-lookup"><span data-stu-id="86035-118">0 – User Uri</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

