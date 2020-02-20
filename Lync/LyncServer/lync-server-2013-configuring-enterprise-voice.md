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
ms.openlocfilehash: e888df769a6cf36c3285a167b61a291a7d2c8b9f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151515"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="f9f82-102">Настройка корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9f82-102">Configuring Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9f82-103">_**Последнее изменение темы:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="f9f82-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="f9f82-104">Для развертывания корпоративной голосовой связи необходимо настроить следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="f9f82-104">To deploy Enterprise Voice, you’ll need to configure the following:</span></span>

  - <span data-ttu-id="f9f82-105">Создание магистрали</span><span class="sxs-lookup"><span data-stu-id="f9f82-105">Create a Trunk</span></span>

  - <span data-ttu-id="f9f82-106">Определение политики голосовой связи</span><span class="sxs-lookup"><span data-stu-id="f9f82-106">Define a Voice Policy</span></span>

  - <span data-ttu-id="f9f82-107">Определение маршрута голосовой связи</span><span class="sxs-lookup"><span data-stu-id="f9f82-107">Define a Voice Route</span></span>

  - <span data-ttu-id="f9f82-108">Включение корпоративной голосовой связи для пользователей</span><span class="sxs-lookup"><span data-stu-id="f9f82-108">Enable Users for Enterprise Voice</span></span>

<div>

## <a name="create-a-trunk"></a><span data-ttu-id="f9f82-109">Создание магистрали</span><span class="sxs-lookup"><span data-stu-id="f9f82-109">Create a Trunk</span></span>

