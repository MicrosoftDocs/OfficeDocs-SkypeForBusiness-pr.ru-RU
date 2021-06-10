---
title: Включение функции "Маршрутизация на основе расположения" для прямой маршрутизации
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Узнайте, как Location-Based маршрутизов для прямой маршрутации, в том числе для пользователей, сетевых сайтов, конфигураций шлюза и политик звонков.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d43d650384dd538ff481ac9625c15b9a9f420d95
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120580"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="871ec-103">Включение функции "Маршрутизация на основе расположения" для прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="871ec-103">Enable Location-Based Routing for Direct Routing</span></span>

<span data-ttu-id="871ec-104">Прежде чем выполнять действия, которые вы выполните в этой статье, прочитайте статью [Планирование](location-based-routing-plan.md) маршрутов Location-Based для прямой маршрутии и выполните действия, которые можно сделать в статье Настройка сетевых параметров Location-Based [маршрутии.](location-based-routing-configure-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="871ec-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="871ec-105">В этой статье описано, как включить Location-Based для прямой маршрутии.</span><span class="sxs-lookup"><span data-stu-id="871ec-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="871ec-106">После развертывания телефонная система прямой маршрутизации и настроив сетевые регионы, сайты и подсети, вы можете включить Location-Based маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="871ec-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="871ec-107">Для выполнения действий, которые вы выполните в этой статье, необходимо ознакомиться с помощью cmdlets PowerShell.</span><span class="sxs-lookup"><span data-stu-id="871ec-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="871ec-108">Дополнительные сведения см. [в Teams PowerShell.](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="871ec-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="871ec-109">Для этого необходимо Location-Based маршрутику:</span><span class="sxs-lookup"><span data-stu-id="871ec-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="871ec-110">Пользователи</span><span class="sxs-lookup"><span data-stu-id="871ec-110">Users</span></span>
- <span data-ttu-id="871ec-111">Сетевые сайты</span><span class="sxs-lookup"><span data-stu-id="871ec-111">Network sites</span></span>
- <span data-ttu-id="871ec-112">Конфигурации шлюза</span><span class="sxs-lookup"><span data-stu-id="871ec-112">Gateway configurations</span></span>
- <span data-ttu-id="871ec-113">Политики звонков</span><span class="sxs-lookup"><span data-stu-id="871ec-113">Calling policies</span></span>

<span data-ttu-id="871ec-114">Вы можете использовать [Центр администрирования Microsoft Team](#using-the-microsoft-teams-admin-center) или [PowerShel](#using-powershell)l, чтобы Location-Based маршрутику.</span><span class="sxs-lookup"><span data-stu-id="871ec-114">You can use the [Microsoft Team admin center](#using-the-microsoft-teams-admin-center) or [PowerShel](#using-powershell)l to enable Location-Based Routing.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="871ec-115">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="871ec-115">Using the Microsoft Teams admin center</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="871ec-116">Включить Location-Based маршрутии для пользователей</span><span class="sxs-lookup"><span data-stu-id="871ec-116">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="871ec-117">Создайте политику маршрутинга голосовой почты и назначьте политике использование услуг STN.</span><span class="sxs-lookup"><span data-stu-id="871ec-117">Create a voice routing policy and assign PSTN usages to the policy.</span></span> <span data-ttu-id="871ec-118">При назначении политикам использования ННР необходимо сделать одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="871ec-118">When you assign PSTN usages to a policy, make sure you do one of the following:</span></span>

    - <span data-ttu-id="871ec-119">Использование услуг STN, связанных с голосовой маршрутией, в которую используется локальный шлюз STN на сайте.</span><span class="sxs-lookup"><span data-stu-id="871ec-119">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site.</span></span>
    - <span data-ttu-id="871ec-120">Использование услуг ННП, связанных с голосовой маршрутикой, в которой используется шлюз ННР, расположенный в регионе, где Location-Based маршруты не нужны.</span><span class="sxs-lookup"><span data-stu-id="871ec-120">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>
2. <span data-ttu-id="871ec-121">Назначьте политику маршрутинга голосовой почты пользователям, для которых требуются ограничения маршрутики.</span><span class="sxs-lookup"><span data-stu-id="871ec-121">Assign the voice routing policy to users who require routing restrictions to be enforced.</span></span>

<span data-ttu-id="871ec-122">Дополнительные информацию о создании политик голосовой маршрутики и их назначении пользователям см. в [Microsoft Teams.](manage-voice-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="871ec-122">To learn more about how to create voice routing policies and assign them to users, see [Manage voice routing policies in Microsoft Teams](manage-voice-routing-policies.md).</span></span>

### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="871ec-123">Включить Location-Based маршрутику для сетевых сайтов</span><span class="sxs-lookup"><span data-stu-id="871ec-123">Enable Location-Based Routing for network sites</span></span>

<span data-ttu-id="871ec-124">В Location-Based перенаустоять маршруты для сайтов, для которые необходимо навести ограничения на маршрутику.</span><span class="sxs-lookup"><span data-stu-id="871ec-124">Enable Location-Based Routing for your sites that need to enforce routing restrictions.</span></span> <span data-ttu-id="871ec-125">Для этого в левой области навигации Центра администрирования Microsoft Teams перейдите в топологию сети расположений , выберите сетевой сайт, нажмите кнопку Изменить и включите маршрутику на основе расположения  >  .  </span><span class="sxs-lookup"><span data-stu-id="871ec-125">To do this, in the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, select a network site, click **Edit**, and then turn on **Location based routing**.</span></span>  

<span data-ttu-id="871ec-126">Дополнительные узнать см. в [управлении топологией сети.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="871ec-126">To learn more, see [Manage your network topology](manage-your-network-topology.md).</span></span>

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="871ec-127">Включить Location-Based маршрутику для шлюзов</span><span class="sxs-lookup"><span data-stu-id="871ec-127">Enable Location-Based Routing for gateways</span></span>

<span data-ttu-id="871ec-128">В Location-Based маршрутизов можно включить маршрутику шлюзов, которые перенаустанавлиют вызовы на шлюзы ПСС, которые перенаустанавлиют вызовы на STN, и связать сетевой сайт, на котором находится шлюз.</span><span class="sxs-lookup"><span data-stu-id="871ec-128">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span> 

1. <span data-ttu-id="871ec-129">В области навигации слева перейдите в **voice**  >  **Direct Routing** и перейдите на вкладку **SBCs.**</span><span class="sxs-lookup"><span data-stu-id="871ec-129">In the left navigation, go to **Voice** > **Direct Routing**, and then click the **SBCs** tab.</span></span>
2. <span data-ttu-id="871ec-130">Выберите SBC и нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="871ec-130">Select the SBC, and then click **Edit**.</span></span> 
3. <span data-ttu-id="871ec-131">В **области Маршрутизация на основе расположения и оптимизация мультимедиа** включите включить маршрутизация на основе **расположения**.</span><span class="sxs-lookup"><span data-stu-id="871ec-131">Under **Location based routing and media optimization**, turn on **Enable location based routing**.</span></span>
4. <span data-ttu-id="871ec-132">Укажите ИД сайта шлюза, а затем установите режим обхода.</span><span class="sxs-lookup"><span data-stu-id="871ec-132">Specify the gateway site ID, and then set the bypass mode.</span></span>
5. <span data-ttu-id="871ec-133">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="871ec-133">Click **Save**.</span></span>

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="871ec-134">Включить Location-Based маршрутизов для политик звонков</span><span class="sxs-lookup"><span data-stu-id="871ec-134">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="871ec-135">Чтобы принудительно Location-Based маршрутизов для определенных пользователей, установите для них политику звонков, чтобы запретить обход платных звонков по ОКП.</span><span class="sxs-lookup"><span data-stu-id="871ec-135">To enforce Location-Based Routing for specific users, set up the user's calling policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="871ec-136">Для этого включите параметр Запретить платный **обход** в политике звонков.</span><span class="sxs-lookup"><span data-stu-id="871ec-136">To do this, turn on the **Prevent toll bypass** setting in the calling policy.</span></span>

<span data-ttu-id="871ec-137">Дополнительные информации см. в [Teams.](teams-calling-policy.md)</span><span class="sxs-lookup"><span data-stu-id="871ec-137">To learn more, see [Calling policies in Teams](teams-calling-policy.md).</span></span>

## <a name="using-powershell"></a><span data-ttu-id="871ec-138">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="871ec-138">Using PowerShell</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="871ec-139">Включить Location-Based маршрутии для пользователей</span><span class="sxs-lookup"><span data-stu-id="871ec-139">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="871ec-140">Для этого используйте для этого [cmdlet Set-CsOnlinePstnUsage.](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="871ec-140">Use the [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="871ec-141">Для нескольких использования разделять каждое использование запятой.</span><span class="sxs-lookup"><span data-stu-id="871ec-141">For multiple usages, separate each usage with a comma.</span></span>

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="871ec-142">Например:</span><span class="sxs-lookup"><span data-stu-id="871ec-142">For example:</span></span>
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="871ec-143">С помощью [нового-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) создайте политику маршрутизации голосовой связи, чтобы связать пользователя с соответствующими использованием ОКП.</span><span class="sxs-lookup"><span data-stu-id="871ec-143">Use the [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="871ec-144">При назначении использования услуг ННР политике голосовой маршрутии убедитесь, что вы делаете одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="871ec-144">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="871ec-145">Использование службы STN, связанных с голосовой маршрутией, в сети с локальным шлюзом STN на сайте</span><span class="sxs-lookup"><span data-stu-id="871ec-145">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="871ec-146">Использование услуг ННП, связанных с голосовой маршрутикой, в которой используется шлюз ННР, расположенный в регионе, где Location-Based маршруты не нужны.</span><span class="sxs-lookup"><span data-stu-id="871ec-146">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="871ec-147">В этом примере мы создадим две новые политики маршрутинга голосовой связи и назначим им использование услуг STN.</span><span class="sxs-lookup"><span data-stu-id="871ec-147">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="871ec-148">В таблице ниже показаны политики маршрутии голосовой связи, определенные в данном примере.</span><span class="sxs-lookup"><span data-stu-id="871ec-148">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="871ec-149">Политика маршрутинга голосовой почты 1</span><span class="sxs-lookup"><span data-stu-id="871ec-149">Voice routing policy 1</span></span>|<span data-ttu-id="871ec-150">Политика маршрутинга голосовой почты 2</span><span class="sxs-lookup"><span data-stu-id="871ec-150">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="871ec-151">ИД голосовой политики в Интернете</span><span class="sxs-lookup"><span data-stu-id="871ec-151">Online voice policy ID</span></span>   |<span data-ttu-id="871ec-152">Политика маршрутистики голосовой почты в Интернете</span><span class="sxs-lookup"><span data-stu-id="871ec-152">Delhi online voice routing policy</span></span>   |<span data-ttu-id="871ec-153">Политика маршрутистики голосовой почты в Интернете</span><span class="sxs-lookup"><span data-stu-id="871ec-153">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="871ec-154">Использование услуг STN в Интернете</span><span class="sxs-lookup"><span data-stu-id="871ec-154">Online PSTN usages</span></span>  |<span data-ttu-id="871ec-155">Длинное расстояние</span><span class="sxs-lookup"><span data-stu-id="871ec-155">Long Distance</span></span>  |<span data-ttu-id="871ec-156">Long Distance, Local, Internal</span><span class="sxs-lookup"><span data-stu-id="871ec-156">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="871ec-157">Используйте для [связывания](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) политик маршрутизации голосовой маршрутизации в Интернете с пользователями, для которых требуются ограничения маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="871ec-157">Use the [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="871ec-158">Включить Location-Based маршрутику для сетевых сайтов</span><span class="sxs-lookup"><span data-stu-id="871ec-158">Enable Location-Based Routing for network sites</span></span>

1.  <span data-ttu-id="871ec-159">С помощью [командлета Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) можно включить Location-Based маршрутизации и связать политики маршрутизации голосовой связи с сетевыми сайтами, которые должны применять ограничения маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="871ec-159">Use the [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="871ec-160">В этом примере мы Location-Based маршрутику для сайта "Сова" и сайта "Омеровая система".</span><span class="sxs-lookup"><span data-stu-id="871ec-160">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="871ec-161">В следующей таблице показаны сайты, Location-Based маршруты в этом примере.</span><span class="sxs-lookup"><span data-stu-id="871ec-161">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="871ec-162">Сайт 1 (вЕтвях)</span><span class="sxs-lookup"><span data-stu-id="871ec-162">Site 1 (Delhi)</span></span>  |<span data-ttu-id="871ec-163">Сайт 2 (Кузьмина)</span><span class="sxs-lookup"><span data-stu-id="871ec-163">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="871ec-164">Имя сайта</span><span class="sxs-lookup"><span data-stu-id="871ec-164">Site name</span></span>    |<span data-ttu-id="871ec-165">Сайт 1 (вЕтвях)</span><span class="sxs-lookup"><span data-stu-id="871ec-165">Site 1 (Delhi)</span></span>    |<span data-ttu-id="871ec-166">Сайт 2 (Кузьмина)</span><span class="sxs-lookup"><span data-stu-id="871ec-166">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="871ec-167">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="871ec-167">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="871ec-168">Верно</span><span class="sxs-lookup"><span data-stu-id="871ec-168">True</span></span>    |<span data-ttu-id="871ec-169">Верно</span><span class="sxs-lookup"><span data-stu-id="871ec-169">True</span></span>    |
    |<span data-ttu-id="871ec-170">Подсети</span><span class="sxs-lookup"><span data-stu-id="871ec-170">Subnets</span></span>     |<span data-ttu-id="871ec-171">Подсеть 1 (Висяче)</span><span class="sxs-lookup"><span data-stu-id="871ec-171">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="871ec-172">Подсеть 2 (Кузнецов)</span><span class="sxs-lookup"><span data-stu-id="871ec-172">Subnet 2 (Hyderabad)</span></span>     |

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="871ec-173">Включить Location-Based маршрутику для шлюзов</span><span class="sxs-lookup"><span data-stu-id="871ec-173">Enable Location-Based Routing for gateways</span></span>

1. <span data-ttu-id="871ec-174">С помощью [нового CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) можно создать конфигурацию шлюза для каждого шлюза или сайта сети.</span><span class="sxs-lookup"><span data-stu-id="871ec-174">Use the [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="871ec-175">Если с системой связано несколько шлюзов (например, Шлюз или УАКС), измените каждый шлюз, чтобы включить Location-Based маршрутии.</span><span class="sxs-lookup"><span data-stu-id="871ec-175">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="871ec-176">В этом примере для каждого шлюза создается одна конфигурация.</span><span class="sxs-lookup"><span data-stu-id="871ec-176">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    <span data-ttu-id="871ec-177">Дополнительные сведения см. [в этой ссылке.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="871ec-177">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="871ec-178">Чтобы включить маршрутиз Location-Based шлюзов, которые должны применять ограничения на маршрутику, используйте Location-Based [Set-CSOnlinePSTNGateway.](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="871ec-178">Use the [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="871ec-179">В Location-Based маршрутизов можно включить маршрутику шлюзов, которые перенаустанавлиют вызовы на шлюзы ПСС, которые перенаустанавлиют вызовы на STN, и связать сетевой сайт, на котором находится шлюз.</span><span class="sxs-lookup"><span data-stu-id="871ec-179">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="871ec-180">В этом примере мы Location-Based маршрутику для каждого шлюза, связанного со шлюзами ННП, на сайтах "Висяк" и "Омерверхи".</span><span class="sxs-lookup"><span data-stu-id="871ec-180">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    <span data-ttu-id="871ec-181">Не в Location-Based маршрутизов для шлюзов, которые не перенаустанавлиют вызовы в ОКП.</span><span class="sxs-lookup"><span data-stu-id="871ec-181">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="871ec-182">Однако вам все равно придется связать шлюз с сетевым сайтом, на котором находится система.</span><span class="sxs-lookup"><span data-stu-id="871ec-182">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="871ec-183">Это связано с темLocation-Based что для звонков по ДНР, которые находятся в конечных точках, подключенных с помощью этого шлюза, необходимо применять Location-Based маршрутизов.</span><span class="sxs-lookup"><span data-stu-id="871ec-183">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="871ec-184">В этом примере Location-Based для каждого шлюза, связанного с системами УАКС, на сайтах "Висячая" и "Омеровая маршрутия".</span><span class="sxs-lookup"><span data-stu-id="871ec-184">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="871ec-185">Включить Location-Based маршрутизов для политик звонков</span><span class="sxs-lookup"><span data-stu-id="871ec-185">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="871ec-186">Чтобы принудительно Location-Based маршрутику для определенных пользователей, установите для них голосовую политику, чтобы запретить обход платных номеров ТССК.</span><span class="sxs-lookup"><span data-stu-id="871ec-186">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="871ec-187">Используйте для [этого](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) Location-Based маршрутизации, предотвращая обход платных номеров ОКП.</span><span class="sxs-lookup"><span data-stu-id="871ec-187">Use the [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="871ec-188">В этом примере мы не мешаем обходу платных номеров ЗВОНКОВ по политикам звонков пользователя 1.</span><span class="sxs-lookup"><span data-stu-id="871ec-188">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a><span data-ttu-id="871ec-189">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="871ec-189">Related topics</span></span>

- [<span data-ttu-id="871ec-190">Параметры сети для облачных функций голосовой связи в Teams</span><span class="sxs-lookup"><span data-stu-id="871ec-190">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)