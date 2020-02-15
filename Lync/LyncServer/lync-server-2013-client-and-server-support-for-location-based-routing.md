---
title: 'Lync Server 2013: поддержка маршрутизации на основе расположения для клиентов и серверов'
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
ms.openlocfilehash: efdb03adbdf1392e27c3107eef4aaf97f3708e66
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043841"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="81048-102">Поддержка маршрутизации на основе расположения в клиенте и сервере в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81048-102">Client and server support for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81048-103">_**Последнее изменение темы:** 2013-06-18_</span><span class="sxs-lookup"><span data-stu-id="81048-103">_**Topic Last Modified:** 2013-06-18_</span></span>

<span data-ttu-id="81048-104">Маршрутизация на основе расположения обеспечивается Lync Server.</span><span class="sxs-lookup"><span data-stu-id="81048-104">Location-Based Routing is enforced by Lync Server.</span></span> <span data-ttu-id="81048-105">Lync Server может определять сетевые сайты, к которым пользователи подключаются из корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="81048-105">Lync Server can identify the network sites where users are connecting from within the corporate network.</span></span> <span data-ttu-id="81048-106">Так как удаленные пользователи выходят за границы корпоративной сети, их расположение считается неизвестным.</span><span class="sxs-lookup"><span data-stu-id="81048-106">Since remote users are outside the corporate network, their location is considered to be unknown.</span></span>

<div>

## <a name="lync-server-support"></a><span data-ttu-id="81048-107">Поддержка Lync Server</span><span class="sxs-lookup"><span data-stu-id="81048-107">Lync Server Support</span></span>

<span data-ttu-id="81048-108">Для маршрутизации на основе расположения необходимо, чтобы Lync Server 2013 CU1 был развернут на всех интерфейсных пулах и серверах Standard Edition в заданной топологии.</span><span class="sxs-lookup"><span data-stu-id="81048-108">Location-Based Routing requires that Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology.</span></span> <span data-ttu-id="81048-109">Если Lync Server 2013 CU1 не установлен на определенных компонентах Lync в топологии, ограничения маршрутизации на основе расположения не могут быть полностью применены.</span><span class="sxs-lookup"><span data-stu-id="81048-109">If Lync Server 2013 CU1 is not installed on certain Lync components in the topology, Location-Based Routing restrictions cannot be fully enforced.</span></span>

<span data-ttu-id="81048-110">В следующей таблице указаны комбинации ролей и версий сервера, которые поддерживают маршрутизацию на основе расположения.</span><span class="sxs-lookup"><span data-stu-id="81048-110">The following table identifies the combination of server roles and versions that is supported for Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81048-111">Версия пула</span><span class="sxs-lookup"><span data-stu-id="81048-111">Pool version</span></span></th>
<th><span data-ttu-id="81048-112">Версия сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="81048-112">Mediation Server version</span></span></th>
<th><span data-ttu-id="81048-113">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="81048-113">Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81048-114">Накопительный пакет обновления Lync Server 2013 февраль 2013</span><span class="sxs-lookup"><span data-stu-id="81048-114">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="81048-115">Накопительный пакет обновления Lync Server 2013 февраль 2013</span><span class="sxs-lookup"><span data-stu-id="81048-115">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="81048-116">Да</span><span class="sxs-lookup"><span data-stu-id="81048-116">yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81048-117">Накопительный пакет обновления Lync Server 2013 февраль 2013</span><span class="sxs-lookup"><span data-stu-id="81048-117">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="81048-118">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81048-118">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="81048-119">нет</span><span class="sxs-lookup"><span data-stu-id="81048-119">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81048-120">Накопительный пакет обновления Lync Server 2013 февраль 2013</span><span class="sxs-lookup"><span data-stu-id="81048-120">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="81048-121">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="81048-121">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="81048-122">нет</span><span class="sxs-lookup"><span data-stu-id="81048-122">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81048-123">Накопительный пакет обновления Lync Server 2013 февраль 2013</span><span class="sxs-lookup"><span data-stu-id="81048-123">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="81048-124">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="81048-124">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="81048-125">нет</span><span class="sxs-lookup"><span data-stu-id="81048-125">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81048-126">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81048-126">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="81048-127">любой</span><span class="sxs-lookup"><span data-stu-id="81048-127">any</span></span></p></td>
<td><p><span data-ttu-id="81048-128">нет</span><span class="sxs-lookup"><span data-stu-id="81048-128">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81048-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="81048-129">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="81048-130">любой</span><span class="sxs-lookup"><span data-stu-id="81048-130">any</span></span></p></td>
<td><p><span data-ttu-id="81048-131">нет</span><span class="sxs-lookup"><span data-stu-id="81048-131">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81048-132">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="81048-132">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="81048-133">любой</span><span class="sxs-lookup"><span data-stu-id="81048-133">any</span></span></p></td>
<td><p><span data-ttu-id="81048-134">нет</span><span class="sxs-lookup"><span data-stu-id="81048-134">no</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="81048-135">Поддержка клиента Lync</span><span class="sxs-lookup"><span data-stu-id="81048-135">Lync Client Support</span></span>

