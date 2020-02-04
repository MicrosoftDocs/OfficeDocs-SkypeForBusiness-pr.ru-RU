---
title: 'Lync Server 2013: Настройка корпоративной голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise Voice
ms:assetid: 7df179fa-d3a2-4b23-a433-b750aedf980b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994041(v=OCS.15)
ms:contentKeyID: 51803952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d6bf9f79725f1f4812ac1e1c1c3c0e3217b939b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728939"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="33d2c-102">Настройка корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33d2c-102">Configuring Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33d2c-103">_**Тема последнего изменения:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="33d2c-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="33d2c-104">Для развертывания корпоративной голосовой связи необходимо настроить указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="33d2c-104">To deploy Enterprise Voice, you’ll need to configure the following:</span></span>

  - <span data-ttu-id="33d2c-105">Создание магистрали</span><span class="sxs-lookup"><span data-stu-id="33d2c-105">Create a Trunk</span></span>

  - <span data-ttu-id="33d2c-106">Определение политики голосовой связи</span><span class="sxs-lookup"><span data-stu-id="33d2c-106">Define a Voice Policy</span></span>

  - <span data-ttu-id="33d2c-107">Определение голосового маршрута</span><span class="sxs-lookup"><span data-stu-id="33d2c-107">Define a Voice Route</span></span>

  - <span data-ttu-id="33d2c-108">Enable Users for Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="33d2c-108">Enable Users for Enterprise Voice</span></span>

<div>

## <a name="create-a-trunk"></a><span data-ttu-id="33d2c-109">Создание магистрали</span><span class="sxs-lookup"><span data-stu-id="33d2c-109">Create a Trunk</span></span>

