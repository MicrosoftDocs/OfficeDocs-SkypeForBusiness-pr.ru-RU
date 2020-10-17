---
title: 'Lync Server 2013: контрольный список развертывания магистрали SIP'
description: 'Lync Server 2013: контрольный список развертывания магистрали SIP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunk deployment checklist
ms:assetid: 94f4f03e-19d5-4198-92be-e4076dbb959a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398755(v=OCS.15)
ms:contentKeyID: 48184891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbab9647a7146b2478317ab6c020969506f9c0ef
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559045"
---
# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="6ce5d-103">Контрольный список развертывания магистрали SIP для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ce5d-103">SIP trunk deployment checklist for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ce5d-104">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="6ce5d-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="6ce5d-105">Чтобы развернуть магистраль SIP, вам нужно обменяться с поставщиком услуг некоторыми основными сведениями о соответствующих конечных точках магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="6ce5d-105">Before you can deploy a SIP trunk, you and your service provider must exchange some basic connection information about your respective SIP trunk endpoints.</span></span>

<span data-ttu-id="6ce5d-106">Получите следующие сведения для каждого шлюза поставщика услуг интернет-телефонии (ITSP), к которому вы будете подключаться:</span><span class="sxs-lookup"><span data-stu-id="6ce5d-106">Get the following information for each ITSP gateway that you will connect to:</span></span>

  - <span data-ttu-id="6ce5d-107">IP-адрес;</span><span class="sxs-lookup"><span data-stu-id="6ce5d-107">IP address</span></span>

  - <span data-ttu-id="6ce5d-108">полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="6ce5d-108">Fully qualified domain name (FQDN)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6ce5d-109">Поставщик услуг может попросить вас подключиться к нескольким шлюзам ITSP.</span><span class="sxs-lookup"><span data-stu-id="6ce5d-109">The service provider may ask you to connect to more than one ITSP gateway.</span></span> <span data-ttu-id="6ce5d-110">В этом случае необходимо настроить подключение между каждым шлюзом ITSP и каждым сервером-посредником в пуле.</span><span class="sxs-lookup"><span data-stu-id="6ce5d-110">In that case, you must configure a connection between each ITSP gateway and each Mediation Server in your pool.</span></span>



</div>

<span data-ttu-id="6ce5d-111">Сведения, которые вам нужно предоставить поставщику услуг, зависят от типа подключения магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="6ce5d-111">The information you give to your service provider depends on your SIP trunk connection type:</span></span>

  - <span data-ttu-id="6ce5d-112">Для подключений с многопротокольной коммутацией по меткам (MPLS) или подключений к частной сети предоставьте поставщику услуг IP-адрес с возможностью общедоступной маршрутизации, назначенный маршрутизатору в сети периметра (также известной как демилитаризованная зона или промежуточная подсеть).</span><span class="sxs-lookup"><span data-stu-id="6ce5d-112">For Multiprotocol Label Switching (MPLS) or private network connections, give the ITSP the publicly routable IP Address of the router in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="6ce5d-113">Убедитесь в том, что этот адрес доступен шлюзу или пограничному контроллеру сеансов (SBC) на стороне поставщика услуг.</span><span class="sxs-lookup"><span data-stu-id="6ce5d-113">Verify that the gateway or Session Border Controller (SBC) at the ITSP can reach this address.</span></span> <span data-ttu-id="6ce5d-114">Кроме того, предоставьте ITSP полное доменное имя сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="6ce5d-114">Also give the ITSP the FQDN of your Mediation Server.</span></span>

  - <span data-ttu-id="6ce5d-115">Для подключений к виртуальной частной сети (VPN) предоставьте поставщику услуг IP-адрес VPN-сервера.</span><span class="sxs-lookup"><span data-stu-id="6ce5d-115">For virtual private network (VPN) connections, give the ITSP the IP address of your VPN server.</span></span>

<div>

## <a name="certificate-considerations"></a><span data-ttu-id="6ce5d-116">Вопросы, связанные с сертификатами</span><span class="sxs-lookup"><span data-stu-id="6ce5d-116">Certificate Considerations</span></span>

<span data-ttu-id="6ce5d-117">Чтобы узнать, нужен ли вам сертификат для распределения каналов SIP, запросите у поставщика услуг сведения о поддержке протоколов.</span><span class="sxs-lookup"><span data-stu-id="6ce5d-117">To determine whether you need a certificate for SIP trunking, check with your ITSP about protocol support:</span></span>

1.  <span data-ttu-id="6ce5d-118">Если ваш поставщик поддерживает только протокол TCP, сертификат не нужен.</span><span class="sxs-lookup"><span data-stu-id="6ce5d-118">If your ITSP supports Transmission Control Protocol (TCP) only, you do not need a certificate.</span></span>

2.  <span data-ttu-id="6ce5d-119">Если поставщик поддерживает протокол TLS, он должен предоставить вам сертификат.</span><span class="sxs-lookup"><span data-stu-id="6ce5d-119">If your ITSP supports Transport Layer Security (TLS), the ITSP must provide you with a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6ce5d-120">Протокол SIP используется совместно с протоколами RTP или SRTP, которые управляют голосовыми данными в рамках звонков VoIP.</span><span class="sxs-lookup"><span data-stu-id="6ce5d-120">SIP works in conjunction with real-time transport protocol (RTP) or secure real-time transport protocol (SRTP), the protocols that manage the actual voice data in Voice over Internet Protocol (VoIP) calls.</span></span>



</div>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="6ce5d-121">Процесс развертывания</span><span class="sxs-lookup"><span data-stu-id="6ce5d-121">Deployment Process</span></span>

<span data-ttu-id="6ce5d-122">Чтобы реализовать сервер Lync для подключения магистральной линии SIP, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="6ce5d-122">To implement the Lync Server side of the SIP trunk connection, follow these steps:</span></span>

1.  <span data-ttu-id="6ce5d-123">Используя построитель топологий Lync Server, создайте и настройте топологию домена SIP.</span><span class="sxs-lookup"><span data-stu-id="6ce5d-123">Using the Lync Server Topology Builder, create and configure the SIP domain topology.</span></span> <span data-ttu-id="6ce5d-124">Дополнительные сведения приведены [в статье определение и Настройка топологии в построителе топологий для Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="6ce5d-124">For details, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="6ce5d-125">С помощью панели управления Lync Server Настройте маршрутизацию голосовой связи для нового домена SIP.</span><span class="sxs-lookup"><span data-stu-id="6ce5d-125">Using the Lync Server Control Panel, configure voice routing for the new SIP domain.</span></span> <span data-ttu-id="6ce5d-126">Для получения дополнительных сведений см раздел [Настройка магистрали в Lync Server 2013](lync-server-2013-configuring-trunks.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="6ce5d-126">For details, see [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="6ce5d-127">Проверьте подключение с помощью командлета **Test-CsPstnOutboundCall**.</span><span class="sxs-lookup"><span data-stu-id="6ce5d-127">Test connectivity by using the **Test-CsPstnOutboundCall** cmdlet.</span></span> <span data-ttu-id="6ce5d-128">Дополнительные сведения можно найти в документации по командной консоли Lync Server или справке по консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6ce5d-128">For details, see the Lync Server Management Shell documentation or Help for Lync Server Management Shell.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

