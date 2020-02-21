---
title: 'Lync Server 2013: компоненты и топологии для сервера-посредника'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Mediation Server
ms:assetid: 71397168-36c3-4d21-b8ef-db6a751634ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398537(v=OCS.15)
ms:contentKeyID: 48184487
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1b6c824da8eccaec0cb48450b0d81dddcc60f99
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187992"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="a6bc4-102">Компоненты и топологии для сервера-посредника в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6bc4-102">Components and topologies for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6bc4-103">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="a6bc4-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="a6bc4-104">В этом разделе описываются компоненты, от которых зависит сервер-посредник, и топологии, в которых может быть развернут сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="a6bc4-104">This topic describes the components on which the Mediation Server is dependent and the topologies in which the Mediation Server can be deployed</span></span>

<div>

## <a name="dependencies"></a><span data-ttu-id="a6bc4-105">Зависимости</span><span class="sxs-lookup"><span data-stu-id="a6bc4-105">Dependencies</span></span>

<span data-ttu-id="a6bc4-106">Сервер-посредник имеет следующие зависимости:</span><span class="sxs-lookup"><span data-stu-id="a6bc4-106">The Mediation Server has the following dependencies:</span></span>

  - <span data-ttu-id="a6bc4-107">**Регистратор.**</span><span class="sxs-lookup"><span data-stu-id="a6bc4-107">**Registrar.**</span></span> <span data-ttu-id="a6bc4-108">Обязательное.</span><span class="sxs-lookup"><span data-stu-id="a6bc4-108">Required.</span></span> <span data-ttu-id="a6bc4-109">Регистратор является следующим прыжком для сигнализации на сервере-посреднике взаимодействия с сетью Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6bc4-109">The Registrar is the next hop for signaling in the Mediation Server interactions with the Lync Server 2013 network.</span></span> <span data-ttu-id="a6bc4-110">Обратите внимание на то, что сервер-посредник можно разместить на сервере переднего плана вместе с регистратором, помимо того, чтобы устанавливаться в автономный пул, состоящий только из серверов-посредников.</span><span class="sxs-lookup"><span data-stu-id="a6bc4-110">Note that Mediation Server can be collocated on a Front End Server along with the Registrar, in addition to being installed in a stand-alone pool consisting only of Mediation Servers.</span></span> <span data-ttu-id="a6bc4-111">Регистратор размещается совместно с сервером-посредником и шлюзом PSTN на устройстве для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="a6bc4-111">The Registrar is collocated with a Mediation Server and PSTN gateway on a Survivable Branch Appliance.</span></span>

  - <span data-ttu-id="a6bc4-112">**Сервер мониторинга.**</span><span class="sxs-lookup"><span data-stu-id="a6bc4-112">**Monitoring Server.**</span></span> <span data-ttu-id="a6bc4-113">Необязателен, но настоятельно рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="a6bc4-113">Optional but highly recommended.</span></span> <span data-ttu-id="a6bc4-114">Сервер мониторинга позволяет серверу-посреднику записывать метрики качества, связанные с сеансами мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="a6bc4-114">The Monitoring Server allows the Mediation Server to record quality metrics associated with its media sessions.</span></span>

  - <span data-ttu-id="a6bc4-115">**Пограничный сервер.**</span><span class="sxs-lookup"><span data-stu-id="a6bc4-115">**Edge Server.**</span></span> <span data-ttu-id="a6bc4-116">Требуется для поддержки внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="a6bc4-116">Required for external user support.</span></span> <span data-ttu-id="a6bc4-117">Пограничный сервер позволяет серверу-посреднику взаимодействовать с пользователями, расположенными за NAT или брандмауэром.</span><span class="sxs-lookup"><span data-stu-id="a6bc4-117">The Edge Server allows the Mediation Server to interact with users who are located behind a NAT or firewall.</span></span>

</div>

<div>

## <a name="topologies"></a><span data-ttu-id="a6bc4-118">Топологии</span><span class="sxs-lookup"><span data-stu-id="a6bc4-118">Topologies</span></span>

<span data-ttu-id="a6bc4-119">Сервер Lync Server 2013, сервер-посредник по умолчанию выровнен с помощью экземпляра регистратора на сервере Standard Edition, интерфейсном пуле или устройстве для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="a6bc4-119">The Lync Server 2013, Mediation Server is by default collocated with an instance of the Registrar on a Standard Edition server, a Front End pool, or Survivable Branch Appliance.</span></span> <span data-ttu-id="a6bc4-120">Все серверы-посредники в пуле переднего плана должны быть настроены одинаково.</span><span class="sxs-lookup"><span data-stu-id="a6bc4-120">All Mediation Servers in a Front End pool must be configured identically.</span></span>

