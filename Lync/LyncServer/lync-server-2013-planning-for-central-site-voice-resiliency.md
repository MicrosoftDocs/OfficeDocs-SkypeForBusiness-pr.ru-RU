---
title: 'Lync Server 2013: планирование устойчивости голосовой связи для центрального сайта'
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
ms.openlocfilehash: fbeda869c078e6adfce18088545428170b356980
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41754359"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-central-site-voice-resiliency-in-lync-server-2013"></a><span data-ttu-id="b3862-102">Планирование устойчивости голосовой связи для центрального сайта в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3862-102">Planning for central site voice resiliency in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3862-103">_**Тема последнего изменения:** 2013-10-30_</span><span class="sxs-lookup"><span data-stu-id="b3862-103">_**Topic Last Modified:** 2013-10-30_</span></span>

<span data-ttu-id="b3862-104">Все чаще у предприятий появляется много сайтов, распределенных по всему миру.</span><span class="sxs-lookup"><span data-stu-id="b3862-104">Increasingly, enterprises have multiple sites spread across the globe.</span></span> <span data-ttu-id="b3862-105">Поддержка экстренных служб, доступ к службе поддержки и возможность проведения критических задач, если центральный сайт не предназначен для использования в любых решениях для обеспечения устойчивости в рамках предприятия.</span><span class="sxs-lookup"><span data-stu-id="b3862-105">Maintaining emergency services, access to help desk, and the ability to conduct critical business tasks when a central site is out of service is essential for any Enterprise Voice resiliency solution.</span></span> <span data-ttu-id="b3862-106">Когда центральный сайт выходит из строя, должны выполняться следующие условия.</span><span class="sxs-lookup"><span data-stu-id="b3862-106">When a central site becomes unavailable, the following conditions must be met:</span></span>

  - <span data-ttu-id="b3862-107">Должна обеспечиваться отработка отказа голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="b3862-107">Voice failover must be provided.</span></span>

  - <span data-ttu-id="b3862-108">Пользователи, которые обычно регистрируются в пуле переднего плана на центральном сайте, должны иметь возможность зарегистрироваться с помощью альтернативного пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="b3862-108">Users who ordinarily register with the Front End pool at the central site must be able to register with an alternative Front End pool.</span></span> <span data-ttu-id="b3862-109">Это можно сделать, создав несколько DNS SRV-записей, каждый из которых разрешается в пул директоров или интерфейсного пула на каждом из ваших основных сайтов.</span><span class="sxs-lookup"><span data-stu-id="b3862-109">This can be done by creating multiple DNS SRV records, each of which resolves to a Director pool or Front End pool in each of your central sites.</span></span> <span data-ttu-id="b3862-110">Вы можете настроить приоритет и веса записей SRV таким образом, чтобы пользователи, обслуживаемые этим центральным сайтом, могли получать соответствующую директорию и пул переднего плана вперед из других записей SRV.</span><span class="sxs-lookup"><span data-stu-id="b3862-110">You can adjust the priority and weights of the SRV records so that users who are served by that central site get the corresponding Director and Front End pool ahead of those in other SRV records.</span></span>

  - <span data-ttu-id="b3862-111">Входящие и исходящие вызовы пользователей, расположенных на других сайтах, должны перенаправляться в ТСОП.</span><span class="sxs-lookup"><span data-stu-id="b3862-111">Calls to and from users located at other sites must be rerouted to the PSTN.</span></span>

<span data-ttu-id="b3862-112">В этой статье описывается рекомендуемое решение для защиты устойчивости центрального сайта голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="b3862-112">This topic describes the recommended solution for securing central site voice resiliency.</span></span>

<div>

## <a name="architecture-and-topology"></a><span data-ttu-id="b3862-113">Архитектура и топология</span><span class="sxs-lookup"><span data-stu-id="b3862-113">Architecture and Topology</span></span>

