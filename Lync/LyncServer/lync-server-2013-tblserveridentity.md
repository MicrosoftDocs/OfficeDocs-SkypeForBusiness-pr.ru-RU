---
title: 'Lync Server 2013: tblServerIdentity'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblServerIdentity
ms:assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558648(v=OCS.15)
ms:contentKeyID: 48184125
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7bdd939f838a9f72191d3aae27b9a4a56d26be3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849521"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblserveridentity-in-lync-server-2013"></a><span data-ttu-id="4eb94-102">tblServerIdentity в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4eb94-102">tblServerIdentity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4eb94-103">_**Тема последнего изменения:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="4eb94-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="4eb94-104">Тблсерверидентити включает в себя серверы активных чатов в пуле серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="4eb94-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>

### <a name="columns"></a><span data-ttu-id="4eb94-105">Столбцов</span><span class="sxs-lookup"><span data-stu-id="4eb94-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4eb94-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="4eb94-106">Column</span></span></th>
<th><span data-ttu-id="4eb94-107">Тип</span><span class="sxs-lookup"><span data-stu-id="4eb94-107">Type</span></span></th>
<th><span data-ttu-id="4eb94-108">Описание</span><span class="sxs-lookup"><span data-stu-id="4eb94-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4eb94-109">Серверид</span><span class="sxs-lookup"><span data-stu-id="4eb94-109">serverID</span></span></p></td>
<td><p><span data-ttu-id="4eb94-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="4eb94-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="4eb94-111">Идентификатор сервера.</span><span class="sxs-lookup"><span data-stu-id="4eb94-111">Server ID.</span></span> <span data-ttu-id="4eb94-112">Соответствует ИДЕНТИФИКАТОРу экземпляра из хранилища центрального управления.</span><span class="sxs-lookup"><span data-stu-id="4eb94-112">Corresponds to the instance ID from Central Management store.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4eb94-113">Сервераддресс</span><span class="sxs-lookup"><span data-stu-id="4eb94-113">serverAddress</span></span></p></td>
<td><p><span data-ttu-id="4eb94-114">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="4eb94-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="4eb94-115">Адрес сервера с использованием адреса Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="4eb94-115">Server address using the Windows Communication Foundation address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4eb94-116">Серверластпингтиме</span><span class="sxs-lookup"><span data-stu-id="4eb94-116">serverLastPingTime</span></span></p></td>
<td><p><span data-ttu-id="4eb94-117">datetime</span><span class="sxs-lookup"><span data-stu-id="4eb94-117">datetime</span></span></p></td>
<td><p><span data-ttu-id="4eb94-118">Последнее время, в течение которого сервер канала обновил эту строку, чтобы дать свидетельство о том, что оно запущено.</span><span class="sxs-lookup"><span data-stu-id="4eb94-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="4eb94-119">Ключ</span><span class="sxs-lookup"><span data-stu-id="4eb94-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4eb94-120">Столбец</span><span class="sxs-lookup"><span data-stu-id="4eb94-120">Column</span></span></th>
<th><span data-ttu-id="4eb94-121">Описание</span><span class="sxs-lookup"><span data-stu-id="4eb94-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4eb94-122">Серверид</span><span class="sxs-lookup"><span data-stu-id="4eb94-122">serverID</span></span></p></td>
<td><p><span data-ttu-id="4eb94-123">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="4eb94-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