<span data-ttu-id="a6bc4-121">Если производительность является неисправностью, может быть предпочтительным развертывание одного или нескольких серверов-посредников в выделенном изолированном пуле.</span><span class="sxs-lookup"><span data-stu-id="a6bc4-121">Where performance is an issue, it may be preferable to deploy one or more Mediation Servers in a dedicated stand-alone pool.</span></span> <span data-ttu-id="a6bc4-122">Если вы развертываете магистраль SIP, рекомендуем развернуть пул изолированных серверов-посредников.</span><span class="sxs-lookup"><span data-stu-id="a6bc4-122">Or, if you are deploying SIP trunking, we recommend that you deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="a6bc4-123">Если вы развертываете прямые подключения SIP к квалифицированному шлюзу ТСОП, поддерживающему обход сервера-посредника и балансировку нагрузки DNS, отдельный пул серверов-посредников не является необходимым.</span><span class="sxs-lookup"><span data-stu-id="a6bc4-123">If you deploy Direct SIP connections to a qualified PSTN gateway that supports media bypass and DNS load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="a6bc4-124">Изолированный пул серверов-посредников не требуется, так как квалифицированные шлюзы могут выполнять балансировку нагрузки на DNS для пула серверов-посредников и могут получать трафик от любого сервера-посредника в пуле.</span><span class="sxs-lookup"><span data-stu-id="a6bc4-124">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span>

<span data-ttu-id="a6bc4-125">Кроме того, рекомендуется размещать сервер-посредник в пуле переднего плана, если вы развернули IP-УАТС или подключаются к пограничным контроллеру сеансов (SBC) поставщика услуг телефонной сети (SBC), пока выполняются следующие условия:</span><span class="sxs-lookup"><span data-stu-id="a6bc4-125">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider’s Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

  - <span data-ttu-id="a6bc4-126">IP-АТС или пограничный контроллер сеансов настроены на прием трафика от любого сервера-посредника в пуле и могут равномерно перенаправлять трафик на все серверы-посредники в пуле.</span><span class="sxs-lookup"><span data-stu-id="a6bc4-126">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

  - <span data-ttu-id="a6bc4-127">IP-УАТС не поддерживает обход сервера-посредника, но интерфейсный пул, на котором размещен сервер-посредник, может обрабатывать перекодировку голосовой связи для вызовов, к которым не применяется обход сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="a6bc4-127">The IP-PBX does not support media bypass, but the Front End pool that is hosting the Mediation Server can handle voice transcoding for calls to which media bypass does not apply.</span></span>

