---
title: 'Lync Server 2013: рекомендации по развертыванию сервера обновлений'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Mediation Server
ms:assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398622(v=OCS.15)
ms:contentKeyID: 48184606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c91ea4368d96e6a558a25eda86d163e4ced4cb8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="bc43a-102">Рекомендации по развертыванию сервера обновлений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc43a-102">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc43a-103">_**Тема последнего изменения:** 2012-10-12_</span><span class="sxs-lookup"><span data-stu-id="bc43a-103">_**Topic Last Modified:** 2012-10-12_</span></span>

<span data-ttu-id="bc43a-104">В этой статье описаны рекомендации по планированию развертывания сервера исправлений.</span><span class="sxs-lookup"><span data-stu-id="bc43a-104">This topic describes planning guidelines for Mediation Server deployment.</span></span> <span data-ttu-id="bc43a-105">После того как вы Ознакомьтесь с этими рекомендациями, мы рекомендуем использовать средство планирования для создания и просмотра возможных альтернативных топологий, которые могут служить в качестве моделей для конечной топологии, которую вы решили развернуть.</span><span class="sxs-lookup"><span data-stu-id="bc43a-105">After reviewing these guidelines, we recommend that you use the Planning Tool to create and view possible alternative topologies, which can serve as models for what the final tailored topology that you decide to deploy would look like.</span></span>

<div>

## <a name="collocated-or-stand-alone-mediation-server"></a><span data-ttu-id="bc43a-106">Размещенный или изолированный сервер-посредник?</span><span class="sxs-lookup"><span data-stu-id="bc43a-106">Collocated or Stand-alone Mediation Server?</span></span>

<span data-ttu-id="bc43a-107">Сервер-посредник по умолчанию выровнен на сервере Standard Edition или на сервере переднего плана в пуле переднего плана на центральных сайтах.</span><span class="sxs-lookup"><span data-stu-id="bc43a-107">Mediation Server is by default collocated on the Standard Edition server or Front End Server in a Front End pool at central sites.</span></span> <span data-ttu-id="bc43a-108">Количество вызовов по телефонной сети общего пользования (ТСОП), которые могут быть обработаны, и количество компьютеров, необходимое в пуле, будет зависеть от следующих факторов:</span><span class="sxs-lookup"><span data-stu-id="bc43a-108">The number of public switched telephone network (PSTN) calls that can be handled and the number of machines required in the pool will depend on the following:</span></span>

  - <span data-ttu-id="bc43a-109">Количество одноранговых узлов шлюза, которые находятся в элементе управления "пул серверов обновлений"</span><span class="sxs-lookup"><span data-stu-id="bc43a-109">The number of gateway peers that the Mediation Server pool controls</span></span>

  - <span data-ttu-id="bc43a-110">от трафика через эти шлюзы в периоды высокой нагрузки;</span><span class="sxs-lookup"><span data-stu-id="bc43a-110">The high-volume traffic periods through those gateways</span></span>

  - <span data-ttu-id="bc43a-111">Процент звонков, исходящие из которых обходит сервер по устранению неполадок</span><span class="sxs-lookup"><span data-stu-id="bc43a-111">The percentage of calls that are calls whose media bypass the Mediation Server</span></span>

<span data-ttu-id="bc43a-112">При планировании обязательно учитывайте требования для обработки вызовов ТСОП и аудио- или видеоконференций, которые не настроены для обхода сервера-посредника, а также для обработки, необходимой для взаимодействий по передаче сигналов, для того количества вызовов в рабочие часы, которое должно поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="bc43a-112">When planning, be sure to take into account the media processing requirements for PSTN calls and A/V conferences that are not configured for media bypass, as well as the processing needed to handle signaling interactions for the number of busy-hour calls that need to be supported.</span></span> <span data-ttu-id="bc43a-113">Если ЦП недостаточно, необходимо развернуть изолированный пул серверов-исправлений. шлюзы PSTN, IP-АТС и SBCs должны быть разделены на подмножества, управляемые объединенными серверами в одном и том же пуле и изолированными серверами для одного или нескольких изолированных пулов.</span><span class="sxs-lookup"><span data-stu-id="bc43a-113">If there is not enough CPU, then you must deploy a stand-alone pool of Mediation Servers; and PSTN gateways, IP-PBXs, and SBCs will need to be split into subsets that are controlled by the collocated Mediation Servers in one pool and the stand-alone Mediation Servers in one or more stand-alone pools.</span></span>

