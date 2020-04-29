---
title: Управление топологией сети для облачных функций голосовой связи в Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Сведения о том, как настроить параметры сети для функций голосовой связи в облаке в Microsoft Teams.
ms.openlocfilehash: 2f615de14cb38c24a1789b968e7c77e38698e26d
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888708"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a><span data-ttu-id="f9d27-103">Управление топологией сети для облачных функций голосовой связи в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f9d27-103">Manage your network topology for cloud voice features in Microsoft Teams</span></span>

<span data-ttu-id="f9d27-104">Если в вашей организации используется [Прямая маршрутизация](location-based-routing-plan.md) или [динамический вызов экстренной](configure-dynamic-emergency-calling.md)помощи, необходимо настроить параметры сети для использования в этих функциях голосовой связи в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f9d27-104">If your organization is deploying [Location-Based Routing for Direct Routing](location-based-routing-plan.md) or [dynamic emergency calling](configure-dynamic-emergency-calling.md), you must configure network settings for use with these cloud voice features in Microsoft Teams.</span></span> <span data-ttu-id="f9d27-105">Параметры сети используются для определения местоположения клиента Teams и включения сетевых регионов, сетевых сайтов, подсетей и доверенных IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="f9d27-105">Network settings are used to determine the location of a Teams client and include network regions, network sites, subnets, and trusted IP addresses.</span></span> <span data-ttu-id="f9d27-106">В зависимости от того, какая функция голосовой связи облачных функций и возможностей развертывается, вы можете настроить некоторые или все эти параметры.</span><span class="sxs-lookup"><span data-stu-id="f9d27-106">Depending on the cloud voice feature and capability that you're deploying, you configure some or all these settings.</span></span> <span data-ttu-id="f9d27-107">Дополнительные сведения об этих терминах можно найти в разделе [Параметры сети для функций голосовой связи в облаке](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="f9d27-107">To learn more about these terms, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="f9d27-108">Вы настраиваете параметры сети на странице **Сетевая топология** центра администрирования Microsoft Teams или с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f9d27-108">You configure network settings on the **Network topology** page of the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="f9d27-109">Настройка параметров сети в центре администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f9d27-109">Configure network settings in the Microsoft Teams admin center</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="f9d27-110">Вы определяете сетевые регионы, сетевые сайты и подсети на вкладке " **Сетевые сайты** " на странице " **топология сети** ".</span><span class="sxs-lookup"><span data-stu-id="f9d27-110">You define network regions, network sites, and subnets on the **Network sites** tab of the **Network topology** page.</span></span> <span data-ttu-id="f9d27-111">Здесь вы можете создать или изменить сетевой сайт, связать сайт с сетевым регионом, связать подсеть с сайтом, включить маршрутизацию на основе местоположения и назначить узлу политики для экстренного реагирования.</span><span class="sxs-lookup"><span data-stu-id="f9d27-111">Here, you can create or modify a network site, associate a site with a network region, associate a subnet to the site, turn on Location-based Routing, and assign emergency policies to the site.</span></span> <span data-ttu-id="f9d27-112">Вы также можете добавить сетевые регионы, которые можно использовать глобально для всех сайтов.</span><span class="sxs-lookup"><span data-stu-id="f9d27-112">You can also add network regions that can be used globally for all sites.</span></span>

#### <a name="add-and-configure-a-network-site"></a><span data-ttu-id="f9d27-113">Добавление и настройка сетевого сайта</span><span class="sxs-lookup"><span data-stu-id="f9d27-113">Add and configure a network site</span></span>

1. <span data-ttu-id="f9d27-114">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел **Расположение** > **топологии сети**и откройте вкладку **Сетевые сайты** .</span><span class="sxs-lookup"><span data-stu-id="f9d27-114">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Network sites** tab.</span></span>
2. <span data-ttu-id="f9d27-115">Нажмите кнопку **создать**, а затем введите имя и описание сайта.</span><span class="sxs-lookup"><span data-stu-id="f9d27-115">Click **New**, and then enter a name and description for the site.</span></span>

    ![Снимок экрана: страница "Добавление сетевого сайта"](media/manage-network-topology-add-site.png)

