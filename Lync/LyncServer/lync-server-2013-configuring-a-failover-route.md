---
title: 'Lync Server 2013: Настройка маршрута отработки отказа'
description: 'Lync Server 2013: Настройка маршрута отработки отказа.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a failover route
ms:assetid: 76e48df4-3b78-4fb7-b1f7-c1e604b81bad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398581(v=OCS.15)
ms:contentKeyID: 48184542
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7cfc45276931685a2d42103b1b7f1d5015dcd7e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560495"
---
# <a name="configuring-a-failover-route-in-lync-server-2013"></a><span data-ttu-id="0f8e1-103">Настройка маршрута отработки отказа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f8e1-103">Configuring a failover route in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f8e1-104">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="0f8e1-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="0f8e1-p101">В следующем примере показано, как администратор может определить маршрут отработки отказа на тот случай, если шлюз Dallas-GW1 отключается для проведения технического обслуживания или недоступен по иным причинам. В таблице ниже показаны изменения, которые нужно внести в конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="0f8e1-p101">The following example shows how an administrator can define a failover route for use if the Dallas-GW1 is down for maintenance or is otherwise unavailable. The following tables illustrate the required configuration change.</span></span>

### <a name="table-1-user-policy"></a><span data-ttu-id="0f8e1-p102">Таблица 1. Политика пользователя</span><span class="sxs-lookup"><span data-stu-id="0f8e1-p102">Table 1. User Policy</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0f8e1-109">Политика пользователя</span><span class="sxs-lookup"><span data-stu-id="0f8e1-109">User policy</span></span></th>
<th><span data-ttu-id="0f8e1-110">Использование телефонов</span><span class="sxs-lookup"><span data-stu-id="0f8e1-110">Phone usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f8e1-111">Политика звонков по умолчанию</span><span class="sxs-lookup"><span data-stu-id="0f8e1-111">Default Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="0f8e1-112">Локальный</span><span class="sxs-lookup"><span data-stu-id="0f8e1-112">Local</span></span></p>
<p><span data-ttu-id="0f8e1-113">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="0f8e1-113">GlobalPSTNHopoff</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f8e1-114">Локальная политика в Редмонде</span><span class="sxs-lookup"><span data-stu-id="0f8e1-114">Redmond Local Policy</span></span></p></td>
<td><p><span data-ttu-id="0f8e1-115">редмондлокал</span><span class="sxs-lookup"><span data-stu-id="0f8e1-115">RedmondLocal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f8e1-116">Политика звонков в Далласе</span><span class="sxs-lookup"><span data-stu-id="0f8e1-116">Dallas Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="0f8e1-117">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="0f8e1-117">DallasUsers</span></span></p>
<p><span data-ttu-id="0f8e1-118">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="0f8e1-118">GlobalPSTNHopoff</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a><span data-ttu-id="0f8e1-p103">Таблица 2. Маршруты</span><span class="sxs-lookup"><span data-stu-id="0f8e1-p103">Table 2. Routes</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0f8e1-121">Название маршрута</span><span class="sxs-lookup"><span data-stu-id="0f8e1-121">Route name</span></span></th>
<th><span data-ttu-id="0f8e1-122">Шаблон номера</span><span class="sxs-lookup"><span data-stu-id="0f8e1-122">Number pattern</span></span></th>
<th><span data-ttu-id="0f8e1-123">Использование телефонов</span><span class="sxs-lookup"><span data-stu-id="0f8e1-123">Phone usage</span></span></th>
<th><span data-ttu-id="0f8e1-124">Магистрали</span><span class="sxs-lookup"><span data-stu-id="0f8e1-124">Trunk</span></span></th>
<th><span data-ttu-id="0f8e1-125">Шлюз</span><span class="sxs-lookup"><span data-stu-id="0f8e1-125">Gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f8e1-126">Локальный маршрут в Редмонде</span><span class="sxs-lookup"><span data-stu-id="0f8e1-126">Redmond Local Route</span></span></p></td>
<td><p><span data-ttu-id="0f8e1-127">^\+1 (425 | 206 | 253) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="0f8e1-127">^\+1(425|206|253)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="0f8e1-128">Локальный</span><span class="sxs-lookup"><span data-stu-id="0f8e1-128">Local</span></span></p>
<p><span data-ttu-id="0f8e1-129">редмондлокал</span><span class="sxs-lookup"><span data-stu-id="0f8e1-129">RedmondLocal</span></span></p></td>
<td><p><span data-ttu-id="0f8e1-130">Trunk1</span><span class="sxs-lookup"><span data-stu-id="0f8e1-130">Trunk1</span></span></p>
<p><span data-ttu-id="0f8e1-131">Trunk2</span><span class="sxs-lookup"><span data-stu-id="0f8e1-131">Trunk2</span></span></p></td>
<td><p><span data-ttu-id="0f8e1-132">Red — GW1</span><span class="sxs-lookup"><span data-stu-id="0f8e1-132">Red-GW1</span></span></p>
<p><span data-ttu-id="0f8e1-133">Red — GW2</span><span class="sxs-lookup"><span data-stu-id="0f8e1-133">Red-GW2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f8e1-134">Локальный маршрут в Далласе</span><span class="sxs-lookup"><span data-stu-id="0f8e1-134">Dallas Local Route</span></span></p></td>
<td><p><span data-ttu-id="0f8e1-135">^\+1 (972 | 214 | 469) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="0f8e1-135">^\+1(972|214|469)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="0f8e1-136">Локальный</span><span class="sxs-lookup"><span data-stu-id="0f8e1-136">Local</span></span></p></td>
<td><p><span data-ttu-id="0f8e1-137">Trunk3</span><span class="sxs-lookup"><span data-stu-id="0f8e1-137">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="0f8e1-138">Dallas — GW1</span><span class="sxs-lookup"><span data-stu-id="0f8e1-138">Dallas-GW1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f8e1-139">Универсальный маршрут</span><span class="sxs-lookup"><span data-stu-id="0f8e1-139">Universal Route</span></span></p></td>
<td><p><span data-ttu-id="0f8e1-140">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="0f8e1-140">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="0f8e1-141">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="0f8e1-141">GlobalPSTNHopoff</span></span></p></td>
<td><p><span data-ttu-id="0f8e1-142">Trunk1</span><span class="sxs-lookup"><span data-stu-id="0f8e1-142">Trunk1</span></span></p>
<p><span data-ttu-id="0f8e1-143">Trunk2</span><span class="sxs-lookup"><span data-stu-id="0f8e1-143">Trunk2</span></span></p>
<p><span data-ttu-id="0f8e1-144">Trunk3</span><span class="sxs-lookup"><span data-stu-id="0f8e1-144">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="0f8e1-145">Red — GW1</span><span class="sxs-lookup"><span data-stu-id="0f8e1-145">Red-GW1</span></span></p>
<p><span data-ttu-id="0f8e1-146">Red — GW2</span><span class="sxs-lookup"><span data-stu-id="0f8e1-146">Red-GW2</span></span></p>
<p><span data-ttu-id="0f8e1-147">Dallas — GW1</span><span class="sxs-lookup"><span data-stu-id="0f8e1-147">Dallas-GW1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f8e1-148">Маршрут для пользователей в Далласе</span><span class="sxs-lookup"><span data-stu-id="0f8e1-148">Dallas Users Route</span></span></p></td>
<td><p><span data-ttu-id="0f8e1-149">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="0f8e1-149">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="0f8e1-150">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="0f8e1-150">DallasUsers</span></span></p></td>
<td><p><span data-ttu-id="0f8e1-151">Trunk3</span><span class="sxs-lookup"><span data-stu-id="0f8e1-151">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="0f8e1-152">Dallas — GW1</span><span class="sxs-lookup"><span data-stu-id="0f8e1-152">Dallas-GW1</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0f8e1-p104">В таблице 1 использование телефона GlobalPSTNHopoff добавлено после использования телефона DallasUsers в политике звонков в Далласе. Это позволяет использовать для звонков, к которым применяется политика звонков в Далласе, маршруты, настроенные для использования телефонов GlobalPSTNHopoff, если маршрут, заданный для использования телефонов DallasUsers, недоступен.</span><span class="sxs-lookup"><span data-stu-id="0f8e1-p104">In Table 1, a phone usage of GlobalPSTNHopoff is added after the DallasUsers phone usage in the Dallas Calling Policy. This enables calls with the Dallas Calling policy to use routes that are configured for the GlobalPSTNHopoff phone usage if a route for the DallasUsers phone usage is unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

