---
title: 'Lync Server 2013: Планирование устойчивости голосовой связи для центрального сайта'
description: 'Lync Server 2013: Планирование устойчивости голосовой связи для центрального сайта.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for central site voice resiliency
ms:assetid: 52dd0c3e-cd3c-44cf-bef5-8c49ff5e4c7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398347(v=OCS.15)
ms:contentKeyID: 48184164
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd41943212459311abdb64b3ed77c918539d082d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567385"
---
# <a name="planning-for-central-site-voice-resiliency-in-lync-server-2013"></a><span data-ttu-id="5d5a7-103">Планирование устойчивости голосовой связи для центрального сайта в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d5a7-103">Planning for central site voice resiliency in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d5a7-104">_**Последнее изменение темы:** 2013-10-30_</span><span class="sxs-lookup"><span data-stu-id="5d5a7-104">_**Topic Last Modified:** 2013-10-30_</span></span>

<span data-ttu-id="5d5a7-105">Все чаще у предприятий появляется много сайтов, распределенных по всему миру.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-105">Increasingly, enterprises have multiple sites spread across the globe.</span></span> <span data-ttu-id="5d5a7-106">Обслуживание экстренных служб, доступ к службе технической поддержки и возможность проведения критических бизнес-задач, когда Центральный сайт не работает, является обязательным для любого решения для обеспечения устойчивости корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-106">Maintaining emergency services, access to help desk, and the ability to conduct critical business tasks when a central site is out of service is essential for any Enterprise Voice resiliency solution.</span></span> <span data-ttu-id="5d5a7-107">Когда центральный сайт выходит из строя, должны выполняться следующие условия.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-107">When a central site becomes unavailable, the following conditions must be met:</span></span>

  - <span data-ttu-id="5d5a7-108">Должна обеспечиваться отработка отказа голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-108">Voice failover must be provided.</span></span>

  - <span data-ttu-id="5d5a7-109">Пользователи, которые обычно регистрируются в пуле переднего плана на центральном сайте, должны иметь возможность зарегистрироваться в альтернативном интерфейсном пуле.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-109">Users who ordinarily register with the Front End pool at the central site must be able to register with an alternative Front End pool.</span></span> <span data-ttu-id="5d5a7-110">Это можно сделать, создав несколько DNS-записей SRV, каждый из которых разрешается в пул директоров или интерфейсный пул на каждом из центральных сайтов.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-110">This can be done by creating multiple DNS SRV records, each of which resolves to a Director pool or Front End pool in each of your central sites.</span></span> <span data-ttu-id="5d5a7-111">Вы можете настроить приоритет и веса записей SRV, чтобы пользователи, обслуживаемые этим центральным сайтом, переполучили соответствующий директор и пул переднего плана вперед от этих записей в других записях SRV.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-111">You can adjust the priority and weights of the SRV records so that users who are served by that central site get the corresponding Director and Front End pool ahead of those in other SRV records.</span></span>

  - <span data-ttu-id="5d5a7-112">Входящие и исходящие вызовы пользователей, расположенных на других сайтах, должны перенаправляться в ТСОП.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-112">Calls to and from users located at other sites must be rerouted to the PSTN.</span></span>

<span data-ttu-id="5d5a7-113">В этой статье описывается рекомендуемое решение для защиты устойчивости центрального сайта голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-113">This topic describes the recommended solution for securing central site voice resiliency.</span></span>

<div>

## <a name="architecture-and-topology"></a><span data-ttu-id="5d5a7-114">Архитектура и топология</span><span class="sxs-lookup"><span data-stu-id="5d5a7-114">Architecture and Topology</span></span>

