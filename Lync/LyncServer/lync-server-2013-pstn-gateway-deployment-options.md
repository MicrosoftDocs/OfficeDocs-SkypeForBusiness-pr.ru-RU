---
title: 'Lync Server 2013: варианты развертывания шлюза PSTN'
description: 'Lync Server 2013: варианты развертывания шлюза PSTN.'
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
ms.openlocfilehash: 871bc4d573e927f83cdb07d4fb2b5d5b954e6383
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565595"
---
# <a name="pstn-gateway-deployment-options-in-lync-server-2013"></a><span data-ttu-id="dbf1d-103">Варианты развертывания шлюза PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dbf1d-103">PSTN gateway deployment options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbf1d-104">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="dbf1d-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>

## <a name="pstn-gateways"></a><span data-ttu-id="dbf1d-105">Шлюзы ТСОП</span><span class="sxs-lookup"><span data-stu-id="dbf1d-105">PSTN Gateways</span></span>

<span data-ttu-id="dbf1d-106">Шлюзы PSTN — это аппаратные компоненты сторонних производителей, которые преобразуют сигналы и мультимедиа между инфраструктурой корпоративной голосовой связи и PSTN (напрямую или через подключение к магистральным линиям SIP).</span><span class="sxs-lookup"><span data-stu-id="dbf1d-106">Public switched telephone network (PSTN) gateways are third-party hardware components that translate signaling and media between the Enterprise Voice infrastructure and the PSTN, either directly or through connection to SIP trunks.</span></span> <span data-ttu-id="dbf1d-107">При любой топологии канал PSTN оканчивается шлюзом.</span><span class="sxs-lookup"><span data-stu-id="dbf1d-107">In either topology, the gateway terminates the PSTN.</span></span> <span data-ttu-id="dbf1d-108">Шлюз изолирован в собственной подсети и подключен к корпоративной сети через сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="dbf1d-108">The gateway is isolated in its own subnet and is connected to the enterprise network through the Mediation Server.</span></span>

<span data-ttu-id="dbf1d-109">Предприятие с несколькими сайтами обычно может развернуть на каждом сайте один или несколько шлюзов.</span><span class="sxs-lookup"><span data-stu-id="dbf1d-109">An enterprise with multiple sites would typically deploy one or more gateways at each site.</span></span> <span data-ttu-id="dbf1d-110">Сайты филиалов могут подключаться к PSTN либо через шлюз, либо через устройство для обеспечения связи в филиалах, которое сочетает шлюз и серверы в одном поле.</span><span class="sxs-lookup"><span data-stu-id="dbf1d-110">Branch sites can connect to the PSTN either through a gateway, or through a Survivable Branch Appliance, which combines gateway and servers in a single box.</span></span> <span data-ttu-id="dbf1d-111">Если для сайтов филиалов используется шлюз, на сайте необходимо указать и регистратор, и сервер-посредник, если канал WAN не является устойчивым.</span><span class="sxs-lookup"><span data-stu-id="dbf1d-111">If branch sites use a gateway, both a Registrar and Mediation Server are required on site, unless the WAN link is resilient.</span></span> <span data-ttu-id="dbf1d-112">Один или несколько серверов-посредников, размещенных на серверах переднего плана, могут маршрутизировать вызовы для одного или нескольких шлюзов на каждом сайте.</span><span class="sxs-lookup"><span data-stu-id="dbf1d-112">One or more Mediation Servers, which are collocated on Front End Servers, can route calls for the one or more gateways at each site.</span></span> <span data-ttu-id="dbf1d-113">Рекомендуется развертывать регистратор, сервер-посредник и шлюз на сайте в качестве устройства для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="dbf1d-113">We recommend that the Registrar, Mediation Server, and gateway required on site are deployed as a Survivable Branch Appliance.</span></span>

<span data-ttu-id="dbf1d-114">Определение количества, размера и местоположения шлюзов PSTN может быть самым важным и дорогостоящим решением, которое необходимо принять при планировании корпоративной инфраструктуры голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="dbf1d-114">Determining the number, size, and location of PSTN gateways is perhaps the most important and expensive decision you must make when planning your Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="dbf1d-p103">Следует принять во внимание несколько основных вопросов. Помните, что ответы на все эти вопросы зависят друг от друга.</span><span class="sxs-lookup"><span data-stu-id="dbf1d-p103">Here are the main questions to consider. Keep in mind that the answers to these questions are all interdependent</span></span>

  - <span data-ttu-id="dbf1d-p104">Сколько требуется шлюзов ТСОП? Ответ зависит от числа пользователей, предполагаемого числа одновременных звонков (трафика) и числа сайтов (на каждом сайте требуется один шлюз).</span><span class="sxs-lookup"><span data-stu-id="dbf1d-p104">How many PSTN gateways are needed? The answer depends on the number of users, the anticipated number of simultaneous calls (traffic load), and the number of sites (each site needs one).</span></span>

  - <span data-ttu-id="dbf1d-p105">Каков должен быть размер шлюза? Ответ зависит от числа пользователей на сайте и трафика.</span><span class="sxs-lookup"><span data-stu-id="dbf1d-p105">What size should the gateways be? The answer depends on the number of users at the site and on the traffic load.</span></span>

  - <span data-ttu-id="dbf1d-p106">Где шлюзы должны быть расположены? Ответ частично зависит от топологии и частично от географического распределения организации.</span><span class="sxs-lookup"><span data-stu-id="dbf1d-p106">Where should the gateways be located? The answer depends in part on the topology and in part on the geographic distribution of your organization.</span></span>

