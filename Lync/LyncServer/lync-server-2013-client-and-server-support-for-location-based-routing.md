---
title: 'Lync Server 2013: поддержка маршрутизации Location-Based на клиенте и сервере'
description: 'Lync Server 2013: поддержка маршрутизации Location-Based клиентом и сервером.'
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
ms.openlocfilehash: 20dca7444f58ee62dbc36edbb7d9e1c976a97807
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549635"
---
# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="6767d-103">Поддержка маршрутизации Location-Based для клиентов и серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6767d-103">Client and server support for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6767d-104">_**Последнее изменение темы:** 2013-06-18_</span><span class="sxs-lookup"><span data-stu-id="6767d-104">_**Topic Last Modified:** 2013-06-18_</span></span>

<span data-ttu-id="6767d-105">Location-Based маршрутизация обеспечивается Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6767d-105">Location-Based Routing is enforced by Lync Server.</span></span> <span data-ttu-id="6767d-106">Lync Server может определять сетевые сайты, к которым пользователи подключаются из корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="6767d-106">Lync Server can identify the network sites where users are connecting from within the corporate network.</span></span> <span data-ttu-id="6767d-107">Так как удаленные пользователи выходят за границы корпоративной сети, их расположение считается неизвестным.</span><span class="sxs-lookup"><span data-stu-id="6767d-107">Since remote users are outside the corporate network, their location is considered to be unknown.</span></span>

<div>

## <a name="lync-server-support"></a><span data-ttu-id="6767d-108">Поддержка Lync Server</span><span class="sxs-lookup"><span data-stu-id="6767d-108">Lync Server Support</span></span>

<span data-ttu-id="6767d-109">Для маршрутизации Location-Based необходимо, чтобы Lync Server 2013 CU1 был развернут на всех интерфейсных пулах и серверах Standard Edition в заданной топологии.</span><span class="sxs-lookup"><span data-stu-id="6767d-109">Location-Based Routing requires that Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology.</span></span> <span data-ttu-id="6767d-110">Если Lync Server 2013 CU1 не установлен на определенных компонентах Lync в топологии, ограничения маршрутизации Location-Based не могут быть полностью применены.</span><span class="sxs-lookup"><span data-stu-id="6767d-110">If Lync Server 2013 CU1 is not installed on certain Lync components in the topology, Location-Based Routing restrictions cannot be fully enforced.</span></span>

<span data-ttu-id="6767d-111">В следующей таблице указаны комбинации ролей и версий сервера, которые поддерживаются для маршрутизации Location-Based.</span><span class="sxs-lookup"><span data-stu-id="6767d-111">The following table identifies the combination of server roles and versions that is supported for Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6767d-112">Версия пула</span><span class="sxs-lookup"><span data-stu-id="6767d-112">Pool version</span></span></th>
<th><span data-ttu-id="6767d-113">Версия сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="6767d-113">Mediation Server version</span></span></th>
<th><span data-ttu-id="6767d-114">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="6767d-114">Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6767d-115">Накопительный пакет обновления Lync Server 2013 февраль 2013</span><span class="sxs-lookup"><span data-stu-id="6767d-115">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="6767d-116">Накопительный пакет обновления Lync Server 2013 февраль 2013</span><span class="sxs-lookup"><span data-stu-id="6767d-116">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="6767d-117">Да</span><span class="sxs-lookup"><span data-stu-id="6767d-117">yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6767d-118">Накопительный пакет обновления Lync Server 2013 февраль 2013</span><span class="sxs-lookup"><span data-stu-id="6767d-118">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="6767d-119">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6767d-119">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="6767d-120">Нет</span><span class="sxs-lookup"><span data-stu-id="6767d-120">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6767d-121">Накопительный пакет обновления Lync Server 2013 февраль 2013</span><span class="sxs-lookup"><span data-stu-id="6767d-121">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="6767d-122">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="6767d-122">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="6767d-123">Нет</span><span class="sxs-lookup"><span data-stu-id="6767d-123">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6767d-124">Накопительный пакет обновления Lync Server 2013 февраль 2013</span><span class="sxs-lookup"><span data-stu-id="6767d-124">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="6767d-125">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="6767d-125">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="6767d-126">Нет</span><span class="sxs-lookup"><span data-stu-id="6767d-126">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6767d-127">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6767d-127">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="6767d-128">любой</span><span class="sxs-lookup"><span data-stu-id="6767d-128">any</span></span></p></td>
<td><p><span data-ttu-id="6767d-129">Нет</span><span class="sxs-lookup"><span data-stu-id="6767d-129">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6767d-130">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="6767d-130">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="6767d-131">любой</span><span class="sxs-lookup"><span data-stu-id="6767d-131">any</span></span></p></td>
<td><p><span data-ttu-id="6767d-132">Нет</span><span class="sxs-lookup"><span data-stu-id="6767d-132">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6767d-133">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="6767d-133">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="6767d-134">любой</span><span class="sxs-lookup"><span data-stu-id="6767d-134">any</span></span></p></td>
<td><p><span data-ttu-id="6767d-135">Нет</span><span class="sxs-lookup"><span data-stu-id="6767d-135">no</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="6767d-136">Поддержка клиента Lync</span><span class="sxs-lookup"><span data-stu-id="6767d-136">Lync Client Support</span></span>

