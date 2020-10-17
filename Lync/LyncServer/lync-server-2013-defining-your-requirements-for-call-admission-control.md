---
title: 'Lync Server 2013: определение требований для контроля допуска звонков'
description: 'Lync Server 2013: определение требований для контроля допуска звонков.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for call admission control
ms:assetid: 5122171a-a5b0-4059-b033-846caec10d1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398334(v=OCS.15)
ms:contentKeyID: 48184104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9f675ac5811e0c0c1c23dc76ebb8b4525857836
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545425"
---
# <a name="defining-your-requirements-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="29f50-103">Определение требований для контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29f50-103">Defining your requirements for call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29f50-104">_**Последнее изменение темы:** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="29f50-104">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="29f50-p101">Для планирования контроля допуска звонков (CAC) необходимы подробные сведения о топологии сети предприятия. Чтобы успешно спланировать контроль допуска звонков, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="29f50-p101">Planning for call admission control (CAC) requires detailed information about your enterprise network topology. To help plan your call admission control policies, follow these steps.</span></span>

1.  <span data-ttu-id="29f50-107">Укажите концентраторы/магистральные области (называемые *сетевыми регионами*) в корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="29f50-107">Identify the hubs/backbones (called *network regions*) within your enterprise network.</span></span>

2.  <span data-ttu-id="29f50-108">Укажите офисы или филиалы (называемые *сетевыми узлами*) в каждом регионе сети.</span><span class="sxs-lookup"><span data-stu-id="29f50-108">Identify the offices or locations (called *network sites*) within each network region.</span></span>

3.  <span data-ttu-id="29f50-109">Определите сетевой маршрут между каждой парой сетевых регионов.</span><span class="sxs-lookup"><span data-stu-id="29f50-109">Determine the network route between every pair of network regions.</span></span>

4.  <span data-ttu-id="29f50-110">Определите ограничения полосы пропускания для каждого соединения WAN.</span><span class="sxs-lookup"><span data-stu-id="29f50-110">Determine the bandwidth limits for each WAN link.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="29f50-111">Пределы пропускной способности относятся к тому, сколько пропускной способности в канале WAN выделяется для корпоративной голосовой связи и передачи аудио-и видеоданных.</span><span class="sxs-lookup"><span data-stu-id="29f50-111">Bandwidth limits refer to how much of the bandwidth on a WAN link is allocated to Enterprise Voice and audio/video traffic.</span></span> <span data-ttu-id="29f50-112">Если WAN-соединение характеризуется как соединение с ограниченной полосой пропускания, для этого соединения установлено ограничение пропускной способности, которое меньше значения ожидаемого пикового трафика.</span><span class="sxs-lookup"><span data-stu-id="29f50-112">When a WAN link is described as “bandwidth-constrained,” the WAN link has a bandwidth limit that is lower than the expected peak traffic over the link.</span></span>

    
    </div>

5.  <span data-ttu-id="29f50-113">Определите IP-подсети, назначенные каждому узлу сети.</span><span class="sxs-lookup"><span data-stu-id="29f50-113">Identify the IP subnets that are assigned to each network site.</span></span>

<span data-ttu-id="29f50-114">Чтобы объяснить эти понятия, мы будем использовать пример топологии сети, представленный на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="29f50-114">To explain these concepts, we’ll use the example network topology shown in the following figure.</span></span>

<span data-ttu-id="29f50-115">**Пример топологии для контроля допуска звонков**</span><span class="sxs-lookup"><span data-stu-id="29f50-115">**Example topology for call admission control**</span></span>

<span data-ttu-id="29f50-116">![Пример топологии сети Litware Inc.](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Пример топологии сети Litware Inc.")</span><span class="sxs-lookup"><span data-stu-id="29f50-116">![Litware Inc. Network Topology Example](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Litware Inc. Network Topology Example")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="29f50-p103">Все сетевые узлы связаны с регионом сети. Например, Портленд, Рено и Альбукерке включены в регион «Северная Америка». На этом рисунке представлены соединения WAN, к которым применяются политики CAC, с указанием ограничений полосы пропускании. Сетевые узлы Чикаго, Нью-Йорк и Детройт представлены внутри региона «Северная Америка», поскольку полоса пропускания для них не ограничена, а следовательно, применение политик CAC не требуется.</span><span class="sxs-lookup"><span data-stu-id="29f50-p103">All network sites are associated with a network region. For example, Portland, Reno, and Albuquerque are included in the North America region. In this figure, only WAN links that have CAC policies applied are shown, with bandwidth limits. The network sites of Chicago, New York, and Detroit are shown inside the North America region oval because they are not bandwidth-constrained, and therefore do not require CAC policies.</span></span>



</div>

<span data-ttu-id="29f50-121">Описание компонентов этой примерной топологии приведено в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="29f50-121">The components of this example topology are explained in the following sections.</span></span> <span data-ttu-id="29f50-122">Сведения о том, как запланирована эта топология, включая пределы пропускной способности, приведены в статье [Пример: сбор требований для контроля допуска звонков в Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="29f50-122">For details about how this topology was planned, including the bandwidth limits, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md).</span></span>

