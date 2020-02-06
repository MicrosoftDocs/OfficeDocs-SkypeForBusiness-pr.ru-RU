---
title: Компоненты и топологии для управления допуском звонков в Skype для бизнеса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Планирование отчета по контролю допуска звонков (CAC) при наличии сети MPLS, магистрали SIP или шлюза ТСОП или УАТС. Применимо к голосовой связи Skype для бизнеса Server Enterprise.
ms.openlocfilehash: 7fcbc3e8c7fc7b4139fd9c83718db59af099f47f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803119"
---
# <a name="components-and-topologies-for-call-admission-control-in-skype-for-business"></a><span data-ttu-id="411e5-104">Компоненты и топологии для управления допуском звонков в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="411e5-104">Components and topologies for call admission control in Skype for Business</span></span>

<span data-ttu-id="411e5-105">Планирование отчета по контролю допуска звонков (CAC) при наличии сети MPLS, магистрали SIP или шлюза ТСОП или УАТС.</span><span class="sxs-lookup"><span data-stu-id="411e5-105">Planning for call admission control (CAC) if you have an MPLS network, a SIP trunk, or a third-party PSTN gateway or PBX.</span></span> <span data-ttu-id="411e5-106">Применимо к голосовой связи Skype для бизнеса Server Enterprise.</span><span class="sxs-lookup"><span data-stu-id="411e5-106">Applies to Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="411e5-107">В этом разделе описываются моменты, которые следует учитывать при развертывании контроля допуска звонков с различными типами топологии сети.</span><span class="sxs-lookup"><span data-stu-id="411e5-107">The topics in this section provide information about special considerations for deploying call admission control (CAC) with various types of network topologies.</span></span>

## <a name="call-admission-control-on-an-mpls-network"></a><span data-ttu-id="411e5-108">Контроль допуска звонков в сети MPLS</span><span class="sxs-lookup"><span data-stu-id="411e5-108">Call admission control on an MPLS network</span></span>

<span data-ttu-id="411e5-p103">В сети с многопротокольной коммутацией по меткам (MPLS) все сайты соединены в полную сетку. Это значит, что все сайты подключаются напрямую к MPLS-магистрали поставщика услуг Интернета, и каждому сайту выделяется полоса пропускания, используемая для взаимодействия по каналу глобальной сети с MPLS-облаком. Не существует ни сетевого концентратора, ни центрального сайта для управления IP-маршрутизацией. На следующем рисунке показана простая сеть, основанная на технологии MPLS.</span><span class="sxs-lookup"><span data-stu-id="411e5-p103">In a Multiprotocol Label Switching (MPLS) network, all sites are connected by a full-mesh. That is, all sites are connected directly to the MPLS backbone of the Internet service provider, and each site is provisioned bandwidth to be used across a WAN link to the MPLS cloud. There is no network hub or central site to control IP routing. The following figure shows a simple network based on MPLS technology.</span></span>

<span data-ttu-id="411e5-113">**Пример сети MPLS**</span><span class="sxs-lookup"><span data-stu-id="411e5-113">**Example MPLS network**</span></span>

![Контроль допуска звонков с многопротокольной коммутацией по меткам (MPLS)](../../media/CAC_MPLS_1.jpg)

<span data-ttu-id="411e5-p104">Чтобы развернуть контроль допуска звонков в сети MPLS, требуется создать область сети, представляющую облако MPLS, и создать сетевой сайт, представляющий каждый вспомогательный сайт MPLS. На следующем рисунке показано, как следует настроить область сети и сетевые сайты, чтобы они представляли пример сети MPLS на предыдущем рисунке. Ограничения для общей пропускной способности и пропускной способности сеанса основываются на емкости канала связи глобальной сети от каждого сетевого сайта к области сети, которая представляет облако MPLS.</span><span class="sxs-lookup"><span data-stu-id="411e5-p104">To deploy call admission control (CAC) in an MPLS network, you create a network region to represent the MPLS cloud, and create a network site to represent each MPLS satellite site. The following figure illustrates how the network region and network sites should be configured to represent the example MPLS network in the previous figure. The overall bandwidth limits and bandwidth session limits are then based on the capacity of the WAN link from each network site to the network region that represents the MPLS cloud.</span></span>

<span data-ttu-id="411e5-118">**Область сети и сетевые сайты для сети MPLS**</span><span class="sxs-lookup"><span data-stu-id="411e5-118">**Network region and network sites for an MPLS network**</span></span>

