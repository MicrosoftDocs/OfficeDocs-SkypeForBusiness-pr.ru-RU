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
ms.openlocfilehash: ebde759bceaf682384284cffb6a2ec710050126c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031203"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblactivepeers-in-lync-server-2013"></a><span data-ttu-id="a8f25-102">Тблактивепирс в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8f25-102">tblActivePeers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8f25-103">_**Последнее изменение темы:** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="a8f25-103">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="a8f25-104">Таблица tblActivePeers содержит текущие одноранговые соединения между службами чата.</span><span class="sxs-lookup"><span data-stu-id="a8f25-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>

### <a name="columns"></a><span data-ttu-id="a8f25-105">Columns</span><span class="sxs-lookup"><span data-stu-id="a8f25-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a8f25-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="a8f25-106">Column</span></span></th>
<th><span data-ttu-id="a8f25-107">Тип</span><span class="sxs-lookup"><span data-stu-id="a8f25-107">Type</span></span></th>
<th><span data-ttu-id="a8f25-108">Описание</span><span class="sxs-lookup"><span data-stu-id="a8f25-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a8f25-109">аплсерверид</span><span class="sxs-lookup"><span data-stu-id="a8f25-109">aplServerID</span></span></p></td>
<td><p><span data-ttu-id="a8f25-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="a8f25-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="a8f25-111">ИД сервера, добавившего запись.</span><span class="sxs-lookup"><span data-stu-id="a8f25-111">ID of the server that posted the entry.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8f25-112">аплпирид</span><span class="sxs-lookup"><span data-stu-id="a8f25-112">aplPeerID</span></span></p></td>
<td><p><span data-ttu-id="a8f25-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="a8f25-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="a8f25-114">ИД узла, к которому подключен сервер, добавивший запись.</span><span class="sxs-lookup"><span data-stu-id="a8f25-114">ID of the peer that the posting server is connected to.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="a8f25-115">Keys</span><span class="sxs-lookup"><span data-stu-id="a8f25-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a8f25-116">Столбец</span><span class="sxs-lookup"><span data-stu-id="a8f25-116">Column</span></span></th>
<th><span data-ttu-id="a8f25-117">Описание</span><span class="sxs-lookup"><span data-stu-id="a8f25-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a8f25-118">&lt;Аплсерверид, Аплпирид&gt;</span><span class="sxs-lookup"><span data-stu-id="a8f25-118">&lt;aplServerID, aplPeerID&gt;</span></span></p></td>
<td><p><span data-ttu-id="a8f25-119">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="a8f25-119">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8f25-120">аплсерверид</span><span class="sxs-lookup"><span data-stu-id="a8f25-120">aplServerID</span></span></p></td>
<td><p><span data-ttu-id="a8f25-121">Внешний ключ с поиском в таблице tblServerIdentity.serverID.</span><span class="sxs-lookup"><span data-stu-id="a8f25-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a8f25-122">аплпирид</span><span class="sxs-lookup"><span data-stu-id="a8f25-122">aplPeerID</span></span></p></td>
<td><p><span data-ttu-id="a8f25-123">Внешний ключ с поиском в таблице tblServerIdentity.serverID.</span><span class="sxs-lookup"><span data-stu-id="a8f25-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

