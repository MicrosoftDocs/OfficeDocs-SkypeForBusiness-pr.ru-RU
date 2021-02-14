---
title: Управление топологией сети для функций облачного голосового управления в Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
- m365initiative-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Узнайте, как настроить параметры сети для функций облачного голосового связи в Microsoft Teams.
ms.openlocfilehash: 7d8bc7f06934134538fca59a3f19285d97756e2f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802579"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a><span data-ttu-id="893bf-103">Управление топологией сети для функций облачного голосового управления в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="893bf-103">Manage your network topology for cloud voice features in Microsoft Teams</span></span>

<span data-ttu-id="893bf-104">Если ваша организация [](location-based-routing-plan.md) развертывает маршрутную маршрутику на основе местоположения для прямой маршрутизации или динамических экстренных вызовов, [](configure-dynamic-emergency-calling.md)необходимо настроить параметры сети для использования с этими облачными функциями голосовой связи в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="893bf-104">If your organization is deploying [Location-Based Routing for Direct Routing](location-based-routing-plan.md) or [dynamic emergency calling](configure-dynamic-emergency-calling.md), you must configure network settings for use with these cloud voice features in Microsoft Teams.</span></span> <span data-ttu-id="893bf-105">Параметры сети используются для определения расположения клиента Teams и включают сетевые регионы, сетевые сайты, подсети и надежные IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="893bf-105">Network settings are used to determine the location of a Teams client and include network regions, network sites, subnets, and trusted IP addresses.</span></span> <span data-ttu-id="893bf-106">В зависимости от функции облачного голосового голоса и возможности развертывания вы можете настроить некоторые или все эти параметры.</span><span class="sxs-lookup"><span data-stu-id="893bf-106">Depending on the cloud voice feature and capability that you're deploying, you configure some or all these settings.</span></span> <span data-ttu-id="893bf-107">Подробнее об этих условиях см. в параметрах сети для [функций облачного голосового связи.](cloud-voice-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="893bf-107">To learn more about these terms, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="893bf-108">Параметры сети настраиваются на **странице** топологии сети Центра администрирования Microsoft Teams или с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="893bf-108">You configure network settings on the **Network topology** page of the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="893bf-109">Настройка параметров сети в Центре администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="893bf-109">Configure network settings in the Microsoft Teams admin center</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="893bf-110">На вкладке "Сетевые сайты" страницы топологии сети определяются сетевые регионы, сетевые сайты **и** подсети. </span><span class="sxs-lookup"><span data-stu-id="893bf-110">You define network regions, network sites, and subnets on the **Network sites** tab of the **Network topology** page.</span></span> <span data-ttu-id="893bf-111">Здесь можно создать или изменить сетевой сайт, связать сайт с сетевым регионом, связать с ним подсеть, включить маршрутизация на основе расположения и назначить на сайт политики экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="893bf-111">Here, you can create or modify a network site, associate a site with a network region, associate a subnet to the site, turn on Location-based Routing, and assign emergency policies to the site.</span></span> <span data-ttu-id="893bf-112">Вы также можете добавить сетевые регионы, которые можно использовать глобально для всех сайтов.</span><span class="sxs-lookup"><span data-stu-id="893bf-112">You can also add network regions that can be used globally for all sites.</span></span>

#### <a name="add-and-configure-a-network-site"></a><span data-ttu-id="893bf-113">Добавление и настройка сетевого сайта</span><span class="sxs-lookup"><span data-stu-id="893bf-113">Add and configure a network site</span></span>

1. <span data-ttu-id="893bf-114">В левой области навигации Центра администрирования Microsoft Teams перейдите в топологию **сетей Locations** и щелкните вкладку  >   **"Сетевые сайты".**</span><span class="sxs-lookup"><span data-stu-id="893bf-114">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Network sites** tab.</span></span>
2. <span data-ttu-id="893bf-115">Нажмите **кнопку**"Добавить" и введите имя и описание сайта.</span><span class="sxs-lookup"><span data-stu-id="893bf-115">Click **Add**, and then enter a name and description for the site.</span></span>

    ![Снимок экрана: страница добавления сайта сети](media/manage-network-topology-add-site.png)

