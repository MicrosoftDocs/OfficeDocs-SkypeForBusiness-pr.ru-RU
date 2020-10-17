---
title: 'Lync Server 2013: tblServerIdentity'
description: 'Lync Server 2013: tblServerIdentity.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblServerIdentity
ms:assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558648(v=OCS.15)
ms:contentKeyID: 48184125
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e954618cb373f2cf4f1b7ed929c3aaf6d8875e92
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564535"
---
# <a name="tblserveridentity-in-lync-server-2013"></a><span data-ttu-id="bdbce-103">tblServerIdentity в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdbce-103">tblServerIdentity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bdbce-104">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="bdbce-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="bdbce-105">tblServerIdentity содержит активные серверы чата в пуле серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="bdbce-105">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>

### <a name="columns"></a><span data-ttu-id="bdbce-106">Столбцы</span><span class="sxs-lookup"><span data-stu-id="bdbce-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bdbce-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="bdbce-107">Column</span></span></th>
<th><span data-ttu-id="bdbce-108">Тип</span><span class="sxs-lookup"><span data-stu-id="bdbce-108">Type</span></span></th>
<th><span data-ttu-id="bdbce-109">Описание</span><span class="sxs-lookup"><span data-stu-id="bdbce-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bdbce-110">serverID</span><span class="sxs-lookup"><span data-stu-id="bdbce-110">serverID</span></span></p></td>
<td><p><span data-ttu-id="bdbce-111">целое, не равно null</span><span class="sxs-lookup"><span data-stu-id="bdbce-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="bdbce-112">Идентификатор сервера.</span><span class="sxs-lookup"><span data-stu-id="bdbce-112">Server ID.</span></span> <span data-ttu-id="bdbce-113">Соответствует ИДЕНТИФИКАТОРу экземпляра из центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="bdbce-113">Corresponds to the instance ID from Central Management store.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdbce-114">сервераддресс</span><span class="sxs-lookup"><span data-stu-id="bdbce-114">serverAddress</span></span></p></td>
<td><p><span data-ttu-id="bdbce-115">nvarchar (256), не равно null</span><span class="sxs-lookup"><span data-stu-id="bdbce-115">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="bdbce-116">Адрес сервера с использованием адреса платформы Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="bdbce-116">Server address using the Windows Communication Foundation address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdbce-117">серверластпингтиме</span><span class="sxs-lookup"><span data-stu-id="bdbce-117">serverLastPingTime</span></span></p></td>
<td><p><span data-ttu-id="bdbce-118">datetime</span><span class="sxs-lookup"><span data-stu-id="bdbce-118">datetime</span></span></p></td>
<td><p><span data-ttu-id="bdbce-119">Время последнего обновления этой строки сервером канала для подтверждения функционирования.</span><span class="sxs-lookup"><span data-stu-id="bdbce-119">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="bdbce-120">Key</span><span class="sxs-lookup"><span data-stu-id="bdbce-120">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bdbce-121">Столбец</span><span class="sxs-lookup"><span data-stu-id="bdbce-121">Column</span></span></th>
<th><span data-ttu-id="bdbce-122">Описание</span><span class="sxs-lookup"><span data-stu-id="bdbce-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bdbce-123">serverID</span><span class="sxs-lookup"><span data-stu-id="bdbce-123">serverID</span></span></p></td>
<td><p><span data-ttu-id="bdbce-124">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="bdbce-124">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

