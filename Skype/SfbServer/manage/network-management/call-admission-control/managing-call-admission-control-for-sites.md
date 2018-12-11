---
title: Управление контролем допуска звонков для сайтов
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Сетевые узлы не офисы или расположения в каждом регионе сети для контроля допуска звонков (CAC), E9-1-1 и развертываний обход мультимедиа.
ms.openlocfilehash: ecf23a8a052afbd21b02f8ff5507c248d42b7118
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223173"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a><span data-ttu-id="dabec-103">Управление контролем допуска звонков для сайтов в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="dabec-103">Managing call admission control for sites in Skype for Business Server</span></span>

<span data-ttu-id="dabec-104">Сетевые узлы не офисы или расположения в каждом регионе сети для контроля допуска звонков (CAC), E9-1-1 и развертываний обход мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="dabec-104">Network sites are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="dabec-105">Используйте процедуры, описанные в этой статье Настройка контроль допуска звонков для сетевых узлов.</span><span class="sxs-lookup"><span data-stu-id="dabec-105">Use the procedures in this article to configure call admission control for network sites.</span></span>

## <a name="configure-network-site-links"></a><span data-ttu-id="dabec-106">Настройка ссылок на сайты сети</span><span class="sxs-lookup"><span data-stu-id="dabec-106">Configure network site links</span></span>

<span data-ttu-id="dabec-107">В конфигурации контроля допуска допуска звонков можно создать сети между сайтами политик, которые определяют ограничения пропускной способности между сайтами, напрямую связанными.</span><span class="sxs-lookup"><span data-stu-id="dabec-107">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="dabec-108">Если сетевые узлы имеют прямая ссылка, может быть определен ограничения пропускной способности для подключения к аудио- и видеоконференций между этих двух сайтов.</span><span class="sxs-lookup"><span data-stu-id="dabec-108">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="dabec-109">Скайп для панели управления Business Server нельзя использовать для настройки сетевые политики сайта, это можно сделать только с помощью командлетов из Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="dabec-109">You cannot use the Skype for Business Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="dabec-110">Создавать, изменять и удалять связи между сетевыми узлами (также известной как сетевая межсайтовая политика) из Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="dabec-110">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Skype for Business Server Management Shell.</span></span>

### <a name="to-create-a-network-site-link"></a><span data-ttu-id="dabec-111">Создание связи между сетевыми узлами</span><span class="sxs-lookup"><span data-stu-id="dabec-111">To create a network site link</span></span>