<span data-ttu-id="6767d-137">В следующей таблице указаны клиенты, которые Location-Based поддерживаются службой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="6767d-137">The following table identifies the clients that Location-Based Routing supports.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6767d-138">Тип клиента</span><span class="sxs-lookup"><span data-stu-id="6767d-138">Client type</span></span></th>
<th><span data-ttu-id="6767d-139">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="6767d-139">Supported</span></span></th>
<th><span data-ttu-id="6767d-140">Сведения</span><span class="sxs-lookup"><span data-stu-id="6767d-140">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6767d-141">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="6767d-141">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="6767d-142">Да</span><span class="sxs-lookup"><span data-stu-id="6767d-142">yes</span></span></p></td>
<td><p><span data-ttu-id="6767d-143">В том числе Lync 2013 февраль 2013 накопительный пакет обновления</span><span class="sxs-lookup"><span data-stu-id="6767d-143">Including Lync 2013 February 2013 Cumulative Update</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6767d-144">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="6767d-144">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="6767d-145">Да</span><span class="sxs-lookup"><span data-stu-id="6767d-145">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6767d-146">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="6767d-146">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="6767d-147">Нет</span><span class="sxs-lookup"><span data-stu-id="6767d-147">no</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6767d-148">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="6767d-148">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="6767d-149">Да</span><span class="sxs-lookup"><span data-stu-id="6767d-149">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6767d-150">Помощник по Lync</span><span class="sxs-lookup"><span data-stu-id="6767d-150">Lync Attendant</span></span></p></td>
<td><p><span data-ttu-id="6767d-151">Да</span><span class="sxs-lookup"><span data-stu-id="6767d-151">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6767d-152">Lync для Windows 8</span><span class="sxs-lookup"><span data-stu-id="6767d-152">Lync for Windows 8</span></span></p></td>
<td><p><span data-ttu-id="6767d-153">Нет</span><span class="sxs-lookup"><span data-stu-id="6767d-153">no</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6767d-154">Lync Mobile 2013</span><span class="sxs-lookup"><span data-stu-id="6767d-154">Lync Mobile 2013</span></span></p></td>
<td><p><span data-ttu-id="6767d-155">Нет</span><span class="sxs-lookup"><span data-stu-id="6767d-155">no</span></span></p></td>
<td><p><span data-ttu-id="6767d-156">Службу VoIP необходимо отключить для клиентов Lync Mobile 2013, если они используются пользователями с включенной маршрутизацией Location-Based.</span><span class="sxs-lookup"><span data-stu-id="6767d-156">VoIP must be disabled for Lync Mobile 2013 clients if used by users with Location-Based Routing enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6767d-157">Lync Mobile 2010</span><span class="sxs-lookup"><span data-stu-id="6767d-157">Lync Mobile 2010</span></span></p></td>
<td><p><span data-ttu-id="6767d-158">Да</span><span class="sxs-lookup"><span data-stu-id="6767d-158">yes</span></span></p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> <span data-ttu-id="6767d-159">Чтобы отключить VoIP для клиентов Lync Mobile 2013, назначьте политику мобильности с параметром, IP-аудио/видео, отключенным для всех пользователей, для которых включена маршрутизация на основе расположения.</span><span class="sxs-lookup"><span data-stu-id="6767d-159">To disable VoIP for Lync Mobile 2013 clients, assign a mobility policy with the setting, IP Audio/Video, disabled for all users enabled for Location Based Routing.</span></span> <span data-ttu-id="6767d-160">Дополнительные сведения о политике мобильности можно найти в статье <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New – CsMobilityPolicy</A>.</span><span class="sxs-lookup"><span data-stu-id="6767d-160">For more details about mobility policy, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6767d-161">См. также</span><span class="sxs-lookup"><span data-stu-id="6767d-161">See Also</span></span>


[<span data-ttu-id="6767d-162">Планирование маршрутизации Location-Based в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6767d-162">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

