---
title: Управление управлением приемом вызовов для сайтов
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Сайты сети — это офисы или местоположения в каждом регионе сети развертывания контроля допуска вызовов (CAC), E9-1-1 и обхода мультимедиа.
ms.openlocfilehash: 0b339f15e53dd94bda655884f70c041f9da9e5a8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118568"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a><span data-ttu-id="4c9d9-103">Управление контролем допуска звонков для сайтов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="4c9d9-103">Managing call admission control for sites in Skype for Business Server</span></span>

<span data-ttu-id="4c9d9-104">Сайты сети — это офисы или местоположения в каждом регионе сети развертывания контроля допуска вызовов (CAC), E9-1-1 и обхода мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-104">Network sites are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="4c9d9-105">Используйте процедуры в этой статье для настройки управления приемом вызовов для сетевых сайтов.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-105">Use the procedures in this article to configure call admission control for network sites.</span></span>

## <a name="configure-network-site-links"></a><span data-ttu-id="4c9d9-106">Настройка ссылок на веб-сайт сети</span><span class="sxs-lookup"><span data-stu-id="4c9d9-106">Configure network site links</span></span>

<span data-ttu-id="4c9d9-107">В конфигурации контроля допуска звонков можно создать сетевые межузловые политики, которые определяют ограничения пропускной способности между связанными напрямую узлами.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-107">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="4c9d9-108">Когда сетевые узлы совместно используют прямую связь, ограничения для аудио- и видеосвязи можно задавать между этими двумя узлами.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-108">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="4c9d9-109">Панель управления Skype для бизнес-серверов не может настраивать политики веб-сайтов сети, это можно сделать только с помощью команды из оболочки управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-109">You cannot use the Skype for Business Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="4c9d9-110">Вы можете создать, изменить и удалить ссылку сетевого сайта (также известная как политика сетевого межсайтового сайта) из оболочки управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-110">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Skype for Business Server Management Shell.</span></span>

### <a name="to-create-a-network-site-link"></a><span data-ttu-id="4c9d9-111">Создание связи между сетевыми узлами</span><span class="sxs-lookup"><span data-stu-id="4c9d9-111">To create a network site link</span></span>