<span data-ttu-id="bc43a-114">Если вы развернули шлюзы PSTN, IP-АТС или контроллеры границ сеанса (SBCs), которые не поддерживают нужные возможности для взаимодействия с пулом серверов-посредников, включая указанные ниже, они должны быть связаны с изолированным пулом, состоящим из одного из серверов-посредников:</span><span class="sxs-lookup"><span data-stu-id="bc43a-114">If you deployed PSTN gateways, IP-PBXs, or Session Border Controllers (SBCs) that do not support the correct capabilities to interact with a pool of Mediation Servers, including the following, then they will need to be associated with a stand-alone pool consisting of a single Mediation Server:</span></span>

  - <span data-ttu-id="bc43a-115">Выполнение балансировки нагрузки DNS для службы доменных имен в сети на серверах-посредниках в пуле (или иным образом трафик по маршруту для всех серверов-посредников в пуле)</span><span class="sxs-lookup"><span data-stu-id="bc43a-115">Perform network layer Domain Name System (DNS) load balancing across Mediation Servers in a pool (or otherwise route traffic uniformly to all Mediation Servers in a pool)</span></span>

  - <span data-ttu-id="bc43a-116">Пропускать трафик с любого сервера-посредника в пуле</span><span class="sxs-lookup"><span data-stu-id="bc43a-116">Accept traffic from any Mediation Server in a pool</span></span>

<span data-ttu-id="bc43a-117">Вы можете использовать средство Microsoft Lync Server 2013, планирование, чтобы определить, может ли выгрузить разгруппирование сервера обновлений с интерфейсом переднего плана.</span><span class="sxs-lookup"><span data-stu-id="bc43a-117">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether collocating the Mediation Server with your Front End pool can handle the load.</span></span> <span data-ttu-id="bc43a-118">Если среда не отвечает этим требованиям, необходимо развернуть пул серверов изолированных исправлений.</span><span class="sxs-lookup"><span data-stu-id="bc43a-118">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

</div>

<div>

## <a name="central-site-and-branch-site-considerations"></a><span data-ttu-id="bc43a-119">Рекомендации для центрального сайта и сайта филиала</span><span class="sxs-lookup"><span data-stu-id="bc43a-119">Central Site and Branch Site Considerations</span></span>

<span data-ttu-id="bc43a-120">Серверы исправлений на центральном веб-сайте могут использоваться для маршрутизации звонков для шлюзов IP-АТС или PSTN на сайтах филиалов.</span><span class="sxs-lookup"><span data-stu-id="bc43a-120">Mediation Servers at the central site can be used to route calls for IP-PBXs or PSTN gateways at branch sites.</span></span> <span data-ttu-id="bc43a-121">Однако при развертывании магистральных каналов SIP необходимо развернуть сервер-посредник на сайте, на котором завершается Каждая магистральная линия.</span><span class="sxs-lookup"><span data-stu-id="bc43a-121">If you deploy SIP trunks, however, you must deploy a Mediation Server at the site where each trunk terminates.</span></span> <span data-ttu-id="bc43a-122">Наличие сервера-посредника на центральном веб-сайте или шлюзе PSTN на сайте филиала не требует использования обхода мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="bc43a-122">Having a Mediation Server at the central site route calls for an IP-PBX or PSTN gateway at a branch site does not require the use of media bypass.</span></span> <span data-ttu-id="bc43a-123">Тем не менее, если вы можете включить обход мультимедиа, это сократит задержку пути к носителю и, следовательно, получит улучшенное качество мультимедиа, так как больше не требуется указывать путь к сообщению.</span><span class="sxs-lookup"><span data-stu-id="bc43a-123">However, if you can enable media bypass, doing so will reduce media path latency and, consequently, result in improved media quality because the media path is no longer required to follow the signaling path.</span></span> <span data-ttu-id="bc43a-124">Media bypass will also decrease the processing load on the pool.</span><span class="sxs-lookup"><span data-stu-id="bc43a-124">Media bypass will also decrease the processing load on the pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bc43a-125">Функция обхода сервера-посредника взаимодействует не со всеми шлюзами ТСОП, IP-PBX и пограничным контроллером SBC.</span><span class="sxs-lookup"><span data-stu-id="bc43a-125">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="bc43a-126">Корпорация Майкрософт протестировала набор шлюзов ТСОП и контроллеров SBC с сертифицированными партнерами и провела некоторые тесты для Cisco IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="bc43a-126">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="bc43a-127">Обход мультимедиа поддерживается только в том случае, если у вас есть продукты и версии, указанные в едином приложении <A href="http://go.microsoft.com/fwlink/p/?linkid=268730">http://go.microsoft.com/fwlink/p/?LinkId=268730</A>для взаимодействия с Open Communications — Lync Server на.</span><span class="sxs-lookup"><span data-stu-id="bc43a-127">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=268730">http://go.microsoft.com/fwlink/p/?LinkId=268730</A>.</span></span>