<span data-ttu-id="5d5a7-115">При планировании устойчивости голосовой связи на центральном сайте необходимо базовое понимание центральной роли, выполняемой регистратором Lync Server 2013, в рамках поддержки голосовой отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-115">Planning for voice resiliency at a central site requires a basic understanding of the central role played by the Lync Server 2013 Registrar in enabling voice failover.</span></span> <span data-ttu-id="5d5a7-116">Служба регистратора Lync Server — это роль сервера, которая включает регистрацию и проверку подлинности клиентов и предоставляет службы маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-116">The Lync Server Registrar is a server role that enables client registration and authentication and provides routing services.</span></span> <span data-ttu-id="5d5a7-117">Он размещается вместе с другими компонентами на сервере Standard Edition, на сервере переднего плана, в директоре или в устройстве для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-117">It resides along with other components on a Standard Edition server, Front End Server, Director, or Survivable Branch Appliance.</span></span> <span data-ttu-id="5d5a7-118">Пул регистратора состоит из служб регистратора, работающих в интерфейсном пуле и находящихся на том же сайте.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-118">A Registrar pool consists of Registrar Services running on the Front End pool and residing at the same site.</span></span> <span data-ttu-id="5d5a7-119">Пул переднего плана должен поддерживать балансировку нагрузки.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-119">The Front End pool must be load balanced.</span></span> <span data-ttu-id="5d5a7-120">Рекомендуется балансировка нагрузки на DNS, но допустима и аппаратная балансировка нагрузки.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-120">DNS load balancing is recommended, but hardware load balancing is acceptable.</span></span> <span data-ttu-id="5d5a7-121">Клиент Lync обнаруживает интерфейсный пул с помощью следующего механизма обнаружения:</span><span class="sxs-lookup"><span data-stu-id="5d5a7-121">A Lync client discovers the Front End pool through the following discovery mechanism:</span></span>

1.  <span data-ttu-id="5d5a7-122">DNS-запись SRV</span><span class="sxs-lookup"><span data-stu-id="5d5a7-122">DNS SRV record</span></span>

2.  <span data-ttu-id="5d5a7-123">Веб-служба автообнаружения (Новая надстройка в Lync Server 2013)</span><span class="sxs-lookup"><span data-stu-id="5d5a7-123">Autodiscovery Web Service (new in Lync Server 2013)</span></span>

3.  <span data-ttu-id="5d5a7-124">Параметр DHCP 120</span><span class="sxs-lookup"><span data-stu-id="5d5a7-124">DHCP option 120</span></span>

<span data-ttu-id="5d5a7-125">После подключения клиента Lync к интерфейсному пулу он направляется подсистемой балансировки нагрузки на один из серверов переднего плана в пуле.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-125">After the Lync client connects to the Front End pool, it is directed by the load balancer to one of the Front End Servers in the pool.</span></span> <span data-ttu-id="5d5a7-126">Сервер переднего плана, в свою очередь, перенаправляет клиента на предпочитаемый регистратор в пуле.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-126">That Front End Server, in turn, redirects the client to a preferred Registrar in the pool.</span></span>

<span data-ttu-id="5d5a7-127">Каждый пользователь, для которого включена Корпоративная голосовая связь, назначается определенному пулу регистратора, который становится основным пулом регистратора этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-127">Each user enabled for Enterprise Voice is assigned to a particular Registrar pool, which becomes that user’s primary Registrar pool.</span></span> <span data-ttu-id="5d5a7-128">На конкретном сайте сотни или тысячи пользователей обычно совместно используют один основной пул регистратора.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-128">At a given site, hundreds or thousands of users typically share a single primary Registrar pool.</span></span> <span data-ttu-id="5d5a7-129">Учитывая потребление ресурсов центрального сайта всеми пользователями сайтов филиалов, функции присутствия, конференц-связи или отработки отказа которых зависят от центрального сайта, мы рекомендуем рассматривать каждого пользователя сайта филиала, как если бы он был зарегистрирован на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-129">To account for the consumption of central site resources by any branch site users that rely on the central site for presence, conferencing, or failover, we recommend that you consider each branch site user as though the user were a user registered with the central site.</span></span> <span data-ttu-id="5d5a7-130">В настоящее время количество пользователей сайта филиала не ограничено, включая пользователей, зарегистрированных с помощью устройства для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-130">There are currently no limits on the number of branch site users, including users registered with a Survivable Branch Appliance.</span></span>