3. <span data-ttu-id="893bf-117">Чтобы связать сайт с сетевым регионом, щелкните "Добавить  регион сети", выберите существующий регион или нажмите кнопку "Добавить", чтобы добавить регион, а затем нажмите кнопку **"Ссылка".**</span><span class="sxs-lookup"><span data-stu-id="893bf-117">To associate the site with a network region, click **Add network region**, select an existing region or click **Add** to add a region, and then click **Link**.</span></span>  
4. <span data-ttu-id="893bf-118">Чтобы включить Location-Based для сайта, включив **маршрутную маршрутку на основе расположения.**</span><span class="sxs-lookup"><span data-stu-id="893bf-118">To enable Location-Based Routing for the site, turn on **Location based routing**.</span></span>
5. <span data-ttu-id="893bf-119">Чтобы назначить на сайт политики экстренных служб, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="893bf-119">To assign emergency services policies to the site, do one or both of the following:</span></span>

    - <span data-ttu-id="893bf-120">Если в вашей организации используются планы звонков или развернута прямая маршрутия телефонной системы, в соответствии с политикой экстренных вызовов **выберите** политику.</span><span class="sxs-lookup"><span data-stu-id="893bf-120">If your organization uses Calling Plans or deployed Phone System Direct Routing, under **Emergency calling policy**, select the policy that you want.</span></span>
    - <span data-ttu-id="893bf-121">Если в вашей организации развернута прямая маршрутия телефонной системы, выберите ее в соответствии с политикой маршрутизации экстренных вызовов.</span><span class="sxs-lookup"><span data-stu-id="893bf-121">If your organization deployed Phone System Direct Routing, under **Emergency call routing policy**, select the  policy that you want.</span></span>

6. <span data-ttu-id="893bf-122">Чтобы связать подсеть с сайтом, в **подсетях** нажмите кнопку **"Добавить подсети".**</span><span class="sxs-lookup"><span data-stu-id="893bf-122">To associate a subnet to the site, under **Subnets**, click **Add subnets**.</span></span> <span data-ttu-id="893bf-123">Укажите версию IP-адреса, IP-адрес, диапазон сети, добавьте описание и нажмите кнопку **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="893bf-123">Specify the IP version, IP address, network range, add a description, and then click **Apply**.</span></span> <span data-ttu-id="893bf-124">Каждую подсеть необходимо связывать с определенным сайтом.</span><span class="sxs-lookup"><span data-stu-id="893bf-124">Each subnet must be associated with a specific site.</span></span>
7. <span data-ttu-id="893bf-125">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="893bf-125">Click **Save**.</span></span>

#### <a name="modify-a-network-site"></a><span data-ttu-id="893bf-126">Изменение сайта сети</span><span class="sxs-lookup"><span data-stu-id="893bf-126">Modify a network site</span></span>

1. <span data-ttu-id="893bf-127">В левой области навигации Центра администрирования Microsoft Teams перейдите в топологию **сетей Locations** и щелкните вкладку  >   **"Сетевые сайты".**</span><span class="sxs-lookup"><span data-stu-id="893bf-127">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Network sites** tab.</span></span>
2. <span data-ttu-id="893bf-128">Выберите сайт, щелкнув слева от его имени и нажав кнопку **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="893bf-128">Select the site by clicking to the left of the site name, and then click **Edit**.</span></span>
3. <span data-ttu-id="893bf-129">Внести нужные изменения и нажмите кнопку **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="893bf-129">Make the changes that you want, and then click **Save.**</span></span>

### <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="893bf-130">Управление внешними надежными IP-адресами</span><span class="sxs-lookup"><span data-stu-id="893bf-130">Manage external trusted IP addresses</span></span>

<span data-ttu-id="893bf-131">Управление внешними надежными IP-адресами происходит  на вкладке **"Надежные IP-адреса"** на странице топологии сети Центра администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="893bf-131">You manage external trusted IP addresses on the **Trusted IPs** tab on the **Network topology** page of the Microsoft Teams admin center.</span></span> <span data-ttu-id="893bf-132">Вы можете добавить неограниченное количество внешних доверенных IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="893bf-132">You can add an unlimited number of external trusted IP addresses.</span></span>

