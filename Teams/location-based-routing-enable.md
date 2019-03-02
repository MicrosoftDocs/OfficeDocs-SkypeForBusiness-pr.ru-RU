---
title: Включение функции "Маршрутизация на основе расположения" для прямой маршрутизации
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: Узнайте, как включить маршрутизации на основе расположения для прямой маршрутизации.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 854f0fefc006c02bc07c73cd4519b943411094f5
ms.sourcegitcommit: 59eda0c17ff39a3e6632810391d78bbadc214419
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2019
ms.locfileid: "30352548"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="52d23-103">Включение функции "Маршрутизация на основе расположения" для прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="52d23-103">Enable Location-Based Routing for Direct Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="52d23-104">Прежде чем выполнять действия, описанные в этой статье, убедитесь, что вы чтение [Plan Location-Based маршрутизации для прямого](location-based-routing-plan.md) и выполнить действия, описанные в [настроить параметры сети для маршрутизации на основе местоположения](location-based-routing-configure-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="52d23-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="52d23-105">В этой статье описывается, как включить маршрутизации на основе расположения для прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="52d23-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="52d23-106">После развертывания прямой маршрутизации телефонной системы и настройка области сети, сайтов и подсетей, вы готовы для включения маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="52d23-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="52d23-107">Чтобы выполнить действия, описанные в этой статье, вам потребуются некоторые навыки работы с помощью командлетов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="52d23-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="52d23-108">Для получения дополнительных сведений см [Команды PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="52d23-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="52d23-109">Вам необходимо включить зависимостью от расположения маршрутизации для следующих:</span><span class="sxs-lookup"><span data-stu-id="52d23-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="52d23-110">Пользователи</span><span class="sxs-lookup"><span data-stu-id="52d23-110">Users</span></span>
- <span data-ttu-id="52d23-111">Сетевые узлы</span><span class="sxs-lookup"><span data-stu-id="52d23-111">Network sites</span></span>
- <span data-ttu-id="52d23-112">Шлюзов</span><span class="sxs-lookup"><span data-stu-id="52d23-112">Gateway configurations</span></span>
- <span data-ttu-id="52d23-113">Вызов политик</span><span class="sxs-lookup"><span data-stu-id="52d23-113">Calling policies</span></span>

## <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="52d23-114">Включение маршрутизации на основе расположения для пользователей</span><span class="sxs-lookup"><span data-stu-id="52d23-114">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="52d23-115">Использование ``Set-CsOnlinePstnUsages`` командлет, чтобы задать случаев использования PSTN.</span><span class="sxs-lookup"><span data-stu-id="52d23-115">Use the ``Set-CsOnlinePstnUsages`` cmdlet to set PSTN usages.</span></span> <span data-ttu-id="52d23-116">Для нескольких вариантов использования разделяются запятыми каждого использования.</span><span class="sxs-lookup"><span data-stu-id="52d23-116">For multiple usages, separate each usage with a comma.</span></span>

    ```
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="52d23-117">Например:</span><span class="sxs-lookup"><span data-stu-id="52d23-117">For example:</span></span>
    ```
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="52d23-118">Использование ``New-CsOnlineVoiceRoutingPolicy`` командлет, чтобы создать политику маршрутизации голосовой связи, чтобы связать пользователя с соответствующих случаев использования PSTN.</span><span class="sxs-lookup"><span data-stu-id="52d23-118">Use the ``New-CsOnlineVoiceRoutingPolicy`` cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="52d23-119">При назначении политики маршрутизации голосовых данных случаев использования PSTN, убедитесь, что вы выполните одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="52d23-119">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="52d23-120">Используйте случаев использования PSTN, связанный со маршрутов голосовых вызовов, которые используют локального шлюза ТСОП для сайта</span><span class="sxs-lookup"><span data-stu-id="52d23-120">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="52d23-121">С помощью использования ТСОП, связанный со маршрутов голосовых вызовов, использующих шлюз ТСОП, расположенной в области, где ограничений на основе местоположения маршрутизации не требуется.</span><span class="sxs-lookup"><span data-stu-id="52d23-121">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="52d23-122">В этом примере мы создайте две новые политики маршрутизации голосовых данных и назначать им случаев использования PSTN.</span><span class="sxs-lookup"><span data-stu-id="52d23-122">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="52d23-123">В следующей таблице показаны политики маршрутизации голосовой связи, определенных в этом примере.</span><span class="sxs-lookup"><span data-stu-id="52d23-123">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="52d23-124">Политики маршрутизации 1 голосовой связи</span><span class="sxs-lookup"><span data-stu-id="52d23-124">Voice routing policy 1</span></span>|<span data-ttu-id="52d23-125">Политики маршрутизации 2 голосовой связи</span><span class="sxs-lookup"><span data-stu-id="52d23-125">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="52d23-126">Идентификатор политики голосовой связи через Интернет</span><span class="sxs-lookup"><span data-stu-id="52d23-126">Online voice policy ID</span></span>   |<span data-ttu-id="52d23-127">Delhi политики маршрутизации голосовой связи через Интернет</span><span class="sxs-lookup"><span data-stu-id="52d23-127">Delhi online voice routing policy</span></span>   |<span data-ttu-id="52d23-128">Hyderabad политики маршрутизации голосовой связи через Интернет</span><span class="sxs-lookup"><span data-stu-id="52d23-128">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="52d23-129">Online использования ТСОП</span><span class="sxs-lookup"><span data-stu-id="52d23-129">Online PSTN usages</span></span>  |<span data-ttu-id="52d23-130">Междугородный</span><span class="sxs-lookup"><span data-stu-id="52d23-130">Long Distance</span></span>  |<span data-ttu-id="52d23-131">Междугородный, локальные, внутренний</span><span class="sxs-lookup"><span data-stu-id="52d23-131">Long Distance, Local, Internal</span></span>  |

    <span data-ttu-id="52d23-132">Дополнительные сведения содержатся в разделе [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="52d23-132">For more information, see [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>
3. <span data-ttu-id="52d23-133">Использование ``Grant-CsOnlineVoiceRoutingPolicy`` командлет, чтобы связать Интернет-версия голосовой маршрутизации политик для пользователей, которым требуется маршрутизации ограничения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="52d23-133">Use the ``Grant-CsOnlineVoiceRoutingPolicy`` cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="52d23-134">Включение маршрутизации на основе расположения для сетевых узлов</span><span class="sxs-lookup"><span data-stu-id="52d23-134">Enable Location-Based Routing for network sites</span></span>
1.  <span data-ttu-id="52d23-135">Использование ``Set-CsTenantNetworkSite`` используется для включения маршрутизации на основе расположения и связать голосовой политики маршрутизации для сетевых сайтов, которые необходимо применить ограничения по маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="52d23-135">Use the ``Set-CsTenantNetworkSite`` cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="52d23-136">В этом примере мы Включение маршрутизации на основе расположения для узла Delhi и Hyderabad сайта.</span><span class="sxs-lookup"><span data-stu-id="52d23-136">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="52d23-137">Ниже указаны сайты, включены для маршрутизации на основе расположения в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="52d23-137">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="52d23-138">Узел 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="52d23-138">Site 1 (Delhi)</span></span>  |<span data-ttu-id="52d23-139">Узел 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="52d23-139">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="52d23-140">Имя сайта</span><span class="sxs-lookup"><span data-stu-id="52d23-140">Site name</span></span>    |<span data-ttu-id="52d23-141">Узел 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="52d23-141">Site 1 (Delhi)</span></span>    |<span data-ttu-id="52d23-142">Узел 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="52d23-142">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="52d23-143">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="52d23-143">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="52d23-144">True</span><span class="sxs-lookup"><span data-stu-id="52d23-144">True</span></span>    |<span data-ttu-id="52d23-145">True</span><span class="sxs-lookup"><span data-stu-id="52d23-145">True</span></span>    |
    |<span data-ttu-id="52d23-146">Подсети</span><span class="sxs-lookup"><span data-stu-id="52d23-146">Subnets</span></span>     |<span data-ttu-id="52d23-147">Подсеть 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="52d23-147">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="52d23-148">Подсеть 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="52d23-148">Subnet 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="52d23-149">Включение маршрутизации на основе расположения для шлюзов</span><span class="sxs-lookup"><span data-stu-id="52d23-149">Enable Location-Based Routing for gateways</span></span>
1. <span data-ttu-id="52d23-150">Использование ``New-CsOnlinePstnGateway`` командлет, чтобы создать шлюз для каждого шлюза или сетевого узла.</span><span class="sxs-lookup"><span data-stu-id="52d23-150">Use the ``New-CsOnlinePstnGateway`` cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignallingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="52d23-151">Если несколько шлюзов, связанные с системой (например, шлюзом или УАТС), измените каждый шлюз для включения ограничений на основе местоположения маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="52d23-151">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="52d23-152">В этом примере мы создадим одной конфигурации шлюза для каждого шлюза.</span><span class="sxs-lookup"><span data-stu-id="52d23-152">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignallingPort 5067 
    ```
    <span data-ttu-id="52d23-153">Дополнительные сведения можно [Настроить прямой маршрутизации](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="52d23-153">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="52d23-154">Использование ``Set-CSOnlinePSTNGateway`` используется для включения маршрутизации на основе расположения для вашей шлюзов, которые необходимо применить ограничения по маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="52d23-154">Use the ``Set-CSOnlinePSTNGateway`` cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="52d23-155">Включение маршрутизации на основе расположения для шлюзов, которые маршрутизации вызовов для шлюзов PSTN, маршрутизировать вызовы в ТСОП и сопоставить сетевого узла, где находится шлюз.</span><span class="sxs-lookup"><span data-stu-id="52d23-155">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="52d23-156">В этом примере мы Включение маршрутизации на основе расположения для каждого шлюза, сопоставленные для шлюзов ТСОП на веб-сайтах Delhi и Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="52d23-156">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    <span data-ttu-id="52d23-157">Не Включение маршрутизации на основе расположения для шлюзов, которые не маршрутизировать вызовы в ТСОП.</span><span class="sxs-lookup"><span data-stu-id="52d23-157">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="52d23-158">Тем не менее необходимо связать шлюза для сетевого узла, где расположена система.</span><span class="sxs-lookup"><span data-stu-id="52d23-158">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="52d23-159">Это из-за ограничений на основе местоположения маршрутизации должны применяться для вызовов ТСОП достигает конечные точки, подключенные через этот шлюз.</span><span class="sxs-lookup"><span data-stu-id="52d23-159">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="52d23-160">В этом примере зависимостью от расположения маршрутизации не включен для каждого шлюза, содержащего АТС на веб-сайтах Delhi и Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="52d23-160">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    <span data-ttu-id="52d23-161">Конечные точки, подключенные к системам, которые не маршрутизировать вызовы в ТСОП (например, УАТС) будут иметь аналогичные ограничения как конечных точек пользователям группы с поддержкой маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="52d23-161">Endpoints connected to systems that don't route calls to the PSTN (for example, a PBX) will have similar restrictions as endpoints of Teams users enabled for Location-Based Routing.</span></span> <span data-ttu-id="52d23-162">Это означает, что эти пользователи могут выполнять и принимать вызовы, связанные с группами пользователей независимо от расположения пользователя.</span><span class="sxs-lookup"><span data-stu-id="52d23-162">This means that these users can place and receive calls to and from Teams users regardless of the user’s location.</span></span> <span data-ttu-id="52d23-163">Пользователь может звонить и принимать звонки, чтобы и других систем, которые не маршрутизировать вызовы Телефонной сети общего пользования (например, конечную точку, подключенный к УАТС различных) независимо от сетевого узла, с которым связана системы.</span><span class="sxs-lookup"><span data-stu-id="52d23-163">They can also place and receive calls to and from other systems that don't route calls to the PSTN network (for example, an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="52d23-164">Все входящие вызовы, исходящие вызовы, перевод звонков и переадресацию звонков, связанных с конечными точками PSTN будет использоваться принудительным ограничением маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="52d23-164">All inbound calls, outbound calls, call transfers and call forwarding that involve PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="52d23-165">Эти вызовы необходимо использовать только шлюзы ТСОП, определенные как локальный для таких систем.</span><span class="sxs-lookup"><span data-stu-id="52d23-165">These calls must use only PSTN gateways that are defined as local to such systems.</span></span> 

    <span data-ttu-id="52d23-166">В следующей таблице показаны настройки шлюза четыре шлюзов в двух различных сетевых сайтов: два, подключенных к шлюзы ТСОП и по два подключенных к УАТС.</span><span class="sxs-lookup"><span data-stu-id="52d23-166">The following table shows the gateway configuration of four gateways in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span> 

    ||<span data-ttu-id="52d23-167">GatewaySiteLbrEnabled</span><span class="sxs-lookup"><span data-stu-id="52d23-167">GatewaySiteLbrEnabled</span></span>   |<span data-ttu-id="52d23-168">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="52d23-168">NetworkSiteID</span></span>  |
    |---------|---------|---------|
    |<span data-ttu-id="52d23-169">DEL PstnGateway:Gateway 1-Себестоимости</span><span class="sxs-lookup"><span data-stu-id="52d23-169">PstnGateway:Gateway 1 DEL-GW</span></span>    |    <span data-ttu-id="52d23-170">True</span><span class="sxs-lookup"><span data-stu-id="52d23-170">True</span></span>     |   <span data-ttu-id="52d23-171">Узел 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="52d23-171">Site 1 (Delhi)</span></span>      |
    |<span data-ttu-id="52d23-172">PstnGateway:Gateway 2 HYD-Себестоимости</span><span class="sxs-lookup"><span data-stu-id="52d23-172">PstnGateway:Gateway 2 HYD-GW</span></span>     |   <span data-ttu-id="52d23-173">True</span><span class="sxs-lookup"><span data-stu-id="52d23-173">True</span></span>      |      <span data-ttu-id="52d23-174">Узел 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="52d23-174">Site 2 (Hyderabad)</span></span>   |
    |<span data-ttu-id="52d23-175">DEL PstnGateway:Gateway 3-УАТС</span><span class="sxs-lookup"><span data-stu-id="52d23-175">PstnGateway:Gateway 3 DEL-PBX</span></span>    |    <span data-ttu-id="52d23-176">False</span><span class="sxs-lookup"><span data-stu-id="52d23-176">False</span></span>     |     <span data-ttu-id="52d23-177">Узел 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="52d23-177">Site 1 (Delhi)</span></span>    |
    |<span data-ttu-id="52d23-178">HYD PstnGateway:Gateway 4-УАТС</span><span class="sxs-lookup"><span data-stu-id="52d23-178">PstnGateway:Gateway 4 HYD-PBX</span></span>    |    <span data-ttu-id="52d23-179">False</span><span class="sxs-lookup"><span data-stu-id="52d23-179">False</span></span>     |    <span data-ttu-id="52d23-180">Узел 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="52d23-180">Site 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="52d23-181">Включение маршрутизации на основе расположения для вызова политик</span><span class="sxs-lookup"><span data-stu-id="52d23-181">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="52d23-182">Для применения параметров маршрутизации на основе расположения для отдельных пользователей, настройте политику голосовой связи пользователей, чтобы запретить международную PTSN обхода.</span><span class="sxs-lookup"><span data-stu-id="52d23-182">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="52d23-183">Использование ``Grant-CsTeamsCallingPolicy`` пропускать командлет, чтобы включить маршрутизация на основе местоположения, устраняя международную PSTN.</span><span class="sxs-lookup"><span data-stu-id="52d23-183">Use the ``Grant-CsTeamsCallingPolicy`` cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="52d23-184">В этом примере мы запретить PSTN международную сервера-посредника для пользователя User1 вызов политик.</span><span class="sxs-lookup"><span data-stu-id="52d23-184">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```
Grant-CsTeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

### <a name="related-topics"></a><span data-ttu-id="52d23-185">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="52d23-185">Related topics</span></span>
- [<span data-ttu-id="52d23-186">Планирование маршрутизации на основе расположения для прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="52d23-186">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="52d23-187">Настройка параметров сети для маршрутизации на основе расположения</span><span class="sxs-lookup"><span data-stu-id="52d23-187">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="52d23-188">Терминология маршрутизации на основе расположения</span><span class="sxs-lookup"><span data-stu-id="52d23-188">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)
