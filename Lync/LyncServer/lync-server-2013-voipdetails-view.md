---
title: 'Lync Server 2013: представление Таблица voipdetails'
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
ms.openlocfilehash: 7911a203a46d9bfa5698d01dc43c27c5f789c89a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210923"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="voipdetails-view-in-lync-server-2013"></a><span data-ttu-id="34572-102">Представление Таблица voipdetails в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34572-102">VoIPDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34572-103">_**Последнее изменение темы:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="34572-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="34572-104">В представлении Таблица voipdetails хранятся сведения об одноранговых сеансах, где по крайней мере один пользователь является пользователем VoIP.</span><span class="sxs-lookup"><span data-stu-id="34572-104">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="34572-105">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="34572-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="34572-106">В представлении Таблица voipdetails содержатся все столбцы в <A href="lync-server-2013-sessiondetails-view.md">представлении SessionDetails в Lync Server 2013</A> , а также столбцы, перечисленные ниже.</span><span class="sxs-lookup"><span data-stu-id="34572-106">The VoIPDetails view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="34572-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="34572-107">Column</span></span></th>
<th><span data-ttu-id="34572-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="34572-108">Data Type</span></span></th>
<th><span data-ttu-id="34572-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="34572-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="34572-110"><strong>фромфоне</strong></span><span class="sxs-lookup"><span data-stu-id="34572-110"><strong>FromPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="34572-111">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="34572-111">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="34572-112">Универсальный код ресурса (URI) телефона пользователя, запустившего сеанс.</span><span class="sxs-lookup"><span data-stu-id="34572-112">Phone URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34572-113"><strong>тофоне</strong></span><span class="sxs-lookup"><span data-stu-id="34572-113"><strong>ToPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="34572-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="34572-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="34572-115">Универсальный код ресурса (URI) телефона пользователя, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="34572-115">Phone URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34572-116"><strong>дисконнектедбюри</strong></span><span class="sxs-lookup"><span data-stu-id="34572-116"><strong>DisconnectedByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="34572-117">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="34572-117">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="34572-118">Универсальный код ресурса (URI) пользователя, который отключил сеанс.</span><span class="sxs-lookup"><span data-stu-id="34572-118">URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34572-119"><strong>дисконнектедбюритипе</strong></span><span class="sxs-lookup"><span data-stu-id="34572-119"><strong>DisconnectedByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="34572-120">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="34572-120">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34572-121">Тип универсального кода ресурса (URI) пользователя, который отключил сеанс.</span><span class="sxs-lookup"><span data-stu-id="34572-121">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="34572-122">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="34572-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34572-123"><strong>дисконнектедбитенант</strong></span><span class="sxs-lookup"><span data-stu-id="34572-123"><strong>DisconnectedByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="34572-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="34572-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34572-125">Клиент пользователя, который отключил сеанс.</span><span class="sxs-lookup"><span data-stu-id="34572-125">Tenant of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34572-126"><strong>дисконнектедбифоне</strong></span><span class="sxs-lookup"><span data-stu-id="34572-126"><strong>DisconnectedByPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="34572-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="34572-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="34572-128">Универсальный код ресурса (URI) телефона пользователя, который отключил сеанс.</span><span class="sxs-lookup"><span data-stu-id="34572-128">Phone URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34572-129"><strong>фроммедиатионсервер</strong></span><span class="sxs-lookup"><span data-stu-id="34572-129"><strong>FromMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="34572-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="34572-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34572-131">Сервер-посредник, используемый пользователем, запустившего сеанс.</span><span class="sxs-lookup"><span data-stu-id="34572-131">Mediation Server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34572-132"><strong>томедиатионсервер</strong></span><span class="sxs-lookup"><span data-stu-id="34572-132"><strong>ToMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="34572-133">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="34572-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34572-134">Сервер-посредник, используемый пользователем, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="34572-134">Mediation Server used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34572-135"><strong>фромгатевай</strong></span><span class="sxs-lookup"><span data-stu-id="34572-135"><strong>FromGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="34572-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="34572-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34572-137">Шлюз, используемый пользователем, запустившего сеанс.</span><span class="sxs-lookup"><span data-stu-id="34572-137">Gateway used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34572-138"><strong>тогатевай</strong></span><span class="sxs-lookup"><span data-stu-id="34572-138"><strong>ToGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="34572-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="34572-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34572-140">Шлюз, используемый пользователем, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="34572-140">Gateway used by the user who joined the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

