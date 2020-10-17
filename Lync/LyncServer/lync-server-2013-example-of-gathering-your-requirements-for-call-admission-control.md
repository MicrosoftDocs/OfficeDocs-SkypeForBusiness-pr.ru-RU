---
title: Пример сбора требований для контроля допуска звонков
description: Пример сбора требований для контроля допуска звонков.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Example of gathering your requirements for call admission control
ms:assetid: 3363ac53-b7c4-4a59-aea1-b2f3ee016ae1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425827(v=OCS.15)
ms:contentKeyID: 48183820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25c0b450070bda62c2610d98cfff8c8cd16ad2af
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564945"
---
# <a name="example-gathering-your-requirements-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="1412d-103">Пример: сбор требований для контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1412d-103">Example: Gathering your requirements for call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1412d-104">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="1412d-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="1412d-p101">В этом примере показано, как спланировать и реализовать контроль допуска звонков (CAC). На высоком уровне этот процесс включает в себя следующие действия:</span><span class="sxs-lookup"><span data-stu-id="1412d-p101">This example shows you how to plan for and implement call admission control (CAC). At a high level, this consists of the following activities:</span></span>

1.  <span data-ttu-id="1412d-107">Определение всех сетевых концентраторов и магистралей (называемых *областями сети*).</span><span class="sxs-lookup"><span data-stu-id="1412d-107">Identify all of your network hubs and backbones (known as *network regions*).</span></span>

2.  <span data-ttu-id="1412d-108">Определите центральный сайт Lync Server, который будет управлять CAC для каждой области сети.</span><span class="sxs-lookup"><span data-stu-id="1412d-108">Identify the Lync Server central site that will manage CAC for each network region.</span></span>

3.  <span data-ttu-id="1412d-109">Определение \*сетевых узлов \*, подключенных к каждой области сети.</span><span class="sxs-lookup"><span data-stu-id="1412d-109">Identify and define the *network sites* that are connected to each network region.</span></span>

4.  <span data-ttu-id="1412d-110">Для каждого сетевого сайта, подключение к которому выполняется с ограниченной полосой пропускания, опишите пропускную способность подключения WAN и ограничения пропускной способности, установленные администратором сети для трафика мультимедиа Lync Server (если это необходимо).</span><span class="sxs-lookup"><span data-stu-id="1412d-110">For each network site whose connection to the WAN is bandwidth-constrained, describe the bandwidth capacity of the WAN connection and the bandwidth limits that to the network administrator has set for Lync Server media traffic, if applicable.</span></span> <span data-ttu-id="1412d-111">Вам не требуется включать узлы, подключения к глобальной сети которых не ограничены по пропускной полосе.</span><span class="sxs-lookup"><span data-stu-id="1412d-111">You do not need to include sites whose connection to the WAN is not bandwidth-constrained.</span></span>

5.  <span data-ttu-id="1412d-112">Свяжите каждую подсеть в сети с сетевым узлом.</span><span class="sxs-lookup"><span data-stu-id="1412d-112">Associate each subnet in your network with a network site.</span></span>

6.  <span data-ttu-id="1412d-113">Сопоставьте каналы между областями сети.</span><span class="sxs-lookup"><span data-stu-id="1412d-113">Map the links between the network regions.</span></span> <span data-ttu-id="1412d-114">Для каждой ссылки опишите свою полосу пропускания и все пределы, которые администратор сети поместил на трафик сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1412d-114">For each link, describe its bandwidth capacity and any limits that the network administrator has placed on Lync Server media traffic.</span></span>

7.  <span data-ttu-id="1412d-115">Определите маршрут между каждой парой областей сети.</span><span class="sxs-lookup"><span data-stu-id="1412d-115">Define a route between every pair of network regions.</span></span>

<div>

## <a name="gather-the-required-information"></a><span data-ttu-id="1412d-116">Сбор необходимой информации</span><span class="sxs-lookup"><span data-stu-id="1412d-116">Gather the Required Information</span></span>

<span data-ttu-id="1412d-117">Чтобы подготовиться к реализации контроля допуска вызовов, соберите информацию, описанную далее:</span><span class="sxs-lookup"><span data-stu-id="1412d-117">To prepare for call admission control, gather the information described in the following steps:</span></span>

1.  <span data-ttu-id="1412d-p104">Определите области сети, которые представляют сетевую магистраль или сетевой концентратор.</span><span class="sxs-lookup"><span data-stu-id="1412d-p104">Identify your network regions. A network region represents a network backbone or a network hub.</span></span>
    
    <span data-ttu-id="1412d-p105">Магистраль или концентратор сети является частью инфраструктуры компьютерной сети, которая соединяет различные части сети, предоставляя путь для обмена информацией между различными локальными сетями или подсетями. Магистраль может объединять различные сети: от небольших локальных сетей до крупномасштабных сетей. Мощность магистрали обычно больше, чем у сетей, подключенных к ней.</span><span class="sxs-lookup"><span data-stu-id="1412d-p105">A network backbone or a network hub is a part of computer network infrastructure that interconnects various pieces of network, providing a path for the exchange of information between different LANs or subnets. A backbone can tie together diverse networks, from a small location to a wide geographic area. The backbone's capacity is typically greater than that of the networks connected to it.</span></span>
    
    <span data-ttu-id="1412d-p106">Пример топологии сети содержит три области: Северная Америка, EMEA (Европа, Ближний Восток и Африка) и APAC (Азиатско-Тихоокеанский регион). Область сети содержит коллекцию сетевых узлов. Определите области сети вашего предприятия вместе с сетевым администратором.</span><span class="sxs-lookup"><span data-stu-id="1412d-p106">Our example topology has three network regions: North America, EMEA, and APAC. A network region contains a collection of network sites. Work with your network administrator to define the network regions for your enterprise.</span></span>

