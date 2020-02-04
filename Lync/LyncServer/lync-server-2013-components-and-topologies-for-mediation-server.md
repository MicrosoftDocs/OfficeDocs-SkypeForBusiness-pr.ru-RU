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
ms.openlocfilehash: 62516645266f67b7be61154b45afd00107ec3814
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742619"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="b485f-102">Компоненты и топологии для сервера-посредника в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b485f-102">Components and topologies for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b485f-103">_**Тема последнего изменения:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="b485f-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="b485f-104">В этой статье описаны компоненты, от которых зависит сервер исправлений, и топологии, в которой можно разворачивать сервер обновлений.</span><span class="sxs-lookup"><span data-stu-id="b485f-104">This topic describes the components on which the Mediation Server is dependent and the topologies in which the Mediation Server can be deployed</span></span>

<div>

## <a name="dependencies"></a><span data-ttu-id="b485f-105">Зависимости</span><span class="sxs-lookup"><span data-stu-id="b485f-105">Dependencies</span></span>

<span data-ttu-id="b485f-106">Сервер исправлений имеет следующие зависимости:</span><span class="sxs-lookup"><span data-stu-id="b485f-106">The Mediation Server has the following dependencies:</span></span>

  - <span data-ttu-id="b485f-107">**Регистратора.**</span><span class="sxs-lookup"><span data-stu-id="b485f-107">**Registrar.**</span></span> <span data-ttu-id="b485f-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="b485f-108">Required.</span></span> <span data-ttu-id="b485f-109">Регистратор является следующим прыжком для передачи сигналов в сети Lync Server 2013 с помощью взаимодействия с сервером.</span><span class="sxs-lookup"><span data-stu-id="b485f-109">The Registrar is the next hop for signaling in the Mediation Server interactions with the Lync Server 2013 network.</span></span> <span data-ttu-id="b485f-110">Обратите внимание на то, что сервер-посредник может быть размещен на сервере переднего плана вместе с регистратором, а также в дополнение к установке в отдельном пуле, состоящем только из серверов-исправлений.</span><span class="sxs-lookup"><span data-stu-id="b485f-110">Note that Mediation Server can be collocated on a Front End Server along with the Registrar, in addition to being installed in a stand-alone pool consisting only of Mediation Servers.</span></span> <span data-ttu-id="b485f-111">Регистратор размещается на сервере-посреднике и шлюзе PSTN на работающем устройстве филиала.</span><span class="sxs-lookup"><span data-stu-id="b485f-111">The Registrar is collocated with a Mediation Server and PSTN gateway on a Survivable Branch Appliance.</span></span>

  - <span data-ttu-id="b485f-112">**Сервер мониторинга.**</span><span class="sxs-lookup"><span data-stu-id="b485f-112">**Monitoring Server.**</span></span> <span data-ttu-id="b485f-113">Это необязательно, но настоятельно рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="b485f-113">Optional but highly recommended.</span></span> <span data-ttu-id="b485f-114">Сервер мониторинга позволяет записывать метрики качества, связанные с его сеансами мультимедиа, на сервере обновлений.</span><span class="sxs-lookup"><span data-stu-id="b485f-114">The Monitoring Server allows the Mediation Server to record quality metrics associated with its media sessions.</span></span>

  - <span data-ttu-id="b485f-115">**Пограничный сервер.**</span><span class="sxs-lookup"><span data-stu-id="b485f-115">**Edge Server.**</span></span> <span data-ttu-id="b485f-116">Требуется для поддержки внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="b485f-116">Required for external user support.</span></span> <span data-ttu-id="b485f-117">Пограничный сервер позволяет серверу-посреднику взаимодействовать с пользователями, которые находятся за пределами NAT или брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="b485f-117">The Edge Server allows the Mediation Server to interact with users who are located behind a NAT or firewall.</span></span>

</div>

<div>

## <a name="topologies"></a><span data-ttu-id="b485f-118">Топологий</span><span class="sxs-lookup"><span data-stu-id="b485f-118">Topologies</span></span>

<span data-ttu-id="b485f-119">Lync Server 2013, сервер-посредник по умолчанию выровнен с помощью экземпляра регистратора на сервере Standard Edition, пуле интерфейсов или работающем устройстве филиала.</span><span class="sxs-lookup"><span data-stu-id="b485f-119">The Lync Server 2013, Mediation Server is by default collocated with an instance of the Registrar on a Standard Edition server, a Front End pool, or Survivable Branch Appliance.</span></span> <span data-ttu-id="b485f-120">Все серверы-посредники в пуле переднего плана должны быть настроены одинаково.</span><span class="sxs-lookup"><span data-stu-id="b485f-120">All Mediation Servers in a Front End pool must be configured identically.</span></span>

