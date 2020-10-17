---
title: Требования к сетевой инфраструктуре Lync Server 2013
description: Требования к сетевой инфраструктуре Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network infrastructure requirements
ms:assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425841(v=OCS.15)
ms:contentKeyID: 48183804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f7ff21c2f936ef8e048f6831d55408994055400
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561505"
---
# <a name="network-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="cc8fb-103">Требования к инфраструктуре сети для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc8fb-103">Network infrastructure requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc8fb-104">_**Последнее изменение темы:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="cc8fb-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="cc8fb-105">Сетевой адаптер каждого сервера в топологии Lync Server 2013 должен поддерживать по крайней мере 1 гигабит в секунду (Гбит/с).</span><span class="sxs-lookup"><span data-stu-id="cc8fb-105">The network adapter card of each server in the Lync Server 2013 topology must support at least 1 gigabit per second (Gbps).</span></span> <span data-ttu-id="cc8fb-106">В общем случае необходимо подключить все роли сервера в пределах топологии Lync Server, используя низкую задержку и локальную сеть высокой пропускной способности (ЛВС).</span><span class="sxs-lookup"><span data-stu-id="cc8fb-106">In general, you should connect all server roles within the Lync Server topology using a low latency and high bandwidth local area network (LAN).</span></span> <span data-ttu-id="cc8fb-107">Размер локальной сети зависит от размера топологии.</span><span class="sxs-lookup"><span data-stu-id="cc8fb-107">The size of the LAN is dependent on the size of the topology:</span></span>

  - <span data-ttu-id="cc8fb-108">В топологиях Standard Edition серверы должны быть в сети, поддерживающей 1 Гбит/с, или аналогичной.</span><span class="sxs-lookup"><span data-stu-id="cc8fb-108">In Standard Edition topologies, servers should be in a network that supports 1 Gbps Ethernet or equivalent.</span></span>

  - <span data-ttu-id="cc8fb-109">В топологиях пула переднего плана большинство серверов должны находиться в сети, поддерживающей более 1 Гбит/с, особенно при поддержке конференц-связи аудио-и видеоданных (A/V) и общего доступа к приложениям.</span><span class="sxs-lookup"><span data-stu-id="cc8fb-109">In Front End pool topologies, most servers should be in a network that supports more than 1 Gbps, especially when supporting audio/video (A/V) conferencing and application sharing.</span></span>

<span data-ttu-id="cc8fb-110">Для интеграции с телефонной сетью общего пользования (ТСОП) можно использовать линии T1/E1 или распределение каналов SIP.</span><span class="sxs-lookup"><span data-stu-id="cc8fb-110">For public switched telephone network (PSTN) integration, you can integrate by using either T1/E1 lines or SIP trunking.</span></span>

<div>

## <a name="audiovideo-network-requirements"></a><span data-ttu-id="cc8fb-111">Требования к сети для передачи звука и видео</span><span class="sxs-lookup"><span data-stu-id="cc8fb-111">Audio/Video Network Requirements</span></span>