2.  <span data-ttu-id="1412d-126">Определите центральный узел каждой области сети.</span><span class="sxs-lookup"><span data-stu-id="1412d-126">Identify each network region’s associated central site.</span></span> <span data-ttu-id="1412d-127">Центральный сайт содержит по крайней мере один сервер переднего плана и является развертыванием Lync Server, которое будет управлять CAC для всего трафика мультимедиа, который проходит через подключение WAN сетевого региона.</span><span class="sxs-lookup"><span data-stu-id="1412d-127">A central site contains at least one Front End Server and is the Lync Server deployment that will manage CAC for all media traffic that passes through the network region’s WAN connection.</span></span>
    
    <span data-ttu-id="1412d-128">**Пример корпоративной сети, разделенной на три области**</span><span class="sxs-lookup"><span data-stu-id="1412d-128">**An example enterprise network divided into three network regions**</span></span>
    
    <span data-ttu-id="1412d-129">![Пример топологии сети с 3 областями сети](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "Пример топологии сети с 3 областями сети")</span><span class="sxs-lookup"><span data-stu-id="1412d-129">![Network Topology Example with 3 Network Regions](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "Network Topology Example with 3 Network Regions")</span></span>  
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="1412d-130">Сеть MPLS следует представить как область сети, в которой каждому географическому расположению соответствует определенный сетевой узел.</span><span class="sxs-lookup"><span data-stu-id="1412d-130">A Multiprotocol Label Switching (MPLS) network should be represented as a network region in which each geographic location has a corresponding network site.</span></span> <span data-ttu-id="1412d-131">Дополнительные сведения можно найти в разделе "<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">Контроль допуска звонков в сети MPLS с Lync Server 2013</A>" в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="1412d-131">For details, see the “<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">Call admission control on an MPLS network with Lync Server 2013</A>” topic in the Planning documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="1412d-132">В приведенном выше примере топологии сети существует три области сети, каждая с центральным сайтом Lync Server, которая управляет CAC.</span><span class="sxs-lookup"><span data-stu-id="1412d-132">In the preceding example network topology, there are three network regions, each with a Lync Server central site that manages CAC.</span></span> <span data-ttu-id="1412d-133">Соответствующий центральный узел для области сети выбирается на основе географической близости.</span><span class="sxs-lookup"><span data-stu-id="1412d-133">The appropriate central site for a network region is chosen by the geographic vicinity.</span></span> <span data-ttu-id="1412d-134">Так как трафик мультимедиа будет наиболее объемным в областях сети, определение владельца на основе близости позволяет сделать центральный узел автономным и продолжать работу, даже если другие центральные узлы станут недоступными.</span><span class="sxs-lookup"><span data-stu-id="1412d-134">Because media traffic will be heaviest within network regions, the ownership by geographic vicinity makes it self-contained and will continue to be functional even if other central sites become unavailable.</span></span>
    
    <span data-ttu-id="1412d-135">В этом примере развертывание Lync Server с именем Чикаго является центральным сайтом для региона "Северная Америка".</span><span class="sxs-lookup"><span data-stu-id="1412d-135">In this example, a Lync Server deployment named Chicago is the central site for the North America region.</span></span>
    
    <span data-ttu-id="1412d-136">Все пользователи Lync в Северной Америке размещаются на серверах в развертывании в Чикаго.</span><span class="sxs-lookup"><span data-stu-id="1412d-136">All Lync users in North America are homed on servers in the Chicago deployment.</span></span> <span data-ttu-id="1412d-137">В следующей таблице показаны центральные узлы для всех трех областей.</span><span class="sxs-lookup"><span data-stu-id="1412d-137">The following table shows central sites for all three network regions.</span></span>
    
    ### <a name="network-regions-and-their-associated-central-sites"></a><span data-ttu-id="1412d-138">Области сети и связанные с ними центральные узлы</span><span class="sxs-lookup"><span data-stu-id="1412d-138">Network Regions and their Associated Central Sites</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="1412d-139">Область сети</span><span class="sxs-lookup"><span data-stu-id="1412d-139">Network Region</span></span></th>
    <th><span data-ttu-id="1412d-140">Центральный узел</span><span class="sxs-lookup"><span data-stu-id="1412d-140">Central Site</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="1412d-141">Северная Америка</span><span class="sxs-lookup"><span data-stu-id="1412d-141">North America</span></span></p></td>
    <td><p><span data-ttu-id="1412d-142">Офис</span><span class="sxs-lookup"><span data-stu-id="1412d-142">Chicago</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="1412d-143">EMEA</span><span class="sxs-lookup"><span data-stu-id="1412d-143">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="1412d-144">Лондон</span><span class="sxs-lookup"><span data-stu-id="1412d-144">London</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="1412d-145">APAC</span><span class="sxs-lookup"><span data-stu-id="1412d-145">APAC</span></span></p></td>
    <td><p><span data-ttu-id="1412d-146">Пекин</span><span class="sxs-lookup"><span data-stu-id="1412d-146">Beijing</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="1412d-147">В зависимости от топологии Lync Server один центральный сайт может быть назначен нескольким областям сети.</span><span class="sxs-lookup"><span data-stu-id="1412d-147">Depending on your Lync Server topology, the same central site can be assigned to multiple network regions.</span></span>

    
    </div>

3.  <span data-ttu-id="1412d-p111">Для каждой области сети определите все сетевые узлы (офисы или расположения), подключения к глобальной сети которых не ограничены по пропускной способности. Так как ограничений нет, к ним не требуется применять политики пропускной способности CAC.</span><span class="sxs-lookup"><span data-stu-id="1412d-p111">For each network region, identify all of the network sites (offices or locations) whose WAN connections are not bandwidth-constrained. Because these sites are not bandwidth constrained, you do not need to apply CAC bandwidth policies to them.</span></span>
    
    <span data-ttu-id="1412d-150">В примере в следующей таблице у сетевых узлов нет каналов глобальной сети с ограниченной полосой пропускания: Нью-Йорк, Чикаго и Детройт.</span><span class="sxs-lookup"><span data-stu-id="1412d-150">In the example shown in the following table, three network sites do not have bandwidth-constrained WAN links: New York, Chicago, and Detroit.</span></span>
    
    ### <a name="network-sites-not-constrained-by-wan-bandwidth"></a><span data-ttu-id="1412d-151">Сетевые узлы без ограниченной пропускной способностью канала глобальной сети</span><span class="sxs-lookup"><span data-stu-id="1412d-151">Network Sites not Constrained by WAN Bandwidth</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="1412d-152">Сетевой узел</span><span class="sxs-lookup"><span data-stu-id="1412d-152">Network Site</span></span></th>
    <th><span data-ttu-id="1412d-153">Область сети</span><span class="sxs-lookup"><span data-stu-id="1412d-153">Network Region</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="1412d-154">Нью-Йорк</span><span class="sxs-lookup"><span data-stu-id="1412d-154">New York</span></span></p></td>
    <td><p><span data-ttu-id="1412d-155">Северная Америка</span><span class="sxs-lookup"><span data-stu-id="1412d-155">North America</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="1412d-156">Офис</span><span class="sxs-lookup"><span data-stu-id="1412d-156">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="1412d-157">Северная Америка</span><span class="sxs-lookup"><span data-stu-id="1412d-157">North America</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="1412d-158">Детройт</span><span class="sxs-lookup"><span data-stu-id="1412d-158">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="1412d-159">Северная Америка</span><span class="sxs-lookup"><span data-stu-id="1412d-159">North America</span></span></p></td>
    </tr>
    </tbody>
    </table>