<span data-ttu-id="81048-136">В следующей таблице указаны клиенты, поддерживаемые маршрутизацией на основе расположения.</span><span class="sxs-lookup"><span data-stu-id="81048-136">The following table identifies the clients that Location-Based Routing supports.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81048-137">Тип клиента</span><span class="sxs-lookup"><span data-stu-id="81048-137">Client type</span></span></th>
<th><span data-ttu-id="81048-138">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="81048-138">Supported</span></span></th>
<th><span data-ttu-id="81048-139">Сведения</span><span class="sxs-lookup"><span data-stu-id="81048-139">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81048-140">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="81048-140">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="81048-141">Да</span><span class="sxs-lookup"><span data-stu-id="81048-141">yes</span></span></p></td>
<td><p><span data-ttu-id="81048-142">В том числе Lync 2013 февраль 2013 накопительный пакет обновления</span><span class="sxs-lookup"><span data-stu-id="81048-142">Including Lync 2013 February 2013 Cumulative Update</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81048-143">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="81048-143">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="81048-144">Да</span><span class="sxs-lookup"><span data-stu-id="81048-144">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81048-145">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="81048-145">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="81048-146">нет</span><span class="sxs-lookup"><span data-stu-id="81048-146">no</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81048-147">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="81048-147">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="81048-148">Да</span><span class="sxs-lookup"><span data-stu-id="81048-148">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81048-149">Помощник по Lync</span><span class="sxs-lookup"><span data-stu-id="81048-149">Lync Attendant</span></span></p></td>
<td><p><span data-ttu-id="81048-150">Да</span><span class="sxs-lookup"><span data-stu-id="81048-150">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81048-151">Lync для Windows 8</span><span class="sxs-lookup"><span data-stu-id="81048-151">Lync for Windows 8</span></span></p></td>
<td><p><span data-ttu-id="81048-152">нет</span><span class="sxs-lookup"><span data-stu-id="81048-152">no</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81048-153">Lync Mobile 2013</span><span class="sxs-lookup"><span data-stu-id="81048-153">Lync Mobile 2013</span></span></p></td>
<td><p><span data-ttu-id="81048-154">нет</span><span class="sxs-lookup"><span data-stu-id="81048-154">no</span></span></p></td>
<td><p><span data-ttu-id="81048-155">Службу VoIP необходимо отключить для клиентов Lync Mobile 2013, если они используются пользователями, для которых включена маршрутизация на основе расположения.</span><span class="sxs-lookup"><span data-stu-id="81048-155">VoIP must be disabled for Lync Mobile 2013 clients if used by users with Location-Based Routing enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81048-156">Lync Mobile 2010</span><span class="sxs-lookup"><span data-stu-id="81048-156">Lync Mobile 2010</span></span></p></td>
<td><p><span data-ttu-id="81048-157">Да</span><span class="sxs-lookup"><span data-stu-id="81048-157">yes</span></span></p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> <span data-ttu-id="81048-158">Чтобы отключить VoIP для клиентов Lync Mobile 2013, назначьте политику мобильности с параметром, IP-аудио/видео, отключенным для всех пользователей, для которых включена маршрутизация на основе расположения.</span><span class="sxs-lookup"><span data-stu-id="81048-158">To disable VoIP for Lync Mobile 2013 clients, assign a mobility policy with the setting, IP Audio/Video, disabled for all users enabled for Location Based Routing.</span></span> <span data-ttu-id="81048-159">Дополнительные сведения о политике мобильности можно найти в статье <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New – CsMobilityPolicy</A>.</span><span class="sxs-lookup"><span data-stu-id="81048-159">For more details about mobility policy, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="81048-160">См. также</span><span class="sxs-lookup"><span data-stu-id="81048-160">See Also</span></span>


[<span data-ttu-id="81048-161">Планирование маршрутизации на основе расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81048-161">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

