---
title: 'Lync Server 2013: рекомендации по развертыванию для сервера-посредника'
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
ms.openlocfilehash: f55ec3444348b2717721dcad890a4712cd8b9a3b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138200"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="f760f-102">Рекомендации по развертыванию сервера-посредника в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f760f-102">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f760f-103">_**Последнее изменение темы:** 2012-10-12_</span><span class="sxs-lookup"><span data-stu-id="f760f-103">_**Topic Last Modified:** 2012-10-12_</span></span>

<span data-ttu-id="f760f-104">В этом разделе описываются рекомендации по планированию развертывания сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="f760f-104">This topic describes planning guidelines for Mediation Server deployment.</span></span> <span data-ttu-id="f760f-105">После рассмотрения этих рекомендаций мы рекомендуем использовать средство планирования для создания и просмотра возможных альтернативных топологий, которые могут использоваться в качестве моделей для конечной подготовки, которая будет выглядеть в конечной топологии.</span><span class="sxs-lookup"><span data-stu-id="f760f-105">After reviewing these guidelines, we recommend that you use the Planning Tool to create and view possible alternative topologies, which can serve as models for what the final tailored topology that you decide to deploy would look like.</span></span>

<div>

## <a name="collocated-or-stand-alone-mediation-server"></a><span data-ttu-id="f760f-106">Совмещенный или изолированный сервер-посредник?</span><span class="sxs-lookup"><span data-stu-id="f760f-106">Collocated or Stand-alone Mediation Server?</span></span>

<span data-ttu-id="f760f-107">Сервер-посредник по умолчанию размещается на сервере Standard Edition или сервере переднего плана в интерфейсном пуле на центральных сайтах.</span><span class="sxs-lookup"><span data-stu-id="f760f-107">Mediation Server is by default collocated on the Standard Edition server or Front End Server in a Front End pool at central sites.</span></span> <span data-ttu-id="f760f-108">Количество вызовов ТСОП, которое может быть обработано, и необходимое количество компьютеров в пуле будет зависеть от следующих факторов:</span><span class="sxs-lookup"><span data-stu-id="f760f-108">The number of public switched telephone network (PSTN) calls that can be handled and the number of machines required in the pool will depend on the following:</span></span>

  - <span data-ttu-id="f760f-109">Число одноранговых узлов шлюза, которые управляются в пуле серверов-посредников</span><span class="sxs-lookup"><span data-stu-id="f760f-109">The number of gateway peers that the Mediation Server pool controls</span></span>

  - <span data-ttu-id="f760f-110">от трафика через эти шлюзы в периоды высокой нагрузки;</span><span class="sxs-lookup"><span data-stu-id="f760f-110">The high-volume traffic periods through those gateways</span></span>

  - <span data-ttu-id="f760f-111">Процент вызовов, которые обходят сервер-посредник, который обходит сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="f760f-111">The percentage of calls that are calls whose media bypass the Mediation Server</span></span>

<span data-ttu-id="f760f-112">При планировании убедитесь, что после учета требований обработки для вызовов ТСОП и для аудио- и видеоконференций, которые не настроены для обхода сервера-посредника, а также для обработки, необходимой для взаимодействия по передаче сигналов для того количества вызовов в часы наибольшей нагрузки, которое должно поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="f760f-112">When planning, be sure to take into account the media processing requirements for PSTN calls and A/V conferences that are not configured for media bypass, as well as the processing needed to handle signaling interactions for the number of busy-hour calls that need to be supported.</span></span> <span data-ttu-id="f760f-113">Если ЦП недостаточно, необходимо развернуть изолированный пул серверов-посредников; шлюзы PSTN, IP-УАТС и SBCs должны быть разделены на подмножества, которые управляются совмещенными серверами-посредниками в одном пуле и изолированными серверами-посредниками в одном или нескольких автономных пулах.</span><span class="sxs-lookup"><span data-stu-id="f760f-113">If there is not enough CPU, then you must deploy a stand-alone pool of Mediation Servers; and PSTN gateways, IP-PBXs, and SBCs will need to be split into subsets that are controlled by the collocated Mediation Servers in one pool and the stand-alone Mediation Servers in one or more stand-alone pools.</span></span>

