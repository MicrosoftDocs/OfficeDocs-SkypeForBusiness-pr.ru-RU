---
title: 'Lync Server 2013: параметры развертывания шлюза ТСОП'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN gateway deployment options
ms:assetid: d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398899(v=OCS.15)
ms:contentKeyID: 48185445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b2f3cd153a6dc8d101f44a3f087f0ccedfa9bf7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateway-deployment-options-in-lync-server-2013"></a><span data-ttu-id="96d32-102">Параметры развертывания шлюза ТСОП в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96d32-102">PSTN gateway deployment options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96d32-103">_**Тема последнего изменения:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="96d32-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>

## <a name="pstn-gateways"></a><span data-ttu-id="96d32-104">Шлюзы ТСОП</span><span class="sxs-lookup"><span data-stu-id="96d32-104">PSTN Gateways</span></span>

<span data-ttu-id="96d32-105">Шлюзы телефонных сетей общего пользования (ТСОП) — это сторонние аппаратные компоненты, которые преобразуют сигналы и данные между инфраструктурой службы "Корпоративная голосовая связь" и ТСОП либо напрямую, либо через подключение к магистралям SIP.</span><span class="sxs-lookup"><span data-stu-id="96d32-105">Public switched telephone network (PSTN) gateways are third-party hardware components that translate signaling and media between the Enterprise Voice infrastructure and the PSTN, either directly or through connection to SIP trunks.</span></span> <span data-ttu-id="96d32-106">В любой топологии канал ТСОП оканчивается шлюзом.</span><span class="sxs-lookup"><span data-stu-id="96d32-106">In either topology, the gateway terminates the PSTN.</span></span> <span data-ttu-id="96d32-107">Шлюз изолирован в собственной подсети и подключается к корпоративной сети через сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="96d32-107">The gateway is isolated in its own subnet and is connected to the enterprise network through the Mediation Server.</span></span>

<span data-ttu-id="96d32-108">В предприятиях с несколькими сайтами обычно можно развернуть на каждом сайте один или несколько шлюзов.</span><span class="sxs-lookup"><span data-stu-id="96d32-108">An enterprise with multiple sites would typically deploy one or more gateways at each site.</span></span> <span data-ttu-id="96d32-109">Сайты филиалов могут подключаться к ТСОП либо через шлюз, либо через устройство для обеспечения связи в филиалах, в котором совмещаются шлюз и серверы.</span><span class="sxs-lookup"><span data-stu-id="96d32-109">Branch sites can connect to the PSTN either through a gateway, or through a Survivable Branch Appliance, which combines gateway and servers in a single box.</span></span> <span data-ttu-id="96d32-110">При использовании шлюза на сайте филиала требуются регистратор и сервер-посредник, если только подключение через глобальную сеть не является достаточно устойчивым.</span><span class="sxs-lookup"><span data-stu-id="96d32-110">If branch sites use a gateway, both a Registrar and Mediation Server are required on site, unless the WAN link is resilient.</span></span> <span data-ttu-id="96d32-111">Один или несколько серверов-посредников, совместно размещаемых на серверах переднего плана, могут маршрутизировать звонки для одного или нескольких шлюзов на каждом сайте.</span><span class="sxs-lookup"><span data-stu-id="96d32-111">One or more Mediation Servers, which are collocated on Front End Servers, can route calls for the one or more gateways at each site.</span></span> <span data-ttu-id="96d32-112">Регистратор, сервер-посредник и шлюз, необходимые для сайта, рекомендуется развернуть в виде устройства для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="96d32-112">We recommend that the Registrar, Mediation Server, and gateway required on site are deployed as a Survivable Branch Appliance.</span></span>

