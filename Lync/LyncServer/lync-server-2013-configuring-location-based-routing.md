---
title: 'Lync Server 2013: Настройка маршрутизации Location-Based'
description: 'Lync Server 2013: Настройка маршрутизации Location-Based.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Location-Based Routing
ms:assetid: 63cdc474-e80f-43b1-a237-9d9ed673300a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994036(v=OCS.15)
ms:contentKeyID: 51803946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 080c2a3a82a8714fc35ce882b0c6cb1630552f27
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570885"
---
# <a name="configuring-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="91234-103">Настройка маршрутизации Location-Based в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91234-103">Configuring Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91234-104">_**Последнее изменение темы:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="91234-104">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="91234-105">Lync Server 2013 CU1, Location-Based маршрутизация — это функция корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="91234-105">Lync Server 2013 CU1, Location-Based Routing is a feature of Enterprise Voice.</span></span> <span data-ttu-id="91234-106">Location-Based маршрутизация — это функция управления звонками, которая управляет тем, как звонки направляются Lync Server 2013 CU1.</span><span class="sxs-lookup"><span data-stu-id="91234-106">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="91234-107">Он применяет ограничения на то, могут ли звонки перенаправляться в адреса для УАТС или PSTN на основе расположения абонента Lync.</span><span class="sxs-lookup"><span data-stu-id="91234-107">It enforces restrictions on whether calls can be routed to PBX or PSTN destinations based on the Lync caller’s location.</span></span> <span data-ttu-id="91234-108">Маршрутизация Location-Based применяет правила авторизации вызовов к звонкам PSTN на основе расположения в сети вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="91234-108">Location-Based Routing applies call authorization rules to PSTN calls based on the caller’s network location.</span></span> <span data-ttu-id="91234-109">Местоположение вызывающего абонента определяется на основе сетевого сайта, связанного с сетевой подсетью, к которой подключен вызывающий абонент.</span><span class="sxs-lookup"><span data-stu-id="91234-109">The caller’s location is determined based on the network site associated with the network subnet the caller is connected on.</span></span> <span data-ttu-id="91234-110">Для настройки маршрутизации Location-Based сначала необходимо развернуть корпоративную голосовую связь, а затем настроить области сети, сайты и подсети.</span><span class="sxs-lookup"><span data-stu-id="91234-110">Configuring Location-Based Routing requires first deploying Enterprise Voice, then configuring network regions, sites and subnets.</span></span> <span data-ttu-id="91234-111">При этом настраивается основа для поддержки маршрутизации Location-Based.</span><span class="sxs-lookup"><span data-stu-id="91234-111">This sets up the foundation for enabling Location-Based Routing.</span></span>