<span data-ttu-id="b3862-114">Для планирования устойчивости голоса на центральном сайте требуется понимание центральной роли, которую играют регистратор Lync Server 2013 при включении голосовой отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="b3862-114">Planning for voice resiliency at a central site requires a basic understanding of the central role played by the Lync Server 2013 Registrar in enabling voice failover.</span></span> <span data-ttu-id="b3862-115">Служба регистратора Lync Server — это роль сервера, обеспечивающая регистрацию и проверку подлинности клиента и предоставляющей услуги маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="b3862-115">The Lync Server Registrar is a server role that enables client registration and authentication and provides routing services.</span></span> <span data-ttu-id="b3862-116">Оно размещается вместе с другими компонентами на сервере Standard Edition, серверном сервере, режиссером или бесперебойно работающем устройстве филиалов.</span><span class="sxs-lookup"><span data-stu-id="b3862-116">It resides along with other components on a Standard Edition server, Front End Server, Director, or Survivable Branch Appliance.</span></span> <span data-ttu-id="b3862-117">Пул регистраторов состоит из служб регистратора, запущенных в пуле переднего плана и расположенных на том же сайте.</span><span class="sxs-lookup"><span data-stu-id="b3862-117">A Registrar pool consists of Registrar Services running on the Front End pool and residing at the same site.</span></span> <span data-ttu-id="b3862-118">Пул переднего плана должен поддерживать балансировку нагрузки.</span><span class="sxs-lookup"><span data-stu-id="b3862-118">The Front End pool must be load balanced.</span></span> <span data-ttu-id="b3862-119">Рекомендуется балансировка нагрузки DNS, но балансировка нагрузки для оборудования является приемлемой.</span><span class="sxs-lookup"><span data-stu-id="b3862-119">DNS load balancing is recommended, but hardware load balancing is acceptable.</span></span> <span data-ttu-id="b3862-120">Клиент Lync обнаружит интерфейсный пул с помощью следующего механизма обнаружения:</span><span class="sxs-lookup"><span data-stu-id="b3862-120">A Lync client discovers the Front End pool through the following discovery mechanism:</span></span>

1.  <span data-ttu-id="b3862-121">SRV-запись DNS</span><span class="sxs-lookup"><span data-stu-id="b3862-121">DNS SRV record</span></span>

2.  <span data-ttu-id="b3862-122">Веб-служба с автообнаружением (Новая в Lync Server 2013)</span><span class="sxs-lookup"><span data-stu-id="b3862-122">Autodiscovery Web Service (new in Lync Server 2013)</span></span>

3.  <span data-ttu-id="b3862-123">Параметр DHCP 120</span><span class="sxs-lookup"><span data-stu-id="b3862-123">DHCP option 120</span></span>

<span data-ttu-id="b3862-124">После того как клиент Lync соединяется с интерфейсом переднего плана, он перенаправляется подсистемой балансировки нагрузки на один из серверов переднего плана в пуле.</span><span class="sxs-lookup"><span data-stu-id="b3862-124">After the Lync client connects to the Front End pool, it is directed by the load balancer to one of the Front End Servers in the pool.</span></span> <span data-ttu-id="b3862-125">Этот сервер переднего плана, в свою очередь, перенаправляет клиента на предпочтительный регистратор в пуле.</span><span class="sxs-lookup"><span data-stu-id="b3862-125">That Front End Server, in turn, redirects the client to a preferred Registrar in the pool.</span></span>

