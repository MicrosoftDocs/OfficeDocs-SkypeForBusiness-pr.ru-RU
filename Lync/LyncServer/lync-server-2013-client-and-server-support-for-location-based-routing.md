---
title: 'Lync Server 2013: поддержка маршрутизации на основе расположения клиентами и серверами'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Client and server support for Location-Based Routing
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994024(v=OCS.15)
ms:contentKeyID: 51803933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3791b359422c4b5bef463a612db6f0b74c07f096
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841565"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="3be0c-102">Поддержка маршрутизации на основе расположения клиентами и серверами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3be0c-102">Client and server support for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3be0c-103">_**Тема последнего изменения:** 2013-06-18_</span><span class="sxs-lookup"><span data-stu-id="3be0c-103">_**Topic Last Modified:** 2013-06-18_</span></span>

<span data-ttu-id="3be0c-104">Маршрутизация на основе местоположения обеспечивается приложением Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3be0c-104">Location-Based Routing is enforced by Lync Server.</span></span> <span data-ttu-id="3be0c-105">Lync Server может определять сетевые сайты, в которых пользователи подключаются из корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="3be0c-105">Lync Server can identify the network sites where users are connecting from within the corporate network.</span></span> <span data-ttu-id="3be0c-106">Расположение удаленных пользователей считается неизвестным, поскольку они находятся вне корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="3be0c-106">Since remote users are outside the corporate network, their location is considered to be unknown.</span></span>

<div>

## <a name="lync-server-support"></a><span data-ttu-id="3be0c-107">Поддержка Lync Server</span><span class="sxs-lookup"><span data-stu-id="3be0c-107">Lync Server Support</span></span>

<span data-ttu-id="3be0c-108">Для маршрутизации на основе местоположения требуется, чтобы Lync Server 2013 CU1 был развернут на всех пулах интерфейсных и стандартных серверах выпуска в заданной топологии.</span><span class="sxs-lookup"><span data-stu-id="3be0c-108">Location-Based Routing requires that Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology.</span></span> <span data-ttu-id="3be0c-109">Если Lync Server 2013 CU1 не установлен в некоторых компонентах Lync в топологии, ограничения на маршрутизацию с учетом расположения не могут быть полностью применены.</span><span class="sxs-lookup"><span data-stu-id="3be0c-109">If Lync Server 2013 CU1 is not installed on certain Lync components in the topology, Location-Based Routing restrictions cannot be fully enforced.</span></span>

<span data-ttu-id="3be0c-110">В следующей таблице указаны комбинации ролей сервера и версий, которые поддерживаются для маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="3be0c-110">The following table identifies the combination of server roles and versions that is supported for Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3be0c-111">Версия пула</span><span class="sxs-lookup"><span data-stu-id="3be0c-111">Pool version</span></span></th>
<th><span data-ttu-id="3be0c-112">Версия cервера-посредника</span><span class="sxs-lookup"><span data-stu-id="3be0c-112">Mediation Server version</span></span></th>
<th><span data-ttu-id="3be0c-113">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="3be0c-113">Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3be0c-114">Накопительное обновление для Lync Server 2013 за Февраль 2013</span><span class="sxs-lookup"><span data-stu-id="3be0c-114">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="3be0c-115">Накопительное обновление для Lync Server 2013 за Февраль 2013</span><span class="sxs-lookup"><span data-stu-id="3be0c-115">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="3be0c-116">Да</span><span class="sxs-lookup"><span data-stu-id="3be0c-116">yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be0c-117">Накопительное обновление для Lync Server 2013 за Февраль 2013</span><span class="sxs-lookup"><span data-stu-id="3be0c-117">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="3be0c-118">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3be0c-118">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="3be0c-119">нет</span><span class="sxs-lookup"><span data-stu-id="3be0c-119">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be0c-120">Накопительное обновление для Lync Server 2013 за Февраль 2013</span><span class="sxs-lookup"><span data-stu-id="3be0c-120">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="3be0c-121">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="3be0c-121">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="3be0c-122">нет</span><span class="sxs-lookup"><span data-stu-id="3be0c-122">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be0c-123">Накопительное обновление для Lync Server 2013 за Февраль 2013</span><span class="sxs-lookup"><span data-stu-id="3be0c-123">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="3be0c-124">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="3be0c-124">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="3be0c-125">нет</span><span class="sxs-lookup"><span data-stu-id="3be0c-125">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be0c-126">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3be0c-126">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="3be0c-127">любая</span><span class="sxs-lookup"><span data-stu-id="3be0c-127">any</span></span></p></td>
<td><p><span data-ttu-id="3be0c-128">нет</span><span class="sxs-lookup"><span data-stu-id="3be0c-128">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be0c-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="3be0c-129">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="3be0c-130">любая</span><span class="sxs-lookup"><span data-stu-id="3be0c-130">any</span></span></p></td>
<td><p><span data-ttu-id="3be0c-131">нет</span><span class="sxs-lookup"><span data-stu-id="3be0c-131">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be0c-132">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="3be0c-132">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="3be0c-133">любая</span><span class="sxs-lookup"><span data-stu-id="3be0c-133">any</span></span></p></td>
<td><p><span data-ttu-id="3be0c-134">нет</span><span class="sxs-lookup"><span data-stu-id="3be0c-134">no</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="3be0c-135">Поддержка клиента Lync</span><span class="sxs-lookup"><span data-stu-id="3be0c-135">Lync Client Support</span></span>

