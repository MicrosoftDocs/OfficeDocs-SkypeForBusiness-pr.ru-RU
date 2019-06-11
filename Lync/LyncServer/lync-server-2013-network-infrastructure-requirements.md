---
title: Требования к сетевой инфраструктуре Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Network infrastructure requirements
ms:assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425841(v=OCS.15)
ms:contentKeyID: 48183804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc1f74705469bf3a024d84848942eae972e0a629
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826530"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="8e0ab-102">Требования к инфраструктуре сети для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e0ab-102">Network infrastructure requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e0ab-103">_**Тема последнего изменения:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="8e0ab-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="8e0ab-104">Сетевая плата каждого сервера в топологии Lync Server 2013 должна поддерживать по крайней мере 1 гигабит в секунду (Гбит/с).</span><span class="sxs-lookup"><span data-stu-id="8e0ab-104">The network adapter card of each server in the Lync Server 2013 topology must support at least 1 gigabit per second (Gbps).</span></span> <span data-ttu-id="8e0ab-105">В общем случае следует подключить все роли сервера в пределах топологии Lync Server, используя небольшую задержку и локальную сеть с высокой пропускной способностью (ЛВС).</span><span class="sxs-lookup"><span data-stu-id="8e0ab-105">In general, you should connect all server roles within the Lync Server topology using a low latency and high bandwidth local area network (LAN).</span></span> <span data-ttu-id="8e0ab-106">Размер локальной сети зависит от размера топологии.</span><span class="sxs-lookup"><span data-stu-id="8e0ab-106">The size of the LAN is dependent on the size of the topology:</span></span>

  - <span data-ttu-id="8e0ab-107">В стандартных топологиях выпуска серверы должны находиться в сети, поддерживающей 1 Гбит/с Ethernet или аналогичный.</span><span class="sxs-lookup"><span data-stu-id="8e0ab-107">In Standard Edition topologies, servers should be in a network that supports 1 Gbps Ethernet or equivalent.</span></span>

  - <span data-ttu-id="8e0ab-108">В топологиях пула переднего плана большинство серверов должны находиться в сети, поддерживающей более 1 Гбит/с, особенно при поддержке конференций аудио-и видеосвязи и общего доступа к приложениям.</span><span class="sxs-lookup"><span data-stu-id="8e0ab-108">In Front End pool topologies, most servers should be in a network that supports more than 1 Gbps, especially when supporting audio/video (A/V) conferencing and application sharing.</span></span>

<span data-ttu-id="8e0ab-109">Для интеграции с телефонной сетью общего пользования (ТСОП) можно использовать линии T1/E1 или распределение каналов SIP.</span><span class="sxs-lookup"><span data-stu-id="8e0ab-109">For public switched telephone network (PSTN) integration, you can integrate by using either T1/E1 lines or SIP trunking.</span></span>

<div>

## <a name="audiovideo-network-requirements"></a><span data-ttu-id="8e0ab-110">Требования к аудио-и видеосети</span><span class="sxs-lookup"><span data-stu-id="8e0ab-110">Audio/Video Network Requirements</span></span>