<span data-ttu-id="5d5a7-131">Для обеспечения устойчивости голосовой связи в случае сбоя центрального сайта основной пул регистратора должен иметь один назначенный резервный пул регистратора, расположенный на другом сайте.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-131">To assure voice resiliency in the event of a central site failure, the primary Registrar pool must have a single designated backup Registrar pool located at another site.</span></span> <span data-ttu-id="5d5a7-132">Резервное копирование можно настроить с помощью параметров устойчивости в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-132">The backup can be configured by using Topology Builder resiliency settings.</span></span> <span data-ttu-id="5d5a7-133">Если существует устойчивая связь WAN между этими двумя сайтами, то пользователи, чей основной пул регистратора стал недоступен, автоматически перенаправляются в резервный пул регистратора.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-133">Assuming a resilient WAN link between the two sites, users whose primary Registrar pool is no longer available are automatically directed to the backup Registrar pool.</span></span>

<span data-ttu-id="5d5a7-134">Следующие действия описывают процесс обнаружения и регистрации клиента.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-134">The following steps describe the client discovery and registration process:</span></span>

1.  <span data-ttu-id="5d5a7-135">Клиент обнаруживает Lync Server с помощью записей DNS SRV.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-135">A client discovers Lync Server through DNS SRV records.</span></span> <span data-ttu-id="5d5a7-136">В Lync Server 2013 записи DNS SRV можно настроить так, чтобы они возвращали несколько полных доменных имен в запрос DNS SRV.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-136">In Lync Server 2013, DNS SRV records can be configured to return more than one FQDN to the DNS SRV query.</span></span> <span data-ttu-id="5d5a7-137">Например, если предприятие Contoso имеет три центральных сайта (в Северной Америке, в Европе и в Азиатско-Тихоокеанском регионе), и пул Директор существует на каждом центральном сайте, то записи DNS SRV могут указывать на полное доменное имя пула Директор в каждом из этих трех расположений.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-137">For example, if enterprise Contoso has three central sites (North America, Europe, and Asia-Pacific) and a Director pool at each central site, DNS SRV records can point to the Director pool FQDNs in each of the three locations.</span></span> <span data-ttu-id="5d5a7-138">Пока пул директоров в одном из расположений доступен, клиент может подключиться к серверу Lync Server первого прыжка.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-138">As long as the Director pool in one of the locations is available, the client can connect to the first hop Lync Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5d5a7-139">Использование пула директоров является необязательным.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-139">Using a Director pool is optional.</span></span> <span data-ttu-id="5d5a7-140">Вместо этого можно использовать пул переднего плана.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-140">A Front End pool can be used instead.</span></span>

    
    </div>

2.  <span data-ttu-id="5d5a7-141">Пул директоров информирует клиента Lync о основном и резервном пуле регистратора пользователя.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-141">The Director pool informs the Lync client about the user’s primary Registrar pool and backup Registrar pool.</span></span>

3.  <span data-ttu-id="5d5a7-142">Клиент Lync сначала пытается подключиться к основному пулу регистратора пользователя.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-142">The Lync client attempts to connect to the user’s primary Registrar pool first.</span></span> <span data-ttu-id="5d5a7-143">Если основной пул регистратора доступен, то регистратор принимает регистрацию.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-143">If the primary Registrar pool is available, the Registrar accepts the registration.</span></span> <span data-ttu-id="5d5a7-144">Если основной пул регистратора недоступен, клиент Lync пытается подключиться к пулу резервного регистратора.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-144">If the primary Registrar pool is unavailable, the Lync client attempts to connect to the backup Registrar pool.</span></span> <span data-ttu-id="5d5a7-145">Если резервный пул регистратора доступен и определяет, что основной пул регистратора недоступен (обнаруживая отсутствие пульса для указанного интервала отработки отказа), то этот резервный пул регистратора принимает регистрацию пользователя.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-145">If the backup Registrar pool is available and has determined that the user’s primary Registrar pool is unavailable (by detecting a lack of heartbeat for a specified failover interval) the backup Registrar pool accepts the user’s registration.</span></span> <span data-ttu-id="5d5a7-146">После того как регистраторы резервного копирования обнаружит, что основной регистратор снова станет доступным, пул резервного регистратора перенаправит клиенты Lync отработки отказа в основной пул.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-146">After the backup Registrar detects that the primary Registrar is again available, the backup Registrar pool will redirect failover Lync clients to their primary pool.</span></span>