<span data-ttu-id="3be0c-136">В следующей таблице указаны клиенты, которые поддерживают маршрутизацию с учетом расположения.</span><span class="sxs-lookup"><span data-stu-id="3be0c-136">The following table identifies the clients that Location-Based Routing supports.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3be0c-137">Тип клиента</span><span class="sxs-lookup"><span data-stu-id="3be0c-137">Client type</span></span></th>
<th><span data-ttu-id="3be0c-138">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="3be0c-138">Supported</span></span></th>
<th><span data-ttu-id="3be0c-139">Сведения</span><span class="sxs-lookup"><span data-stu-id="3be0c-139">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3be0c-140">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="3be0c-140">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="3be0c-141">Да</span><span class="sxs-lookup"><span data-stu-id="3be0c-141">yes</span></span></p></td>
<td><p><span data-ttu-id="3be0c-142">В том числе накопительное обновление для Lync 2013 за Февраль 2013</span><span class="sxs-lookup"><span data-stu-id="3be0c-142">Including Lync 2013 February 2013 Cumulative Update</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be0c-143">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="3be0c-143">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="3be0c-144">Да</span><span class="sxs-lookup"><span data-stu-id="3be0c-144">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be0c-145">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="3be0c-145">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="3be0c-146">нет</span><span class="sxs-lookup"><span data-stu-id="3be0c-146">no</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be0c-147">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="3be0c-147">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="3be0c-148">Да</span><span class="sxs-lookup"><span data-stu-id="3be0c-148">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be0c-149">Lync Attendant</span><span class="sxs-lookup"><span data-stu-id="3be0c-149">Lync Attendant</span></span></p></td>
<td><p><span data-ttu-id="3be0c-150">Да</span><span class="sxs-lookup"><span data-stu-id="3be0c-150">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be0c-151">Lync для Windows 8</span><span class="sxs-lookup"><span data-stu-id="3be0c-151">Lync for Windows 8</span></span></p></td>
<td><p><span data-ttu-id="3be0c-152">нет</span><span class="sxs-lookup"><span data-stu-id="3be0c-152">no</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3be0c-153">Lync Mobile 2013</span><span class="sxs-lookup"><span data-stu-id="3be0c-153">Lync Mobile 2013</span></span></p></td>
<td><p><span data-ttu-id="3be0c-154">нет</span><span class="sxs-lookup"><span data-stu-id="3be0c-154">no</span></span></p></td>
<td><p><span data-ttu-id="3be0c-155">Для клиентов Lync Mobile 2013 необходимо отключить VoIP, если они используются пользователями, для которых включена маршрутизация на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="3be0c-155">VoIP must be disabled for Lync Mobile 2013 clients if used by users with Location-Based Routing enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3be0c-156">Lync Mobile 2010</span><span class="sxs-lookup"><span data-stu-id="3be0c-156">Lync Mobile 2010</span></span></p></td>
<td><p><span data-ttu-id="3be0c-157">Да</span><span class="sxs-lookup"><span data-stu-id="3be0c-157">yes</span></span></p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> <span data-ttu-id="3be0c-158">Чтобы отключить VoIP для клиентов Lync Mobile 2013, назначьте политику мобильности с параметром, IP аудио-и видеофайлы, отключенными для всех пользователей, для которых включена маршрутизация на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="3be0c-158">To disable VoIP for Lync Mobile 2013 clients, assign a mobility policy with the setting, IP Audio/Video, disabled for all users enabled for Location Based Routing.</span></span> <span data-ttu-id="3be0c-159">Более подробно о политике мобильности см. в разделе <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span><span class="sxs-lookup"><span data-stu-id="3be0c-159">For more details about mobility policy, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3be0c-160">См. также</span><span class="sxs-lookup"><span data-stu-id="3be0c-160">See Also</span></span>


[<span data-ttu-id="3be0c-161">Планирование маршрутизации на основе местоположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3be0c-161">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