3. <span data-ttu-id="f9d27-117">Чтобы связать сайт с сетевым регионом, щелкните **ссылку регион сети**, выберите существующий регион или нажмите кнопку **Добавить** , чтобы добавить регион, а затем нажмите кнопку **связать**.</span><span class="sxs-lookup"><span data-stu-id="f9d27-117">To associate the site with a network region, click **Link network region**, select an existing region or click **Add** to add a region, and then click **Link**.</span></span>  
4. <span data-ttu-id="f9d27-118">Чтобы включить маршрутизацию на основе местоположения для сайта, включите функцию **маршрутизации на основе**местоположения.</span><span class="sxs-lookup"><span data-stu-id="f9d27-118">To enable Location-Based Routing for the site, turn on **Location based routing**.</span></span>
5. <span data-ttu-id="f9d27-119">Чтобы назначить на сайт политики службы экстренной помощи, выполните одно или оба указанных ниже действия.</span><span class="sxs-lookup"><span data-stu-id="f9d27-119">To assign emergency services policies to the site, do one or both of the following:</span></span>

    - <span data-ttu-id="f9d27-120">Если в вашей организации используются планы звонков или прямая маршрутизация на телефонную систему, в разделе **политика вызова экстренной политики**выберите нужную политику.</span><span class="sxs-lookup"><span data-stu-id="f9d27-120">If your organization uses Calling Plans or deployed Phone System Direct Routing, under **Emergency calling policy**, select the policy that you want.</span></span>
    - <span data-ttu-id="f9d27-121">Если ваша организация развернута прямая маршрутизация телефонной системы, выберите нужную политику в разделе **Политика маршрутизации вызова экстренной**помощи.</span><span class="sxs-lookup"><span data-stu-id="f9d27-121">If your organization deployed Phone System Direct Routing, under **Emergency call routing policy**, select the  policy that you want.</span></span>

6. <span data-ttu-id="f9d27-122">Чтобы связать подсеть с сайтом, в разделе **подсети**нажмите кнопку **Добавить подсети**.</span><span class="sxs-lookup"><span data-stu-id="f9d27-122">To associate a subnet to the site, under **Subnets**, click **Add subnets**.</span></span> <span data-ttu-id="f9d27-123">Укажите версию IP, IP-адрес, диапазон сети, добавьте описание и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="f9d27-123">Specify the IP version, IP address, network range, add a description, and then click **Apply**.</span></span> <span data-ttu-id="f9d27-124">Каждая подсеть должна быть связана с определенным сайтом.</span><span class="sxs-lookup"><span data-stu-id="f9d27-124">Each subnet must be associated with a specific site.</span></span>
7. <span data-ttu-id="f9d27-125">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f9d27-125">Click **Save**.</span></span>

#### <a name="modify-a-network-site"></a><span data-ttu-id="f9d27-126">Изменение сетевого сайта</span><span class="sxs-lookup"><span data-stu-id="f9d27-126">Modify a network site</span></span>

1. <span data-ttu-id="f9d27-127">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел **Расположение** > **топологии сети**и откройте вкладку **Сетевые сайты** .</span><span class="sxs-lookup"><span data-stu-id="f9d27-127">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Network sites** tab.</span></span>
2. <span data-ttu-id="f9d27-128">Выберите сайт, щелкнув слева от его имени, а затем нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="f9d27-128">Select the site by clicking to the left of the site name, and then click **Edit**.</span></span>
3. <span data-ttu-id="f9d27-129">Внесите нужные изменения и нажмите кнопку **Сохранить.**</span><span class="sxs-lookup"><span data-stu-id="f9d27-129">Make the changes that you want, and then click **Save.**</span></span>

### <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="f9d27-130">Управление внешними надежными IP-адресами</span><span class="sxs-lookup"><span data-stu-id="f9d27-130">Manage external trusted IP addresses</span></span>