<span data-ttu-id="96d32-113">Возможно, самое важное и дорогостоящее решение, которое необходимо принять во время планирования инфраструктуры службы "Корпоративная голосовая связь", — это определение количества, размера и расположения шлюзов ТСОП.</span><span class="sxs-lookup"><span data-stu-id="96d32-113">Determining the number, size, and location of PSTN gateways is perhaps the most important and expensive decision you must make when planning your Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="96d32-114">Следует принять во внимание несколько основных вопросов.</span><span class="sxs-lookup"><span data-stu-id="96d32-114">Here are the main questions to consider.</span></span> <span data-ttu-id="96d32-115">Помните, что ответы на все эти вопросы зависят друг от друга.</span><span class="sxs-lookup"><span data-stu-id="96d32-115">Keep in mind that the answers to these questions are all interdependent</span></span>

  - <span data-ttu-id="96d32-116">Сколько требуется шлюзов ТСОП?</span><span class="sxs-lookup"><span data-stu-id="96d32-116">How many PSTN gateways are needed?</span></span> <span data-ttu-id="96d32-117">Ответ зависит от числа пользователей, предполагаемого количества одновременных звонков (интенсивности трафика) и числа сайтов (на каждом сайте требуется один шлюз).</span><span class="sxs-lookup"><span data-stu-id="96d32-117">The answer depends on the number of users, the anticipated number of simultaneous calls (traffic load), and the number of sites (each site needs one).</span></span>

  - <span data-ttu-id="96d32-118">Каким должен быть размер шлюза?</span><span class="sxs-lookup"><span data-stu-id="96d32-118">What size should the gateways be?</span></span> <span data-ttu-id="96d32-119">Ответ зависит от числа пользователей на сайте и интенсивности трафика.</span><span class="sxs-lookup"><span data-stu-id="96d32-119">The answer depends on the number of users at the site and on the traffic load.</span></span>

  - <span data-ttu-id="96d32-120">Где шлюзы должны быть расположены?</span><span class="sxs-lookup"><span data-stu-id="96d32-120">Where should the gateways be located?</span></span> <span data-ttu-id="96d32-121">Ответ отчасти зависит от топологии и отчасти от географического распределения организации.</span><span class="sxs-lookup"><span data-stu-id="96d32-121">The answer depends in part on the topology and in part on the geographic distribution of your organization.</span></span>

<span data-ttu-id="96d32-122">Следует также учитывать характеристики топологии шлюза (дополнительные сведения см. в разделе "Топологии шлюзов" далее в этой статье).</span><span class="sxs-lookup"><span data-stu-id="96d32-122">You should also consider your gateway topology options (for details, see Gateway Topologies later in this topic).</span></span>

<div>

## <a name="mn-trunk-support"></a><span data-ttu-id="96d32-123">Поддержка магистрали M:N</span><span class="sxs-lookup"><span data-stu-id="96d32-123">M:N Trunk Support</span></span>

<span data-ttu-id="96d32-124">Сервер-посредник может маршрутизировать звонки через несколько шлюзов, через пограничные контроллеры сеансов (SBC), предоставляемые поставщиками услуг Интернет-телефонии, или через их сочетание.</span><span class="sxs-lookup"><span data-stu-id="96d32-124">The Mediation Servers can route calls through multiple gateways, Session Border Controllers (SBCs) provided by Internet telephony service providers, or a combination of the two.</span></span> <span data-ttu-id="96d32-125">Кроме того, несколько серверов-посредников в пуле могут взаимодействовать с несколькими шлюзами.</span><span class="sxs-lookup"><span data-stu-id="96d32-125">Additionally, multiple Mediation Servers in the pool can interact with multiple gateways.</span></span> <span data-ttu-id="96d32-126">Логический маршрут, определенный между сервером-посредником и шлюзом, называется *магистральом*.</span><span class="sxs-lookup"><span data-stu-id="96d32-126">The logical route defined between a Mediation Server and gateway is called a *trunk*.</span></span> <span data-ttu-id="96d32-127">Когда внутренний пользователь совершает звонок ТСОП, логика маршрутизации исходящих вызовов в интерфейсном пуле выбирает, через какую магистраль осуществлять маршрутизацию, из всех возможных комбинаций, которые могут быть доступны для маршрутизации этого конкретного звонка.</span><span class="sxs-lookup"><span data-stu-id="96d32-127">When an internal user places a PSTN call, outbound routing logic on the Front End pool chooses which trunk to route over out of all possible combinations that may be available for routing that particular call.</span></span> <span data-ttu-id="96d32-128">Если звонок не может достигнуть шлюза из-за проблем с определенным сервером-посредником в пуле, то с помощью балансировки нагрузки DNS звонок может быть направлен на другой сервер-посредник в пуле.</span><span class="sxs-lookup"><span data-stu-id="96d32-128">With DNS load balancing, if a call fails to reach a gateway due to an issue with a particular Mediation Server in the pool, the call will be retried to an alternate Mediation Server in the pool.</span></span>