4.  <span data-ttu-id="1412d-160">Для каждой области сети определите все сетевые узлы, подключающиеся к области по каналам глобальной сети с ограниченной полосой пропускания.</span><span class="sxs-lookup"><span data-stu-id="1412d-160">For each network region, identify all of the network sites that connect to the network region through bandwidth-constrained WAN links.</span></span>
    
    <span data-ttu-id="1412d-161">Чтобы помочь обеспечить высокое качество звука и видео, рекомендуется отслеживать в этих узлах каналы глобальной сети и использовать политики пропускной способности CAC, которые ограничивают трафик мультимедиа (голос или видео) для данной области сети.</span><span class="sxs-lookup"><span data-stu-id="1412d-161">To help ensure audio and video quality, we recommend that these bandwidth-constrained network sites have their WANs monitored and CAC bandwidth policies that limit media (voice or video) traffic flow to and from the network region.</span></span>
    
    <span data-ttu-id="1412d-162">В примере показано следующей таблице три сетевых узла с ограниченной полосой пропускания глобальной сети: Портленд, Рино и и Альбукерке.</span><span class="sxs-lookup"><span data-stu-id="1412d-162">In the example shown in the following table, there are three network sites that are constrained by WAN bandwidth: Portland, Reno and Albuquerque.</span></span>
    
    ### <a name="network-sites-constrained-by-wan-bandwidth"></a><span data-ttu-id="1412d-163">Сетевые узлы с ограниченной пропускной способностью глобальной сети</span><span class="sxs-lookup"><span data-stu-id="1412d-163">Network Sites Constrained by WAN Bandwidth</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="1412d-164">Сетевой узел</span><span class="sxs-lookup"><span data-stu-id="1412d-164">Network Site</span></span></th>
    <th><span data-ttu-id="1412d-165">Область сети</span><span class="sxs-lookup"><span data-stu-id="1412d-165">Network Region</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="1412d-166">Альбукерке</span><span class="sxs-lookup"><span data-stu-id="1412d-166">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="1412d-167">Северная Америка</span><span class="sxs-lookup"><span data-stu-id="1412d-167">North America</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="1412d-168">Рино</span><span class="sxs-lookup"><span data-stu-id="1412d-168">Reno</span></span></p></td>
    <td><p><span data-ttu-id="1412d-169">Северная Америка</span><span class="sxs-lookup"><span data-stu-id="1412d-169">North America</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="1412d-170">Портленд</span><span class="sxs-lookup"><span data-stu-id="1412d-170">Portland</span></span></p></td>
    <td><p><span data-ttu-id="1412d-171">Северная Америка</span><span class="sxs-lookup"><span data-stu-id="1412d-171">North America</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="1412d-172">**Область сети CAC Северная Америка с тремя сетевыми узлами без ограниченной пропускной способностью (Чикаго, Нью-Йорк и Детройт) и тремя сетевыми узлами с ограниченной пропускной способностью глобальной сети (Портленд, Рино и Альбукерке)**</span><span class="sxs-lookup"><span data-stu-id="1412d-172">**CAC network region North America with three network sites that are unconstrained by bandwidth (Chicago, New York, and Detroit) and three network sites that are constrained by WAN bandwidth (Portland, Reno, and Albuquerque)**</span></span>
    
    <span data-ttu-id="1412d-173">![Пример сетевых сайтов, ограниченных пропускной способностью глобальной сети](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "Пример сетевых сайтов, ограниченных пропускной способностью глобальной сети")</span><span class="sxs-lookup"><span data-stu-id="1412d-173">![Example network sites constrained by WAN bandwidth](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "Example network sites constrained by WAN bandwidth")</span></span>  

