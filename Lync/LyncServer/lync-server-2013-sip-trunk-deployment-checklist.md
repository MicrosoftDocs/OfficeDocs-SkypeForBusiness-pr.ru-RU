---
title: 'Lync Server 2013: контрольный список развертывания для каналов SIP'
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
ms.openlocfilehash: ef670fc4ae9e8a9acba3277a00fc0daf6ff766b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="5bc39-102">Контрольный список развертывания для каналов SIP для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bc39-102">SIP trunk deployment checklist for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5bc39-103">_**Тема последнего изменения:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="5bc39-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="5bc39-104">Перед развертыванием магистральной магистрали SIP вы, как и поставщик услуг, должны переключить некоторые основные сведения о подключении к соответствующим конечным точкам магистральов SIP.</span><span class="sxs-lookup"><span data-stu-id="5bc39-104">Before you can deploy a SIP trunk, you and your service provider must exchange some basic connection information about your respective SIP trunk endpoints.</span></span>

<span data-ttu-id="5bc39-105">Получите следующие сведения о каждом шлюзе ИТСП, к которому вы хотите подключиться.</span><span class="sxs-lookup"><span data-stu-id="5bc39-105">Get the following information for each ITSP gateway that you will connect to:</span></span>

  - <span data-ttu-id="5bc39-106">IP-адрес</span><span class="sxs-lookup"><span data-stu-id="5bc39-106">IP address</span></span>

  - <span data-ttu-id="5bc39-107">Полное доменное имя (FQDN)</span><span class="sxs-lookup"><span data-stu-id="5bc39-107">Fully qualified domain name (FQDN)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5bc39-108">Поставщик услуг может попросить вас подключиться к нескольким шлюзам ИТСП.</span><span class="sxs-lookup"><span data-stu-id="5bc39-108">The service provider may ask you to connect to more than one ITSP gateway.</span></span> <span data-ttu-id="5bc39-109">В этом случае необходимо настроить подключение между каждым шлюзом ИТСП и каждым сервером-посредником в пуле.</span><span class="sxs-lookup"><span data-stu-id="5bc39-109">In that case, you must configure a connection between each ITSP gateway and each Mediation Server in your pool.</span></span>



</div>

<span data-ttu-id="5bc39-110">Сведения, предоставленные вашему поставщику услуг, зависят от типа подключения к магистрали по протоколу SIP:</span><span class="sxs-lookup"><span data-stu-id="5bc39-110">The information you give to your service provider depends on your SIP trunk connection type:</span></span>

  - <span data-ttu-id="5bc39-111">При переключении многопротокольной метки (MPLS) или подключения к частной сети выведите ИТСП IP-адрес маршрутизатора в демилитаризованной зоне (также называется демилитаризованной зоной, ДМЗ, экранированной подсетью).</span><span class="sxs-lookup"><span data-stu-id="5bc39-111">For Multiprotocol Label Switching (MPLS) or private network connections, give the ITSP the publicly routable IP Address of the router in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="5bc39-112">Убедитесь, что шлюз или однограницный контроллер (SBC) в ИТСП может получить к этому адресу.</span><span class="sxs-lookup"><span data-stu-id="5bc39-112">Verify that the gateway or Session Border Controller (SBC) at the ITSP can reach this address.</span></span> <span data-ttu-id="5bc39-113">Также предоставьте ИТСП полное доменное имя сервера.</span><span class="sxs-lookup"><span data-stu-id="5bc39-113">Also give the ITSP the FQDN of your Mediation Server.</span></span>

  - <span data-ttu-id="5bc39-114">Для подключений к виртуальным частным сетям (VPN) назначьте ИТСП IP-адресу VPN-сервера.</span><span class="sxs-lookup"><span data-stu-id="5bc39-114">For virtual private network (VPN) connections, give the ITSP the IP address of your VPN server.</span></span>

<div>

## <a name="certificate-considerations"></a><span data-ttu-id="5bc39-115">Сведения о сертификате</span><span class="sxs-lookup"><span data-stu-id="5bc39-115">Certificate Considerations</span></span>

<span data-ttu-id="5bc39-116">Чтобы определить, нужен ли вам сертификат для магистральной магистрали SIP, обратитесь к ИТСП о поддержке протоколов:</span><span class="sxs-lookup"><span data-stu-id="5bc39-116">To determine whether you need a certificate for SIP trunking, check with your ITSP about protocol support:</span></span>

1.  <span data-ttu-id="5bc39-117">Если ваш ИТСП поддерживает только протокол TCP, сертификат вам не нужен.</span><span class="sxs-lookup"><span data-stu-id="5bc39-117">If your ITSP supports Transmission Control Protocol (TCP) only, you do not need a certificate.</span></span>

2.  <span data-ttu-id="5bc39-118">Если ваш ИТСП поддерживает TLS, ИТСП должен предоставить вам сертификат.</span><span class="sxs-lookup"><span data-stu-id="5bc39-118">If your ITSP supports Transport Layer Security (TLS), the ITSP must provide you with a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5bc39-119">SIP работает совместно с протоколом транспортной сети в реальном времени (RTP) или протоколом передачи данных в режиме реального времени (SRTP) — протоколы, которые управляют реальными голосовыми данными в звонках по протоколу VoIP.</span><span class="sxs-lookup"><span data-stu-id="5bc39-119">SIP works in conjunction with real-time transport protocol (RTP) or secure real-time transport protocol (SRTP), the protocols that manage the actual voice data in Voice over Internet Protocol (VoIP) calls.</span></span>



</div>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="5bc39-120">Процесс развертывания</span><span class="sxs-lookup"><span data-stu-id="5bc39-120">Deployment Process</span></span>

<span data-ttu-id="5bc39-121">Чтобы реализовать сервер Lync Server на стороне магистрали магистральной сети SIP, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5bc39-121">To implement the Lync Server side of the SIP trunk connection, follow these steps:</span></span>

1.  <span data-ttu-id="5bc39-122">С помощью построителя топологии Lync Server создайте и настройте топологию домена SIP.</span><span class="sxs-lookup"><span data-stu-id="5bc39-122">Using the Lync Server Topology Builder, create and configure the SIP domain topology.</span></span> <span data-ttu-id="5bc39-123">Подробности можно найти [в разделе Определение и Настройка топологии в построителе топологии для Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="5bc39-123">For details, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="5bc39-124">С помощью панели управления Lync Server Настройте маршрутизацию голосовой связи для нового домена SIP.</span><span class="sxs-lookup"><span data-stu-id="5bc39-124">Using the Lync Server Control Panel, configure voice routing for the new SIP domain.</span></span> <span data-ttu-id="5bc39-125">Подробности можно найти [в разделе Настройка каналов в Lync Server 2013](lync-server-2013-configuring-trunks.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="5bc39-125">For details, see [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="5bc39-126">Протестируйте подключение с помощью командлета **Test-кспстнаутбаундкалл** .</span><span class="sxs-lookup"><span data-stu-id="5bc39-126">Test connectivity by using the **Test-CsPstnOutboundCall** cmdlet.</span></span> <span data-ttu-id="5bc39-127">Подробные сведения можно найти в документации по оболочке управления Lync Server Management Shell или в справочной среде Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5bc39-127">For details, see the Lync Server Management Shell documentation or Help for Lync Server Management Shell.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

