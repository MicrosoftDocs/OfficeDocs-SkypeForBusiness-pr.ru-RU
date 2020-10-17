---
title: 'Lync Server 2013: представление Таблица voipdetails'
description: 'Lync Server 2013: представление Таблица voipdetails.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VoIPDetails view
ms:assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687973(v=OCS.15)
ms:contentKeyID: 49733561
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ecd34be0c8568eef29d773f088e8503a8065743
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566205"
---
# <a name="voipdetails-view-in-lync-server-2013"></a><span data-ttu-id="a62b3-103">Представление Таблица voipdetails в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a62b3-103">VoIPDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a62b3-104">_**Последнее изменение темы:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="a62b3-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="a62b3-105">В представлении Таблица voipdetails хранятся сведения об одноранговых сеансах, где по крайней мере один пользователь является пользователем VoIP.</span><span class="sxs-lookup"><span data-stu-id="a62b3-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="a62b3-106">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a62b3-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a62b3-107">В представлении Таблица voipdetails содержатся все столбцы в <A href="lync-server-2013-sessiondetails-view.md">представлении SessionDetails в Lync Server 2013</A> , а также столбцы, перечисленные ниже.</span><span class="sxs-lookup"><span data-stu-id="a62b3-107">The VoIPDetails view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a62b3-108">Столбец</span><span class="sxs-lookup"><span data-stu-id="a62b3-108">Column</span></span></th>
<th><span data-ttu-id="a62b3-109">Тип данных</span><span class="sxs-lookup"><span data-stu-id="a62b3-109">Data Type</span></span></th>
<th><span data-ttu-id="a62b3-110">Сведения</span><span class="sxs-lookup"><span data-stu-id="a62b3-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a62b3-111"><strong>фромфоне</strong></span><span class="sxs-lookup"><span data-stu-id="a62b3-111"><strong>FromPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="a62b3-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a62b3-112">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a62b3-113">Универсальный код ресурса (URI) телефона пользователя, запустившего сеанс.</span><span class="sxs-lookup"><span data-stu-id="a62b3-113">Phone URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a62b3-114"><strong>тофоне</strong></span><span class="sxs-lookup"><span data-stu-id="a62b3-114"><strong>ToPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="a62b3-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a62b3-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a62b3-116">Универсальный код ресурса (URI) телефона пользователя, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="a62b3-116">Phone URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a62b3-117"><strong>дисконнектедбюри</strong></span><span class="sxs-lookup"><span data-stu-id="a62b3-117"><strong>DisconnectedByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a62b3-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a62b3-118">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a62b3-119">Универсальный код ресурса (URI) пользователя, который отключил сеанс.</span><span class="sxs-lookup"><span data-stu-id="a62b3-119">URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a62b3-120"><strong>дисконнектедбюритипе</strong></span><span class="sxs-lookup"><span data-stu-id="a62b3-120"><strong>DisconnectedByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="a62b3-121">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a62b3-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a62b3-122">Тип универсального кода ресурса (URI) пользователя, который отключил сеанс.</span><span class="sxs-lookup"><span data-stu-id="a62b3-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="a62b3-123">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a62b3-123">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a62b3-124"><strong>дисконнектедбитенант</strong></span><span class="sxs-lookup"><span data-stu-id="a62b3-124"><strong>DisconnectedByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="a62b3-125">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a62b3-125">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a62b3-126">Клиент пользователя, который отключил сеанс.</span><span class="sxs-lookup"><span data-stu-id="a62b3-126">Tenant of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a62b3-127"><strong>дисконнектедбифоне</strong></span><span class="sxs-lookup"><span data-stu-id="a62b3-127"><strong>DisconnectedByPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="a62b3-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a62b3-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a62b3-129">Универсальный код ресурса (URI) телефона пользователя, который отключил сеанс.</span><span class="sxs-lookup"><span data-stu-id="a62b3-129">Phone URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a62b3-130"><strong>фроммедиатионсервер</strong></span><span class="sxs-lookup"><span data-stu-id="a62b3-130"><strong>FromMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="a62b3-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a62b3-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a62b3-132">Сервер-посредник, используемый пользователем, запустившего сеанс.</span><span class="sxs-lookup"><span data-stu-id="a62b3-132">Mediation Server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a62b3-133"><strong>томедиатионсервер</strong></span><span class="sxs-lookup"><span data-stu-id="a62b3-133"><strong>ToMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="a62b3-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a62b3-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a62b3-135">Сервер-посредник, используемый пользователем, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="a62b3-135">Mediation Server used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a62b3-136"><strong>фромгатевай</strong></span><span class="sxs-lookup"><span data-stu-id="a62b3-136"><strong>FromGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="a62b3-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a62b3-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a62b3-138">Шлюз, используемый пользователем, запустившего сеанс.</span><span class="sxs-lookup"><span data-stu-id="a62b3-138">Gateway used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a62b3-139"><strong>тогатевай</strong></span><span class="sxs-lookup"><span data-stu-id="a62b3-139"><strong>ToGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="a62b3-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a62b3-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a62b3-141">Шлюз, используемый пользователем, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="a62b3-141">Gateway used by the user who joined the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