<span data-ttu-id="5d5a7-p110">На следующем рисунке показана рекомендуемая топология для обеспечения устойчивости центрального сайта. На этом рисунке два сайта соединяются устойчивой связью WAN. Если центральный сайт становится недоступен, то назначенные этому пулу пользователи перенаправляются на резервный сайт для регистрации.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-p110">The following figure shows the recommended topology for assuring central site resiliency. The two sites are connected by a resilient WAN link. If the central site becomes unavailable, users who are assigned to that pool are directed to the backup site for registration.</span></span>

<span data-ttu-id="5d5a7-150">**Рекомендуемая топология для устойчивости центрального сайта**</span><span class="sxs-lookup"><span data-stu-id="5d5a7-150">**Recommended topology for central site voice resiliency**</span></span>

<span data-ttu-id="5d5a7-151">![Топология для центрального сайта голосовой связи](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "Топология для центрального сайта голосовой связи")</span><span class="sxs-lookup"><span data-stu-id="5d5a7-151">![Topology for central site voice resliency](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "Topology for central site voice resliency")</span></span>

</div>

<div>

## <a name="requirements-and-recommendations"></a><span data-ttu-id="5d5a7-152">Требования и рекомендации</span><span class="sxs-lookup"><span data-stu-id="5d5a7-152">Requirements and Recommendations</span></span>

<span data-ttu-id="5d5a7-153">Следующие требования и рекомендации для реализации устойчивости голосовой связи на центральном сайте подходят для большинства организаций.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-153">The following requirements and recommendations for implementing central site voice resiliency are appropriate for most organizations:</span></span>

  - <span data-ttu-id="5d5a7-154">Сайты, на которых размещаются основной и резервный пулы регистратора, должны быть связаны устойчивой связью WAN.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-154">The sites in which the primary and backup Registrar pools reside should be connected by a resilient WAN link.</span></span>

  - <span data-ttu-id="5d5a7-155">На каждом центральном сайте должен быть пул регистратора, состоящий из одного или нескольких регистраторов.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-155">Each central site must contain a Registrar pool consisting of one or more Registrars.</span></span>

  - <span data-ttu-id="5d5a7-156">Каждый пул регистратора должен быть сбалансирован с балансировкой нагрузки с помощью балансировки нагрузки на DNS, аппаратной балансировки нагрузки или и того, и других.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-156">Each Registrar pool must be load-balanced by using DNS load balancing, hardware load balancing, or both.</span></span> <span data-ttu-id="5d5a7-157">Подробные сведения о планировании конфигурации балансировки нагрузки приведены в статье [требования к балансировке нагрузки для Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d5a7-157">For detailed information about planning your load balancing configuration, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

  - <span data-ttu-id="5d5a7-158">Каждый пользователь должен быть назначен основному пулу регистратора с помощью командлета Lync Server Management Shell **Set — CsUser** или панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-158">Each user must be assigned to a primary Registrar pool by using either the Lync Server Management Shell **set-CsUser** cmdlet or the Lync Server Control Panel.</span></span>

  - <span data-ttu-id="5d5a7-159">Основной пул регистратора должен иметь один резервный пул регистратора, расположенный на другом центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-159">The primary Registrar pool must have a single backup Registrar pool located in a different central site.</span></span>

  - <span data-ttu-id="5d5a7-160">Основной пул регистратора должен быть настроен для отработки отказа в резервный пул регистратора.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-160">The primary Registrar pool must be configured to fail over to the backup Registrar pool.</span></span> <span data-ttu-id="5d5a7-161">По умолчанию задана отработка отказа основного пула регистратора в резервный пул через 300 секунд.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-161">By default, the primary Registrar is set to fail over to the backup Registrar pool after an interval of 300 seconds.</span></span> <span data-ttu-id="5d5a7-162">Этот интервал можно изменить с помощью построителя топологий Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-162">You can change this interval by using the Lync Server 2013 Topology Builder.</span></span>

  - <span data-ttu-id="5d5a7-163">Настройте маршрут отработки отказа, как описано в разделе "[Настройка отказоустойчивого маршрута в Lync Server 2013](lync-server-2013-configuring-a-failover-route.md)" в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-163">Configure a failover route, as described in the “[Configuring a failover route in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md)” topic in the Planning documentation.</span></span> <span data-ttu-id="5d5a7-164">При настройке маршрута укажите шлюз, расположенный на другом сайте, чем шлюз, указанный в основном маршруте.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-164">When configuring the route, specify a gateway that is located at a different site from the gateway specified in the primary route.</span></span>

  - <span data-ttu-id="5d5a7-165">Если центральный сайт, на котором размещается основной сервер управления, возможно, вышел из строя на длительное время, то придется переустановить средства управления на резервном сайте, иначе не будет возможности изменить какие-либо параметры управления.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-165">If the central site contained your primary management server and the site is likely to be down for an extended period, you will need to reinstall your management tools at the backup site; otherwise, you won’t be able to change any management settings.</span></span>

