---
title: 'Lync Server 2013: tblComplianceFanout'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceFanout
ms:assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615050(v=OCS.15)
ms:contentKeyID: 48185828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bb9ab36bbbec83ea706231d2a3fa6dd890fb1e7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblcompliancefanout-in-lync-server-2013"></a><span data-ttu-id="64bd2-102">tblComplianceFanout в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64bd2-102">tblComplianceFanout in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64bd2-103">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="64bd2-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="64bd2-104">tblComplianceFanout содержит все серверы, обработавшие событие соответствия.</span><span class="sxs-lookup"><span data-stu-id="64bd2-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>

### <a name="columns"></a><span data-ttu-id="64bd2-105">Columns</span><span class="sxs-lookup"><span data-stu-id="64bd2-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="64bd2-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="64bd2-106">Column</span></span></th>
<th><span data-ttu-id="64bd2-107">Тип</span><span class="sxs-lookup"><span data-stu-id="64bd2-107">Type</span></span></th>
<th><span data-ttu-id="64bd2-108">Описание</span><span class="sxs-lookup"><span data-stu-id="64bd2-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="64bd2-109">фанаутевентид</span><span class="sxs-lookup"><span data-stu-id="64bd2-109">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="64bd2-110">int</span><span class="sxs-lookup"><span data-stu-id="64bd2-110">int</span></span></p></td>
<td><p><span data-ttu-id="64bd2-111">Идентификатор события.</span><span class="sxs-lookup"><span data-stu-id="64bd2-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64bd2-112">фанаутсерверид</span><span class="sxs-lookup"><span data-stu-id="64bd2-112">fanoutServerID</span></span></p></td>
<td><p><span data-ttu-id="64bd2-113">int</span><span class="sxs-lookup"><span data-stu-id="64bd2-113">int</span></span></p></td>
<td><p><span data-ttu-id="64bd2-114">Идентификатор сервера (в соответствии с таблицей tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="64bd2-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="64bd2-115">Key</span><span class="sxs-lookup"><span data-stu-id="64bd2-115">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="64bd2-116">Столбец</span><span class="sxs-lookup"><span data-stu-id="64bd2-116">Column</span></span></th>
<th><span data-ttu-id="64bd2-117">Описание</span><span class="sxs-lookup"><span data-stu-id="64bd2-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="64bd2-118">фанаутевентид</span><span class="sxs-lookup"><span data-stu-id="64bd2-118">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="64bd2-119">Внешний ключ с поиском в таблице tblComplianceData.cmplEventID.</span><span class="sxs-lookup"><span data-stu-id="64bd2-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