<span data-ttu-id="dbf1d-123">Следует также учитывать характеристики топологии шлюза (для получения дополнительных сведений см. пункт «Топологии шлюзов» далее в этом разделе).</span><span class="sxs-lookup"><span data-stu-id="dbf1d-123">You should also consider your gateway topology options (for details, see Gateway Topologies later in this topic).</span></span>

<div>

## <a name="mn-trunk-support"></a><span data-ttu-id="dbf1d-124">Поддержка магистрали M:N</span><span class="sxs-lookup"><span data-stu-id="dbf1d-124">M:N Trunk Support</span></span>

<span data-ttu-id="dbf1d-125">Серверы-посредники могут маршрутизировать вызовы с помощью нескольких шлюзов, пограничных контроллеров сеансов (SBCs), предоставляемых поставщиками услуг Интернет-телефонии, или их комбинации.</span><span class="sxs-lookup"><span data-stu-id="dbf1d-125">The Mediation Servers can route calls through multiple gateways, Session Border Controllers (SBCs) provided by Internet telephony service providers, or a combination of the two.</span></span> <span data-ttu-id="dbf1d-126">Кроме того, несколько серверов-посредников в пуле могут взаимодействовать с несколькими шлюзами.</span><span class="sxs-lookup"><span data-stu-id="dbf1d-126">Additionally, multiple Mediation Servers in the pool can interact with multiple gateways.</span></span> <span data-ttu-id="dbf1d-127">Логический маршрут, определенный между сервером-посредником и шлюзом, называется *магистральной магистралью*.</span><span class="sxs-lookup"><span data-stu-id="dbf1d-127">The logical route defined between a Mediation Server and gateway is called a *trunk*.</span></span> <span data-ttu-id="dbf1d-128">Когда внутренний пользователь помещает Звонок PSTN, логика маршрутизации исходящей маршрутизации в пуле переднего плана выбирает магистраль для маршрутизации всех возможных комбинаций, которые могут быть доступны для маршрутизации конкретного вызова.</span><span class="sxs-lookup"><span data-stu-id="dbf1d-128">When an internal user places a PSTN call, outbound routing logic on the Front End pool chooses which trunk to route over out of all possible combinations that may be available for routing that particular call.</span></span> <span data-ttu-id="dbf1d-129">При использовании балансировки нагрузки на DNS, если при вызове шлюза не удается получить доступ к шлюзу из-за проблем с определенным сервером-посредником в пуле, в этом случае будет выполнена повторная попытка вызова альтернативного сервера-посредника в пуле.</span><span class="sxs-lookup"><span data-stu-id="dbf1d-129">With DNS load balancing, if a call fails to reach a gateway due to an issue with a particular Mediation Server in the pool, the call will be retried to an alternate Mediation Server in the pool.</span></span>

<span data-ttu-id="dbf1d-130">Более подробную информацию о планировании нескольких шлюзов можно найти [в статье M:N магистрали в Lync Server 2013](lync-server-2013-m-n-trunk.md).</span><span class="sxs-lookup"><span data-stu-id="dbf1d-130">For details about planning for multiple gateways, see [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).</span></span>

