---
title: Развертывание областей сети, сайты и подсети в Скайп для бизнеса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
description: 'Создание или изменение областей сети, сетевых узлов и сопоставление подсетей в Скайп для Business Server. Все эти группы используются для расширенных функций корпоративной голосовой связи: обход мультимедиа, контроль допуска звонков и маршрутизация на основе местоположения.'
ms.openlocfilehash: b5de9ed76dcba917a186a6f9060021f51d5abac9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892666"
---
# <a name="deploy-network-regions-sites-and-subnets-in-skype-for-business"></a><span data-ttu-id="1287b-104">Развертывание областей сети, сайты и подсети в Скайп для бизнеса</span><span class="sxs-lookup"><span data-stu-id="1287b-104">Deploy network regions, sites and subnets in Skype for Business</span></span>

<span data-ttu-id="1287b-105">Создание или изменение областей сети, сетевых узлов и сопоставление подсетей в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="1287b-105">Create or modify network regions, network sites, and associate network subnets in Skype for Business Server.</span></span> <span data-ttu-id="1287b-106">Все эти группы используются для расширенных функций корпоративной голосовой связи: обход мультимедиа, контроль допуска звонков и маршрутизация на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="1287b-106">All these are used for the advanced Enterprise Voice features: media bypass, call admission control, and location-based routing.</span></span>

