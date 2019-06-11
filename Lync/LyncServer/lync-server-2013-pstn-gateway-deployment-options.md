---
title: 'Lync Server 2013: параметры развертывания шлюза ТСОП'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN gateway deployment options
ms:assetid: d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398899(v=OCS.15)
ms:contentKeyID: 48185445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 137c9996429e953db22bea0c0dbd382f5a7af9a2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823821"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateway-deployment-options-in-lync-server-2013"></a><span data-ttu-id="37df2-102">Параметры развертывания шлюза ТСОП в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37df2-102">PSTN gateway deployment options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37df2-103">_**Тема последнего изменения:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="37df2-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>

## <a name="pstn-gateways"></a><span data-ttu-id="37df2-104">Шлюзы PSTN</span><span class="sxs-lookup"><span data-stu-id="37df2-104">PSTN Gateways</span></span>

<span data-ttu-id="37df2-105">Шлюзы коммутируемой телефонной сети (PSTN) — это аппаратные компоненты сторонних производителей, которые преобразуют сигнализацию и носители между корпоративной инфраструктурой голосовой связи и КТСОП (напрямую или с помощью связи с магистральными коммутаторами SIP).</span><span class="sxs-lookup"><span data-stu-id="37df2-105">Public switched telephone network (PSTN) gateways are third-party hardware components that translate signaling and media between the Enterprise Voice infrastructure and the PSTN, either directly or through connection to SIP trunks.</span></span> <span data-ttu-id="37df2-106">В любой из топологий шлюз прерывает PSTN.</span><span class="sxs-lookup"><span data-stu-id="37df2-106">In either topology, the gateway terminates the PSTN.</span></span> <span data-ttu-id="37df2-107">Шлюз изолирован в собственной подсети и подключается к корпоративной сети с помощью сервера обновлений.</span><span class="sxs-lookup"><span data-stu-id="37df2-107">The gateway is isolated in its own subnet and is connected to the enterprise network through the Mediation Server.</span></span>

<span data-ttu-id="37df2-108">Предприятие с несколькими сайтами обычно разворачивает один или несколько шлюзов на каждом сайте.</span><span class="sxs-lookup"><span data-stu-id="37df2-108">An enterprise with multiple sites would typically deploy one or more gateways at each site.</span></span> <span data-ttu-id="37df2-109">Сайты филиалов могут подключаться к КТСОП через шлюз или с помощью работающего устройства филиала, объединяющего шлюз и серверы в едином поле.</span><span class="sxs-lookup"><span data-stu-id="37df2-109">Branch sites can connect to the PSTN either through a gateway, or through a Survivable Branch Appliance, which combines gateway and servers in a single box.</span></span> <span data-ttu-id="37df2-110">Если сайты филиалов используют шлюз, на сайте должны быть как регистратора, так и сервера-посредника, если только это не является устойчивой ссылкой на глобальную сеть.</span><span class="sxs-lookup"><span data-stu-id="37df2-110">If branch sites use a gateway, both a Registrar and Mediation Server are required on site, unless the WAN link is resilient.</span></span> <span data-ttu-id="37df2-111">Один или несколько серверов-посредников, размещенных на серверах переднего плана, могут маршрутизировать звонки для одного или нескольких шлюзов на каждом сайте.</span><span class="sxs-lookup"><span data-stu-id="37df2-111">One or more Mediation Servers, which are collocated on Front End Servers, can route calls for the one or more gateways at each site.</span></span> <span data-ttu-id="37df2-112">Рекомендуется, чтобы регистратор, сервер-посредник и шлюз, необходимые для сайта, были развернуты как бесперебойно работающее устройство филиала.</span><span class="sxs-lookup"><span data-stu-id="37df2-112">We recommend that the Registrar, Mediation Server, and gateway required on site are deployed as a Survivable Branch Appliance.</span></span>