<div>

## <a name="identify-network-regions"></a><span data-ttu-id="29f50-123">Определение регионов сети</span><span class="sxs-lookup"><span data-stu-id="29f50-123">Identify Network Regions</span></span>

<span data-ttu-id="29f50-124">Сетевой регион представляет собой сетевой концентратор или магистральную область.</span><span class="sxs-lookup"><span data-stu-id="29f50-124">A network region represents a network backbone or a network hub.</span></span>

<span data-ttu-id="29f50-p105">Магистральная область или сетевой концентратор — это часть инфраструктуры компьютерной сети, которая соединяет различные части сети, предоставляя канал для обмена информацией между различными ЛВС или подсетями. Магистральная область может объединять разнообразные сети в широких географических масштабах. Емкости магистральной области обычно выше, чем емкостью сетей, подключенных к ней.</span><span class="sxs-lookup"><span data-stu-id="29f50-p105">A network backbone or hub is a part of computer network infrastructure that interconnects different parts of the network, providing a path for the exchange of information between different LANs or subnets. A backbone can tie together diverse networks from a small location to a wide geographic area. The backbone's capacity is typically greater than that of the networks that connect to it.</span></span>

<span data-ttu-id="29f50-p106">В наш пример топологии включены три сетевых региона: Северная Америка, EMEA и APAC. Сетевой регион содержит набор сетевых узлов (см. определение сетевых узлов далее в этом разделе). В сотрудничестве с отделом сетевых операций определите сетевые регионы.</span><span class="sxs-lookup"><span data-stu-id="29f50-p106">Our example topology has three network regions: North America, EMEA, and APAC. A network region contains a collection of network sites (see the definition of network sites later in this topic). Work with your network operations team to identify your network regions.</span></span>

</div>

<div>

## <a name="associating-a-central-site-with-each-network-region"></a><span data-ttu-id="29f50-131">Связь центрального узла с каждым регионом сети</span><span class="sxs-lookup"><span data-stu-id="29f50-131">Associating a Central Site with each Network Region</span></span>

<span data-ttu-id="29f50-132">Для управления CAC необходимо, чтобы центральный сайт Lync Server определялся для каждой области сети.</span><span class="sxs-lookup"><span data-stu-id="29f50-132">CAC requires that a Lync Server central site is defined for each network region.</span></span> <span data-ttu-id="29f50-133">Центральный сайт выбирается с учетом лучшего сетевого подключения и самой высокой пропускной способности для всех прочих сайтов в этом сетевом регионе.</span><span class="sxs-lookup"><span data-stu-id="29f50-133">The central site is selected with the best network connectivity and highest bandwidth to all the other sites within that network region.</span></span> <span data-ttu-id="29f50-134">В предыдущем примере сетевая топология отображает разных сетевых регионов, каждый из которых имеет центральный сайт, обрабатывающий решения CAS.</span><span class="sxs-lookup"><span data-stu-id="29f50-134">The preceding example of network topology shows three network regions, each with a central site that manages CAC decisions.</span></span> <span data-ttu-id="29f50-135">На основе предыдущего примера подходящее сопоставление приведено в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="29f50-135">From the preceding example, the appropriate association is shown in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="29f50-136">Центральные узлы необязательно соответствуют сетевым узлам.</span><span class="sxs-lookup"><span data-stu-id="29f50-136">Central sites do not necessarily correspond to network sites.</span></span> <span data-ttu-id="29f50-137">В примерах, приведенных в данной документации, некоторые центральные узлы — Чикаго, Лондон и Пекин — имеют те же имена, что и соответствующие сайты сети.</span><span class="sxs-lookup"><span data-stu-id="29f50-137">In the examples in this documentation, some central sites—Chicago, London, and Beijing—share the same name as the network sites.</span></span> <span data-ttu-id="29f50-138">Тем не менее, даже если центральный сайт и сетевой сайт имеют одно и то же имя, центральный сайт является элементом топологии Lync Server, а сетевой сайт является частью общей сети, в которой размещается топология Lync Server.</span><span class="sxs-lookup"><span data-stu-id="29f50-138">However, even if a central site and network site share the same name, the central site is an element of the Lync Server topology, whereas the network site is a part of the overall network in which the Lync Server topology resides.</span></span>



</div>