</div>

<div>

## <a name="dependencies"></a><span data-ttu-id="5d5a7-166">Зависимости</span><span class="sxs-lookup"><span data-stu-id="5d5a7-166">Dependencies</span></span>

<span data-ttu-id="5d5a7-167">Lync Server зависит от следующих компонентов инфраструктуры и программного обеспечения для обеспечения устойчивости голосовой связи:</span><span class="sxs-lookup"><span data-stu-id="5d5a7-167">Lync Server depends on the following infrastructure and software components to assure voice resiliency:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d5a7-168"><strong>Компонент</strong></span><span class="sxs-lookup"><span data-stu-id="5d5a7-168"><strong>Component</strong></span></span></p></td>
<td><p><span data-ttu-id="5d5a7-169"><strong>Nтекущий</strong></span><span class="sxs-lookup"><span data-stu-id="5d5a7-169"><strong>Functional</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d5a7-170">DNS</span><span class="sxs-lookup"><span data-stu-id="5d5a7-170">DNS</span></span></p></td>
<td><p><span data-ttu-id="5d5a7-171">Разрешение записей SRV и A для сервера и для возможности подключения клиента к серверу</span><span class="sxs-lookup"><span data-stu-id="5d5a7-171">Resolving SRV records and A records for server-server and server-client connectivity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d5a7-172">Exchange и веб-службы Exchange (EWS)</span><span class="sxs-lookup"><span data-stu-id="5d5a7-172">Exchange and Exchange Web Services (EWS)</span></span></p></td>
<td><p><span data-ttu-id="5d5a7-173">Хранение контактов; данные календаря</span><span class="sxs-lookup"><span data-stu-id="5d5a7-173">Contact storage; calendar data</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d5a7-174">Единая система обмена сообщениями Exchange и веб-службы Exchange</span><span class="sxs-lookup"><span data-stu-id="5d5a7-174">Exchange Unified Messaging and Exchange Web Services</span></span></p></td>
<td><p><span data-ttu-id="5d5a7-175">Журналы вызовов, список голосовой почты, голосовая почта</span><span class="sxs-lookup"><span data-stu-id="5d5a7-175">Call logs, voice mail list, voice mail</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d5a7-176">Параметры DHCP 120</span><span class="sxs-lookup"><span data-stu-id="5d5a7-176">DHCP Options 120</span></span></p></td>
<td><p><span data-ttu-id="5d5a7-177">Если запись DNS SRV недоступна, то для обнаружения регистратора клиент будет пытаться использовать параметр DHCP 120.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-177">If DNS SRV is unavailable, the client will attempt to use DHCP Option 120 to discover the Registrar.</span></span> <span data-ttu-id="5d5a7-178">Чтобы это работало, необходимо настроить DHCP-сервер или включить службу DHCP Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-178">For this to work, either a DHCP server must be configured or Lync Server 2013 DHCP must be enabled.</span></span> <span data-ttu-id="5d5a7-179">Сведения о требованиях к оборудованию и программному обеспечению для обеспечения устойчивости Branch-Site в разделе " <a href="lync-server-2013-branch-site-resiliency-requirements.md">требования к устойчивости сайта филиала" для Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5d5a7-179">For details, see Hardware and Software Requirements for Branch-Site Resiliency in <a href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</a> section.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="survivable-voice-features"></a><span data-ttu-id="5d5a7-180">Функции обеспечения голосовой связи</span><span class="sxs-lookup"><span data-stu-id="5d5a7-180">Survivable Voice Features</span></span>

