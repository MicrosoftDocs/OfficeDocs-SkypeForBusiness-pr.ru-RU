---
title: Включение функции "Маршрутизация на основе расположения" для прямой маршрутизации
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Сведения о том, как включить маршрутизацию на основе местоположения для прямой маршрутизации.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 734a2354e81dc88430e8f880c46b0f97862158b5
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836559"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="de786-103">Включение функции "Маршрутизация на основе расположения" для прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="de786-103">Enable Location-Based Routing for Direct Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="de786-104">Перед выполнением действий, описанных в этой статье, убедитесь в том, что вы прочитали [маршрут на основе местоположения для прямой маршрутизации](location-based-routing-plan.md) и завершили этапы в разделе [Настройка сетевых параметров для маршрутизации на основе местоположения](location-based-routing-configure-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="de786-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="de786-105">В этой статье описано, как включить маршрутизацию на основе местоположения для прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="de786-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="de786-106">После развертывания прямой маршрутизации на телефонную систему и настройки регионов сети, сайтов и подсетей вы можете включить маршрутизацию на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="de786-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="de786-107">Для выполнения действий, описанных в этой статье, вам потребуется ознакомиться с командлетами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="de786-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="de786-108">Дополнительные сведения можно найти в разделе [Общие сведения о Teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="de786-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="de786-109">Вы должны включить маршрутизацию на основе местоположения для указанных ниже вариантов.</span><span class="sxs-lookup"><span data-stu-id="de786-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="de786-110">Пользователи</span><span class="sxs-lookup"><span data-stu-id="de786-110">Users</span></span>
- <span data-ttu-id="de786-111">Сетевые сайты</span><span class="sxs-lookup"><span data-stu-id="de786-111">Network sites</span></span>
- <span data-ttu-id="de786-112">Конфигурации шлюзов</span><span class="sxs-lookup"><span data-stu-id="de786-112">Gateway configurations</span></span>
- <span data-ttu-id="de786-113">Политики звонков</span><span class="sxs-lookup"><span data-stu-id="de786-113">Calling policies</span></span>