<span data-ttu-id="33d2c-110">Вы должны определить в развертывании своей корпоративной голосовой сети магистральные магистрали.</span><span class="sxs-lookup"><span data-stu-id="33d2c-110">You must define trunks in your Enterprise Voice deployment.</span></span> <span data-ttu-id="33d2c-111">Для маршрутизации на основе местоположения необходимо создать конфигурацию магистрали для каждой магистрали.</span><span class="sxs-lookup"><span data-stu-id="33d2c-111">For Location-Based Routing, you must create a trunk configuration per trunk.</span></span> <span data-ttu-id="33d2c-112">Используйте построитель топологии Lync Server для определения ваших каналов и используйте команду Lync Server Windows PowerShell New-CsTrunkConfiguration или панель управления Lync Server для определения соответствующих конфигураций магистрали.</span><span class="sxs-lookup"><span data-stu-id="33d2c-112">Use the Lync Server Topology Builder to define your trunks, and use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, or the Lync Server Control Panel to define the corresponding trunk configurations.</span></span> <span data-ttu-id="33d2c-113">Дополнительные сведения о включении маршрутизации на основе местоположения на магистральных конфигурациях можно найти в разделе Включение маршрутизации с помощью местоположения на Магистральы в разделе Создание [маршрутизации на основе местоположения в Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="33d2c-113">More information on how to enable Location-Based Routing on trunk configurations can be found in the section, Enable Location-Based Routing to Trunks, in the topic, [Enabling Location-Based Routing in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span></span> <span data-ttu-id="33d2c-114">В этом примере в следующей таблице показаны магистральные линии, используемые в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="33d2c-114">For this example, the following table illustrates the trunks used in this scenario.</span></span>

<span data-ttu-id="33d2c-115">Дополнительные сведения можно найти [в разделе Определение дополнительных каналов в построителе топологии в Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span><span class="sxs-lookup"><span data-stu-id="33d2c-115">For more information, see [Define additional trunks in Topology Builder in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span></span>


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
<th><span data-ttu-id="33d2c-116">Название магистрали</span><span class="sxs-lookup"><span data-stu-id="33d2c-116">Trunk name</span></span></th>
<th><span data-ttu-id="33d2c-117">Тип системы</span><span class="sxs-lookup"><span data-stu-id="33d2c-117">System type</span></span></th>
<th><span data-ttu-id="33d2c-118">Имя</span><span class="sxs-lookup"><span data-stu-id="33d2c-118">Name</span></span></th>
<th><span data-ttu-id="33d2c-119">Местоположение</span><span class="sxs-lookup"><span data-stu-id="33d2c-119">Location</span></span></th>
<th><span data-ttu-id="33d2c-120">Сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="33d2c-120">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="33d2c-121">Магистраль 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="33d2c-121">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="33d2c-122">Шлюз ТСОП</span><span class="sxs-lookup"><span data-stu-id="33d2c-122">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="33d2c-123">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="33d2c-123">DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="33d2c-124">Delhi</span><span class="sxs-lookup"><span data-stu-id="33d2c-124">Delhi</span></span></p></td>
<td><p><span data-ttu-id="33d2c-125">MS1</span><span class="sxs-lookup"><span data-stu-id="33d2c-125">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33d2c-126">Магистраль 2 ХИД-GW</span><span class="sxs-lookup"><span data-stu-id="33d2c-126">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="33d2c-127">Шлюз ТСОП</span><span class="sxs-lookup"><span data-stu-id="33d2c-127">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="33d2c-128">ХИД-GW</span><span class="sxs-lookup"><span data-stu-id="33d2c-128">HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="33d2c-129">хидерабад</span><span class="sxs-lookup"><span data-stu-id="33d2c-129">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="33d2c-130">MS1</span><span class="sxs-lookup"><span data-stu-id="33d2c-130">MS1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33d2c-131">Магистрали 3, DEL и АТС</span><span class="sxs-lookup"><span data-stu-id="33d2c-131">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="33d2c-132">АТС</span><span class="sxs-lookup"><span data-stu-id="33d2c-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="33d2c-133">DELETE-УАТС</span><span class="sxs-lookup"><span data-stu-id="33d2c-133">DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="33d2c-134">Delhi</span><span class="sxs-lookup"><span data-stu-id="33d2c-134">Delhi</span></span></p></td>
<td><p><span data-ttu-id="33d2c-135">MS1</span><span class="sxs-lookup"><span data-stu-id="33d2c-135">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33d2c-136">Магистральная ХИД 4-УАТС</span><span class="sxs-lookup"><span data-stu-id="33d2c-136">Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="33d2c-137">АТС</span><span class="sxs-lookup"><span data-stu-id="33d2c-137">PBX</span></span></p></td>
<td><p><span data-ttu-id="33d2c-138">ХИД-УАТС</span><span class="sxs-lookup"><span data-stu-id="33d2c-138">HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="33d2c-139">хидерабад</span><span class="sxs-lookup"><span data-stu-id="33d2c-139">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="33d2c-140">MS1</span><span class="sxs-lookup"><span data-stu-id="33d2c-140">MS1</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a><span data-ttu-id="33d2c-141">Определяет политики голосовой связи</span><span class="sxs-lookup"><span data-stu-id="33d2c-141">Defines Voice Policies</span></span>

<span data-ttu-id="33d2c-142">Вы должны определить политики голосовой связи для своего корпоративного развертывания.</span><span class="sxs-lookup"><span data-stu-id="33d2c-142">You must define voice policies for your Enterprise Voice deployment.</span></span> <span data-ttu-id="33d2c-143">Определение политики голосовой связи для обеспечения ограничений маршрутизации на основе местоположения для подмножества пользователей, если для работы с маршрутизацией на основе местоположения требуется только подмножество.</span><span class="sxs-lookup"><span data-stu-id="33d2c-143">Define a Voice Policy to enforce Location-Based Routing restrictions to a subset of users if only a subset of them is required to use Location-Based Routing.</span></span> <span data-ttu-id="33d2c-144">В этом примере в следующей таблице показаны политики голосовой связи, используемые в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="33d2c-144">For this example, the following table illustrates the voice policies used in this scenario.</span></span> <span data-ttu-id="33d2c-145">В таблице ниже приведены только те параметры, которые относятся к маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="33d2c-145">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="33d2c-146">Дополнительные сведения можно найти в разделе [Настройка политик голосовой связи и использование PSTN для авторизации функций и привилегий для звонков в Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span><span class="sxs-lookup"><span data-stu-id="33d2c-146">For more information, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="33d2c-147">Политика голосовой связи 1</span><span class="sxs-lookup"><span data-stu-id="33d2c-147">Voice policy 1</span></span></th>
<th><span data-ttu-id="33d2c-148">Политика голосовой связи 2</span><span class="sxs-lookup"><span data-stu-id="33d2c-148">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="33d2c-149">Идентификатор политики голосовой связи</span><span class="sxs-lookup"><span data-stu-id="33d2c-149">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="33d2c-150">Политика голосовой связи Делхи</span><span class="sxs-lookup"><span data-stu-id="33d2c-150">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="33d2c-151">Политика голосовой связи Хидерабад</span><span class="sxs-lookup"><span data-stu-id="33d2c-151">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33d2c-152">Использование PSTN</span><span class="sxs-lookup"><span data-stu-id="33d2c-152">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="33d2c-153">Использование Делхи, использование АТС DELETE, использование Хид УАТС</span><span class="sxs-lookup"><span data-stu-id="33d2c-153">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="33d2c-154">Использование Хидерабад, Хид УАТС, использование АТС Delete</span><span class="sxs-lookup"><span data-stu-id="33d2c-154">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33d2c-155">превентпстнтоллбипасс</span><span class="sxs-lookup"><span data-stu-id="33d2c-155">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="33d2c-156">False</span><span class="sxs-lookup"><span data-stu-id="33d2c-156">False</span></span></p></td>
<td><p><span data-ttu-id="33d2c-157">False</span><span class="sxs-lookup"><span data-stu-id="33d2c-157">False</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a><span data-ttu-id="33d2c-158">Определение маршрутов голосовой связи</span><span class="sxs-lookup"><span data-stu-id="33d2c-158">Define Voice Routes</span></span>

<span data-ttu-id="33d2c-159">Вы должны определить Голосовые маршруты для своего корпоративного развертывания.</span><span class="sxs-lookup"><span data-stu-id="33d2c-159">You must define voice routes for your Enterprise Voice deployment.</span></span> <span data-ttu-id="33d2c-160">В этом примере в приведенной ниже таблице показаны маршруты голосовой связи, используемые в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="33d2c-160">For this example, the following table illustrates the voice routes used in this scenario.</span></span> <span data-ttu-id="33d2c-161">В таблице ниже приведены только те параметры, которые относятся к маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="33d2c-161">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="33d2c-162">Дополнительные сведения можно найти [в разделе Настройка голосовых маршрутов для исходящих звонков в Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span><span class="sxs-lookup"><span data-stu-id="33d2c-162">For more information, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>


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
<th></th>
<th><span data-ttu-id="33d2c-163">Маршрут к голосовой связи 1</span><span class="sxs-lookup"><span data-stu-id="33d2c-163">Voice route 1</span></span></th>
<th><span data-ttu-id="33d2c-164">Маршрут к голосовой связи 2</span><span class="sxs-lookup"><span data-stu-id="33d2c-164">Voice route 2</span></span></th>
<th><span data-ttu-id="33d2c-165">Маршрут голоса 3</span><span class="sxs-lookup"><span data-stu-id="33d2c-165">Voice route 3</span></span></th>
<th><span data-ttu-id="33d2c-166">Маршрут голосовой связи 4</span><span class="sxs-lookup"><span data-stu-id="33d2c-166">Voice route 4</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="33d2c-167">Имя</span><span class="sxs-lookup"><span data-stu-id="33d2c-167">Name</span></span></p></td>
<td><p><span data-ttu-id="33d2c-168">Маршрут Делхи</span><span class="sxs-lookup"><span data-stu-id="33d2c-168">Delhi route</span></span></p></td>
<td><p><span data-ttu-id="33d2c-169">Маршрут Хидерабад</span><span class="sxs-lookup"><span data-stu-id="33d2c-169">Hyderabad route</span></span></p></td>
<td><p><span data-ttu-id="33d2c-170">Маршрут для УАТС Delete</span><span class="sxs-lookup"><span data-stu-id="33d2c-170">PBX Del route</span></span></p></td>
<td><p><span data-ttu-id="33d2c-171">Маршрут Хид УАТС</span><span class="sxs-lookup"><span data-stu-id="33d2c-171">PBX Hyd route</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33d2c-172">Использование PSTN</span><span class="sxs-lookup"><span data-stu-id="33d2c-172">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="33d2c-173">Использование Делхи</span><span class="sxs-lookup"><span data-stu-id="33d2c-173">Delhi usage</span></span></p></td>
<td><p><span data-ttu-id="33d2c-174">Использование Хидерабад</span><span class="sxs-lookup"><span data-stu-id="33d2c-174">Hyderabad usage</span></span></p></td>
<td><p><span data-ttu-id="33d2c-175">Использование DELETE для АТС</span><span class="sxs-lookup"><span data-stu-id="33d2c-175">PBX Del usage</span></span></p></td>
<td><p><span data-ttu-id="33d2c-176">Использование Хид УАТС</span><span class="sxs-lookup"><span data-stu-id="33d2c-176">PBX Hyd usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33d2c-177">Линия связи</span><span class="sxs-lookup"><span data-stu-id="33d2c-177">Trunk</span></span></p></td>
<td><p><span data-ttu-id="33d2c-178">Магистраль 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="33d2c-178">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="33d2c-179">Магистраль 2 ХИД-GW</span><span class="sxs-lookup"><span data-stu-id="33d2c-179">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="33d2c-180">Магистрали 3, DEL и АТС</span><span class="sxs-lookup"><span data-stu-id="33d2c-180">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="33d2c-181">Магистральная ХИД 4-УАТС</span><span class="sxs-lookup"><span data-stu-id="33d2c-181">Trunk 4 HYD-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a><span data-ttu-id="33d2c-182">Enable Users for Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="33d2c-182">Enable Users for Enterprise Voice</span></span>

<span data-ttu-id="33d2c-183">Включите пользователей для корпоративного голоса и назначьте им политику голосовой связи, которую вы определили ранее.</span><span class="sxs-lookup"><span data-stu-id="33d2c-183">Enable users for Enterprise Voice and assign them a voice policy you’ve previously defined.</span></span> <span data-ttu-id="33d2c-184">В этом примере в приведенной ниже таблице показано назначение, используемое в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="33d2c-184">For this example, the following table illustrates the assignment used in this scenario.</span></span> <span data-ttu-id="33d2c-185">В таблице ниже приведены только те параметры, которые относятся к маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="33d2c-185">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="33d2c-186">Дополнительные сведения можно найти [в разделе Включение пользователей для корпоративной голосовой связи в Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="33d2c-186">For more information, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="33d2c-187">Пользователи, находящиеся в Делхи</span><span class="sxs-lookup"><span data-stu-id="33d2c-187">Users located in Delhi</span></span></th>
<th><span data-ttu-id="33d2c-188">Пользователи, находящиеся в Хидерабад</span><span class="sxs-lookup"><span data-stu-id="33d2c-188">Users located in Hyderabad</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="33d2c-189">Соответствующая политика голосовой связи</span><span class="sxs-lookup"><span data-stu-id="33d2c-189">Associated voice policy</span></span></p></td>
<td><p><span data-ttu-id="33d2c-190">Политика голосовой связи Делхи</span><span class="sxs-lookup"><span data-stu-id="33d2c-190">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="33d2c-191">Политика голосовой связи Хидерабад</span><span class="sxs-lookup"><span data-stu-id="33d2c-191">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33d2c-192">Примеры пользователей</span><span class="sxs-lookup"><span data-stu-id="33d2c-192">Sample users</span></span></p></td>
<td><p><span data-ttu-id="33d2c-193">DEL — LYNC-1, DEL-LYNC-2, DEL-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="33d2c-193">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
<td><p><span data-ttu-id="33d2c-194">ХИД-LYNC-1, ХИД-LYNC-2, ХИД-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="33d2c-194">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="33d2c-195">См. также</span><span class="sxs-lookup"><span data-stu-id="33d2c-195">See Also</span></span>


[<span data-ttu-id="33d2c-196">Настройка маршрутизации на основе расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33d2c-196">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