<span data-ttu-id="b3862-126">Каждому пользователю, для которого разрешено использование корпоративной голосовой почты, назначается конкретный пул регистраторов, который становится основным пулом регистраторов пользователей.</span><span class="sxs-lookup"><span data-stu-id="b3862-126">Each user enabled for Enterprise Voice is assigned to a particular Registrar pool, which becomes that user’s primary Registrar pool.</span></span> <span data-ttu-id="b3862-127">На конкретном сайте сотни или тысячи пользователей обычно совместно используют один основной пул регистратора.</span><span class="sxs-lookup"><span data-stu-id="b3862-127">At a given site, hundreds or thousands of users typically share a single primary Registrar pool.</span></span> <span data-ttu-id="b3862-128">Учитывая потребление ресурсов центрального сайта всеми пользователями сайтов филиалов, для которых функции присутствия, конференц-связи или отработки отказа зависят от центрального сайта, мы рекомендуем рассматривать каждого пользователя сайта филиала, как если бы он был зарегистрирован на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="b3862-128">To account for the consumption of central site resources by any branch site users that rely on the central site for presence, conferencing, or failover, we recommend that you consider each branch site user as though the user were a user registered with the central site.</span></span> <span data-ttu-id="b3862-129">В настоящее время не существует ограничений на количество пользователей сайтов филиалов, включая пользователей, зарегистрированных с помощью работающего устройства филиалов.</span><span class="sxs-lookup"><span data-stu-id="b3862-129">There are currently no limits on the number of branch site users, including users registered with a Survivable Branch Appliance.</span></span>

<span data-ttu-id="b3862-130">To assure voice resiliency in the event of a central site failure, the primary Registrar pool must have a single designated backup Registrar pool located at another site.</span><span class="sxs-lookup"><span data-stu-id="b3862-130">To assure voice resiliency in the event of a central site failure, the primary Registrar pool must have a single designated backup Registrar pool located at another site.</span></span> <span data-ttu-id="b3862-131">Резервное копирование можно настроить с помощью параметров устойчивости построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="b3862-131">The backup can be configured by using Topology Builder resiliency settings.</span></span> <span data-ttu-id="b3862-132">Assuming a resilient WAN link between the two sites, users whose primary Registrar pool is no longer available are automatically directed to the backup Registrar pool.</span><span class="sxs-lookup"><span data-stu-id="b3862-132">Assuming a resilient WAN link between the two sites, users whose primary Registrar pool is no longer available are automatically directed to the backup Registrar pool.</span></span>

<span data-ttu-id="b3862-133">Следующие действия описывают процесс обнаружения и регистрации клиента.</span><span class="sxs-lookup"><span data-stu-id="b3862-133">The following steps describe the client discovery and registration process:</span></span>

1.  <span data-ttu-id="b3862-134">Клиент обнаружит сервер Lync с помощью DNS SRV-записей.</span><span class="sxs-lookup"><span data-stu-id="b3862-134">A client discovers Lync Server through DNS SRV records.</span></span> <span data-ttu-id="b3862-135">В Lync Server 2013 записи DNS SRV можно настроить так, чтобы они возвращали несколько полных доменных имен в запрос DNS SRV.</span><span class="sxs-lookup"><span data-stu-id="b3862-135">In Lync Server 2013, DNS SRV records can be configured to return more than one FQDN to the DNS SRV query.</span></span> <span data-ttu-id="b3862-136">Например, если предприятие Contoso имеет три центральных сайта (в Северной Америке, в Европе и в Азиатско-Тихоокеанском регионе), и пул директоров существует на каждом центральном сайте, то записи DNS SRV могут указывать на полное доменное имя пула директоров в каждом из этих трех расположений.</span><span class="sxs-lookup"><span data-stu-id="b3862-136">For example, if enterprise Contoso has three central sites (North America, Europe, and Asia-Pacific) and a Director pool at each central site, DNS SRV records can point to the Director pool FQDNs in each of the three locations.</span></span> <span data-ttu-id="b3862-137">Если в одном из расположений есть пул режиссеров, клиент может подключиться к серверу Lync Server первого прыжка.</span><span class="sxs-lookup"><span data-stu-id="b3862-137">As long as the Director pool in one of the locations is available, the client can connect to the first hop Lync Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b3862-138">Использование пула режиссера не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="b3862-138">Using a Director pool is optional.</span></span> <span data-ttu-id="b3862-139">Вместо этого можно использовать пул переднего плана.</span><span class="sxs-lookup"><span data-stu-id="b3862-139">A Front End pool can be used instead.</span></span>

    
    </div>

