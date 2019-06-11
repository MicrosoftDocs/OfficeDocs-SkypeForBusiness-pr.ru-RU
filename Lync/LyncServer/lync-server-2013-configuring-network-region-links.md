---
title: 'Lync Server 2013: Настройка ссылок на сетевой регион'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring network region links
ms:assetid: 952bc93e-e6aa-4539-85c7-2b15f14eb382
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182551(v=OCS.15)
ms:contentKeyID: 48184829
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 895c85a80d3e5a7fadee3dccad25f9d89f04028a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-network-region-links-in-lync-server-2013"></a><span data-ttu-id="330b0-102">Настройка ссылок на сетевой регион в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="330b0-102">Configuring network region links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="330b0-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="330b0-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="330b0-104">Вы можете настроить связи между двумя сетевыми областями в рамках управления допуском звонков (CAC).</span><span class="sxs-lookup"><span data-stu-id="330b0-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="330b0-105">Регионы в сети связаны по ГЛОБАЛЬным сетевым подключениям.</span><span class="sxs-lookup"><span data-stu-id="330b0-105">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="330b0-106">С помощью панели управления Lync Server вы можете определить связь между двумя областями сети и задать ограничения пропускной способности для звуковых и видеоподключений между этими регионами.</span><span class="sxs-lookup"><span data-stu-id="330b0-106">You can use the Lync Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span> <span data-ttu-id="330b0-107">Подробнее об удалении ссылки на существующий сетевой регион можно узнать [в разделе Удаление ссылок на области сети в Lync Server 2013](lync-server-2013-deleting-network-region-links.md).</span><span class="sxs-lookup"><span data-stu-id="330b0-107">For details about deleting an existing network region link, see [Deleting network region links in Lync Server 2013](lync-server-2013-deleting-network-region-links.md).</span></span>

<div>

## <a name="to-create-a-network-region-link"></a><span data-ttu-id="330b0-108">Создание ссылки на сетевой регион</span><span class="sxs-lookup"><span data-stu-id="330b0-108">To create a network region link</span></span>

1.  <span data-ttu-id="330b0-109">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="330b0-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="330b0-110">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="330b0-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="330b0-111">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="330b0-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="330b0-112">На панели навигации слева выберите пункт **Настройка сети** , а затем щелкните **ссылку Region (регион**).</span><span class="sxs-lookup"><span data-stu-id="330b0-112">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="330b0-113">На странице " **ссылка на регион** " нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="330b0-113">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="330b0-114">В поле " **ссылка на новый регион**" введите значение из поля **имя** .</span><span class="sxs-lookup"><span data-stu-id="330b0-114">In **New Region Link**, type a value in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="330b0-115">Это значение должно быть уникальным в рамках развертывания Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="330b0-115">This value must be unique within your Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="330b0-116">В раскрывающемся списке **сетевой регион \#1** выберите один из двух областей, которые нужно связать.</span><span class="sxs-lookup"><span data-stu-id="330b0-116">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="330b0-117">В раскрывающемся списке **сетевой регион \#2** выберите другой регион, который нужно связать.</span><span class="sxs-lookup"><span data-stu-id="330b0-117">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="330b0-118">Этот регион должен отличаться от региона, выбранного для сетевого региона \#1.</span><span class="sxs-lookup"><span data-stu-id="330b0-118">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="330b0-119">Необязательно Если вы хотите помещать ограничения на пропускную способность для звуковых и видеозвонков в этих регионах, выберите профиль политики пропускной способности из раскрывающегося списка **политика пропускной способности** .</span><span class="sxs-lookup"><span data-stu-id="330b0-119">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="330b0-120">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="330b0-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-link"></a><span data-ttu-id="330b0-121">Изменение ссылки на сетевой регион</span><span class="sxs-lookup"><span data-stu-id="330b0-121">To modify a network region link</span></span>

1.  <span data-ttu-id="330b0-122">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="330b0-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="330b0-123">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="330b0-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="330b0-124">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="330b0-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="330b0-125">На панели навигации слева выберите пункт **Настройка сети** , а затем щелкните **ссылку Region (регион**).</span><span class="sxs-lookup"><span data-stu-id="330b0-125">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="330b0-126">На странице " **ссылка на регион** " щелкните ссылку на область, которую вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="330b0-126">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="330b0-127">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="330b0-127">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="330b0-128">В **ссылке Изменить регион**можно изменить связанные с ней регионы или профиль политики пропускной способности для этой ссылки.</span><span class="sxs-lookup"><span data-stu-id="330b0-128">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="330b0-129">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="330b0-129">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="330b0-130">См. также</span><span class="sxs-lookup"><span data-stu-id="330b0-130">See Also</span></span>


[<span data-ttu-id="330b0-131">Удаление ссылок на сетевой регион в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="330b0-131">Deleting network region links in Lync Server 2013</span></span>](lync-server-2013-deleting-network-region-links.md)  


[<span data-ttu-id="330b0-132">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="330b0-132">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  
[<span data-ttu-id="330b0-133">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="330b0-133">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  
[<span data-ttu-id="330b0-134">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="330b0-134">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  
[<span data-ttu-id="330b0-135">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="330b0-135">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
