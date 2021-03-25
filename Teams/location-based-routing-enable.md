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
description: Узнайте, как включить Location-Based для прямой маршрутации, в том числе включить ее для пользователей, сетевых сайтов, конфигураций шлюза и политик звонков.
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
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="a120f-103">Включение функции "Маршрутизация на основе расположения" для прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="a120f-103">Enable Location-Based Routing for Direct Routing</span></span>

<span data-ttu-id="a120f-104">Прежде чем выполнять действия, которые следуют из этой статьи, прочитайте план Location-Based [Маршруты](location-based-routing-plan.md) для прямой маршрутинга и выполните действия, которые необходимо предпринять в статье "Настройка параметров сети для Location-Based [маршрутов".](location-based-routing-configure-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="a120f-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="a120f-105">В этой статье описано, как включить Location-Based для прямой маршрутинга.</span><span class="sxs-lookup"><span data-stu-id="a120f-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="a120f-106">После развертывания прямой маршрутизации телефонной системы и настроив сетевые регионы, сайты и подсети, вы можете включить Location-Based маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="a120f-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="a120f-107">Для выполнения действий, которые вы найдете в этой статье, необходимо ознакомиться с cmdlets PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a120f-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="a120f-108">Дополнительные сведения см. в [обзоре Teams PowerShell.](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a120f-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="a120f-109">Необходимо включить Location-Based для следующих экономий:</span><span class="sxs-lookup"><span data-stu-id="a120f-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="a120f-110">Пользователи</span><span class="sxs-lookup"><span data-stu-id="a120f-110">Users</span></span>
- <span data-ttu-id="a120f-111">Сетевые сайты</span><span class="sxs-lookup"><span data-stu-id="a120f-111">Network sites</span></span>
- <span data-ttu-id="a120f-112">Конфигурации шлюза</span><span class="sxs-lookup"><span data-stu-id="a120f-112">Gateway configurations</span></span>
- <span data-ttu-id="a120f-113">Политики звонков</span><span class="sxs-lookup"><span data-stu-id="a120f-113">Calling policies</span></span>

<span data-ttu-id="a120f-114">Для этого можно [использовать Центр](#using-the-microsoft-teams-admin-center) администрирования Microsoft Team или [PowerShel](#using-powershell)l, чтобы Location-Based маршрутику.</span><span class="sxs-lookup"><span data-stu-id="a120f-114">You can use the [Microsoft Team admin center](#using-the-microsoft-teams-admin-center) or [PowerShel](#using-powershell)l to enable Location-Based Routing.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="a120f-115">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a120f-115">Using the Microsoft Teams admin center</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="a120f-116">Включить Location-Based маршрутии для пользователей</span><span class="sxs-lookup"><span data-stu-id="a120f-116">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="a120f-117">Создайте политику маршрутинга голосовой почты и назначьте политике использование услуг ННР.</span><span class="sxs-lookup"><span data-stu-id="a120f-117">Create a voice routing policy and assign PSTN usages to the policy.</span></span> <span data-ttu-id="a120f-118">При назначении политик использования ННР убедитесь, что вы делаете одно из следующего:</span><span class="sxs-lookup"><span data-stu-id="a120f-118">When you assign PSTN usages to a policy, make sure you do one of the following:</span></span>

    - <span data-ttu-id="a120f-119">Использование ННР, связанных с голосовой маршрутией, при использовании локального шлюза ННП на сайте.</span><span class="sxs-lookup"><span data-stu-id="a120f-119">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site.</span></span>
    - <span data-ttu-id="a120f-120">Использование ННР, связанных с голосовой маршрутией, в которой используется шлюз ННР, расположенный в регионе, где Location-Based маршруты не нужны.</span><span class="sxs-lookup"><span data-stu-id="a120f-120">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>
2. <span data-ttu-id="a120f-121">Назначьте политику маршрутики голосовой почты пользователям, которым требуются ограничения маршрутики.</span><span class="sxs-lookup"><span data-stu-id="a120f-121">Assign the voice routing policy to users who require routing restrictions to be enforced.</span></span>

<span data-ttu-id="a120f-122">Дополнительные информацию о создании политик голосовой маршрутии и их назначении пользователям см. в подмнося "Управление политиками маршрутинга голосовой [маршрутии в Microsoft Teams".](manage-voice-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="a120f-122">To learn more about how to create voice routing policies and assign them to users, see [Manage voice routing policies in Microsoft Teams](manage-voice-routing-policies.md).</span></span>

### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="a120f-123">Включить Location-Based маршрутов для сетевых сайтов</span><span class="sxs-lookup"><span data-stu-id="a120f-123">Enable Location-Based Routing for network sites</span></span>

<span data-ttu-id="a120f-124">В Location-Based включить маршрутную маршрутику для сайтов, для которые необходимо навести ограничения.</span><span class="sxs-lookup"><span data-stu-id="a120f-124">Enable Location-Based Routing for your sites that need to enforce routing restrictions.</span></span> <span data-ttu-id="a120f-125">Для этого в левой области навигации Центра администрирования Microsoft Teams перейдите в топологию сети расположений, выберите сетевой сайт, нажмите кнопку "Изменить" и включайте маршрутику на основе  >   **расположения.** </span><span class="sxs-lookup"><span data-stu-id="a120f-125">To do this, in the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, select a network site, click **Edit**, and then turn on **Location based routing**.</span></span>  

<span data-ttu-id="a120f-126">Дополнительные узнать см. в [топологии "Управление сетью".](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="a120f-126">To learn more, see [Manage your network topology](manage-your-network-topology.md).</span></span>

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="a120f-127">Включить Location-Based маршрутов для шлюзов</span><span class="sxs-lookup"><span data-stu-id="a120f-127">Enable Location-Based Routing for gateways</span></span>

<span data-ttu-id="a120f-128">В Location-Based перенастройку маршрутов шлюзам, которые перена маршрутируют вызовы на шлюзы STN, которые перена могут перенапорять вызовы на ПС, и связать сетевой сайт, на котором находится шлюз.</span><span class="sxs-lookup"><span data-stu-id="a120f-128">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span> 

1. <span data-ttu-id="a120f-129">В области навигации слева перейдите к маршруту **Voice** Direct Routing и выберите вкладку  >   **"SBCs".**</span><span class="sxs-lookup"><span data-stu-id="a120f-129">In the left navigation, go to **Voice** > **Direct Routing**, and then click the **SBCs** tab.</span></span>
2. <span data-ttu-id="a120f-130">Выберите SBC и нажмите кнопку **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="a120f-130">Select the SBC, and then click **Edit**.</span></span> 
3. <span data-ttu-id="a120f-131">В **области "Маршрутизация на основе расположения" и "Оптимизация мультимедиа"** включите ее. </span><span class="sxs-lookup"><span data-stu-id="a120f-131">Under **Location based routing and media optimization**, turn on **Enable location based routing**.</span></span>
4. <span data-ttu-id="a120f-132">Укажите ИД сайта шлюза, а затем укажите режим обхода.</span><span class="sxs-lookup"><span data-stu-id="a120f-132">Specify the gateway site ID, and then set the bypass mode.</span></span>
5. <span data-ttu-id="a120f-133">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a120f-133">Click **Save**.</span></span>

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="a120f-134">Включить Location-Based маршрутов для политик звонков</span><span class="sxs-lookup"><span data-stu-id="a120f-134">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="a120f-135">Чтобы принудительно Location-Based маршрутизов для определенных пользователей, установите для них политику звонков, чтобы запретить обход платных звонков по ДНР.</span><span class="sxs-lookup"><span data-stu-id="a120f-135">To enforce Location-Based Routing for specific users, set up the user's calling policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="a120f-136">Для этого включите параметр "Запретить платный **обход"** в политике звонков.</span><span class="sxs-lookup"><span data-stu-id="a120f-136">To do this, turn on the **Prevent toll bypass** setting in the calling policy.</span></span>

<span data-ttu-id="a120f-137">Подробнее см. в [политиках звонков в Teams.](teams-calling-policy.md)</span><span class="sxs-lookup"><span data-stu-id="a120f-137">To learn more, see [Calling policies in Teams](teams-calling-policy.md).</span></span>

## <a name="using-powershell"></a><span data-ttu-id="a120f-138">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="a120f-138">Using PowerShell</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="a120f-139">Включить Location-Based маршрутии для пользователей</span><span class="sxs-lookup"><span data-stu-id="a120f-139">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="a120f-140">Для этого [используйте cmdlet Set-CsOnlinePstnUsage.](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="a120f-140">Use the [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="a120f-141">Для нескольких вариантов использования разделять каждое использование запятой.</span><span class="sxs-lookup"><span data-stu-id="a120f-141">For multiple usages, separate each usage with a comma.</span></span>

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="a120f-142">Например:</span><span class="sxs-lookup"><span data-stu-id="a120f-142">For example:</span></span>
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="a120f-143">Используйте cmdlet [New-CsOnlineVoiceRoutingPolicy,](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) чтобы создать политику маршрутизации голоса, чтобы связать пользователя с соответствующими использованием ННР.</span><span class="sxs-lookup"><span data-stu-id="a120f-143">Use the [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="a120f-144">При назначении использования ПС НН для политики голосовой маршрутки убедитесь, что вы делаете одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="a120f-144">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="a120f-145">Использование ННР, связанных с голосовой маршрутией, при использовании локального шлюза STN на сайте</span><span class="sxs-lookup"><span data-stu-id="a120f-145">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="a120f-146">Использование ННР, связанных с голосовой маршрутией, в которой используется шлюз ННР, расположенный в регионе, где Location-Based маршруты не нужны.</span><span class="sxs-lookup"><span data-stu-id="a120f-146">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="a120f-147">В этом примере мы создадим две новые политики маршрутинга голосовой связи и назначим им использование услуг ННР.</span><span class="sxs-lookup"><span data-stu-id="a120f-147">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="a120f-148">В таблице ниже показаны политики маршрутинга голосовой связи, определенные в данном примере.</span><span class="sxs-lookup"><span data-stu-id="a120f-148">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="a120f-149">Политика маршрутинга голосовой почты 1</span><span class="sxs-lookup"><span data-stu-id="a120f-149">Voice routing policy 1</span></span>|<span data-ttu-id="a120f-150">Политика маршрутинга голосовой почты 2</span><span class="sxs-lookup"><span data-stu-id="a120f-150">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="a120f-151">Online voice policy ID</span><span class="sxs-lookup"><span data-stu-id="a120f-151">Online voice policy ID</span></span>   |<span data-ttu-id="a120f-152">Зауминая политика маршрутинга голосовой почты в Интернете</span><span class="sxs-lookup"><span data-stu-id="a120f-152">Delhi online voice routing policy</span></span>   |<span data-ttu-id="a120f-153">Политика сетевой маршрутии голосовой почты</span><span class="sxs-lookup"><span data-stu-id="a120f-153">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="a120f-154">Использование сетевых услуг ННР</span><span class="sxs-lookup"><span data-stu-id="a120f-154">Online PSTN usages</span></span>  |<span data-ttu-id="a120f-155">Длинное расстояние</span><span class="sxs-lookup"><span data-stu-id="a120f-155">Long Distance</span></span>  |<span data-ttu-id="a120f-156">Междугородние, локальные, внутренние</span><span class="sxs-lookup"><span data-stu-id="a120f-156">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="a120f-157">Используйте [cmdlet Grant-CsOnlineVoiceRoutingPolicy,](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) чтобы связать сетевые политики маршрутизации с пользователями, которым требуется навести ограничения маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="a120f-157">Use the [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="a120f-158">Включить Location-Based маршрутов для сетевых сайтов</span><span class="sxs-lookup"><span data-stu-id="a120f-158">Enable Location-Based Routing for network sites</span></span>

1.  <span data-ttu-id="a120f-159">Используйте командлет [Set-CsTenantNetworkSite,](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) чтобы включить Location-Based маршрутизации и связать политики голосовой маршрутизации с сетевыми сайтами, которые должны применять ограничения маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="a120f-159">Use the [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="a120f-160">В этом примере мы Location-Based маршрутику для сайтов "Висяк" и "Приодерев".</span><span class="sxs-lookup"><span data-stu-id="a120f-160">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="a120f-161">В таблице ниже показаны сайты, для Location-Based маршрутов в этом примере.</span><span class="sxs-lookup"><span data-stu-id="a120f-161">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="a120f-162">Сайт 1 (Висяк)</span><span class="sxs-lookup"><span data-stu-id="a120f-162">Site 1 (Delhi)</span></span>  |<span data-ttu-id="a120f-163">Сайт 2 (Приокрет)</span><span class="sxs-lookup"><span data-stu-id="a120f-163">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="a120f-164">Имя сайта</span><span class="sxs-lookup"><span data-stu-id="a120f-164">Site name</span></span>    |<span data-ttu-id="a120f-165">Сайт 1 (Висяк)</span><span class="sxs-lookup"><span data-stu-id="a120f-165">Site 1 (Delhi)</span></span>    |<span data-ttu-id="a120f-166">Сайт 2 (Приокрет)</span><span class="sxs-lookup"><span data-stu-id="a120f-166">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="a120f-167">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="a120f-167">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="a120f-168">Верно</span><span class="sxs-lookup"><span data-stu-id="a120f-168">True</span></span>    |<span data-ttu-id="a120f-169">Верно</span><span class="sxs-lookup"><span data-stu-id="a120f-169">True</span></span>    |
    |<span data-ttu-id="a120f-170">Подсети</span><span class="sxs-lookup"><span data-stu-id="a120f-170">Subnets</span></span>     |<span data-ttu-id="a120f-171">Подсеть 1 (Ви2)</span><span class="sxs-lookup"><span data-stu-id="a120f-171">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="a120f-172">Подсеть 2 (Приокрет)</span><span class="sxs-lookup"><span data-stu-id="a120f-172">Subnet 2 (Hyderabad)</span></span>     |

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="a120f-173">Включить Location-Based маршрутов для шлюзов</span><span class="sxs-lookup"><span data-stu-id="a120f-173">Enable Location-Based Routing for gateways</span></span>

1. <span data-ttu-id="a120f-174">С помощью [cmdlet new-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) можно создать конфигурацию шлюза для каждого шлюза или сайта сети.</span><span class="sxs-lookup"><span data-stu-id="a120f-174">Use the [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="a120f-175">Если с системой связано несколько шлюзов (например, шлюз или УАКС), измените каждый шлюз, чтобы включить Location-Based маршрутов.</span><span class="sxs-lookup"><span data-stu-id="a120f-175">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="a120f-176">В этом примере для каждого шлюза создается одна конфигурация.</span><span class="sxs-lookup"><span data-stu-id="a120f-176">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    <span data-ttu-id="a120f-177">Дополнительные сведения см. [в сведениях о настройке прямой маршрутинга.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="a120f-177">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="a120f-178">Используйте для этого Location-Based маршрутов шлюзов с помощью Location-Based [CSOnlinePSTNGateway.](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="a120f-178">Use the [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="a120f-179">В Location-Based перенастройку маршрутов шлюзам, которые перена маршрутируют вызовы на шлюзы STN, которые перена могут перенапорять вызовы на ПС, и связать сетевой сайт, на котором находится шлюз.</span><span class="sxs-lookup"><span data-stu-id="a120f-179">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="a120f-180">В этом примере мы Location-Based маршрутику для каждого шлюза, связанного со шлюзами ННР, на сайтах "Висяк" и "Висяк".</span><span class="sxs-lookup"><span data-stu-id="a120f-180">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    <span data-ttu-id="a120f-181">Не в Location-Based перенастройки шлюзов, которые не перена могут перенаупорять вызовы через ПСО.</span><span class="sxs-lookup"><span data-stu-id="a120f-181">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="a120f-182">Однако вам все равно придется связать шлюз с сетевым сайтом, на котором расположена система.</span><span class="sxs-lookup"><span data-stu-id="a120f-182">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="a120f-183">Это связано с темLocation-Based что для звонков по ПС, которые подключаются к конечным точкам, подключенным через этот шлюз, необходимо навести ограничения маршрутинга.</span><span class="sxs-lookup"><span data-stu-id="a120f-183">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="a120f-184">В этом примере Location-Based для каждого шлюза, связанного с системами УАПС, на сайтах "Висячай" и "Подсистема" не включена маршрутка.</span><span class="sxs-lookup"><span data-stu-id="a120f-184">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="a120f-185">Включить Location-Based маршрутов для политик звонков</span><span class="sxs-lookup"><span data-stu-id="a120f-185">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="a120f-186">Чтобы принудительно Location-Based маршрутику для определенных пользователей, установите для них голосовую политику, чтобы запретить обход платных номеров ТСО.</span><span class="sxs-lookup"><span data-stu-id="a120f-186">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="a120f-187">Используйте [cmdlet Grant-CsTeamsCallingPolicy,](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) чтобы Location-Based маршрутизации, предотвращая обход платных номеров ДНР.</span><span class="sxs-lookup"><span data-stu-id="a120f-187">Use the [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="a120f-188">В этом примере мы предотвращаем обход платных номеров ННР в политиках звонков пользователя 1.</span><span class="sxs-lookup"><span data-stu-id="a120f-188">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a><span data-ttu-id="a120f-189">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="a120f-189">Related topics</span></span>

- [<span data-ttu-id="a120f-190">Параметры сети для функций облачного голосового связи в Teams</span><span class="sxs-lookup"><span data-stu-id="a120f-190">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)