<span data-ttu-id="8e0ab-111">Сетевые требования для аудио-и видеосвязи (A/V) в развертывании Lync Server включают следующее:</span><span class="sxs-lookup"><span data-stu-id="8e0ab-111">Network requirements for audio/video (A/V) in a Lync Server deployment include the following:</span></span>

  - <span data-ttu-id="8e0ab-112">При развертывании одного пограничного сервера или пула Edge с помощью балансировки нагрузки DNS вы можете настроить внешний брандмауэр как NAT.</span><span class="sxs-lookup"><span data-stu-id="8e0ab-112">If you are deploying a single Edge Server or an Edge pool using DNS load balancing, you can configure the external firewall as a NAT.</span></span> <span data-ttu-id="8e0ab-113">Внутренний межсетевой экран нельзя настроить как NAT.</span><span class="sxs-lookup"><span data-stu-id="8e0ab-113">You cannot configure the internal firewall as a NAT.</span></span> <span data-ttu-id="8e0ab-114">Подробнее об этих требованиях можно узнать в статьях [Определение внешних брандмауэров и требований к портам для Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="8e0ab-114">For details about these requirements, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) in the Planning documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8e0ab-115">Если у вас есть пул EDGE и вы используете аппаратную подсистему балансировки нагрузки, вы должны использовать общедоступные IP-адреса на каждом пограничном сервере и не можете использовать NAT для серверов или пула на устройстве NAT (например, брандмауэре или другом устройстве-инфраструктуре, которое будет NAT Инбау ND или исходящий трафик).</span><span class="sxs-lookup"><span data-stu-id="8e0ab-115">If you have an Edge pool and are using a hardware load balancer, you must use public IP addresses on each of the Edge Servers and you cannot use NAT for the servers or the pool at your NAT device (for example, the firewall, or other infrastructure device that would NAT inbound or outbound traffic).</span></span> <span data-ttu-id="8e0ab-116">Подробные сведения можно найти <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">в разделе "Сводная информация о порте" с масштабированием подсистемы балансировки нагрузки для оборудования в Lync Server 2013</A> в документации "планирование для внешних пользователей".</span><span class="sxs-lookup"><span data-stu-id="8e0ab-116">For details, see <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</A> in the Planning for External User Access documentation.</span></span>

    
    </div>

  - <span data-ttu-id="8e0ab-117">Если в вашей организации используется инфраструктура качества обслуживания (QoS), подсистема передачи мультимедиа настроена на работу в этой существующей инфраструктуре.</span><span class="sxs-lookup"><span data-stu-id="8e0ab-117">If your organization uses a Quality of Service (QoS) infrastructure, the media subsystem is designed to work within this existing infrastructure.</span></span>

  - <span data-ttu-id="8e0ab-118">Если вы используете протоколы IPsec, мы рекомендуем отключить их для диапазона портов, который используется для аудио- и видеотрафика.</span><span class="sxs-lookup"><span data-stu-id="8e0ab-118">If you use Internet Protocol security (IPsec), we recommend disabling IPsec over the port ranges used for A/V traffic.</span></span> <span data-ttu-id="8e0ab-119">Дополнительные сведения можно найти [в разделе исключения IPSec в Lync Server 2013](lync-server-2013-ipsec-exceptions.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="8e0ab-119">For details, see [IPsec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) in the Planning documentation.</span></span>

<span data-ttu-id="8e0ab-120">Чтобы обеспечить оптимальное качество мультимедиа, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="8e0ab-120">To ensure optimal media quality, do the following:</span></span>

  - <span data-ttu-id="8e0ab-121">Подготовьте сетевые ссылки для поддержки пропускной способности 65 килобит в секунду (кбит/с) на поток аудио и 500 Кбит/с для каждого видеопотока, если включено в периоды пикового использования.</span><span class="sxs-lookup"><span data-stu-id="8e0ab-121">Provision your network links to support throughput of 65 kilobits per second (Kbps) per audio stream and 500 Kbps per video stream, if enabled, during peak usage periods.</span></span> <span data-ttu-id="8e0ab-122">Двунаправленный звуковой или видеосеанс состоит из двух потоков.</span><span class="sxs-lookup"><span data-stu-id="8e0ab-122">A bidirectional audio or video session consists of two streams.</span></span>

  - <span data-ttu-id="8e0ab-123">Для решения непредвиденных скачков трафика выше этого уровня и более длительного использования с течением времени конечные точки мультимедиа сервера Lync Server могут адаптироваться к различным условиям сети и поддерживать загрузку в три раза больше, чем пропускная способность (например, предыдущий абзац) для аудио-и видеосвязи. сохранение приемлемого качества.</span><span class="sxs-lookup"><span data-stu-id="8e0ab-123">To cope with unexpected spikes in traffic above this level and increased usage over time, Lync Server media endpoints can adapt to varying network conditions and support loads of three times the throughput (see previous paragraph) for audio and video while still retaining acceptable quality.</span></span> <span data-ttu-id="8e0ab-124">Однако не следует рассчитывать на то, что эта адаптируемость будет поддерживать подготовную сеть.</span><span class="sxs-lookup"><span data-stu-id="8e0ab-124">However, do not assume that this adaptability will support an under-provisioned network.</span></span> <span data-ttu-id="8e0ab-125">В неподготовленной сети способность конечных точек мультимедиа-сервера Lync Server динамически обрабатывать различные сетевые условия (например, временная потеря пакетов) уменьшается.</span><span class="sxs-lookup"><span data-stu-id="8e0ab-125">In an under-provisioned network, the ability of the Lync Server media endpoints to dynamically deal with varying network conditions (for example, temporary high packet loss) is reduced.</span></span>

  - <span data-ttu-id="8e0ab-126">Для сетевых ссылок, в которых подготовка является чрезвычайно дорогостоящей и сложной, возможно, потребуется подготовиться для более узкого объема трафика.</span><span class="sxs-lookup"><span data-stu-id="8e0ab-126">For network links where provisioning is extremely costly and difficult, you may need to consider provisioning for a lower volume of traffic.</span></span> <span data-ttu-id="8e0ab-127">В этом сценарии для эластичности конечных точек мультимедиа сервера Lync Server уменьшается разница между объемом трафика и уровнем пиковой нагрузки за счет снижения качества голоса.</span><span class="sxs-lookup"><span data-stu-id="8e0ab-127">In this scenario, let the elasticity of the Lync Server media endpoints absorb the difference between the traffic volume and the peak traffic level, at the cost of some reduction in the voice quality.</span></span> <span data-ttu-id="8e0ab-128">Кроме того, существует снижение запаса, которое можно использовать в других случаях для снижения нагрузки внезапного пикового трафика.</span><span class="sxs-lookup"><span data-stu-id="8e0ab-128">Also, there is a decrease in the headroom otherwise available to absorb sudden peaks in traffic.</span></span>

  - <span data-ttu-id="8e0ab-129">Для ссылок, которые не могут быть правильно указаны в коротком случае (например, на сайте с очень низкими связями по глобальным сетям), можно отключить видео для некоторых пользователей.</span><span class="sxs-lookup"><span data-stu-id="8e0ab-129">For links that cannot be correctly provisioned in the short term (for example, a site with very poor WAN links), consider disabling video for certain users.</span></span>

  - <span data-ttu-id="8e0ab-130">Подготовьте сеть, чтобы обеспечить максимальную задержку (задержку) в 150 миллисекунд (МС) в течение пиковой нагрузки.</span><span class="sxs-lookup"><span data-stu-id="8e0ab-130">Provision your network to ensure a maximum end-to-end delay (latency) of 150 milliseconds (ms) under peak load.</span></span> <span data-ttu-id="8e0ab-131">Задержка — это нарушение в сети, которое компонент мультимедиа Lync Server не может сократить, и важно найти и устранить слабые точки.</span><span class="sxs-lookup"><span data-stu-id="8e0ab-131">Latency is the one network impairment that Lync Server media components cannot reduce, and it is important to find and eliminate the weak points.</span></span>

  - <span data-ttu-id="8e0ab-132">Для серверов с установленным антивирусным программным обеспечением включите все серверы, на которых работает Lync Server, в список исключений, чтобы обеспечить оптимальную производительность и качество звука.</span><span class="sxs-lookup"><span data-stu-id="8e0ab-132">For servers running antivirus software, include all servers running Lync Server in the exception list in order to provide optimal performance and audio quality.</span></span>

</div>

<div>

## <a name="conferencing-network-requirements"></a><span data-ttu-id="8e0ab-133">Сетевые требования для конференц-связи</span><span class="sxs-lookup"><span data-stu-id="8e0ab-133">Conferencing Network Requirements</span></span>

<span data-ttu-id="8e0ab-134">Пропускная способность, используемая для загрузки содержимого конференции с сервера служб IIS, зависит от размера загруженного содержимого.</span><span class="sxs-lookup"><span data-stu-id="8e0ab-134">The bandwidth that is used to download conference content from the Internet Information Services (IIS) server depends on the size of the content that is uploaded.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

