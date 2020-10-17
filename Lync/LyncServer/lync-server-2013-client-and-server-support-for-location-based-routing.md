---
title: 'Lync Server 2013: поддержка маршрутизации Location-Based на клиенте и сервере'
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
ms.openlocfilehash: d85e2ce1738ee5de9d4d542cedd7a9e544771938
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529346"
---
# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="7abca-102">Поддержка маршрутизации Location-Based для клиентов и серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7abca-102">Client and server support for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7abca-103">_**Последнее изменение темы:** 2013-06-18_</span><span class="sxs-lookup"><span data-stu-id="7abca-103">_**Topic Last Modified:** 2013-06-18_</span></span>

<span data-ttu-id="7abca-104">Location-Based маршрутизация обеспечивается Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7abca-104">Location-Based Routing is enforced by Lync Server.</span></span> <span data-ttu-id="7abca-105">Lync Server может определять сетевые сайты, к которым пользователи подключаются из корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="7abca-105">Lync Server can identify the network sites where users are connecting from within the corporate network.</span></span> <span data-ttu-id="7abca-106">Так как удаленные пользователи выходят за границы корпоративной сети, их расположение считается неизвестным.</span><span class="sxs-lookup"><span data-stu-id="7abca-106">Since remote users are outside the corporate network, their location is considered to be unknown.</span></span>

<div>

## <a name="lync-server-support"></a><span data-ttu-id="7abca-107">Поддержка Lync Server</span><span class="sxs-lookup"><span data-stu-id="7abca-107">Lync Server Support</span></span>

<span data-ttu-id="7abca-108">Для маршрутизации Location-Based необходимо, чтобы Lync Server 2013 CU1 был развернут на всех интерфейсных пулах и серверах Standard Edition в заданной топологии.</span><span class="sxs-lookup"><span data-stu-id="7abca-108">Location-Based Routing requires that Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology.</span></span> <span data-ttu-id="7abca-109">Если Lync Server 2013 CU1 не установлен на определенных компонентах Lync в топологии, ограничения маршрутизации Location-Based не могут быть полностью применены.</span><span class="sxs-lookup"><span data-stu-id="7abca-109">If Lync Server 2013 CU1 is not installed on certain Lync components in the topology, Location-Based Routing restrictions cannot be fully enforced.</span></span>

<span data-ttu-id="7abca-110">В следующей таблице указаны комбинации ролей и версий сервера, которые поддерживаются для маршрутизации Location-Based.</span><span class="sxs-lookup"><span data-stu-id="7abca-110">The following table identifies the combination of server roles and versions that is supported for Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7abca-111">Версия пула</span><span class="sxs-lookup"><span data-stu-id="7abca-111">Pool version</span></span></th>
<th><span data-ttu-id="7abca-112">Версия сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="7abca-112">Mediation Server version</span></span></th>
<th><span data-ttu-id="7abca-113">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="7abca-113">Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7abca-114">Накопительный пакет обновления Lync Server 2013 февраль 2013</span><span class="sxs-lookup"><span data-stu-id="7abca-114">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="7abca-115">Накопительный пакет обновления Lync Server 2013 февраль 2013</span><span class="sxs-lookup"><span data-stu-id="7abca-115">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="7abca-116">Да</span><span class="sxs-lookup"><span data-stu-id="7abca-116">yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7abca-117">Накопительный пакет обновления Lync Server 2013 февраль 2013</span><span class="sxs-lookup"><span data-stu-id="7abca-117">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="7abca-118">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7abca-118">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="7abca-119">Нет</span><span class="sxs-lookup"><span data-stu-id="7abca-119">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7abca-120">Накопительный пакет обновления Lync Server 2013 февраль 2013</span><span class="sxs-lookup"><span data-stu-id="7abca-120">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="7abca-121">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="7abca-121">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="7abca-122">Нет</span><span class="sxs-lookup"><span data-stu-id="7abca-122">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7abca-123">Накопительный пакет обновления Lync Server 2013 февраль 2013</span><span class="sxs-lookup"><span data-stu-id="7abca-123">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="7abca-124">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="7abca-124">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="7abca-125">Нет</span><span class="sxs-lookup"><span data-stu-id="7abca-125">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7abca-126">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7abca-126">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="7abca-127">любой</span><span class="sxs-lookup"><span data-stu-id="7abca-127">any</span></span></p></td>
<td><p><span data-ttu-id="7abca-128">Нет</span><span class="sxs-lookup"><span data-stu-id="7abca-128">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7abca-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="7abca-129">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="7abca-130">любой</span><span class="sxs-lookup"><span data-stu-id="7abca-130">any</span></span></p></td>
<td><p><span data-ttu-id="7abca-131">Нет</span><span class="sxs-lookup"><span data-stu-id="7abca-131">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7abca-132">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="7abca-132">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="7abca-133">любой</span><span class="sxs-lookup"><span data-stu-id="7abca-133">any</span></span></p></td>
<td><p><span data-ttu-id="7abca-134">Нет</span><span class="sxs-lookup"><span data-stu-id="7abca-134">no</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="7abca-135">Поддержка клиента Lync</span><span class="sxs-lookup"><span data-stu-id="7abca-135">Lync Client Support</span></span>