<span data-ttu-id="1287b-107">В расширенные функции корпоративной голосовой связи входят: [call admission control](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md), [media bypass](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md), [ location-based routing](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md) и [E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md).</span><span class="sxs-lookup"><span data-stu-id="1287b-107">The advanced Enterprise Voice features are [call admission control](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md), [media bypass](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md), [ location-based routing](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md), and [E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md).</span></span> <span data-ttu-id="1287b-108">Данные функции требуются для создания сетевых областей, сетевых сайтов и подсетей.</span><span class="sxs-lookup"><span data-stu-id="1287b-108">These features all require you to create network regions, network sites, and subnets.</span></span> <span data-ttu-id="1287b-109">Например, для всех этих функций требуется, чтобы каждая подсеть в топологии была связана с определенным сетевым сайтом, а каждый сетевой сайт должен быть связан с сетевой областью.</span><span class="sxs-lookup"><span data-stu-id="1287b-109">For example, all of these features require that each subnet in your topology be associated with a specific network site, and each network site must be associated with a network region.</span></span> <span data-ttu-id="1287b-110">Дополнительные сведения об условиях см. в разделе [Network settings for the advanced Enterprise Voice features in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="1287b-110">For more information on these terms, see [Network settings for the advanced Enterprise Voice features in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md)</span></span>

<span data-ttu-id="1287b-111">На контроль допуска звонков и E9-1-1 распространяются дополнительные требования относительно конфигурации для сетевых сайтов:</span><span class="sxs-lookup"><span data-stu-id="1287b-111">Call admission control and E9-1-1 have additional configuration requirements for network sites:</span></span>

- <span data-ttu-id="1287b-112">Для использования функции контроля допуска звонков необходимо указать профиль политики пропускной способности для каждого сайта, на который распространяются ограничения полосы пропускания WAN.</span><span class="sxs-lookup"><span data-stu-id="1287b-112">Call admission control requires that a bandwidth policy profile be specified for each site that is constrained by WAN bandwidth limitations.</span></span> <span data-ttu-id="1287b-113">Если вы планируете развернуть контроля допуска звонков, прежде чем настраивать сетевые узлы необходимо [Создание профилей политики пропускной способности в Скайп для Business Server](create-bandwidth-policy-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="1287b-113">If you plan to deploy call admission control, you must [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md) before you configure your network sites.</span></span>

- <span data-ttu-id="1287b-114">Для использования E9-1-1 необходимо указать политику расположения для каждого сайта.</span><span class="sxs-lookup"><span data-stu-id="1287b-114">E9-1-1 requires that a location policy be specified for each site.</span></span> <span data-ttu-id="1287b-115">Если вы планируете развернуть E9-1-1, прежде чем настраивать сетевые узлы необходимо [Создание политик расположения в Скайп для Business Server](create-location-policies.md) .</span><span class="sxs-lookup"><span data-stu-id="1287b-115">If you plan to deploy E9-1-1, you must [Create location policies in Skype for Business Server](create-location-policies.md) before you configure your network sites.</span></span>

## <a name="create-or-modify-a-network-region"></a><span data-ttu-id="1287b-116">Создание или изменение сетевой области</span><span class="sxs-lookup"><span data-stu-id="1287b-116">Create or modify a Network Region</span></span>

<span data-ttu-id="1287b-117">Если вы уже создали областей сети для одного из этих функций, не требуется создавать новые области сети; другие расширенные функции корпоративной голосовой связи будет использовать те же области сети.</span><span class="sxs-lookup"><span data-stu-id="1287b-117">If you have already created network regions for one of these features, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span>

<span data-ttu-id="1287b-p106">Однако вам может потребоваться изменить существующее определение области сети для применения параметров, относящихся к функции. Например, если вы создали области сети для службы E9-1-1, для которой не требуется связанный центральный сайт, и затем развернули службу контроля допуска звонков, вам потребуется изменить определения областей сети, чтобы указать центральный сайт.</span><span class="sxs-lookup"><span data-stu-id="1287b-p106">You may, however, need to modify an existing network region definition to apply feature-specific settings. For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span>

### <a name="to-create-a-network-region-using-skype-for-business-server-management-shell"></a><span data-ttu-id="1287b-120">Создание области сети, с помощью Скайп для консоли Business Server</span><span class="sxs-lookup"><span data-stu-id="1287b-120">To create a network region using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="1287b-121">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="1287b-121">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="1287b-122">Чтобы создать области сети, используйте командлет New-CsNetworkRegion.</span><span class="sxs-lookup"><span data-stu-id="1287b-122">Run the New-CsNetworkRegion cmdlet to create network regions:</span></span>

   ```
   New-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    <span data-ttu-id="1287b-123">Например:</span><span class="sxs-lookup"><span data-stu-id="1287b-123">For example:</span></span>

   ```
   New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
   ```

    <span data-ttu-id="1287b-124">В этом примере вы создали области сети, называется «NorthAmerica», которая связана с центральным сайтом с ИД CHICAGO.</span><span class="sxs-lookup"><span data-stu-id="1287b-124">In this example, you created a network region called "NorthAmerica" that is associated with a central site with site ID CHICAGO.</span></span>

3. <span data-ttu-id="1287b-125">Чтобы завершить создание областей сети для вашей топологии, повторите шаг 2, указав требуемые параметры для каждой области сети.</span><span class="sxs-lookup"><span data-stu-id="1287b-125">To finish creating network regions for your topology, repeat step 2 with settings for each network region.</span></span>

### <a name="to-create-a-network-region-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1287b-126">Создание области сети, с помощью Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="1287b-126">To create a network region using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="1287b-127">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="1287b-127">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="1287b-128">В левой области навигации щелкните элемент **Конфигурация сети**.</span><span class="sxs-lookup"><span data-stu-id="1287b-128">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="1287b-129">Щелкните **Область**.</span><span class="sxs-lookup"><span data-stu-id="1287b-129">Click **Region**.</span></span>

4. <span data-ttu-id="1287b-130">Выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="1287b-130">Click **New**.</span></span>

5. <span data-ttu-id="1287b-131">На странице **Создание области** введите имя области сети в поле **Имя**.</span><span class="sxs-lookup"><span data-stu-id="1287b-131">On the **New Region** page, click **Name** and then type a name for the network region.</span></span>

6. <span data-ttu-id="1287b-132">Щелкните **Центральный сайт**, затем выберите центральный сайт в списке.</span><span class="sxs-lookup"><span data-stu-id="1287b-132">Click **Central site**, and then click a central site in the list.</span></span>

7. <span data-ttu-id="1287b-133">В поле **Описание** введите дополнительные сведения об области сети (необязательно).</span><span class="sxs-lookup"><span data-stu-id="1287b-133">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

8. <span data-ttu-id="1287b-134">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="1287b-134">Click **Commit**.</span></span>

9. <span data-ttu-id="1287b-135">Чтобы завершить создание областей сети для вашей топологии, повторите шаги с 4 по 8, указав требуемые параметры для остальных областей.</span><span class="sxs-lookup"><span data-stu-id="1287b-135">To finish creating network regions for your topology, repeat steps 4 through 8 with settings for other regions.</span></span>

### <a name="to-modify-a-network-region-using-skype-for-business-server-management-shell"></a><span data-ttu-id="1287b-136">Изменение области сети с помощью Скайп для консоли Business Server</span><span class="sxs-lookup"><span data-stu-id="1287b-136">To modify a network region using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="1287b-137">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="1287b-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="1287b-138">Чтобы изменить существующую область сети, выполните командлет Set-CsNetworkRegion.</span><span class="sxs-lookup"><span data-stu-id="1287b-138">Run the Set-CsNetworkRegion cmdlet to modify an existing network region:</span></span>

   ```
   Set-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    <span data-ttu-id="1287b-139">Например:</span><span class="sxs-lookup"><span data-stu-id="1287b-139">For example:</span></span>

   ```
   Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
   ```

    <span data-ttu-id="1287b-140">В этом примере изменить существующую область сети называется «NorthAmerica» (созданный с помощью процедур, описанных ранее в этом разделе), изменив описание.</span><span class="sxs-lookup"><span data-stu-id="1287b-140">In this example, you modified an existing network region called "NorthAmerica" (created using the procedures earlier in this topic) by changing the description.</span></span> <span data-ttu-id="1287b-141">Описание существовало для региона «NorthAmerica», эта команда переопределяет это значение; Если описание не ранее было задано, эта команда задает его.</span><span class="sxs-lookup"><span data-stu-id="1287b-141">If a description existed for the "NorthAmerica" region, this command overwrites it with this value; if no description had been set, then this command sets it.</span></span>

3. <span data-ttu-id="1287b-142">Чтобы изменить остальные области сети, повторите шаг 2, указав параметры для остальных областей.</span><span class="sxs-lookup"><span data-stu-id="1287b-142">To modify other network regions, repeat step 2 with settings for other regions.</span></span>

### <a name="to-modify-a-network-region-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1287b-143">Изменение области сети с помощью Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="1287b-143">To modify a network region using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="1287b-144">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="1287b-144">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="1287b-145">В левой области навигации щелкните элемент **Конфигурация сети**.</span><span class="sxs-lookup"><span data-stu-id="1287b-145">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="1287b-146">Нажмите кнопку навигации **Область**.</span><span class="sxs-lookup"><span data-stu-id="1287b-146">Click the **Region** navigation button.</span></span>

4. <span data-ttu-id="1287b-147">В таблице щелкните область сети, которую требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="1287b-147">In the table, click the network region that you want to modify.</span></span>

5. <span data-ttu-id="1287b-148">Щелкните **Изменить**, затем щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="1287b-148">Click **Edit**, and then click **Show details…**.</span></span>

6. <span data-ttu-id="1287b-149">На странице " **Изменить область** " измените значения для параметров этой области сети соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="1287b-149">On the **Edit Region** page, change the values for this network region's settings as appropriate.</span></span>

7. <span data-ttu-id="1287b-150">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="1287b-150">Click **Commit**.</span></span>

8. <span data-ttu-id="1287b-151">Чтобы завершить изменение областей сети, повторите шаги 4–7, используя параметры для других областей.</span><span class="sxs-lookup"><span data-stu-id="1287b-151">To finish modify network regions, repeat steps 4 through 7 with settings for other regions.</span></span>

## <a name="create-or-modify-a-network-site"></a><span data-ttu-id="1287b-152">Создание или изменение сетевого сайта</span><span class="sxs-lookup"><span data-stu-id="1287b-152">Create or modify a network site</span></span>

<span data-ttu-id="1287b-153">Если вы уже создали сетевых узлов для одного из этих функций, не требуется создавать новые сайты сети; другие расширенные функции корпоративной голосовой связи будет использовать те же сетевые узлы.</span><span class="sxs-lookup"><span data-stu-id="1287b-153">If you have already created network sites for one of these features, you do not need to create new network sites; other advanced Enterprise Voice features will use those same network sites.</span></span> <span data-ttu-id="1287b-154">You may, however, need to modify an existing network site definition to apply feature-specific settings.</span><span class="sxs-lookup"><span data-stu-id="1287b-154">You may, however, need to modify an existing network site definition to apply feature-specific settings.</span></span> <span data-ttu-id="1287b-155">For example, if you created a network site for E9-1-1, you need to modify the network site during deployment of call admission control to apply a bandwidth policy profile.</span><span class="sxs-lookup"><span data-stu-id="1287b-155">For example, if you created a network site for E9-1-1, you need to modify the network site during deployment of call admission control to apply a bandwidth policy profile.</span></span>

### <a name="to-create-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="1287b-156">Создание области сети с помощью Скайп для консоли Business Server</span><span class="sxs-lookup"><span data-stu-id="1287b-156">To create a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="1287b-157">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="1287b-157">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="1287b-158">Выполните командлет New-CsNetworkSite для создания областей сети:</span><span class="sxs-lookup"><span data-stu-id="1287b-158">Run the New-CsNetworkSite cmdlet to create network sites:</span></span>

   ```
   New-CsNetworkSite -NetworkSiteID <string>
   ```

    <span data-ttu-id="1287b-159">Например:</span><span class="sxs-lookup"><span data-stu-id="1287b-159">For example:</span></span>

   ```
   New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
   ```

    <span data-ttu-id="1287b-160">В этом примере вы создали сетевой узел с именем «Chicago», который находится в сети «northamerica».</span><span class="sxs-lookup"><span data-stu-id="1287b-160">In this example, you created a network site called "Chicago" that is in the "NorthAmerica" network region.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1287b-161">Чтобы эта команда выполнилась успешно, область сети NorthAmerica должна уже быть создана.</span><span class="sxs-lookup"><span data-stu-id="1287b-161">The NorthAmerica network region must already exist for this command to run successfully.</span></span>

3. <span data-ttu-id="1287b-162">Чтобы закончить создание сетевых узлов для вашей топологии, повторите действие 2 с параметрами других узлов.</span><span class="sxs-lookup"><span data-stu-id="1287b-162">To finish creating network sites for your topology, repeat step 2 with settings for other sites.</span></span>

### <a name="to-create-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1287b-163">Создание области сети с помощью Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="1287b-163">To create a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="1287b-164">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="1287b-164">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="1287b-165">В левой области навигации щелкните элемент **Конфигурация сети**.</span><span class="sxs-lookup"><span data-stu-id="1287b-165">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="1287b-166">Нажмите кнопку навигации **Сайт**.</span><span class="sxs-lookup"><span data-stu-id="1287b-166">Click the **Site** navigation button.</span></span>

4. <span data-ttu-id="1287b-167">Выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="1287b-167">Click **New**.</span></span>

5. <span data-ttu-id="1287b-168">На странице **Создать сайт** выберите поле **Имя** и введите имя для сетевого сайта.</span><span class="sxs-lookup"><span data-stu-id="1287b-168">On the **New Site** page, click **Name** and then type a name for the network site.</span></span>

6. <span data-ttu-id="1287b-169">Нажмите пункт **Область** и выберите в списке нужную область.</span><span class="sxs-lookup"><span data-stu-id="1287b-169">Click **Region**, and then click a region in the list.</span></span>

7. <span data-ttu-id="1287b-170">Дополнительно можно выбрать пункт **Политика пропускной способности** и выбрать нужную политику в списке.</span><span class="sxs-lookup"><span data-stu-id="1287b-170">Optionally, click **Bandwidth policy**, and then click a bandwidth policy in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1287b-171">Политика пропускной способности требуется только в том случае, если в узле разворачивается контроль допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="1287b-171">Bandwidth policy is required only if you deploy call admission control at the site.</span></span>

8. <span data-ttu-id="1287b-172">Дополнительно можно выбрать пункт **Политика местонахождения** и выбрать нужную политику местонахождения в списке.</span><span class="sxs-lookup"><span data-stu-id="1287b-172">Optionally, click **Location policy**, and then click a location policy in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1287b-173">Политика местонахождения требуется только в том случае, если в узле разворачивается служба E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="1287b-173">Location policy is required only if you deploy E9-1-1 at the site.</span></span>

9. <span data-ttu-id="1287b-174">В поле **Описание** введите дополнительные сведения об области сети (необязательно).</span><span class="sxs-lookup"><span data-stu-id="1287b-174">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

10. <span data-ttu-id="1287b-175">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="1287b-175">Click **Commit**.</span></span>

11. <span data-ttu-id="1287b-176">Чтобы завершить создание сетевых узлов для вашей топологии, повторите действия с 4 по 10 с параметрами для других узлов.</span><span class="sxs-lookup"><span data-stu-id="1287b-176">To finish creating network sites for your topology, repeat steps 4 through 10 with settings for other sites.</span></span>

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="1287b-177">Изменение области сети с помощью Скайп для консоли Business Server</span><span class="sxs-lookup"><span data-stu-id="1287b-177">To modify a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="1287b-178">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="1287b-178">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="1287b-179">Чтобы изменить сетевые узлы, выполните командлет Set-CsNetworkSite:</span><span class="sxs-lookup"><span data-stu-id="1287b-179">Run the Set-CsNetworkSite cmdlet to modify network sites:</span></span>

   ```
   Set-CsNetworkSite -Identity <string>
   ```

    <span data-ttu-id="1287b-180">Например:</span><span class="sxs-lookup"><span data-stu-id="1287b-180">For example:</span></span>

   ```
   Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
   ```

    <span data-ttu-id="1287b-181">В этом примере узел с именем «Альбукерке» будет перемещено в область сети «NorthAmerica».</span><span class="sxs-lookup"><span data-stu-id="1287b-181">In this example, the site called "Albuquerque" is moved to the "NorthAmerica" network region.</span></span> <span data-ttu-id="1287b-182">Чтобы изменить конфигурацию этого сетевого узла для развертывания контроля допуска звонков, E9-1-1 или обхода сервера-посредника, измените параметры сетевого узла, выполнив командлет Set-CsNetworkSite с параметром BWPolicyProfileID или LocationPolicy соответственно.</span><span class="sxs-lookup"><span data-stu-id="1287b-182">To modify the network site configuration to deploy call admission control, E9-1-1, or media bypass, modify the network site settings by running the Set-CsNetworkSite cmdlet with the BWPolicyProfileID or LocationPolicy parameter, respectively.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1287b-p110">Хотя для обхода сервера-посредника существует параметр BypassID, настоятельно рекомендуется не переопределять автоматически созданные идентификаторы обхода. Чтобы настроить сетевой узел для обхода сервера-посредника, указывать дополнительные параметры не требуется.</span><span class="sxs-lookup"><span data-stu-id="1287b-p110">Although the BypassID parameter exists for media bypass, we strongly recommend that you do not override automatically generated bypass IDs. You do not need to specify additional parameters to configure a network site for media bypass.</span></span>

3. <span data-ttu-id="1287b-185">Чтобы закончить изменение сетевых узлов для вашей топологии, повторите действие 2 с параметрами других узлов.</span><span class="sxs-lookup"><span data-stu-id="1287b-185">To finish modifying network sites for your topology, repeat step 2 with settings for other sites.</span></span>

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1287b-186">Изменение области сети с помощью Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="1287b-186">To modify a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="1287b-187">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="1287b-187">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="1287b-188">В левой области навигации щелкните элемент **Конфигурация сети**.</span><span class="sxs-lookup"><span data-stu-id="1287b-188">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="1287b-189">Нажмите кнопку навигации **Сайт**.</span><span class="sxs-lookup"><span data-stu-id="1287b-189">Click the **Site** navigation button.</span></span>

4. <span data-ttu-id="1287b-190">Выберите в таблице сетевой узел, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="1287b-190">In the table, click the network site that you want to modify.</span></span>

5. <span data-ttu-id="1287b-191">Щелкните **Изменить**, затем щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="1287b-191">Click **Edit**, and then click **Show details…**.</span></span>

6. <span data-ttu-id="1287b-192">На странице " **Изменение сайта** " измените значения для параметров этого сетевого узла соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="1287b-192">On the **Edit Site** page, change the values for this network site's settings as appropriate.</span></span>

7. <span data-ttu-id="1287b-193">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="1287b-193">Click **Commit**.</span></span>

8. <span data-ttu-id="1287b-194">Чтобы завершить изменение сетевых узлов, повторите действия с 4 по 7 с параметрами для других узлов.</span><span class="sxs-lookup"><span data-stu-id="1287b-194">To finish modify network sites, repeat steps 4 through 7 with settings for other sites.</span></span>

## <a name="associate-a-subnet-with-a-network-site"></a><span data-ttu-id="1287b-195">Связь подсети с сетевым сайтом</span><span class="sxs-lookup"><span data-stu-id="1287b-195">Associate a subnet with a network site</span></span>
<span data-ttu-id="1287b-196"><a name="BKMK_AssociateSubnets"> </a></span><span class="sxs-lookup"><span data-stu-id="1287b-196"></span></span>

<span data-ttu-id="1287b-197">Every subnet in your network must be associated with a specific network site, because subnet information is used to determine the network site on which an endpoint is located while a new session is initiated.</span><span class="sxs-lookup"><span data-stu-id="1287b-197">Every subnet in your network must be associated with a specific network site, because subnet information is used to determine the network site on which an endpoint is located while a new session is initiated.</span></span> <span data-ttu-id="1287b-198">Когда известно местоположение каждой стороны в сеансе advanced Enterprise Voice функции можно применять эти сведения для определения способа обработки установки вызова или маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="1287b-198">When the location of each party in a session is known, advanced Enterprise Voice features can apply that information to determine how to handle the call setup or routing.</span></span>

<span data-ttu-id="1287b-199">All configured public IP addresses of the Audio/Video Edge Servers in your deployment must be added to your network configuration settings.</span><span class="sxs-lookup"><span data-stu-id="1287b-199">All configured public IP addresses of the Audio/Video Edge Servers in your deployment must be added to your network configuration settings.</span></span> <span data-ttu-id="1287b-200">These IP addresses are added as subnets with a mask of 32.</span><span class="sxs-lookup"><span data-stu-id="1287b-200">These IP addresses are added as subnets with a mask of 32.</span></span> <span data-ttu-id="1287b-201">The associated network site should correspond to the appropriate configured network site.</span><span class="sxs-lookup"><span data-stu-id="1287b-201">The associated network site should correspond to the appropriate configured network site.</span></span> <span data-ttu-id="1287b-202">Например, общедоступный IP-адрес, соответствующий A аудио- и видеоконференций в центральном узле Чикаго может быть Чикаго NetworkSiteID.</span><span class="sxs-lookup"><span data-stu-id="1287b-202">For example, the public IP address that corresponds to the A/V Edge service in central site Chicago would be NetworkSiteID Chicago.</span></span>

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="1287b-203">Чтобы связать подсеть с сетевым узлом с помощью Скайп для консоли Business Server</span><span class="sxs-lookup"><span data-stu-id="1287b-203">To associate a subnet with a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="1287b-204">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="1287b-204">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="1287b-205">Чтобы связать подсеть с сетевым сайтом, используйте командлет **New-CsNetworkSubnet**:</span><span class="sxs-lookup"><span data-stu-id="1287b-205">Run the **New-CsNetworkSubnet** cmdlet to associate a subnet with a network site:</span></span>

   ```
   New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
   ```

    <span data-ttu-id="1287b-206">Например:</span><span class="sxs-lookup"><span data-stu-id="1287b-206">For example:</span></span>

   ```
   New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
   ```

    <span data-ttu-id="1287b-207">В этом примере создается связь между подсетью 172.11.12.13 и сетевым узлом «Chicago».</span><span class="sxs-lookup"><span data-stu-id="1287b-207">In this example, you created an association between the subnet 172.11.12.13 and the network site "Chicago".</span></span>

3. <span data-ttu-id="1287b-208">Повторите шаг 2 для всех подсетей топологии.</span><span class="sxs-lookup"><span data-stu-id="1287b-208">Repeat step 2 for all subnets in your topology.</span></span>

### <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a><span data-ttu-id="1287b-209">Связывание подсетей с сетевыми узлами путем импорта CSV-файла</span><span class="sxs-lookup"><span data-stu-id="1287b-209">To associate subnets with network sites by importing a CSV file</span></span>

1. <span data-ttu-id="1287b-p113">Создайте CSV-файл, содержащий все добавляемые подсети. Например, создайте файл с именем **subnet.csv**, содержащий следующие данные:</span><span class="sxs-lookup"><span data-stu-id="1287b-p113">Create a CSV file that includes all of the subnets you want to add. For example, create a file named **subnet.csv** with the following content:</span></span>

     `IPAddress, mask, description, NetworkSiteID`

     `172.11.12.0, 24, "NA:Subnet in Portland", Portland`

     `172.11.13.0, 24, "NA:Subnet in Reno", Reno`

     `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`

     `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2. <span data-ttu-id="1287b-212">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="1287b-212">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="1287b-213">Выполните следующий командлет, чтобы импортировать **файл subnet.csv**, а затем сохраните его содержимое в хранилище управления Lync Server:</span><span class="sxs-lookup"><span data-stu-id="1287b-213">Run the following cmdlet to import **subnet.csv**, and then store its contents in the Lync Server management store:</span></span>

   ```
   import-csv subnet.csv | foreach {New-CsNetworkSubnet -Identity $_.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}
   ```

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1287b-214">Чтобы связать подсеть с сетевым узлом с помощью Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="1287b-214">To associate a subnet with a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="1287b-215">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="1287b-215">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="1287b-216">В левой области навигации щелкните элемент **Конфигурация сети**.</span><span class="sxs-lookup"><span data-stu-id="1287b-216">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="1287b-217">Нажмите кнопку навигации **Подсеть**.</span><span class="sxs-lookup"><span data-stu-id="1287b-217">Click the **Subnet** navigation button.</span></span>

4. <span data-ttu-id="1287b-218">Выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="1287b-218">Click **New**.</span></span>

5. <span data-ttu-id="1287b-219">На странице **Создание подсети** щелкните **ИД подсети**, затем введите первый адрес диапазона IP-адресов подсети, которую требуется связать с сетевым узлом.</span><span class="sxs-lookup"><span data-stu-id="1287b-219">On the **New Subnet** page, click **Subnet ID**, and then type the first address in the IP address range defined by the subnet you want to associate with a network site.</span></span>

6. <span data-ttu-id="1287b-220">Щелкните **Маска**, затем введите битовую маску, применяемую к подсети.</span><span class="sxs-lookup"><span data-stu-id="1287b-220">Click **Mask**, and then type the bitmask to apply to the subnet.</span></span>

7. <span data-ttu-id="1287b-221">Щелкните **ИД сетевого узла**, затем выберите ИД узла, в который необходимо добавить эту подсеть.</span><span class="sxs-lookup"><span data-stu-id="1287b-221">Click **Network site ID**, and then select the site ID of the site to which you are adding this subnet.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1287b-222">Если вы еще не создали сетевые сайты, то этот список будет пустым.</span><span class="sxs-lookup"><span data-stu-id="1287b-222">If you have not yet created network sites, this list will be empty.</span></span> <span data-ttu-id="1287b-223">Дополнительные сведения см. в разделе [Create or Modify a Network Site](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx).</span><span class="sxs-lookup"><span data-stu-id="1287b-223">For details about the procedure, see [Create or Modify a Network Site](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx).</span></span> <span data-ttu-id="1287b-224">Также для получения ИД сетевых сайтов можно использовать командлет **Get-CsNetworkSite**.</span><span class="sxs-lookup"><span data-stu-id="1287b-224">You can also retrieve site IDs for your deployment by running the **Get-CsNetworkSite** cmdlet.</span></span> <span data-ttu-id="1287b-225">Дополнительные сведения см Скайп для документации по консоли управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="1287b-225">For details, see the Skype for Business Server Management Shell documentation.</span></span>

8. <span data-ttu-id="1287b-226">В поле **Описание** введите дополнительные сведения об этой подсети.</span><span class="sxs-lookup"><span data-stu-id="1287b-226">Optionally, click **Description**, and then type additional information to describe this subnet.</span></span>

9. <span data-ttu-id="1287b-227">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="1287b-227">Click **Commit**.</span></span>

<span data-ttu-id="1287b-228">Повторите эти действия, чтобы добавить остальные подсети в сетевой узел.</span><span class="sxs-lookup"><span data-stu-id="1287b-228">Repeat these steps to add other subnets to a network site.</span></span>
> [!NOTE]
> <span data-ttu-id="1287b-229">Для указания списка IP-адресов, которые не связаны ни с одной подсетью, или подсети, которая не связана ни с одним сетевым сайтом, вызывается оповещение Key Health Indicator (основной индикатор работоспособности).</span><span class="sxs-lookup"><span data-stu-id="1287b-229">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site.</span></span> <span data-ttu-id="1287b-230">Минимальный интервал вызова оповещения составляет 8 часов.</span><span class="sxs-lookup"><span data-stu-id="1287b-230">This alert will not be raised more than once within an 8-hour period.</span></span>

<span data-ttu-id="1287b-231">Ниже приведены сведения об оповещении и пример:</span><span class="sxs-lookup"><span data-stu-id="1287b-231">The relevant alert information and an example are as follows:</span></span>

 <span data-ttu-id="1287b-232">**Источник**: служба политики пропускной способности CS (ядро)</span><span class="sxs-lookup"><span data-stu-id="1287b-232">**Source**: CS Bandwidth Policy Service (Core)</span></span>

 <span data-ttu-id="1287b-233">**Номер события**: 36034</span><span class="sxs-lookup"><span data-stu-id="1287b-233">**Event number**: 36034</span></span>

 <span data-ttu-id="1287b-234">**Уровень**: 2</span><span class="sxs-lookup"><span data-stu-id="1287b-234">**Level**: 2</span></span>

 <span data-ttu-id="1287b-235">**Описание**: подсети для следующих IP-адресов: \<список IP-адресов\> не настроены или подсети не связаны с сетевым узлом.</span><span class="sxs-lookup"><span data-stu-id="1287b-235">**Description**: The subnets for the following IP addresses: \<List of IP Addresses\> are either not configured or the subnets are not associated to a Network Site.</span></span>

 <span data-ttu-id="1287b-236">**Причина**: подсети для соответствующих IP-адресов не указаны в параметрах конфигурации сети или не связаны с сетевым сайтом.</span><span class="sxs-lookup"><span data-stu-id="1287b-236">**Cause**: The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span>

 <span data-ttu-id="1287b-237">**Решение**: добавьте в конфигурацию сети подсети, соответствующие списку IP-адресов, и свяжите каждую подсеть с сетевым сайтом.</span><span class="sxs-lookup"><span data-stu-id="1287b-237">**Resolution**: Add subnets corresponding to the list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span>

<span data-ttu-id="1287b-p116">Например, если в оповещении указаны IP-адреса 10.121.248.226 и 10.121.249.20, либо эти IP-адреса не связаны с подсетью, либо подсеть, с которой связаны эти адреса, не принадлежит сетевому узлу. Если этим адресам соответствуют подсети 10.121.248.0/24 и 10.121.249.0/24, то для решения этой проблемы выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="1287b-p116">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet or the subnet they are associated with does not belong to a network site. If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span>

1. <span data-ttu-id="1287b-240">Убедитесь в том, что IP-адрес 10.121.248.226 связан с подсетью 10.121.248.0/24, а IP-адрес 10.121.249.20 — с подсетью 10.121.249.0/24.</span><span class="sxs-lookup"><span data-stu-id="1287b-240">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span>

2. <span data-ttu-id="1287b-241">Убедитесь, в том что обе подсети 10.121.248.0/24 и 10.121.249.0/24 связаны с сетевым сайтом.</span><span class="sxs-lookup"><span data-stu-id="1287b-241">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span>

## <a name="see-also"></a><span data-ttu-id="1287b-242">См. также</span><span class="sxs-lookup"><span data-stu-id="1287b-242">See also</span></span>
<span data-ttu-id="1287b-243"><a name="BKMK_AssociateSubnets"> </a></span><span class="sxs-lookup"><span data-stu-id="1287b-243"></span></span>


[<span data-ttu-id="1287b-244">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="1287b-244">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregion?view=skype-ps)

[<span data-ttu-id="1287b-245">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="1287b-245">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregion?view=skype-ps)

[<span data-ttu-id="1287b-246">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="1287b-246">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregion?view=skype-ps)

[<span data-ttu-id="1287b-247">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="1287b-247">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregion?view=skype-ps)

[<span data-ttu-id="1287b-248">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="1287b-248">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworksubnet?view=skype-ps)

[<span data-ttu-id="1287b-249">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="1287b-249">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworksubnet?view=skype-ps)

[<span data-ttu-id="1287b-250">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="1287b-250">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworksubnet?view=skype-ps)

[<span data-ttu-id="1287b-251">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="1287b-251">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworksubnet?view=skype-ps)