</div>

<span data-ttu-id="bc43a-128">Если требуется устойчивость сайта филиала, то можно разворачивать работающее устройство филиала или сочетание сервера переднего плана, сервера-посредника и шлюза на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="bc43a-128">If branch site resiliency is required, a Survivable Branch Appliance or combination of a Front End Server, a Mediation Server, and a gateway must be deployed at the branch site.</span></span> <span data-ttu-id="bc43a-129">(Допущение с учетом устойчивости сайтов филиалов состоит в том, что присутствие и конференции на сайте не устойчивы.) Рекомендации по планированию веб-сайтов для голосовой связи можно найти [в статье Планирование обеспечения устойчивости голоса для филиалов в Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span><span class="sxs-lookup"><span data-stu-id="bc43a-129">(The assumption with branch site resiliency is that presence and conferencing are not resilient at the site.) For guidance on branch site planning for voice, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span></span>

<span data-ttu-id="bc43a-130">При взаимодействии с IP-УАТС, если IP-УАТС неправильно поддерживает раннее взаимодействие с мультимедиа в нескольких ранних диалоговых окнах и взаимодействиях RFC 3960, может быть выполнена обрезка первых нескольких слов приветствия для входящих звонков из IP-УАТС в конечные точки Lync.</span><span class="sxs-lookup"><span data-stu-id="bc43a-130">For interactions with an IP-PBX, if the IP-PBX does not correctly support early media interactions with multiple early dialogs and RFC 3960 interactions, there can be clipping of the first few words of the greeting for incoming calls from the IP-PBX to Lync endpoints.</span></span> <span data-ttu-id="bc43a-131">Такое поведение может быть более серьезным, если сервер-посредник на центральном сайте является маршрутной маршрутизацией для IP-УАТС, в которой маршрут завершается на сайте филиала, так как для завершения передачи сигналов требуется больше времени.</span><span class="sxs-lookup"><span data-stu-id="bc43a-131">This behavior can be more severe if a Mediation Server at a central site is routing calls for an IP-PBX where the route terminates at a branch site, because more time is needed for signaling to complete.</span></span> <span data-ttu-id="bc43a-132">Если вы попытаетесь устранить эту проблему, развертывание сервера обновлений на сайте филиала является единственным способом сокращения количества первых слов.</span><span class="sxs-lookup"><span data-stu-id="bc43a-132">If you experience this behavior, deploying a Mediation Server at the branch site is the only way to reduce clipping of the first few words.</span></span>

<span data-ttu-id="bc43a-133">Наконец, если у вашего центрального сайта есть УАТС ТДМ или если ваш IP-УАТС не устраняет необходимость в шлюзе PSTN, необходимо развернуть шлюз на сервере-отсоединении и АТС, соединяющем маршрут звонков.</span><span class="sxs-lookup"><span data-stu-id="bc43a-133">Finally, if your central site has a TDM PBX, or if your IP-PBX does not eliminate the need for a PSTN gateway, then you must deploy a gateway on the call route connecting Mediation Server and the PBX.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bc43a-134">Чтобы улучшить производительность автономного сервера-посредника, следует включить масштабирование на принимающей стороне (RSS) в сетевых адаптерах на этих серверах.</span><span class="sxs-lookup"><span data-stu-id="bc43a-134">To improve the media performance of standalone Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on these servers.</span></span> <span data-ttu-id="bc43a-135">RSS поддерживает параллельную обработку входящих пакетов несколькими процессорами сервера.</span><span class="sxs-lookup"><span data-stu-id="bc43a-135">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="bc43a-136">Дополнительные сведения можно найти в разделе улучшенные возможности масштабирования на стороне приема в Windows Server <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?LinkId=268731</A>.</span><span class="sxs-lookup"><span data-stu-id="bc43a-136">For details, see "Receive-Side Scaling Enhancements in Windows Server" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?LinkId=268731</A>.</span></span> <span data-ttu-id="bc43a-137">Сведения о том, как включить RSS, см. в документации сетевого адаптера.</span><span class="sxs-lookup"><span data-stu-id="bc43a-137">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