<span data-ttu-id="b485f-121">При возникновении проблем с производительностью может быть предпочтительнее развернуть один или несколько серверов-исправлений в выделенном отдельном пуле.</span><span class="sxs-lookup"><span data-stu-id="b485f-121">Where performance is an issue, it may be preferable to deploy one or more Mediation Servers in a dedicated stand-alone pool.</span></span> <span data-ttu-id="b485f-122">Кроме того, при развертывании магистральной магистрали SIP рекомендуется развернуть пул серверов изолированных исправлений.</span><span class="sxs-lookup"><span data-stu-id="b485f-122">Or, if you are deploying SIP trunking, we recommend that you deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="b485f-123">Если вы разворачиваете прямые подключения по протоколу SIP к квалифицированному шлюзу PSTN, поддерживающему обход ресурсов мультимедиа и балансировку нагрузки DNS, то не нужно использовать изолированный пул серверов для исправления.</span><span class="sxs-lookup"><span data-stu-id="b485f-123">If you deploy Direct SIP connections to a qualified PSTN gateway that supports media bypass and DNS load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="b485f-124">Пул серверов автономных исправлений не нужен, так как квалифицированные шлюзы могут выполнять балансировку нагрузки DNS для пула серверов-посредников, и они могут принимать трафик от любого сервера обновлений в пуле.</span><span class="sxs-lookup"><span data-stu-id="b485f-124">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span>

<span data-ttu-id="b485f-125">Кроме того, мы рекомендуем вам разгруппировать сервер-посредник в пуле переднего плана, если вы разработали IP-АТС или подключаться к контроллеру границ сеанса поставщика услуг телефонной сети Интернет (SBC), если выполняются следующие условия:</span><span class="sxs-lookup"><span data-stu-id="b485f-125">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider’s Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

  - <span data-ttu-id="b485f-126">IP-УАТС или SBC настроен для приема трафика от любого сервера-посредника в пуле и может маршрутизировать трафик одинаково для всех серверов-посредников в пуле.</span><span class="sxs-lookup"><span data-stu-id="b485f-126">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

  - <span data-ttu-id="b485f-127">IP-УАТС не поддерживает обход мультимедиа, но интерфейсный пул, на котором размещен сервер-посредник, может обрабатывать передачу голосовой почты для звонков, к которым не применяется обход мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="b485f-127">The IP-PBX does not support media bypass, but the Front End pool that is hosting the Mediation Server can handle voice transcoding for calls to which media bypass does not apply.</span></span>