## <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="de786-114">Включение маршрутизации на основе местоположения для пользователей</span><span class="sxs-lookup"><span data-stu-id="de786-114">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="de786-115">Используйте командлет [Set-ксонлинепстнусаже](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) , чтобы настроить использование КТСОП.</span><span class="sxs-lookup"><span data-stu-id="de786-115">Use the [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="de786-116">Для нескольких использований Разделяйте каждое использование запятыми.</span><span class="sxs-lookup"><span data-stu-id="de786-116">For multiple usages, separate each usage with a comma.</span></span>

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="de786-117">Например:</span><span class="sxs-lookup"><span data-stu-id="de786-117">For example:</span></span>
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="de786-118">С помощью командлета [New-ксонлиневоицераутингполици](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) можно создать политику маршрутизации голосовой связи, связывающую пользователя с использованием соответствующих ресурсов PSTN.</span><span class="sxs-lookup"><span data-stu-id="de786-118">Use the [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="de786-119">При назначении политики голосовой маршрутизации параметров использования PSTN убедитесь, что вы выполняете одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="de786-119">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="de786-120">Использование PSTN, связанных с голосовыми маршрутами, которые используют локальный шлюз PSTN для сайта</span><span class="sxs-lookup"><span data-stu-id="de786-120">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="de786-121">Используйте PSTN, связанные с голосовыми маршрутами, которые используют шлюз PSTN, находящийся в регионе, где не требуются ограничения на маршрутизацию на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="de786-121">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="de786-122">В этом примере мы создадим две новые политики голосовой маршрутизации и назначаем им использование PSTN.</span><span class="sxs-lookup"><span data-stu-id="de786-122">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="de786-123">В следующей таблице показаны политики маршрутизации голосовой связи, определенные в этом примере.</span><span class="sxs-lookup"><span data-stu-id="de786-123">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="de786-124">Политика маршрутизации голосовой связи 1</span><span class="sxs-lookup"><span data-stu-id="de786-124">Voice routing policy 1</span></span>|<span data-ttu-id="de786-125">Политика маршрутизации голосовой связи 2</span><span class="sxs-lookup"><span data-stu-id="de786-125">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="de786-126">КОД политики голосовой связи через Интернет</span><span class="sxs-lookup"><span data-stu-id="de786-126">Online voice policy ID</span></span>   |<span data-ttu-id="de786-127">Политика маршрутизации голосовой связи Делхи Online</span><span class="sxs-lookup"><span data-stu-id="de786-127">Delhi online voice routing policy</span></span>   |<span data-ttu-id="de786-128">Политика маршрутизации голосовой связи Хидерабад Online</span><span class="sxs-lookup"><span data-stu-id="de786-128">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="de786-129">Использование сети PSTN</span><span class="sxs-lookup"><span data-stu-id="de786-129">Online PSTN usages</span></span>  |<span data-ttu-id="de786-130">Междугородные звонки</span><span class="sxs-lookup"><span data-stu-id="de786-130">Long Distance</span></span>  |<span data-ttu-id="de786-131">Междугородный, локальный, внутренний</span><span class="sxs-lookup"><span data-stu-id="de786-131">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="de786-132">С помощью командлета [Grant-ксонлиневоицераутингполици](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) можно связать политики голосовой маршрутизации через Интернет с пользователями, которым требуются ограничения маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="de786-132">Use the [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="de786-133">Включение маршрутизации на основе местоположения для сетевых сайтов</span><span class="sxs-lookup"><span data-stu-id="de786-133">Enable Location-Based Routing for network sites</span></span>
1.  <span data-ttu-id="de786-134">Используйте командлет [Set-кстенантнетворксите](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) , чтобы включить маршрутизацию на основе местоположения и связать политики голосовой маршрутизации с сетевыми сайтами, которые должны применять ограничения маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="de786-134">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="de786-135">В этом примере включается маршрутизация на основе местоположения для сайта Делхи и сайта Хидерабад.</span><span class="sxs-lookup"><span data-stu-id="de786-135">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="de786-136">В приведенной ниже таблице показаны сайты, для которых включена маршрутизация на основе местоположения в этом примере.</span><span class="sxs-lookup"><span data-stu-id="de786-136">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="de786-137">Сайт 1 (Делхи)</span><span class="sxs-lookup"><span data-stu-id="de786-137">Site 1 (Delhi)</span></span>  |<span data-ttu-id="de786-138">Сайт 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="de786-138">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="de786-139">Имя сайта</span><span class="sxs-lookup"><span data-stu-id="de786-139">Site name</span></span>    |<span data-ttu-id="de786-140">Сайт 1 (Делхи)</span><span class="sxs-lookup"><span data-stu-id="de786-140">Site 1 (Delhi)</span></span>    |<span data-ttu-id="de786-141">Сайт 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="de786-141">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="de786-142">енаблелокатионбаседраутинг</span><span class="sxs-lookup"><span data-stu-id="de786-142">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="de786-143">Верно</span><span class="sxs-lookup"><span data-stu-id="de786-143">True</span></span>    |<span data-ttu-id="de786-144">Верно</span><span class="sxs-lookup"><span data-stu-id="de786-144">True</span></span>    |
    |<span data-ttu-id="de786-145">Подсети</span><span class="sxs-lookup"><span data-stu-id="de786-145">Subnets</span></span>     |<span data-ttu-id="de786-146">Подсеть 1 (Делхи)</span><span class="sxs-lookup"><span data-stu-id="de786-146">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="de786-147">Подсеть 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="de786-147">Subnet 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="de786-148">Включение маршрутизации на основе местоположения для шлюзов</span><span class="sxs-lookup"><span data-stu-id="de786-148">Enable Location-Based Routing for gateways</span></span>
1. <span data-ttu-id="de786-149">Используйте командлет [New-ксонлинепстнгатевай](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) для создания конфигурации шлюза для каждого шлюза или сайта сети.</span><span class="sxs-lookup"><span data-stu-id="de786-149">Use the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="de786-150">Если несколько шлюзов связаны с системой (например, Gateway или УАТС), измените каждый из них, чтобы включить ограничения маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="de786-150">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="de786-151">В этом примере мы создадим одну конфигурацию шлюза для каждого шлюза.</span><span class="sxs-lookup"><span data-stu-id="de786-151">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    <span data-ttu-id="de786-152">Дополнительные сведения можно найти в разделе [Настройка прямого маршрута](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="de786-152">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="de786-153">Используйте командлет [Set-ксонлинепстнгатевай](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) , чтобы включить маршрутизацию на основе местоположения для шлюзов, которые должны применять ограничения маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="de786-153">Use the [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="de786-154">Включите возможность маршрутизации на основе местоположения для шлюзов, которые направляют звонки на шлюзы PSTN, которые направляют звонки в КТСОП и связывают сетевой сайт, на котором расположен шлюз.</span><span class="sxs-lookup"><span data-stu-id="de786-154">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="de786-155">В этом примере включена маршрутизация на основе местоположения для каждого шлюза, связанного с шлюзами PSTN на сайтах Делхи и Хидерабад.</span><span class="sxs-lookup"><span data-stu-id="de786-155">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    <span data-ttu-id="de786-156">Не включайте маршрутизацию на основе местоположения для шлюзов, не направлять звонки в КТСОП.</span><span class="sxs-lookup"><span data-stu-id="de786-156">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="de786-157">Однако вы по-прежнему должны ассоциировать шлюз с сетевым сайтом, на котором находится система.</span><span class="sxs-lookup"><span data-stu-id="de786-157">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="de786-158">Это связано с тем, что для звонков по протоколу PSTN должны применяться ограничения на маршрутизацию на основе местоположения, связанные с конечными точками, которые подключены через этот шлюз.</span><span class="sxs-lookup"><span data-stu-id="de786-158">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="de786-159">В этом примере маршрутизация на основе местоположения не включена для каждого шлюза, связанного с системами УАТС на сайтах Делхи и Хидерабад.</span><span class="sxs-lookup"><span data-stu-id="de786-159">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    <span data-ttu-id="de786-160">Конечные точки, подключенные к системам, не накладываемые на протокол PSTN (например, УАТС), имеют аналогичные ограничения в качестве конечных точек пользователей Teams, поддерживающих маршрутизацию на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="de786-160">Endpoints connected to systems that don't route calls to the PSTN (for example, a PBX) will have similar restrictions as endpoints of Teams users enabled for Location-Based Routing.</span></span> <span data-ttu-id="de786-161">Это означает, что эти пользователи могут выполнять и принимать звонки от пользователей Teams, независимо от местонахождения пользователя.</span><span class="sxs-lookup"><span data-stu-id="de786-161">This means that these users can place and receive calls to and from Teams users regardless of the user’s location.</span></span> <span data-ttu-id="de786-162">Они также могут размещать и принимать звонки в другие системы, не находящиеся в сети PSTN (например, конечную точку, подключенную к другой УАТС) независимо от того, с какой сетевой страницей связана система.</span><span class="sxs-lookup"><span data-stu-id="de786-162">They can also place and receive calls to and from other systems that don't route calls to the PSTN network (for example, an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="de786-163">Для всех входящих звонков, исходящих звонков, передачи звонков и переадресации звонков, использующих конечные точки PSTN, будет применяться маршрутизация на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="de786-163">All inbound calls, outbound calls, call transfers and call forwarding that involve PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="de786-164">Эти звонки должны использовать только шлюзы PSTN, определенные как локальные для таких систем.</span><span class="sxs-lookup"><span data-stu-id="de786-164">These calls must use only PSTN gateways that are defined as local to such systems.</span></span> 

    <span data-ttu-id="de786-165">В приведенной ниже таблице показана настройка шлюза для четырех шлюзов на двух разных сетевых сайтах: два соединения с шлюзами PSTN и двумя подключенными к системам АТС.</span><span class="sxs-lookup"><span data-stu-id="de786-165">The following table shows the gateway configuration of four gateways in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span> 

    ||<span data-ttu-id="de786-166">гатевайсителбренаблед</span><span class="sxs-lookup"><span data-stu-id="de786-166">GatewaySiteLbrEnabled</span></span>   |<span data-ttu-id="de786-167">нетворкситеид</span><span class="sxs-lookup"><span data-stu-id="de786-167">NetworkSiteID</span></span>  |
    |---------|---------|---------|
    |<span data-ttu-id="de786-168">Пстнгатевай: шлюз 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="de786-168">PstnGateway:Gateway 1 DEL-GW</span></span>    |    <span data-ttu-id="de786-169">Верно</span><span class="sxs-lookup"><span data-stu-id="de786-169">True</span></span>     |   <span data-ttu-id="de786-170">Сайт 1 (Делхи)</span><span class="sxs-lookup"><span data-stu-id="de786-170">Site 1 (Delhi)</span></span>      |
    |<span data-ttu-id="de786-171">Пстнгатевай: шлюз 2 ХИД-GW</span><span class="sxs-lookup"><span data-stu-id="de786-171">PstnGateway:Gateway 2 HYD-GW</span></span>     |   <span data-ttu-id="de786-172">Верно</span><span class="sxs-lookup"><span data-stu-id="de786-172">True</span></span>      |      <span data-ttu-id="de786-173">Сайт 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="de786-173">Site 2 (Hyderabad)</span></span>   |
    |<span data-ttu-id="de786-174">Пстнгатевай: Gateway 3 Delete-УАТС</span><span class="sxs-lookup"><span data-stu-id="de786-174">PstnGateway:Gateway 3 DEL-PBX</span></span>    |    <span data-ttu-id="de786-175">False</span><span class="sxs-lookup"><span data-stu-id="de786-175">False</span></span>     |     <span data-ttu-id="de786-176">Сайт 1 (Делхи)</span><span class="sxs-lookup"><span data-stu-id="de786-176">Site 1 (Delhi)</span></span>    |
    |<span data-ttu-id="de786-177">Пстнгатевай: шлюз 4 ХИД-УАТС</span><span class="sxs-lookup"><span data-stu-id="de786-177">PstnGateway:Gateway 4 HYD-PBX</span></span>    |    <span data-ttu-id="de786-178">False</span><span class="sxs-lookup"><span data-stu-id="de786-178">False</span></span>     |    <span data-ttu-id="de786-179">Сайт 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="de786-179">Site 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="de786-180">Включение маршрутизации на основе местоположения для политик звонков</span><span class="sxs-lookup"><span data-stu-id="de786-180">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="de786-181">Чтобы обеспечить возможность маршрутизации на основе местоположения для конкретных пользователей, настройте политику голосовой связи пользователей, чтобы предотвратить ОКТС платный звонок.</span><span class="sxs-lookup"><span data-stu-id="de786-181">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="de786-182">Используйте командлет [Grant-кстеамскаллингполици](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) , чтобы включить маршрутизацию на основе местоположения, запретив бесплатный звонок без поддержки КТСОП.</span><span class="sxs-lookup"><span data-stu-id="de786-182">Use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="de786-183">В этом примере мы постараемся отключить платный звонок в политики User1's звонков.</span><span class="sxs-lookup"><span data-stu-id="de786-183">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

## <a name="related-topics"></a><span data-ttu-id="de786-184">См. также</span><span class="sxs-lookup"><span data-stu-id="de786-184">Related topics</span></span>

- [<span data-ttu-id="de786-185">Параметры сети для функций голосовой связи в облаке в Teams</span><span class="sxs-lookup"><span data-stu-id="de786-185">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
