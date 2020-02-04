---
title: 'Lync Server 2013: настройка маршрутизации на основе расположения'
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
ms.openlocfilehash: a0e82ae8a0dd9961bfeb9d2a513cb77b0affb2c4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762817"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="f28f7-102">Настройка маршрутизации на основе расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f28f7-102">Configuring Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f28f7-103">_**Тема последнего изменения:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="f28f7-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="f28f7-104">Lync Server 2013 CU1, маршрутизация на основе местоположения — это функция корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="f28f7-104">Lync Server 2013 CU1, Location-Based Routing is a feature of Enterprise Voice.</span></span> <span data-ttu-id="f28f7-105">Маршрутизация на основе местоположения — это функция управления звонками, определяющая способ маршрутизации звонков Lync Server 2013 CU1.</span><span class="sxs-lookup"><span data-stu-id="f28f7-105">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="f28f7-106">Она обеспечивает ограничения на то, могут ли звонки перенаправляться в адреса для АТС или PSTN, основываясь на расположении вызывающего абонента Lync.</span><span class="sxs-lookup"><span data-stu-id="f28f7-106">It enforces restrictions on whether calls can be routed to PBX or PSTN destinations based on the Lync caller’s location.</span></span> <span data-ttu-id="f28f7-107">Маршрутизация на основе местоположения применяет правила авторизации вызовов к КОММУТИРУЕМым звонкам с учетом расположения в сети вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="f28f7-107">Location-Based Routing applies call authorization rules to PSTN calls based on the caller’s network location.</span></span> <span data-ttu-id="f28f7-108">Расположение вызывающего абонента определяется на основе сетевого сайта, связанного с сетевой подсетью, в которой подключен вызывающий абонент.</span><span class="sxs-lookup"><span data-stu-id="f28f7-108">The caller’s location is determined based on the network site associated with the network subnet the caller is connected on.</span></span> <span data-ttu-id="f28f7-109">Для настройки маршрутизации на основе местоположения сначала необходимо предварительно развернуть корпоративный голос, а затем настроить регионы сети, сайты и подсети.</span><span class="sxs-lookup"><span data-stu-id="f28f7-109">Configuring Location-Based Routing requires first deploying Enterprise Voice, then configuring network regions, sites and subnets.</span></span> <span data-ttu-id="f28f7-110">Таким образом, вы настраиваете основу для включения маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="f28f7-110">This sets up the foundation for enabling Location-Based Routing.</span></span>