<span data-ttu-id="a6bc4-128">Вы можете использовать Microsoft Lync Server 2013, средство планирования, чтобы определить, может ли пул переднего плана, на котором будет размещаться сервер-посредник, обрабатывать нагрузку.</span><span class="sxs-lookup"><span data-stu-id="a6bc4-128">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="a6bc4-129">Если ваша среда не удовлетворяет данным требованиям, следует развернуть отдельный пул серверов-посредников.</span><span class="sxs-lookup"><span data-stu-id="a6bc4-129">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="a6bc4-130">Сведения о топологии, которую необходимо развернуть, приведены [в статье рекомендации по развертыванию сервера-посредника в Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="a6bc4-130">For details about which topology to deploy, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="a6bc4-131">На следующем рисунке показана простая топология, состоящая из двух сайтов, соединенных через глобальную сеть.</span><span class="sxs-lookup"><span data-stu-id="a6bc4-131">The following figure shows a simple topology consisting of two sites connected by a WAN link.</span></span> <span data-ttu-id="a6bc4-132">Сервер-посредник размещается вместе с регистратором в интерфейсном пуле на сайте 1.</span><span class="sxs-lookup"><span data-stu-id="a6bc4-132">Mediation Server is collocated with the Registrar on a Front End pool at Site 1.</span></span> <span data-ttu-id="a6bc4-133">Серверы-посредники на сайте 1 управляют шлюзом PSTN на сайте 1 и шлюзом на сайте 2.</span><span class="sxs-lookup"><span data-stu-id="a6bc4-133">The Mediation Servers at Site 1 controls both the PSTN gateway at Site 1 and the gateway at Site 2.</span></span> <span data-ttu-id="a6bc4-134">В этой топологии обход сервера-посредника включен глобально, чтобы использовать сведения о сайте и регионе, и чтобы магистрали к каждому шлюзу ТСОП (GW1 и GW2) поддерживали обход.</span><span class="sxs-lookup"><span data-stu-id="a6bc4-134">In this topology, media bypass is enabled globally to use site and region information, and the trunks to each PSTN gateway (GW1 and GW2) have bypass enabled.</span></span>

<span data-ttu-id="a6bc4-135">**Пример сайтов, подключенных через глобальную сеть с сервером-посредником на сайте 1 и шлюзом ТСОП на сайте 2**</span><span class="sxs-lookup"><span data-stu-id="a6bc4-135">**Example of sites connected by a WAN link with a Mediation Server at Site 1 and a PSTN gateway at Site 2**</span></span>

<span data-ttu-id="a6bc4-136">![Топология голосовой связи с шлюзом WAN Server-посредника](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Топология голосовой связи с шлюзом WAN Server-посредника")</span><span class="sxs-lookup"><span data-stu-id="a6bc4-136">![Voice Topology with Mediation Server WAN Gateway](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Voice Topology with Mediation Server WAN Gateway")</span></span>

<span data-ttu-id="a6bc4-137">На следующем рисунке показана простая топология, в которой сервер-посредник размещен с регистратором в интерфейсном пуле на сайте 1 и имеет прямое SIP-соединение с IP-УАТС на сайте 1.</span><span class="sxs-lookup"><span data-stu-id="a6bc4-137">The next figure shows a simple topology where the Mediation Server is collocated with the Registrar on Front End pool at Site 1 and has a Direct SIP connection to the IP-PBX at Site 1.</span></span> <span data-ttu-id="a6bc4-138">На этом рисунке сервер-посредник также управляет шлюзом PSTN на сайте 2.</span><span class="sxs-lookup"><span data-stu-id="a6bc4-138">In this figure, the Mediation Server also controls a PSTN gateway at Site 2.</span></span> <span data-ttu-id="a6bc4-139">Предположим, что пользователи Lync существуют на сайтах 1 и 2.</span><span class="sxs-lookup"><span data-stu-id="a6bc4-139">Assume that Lync users exist at both Sites 1 and 2.</span></span> <span data-ttu-id="a6bc4-140">Кроме того, предположим, что у IP-УАТС есть связанный с ним обработчик мультимедиа, который должен проходить все, что происходит из конечных точек Lync, прежде чем отправлять их конечным точкам, управляемым IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="a6bc4-140">Also assume that the IP-PBX has an associated media processor that must be traversed by all media originating from Lync endpoints before being sent to media endpoints controlled by the IP-PBX.</span></span> <span data-ttu-id="a6bc4-141">В этой топологии обход сервера-посредника включен глобально, чтобы использовать сведения сайта и региона, и чтобы магистрали к PBX и шлюзу ТСОП поддерживали обход сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="a6bc4-141">In this topology, media bypass is enabled globally to use site and region information, and the trunks to the PBX and PSTN gateway have media bypass enabled.</span></span>

<span data-ttu-id="a6bc4-142">**Пример сайтов, подключенных через глобальную сеть с сервером-посредником на сайте 1 и PBX на сайте 2**</span><span class="sxs-lookup"><span data-stu-id="a6bc4-142">**Example of sites connected by a WAN link with a Mediation Server at Site 1 and a PBX at Site 2**</span></span>

<span data-ttu-id="a6bc4-143">![WAN-УАТС сервера-посредника голосовой топологии](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "WAN-УАТС сервера-посредника голосовой топологии")</span><span class="sxs-lookup"><span data-stu-id="a6bc4-143">![Voice Topology Mediation Server WAN PBX](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "Voice Topology Mediation Server WAN PBX")</span></span>

<span data-ttu-id="a6bc4-144">Сведения о планировании топологий УАТС приведены в статье [рекомендации по развертыванию сервера-посредника в Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) и [функции прямого развертывания SIP в Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).</span><span class="sxs-lookup"><span data-stu-id="a6bc4-144">For details about planning for PBX topologies, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) and [Direct SIP deployment options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).</span></span>

<span data-ttu-id="a6bc4-145">На последней фигуре в этом разделе показана топология, в которой сервер-посредник подключен к SBC поставщика услуг Интернет-телефонии.</span><span class="sxs-lookup"><span data-stu-id="a6bc4-145">The last figure in this topic shows a topology where the Mediation Server is connected to the SBC of an Internet Telephony Service Provider.</span></span> <span data-ttu-id="a6bc4-146">Подробные сведения о топологиях магистральных топологий SIP приведены в статье распределение [каналов SIP в Lync Server 2013](lync-server-2013-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="a6bc4-146">For details about SIP trunk topologies, see [SIP trunking in Lync Server 2013](lync-server-2013-sip-trunking.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