<span data-ttu-id="b485f-128">Вы можете воспользоваться средством Microsoft Lync Server 2013, планированием, чтобы определить, может ли пул переднего плана, где должен быть размещен сервер обновлений, обрабатывать загрузку.</span><span class="sxs-lookup"><span data-stu-id="b485f-128">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="b485f-129">Если среда не отвечает этим требованиям, необходимо развернуть пул серверов изолированных исправлений.</span><span class="sxs-lookup"><span data-stu-id="b485f-129">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="b485f-130">Сведения о том, какая топология развертывается, приведены [в разделе рекомендации по развертыванию сервера обновлений в Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="b485f-130">For details about which topology to deploy, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="b485f-131">На следующем рисунке показана простая топология, состоящая из двух сайтов, соединенных через WAN-канал.</span><span class="sxs-lookup"><span data-stu-id="b485f-131">The following figure shows a simple topology consisting of two sites connected by a WAN link.</span></span> <span data-ttu-id="b485f-132">Сервер-посредник будет размещен с помощью регистратора в пуле переднего плана на сайте 1.</span><span class="sxs-lookup"><span data-stu-id="b485f-132">Mediation Server is collocated with the Registrar on a Front End pool at Site 1.</span></span> <span data-ttu-id="b485f-133">Серверы обновлений на сайте 1 выявляются и шлюзом КТСОП на сайте 1, и шлюзом на сайте 2.</span><span class="sxs-lookup"><span data-stu-id="b485f-133">The Mediation Servers at Site 1 controls both the PSTN gateway at Site 1 and the gateway at Site 2.</span></span> <span data-ttu-id="b485f-134">В этой топологии обход сервера-посредника включен глобально, чтобы использовать сведения о сайте и регионе и чтобы магистрали к каждому шлюзу ТСОП (GW1 и GW2) поддерживали обход.</span><span class="sxs-lookup"><span data-stu-id="b485f-134">In this topology, media bypass is enabled globally to use site and region information, and the trunks to each PSTN gateway (GW1 and GW2) have bypass enabled.</span></span>

<span data-ttu-id="b485f-135">**Пример сайтов, подключенных через WAN-канал с сервером-посредником на сайте 1 и шлюзом ТСОП на сайте 2**</span><span class="sxs-lookup"><span data-stu-id="b485f-135">**Example of sites connected by a WAN link with a Mediation Server at Site 1 and a PSTN gateway at Site 2**</span></span>

<span data-ttu-id="b485f-136">![Голосовая топология с сервером-посредником и шлюзом глобальной сети](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Голосовая топология с сервером-посредником и шлюзом глобальной сети")</span><span class="sxs-lookup"><span data-stu-id="b485f-136">![Voice Topology with Mediation Server WAN Gateway](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Voice Topology with Mediation Server WAN Gateway")</span></span>

<span data-ttu-id="b485f-137">На следующем рисунке показана простая топология, в которой сервер-посредник размещен с помощью регистратора в пуле переднего плана на сайте 1 и имеет прямое соединение SIP с IP-УАТС на сайте 1.</span><span class="sxs-lookup"><span data-stu-id="b485f-137">The next figure shows a simple topology where the Mediation Server is collocated with the Registrar on Front End pool at Site 1 and has a Direct SIP connection to the IP-PBX at Site 1.</span></span> <span data-ttu-id="b485f-138">На этом рисунке сервер-посредник также управляет шлюзом PSTN на сайте 2.</span><span class="sxs-lookup"><span data-stu-id="b485f-138">In this figure, the Mediation Server also controls a PSTN gateway at Site 2.</span></span> <span data-ttu-id="b485f-139">Предположим, что пользователи Lync существуют на сайтах 1 и 2.</span><span class="sxs-lookup"><span data-stu-id="b485f-139">Assume that Lync users exist at both Sites 1 and 2.</span></span> <span data-ttu-id="b485f-140">Кроме того, предположим, что у IP-УАТС есть процессор мультимедиа, который должен пройти все носители из конечных точек Lync, прежде чем они будут отправлены в конечные точки мультимедиа, управляемые IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="b485f-140">Also assume that the IP-PBX has an associated media processor that must be traversed by all media originating from Lync endpoints before being sent to media endpoints controlled by the IP-PBX.</span></span> <span data-ttu-id="b485f-141">В этой топологии обход сервера-посредника включен глобально, чтобы использовать сведения сайта и региона и чтобы магистрали к PBX и шлюзу ТСОП поддерживали обход сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="b485f-141">In this topology, media bypass is enabled globally to use site and region information, and the trunks to the PBX and PSTN gateway have media bypass enabled.</span></span>

<span data-ttu-id="b485f-142">**Пример сайтов, подключенных через WAN-канал с сервером-посредником на сайте 1 и УАТС на сайте 2**</span><span class="sxs-lookup"><span data-stu-id="b485f-142">**Example of sites connected by a WAN link with a Mediation Server at Site 1 and a PBX at Site 2**</span></span>

<span data-ttu-id="b485f-143">![Голосовая топология с сервером-посредником и УАТС, подключенной к глобальной сети](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "Голосовая топология с сервером-посредником и УАТС, подключенной к глобальной сети")</span><span class="sxs-lookup"><span data-stu-id="b485f-143">![Voice Topology Mediation Server WAN PBX](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "Voice Topology Mediation Server WAN PBX")</span></span>

<span data-ttu-id="b485f-144">Дополнительные сведения о планировании топологий АТС можно найти [в разделе рекомендации по развертыванию сервера обновлений в Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) и [Параметры развертывания Direct SIP в Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).</span><span class="sxs-lookup"><span data-stu-id="b485f-144">For details about planning for PBX topologies, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) and [Direct SIP deployment options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).</span></span>

<span data-ttu-id="b485f-145">На последней фигуре в этой статье показана топология, в которой сервер-посредник подключен к SBC поставщика услуг телефонной связи через Интернет.</span><span class="sxs-lookup"><span data-stu-id="b485f-145">The last figure in this topic shows a topology where the Mediation Server is connected to the SBC of an Internet Telephony Service Provider.</span></span> <span data-ttu-id="b485f-146">Дополнительные сведения о топологиях магистральных модулей SIP можно найти [в разделе магистральные линии SIP в Lync Server 2013](lync-server-2013-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="b485f-146">For details about SIP trunk topologies, see [SIP trunking in Lync Server 2013](lync-server-2013-sip-trunking.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