<span data-ttu-id="37df2-113">Определение количества, размера и местоположения шлюзов PSTN является, возможно, самым важным и дорогостоящим решением, которые необходимо учитывать при планировании корпоративной голосовой инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="37df2-113">Determining the number, size, and location of PSTN gateways is perhaps the most important and expensive decision you must make when planning your Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="37df2-114">Ниже приведены основные вопросы, на которые следует обратитьесь.</span><span class="sxs-lookup"><span data-stu-id="37df2-114">Here are the main questions to consider.</span></span> <span data-ttu-id="37df2-115">Имейте в виду, что ответы на эти вопросы будут зависеть друг от друга.</span><span class="sxs-lookup"><span data-stu-id="37df2-115">Keep in mind that the answers to these questions are all interdependent</span></span>

  - <span data-ttu-id="37df2-116">Сколько требуются шлюзы PSTN?</span><span class="sxs-lookup"><span data-stu-id="37df2-116">How many PSTN gateways are needed?</span></span> <span data-ttu-id="37df2-117">Ответ зависит от количества пользователей, ожидаемого числа одновременных звонков (нагрузки на трафик) и количества сайтов (для каждого сайта требуется один).</span><span class="sxs-lookup"><span data-stu-id="37df2-117">The answer depends on the number of users, the anticipated number of simultaneous calls (traffic load), and the number of sites (each site needs one).</span></span>

  - <span data-ttu-id="37df2-118">Укажите размер шлюзов.</span><span class="sxs-lookup"><span data-stu-id="37df2-118">What size should the gateways be?</span></span> <span data-ttu-id="37df2-119">Ответ зависит от количества пользователей на сайте и нагрузки на трафик.</span><span class="sxs-lookup"><span data-stu-id="37df2-119">The answer depends on the number of users at the site and on the traffic load.</span></span>

  - <span data-ttu-id="37df2-120">Где должны располагаться шлюзы?</span><span class="sxs-lookup"><span data-stu-id="37df2-120">Where should the gateways be located?</span></span> <span data-ttu-id="37df2-121">Ответ зависит частично на топологии и в географическом распределении Организации.</span><span class="sxs-lookup"><span data-stu-id="37df2-121">The answer depends in part on the topology and in part on the geographic distribution of your organization.</span></span>

<span data-ttu-id="37df2-122">Кроме того, следует ознакомиться с параметрами топологии шлюзов (Подробнее об этом можно узнать в разделе топологии шлюзов ниже в этой статье).</span><span class="sxs-lookup"><span data-stu-id="37df2-122">You should also consider your gateway topology options (for details, see Gateway Topologies later in this topic).</span></span>

<div>

## <a name="mn-trunk-support"></a><span data-ttu-id="37df2-123">Поддержка магистрали M:N</span><span class="sxs-lookup"><span data-stu-id="37df2-123">M:N Trunk Support</span></span>

<span data-ttu-id="37df2-124">Серверы-посредники могут маршрутизировать звонки с помощью нескольких шлюзов, контроллеров границ сеансов (SBCs), предоставленных поставщиками услуг телефонной связи Интернет, или сочетанием этих двух.</span><span class="sxs-lookup"><span data-stu-id="37df2-124">The Mediation Servers can route calls through multiple gateways, Session Border Controllers (SBCs) provided by Internet telephony service providers, or a combination of the two.</span></span> <span data-ttu-id="37df2-125">Кроме того, несколько серверов обновлений в пуле могут взаимодействовать с несколькими шлюзами.</span><span class="sxs-lookup"><span data-stu-id="37df2-125">Additionally, multiple Mediation Servers in the pool can interact with multiple gateways.</span></span> <span data-ttu-id="37df2-126">Логический маршрут, определенный между сервером-посредником и шлюзом, \*\* называется магистральом.</span><span class="sxs-lookup"><span data-stu-id="37df2-126">The logical route defined between a Mediation Server and gateway is called a *trunk*.</span></span> <span data-ttu-id="37df2-127">Когда внутренний пользователь посылает Звонок по протоколу PSTN, Маршрутизация исходящей маршрутизации в пуле переднего плана определяет, какая магистральная линия будет передаваться за весь список возможных сочетаний, которые могут быть доступны для маршрутизации определенного звонка.</span><span class="sxs-lookup"><span data-stu-id="37df2-127">When an internal user places a PSTN call, outbound routing logic on the Front End pool chooses which trunk to route over out of all possible combinations that may be available for routing that particular call.</span></span> <span data-ttu-id="37df2-128">Если при использовании функции балансировки нагрузки DNS не удается получить доступ к шлюзу из-за проблем с конкретным сервером в пуле, этот вызов будет выполнен повторно на альтернативный сервер-посредник в пуле.</span><span class="sxs-lookup"><span data-stu-id="37df2-128">With DNS load balancing, if a call fails to reach a gateway due to an issue with a particular Mediation Server in the pool, the call will be retried to an alternate Mediation Server in the pool.</span></span>

