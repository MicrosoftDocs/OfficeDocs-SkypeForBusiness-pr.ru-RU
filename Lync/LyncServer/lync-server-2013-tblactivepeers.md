---
title: 'Lync Server 2013: Тблактивепирс'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblActivePeers
ms:assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615030(v=OCS.15)
ms:contentKeyID: 48185176
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a47ac4368dd424b08cfb47c6d867bc20144e45c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192132"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblactivepeers-in-lync-server-2013"></a><span data-ttu-id="de7d6-102">Тблактивепирс в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de7d6-102">tblActivePeers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de7d6-103">_**Последнее изменение темы:** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="de7d6-103">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="de7d6-104">Таблица tblActivePeers содержит текущие одноранговые соединения между службами чата.</span><span class="sxs-lookup"><span data-stu-id="de7d6-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>

### <a name="columns"></a><span data-ttu-id="de7d6-105">Columns</span><span class="sxs-lookup"><span data-stu-id="de7d6-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="de7d6-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="de7d6-106">Column</span></span></th>
<th><span data-ttu-id="de7d6-107">Тип</span><span class="sxs-lookup"><span data-stu-id="de7d6-107">Type</span></span></th>
<th><span data-ttu-id="de7d6-108">Описание</span><span class="sxs-lookup"><span data-stu-id="de7d6-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="de7d6-109">аплсерверид</span><span class="sxs-lookup"><span data-stu-id="de7d6-109">aplServerID</span></span></p></td>
<td><p><span data-ttu-id="de7d6-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="de7d6-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="de7d6-111">ИД сервера, добавившего запись.</span><span class="sxs-lookup"><span data-stu-id="de7d6-111">ID of the server that posted the entry.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de7d6-112">аплпирид</span><span class="sxs-lookup"><span data-stu-id="de7d6-112">aplPeerID</span></span></p></td>
<td><p><span data-ttu-id="de7d6-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="de7d6-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="de7d6-114">ИД узла, к которому подключен сервер, добавивший запись.</span><span class="sxs-lookup"><span data-stu-id="de7d6-114">ID of the peer that the posting server is connected to.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="de7d6-115">Keys</span><span class="sxs-lookup"><span data-stu-id="de7d6-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="de7d6-116">Столбец</span><span class="sxs-lookup"><span data-stu-id="de7d6-116">Column</span></span></th>
<th><span data-ttu-id="de7d6-117">Описание</span><span class="sxs-lookup"><span data-stu-id="de7d6-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="de7d6-118">&lt;Аплсерверид, Аплпирид&gt;</span><span class="sxs-lookup"><span data-stu-id="de7d6-118">&lt;aplServerID, aplPeerID&gt;</span></span></p></td>
<td><p><span data-ttu-id="de7d6-119">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="de7d6-119">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de7d6-120">аплсерверид</span><span class="sxs-lookup"><span data-stu-id="de7d6-120">aplServerID</span></span></p></td>
<td><p><span data-ttu-id="de7d6-121">Внешний ключ с поиском в таблице tblServerIdentity.serverID.</span><span class="sxs-lookup"><span data-stu-id="de7d6-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de7d6-122">аплпирид</span><span class="sxs-lookup"><span data-stu-id="de7d6-122">aplPeerID</span></span></p></td>
<td><p><span data-ttu-id="de7d6-123">Внешний ключ с поиском в таблице tblServerIdentity.serverID.</span><span class="sxs-lookup"><span data-stu-id="de7d6-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