2.  <span data-ttu-id="b3862-140">Пул режиссера информирует клиента Lync о основном пуле регистраторов и пуле регистратора резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="b3862-140">The Director pool informs the Lync client about the user’s primary Registrar pool and backup Registrar pool.</span></span>

3.  <span data-ttu-id="b3862-141">Клиент Lync сначала пытается соединиться с основным пулом регистраторов пользователей.</span><span class="sxs-lookup"><span data-stu-id="b3862-141">The Lync client attempts to connect to the user’s primary Registrar pool first.</span></span> <span data-ttu-id="b3862-142">Если основной пул регистратора доступен, то регистратор принимает регистрацию.</span><span class="sxs-lookup"><span data-stu-id="b3862-142">If the primary Registrar pool is available, the Registrar accepts the registration.</span></span> <span data-ttu-id="b3862-143">Если основной пул регистраторов недоступен, клиент Lync пытается подключиться к пулу регистратора резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="b3862-143">If the primary Registrar pool is unavailable, the Lync client attempts to connect to the backup Registrar pool.</span></span> <span data-ttu-id="b3862-144">Если резервный пул регистратора доступен и определяет, что основной пул регистратора недоступен (обнаруживая отсутствие пульса для указанного интервала отработки отказа), то этот резервный пул регистратора принимает регистрацию пользователя.</span><span class="sxs-lookup"><span data-stu-id="b3862-144">If the backup Registrar pool is available and has determined that the user’s primary Registrar pool is unavailable (by detecting a lack of heartbeat for a specified failover interval) the backup Registrar pool accepts the user’s registration.</span></span> <span data-ttu-id="b3862-145">После того как регистраторы архивации обнаружит, что основной регистратор снова станет доступен, пул регистратора резервных копий перенаправит клиентов Lync для отработки отказа в основной пул.</span><span class="sxs-lookup"><span data-stu-id="b3862-145">After the backup Registrar detects that the primary Registrar is again available, the backup Registrar pool will redirect failover Lync clients to their primary pool.</span></span>

<span data-ttu-id="b3862-146">На приведенном ниже рисунке показана Рекомендуемая топология для обеспечения устойчивости центрального сайта.</span><span class="sxs-lookup"><span data-stu-id="b3862-146">The following figure shows the recommended topology for assuring central site resiliency.</span></span> <span data-ttu-id="b3862-147">Два сайта соединены с помощью отказоустойчивой глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="b3862-147">The two sites are connected by a resilient WAN link.</span></span> <span data-ttu-id="b3862-148">Если центральный сайт станет недоступен, пользователи, которым назначен этот пул, направляются на резервный сайт для регистрации.</span><span class="sxs-lookup"><span data-stu-id="b3862-148">If the central site becomes unavailable, users who are assigned to that pool are directed to the backup site for registration.</span></span>

<span data-ttu-id="b3862-149">**Рекомендуемая топология для обеспечения устойчивости центрального голоса на центральном сайте**</span><span class="sxs-lookup"><span data-stu-id="b3862-149">**Recommended topology for central site voice resiliency**</span></span>

<span data-ttu-id="b3862-150">![Топология центрального сайта, обеспечивающего надежность голосовой связи](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "Топология центрального сайта, обеспечивающего надежность голосовой связи")</span><span class="sxs-lookup"><span data-stu-id="b3862-150">![Topology for central site voice resliency](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "Topology for central site voice resliency")</span></span>

</div>

<div>

## <a name="requirements-and-recommendations"></a><span data-ttu-id="b3862-151">Требования и рекомендации</span><span class="sxs-lookup"><span data-stu-id="b3862-151">Requirements and Recommendations</span></span>