5.  <span data-ttu-id="1412d-174">Для каждого канала глобальной сети с ограниченной пропускной способностью определите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="1412d-174">For each bandwidth-constrained WAN link, determine the following:</span></span>
    
      - <span data-ttu-id="1412d-175">Общее ограничение пропускной способности, которое необходимо задать всех параллельных аудиосеансов.</span><span class="sxs-lookup"><span data-stu-id="1412d-175">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="1412d-176">Если новый сеанс аудиозаписи приведет к превышению этого ограничения, Lync Server не разрешает запуск сеанса.</span><span class="sxs-lookup"><span data-stu-id="1412d-176">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="1412d-p113">Ограничение пропускной способности, которое необходимо задать для каждого отдельного аудиосеанса. По умолчанию это ограничение CAC равно 175 кбит/с, но его может изменить администратор.</span><span class="sxs-lookup"><span data-stu-id="1412d-p113">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="1412d-179">Общее ограничение пропускной способности, которое необходимо задать всех параллельных видеосеансов.</span><span class="sxs-lookup"><span data-stu-id="1412d-179">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="1412d-180">Если новый видеосеанс приведет к превышению этого ограничения, Lync Server не разрешает запуск сеанса.</span><span class="sxs-lookup"><span data-stu-id="1412d-180">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="1412d-p115">Ограничение пропускной способности, которое необходимо задать для каждого отдельного видеосеанса. По умолчанию это ограничение CAC равно 700 кбит/с, но его может изменить администратор.</span><span class="sxs-lookup"><span data-stu-id="1412d-p115">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    ### <a name="network-sites-with-wan-bandwidth-constraint-information-bandwidth-in-kbps"></a><span data-ttu-id="1412d-183">Сведения о сетевых узлах с ограниченной пропускной способностью глобальной сети (пропускная способность в кбит/с)</span><span class="sxs-lookup"><span data-stu-id="1412d-183">Network Sites with WAN Bandwidth Constraint Information (Bandwidth in kbps)</span></span>
    
    <table style="width:100%;">
    <colgroup>
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="1412d-184">Сетевой узел</span><span class="sxs-lookup"><span data-stu-id="1412d-184">Network Site</span></span></th>
    <th><span data-ttu-id="1412d-185">Область сети</span><span class="sxs-lookup"><span data-stu-id="1412d-185">Network Region</span></span></th>
    <th><span data-ttu-id="1412d-186">Ограничение пропускной способности</span><span class="sxs-lookup"><span data-stu-id="1412d-186">BW Limit</span></span></th>
    <th><span data-ttu-id="1412d-187">Ограничение для аудио</span><span class="sxs-lookup"><span data-stu-id="1412d-187">Audio Limit</span></span></th>
    <th><span data-ttu-id="1412d-188">Ограничение аудиосеансов</span><span class="sxs-lookup"><span data-stu-id="1412d-188">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="1412d-189">Ограничение для видео</span><span class="sxs-lookup"><span data-stu-id="1412d-189">Video Limit</span></span></th>
    <th><span data-ttu-id="1412d-190">Ограничение видеосеансов</span><span class="sxs-lookup"><span data-stu-id="1412d-190">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="1412d-191">Альбукерке</span><span class="sxs-lookup"><span data-stu-id="1412d-191">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="1412d-192">Северная Америка</span><span class="sxs-lookup"><span data-stu-id="1412d-192">North America</span></span></p></td>
    <td><p><span data-ttu-id="1412d-193">5,000</span><span class="sxs-lookup"><span data-stu-id="1412d-193">5,000</span></span></p></td>
    <td><p><span data-ttu-id="1412d-194">2,000</span><span class="sxs-lookup"><span data-stu-id="1412d-194">2,000</span></span></p></td>
    <td><p><span data-ttu-id="1412d-195">175</span><span class="sxs-lookup"><span data-stu-id="1412d-195">175</span></span></p></td>
    <td><p><span data-ttu-id="1412d-196">1 400</span><span class="sxs-lookup"><span data-stu-id="1412d-196">1,400</span></span></p></td>
    <td><p><span data-ttu-id="1412d-197">700</span><span class="sxs-lookup"><span data-stu-id="1412d-197">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="1412d-198">Рино</span><span class="sxs-lookup"><span data-stu-id="1412d-198">Reno</span></span></p></td>
    <td><p><span data-ttu-id="1412d-199">Северная Америка</span><span class="sxs-lookup"><span data-stu-id="1412d-199">North America</span></span></p></td>
    <td><p><span data-ttu-id="1412d-200">10 000</span><span class="sxs-lookup"><span data-stu-id="1412d-200">10,000</span></span></p></td>
    <td><p><span data-ttu-id="1412d-201">4 000</span><span class="sxs-lookup"><span data-stu-id="1412d-201">4,000</span></span></p></td>
    <td><p><span data-ttu-id="1412d-202">175</span><span class="sxs-lookup"><span data-stu-id="1412d-202">175</span></span></p></td>
    <td><p><span data-ttu-id="1412d-203">2 800</span><span class="sxs-lookup"><span data-stu-id="1412d-203">2,800</span></span></p></td>
    <td><p><span data-ttu-id="1412d-204">700</span><span class="sxs-lookup"><span data-stu-id="1412d-204">700</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="1412d-205">Портленд</span><span class="sxs-lookup"><span data-stu-id="1412d-205">Portland</span></span></p></td>
    <td><p><span data-ttu-id="1412d-206">Северная Америка</span><span class="sxs-lookup"><span data-stu-id="1412d-206">North America</span></span></p></td>
    <td><p><span data-ttu-id="1412d-207">5,000</span><span class="sxs-lookup"><span data-stu-id="1412d-207">5,000</span></span></p></td>
    <td><p><span data-ttu-id="1412d-208">4 000</span><span class="sxs-lookup"><span data-stu-id="1412d-208">4,000</span></span></p></td>
    <td><p><span data-ttu-id="1412d-209">175</span><span class="sxs-lookup"><span data-stu-id="1412d-209">175</span></span></p></td>
    <td><p><span data-ttu-id="1412d-210">2 800</span><span class="sxs-lookup"><span data-stu-id="1412d-210">2,800</span></span></p></td>
    <td><p><span data-ttu-id="1412d-211">700</span><span class="sxs-lookup"><span data-stu-id="1412d-211">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="1412d-212">Нью-Йорк</span><span class="sxs-lookup"><span data-stu-id="1412d-212">New York</span></span></p></td>
    <td><p><span data-ttu-id="1412d-213">Северная Америка</span><span class="sxs-lookup"><span data-stu-id="1412d-213">North America</span></span></p></td>
    <td><p><span data-ttu-id="1412d-214">(без ограничений)</span><span class="sxs-lookup"><span data-stu-id="1412d-214">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1412d-215">(без ограничений)</span><span class="sxs-lookup"><span data-stu-id="1412d-215">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1412d-216">(без ограничений)</span><span class="sxs-lookup"><span data-stu-id="1412d-216">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1412d-217">(без ограничений)</span><span class="sxs-lookup"><span data-stu-id="1412d-217">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1412d-218">(без ограничений)</span><span class="sxs-lookup"><span data-stu-id="1412d-218">(no limit)</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="1412d-219">Офис</span><span class="sxs-lookup"><span data-stu-id="1412d-219">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="1412d-220">Северная Америка</span><span class="sxs-lookup"><span data-stu-id="1412d-220">North America</span></span></p></td>
    <td><p><span data-ttu-id="1412d-221">(без ограничений)</span><span class="sxs-lookup"><span data-stu-id="1412d-221">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1412d-222">(без ограничений)</span><span class="sxs-lookup"><span data-stu-id="1412d-222">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1412d-223">(без ограничений)</span><span class="sxs-lookup"><span data-stu-id="1412d-223">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1412d-224">(без ограничений)</span><span class="sxs-lookup"><span data-stu-id="1412d-224">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1412d-225">(без ограничений)</span><span class="sxs-lookup"><span data-stu-id="1412d-225">(no limit)</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="1412d-226">Детройт</span><span class="sxs-lookup"><span data-stu-id="1412d-226">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="1412d-227">Северная Америка</span><span class="sxs-lookup"><span data-stu-id="1412d-227">North America</span></span></p></td>
    <td><p><span data-ttu-id="1412d-228">(без ограничений)</span><span class="sxs-lookup"><span data-stu-id="1412d-228">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1412d-229">(без ограничений)</span><span class="sxs-lookup"><span data-stu-id="1412d-229">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1412d-230">(без ограничений)</span><span class="sxs-lookup"><span data-stu-id="1412d-230">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1412d-231">(без ограничений)</span><span class="sxs-lookup"><span data-stu-id="1412d-231">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1412d-232">(без ограничений)</span><span class="sxs-lookup"><span data-stu-id="1412d-232">(no limit)</span></span></p></td>
    </tr>
    </tbody>
    </table>


