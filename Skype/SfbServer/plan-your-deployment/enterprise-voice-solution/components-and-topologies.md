---
title: Компоненты и топологии для управления приемом вызовов в Skype для бизнеса
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
description: Планирование управления приемом вызовов (CAC), если у вас есть сеть MPLS, магистраль SIP или сторонний шлюз PSTN или PBX. Применяется к Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: 771b98e10c28248bc917bff2b8128b6258c140c5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109195"
---
# <a name="components-and-topologies-for-call-admission-control-in-skype-for-business"></a><span data-ttu-id="12271-104">Компоненты и топологии для управления приемом вызовов в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="12271-104">Components and topologies for call admission control in Skype for Business</span></span>

<span data-ttu-id="12271-105">Планирование управления приемом вызовов (CAC), если у вас есть сеть MPLS, магистраль SIP или сторонний шлюз PSTN или PBX.</span><span class="sxs-lookup"><span data-stu-id="12271-105">Planning for call admission control (CAC) if you have an MPLS network, a SIP trunk, or a third-party PSTN gateway or PBX.</span></span> <span data-ttu-id="12271-106">Применяется к Skype для бизнеса Server Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="12271-106">Applies to Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="12271-107">В этом разделе описываются моменты, которые следует учитывать при развертывании контроля допуска звонков с различными типами топологии сети.</span><span class="sxs-lookup"><span data-stu-id="12271-107">The topics in this section provide information about special considerations for deploying call admission control (CAC) with various types of network topologies.</span></span>

## <a name="call-admission-control-on-an-mpls-network"></a><span data-ttu-id="12271-108">Управление приемом вызовов в сети MPLS</span><span class="sxs-lookup"><span data-stu-id="12271-108">Call admission control on an MPLS network</span></span>

<span data-ttu-id="12271-p103">В сети с многопротокольной коммутацией по меткам (MPLS) все сайты соединены в полную сетку. То есть, все сайты подключаются напрямую к MPLS-магистрали поставщика услуг Интернета, и каждому сайту выделяется полоса пропускания, используемая для взаимодействия по каналу глобальной сети с MPLS-облаком. Не существует ни сетевого концентратора, ни центрального сайта для управления IP-маршрутизацией. На следующему рисунке показана простая сеть, основанная на технологии MPLS.</span><span class="sxs-lookup"><span data-stu-id="12271-p103">In a Multiprotocol Label Switching (MPLS) network, all sites are connected by a full-mesh. That is, all sites are connected directly to the MPLS backbone of the Internet service provider, and each site is provisioned bandwidth to be used across a WAN link to the MPLS cloud. There is no network hub or central site to control IP routing. The following figure shows a simple network based on MPLS technology.</span></span>

<span data-ttu-id="12271-113">**Пример сети MPLS**</span><span class="sxs-lookup"><span data-stu-id="12271-113">**Example MPLS network**</span></span>

![CAC с MPLS](../../media/CAC_MPLS_1.jpg)

<span data-ttu-id="12271-p104">Чтобы развернуть контроль допуска звонков в сети MPLS, вам требуется создать область сети, представляющую облако MPLS, и создать сетевой узел, представляющий каждый вспомогательный сайт MPLS. На следующем рисунке показано, как следует настроить область сети и сетевые узлы, чтобы они представляли пример сети MPLS из предыдущего примера. Ограничения для общей пропускной способности и пропускной способности сеанса основываются на емкости канала связи глобальной сети от каждого сетевого узла к области сети, которая представляет облако MPLS.</span><span class="sxs-lookup"><span data-stu-id="12271-p104">To deploy call admission control (CAC) in an MPLS network, you create a network region to represent the MPLS cloud, and create a network site to represent each MPLS satellite site. The following figure illustrates how the network region and network sites should be configured to represent the example MPLS network in the previous figure. The overall bandwidth limits and bandwidth session limits are then based on the capacity of the WAN link from each network site to the network region that represents the MPLS cloud.</span></span>

<span data-ttu-id="12271-118">**Область сети и сетевые узлы для сети MPLS**</span><span class="sxs-lookup"><span data-stu-id="12271-118">**Network region and network sites for an MPLS network**</span></span>

![Управление приемом вызовов (CAC) с помощью схемы MPLS](../../media/CAC_MPLS_2.jpg)

