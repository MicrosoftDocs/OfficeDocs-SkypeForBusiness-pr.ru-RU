---
title: 'Lync Server 2013: Настройка корпоративной голосовой связи'
description: 'Lync Server 2013: Настройка корпоративной голосовой связи.'
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
ms.openlocfilehash: 49a231b92bf7b04aa3466927a79258f0cbad4e3f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548435"
---
# <a name="configuring-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="c44f3-103">Настройка корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c44f3-103">Configuring Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c44f3-104">_**Последнее изменение темы:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="c44f3-104">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="c44f3-105">Для развертывания корпоративной голосовой связи необходимо настроить следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="c44f3-105">To deploy Enterprise Voice, you’ll need to configure the following:</span></span>

  - <span data-ttu-id="c44f3-106">Создание магистрали</span><span class="sxs-lookup"><span data-stu-id="c44f3-106">Create a Trunk</span></span>

  - <span data-ttu-id="c44f3-107">Определение политики голосовой связи</span><span class="sxs-lookup"><span data-stu-id="c44f3-107">Define a Voice Policy</span></span>

  - <span data-ttu-id="c44f3-108">Определение маршрута голосовой связи</span><span class="sxs-lookup"><span data-stu-id="c44f3-108">Define a Voice Route</span></span>

  - <span data-ttu-id="c44f3-109">Включение корпоративной голосовой связи для пользователей</span><span class="sxs-lookup"><span data-stu-id="c44f3-109">Enable Users for Enterprise Voice</span></span>

<div>

## <a name="create-a-trunk"></a><span data-ttu-id="c44f3-110">Создание магистрали</span><span class="sxs-lookup"><span data-stu-id="c44f3-110">Create a Trunk</span></span>