<span data-ttu-id="f28f7-111">Перед развертыванием маршрутизации на основе местоположения необходимо предварительно развернуть корпоративный голос и настроить регионы сети, сайты и связать сетевые подсети с сетевыми сайтами.</span><span class="sxs-lookup"><span data-stu-id="f28f7-111">Before deploying Location-Based Routing, you must first deploy Enterprise Voice, and configure network regions, sites, and associate network subnets to your network sites.</span></span> <span data-ttu-id="f28f7-112">После завершения настройки можно настроить маршрутизацию на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="f28f7-112">Once completed, you can configure Location-Based Routing.</span></span> <span data-ttu-id="f28f7-113">Инструкции по настройке регионов сети, сайтов и подсетей можно найти [в статье развертывание расширенных функций голосовой связи для предприятий в Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span><span class="sxs-lookup"><span data-stu-id="f28f7-113">For steps on how to configure network regions, sites and subnets, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span></span>

<span data-ttu-id="f28f7-114">В этом разделе рассказывается, как настроить маршрутизацию на основе местоположения, выполнив приведенный ниже пример в качестве иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="f28f7-114">This section guides you through the configuration of Location-Based Routing using the following example as illustration.</span></span>

<span data-ttu-id="f28f7-115">![Пример маршрутизации на основе расположения голоса в корпоративной среде](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Пример маршрутизации на основе расположения голоса в корпоративной среде")</span><span class="sxs-lookup"><span data-stu-id="f28f7-115">![Enterprise Voice location-based routing example](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice location-based routing example")</span></span>

  
<span data-ttu-id="f28f7-116">В следующей таблице представлены пользователи, определенные в этом примере.</span><span class="sxs-lookup"><span data-stu-id="f28f7-116">The following table represents the users defined in this example.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f28f7-117">Тип конечной точки</span><span class="sxs-lookup"><span data-stu-id="f28f7-117">Endpoint type</span></span></th>
<th><span data-ttu-id="f28f7-118">Местоположение</span><span class="sxs-lookup"><span data-stu-id="f28f7-118">Location</span></span></th>
<th><span data-ttu-id="f28f7-119">Пользователи</span><span class="sxs-lookup"><span data-stu-id="f28f7-119">Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f28f7-120">Lync</span><span class="sxs-lookup"><span data-stu-id="f28f7-120">Lync</span></span></p></td>
<td><p><span data-ttu-id="f28f7-121">Корпоративный офис Делхи</span><span class="sxs-lookup"><span data-stu-id="f28f7-121">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="f28f7-122">DEL — LYNC-1, DEL-LYNC-2, DEL-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="f28f7-122">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f28f7-123">Lync</span><span class="sxs-lookup"><span data-stu-id="f28f7-123">Lync</span></span></p></td>
<td><p><span data-ttu-id="f28f7-124">Корпоративный офис Хидерабад</span><span class="sxs-lookup"><span data-stu-id="f28f7-124">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="f28f7-125">ХИД-LYNC-1, ХИД-LYNC-2, ХИД-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="f28f7-125">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f28f7-126">Lync</span><span class="sxs-lookup"><span data-stu-id="f28f7-126">Lync</span></span></p></td>
<td><p><span data-ttu-id="f28f7-127">Неизвестно (например, Гостиницы)</span><span class="sxs-lookup"><span data-stu-id="f28f7-127">Unknown (i.e. hotel)</span></span></p></td>
<td><p><span data-ttu-id="f28f7-128">УНК-LYNC-1</span><span class="sxs-lookup"><span data-stu-id="f28f7-128">UNK-LYNC-1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f28f7-129">АТС</span><span class="sxs-lookup"><span data-stu-id="f28f7-129">PBX</span></span></p></td>
<td><p><span data-ttu-id="f28f7-130">Корпоративный офис Делхи</span><span class="sxs-lookup"><span data-stu-id="f28f7-130">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="f28f7-131">DEL-УАТС-1, DEL-УАТС-2</span><span class="sxs-lookup"><span data-stu-id="f28f7-131">DEL-PBX-1, DEL-PBX-2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f28f7-132">АТС</span><span class="sxs-lookup"><span data-stu-id="f28f7-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="f28f7-133">Корпоративный офис Хидерабад</span><span class="sxs-lookup"><span data-stu-id="f28f7-133">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="f28f7-134">ХИД-УАТС-1, ХИД-УАТС-2</span><span class="sxs-lookup"><span data-stu-id="f28f7-134">HYD-PBX-1, HYD-PBX-2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f28f7-135">ТСОП</span><span class="sxs-lookup"><span data-stu-id="f28f7-135">PSTN</span></span></p></td>
<td><p><span data-ttu-id="f28f7-136">Неожиданно</span><span class="sxs-lookup"><span data-stu-id="f28f7-136">Unknown</span></span></p></td>
<td><p><span data-ttu-id="f28f7-137">PSTN-1, PSTN-2, КТСОП-3</span><span class="sxs-lookup"><span data-stu-id="f28f7-137">PSTN-1, PSTN-2, PSTN-3</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="f28f7-138">В следующей таблице представлены системы, показанные в этом примере среды.</span><span class="sxs-lookup"><span data-stu-id="f28f7-138">The following table represents the systems illustrated in this example environment.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f28f7-139">Администратор</span><span class="sxs-lookup"><span data-stu-id="f28f7-139">System</span></span></th>
<th><span data-ttu-id="f28f7-140">Местоположение</span><span class="sxs-lookup"><span data-stu-id="f28f7-140">Location</span></span></th>
<th><span data-ttu-id="f28f7-141">Имя</span><span class="sxs-lookup"><span data-stu-id="f28f7-141">Name</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f28f7-142">Пул Lync Server 2013 CU1</span><span class="sxs-lookup"><span data-stu-id="f28f7-142">Lync Server 2013 CU1 pool</span></span></p></td>
<td><p><span data-ttu-id="f28f7-143">любой</span><span class="sxs-lookup"><span data-stu-id="f28f7-143">any</span></span></p></td>
<td><p><span data-ttu-id="f28f7-144">LS-PL1</span><span class="sxs-lookup"><span data-stu-id="f28f7-144">LS-PL1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f28f7-145">Lync Server 2013 CU1, сервер для устранения проблем</span><span class="sxs-lookup"><span data-stu-id="f28f7-145">Lync Server 2013 CU1, Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="f28f7-146">любой</span><span class="sxs-lookup"><span data-stu-id="f28f7-146">any</span></span></p></td>
<td><p><span data-ttu-id="f28f7-147">MS-PL1</span><span class="sxs-lookup"><span data-stu-id="f28f7-147">MS-PL1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f28f7-148">Шлюз PSTN 1</span><span class="sxs-lookup"><span data-stu-id="f28f7-148">PSTN gateway 1</span></span></p></td>
<td><p><span data-ttu-id="f28f7-149">Delhi</span><span class="sxs-lookup"><span data-stu-id="f28f7-149">Delhi</span></span></p></td>
<td><p><span data-ttu-id="f28f7-150">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="f28f7-150">DEL-GW</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f28f7-151">Шлюз PSTN 2</span><span class="sxs-lookup"><span data-stu-id="f28f7-151">PSTN gateway 2</span></span></p></td>
<td><p><span data-ttu-id="f28f7-152">хидерабад</span><span class="sxs-lookup"><span data-stu-id="f28f7-152">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="f28f7-153">ХИД-GW</span><span class="sxs-lookup"><span data-stu-id="f28f7-153">HYD-GW</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f28f7-154">АТС 1</span><span class="sxs-lookup"><span data-stu-id="f28f7-154">PBX 1</span></span></p></td>
<td><p><span data-ttu-id="f28f7-155">Delhi</span><span class="sxs-lookup"><span data-stu-id="f28f7-155">Delhi</span></span></p></td>
<td><p><span data-ttu-id="f28f7-156">DELETE-УАТС</span><span class="sxs-lookup"><span data-stu-id="f28f7-156">DEL-PBX</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f28f7-157">АТС 2</span><span class="sxs-lookup"><span data-stu-id="f28f7-157">PBX 2</span></span></p></td>
<td><p><span data-ttu-id="f28f7-158">хидерабад</span><span class="sxs-lookup"><span data-stu-id="f28f7-158">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="f28f7-159">КРАСНАЯ-УАТС</span><span class="sxs-lookup"><span data-stu-id="f28f7-159">RED-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="f28f7-160">Содержание</span><span class="sxs-lookup"><span data-stu-id="f28f7-160">In This Section</span></span>

  - [<span data-ttu-id="f28f7-161">Настройка корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f28f7-161">Configuring Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-configuring-enterprise-voice.md)

  - [<span data-ttu-id="f28f7-162">Развертывание регионов сети, сайтов и подсетей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f28f7-162">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [<span data-ttu-id="f28f7-163">Включение маршрутизации на основе местоположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f28f7-163">Enabling Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f28f7-164">См. также</span><span class="sxs-lookup"><span data-stu-id="f28f7-164">See Also</span></span>


[<span data-ttu-id="f28f7-165">Развертывание улучшенных функций голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f28f7-165">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