<span data-ttu-id="b3862-152">Следующие требования и рекомендации для реализации устойчивости голосовой связи на центральном сайте подходят для большинства организаций.</span><span class="sxs-lookup"><span data-stu-id="b3862-152">The following requirements and recommendations for implementing central site voice resiliency are appropriate for most organizations:</span></span>

  - <span data-ttu-id="b3862-153">Сайты, на которых размещаются основной и резервный пулы регистратора, должны быть связаны устойчивой связью WAN.</span><span class="sxs-lookup"><span data-stu-id="b3862-153">The sites in which the primary and backup Registrar pools reside should be connected by a resilient WAN link.</span></span>

  - <span data-ttu-id="b3862-154">На каждом центральном сайте должен быть пул регистратора, состоящий из одного или нескольких регистраторов.</span><span class="sxs-lookup"><span data-stu-id="b3862-154">Each central site must contain a Registrar pool consisting of one or more Registrars.</span></span>

  - <span data-ttu-id="b3862-155">Каждый пул регистратора должен иметь балансировку нагрузки с использованием балансировки нагрузки DNS, аппаратную балансировку нагрузки или обе.</span><span class="sxs-lookup"><span data-stu-id="b3862-155">Each Registrar pool must be load-balanced by using DNS load balancing, hardware load balancing, or both.</span></span> <span data-ttu-id="b3862-156">Подробные сведения о планировании конфигурации балансировки нагрузки описаны в разделе [требования к балансировке нагрузки для Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3862-156">For detailed information about planning your load balancing configuration, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

  - <span data-ttu-id="b3862-157">Каждый пользователь должен быть назначен для основного пула регистратора с помощью командлета **Set-CsUser** оболочки Lync Server Management Shell или панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b3862-157">Each user must be assigned to a primary Registrar pool by using either the Lync Server Management Shell **set-CsUser** cmdlet or the Lync Server Control Panel.</span></span>

  - <span data-ttu-id="b3862-158">Основной пул регистратора должен иметь один резервный пул регистратора, расположенный на другом центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="b3862-158">The primary Registrar pool must have a single backup Registrar pool located in a different central site.</span></span>

  - <span data-ttu-id="b3862-159">The primary Registrar pool must be configured to fail over to the backup Registrar pool.</span><span class="sxs-lookup"><span data-stu-id="b3862-159">The primary Registrar pool must be configured to fail over to the backup Registrar pool.</span></span> <span data-ttu-id="b3862-160">By default, the primary Registrar is set to fail over to the backup Registrar pool after an interval of 300 seconds.</span><span class="sxs-lookup"><span data-stu-id="b3862-160">By default, the primary Registrar is set to fail over to the backup Registrar pool after an interval of 300 seconds.</span></span> <span data-ttu-id="b3862-161">Этот интервал можно изменить с помощью построителя топологии Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b3862-161">You can change this interval by using the Lync Server 2013 Topology Builder.</span></span>

  - <span data-ttu-id="b3862-162">Настройте маршрут перемещения при сбое, как описано в разделе "[Настройка маршрутизации для перемещения при сбое в Lync Server 2013](lync-server-2013-configuring-a-failover-route.md)" в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="b3862-162">Configure a failover route, as described in the “[Configuring a failover route in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md)” topic in the Planning documentation.</span></span> <span data-ttu-id="b3862-163">При настройке маршрута укажите шлюз, расположенный на другом сайте, чем шлюз, указанный в основном маршруте.</span><span class="sxs-lookup"><span data-stu-id="b3862-163">When configuring the route, specify a gateway that is located at a different site from the gateway specified in the primary route.</span></span>

  - <span data-ttu-id="b3862-164">Если центральный сайт, на котором размещается основной сервер управления, возможно, вышел из строя на длительное время, то придется переустановить средства управления на резервном сайте, иначе не будет возможности изменить какие-либо параметры управления.</span><span class="sxs-lookup"><span data-stu-id="b3862-164">If the central site contained your primary management server and the site is likely to be down for an extended period, you will need to reinstall your management tools at the backup site; otherwise, you won’t be able to change any management settings.</span></span>

</div>

<div>

## <a name="dependencies"></a><span data-ttu-id="b3862-165">Зависимости</span><span class="sxs-lookup"><span data-stu-id="b3862-165">Dependencies</span></span>

<span data-ttu-id="b3862-166">Сервер Lync Server зависит от следующих компонентов инфраструктуры и программного обеспечения, чтобы гарантировать устойчивость голоса.</span><span class="sxs-lookup"><span data-stu-id="b3862-166">Lync Server depends on the following infrastructure and software components to assure voice resiliency:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3862-167"><strong>Компонент</strong></span><span class="sxs-lookup"><span data-stu-id="b3862-167"><strong>Component</strong></span></span></p></td>
<td><p><span data-ttu-id="b3862-168"><strong>Функция</strong></span><span class="sxs-lookup"><span data-stu-id="b3862-168"><strong>Functional</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3862-169">Служба доменных имен</span><span class="sxs-lookup"><span data-stu-id="b3862-169">DNS</span></span></p></td>
<td><p><span data-ttu-id="b3862-170">Разрешение записей SRV и A для сервера и для возможности подключения клиента к серверу</span><span class="sxs-lookup"><span data-stu-id="b3862-170">Resolving SRV records and A records for server-server and server-client connectivity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3862-171">Exchange и веб-службы Exchange (EWS)</span><span class="sxs-lookup"><span data-stu-id="b3862-171">Exchange and Exchange Web Services (EWS)</span></span></p></td>
<td><p><span data-ttu-id="b3862-172">Хранение контактов; данные календаря</span><span class="sxs-lookup"><span data-stu-id="b3862-172">Contact storage; calendar data</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3862-173">Единая система обмена сообщениями Exchange и веб-службы Exchange</span><span class="sxs-lookup"><span data-stu-id="b3862-173">Exchange Unified Messaging and Exchange Web Services</span></span></p></td>
<td><p><span data-ttu-id="b3862-174">Журналы вызовов, список голосовой почты, голосовая почта</span><span class="sxs-lookup"><span data-stu-id="b3862-174">Call logs, voice mail list, voice mail</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3862-175">Параметры DHCP 120</span><span class="sxs-lookup"><span data-stu-id="b3862-175">DHCP Options 120</span></span></p></td>
<td><p><span data-ttu-id="b3862-176">Если запись DNS SRV недоступна, то для обнаружения регистратора клиент будет пытаться использовать параметр DHCP 120.</span><span class="sxs-lookup"><span data-stu-id="b3862-176">If DNS SRV is unavailable, the client will attempt to use DHCP Option 120 to discover the Registrar.</span></span> <span data-ttu-id="b3862-177">Для этого необходимо настроить DHCP-сервер или включить поддержку протокола "Lync Server 2013".</span><span class="sxs-lookup"><span data-stu-id="b3862-177">For this to work, either a DHCP server must be configured or Lync Server 2013 DHCP must be enabled.</span></span> <span data-ttu-id="b3862-178">Дополнительные сведения: требования к оборудованию и программному обеспечению для обеспечения устойчивости сайтов филиалов в разделе <a href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b3862-178">For details, see Hardware and Software Requirements for Branch-Site Resiliency in <a href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</a> section.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="survivable-voice-features"></a><span data-ttu-id="b3862-179">Функции обеспечения голосовой связи</span><span class="sxs-lookup"><span data-stu-id="b3862-179">Survivable Voice Features</span></span>

<span data-ttu-id="b3862-180">Если предыдущие требования и рекомендации реализованы, то резервным пулом регистратора будут предоставляться следующие функции голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="b3862-180">If the preceding requirements and recommendations have been implemented, the following voice features will be provided by the backup Registrar pool:</span></span>

  - <span data-ttu-id="b3862-181">Исходящие вызовы ТСОП.</span><span class="sxs-lookup"><span data-stu-id="b3862-181">Outbound PSTN calls</span></span>

  - <span data-ttu-id="b3862-182">Входящие вызовы ТСОП, если поставщик услуг телефонной связи поддерживает возможность отработки отказа на резервный сайт.</span><span class="sxs-lookup"><span data-stu-id="b3862-182">Inbound PSTN calls, if the telephony service provider supports the ability to fail over to a backup site</span></span>

  - <span data-ttu-id="b3862-183">Корпоративные вызовы между пользователями как одного сайта, так и разных сайтов.</span><span class="sxs-lookup"><span data-stu-id="b3862-183">Enterprise calls between users at both the same site and between two different sites</span></span>

  - <span data-ttu-id="b3862-184">Базовая обработка вызова, включая удержание, возобновление и переключение вызовов.</span><span class="sxs-lookup"><span data-stu-id="b3862-184">Basic call handling, including call hold, retrieval, and transfer</span></span>

  - <span data-ttu-id="b3862-185">Двусторонний обмен мгновенными сообщениями и совместное использование аудио и видео пользователями на одном сайте.</span><span class="sxs-lookup"><span data-stu-id="b3862-185">Two-party instant messaging and sharing audio and video between users at the same site</span></span>

  - <span data-ttu-id="b3862-186">Услуги переадресации вызовов, одновременных звонков в нескольких конечных точках, делегирования вызовов и групповых звонков, но только если обе стороны делегирования вызова или все члены группы настроены на одном и том же сайте.</span><span class="sxs-lookup"><span data-stu-id="b3862-186">Call forwarding, simultaneous ringing of endpoints, call delegation, and team call services, but only if both parties to call delegation, or all team members, are configured at the same site.</span></span>

  - <span data-ttu-id="b3862-187">Продолжение функционирования существующих телефонов и клиентов.</span><span class="sxs-lookup"><span data-stu-id="b3862-187">Existing phones and clients continue to work.</span></span>

  - <span data-ttu-id="b3862-188">Регистрация вызовов (CDR).</span><span class="sxs-lookup"><span data-stu-id="b3862-188">Call detail recording (CDR)</span></span>

  - <span data-ttu-id="b3862-189">Проверка подлинности и авторизация.</span><span class="sxs-lookup"><span data-stu-id="b3862-189">Authentication and authorization</span></span>

<span data-ttu-id="b3862-190">Когда основной центральный сайт выходит из строя, могут также работать следующие функции голосовой связи (в зависимости от того, как они были настроены).</span><span class="sxs-lookup"><span data-stu-id="b3862-190">Depending on how they are configured, the following voice features may or may not work when a primary central site is out of service:</span></span>

  - <span data-ttu-id="b3862-191">Размещение и извлечение голосовых сообщений.</span><span class="sxs-lookup"><span data-stu-id="b3862-191">Voice mail deposit and retrieval</span></span>
    
    <span data-ttu-id="b3862-192">Если необходимо, чтобы при выходе из строя основного центрального сайта оставалась доступной единая система обмена сообщениями Exchange, то необходимо выполнить одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="b3862-192">If you want to make Exchange UM available when the primary central site is out of service, you must do one of the following:</span></span>
    
      - <span data-ttu-id="b3862-193">Изменить запись DNS SRV таким образом, чтобы серверы единой системы обмена сообщениями Exchange на центральном сайте указывали на резервные серверы единой системы обмена сообщениями Exchange на другом сайте.</span><span class="sxs-lookup"><span data-stu-id="b3862-193">Change DNS SRV records so that the Exchange UM servers at the central site point to backup Exchange UM servers at another site.</span></span>
    
      - <span data-ttu-id="b3862-194">Настройте абонентскую группу Exchange для каждого пользователя, чтобы она включала серверы Exchange UM как на центральном сайте, так и на сайте резервного копирования, но указывает на то, что резервные серверы Exchange Server единой системы обмена сообщениями отключены.</span><span class="sxs-lookup"><span data-stu-id="b3862-194">Configure each user’s Exchange UM dial plan to include Exchange UM servers at both the central site and the backup site, but designate the backup Exchange UM servers as disabled.</span></span> <span data-ttu-id="b3862-195">Если основной сайт станет недоступен, администратор Exchange должен помечать серверы Exchange UM на резервном сайте как включенные.</span><span class="sxs-lookup"><span data-stu-id="b3862-195">If the primary site becomes unavailable, the Exchange administrator has to mark the Exchange UM servers at the backup site as enabled.</span></span>
    
    <span data-ttu-id="b3862-196">Если ни одно из описанных выше решений невозможно, то Exchange UM не будет доступен в случае, если центральный сайт станет недоступен.</span><span class="sxs-lookup"><span data-stu-id="b3862-196">If neither of the preceding solutions is possible, then Exchange UM will not be available in the event the central site becomes unavailable.</span></span>

  - <span data-ttu-id="b3862-197">Конференц-связь всех типов.</span><span class="sxs-lookup"><span data-stu-id="b3862-197">Conferencing of all types</span></span>
    
    <span data-ttu-id="b3862-p116">Пользователь, который в результате отработки отказа оказался на резервном сайте, может присоединяться к конференции, созданной или размещенной тем организатором, чей пул доступен, но не может создавать или размещать конференцию в своем основном пуле, который стал недоступен. Аналогично, другие пользователи не могут присоединяться к конференциям, размещенным в основном пуле пользователя, вовлеченного в отработку отказа.</span><span class="sxs-lookup"><span data-stu-id="b3862-p116">A user who has failed over to a backup site can join a conference that is created or hosted by an organizer whose pool is available but cannot create or host a conference on his or her own primary pool, which is no longer available. Similarly, others users cannot join conferences that are hosted on the affected user’s primary pool.</span></span>

<span data-ttu-id="b3862-200">Следующие функции голосовой связи не будут работать в случае выхода из строя основного центрального сайта.</span><span class="sxs-lookup"><span data-stu-id="b3862-200">The following voice features do not work when a primary central site is out of service:</span></span>

  - <span data-ttu-id="b3862-201">Автосекретарь конференции.</span><span class="sxs-lookup"><span data-stu-id="b3862-201">Conference Auto-Attendant</span></span>

  - <span data-ttu-id="b3862-202">Функция присутствия и маршрутизация на основе DND.</span><span class="sxs-lookup"><span data-stu-id="b3862-202">Presence and DND-based routing</span></span>

  - <span data-ttu-id="b3862-203">Обновление параметров переадресации вызовов.</span><span class="sxs-lookup"><span data-stu-id="b3862-203">Updating call forwarding settings</span></span>

  - <span data-ttu-id="b3862-204">Служба "Группа ответа" и парковка вызовов.</span><span class="sxs-lookup"><span data-stu-id="b3862-204">Response Group service and Call Park</span></span>

  - <span data-ttu-id="b3862-205">Подготовка новых телефонов и клиентов.</span><span class="sxs-lookup"><span data-stu-id="b3862-205">Provisioning new phones and clients</span></span>

  - <span data-ttu-id="b3862-206">Веб-поиск в адресной книге</span><span class="sxs-lookup"><span data-stu-id="b3862-206">Address Book Web Search</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b3862-207">См. также</span><span class="sxs-lookup"><span data-stu-id="b3862-207">See Also</span></span>


[<span data-ttu-id="b3862-208">Планирование устойчивости голосовой связи для сайта филиала в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3862-208">Planning for branch-site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-branch-site-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