#### <a name="add-a-trusted-ip-address"></a><span data-ttu-id="893bf-133">Добавление надежного IP-адреса</span><span class="sxs-lookup"><span data-stu-id="893bf-133">Add a trusted IP address</span></span>

1. <span data-ttu-id="893bf-134">В левой области навигации Центра администрирования Microsoft Teams перейдите в топологию **сети** locations и перейдите на вкладку  >  "Надежные **адреса IPs".**</span><span class="sxs-lookup"><span data-stu-id="893bf-134">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Trusted IPs** tab.</span></span>
2. <span data-ttu-id="893bf-135">Выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="893bf-135">Click **New**.</span></span>
3. <span data-ttu-id="893bf-136">В области "Добавление надежного **IP-адреса"** укажите версию IP-адреса, IP-адрес, диапазон сети, добавьте описание и нажмите кнопку **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="893bf-136">In the **Add trusted IP address** pane, specify the IP version, IP address, network range, add a description, and then click **Apply**.</span></span>

    ![Снимок экрана: области "Добавление доверенных IP-адресов"](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a><span data-ttu-id="893bf-138">Изменение надежного IP-адреса</span><span class="sxs-lookup"><span data-stu-id="893bf-138">Edit a trusted IP address</span></span>

1. <span data-ttu-id="893bf-139">В левой области навигации Центра администрирования Microsoft Teams перейдите в топологию **сети** locations и перейдите на вкладку  >  "Надежные **адреса IPs".**</span><span class="sxs-lookup"><span data-stu-id="893bf-139">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Trusted IPs** tab.</span></span>
2. <span data-ttu-id="893bf-140">Выберите IP-адрес, щелкнув слева от него и нажав кнопку **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="893bf-140">Select the IP address by clicking to the left of it, and then click **Edit**.</span></span>
3. <span data-ttu-id="893bf-141">В области **"Изменить надежные IP-адреса"** внесите нужные изменения и нажмите кнопку "Применить". </span><span class="sxs-lookup"><span data-stu-id="893bf-141">In the **Edit trusted IP address** pane, make the changes that you want, and then click **Apply**.</span></span>

## <a name="configure-network-settings-using-powershell"></a><span data-ttu-id="893bf-142">Настройка параметров сети с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="893bf-142">Configure network settings using PowerShell</span></span>

<span data-ttu-id="893bf-143">Для выполнения действий, которые вы выполните в этом разделе, необходимо ознакомиться с cmdlets PowerShell.</span><span class="sxs-lookup"><span data-stu-id="893bf-143">To complete the steps in this section, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="893bf-144">Дополнительные сведения см. в [обзоре Teams PowerShell.](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="893bf-144">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="893bf-145">Определение сетевых регионов</span><span class="sxs-lookup"><span data-stu-id="893bf-145">Define network regions</span></span>

 <span data-ttu-id="893bf-146">Для определения сетевых регионов используйте командлет [New-CsTenantNetworkRegion.](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion)</span><span class="sxs-lookup"><span data-stu-id="893bf-146">Use the [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion) cmdlet to define network regions.</span></span> <span data-ttu-id="893bf-147">Обратите внимание, что параметр RegionID — это логическое имя, которое представляет географическое положение региона и не имеет зависимостей и ограничений, а параметр "ИД центрального сайта" &lt; &gt; необязателен.</span><span class="sxs-lookup"><span data-stu-id="893bf-147">Note that the RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions and the CentralSite &lt;site ID&gt; parameter is optional.</span></span>

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="893bf-148">В этом примере мы создадим сетевой регион "Индия".</span><span class="sxs-lookup"><span data-stu-id="893bf-148">In this example, we create a network region named India.</span></span>
```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

<span data-ttu-id="893bf-149">См. [также Set-CsTenantNetworkRegion.](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworkregion)</span><span class="sxs-lookup"><span data-stu-id="893bf-149">See also [Set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworkregion).</span></span>

### <a name="define-network-sites"></a><span data-ttu-id="893bf-150">Определение сетевых сайтов</span><span class="sxs-lookup"><span data-stu-id="893bf-150">Define network sites</span></span>

<span data-ttu-id="893bf-151">Для определения сетевых сайтов используйте командлет [New-CsTenantNetworkSite.](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="893bf-151">Use the [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet to define network sites.</span></span> <span data-ttu-id="893bf-152">Каждый сетевой сайт должен быть связан с сетевым регионом.</span><span class="sxs-lookup"><span data-stu-id="893bf-152">Each network site must be associated with a network region.</span></span>

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="893bf-153">В этом примере мы создадим два новых сетевых сайта — "Алехи" и "Приодерха" в Индии.</span><span class="sxs-lookup"><span data-stu-id="893bf-153">In this example, we create two new network sites, Delhi and Hyderabad, in the India region.</span></span>

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

<span data-ttu-id="893bf-154">В таблице ниже показаны сетевые сайты, определенные в данном примере.</span><span class="sxs-lookup"><span data-stu-id="893bf-154">The following table shows the network sites defined in this example.</span></span>

||<span data-ttu-id="893bf-155">Сайт 1</span><span class="sxs-lookup"><span data-stu-id="893bf-155">Site 1</span></span> |<span data-ttu-id="893bf-156">Сайт 2</span><span class="sxs-lookup"><span data-stu-id="893bf-156">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="893bf-157">ИД сайта</span><span class="sxs-lookup"><span data-stu-id="893bf-157">Site ID</span></span>    |    <span data-ttu-id="893bf-158">Сайт 1 (Висяк)</span><span class="sxs-lookup"><span data-stu-id="893bf-158">Site 1 (Delhi)</span></span>     |  <span data-ttu-id="893bf-159">Сайт 2 (Приокрет)</span><span class="sxs-lookup"><span data-stu-id="893bf-159">Site 2 (Hyderabad)</span></span>       |
|<span data-ttu-id="893bf-160">ИД региона</span><span class="sxs-lookup"><span data-stu-id="893bf-160">Region ID</span></span>  |     <span data-ttu-id="893bf-161">Регион 1 (Индия)</span><span class="sxs-lookup"><span data-stu-id="893bf-161">Region 1 (India)</span></span>    |   <span data-ttu-id="893bf-162">Регион 1 (Индия)</span><span class="sxs-lookup"><span data-stu-id="893bf-162">Region 1 (India)</span></span>      |

<span data-ttu-id="893bf-163">См. [также Set-CsTenantNetworkRegion.](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite)</span><span class="sxs-lookup"><span data-stu-id="893bf-163">See also [Set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite).</span></span>

### <a name="define-network-subnets"></a><span data-ttu-id="893bf-164">Определение сетевых подсетей</span><span class="sxs-lookup"><span data-stu-id="893bf-164">Define network subnets</span></span>

<span data-ttu-id="893bf-165">Используйте [командлет New-CsTenantNetworkSubnet,](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) чтобы определить подсети сети и связать их с сетевыми сайтами.</span><span class="sxs-lookup"><span data-stu-id="893bf-165">Use the [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet to define network subnets and associate them to network sites.</span></span> <span data-ttu-id="893bf-166">Каждую сетевую подсеть можно связывать только с одним сайтом.</span><span class="sxs-lookup"><span data-stu-id="893bf-166">Each network subnet can only be associated with one site.</span></span>

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="893bf-167">В этом примере мы создадим связь между подсетей 192.168.0.0 и сетевым сайтом "Ветвь" и между подсети 2001:4898:e8:25:844e:926f:85ad:dd8e и сайтом сети Послевузова.</span><span class="sxs-lookup"><span data-stu-id="893bf-167">In this example, we create an association between subnet 192.168.0.0 and the Delhi network site and between subnet 2001:4898:e8:25:844e:926f:85ad:dd8e and the Hyderabad network site.</span></span>

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"
```

<span data-ttu-id="893bf-168">В следующей таблице показаны подсети, определенные в данном примере.</span><span class="sxs-lookup"><span data-stu-id="893bf-168">The following table shows the subnets defined in this example.</span></span>

||<span data-ttu-id="893bf-169">Сайт 1</span><span class="sxs-lookup"><span data-stu-id="893bf-169">Site 1</span></span> |<span data-ttu-id="893bf-170">Сайт 2</span><span class="sxs-lookup"><span data-stu-id="893bf-170">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="893bf-171">ИД подсети</span><span class="sxs-lookup"><span data-stu-id="893bf-171">Subnet ID</span></span>   |    <span data-ttu-id="893bf-172">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="893bf-172">192.168.0.0</span></span>     |  <span data-ttu-id="893bf-173">2001:4898:e8:25:844e:926f:85ad:dd8e</span><span class="sxs-lookup"><span data-stu-id="893bf-173">2001:4898:e8:25:844e:926f:85ad:dd8e</span></span>     |
|<span data-ttu-id="893bf-174">Маска</span><span class="sxs-lookup"><span data-stu-id="893bf-174">Mask</span></span>  |     <span data-ttu-id="893bf-175">24</span><span class="sxs-lookup"><span data-stu-id="893bf-175">24</span></span>    |   <span data-ttu-id="893bf-176">120</span><span class="sxs-lookup"><span data-stu-id="893bf-176">120</span></span>      |
|<span data-ttu-id="893bf-177">ИД сайта</span><span class="sxs-lookup"><span data-stu-id="893bf-177">Site ID</span></span>  | <span data-ttu-id="893bf-178">Сайт (Высве))</span><span class="sxs-lookup"><span data-stu-id="893bf-178">Site (Delhi)</span></span> | <span data-ttu-id="893bf-179">Сайт 2 (Приокрет)</span><span class="sxs-lookup"><span data-stu-id="893bf-179">Site 2 (Hyderabad)</span></span> |

<span data-ttu-id="893bf-180">Для нескольких подсетей CSV-файл можно импортировать с помощью следующего сценария:</span><span class="sxs-lookup"><span data-stu-id="893bf-180">For multiple subnets, you can import a CSV file by using a script such as the following.</span></span>

```PowerShell
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.Identity -MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```

<span data-ttu-id="893bf-181">В этом примере CSV-файл выглядит так:</span><span class="sxs-lookup"><span data-stu-id="893bf-181">In this example, the CSV file looks something like this:</span></span> 

```console
Identity, Mask, SiteID
172.11.12.0, 24, Redmond
172.11.13.0, 24, Chicago
172.11.14.0, 25, Vancouver
172.11.15.0, 28, Paris
```

<span data-ttu-id="893bf-182">См. [также Set-CsTenantNetworkSubnet.](hhttps://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksubnet)</span><span class="sxs-lookup"><span data-stu-id="893bf-182">See also [Set-CsTenantNetworkSubnet](hhttps://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksubnet).</span></span>

### <a name="define-external-subnets-external-trusted-ip-addresses"></a><span data-ttu-id="893bf-183">Определение внешних подсетей (внешних доверенных IP-адресов)</span><span class="sxs-lookup"><span data-stu-id="893bf-183">Define external subnets (external trusted IP addresses)</span></span>

<span data-ttu-id="893bf-184">Чтобы определить внешние подсети и назначить их для клиента, используйте для этого [cmdlet New-CsTenantTrustedIPAddress.](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="893bf-184">Use the [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet to define external subnets and assign them to the tenant.</span></span> <span data-ttu-id="893bf-185">Для клиента можно определить неограниченное количество внешних подсетей.</span><span class="sxs-lookup"><span data-stu-id="893bf-185">You can define an unlimited number of external subnets for a tenant.</span></span>

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

<span data-ttu-id="893bf-186">Например:</span><span class="sxs-lookup"><span data-stu-id="893bf-186">For example:</span></span>

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

<span data-ttu-id="893bf-187">См. [также Set-CsTenantTrustedIPAddress.](https://docs.microsoft.com/powershell/module/skype/set-cstenanttrustedipaddress)</span><span class="sxs-lookup"><span data-stu-id="893bf-187">See also [Set-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/set-cstenanttrustedipaddress).</span></span>

## <a name="related-topics"></a><span data-ttu-id="893bf-188">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="893bf-188">Related topics</span></span>

- [<span data-ttu-id="893bf-189">Параметры сети для функций облачного голосового связи в Teams</span><span class="sxs-lookup"><span data-stu-id="893bf-189">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
