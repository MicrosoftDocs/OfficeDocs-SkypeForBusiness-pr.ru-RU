---
title: 'Lync Server 2013: tblServerIdentity'
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
ms.openlocfilehash: 5f6ed7f0eed08dbb4ab3b0d6f41c9ec91fb719f1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblserveridentity-in-lync-server-2013"></a><span data-ttu-id="11bd2-102">tblServerIdentity в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11bd2-102">tblServerIdentity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11bd2-103">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="11bd2-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="11bd2-104">tblServerIdentity содержит активные серверы чата в пуле серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="11bd2-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>

### <a name="columns"></a><span data-ttu-id="11bd2-105">Columns</span><span class="sxs-lookup"><span data-stu-id="11bd2-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11bd2-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="11bd2-106">Column</span></span></th>
<th><span data-ttu-id="11bd2-107">Тип</span><span class="sxs-lookup"><span data-stu-id="11bd2-107">Type</span></span></th>
<th><span data-ttu-id="11bd2-108">Описание</span><span class="sxs-lookup"><span data-stu-id="11bd2-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11bd2-109">serverID</span><span class="sxs-lookup"><span data-stu-id="11bd2-109">serverID</span></span></p></td>
<td><p><span data-ttu-id="11bd2-110">целое, не равно null</span><span class="sxs-lookup"><span data-stu-id="11bd2-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="11bd2-111">Идентификатор сервера.</span><span class="sxs-lookup"><span data-stu-id="11bd2-111">Server ID.</span></span> <span data-ttu-id="11bd2-112">Соответствует ИДЕНТИФИКАТОРу экземпляра из центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="11bd2-112">Corresponds to the instance ID from Central Management store.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11bd2-113">сервераддресс</span><span class="sxs-lookup"><span data-stu-id="11bd2-113">serverAddress</span></span></p></td>
<td><p><span data-ttu-id="11bd2-114">nvarchar (256), не равно null</span><span class="sxs-lookup"><span data-stu-id="11bd2-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="11bd2-115">Адрес сервера с использованием адреса платформы Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="11bd2-115">Server address using the Windows Communication Foundation address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11bd2-116">серверластпингтиме</span><span class="sxs-lookup"><span data-stu-id="11bd2-116">serverLastPingTime</span></span></p></td>
<td><p><span data-ttu-id="11bd2-117">datetime</span><span class="sxs-lookup"><span data-stu-id="11bd2-117">datetime</span></span></p></td>
<td><p><span data-ttu-id="11bd2-118">Время последнего обновления этой строки сервером канала для подтверждения функционирования.</span><span class="sxs-lookup"><span data-stu-id="11bd2-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="11bd2-119">Key</span><span class="sxs-lookup"><span data-stu-id="11bd2-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11bd2-120">Столбец</span><span class="sxs-lookup"><span data-stu-id="11bd2-120">Column</span></span></th>
<th><span data-ttu-id="11bd2-121">Описание</span><span class="sxs-lookup"><span data-stu-id="11bd2-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11bd2-122">serverID</span><span class="sxs-lookup"><span data-stu-id="11bd2-122">serverID</span></span></p></td>
<td><p><span data-ttu-id="11bd2-123">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="11bd2-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

