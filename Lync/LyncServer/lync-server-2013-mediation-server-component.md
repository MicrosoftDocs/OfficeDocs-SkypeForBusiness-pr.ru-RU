---
title: 'Lync Server 2013: компонент сервера-посредника'
description: 'Lync Server 2013: компонент сервера-посредника.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mediation Server component
ms:assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398399(v=OCS.15)
ms:contentKeyID: 48184239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08c11bff3ee7077d991204cda5a9885787c50ec2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568645"
---
# <a name="mediation-server-component-in-lync-server-2013"></a><span data-ttu-id="9566c-103">Компонент сервера-посредника в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9566c-103">Mediation Server component in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9566c-104">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="9566c-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="9566c-105">При развертывании рабочей нагрузки корпоративной голосовой связи необходимо развернуть сервер-посредник 2013, сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="9566c-105">You must deploy Lync Server 2013, Mediation Server if you deploy the Enterprise Voice workload.</span></span> <span data-ttu-id="9566c-106">В этом разделе описываются общие функциональные возможности, зависимости, базовые топологии и рекомендации по планированию.</span><span class="sxs-lookup"><span data-stu-id="9566c-106">This section describes basic functionality, dependencies, basic topologies, and planning guidelines.</span></span>

<span data-ttu-id="9566c-107">Сервер-посредник переводит сигнал и, в некоторых конфигурациях, мультимедиа между внутренней инфраструктурой Lync Server 2013, корпоративной голосовой связью и шлюзом телефонной сети общего пользования (PSTN) или магистральным протоколом SIP.</span><span class="sxs-lookup"><span data-stu-id="9566c-107">The Mediation Server translates signaling and, in some configurations, media between your internal Lync Server 2013, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="9566c-108">На стороне Lync Server 2013 сервер-посредник прослушивает один транспортный адрес взаимного TLS (MTLS).</span><span class="sxs-lookup"><span data-stu-id="9566c-108">On the Lync Server 2013 side, Mediation Server listens on a single mutual TLS (MTLS) transport address.</span></span> <span data-ttu-id="9566c-109">Сервер-посредник на стороне шлюза  прослушивает все соответствующие порты, связанные с магистралями, определенными в документе топологии.</span><span class="sxs-lookup"><span data-stu-id="9566c-109">On the gateway side, Mediation Server listens on all associated listening ports associated with trunks defined in the Topology document.</span></span> <span data-ttu-id="9566c-110">Все соответствующие шлюзы должны поддерживать TLS, но могут работать и через TCP.</span><span class="sxs-lookup"><span data-stu-id="9566c-110">All qualified gateways must support TLS, but can enable TCP as well.</span></span> <span data-ttu-id="9566c-111">TCP используется для шлюзов, которые не поддерживают TLS.</span><span class="sxs-lookup"><span data-stu-id="9566c-111">TCP is supported for gateways that do not support TLS.</span></span>

<span data-ttu-id="9566c-112">Если в вашей среде есть существующая УАТС, сервер-посредник обрабатывает вызовы между пользователями корпоративной голосовой связи и УАТС.</span><span class="sxs-lookup"><span data-stu-id="9566c-112">If you also have an existing Public Branch Exchange (PBX) in your environment, Mediation Server handles calls between Enterprise Voice users and the PBX.</span></span> <span data-ttu-id="9566c-113">Если УАТС является IP-УАТС, можно создать прямое SIP-соединение между УАТС и сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="9566c-113">If your PBX is an IP-PBX, you can create a direct SIP connection between the PBX and Mediation Server.</span></span> <span data-ttu-id="9566c-114">Если УАТС является УАТС (TDM), необходимо также развернуть шлюз PSTN между сервером-посредником и УАТС.</span><span class="sxs-lookup"><span data-stu-id="9566c-114">If your PBX is a Time Division Multiplex (TDM) PBX, you must also deploy a PSTN gateway between Mediation Server and the PBX.</span></span>

<span data-ttu-id="9566c-115">По умолчанию сервер-посредник размещен на сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="9566c-115">The Mediation Server is collocated with the Front End Server by default.</span></span> <span data-ttu-id="9566c-116">Сервер-посредник также может быть развернут в изолированном пуле по соображениям производительности или при развертывании магистральной магистрали SIP, в этом случае настоятельно рекомендуется использовать автономный пул.</span><span class="sxs-lookup"><span data-stu-id="9566c-116">The Mediation Server can also be deployed in a stand-alone pool for performance reasons, or if you deploy SIP trunking, in which case the stand-alone pool is strongly recommended.</span></span>

<span data-ttu-id="9566c-117">Если вы развертываете прямые подключения SIP к квалифицированному шлюзу ТСОП, поддерживающему обход сервера-посредника и балансировку нагрузки DNS, отдельный пул серверов-посредников не является необходимым.</span><span class="sxs-lookup"><span data-stu-id="9566c-117">If you deploy Direct SIP connections to a qualified PSTN gateway that supports media bypass and DNS load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="9566c-118">Изолированный пул серверов-посредников не требуется, так как квалифицированные шлюзы могут выполнять балансировку нагрузки на DNS для пула серверов-посредников и могут получать трафик от любого сервера-посредника в пуле.</span><span class="sxs-lookup"><span data-stu-id="9566c-118">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span>

