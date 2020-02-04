---
title: 'Lync Server 2013: поддержка маршрутизации на основе расположения клиентами и серверами'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client and server support for Location-Based Routing
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994024(v=OCS.15)
ms:contentKeyID: 51803933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ad7ead20eb9961180fec9204a84b3392b7fa96f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729859"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="db38d-102">Поддержка маршрутизации на основе расположения клиентами и серверами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db38d-102">Client and server support for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db38d-103">_**Тема последнего изменения:** 2013-06-18_</span><span class="sxs-lookup"><span data-stu-id="db38d-103">_**Topic Last Modified:** 2013-06-18_</span></span>

<span data-ttu-id="db38d-104">Маршрутизация на основе местоположения обеспечивается приложением Lync Server.</span><span class="sxs-lookup"><span data-stu-id="db38d-104">Location-Based Routing is enforced by Lync Server.</span></span> <span data-ttu-id="db38d-105">Lync Server может определять сетевые сайты, в которых пользователи подключаются из корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="db38d-105">Lync Server can identify the network sites where users are connecting from within the corporate network.</span></span> <span data-ttu-id="db38d-106">Расположение удаленных пользователей считается неизвестным, поскольку они находятся вне корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="db38d-106">Since remote users are outside the corporate network, their location is considered to be unknown.</span></span>

<div>

## <a name="lync-server-support"></a><span data-ttu-id="db38d-107">Поддержка Lync Server</span><span class="sxs-lookup"><span data-stu-id="db38d-107">Lync Server Support</span></span>

<span data-ttu-id="db38d-108">Для маршрутизации на основе местоположения требуется, чтобы Lync Server 2013 CU1 был развернут на всех пулах интерфейсных и стандартных серверах выпуска в заданной топологии.</span><span class="sxs-lookup"><span data-stu-id="db38d-108">Location-Based Routing requires that Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology.</span></span> <span data-ttu-id="db38d-109">Если Lync Server 2013 CU1 не установлен в некоторых компонентах Lync в топологии, ограничения на маршрутизацию с учетом расположения не могут быть полностью применены.</span><span class="sxs-lookup"><span data-stu-id="db38d-109">If Lync Server 2013 CU1 is not installed on certain Lync components in the topology, Location-Based Routing restrictions cannot be fully enforced.</span></span>

<span data-ttu-id="db38d-110">В следующей таблице указаны комбинации ролей сервера и версий, которые поддерживаются для маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="db38d-110">The following table identifies the combination of server roles and versions that is supported for Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db38d-111">Версия пула</span><span class="sxs-lookup"><span data-stu-id="db38d-111">Pool version</span></span></th>
<th><span data-ttu-id="db38d-112">Версия cервера-посредника</span><span class="sxs-lookup"><span data-stu-id="db38d-112">Mediation Server version</span></span></th>
<th><span data-ttu-id="db38d-113">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="db38d-113">Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db38d-114">Накопительное обновление для Lync Server 2013 за Февраль 2013</span><span class="sxs-lookup"><span data-stu-id="db38d-114">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="db38d-115">Накопительное обновление для Lync Server 2013 за Февраль 2013</span><span class="sxs-lookup"><span data-stu-id="db38d-115">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="db38d-116">Да</span><span class="sxs-lookup"><span data-stu-id="db38d-116">yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db38d-117">Накопительное обновление для Lync Server 2013 за Февраль 2013</span><span class="sxs-lookup"><span data-stu-id="db38d-117">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="db38d-118">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db38d-118">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="db38d-119">нет</span><span class="sxs-lookup"><span data-stu-id="db38d-119">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db38d-120">Накопительное обновление для Lync Server 2013 за Февраль 2013</span><span class="sxs-lookup"><span data-stu-id="db38d-120">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="db38d-121">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="db38d-121">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="db38d-122">нет</span><span class="sxs-lookup"><span data-stu-id="db38d-122">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db38d-123">Накопительное обновление для Lync Server 2013 за Февраль 2013</span><span class="sxs-lookup"><span data-stu-id="db38d-123">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="db38d-124">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="db38d-124">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="db38d-125">нет</span><span class="sxs-lookup"><span data-stu-id="db38d-125">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db38d-126">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db38d-126">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="db38d-127">любая</span><span class="sxs-lookup"><span data-stu-id="db38d-127">any</span></span></p></td>
<td><p><span data-ttu-id="db38d-128">нет</span><span class="sxs-lookup"><span data-stu-id="db38d-128">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db38d-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="db38d-129">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="db38d-130">любая</span><span class="sxs-lookup"><span data-stu-id="db38d-130">any</span></span></p></td>
<td><p><span data-ttu-id="db38d-131">нет</span><span class="sxs-lookup"><span data-stu-id="db38d-131">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db38d-132">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="db38d-132">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="db38d-133">любая</span><span class="sxs-lookup"><span data-stu-id="db38d-133">any</span></span></p></td>
<td><p><span data-ttu-id="db38d-134">нет</span><span class="sxs-lookup"><span data-stu-id="db38d-134">no</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="db38d-135">Поддержка клиента Lync</span><span class="sxs-lookup"><span data-stu-id="db38d-135">Lync Client Support</span></span>