<span data-ttu-id="cc8fb-112">Требования к сети для аудио/видео (A/V) в развертывании Lync Server включают следующее:</span><span class="sxs-lookup"><span data-stu-id="cc8fb-112">Network requirements for audio/video (A/V) in a Lync Server deployment include the following:</span></span>

  - <span data-ttu-id="cc8fb-113">Если вы развертываете один пограничный сервер или пограничный пул с помощью балансировки нагрузки на DNS, вы можете настроить внешний брандмауэр как NAT.</span><span class="sxs-lookup"><span data-stu-id="cc8fb-113">If you are deploying a single Edge Server or an Edge pool using DNS load balancing, you can configure the external firewall as a NAT.</span></span> <span data-ttu-id="cc8fb-114">Внутренний брандмауэр нельзя настроить как устройство NAT.</span><span class="sxs-lookup"><span data-stu-id="cc8fb-114">You cannot configure the internal firewall as a NAT.</span></span> <span data-ttu-id="cc8fb-115">Подробнее об этих требованиях можно узнать в статье [Определение требований к портам внешнего аудио-и видеоподключения для Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="cc8fb-115">For details about these requirements, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) in the Planning documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cc8fb-116">Если у вас есть пограничный пул, использующий аппаратную подсистему балансировки нагрузки, необходимо использовать общедоступные IP-адреса на каждом пограничном сервере, и вы не можете использовать NAT для серверов или пула на устройстве NAT (например, брандмауэр или другое устройство с инфраструктурой, которое будет выполнять входящий или исходящий трафик NAT).</span><span class="sxs-lookup"><span data-stu-id="cc8fb-116">If you have an Edge pool and are using a hardware load balancer, you must use public IP addresses on each of the Edge Servers and you cannot use NAT for the servers or the pool at your NAT device (for example, the firewall, or other infrastructure device that would NAT inbound or outbound traffic).</span></span> <span data-ttu-id="cc8fb-117">Подробные сведения о <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">портах: масштабируемая консолидированная пограничная система с аппаратными подсистемами балансировки нагрузки в Lync Server 2013</A> в документации по планированию внешнего доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="cc8fb-117">For details, see <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</A> in the Planning for External User Access documentation.</span></span>

    
    </div>

  - <span data-ttu-id="cc8fb-118">Если в вашей организации используется инфраструктура качества обслуживания (QoS), подсистема передачи мультимедиа настроена на работу в этой существующей инфраструктуре.</span><span class="sxs-lookup"><span data-stu-id="cc8fb-118">If your organization uses a Quality of Service (QoS) infrastructure, the media subsystem is designed to work within this existing infrastructure.</span></span>

  - <span data-ttu-id="cc8fb-119">Если вы используете протоколы IPsec, мы рекомендуем отключить их для диапазона портов, который используется для аудио- и видеотрафика.</span><span class="sxs-lookup"><span data-stu-id="cc8fb-119">If you use Internet Protocol security (IPsec), we recommend disabling IPsec over the port ranges used for A/V traffic.</span></span> <span data-ttu-id="cc8fb-120">Дополнительные сведения см. [в статье исключения IPSec в Lync Server 2013](lync-server-2013-ipsec-exceptions.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="cc8fb-120">For details, see [IPsec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) in the Planning documentation.</span></span>

<span data-ttu-id="cc8fb-121">Чтобы обеспечить оптимальное качество мультимедиа, сделайте следующее.</span><span class="sxs-lookup"><span data-stu-id="cc8fb-121">To ensure optimal media quality, do the following:</span></span>

  - <span data-ttu-id="cc8fb-p105">Обеспечьте пропускную способность сетевых каналов в периоды пикового использования в 65 килобит в секунду (Кбит/с) для аудиопотока и 500 Кбит/с для видеопотока, если он включен. Двунаправленный аудио- или видеосеанс включает два потока.</span><span class="sxs-lookup"><span data-stu-id="cc8fb-p105">Provision your network links to support throughput of 65 kilobits per second (Kbps) per audio stream and 500 Kbps per video stream, if enabled, during peak usage periods. A bidirectional audio or video session consists of two streams.</span></span>

  - <span data-ttu-id="cc8fb-124">Чтобы справиться с неожиданными нагрузками в трафике выше этого уровня и при увеличении использования с течением времени, конечные точки мультимедиа Lync Server могут адаптироваться к различным условиям сети и поддерживать загрузку в три раза больше пропускной способности (см. предыдущий абзац) для звука и видео, сохраняя приемлемое качество.</span><span class="sxs-lookup"><span data-stu-id="cc8fb-124">To cope with unexpected spikes in traffic above this level and increased usage over time, Lync Server media endpoints can adapt to varying network conditions and support loads of three times the throughput (see previous paragraph) for audio and video while still retaining acceptable quality.</span></span> <span data-ttu-id="cc8fb-125">Однако не следует предполагать, что эта адаптируемость будет поддерживать сеть с подготовкой.</span><span class="sxs-lookup"><span data-stu-id="cc8fb-125">However, do not assume that this adaptability will support an under-provisioned network.</span></span> <span data-ttu-id="cc8fb-126">В подготовной сети способность конечных точек мультимедиа-сервера Lync Server динамически работать с переменными условиями сети (например, временная потеря высокой потери пакетов).</span><span class="sxs-lookup"><span data-stu-id="cc8fb-126">In an under-provisioned network, the ability of the Lync Server media endpoints to dynamically deal with varying network conditions (for example, temporary high packet loss) is reduced.</span></span>

  - <span data-ttu-id="cc8fb-127">Если обеспечение достаточных ресурсов сети является крайне дорогостоящим и трудоемким мероприятием, можно попытаться снизить объем трафика.</span><span class="sxs-lookup"><span data-stu-id="cc8fb-127">For network links where provisioning is extremely costly and difficult, you may need to consider provisioning for a lower volume of traffic.</span></span> <span data-ttu-id="cc8fb-128">В этом сценарии для эластичности конечных точек мультимедиа Lync Server уменьшается разница между объемом трафика и уровнем пикового трафика за счет снижения качества голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="cc8fb-128">In this scenario, let the elasticity of the Lync Server media endpoints absorb the difference between the traffic volume and the peak traffic level, at the cost of some reduction in the voice quality.</span></span> <span data-ttu-id="cc8fb-129">Кроме того, в этом случае снижается запас по уровню, который позволяет справляться с резкими увеличениями объема трафика.</span><span class="sxs-lookup"><span data-stu-id="cc8fb-129">Also, there is a decrease in the headroom otherwise available to absorb sudden peaks in traffic.</span></span>

  - <span data-ttu-id="cc8fb-130">Если вам не удается подготовить соответствующие каналы в краткосрочной перспективе (например, если узел имеет каналы глобальной сети с очень низкой пропускной способностью), вы можете отключить видео для некоторых пользователей.</span><span class="sxs-lookup"><span data-stu-id="cc8fb-130">For links that cannot be correctly provisioned in the short term (for example, a site with very poor WAN links), consider disabling video for certain users.</span></span>

  - <span data-ttu-id="cc8fb-131">При подготовке сети обеспечьте максимальную задержку сквозной передачи на уровне не более 150 миллисекунд (мс) при максимальной нагрузке.</span><span class="sxs-lookup"><span data-stu-id="cc8fb-131">Provision your network to ensure a maximum end-to-end delay (latency) of 150 milliseconds (ms) under peak load.</span></span> <span data-ttu-id="cc8fb-132">Задержка — это сетевое нарушение, в результате которого компоненты мультимедиа Lync Server не могут уменьшиться, и важно найти и устранить слабые точки.</span><span class="sxs-lookup"><span data-stu-id="cc8fb-132">Latency is the one network impairment that Lync Server media components cannot reduce, and it is important to find and eliminate the weak points.</span></span>

  - <span data-ttu-id="cc8fb-133">Для серверов, на которых работает антивирусное программное обеспечение, включите все серверы, на которых работает Lync Server, в список исключений, чтобы обеспечить оптимальную производительность и качество звука.</span><span class="sxs-lookup"><span data-stu-id="cc8fb-133">For servers running antivirus software, include all servers running Lync Server in the exception list in order to provide optimal performance and audio quality.</span></span>

</div>

<div>

## <a name="conferencing-network-requirements"></a><span data-ttu-id="cc8fb-134">Требования к сети для конференц-связи</span><span class="sxs-lookup"><span data-stu-id="cc8fb-134">Conferencing Network Requirements</span></span>

<span data-ttu-id="cc8fb-135">Пропускная способность, используемая для загрузки содержимого конференций с сервера служб IIS, зависит от размера отправляемого содержимого.</span><span class="sxs-lookup"><span data-stu-id="cc8fb-135">The bandwidth that is used to download conference content from the Internet Information Services (IIS) server depends on the size of the content that is uploaded.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