### <a name="network-regions-central-sites-and-network-sites"></a><span data-ttu-id="29f50-139">Области сети, центральные узлы и сетевые узлы</span><span class="sxs-lookup"><span data-stu-id="29f50-139">Network regions, central sites, and network sites</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29f50-140">Область сети</span><span class="sxs-lookup"><span data-stu-id="29f50-140">Network Region</span></span></th>
<th><span data-ttu-id="29f50-141">Центральный узел</span><span class="sxs-lookup"><span data-stu-id="29f50-141">Central Site</span></span></th>
<th><span data-ttu-id="29f50-142">Сетевые узлы</span><span class="sxs-lookup"><span data-stu-id="29f50-142">Network Sites</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29f50-143">Северная Америка</span><span class="sxs-lookup"><span data-stu-id="29f50-143">North America</span></span></p></td>
<td><p><span data-ttu-id="29f50-144">Офис</span><span class="sxs-lookup"><span data-stu-id="29f50-144">Chicago</span></span></p></td>
<td><p><span data-ttu-id="29f50-145">Офис</span><span class="sxs-lookup"><span data-stu-id="29f50-145">Chicago</span></span></p>
<p><span data-ttu-id="29f50-146">Нью-Йорк</span><span class="sxs-lookup"><span data-stu-id="29f50-146">New York</span></span></p>
<p><span data-ttu-id="29f50-147">Детройт</span><span class="sxs-lookup"><span data-stu-id="29f50-147">Detroit</span></span></p>
<p><span data-ttu-id="29f50-148">Портленд</span><span class="sxs-lookup"><span data-stu-id="29f50-148">Portland</span></span></p>
<p><span data-ttu-id="29f50-149">Рино</span><span class="sxs-lookup"><span data-stu-id="29f50-149">Reno</span></span></p>
<p><span data-ttu-id="29f50-150">Альбукерке</span><span class="sxs-lookup"><span data-stu-id="29f50-150">Albuquerque</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29f50-151">EMEA</span><span class="sxs-lookup"><span data-stu-id="29f50-151">EMEA</span></span></p></td>
<td><p><span data-ttu-id="29f50-152">Лондон</span><span class="sxs-lookup"><span data-stu-id="29f50-152">London</span></span></p></td>
<td><p><span data-ttu-id="29f50-153">Лондон</span><span class="sxs-lookup"><span data-stu-id="29f50-153">London</span></span></p>
<p><span data-ttu-id="29f50-154">Кельн</span><span class="sxs-lookup"><span data-stu-id="29f50-154">Cologne</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29f50-155">APAC</span><span class="sxs-lookup"><span data-stu-id="29f50-155">APAC</span></span></p></td>
<td><p><span data-ttu-id="29f50-156">Пекин</span><span class="sxs-lookup"><span data-stu-id="29f50-156">Beijing</span></span></p></td>
<td><p><span data-ttu-id="29f50-157">Пекин</span><span class="sxs-lookup"><span data-stu-id="29f50-157">Beijing</span></span></p>
<p><span data-ttu-id="29f50-158">Манилу</span><span class="sxs-lookup"><span data-stu-id="29f50-158">Manila</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-network-sites"></a><span data-ttu-id="29f50-159">Определение сетевых узлов</span><span class="sxs-lookup"><span data-stu-id="29f50-159">Identify Network Sites</span></span>

<span data-ttu-id="29f50-p109">Сетевой узел представляет собой место, в котором у организации имеется собственность, например офисы, здания или территории. Физический объект со связью через локальную или проводную сеть с другими сайтами считается сетевым сайтом. Начните с инвентаризации всех офисов организации. В нашем примере топологии регион сети «Северная Америка» состоит из следующих сетевых узлов: Нью-Йорк, Чикаго, Детройт, Портленд, Рено и Альбукерке.</span><span class="sxs-lookup"><span data-stu-id="29f50-p109">A network site represents a location where your organization has a physical venue—for example, offices, a set of buildings, or a campus. A physical venue with a LAN and has WAN connectivity to other sites is considered a network site. Start by inventorying all of your organization’s offices. In our example topology, the North America network region consists of the following network sites: New York, Chicago, Detroit, Portland, Reno, and Albuquerque.</span></span>

<span data-ttu-id="29f50-p110">Необходимо связать каждый сетевой узел с регионом сети. В зависимости от наличия или отсутствия у сетевого узла ограниченной связи WAN сетевому узлу назначается политика пропускной способности. Для получения дополнительных сведений о политиках CAC и полосе пропускания, выделяемой с их помощью, см. тему «Определение политик пропускной способности» далее в этом разделе. Чтобы настроить CAC, вы связываете сетевые узлы с регионами сети, а затем создаете политики выделения полосы пропускания для установления подключений с ограниченной полосой пропускания между данным узлом или регионом и подключений WAN между узлам и регионами.</span><span class="sxs-lookup"><span data-stu-id="29f50-p110">You must associate every network site with a network region. Depending on whether the network site has a constrained WAN link, a bandwidth policy is associated with the network site. For details about CAC policies and the bandwidth that you allocate by using them, see "Define Bandwidth Policies" later in this topic. To configure CAC, you associate network sites with network regions, and then you create bandwidth-allocating policies to apply to the bandwidth-constrained connections between a given site or region and the WAN connections between the sites and regions.</span></span>

</div>

<div>

## <a name="identify-network-links"></a><span data-ttu-id="29f50-168">Определение сетевых соединений</span><span class="sxs-lookup"><span data-stu-id="29f50-168">Identify Network Links</span></span>

