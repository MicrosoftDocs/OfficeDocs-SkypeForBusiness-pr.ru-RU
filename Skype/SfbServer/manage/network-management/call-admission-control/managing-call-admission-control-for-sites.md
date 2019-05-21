---
title: Управление допуском звонков для сайтов
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Сетевые сайты — это офисы или места в каждом сетевом регионе управления допуском звонков (CAC), E9-1-1, а также с помощью мультимедийных развертываний.
ms.openlocfilehash: a90781eae38d92d560dd1bf34db3b6918e8aeaf5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279545"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a><span data-ttu-id="33f7a-103">Управление контролем допуска звонков для сайтов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="33f7a-103">Managing call admission control for sites in Skype for Business Server</span></span>

<span data-ttu-id="33f7a-104">Сетевые сайты — это офисы или места в каждом сетевом регионе управления допуском звонков (CAC), E9-1-1, а также с помощью мультимедийных развертываний.</span><span class="sxs-lookup"><span data-stu-id="33f7a-104">Network sites are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="33f7a-105">Чтобы настроить управление допуском звонков для сетевых сайтов, выполните действия, описанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="33f7a-105">Use the procedures in this article to configure call admission control for network sites.</span></span>

## <a name="configure-network-site-links"></a><span data-ttu-id="33f7a-106">Настройка связей сайтов сети</span><span class="sxs-lookup"><span data-stu-id="33f7a-106">Configure network site links</span></span>

<span data-ttu-id="33f7a-107">В конфигурации управления допуском звонков (CAC) можно создавать сетевые политики межсайтовых связей, определяющие ограничения пропускной способности между сайтами, которые непосредственно связаны.</span><span class="sxs-lookup"><span data-stu-id="33f7a-107">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="33f7a-108">Если сетевые сайты имеют прямую связь, для них можно определять ограничения пропускной способности для аудио-и видеоподключений.</span><span class="sxs-lookup"><span data-stu-id="33f7a-108">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="33f7a-109">Вы не можете использовать панель управления "Skype для бизнеса" на сервере для настройки политик сетевого сайта, это можно сделать только с помощью командлетов из командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="33f7a-109">You cannot use the Skype for Business Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="33f7a-110">Вы можете создавать, изменять и удалять ссылки на сетевые сайты (также называемые сетевым межсайтовыми политиками) из командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="33f7a-110">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Skype for Business Server Management Shell.</span></span>

### <a name="to-create-a-network-site-link"></a><span data-ttu-id="33f7a-111">Создание связи сайтов сети</span><span class="sxs-lookup"><span data-stu-id="33f7a-111">To create a network site link</span></span>