## <a name="call-admission-control-on-a-sip-trunk"></a><span data-ttu-id="12271-120">Управление приемом вызовов в магистрали SIP</span><span class="sxs-lookup"><span data-stu-id="12271-120">Call admission control on a SIP trunk</span></span>

<span data-ttu-id="12271-p105">Для развертывания контроля допуска звонков в канал SIP создается сетевой узел, который представляет поставщика услуг Интернет-телефонии (ITSP). Для применения значений политики пропускной способности в канале SIP создается межузловая политика между сетевым узлом в предприятии и сетевым узлом, созданным для представления ITSP.</span><span class="sxs-lookup"><span data-stu-id="12271-p105">To deploy call admission control (CAC) on a SIP trunk, you create a network site to represent the Internet telephony service provider (ITSP). To apply bandwidth policy values on the SIP trunk, you create an inter-site policy between the network site in your enterprise and the network site that you create to represent the ITSP.</span></span>

<span data-ttu-id="12271-123">На следующем рисунке показан пример развертывания контроля допуска звонков в канале SIP.</span><span class="sxs-lookup"><span data-stu-id="12271-123">The following figure shows an example CAC deployment on a SIP trunk.</span></span>

<span data-ttu-id="12271-124">**Конфигурация контроля допуска звонков в канале SIP**</span><span class="sxs-lookup"><span data-stu-id="12271-124">**CAC configuration on a SIP trunk**</span></span>

![Схема магистрали управления входом вызовов SIP](../../media/CAC_SIP_trunk_1.jpg)

<span data-ttu-id="12271-126">Чтобы настроить контроль допуска звонков в канале SIP, во время развертывания контроля допуска звонков необходимо выполнить следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="12271-126">To configure CAC on a SIP trunk, you will have to perform the following tasks during CAC deployment:</span></span>

1. <span data-ttu-id="12271-127">Создать сетевой узел, представляющий поставщика услуг Интернет-телефонии (ITSP).</span><span class="sxs-lookup"><span data-stu-id="12271-127">Create a network site to represent the ITSP.</span></span> <span data-ttu-id="12271-128">Связать этот сетевой узел с соответствующей областью сети и выделить в этом сетевом узле нулевую пропускную способность для аудио и видео.</span><span class="sxs-lookup"><span data-stu-id="12271-128">Associate the network site to an appropriate network region, and allocate bandwidth of zero for audio and video for this network site.</span></span> <span data-ttu-id="12271-129">Подробные сведения см. в разделе [Configure Network Sites for CAC](/previous-versions/office/lync-server-2013/lync-server-2013-configure-network-sites-for-cac) документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="12271-129">For details, see [Configure Network Sites for CAC](/previous-versions/office/lync-server-2013/lync-server-2013-configure-network-sites-for-cac) in the Deployment documentation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="12271-130">Для ITSP конфигурация этого сетевого узла не функциональна.</span><span class="sxs-lookup"><span data-stu-id="12271-130">For the ITSP, this network site configuration is not functional.</span></span> <span data-ttu-id="12271-131">Значения политики пропускной способности фактически применяются в шаге 2.</span><span class="sxs-lookup"><span data-stu-id="12271-131">Bandwidth policy values are actually applied in step 2.</span></span>