<span data-ttu-id="29f50-p111">Сетевые соединения представляют собой подключения к физической сети WAN, которая связывает различные регионы и узлы. В нашем примере топологии существуют два сетевых соединения с регионами, пять сетевых соединений между регионами и узлами и одно сетевое соединение между двумя узлами.</span><span class="sxs-lookup"><span data-stu-id="29f50-p111">Network links represent connections to the physical WAN that links different regions and sites. In our example topology, there are two regional network links, five network links between regions and sites, and one network link between two sites.</span></span>

<span data-ttu-id="29f50-171">Два региональных соединения — это соединение между Северной Америкой и регионом EMEA, которое обозначается как канал NA-EMEA-LINK, и соединение между регионами APAC и EMEA, которое обозначается как канал EMEA-APAC-LINK.</span><span class="sxs-lookup"><span data-stu-id="29f50-171">The two regional links are between North America and EMEA, represented as NA-EMEA-LINK, and between APAC and EMEA, represented as EMEA-APAC-LINK.</span></span>

<span data-ttu-id="29f50-p112">Соединения между узлами обозначены как каналы, соединяющие Портленд, Рено и Альбукерке с регионом «Северная Америка», Манилу с регионом «APAC» и Кельн с регионом «EMEA». Соединение между Рено и Альбукерке представлено прямым сетевым каналом между этими двумя узлами.</span><span class="sxs-lookup"><span data-stu-id="29f50-p112">The site links are indicated by the lines connecting Portland, Reno, and Albuquerque to the North America region, Manila to the APAC region, and Cologne to the EMEA region. The line between Reno and Albuquerque shows a direct network link between these two sites.</span></span>

</div>

<div>

## <a name="define-bandwidth-policies"></a><span data-ttu-id="29f50-174">Определение политик пропускной способности</span><span class="sxs-lookup"><span data-stu-id="29f50-174">Define Bandwidth Policies</span></span>

<span data-ttu-id="29f50-p113">В сотрудничестве с отделом сетевых операций определите, какая полоса пропускания WAN доступна для передачи аудио-и видеоинформации в реальном времени по каналам WAN в организации. Политики полосы пропускания обычно применяются к соединениям WAN, если предполагается, что может потребоваться выделение более широкой полосы пропускания, чем та, которая может быть выделена для аудио- и видеокомпонентов.</span><span class="sxs-lookup"><span data-stu-id="29f50-p113">Work with your network operations team to determine how much WAN bandwidth is available for real-time audio and video traffic across the WAN links in your organization. Bandwidth policies are typically applied to WAN links if the bandwidth usage is constrained; that is, if it expected to be more than the bandwidth that can be allocated for audio and video modalities.</span></span>

<span data-ttu-id="29f50-p114">*Политики пропускной способности* определяют максимальную пропускную способность, которая может быть зарезервирована для передачи звука и видео в режиме реального времени. Так как CAC не ограничивает скорость передачи другого трафика, он не может предотвратить полного использования пропускной способности сети при передаче других данных, таких как передача больших файлов или потоковое воспроизведение музыки.</span><span class="sxs-lookup"><span data-stu-id="29f50-p114">CAC *bandwidth policies* define the maximum bandwidth that can be reserved for real-time audio and video modalities. Since CAC does not limit the bandwidth of other traffic, it cannot prevent other data traffic such as a large file transfer, music streaming, from using up all of the network bandwidth.</span></span>