<span data-ttu-id="f760f-114">Если вы развернули шлюзы PSTN, IP-УАТС или пограничные контроллеры сеансов, которые не поддерживают правильные возможности взаимодействия с пулом серверов-посредников, в том числе следующие, они должны быть связаны с изолированным пулом, состоящим из один сервер-посредник:</span><span class="sxs-lookup"><span data-stu-id="f760f-114">If you deployed PSTN gateways, IP-PBXs, or Session Border Controllers (SBCs) that do not support the correct capabilities to interact with a pool of Mediation Servers, including the following, then they will need to be associated with a stand-alone pool consisting of a single Mediation Server:</span></span>

  - <span data-ttu-id="f760f-115">Выполнение балансировки нагрузки на DNS-сервере для серверов-посредников в пуле (или иным образом распределяет трафик по маршруту на все серверы-посредники в пуле)</span><span class="sxs-lookup"><span data-stu-id="f760f-115">Perform network layer Domain Name System (DNS) load balancing across Mediation Servers in a pool (or otherwise route traffic uniformly to all Mediation Servers in a pool)</span></span>

  - <span data-ttu-id="f760f-116">Принимать трафик от любого сервера-посредника в пуле</span><span class="sxs-lookup"><span data-stu-id="f760f-116">Accept traffic from any Mediation Server in a pool</span></span>

<span data-ttu-id="f760f-117">Можно использовать Microsoft Lync Server 2013, средство планирования для оценки того, может ли совмещенный сервер-посредник с пулом переднего плана обрабатывать нагрузку.</span><span class="sxs-lookup"><span data-stu-id="f760f-117">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether collocating the Mediation Server with your Front End pool can handle the load.</span></span> <span data-ttu-id="f760f-118">Если ваша среда не удовлетворяет данным требованиям, следует развернуть отдельный пул серверов-посредников.</span><span class="sxs-lookup"><span data-stu-id="f760f-118">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

</div>

<div>

## <a name="central-site-and-branch-site-considerations"></a><span data-ttu-id="f760f-119">Некоторые аспекты центрального сайта и сайта филиала</span><span class="sxs-lookup"><span data-stu-id="f760f-119">Central Site and Branch Site Considerations</span></span>

<span data-ttu-id="f760f-120">Серверы-посредники на центральном сайте могут использоваться для маршрутизации вызовов для IP-УАТС или шлюзов PSTN на сайтах филиалов.</span><span class="sxs-lookup"><span data-stu-id="f760f-120">Mediation Servers at the central site can be used to route calls for IP-PBXs or PSTN gateways at branch sites.</span></span> <span data-ttu-id="f760f-121">Однако при развертывании магистральных каналов SIP необходимо развернуть сервер-посредник на сайте, на котором завершается каждая магистраль.</span><span class="sxs-lookup"><span data-stu-id="f760f-121">If you deploy SIP trunks, however, you must deploy a Mediation Server at the site where each trunk terminates.</span></span> <span data-ttu-id="f760f-122">Наличие сервера-посредника на центральном сайте маршрутов для шлюза IP-УАТС или PSTN на сайте филиала не требует использования обхода сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="f760f-122">Having a Mediation Server at the central site route calls for an IP-PBX or PSTN gateway at a branch site does not require the use of media bypass.</span></span> <span data-ttu-id="f760f-123">Однако если есть возможность включить обход сервера-посредника, это рекомендуется сделать, так как это уменьшит задержку пути мультимедиа и в результате улучшит качество мультимедиа, поскольку путь мультимедиа больше не будет должен следовать пути передачи сигналов.</span><span class="sxs-lookup"><span data-stu-id="f760f-123">However, if you can enable media bypass, doing so will reduce media path latency and, consequently, result in improved media quality because the media path is no longer required to follow the signaling path.</span></span> <span data-ttu-id="f760f-124">Обход сервера-посредника также сократит нагрузку обработки в пуле.</span><span class="sxs-lookup"><span data-stu-id="f760f-124">Media bypass will also decrease the processing load on the pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f760f-125">Обход сервера-посредника не будет взаимодействовать с каждым шлюзом ТСОП, IP-УАТС и SBC.</span><span class="sxs-lookup"><span data-stu-id="f760f-125">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="f760f-126">Корпорация Майкрософт протестировала ряд шлюзов ТСОП и SBC с сертифицированными партнерами и выполнила некоторые тесты с IP-УАТС компании Cisco.</span><span class="sxs-lookup"><span data-stu-id="f760f-126">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="f760f-127">Обход сервера-посредника поддерживается только для продуктов и версий, перечисленных в общедоступной программе для взаимодействия с <A href="https://go.microsoft.com/fwlink/p/?linkid=268730">https://go.microsoft.com/fwlink/p/?LinkId=268730</A>единой системой обмена сообщениями — Lync Server по адресу.</span><span class="sxs-lookup"><span data-stu-id="f760f-127">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=268730">https://go.microsoft.com/fwlink/p/?LinkId=268730</A>.</span></span>



