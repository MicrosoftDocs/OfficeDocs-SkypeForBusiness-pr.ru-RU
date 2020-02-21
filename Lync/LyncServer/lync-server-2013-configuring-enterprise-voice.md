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
ms.openlocfilehash: 8a6c09bd44f9fc4b98488c7825f8cab1d3eea7f6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202945"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="4b8f4-102">Настройка корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b8f4-102">Configuring Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b8f4-103">_**Последнее изменение темы:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="4b8f4-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="4b8f4-104">Для развертывания корпоративной голосовой связи необходимо настроить следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="4b8f4-104">To deploy Enterprise Voice, you’ll need to configure the following:</span></span>

  - <span data-ttu-id="4b8f4-105">Создание магистрали</span><span class="sxs-lookup"><span data-stu-id="4b8f4-105">Create a Trunk</span></span>

  - <span data-ttu-id="4b8f4-106">Определение политики голосовой связи</span><span class="sxs-lookup"><span data-stu-id="4b8f4-106">Define a Voice Policy</span></span>

  - <span data-ttu-id="4b8f4-107">Определение маршрута голосовой связи</span><span class="sxs-lookup"><span data-stu-id="4b8f4-107">Define a Voice Route</span></span>

  - <span data-ttu-id="4b8f4-108">Включение корпоративной голосовой связи для пользователей</span><span class="sxs-lookup"><span data-stu-id="4b8f4-108">Enable Users for Enterprise Voice</span></span>

<div>

## <a name="create-a-trunk"></a><span data-ttu-id="4b8f4-109">Создание магистрали</span><span class="sxs-lookup"><span data-stu-id="4b8f4-109">Create a Trunk</span></span>