<span data-ttu-id="c44f3-111">Необходимо определить магистрали в развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="c44f3-111">You must define trunks in your Enterprise Voice deployment.</span></span> <span data-ttu-id="c44f3-112">Для маршрутизации Location-Based необходимо создать конфигурацию магистрали для каждой магистрали.</span><span class="sxs-lookup"><span data-stu-id="c44f3-112">For Location-Based Routing, you must create a trunk configuration per trunk.</span></span> <span data-ttu-id="c44f3-113">Используйте построитель топологий Lync Server, чтобы определить магистрали, и используйте командную консоль Windows PowerShell Lync Server, New — CsTrunkConfiguration или панель управления Lync Server, чтобы определить соответствующие конфигурации магистрали.</span><span class="sxs-lookup"><span data-stu-id="c44f3-113">Use the Lync Server Topology Builder to define your trunks, and use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, or the Lync Server Control Panel to define the corresponding trunk configurations.</span></span> <span data-ttu-id="c44f3-114">Дополнительные сведения о том, как включить маршрутизацию Location-Based в конфигурациях магистрали, можно найти в разделе, разрешив Location-Based маршрутизацию на магистральные линии, а также включить [Location-Basedную маршрутизацию в Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="c44f3-114">More information on how to enable Location-Based Routing on trunk configurations can be found in the section, Enable Location-Based Routing to Trunks, in the topic, [Enabling Location-Based Routing in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span></span> <span data-ttu-id="c44f3-115">В этом примере в приведенной ниже таблице показаны магистральные линии, используемые в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="c44f3-115">For this example, the following table illustrates the trunks used in this scenario.</span></span>

<span data-ttu-id="c44f3-116">Дополнительные сведения см в разделе [Определение дополнительных магистральных линий в построителе топологий в Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span><span class="sxs-lookup"><span data-stu-id="c44f3-116">For more information, see [Define additional trunks in Topology Builder in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span></span>


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
<th><span data-ttu-id="c44f3-117">Название магистрали</span><span class="sxs-lookup"><span data-stu-id="c44f3-117">Trunk name</span></span></th>
<th><span data-ttu-id="c44f3-118">Тип системы</span><span class="sxs-lookup"><span data-stu-id="c44f3-118">System type</span></span></th>
<th><span data-ttu-id="c44f3-119">Имя</span><span class="sxs-lookup"><span data-stu-id="c44f3-119">Name</span></span></th>
<th><span data-ttu-id="c44f3-120">Расположение</span><span class="sxs-lookup"><span data-stu-id="c44f3-120">Location</span></span></th>
<th><span data-ttu-id="c44f3-121">Mediation Server (Сервер-посредник);</span><span class="sxs-lookup"><span data-stu-id="c44f3-121">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c44f3-122">Магистраль 1 DEL — GW</span><span class="sxs-lookup"><span data-stu-id="c44f3-122">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="c44f3-123">шлюз ТСОП;</span><span class="sxs-lookup"><span data-stu-id="c44f3-123">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="c44f3-124">DEL (GW)</span><span class="sxs-lookup"><span data-stu-id="c44f3-124">DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="c44f3-125">Дели</span><span class="sxs-lookup"><span data-stu-id="c44f3-125">Delhi</span></span></p></td>
<td><p><span data-ttu-id="c44f3-126">MS1</span><span class="sxs-lookup"><span data-stu-id="c44f3-126">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c44f3-127">Магистраль 2 ХИД (GW)</span><span class="sxs-lookup"><span data-stu-id="c44f3-127">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="c44f3-128">шлюз ТСОП;</span><span class="sxs-lookup"><span data-stu-id="c44f3-128">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="c44f3-129">ХИД — GW</span><span class="sxs-lookup"><span data-stu-id="c44f3-129">HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="c44f3-130">хидерабад</span><span class="sxs-lookup"><span data-stu-id="c44f3-130">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="c44f3-131">MS1</span><span class="sxs-lookup"><span data-stu-id="c44f3-131">MS1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c44f3-132">Магистраль 3 DEL — УАТС</span><span class="sxs-lookup"><span data-stu-id="c44f3-132">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="c44f3-133">ОФИС</span><span class="sxs-lookup"><span data-stu-id="c44f3-133">PBX</span></span></p></td>
<td><p><span data-ttu-id="c44f3-134">DEL — УАТС</span><span class="sxs-lookup"><span data-stu-id="c44f3-134">DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="c44f3-135">Дели</span><span class="sxs-lookup"><span data-stu-id="c44f3-135">Delhi</span></span></p></td>
<td><p><span data-ttu-id="c44f3-136">MS1</span><span class="sxs-lookup"><span data-stu-id="c44f3-136">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c44f3-137">Магистраль 4 ХИД — УАТС</span><span class="sxs-lookup"><span data-stu-id="c44f3-137">Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="c44f3-138">ОФИС</span><span class="sxs-lookup"><span data-stu-id="c44f3-138">PBX</span></span></p></td>
<td><p><span data-ttu-id="c44f3-139">ХИД — УАТС</span><span class="sxs-lookup"><span data-stu-id="c44f3-139">HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="c44f3-140">хидерабад</span><span class="sxs-lookup"><span data-stu-id="c44f3-140">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="c44f3-141">MS1</span><span class="sxs-lookup"><span data-stu-id="c44f3-141">MS1</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a><span data-ttu-id="c44f3-142">Определяет политики голосовой связи</span><span class="sxs-lookup"><span data-stu-id="c44f3-142">Defines Voice Policies</span></span>

<span data-ttu-id="c44f3-143">Необходимо определить политики голосовой связи для развертывания корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="c44f3-143">You must define voice policies for your Enterprise Voice deployment.</span></span> <span data-ttu-id="c44f3-144">Определите политику голосовой связи, чтобы применить ограничения Location-Based маршрутизации к подмножеству пользователей, если для маршрутизации Location-Based требуется только подмножество этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="c44f3-144">Define a Voice Policy to enforce Location-Based Routing restrictions to a subset of users if only a subset of them is required to use Location-Based Routing.</span></span> <span data-ttu-id="c44f3-145">В этом примере в следующей таблице показаны политики голосовой связи, используемые в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="c44f3-145">For this example, the following table illustrates the voice policies used in this scenario.</span></span> <span data-ttu-id="c44f3-146">Только те параметры, которые относятся к Location-Based маршрутизации, включены в таблицу для целей иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="c44f3-146">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="c44f3-147">Дополнительную информацию можно узнать [в статье Настройка политик голосовой связи и сети PSTN для авторизации функций звонков и привилегий в Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span><span class="sxs-lookup"><span data-stu-id="c44f3-147">For more information, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="c44f3-148">Политика голосовой связи 1</span><span class="sxs-lookup"><span data-stu-id="c44f3-148">Voice policy 1</span></span></th>
<th><span data-ttu-id="c44f3-149">Политика голосовой связи 2</span><span class="sxs-lookup"><span data-stu-id="c44f3-149">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c44f3-150">Идентификатор политики голосовой связи</span><span class="sxs-lookup"><span data-stu-id="c44f3-150">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="c44f3-151">Политика голосовой связи Нью Дели</span><span class="sxs-lookup"><span data-stu-id="c44f3-151">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="c44f3-152">Политика голосовой связи Хидерабад</span><span class="sxs-lookup"><span data-stu-id="c44f3-152">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c44f3-153">Использование PSTN</span><span class="sxs-lookup"><span data-stu-id="c44f3-153">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="c44f3-154">Использование Нью Дели, использование УАТС Del, использование Хид УАТС</span><span class="sxs-lookup"><span data-stu-id="c44f3-154">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="c44f3-155">Использование Хидерабад, использование Хид УАТС, использование УАТС del</span><span class="sxs-lookup"><span data-stu-id="c44f3-155">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c44f3-156">превентпстнтоллбипасс</span><span class="sxs-lookup"><span data-stu-id="c44f3-156">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="c44f3-157">False</span><span class="sxs-lookup"><span data-stu-id="c44f3-157">False</span></span></p></td>
<td><p><span data-ttu-id="c44f3-158">False</span><span class="sxs-lookup"><span data-stu-id="c44f3-158">False</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a><span data-ttu-id="c44f3-159">Определение маршрутов голосовой связи</span><span class="sxs-lookup"><span data-stu-id="c44f3-159">Define Voice Routes</span></span>

<span data-ttu-id="c44f3-160">Необходимо определить маршруты голосовой связи для развертывания корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="c44f3-160">You must define voice routes for your Enterprise Voice deployment.</span></span> <span data-ttu-id="c44f3-161">В этом примере в следующей таблице показаны маршруты голосовых вызовов, используемые в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="c44f3-161">For this example, the following table illustrates the voice routes used in this scenario.</span></span> <span data-ttu-id="c44f3-162">Только те параметры, которые относятся к Location-Based маршрутизации, включены в таблицу для целей иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="c44f3-162">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="c44f3-163">Для получения дополнительных сведений см [Настройка маршрутов голосовой связи для исходящих вызовов в Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span><span class="sxs-lookup"><span data-stu-id="c44f3-163">For more information, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>


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
<th><span data-ttu-id="c44f3-164">Маршрут голосовых вызовов 1</span><span class="sxs-lookup"><span data-stu-id="c44f3-164">Voice route 1</span></span></th>
<th><span data-ttu-id="c44f3-165">Маршрут голосовых вызовов 2</span><span class="sxs-lookup"><span data-stu-id="c44f3-165">Voice route 2</span></span></th>
<th><span data-ttu-id="c44f3-166">Маршрут голосовых вызовов 3</span><span class="sxs-lookup"><span data-stu-id="c44f3-166">Voice route 3</span></span></th>
<th><span data-ttu-id="c44f3-167">Маршрут голосовых вызовов 4</span><span class="sxs-lookup"><span data-stu-id="c44f3-167">Voice route 4</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c44f3-168">Имя</span><span class="sxs-lookup"><span data-stu-id="c44f3-168">Name</span></span></p></td>
<td><p><span data-ttu-id="c44f3-169">Маршрут Нью Дели</span><span class="sxs-lookup"><span data-stu-id="c44f3-169">Delhi route</span></span></p></td>
<td><p><span data-ttu-id="c44f3-170">Маршрут Хидерабад</span><span class="sxs-lookup"><span data-stu-id="c44f3-170">Hyderabad route</span></span></p></td>
<td><p><span data-ttu-id="c44f3-171">Маршрут УАТС del</span><span class="sxs-lookup"><span data-stu-id="c44f3-171">PBX Del route</span></span></p></td>
<td><p><span data-ttu-id="c44f3-172">Маршрут Хид УАТС</span><span class="sxs-lookup"><span data-stu-id="c44f3-172">PBX Hyd route</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c44f3-173">Использование PSTN</span><span class="sxs-lookup"><span data-stu-id="c44f3-173">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="c44f3-174">Использование Нью Дели</span><span class="sxs-lookup"><span data-stu-id="c44f3-174">Delhi usage</span></span></p></td>
<td><p><span data-ttu-id="c44f3-175">Использование Хидерабад</span><span class="sxs-lookup"><span data-stu-id="c44f3-175">Hyderabad usage</span></span></p></td>
<td><p><span data-ttu-id="c44f3-176">Использование УАТС del</span><span class="sxs-lookup"><span data-stu-id="c44f3-176">PBX Del usage</span></span></p></td>
<td><p><span data-ttu-id="c44f3-177">Использование Хид УАТС</span><span class="sxs-lookup"><span data-stu-id="c44f3-177">PBX Hyd usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c44f3-178">Магистрали</span><span class="sxs-lookup"><span data-stu-id="c44f3-178">Trunk</span></span></p></td>
<td><p><span data-ttu-id="c44f3-179">Магистраль 1 DEL — GW</span><span class="sxs-lookup"><span data-stu-id="c44f3-179">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="c44f3-180">Магистраль 2 ХИД (GW)</span><span class="sxs-lookup"><span data-stu-id="c44f3-180">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="c44f3-181">Магистраль 3 DEL — УАТС</span><span class="sxs-lookup"><span data-stu-id="c44f3-181">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="c44f3-182">Магистраль 4 ХИД — УАТС</span><span class="sxs-lookup"><span data-stu-id="c44f3-182">Trunk 4 HYD-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a><span data-ttu-id="c44f3-183">Включение корпоративной голосовой связи для пользователей</span><span class="sxs-lookup"><span data-stu-id="c44f3-183">Enable Users for Enterprise Voice</span></span>

<span data-ttu-id="c44f3-184">Разрешить пользователям использовать корпоративную голосовую связь и назначить им политику голосовой связи, которую вы определили ранее.</span><span class="sxs-lookup"><span data-stu-id="c44f3-184">Enable users for Enterprise Voice and assign them a voice policy you’ve previously defined.</span></span> <span data-ttu-id="c44f3-185">В этом примере показано назначение, используемое в этом сценарии, в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="c44f3-185">For this example, the following table illustrates the assignment used in this scenario.</span></span> <span data-ttu-id="c44f3-186">Только те параметры, которые относятся к Location-Based маршрутизации, включены в таблицу для целей иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="c44f3-186">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="c44f3-187">Дополнительные сведения приведены в статье [Включение поддержки корпоративной голосовой связи для пользователей в Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="c44f3-187">For more information, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="c44f3-188">Пользователи, размещенные в Нью Дели</span><span class="sxs-lookup"><span data-stu-id="c44f3-188">Users located in Delhi</span></span></th>
<th><span data-ttu-id="c44f3-189">Пользователи, размещенные в Хидерабад</span><span class="sxs-lookup"><span data-stu-id="c44f3-189">Users located in Hyderabad</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c44f3-190">Связанная политика голосовой связи</span><span class="sxs-lookup"><span data-stu-id="c44f3-190">Associated voice policy</span></span></p></td>
<td><p><span data-ttu-id="c44f3-191">Политика голосовой связи Нью Дели</span><span class="sxs-lookup"><span data-stu-id="c44f3-191">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="c44f3-192">Политика голосовой связи Хидерабад</span><span class="sxs-lookup"><span data-stu-id="c44f3-192">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c44f3-193">Примеры пользователей</span><span class="sxs-lookup"><span data-stu-id="c44f3-193">Sample users</span></span></p></td>
<td><p><span data-ttu-id="c44f3-194">DEL — LYNC — 1, DEL, LYNC — 2, DEL — LYNC — 3</span><span class="sxs-lookup"><span data-stu-id="c44f3-194">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
<td><p><span data-ttu-id="c44f3-195">ХИД — LYNC — 1, ХИД – LYNC – 2, ХИД — LYNC — 3</span><span class="sxs-lookup"><span data-stu-id="c44f3-195">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c44f3-196">См. также</span><span class="sxs-lookup"><span data-stu-id="c44f3-196">See Also</span></span>


[<span data-ttu-id="c44f3-197">Настройка маршрутизации Location-Based в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c44f3-197">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