6.  <span data-ttu-id="1412d-233">Для каждой подсети в вашей сети укажите связанные с ними сетевой узел.</span><span class="sxs-lookup"><span data-stu-id="1412d-233">For every subnet in your network, specify its associated network site.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="1412d-p116">Каждая подсеть необходимо связать с сетевым узлом, даже если он не ограничен по пропускной способности. Это связано с тем, что контроль допуска вызовов использует информацию о подсети, чтобы определить, в каком сетевом узле расположена конечная точка. Когда расположение обеих сторон сеанса определено, контроль допуска вызовов может определить, достаточно ли пропускной способности для осуществления вызова. Когда сеанс инициируется по каналу без ограничения пропускной способности, создается предупреждение.</span><span class="sxs-lookup"><span data-stu-id="1412d-p116">Every subnet in your network must be associated with a network site, even if the network site is not bandwidth constrained. This is because call admission control uses subnet information to determine at which network site an endpoint is located. When the locations of both parties in the session are determined, call admission control can determine if there is sufficient bandwidth to establish a call. When a session is established over a link that has no bandwidth limits, an alert is generated.</span></span><BR><span data-ttu-id="1412d-238">Если развертываются пограничные серверы аудио- и видеоданных, общедоступные IP-адреса каждого из них должны быть связаны с сетевым узлом, в котором развертывается пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="1412d-238">If you deploy Audio/Video Edge Servers, the public IP addresses of each Edge Server must be associated with the network site where the Edge Server is deployed.</span></span> <span data-ttu-id="1412d-239">Каждый общедоступный IP-адрес пограничного сервера аудио- и видеоданных должен быть добавлен в параметры конфигурации сети как подсеть с маской 32.</span><span class="sxs-lookup"><span data-stu-id="1412d-239">Each public IP address of the A/V Edge Server must be added to your network configuration settings as a subnet with a subnet mask of 32.</span></span> <span data-ttu-id="1412d-240">Например, если вы развертываете пограничные серверы аудио- и видеоданных в Чикаго, затем для каждого внешнего IP-адреса этих серверов создаете подсеть с маской 32 и связываете сетевой узел Чикаго с этими подсетями.</span><span class="sxs-lookup"><span data-stu-id="1412d-240">For example, if you deploy A/V Edge Servers in Chicago, then for each external IP address of those servers create a subnet with a subnet mask of 32 and associate network site Chicago with those subnets.</span></span> <span data-ttu-id="1412d-241">Подробнее об общедоступных IP-адресах можно узнать в статье <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Определение требований к портам внешнего аудио-и видеоподключения для Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="1412d-241">For details about public IP addresses, see <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Determine external A/V firewall and port requirements for Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="1412d-p118">Формируется предупреждение ключевого индикатора работоспособности (KHI) со списком списка IP-адресов, которые существуют в сети, но которые либо не связаны с подсетью или связаны с подсетью, включающей IP-адреса, не связанные с сетевым узлом. Данное предупреждение не формируется более одного раза в течение 8 часов. Далее представлен сведения о предупреждении и пример:</span><span class="sxs-lookup"><span data-stu-id="1412d-p118">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site. This alert will not be raised more than once within an 8 hour period. The relevant alert information and an example are as follows:</span></span><BR><span data-ttu-id="1412d-245"><STRONG>Источник:</STRONG> Служба политики пропускной способности CS (ядро)</span><span class="sxs-lookup"><span data-stu-id="1412d-245"><STRONG>Source:</STRONG> CS Bandwidth Policy Service (Core)</span></span><BR><span data-ttu-id="1412d-246"><STRONG>Номер события:</STRONG> 36034</span><span class="sxs-lookup"><span data-stu-id="1412d-246"><STRONG>Event number:</STRONG> 36034</span></span><BR><span data-ttu-id="1412d-247"><STRONG>Уровень:</STRONG> 2</span><span class="sxs-lookup"><span data-stu-id="1412d-247"><STRONG>Level:</STRONG> 2</span></span><BR><span data-ttu-id="1412d-248"><STRONG>Description:</STRONG> Подсети для следующих IP-адресов: &lt; список IP-адресов &gt; либо не настроен, либо подсети не связаны с сетевым сайтом.</span><span class="sxs-lookup"><span data-stu-id="1412d-248"><STRONG>Description:</STRONG> The subnets for the following IP Addresses: &lt;List of IP Addresses&gt; are either not configured or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="1412d-249"><STRONG>Причина:</STRONG> Подсети для соответствующих IP-адресов отсутствуют в параметрах конфигурации сети, или подсети не связаны с сетевым сайтом.</span><span class="sxs-lookup"><span data-stu-id="1412d-249"><STRONG>Cause:</STRONG> The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="1412d-250"><STRONG>Решение:</STRONG> Добавьте подсети, соответствующие предыдущему списку IP-адресов, в параметры конфигурации сети и свяжите каждую подсеть с сетевым сайтом.</span><span class="sxs-lookup"><span data-stu-id="1412d-250"><STRONG>Resolution:</STRONG> Add subnets corresponding to the preceding list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span><BR><span data-ttu-id="1412d-p119">Например, если список IP-адресов в предупреждении содержит адреса 10.121.248.226 и 10.121.249.20, эти IP-адреса не связаны с подсетью или же подсеть, с которой они связаны, не принадлежат сетевому узлу. Если 10.121.248.0/24 и 10.121.249.0/24 являются соответствующими подсетями для этих адресов, эту проблему можно решить следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1412d-p119">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet, or the subnet that they are associated with does not belong to a network site. If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="1412d-253">убедитесь, что IP-адрес 10.121.248.226 связан с подсетью 10.121.248.0/24, а IP-адрес 10.121.249.20 связан с подсетью 10.121.249.0/24;</span><span class="sxs-lookup"><span data-stu-id="1412d-253">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="1412d-254">убедитесь, что подсети 10.121.249.0/24 и 10.121.248.0/24 связаны с сетевым узлом.</span><span class="sxs-lookup"><span data-stu-id="1412d-254">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span></P></LI></OL>

    
    </div>
    
    ### <a name="network-sites-and-associated-subnets-bandwidth-in-kbps"></a><span data-ttu-id="1412d-255">Сетевые узлы и связанные подсети (пропускная способность в кбит/с)</span><span class="sxs-lookup"><span data-stu-id="1412d-255">Network Sites and Associated Subnets (Bandwidth in kbps)</span></span>
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="1412d-256">Сетевой узел</span><span class="sxs-lookup"><span data-stu-id="1412d-256">Network Site</span></span></th>
    <th><span data-ttu-id="1412d-257">Область сети</span><span class="sxs-lookup"><span data-stu-id="1412d-257">Network Region</span></span></th>
    <th><span data-ttu-id="1412d-258">Ограничение пропускной способности</span><span class="sxs-lookup"><span data-stu-id="1412d-258">BW Limit</span></span></th>
    <th><span data-ttu-id="1412d-259">Ограничение для аудио</span><span class="sxs-lookup"><span data-stu-id="1412d-259">Audio Limit</span></span></th>
    <th><span data-ttu-id="1412d-260">Ограничение аудиосеансов</span><span class="sxs-lookup"><span data-stu-id="1412d-260">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="1412d-261">Ограничение для видео</span><span class="sxs-lookup"><span data-stu-id="1412d-261">Video Limit</span></span></th>
    <th><span data-ttu-id="1412d-262">Ограничение видеосеансов</span><span class="sxs-lookup"><span data-stu-id="1412d-262">Video Session Limit</span></span></th>
    <th><span data-ttu-id="1412d-263">Подсети</span><span class="sxs-lookup"><span data-stu-id="1412d-263">Subnets</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="1412d-264">Альбукерке</span><span class="sxs-lookup"><span data-stu-id="1412d-264">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="1412d-265">Северная Америка</span><span class="sxs-lookup"><span data-stu-id="1412d-265">North America</span></span></p></td>
    <td><p><span data-ttu-id="1412d-266">5,000</span><span class="sxs-lookup"><span data-stu-id="1412d-266">5,000</span></span></p></td>
    <td><p><span data-ttu-id="1412d-267">2,000</span><span class="sxs-lookup"><span data-stu-id="1412d-267">2,000</span></span></p></td>
    <td><p><span data-ttu-id="1412d-268">175</span><span class="sxs-lookup"><span data-stu-id="1412d-268">175</span></span></p></td>
    <td><p><span data-ttu-id="1412d-269">1 400</span><span class="sxs-lookup"><span data-stu-id="1412d-269">1,400</span></span></p></td>
    <td><p><span data-ttu-id="1412d-270">700</span><span class="sxs-lookup"><span data-stu-id="1412d-270">700</span></span></p></td>
    <td><p><span data-ttu-id="1412d-271">172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</span><span class="sxs-lookup"><span data-stu-id="1412d-271">172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="1412d-272">Рино</span><span class="sxs-lookup"><span data-stu-id="1412d-272">Reno</span></span></p></td>
    <td><p><span data-ttu-id="1412d-273">Северная Америка</span><span class="sxs-lookup"><span data-stu-id="1412d-273">North America</span></span></p></td>
    <td><p><span data-ttu-id="1412d-274">10 000</span><span class="sxs-lookup"><span data-stu-id="1412d-274">10,000</span></span></p></td>
    <td><p><span data-ttu-id="1412d-275">4 000</span><span class="sxs-lookup"><span data-stu-id="1412d-275">4,000</span></span></p></td>
    <td><p><span data-ttu-id="1412d-276">175</span><span class="sxs-lookup"><span data-stu-id="1412d-276">175</span></span></p></td>
    <td><p><span data-ttu-id="1412d-277">2 800</span><span class="sxs-lookup"><span data-stu-id="1412d-277">2,800</span></span></p></td>
    <td><p><span data-ttu-id="1412d-278">700</span><span class="sxs-lookup"><span data-stu-id="1412d-278">700</span></span></p></td>
    <td><p><span data-ttu-id="1412d-279">157.57.210.0/23, 172.28.151.128/25</span><span class="sxs-lookup"><span data-stu-id="1412d-279">157.57.210.0/23, 172.28.151.128/25</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="1412d-280">Портленд</span><span class="sxs-lookup"><span data-stu-id="1412d-280">Portland</span></span></p></td>
    <td><p><span data-ttu-id="1412d-281">Северная Америка</span><span class="sxs-lookup"><span data-stu-id="1412d-281">North America</span></span></p></td>
    <td><p><span data-ttu-id="1412d-282">5,000</span><span class="sxs-lookup"><span data-stu-id="1412d-282">5,000</span></span></p></td>
    <td><p><span data-ttu-id="1412d-283">4 000</span><span class="sxs-lookup"><span data-stu-id="1412d-283">4,000</span></span></p></td>
    <td><p><span data-ttu-id="1412d-284">175</span><span class="sxs-lookup"><span data-stu-id="1412d-284">175</span></span></p></td>
    <td><p><span data-ttu-id="1412d-285">2 800</span><span class="sxs-lookup"><span data-stu-id="1412d-285">2,800</span></span></p></td>
    <td><p><span data-ttu-id="1412d-286">700</span><span class="sxs-lookup"><span data-stu-id="1412d-286">700</span></span></p></td>
    <td><p><span data-ttu-id="1412d-287">172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</span><span class="sxs-lookup"><span data-stu-id="1412d-287">172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="1412d-288">Нью-Йорк</span><span class="sxs-lookup"><span data-stu-id="1412d-288">New York</span></span></p></td>
    <td><p><span data-ttu-id="1412d-289">Северная Америка</span><span class="sxs-lookup"><span data-stu-id="1412d-289">North America</span></span></p></td>
    <td><p><span data-ttu-id="1412d-290">(без ограничений)</span><span class="sxs-lookup"><span data-stu-id="1412d-290">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1412d-291">(без ограничений)</span><span class="sxs-lookup"><span data-stu-id="1412d-291">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1412d-292">(без ограничений)</span><span class="sxs-lookup"><span data-stu-id="1412d-292">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1412d-293">(без ограничений)</span><span class="sxs-lookup"><span data-stu-id="1412d-293">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1412d-294">(без ограничений)</span><span class="sxs-lookup"><span data-stu-id="1412d-294">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1412d-295">172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</span><span class="sxs-lookup"><span data-stu-id="1412d-295">172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="1412d-296">Офис</span><span class="sxs-lookup"><span data-stu-id="1412d-296">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="1412d-297">Северная Америка</span><span class="sxs-lookup"><span data-stu-id="1412d-297">North America</span></span></p></td>
    <td><p><span data-ttu-id="1412d-298">(без ограничений)</span><span class="sxs-lookup"><span data-stu-id="1412d-298">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1412d-299">(без ограничений)</span><span class="sxs-lookup"><span data-stu-id="1412d-299">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1412d-300">(без ограничений)</span><span class="sxs-lookup"><span data-stu-id="1412d-300">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1412d-301">(без ограничений)</span><span class="sxs-lookup"><span data-stu-id="1412d-301">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1412d-302">(без ограничений)</span><span class="sxs-lookup"><span data-stu-id="1412d-302">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1412d-303">157.57.211.0/23, 172.28.152.128/25</span><span class="sxs-lookup"><span data-stu-id="1412d-303">157.57.211.0/23, 172.28.152.128/25</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="1412d-304">Детройт</span><span class="sxs-lookup"><span data-stu-id="1412d-304">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="1412d-305">Северная Америка</span><span class="sxs-lookup"><span data-stu-id="1412d-305">North America</span></span></p></td>
    <td><p><span data-ttu-id="1412d-306">(без ограничений)</span><span class="sxs-lookup"><span data-stu-id="1412d-306">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1412d-307">(без ограничений)</span><span class="sxs-lookup"><span data-stu-id="1412d-307">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1412d-308">(без ограничений)</span><span class="sxs-lookup"><span data-stu-id="1412d-308">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1412d-309">(без ограничений)</span><span class="sxs-lookup"><span data-stu-id="1412d-309">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1412d-310">(без ограничений)</span><span class="sxs-lookup"><span data-stu-id="1412d-310">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="1412d-311">172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</span><span class="sxs-lookup"><span data-stu-id="1412d-311">172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</span></span></p></td>
    </tr>
    </tbody>
    </table>