2. <span data-ttu-id="12271-132">Создайте межсайтовую ссылку для магистрали SIP с использованием соответствующих значений параметров для сайта, созданного на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="12271-132">Create an inter-site link for the SIP trunk using the relevant parameter values for the site you created in step 1.</span></span> <span data-ttu-id="12271-133">Например, используйте имя сетевого сайта в вашем предприятии в качестве значения параметра NetworkSiteID1, а сетевого сайта ITSP как значение параметра NetworkSiteID2.</span><span class="sxs-lookup"><span data-stu-id="12271-133">For example, use the name of the network site in your enterprise as the value of the NetworkSiteID1 parameter, and the ITSP network site as the value of the NetworkSiteID2 parameter.</span></span> <span data-ttu-id="12271-134">Дополнительные сведения см. в материале Create network [intersite policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) в документации по развертыванию и [New-CsNetworkInterSitePolicy.](/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="12271-134">For details, see [Create network intersite policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) in the Deployment documentation, and [New-CsNetworkInterSitePolicy](/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps).</span></span>

3. <span data-ttu-id="12271-135">Получите IP-адрес точки прерывания мультимедиа диспетчера сеанса (SCB) в своем ITSP.</span><span class="sxs-lookup"><span data-stu-id="12271-135">Get the IP address of the Session Border Controller's (SCB) Media Termination Point from your ITSP.</span></span> <span data-ttu-id="12271-136">Добавить этот IP-адрес с маской подсети 32 к сетевому узлу, представляющему ITSP.</span><span class="sxs-lookup"><span data-stu-id="12271-136">Add that IP address with a subnet mask of 32 to the network site that represents the ITSP.</span></span> <span data-ttu-id="12271-137">Подробные сведения см. в статье [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site).</span><span class="sxs-lookup"><span data-stu-id="12271-137">For details, see [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site).</span></span>

## <a name="call-admission-control-with-a-third-party-pstn-gateway-or-pbx"></a><span data-ttu-id="12271-138">Управление приемом вызовов с помощью сторонних шлюзов PSTN или PBX</span><span class="sxs-lookup"><span data-stu-id="12271-138">Call admission control with a third-party PSTN gateway or PBX</span></span>

<span data-ttu-id="12271-139">В этом разделе описываются примеры развертывания управления приемом вызовов (CAC) по ссылке между интерфейсом шлюза сервера-посредника и шлюзом открытой телефонной сети (PSTN) или частным филиалом (PBX).</span><span class="sxs-lookup"><span data-stu-id="12271-139">This topic describes examples of how call admission control (CAC) can be deployed on the link between the Mediation Server's gateway interface and a third-party public switched telephone network (PSTN) gateway or private branch exchange (PBX).</span></span>

### <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a><span data-ttu-id="12271-140">Случай 1. Контроль допуска звонков между сервером-посредником и шлюзом ТСОП</span><span class="sxs-lookup"><span data-stu-id="12271-140">Case 1: CAC between the Mediation Server and a PSTN gateway</span></span>

<span data-ttu-id="12271-141">CAC можно развернуть по ссылке WAN из интерфейса шлюза сервера-посредника в сторонний шлюз PBX или PSTN.</span><span class="sxs-lookup"><span data-stu-id="12271-141">CAC can be deployed on the WAN link from the Mediation Server's gateway interface to a third-party PBX or PSTN gateway.</span></span>

<span data-ttu-id="12271-142">**Случай 1. Контроль допуска звонков между сервером-посредником и шлюзом ТСОП**</span><span class="sxs-lookup"><span data-stu-id="12271-142">**Case 1: CAC between the Mediation Server and a PSTN gateway**</span></span>

![Пример 1. CAC между шлюзом PSTN сервера-посредника](../../media/CAC_gateways_1.jpg)

<span data-ttu-id="12271-144">В этом примере контроль допуска звонков реализуется между сервером-посредником и шлюзом ТСОП.</span><span class="sxs-lookup"><span data-stu-id="12271-144">In this example, CAC is applied between the Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="12271-145">Если клиент Skype для бизнеса на сетевом сайте 1 помещает вызов PSTN через шлюз PSTN в сетевом сайте 2, средства массовой информации течет через ссылку WAN.</span><span class="sxs-lookup"><span data-stu-id="12271-145">If a Skype for Business client user at Network Site 1 places a PSTN call through the PSTN gateway in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="12271-146">Поэтому для каждого сеанса ТСОП выполняются две проверки контроля допуска звонков:</span><span class="sxs-lookup"><span data-stu-id="12271-146">Therefore, two CAC checks are performed for each PSTN session:</span></span>

- <span data-ttu-id="12271-147">Между клиентской приложением Skype для бизнеса и сервером-посредником</span><span class="sxs-lookup"><span data-stu-id="12271-147">Between the Skype for Business client application and the Mediation Server</span></span>

- <span data-ttu-id="12271-148">между сервером-посредником и шлюзом ТСОП.</span><span class="sxs-lookup"><span data-stu-id="12271-148">Between the Mediation Server and the PSTN gateway</span></span>

<span data-ttu-id="12271-149">Проверки выполняются как для входящих звонков ТСОП, поступающих в клиент в сетевом узле 1, так и для исходящих звонков ТСОП из клиентского приложения в сетевом узле 1.</span><span class="sxs-lookup"><span data-stu-id="12271-149">This works for both incoming PSTN calls to a client in Network Site 1, and for outgoing PSTN calls originating from a client application in Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="12271-150">Убедитесь в том, что IP-подсеть, к которой относится шлюз ТСОП, настроена и связана с сетевым узлом 2.</span><span class="sxs-lookup"><span data-stu-id="12271-150">Make sure that the IP subnet that the PSTN gateway belongs to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="12271-151">Убедитесь в том, что IP-подсеть, к которой относятся оба интерфейса сервера-посредника, настроена и связана с сетевым узлом 1.</span><span class="sxs-lookup"><span data-stu-id="12271-151">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="12271-152">Подробнее см. в разделе [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site).</span><span class="sxs-lookup"><span data-stu-id="12271-152">For details, see [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site).</span></span>

### <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a><span data-ttu-id="12271-153">Случай 2. Контроль допуска звонков между сервером-посредником и сторонней УАТС с точкой Media Termination Point</span><span class="sxs-lookup"><span data-stu-id="12271-153">Case 2: CAC between the Mediation Server and a third-party PBX with Media Termination Point</span></span>

<span data-ttu-id="12271-p111">Эта конфигурация аналогична случаю 1. В обоих случаях серверу-посреднику известно, какое устройство является конечным на противоположном конце канала глобальной сети, и IP-адрес шлюза ТСОП или УАТС с точкой Media Termination Point (MTP) настраивается на сервере-посреднике как следующий прыжок.</span><span class="sxs-lookup"><span data-stu-id="12271-p111">This configuration is similar to Case 1. In both the cases, the Mediation Server knows what device terminates media at the opposite end of the WAN link, and the IP address of the PSTN gateway or PBX with Media Termination Point (MTP) is configured on the Mediation Server as the next hop.</span></span>

<span data-ttu-id="12271-156">**Случай 2. Контроль допуска звонков между сервером-посредником и сторонней УАТС с точкой MTP**</span><span class="sxs-lookup"><span data-stu-id="12271-156">**Case 2: CAC between the Mediation Server and a third-party PBX with MTP**</span></span>

![Пример 2. CAC между сервером-посредником PBX с MTP](../../media/CAC_gateways_2.jpg)

<span data-ttu-id="12271-158">В этом примере контроль допуска звонков реализуется между сервером-посредником и УАТС с точкой MTP.</span><span class="sxs-lookup"><span data-stu-id="12271-158">In this example, CAC is applied between the Mediation Server and the PBX/MTP.</span></span> <span data-ttu-id="12271-159">Если клиент Skype для бизнеса на сетевом сайте 1 помещает вызов PSTN через PBX/MTP, расположенный в сетевом сайте 2, средства массовой информации течет через ссылку WAN.</span><span class="sxs-lookup"><span data-stu-id="12271-159">If a Skype for Business client user at the Network Site 1 places a PSTN call through the PBX/MTP located in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="12271-160">Поэтому для каждого сеанса ТСОП выполняются две проверки контроля допуска звонков:</span><span class="sxs-lookup"><span data-stu-id="12271-160">Therefore, for each PSTN session two CAC checks are performed:</span></span>

- <span data-ttu-id="12271-161">Между клиентской приложением Skype для бизнеса и сервером-посредником</span><span class="sxs-lookup"><span data-stu-id="12271-161">Between the Skype for Business client application and the Mediation Server</span></span>

- <span data-ttu-id="12271-162">между сервером-посредником и УАТС с точкой MTP.</span><span class="sxs-lookup"><span data-stu-id="12271-162">Between the Mediation Server and the PBX/MTP</span></span>

<span data-ttu-id="12271-163">Проверки выполняются как для входящих звонков ТСОП, поступающих в клиент в сетевом узле 1, так и для исходящих звонков ТСОП из клиента в сетевом узле 1.</span><span class="sxs-lookup"><span data-stu-id="12271-163">This works for both incoming PSTN calls to a client in Network Site 1, and outgoing PSTN calls originating from a client in Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="12271-164">Убедитесь в том, что IP-подсеть, к которой относится точка MTP, настроена и связана с сетевым узлом 2.</span><span class="sxs-lookup"><span data-stu-id="12271-164">Make sure that the IP subnet that the MTP belongs to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="12271-165">Убедитесь в том, что IP-подсеть, к которой относятся оба интерфейса сервера-посредника, настроена и связана с сетевым узлом 1.</span><span class="sxs-lookup"><span data-stu-id="12271-165">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="12271-166">Подробнее см. в разделе [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site).</span><span class="sxs-lookup"><span data-stu-id="12271-166">For details, see [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site).</span></span>

### <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a><span data-ttu-id="12271-167">Случай 3. Контроль допуска звонков между сервером-посредником и сторонней УАТС без точки Media Termination Point</span><span class="sxs-lookup"><span data-stu-id="12271-167">Case 3: CAC between the Mediation Server and a third-party PBX without a Media Termination Point</span></span>

<span data-ttu-id="12271-p113">Случай 3 немного отличается от первых двух. Если на сторонней УАТС отсутствует точка MTP, то при выполнении запроса исходящего сеанса к сторонней УАТС серверу-посреднику неизвестно, куда поступят данные в пределах УАТС. В этом случае данные передаются непосредственно между сервером-посредником и сторонним конечным устройством.</span><span class="sxs-lookup"><span data-stu-id="12271-p113">Case 3 is slightly different from the first two cases. If there is no MTP on the third-party PBX, for an outgoing session request to the third-party PBX the Mediation Server does not know where media will terminate in the PBX boundary. In this case, the media flows directly between the Mediation Server and the third-party endpoint device.</span></span>

<span data-ttu-id="12271-171">**Случай 3. Контроль допуска звонков между сервером-посредником и сторонней УАТС без точки MTP**</span><span class="sxs-lookup"><span data-stu-id="12271-171">**Case 3: CAC between the Mediation Server and a third-party PBX without MTP**</span></span>

![Пример 3. CAC между сервером-посредником PBX без MTP](../../media/CAC_gateways_3.jpg)

<span data-ttu-id="12271-173">В этом примере, если клиент Skype для бизнеса на сетевом сайте 1 помещает вызов пользователю через PBX, сервер-посредник может выполнять проверки CAC только на прокси-сервере (между клиентом Skype для бизнеса и сервером-посредником).</span><span class="sxs-lookup"><span data-stu-id="12271-173">In this example, if a Skype for Business client user at Network Site 1 places a call to a user through the PBX, the Mediation Server is able to perform CAC checks only on the proxy leg (between the Skype for Business client application and Mediation Server).</span></span> <span data-ttu-id="12271-174">Поскольку сервер-посредник не имеет сведений о конечном устройстве при запросе сеанса, проверки контроля допуска звонков нельзя выполнить на канале глобальной сети (между сервером-посредником и сторонним устройством) до того, как звонок будет установлен.</span><span class="sxs-lookup"><span data-stu-id="12271-174">Because the Mediation Server does not have information about the endpoint device while the session is being requested, CAC checks cannot be performed on the WAN link (between the Mediation Server and the third-party endpoint) prior to call establishment.</span></span> <span data-ttu-id="12271-175">Однако после установки сеанса серверу-посреднику проще контролировать используемую пропускную способность магистрали.</span><span class="sxs-lookup"><span data-stu-id="12271-175">After the session is established, however, the Mediation Server facilitates in accounting for the bandwidth used on the trunk.</span></span>

<span data-ttu-id="12271-176">Если звонки исходят со сторонней конечной точки, информация об устройстве становится доступна в момент выполнения запроса сеанса, после чего проверки контроля допуска звонков можно выполнить на обеих сторонах сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="12271-176">For calls that originate from the third-party endpoint, the information about that endpoint device is available at the time of session request and CAC check can be performed on both the sides of the Mediation Server.</span></span>

> [!NOTE]
> <span data-ttu-id="12271-177">Убедитесь в том, что IP-подсеть, к которой относятся устройства конечных точек, настроена и связана с сетевым узлом 2.</span><span class="sxs-lookup"><span data-stu-id="12271-177">Make sure that the IP subnet that the endpoint devices belong to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="12271-178">Убедитесь в том, что IP-подсеть, к которой относятся оба интерфейса сервера-посредника, настроена и связана с сетевым узлом 1.</span><span class="sxs-lookup"><span data-stu-id="12271-178">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="12271-179">Подробнее см. в разделе [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site).</span><span class="sxs-lookup"><span data-stu-id="12271-179">For details, see [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site).</span></span>