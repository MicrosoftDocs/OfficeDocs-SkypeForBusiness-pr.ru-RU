---
title: 'Lync Server 2013: настройка маршрута отработки отказа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a failover route
ms:assetid: 76e48df4-3b78-4fb7-b1f7-c1e604b81bad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398581(v=OCS.15)
ms:contentKeyID: 48184542
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e65070326c82e3a30977b3512bd2785d6bb4bd2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-failover-route-in-lync-server-2013"></a><span data-ttu-id="1243b-102">Настройка маршрута отработки отказа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1243b-102">Configuring a failover route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1243b-103">_**Тема последнего изменения:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="1243b-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="1243b-p101">В следующем примере показано, как администратор может определить маршрут отработки отказа на тот случай, если шлюз Dallas-GW1 отключается для проведения технического обслуживания или недоступен по иным причинам. В таблице ниже показаны изменения, которые нужно внести в конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="1243b-p101">The following example shows how an administrator can define a failover route for use if the Dallas-GW1 is down for maintenance or is otherwise unavailable. The following tables illustrate the required configuration change.</span></span>

### <a name="table-1-user-policy"></a><span data-ttu-id="1243b-p102">Таблица 1. Политика пользователя</span><span class="sxs-lookup"><span data-stu-id="1243b-p102">Table 1. User Policy</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1243b-108">Политика пользователя</span><span class="sxs-lookup"><span data-stu-id="1243b-108">User policy</span></span></th>
<th><span data-ttu-id="1243b-109">Использование телефонов</span><span class="sxs-lookup"><span data-stu-id="1243b-109">Phone usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1243b-110">Политика звонков по умолчанию</span><span class="sxs-lookup"><span data-stu-id="1243b-110">Default Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="1243b-111">Local</span><span class="sxs-lookup"><span data-stu-id="1243b-111">Local</span></span></p>
<p><span data-ttu-id="1243b-112">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="1243b-112">GlobalPSTNHopoff</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1243b-113">Локальная политика в Редмонде</span><span class="sxs-lookup"><span data-stu-id="1243b-113">Redmond Local Policy</span></span></p></td>
<td><p><span data-ttu-id="1243b-114">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="1243b-114">RedmondLocal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1243b-115">Политика звонков в Далласе</span><span class="sxs-lookup"><span data-stu-id="1243b-115">Dallas Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="1243b-116">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="1243b-116">DallasUsers</span></span></p>
<p><span data-ttu-id="1243b-117">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="1243b-117">GlobalPSTNHopoff</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a><span data-ttu-id="1243b-p103">Таблица 2. Маршруты</span><span class="sxs-lookup"><span data-stu-id="1243b-p103">Table 2. Routes</span></span>

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
<th><span data-ttu-id="1243b-120">Название маршрута</span><span class="sxs-lookup"><span data-stu-id="1243b-120">Route name</span></span></th>
<th><span data-ttu-id="1243b-121">Шаблон номера</span><span class="sxs-lookup"><span data-stu-id="1243b-121">Number pattern</span></span></th>
<th><span data-ttu-id="1243b-122">Использование телефонов</span><span class="sxs-lookup"><span data-stu-id="1243b-122">Phone usage</span></span></th>
<th><span data-ttu-id="1243b-123">Линия связи</span><span class="sxs-lookup"><span data-stu-id="1243b-123">Trunk</span></span></th>
<th><span data-ttu-id="1243b-124">Шлюз</span><span class="sxs-lookup"><span data-stu-id="1243b-124">Gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1243b-125">Локальный маршрут в Редмонде</span><span class="sxs-lookup"><span data-stu-id="1243b-125">Redmond Local Route</span></span></p></td>
<td><p><span data-ttu-id="1243b-126">^\+1 (425 | 206 | 253) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="1243b-126">^\+1(425|206|253)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="1243b-127">Local</span><span class="sxs-lookup"><span data-stu-id="1243b-127">Local</span></span></p>
<p><span data-ttu-id="1243b-128">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="1243b-128">RedmondLocal</span></span></p></td>
<td><p><span data-ttu-id="1243b-129">Trunk1</span><span class="sxs-lookup"><span data-stu-id="1243b-129">Trunk1</span></span></p>
<p><span data-ttu-id="1243b-130">Trunk2</span><span class="sxs-lookup"><span data-stu-id="1243b-130">Trunk2</span></span></p></td>
<td><p><span data-ttu-id="1243b-131">Red-GW1</span><span class="sxs-lookup"><span data-stu-id="1243b-131">Red-GW1</span></span></p>
<p><span data-ttu-id="1243b-132">Red-GW2</span><span class="sxs-lookup"><span data-stu-id="1243b-132">Red-GW2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1243b-133">Локальный маршрут в Далласе</span><span class="sxs-lookup"><span data-stu-id="1243b-133">Dallas Local Route</span></span></p></td>
<td><p><span data-ttu-id="1243b-134">^\+1 (972 | 214 | 469) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="1243b-134">^\+1(972|214|469)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="1243b-135">Local</span><span class="sxs-lookup"><span data-stu-id="1243b-135">Local</span></span></p></td>
<td><p><span data-ttu-id="1243b-136">Trunk3</span><span class="sxs-lookup"><span data-stu-id="1243b-136">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="1243b-137">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="1243b-137">Dallas-GW1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1243b-138">Универсальный маршрут</span><span class="sxs-lookup"><span data-stu-id="1243b-138">Universal Route</span></span></p></td>
<td><p><span data-ttu-id="1243b-139">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="1243b-139">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="1243b-140">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="1243b-140">GlobalPSTNHopoff</span></span></p></td>
<td><p><span data-ttu-id="1243b-141">Trunk1</span><span class="sxs-lookup"><span data-stu-id="1243b-141">Trunk1</span></span></p>
<p><span data-ttu-id="1243b-142">Trunk2</span><span class="sxs-lookup"><span data-stu-id="1243b-142">Trunk2</span></span></p>
<p><span data-ttu-id="1243b-143">Trunk3</span><span class="sxs-lookup"><span data-stu-id="1243b-143">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="1243b-144">Red-GW1</span><span class="sxs-lookup"><span data-stu-id="1243b-144">Red-GW1</span></span></p>
<p><span data-ttu-id="1243b-145">Red-GW2</span><span class="sxs-lookup"><span data-stu-id="1243b-145">Red-GW2</span></span></p>
<p><span data-ttu-id="1243b-146">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="1243b-146">Dallas-GW1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1243b-147">Маршрут для пользователей в Далласе</span><span class="sxs-lookup"><span data-stu-id="1243b-147">Dallas Users Route</span></span></p></td>
<td><p><span data-ttu-id="1243b-148">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="1243b-148">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="1243b-149">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="1243b-149">DallasUsers</span></span></p></td>
<td><p><span data-ttu-id="1243b-150">Trunk3</span><span class="sxs-lookup"><span data-stu-id="1243b-150">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="1243b-151">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="1243b-151">Dallas-GW1</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1243b-p104">В таблице 1 использование телефона GlobalPSTNHopoff добавлено после использования телефона DallasUsers в политике звонков в Далласе. Это позволяет использовать для звонков, к которым применяется политика звонков в Далласе, маршруты, настроенные для использования телефонов GlobalPSTNHopoff, если маршрут, заданный для использования телефонов DallasUsers, недоступен.</span><span class="sxs-lookup"><span data-stu-id="1243b-p104">In Table 1, a phone usage of GlobalPSTNHopoff is added after the DallasUsers phone usage in the Dallas Calling Policy. This enables calls with the Dallas Calling policy to use routes that are configured for the GlobalPSTNHopoff phone usage if a route for the DallasUsers phone usage is unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