7.  <span data-ttu-id="1412d-312">В элементе управления допуском вызовов Lync Server подключения между сетевыми областями называются *связями областей*.</span><span class="sxs-lookup"><span data-stu-id="1412d-312">In Lync Server call admission control, the connections between network regions are called *region links*.</span></span> <span data-ttu-id="1412d-313">Для каждой связи области определите следующие параметры (как и для сетевых узлов):</span><span class="sxs-lookup"><span data-stu-id="1412d-313">For each region link, determine the following, just as you did for the network sites:</span></span>
    
      - <span data-ttu-id="1412d-314">Общее ограничение пропускной способности, которое необходимо задать всех параллельных аудиосеансов.</span><span class="sxs-lookup"><span data-stu-id="1412d-314">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="1412d-315">Если новый сеанс аудиозаписи приведет к превышению этого ограничения, Lync Server не разрешает запуск сеанса.</span><span class="sxs-lookup"><span data-stu-id="1412d-315">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="1412d-p122">Ограничение пропускной способности, которое необходимо задать для каждого отдельного аудиосеанса. По умолчанию это ограничение CAC равно 175 кбит/с, но его может изменить администратор.</span><span class="sxs-lookup"><span data-stu-id="1412d-p122">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="1412d-318">Общее ограничение пропускной способности, которое необходимо задать всех параллельных видеосеансов.</span><span class="sxs-lookup"><span data-stu-id="1412d-318">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="1412d-319">Если новый видеосеанс приведет к превышению этого ограничения, Lync Server не разрешает запуск сеанса.</span><span class="sxs-lookup"><span data-stu-id="1412d-319">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="1412d-p124">Ограничение пропускной способности, которое необходимо задать для каждого отдельного видеосеанса. По умолчанию это ограничение CAC равно 700 кбит/с, но его может изменить администратор.</span><span class="sxs-lookup"><span data-stu-id="1412d-p124">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    <span data-ttu-id="1412d-322">**Связи областей сети с соответствующими ограничениями пропускной способности**</span><span class="sxs-lookup"><span data-stu-id="1412d-322">**Network Region links with associated bandwidth limits**</span></span>
    
    <span data-ttu-id="1412d-323">![Пример ограничений между 3 областями](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "Пример ограничений между 3 областями")</span><span class="sxs-lookup"><span data-stu-id="1412d-323">![Example of Limitations between 3 Regions](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "Example of Limitations between 3 Regions")</span></span>  
    
    ### <a name="region-link-bandwidth-information-bandwidth-in-kbps"></a><span data-ttu-id="1412d-324">Сведения о пропускной способности связи области (полоса пропускания в кбит/с)</span><span class="sxs-lookup"><span data-stu-id="1412d-324">Region Link Bandwidth Information (Bandwidth in kbps)</span></span>
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="1412d-325">Имя связи области</span><span class="sxs-lookup"><span data-stu-id="1412d-325">Region Link Name</span></span></th>
    <th><span data-ttu-id="1412d-326">Первая область</span><span class="sxs-lookup"><span data-stu-id="1412d-326">First Region</span></span></th>
    <th><span data-ttu-id="1412d-327">Вторая область</span><span class="sxs-lookup"><span data-stu-id="1412d-327">Second Region</span></span></th>
    <th><span data-ttu-id="1412d-328">Ограничение пропускной способности</span><span class="sxs-lookup"><span data-stu-id="1412d-328">BW Limit</span></span></th>
    <th><span data-ttu-id="1412d-329">Ограничение для аудио</span><span class="sxs-lookup"><span data-stu-id="1412d-329">Audio Limit</span></span></th>
    <th><span data-ttu-id="1412d-330">Ограничение аудиосеансов</span><span class="sxs-lookup"><span data-stu-id="1412d-330">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="1412d-331">Ограничение для видео</span><span class="sxs-lookup"><span data-stu-id="1412d-331">Video Limit</span></span></th>
    <th><span data-ttu-id="1412d-332">Ограничение видеосеансов</span><span class="sxs-lookup"><span data-stu-id="1412d-332">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="1412d-333">NA – EMEA — ССЫЛКА</span><span class="sxs-lookup"><span data-stu-id="1412d-333">NA-EMEA-LINK</span></span></p></td>
    <td><p><span data-ttu-id="1412d-334">Северная Америка</span><span class="sxs-lookup"><span data-stu-id="1412d-334">North America</span></span></p></td>
    <td><p><span data-ttu-id="1412d-335">EMEA</span><span class="sxs-lookup"><span data-stu-id="1412d-335">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="1412d-336">50 000</span><span class="sxs-lookup"><span data-stu-id="1412d-336">50,000</span></span></p></td>
    <td><p><span data-ttu-id="1412d-337">20,000</span><span class="sxs-lookup"><span data-stu-id="1412d-337">20,000</span></span></p></td>
    <td><p><span data-ttu-id="1412d-338">175</span><span class="sxs-lookup"><span data-stu-id="1412d-338">175</span></span></p></td>
    <td><p><span data-ttu-id="1412d-339">14 000</span><span class="sxs-lookup"><span data-stu-id="1412d-339">14,000</span></span></p></td>
    <td><p><span data-ttu-id="1412d-340">700</span><span class="sxs-lookup"><span data-stu-id="1412d-340">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="1412d-341">EMEA — APAC — LINK</span><span class="sxs-lookup"><span data-stu-id="1412d-341">EMEA-APAC-LINK</span></span></p></td>
    <td><p><span data-ttu-id="1412d-342">EMEA</span><span class="sxs-lookup"><span data-stu-id="1412d-342">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="1412d-343">APAC</span><span class="sxs-lookup"><span data-stu-id="1412d-343">APAC</span></span></p></td>
    <td><p><span data-ttu-id="1412d-344">25 000 </span><span class="sxs-lookup"><span data-stu-id="1412d-344">25,000</span></span></p></td>
    <td><p><span data-ttu-id="1412d-345">10 000</span><span class="sxs-lookup"><span data-stu-id="1412d-345">10,000</span></span></p></td>
    <td><p><span data-ttu-id="1412d-346">175</span><span class="sxs-lookup"><span data-stu-id="1412d-346">175</span></span></p></td>
    <td><p><span data-ttu-id="1412d-347">7 000</span><span class="sxs-lookup"><span data-stu-id="1412d-347">7,000</span></span></p></td>
    <td><p><span data-ttu-id="1412d-348">700</span><span class="sxs-lookup"><span data-stu-id="1412d-348">700</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="1412d-349">Определите маршрут между каждой парой областей сети.</span><span class="sxs-lookup"><span data-stu-id="1412d-349">Define a route between every pair of network regions.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="1412d-350">Две связи необходимы для маршрута между Северной Америкой и Азиатско-Тихоокеанской областью, поскольку отсутствует связь, которая напрямую связывает их.</span><span class="sxs-lookup"><span data-stu-id="1412d-350">Two links are required for the route between the North America and APAC regions because there is no region link that directly connects them.</span></span>

    
    </div>
    
    ### <a name="region-routes"></a><span data-ttu-id="1412d-351">Маршруты области</span><span class="sxs-lookup"><span data-stu-id="1412d-351">Region Routes</span></span>
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="1412d-352">Имя маршрута области</span><span class="sxs-lookup"><span data-stu-id="1412d-352">Region Route Name</span></span></th>
    <th><span data-ttu-id="1412d-353">Первая область</span><span class="sxs-lookup"><span data-stu-id="1412d-353">First Region</span></span></th>
    <th><span data-ttu-id="1412d-354">Вторая область</span><span class="sxs-lookup"><span data-stu-id="1412d-354">Second Region</span></span></th>
    <th><span data-ttu-id="1412d-355">Связи области</span><span class="sxs-lookup"><span data-stu-id="1412d-355">Region Links</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="1412d-356">NA – EMEA — МАРШРУТ</span><span class="sxs-lookup"><span data-stu-id="1412d-356">NA-EMEA-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="1412d-357">Северная Америка</span><span class="sxs-lookup"><span data-stu-id="1412d-357">North America</span></span></p></td>
    <td><p><span data-ttu-id="1412d-358">EMEA</span><span class="sxs-lookup"><span data-stu-id="1412d-358">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="1412d-359">NA – EMEA — ССЫЛКА</span><span class="sxs-lookup"><span data-stu-id="1412d-359">NA-EMEA-LINK</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="1412d-360">EMEA — APAC — ROUTE</span><span class="sxs-lookup"><span data-stu-id="1412d-360">EMEA-APAC-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="1412d-361">EMEA</span><span class="sxs-lookup"><span data-stu-id="1412d-361">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="1412d-362">APAC</span><span class="sxs-lookup"><span data-stu-id="1412d-362">APAC</span></span></p></td>
    <td><p><span data-ttu-id="1412d-363">EMEA — APAC — LINK</span><span class="sxs-lookup"><span data-stu-id="1412d-363">EMEA-APAC-LINK</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="1412d-364">NA — APAC — ROUTE</span><span class="sxs-lookup"><span data-stu-id="1412d-364">NA-APAC-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="1412d-365">Северная Америка</span><span class="sxs-lookup"><span data-stu-id="1412d-365">North America</span></span></p></td>
    <td><p><span data-ttu-id="1412d-366">APAC</span><span class="sxs-lookup"><span data-stu-id="1412d-366">APAC</span></span></p></td>
    <td><p><span data-ttu-id="1412d-367">NA-EMEA-LINK, EMEA-APAC-LINK</span><span class="sxs-lookup"><span data-stu-id="1412d-367">NA-EMEA-LINK, EMEA-APAC-LINK</span></span></p></td>
    </tr>
    </tbody>
    </table>