</div>

<span data-ttu-id="f760f-128">Если требуется устойчивость сайта филиала, устройство для обеспечения связи в филиалах или сочетание сервера переднего плана, сервера-посредника и шлюза должны быть развернуты на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="f760f-128">If branch site resiliency is required, a Survivable Branch Appliance or combination of a Front End Server, a Mediation Server, and a gateway must be deployed at the branch site.</span></span> <span data-ttu-id="f760f-129">(Допущение с обеспечением устойчивости сайта филиала состоит в том, что присутствие и конференц-связь не являются устойчивыми на сайте.) Рекомендации по планированию голосовой связи для сайта филиала приведены [в статье Планирование устойчивости голосовой связи для сайта филиала в Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span><span class="sxs-lookup"><span data-stu-id="f760f-129">(The assumption with branch site resiliency is that presence and conferencing are not resilient at the site.) For guidance on branch site planning for voice, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span></span>

<span data-ttu-id="f760f-130">При взаимодействии с IP-УАТС, если IP-УАТС неправильно поддерживает односторонние диалоговые окна и взаимодействия RFC 3960, можно отрезать первые несколько слов из приветствия для входящих вызовов из IP-УАТС в конечные точки Lync.</span><span class="sxs-lookup"><span data-stu-id="f760f-130">For interactions with an IP-PBX, if the IP-PBX does not correctly support early media interactions with multiple early dialogs and RFC 3960 interactions, there can be clipping of the first few words of the greeting for incoming calls from the IP-PBX to Lync endpoints.</span></span> <span data-ttu-id="f760f-131">Такое поведение может быть более серьезным, если сервер-посредник на центральном сайте выполняет маршрутизацию вызовов для IP-УАТС, в которой маршрут завершается на сайте филиала, так как для завершения передачи сигналов требуется больше времени.</span><span class="sxs-lookup"><span data-stu-id="f760f-131">This behavior can be more severe if a Mediation Server at a central site is routing calls for an IP-PBX where the route terminates at a branch site, because more time is needed for signaling to complete.</span></span> <span data-ttu-id="f760f-132">Если вы поработаете с этим поведением, развертывание сервера-посредника на сайте филиала — единственный способ сократить вырезку первых нескольких слов.</span><span class="sxs-lookup"><span data-stu-id="f760f-132">If you experience this behavior, deploying a Mediation Server at the branch site is the only way to reduce clipping of the first few words.</span></span>

<span data-ttu-id="f760f-133">Наконец, если на центральном сайте есть УАТС TDM, или если ваша IP-УАТС не устраняет потребность в шлюзе PSTN, необходимо развернуть шлюз на сервере-посреднике с подключением к подсистеме маршрутизации вызовов и УАТС.</span><span class="sxs-lookup"><span data-stu-id="f760f-133">Finally, if your central site has a TDM PBX, or if your IP-PBX does not eliminate the need for a PSTN gateway, then you must deploy a gateway on the call route connecting Mediation Server and the PBX.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f760f-134">Чтобы улучшить производительность автономного сервера-посредника, следует включить масштабирование на принимающей стороне (RSS) в сетевых адаптерах на этих серверах.</span><span class="sxs-lookup"><span data-stu-id="f760f-134">To improve the media performance of standalone Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on these servers.</span></span> <span data-ttu-id="f760f-135">RSS позволяет обрабатывать входящие пакеты параллельно несколькими процессорами на сервере.</span><span class="sxs-lookup"><span data-stu-id="f760f-135">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="f760f-136">Дополнительные сведения см. в <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?LinkId=268731</A>разделе "улучшение масштабирования на стороне Windows Server".</span><span class="sxs-lookup"><span data-stu-id="f760f-136">For details, see "Receive-Side Scaling Enhancements in Windows Server" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?LinkId=268731</A>.</span></span> <span data-ttu-id="f760f-137">Сведения о включении RSS см. в документации вашего сетевого адаптера.</span><span class="sxs-lookup"><span data-stu-id="f760f-137">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