1.  <span data-ttu-id="4c9d9-112">Войдите на компьютер, на котором установлена оболочка управления Skype для бизнес-серверов в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-112">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="4c9d9-113">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните **Skype для** бизнес-сервера, а затем нажмите кнопку Skype для управления **бизнес-сервером.**</span><span class="sxs-lookup"><span data-stu-id="4c9d9-113">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="4c9d9-114">В Введите в командной строке следующую команду, подставив значения, подходящие для вашей конфигурации:</span><span class="sxs-lookup"><span data-stu-id="4c9d9-114">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="4c9d9-115">В этом примере создается новая ссылка на сетевой сайт с именем Reno Portland, которая задает ограничения пропускной способности между сетевыми сайтами \_ Reno и Portland.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-115">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="4c9d9-116">Перед выполнением этой команды уже должны существовать эти сетевые узлы и профиль политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-116">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="4c9d9-117">Подробные описания параметров см. [в обзоре New-CsNetworkInterSitePolicy.](/powershell/module/skype/New-CsNetworkInterSitePolicy)</span><span class="sxs-lookup"><span data-stu-id="4c9d9-117">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](/powershell/module/skype/New-CsNetworkInterSitePolicy).</span></span> <span data-ttu-id="4c9d9-118">Чтобы получить список профилей политик пропускной способности, которые можно применять к связи между сетевыми узлами, вызовите командлет **Get-CsNetworkBandwidthPolicyProfile**.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-118">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="4c9d9-119">Подробные сведения [см. в материале Get-CsNetworkBandwidthPolicyProfile.](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)</span><span class="sxs-lookup"><span data-stu-id="4c9d9-119">For details, see [Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span></span>

### <a name="to-modify-a-network-site-link"></a><span data-ttu-id="4c9d9-120">Изменение связи между сетевыми узлами</span><span class="sxs-lookup"><span data-stu-id="4c9d9-120">To modify a network site link</span></span>

1.  <span data-ttu-id="4c9d9-121">Войдите на компьютер, на котором установлена оболочка управления Skype для бизнес-серверов в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-121">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="4c9d9-122">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните **Skype для** бизнес-сервера, а затем нажмите кнопку Skype для управления **бизнес-сервером.**</span><span class="sxs-lookup"><span data-stu-id="4c9d9-122">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="4c9d9-123">Для изменения свойств конкретной связи между сетевыми узлами используется командлет **Set-CsNetworkInterSitePolicy**.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-123">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="4c9d9-124">Можно изменять каждый из связанных узлов (или оба этих узла), а также профиль политики пропускной способности, привязанный к этой связи.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-124">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="4c9d9-125">Вот пример изменения профиля политики пропускной способности ссылки сайта с именем Reno \_ Portland:</span><span class="sxs-lookup"><span data-stu-id="4c9d9-125">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="4c9d9-126">Подробные описания параметров см. [в инструкции Set-CsNetworkInterSitePolicy.](/powershell/module/skype/Set-CsNetworkInterSitePolicy)</span><span class="sxs-lookup"><span data-stu-id="4c9d9-126">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span></span>


### <a name="to-delete-a-network-site-link"></a><span data-ttu-id="4c9d9-127">Удаление связи между сетевыми узлами</span><span class="sxs-lookup"><span data-stu-id="4c9d9-127">To delete a network site link</span></span>

1.  <span data-ttu-id="4c9d9-128">Войдите на компьютер, на котором установлена оболочка управления Skype для бизнес-серверов в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-128">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="4c9d9-129">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните **Skype для** бизнес-сервера, а затем нажмите кнопку Skype для управления **бизнес-сервером.**</span><span class="sxs-lookup"><span data-stu-id="4c9d9-129">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="4c9d9-130">Для удаления связи между сетевыми узлами используется командлет **Remove-CsNetworkInterSitePolicy**.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-130">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="4c9d9-131">В следующем примере удаляется ссылка на веб-сайт сети Reno \_ Portland:</span><span class="sxs-lookup"><span data-stu-id="4c9d9-131">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="4c9d9-132">Подробные описания параметров см. [в инструкции Remove-CsNetworkInterSitePolicy.](/powershell/module/skype/Remove-CsNetworkInterSitePolicy)</span><span class="sxs-lookup"><span data-stu-id="4c9d9-132">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span></span>


## <a name="view-network-site-information"></a><span data-ttu-id="4c9d9-133">Просмотр сведений о сетевом сайте</span><span class="sxs-lookup"><span data-stu-id="4c9d9-133">View network site information</span></span>

<span data-ttu-id="4c9d9-134">Сетевые узлы — это офисы или места, настроенные в каждой области развертывания контроля допуска звонков (CAC) или Enhanced 9-1-1.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-134">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="4c9d9-135">Сведения о сетевом сайте можно просматривать в панели управления Skype для бизнес-серверов или в панели управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-135">You can view network site information in either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="4c9d9-136">Просмотр сведений о сетевом сайте в панели управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="4c9d9-136">To view network site information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="4c9d9-137">С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4c9d9-138">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-138">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4c9d9-139">В левой панели навигации щелкните **Конфигурация сети** и нажмите **кнопку Сайт**.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-139">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="4c9d9-140">На странице **Сайт** выберите сайт, который хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-140">On the **Site** page, click the site that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="4c9d9-141">Допускается одновременный просмотр данных только для одного сайта.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-141">You can only view information for one site at a time.</span></span>

5.  <span data-ttu-id="4c9d9-142">В меню **Правка** щелкните **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-142">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4c9d9-143">Просмотр сведений о сетевом сайте с помощью Windows PowerShell-кодлетов</span><span class="sxs-lookup"><span data-stu-id="4c9d9-143">Viewing network site information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="4c9d9-144">Сведения о сетевом сайте можно просматривать с помощью Windows PowerShell и Get-CsNetworkSite.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-144">You can view network site information by using Windows PowerShell and the Get-CsNetworkSite cmdlet.</span></span> <span data-ttu-id="4c9d9-145">Этот комлет можно выполнить либо из оболочки управления skype для бизнес-серверов, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-145">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-site-information"></a><span data-ttu-id="4c9d9-146">Просмотр сведений о сетевом сайте</span><span class="sxs-lookup"><span data-stu-id="4c9d9-146">To view network site information</span></span>

  - <span data-ttu-id="4c9d9-147">Чтобы просмотреть сведения обо всех сетевых сайтах, введите следующую команду в командной командной оболочке Skype для бизнес-серверов и нажмите кнопку ENTER:</span><span class="sxs-lookup"><span data-stu-id="4c9d9-147">To view information about all your network sites, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkSite
    
    <span data-ttu-id="4c9d9-148">Это приведет к возврату приблизительно такой информации:</span><span class="sxs-lookup"><span data-stu-id="4c9d9-148">That will return information similar to this:</span></span>
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

<span data-ttu-id="4c9d9-149">Дополнительные сведения см. в разделе справки для командлета [Get-CsNetworkSite](/powershell/module/skype/Get-CsNetworkSite).</span><span class="sxs-lookup"><span data-stu-id="4c9d9-149">For more information, see the help topic for the [Get-CsNetworkSite](/powershell/module/skype/Get-CsNetworkSite) cmdlet.</span></span>


## <a name="create-or-modify-network-sites"></a><span data-ttu-id="4c9d9-150">Создание или изменение сетевых сайтов</span><span class="sxs-lookup"><span data-stu-id="4c9d9-150">Create or modify network sites</span></span> 

<span data-ttu-id="4c9d9-151">Сетевые узлы — это офисы или места, настроенные в каждой области развертывания контроля допуска звонков (CAC) или Enhanced 9-1-1.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-151">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="4c9d9-152">Панель управления Skype для бизнес-серверов можно настроить сайты и связать их с регионами.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-152">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="4c9d9-153">Например, сетевую область для Северной Америки можно связать с такими сетевыми узлами, как Чикаго, Редмонд и Ванкувер.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-153">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="4c9d9-154">Сетевой узел CAC необходимо создать для каждого узла в организации, даже если у этого узла нет ограничений по пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-154">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="4c9d9-155">С панели управления Skype для бизнес-серверов можно создавать, изменять и удалять сетевые сайты.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-155">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="4c9d9-156">Ниже описаны процедуры для создания или изменения сетевого узла.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-156">Use the following procedures to create or modify a network site.</span></span> 

### <a name="to-create-a-network-site"></a><span data-ttu-id="4c9d9-157">Создание сетевого узла</span><span class="sxs-lookup"><span data-stu-id="4c9d9-157">To create a network site</span></span>

1.  <span data-ttu-id="4c9d9-158">С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-158">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4c9d9-159">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-159">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4c9d9-160">В левой панели навигации щелкните **Конфигурация сети** и нажмите **кнопку Сайт**.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-160">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="4c9d9-161">На странице **Узел** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-161">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="4c9d9-162">В диалоговом окне **Создание узла** введите имя узла в поле **Имя**.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-162">In **New Site**, type a name for this site in the **Name** field.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="4c9d9-163">Имена сайтов должны быть уникальными в развертывании Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-163">Site names must be unique within the Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="4c9d9-164">В раскрывающемся списке **Область** выберите сетевую область, которую необходимо сопоставить с этим узлом.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-164">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="4c9d9-165">(Необязательно) Если нужно наложить ограничения полосы пропускания на аудио- или видеовызовы с данного узла, выберите профиль политики с соответствующими параметрами в раскрывающемся списке **Политика полосы пропускания**.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-165">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="4c9d9-166">Сведения о доступных профилях политики пропускной способности или создание нового профиля политики пропускной способности можно просмотреть на странице **Policy Profil** группы **конфигурации** сети.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-166">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the **Policy Profil** page of the **Network Configuration** group.</span></span> <span data-ttu-id="4c9d9-167">Подробные сведения см. в [материале Managing network bandwidth policy profiles.](managing-network-bandwidth-policy-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="4c9d9-167">For details, see [Managing network bandwidth policy profiles](managing-network-bandwidth-policy-profiles.md).</span></span>

8.  <span data-ttu-id="4c9d9-168">(Необязательно) Если требуется предоставить параметры местоположения для данного узла, выберите политику расположения в раскрывающемся списке **Политика расположения**.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-168">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="4c9d9-169">Политика расположения устанавливает определенные параметры системы Enhanced 9-1-1 (E9-1-1) и клиентского расположения для узла.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-169">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="4c9d9-170">Вы можете просмотреть сведения о доступных политиках или создать новую на странице **Политика расположения** группы **Конфигурация сети**.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-170">You can view the details of the available location policies, or create a new location policy, from the **Location Policy** page of the **Network Configuration** group.</span></span> 

9.  <span data-ttu-id="4c9d9-171">(Необязательно) Введите значение в поле **Описание**, чтобы предоставить дополнительную информацию об этом узле, которую нельзя выразить в имени.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-171">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="4c9d9-172">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-172">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="4c9d9-173">Таблица **Связанные подсети** не используется при создании нового сетевого узла.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-173">You do not use the **Associated Subnets** table when you create a new network site.</span></span> <span data-ttu-id="4c9d9-174">Необходимо связать подсеть с узлом при создании или изменении подсети.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-174">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="4c9d9-175">Подробные сведения см. [в материале Managing network subnets.](managing-network-subnets.md)</span><span class="sxs-lookup"><span data-stu-id="4c9d9-175">For details, see [Managing network subnets](managing-network-subnets.md).</span></span>

### <a name="to-modify-a-network-site"></a><span data-ttu-id="4c9d9-176">Изменение сетевого узла</span><span class="sxs-lookup"><span data-stu-id="4c9d9-176">To modify a network site</span></span>

1.  <span data-ttu-id="4c9d9-177">С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-177">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4c9d9-178">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-178">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4c9d9-179">В левой панели навигации щелкните **Конфигурация сети** и нажмите **кнопку Сайт**.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-179">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="4c9d9-180">На странице **Узел** щелкните узел, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-180">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="4c9d9-181">В меню **Правка** выберите команду **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-181">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="4c9d9-182">На странице **Редактирование узла** вы можете изменить описание, область, профиль политики полосы пропускания и политику расположения, связанную с узлом.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-182">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site.</span></span> <span data-ttu-id="4c9d9-183">Дополнительные сведения [см. в материале "Создание сетевого сайта](#to-create-a-network-site) выше".</span><span class="sxs-lookup"><span data-stu-id="4c9d9-183">For details, see [To create a network site](#to-create-a-network-site) above.</span></span>

7.  <span data-ttu-id="4c9d9-184">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-184">Click **Commit**.</span></span>

<span data-ttu-id="4c9d9-p114">Вы не можете изменить таблицу **Связанные подсети** на этой странице. Список связанных подсетей предоставлен для справки, чтобы вы могли узнать, на что повлияет изменение параметров узла.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-p114">You cannot modify the **Associated Subnets** table on this page. The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>


## <a name="delete-an-existing-network-site"></a><span data-ttu-id="4c9d9-187">Удаление существующего сетевого сайта</span><span class="sxs-lookup"><span data-stu-id="4c9d9-187">Delete an existing network site</span></span>

<span data-ttu-id="4c9d9-188">Сетевые узлы — это офисы или места, настроенные в каждой области развертывания контроля допуска звонков (CAC) или Enhanced 9-1-1.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-188">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="4c9d9-189">Панель управления Skype для бизнес-серверов можно настроить сайты и связать их с регионами.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-189">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="4c9d9-190">Например, сетевую область для Северной Америки можно связать с такими сетевыми узлами, как Чикаго, Редмонд и Ванкувер.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-190">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="4c9d9-191">Сетевой узел CAC необходимо создать для каждого узла в организации, даже если у этого узла нет ограничений по пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-191">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="4c9d9-192">С панели управления Skype для бизнес-серверов можно создавать, изменять и удалять сетевые сайты.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-192">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="4c9d9-193">Используйте следующую процедуру для удаления существующего сетевого сайта.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-193">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="4c9d9-194">Дополнительные сведения о создании или изменении сетевых сайтов см. в материале [Managing call admission control for sites.](managing-call-admission-control-for-sites.md)</span><span class="sxs-lookup"><span data-stu-id="4c9d9-194">For details about creating or modifying network sites, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>


### <a name="to-delete-a-network-site"></a><span data-ttu-id="4c9d9-195">Удаление сетевого узла</span><span class="sxs-lookup"><span data-stu-id="4c9d9-195">To delete a network site</span></span>

1.  <span data-ttu-id="4c9d9-196">С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-196">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4c9d9-197">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-197">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4c9d9-198">В левой панели навигации щелкните **Конфигурация сети** и нажмите **кнопку Сайт**.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-198">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="4c9d9-199">На странице **Узел** щелкните узел, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-199">On the **Site** page, click the site that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="4c9d9-p116">Вы можете удалить несколько узлов за раз. Для этого нажмите клавишу CTRL и выберите несколько узлов, удерживая клавишу CTRL нажатой. Или, чтобы выбрать все узлы, щелкните **Выбрать все** в меню **Правка**.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-p116">You can delete more than one site at a time. To do this, press CTRL and select multiple sites while holding down the CTRL key. Or, to select all sites, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="4c9d9-203">В меню **Правка** выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-203">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="4c9d9-204">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-204">Click **OK**.</span></span>
    

    > [!WARNING]  
    > <span data-ttu-id="4c9d9-p117">Вы не можете удалить сетевой узел, если он связан с подсетью. При попытке удаления такого узла отображается сообщение об ошибке. Чтобы увидеть, связал ли узел с какой-либо подсетью, щелкните узел и выберите команду **Показать подробности** в меню **Правка**.</span><span class="sxs-lookup"><span data-stu-id="4c9d9-p117">You cannot remove a network site if it is associated with a network subnet. If you attempt to remove a site associated with a subnet you will receive an error message. To see if a site is associated with any subnets, click the site and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="4c9d9-208">См. также</span><span class="sxs-lookup"><span data-stu-id="4c9d9-208">See Also</span></span>


[<span data-ttu-id="4c9d9-209">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="4c9d9-209">New-CsNetworkInterSitePolicy</span></span>](/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[<span data-ttu-id="4c9d9-210">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="4c9d9-210">Set-CsNetworkInterSitePolicy</span></span>](/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[<span data-ttu-id="4c9d9-211">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="4c9d9-211">Remove-CsNetworkInterSitePolicy</span></span>](/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[<span data-ttu-id="4c9d9-212">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="4c9d9-212">Get-CsNetworkInterSitePolicy</span></span>](/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[<span data-ttu-id="4c9d9-213">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="4c9d9-213">Get-CsNetworkBandwidthPolicyProfile</span></span>](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="4c9d9-214">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="4c9d9-214">New-CsNetworkSite</span></span>](/powershell/module/skype/New-CsNetworkSite)

[<span data-ttu-id="4c9d9-215">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="4c9d9-215">Set-CsNetworkSite</span></span>](/powershell/module/skype/Set-CsNetworkSite)

[<span data-ttu-id="4c9d9-216">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="4c9d9-216">Remove-CsNetworkSite</span></span>](/powershell/module/skype/Remove-CsNetworkSite)  

[<span data-ttu-id="4c9d9-217">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="4c9d9-217">Get-CsNetworkSite</span></span>](/powershell/module/skype/Get-CsNetworkSite)