<span data-ttu-id="37df2-129">Сведения о планировании нескольких шлюзов можно найти [в м:н магистральной магистрали в Lync Server 2013](lync-server-2013-m-n-trunk.md).</span><span class="sxs-lookup"><span data-stu-id="37df2-129">For details about planning for multiple gateways, see [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).</span></span>

<span data-ttu-id="37df2-130">Подробнее об улучшении маршрутизации исходящих сообщений можно узнать [в разделе маршруты к голосовой связи в Lync Server 2013](lync-server-2013-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="37df2-130">For details about other outbound routing enhancements, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="gateway-topologies"></a><span data-ttu-id="37df2-131">Топологии шлюзов</span><span class="sxs-lookup"><span data-stu-id="37df2-131">Gateway Topologies</span></span>

<span data-ttu-id="37df2-132">При рассмотрении основных вопросов, возникающих при развертывании шлюза, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="37df2-132">When you consider the fundamental questions of gateway deployment, follow these steps:</span></span>

1.  <span data-ttu-id="37df2-133">Подсчитайте количество сайтов, на которых вы хотите использовать PSTN-связь, с помощью корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="37df2-133">Count the sites at which you want to provide PSTN connectivity by using Enterprise Voice.</span></span>

2.  <span data-ttu-id="37df2-134">Оцените трафик на каждом сайте (количество пользователей и среднее количество звонков в час для одного пользователя).</span><span class="sxs-lookup"><span data-stu-id="37df2-134">Estimate the traffic at each site (number of users and average number of calls per hour per user).</span></span>

3.  <span data-ttu-id="37df2-135">Развертывание одного или нескольких шлюзов на каждом сайте для обработки предполагаемого трафика.</span><span class="sxs-lookup"><span data-stu-id="37df2-135">Deploy one or more gateways at each site to handle the anticipated traffic.</span></span>

<span data-ttu-id="37df2-136">Результирующая топология распределенного шлюза показана на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="37df2-136">The resulting distributed gateway topology is shown in the following figure.</span></span>

<span data-ttu-id="37df2-137">**Топология распределенного шлюза**</span><span class="sxs-lookup"><span data-stu-id="37df2-137">**Distributed gateway topology**</span></span>

<span data-ttu-id="37df2-138">![Схема топологии распределенного шлюза] (images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Схема топологии распределенного шлюза")</span><span class="sxs-lookup"><span data-stu-id="37df2-138">![Distributed Gateway Topology diagram](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Distributed Gateway Topology diagram")</span></span>

<span data-ttu-id="37df2-139">В этой топологии звонки между сотрудниками на каждом сайте и между сайтами пересылаются по интрасети.</span><span class="sxs-lookup"><span data-stu-id="37df2-139">With this topology, calls among workers at each site and between sites are all routed over your intranet.</span></span> <span data-ttu-id="37df2-140">Звонки по протоколу PSTN направляются по корпоративной IP-сети на шлюзы, которые ближе всего к расположению целевых номеров. Но что делать, если ваша организация поддерживает десятки или сотни и даже тысячи сайтов, распределенных по одному или нескольким континентам, то есть сколько финансовых учреждений и других крупных организаций?</span><span class="sxs-lookup"><span data-stu-id="37df2-140">Calls to the PSTN are routed over the enterprise IP network to the gateways that are closest to the location of the destination numbers.But what if your organization supports dozens or hundreds or even thousands of sites spread across one or more continents, as many financial institutions and other large enterprises do?</span></span> <span data-ttu-id="37df2-141">В таких случаях развертывание отдельных шлюзов на каждом сайте непрактично.</span><span class="sxs-lookup"><span data-stu-id="37df2-141">In such cases, deploying a separate gateway at each site is not practical.</span></span>

<span data-ttu-id="37df2-142">Для устранения этой неполадки многие крупные компании предпочитают разворачивать один или несколько крупных центральных сайтов телефонии, как показано на приведенном ниже рисунке.</span><span class="sxs-lookup"><span data-stu-id="37df2-142">To address this issue, many large companies prefer to deploy one or a few large telephony central sites, as shown in the following figure.</span></span>

<span data-ttu-id="37df2-143">**Топология центрального сайта телефонной связи**</span><span class="sxs-lookup"><span data-stu-id="37df2-143">**Telephony central site topology**</span></span>

<span data-ttu-id="37df2-144">![Топология шлюза центра обработки данных] (images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Топология шлюза центра обработки данных")</span><span class="sxs-lookup"><span data-stu-id="37df2-144">![Data center gateway topology](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Data center gateway topology")</span></span>

<span data-ttu-id="37df2-145">В этой топологии несколько крупных шлюзов, достаточных для размещения предполагаемой пользовательской нагрузки, развертываются на каждом центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="37df2-145">In this topology, several large gateways sufficient to accommodate the anticipated user load are deployed at each central site.</span></span> <span data-ttu-id="37df2-146">Все звонки пользователям в сети пересылаются поставщиком услуг телефонной связи компании на центральный сайт.</span><span class="sxs-lookup"><span data-stu-id="37df2-146">All calls to users in the enterprise are forwarded by the company's telephone service provider to a central site.</span></span> <span data-ttu-id="37df2-147">Логика маршрутизации на центральном сайте определяет, следует ли перенаправлять Звонок в интрасети или в КТСОП.</span><span class="sxs-lookup"><span data-stu-id="37df2-147">Routing logic at the central site determines whether the call should be routed over the intranet or to the PSTN.</span></span>

</div>

<div>

## <a name="gateway-location"></a><span data-ttu-id="37df2-148">Расположение шлюза</span><span class="sxs-lookup"><span data-stu-id="37df2-148">Gateway Location</span></span>

<span data-ttu-id="37df2-149">Расположение шлюза также может определять типы шлюзов, которые вы выбрали, и их настройки.</span><span class="sxs-lookup"><span data-stu-id="37df2-149">Gateway location may also determine the types of gateways that you choose and how they are configured.</span></span> <span data-ttu-id="37df2-150">Существуют десятки протоколов PSTN, но ни один из них не является общемировым стандартом.</span><span class="sxs-lookup"><span data-stu-id="37df2-150">There are dozens of PSTN protocols, none of which is a worldwide standard.</span></span> <span data-ttu-id="37df2-151">Если все шлюзы находятся в одной стране или регионе, это не является проблемой, но если вы обнаружите шлюзы в нескольких странах или регионах, каждый из них должен быть настроен согласно стандартам PSTN для страны/региона.</span><span class="sxs-lookup"><span data-stu-id="37df2-151">If all your gateways are located in a single country/region, this is not an issue, but if you locate gateways in several countries/regions, each must be configured according to the PSTN standards of that country/region.</span></span> <span data-ttu-id="37df2-152">Кроме того, шлюзы, сертифицированные для работы в (например, в Канаде), могут не быть сертифицированы в Индии, Бразилии и ЕС.</span><span class="sxs-lookup"><span data-stu-id="37df2-152">Moreover, gateways that are certified for operation in, for example, Canada, may not be certified in India, Brazil, or the European Union.</span></span>

</div>

<div>

## <a name="gateway-size-and-number"></a><span data-ttu-id="37df2-153">Размер и номер шлюза</span><span class="sxs-lookup"><span data-stu-id="37df2-153">Gateway Size and Number</span></span>

<span data-ttu-id="37df2-154">Шлюзы PSTN, которые в большинстве организаций будут расцелесообразны для развертывания диапазонов размером от 2 до двух портов 960.</span><span class="sxs-lookup"><span data-stu-id="37df2-154">The PSTN gateways that most organizations will consider deploying range in size from 2 to as many as 960 ports.</span></span> <span data-ttu-id="37df2-155">(Существуют еще более крупные шлюзы, но они используются преимущественно поставщиками услуг телефонной связи.) При оценке количества портов, необходимых для вашей организации, используйте следующие правила:</span><span class="sxs-lookup"><span data-stu-id="37df2-155">(There are even larger gateways, but these are used mainly by telephone service providers.) When estimating the number of ports your organization requires, use the following guidelines:</span></span>

  - <span data-ttu-id="37df2-156">Организации с интенсивным использованием телефонной связи (один КОММУТИРУЕМый Звонок на пользователя в час) должны выделять один порт для каждых 15 пользователей.</span><span class="sxs-lookup"><span data-stu-id="37df2-156">Organizations with light telephony usage (one PSTN call per user per hour) should allocate one port for every 15 users.</span></span> <span data-ttu-id="37df2-157">Например, если у вас 20 пользователей, вам потребуется шлюз с двумя портами.</span><span class="sxs-lookup"><span data-stu-id="37df2-157">For example, if you have 20 users, you will require a gateway with two ports.</span></span>

  - <span data-ttu-id="37df2-158">Организации со средним использованием телефонной связи (два звонка на каждого пользователя в час) должны выделять один порт для каждых 10 пользователей.</span><span class="sxs-lookup"><span data-stu-id="37df2-158">Organizations with moderate telephony usage (two PSTN calls per user per hour) should allocate one port for every 10 users.</span></span> <span data-ttu-id="37df2-159">Например, если у вас есть 100 пользователей, вам потребуется всего 10 портов, выделенных для одного или нескольких шлюзов.</span><span class="sxs-lookup"><span data-stu-id="37df2-159">For example, if you have 100 users, you will require a total of 10 ports allocated among one or more gateways.</span></span>

  - <span data-ttu-id="37df2-160">Организации с высокой использованием телефонной связи (три или более PSTN-звонки на одного пользователя в час) должны выделять один порт для каждых пяти пользователей.</span><span class="sxs-lookup"><span data-stu-id="37df2-160">Organizations with heavy telephony usage (three or more PSTN calls per user per hour) should allocate one port for every five users.</span></span> <span data-ttu-id="37df2-161">Например, если у вас есть 47 000 пользователей, вам потребуется всего один из 9 400 портов, выделенных по крайней мере на 10 крупных шлюзов.</span><span class="sxs-lookup"><span data-stu-id="37df2-161">For example, if you have 47,000 users, you will require a total of 9,400 ports allocated among at least 10 large gateways.</span></span>

  - <span data-ttu-id="37df2-162">Дополнительные порты можно приобрести в том случае, если количество пользователей или объем трафика в Организации увеличится.</span><span class="sxs-lookup"><span data-stu-id="37df2-162">Additional ports can be acquired as the number of users or amount of traffic in your organization increases.</span></span>

<span data-ttu-id="37df2-163">Для любого числа пользователей, которых вы обязаны поддерживатье, вы можете выбирать вариант развертывания меньшего количества более крупных шлюзов или небольших единиц.</span><span class="sxs-lookup"><span data-stu-id="37df2-163">For any given number of users you must support, you have the choice of deploying fewer, larger gateways, or smaller ones.</span></span> <span data-ttu-id="37df2-164">Как правило, рекомендуется поддерживать доступность не менее двух шлюзов для Организации в случае сбоя одного шлюза.</span><span class="sxs-lookup"><span data-stu-id="37df2-164">As a rule, a minimum of two gateways for an organization is recommended to maintain availability if one gateway fails.</span></span>

<span data-ttu-id="37df2-165">У каждого развертываемого шлюза PSTN должен быть хотя бы один сервер соответствующего посредника.</span><span class="sxs-lookup"><span data-stu-id="37df2-165">Each PSTN gateway that you deploy must have at least one corresponding Mediation Server.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