<span data-ttu-id="4b8f4-110">Необходимо определить магистрали в развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="4b8f4-110">You must define trunks in your Enterprise Voice deployment.</span></span> <span data-ttu-id="4b8f4-111">Для маршрутизации на основе расположения необходимо создать конфигурацию магистрали для каждой магистрали.</span><span class="sxs-lookup"><span data-stu-id="4b8f4-111">For Location-Based Routing, you must create a trunk configuration per trunk.</span></span> <span data-ttu-id="4b8f4-112">Используйте построитель топологий Lync Server, чтобы определить магистрали, и используйте командную консоль Windows PowerShell Lync Server, New — CsTrunkConfiguration или панель управления Lync Server, чтобы определить соответствующие конфигурации магистрали.</span><span class="sxs-lookup"><span data-stu-id="4b8f4-112">Use the Lync Server Topology Builder to define your trunks, and use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, or the Lync Server Control Panel to define the corresponding trunk configurations.</span></span> <span data-ttu-id="4b8f4-113">Дополнительные сведения о включении маршрутизации на основе расположения в конфигурациях магистрали можно найти в разделе Включение маршрутизации на основе расположения в магистрали, а также [Включение маршрутизации на основе расположения в Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="4b8f4-113">More information on how to enable Location-Based Routing on trunk configurations can be found in the section, Enable Location-Based Routing to Trunks, in the topic, [Enabling Location-Based Routing in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span></span> <span data-ttu-id="4b8f4-114">В этом примере в приведенной ниже таблице показаны магистральные линии, используемые в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="4b8f4-114">For this example, the following table illustrates the trunks used in this scenario.</span></span>

<span data-ttu-id="4b8f4-115">Дополнительные сведения см в разделе [Определение дополнительных магистральных линий в построителе топологий в Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span><span class="sxs-lookup"><span data-stu-id="4b8f4-115">For more information, see [Define additional trunks in Topology Builder in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span></span>


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
<th><span data-ttu-id="4b8f4-116">Название магистрали</span><span class="sxs-lookup"><span data-stu-id="4b8f4-116">Trunk name</span></span></th>
<th><span data-ttu-id="4b8f4-117">Тип системы</span><span class="sxs-lookup"><span data-stu-id="4b8f4-117">System type</span></span></th>
<th><span data-ttu-id="4b8f4-118">Имя</span><span class="sxs-lookup"><span data-stu-id="4b8f4-118">Name</span></span></th>
<th><span data-ttu-id="4b8f4-119">Расположение</span><span class="sxs-lookup"><span data-stu-id="4b8f4-119">Location</span></span></th>
<th><span data-ttu-id="4b8f4-120">Mediation Server (Сервер-посредник);</span><span class="sxs-lookup"><span data-stu-id="4b8f4-120">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b8f4-121">Магистраль 1 DEL — GW</span><span class="sxs-lookup"><span data-stu-id="4b8f4-121">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-122">шлюз ТСОП;</span><span class="sxs-lookup"><span data-stu-id="4b8f4-122">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-123">DEL (GW)</span><span class="sxs-lookup"><span data-stu-id="4b8f4-123">DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-124">Дели</span><span class="sxs-lookup"><span data-stu-id="4b8f4-124">Delhi</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-125">MS1</span><span class="sxs-lookup"><span data-stu-id="4b8f4-125">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b8f4-126">Магистраль 2 ХИД (GW)</span><span class="sxs-lookup"><span data-stu-id="4b8f4-126">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-127">шлюз ТСОП;</span><span class="sxs-lookup"><span data-stu-id="4b8f4-127">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-128">ХИД — GW</span><span class="sxs-lookup"><span data-stu-id="4b8f4-128">HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-129">хидерабад</span><span class="sxs-lookup"><span data-stu-id="4b8f4-129">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-130">MS1</span><span class="sxs-lookup"><span data-stu-id="4b8f4-130">MS1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b8f4-131">Магистраль 3 DEL — УАТС</span><span class="sxs-lookup"><span data-stu-id="4b8f4-131">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-132">ОФИС</span><span class="sxs-lookup"><span data-stu-id="4b8f4-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-133">DEL — УАТС</span><span class="sxs-lookup"><span data-stu-id="4b8f4-133">DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-134">Дели</span><span class="sxs-lookup"><span data-stu-id="4b8f4-134">Delhi</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-135">MS1</span><span class="sxs-lookup"><span data-stu-id="4b8f4-135">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b8f4-136">Магистраль 4 ХИД — УАТС</span><span class="sxs-lookup"><span data-stu-id="4b8f4-136">Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-137">ОФИС</span><span class="sxs-lookup"><span data-stu-id="4b8f4-137">PBX</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-138">ХИД — УАТС</span><span class="sxs-lookup"><span data-stu-id="4b8f4-138">HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-139">хидерабад</span><span class="sxs-lookup"><span data-stu-id="4b8f4-139">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-140">MS1</span><span class="sxs-lookup"><span data-stu-id="4b8f4-140">MS1</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a><span data-ttu-id="4b8f4-141">Определяет политики голосовой связи</span><span class="sxs-lookup"><span data-stu-id="4b8f4-141">Defines Voice Policies</span></span>

<span data-ttu-id="4b8f4-142">Необходимо определить политики голосовой связи для развертывания корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="4b8f4-142">You must define voice policies for your Enterprise Voice deployment.</span></span> <span data-ttu-id="4b8f4-143">Определение политики голосовой связи для применения ограничений маршрутизации на основе расположения к подмножеству пользователей, если для использования маршрутизации на основе расположения требуется только подмножество этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="4b8f4-143">Define a Voice Policy to enforce Location-Based Routing restrictions to a subset of users if only a subset of them is required to use Location-Based Routing.</span></span> <span data-ttu-id="4b8f4-144">В этом примере в следующей таблице показаны политики голосовой связи, используемые в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="4b8f4-144">For this example, the following table illustrates the voice policies used in this scenario.</span></span> <span data-ttu-id="4b8f4-145">Только те параметры, которые относятся к маршрутизации на основе расположения, включены в таблицу для целей иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="4b8f4-145">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="4b8f4-146">Дополнительную информацию можно узнать [в статье Настройка политик голосовой связи и сети PSTN для авторизации функций звонков и привилегий в Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span><span class="sxs-lookup"><span data-stu-id="4b8f4-146">For more information, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="4b8f4-147">Политика голосовой связи 1</span><span class="sxs-lookup"><span data-stu-id="4b8f4-147">Voice policy 1</span></span></th>
<th><span data-ttu-id="4b8f4-148">Политика голосовой связи 2</span><span class="sxs-lookup"><span data-stu-id="4b8f4-148">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b8f4-149">Идентификатор политики голосовой связи</span><span class="sxs-lookup"><span data-stu-id="4b8f4-149">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-150">Политика голосовой связи Нью Дели</span><span class="sxs-lookup"><span data-stu-id="4b8f4-150">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-151">Политика голосовой связи Хидерабад</span><span class="sxs-lookup"><span data-stu-id="4b8f4-151">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b8f4-152">Использование PSTN</span><span class="sxs-lookup"><span data-stu-id="4b8f4-152">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-153">Использование Нью Дели, использование УАТС Del, использование Хид УАТС</span><span class="sxs-lookup"><span data-stu-id="4b8f4-153">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-154">Использование Хидерабад, использование Хид УАТС, использование УАТС del</span><span class="sxs-lookup"><span data-stu-id="4b8f4-154">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b8f4-155">превентпстнтоллбипасс</span><span class="sxs-lookup"><span data-stu-id="4b8f4-155">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-156">False</span><span class="sxs-lookup"><span data-stu-id="4b8f4-156">False</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-157">False</span><span class="sxs-lookup"><span data-stu-id="4b8f4-157">False</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a><span data-ttu-id="4b8f4-158">Определение маршрутов голосовой связи</span><span class="sxs-lookup"><span data-stu-id="4b8f4-158">Define Voice Routes</span></span>

<span data-ttu-id="4b8f4-159">Необходимо определить маршруты голосовой связи для развертывания корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="4b8f4-159">You must define voice routes for your Enterprise Voice deployment.</span></span> <span data-ttu-id="4b8f4-160">В этом примере в следующей таблице показаны маршруты голосовых вызовов, используемые в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="4b8f4-160">For this example, the following table illustrates the voice routes used in this scenario.</span></span> <span data-ttu-id="4b8f4-161">Только те параметры, которые относятся к маршрутизации на основе расположения, включены в таблицу для целей иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="4b8f4-161">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="4b8f4-162">Для получения дополнительных сведений см [Настройка маршрутов голосовой связи для исходящих вызовов в Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span><span class="sxs-lookup"><span data-stu-id="4b8f4-162">For more information, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>


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
<th><span data-ttu-id="4b8f4-163">Маршрут голосовых вызовов 1</span><span class="sxs-lookup"><span data-stu-id="4b8f4-163">Voice route 1</span></span></th>
<th><span data-ttu-id="4b8f4-164">Маршрут голосовых вызовов 2</span><span class="sxs-lookup"><span data-stu-id="4b8f4-164">Voice route 2</span></span></th>
<th><span data-ttu-id="4b8f4-165">Маршрут голосовых вызовов 3</span><span class="sxs-lookup"><span data-stu-id="4b8f4-165">Voice route 3</span></span></th>
<th><span data-ttu-id="4b8f4-166">Маршрут голосовых вызовов 4</span><span class="sxs-lookup"><span data-stu-id="4b8f4-166">Voice route 4</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b8f4-167">Имя</span><span class="sxs-lookup"><span data-stu-id="4b8f4-167">Name</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-168">Маршрут Нью Дели</span><span class="sxs-lookup"><span data-stu-id="4b8f4-168">Delhi route</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-169">Маршрут Хидерабад</span><span class="sxs-lookup"><span data-stu-id="4b8f4-169">Hyderabad route</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-170">Маршрут УАТС del</span><span class="sxs-lookup"><span data-stu-id="4b8f4-170">PBX Del route</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-171">Маршрут Хид УАТС</span><span class="sxs-lookup"><span data-stu-id="4b8f4-171">PBX Hyd route</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b8f4-172">Использование PSTN</span><span class="sxs-lookup"><span data-stu-id="4b8f4-172">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-173">Использование Нью Дели</span><span class="sxs-lookup"><span data-stu-id="4b8f4-173">Delhi usage</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-174">Использование Хидерабад</span><span class="sxs-lookup"><span data-stu-id="4b8f4-174">Hyderabad usage</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-175">Использование УАТС del</span><span class="sxs-lookup"><span data-stu-id="4b8f4-175">PBX Del usage</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-176">Использование Хид УАТС</span><span class="sxs-lookup"><span data-stu-id="4b8f4-176">PBX Hyd usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b8f4-177">Магистрали</span><span class="sxs-lookup"><span data-stu-id="4b8f4-177">Trunk</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-178">Магистраль 1 DEL — GW</span><span class="sxs-lookup"><span data-stu-id="4b8f4-178">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-179">Магистраль 2 ХИД (GW)</span><span class="sxs-lookup"><span data-stu-id="4b8f4-179">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-180">Магистраль 3 DEL — УАТС</span><span class="sxs-lookup"><span data-stu-id="4b8f4-180">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-181">Магистраль 4 ХИД — УАТС</span><span class="sxs-lookup"><span data-stu-id="4b8f4-181">Trunk 4 HYD-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a><span data-ttu-id="4b8f4-182">Включение корпоративной голосовой связи для пользователей</span><span class="sxs-lookup"><span data-stu-id="4b8f4-182">Enable Users for Enterprise Voice</span></span>

<span data-ttu-id="4b8f4-183">Разрешить пользователям использовать корпоративную голосовую связь и назначить им политику голосовой связи, которую вы определили ранее.</span><span class="sxs-lookup"><span data-stu-id="4b8f4-183">Enable users for Enterprise Voice and assign them a voice policy you’ve previously defined.</span></span> <span data-ttu-id="4b8f4-184">В этом примере показано назначение, используемое в этом сценарии, в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="4b8f4-184">For this example, the following table illustrates the assignment used in this scenario.</span></span> <span data-ttu-id="4b8f4-185">Только те параметры, которые относятся к маршрутизации на основе расположения, включены в таблицу для целей иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="4b8f4-185">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="4b8f4-186">Дополнительные сведения приведены в статье [Включение поддержки корпоративной голосовой связи для пользователей в Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="4b8f4-186">For more information, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="4b8f4-187">Пользователи, размещенные в Нью Дели</span><span class="sxs-lookup"><span data-stu-id="4b8f4-187">Users located in Delhi</span></span></th>
<th><span data-ttu-id="4b8f4-188">Пользователи, размещенные в Хидерабад</span><span class="sxs-lookup"><span data-stu-id="4b8f4-188">Users located in Hyderabad</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b8f4-189">Связанная политика голосовой связи</span><span class="sxs-lookup"><span data-stu-id="4b8f4-189">Associated voice policy</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-190">Политика голосовой связи Нью Дели</span><span class="sxs-lookup"><span data-stu-id="4b8f4-190">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-191">Политика голосовой связи Хидерабад</span><span class="sxs-lookup"><span data-stu-id="4b8f4-191">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b8f4-192">Примеры пользователей</span><span class="sxs-lookup"><span data-stu-id="4b8f4-192">Sample users</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-193">DEL — LYNC — 1, DEL, LYNC — 2, DEL — LYNC — 3</span><span class="sxs-lookup"><span data-stu-id="4b8f4-193">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
<td><p><span data-ttu-id="4b8f4-194">ХИД — LYNC — 1, ХИД – LYNC – 2, ХИД — LYNC — 3</span><span class="sxs-lookup"><span data-stu-id="4b8f4-194">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4b8f4-195">См. также</span><span class="sxs-lookup"><span data-stu-id="4b8f4-195">See Also</span></span>


[<span data-ttu-id="4b8f4-196">Настройка маршрутизации на основе расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b8f4-196">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