<span data-ttu-id="5d5a7-181">Если предыдущие требования и рекомендации реализованы, то резервным пулом регистратора будут предоставляться следующие функции голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-181">If the preceding requirements and recommendations have been implemented, the following voice features will be provided by the backup Registrar pool:</span></span>

  - <span data-ttu-id="5d5a7-182">Исходящие вызовы ТСОП.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-182">Outbound PSTN calls</span></span>

  - <span data-ttu-id="5d5a7-183">Входящие вызовы ТСОП, если поставщик услуг телефонной связи поддерживает возможность отработки отказа на резервный сайт.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-183">Inbound PSTN calls, if the telephony service provider supports the ability to fail over to a backup site</span></span>

  - <span data-ttu-id="5d5a7-184">Корпоративные вызовы между пользователями как одного сайта, так и разных сайтов.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-184">Enterprise calls between users at both the same site and between two different sites</span></span>

  - <span data-ttu-id="5d5a7-185">Базовая обработка вызова, включая удержание, возобновление и переключение вызовов.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-185">Basic call handling, including call hold, retrieval, and transfer</span></span>

  - <span data-ttu-id="5d5a7-186">Двусторонний обмен мгновенными сообщениями и совместное использование аудио и видео пользователями на одном сайте.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-186">Two-party instant messaging and sharing audio and video between users at the same site</span></span>

  - <span data-ttu-id="5d5a7-187">Услуги переадресации вызовов, одновременных звонков в нескольких конечных точках, делегирования вызовов и групповых звонков, но только если обе стороны делегирования вызова или все члены группы настроены на одном и том же сайте.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-187">Call forwarding, simultaneous ringing of endpoints, call delegation, and team call services, but only if both parties to call delegation, or all team members, are configured at the same site.</span></span>

  - <span data-ttu-id="5d5a7-188">Продолжение функционирования существующих телефонов и клиентов.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-188">Existing phones and clients continue to work.</span></span>

  - <span data-ttu-id="5d5a7-189">Регистрация вызовов (CDR).</span><span class="sxs-lookup"><span data-stu-id="5d5a7-189">Call detail recording (CDR)</span></span>

  - <span data-ttu-id="5d5a7-190">Проверка подлинности и авторизация.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-190">Authentication and authorization</span></span>