<span data-ttu-id="96d32-129">Сведения о планировании нескольких шлюзов можно найти [в м:н магистральной магистрали в Lync Server 2013](lync-server-2013-m-n-trunk.md).</span><span class="sxs-lookup"><span data-stu-id="96d32-129">For details about planning for multiple gateways, see [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).</span></span>

<span data-ttu-id="96d32-130">Подробнее об улучшении маршрутизации исходящих сообщений можно узнать [в разделе маршруты к голосовой связи в Lync Server 2013](lync-server-2013-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="96d32-130">For details about other outbound routing enhancements, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="gateway-topologies"></a><span data-ttu-id="96d32-131">Топологии шлюзов</span><span class="sxs-lookup"><span data-stu-id="96d32-131">Gateway Topologies</span></span>

<span data-ttu-id="96d32-132">Рассматривая основные вопросы развертывания шлюзов, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="96d32-132">When you consider the fundamental questions of gateway deployment, follow these steps:</span></span>

1.  <span data-ttu-id="96d32-133">Посчитайте сайты, для которых необходимо предоставить подключение ТСОП с помощью службы "Корпоративная голосовая связь".</span><span class="sxs-lookup"><span data-stu-id="96d32-133">Count the sites at which you want to provide PSTN connectivity by using Enterprise Voice.</span></span>

2.  <span data-ttu-id="96d32-134">Оцените трафик на каждом сайте (число пользователей и среднее число звонков в час на пользователя).</span><span class="sxs-lookup"><span data-stu-id="96d32-134">Estimate the traffic at each site (number of users and average number of calls per hour per user).</span></span>

3.  <span data-ttu-id="96d32-135">Разверните один или несколько шлюзов на каждом сайте, чтобы обрабатывать предполагаемый трафик.</span><span class="sxs-lookup"><span data-stu-id="96d32-135">Deploy one or more gateways at each site to handle the anticipated traffic.</span></span>

<span data-ttu-id="96d32-136">Результирующая топология распределенного шлюза показана на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="96d32-136">The resulting distributed gateway topology is shown in the following figure.</span></span>

<span data-ttu-id="96d32-137">**Топология распределенного шлюза**</span><span class="sxs-lookup"><span data-stu-id="96d32-137">**Distributed gateway topology**</span></span>

<span data-ttu-id="96d32-138">![Схема топологии распределенного шлюза](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Схема топологии распределенного шлюза")</span><span class="sxs-lookup"><span data-stu-id="96d32-138">![Distributed Gateway Topology diagram](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Distributed Gateway Topology diagram")</span></span>

<span data-ttu-id="96d32-139">В этой топологии все звонки между сотрудниками в рамках каждого сайта и между сайтами маршрутизируются через интрасеть.</span><span class="sxs-lookup"><span data-stu-id="96d32-139">With this topology, calls among workers at each site and between sites are all routed over your intranet.</span></span> <span data-ttu-id="96d32-140">Звонки в ТСОП направляются через корпоративную IP-сеть в шлюзы, находящиеся ближе всего к расположению конечных номеров. А что если организация поддерживает десятки, сотни или даже тысячи сайтов, распределенных по одному или нескольким континентам, как это происходит в больших финансовых учреждениях и на других крупных предприятиях?</span><span class="sxs-lookup"><span data-stu-id="96d32-140">Calls to the PSTN are routed over the enterprise IP network to the gateways that are closest to the location of the destination numbers.But what if your organization supports dozens or hundreds or even thousands of sites spread across one or more continents, as many financial institutions and other large enterprises do?</span></span> <span data-ttu-id="96d32-141">В таких случаях развертывание отдельных шлюзов в каждом сайте непрактично.</span><span class="sxs-lookup"><span data-stu-id="96d32-141">In such cases, deploying a separate gateway at each site is not practical.</span></span>

<span data-ttu-id="96d32-142">Для устранения этой неполадки многие крупные компании предпочитают разворачивать один или несколько крупных центральных сайтов телефонии, как показано на приведенном ниже рисунке.</span><span class="sxs-lookup"><span data-stu-id="96d32-142">To address this issue, many large companies prefer to deploy one or a few large telephony central sites, as shown in the following figure.</span></span>

<span data-ttu-id="96d32-143">**Топология центрального сайта телефонной связи**</span><span class="sxs-lookup"><span data-stu-id="96d32-143">**Telephony central site topology**</span></span>

<span data-ttu-id="96d32-144">![Топология шлюза центра обработки данных](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Топология шлюза центра обработки данных")</span><span class="sxs-lookup"><span data-stu-id="96d32-144">![Data center gateway topology](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Data center gateway topology")</span></span>

<span data-ttu-id="96d32-145">В этой топологии на каждом центральном сайте развертывается несколько крупных шлюзов, которых достаточно для обслуживания предполагаемой пользовательской нагрузки.</span><span class="sxs-lookup"><span data-stu-id="96d32-145">In this topology, several large gateways sufficient to accommodate the anticipated user load are deployed at each central site.</span></span> <span data-ttu-id="96d32-146">Все звонки пользователям предприятия переадресовываются поставщиком услуг телефонии предприятия в центральный сайт.</span><span class="sxs-lookup"><span data-stu-id="96d32-146">All calls to users in the enterprise are forwarded by the company's telephone service provider to a central site.</span></span> <span data-ttu-id="96d32-147">Логика маршрутизации на центральном сайте определяет, должен ли звонок маршрутизироваться через интрасеть или направляться в ТСОП.</span><span class="sxs-lookup"><span data-stu-id="96d32-147">Routing logic at the central site determines whether the call should be routed over the intranet or to the PSTN.</span></span>

</div>

<div>

## <a name="gateway-location"></a><span data-ttu-id="96d32-148">Расположение шлюза</span><span class="sxs-lookup"><span data-stu-id="96d32-148">Gateway Location</span></span>

<span data-ttu-id="96d32-149">Расположение шлюзов также может влиять на выбор их типов и конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="96d32-149">Gateway location may also determine the types of gateways that you choose and how they are configured.</span></span> <span data-ttu-id="96d32-150">Существуют десятки протоколов ТСОП, и ни один из них не является мировым стандартом.</span><span class="sxs-lookup"><span data-stu-id="96d32-150">There are dozens of PSTN protocols, none of which is a worldwide standard.</span></span> <span data-ttu-id="96d32-151">Если все ваши шлюзы расположены в одной стране или регионе, то проблем нет, но если шлюзы расположены в нескольких странах или регионах, то каждый шлюз должен быть настроен в соответствии со стандартами ТСОП этой страны или этого региона.</span><span class="sxs-lookup"><span data-stu-id="96d32-151">If all your gateways are located in a single country/region, this is not an issue, but if you locate gateways in several countries/regions, each must be configured according to the PSTN standards of that country/region.</span></span> <span data-ttu-id="96d32-152">Более того, шлюзы, которые сертифицированы для работы, скажем, в Канаде, могут не быть сертифицированы в Индии, Бразилии или ЕС.</span><span class="sxs-lookup"><span data-stu-id="96d32-152">Moreover, gateways that are certified for operation in, for example, Canada, may not be certified in India, Brazil, or the European Union.</span></span>

</div>

<div>

## <a name="gateway-size-and-number"></a><span data-ttu-id="96d32-153">Размер и число шлюзов</span><span class="sxs-lookup"><span data-stu-id="96d32-153">Gateway Size and Number</span></span>

<span data-ttu-id="96d32-154">Размер шлюзов ТСОП, которые большинство организаций будут выбирать для развертывания, находится в диапазоне от 2 до 960 портов.</span><span class="sxs-lookup"><span data-stu-id="96d32-154">The PSTN gateways that most organizations will consider deploying range in size from 2 to as many as 960 ports.</span></span> <span data-ttu-id="96d32-155">(Существуют и более крупные шлюзы, но их используют в основном поставщики услуг телефонии.) При оценке числа портов, необходимого организации, руководствуйтесь приведенными ниже рекомендациями.</span><span class="sxs-lookup"><span data-stu-id="96d32-155">(There are even larger gateways, but these are used mainly by telephone service providers.) When estimating the number of ports your organization requires, use the following guidelines:</span></span>

  - <span data-ttu-id="96d32-156">Организациям, в которых телефония используется редко (один звонок ТСОП на пользователя в час), следует выделять по одному порту на 15 пользователей.</span><span class="sxs-lookup"><span data-stu-id="96d32-156">Organizations with light telephony usage (one PSTN call per user per hour) should allocate one port for every 15 users.</span></span> <span data-ttu-id="96d32-157">Например, если имеется 20 пользователей, нужен шлюз с двумя портами.</span><span class="sxs-lookup"><span data-stu-id="96d32-157">For example, if you have 20 users, you will require a gateway with two ports.</span></span>

  - <span data-ttu-id="96d32-158">Организациям с умеренным использованием телефонии (два звонка ТСОП на пользователя в час) следует выделять по одному порту на 10 пользователей.</span><span class="sxs-lookup"><span data-stu-id="96d32-158">Organizations with moderate telephony usage (two PSTN calls per user per hour) should allocate one port for every 10 users.</span></span> <span data-ttu-id="96d32-159">Например, если имеется 100 пользователей, в сумме нужно 10 портов, содержащихся в одном или нескольких шлюзах.</span><span class="sxs-lookup"><span data-stu-id="96d32-159">For example, if you have 100 users, you will require a total of 10 ports allocated among one or more gateways.</span></span>

  - <span data-ttu-id="96d32-160">Организациям с интенсивным использованием телефонии (три или более звонков ТСОП на пользователя в час) следует выделять по одному порту на пять пользователей.</span><span class="sxs-lookup"><span data-stu-id="96d32-160">Organizations with heavy telephony usage (three or more PSTN calls per user per hour) should allocate one port for every five users.</span></span> <span data-ttu-id="96d32-161">Например, если имеется 47 000 пользователей, в сумме нужно 9400 портов, содержащихся как минимум в 10 крупных шлюзах.</span><span class="sxs-lookup"><span data-stu-id="96d32-161">For example, if you have 47,000 users, you will require a total of 9,400 ports allocated among at least 10 large gateways.</span></span>

  - <span data-ttu-id="96d32-162">Дополнительные порты можно приобретать по мере увеличении числа пользователей или трафика в организации.</span><span class="sxs-lookup"><span data-stu-id="96d32-162">Additional ports can be acquired as the number of users or amount of traffic in your organization increases.</span></span>

<span data-ttu-id="96d32-163">Для любого количества обслуживаемых пользователей можно развернуть меньшее количество крупных шлюзов или большее число небольших шлюзов.</span><span class="sxs-lookup"><span data-stu-id="96d32-163">For any given number of users you must support, you have the choice of deploying fewer, larger gateways, or smaller ones.</span></span> <span data-ttu-id="96d32-164">Как правило, рекомендуется развертывать минимум два шлюза, чтобы поддерживать доступность в случае сбоя одного из них.</span><span class="sxs-lookup"><span data-stu-id="96d32-164">As a rule, a minimum of two gateways for an organization is recommended to maintain availability if one gateway fails.</span></span>

<span data-ttu-id="96d32-165">Каждому развернутому шлюзу ТСОП должен соответствовать как минимум один сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="96d32-165">Each PSTN gateway that you deploy must have at least one corresponding Mediation Server.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