9.  <span data-ttu-id="1412d-368">Для каждой пары сетевых узлов, которые соединены напрямую одной связью (которую называют *межсайтовой* связью), определите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="1412d-368">For every pair of network sites that are directly connected by a single link (called an *inter-site* link), determine the following:</span></span>
    
      - <span data-ttu-id="1412d-369">Общее ограничение пропускной способности, которое необходимо задать всех параллельных аудиосеансов.</span><span class="sxs-lookup"><span data-stu-id="1412d-369">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="1412d-370">Если новый сеанс аудиозаписи приведет к превышению этого ограничения, Lync Server не разрешает запуск сеанса.</span><span class="sxs-lookup"><span data-stu-id="1412d-370">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="1412d-p126">Ограничение пропускной способности, которое необходимо задать для каждого отдельного аудиосеанса. По умолчанию это ограничение CAC равно 175 кбит/с, но его может изменить администратор.</span><span class="sxs-lookup"><span data-stu-id="1412d-p126">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="1412d-373">Общее ограничение пропускной способности, которое необходимо задать всех параллельных видеосеансов.</span><span class="sxs-lookup"><span data-stu-id="1412d-373">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="1412d-374">Если новый видеосеанс приведет к превышению этого ограничения, Lync Server не разрешает запуск сеанса.</span><span class="sxs-lookup"><span data-stu-id="1412d-374">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="1412d-p128">Ограничение пропускной способности, которое необходимо задать для каждого отдельного видеосеанса. По умолчанию это ограничение CAC равно 700 кбит/с, но его может изменить администратор.</span><span class="sxs-lookup"><span data-stu-id="1412d-p128">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    <span data-ttu-id="1412d-377">**Область сети CAC Северная Америка с отображением пропускной способности и ограничений пропускной способности для межсайтовой связи между Рино и Альбукерке**</span><span class="sxs-lookup"><span data-stu-id="1412d-377">**CAC network region North America showing the bandwidth capacities and bandwidth limits for the inter-site link between Reno and Albuquerque**</span></span>
    
    <span data-ttu-id="1412d-378">![Пример сетевых сайтов, ограниченных пропускной способностью глобальной сети](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "Пример сетевых сайтов, ограниченных пропускной способностью глобальной сети")</span><span class="sxs-lookup"><span data-stu-id="1412d-378">![Network Sites Constrained by WAN Bandwidth example](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "Network Sites Constrained by WAN Bandwidth example")</span></span>  
    
    ### <a name="bandwidth-information-for-an-inter-site-link-between-two-network-sites-bandwidth-in-kbps"></a><span data-ttu-id="1412d-379">Сведения о пропускной способности межсайтовой связи между двумя сетевыми узлами (пропускная способность в кбит/с)</span><span class="sxs-lookup"><span data-stu-id="1412d-379">Bandwidth Information for an Inter-Site Link between Two Network Sites (Bandwidth in kbps)</span></span>
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="1412d-380">Имя межсайтовой связи</span><span class="sxs-lookup"><span data-stu-id="1412d-380">Inter-Site Link Name</span></span></th>
    <th><span data-ttu-id="1412d-381">Первый узел</span><span class="sxs-lookup"><span data-stu-id="1412d-381">First Site</span></span></th>
    <th><span data-ttu-id="1412d-382">Второй узел</span><span class="sxs-lookup"><span data-stu-id="1412d-382">Second Site</span></span></th>
    <th><span data-ttu-id="1412d-383">Ограничение пропускной способности</span><span class="sxs-lookup"><span data-stu-id="1412d-383">BW Limit</span></span></th>
    <th><span data-ttu-id="1412d-384">Ограничение для аудио</span><span class="sxs-lookup"><span data-stu-id="1412d-384">Audio Limit</span></span></th>
    <th><span data-ttu-id="1412d-385">Ограничение аудиосеансов</span><span class="sxs-lookup"><span data-stu-id="1412d-385">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="1412d-386">Ограничение для видео</span><span class="sxs-lookup"><span data-stu-id="1412d-386">Video Limit</span></span></th>
    <th><span data-ttu-id="1412d-387">Ограничение видеосеансов</span><span class="sxs-lookup"><span data-stu-id="1412d-387">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="1412d-388">Рино — Албу — сайт — ссылка</span><span class="sxs-lookup"><span data-stu-id="1412d-388">Reno-Albu-Intersite-Link</span></span></p></td>
    <td><p><span data-ttu-id="1412d-389">Рино</span><span class="sxs-lookup"><span data-stu-id="1412d-389">Reno</span></span></p></td>
    <td><p><span data-ttu-id="1412d-390">Альбукерке</span><span class="sxs-lookup"><span data-stu-id="1412d-390">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="1412d-391">20,000</span><span class="sxs-lookup"><span data-stu-id="1412d-391">20,000</span></span></p></td>
    <td><p><span data-ttu-id="1412d-392">12 000</span><span class="sxs-lookup"><span data-stu-id="1412d-392">12,000</span></span></p></td>
    <td><p><span data-ttu-id="1412d-393">175</span><span class="sxs-lookup"><span data-stu-id="1412d-393">175</span></span></p></td>
    <td><p><span data-ttu-id="1412d-394">5,000</span><span class="sxs-lookup"><span data-stu-id="1412d-394">5,000</span></span></p></td>
    <td><p><span data-ttu-id="1412d-395">700</span><span class="sxs-lookup"><span data-stu-id="1412d-395">700</span></span></p></td>
    </tr>
    </tbody>
    </table>


<div>

## <a name="next-steps"></a><span data-ttu-id="1412d-396">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="1412d-396">Next Steps</span></span>

<span data-ttu-id="1412d-397">После того как вы собрали необходимые сведения, вы можете выполнить развертывание CAC с помощью командной консоли Lync Server или панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1412d-397">After you have gathered the required information, you can perform CAC deployment either by using the Lync Server Management Shell or Lync Server Control Panel.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="1412d-398">Несмотря на то, что вы можете выполнять большинство задач по настройке сети с помощью панели управления Lync Server, для создания подсетей и межсайтовых ссылок необходимо использовать командную консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1412d-398">Although you can perform most network configuration tasks by using Lync Server Control Panel, to create subnets and intersite links, you must use Lync Server Management Shell.</span></span> <span data-ttu-id="1412d-399">Дополнительные сведения можно найти в документации по командной консоли Lync Server для командлета <STRONG>New – CsNetworkSubnet</STRONG> и командлета <STRONG>New – CsNetworkIntersitePolicy</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="1412d-399">For details, see the Lync Server Management Shell documentation for the <STRONG>New-CsNetworkSubnet</STRONG> cmdlet and the <STRONG>New-CsNetworkIntersitePolicy</STRONG> cmdlet.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

