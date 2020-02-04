---
title: 'Lync Server 2013: представление Воипдетаилс'
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
ms.openlocfilehash: db65da0af7c34d1121e97436af47750186706b68
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-view-in-lync-server-2013"></a><span data-ttu-id="fa741-102">Воипдетаилс представления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa741-102">VoIPDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa741-103">_**Тема последнего изменения:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="fa741-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="fa741-104">В представлении Воипдетаилс хранятся сведения о одноранговых сеансах, где по крайней мере один пользователь является пользователем VoIP.</span><span class="sxs-lookup"><span data-stu-id="fa741-104">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="fa741-105">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fa741-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fa741-106">В представлении Воипдетаилс содержатся все столбцы в <A href="lync-server-2013-sessiondetails-view.md">представлении сессиондетаилс в Lync Server 2013</A> в дополнение к столбцам, перечисленным ниже.</span><span class="sxs-lookup"><span data-stu-id="fa741-106">The VoIPDetails view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa741-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="fa741-107">Column</span></span></th>
<th><span data-ttu-id="fa741-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="fa741-108">Data Type</span></span></th>
<th><span data-ttu-id="fa741-109">Подробности</span><span class="sxs-lookup"><span data-stu-id="fa741-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa741-110"><strong>фромфоне</strong></span><span class="sxs-lookup"><span data-stu-id="fa741-110"><strong>FromPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="fa741-111">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fa741-111">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fa741-112">URI телефона пользователя, запустившего сеанс.</span><span class="sxs-lookup"><span data-stu-id="fa741-112">Phone URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa741-113"><strong>тофоне</strong></span><span class="sxs-lookup"><span data-stu-id="fa741-113"><strong>ToPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="fa741-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fa741-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fa741-115">Универсальный код ресурса (URI) пользователя, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="fa741-115">Phone URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa741-116"><strong>дисконнектедбюри</strong></span><span class="sxs-lookup"><span data-stu-id="fa741-116"><strong>DisconnectedByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="fa741-117">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fa741-117">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fa741-118">Универсальный код ресурса (URI) пользователя, который отключил сеанс.</span><span class="sxs-lookup"><span data-stu-id="fa741-118">URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa741-119"><strong>дисконнектедбюритипе</strong></span><span class="sxs-lookup"><span data-stu-id="fa741-119"><strong>DisconnectedByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="fa741-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fa741-120">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fa741-121">Тип URI пользователя, который отключил сеанс.</span><span class="sxs-lookup"><span data-stu-id="fa741-121">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="fa741-122">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fa741-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa741-123"><strong>дисконнектедбитенант</strong></span><span class="sxs-lookup"><span data-stu-id="fa741-123"><strong>DisconnectedByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="fa741-124">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fa741-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fa741-125">Клиент пользователя, который отключил сеанс.</span><span class="sxs-lookup"><span data-stu-id="fa741-125">Tenant of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa741-126"><strong>дисконнектедбифоне</strong></span><span class="sxs-lookup"><span data-stu-id="fa741-126"><strong>DisconnectedByPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="fa741-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fa741-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fa741-128">Универсальный код ресурса (URI) пользователя, который отключил сеанс.</span><span class="sxs-lookup"><span data-stu-id="fa741-128">Phone URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa741-129"><strong>фроммедиатионсервер</strong></span><span class="sxs-lookup"><span data-stu-id="fa741-129"><strong>FromMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="fa741-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fa741-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fa741-131">Сервер исправлений, используемый пользователем, который запустил сеанс.</span><span class="sxs-lookup"><span data-stu-id="fa741-131">Mediation Server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa741-132"><strong>томедиатионсервер</strong></span><span class="sxs-lookup"><span data-stu-id="fa741-132"><strong>ToMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="fa741-133">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fa741-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fa741-134">Сервер исправлений, используемый пользователем, который присоединил сеанс.</span><span class="sxs-lookup"><span data-stu-id="fa741-134">Mediation Server used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa741-135"><strong>фромгатевай</strong></span><span class="sxs-lookup"><span data-stu-id="fa741-135"><strong>FromGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="fa741-136">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fa741-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fa741-137">Шлюз, используемый пользователем, который запустил сеанс.</span><span class="sxs-lookup"><span data-stu-id="fa741-137">Gateway used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa741-138"><strong>тогатевай</strong></span><span class="sxs-lookup"><span data-stu-id="fa741-138"><strong>ToGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="fa741-139">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fa741-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fa741-140">Шлюз, используемый пользователем, который присоединился к сеансу.</span><span class="sxs-lookup"><span data-stu-id="fa741-140">Gateway used by the user who joined the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