<span data-ttu-id="29f50-179">Политики полосы пропускания CAC могут определять любые из следующих характеристик (или все следующие характеристики):</span><span class="sxs-lookup"><span data-stu-id="29f50-179">CAC bandwidth policies can define any or all of the following:</span></span>

  - <span data-ttu-id="29f50-180">Максимальная общая полоса пропускания, выделенная для аудиокомпонентов.</span><span class="sxs-lookup"><span data-stu-id="29f50-180">Maximum total bandwidth allocated for audio.</span></span>

  - <span data-ttu-id="29f50-181">Максимальная общая полоса пропускания, выделенная для видеокомпонентов.</span><span class="sxs-lookup"><span data-stu-id="29f50-181">Maximum total bandwidth allocated for video.</span></span>

  - <span data-ttu-id="29f50-182">Максимальная полоса пропускания, выделенная для одного аудиовызова (сеанса).</span><span class="sxs-lookup"><span data-stu-id="29f50-182">Maximum bandwidth allocated for a single audio call (session).</span></span>

  - <span data-ttu-id="29f50-183">Максимальная полоса пропускания, выделенная для одного видеовызова (сеанса).</span><span class="sxs-lookup"><span data-stu-id="29f50-183">Maximum bandwidth allocated for a single video call (session).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="29f50-184">Все значения полосы пропускания CAC представляют максимальные ограничения <EM>однонаправленной</EM> полосы пропускания.</span><span class="sxs-lookup"><span data-stu-id="29f50-184">All CAC bandwidth values represent the maximum <EM>unidirectional</EM> bandwidth limits.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="29f50-185">Функции политики голосовой связи Lync Server 2013 предоставляют возможность переопределения проверки политики пропускной способности для входящих вызовов пользователя (а не для исходящих вызовов, размещаемых пользователем).</span><span class="sxs-lookup"><span data-stu-id="29f50-185">The Lync Server 2013 Voice Policy features provide the ability to override bandwidth policy checks for incoming calls to the user (not for outgoing calls that are placed by the user).</span></span> <span data-ttu-id="29f50-186">После установления сеанса пропускная способность будет точно соответствовать учетной записи.</span><span class="sxs-lookup"><span data-stu-id="29f50-186">After the session is established, the bandwidth consumption will be accurately accounted for.</span></span> <span data-ttu-id="29f50-187">Этот параметр следует использовать с осторожностью.</span><span class="sxs-lookup"><span data-stu-id="29f50-187">This setting should be used sparingly.</span></span> <span data-ttu-id="29f50-188">Для получения дополнительных сведений см. <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Создание политики голосовой связи и настройка записей использования PSTN в Lync server 2013</A> или <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">изменение политики голосовой связи в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="29f50-188">For details, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="29f50-p116">Чтобы оптимизировать использование полосы пропускания для отдельных сеансов, примите во внимание тип аудио- и видеокодеков, которые будут использоваться. В частности избегайте выделения недостаточной полосы пропускания для кодека, который предполагается использовать часто. Наоборот, если необходимо предотвратить использование кодека, для которого требуется выделение более широкой полосы пропускания, следует задать достаточно низкое значение максимальной полосы пропускания для отдельных сеансов, чтобы воспрепятствовать его использованию. Если речь идет об аудиокомпонентах, не все кодеки доступны для каждого сценария. Например:</span><span class="sxs-lookup"><span data-stu-id="29f50-p116">To optimize bandwidth utilization on a per-session basis, consider the type of audio and video codecs that will be used. In particular, avoid allocating insufficient bandwidth for a codec that you expect to be used frequently. Conversely, if you want to prevent media from using a codec that requires more bandwidth, you should set the maximum bandwidth per session low enough to discourage such use. For audio, not every codec is available for every scenario. For example:</span></span>

  - <span data-ttu-id="29f50-194">Одноранговые голосовые вызовы между конечными точками Lync будут использовать RTAudio (8 кГц) или RTAudio (16 кГц) при множители пропускной способности и приоритизации кодеков.</span><span class="sxs-lookup"><span data-stu-id="29f50-194">Peer-to-peer audio calls between Lync endpoints will use either RTAudio (8kHz) or RTAudio (16kHz) when you factor in the bandwidth and prioritization of codecs.</span></span>

  - <span data-ttu-id="29f50-195">Конференц-вызовы между конечными точками Lync и службой аудио-и видеоконференций будут использовать либо G. 722, либо Siren.</span><span class="sxs-lookup"><span data-stu-id="29f50-195">Conference calls between Lync endpoints and the A/V Conferencing service will use either G.722 or Siren.</span></span>

  - <span data-ttu-id="29f50-196">При вызове телефонной сети общего пользования (PSTN) в конечных точках Lync или из них будет использоваться либо G. 711, либо RTAudio (8 кГц).</span><span class="sxs-lookup"><span data-stu-id="29f50-196">Calls to the public switched telephone network (PSTN) either to or from Lync endpoints will use either G.711 or RTAudio (8kHz).</span></span>

<span data-ttu-id="29f50-197">Используйте приведенную ниже таблицу для подбора максимальных параметров полосы пропускания для отдельного сеанса.</span><span class="sxs-lookup"><span data-stu-id="29f50-197">Use the following table to help optimize the maximum per-session bandwidth settings.</span></span>