<span data-ttu-id="f9f82-110">Необходимо определить магистрали в развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="f9f82-110">You must define trunks in your Enterprise Voice deployment.</span></span> <span data-ttu-id="f9f82-111">Для маршрутизации на основе расположения необходимо создать конфигурацию магистрали для каждой магистрали.</span><span class="sxs-lookup"><span data-stu-id="f9f82-111">For Location-Based Routing, you must create a trunk configuration per trunk.</span></span> <span data-ttu-id="f9f82-112">Используйте построитель топологий Lync Server, чтобы определить магистрали, и используйте командную консоль Windows PowerShell Lync Server, New — CsTrunkConfiguration или панель управления Lync Server, чтобы определить соответствующие конфигурации магистрали.</span><span class="sxs-lookup"><span data-stu-id="f9f82-112">Use the Lync Server Topology Builder to define your trunks, and use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, or the Lync Server Control Panel to define the corresponding trunk configurations.</span></span> <span data-ttu-id="f9f82-113">Дополнительные сведения о включении маршрутизации на основе расположения в конфигурациях магистрали можно найти в разделе Включение маршрутизации на основе расположения в магистрали, а также [Включение маршрутизации на основе расположения в Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="f9f82-113">More information on how to enable Location-Based Routing on trunk configurations can be found in the section, Enable Location-Based Routing to Trunks, in the topic, [Enabling Location-Based Routing in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span></span> <span data-ttu-id="f9f82-114">В этом примере в приведенной ниже таблице показаны магистральные линии, используемые в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="f9f82-114">For this example, the following table illustrates the trunks used in this scenario.</span></span>

<span data-ttu-id="f9f82-115">Дополнительные сведения см в разделе [Определение дополнительных магистральных линий в построителе топологий в Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span><span class="sxs-lookup"><span data-stu-id="f9f82-115">For more information, see [Define additional trunks in Topology Builder in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span></span>


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
<th><span data-ttu-id="f9f82-116">Название магистрали</span><span class="sxs-lookup"><span data-stu-id="f9f82-116">Trunk name</span></span></th>
<th><span data-ttu-id="f9f82-117">Тип системы</span><span class="sxs-lookup"><span data-stu-id="f9f82-117">System type</span></span></th>
<th><span data-ttu-id="f9f82-118">Имя</span><span class="sxs-lookup"><span data-stu-id="f9f82-118">Name</span></span></th>
<th><span data-ttu-id="f9f82-119">Расположение</span><span class="sxs-lookup"><span data-stu-id="f9f82-119">Location</span></span></th>
<th><span data-ttu-id="f9f82-120">Mediation Server (Сервер-посредник);</span><span class="sxs-lookup"><span data-stu-id="f9f82-120">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9f82-121">Магистраль 1 DEL — GW</span><span class="sxs-lookup"><span data-stu-id="f9f82-121">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="f9f82-122">шлюз ТСОП;</span><span class="sxs-lookup"><span data-stu-id="f9f82-122">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="f9f82-123">DEL (GW)</span><span class="sxs-lookup"><span data-stu-id="f9f82-123">DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="f9f82-124">Дели</span><span class="sxs-lookup"><span data-stu-id="f9f82-124">Delhi</span></span></p></td>
<td><p><span data-ttu-id="f9f82-125">MS1</span><span class="sxs-lookup"><span data-stu-id="f9f82-125">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9f82-126">Магистраль 2 ХИД (GW)</span><span class="sxs-lookup"><span data-stu-id="f9f82-126">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="f9f82-127">шлюз ТСОП;</span><span class="sxs-lookup"><span data-stu-id="f9f82-127">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="f9f82-128">ХИД — GW</span><span class="sxs-lookup"><span data-stu-id="f9f82-128">HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="f9f82-129">хидерабад</span><span class="sxs-lookup"><span data-stu-id="f9f82-129">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="f9f82-130">MS1</span><span class="sxs-lookup"><span data-stu-id="f9f82-130">MS1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9f82-131">Магистраль 3 DEL — УАТС</span><span class="sxs-lookup"><span data-stu-id="f9f82-131">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="f9f82-132">ОФИС</span><span class="sxs-lookup"><span data-stu-id="f9f82-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="f9f82-133">DEL — УАТС</span><span class="sxs-lookup"><span data-stu-id="f9f82-133">DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="f9f82-134">Дели</span><span class="sxs-lookup"><span data-stu-id="f9f82-134">Delhi</span></span></p></td>
<td><p><span data-ttu-id="f9f82-135">MS1</span><span class="sxs-lookup"><span data-stu-id="f9f82-135">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9f82-136">Магистраль 4 ХИД — УАТС</span><span class="sxs-lookup"><span data-stu-id="f9f82-136">Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="f9f82-137">ОФИС</span><span class="sxs-lookup"><span data-stu-id="f9f82-137">PBX</span></span></p></td>
<td><p><span data-ttu-id="f9f82-138">ХИД — УАТС</span><span class="sxs-lookup"><span data-stu-id="f9f82-138">HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="f9f82-139">хидерабад</span><span class="sxs-lookup"><span data-stu-id="f9f82-139">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="f9f82-140">MS1</span><span class="sxs-lookup"><span data-stu-id="f9f82-140">MS1</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a><span data-ttu-id="f9f82-141">Определяет политики голосовой связи</span><span class="sxs-lookup"><span data-stu-id="f9f82-141">Defines Voice Policies</span></span>

<span data-ttu-id="f9f82-142">Необходимо определить политики голосовой связи для развертывания корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="f9f82-142">You must define voice policies for your Enterprise Voice deployment.</span></span> <span data-ttu-id="f9f82-143">Определение политики голосовой связи для применения ограничений маршрутизации на основе расположения к подмножеству пользователей, если для использования маршрутизации на основе расположения требуется только подмножество этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="f9f82-143">Define a Voice Policy to enforce Location-Based Routing restrictions to a subset of users if only a subset of them is required to use Location-Based Routing.</span></span> <span data-ttu-id="f9f82-144">В этом примере в следующей таблице показаны политики голосовой связи, используемые в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="f9f82-144">For this example, the following table illustrates the voice policies used in this scenario.</span></span> <span data-ttu-id="f9f82-145">Только те параметры, которые относятся к маршрутизации на основе расположения, включены в таблицу для целей иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="f9f82-145">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="f9f82-146">Дополнительную информацию можно узнать [в статье Настройка политик голосовой связи и сети PSTN для авторизации функций звонков и привилегий в Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span><span class="sxs-lookup"><span data-stu-id="f9f82-146">For more information, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="f9f82-147">Политика голосовой связи 1</span><span class="sxs-lookup"><span data-stu-id="f9f82-147">Voice policy 1</span></span></th>
<th><span data-ttu-id="f9f82-148">Политика голосовой связи 2</span><span class="sxs-lookup"><span data-stu-id="f9f82-148">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9f82-149">Идентификатор политики голосовой связи</span><span class="sxs-lookup"><span data-stu-id="f9f82-149">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="f9f82-150">Политика голосовой связи Нью Дели</span><span class="sxs-lookup"><span data-stu-id="f9f82-150">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="f9f82-151">Политика голосовой связи Хидерабад</span><span class="sxs-lookup"><span data-stu-id="f9f82-151">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9f82-152">Использование PSTN</span><span class="sxs-lookup"><span data-stu-id="f9f82-152">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="f9f82-153">Использование Нью Дели, использование УАТС Del, использование Хид УАТС</span><span class="sxs-lookup"><span data-stu-id="f9f82-153">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="f9f82-154">Использование Хидерабад, использование Хид УАТС, использование УАТС del</span><span class="sxs-lookup"><span data-stu-id="f9f82-154">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9f82-155">превентпстнтоллбипасс</span><span class="sxs-lookup"><span data-stu-id="f9f82-155">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="f9f82-156">False</span><span class="sxs-lookup"><span data-stu-id="f9f82-156">False</span></span></p></td>
<td><p><span data-ttu-id="f9f82-157">False</span><span class="sxs-lookup"><span data-stu-id="f9f82-157">False</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a><span data-ttu-id="f9f82-158">Определение маршрутов голосовой связи</span><span class="sxs-lookup"><span data-stu-id="f9f82-158">Define Voice Routes</span></span>

<span data-ttu-id="f9f82-159">Необходимо определить маршруты голосовой связи для развертывания корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="f9f82-159">You must define voice routes for your Enterprise Voice deployment.</span></span> <span data-ttu-id="f9f82-160">В этом примере в следующей таблице показаны маршруты голосовых вызовов, используемые в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="f9f82-160">For this example, the following table illustrates the voice routes used in this scenario.</span></span> <span data-ttu-id="f9f82-161">Только те параметры, которые относятся к маршрутизации на основе расположения, включены в таблицу для целей иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="f9f82-161">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="f9f82-162">Для получения дополнительных сведений см [Настройка маршрутов голосовой связи для исходящих вызовов в Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span><span class="sxs-lookup"><span data-stu-id="f9f82-162">For more information, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>


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
<th><span data-ttu-id="f9f82-163">Маршрут голосовых вызовов 1</span><span class="sxs-lookup"><span data-stu-id="f9f82-163">Voice route 1</span></span></th>
<th><span data-ttu-id="f9f82-164">Маршрут голосовых вызовов 2</span><span class="sxs-lookup"><span data-stu-id="f9f82-164">Voice route 2</span></span></th>
<th><span data-ttu-id="f9f82-165">Маршрут голосовых вызовов 3</span><span class="sxs-lookup"><span data-stu-id="f9f82-165">Voice route 3</span></span></th>
<th><span data-ttu-id="f9f82-166">Маршрут голосовых вызовов 4</span><span class="sxs-lookup"><span data-stu-id="f9f82-166">Voice route 4</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9f82-167">Имя</span><span class="sxs-lookup"><span data-stu-id="f9f82-167">Name</span></span></p></td>
<td><p><span data-ttu-id="f9f82-168">Маршрут Нью Дели</span><span class="sxs-lookup"><span data-stu-id="f9f82-168">Delhi route</span></span></p></td>
<td><p><span data-ttu-id="f9f82-169">Маршрут Хидерабад</span><span class="sxs-lookup"><span data-stu-id="f9f82-169">Hyderabad route</span></span></p></td>
<td><p><span data-ttu-id="f9f82-170">Маршрут УАТС del</span><span class="sxs-lookup"><span data-stu-id="f9f82-170">PBX Del route</span></span></p></td>
<td><p><span data-ttu-id="f9f82-171">Маршрут Хид УАТС</span><span class="sxs-lookup"><span data-stu-id="f9f82-171">PBX Hyd route</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9f82-172">Использование PSTN</span><span class="sxs-lookup"><span data-stu-id="f9f82-172">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="f9f82-173">Использование Нью Дели</span><span class="sxs-lookup"><span data-stu-id="f9f82-173">Delhi usage</span></span></p></td>
<td><p><span data-ttu-id="f9f82-174">Использование Хидерабад</span><span class="sxs-lookup"><span data-stu-id="f9f82-174">Hyderabad usage</span></span></p></td>
<td><p><span data-ttu-id="f9f82-175">Использование УАТС del</span><span class="sxs-lookup"><span data-stu-id="f9f82-175">PBX Del usage</span></span></p></td>
<td><p><span data-ttu-id="f9f82-176">Использование Хид УАТС</span><span class="sxs-lookup"><span data-stu-id="f9f82-176">PBX Hyd usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9f82-177">Магистрали</span><span class="sxs-lookup"><span data-stu-id="f9f82-177">Trunk</span></span></p></td>
<td><p><span data-ttu-id="f9f82-178">Магистраль 1 DEL — GW</span><span class="sxs-lookup"><span data-stu-id="f9f82-178">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="f9f82-179">Магистраль 2 ХИД (GW)</span><span class="sxs-lookup"><span data-stu-id="f9f82-179">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="f9f82-180">Магистраль 3 DEL — УАТС</span><span class="sxs-lookup"><span data-stu-id="f9f82-180">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="f9f82-181">Магистраль 4 ХИД — УАТС</span><span class="sxs-lookup"><span data-stu-id="f9f82-181">Trunk 4 HYD-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a><span data-ttu-id="f9f82-182">Включение корпоративной голосовой связи для пользователей</span><span class="sxs-lookup"><span data-stu-id="f9f82-182">Enable Users for Enterprise Voice</span></span>

<span data-ttu-id="f9f82-183">Разрешить пользователям использовать корпоративную голосовую связь и назначить им политику голосовой связи, которую вы определили ранее.</span><span class="sxs-lookup"><span data-stu-id="f9f82-183">Enable users for Enterprise Voice and assign them a voice policy you’ve previously defined.</span></span> <span data-ttu-id="f9f82-184">В этом примере показано назначение, используемое в этом сценарии, в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="f9f82-184">For this example, the following table illustrates the assignment used in this scenario.</span></span> <span data-ttu-id="f9f82-185">Только те параметры, которые относятся к маршрутизации на основе расположения, включены в таблицу для целей иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="f9f82-185">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="f9f82-186">Дополнительные сведения приведены в статье [Включение поддержки корпоративной голосовой связи для пользователей в Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="f9f82-186">For more information, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="f9f82-187">Пользователи, размещенные в Нью Дели</span><span class="sxs-lookup"><span data-stu-id="f9f82-187">Users located in Delhi</span></span></th>
<th><span data-ttu-id="f9f82-188">Пользователи, размещенные в Хидерабад</span><span class="sxs-lookup"><span data-stu-id="f9f82-188">Users located in Hyderabad</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9f82-189">Связанная политика голосовой связи</span><span class="sxs-lookup"><span data-stu-id="f9f82-189">Associated voice policy</span></span></p></td>
<td><p><span data-ttu-id="f9f82-190">Политика голосовой связи Нью Дели</span><span class="sxs-lookup"><span data-stu-id="f9f82-190">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="f9f82-191">Политика голосовой связи Хидерабад</span><span class="sxs-lookup"><span data-stu-id="f9f82-191">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9f82-192">Примеры пользователей</span><span class="sxs-lookup"><span data-stu-id="f9f82-192">Sample users</span></span></p></td>
<td><p><span data-ttu-id="f9f82-193">DEL — LYNC — 1, DEL, LYNC — 2, DEL — LYNC — 3</span><span class="sxs-lookup"><span data-stu-id="f9f82-193">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
<td><p><span data-ttu-id="f9f82-194">ХИД — LYNC — 1, ХИД – LYNC – 2, ХИД — LYNC — 3</span><span class="sxs-lookup"><span data-stu-id="f9f82-194">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f9f82-195">См. также</span><span class="sxs-lookup"><span data-stu-id="f9f82-195">See Also</span></span>


[<span data-ttu-id="f9f82-196">Настройка маршрутизации на основе расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9f82-196">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

