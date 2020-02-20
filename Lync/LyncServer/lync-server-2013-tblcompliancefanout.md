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
ms.openlocfilehash: 283918b723d92aa138f1e8572665e4ef4920abdc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142155"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblcompliancefanout-in-lync-server-2013"></a><span data-ttu-id="c7057-102">tblComplianceFanout в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7057-102">tblComplianceFanout in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7057-103">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="c7057-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="c7057-104">tblComplianceFanout содержит все серверы, обработавшие событие соответствия.</span><span class="sxs-lookup"><span data-stu-id="c7057-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>

### <a name="columns"></a><span data-ttu-id="c7057-105">Columns</span><span class="sxs-lookup"><span data-stu-id="c7057-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7057-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="c7057-106">Column</span></span></th>
<th><span data-ttu-id="c7057-107">Тип</span><span class="sxs-lookup"><span data-stu-id="c7057-107">Type</span></span></th>
<th><span data-ttu-id="c7057-108">Описание</span><span class="sxs-lookup"><span data-stu-id="c7057-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7057-109">фанаутевентид</span><span class="sxs-lookup"><span data-stu-id="c7057-109">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="c7057-110">int</span><span class="sxs-lookup"><span data-stu-id="c7057-110">int</span></span></p></td>
<td><p><span data-ttu-id="c7057-111">Идентификатор события.</span><span class="sxs-lookup"><span data-stu-id="c7057-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7057-112">фанаутсерверид</span><span class="sxs-lookup"><span data-stu-id="c7057-112">fanoutServerID</span></span></p></td>
<td><p><span data-ttu-id="c7057-113">int</span><span class="sxs-lookup"><span data-stu-id="c7057-113">int</span></span></p></td>
<td><p><span data-ttu-id="c7057-114">Идентификатор сервера (в соответствии с таблицей tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="c7057-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="c7057-115">Key</span><span class="sxs-lookup"><span data-stu-id="c7057-115">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7057-116">Столбец</span><span class="sxs-lookup"><span data-stu-id="c7057-116">Column</span></span></th>
<th><span data-ttu-id="c7057-117">Описание</span><span class="sxs-lookup"><span data-stu-id="c7057-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7057-118">фанаутевентид</span><span class="sxs-lookup"><span data-stu-id="c7057-118">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="c7057-119">Внешний ключ с поиском в таблице tblComplianceData.cmplEventID.</span><span class="sxs-lookup"><span data-stu-id="c7057-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