<span data-ttu-id="9566c-119">Кроме того, рекомендуется размещать сервер-посредник в пуле переднего плана, когда вы развернули IP-PBXs или подключаться к пограничным контроллеру сеансов (SBC) поставщика услуг Интернет-телефонии, если выполняются следующие условия:</span><span class="sxs-lookup"><span data-stu-id="9566c-119">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider’s Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

  - <span data-ttu-id="9566c-120">IP-АТС или пограничный контроллер сеансов настроены на прием трафика от любого сервера-посредника в пуле и могут равномерно перенаправлять трафик на все серверы-посредники в пуле.</span><span class="sxs-lookup"><span data-stu-id="9566c-120">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

  - <span data-ttu-id="9566c-121">IP-УАТС не поддерживает обход сервера-посредника, но интерфейсный пул, на котором размещен сервер-посредник, может обрабатывать перекодировку голосовой связи для вызовов, к которым не применяется обход сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="9566c-121">The IP-PBX does not support media bypass, but the Front End pool that is hosting the Mediation Server can handle voice transcoding for calls to which media bypass does not apply.</span></span>

<span data-ttu-id="9566c-122">Вы можете использовать Microsoft Lync Server 2013, средство планирования, чтобы определить, может ли пул переднего плана, на котором будет размещаться сервер-посредник, обрабатывать нагрузку.</span><span class="sxs-lookup"><span data-stu-id="9566c-122">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="9566c-123">Если ваша среда не удовлетворяет данным требованиям, следует развернуть отдельный пул серверов-посредников.</span><span class="sxs-lookup"><span data-stu-id="9566c-123">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="9566c-124">Ниже приведены основные функции сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="9566c-124">The main functions of the Mediation Server are as follows:</span></span>

  - <span data-ttu-id="9566c-125">Шифрование и расшифровка SRTP на стороне Lync Server</span><span class="sxs-lookup"><span data-stu-id="9566c-125">Encrypting and decrypting SRTP on the Lync Server side</span></span>

  - <span data-ttu-id="9566c-126">Преобразование SIP через TCP (для шлюзов, которые не поддерживают TLS) в SIP через MTLS</span><span class="sxs-lookup"><span data-stu-id="9566c-126">Translating SIP over TCP (for gateways that do not support TLS) to SIP over mutual TLS</span></span>

  - <span data-ttu-id="9566c-127">Преобразование потоков мультимедиа между Lync Server и одноранговым узлом шлюза сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="9566c-127">Translating media streams between Lync Server and the gateway peer of the Mediation Server</span></span>

  - <span data-ttu-id="9566c-128">Подключение клиентов, расположенных за пределами сети, к внутренним компонентам ICE, которые позволяют мультимедиа обходить преобразование сетевых адресов (NAT) и брандмауэры</span><span class="sxs-lookup"><span data-stu-id="9566c-128">Connecting clients that are outside the network to internal ICE components, which enable media traversal of NAT and firewalls</span></span>

  - <span data-ttu-id="9566c-129">Выступает в качестве посредника для потоков звонков, которые не поддерживаются шлюзом, например, вызовы от удаленных рабочих процессов на корпоративном клиенте голосовой связи</span><span class="sxs-lookup"><span data-stu-id="9566c-129">Acting as an intermediary for call flows that a gateway does not support, such as calls from remote workers on an Enterprise Voice client</span></span>

  - <span data-ttu-id="9566c-130">Использование совместно с поставщиком услуг распределения каналов SIP в развертываниях, включающих в себя распределение каналов SIP, для обеспечения поддержки ТСОП, которая позволяет устранить потребность в шлюзе ТСОП</span><span class="sxs-lookup"><span data-stu-id="9566c-130">In deployments that include SIP trunking, working with the SIP trunking service provider to provide PSTN support, which eliminates the need for a PSTN gateway</span></span>

<span data-ttu-id="9566c-131">На следующем рисунке показаны протоколы передачи сигналов и мультимедиа, используемые сервером-посредником при взаимодействии с основным шлюзом PSTN и инфраструктурой корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="9566c-131">The following figure shows the signaling and media protocols that are used by the Mediation Server when communicating with a basic PSTN gateway and the Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="9566c-132">**Протоколы передачи сигналов и мультимедиа, используемые сервером-посредником**</span><span class="sxs-lookup"><span data-stu-id="9566c-132">**Signaling and media protocols used by the Mediation Server**</span></span>

<span data-ttu-id="9566c-133">![Схема протоколов сервера-посредника](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "Схема протоколов сервера-посредника")</span><span class="sxs-lookup"><span data-stu-id="9566c-133">![Mediation Server Protocols diagram](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "Mediation Server Protocols diagram")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9566c-134">При использовании протоколов TCP или RTP/RTCP (а не SRTP или СРТКП) в сети между шлюзом PSTN и сервером-посредником рекомендуется принять меры по обеспечению безопасности и конфиденциальности сети.</span><span class="sxs-lookup"><span data-stu-id="9566c-134">If you are using TCP or RTP/RTCP (instead of SRTP or SRTCP) on the network between the PSTN gateway and the Mediation Server, we recommend that you take measures to help ensure the security and privacy of the network.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9566c-135">Содержание</span><span class="sxs-lookup"><span data-stu-id="9566c-135">In This Section</span></span>

  - [<span data-ttu-id="9566c-136">Магистраль M:N в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9566c-136">M:N trunk in Lync Server 2013</span></span>](lync-server-2013-m-n-trunk.md)

  - [<span data-ttu-id="9566c-137">Контроль допуска звонков и сервер-посредник в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9566c-137">Call admission control and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-and-mediation-server.md)

  - [<span data-ttu-id="9566c-138">Улучшенный 9-1-1 (E9-1-1) и сервер-посредник в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9566c-138">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md)

  - [<span data-ttu-id="9566c-139">Обход сервера-посредника и сервер-посредник в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9566c-139">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)

  - [<span data-ttu-id="9566c-140">Компоненты и топологии для сервера-посредника в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9566c-140">Components and topologies for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-mediation-server.md)

  - [<span data-ttu-id="9566c-141">Рекомендации по развертыванию сервера-посредника в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9566c-141">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