### <a name="bandwidth-utilization-by-codecs"></a><span data-ttu-id="29f50-198">Использование полосы пропускания — кодеки</span><span class="sxs-lookup"><span data-stu-id="29f50-198">Bandwidth utilization by codecs</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29f50-199">Кодек</span><span class="sxs-lookup"><span data-stu-id="29f50-199">Codec</span></span></th>
<th><span data-ttu-id="29f50-200">Требования к полосе пропускания без метода прямой коррекции ошибок (FEC)</span><span class="sxs-lookup"><span data-stu-id="29f50-200">Bandwidth requirement with no forward error correction (FEC)</span></span></th>
<th><span data-ttu-id="29f50-201">Требования к полосе пропускания с методом прямой коррекции ошибок (FEC)</span><span class="sxs-lookup"><span data-stu-id="29f50-201">Bandwidth requirement with forward error correction (FEC)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29f50-202">RTAudio (8 кГц)</span><span class="sxs-lookup"><span data-stu-id="29f50-202">RTAudio (8kHz)</span></span></p></td>
<td><p><span data-ttu-id="29f50-203">49,8 кбит/с</span><span class="sxs-lookup"><span data-stu-id="29f50-203">49.8 kbps</span></span></p></td>
<td><p><span data-ttu-id="29f50-204">61,6 кбит/с</span><span class="sxs-lookup"><span data-stu-id="29f50-204">61.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29f50-205">RTAudio (16 кГц)</span><span class="sxs-lookup"><span data-stu-id="29f50-205">RTAudio (16kHz)</span></span></p></td>
<td><p><span data-ttu-id="29f50-206">67 кбит/с</span><span class="sxs-lookup"><span data-stu-id="29f50-206">67 kbps</span></span></p></td>
<td><p><span data-ttu-id="29f50-207">96 кбит/с</span><span class="sxs-lookup"><span data-stu-id="29f50-207">96 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29f50-208">Siren</span><span class="sxs-lookup"><span data-stu-id="29f50-208">Siren</span></span></p></td>
<td><p><span data-ttu-id="29f50-209">57,6 кбит/с</span><span class="sxs-lookup"><span data-stu-id="29f50-209">57.6 kbps</span></span></p></td>
<td><p><span data-ttu-id="29f50-210">73,6 кбит/с</span><span class="sxs-lookup"><span data-stu-id="29f50-210">73.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29f50-211">G. 711</span><span class="sxs-lookup"><span data-stu-id="29f50-211">G.711</span></span></p></td>
<td><p><span data-ttu-id="29f50-212">102 кбит/с</span><span class="sxs-lookup"><span data-stu-id="29f50-212">102 kbps</span></span></p></td>
<td><p><span data-ttu-id="29f50-213">166 кбит/с</span><span class="sxs-lookup"><span data-stu-id="29f50-213">166 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29f50-214">G. 722</span><span class="sxs-lookup"><span data-stu-id="29f50-214">G.722</span></span></p></td>
<td><p><span data-ttu-id="29f50-215">105,6 кбит/с</span><span class="sxs-lookup"><span data-stu-id="29f50-215">105.6 kbps</span></span></p></td>
<td><p><span data-ttu-id="29f50-216">169,6 кбит/с</span><span class="sxs-lookup"><span data-stu-id="29f50-216">169.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29f50-217">RTVideo (CIF 15 кадров в секунду)</span><span class="sxs-lookup"><span data-stu-id="29f50-217">RTVideo (CIF 15 fps)</span></span></p></td>
<td><p><span data-ttu-id="29f50-218">260 кбит/с</span><span class="sxs-lookup"><span data-stu-id="29f50-218">260 kbps</span></span></p></td>
<td><p><span data-ttu-id="29f50-219">Не применимо</span><span class="sxs-lookup"><span data-stu-id="29f50-219">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29f50-220">RTVideo (VGA 30 кадров в секунду)</span><span class="sxs-lookup"><span data-stu-id="29f50-220">RTVideo (VGA 30 fps)</span></span></p></td>
<td><p><span data-ttu-id="29f50-221">610 кбит/с</span><span class="sxs-lookup"><span data-stu-id="29f50-221">610 kbps</span></span></p></td>
<td><p><span data-ttu-id="29f50-222">Не применимо</span><span class="sxs-lookup"><span data-stu-id="29f50-222">Not applicable</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="29f50-p117">Требования к пропускной способности должны определяться с учетом следующих расходов: Ethernet II, IP, UDP, RTP и SRTP. Они также включают 10 кбит/с для RTCP.</span><span class="sxs-lookup"><span data-stu-id="29f50-p117">Bandwidth requirements take into account overhead for the following: Ethernet II, IP, User Datagram Protocol (UDP), RTP (real-time transport protocol), and SRTP (secure real-time transport protocol). They also include 10 kbps for RTCP overhead.</span></span>



</div>

<span data-ttu-id="29f50-225">Кодеки G.722.1 и Siren аналогичны, но они обеспечивают разную скорость потока.</span><span class="sxs-lookup"><span data-stu-id="29f50-225">The G.722.1 and Siren codecs are similar, but they offer different bit rates.</span></span>

<span data-ttu-id="29f50-226">G. 722 кодек, используемый по умолчанию для конференц-связи Lync Server, полностью отличается от кодеков G. 722.1 и Siren.</span><span class="sxs-lookup"><span data-stu-id="29f50-226">G.722, the default codec for Lync Server conferencing, is completely different from the G.722.1 and Siren codecs.</span></span>

<span data-ttu-id="29f50-227">Кодек Siren используется в Lync Server в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="29f50-227">The Siren codec is used in Lync Server in the following situations:</span></span>

  - <span data-ttu-id="29f50-228">Если для полосы пропускания установлено слишком низкое значение, которое не позволяет использовать G.722.</span><span class="sxs-lookup"><span data-stu-id="29f50-228">If the bandwidth policy is set too low for G.722 to be used.</span></span>

  - <span data-ttu-id="29f50-229">Если клиент Communications Server 2007 или Communications Server 2007 R2 подключается к службе конференц-связи Lync Server (так как эти клиенты не поддерживают кодек G. 722).</span><span class="sxs-lookup"><span data-stu-id="29f50-229">If a Communications Server 2007 or Communications Server 2007 R2 client connects to a Lync Server conferencing service (because those clients do not support the G.722 codec).</span></span>

