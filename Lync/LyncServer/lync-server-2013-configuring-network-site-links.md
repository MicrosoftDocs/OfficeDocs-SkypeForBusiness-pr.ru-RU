---
title: 'Lync Server 2013: Настройка ссылок на сайты сети'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring network site links
ms:assetid: 7e9147ae-e727-46c8-8c1a-6c13201f09be
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521023(v=OCS.15)
ms:contentKeyID: 48184622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e379a8195dd0a50d97a514307ac594908be4736c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-network-site-links-in-lync-server-2013"></a><span data-ttu-id="5fadf-102">Настройка связей сайтов сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fadf-102">Configuring network site links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5fadf-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5fadf-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5fadf-104">В конфигурации управления допуском звонков (CAC) можно создавать сетевые политики межсайтовых связей, определяющие ограничения пропускной способности между сайтами, которые непосредственно связаны.</span><span class="sxs-lookup"><span data-stu-id="5fadf-104">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="5fadf-105">Если сетевые сайты имеют прямую связь, для них можно определять ограничения пропускной способности для аудио-и видеоподключений.</span><span class="sxs-lookup"><span data-stu-id="5fadf-105">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="5fadf-106">Вы не можете использовать панель управления Lync Server для настройки политик сетевого сайта, это можно сделать только с помощью командлетов из командной консоли Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5fadf-106">You cannot use the Lync Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Lync Server Management Shell.</span></span> <span data-ttu-id="5fadf-107">Вы можете создавать, изменять и удалять ссылки на сетевые сайты (также называемые межсетевой политикой сайтов) из командной консоли Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5fadf-107">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Lync Server Management Shell.</span></span>

<div>

## <a name="to-create-a-network-site-link"></a><span data-ttu-id="5fadf-108">Создание связи сайтов сети</span><span class="sxs-lookup"><span data-stu-id="5fadf-108">To create a network site link</span></span>

1.  <span data-ttu-id="5fadf-109">Войдите на компьютер, на котором установлена командная консоль Lync Server Management Shell, в группу Рткуниверсалсерверадминс или с необходимыми правами пользователя, как описано в разделе [Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="5fadf-109">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="5fadf-110">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="5fadf-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="5fadf-111">В командной строке введите следующую команду: подставляемые значения, которые являются допустимыми для вашей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5fadf-111">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="5fadf-112">В этом примере создается ссылка на веб-сайт с\_именем Рено Портленде, которая устанавливает ограничения для пропускной способности между сайтами Рено и Портленде.</span><span class="sxs-lookup"><span data-stu-id="5fadf-112">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="5fadf-113">Перед выполнением этой команды необходимо, чтобы сетевые сайты и профиль политики пропускания уже существовали.</span><span class="sxs-lookup"><span data-stu-id="5fadf-113">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="5fadf-114">Подробное описание параметров можно найти в разделе [New-кснетворкинтерситеполици](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) в документации по консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5fadf-114">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span> <span data-ttu-id="5fadf-115">Чтобы получить список профилей политики пропускной способности, которые можно применить к связи сайтов сети, вызовите командлет **Get-кснетворкбандвидсполиципрофиле** .</span><span class="sxs-lookup"><span data-stu-id="5fadf-115">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="5fadf-116">Подробности можно найти в разделе [Get-кснетворкбандвидсполиципрофиле](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) в документации по среде управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5fadf-116">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-modify-a-network-site-link"></a><span data-ttu-id="5fadf-117">Изменение связи сайтов сети</span><span class="sxs-lookup"><span data-stu-id="5fadf-117">To modify a network site link</span></span>

1.  <span data-ttu-id="5fadf-118">Войдите на компьютер, на котором установлена командная консоль Lync Server Management Shell, в группу Рткуниверсалсерверадминс или с необходимыми правами пользователя, как описано в разделе [Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="5fadf-118">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="5fadf-119">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="5fadf-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="5fadf-120">Используйте командлет **Set-кснетворкинтерситеполици** , чтобы изменить свойства данной ссылки на сайт сети.</span><span class="sxs-lookup"><span data-stu-id="5fadf-120">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="5fadf-121">Вы можете изменить либо (или и то, и другое) подключенные сайты, а также изменить профиль политики для пропускной способности, связанный со ссылкой.</span><span class="sxs-lookup"><span data-stu-id="5fadf-121">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="5fadf-122">Ниже приведен пример изменения профиля политики пропускной способности для ссылки на сайт с именем\_Рено Портленде.</span><span class="sxs-lookup"><span data-stu-id="5fadf-122">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="5fadf-123">Подробное описание параметров можно найти в разделе [Set-кснетворкинтерситеполици](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) в документации по консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5fadf-123">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-delete-a-network-site-link"></a><span data-ttu-id="5fadf-124">Удаление ссылки на сайт сети</span><span class="sxs-lookup"><span data-stu-id="5fadf-124">To delete a network site link</span></span>

1.  <span data-ttu-id="5fadf-125">Войдите на компьютер, на котором установлена командная консоль Lync Server Management Shell, в группу Рткуниверсалсерверадминс или с необходимыми правами пользователя, как описано в разделе [Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="5fadf-125">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="5fadf-126">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="5fadf-126">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="5fadf-127">С помощью командлета **Remove-кснетворкинтерситеполици** удалите связь с сетевым сайтом.</span><span class="sxs-lookup"><span data-stu-id="5fadf-127">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="5fadf-128">В следующем примере удаляется ссылка\_на веб-сайт Рено в Портленде:</span><span class="sxs-lookup"><span data-stu-id="5fadf-128">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="5fadf-129">Подробное описание параметров приведено в разделе [Remove-кснетворкинтерситеполици](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) в документации по среде управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5fadf-129">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5fadf-130">См. также</span><span class="sxs-lookup"><span data-stu-id="5fadf-130">See Also</span></span>


[<span data-ttu-id="5fadf-131">Командлеты управления допуском звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fadf-131">Call admission control cmdlets in Lync Server 2013</span></span>](https://docs.microsoft.com/powershell/module/skype/)  


[<span data-ttu-id="5fadf-132">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="5fadf-132">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[<span data-ttu-id="5fadf-133">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="5fadf-133">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[<span data-ttu-id="5fadf-134">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="5fadf-134">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[<span data-ttu-id="5fadf-135">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="5fadf-135">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[<span data-ttu-id="5fadf-136">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="5fadf-136">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