<span data-ttu-id="7abca-136">В следующей таблице указаны клиенты, которые Location-Based поддерживаются службой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="7abca-136">The following table identifies the clients that Location-Based Routing supports.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7abca-137">Тип клиента</span><span class="sxs-lookup"><span data-stu-id="7abca-137">Client type</span></span></th>
<th><span data-ttu-id="7abca-138">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="7abca-138">Supported</span></span></th>
<th><span data-ttu-id="7abca-139">Сведения</span><span class="sxs-lookup"><span data-stu-id="7abca-139">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7abca-140">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="7abca-140">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="7abca-141">Да</span><span class="sxs-lookup"><span data-stu-id="7abca-141">yes</span></span></p></td>
<td><p><span data-ttu-id="7abca-142">В том числе Lync 2013 февраль 2013 накопительный пакет обновления</span><span class="sxs-lookup"><span data-stu-id="7abca-142">Including Lync 2013 February 2013 Cumulative Update</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7abca-143">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="7abca-143">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="7abca-144">Да</span><span class="sxs-lookup"><span data-stu-id="7abca-144">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7abca-145">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="7abca-145">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="7abca-146">Нет</span><span class="sxs-lookup"><span data-stu-id="7abca-146">no</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7abca-147">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="7abca-147">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="7abca-148">Да</span><span class="sxs-lookup"><span data-stu-id="7abca-148">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7abca-149">Помощник по Lync</span><span class="sxs-lookup"><span data-stu-id="7abca-149">Lync Attendant</span></span></p></td>
<td><p><span data-ttu-id="7abca-150">Да</span><span class="sxs-lookup"><span data-stu-id="7abca-150">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7abca-151">Lync для Windows 8</span><span class="sxs-lookup"><span data-stu-id="7abca-151">Lync for Windows 8</span></span></p></td>
<td><p><span data-ttu-id="7abca-152">Нет</span><span class="sxs-lookup"><span data-stu-id="7abca-152">no</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7abca-153">Lync Mobile 2013</span><span class="sxs-lookup"><span data-stu-id="7abca-153">Lync Mobile 2013</span></span></p></td>
<td><p><span data-ttu-id="7abca-154">Нет</span><span class="sxs-lookup"><span data-stu-id="7abca-154">no</span></span></p></td>
<td><p><span data-ttu-id="7abca-155">Службу VoIP необходимо отключить для клиентов Lync Mobile 2013, если они используются пользователями с включенной маршрутизацией Location-Based.</span><span class="sxs-lookup"><span data-stu-id="7abca-155">VoIP must be disabled for Lync Mobile 2013 clients if used by users with Location-Based Routing enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7abca-156">Lync Mobile 2010</span><span class="sxs-lookup"><span data-stu-id="7abca-156">Lync Mobile 2010</span></span></p></td>
<td><p><span data-ttu-id="7abca-157">Да</span><span class="sxs-lookup"><span data-stu-id="7abca-157">yes</span></span></p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> <span data-ttu-id="7abca-158">Чтобы отключить VoIP для клиентов Lync Mobile 2013, назначьте политику мобильности с параметром, IP-аудио/видео, отключенным для всех пользователей, для которых включена маршрутизация на основе расположения.</span><span class="sxs-lookup"><span data-stu-id="7abca-158">To disable VoIP for Lync Mobile 2013 clients, assign a mobility policy with the setting, IP Audio/Video, disabled for all users enabled for Location Based Routing.</span></span> <span data-ttu-id="7abca-159">Дополнительные сведения о политике мобильности можно найти в статье <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New – CsMobilityPolicy</A>.</span><span class="sxs-lookup"><span data-stu-id="7abca-159">For more details about mobility policy, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7abca-160">См. также</span><span class="sxs-lookup"><span data-stu-id="7abca-160">See Also</span></span>


[<span data-ttu-id="7abca-161">Планирование маршрутизации Location-Based в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7abca-161">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

