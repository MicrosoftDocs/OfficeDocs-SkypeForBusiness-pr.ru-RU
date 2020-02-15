---
title: 'Lync Server 2013: Настройка маршрутизации на основе расположения'
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
ms.openlocfilehash: 31e8877c4691decfe0c2e65fd820e97432e095aa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030563"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="706ee-102">Настройка маршрутизации на основе расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="706ee-102">Configuring Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="706ee-103">_**Последнее изменение темы:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="706ee-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="706ee-104">Lync Server 2013 CU1, маршрутизация на основе расположения — это функция корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="706ee-104">Lync Server 2013 CU1, Location-Based Routing is a feature of Enterprise Voice.</span></span> <span data-ttu-id="706ee-105">Маршрутизация на основе расположения — это функция управления звонками, которая управляет тем, как звонки направляются Lync Server 2013 CU1.</span><span class="sxs-lookup"><span data-stu-id="706ee-105">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="706ee-106">Он применяет ограничения на то, могут ли звонки перенаправляться в адреса для УАТС или PSTN на основе расположения абонента Lync.</span><span class="sxs-lookup"><span data-stu-id="706ee-106">It enforces restrictions on whether calls can be routed to PBX or PSTN destinations based on the Lync caller’s location.</span></span> <span data-ttu-id="706ee-107">Маршрутизация на основе расположения применяет правила авторизации вызовов к звонкам PSTN на основе расположения в сети вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="706ee-107">Location-Based Routing applies call authorization rules to PSTN calls based on the caller’s network location.</span></span> <span data-ttu-id="706ee-108">Местоположение вызывающего абонента определяется на основе сетевого сайта, связанного с сетевой подсетью, к которой подключен вызывающий абонент.</span><span class="sxs-lookup"><span data-stu-id="706ee-108">The caller’s location is determined based on the network site associated with the network subnet the caller is connected on.</span></span> <span data-ttu-id="706ee-109">Для настройки маршрутизации на основе расположения необходимо сначала развернуть корпоративную голосовую связь, а затем настроить области сети, сайты и подсети.</span><span class="sxs-lookup"><span data-stu-id="706ee-109">Configuring Location-Based Routing requires first deploying Enterprise Voice, then configuring network regions, sites and subnets.</span></span> <span data-ttu-id="706ee-110">При этом настраивается основа для активации маршрутизации на основе расположения.</span><span class="sxs-lookup"><span data-stu-id="706ee-110">This sets up the foundation for enabling Location-Based Routing.</span></span>