![Контроль допуска звонков с многопротокольной коммутацией по меткам (MPLS) — схема](../../media/CAC_MPLS_2.jpg)

## <a name="call-admission-control-on-a-sip-trunk"></a><span data-ttu-id="411e5-120">Контроль допуска звонков на канале SIP</span><span class="sxs-lookup"><span data-stu-id="411e5-120">Call admission control on a SIP trunk</span></span>

<span data-ttu-id="411e5-p105">Для развертывания контроля допуска звонков в магистрали SIP создается сетевой сайт, который представляет поставщика услуг интернет-телефонии (ITSP). Для применения значений политики пропускной способности в магистрали SIP создается межсайтовая политика между сетевым сайтом на предприятии и сетевым сайтом, созданным для представления ITSP.</span><span class="sxs-lookup"><span data-stu-id="411e5-p105">To deploy call admission control (CAC) on a SIP trunk, you create a network site to represent the Internet telephony service provider (ITSP). To apply bandwidth policy values on the SIP trunk, you create an inter-site policy between the network site in your enterprise and the network site that you create to represent the ITSP.</span></span>

<span data-ttu-id="411e5-123">На следующем рисунке показан пример развертывания контроля допуска звонков в магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="411e5-123">The following figure shows an example CAC deployment on a SIP trunk.</span></span>

<span data-ttu-id="411e5-124">**Конфигурация контроля допуска звонков в магистрали SIP**</span><span class="sxs-lookup"><span data-stu-id="411e5-124">**CAC configuration on a SIP trunk**</span></span>

![Контроль допуска звонков с распределением каналов SIP (схема)](../../media/CAC_SIP_trunk_1.jpg)

<span data-ttu-id="411e5-126">Чтобы настроить контроль допуска звонков в магистрали SIP, во время развертывания контроля допуска звонков необходимо выполнить следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="411e5-126">To configure CAC on a SIP trunk, you will have to perform the following tasks during CAC deployment:</span></span>