<span data-ttu-id="f9d27-131">Вы управляете внешними доверенными IP-адресами на вкладке **Надежные** IP-адреса на странице " **топология сети** " в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f9d27-131">You manage external trusted IP addresses on the **Trusted IPs** tab on the **Network topology** page of the Microsoft Teams admin center.</span></span> <span data-ttu-id="f9d27-132">Вы можете добавить неограниченное количество внешних доверенных IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="f9d27-132">You can add an unlimited number of external trusted IP addresses.</span></span>

#### <a name="add-a-trusted-ip-address"></a><span data-ttu-id="f9d27-133">Добавление надежного IP-адреса</span><span class="sxs-lookup"><span data-stu-id="f9d27-133">Add a trusted IP address</span></span>

1. <span data-ttu-id="f9d27-134">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел **Расположение** > **топологии сети**и откройте вкладку **Надежные IP** .</span><span class="sxs-lookup"><span data-stu-id="f9d27-134">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Trusted IPs** tab.</span></span>
2. <span data-ttu-id="f9d27-135">Выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="f9d27-135">Click **New**.</span></span>
3. <span data-ttu-id="f9d27-136">В области **Добавить доверенный IP-адрес** укажите версию IP-адреса, IP-адрес, диапазон сети, добавьте описание и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="f9d27-136">In the **Add trusted IP address** pane, specify the IP version, IP address, network range, add a description, and then click **Apply**.</span></span>

    ![Снимок экрана: область "добавить доверенный IP-адрес"](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a><span data-ttu-id="f9d27-138">Изменить доверенный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="f9d27-138">Edit a trusted IP address</span></span>

1. <span data-ttu-id="f9d27-139">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел **Расположение** > **топологии сети**и откройте вкладку **Надежные IP** .</span><span class="sxs-lookup"><span data-stu-id="f9d27-139">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Trusted IPs** tab.</span></span>
2. <span data-ttu-id="f9d27-140">Выберите IP-адрес, щелкнув слева от него и нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="f9d27-140">Select the IP address by clicking to the left of it, and then click **Edit**.</span></span>
3. <span data-ttu-id="f9d27-141">В области **изменить доверенный IP-адрес** внесите нужные изменения и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="f9d27-141">In the **Edit trusted IP address** pane, make the changes that you want, and then click **Apply**.</span></span>

## <a name="configure-network-settings-using-powershell"></a><span data-ttu-id="f9d27-142">Настройка параметров сети с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="f9d27-142">Configure network settings using PowerShell</span></span>

<span data-ttu-id="f9d27-143">Для выполнения действий, описанных в этом разделе, вам потребуется ознакомиться с командлетами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f9d27-143">To complete the steps in this section, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="f9d27-144">Дополнительные сведения можно найти в разделе [Общие сведения о Teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f9d27-144">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="f9d27-145">Определение регионов сети</span><span class="sxs-lookup"><span data-stu-id="f9d27-145">Define network regions</span></span>

 <span data-ttu-id="f9d27-146">Используйте командлет [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion) , чтобы определить регионы сети.</span><span class="sxs-lookup"><span data-stu-id="f9d27-146">Use the [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion) cmdlet to define network regions.</span></span> <span data-ttu-id="f9d27-147">Обратите внимание, что параметр RegionID является логическим именем, которое представляет собой географию области и не имеет зависимостей или ограничений и &lt;не является&gt; обязательным параметром идентификатора сайта CentralSite.</span><span class="sxs-lookup"><span data-stu-id="f9d27-147">Note that the RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions and the CentralSite &lt;site ID&gt; parameter is optional.</span></span>

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="f9d27-148">В этом примере мы создаем сетевой регион с именем Индии.</span><span class="sxs-lookup"><span data-stu-id="f9d27-148">In this example, we create a network region named India.</span></span>
```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

<span data-ttu-id="f9d27-149">Дополнительные сведения можно найти в разделе [Set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworkregion).</span><span class="sxs-lookup"><span data-stu-id="f9d27-149">See also [Set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworkregion).</span></span>

### <a name="define-network-sites"></a><span data-ttu-id="f9d27-150">Определение сетевых сайтов</span><span class="sxs-lookup"><span data-stu-id="f9d27-150">Define network sites</span></span>

<span data-ttu-id="f9d27-151">С помощью командлета [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) можно определять сетевые сайты.</span><span class="sxs-lookup"><span data-stu-id="f9d27-151">Use the [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet to define network sites.</span></span> <span data-ttu-id="f9d27-152">Каждый сетевой сайт должен быть связан с сетевым регионом.</span><span class="sxs-lookup"><span data-stu-id="f9d27-152">Each network site must be associated with a network region.</span></span>

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="f9d27-153">В этом примере мы создаем в регионе Индии две новые сетевые сайты, Delhi и Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="f9d27-153">In this example, we create two new network sites, Delhi and Hyderabad, in the India region.</span></span>

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

<span data-ttu-id="f9d27-154">В следующей таблице показаны сетевые сайты, определенные в этом примере.</span><span class="sxs-lookup"><span data-stu-id="f9d27-154">The following table shows the network sites defined in this example.</span></span>

||<span data-ttu-id="f9d27-155">Сайт 1</span><span class="sxs-lookup"><span data-stu-id="f9d27-155">Site 1</span></span> |<span data-ttu-id="f9d27-156">Сайт 2</span><span class="sxs-lookup"><span data-stu-id="f9d27-156">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="f9d27-157">Идентификатор сайта</span><span class="sxs-lookup"><span data-stu-id="f9d27-157">Site ID</span></span>    |    <span data-ttu-id="f9d27-158">Сайт 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="f9d27-158">Site 1 (Delhi)</span></span>     |  <span data-ttu-id="f9d27-159">Сайт 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="f9d27-159">Site 2 (Hyderabad)</span></span>       |
|<span data-ttu-id="f9d27-160">КОД региона</span><span class="sxs-lookup"><span data-stu-id="f9d27-160">Region ID</span></span>  |     <span data-ttu-id="f9d27-161">Регион 1 (Индия)</span><span class="sxs-lookup"><span data-stu-id="f9d27-161">Region 1 (India)</span></span>    |   <span data-ttu-id="f9d27-162">Регион 1 (Индия)</span><span class="sxs-lookup"><span data-stu-id="f9d27-162">Region 1 (India)</span></span>      |

<span data-ttu-id="f9d27-163">Дополнительные сведения можно найти в разделе [Set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite).</span><span class="sxs-lookup"><span data-stu-id="f9d27-163">See also [Set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite).</span></span>

### <a name="define-network-subnets"></a><span data-ttu-id="f9d27-164">Определение подсетей сети</span><span class="sxs-lookup"><span data-stu-id="f9d27-164">Define network subnets</span></span>

<span data-ttu-id="f9d27-165">С помощью командлета [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) можно определять сетевые подсети и связывать их с сетевыми сайтами.</span><span class="sxs-lookup"><span data-stu-id="f9d27-165">Use the [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet to define network subnets and associate them to network sites.</span></span> <span data-ttu-id="f9d27-166">Каждая сетевая подсеть может быть связана только с одним сайтом.</span><span class="sxs-lookup"><span data-stu-id="f9d27-166">Each network subnet can only be associated with one site.</span></span>

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="f9d27-167">В этом примере мы создаем связь между подсетью 192.168.0.0 и сетевым сайтом Delhi и между подсетью 2001:4898: E8:25:844E: 926f: 85ad: dd8e и на сайте Hyderabad Network.</span><span class="sxs-lookup"><span data-stu-id="f9d27-167">In this example, we create an association between subnet 192.168.0.0 and the Delhi network site and between subnet 2001:4898:e8:25:844e:926f:85ad:dd8e and the Hyderabad network site.</span></span>

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"
```

<span data-ttu-id="f9d27-168">В приведенной ниже таблице указаны подсети, определенные в этом примере.</span><span class="sxs-lookup"><span data-stu-id="f9d27-168">The following table shows the subnets defined in this example.</span></span>

||<span data-ttu-id="f9d27-169">Сайт 1</span><span class="sxs-lookup"><span data-stu-id="f9d27-169">Site 1</span></span> |<span data-ttu-id="f9d27-170">Сайт 2</span><span class="sxs-lookup"><span data-stu-id="f9d27-170">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="f9d27-171">КОД подсети</span><span class="sxs-lookup"><span data-stu-id="f9d27-171">Subnet ID</span></span>   |    <span data-ttu-id="f9d27-172">172.16.0.0</span><span class="sxs-lookup"><span data-stu-id="f9d27-172">192.168.0.0</span></span>     |  <span data-ttu-id="f9d27-173">2001:4898: E8:25:844E: 926f: 85ad: dd8e</span><span class="sxs-lookup"><span data-stu-id="f9d27-173">2001:4898:e8:25:844e:926f:85ad:dd8e</span></span>     |
|<span data-ttu-id="f9d27-174">Маски</span><span class="sxs-lookup"><span data-stu-id="f9d27-174">Mask</span></span>  |     <span data-ttu-id="f9d27-175">24</span><span class="sxs-lookup"><span data-stu-id="f9d27-175">24</span></span>    |   <span data-ttu-id="f9d27-176">120</span><span class="sxs-lookup"><span data-stu-id="f9d27-176">120</span></span>      |
|<span data-ttu-id="f9d27-177">Идентификатор сайта</span><span class="sxs-lookup"><span data-stu-id="f9d27-177">Site ID</span></span>  | <span data-ttu-id="f9d27-178">Сайт (Delhi)</span><span class="sxs-lookup"><span data-stu-id="f9d27-178">Site (Delhi)</span></span> | <span data-ttu-id="f9d27-179">Сайт 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="f9d27-179">Site 2 (Hyderabad)</span></span> |

<span data-ttu-id="f9d27-180">Если вы используете несколько подсетей, вы можете импортировать CSV-файл с помощью такого сценария, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="f9d27-180">For multiple subnets, you can import a CSV file by using a script such as the following.</span></span>

```PowerShell
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```

<span data-ttu-id="f9d27-181">В этом примере CSV-файл выглядит примерно так:</span><span class="sxs-lookup"><span data-stu-id="f9d27-181">In this example, the CSV file looks something like this:</span></span>

```console
Identity, Mask, SiteID
172.11.12.0, 24, Redmond
172.11.13.0, 24, Chicago
172.11.14.0, 25, Vancouver
172.11.15.0, 28, Paris
```

<span data-ttu-id="f9d27-182">Дополнительные сведения можно найти в разделе [Set-CsTenantNetworkSubnet](hhttps://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksubnet).</span><span class="sxs-lookup"><span data-stu-id="f9d27-182">See also [Set-CsTenantNetworkSubnet](hhttps://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksubnet).</span></span>

### <a name="define-external-subnets-external-trusted-ip-addresses"></a><span data-ttu-id="f9d27-183">Определение внешних подсетей (внешние доверенные IP-адреса)</span><span class="sxs-lookup"><span data-stu-id="f9d27-183">Define external subnets (external trusted IP addresses)</span></span>

<span data-ttu-id="f9d27-184">С помощью командлета [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) можно определять внешние подсети и назначать их клиентам.</span><span class="sxs-lookup"><span data-stu-id="f9d27-184">Use the [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet to define external subnets and assign them to the tenant.</span></span> <span data-ttu-id="f9d27-185">Вы можете определить неограниченное количество внешних подсетей для клиента.</span><span class="sxs-lookup"><span data-stu-id="f9d27-185">You can define an unlimited number of external subnets for a tenant.</span></span>

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

<span data-ttu-id="f9d27-186">Например:</span><span class="sxs-lookup"><span data-stu-id="f9d27-186">For example:</span></span>

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

<span data-ttu-id="f9d27-187">Дополнительные сведения можно найти в разделе [Set-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/set-cstenanttrustedipaddress).</span><span class="sxs-lookup"><span data-stu-id="f9d27-187">See also [Set-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/set-cstenanttrustedipaddress).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f9d27-188">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="f9d27-188">Related topics</span></span>

- [<span data-ttu-id="f9d27-189">Параметры сети для функций голосовой связи в облаке в Teams</span><span class="sxs-lookup"><span data-stu-id="f9d27-189">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
