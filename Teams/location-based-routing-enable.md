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
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: e68b239d00e67d942f80a259facb87c80ddf2a55
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886034"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="3d765-103">Включение функции "Маршрутизация на основе расположения" для прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="3d765-103">Enable Location-Based Routing for Direct Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="3d765-104">Прежде чем выполнять действия, описанные в этой статье, убедитесь, что вы чтение [Plan Location-Based маршрутизации для прямого](location-based-routing-plan.md) и выполнить действия, описанные в [настроить параметры сети для маршрутизации на основе местоположения](location-based-routing-configure-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="3d765-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="3d765-105">В этой статье описывается, как включить маршрутизации на основе расположения для прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="3d765-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="3d765-106">После развертывания прямой маршрутизации телефонной системы и настройка области сети, сайтов и подсетей, вы готовы для включения маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="3d765-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="3d765-107">Чтобы выполнить действия, описанные в этой статье, вам потребуются некоторые навыки работы с помощью командлетов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d765-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="3d765-108">Для получения дополнительных сведений см [Команды PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3d765-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="3d765-109">Вам необходимо включить зависимостью от расположения маршрутизации для следующих:</span><span class="sxs-lookup"><span data-stu-id="3d765-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="3d765-110">Пользователи</span><span class="sxs-lookup"><span data-stu-id="3d765-110">Users</span></span>
- <span data-ttu-id="3d765-111">Сетевые узлы</span><span class="sxs-lookup"><span data-stu-id="3d765-111">Network sites</span></span>
- <span data-ttu-id="3d765-112">Шлюзов</span><span class="sxs-lookup"><span data-stu-id="3d765-112">Gateway configurations</span></span>
- <span data-ttu-id="3d765-113">Вызов политик</span><span class="sxs-lookup"><span data-stu-id="3d765-113">Calling policies</span></span>

## <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="3d765-114">Включение маршрутизации на основе расположения для пользователей</span><span class="sxs-lookup"><span data-stu-id="3d765-114">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="3d765-115">Командлет [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) случаев использования PSTN.</span><span class="sxs-lookup"><span data-stu-id="3d765-115">Use the [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="3d765-116">Для нескольких вариантов использования разделяются запятыми каждого использования.</span><span class="sxs-lookup"><span data-stu-id="3d765-116">For multiple usages, separate each usage with a comma.</span></span>

    ```
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="3d765-117">Например:</span><span class="sxs-lookup"><span data-stu-id="3d765-117">For example:</span></span>
    ```
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="3d765-118">Командлет [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) используется для создания политики маршрутизации голосовой связи, чтобы связать пользователя с соответствующих случаев использования PSTN.</span><span class="sxs-lookup"><span data-stu-id="3d765-118">Use the [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="3d765-119">При назначении политики маршрутизации голосовых данных случаев использования PSTN, убедитесь, что вы выполните одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="3d765-119">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="3d765-120">Используйте случаев использования PSTN, связанный со маршрутов голосовых вызовов, которые используют локального шлюза ТСОП для сайта</span><span class="sxs-lookup"><span data-stu-id="3d765-120">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="3d765-121">С помощью использования ТСОП, связанный со маршрутов голосовых вызовов, использующих шлюз ТСОП, расположенной в области, где ограничений на основе местоположения маршрутизации не требуется.</span><span class="sxs-lookup"><span data-stu-id="3d765-121">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="3d765-122">В этом примере мы создайте две новые политики маршрутизации голосовых данных и назначать им случаев использования PSTN.</span><span class="sxs-lookup"><span data-stu-id="3d765-122">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="3d765-123">В следующей таблице показаны политики маршрутизации голосовой связи, определенных в этом примере.</span><span class="sxs-lookup"><span data-stu-id="3d765-123">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="3d765-124">Политики маршрутизации 1 голосовой связи</span><span class="sxs-lookup"><span data-stu-id="3d765-124">Voice routing policy 1</span></span>|<span data-ttu-id="3d765-125">Политики маршрутизации 2 голосовой связи</span><span class="sxs-lookup"><span data-stu-id="3d765-125">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="3d765-126">Идентификатор политики голосовой связи через Интернет</span><span class="sxs-lookup"><span data-stu-id="3d765-126">Online voice policy ID</span></span>   |<span data-ttu-id="3d765-127">Delhi политики маршрутизации голосовой связи через Интернет</span><span class="sxs-lookup"><span data-stu-id="3d765-127">Delhi online voice routing policy</span></span>   |<span data-ttu-id="3d765-128">Hyderabad политики маршрутизации голосовой связи через Интернет</span><span class="sxs-lookup"><span data-stu-id="3d765-128">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="3d765-129">Online использования ТСОП</span><span class="sxs-lookup"><span data-stu-id="3d765-129">Online PSTN usages</span></span>  |<span data-ttu-id="3d765-130">Междугородный</span><span class="sxs-lookup"><span data-stu-id="3d765-130">Long Distance</span></span>  |<span data-ttu-id="3d765-131">Междугородный, локальные, внутренний</span><span class="sxs-lookup"><span data-stu-id="3d765-131">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="3d765-132">Командлет [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) связывание маршрутизации политики сети голосовой связи для пользователей, которым требуется маршрутизации ограничения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="3d765-132">Use the [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="3d765-133">Включение маршрутизации на основе расположения для сетевых узлов</span><span class="sxs-lookup"><span data-stu-id="3d765-133">Enable Location-Based Routing for network sites</span></span>
1.  <span data-ttu-id="3d765-134">Командлет [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) для включения маршрутизации на основе расположения и связать политики маршрутизации голосовых данных на сайтах сети, которые необходимо применить ограничения по маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="3d765-134">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="3d765-135">В этом примере мы Включение маршрутизации на основе расположения для узла Delhi и Hyderabad сайта.</span><span class="sxs-lookup"><span data-stu-id="3d765-135">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="3d765-136">Ниже указаны сайты, включены для маршрутизации на основе расположения в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="3d765-136">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="3d765-137">Узел 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="3d765-137">Site 1 (Delhi)</span></span>  |<span data-ttu-id="3d765-138">Узел 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="3d765-138">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="3d765-139">Имя сайта</span><span class="sxs-lookup"><span data-stu-id="3d765-139">Site name</span></span>    |<span data-ttu-id="3d765-140">Узел 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="3d765-140">Site 1 (Delhi)</span></span>    |<span data-ttu-id="3d765-141">Узел 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="3d765-141">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="3d765-142">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="3d765-142">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="3d765-143">True</span><span class="sxs-lookup"><span data-stu-id="3d765-143">True</span></span>    |<span data-ttu-id="3d765-144">True</span><span class="sxs-lookup"><span data-stu-id="3d765-144">True</span></span>    |
    |<span data-ttu-id="3d765-145">Подсети</span><span class="sxs-lookup"><span data-stu-id="3d765-145">Subnets</span></span>     |<span data-ttu-id="3d765-146">Подсеть 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="3d765-146">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="3d765-147">Подсеть 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="3d765-147">Subnet 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="3d765-148">Включение маршрутизации на основе расположения для шлюзов</span><span class="sxs-lookup"><span data-stu-id="3d765-148">Enable Location-Based Routing for gateways</span></span>
1. <span data-ttu-id="3d765-149">Командлет [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) используется для создания конфигурации шлюза для каждого шлюза или сетевого узла.</span><span class="sxs-lookup"><span data-stu-id="3d765-149">Use the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignallingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="3d765-150">Если несколько шлюзов, связанные с системой (например, шлюзом или УАТС), измените каждый шлюз для включения ограничений на основе местоположения маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="3d765-150">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="3d765-151">В этом примере мы создадим одной конфигурации шлюза для каждого шлюза.</span><span class="sxs-lookup"><span data-stu-id="3d765-151">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignallingPort 5067 
    ```
    <span data-ttu-id="3d765-152">Дополнительные сведения можно [Настроить прямой маршрутизации](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="3d765-152">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="3d765-153">Командлет [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) используется для включения маршрутизации на основе расположения для вашей шлюзов, которые необходимо применить ограничения по маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="3d765-153">Use the [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="3d765-154">Включение маршрутизации на основе расположения для шлюзов, которые маршрутизации вызовов для шлюзов PSTN, маршрутизировать вызовы в ТСОП и сопоставить сетевого узла, где находится шлюз.</span><span class="sxs-lookup"><span data-stu-id="3d765-154">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="3d765-155">В этом примере мы Включение маршрутизации на основе расположения для каждого шлюза, сопоставленные для шлюзов ТСОП на веб-сайтах Delhi и Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="3d765-155">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    <span data-ttu-id="3d765-156">Не Включение маршрутизации на основе расположения для шлюзов, которые не маршрутизировать вызовы в ТСОП.</span><span class="sxs-lookup"><span data-stu-id="3d765-156">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="3d765-157">Тем не менее необходимо связать шлюза для сетевого узла, где расположена система.</span><span class="sxs-lookup"><span data-stu-id="3d765-157">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="3d765-158">Это из-за ограничений на основе местоположения маршрутизации должны применяться для вызовов ТСОП достигает конечные точки, подключенные через этот шлюз.</span><span class="sxs-lookup"><span data-stu-id="3d765-158">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="3d765-159">В этом примере зависимостью от расположения маршрутизации не включен для каждого шлюза, содержащего АТС на веб-сайтах Delhi и Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="3d765-159">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    <span data-ttu-id="3d765-160">Конечные точки, подключенные к системам, которые не маршрутизировать вызовы в ТСОП (например, УАТС) будут иметь аналогичные ограничения как конечных точек пользователям группы с поддержкой маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="3d765-160">Endpoints connected to systems that don't route calls to the PSTN (for example, a PBX) will have similar restrictions as endpoints of Teams users enabled for Location-Based Routing.</span></span> <span data-ttu-id="3d765-161">Это означает, что эти пользователи могут выполнять и принимать вызовы, связанные с группами пользователей независимо от расположения пользователя.</span><span class="sxs-lookup"><span data-stu-id="3d765-161">This means that these users can place and receive calls to and from Teams users regardless of the user’s location.</span></span> <span data-ttu-id="3d765-162">Пользователь может звонить и принимать звонки, чтобы и других систем, которые не маршрутизировать вызовы Телефонной сети общего пользования (например, конечную точку, подключенный к УАТС различных) независимо от сетевого узла, с которым связана системы.</span><span class="sxs-lookup"><span data-stu-id="3d765-162">They can also place and receive calls to and from other systems that don't route calls to the PSTN network (for example, an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="3d765-163">Все входящие вызовы, исходящие вызовы, перевод звонков и переадресацию звонков, связанных с конечными точками PSTN будет использоваться принудительным ограничением маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="3d765-163">All inbound calls, outbound calls, call transfers and call forwarding that involve PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="3d765-164">Эти вызовы необходимо использовать только шлюзы ТСОП, определенные как локальный для таких систем.</span><span class="sxs-lookup"><span data-stu-id="3d765-164">These calls must use only PSTN gateways that are defined as local to such systems.</span></span> 

    <span data-ttu-id="3d765-165">В следующей таблице показаны настройки шлюза четыре шлюзов в двух различных сетевых сайтов: два, подключенных к шлюзы ТСОП и по два подключенных к УАТС.</span><span class="sxs-lookup"><span data-stu-id="3d765-165">The following table shows the gateway configuration of four gateways in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span> 

    ||<span data-ttu-id="3d765-166">GatewaySiteLbrEnabled</span><span class="sxs-lookup"><span data-stu-id="3d765-166">GatewaySiteLbrEnabled</span></span>   |<span data-ttu-id="3d765-167">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="3d765-167">NetworkSiteID</span></span>  |
    |---------|---------|---------|
    |<span data-ttu-id="3d765-168">DEL PstnGateway:Gateway 1-Себестоимости</span><span class="sxs-lookup"><span data-stu-id="3d765-168">PstnGateway:Gateway 1 DEL-GW</span></span>    |    <span data-ttu-id="3d765-169">True</span><span class="sxs-lookup"><span data-stu-id="3d765-169">True</span></span>     |   <span data-ttu-id="3d765-170">Узел 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="3d765-170">Site 1 (Delhi)</span></span>      |
    |<span data-ttu-id="3d765-171">PstnGateway:Gateway 2 HYD-Себестоимости</span><span class="sxs-lookup"><span data-stu-id="3d765-171">PstnGateway:Gateway 2 HYD-GW</span></span>     |   <span data-ttu-id="3d765-172">True</span><span class="sxs-lookup"><span data-stu-id="3d765-172">True</span></span>      |      <span data-ttu-id="3d765-173">Узел 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="3d765-173">Site 2 (Hyderabad)</span></span>   |
    |<span data-ttu-id="3d765-174">DEL PstnGateway:Gateway 3-УАТС</span><span class="sxs-lookup"><span data-stu-id="3d765-174">PstnGateway:Gateway 3 DEL-PBX</span></span>    |    <span data-ttu-id="3d765-175">False</span><span class="sxs-lookup"><span data-stu-id="3d765-175">False</span></span>     |     <span data-ttu-id="3d765-176">Узел 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="3d765-176">Site 1 (Delhi)</span></span>    |
    |<span data-ttu-id="3d765-177">HYD PstnGateway:Gateway 4-УАТС</span><span class="sxs-lookup"><span data-stu-id="3d765-177">PstnGateway:Gateway 4 HYD-PBX</span></span>    |    <span data-ttu-id="3d765-178">False</span><span class="sxs-lookup"><span data-stu-id="3d765-178">False</span></span>     |    <span data-ttu-id="3d765-179">Узел 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="3d765-179">Site 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="3d765-180">Включение маршрутизации на основе расположения для вызова политик</span><span class="sxs-lookup"><span data-stu-id="3d765-180">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="3d765-181">Для применения параметров маршрутизации на основе расположения для отдельных пользователей, настройте политику голосовой связи пользователей, чтобы запретить международную PTSN обхода.</span><span class="sxs-lookup"><span data-stu-id="3d765-181">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="3d765-182">Командлет [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) используется для включения маршрутизации на основе местоположения, устраняя PSTN международную сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="3d765-182">Use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="3d765-183">В этом примере мы запретить PSTN международную сервера-посредника для пользователя User1 вызов политик.</span><span class="sxs-lookup"><span data-stu-id="3d765-183">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```
Grant-CsTeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

### <a name="related-topics"></a><span data-ttu-id="3d765-184">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="3d765-184">Related topics</span></span>
- [<span data-ttu-id="3d765-185">Планирование маршрутизации на основе расположения для прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="3d765-185">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="3d765-186">Настройка параметров сети для маршрутизации на основе расположения</span><span class="sxs-lookup"><span data-stu-id="3d765-186">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="3d765-187">Терминология маршрутизации на основе расположения</span><span class="sxs-lookup"><span data-stu-id="3d765-187">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)