<span data-ttu-id="91234-112">Перед развертыванием маршрутизации Location-Based необходимо сначала развернуть корпоративную голосовую связь, а также настроить регионы сети, сайты и связать сетевые подсети с сетевыми сайтами.</span><span class="sxs-lookup"><span data-stu-id="91234-112">Before deploying Location-Based Routing, you must first deploy Enterprise Voice, and configure network regions, sites, and associate network subnets to your network sites.</span></span> <span data-ttu-id="91234-113">После завершения можно настроить маршрутизацию Location-Based.</span><span class="sxs-lookup"><span data-stu-id="91234-113">Once completed, you can configure Location-Based Routing.</span></span> <span data-ttu-id="91234-114">Инструкции по настройке областей сети, сайтов и подсетей см [в статье развертывание расширенных функций корпоративной голосовой связи в Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span><span class="sxs-lookup"><span data-stu-id="91234-114">For steps on how to configure network regions, sites and subnets, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span></span>

<span data-ttu-id="91234-115">В этом разделе описывается настройка маршрутизации Location-Based с помощью следующего примера, как показано на рисунке.</span><span class="sxs-lookup"><span data-stu-id="91234-115">This section guides you through the configuration of Location-Based Routing using the following example as illustration.</span></span>

<span data-ttu-id="91234-116">![Пример маршрутизации на основе расположения корпоративной голосовой связи](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Пример маршрутизации на основе расположения корпоративной голосовой связи")</span><span class="sxs-lookup"><span data-stu-id="91234-116">![Enterprise Voice location-based routing example](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice location-based routing example")</span></span>

  
<span data-ttu-id="91234-117">В следующей таблице представлены пользователи, определенные в этом примере.</span><span class="sxs-lookup"><span data-stu-id="91234-117">The following table represents the users defined in this example.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91234-118">Тип конечной точки</span><span class="sxs-lookup"><span data-stu-id="91234-118">Endpoint type</span></span></th>
<th><span data-ttu-id="91234-119">Расположение</span><span class="sxs-lookup"><span data-stu-id="91234-119">Location</span></span></th>
<th><span data-ttu-id="91234-120">Пользователи</span><span class="sxs-lookup"><span data-stu-id="91234-120">Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91234-121">Lync</span><span class="sxs-lookup"><span data-stu-id="91234-121">Lync</span></span></p></td>
<td><p><span data-ttu-id="91234-122">Корпоративный офис Нью Дели</span><span class="sxs-lookup"><span data-stu-id="91234-122">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="91234-123">DEL — LYNC — 1, DEL, LYNC — 2, DEL — LYNC — 3</span><span class="sxs-lookup"><span data-stu-id="91234-123">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91234-124">Lync</span><span class="sxs-lookup"><span data-stu-id="91234-124">Lync</span></span></p></td>
<td><p><span data-ttu-id="91234-125">Корпоративный офис Хидерабад</span><span class="sxs-lookup"><span data-stu-id="91234-125">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="91234-126">ХИД — LYNC — 1, ХИД – LYNC – 2, ХИД — LYNC — 3</span><span class="sxs-lookup"><span data-stu-id="91234-126">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91234-127">Lync</span><span class="sxs-lookup"><span data-stu-id="91234-127">Lync</span></span></p></td>
<td><p><span data-ttu-id="91234-128">Неизвестно (например, Гостиницы)</span><span class="sxs-lookup"><span data-stu-id="91234-128">Unknown (i.e. hotel)</span></span></p></td>
<td><p><span data-ttu-id="91234-129">УНК — LYNC — 1</span><span class="sxs-lookup"><span data-stu-id="91234-129">UNK-LYNC-1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91234-130">ОФИС</span><span class="sxs-lookup"><span data-stu-id="91234-130">PBX</span></span></p></td>
<td><p><span data-ttu-id="91234-131">Корпоративный офис Нью Дели</span><span class="sxs-lookup"><span data-stu-id="91234-131">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="91234-132">DEL — УАТС — 1, DEL, УАТС – 2</span><span class="sxs-lookup"><span data-stu-id="91234-132">DEL-PBX-1, DEL-PBX-2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91234-133">ОФИС</span><span class="sxs-lookup"><span data-stu-id="91234-133">PBX</span></span></p></td>
<td><p><span data-ttu-id="91234-134">Корпоративный офис Хидерабад</span><span class="sxs-lookup"><span data-stu-id="91234-134">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="91234-135">ХИД — УАТС — 1, ХИД – УАТС – 2</span><span class="sxs-lookup"><span data-stu-id="91234-135">HYD-PBX-1, HYD-PBX-2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91234-136">ТСОП</span><span class="sxs-lookup"><span data-stu-id="91234-136">PSTN</span></span></p></td>
<td><p><span data-ttu-id="91234-137">Unknown</span><span class="sxs-lookup"><span data-stu-id="91234-137">Unknown</span></span></p></td>
<td><p><span data-ttu-id="91234-138">PSTN – 1, PSTN – 2, PSTN – 3</span><span class="sxs-lookup"><span data-stu-id="91234-138">PSTN-1, PSTN-2, PSTN-3</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="91234-139">В следующей таблице представлены системы, показанные в этом примере среды.</span><span class="sxs-lookup"><span data-stu-id="91234-139">The following table represents the systems illustrated in this example environment.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91234-140">Системные</span><span class="sxs-lookup"><span data-stu-id="91234-140">System</span></span></th>
<th><span data-ttu-id="91234-141">Расположение</span><span class="sxs-lookup"><span data-stu-id="91234-141">Location</span></span></th>
<th><span data-ttu-id="91234-142">Имя</span><span class="sxs-lookup"><span data-stu-id="91234-142">Name</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91234-143">Lync Server 2013 CU1 пул</span><span class="sxs-lookup"><span data-stu-id="91234-143">Lync Server 2013 CU1 pool</span></span></p></td>
<td><p><span data-ttu-id="91234-144">любой</span><span class="sxs-lookup"><span data-stu-id="91234-144">any</span></span></p></td>
<td><p><span data-ttu-id="91234-145">LS — PL1</span><span class="sxs-lookup"><span data-stu-id="91234-145">LS-PL1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91234-146">Lync Server 2013 CU1, сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="91234-146">Lync Server 2013 CU1, Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="91234-147">любой</span><span class="sxs-lookup"><span data-stu-id="91234-147">any</span></span></p></td>
<td><p><span data-ttu-id="91234-148">MS — PL1</span><span class="sxs-lookup"><span data-stu-id="91234-148">MS-PL1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91234-149">Шлюз PSTN 1</span><span class="sxs-lookup"><span data-stu-id="91234-149">PSTN gateway 1</span></span></p></td>
<td><p><span data-ttu-id="91234-150">Дели</span><span class="sxs-lookup"><span data-stu-id="91234-150">Delhi</span></span></p></td>
<td><p><span data-ttu-id="91234-151">DEL (GW)</span><span class="sxs-lookup"><span data-stu-id="91234-151">DEL-GW</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91234-152">Шлюз PSTN 2</span><span class="sxs-lookup"><span data-stu-id="91234-152">PSTN gateway 2</span></span></p></td>
<td><p><span data-ttu-id="91234-153">хидерабад</span><span class="sxs-lookup"><span data-stu-id="91234-153">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="91234-154">ХИД — GW</span><span class="sxs-lookup"><span data-stu-id="91234-154">HYD-GW</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91234-155">УАТС 1</span><span class="sxs-lookup"><span data-stu-id="91234-155">PBX 1</span></span></p></td>
<td><p><span data-ttu-id="91234-156">Дели</span><span class="sxs-lookup"><span data-stu-id="91234-156">Delhi</span></span></p></td>
<td><p><span data-ttu-id="91234-157">DEL — УАТС</span><span class="sxs-lookup"><span data-stu-id="91234-157">DEL-PBX</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91234-158">УАТС 2</span><span class="sxs-lookup"><span data-stu-id="91234-158">PBX 2</span></span></p></td>
<td><p><span data-ttu-id="91234-159">хидерабад</span><span class="sxs-lookup"><span data-stu-id="91234-159">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="91234-160">КРАСНАЯ (УАТС)</span><span class="sxs-lookup"><span data-stu-id="91234-160">RED-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="91234-161">Содержание</span><span class="sxs-lookup"><span data-stu-id="91234-161">In This Section</span></span>

  - [<span data-ttu-id="91234-162">Настройка корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91234-162">Configuring Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-configuring-enterprise-voice.md)

  - [<span data-ttu-id="91234-163">Развертывание областей сети, сайтов и подсетей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91234-163">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [<span data-ttu-id="91234-164">Включение маршрутизации Location-Based в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91234-164">Enabling Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="91234-165">См. также</span><span class="sxs-lookup"><span data-stu-id="91234-165">See Also</span></span>


[<span data-ttu-id="91234-166">Развертывание расширенных функций корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91234-166">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