### <a name="bandwidth-utilization-by-scenario"></a><span data-ttu-id="29f50-230">Использование полосы пропускания в различных сценариях</span><span class="sxs-lookup"><span data-stu-id="29f50-230">Bandwidth utilization by scenario</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29f50-231">Сценарий</span><span class="sxs-lookup"><span data-stu-id="29f50-231">Scenario</span></span></th>
<th><span data-ttu-id="29f50-232">Требования к полосе пропускания, оптимизированные с учетом количества (кбит/с)</span><span class="sxs-lookup"><span data-stu-id="29f50-232">Bandwidth requirement optimized for quantity (kbps)</span></span></th>
<th><span data-ttu-id="29f50-233">Требования к полосе пропускания для сбалансированного режима (кбит/с)</span><span class="sxs-lookup"><span data-stu-id="29f50-233">Bandwidth requirement for Balanced mode (kbps)</span></span></th>
<th><span data-ttu-id="29f50-234">Требования к полосе пропускания, оптимизированные с учетом качества (кбит/с)</span><span class="sxs-lookup"><span data-stu-id="29f50-234">Bandwidth requirement optimized for quality (kbps)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29f50-235">Одноранговые аудиовызовы</span><span class="sxs-lookup"><span data-stu-id="29f50-235">Peer-to-peer audio calls</span></span></p></td>
<td><p><span data-ttu-id="29f50-236">45 кбит/с</span><span class="sxs-lookup"><span data-stu-id="29f50-236">45 kbps</span></span></p></td>
<td><p><span data-ttu-id="29f50-237">62 кбит/с</span><span class="sxs-lookup"><span data-stu-id="29f50-237">62 kbps</span></span></p></td>
<td><p><span data-ttu-id="29f50-238">91 кбит/с</span><span class="sxs-lookup"><span data-stu-id="29f50-238">91 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29f50-239">Конференц-вызовы</span><span class="sxs-lookup"><span data-stu-id="29f50-239">Conference calls</span></span></p></td>
<td><p><span data-ttu-id="29f50-240">53 кбит/с</span><span class="sxs-lookup"><span data-stu-id="29f50-240">53 kbps</span></span></p></td>
<td><p><span data-ttu-id="29f50-241">101 кбит/с</span><span class="sxs-lookup"><span data-stu-id="29f50-241">101 kbps</span></span></p></td>
<td><p><span data-ttu-id="29f50-242">165 кбит/с</span><span class="sxs-lookup"><span data-stu-id="29f50-242">165 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29f50-243">Звонки по протоколу PSTN (между Lync 2013 и PSTN Gateway с обходом сервера-посредника)</span><span class="sxs-lookup"><span data-stu-id="29f50-243">PSTN calls (between Lync 2013 and PSTN gateway, with media bypass)</span></span></p></td>
<td><p><span data-ttu-id="29f50-244">97 кбит/с</span><span class="sxs-lookup"><span data-stu-id="29f50-244">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="29f50-245">97 кбит/с</span><span class="sxs-lookup"><span data-stu-id="29f50-245">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="29f50-246">161 кбит/с</span><span class="sxs-lookup"><span data-stu-id="29f50-246">161 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29f50-247">Звонки PSTN (между Lync 2013 и сервером-посредником, без обхода сервера-посредника)</span><span class="sxs-lookup"><span data-stu-id="29f50-247">PSTN calls (between Lync 2013 and Mediation Server, without media bypass)</span></span></p></td>
<td><p><span data-ttu-id="29f50-248">45 кбит/с</span><span class="sxs-lookup"><span data-stu-id="29f50-248">45 kbps</span></span></p></td>
<td><p><span data-ttu-id="29f50-249">97 кбит/с</span><span class="sxs-lookup"><span data-stu-id="29f50-249">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="29f50-250">161 кбит/с</span><span class="sxs-lookup"><span data-stu-id="29f50-250">161 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29f50-251">Звонки PSTN (между сервером-посредником и шлюзом PSTN, без обхода сервера-посредника)</span><span class="sxs-lookup"><span data-stu-id="29f50-251">PSTN calls (between Mediation Server and PSTN gateway, without media bypass)</span></span></p></td>
<td><p><span data-ttu-id="29f50-252">97 кбит/с</span><span class="sxs-lookup"><span data-stu-id="29f50-252">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="29f50-253">97 кбит/с</span><span class="sxs-lookup"><span data-stu-id="29f50-253">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="29f50-254">161 кбит/с</span><span class="sxs-lookup"><span data-stu-id="29f50-254">161 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29f50-255">Вызовы Lync — Polycom</span><span class="sxs-lookup"><span data-stu-id="29f50-255">Lync - Polycom calls</span></span></p></td>
<td><p><span data-ttu-id="29f50-256">101 кбит/с</span><span class="sxs-lookup"><span data-stu-id="29f50-256">101 Kbps</span></span></p></td>
<td><p><span data-ttu-id="29f50-257">101 кбит/с</span><span class="sxs-lookup"><span data-stu-id="29f50-257">101 Kbps</span></span></p></td>
<td><p><span data-ttu-id="29f50-258">101 кбит/с</span><span class="sxs-lookup"><span data-stu-id="29f50-258">101 Kbps</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-ip-subnets"></a><span data-ttu-id="29f50-259">Определение подсистем IP</span><span class="sxs-lookup"><span data-stu-id="29f50-259">Identify IP Subnets</span></span>