<span data-ttu-id="706ee-111">Перед развертыванием маршрутизации на основе расположения необходимо сначала развернуть корпоративную голосовую связь, а также настроить регионы сети, сайты и связать сетевые подсети с сетевыми сайтами.</span><span class="sxs-lookup"><span data-stu-id="706ee-111">Before deploying Location-Based Routing, you must first deploy Enterprise Voice, and configure network regions, sites, and associate network subnets to your network sites.</span></span> <span data-ttu-id="706ee-112">После завершения можно настроить маршрутизацию на основе расположения.</span><span class="sxs-lookup"><span data-stu-id="706ee-112">Once completed, you can configure Location-Based Routing.</span></span> <span data-ttu-id="706ee-113">Инструкции по настройке областей сети, сайтов и подсетей см [в статье развертывание расширенных функций корпоративной голосовой связи в Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span><span class="sxs-lookup"><span data-stu-id="706ee-113">For steps on how to configure network regions, sites and subnets, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span></span>

<span data-ttu-id="706ee-114">В этом разделе описывается настройка маршрутизации на основе расположения с помощью следующего примера, как показано на рисунке.</span><span class="sxs-lookup"><span data-stu-id="706ee-114">This section guides you through the configuration of Location-Based Routing using the following example as illustration.</span></span>

<span data-ttu-id="706ee-115">![Пример маршрутизации на основе расположения корпоративной голосовой связи](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Пример маршрутизации на основе расположения корпоративной голосовой связи")</span><span class="sxs-lookup"><span data-stu-id="706ee-115">![Enterprise Voice location-based routing example](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice location-based routing example")</span></span>

  
<span data-ttu-id="706ee-116">В следующей таблице представлены пользователи, определенные в этом примере.</span><span class="sxs-lookup"><span data-stu-id="706ee-116">The following table represents the users defined in this example.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="706ee-117">Тип конечной точки</span><span class="sxs-lookup"><span data-stu-id="706ee-117">Endpoint type</span></span></th>
<th><span data-ttu-id="706ee-118">Расположение</span><span class="sxs-lookup"><span data-stu-id="706ee-118">Location</span></span></th>
<th><span data-ttu-id="706ee-119">Пользователи</span><span class="sxs-lookup"><span data-stu-id="706ee-119">Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="706ee-120">Lync</span><span class="sxs-lookup"><span data-stu-id="706ee-120">Lync</span></span></p></td>
<td><p><span data-ttu-id="706ee-121">Корпоративный офис Нью Дели</span><span class="sxs-lookup"><span data-stu-id="706ee-121">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="706ee-122">DEL — LYNC — 1, DEL, LYNC — 2, DEL — LYNC — 3</span><span class="sxs-lookup"><span data-stu-id="706ee-122">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="706ee-123">Lync</span><span class="sxs-lookup"><span data-stu-id="706ee-123">Lync</span></span></p></td>
<td><p><span data-ttu-id="706ee-124">Корпоративный офис Хидерабад</span><span class="sxs-lookup"><span data-stu-id="706ee-124">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="706ee-125">ХИД — LYNC — 1, ХИД – LYNC – 2, ХИД — LYNC — 3</span><span class="sxs-lookup"><span data-stu-id="706ee-125">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="706ee-126">Lync</span><span class="sxs-lookup"><span data-stu-id="706ee-126">Lync</span></span></p></td>
<td><p><span data-ttu-id="706ee-127">Неизвестно (например, Гостиницы)</span><span class="sxs-lookup"><span data-stu-id="706ee-127">Unknown (i.e. hotel)</span></span></p></td>
<td><p><span data-ttu-id="706ee-128">УНК — LYNC — 1</span><span class="sxs-lookup"><span data-stu-id="706ee-128">UNK-LYNC-1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="706ee-129">ОФИС</span><span class="sxs-lookup"><span data-stu-id="706ee-129">PBX</span></span></p></td>
<td><p><span data-ttu-id="706ee-130">Корпоративный офис Нью Дели</span><span class="sxs-lookup"><span data-stu-id="706ee-130">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="706ee-131">DEL — УАТС — 1, DEL, УАТС – 2</span><span class="sxs-lookup"><span data-stu-id="706ee-131">DEL-PBX-1, DEL-PBX-2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="706ee-132">ОФИС</span><span class="sxs-lookup"><span data-stu-id="706ee-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="706ee-133">Корпоративный офис Хидерабад</span><span class="sxs-lookup"><span data-stu-id="706ee-133">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="706ee-134">ХИД — УАТС — 1, ХИД – УАТС – 2</span><span class="sxs-lookup"><span data-stu-id="706ee-134">HYD-PBX-1, HYD-PBX-2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="706ee-135">ТСОП</span><span class="sxs-lookup"><span data-stu-id="706ee-135">PSTN</span></span></p></td>
<td><p><span data-ttu-id="706ee-136">Unknown</span><span class="sxs-lookup"><span data-stu-id="706ee-136">Unknown</span></span></p></td>
<td><p><span data-ttu-id="706ee-137">PSTN – 1, PSTN – 2, PSTN – 3</span><span class="sxs-lookup"><span data-stu-id="706ee-137">PSTN-1, PSTN-2, PSTN-3</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="706ee-138">В следующей таблице представлены системы, показанные в этом примере среды.</span><span class="sxs-lookup"><span data-stu-id="706ee-138">The following table represents the systems illustrated in this example environment.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="706ee-139">Системные</span><span class="sxs-lookup"><span data-stu-id="706ee-139">System</span></span></th>
<th><span data-ttu-id="706ee-140">Расположение</span><span class="sxs-lookup"><span data-stu-id="706ee-140">Location</span></span></th>
<th><span data-ttu-id="706ee-141">Имя</span><span class="sxs-lookup"><span data-stu-id="706ee-141">Name</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="706ee-142">Lync Server 2013 CU1 пул</span><span class="sxs-lookup"><span data-stu-id="706ee-142">Lync Server 2013 CU1 pool</span></span></p></td>
<td><p><span data-ttu-id="706ee-143">любой</span><span class="sxs-lookup"><span data-stu-id="706ee-143">any</span></span></p></td>
<td><p><span data-ttu-id="706ee-144">LS — PL1</span><span class="sxs-lookup"><span data-stu-id="706ee-144">LS-PL1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="706ee-145">Lync Server 2013 CU1, сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="706ee-145">Lync Server 2013 CU1, Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="706ee-146">любой</span><span class="sxs-lookup"><span data-stu-id="706ee-146">any</span></span></p></td>
<td><p><span data-ttu-id="706ee-147">MS — PL1</span><span class="sxs-lookup"><span data-stu-id="706ee-147">MS-PL1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="706ee-148">Шлюз PSTN 1</span><span class="sxs-lookup"><span data-stu-id="706ee-148">PSTN gateway 1</span></span></p></td>
<td><p><span data-ttu-id="706ee-149">Дели</span><span class="sxs-lookup"><span data-stu-id="706ee-149">Delhi</span></span></p></td>
<td><p><span data-ttu-id="706ee-150">DEL (GW)</span><span class="sxs-lookup"><span data-stu-id="706ee-150">DEL-GW</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="706ee-151">Шлюз PSTN 2</span><span class="sxs-lookup"><span data-stu-id="706ee-151">PSTN gateway 2</span></span></p></td>
<td><p><span data-ttu-id="706ee-152">хидерабад</span><span class="sxs-lookup"><span data-stu-id="706ee-152">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="706ee-153">ХИД — GW</span><span class="sxs-lookup"><span data-stu-id="706ee-153">HYD-GW</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="706ee-154">УАТС 1</span><span class="sxs-lookup"><span data-stu-id="706ee-154">PBX 1</span></span></p></td>
<td><p><span data-ttu-id="706ee-155">Дели</span><span class="sxs-lookup"><span data-stu-id="706ee-155">Delhi</span></span></p></td>
<td><p><span data-ttu-id="706ee-156">DEL — УАТС</span><span class="sxs-lookup"><span data-stu-id="706ee-156">DEL-PBX</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="706ee-157">УАТС 2</span><span class="sxs-lookup"><span data-stu-id="706ee-157">PBX 2</span></span></p></td>
<td><p><span data-ttu-id="706ee-158">хидерабад</span><span class="sxs-lookup"><span data-stu-id="706ee-158">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="706ee-159">КРАСНАЯ (УАТС)</span><span class="sxs-lookup"><span data-stu-id="706ee-159">RED-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="706ee-160">Содержание</span><span class="sxs-lookup"><span data-stu-id="706ee-160">In This Section</span></span>

  - [<span data-ttu-id="706ee-161">Настройка корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="706ee-161">Configuring Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-configuring-enterprise-voice.md)

  - [<span data-ttu-id="706ee-162">Развертывание областей сети, сайтов и подсетей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="706ee-162">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [<span data-ttu-id="706ee-163">Включение маршрутизации на основе расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="706ee-163">Enabling Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="706ee-164">См. также</span><span class="sxs-lookup"><span data-stu-id="706ee-164">See Also</span></span>


[<span data-ttu-id="706ee-165">Развертывание расширенных функций корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="706ee-165">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

