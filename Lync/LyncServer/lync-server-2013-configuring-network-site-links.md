---
title: 'Lync Server 2013: Настройка связей между сетевыми сайтами'
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
ms.openlocfilehash: 33461781f0392d0e6e4fbfa21bdde8948e7a9a1e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532586"
---
# <a name="configuring-network-site-links-in-lync-server-2013"></a><span data-ttu-id="d7f4a-102">Настройка связей между сетевыми сайтами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7f4a-102">Configuring network site links in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7f4a-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d7f4a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d7f4a-104">В конфигурации контроля допуска звонков можно создать сетевые межузловые политики, которые определяют ограничения пропускной способности между связанными напрямую узлами.</span><span class="sxs-lookup"><span data-stu-id="d7f4a-104">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="d7f4a-105">Когда сетевые узлы совместно используют прямую связь, ограничения для аудио- и видеосвязи можно задавать между этими двумя узлами.</span><span class="sxs-lookup"><span data-stu-id="d7f4a-105">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="d7f4a-106">Вы не можете использовать панель управления Lync Server для настройки политик сетевых сайтов, это можно сделать только с помощью командлетов из командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d7f4a-106">You cannot use the Lync Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Lync Server Management Shell.</span></span> <span data-ttu-id="d7f4a-107">С помощью командной консоли Lync Server можно создавать, изменять и удалять сетевые связи сайтов (также называемые сетевой политикой межсайтовой связи).</span><span class="sxs-lookup"><span data-stu-id="d7f4a-107">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Lync Server Management Shell.</span></span>

<div>

## <a name="to-create-a-network-site-link"></a><span data-ttu-id="d7f4a-108">Создание связи между сетевыми узлами</span><span class="sxs-lookup"><span data-stu-id="d7f4a-108">To create a network site link</span></span>

1.  <span data-ttu-id="d7f4a-109">Выполните вход на компьютер, на котором установлена командная консоль Lync Server, в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="d7f4a-109">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="d7f4a-110">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d7f4a-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d7f4a-111">В Введите в командной строке следующую команду, подставив значения, подходящие для вашей конфигурации:</span><span class="sxs-lookup"><span data-stu-id="d7f4a-111">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="d7f4a-112">В этом примере создается сетевое подключение к сетевому сайту с именем Рино \_ Портленде, которое задает ограничения пропускной способности между узлами Рино и сети Портленде.</span><span class="sxs-lookup"><span data-stu-id="d7f4a-112">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="d7f4a-113">Перед выполнением этой команды уже должны существовать эти сетевые узлы и профиль политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="d7f4a-113">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="d7f4a-114">Подробное описание параметров приведено в разделе [New – CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) в документации по консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d7f4a-114">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span> <span data-ttu-id="d7f4a-115">Чтобы получить список профилей политик пропускной способности, которые можно применять к связи между сетевыми узлами, вызовите командлет **Get-CsNetworkBandwidthPolicyProfile**.</span><span class="sxs-lookup"><span data-stu-id="d7f4a-115">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="d7f4a-116">Дополнительные сведения см. в статье [Get – CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) в документации по консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d7f4a-116">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-modify-a-network-site-link"></a><span data-ttu-id="d7f4a-117">Изменение связи между сетевыми узлами</span><span class="sxs-lookup"><span data-stu-id="d7f4a-117">To modify a network site link</span></span>

1.  <span data-ttu-id="d7f4a-118">Выполните вход на компьютер, на котором установлена командная консоль Lync Server, в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="d7f4a-118">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="d7f4a-119">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d7f4a-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d7f4a-120">Для изменения свойств конкретной связи между сетевыми узлами используется командлет **Set-CsNetworkInterSitePolicy**.</span><span class="sxs-lookup"><span data-stu-id="d7f4a-120">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="d7f4a-121">Можно изменять каждый из связанных узлов (или оба этих узла), а также профиль политики пропускной способности, привязанный к этой связи.</span><span class="sxs-lookup"><span data-stu-id="d7f4a-121">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="d7f4a-122">Ниже приведен пример изменения профиля политики пропускной способности для связи сайтов с именем Рино \_ Портленде:</span><span class="sxs-lookup"><span data-stu-id="d7f4a-122">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="d7f4a-123">Подробное описание параметров приведено в разделе [Set – CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) в документации по консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d7f4a-123">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-delete-a-network-site-link"></a><span data-ttu-id="d7f4a-124">Удаление связи между сетевыми узлами</span><span class="sxs-lookup"><span data-stu-id="d7f4a-124">To delete a network site link</span></span>

1.  <span data-ttu-id="d7f4a-125">Выполните вход на компьютер, на котором установлена командная консоль Lync Server, в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="d7f4a-125">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="d7f4a-126">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d7f4a-126">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d7f4a-127">Для удаления связи между сетевыми узлами используется командлет **Remove-CsNetworkInterSitePolicy**.</span><span class="sxs-lookup"><span data-stu-id="d7f4a-127">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="d7f4a-128">В следующем примере удаляется \_ ссылка на сетевой сайт Рино в Портленде:</span><span class="sxs-lookup"><span data-stu-id="d7f4a-128">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="d7f4a-129">Подробное описание параметров приведено в разделе [Remove – CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) в документации по консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d7f4a-129">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d7f4a-130">См. также</span><span class="sxs-lookup"><span data-stu-id="d7f4a-130">See Also</span></span>


[<span data-ttu-id="d7f4a-131">Командлеты контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7f4a-131">Call admission control cmdlets in Lync Server 2013</span></span>](https://docs.microsoft.com/powershell/module/skype/)  


[<span data-ttu-id="d7f4a-132">New — CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="d7f4a-132">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[<span data-ttu-id="d7f4a-133">Set — CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="d7f4a-133">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[<span data-ttu-id="d7f4a-134">Remove — CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="d7f4a-134">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[<span data-ttu-id="d7f4a-135">Get — CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="d7f4a-135">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[<span data-ttu-id="d7f4a-136">Get — CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="d7f4a-136">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