<span data-ttu-id="29f50-p118">Для каждого узла сети необходимо в сотрудничестве с сетевым администратором определить, какие IP-подсети назначены каждому сетевому узлу. Если администратор сети уже упорядочил IP-подсети в регионы сети, ваша работа значительно упрощается.</span><span class="sxs-lookup"><span data-stu-id="29f50-p118">For each network site, you will need to work with your network administrator to determine what IP subnets are assigned to each network site. If your network administrator has already organized the IP subnets into network regions and network sites, then your work is significantly simplified.</span></span>

<span data-ttu-id="29f50-p119">В нашем примере узлу «Нью-Йорке» в регионе «Северная Америка» назначаются следующие IP-подсети: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Предположим, Боб, который обычно работает в Детройте, отправляется в Нью-Йоркское отделение для прохождения обучения. Когда он включает свой компьютер и подключается к сети, его компьютер получает IP-адрес в одном из четырех регионов, которые зарезервированы для Нью-Йорка, например 172.29.80.103.</span><span class="sxs-lookup"><span data-stu-id="29f50-p119">In our example, the New York site in the North America region is assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Suppose Bob, who typically works in Detroit, travels to the New York office for training. When he turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges reserved for New York, for example 172.29.80.103.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="29f50-265">Подсети IP, указанные во время настройки сети на сервере, должны соответствовать формату, предоставленному клиентскими компьютерами, чтобы гарантировать их надлежащее использование для обхода сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="29f50-265">The IP subnets specified during network configuration on the server must match the format provided by client computers in order to be properly used for media bypass.</span></span> <span data-ttu-id="29f50-266">Клиент Lync принимает свой локальный IP-адрес и маскирует IP-адрес со связанной маской подсети.</span><span class="sxs-lookup"><span data-stu-id="29f50-266">A Lync client takes its local IP address and masks the IP address with the associated subnet mask.</span></span> <span data-ttu-id="29f50-267">При определении идентификатора обхода, связанного с каждым клиентом, регистратор сравнивает список IP-подсетей, связанных с каждым сетевым узлом, с подсетью, предоставленной клиентом, для поиска точного совпадения.</span><span class="sxs-lookup"><span data-stu-id="29f50-267">When determining the bypass ID associated with each client, the Registrar will compare the list of IP subnets associated with each network site against the subnet provided by the client for an exact match.</span></span> <span data-ttu-id="29f50-268">По этой причине крайне важно, чтобы подсети, введенные во время настройки сети на сервере, являлись действительным, а не виртуальными подсетями.</span><span class="sxs-lookup"><span data-stu-id="29f50-268">For this reason, it is important that subnets entered during network configuration on the server are actual subnets instead of virtual subnets.</span></span> <span data-ttu-id="29f50-269">(Если разворачивается контроль допуска звонков, но не обход сервера-посредника, то контроль допуска звонков будет работать должным образом даже при настройке виртуальных подсетей.)</span><span class="sxs-lookup"><span data-stu-id="29f50-269">(If you deploy call admission control, but not media bypass, call admission control will function properly even if you configure virtual subnets.)</span></span><BR><span data-ttu-id="29f50-270">Например, если клиент входит на компьютер с IP-адресом 172.29.81.57 с маской IP-подсети 255.255.255.0, Lync 2013 будет запрашивать идентификатор обхода, связанный с подсетью 172.29.81.0.</span><span class="sxs-lookup"><span data-stu-id="29f50-270">For example, if a client signs in on a computer with an IP address of 172.29.81.57 with an IP subnet mask of 255.255.255.0, Lync 2013 will request the bypass ID associated with subnet 172.29.81.0.</span></span> <span data-ttu-id="29f50-271">Если подсеть определена как 172.29.0.0/16, то хотя клиент принадлежит этой виртуальной подсети, регистратор не будет считать это соответствием, поскольку точно ищет подсеть 172.29.81.0.</span><span class="sxs-lookup"><span data-stu-id="29f50-271">If the subnet is defined as 172.29.0.0/16, although the client belongs to the virtual subnet, the Registrar will not consider this a match because the Registrar is specifically looking for subnet 172.29.81.0.</span></span> <span data-ttu-id="29f50-272">Поэтому важно, чтобы администратор ввел подсети в точности так, как это предоставляется клиентами Lync (которые предоставляются подсетями во время настройки сети статически или по протоколу DHCP).</span><span class="sxs-lookup"><span data-stu-id="29f50-272">Therefore, it is important that the administrator enters subnets exactly as provided by Lync clients (which are provisioned with subnets during network configuration either statically or by DHCP.)</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