1.  <span data-ttu-id="dabec-112">Войдите на компьютер, где установлена Скайп для консоли Business Server как член группы RTCUniversalServerAdmins или с необходимые права пользователя.</span><span class="sxs-lookup"><span data-stu-id="dabec-112">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="dabec-113">Запустите Скайп для консоли Business Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы**, щелкните **Скайп для Business Server**и нажмите кнопку **Скайп для консоли Business Server**.</span><span class="sxs-lookup"><span data-stu-id="dabec-113">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="dabec-114">В командной строке введите следующую команду, подставив значения, подходящие для вашей конфигурации:</span><span class="sxs-lookup"><span data-stu-id="dabec-114">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="dabec-115">В этом примере создается новый связи между сетевыми узлами с именем Reno\_Портленд, который задает ограничения пропускной способности между сетевыми узлами Reno и Портленд.</span><span class="sxs-lookup"><span data-stu-id="dabec-115">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="dabec-116">Сетевые узлы и профиль политики пропускной способности должны уже существовать перед выполнением этой команды.</span><span class="sxs-lookup"><span data-stu-id="dabec-116">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="dabec-117">Параметр подробные описания в разделе [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="dabec-117">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy).</span></span> <span data-ttu-id="dabec-118">Чтобы получить список профилей политики пропускной способности, которые могут быть применены к связи между сетевыми узлами, вызовите командлет **Get-CsNetworkBandwidthPolicyProfile** .</span><span class="sxs-lookup"><span data-stu-id="dabec-118">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="dabec-119">Дополнительные сведения см [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span><span class="sxs-lookup"><span data-stu-id="dabec-119">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span></span>

### <a name="to-modify-a-network-site-link"></a><span data-ttu-id="dabec-120">Изменение связи между сетевыми узлами</span><span class="sxs-lookup"><span data-stu-id="dabec-120">To modify a network site link</span></span>

1.  <span data-ttu-id="dabec-121">Войдите на компьютер, где установлена Скайп для консоли Business Server как член группы RTCUniversalServerAdmins или с необходимые права пользователя.</span><span class="sxs-lookup"><span data-stu-id="dabec-121">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="dabec-122">Запустите Скайп для консоли Business Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы**, щелкните **Скайп для Business Server**и нажмите кнопку **Скайп для консоли Business Server**.</span><span class="sxs-lookup"><span data-stu-id="dabec-122">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="dabec-123">Командлет **Set-CsNetworkInterSitePolicy** для изменения свойств связи между сетевыми данного сайта.</span><span class="sxs-lookup"><span data-stu-id="dabec-123">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="dabec-124">Можно изменить один (или оба) или связи сайтов и можно изменить профиль политики пропускной способности, связанные со ссылкой.</span><span class="sxs-lookup"><span data-stu-id="dabec-124">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="dabec-125">Ниже приведен пример изменения профиля политики пропускной способности связи сайтов с именем Reno\_Портленд:</span><span class="sxs-lookup"><span data-stu-id="dabec-125">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="dabec-126">Параметр подробные описания в разделе [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="dabec-126">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span></span>


### <a name="to-delete-a-network-site-link"></a><span data-ttu-id="dabec-127">Удаление связи между сетевыми узлами</span><span class="sxs-lookup"><span data-stu-id="dabec-127">To delete a network site link</span></span>

1.  <span data-ttu-id="dabec-128">Войдите на компьютер, где установлена Скайп для консоли Business Server как член группы RTCUniversalServerAdmins или с необходимые права пользователя.</span><span class="sxs-lookup"><span data-stu-id="dabec-128">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="dabec-129">Запустите Скайп для консоли Business Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы**, щелкните **Скайп для Business Server**и нажмите кнопку **Скайп для консоли Business Server**.</span><span class="sxs-lookup"><span data-stu-id="dabec-129">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="dabec-130">Командлет **Remove-CsNetworkInterSitePolicy** используется для удаления связи между сетевыми узлами.</span><span class="sxs-lookup"><span data-stu-id="dabec-130">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="dabec-131">В следующем примере удаляется Reno\_Портленд связи между сетевыми узлами:</span><span class="sxs-lookup"><span data-stu-id="dabec-131">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="dabec-132">Параметр подробные описания в разделе [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="dabec-132">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span></span>


## <a name="view-network-site-information"></a><span data-ttu-id="dabec-133">Просмотр сведений о сетевом сайте</span><span class="sxs-lookup"><span data-stu-id="dabec-133">View network site information</span></span>

<span data-ttu-id="dabec-134">Сетевые узлы являются офисы или филиалы, настроенных в каждом регионе контроля допуска звонков (CAC) или развертывания Enhanced 9-1-1.</span><span class="sxs-lookup"><span data-stu-id="dabec-134">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="dabec-135">Можно просмотреть сведений о сетевых сайтах в любом Скайп для панели управления Business Server или Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="dabec-135">You can view network site information in either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="dabec-136">Для просмотра сведений о сетевых сайтах в Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="dabec-136">To view network site information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="dabec-137">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="dabec-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="dabec-138">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="dabec-138">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="dabec-139">В левой панели навигации щелкните **Конфигурация сети**и нажмите кнопку **сайта**.</span><span class="sxs-lookup"><span data-stu-id="dabec-139">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="dabec-140">На странице **сайта** щелкните сайт, который нужно просмотреть.</span><span class="sxs-lookup"><span data-stu-id="dabec-140">On the **Site** page, click the site that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="dabec-141">Можно просматривать только сведения для одного сайта за раз.</span><span class="sxs-lookup"><span data-stu-id="dabec-141">You can only view information for one site at a time.</span></span>

5.  <span data-ttu-id="dabec-142">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="dabec-142">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="dabec-143">Просмотр сведений о сетевом сайте с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dabec-143">Viewing network site information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="dabec-144">Сведений о сетевом сайте можно просмотреть с помощью Windows PowerShell и командлет Get-CsNetworkSite.</span><span class="sxs-lookup"><span data-stu-id="dabec-144">You can view network site information by using Windows PowerShell and the Get-CsNetworkSite cmdlet.</span></span> <span data-ttu-id="dabec-145">Этот командлет можно запустить из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dabec-145">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-site-information"></a><span data-ttu-id="dabec-146">Для просмотра сведений о сетевом сайте</span><span class="sxs-lookup"><span data-stu-id="dabec-146">To view network site information</span></span>

  - <span data-ttu-id="dabec-147">Чтобы просмотреть сведения обо всех сетевых узлов, введите следующую команду в Скайп для консоли Business Server и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="dabec-147">To view information about all your network sites, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkSite
    
    <span data-ttu-id="dabec-148">Команда возвращает примерно следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="dabec-148">That will return information similar to this:</span></span>
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

<span data-ttu-id="dabec-149">Для получения дополнительных сведений см раздел справки для командлета [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) .</span><span class="sxs-lookup"><span data-stu-id="dabec-149">For more information, see the help topic for the [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet.</span></span>


## <a name="create-or-modify-network-sites"></a><span data-ttu-id="dabec-150">Создание или изменение сетевых узлов</span><span class="sxs-lookup"><span data-stu-id="dabec-150">Create or modify network sites</span></span> 

<span data-ttu-id="dabec-151">Сетевые узлы являются офисы или филиалы, настроенных в каждом регионе контроля допуска звонков (CAC) или развертывания Enhanced 9-1-1.</span><span class="sxs-lookup"><span data-stu-id="dabec-151">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="dabec-152">Скайп для панели управления Business Server можно использовать для настройки сайтов и свяжите их с областями.</span><span class="sxs-lookup"><span data-stu-id="dabec-152">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="dabec-153">К примеру области сети в Северной Америке могут быть связаны с сайтами сетей, таких как Чикаго, Redmond и Vancouver.</span><span class="sxs-lookup"><span data-stu-id="dabec-153">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="dabec-154">С сетевым узлом контроля допуска звонков необходимо создать для каждого сайта в пределах организации, даже в том случае, если этот сайт имеет без ограничений пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="dabec-154">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="dabec-155">Из Скайп для панели управления Business Server можно создавать, изменять и удалять сетевых узлов.</span><span class="sxs-lookup"><span data-stu-id="dabec-155">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="dabec-156">Используйте следующие процедуры для создания или изменения с сетевым узлом.</span><span class="sxs-lookup"><span data-stu-id="dabec-156">Use the following procedures to create or modify a network site.</span></span> 

### <a name="to-create-a-network-site"></a><span data-ttu-id="dabec-157">Создание сетевого узла</span><span class="sxs-lookup"><span data-stu-id="dabec-157">To create a network site</span></span>

1.  <span data-ttu-id="dabec-158">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="dabec-158">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="dabec-159">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="dabec-159">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="dabec-160">В левой панели навигации щелкните **Конфигурация сети**и нажмите кнопку **сайта**.</span><span class="sxs-lookup"><span data-stu-id="dabec-160">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="dabec-161">На странице " **сайт** " нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="dabec-161">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="dabec-162">**Новый узел**введите имя для этого сайта в поле **имя** .</span><span class="sxs-lookup"><span data-stu-id="dabec-162">In **New Site**, type a name for this site in the **Name** field.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="dabec-163">Имена узлов должны быть уникальным в рамках Скайп для развертывания Business Server.</span><span class="sxs-lookup"><span data-stu-id="dabec-163">Site names must be unique within the Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="dabec-164">В раскрывающемся списке **область** выберите область сети для связи с этого сайта.</span><span class="sxs-lookup"><span data-stu-id="dabec-164">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="dabec-165">(Необязательно) Если вы хотите наложить ограничения полосы пропускания на аудио- или видеозвонка звонков на этот сайт, выберите профиль политики пропускной способности с соответствующими параметрами из раскрывающегося списка **Политика пропускной способности** .</span><span class="sxs-lookup"><span data-stu-id="dabec-165">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="dabec-166">Можно просмотреть сведения об профилей политики пропускной или создать новый профиль политики пропускной способности, на странице " **Профили политики** " группе **Конфигурация сети** .</span><span class="sxs-lookup"><span data-stu-id="dabec-166">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the **Policy Profil** page of the **Network Configuration** group.</span></span> <span data-ttu-id="dabec-167">Дополнительные сведения см [Управление профилей политики пропускной способности сети](managing-network-bandwidth-policy-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="dabec-167">For details, see [Managing network bandwidth policy profiles](managing-network-bandwidth-policy-profiles.md).</span></span>

8.  <span data-ttu-id="dabec-168">(Необязательно) Если вы хотите предоставить параметры местоположения для данного узла, выберите политику расположения в раскрывающемся списке **Политика расположения** .</span><span class="sxs-lookup"><span data-stu-id="dabec-168">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="dabec-169">Политика расположения назначает конкретных Enhanced 9-1-1 (E9-1-1) и клиентских параметры расположения сайта.</span><span class="sxs-lookup"><span data-stu-id="dabec-169">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="dabec-170">Можно просмотреть сведения об политик расположения недоступны или создать новую политику расположения, на странице **Политика расположения** группе **Конфигурация сети** .</span><span class="sxs-lookup"><span data-stu-id="dabec-170">You can view the details of the available location policies, or create a new location policy, from the **Location Policy** page of the **Network Configuration** group.</span></span> 

9.  <span data-ttu-id="dabec-171">(Необязательно) Введите значение в поле **Описание** введите дополнительные сведения об этом сайте, которые не могут быть выражены одним именем.</span><span class="sxs-lookup"><span data-stu-id="dabec-171">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="dabec-172">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="dabec-172">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="dabec-173">В таблице **Связанные подсети** не используется для создания нового сетевого узла.</span><span class="sxs-lookup"><span data-stu-id="dabec-173">You do not use the **Associated Subnets** table when you create a new network site.</span></span> <span data-ttu-id="dabec-174">Связывание подсети с сайтом при создании или изменении подсеть.</span><span class="sxs-lookup"><span data-stu-id="dabec-174">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="dabec-175">Дополнительные сведения см [Управление подсетей](managing-network-subnets.md).</span><span class="sxs-lookup"><span data-stu-id="dabec-175">For details, see [Managing network subnets](managing-network-subnets.md).</span></span>

### <a name="to-modify-a-network-site"></a><span data-ttu-id="dabec-176">Изменение сетевого узла</span><span class="sxs-lookup"><span data-stu-id="dabec-176">To modify a network site</span></span>

1.  <span data-ttu-id="dabec-177">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="dabec-177">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="dabec-178">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="dabec-178">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="dabec-179">В левой панели навигации щелкните **Конфигурация сети**и нажмите кнопку **сайта**.</span><span class="sxs-lookup"><span data-stu-id="dabec-179">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="dabec-180">На странице **сайта** щелкните сайт, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="dabec-180">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="dabec-181">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="dabec-181">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="dabec-182">На странице **Изменение узла** можно изменить описание, региона, профиль политики пропускной способности и политику расположения, связанного с сайтом.</span><span class="sxs-lookup"><span data-stu-id="dabec-182">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site.</span></span> <span data-ttu-id="dabec-183">Дополнительные сведения см [в Создание сетевого узла](#to-create-a-network-site) выше.</span><span class="sxs-lookup"><span data-stu-id="dabec-183">For details, see [To create a network site](#to-create-a-network-site) above.</span></span>

7.  <span data-ttu-id="dabec-184">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="dabec-184">Click **Commit**.</span></span>

<span data-ttu-id="dabec-185">В таблице **Связанные подсети** на этой странице изменить нельзя.</span><span class="sxs-lookup"><span data-stu-id="dabec-185">You cannot modify the **Associated Subnets** table on this page.</span></span> <span data-ttu-id="dabec-186">Список связанных подсетей предоставляется для ссылки, чтобы знать о том, какие подсети затрагиваются при изменении параметров сайта.</span><span class="sxs-lookup"><span data-stu-id="dabec-186">The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>


## <a name="delete-an-existing-network-site"></a><span data-ttu-id="dabec-187">Удаление существующего сетевого узла</span><span class="sxs-lookup"><span data-stu-id="dabec-187">Delete an existing network site</span></span>

<span data-ttu-id="dabec-188">Сетевые узлы являются офисы или филиалы, настроенных в каждом регионе контроля допуска звонков (CAC) или развертывания Enhanced 9-1-1.</span><span class="sxs-lookup"><span data-stu-id="dabec-188">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="dabec-189">Скайп для панели управления Business Server можно использовать для настройки сайтов и свяжите их с областями.</span><span class="sxs-lookup"><span data-stu-id="dabec-189">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="dabec-190">К примеру области сети в Северной Америке могут быть связаны с сайтами сетей, таких как Чикаго, Redmond и Vancouver.</span><span class="sxs-lookup"><span data-stu-id="dabec-190">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="dabec-191">С сетевым узлом контроля допуска звонков необходимо создать для каждого сайта в пределах организации, даже в том случае, если этот сайт имеет без ограничений пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="dabec-191">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="dabec-192">Из Скайп для панели управления Business Server можно создавать, изменять и удалять сетевых узлов.</span><span class="sxs-lookup"><span data-stu-id="dabec-192">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="dabec-193">Используйте следующую процедуру для удаления существующего сетевого узла.</span><span class="sxs-lookup"><span data-stu-id="dabec-193">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="dabec-194">Для получения дополнительных сведений о создании или изменение сетевых узлов видеть [Управление контроля допуска звонков для сайтов](managing-call-admission-control-for-sites.md).</span><span class="sxs-lookup"><span data-stu-id="dabec-194">For details about creating or modifying network sites, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>


### <a name="to-delete-a-network-site"></a><span data-ttu-id="dabec-195">Удаление сетевого узла</span><span class="sxs-lookup"><span data-stu-id="dabec-195">To delete a network site</span></span>

1.  <span data-ttu-id="dabec-196">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="dabec-196">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="dabec-197">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="dabec-197">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="dabec-198">В левой панели навигации щелкните **Конфигурация сети**и нажмите кнопку **сайта**.</span><span class="sxs-lookup"><span data-stu-id="dabec-198">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="dabec-199">На странице **сайта** щелкните сайт, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="dabec-199">On the **Site** page, click the site that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="dabec-200">Одновременно можно удалить несколько узлов.</span><span class="sxs-lookup"><span data-stu-id="dabec-200">You can delete more than one site at a time.</span></span> <span data-ttu-id="dabec-201">Для этого нажмите клавишу CTRL и выберите несколько сайтов, удерживая нажатой клавишу CTRL.</span><span class="sxs-lookup"><span data-stu-id="dabec-201">To do this, press CTRL and select multiple sites while holding down the CTRL key.</span></span> <span data-ttu-id="dabec-202">Или, чтобы выбрать все сайты, нажмите кнопку **Выбрать все** в меню **Правка** .</span><span class="sxs-lookup"><span data-stu-id="dabec-202">Or, to select all sites, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="dabec-203">В меню **Правка** выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="dabec-203">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="dabec-204">Нажмите **OK**.</span><span class="sxs-lookup"><span data-stu-id="dabec-204">Click **OK**.</span></span>
    

    > [!WARNING]  
    > <span data-ttu-id="dabec-205">Вы не можете удалить с сетевым узлом, если он связан с подсетью сети.</span><span class="sxs-lookup"><span data-stu-id="dabec-205">You cannot remove a network site if it is associated with a network subnet.</span></span> <span data-ttu-id="dabec-206">Если попытаться удалить сайт, связанный с подсети вы получите сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="dabec-206">If you attempt to remove a site associated with a subnet you will receive an error message.</span></span> <span data-ttu-id="dabec-207">Чтобы просмотреть, если сайт связан с любой подсети, щелкните сайт и нажмите кнопку **Показать подробности** в меню **Правка** .</span><span class="sxs-lookup"><span data-stu-id="dabec-207">To see if a site is associated with any subnets, click the site and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="dabec-208">См. также</span><span class="sxs-lookup"><span data-stu-id="dabec-208">See Also</span></span>


[<span data-ttu-id="dabec-209">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="dabec-209">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[<span data-ttu-id="dabec-210">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="dabec-210">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[<span data-ttu-id="dabec-211">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="dabec-211">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[<span data-ttu-id="dabec-212">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="dabec-212">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[<span data-ttu-id="dabec-213">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="dabec-213">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="dabec-214">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="dabec-214">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

[<span data-ttu-id="dabec-215">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="dabec-215">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

[<span data-ttu-id="dabec-216">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="dabec-216">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  

[<span data-ttu-id="dabec-217">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="dabec-217">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  