<span data-ttu-id="dbf1d-131">Сведения о других усовершенствованных возможностях маршрутизации исходящей [почты приведены в статье Route Routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="dbf1d-131">For details about other outbound routing enhancements, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="gateway-topologies"></a><span data-ttu-id="dbf1d-132">Топологии шлюзов</span><span class="sxs-lookup"><span data-stu-id="dbf1d-132">Gateway Topologies</span></span>

<span data-ttu-id="dbf1d-133">Во время рассмотрения основных вопросов развертывания шлюзов придерживайтесь следующего подхода:</span><span class="sxs-lookup"><span data-stu-id="dbf1d-133">When you consider the fundamental questions of gateway deployment, follow these steps:</span></span>

1.  <span data-ttu-id="dbf1d-134">Подсчитайте, на каких сайтах вы хотите обеспечить подключение к сети PSTN с помощью корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="dbf1d-134">Count the sites at which you want to provide PSTN connectivity by using Enterprise Voice.</span></span>

2.  <span data-ttu-id="dbf1d-135">Оцените трафик в каждом сайте (число пользователей и среднее число звонков в час на пользователя).</span><span class="sxs-lookup"><span data-stu-id="dbf1d-135">Estimate the traffic at each site (number of users and average number of calls per hour per user).</span></span>

3.  <span data-ttu-id="dbf1d-136">Разверните один или несколько шлюзов на каждом сайте, чтобы обрабатывать предполагаемый трафик.</span><span class="sxs-lookup"><span data-stu-id="dbf1d-136">Deploy one or more gateways at each site to handle the anticipated traffic.</span></span>

<span data-ttu-id="dbf1d-137">Итоговая топология распределенных шлюзов показана на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="dbf1d-137">The resulting distributed gateway topology is shown in the following figure.</span></span>

<span data-ttu-id="dbf1d-138">**Топология распределенных шлюзов**</span><span class="sxs-lookup"><span data-stu-id="dbf1d-138">**Distributed gateway topology**</span></span>

<span data-ttu-id="dbf1d-139">![Схема топологии распределенного шлюза](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Схема топологии распределенного шлюза")</span><span class="sxs-lookup"><span data-stu-id="dbf1d-139">![Distributed Gateway Topology diagram](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Distributed Gateway Topology diagram")</span></span>

<span data-ttu-id="dbf1d-p108">В этой топологии звонки между работниками на каждом сайте и между сайтами маршрутизируются через интрасеть. Звонки в PSTN маршрутизируются через корпоративную IP-сеть в шлюзы, которые размещены наиболее близко к расположению конечных номеров. Но что если организация поддерживает десятки, сотни или даже тысячи сайтов, распределенных по одному или нескольким континентам, как это происходит в больших финансовых учреждениях и на других крупных предприятиях? В таких случаях развертывание отдельных шлюзов в каждом сайте непрактично.</span><span class="sxs-lookup"><span data-stu-id="dbf1d-p108">With this topology, calls among workers at each site and between sites are all routed over your intranet. Calls to the PSTN are routed over the enterprise IP network to the gateways that are closest to the location of the destination numbers.But what if your organization supports dozens or hundreds or even thousands of sites spread across one or more continents, as many financial institutions and other large enterprises do? In such cases, deploying a separate gateway at each site is not practical.</span></span>

<span data-ttu-id="dbf1d-143">Чтобы устранить эту ошибку, многие крупные компании предпочитают развернуть один или несколько больших центральных сайтов для телефонии, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="dbf1d-143">To address this issue, many large companies prefer to deploy one or a few large telephony central sites, as shown in the following figure.</span></span>

<span data-ttu-id="dbf1d-144">**Топология центрального сайта телефонии**</span><span class="sxs-lookup"><span data-stu-id="dbf1d-144">**Telephony central site topology**</span></span>

<span data-ttu-id="dbf1d-145">![Топология шлюза центра обработки данных](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Топология шлюза центра обработки данных")</span><span class="sxs-lookup"><span data-stu-id="dbf1d-145">![Data center gateway topology](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Data center gateway topology")</span></span>

<span data-ttu-id="dbf1d-146">В этой топологии несколько крупных шлюзов, достаточных для реализации предполагаемой пользовательской нагрузки, развертываются на каждом центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="dbf1d-146">In this topology, several large gateways sufficient to accommodate the anticipated user load are deployed at each central site.</span></span> <span data-ttu-id="dbf1d-147">Все звонки пользователям предприятия переадресовываются поставщиком услуг телефонии предприятия в центральный сайт.</span><span class="sxs-lookup"><span data-stu-id="dbf1d-147">All calls to users in the enterprise are forwarded by the company's telephone service provider to a central site.</span></span> <span data-ttu-id="dbf1d-148">Логика маршрутизации на центральном сайте определяет, следует ли маршрутизировать вызов через интрасеть или PSTN.</span><span class="sxs-lookup"><span data-stu-id="dbf1d-148">Routing logic at the central site determines whether the call should be routed over the intranet or to the PSTN.</span></span>

</div>

<div>

## <a name="gateway-location"></a><span data-ttu-id="dbf1d-149">Расположение шлюза</span><span class="sxs-lookup"><span data-stu-id="dbf1d-149">Gateway Location</span></span>

<span data-ttu-id="dbf1d-p110">Расположение шлюзов также может определять типы выбираемых шлюзов и их настройку. Есть десятки протоколов PSTN и ни один из них не является мировым стандартом. Если все ваши шлюзы расположены в одной стране или регионе, то проблем нет, но если шлюзы расположены в нескольких странах или регионах, то каждый шлюз должен настраиваться в соответствии со стандартами PSTN этой страны или региона. Более того, шлюзы, которые сертифицированы для работы, скажем, в Канаде, могут не быть сертифицированы в Индии, Бразилии или Европейском союзе.</span><span class="sxs-lookup"><span data-stu-id="dbf1d-p110">Gateway location may also determine the types of gateways that you choose and how they are configured. There are dozens of PSTN protocols, none of which is a worldwide standard. If all your gateways are located in a single country/region, this is not an issue, but if you locate gateways in several countries/regions, each must be configured according to the PSTN standards of that country/region. Moreover, gateways that are certified for operation in, for example, Canada, may not be certified in India, Brazil, or the European Union.</span></span>

</div>

<div>

## <a name="gateway-size-and-number"></a><span data-ttu-id="dbf1d-154">Размер и число шлюзов</span><span class="sxs-lookup"><span data-stu-id="dbf1d-154">Gateway Size and Number</span></span>

<span data-ttu-id="dbf1d-p111">Размер шлюзов ТСОП, которые большинство организаций будут выбирать для развертывания, находится в диапазоне от 2 до 960 портов. (Есть и более крупные шлюзы, но они используются в основном поставщиками услуг телефонии.) При оценке числа портов, необходимого организации, используйте следующие рекомендации:</span><span class="sxs-lookup"><span data-stu-id="dbf1d-p111">The PSTN gateways that most organizations will consider deploying range in size from 2 to as many as 960 ports. (There are even larger gateways, but these are used mainly by telephone service providers.) When estimating the number of ports your organization requires, use the following guidelines:</span></span>

  - <span data-ttu-id="dbf1d-p112">Организации с небольшим использованием телефонной связи (один звонок ТСОП на пользователя в час) должны выделять один порт на 15 пользователей. Например, если есть 20 пользователей, нужен шлюз с двумя портами.</span><span class="sxs-lookup"><span data-stu-id="dbf1d-p112">Organizations with light telephony usage (one PSTN call per user per hour) should allocate one port for every 15 users. For example, if you have 20 users, you will require a gateway with two ports.</span></span>

  - <span data-ttu-id="dbf1d-p113">Организации со средним использованием телефонной связи (два звонка ТСОП на пользователя в час) должны выделять один порт на 10 пользователей. Например, если есть 100 пользователей, в сумме нужно 10 портов, содержащихся в одном или нескольких шлюзах.</span><span class="sxs-lookup"><span data-stu-id="dbf1d-p113">Organizations with moderate telephony usage (two PSTN calls per user per hour) should allocate one port for every 10 users. For example, if you have 100 users, you will require a total of 10 ports allocated among one or more gateways.</span></span>

  - <span data-ttu-id="dbf1d-p114">Организации с высоким использованием телефонной связи (три или более звонков ТСОП на пользователя в час) должны выделять один порт на пять пользователей. Например, если есть 47 000 пользователей, в сумме нужно 9 400 портов, содержащихся минимум в десяти крупных шлюзах.</span><span class="sxs-lookup"><span data-stu-id="dbf1d-p114">Organizations with heavy telephony usage (three or more PSTN calls per user per hour) should allocate one port for every five users. For example, if you have 47,000 users, you will require a total of 9,400 ports allocated among at least 10 large gateways.</span></span>

  - <span data-ttu-id="dbf1d-163">Дополнительные порты могут приобретаться по мере увеличении в организации числа пользователей или трафика.</span><span class="sxs-lookup"><span data-stu-id="dbf1d-163">Additional ports can be acquired as the number of users or amount of traffic in your organization increases.</span></span>

<span data-ttu-id="dbf1d-p115">При любом числе пользователей, которых требуется поддерживать, есть выбор между развертыванием меньшего числа крупных шлюзов или большего числа небольших шлюзов. Как правило, рекомендуется развертывать минимум два шлюза, чтобы поддерживать доступность в случае сбоя одного шлюза.</span><span class="sxs-lookup"><span data-stu-id="dbf1d-p115">For any given number of users you must support, you have the choice of deploying fewer, larger gateways, or smaller ones. As a rule, a minimum of two gateways for an organization is recommended to maintain availability if one gateway fails.</span></span>

<span data-ttu-id="dbf1d-166">Каждый развертываемый шлюз PSTN должен иметь по крайней мере один соответствующий сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="dbf1d-166">Each PSTN gateway that you deploy must have at least one corresponding Mediation Server.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