<span data-ttu-id="db38d-136">В следующей таблице указаны клиенты, которые поддерживают маршрутизацию с учетом расположения.</span><span class="sxs-lookup"><span data-stu-id="db38d-136">The following table identifies the clients that Location-Based Routing supports.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db38d-137">Тип клиента</span><span class="sxs-lookup"><span data-stu-id="db38d-137">Client type</span></span></th>
<th><span data-ttu-id="db38d-138">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="db38d-138">Supported</span></span></th>
<th><span data-ttu-id="db38d-139">Сведения</span><span class="sxs-lookup"><span data-stu-id="db38d-139">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db38d-140">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="db38d-140">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="db38d-141">Да</span><span class="sxs-lookup"><span data-stu-id="db38d-141">yes</span></span></p></td>
<td><p><span data-ttu-id="db38d-142">В том числе накопительное обновление для Lync 2013 за Февраль 2013</span><span class="sxs-lookup"><span data-stu-id="db38d-142">Including Lync 2013 February 2013 Cumulative Update</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db38d-143">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="db38d-143">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="db38d-144">Да</span><span class="sxs-lookup"><span data-stu-id="db38d-144">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db38d-145">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="db38d-145">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="db38d-146">нет</span><span class="sxs-lookup"><span data-stu-id="db38d-146">no</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db38d-147">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="db38d-147">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="db38d-148">Да</span><span class="sxs-lookup"><span data-stu-id="db38d-148">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db38d-149">Lync Attendant</span><span class="sxs-lookup"><span data-stu-id="db38d-149">Lync Attendant</span></span></p></td>
<td><p><span data-ttu-id="db38d-150">Да</span><span class="sxs-lookup"><span data-stu-id="db38d-150">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db38d-151">Lync для Windows 8</span><span class="sxs-lookup"><span data-stu-id="db38d-151">Lync for Windows 8</span></span></p></td>
<td><p><span data-ttu-id="db38d-152">нет</span><span class="sxs-lookup"><span data-stu-id="db38d-152">no</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db38d-153">Lync Mobile 2013</span><span class="sxs-lookup"><span data-stu-id="db38d-153">Lync Mobile 2013</span></span></p></td>
<td><p><span data-ttu-id="db38d-154">нет</span><span class="sxs-lookup"><span data-stu-id="db38d-154">no</span></span></p></td>
<td><p><span data-ttu-id="db38d-155">Для клиентов Lync Mobile 2013 необходимо отключить VoIP, если они используются пользователями, для которых включена маршрутизация на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="db38d-155">VoIP must be disabled for Lync Mobile 2013 clients if used by users with Location-Based Routing enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db38d-156">Lync Mobile 2010</span><span class="sxs-lookup"><span data-stu-id="db38d-156">Lync Mobile 2010</span></span></p></td>
<td><p><span data-ttu-id="db38d-157">Да</span><span class="sxs-lookup"><span data-stu-id="db38d-157">yes</span></span></p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> <span data-ttu-id="db38d-158">Чтобы отключить VoIP для клиентов Lync Mobile 2013, назначьте политику мобильности с параметром, IP аудио-и видеофайлы, отключенными для всех пользователей, для которых включена маршрутизация на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="db38d-158">To disable VoIP for Lync Mobile 2013 clients, assign a mobility policy with the setting, IP Audio/Video, disabled for all users enabled for Location Based Routing.</span></span> <span data-ttu-id="db38d-159">Более подробно о политике мобильности см. в разделе <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span><span class="sxs-lookup"><span data-stu-id="db38d-159">For more details about mobility policy, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="db38d-160">См. также</span><span class="sxs-lookup"><span data-stu-id="db38d-160">See Also</span></span>


[<span data-ttu-id="db38d-161">Планирование маршрутизации на основе местоположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db38d-161">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