1.  <span data-ttu-id="33f7a-112">Войдите в систему на компьютере, на котором установлена консоль управления Skype для бизнеса Server, в качестве участника группы Рткуниверсалсерверадминс или с необходимыми правами пользователя.</span><span class="sxs-lookup"><span data-stu-id="33f7a-112">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="33f7a-113">Запустите консоль управления в Skype для бизнеса Server: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Skype**для бизнеса Server, а затем — **Командная консоль управления Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="33f7a-113">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="33f7a-114">В командной строке введите следующую команду: подставляемые значения, которые являются допустимыми для вашей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="33f7a-114">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="33f7a-115">В этом примере создается ссылка на веб-сайт с\_именем Рено Портленде, которая устанавливает ограничения для пропускной способности между сайтами Рено и Портленде.</span><span class="sxs-lookup"><span data-stu-id="33f7a-115">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="33f7a-116">Перед выполнением этой команды необходимо, чтобы сетевые сайты и профиль политики пропускания уже существовали.</span><span class="sxs-lookup"><span data-stu-id="33f7a-116">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="33f7a-117">Подробное описание параметров можно найти в разделе [New-кснетворкинтерситеполици](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="33f7a-117">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy).</span></span> <span data-ttu-id="33f7a-118">Чтобы получить список профилей политики пропускной способности, которые можно применить к связи сайтов сети, вызовите командлет **Get-кснетворкбандвидсполиципрофиле** .</span><span class="sxs-lookup"><span data-stu-id="33f7a-118">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="33f7a-119">Подробности можно найти в [статьях Get-кснетворкбандвидсполиципрофиле](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span><span class="sxs-lookup"><span data-stu-id="33f7a-119">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span></span>

### <a name="to-modify-a-network-site-link"></a><span data-ttu-id="33f7a-120">Изменение связи сайтов сети</span><span class="sxs-lookup"><span data-stu-id="33f7a-120">To modify a network site link</span></span>

1.  <span data-ttu-id="33f7a-121">Войдите в систему на компьютере, на котором установлена консоль управления Skype для бизнеса Server, в качестве участника группы Рткуниверсалсерверадминс или с необходимыми правами пользователя.</span><span class="sxs-lookup"><span data-stu-id="33f7a-121">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="33f7a-122">Запустите консоль управления в Skype для бизнеса Server: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Skype**для бизнеса Server, а затем — **Командная консоль управления Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="33f7a-122">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="33f7a-123">Используйте командлет **Set-кснетворкинтерситеполици** , чтобы изменить свойства данной ссылки на сайт сети.</span><span class="sxs-lookup"><span data-stu-id="33f7a-123">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="33f7a-124">Вы можете изменить либо (или и то, и другое) подключенные сайты, а также изменить профиль политики для пропускной способности, связанный со ссылкой.</span><span class="sxs-lookup"><span data-stu-id="33f7a-124">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="33f7a-125">Ниже приведен пример изменения профиля политики пропускной способности для ссылки на сайт с именем\_Рено Портленде.</span><span class="sxs-lookup"><span data-stu-id="33f7a-125">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="33f7a-126">Подробное описание параметров можно найти в разделе [Set-кснетворкинтерситеполици](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="33f7a-126">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span></span>


### <a name="to-delete-a-network-site-link"></a><span data-ttu-id="33f7a-127">Удаление ссылки на сайт сети</span><span class="sxs-lookup"><span data-stu-id="33f7a-127">To delete a network site link</span></span>

1.  <span data-ttu-id="33f7a-128">Войдите в систему на компьютере, на котором установлена консоль управления Skype для бизнеса Server, в качестве участника группы Рткуниверсалсерверадминс или с необходимыми правами пользователя.</span><span class="sxs-lookup"><span data-stu-id="33f7a-128">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="33f7a-129">Запустите консоль управления в Skype для бизнеса Server: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Skype**для бизнеса Server, а затем — **Командная консоль управления Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="33f7a-129">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="33f7a-130">С помощью командлета **Remove-кснетворкинтерситеполици** удалите связь с сетевым сайтом.</span><span class="sxs-lookup"><span data-stu-id="33f7a-130">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="33f7a-131">В следующем примере удаляется ссылка\_на веб-сайт Рено в Портленде:</span><span class="sxs-lookup"><span data-stu-id="33f7a-131">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="33f7a-132">Подробное описание параметров приведено в разделе [Remove-кснетворкинтерситеполици](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="33f7a-132">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span></span>


## <a name="view-network-site-information"></a><span data-ttu-id="33f7a-133">Просмотр сведений о сетевом сайте</span><span class="sxs-lookup"><span data-stu-id="33f7a-133">View network site information</span></span>

<span data-ttu-id="33f7a-134">Сетевые сайты — это офисы или места, настроенные в каждом регионе управления допуском звонков (CAC) или Улучшенное развертывание 9-1-1.</span><span class="sxs-lookup"><span data-stu-id="33f7a-134">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="33f7a-135">Просмотреть сведения о сетевом сайте можно на панели управления Skype для бизнеса Server или в командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="33f7a-135">You can view network site information in either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="33f7a-136">Просмотр сведений о сетевом сайте на панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="33f7a-136">To view network site information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="33f7a-137">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="33f7a-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="33f7a-138">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="33f7a-138">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="33f7a-139">На панели навигации слева выберите пункт **Настройка сети**, а затем — **сайт**.</span><span class="sxs-lookup"><span data-stu-id="33f7a-139">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="33f7a-140">На странице **сайта** выберите сайт, который вы хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="33f7a-140">On the **Site** page, click the site that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="33f7a-141">Вы можете просматривать сведения только для одного сайта одновременно.</span><span class="sxs-lookup"><span data-stu-id="33f7a-141">You can only view information for one site at a time.</span></span>

5.  <span data-ttu-id="33f7a-142">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="33f7a-142">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="33f7a-143">Просмотр сведений о сетевом сайте с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="33f7a-143">Viewing network site information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="33f7a-144">Вы можете просматривать сведения о сетевом сайте с помощью Windows PowerShell и командлета Get-Кснетворксите.</span><span class="sxs-lookup"><span data-stu-id="33f7a-144">You can view network site information by using Windows PowerShell and the Get-CsNetworkSite cmdlet.</span></span> <span data-ttu-id="33f7a-145">Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="33f7a-145">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-site-information"></a><span data-ttu-id="33f7a-146">Просмотр сведений о сетевом сайте</span><span class="sxs-lookup"><span data-stu-id="33f7a-146">To view network site information</span></span>

  - <span data-ttu-id="33f7a-147">Чтобы просмотреть сведения о всех сетевых сайтах, введите в командной консоли Skype для Business Server указанную ниже команду и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="33f7a-147">To view information about all your network sites, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkSite
    
    <span data-ttu-id="33f7a-148">Команда возвращает примерно следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="33f7a-148">That will return information similar to this:</span></span>
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

<span data-ttu-id="33f7a-149">Дополнительные сведения можно найти в разделе справки по командлету [Get-кснетворксите](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) .</span><span class="sxs-lookup"><span data-stu-id="33f7a-149">For more information, see the help topic for the [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet.</span></span>


## <a name="create-or-modify-network-sites"></a><span data-ttu-id="33f7a-150">Создание и изменение сетевых сайтов</span><span class="sxs-lookup"><span data-stu-id="33f7a-150">Create or modify network sites</span></span> 

<span data-ttu-id="33f7a-151">Сетевые сайты — это офисы или места, настроенные в каждом регионе управления допуском звонков (CAC) или Улучшенное развертывание 9-1-1.</span><span class="sxs-lookup"><span data-stu-id="33f7a-151">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="33f7a-152">Вы можете настроить сайты и связать их с областями с помощью панели управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="33f7a-152">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="33f7a-153">Например, сетевой регион для Северной Америки может быть связан с сайтами сети, например в Чикаго, Redmond и Vancouver.</span><span class="sxs-lookup"><span data-stu-id="33f7a-153">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="33f7a-154">Сайт сети CAC должен создаваться для каждого сайта в Организации, даже если на нем нет ограничений по пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="33f7a-154">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="33f7a-155">На панели управления сервера Skype для бизнеса можно создавать, изменять и удалять сетевые сайты.</span><span class="sxs-lookup"><span data-stu-id="33f7a-155">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="33f7a-156">Для создания и изменения сайта сети выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="33f7a-156">Use the following procedures to create or modify a network site.</span></span> 

### <a name="to-create-a-network-site"></a><span data-ttu-id="33f7a-157">Создание сайта сети</span><span class="sxs-lookup"><span data-stu-id="33f7a-157">To create a network site</span></span>

1.  <span data-ttu-id="33f7a-158">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="33f7a-158">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="33f7a-159">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="33f7a-159">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="33f7a-160">На панели навигации слева выберите пункт **Настройка сети**, а затем — **сайт**.</span><span class="sxs-lookup"><span data-stu-id="33f7a-160">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="33f7a-161">На странице **сайта** нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="33f7a-161">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="33f7a-162">В поле **имя** **нового сайта**введите имя для этого сайта.</span><span class="sxs-lookup"><span data-stu-id="33f7a-162">In **New Site**, type a name for this site in the **Name** field.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="33f7a-163">Имена сайтов должны быть уникальными в рамках развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="33f7a-163">Site names must be unique within the Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="33f7a-164">В раскрывающемся списке **Region (регион** ) выберите сетевую область, которую нужно связать с этим сайтом.</span><span class="sxs-lookup"><span data-stu-id="33f7a-164">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="33f7a-165">Необязательно Если вы хотите помещать ограничения на пропускную способность для звуковых и видеозвонков на этот сайт, выберите профиль политики пропускной способности с нужными параметрами из раскрывающегося списка **политики пропускной способности** .</span><span class="sxs-lookup"><span data-stu-id="33f7a-165">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="33f7a-166">Вы можете просмотреть сведения о доступных профилях политики пропускной способности или создать новый профиль политики пропускной способности на странице **политики профил** в группе **Конфигурация сети** .</span><span class="sxs-lookup"><span data-stu-id="33f7a-166">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the **Policy Profil** page of the **Network Configuration** group.</span></span> <span data-ttu-id="33f7a-167">Подробности можно найти в разделе [Управление профилями политики пропускной способности сети](managing-network-bandwidth-policy-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="33f7a-167">For details, see [Managing network bandwidth policy profiles](managing-network-bandwidth-policy-profiles.md).</span></span>

8.  <span data-ttu-id="33f7a-168">Необязательно Если вы хотите предоставить параметры расположения для этого сайта, выберите политику расположения из раскрывающегося списка " **Политика расположения** ".</span><span class="sxs-lookup"><span data-stu-id="33f7a-168">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="33f7a-169">Политика расположения назначает узлу дополнительные 9-1-1 (E9-1-1) и параметры расположения клиента.</span><span class="sxs-lookup"><span data-stu-id="33f7a-169">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="33f7a-170">Вы можете просмотреть сведения о доступных политиках расположения или создать новую политику местоположения на странице " **Политика расположения** " в группе " **Конфигурация сети** ".</span><span class="sxs-lookup"><span data-stu-id="33f7a-170">You can view the details of the available location policies, or create a new location policy, from the **Location Policy** page of the **Network Configuration** group.</span></span> 

9.  <span data-ttu-id="33f7a-171">Необязательно Введите значение в поле **Описание** , чтобы получить дополнительные сведения об этом сайте, которые нельзя выразить единственным именем.</span><span class="sxs-lookup"><span data-stu-id="33f7a-171">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="33f7a-172">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="33f7a-172">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="33f7a-173">При создании нового сайта сети \*\*\*\* не следует использовать таблицу с сопоставленными подсетями.</span><span class="sxs-lookup"><span data-stu-id="33f7a-173">You do not use the **Associated Subnets** table when you create a new network site.</span></span> <span data-ttu-id="33f7a-174">При создании или изменении подсети вы связываете подсеть с сайтом.</span><span class="sxs-lookup"><span data-stu-id="33f7a-174">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="33f7a-175">Подробности можно найти в разделе [Управление сетевыми](managing-network-subnets.md)подсетями.</span><span class="sxs-lookup"><span data-stu-id="33f7a-175">For details, see [Managing network subnets](managing-network-subnets.md).</span></span>

### <a name="to-modify-a-network-site"></a><span data-ttu-id="33f7a-176">Изменение сетевого сайта</span><span class="sxs-lookup"><span data-stu-id="33f7a-176">To modify a network site</span></span>

1.  <span data-ttu-id="33f7a-177">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="33f7a-177">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="33f7a-178">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="33f7a-178">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="33f7a-179">На панели навигации слева выберите пункт **Настройка сети**, а затем — **сайт**.</span><span class="sxs-lookup"><span data-stu-id="33f7a-179">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="33f7a-180">На странице **сайта** выберите сайт, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="33f7a-180">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="33f7a-181">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="33f7a-181">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="33f7a-182">На странице **изменение сайта** можно изменить описание, область, профиль политики пропускной способности и политику расположения, связанные с сайтом.</span><span class="sxs-lookup"><span data-stu-id="33f7a-182">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site.</span></span> <span data-ttu-id="33f7a-183">Подробности можно найти [в разделе Создание сетевого сайта](#to-create-a-network-site) выше.</span><span class="sxs-lookup"><span data-stu-id="33f7a-183">For details, see [To create a network site](#to-create-a-network-site) above.</span></span>

7.  <span data-ttu-id="33f7a-184">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="33f7a-184">Click **Commit**.</span></span>

<span data-ttu-id="33f7a-185">На этой странице невозможно \*\*\*\* изменить связанную таблицу подсетей.</span><span class="sxs-lookup"><span data-stu-id="33f7a-185">You cannot modify the **Associated Subnets** table on this page.</span></span> <span data-ttu-id="33f7a-186">Список связанных подсетей предоставляется для справки, чтобы узнать о том, какие подсети будут затронуты при изменении параметров сайта.</span><span class="sxs-lookup"><span data-stu-id="33f7a-186">The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>


## <a name="delete-an-existing-network-site"></a><span data-ttu-id="33f7a-187">Удаление существующего сетевого сайта</span><span class="sxs-lookup"><span data-stu-id="33f7a-187">Delete an existing network site</span></span>

<span data-ttu-id="33f7a-188">Сетевые сайты — это офисы или места, настроенные в каждом регионе управления допуском звонков (CAC) или Улучшенное развертывание 9-1-1.</span><span class="sxs-lookup"><span data-stu-id="33f7a-188">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="33f7a-189">Вы можете настроить сайты и связать их с областями с помощью панели управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="33f7a-189">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="33f7a-190">Например, сетевой регион для Северной Америки может быть связан с сайтами сети, например в Чикаго, Redmond и Vancouver.</span><span class="sxs-lookup"><span data-stu-id="33f7a-190">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="33f7a-191">Сайт сети CAC должен создаваться для каждого сайта в Организации, даже если на нем нет ограничений по пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="33f7a-191">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="33f7a-192">На панели управления сервера Skype для бизнеса можно создавать, изменять и удалять сетевые сайты.</span><span class="sxs-lookup"><span data-stu-id="33f7a-192">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="33f7a-193">Чтобы удалить существующий сайт сети, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="33f7a-193">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="33f7a-194">Дополнительные сведения о создании и изменении сайтов сети можно найти в разделе [Управление допуском звонков для сайтов](managing-call-admission-control-for-sites.md).</span><span class="sxs-lookup"><span data-stu-id="33f7a-194">For details about creating or modifying network sites, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>


### <a name="to-delete-a-network-site"></a><span data-ttu-id="33f7a-195">Удаление сайта сети</span><span class="sxs-lookup"><span data-stu-id="33f7a-195">To delete a network site</span></span>

1.  <span data-ttu-id="33f7a-196">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="33f7a-196">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="33f7a-197">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="33f7a-197">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="33f7a-198">На панели навигации слева выберите пункт **Настройка сети**, а затем — **сайт**.</span><span class="sxs-lookup"><span data-stu-id="33f7a-198">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="33f7a-199">На странице **сайта** выберите сайт, который вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="33f7a-199">On the **Site** page, click the site that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="33f7a-200">За один раз можно удалить сразу несколько сайтов.</span><span class="sxs-lookup"><span data-stu-id="33f7a-200">You can delete more than one site at a time.</span></span> <span data-ttu-id="33f7a-201">Для этого нажмите клавишу CTRL и, удерживая нажатой клавишу CTRL, щелкните несколько сайтов.</span><span class="sxs-lookup"><span data-stu-id="33f7a-201">To do this, press CTRL and select multiple sites while holding down the CTRL key.</span></span> <span data-ttu-id="33f7a-202">Кроме того, чтобы выбрать все сайты, в меню **Правка** выберите команду **выделить все** .</span><span class="sxs-lookup"><span data-stu-id="33f7a-202">Or, to select all sites, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="33f7a-203">В меню **Правка** выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="33f7a-203">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="33f7a-204">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="33f7a-204">Click **OK**.</span></span>
    

    > [!WARNING]  
    > <span data-ttu-id="33f7a-205">Вы не можете удалить сайт сети, если он связан с сетевой подсетью.</span><span class="sxs-lookup"><span data-stu-id="33f7a-205">You cannot remove a network site if it is associated with a network subnet.</span></span> <span data-ttu-id="33f7a-206">При попытке удалить сайт, связанный с подсетью, появится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="33f7a-206">If you attempt to remove a site associated with a subnet you will receive an error message.</span></span> <span data-ttu-id="33f7a-207">Чтобы проверить, связан ли сайт с подсетями, щелкните его, а затем в меню **Правка** выберите команду **Показать подробности** .</span><span class="sxs-lookup"><span data-stu-id="33f7a-207">To see if a site is associated with any subnets, click the site and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="33f7a-208">См. также</span><span class="sxs-lookup"><span data-stu-id="33f7a-208">See Also</span></span>


[<span data-ttu-id="33f7a-209">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="33f7a-209">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[<span data-ttu-id="33f7a-210">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="33f7a-210">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[<span data-ttu-id="33f7a-211">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="33f7a-211">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[<span data-ttu-id="33f7a-212">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="33f7a-212">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[<span data-ttu-id="33f7a-213">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="33f7a-213">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="33f7a-214">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="33f7a-214">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

[<span data-ttu-id="33f7a-215">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="33f7a-215">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

[<span data-ttu-id="33f7a-216">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="33f7a-216">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  

[<span data-ttu-id="33f7a-217">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="33f7a-217">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
