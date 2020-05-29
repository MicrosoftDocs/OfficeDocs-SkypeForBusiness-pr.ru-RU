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
description: Сведения о том, как включить маршрутизацию на основе местоположения для прямой маршрутизации, в том числе включать ее для пользователей, сетевые сайты, конфигурации шлюза и политики звонков.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4daf270dcd67dc732bba5e5fe134d5a0994dcd75
ms.sourcegitcommit: 2295a668a6f118b95f010e81150351741572b076
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2020
ms.locfileid: "44412646"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="fff03-103">Включение функции "Маршрутизация на основе расположения" для прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="fff03-103">Enable Location-Based Routing for Direct Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="fff03-104">Перед выполнением действий, описанных в этой статье, убедитесь в том, что вы прочитали [маршрут на основе местоположения для прямой маршрутизации](location-based-routing-plan.md) и завершили этапы в разделе [Настройка сетевых параметров для маршрутизации на основе местоположения](location-based-routing-configure-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="fff03-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="fff03-105">В этой статье описано, как включить маршрутизацию на основе местоположения для прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="fff03-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="fff03-106">После развертывания прямой маршрутизации на телефонную систему и настройки регионов сети, сайтов и подсетей вы можете включить маршрутизацию на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="fff03-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="fff03-107">Для выполнения действий, описанных в этой статье, вам потребуется ознакомиться с командлетами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fff03-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="fff03-108">Дополнительные сведения можно найти в разделе [Общие сведения о Teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fff03-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="fff03-109">Вы должны включить маршрутизацию на основе местоположения для указанных ниже вариантов.</span><span class="sxs-lookup"><span data-stu-id="fff03-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="fff03-110">Пользователи</span><span class="sxs-lookup"><span data-stu-id="fff03-110">Users</span></span>
- <span data-ttu-id="fff03-111">Сетевые сайты</span><span class="sxs-lookup"><span data-stu-id="fff03-111">Network sites</span></span>
- <span data-ttu-id="fff03-112">Конфигурации шлюзов</span><span class="sxs-lookup"><span data-stu-id="fff03-112">Gateway configurations</span></span>
- <span data-ttu-id="fff03-113">Политики звонков</span><span class="sxs-lookup"><span data-stu-id="fff03-113">Calling policies</span></span>

<span data-ttu-id="fff03-114">Вы можете использовать [центр администрирования Microsoft Teams](#using-the-microsoft-teams-admin-center) или [PowerShel](#using-powershell)l для включения маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="fff03-114">You can use the [Microsoft Team admin center](#using-the-microsoft-teams-admin-center) or [PowerShel](#using-powershell)l to enable Location-Based Routing.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="fff03-115">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fff03-115">Using the Microsoft Teams admin center</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="fff03-116">Включение маршрутизации на основе местоположения для пользователей</span><span class="sxs-lookup"><span data-stu-id="fff03-116">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="fff03-117">Создайте политику маршрутизации голосовой связи и назначьте ей использование PSTN.</span><span class="sxs-lookup"><span data-stu-id="fff03-117">Create a voice routing policy and assign PSTN usages to the policy.</span></span> <span data-ttu-id="fff03-118">После назначения политике использования PSTN убедитесь в том, что вы выполняете одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="fff03-118">When you assign PSTN usages to a policy, make sure you do one of the following:</span></span>

    - <span data-ttu-id="fff03-119">Использование PSTN, связанных с голосовыми маршрутами, которые используют локальный шлюз PSTN для сайта.</span><span class="sxs-lookup"><span data-stu-id="fff03-119">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site.</span></span>
    - <span data-ttu-id="fff03-120">Используйте PSTN, связанные с голосовыми маршрутами, которые используют шлюз PSTN, находящийся в регионе, где не требуются ограничения на маршрутизацию на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="fff03-120">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>
2. <span data-ttu-id="fff03-121">Назначьте политику маршрутизации голосовых сообщений пользователям, которым требуется применить ограничения маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="fff03-121">Assign the voice routing policy to users who require routing restrictions to be enforced.</span></span>

<span data-ttu-id="fff03-122">Чтобы узнать больше о том, как создавать политики голосовой маршрутизации и назначать их пользователям, ознакомьтесь со статьей [Управление политиками голосовой маршрутизации в Microsoft Teams](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="fff03-122">To learn more about how to create voice routing policies and assign them to users, see [Manage voice routing policies in Microsoft Teams](manage-voice-routing-policies.md).</span></span>

### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="fff03-123">Включение маршрутизации на основе местоположения для сетевых сайтов</span><span class="sxs-lookup"><span data-stu-id="fff03-123">Enable Location-Based Routing for network sites</span></span>

<span data-ttu-id="fff03-124">Включите маршрутизацию на основе местоположения для сайтов, для которых необходимо применить ограничения маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="fff03-124">Enable Location-Based Routing for your sites that need to enforce routing restrictions.</span></span> <span data-ttu-id="fff03-125">Для этого на левой панели навигации в центре администрирования Microsoft Teams перейдите в раздел **Расположение**  >  **топологии сети**, выберите сайт сети, нажмите кнопку **изменить**, а затем включите **маршрутизацию на основе расположения**.</span><span class="sxs-lookup"><span data-stu-id="fff03-125">To do this, in the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, select a network site, click **Edit**, and then turn on **Location based routing**.</span></span>  

<span data-ttu-id="fff03-126">Дополнительные сведения можно найти в разделе [Управление топологией сети](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="fff03-126">To learn more, see [Manage your network topology](manage-your-network-topology.md).</span></span>

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="fff03-127">Включение маршрутизации на основе местоположения для шлюзов</span><span class="sxs-lookup"><span data-stu-id="fff03-127">Enable Location-Based Routing for gateways</span></span>

<span data-ttu-id="fff03-128">Включите возможность маршрутизации на основе местоположения для шлюзов, которые направляют звонки на шлюзы PSTN, которые направляют звонки в КТСОП и связывают сетевой сайт, на котором расположен шлюз.</span><span class="sxs-lookup"><span data-stu-id="fff03-128">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span> 

1. <span data-ttu-id="fff03-129">На панели навигации слева перейдите к **Voice**  >  **перенаправлению**голосовой почты, а затем откройте вкладку **SBCs** .</span><span class="sxs-lookup"><span data-stu-id="fff03-129">In the left navigation, go to **Voice** > **Direct Routing**, and then click the **SBCs** tab.</span></span>
2. <span data-ttu-id="fff03-130">Выделите SBC и нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="fff03-130">Select the SBC, and then click **Edit**.</span></span> 
3. <span data-ttu-id="fff03-131">В разделе **Оптимизация маршрутизации и мультимедиа с учетом расположения**включите **параметр включить маршрутизацию на основе местоположения**.</span><span class="sxs-lookup"><span data-stu-id="fff03-131">Under **Location based routing and media optimization**, turn on **Enable location based routing**.</span></span>
4. <span data-ttu-id="fff03-132">Укажите идентификатор сайта шлюза, а затем настройте режим пропуска.</span><span class="sxs-lookup"><span data-stu-id="fff03-132">Specify the gateway site ID, and then set the bypass mode.</span></span>
5. <span data-ttu-id="fff03-133">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="fff03-133">Click **Save**.</span></span>

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="fff03-134">Включение маршрутизации на основе местоположения для политик звонков</span><span class="sxs-lookup"><span data-stu-id="fff03-134">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="fff03-135">Чтобы обеспечить возможность маршрутизации на основе местоположения для конкретных пользователей, настройте политику звонков пользователя, чтобы отключить платный звонок.</span><span class="sxs-lookup"><span data-stu-id="fff03-135">To enforce Location-Based Routing for specific users, set up the user's calling policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="fff03-136">Для этого включите параметр **запретить платный звонок** в политике звонков.</span><span class="sxs-lookup"><span data-stu-id="fff03-136">To do this, turn on the **Prevent toll bypass** setting in the calling policy.</span></span>

<span data-ttu-id="fff03-137">Дополнительные сведения можно найти [в разделе политики вызова в Teams](teams-calling-policy.md).</span><span class="sxs-lookup"><span data-stu-id="fff03-137">To learn more, see [Calling policies in Teams](teams-calling-policy.md).</span></span>

## <a name="using-powershell"></a><span data-ttu-id="fff03-138">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="fff03-138">Using PowerShell</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="fff03-139">Включение маршрутизации на основе местоположения для пользователей</span><span class="sxs-lookup"><span data-stu-id="fff03-139">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="fff03-140">Используйте командлет [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) , чтобы настроить использование КТСОП.</span><span class="sxs-lookup"><span data-stu-id="fff03-140">Use the [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="fff03-141">Для нескольких использований Разделяйте каждое использование запятыми.</span><span class="sxs-lookup"><span data-stu-id="fff03-141">For multiple usages, separate each usage with a comma.</span></span>

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="fff03-142">Например:</span><span class="sxs-lookup"><span data-stu-id="fff03-142">For example:</span></span>
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="fff03-143">С помощью командлета [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) можно создать политику маршрутизации голосовой связи, связывающую пользователя с использованием соответствующих ресурсов PSTN.</span><span class="sxs-lookup"><span data-stu-id="fff03-143">Use the [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="fff03-144">При назначении политики голосовой маршрутизации параметров использования PSTN убедитесь, что вы выполняете одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="fff03-144">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="fff03-145">Использование PSTN, связанных с голосовыми маршрутами, которые используют локальный шлюз PSTN для сайта</span><span class="sxs-lookup"><span data-stu-id="fff03-145">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="fff03-146">Используйте PSTN, связанные с голосовыми маршрутами, которые используют шлюз PSTN, находящийся в регионе, где не требуются ограничения на маршрутизацию на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="fff03-146">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="fff03-147">В этом примере мы создадим две новые политики голосовой маршрутизации и назначаем им использование PSTN.</span><span class="sxs-lookup"><span data-stu-id="fff03-147">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="fff03-148">В следующей таблице показаны политики маршрутизации голосовой связи, определенные в этом примере.</span><span class="sxs-lookup"><span data-stu-id="fff03-148">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="fff03-149">Политика маршрутизации голосовой связи 1</span><span class="sxs-lookup"><span data-stu-id="fff03-149">Voice routing policy 1</span></span>|<span data-ttu-id="fff03-150">Политика маршрутизации голосовой связи 2</span><span class="sxs-lookup"><span data-stu-id="fff03-150">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="fff03-151">КОД политики голосовой связи через Интернет</span><span class="sxs-lookup"><span data-stu-id="fff03-151">Online voice policy ID</span></span>   |<span data-ttu-id="fff03-152">Политика маршрутизации голосовой связи Delhi Online</span><span class="sxs-lookup"><span data-stu-id="fff03-152">Delhi online voice routing policy</span></span>   |<span data-ttu-id="fff03-153">Политика маршрутизации голосовой связи Hyderabad Online</span><span class="sxs-lookup"><span data-stu-id="fff03-153">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="fff03-154">Использование сети PSTN</span><span class="sxs-lookup"><span data-stu-id="fff03-154">Online PSTN usages</span></span>  |<span data-ttu-id="fff03-155">Междугородные звонки</span><span class="sxs-lookup"><span data-stu-id="fff03-155">Long Distance</span></span>  |<span data-ttu-id="fff03-156">Междугородный, локальный, внутренний</span><span class="sxs-lookup"><span data-stu-id="fff03-156">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="fff03-157">С помощью командлета [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) можно связать политики голосовой маршрутизации через Интернет с пользователями, которым требуются ограничения маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="fff03-157">Use the [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="fff03-158">Включение маршрутизации на основе местоположения для сетевых сайтов</span><span class="sxs-lookup"><span data-stu-id="fff03-158">Enable Location-Based Routing for network sites</span></span>

1.  <span data-ttu-id="fff03-159">Используйте командлет [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) , чтобы включить маршрутизацию на основе местоположения и связать политики голосовой маршрутизации с сетевыми сайтами, которые должны применять ограничения маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="fff03-159">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="fff03-160">В этом примере включается маршрутизация на основе местоположения для сайта Delhi и сайта Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="fff03-160">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="fff03-161">В приведенной ниже таблице показаны сайты, для которых включена маршрутизация на основе местоположения в этом примере.</span><span class="sxs-lookup"><span data-stu-id="fff03-161">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="fff03-162">Сайт 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="fff03-162">Site 1 (Delhi)</span></span>  |<span data-ttu-id="fff03-163">Сайт 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="fff03-163">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="fff03-164">Имя сайта</span><span class="sxs-lookup"><span data-stu-id="fff03-164">Site name</span></span>    |<span data-ttu-id="fff03-165">Сайт 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="fff03-165">Site 1 (Delhi)</span></span>    |<span data-ttu-id="fff03-166">Сайт 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="fff03-166">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="fff03-167">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="fff03-167">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="fff03-168">Верно</span><span class="sxs-lookup"><span data-stu-id="fff03-168">True</span></span>    |<span data-ttu-id="fff03-169">Верно</span><span class="sxs-lookup"><span data-stu-id="fff03-169">True</span></span>    |
    |<span data-ttu-id="fff03-170">Подсети</span><span class="sxs-lookup"><span data-stu-id="fff03-170">Subnets</span></span>     |<span data-ttu-id="fff03-171">Подсеть 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="fff03-171">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="fff03-172">Подсеть 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="fff03-172">Subnet 2 (Hyderabad)</span></span>     |

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="fff03-173">Включение маршрутизации на основе местоположения для шлюзов</span><span class="sxs-lookup"><span data-stu-id="fff03-173">Enable Location-Based Routing for gateways</span></span>

1. <span data-ttu-id="fff03-174">Используйте командлет [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) для создания конфигурации шлюза для каждого шлюза или сайта сети.</span><span class="sxs-lookup"><span data-stu-id="fff03-174">Use the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="fff03-175">Если несколько шлюзов связаны с системой (например, Gateway или УАТС), измените каждый из них, чтобы включить ограничения маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="fff03-175">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="fff03-176">В этом примере мы создадим одну конфигурацию шлюза для каждого шлюза.</span><span class="sxs-lookup"><span data-stu-id="fff03-176">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    <span data-ttu-id="fff03-177">Дополнительные сведения можно найти в разделе [Настройка прямого маршрута](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="fff03-177">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="fff03-178">Используйте командлет [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) , чтобы включить маршрутизацию на основе местоположения для шлюзов, которые должны применять ограничения маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="fff03-178">Use the [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="fff03-179">Включите возможность маршрутизации на основе местоположения для шлюзов, которые направляют звонки на шлюзы PSTN, которые направляют звонки в КТСОП и связывают сетевой сайт, на котором расположен шлюз.</span><span class="sxs-lookup"><span data-stu-id="fff03-179">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="fff03-180">В этом примере включена маршрутизация на основе местоположения для каждого шлюза, связанного с шлюзами PSTN на сайтах Delhi и Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="fff03-180">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    <span data-ttu-id="fff03-181">Не включайте маршрутизацию на основе местоположения для шлюзов, не направлять звонки в КТСОП.</span><span class="sxs-lookup"><span data-stu-id="fff03-181">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="fff03-182">Однако вы по-прежнему должны ассоциировать шлюз с сетевым сайтом, на котором находится система.</span><span class="sxs-lookup"><span data-stu-id="fff03-182">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="fff03-183">Это связано с тем, что для звонков по протоколу PSTN должны применяться ограничения на маршрутизацию на основе местоположения, связанные с конечными точками, которые подключены через этот шлюз.</span><span class="sxs-lookup"><span data-stu-id="fff03-183">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="fff03-184">В этом примере маршрутизация на основе местоположения не включена для каждого шлюза, связанного с системами УАТС на сайтах Delhi и Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="fff03-184">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="fff03-185">Включение маршрутизации на основе местоположения для политик звонков</span><span class="sxs-lookup"><span data-stu-id="fff03-185">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="fff03-186">Чтобы обеспечить возможность маршрутизации на основе местоположения для конкретных пользователей, настройте политику голосовой связи пользователей, чтобы предотвратить ОКТС платный звонок.</span><span class="sxs-lookup"><span data-stu-id="fff03-186">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="fff03-187">Используйте командлет [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) , чтобы включить маршрутизацию на основе местоположения, запретив бесплатный звонок без поддержки КТСОП.</span><span class="sxs-lookup"><span data-stu-id="fff03-187">Use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="fff03-188">В этом примере мы постараемся отключить платный звонок в политики User1's звонков.</span><span class="sxs-lookup"><span data-stu-id="fff03-188">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a><span data-ttu-id="fff03-189">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="fff03-189">Related topics</span></span>

- [<span data-ttu-id="fff03-190">Параметры сети для функций голосовой связи в облаке в Teams</span><span class="sxs-lookup"><span data-stu-id="fff03-190">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