<span data-ttu-id="5d5a7-191">Когда основной центральный сайт выходит из строя, могут также работать следующие функции голосовой связи (в зависимости от того, как они были настроены).</span><span class="sxs-lookup"><span data-stu-id="5d5a7-191">Depending on how they are configured, the following voice features may or may not work when a primary central site is out of service:</span></span>

  - <span data-ttu-id="5d5a7-192">Размещение и извлечение голосовых сообщений.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-192">Voice mail deposit and retrieval</span></span>
    
    <span data-ttu-id="5d5a7-193">Если необходимо, чтобы при выходе из строя основного центрального сайта оставалась доступной единая система обмена сообщениями Exchange, то необходимо выполнить одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-193">If you want to make Exchange UM available when the primary central site is out of service, you must do one of the following:</span></span>
    
      - <span data-ttu-id="5d5a7-194">Изменить запись DNS SRV таким образом, чтобы серверы единой системы обмена сообщениями Exchange на центральном сайте указывали на резервные серверы единой системы обмена сообщениями Exchange на другом сайте.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-194">Change DNS SRV records so that the Exchange UM servers at the central site point to backup Exchange UM servers at another site.</span></span>
    
      - <span data-ttu-id="5d5a7-195">Настройте абонентскую группу единой системы обмена сообщениями Exchange для каждого пользователя, чтобы включить серверы единой системы обмена сообщениями Exchange на центральном сайте и резервном сайте, но назначьте резервные серверы единой системы обмена сообщениями Exchange как отключенные.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-195">Configure each user’s Exchange UM dial plan to include Exchange UM servers at both the central site and the backup site, but designate the backup Exchange UM servers as disabled.</span></span> <span data-ttu-id="5d5a7-196">Если основной сайт становится недоступен, администратор Exchange должен пометить серверы единой системы обмена сообщениями Exchange на резервном сайте как включенный.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-196">If the primary site becomes unavailable, the Exchange administrator has to mark the Exchange UM servers at the backup site as enabled.</span></span>
    
    <span data-ttu-id="5d5a7-197">Если ни одно из описанных выше решений недоступно, то Exchange единой системы обмена сообщениями не будет доступен в случае, если центральный сайт становится недоступен.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-197">If neither of the preceding solutions is possible, then Exchange UM will not be available in the event the central site becomes unavailable.</span></span>

  - <span data-ttu-id="5d5a7-198">Конференц-связь всех типов.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-198">Conferencing of all types</span></span>
    
    <span data-ttu-id="5d5a7-p116">Пользователь, который в результате отработки отказа оказался на резервном сайте, может присоединяться к конференции, созданной или размещенной тем организатором, чей пул доступен, но не может создавать или размещать конференцию в своем основном пуле, который стал недоступен. Аналогично, другие пользователи не могут присоединяться к конференциям, размещенным в основном пуле пользователя, вовлеченного в отработку отказа.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-p116">A user who has failed over to a backup site can join a conference that is created or hosted by an organizer whose pool is available but cannot create or host a conference on his or her own primary pool, which is no longer available. Similarly, others users cannot join conferences that are hosted on the affected user’s primary pool.</span></span>

<span data-ttu-id="5d5a7-201">Следующие функции голосовой связи не будут работать в случае выхода из строя основного центрального сайта.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-201">The following voice features do not work when a primary central site is out of service:</span></span>

  - <span data-ttu-id="5d5a7-202">Автосекретарь конференции.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-202">Conference Auto-Attendant</span></span>

  - <span data-ttu-id="5d5a7-203">Функция присутствия и маршрутизация на основе DND.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-203">Presence and DND-based routing</span></span>

  - <span data-ttu-id="5d5a7-204">Обновление параметров переадресации вызовов.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-204">Updating call forwarding settings</span></span>

  - <span data-ttu-id="5d5a7-205">Служба "Группа ответа" и парковка вызовов.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-205">Response Group service and Call Park</span></span>

  - <span data-ttu-id="5d5a7-206">Подготовка новых телефонов и клиентов.</span><span class="sxs-lookup"><span data-stu-id="5d5a7-206">Provisioning new phones and clients</span></span>

  - <span data-ttu-id="5d5a7-207">Веб-поиск в адресной книге</span><span class="sxs-lookup"><span data-stu-id="5d5a7-207">Address Book Web Search</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5d5a7-208">См. также</span><span class="sxs-lookup"><span data-stu-id="5d5a7-208">See Also</span></span>


[<span data-ttu-id="5d5a7-209">Планирование устойчивости голосовой связи для сайта филиала в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d5a7-209">Planning for branch-site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-branch-site-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