1. <span data-ttu-id="411e5-p106">Создать сетевой сайт для представления поставщика услуг интернет-телефонии (ITSP). Вписать этот сетевой сайт в соответствующий сетевую область и выделить для этого сетевого сайта нулевую пропускную способность для аудио и видео. Дополнительные сведения см. в разделе [Configure Network Sites for CAC](https://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx) документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="411e5-p106">Create a network site to represent the ITSP. Associate the network site to an appropriate network region, and allocate bandwidth of zero for audio and video for this network site. For details, see [Configure Network Sites for CAC](https://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx) in the Deployment documentation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="411e5-p107">Для ITSP конфигурация этого сетевого сайта не функциональна. Значения политики пропускной способности фактически применяются в шаге 2.</span><span class="sxs-lookup"><span data-stu-id="411e5-p107">For the ITSP, this network site configuration is not functional. Bandwidth policy values are actually applied in step 2.</span></span>

2. <span data-ttu-id="411e5-132">Создать межсайтовую связь для магистрали SIP с помощью соответствующих значений параметров для сайта, созданного на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="411e5-132">Create an inter-site link for the SIP trunk using the relevant parameter values for the site you created in step 1.</span></span> <span data-ttu-id="411e5-133">Например, можно указать имя этого сетевого сайта на предприятии в качестве значения параметра NetworkSiteID1, а имя сетевого сайта ITSP — в качестве значения параметра NetworkSiteID2.</span><span class="sxs-lookup"><span data-stu-id="411e5-133">For example, use the name of the network site in your enterprise as the value of the NetworkSiteID1 parameter, and the ITSP network site as the value of the NetworkSiteID2 parameter.</span></span> <span data-ttu-id="411e5-134">Дополнительные сведения можно найти [в разделе Создание политик межсайтовой сети в Skype для бизнеса Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) в документации по развертыванию и на странице [New-кснетворкинтерситеполици](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="411e5-134">For details, see [Create network intersite policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) in the Deployment documentation, and [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps).</span></span>

3. <span data-ttu-id="411e5-135">Получение IP-адреса точки оконечного напряжения (СКБ) мультимедиа контроллера границ сеанса из ИТСП.</span><span class="sxs-lookup"><span data-stu-id="411e5-135">Get the IP address of the Session Border Controller's (SCB) Media Termination Point from your ITSP.</span></span> <span data-ttu-id="411e5-136">Добавить этот IP-адрес с маской подсети 32 к сетевому сайту, представляющему ITSP.</span><span class="sxs-lookup"><span data-stu-id="411e5-136">Add that IP address with a subnet mask of 32 to the network site that represents the ITSP.</span></span> <span data-ttu-id="411e5-137">Дополнительные сведения см. в разделе [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span><span class="sxs-lookup"><span data-stu-id="411e5-137">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>

## <a name="call-admission-control-with-a-third-party-pstn-gateway-or-pbx"></a><span data-ttu-id="411e5-138">Контроль допуска звонков с помощью стороннего шлюза ТСОП или УАТС</span><span class="sxs-lookup"><span data-stu-id="411e5-138">Call admission control with a third-party PSTN gateway or PBX</span></span>

<span data-ttu-id="411e5-139">В этой статье описаны примеры того, как управление допуском звонков (CAC) может быть развернуто на связи между интерфейсом шлюза сервера-посредника и сторонним шлюзом коммутируемой телефонной сети или частным подключением (АТС).</span><span class="sxs-lookup"><span data-stu-id="411e5-139">This topic describes examples of how call admission control (CAC) can be deployed on the link between the Mediation Server's gateway interface and a third-party public switched telephone network (PSTN) gateway or private branch exchange (PBX).</span></span>

### <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a><span data-ttu-id="411e5-140">Случай 1. Контроль допуска звонков между сервером-посредником и шлюзом ТСОП</span><span class="sxs-lookup"><span data-stu-id="411e5-140">Case 1: CAC between the Mediation Server and a PSTN gateway</span></span>

<span data-ttu-id="411e5-141">Сервер CAC может быть развернут на канале глобальной сети с помощью интерфейса шлюза сервера-партнера, который является сторонним ОФИСным или КОММУТИРУЕМым шлюзом.</span><span class="sxs-lookup"><span data-stu-id="411e5-141">CAC can be deployed on the WAN link from the Mediation Server's gateway interface to a third-party PBX or PSTN gateway.</span></span>

<span data-ttu-id="411e5-142">**Случай 1. Контроль допуска звонков между сервером-посредником и шлюзом ТСОП**</span><span class="sxs-lookup"><span data-stu-id="411e5-142">**Case 1: CAC between the Mediation Server and a PSTN gateway**</span></span>

![Случай 1. Контроль допуска звонков между сервером-посредником и шлюзом ТСОП](../../media/CAC_gateways_1.jpg)

<span data-ttu-id="411e5-144">В этом примере для сервера-посредника и шлюза PSTN применяется CAC.</span><span class="sxs-lookup"><span data-stu-id="411e5-144">In this example, CAC is applied between the Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="411e5-145">Если пользователь клиента Skype для бизнеса на сетевом сайте 1 размещает КОММУТИРУЕМый Звонок через шлюз PSTN в сетевом сайте 2, мультимедиа проходит через ГЛОБАЛЬную сеть.</span><span class="sxs-lookup"><span data-stu-id="411e5-145">If a Skype for Business client user at Network Site 1 places a PSTN call through the PSTN gateway in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="411e5-146">Поэтому для каждого сеанса ТСОП выполняются две проверки контроля допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="411e5-146">Therefore, two CAC checks are performed for each PSTN session:</span></span>

- <span data-ttu-id="411e5-147">Между клиентским приложением Skype для бизнеса и сервером-посредником</span><span class="sxs-lookup"><span data-stu-id="411e5-147">Between the Skype for Business client application and the Mediation Server</span></span>

- <span data-ttu-id="411e5-148">Между сервером исправлений и шлюзом PSTN</span><span class="sxs-lookup"><span data-stu-id="411e5-148">Between the Mediation Server and the PSTN gateway</span></span>

<span data-ttu-id="411e5-149">Проверки выполняются как для входящих звонков ТСОП, поступающих в клиент на сетевом сайте 1, так и для исходящих звонков ТСОП из клиентского приложения на сетевом сайте 1.</span><span class="sxs-lookup"><span data-stu-id="411e5-149">This works for both incoming PSTN calls to a client in Network Site 1, and for outgoing PSTN calls originating from a client application in Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="411e5-150">Убедитесь в том, что IP-подсеть, к которой относится шлюз ТСОП, настроена и связана с сетевым сайтом 2.</span><span class="sxs-lookup"><span data-stu-id="411e5-150">Make sure that the IP subnet that the PSTN gateway belongs to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="411e5-151">Убедитесь, что IP-подсеть, к которой принадлежат оба интерфейса сервера-посредника, настроена и соответствует сетевому сайту 1.</span><span class="sxs-lookup"><span data-stu-id="411e5-151">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="411e5-152">Дополнительные сведения см. в разделе [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span><span class="sxs-lookup"><span data-stu-id="411e5-152">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>

### <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a><span data-ttu-id="411e5-153">Случай 2: CAC между сервером-посредником и сторонней АТС с точкой завершения мультимедиа</span><span class="sxs-lookup"><span data-stu-id="411e5-153">Case 2: CAC between the Mediation Server and a third-party PBX with Media Termination Point</span></span>

<span data-ttu-id="411e5-154">Эта конфигурация аналогична случаю 1.</span><span class="sxs-lookup"><span data-stu-id="411e5-154">This configuration is similar to Case 1.</span></span> <span data-ttu-id="411e5-155">В обоих случаях сервер-посредник определяет, какое устройство завершает работу с мультимедиа на противоположном конце ссылки WAN, и IP-адрес шлюза PSTN или УАТС с точкой завершения (MTP) настроен на сервере-посреднике в качестве следующего прыжка.</span><span class="sxs-lookup"><span data-stu-id="411e5-155">In both the cases, the Mediation Server knows what device terminates media at the opposite end of the WAN link, and the IP address of the PSTN gateway or PBX with Media Termination Point (MTP) is configured on the Mediation Server as the next hop.</span></span>

<span data-ttu-id="411e5-156">**Случай 2. Контроль допуска звонков между сервером-посредником и сторонней УАТС с точкой MTP**</span><span class="sxs-lookup"><span data-stu-id="411e5-156">**Case 2: CAC between the Mediation Server and a third-party PBX with MTP**</span></span>

![Случай 2. Контроль допуска звонков между сервером-посредником и УАТС с точкой Media Termination Point (MTP)](../../media/CAC_gateways_2.jpg)

<span data-ttu-id="411e5-158">В этом примере для сервера-посредника и УАТС (MTP) применяется CAC.</span><span class="sxs-lookup"><span data-stu-id="411e5-158">In this example, CAC is applied between the Mediation Server and the PBX/MTP.</span></span> <span data-ttu-id="411e5-159">Если пользователь клиента Skype для бизнеса на сетевом сайте 1 помещает PSTN-Звонок через УАТС/MTP, расположенную на сайте сети 2, мультимедиа передается через ГЛОБАЛЬную сеть.</span><span class="sxs-lookup"><span data-stu-id="411e5-159">If a Skype for Business client user at the Network Site 1 places a PSTN call through the PBX/MTP located in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="411e5-160">Поэтому для каждого сеанса ТСОП выполняются две проверки контроля допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="411e5-160">Therefore, for each PSTN session two CAC checks are performed:</span></span>

- <span data-ttu-id="411e5-161">Между клиентским приложением Skype для бизнеса и сервером-посредником</span><span class="sxs-lookup"><span data-stu-id="411e5-161">Between the Skype for Business client application and the Mediation Server</span></span>

- <span data-ttu-id="411e5-162">Между сервером-посредником и УАТС/MTP</span><span class="sxs-lookup"><span data-stu-id="411e5-162">Between the Mediation Server and the PBX/MTP</span></span>

<span data-ttu-id="411e5-163">Проверки выполняются как для входящих звонков ТСОП, поступающих в клиент на сетевом сайте 1, так и для исходящих звонков ТСОП из клиента на сетевом сайте 1.</span><span class="sxs-lookup"><span data-stu-id="411e5-163">This works for both incoming PSTN calls to a client in Network Site 1, and outgoing PSTN calls originating from a client in Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="411e5-164">Убедитесь в том, что IP-подсеть, к которой относится точка MTP, настроена и связана с сетевым сайтом 2.</span><span class="sxs-lookup"><span data-stu-id="411e5-164">Make sure that the IP subnet that the MTP belongs to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="411e5-165">Убедитесь, что IP-подсеть, к которой принадлежат оба интерфейса сервера-посредника, настроена и соответствует сетевому сайту 1.</span><span class="sxs-lookup"><span data-stu-id="411e5-165">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="411e5-166">Дополнительные сведения см. в разделе [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span><span class="sxs-lookup"><span data-stu-id="411e5-166">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>

### <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a><span data-ttu-id="411e5-167">Случай 3: CAC между сервером-посредником и сторонней АТС без точки завершения мультимедиа</span><span class="sxs-lookup"><span data-stu-id="411e5-167">Case 3: CAC between the Mediation Server and a third-party PBX without a Media Termination Point</span></span>

<span data-ttu-id="411e5-168">Случай 3 несколько отличается от первых двух.</span><span class="sxs-lookup"><span data-stu-id="411e5-168">Case 3 is slightly different from the first two cases.</span></span> <span data-ttu-id="411e5-169">Если в сторонней УАТС нет MTP, то для запроса исходящего сеанса на независимую АТС не удается определить, в каком месте на границах УАТС будет прерываться мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="411e5-169">If there is no MTP on the third-party PBX, for an outgoing session request to the third-party PBX the Mediation Server does not know where media will terminate in the PBX boundary.</span></span> <span data-ttu-id="411e5-170">В этом случае мультимедиа перетекает прямо между сервером-посредником и сторонним устройством конечной точки.</span><span class="sxs-lookup"><span data-stu-id="411e5-170">In this case, the media flows directly between the Mediation Server and the third-party endpoint device.</span></span>

<span data-ttu-id="411e5-171">**Случай 3. Контроль допуска звонков между сервером-посредником и сторонней УАТС без точки MTP**</span><span class="sxs-lookup"><span data-stu-id="411e5-171">**Case 3: CAC between the Mediation Server and a third-party PBX without MTP**</span></span>

![Случай 3. Контроль допуска звонков между сервером-посредником и УАТС без точки Media Termination Point (MTP)](../../media/CAC_gateways_3.jpg)

<span data-ttu-id="411e5-173">В этом примере, если пользователь клиента Skype для бизнеса на сетевом сайте 1 размещает вызов пользователя через УАТС, сервер-посредник может выполнять проверки с помощью CAC только для прокси-сервера (между клиентским приложением Skype для бизнеса и сервером исправлений).</span><span class="sxs-lookup"><span data-stu-id="411e5-173">In this example, if a Skype for Business client user at Network Site 1 places a call to a user through the PBX, the Mediation Server is able to perform CAC checks only on the proxy leg (between the Skype for Business client application and Mediation Server).</span></span> <span data-ttu-id="411e5-174">Поскольку сервер-посредник не имеет сведений о устройстве конечной точки во время запроса сеанса, перед установкой звонка невозможно выполнить проверки CAC на канале WAN (между сервером-посредником и сторонней конечной точкой).</span><span class="sxs-lookup"><span data-stu-id="411e5-174">Because the Mediation Server does not have information about the endpoint device while the session is being requested, CAC checks cannot be performed on the WAN link (between the Mediation Server and the third-party endpoint) prior to call establishment.</span></span> <span data-ttu-id="411e5-175">Однако после того, как сеанс будет установлен, сервер исправлений облегчает учет пропускной способности, используемой в канале.</span><span class="sxs-lookup"><span data-stu-id="411e5-175">After the session is established, however, the Mediation Server facilitates in accounting for the bandwidth used on the trunk.</span></span>

<span data-ttu-id="411e5-176">Для вызовов, инициированных из сторонней конечной точки, сведения об этом устройстве будут доступны на момент запроса сеанса, а проверка CAC может выполняться на обеих сторонах сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="411e5-176">For calls that originate from the third-party endpoint, the information about that endpoint device is available at the time of session request and CAC check can be performed on both the sides of the Mediation Server.</span></span>

> [!NOTE]
> <span data-ttu-id="411e5-177">Убедитесь в том, что IP-подсеть, к которой относятся устройства конечных точек, настроена и связана с сетевым сайтом 2.</span><span class="sxs-lookup"><span data-stu-id="411e5-177">Make sure that the IP subnet that the endpoint devices belong to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="411e5-178">Убедитесь, что IP-подсеть, к которой принадлежат оба интерфейса сервера-посредника, настроена и соответствует сетевому сайту 1.</span><span class="sxs-lookup"><span data-stu-id="411e5-178">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="411e5-179">Дополнительные сведения см. в разделе [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span><span class="sxs-lookup"><span data-stu-id="411e5-179">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>


