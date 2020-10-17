---
title: 'Lync Server 2013: Настройка связей между сетевыми областями'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring network region links
ms:assetid: 952bc93e-e6aa-4539-85c7-2b15f14eb382
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182551(v=OCS.15)
ms:contentKeyID: 48184829
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 363baeb3065b04dc936b69fff34f2314726f495a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526936"
---
# <a name="configuring-network-region-links-in-lync-server-2013"></a><span data-ttu-id="f3434-102">Настройка связей между областями сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3434-102">Configuring network region links in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3434-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f3434-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f3434-104">Вы можете настроить канал между двумя областями сети как часть контроля допуска звонков (CAC).</span><span class="sxs-lookup"><span data-stu-id="f3434-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="f3434-105">Регионы в сети связываются с помощью физического подключения глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="f3434-105">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="f3434-106">С помощью панели управления Lync Server вы можете определить ссылку между двумя областями сети и установить ограничения пропускной способности для звуковых и видеоподключений между этими областями.</span><span class="sxs-lookup"><span data-stu-id="f3434-106">You can use the Lync Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span> <span data-ttu-id="f3434-107">Дополнительные сведения об удалении существующей связи между областями сети содержатся [в статье Удаление связей между областями сети в Lync Server 2013](lync-server-2013-deleting-network-region-links.md).</span><span class="sxs-lookup"><span data-stu-id="f3434-107">For details about deleting an existing network region link, see [Deleting network region links in Lync Server 2013](lync-server-2013-deleting-network-region-links.md).</span></span>

<div>

## <a name="to-create-a-network-region-link"></a><span data-ttu-id="f3434-108">Создание связи сетевой области</span><span class="sxs-lookup"><span data-stu-id="f3434-108">To create a network region link</span></span>

1.  <span data-ttu-id="f3434-109">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="f3434-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f3434-110">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f3434-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f3434-111">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f3434-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f3434-112">В левой панели навигации щелкните **Конфигурация сети**, а затем щелкните **Связь между областями**.</span><span class="sxs-lookup"><span data-stu-id="f3434-112">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="f3434-113">На странице **Связь между областями** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="f3434-113">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="f3434-114">В окне **Создание связи между областями** введите значение в поле **Имя**.</span><span class="sxs-lookup"><span data-stu-id="f3434-114">In **New Region Link**, type a value in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f3434-115">Это значение должно быть уникальным в рамках развертывания Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f3434-115">This value must be unique within your Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="f3434-116">В раскрывающемся списке **область сети \# 1** выберите одну из двух областей, которые необходимо связать.</span><span class="sxs-lookup"><span data-stu-id="f3434-116">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="f3434-117">В раскрывающемся списке **область сети \# 2** выберите другой регион, который необходимо связать.</span><span class="sxs-lookup"><span data-stu-id="f3434-117">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="f3434-118">Этот регион должен отличаться от региона, выбранного для области сети \# 1.</span><span class="sxs-lookup"><span data-stu-id="f3434-118">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="f3434-119">(Необязательно) Если нужно наложить ограничения полосы пропускания на аудио- или видеовызовы между этими областями, выберите профиль политики в раскрывающемся списке **Политика полосы пропускания**.</span><span class="sxs-lookup"><span data-stu-id="f3434-119">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="f3434-120">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f3434-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-link"></a><span data-ttu-id="f3434-121">Изменение связи сетевой области</span><span class="sxs-lookup"><span data-stu-id="f3434-121">To modify a network region link</span></span>

1.  <span data-ttu-id="f3434-122">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="f3434-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f3434-123">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f3434-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f3434-124">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f3434-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f3434-125">В левой панели навигации щелкните **Конфигурация сети**, а затем щелкните **Связь между областями**.</span><span class="sxs-lookup"><span data-stu-id="f3434-125">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="f3434-126">На странице **Связь между областями** щелкните связь, которую нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="f3434-126">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="f3434-127">В меню **Правка** выберите команду **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="f3434-127">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="f3434-128">В окне **Изменение связи между областями** вы можете изменить связанные области или профиль политики пропускной способности для этой связи.</span><span class="sxs-lookup"><span data-stu-id="f3434-128">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="f3434-129">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f3434-129">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f3434-130">См. также</span><span class="sxs-lookup"><span data-stu-id="f3434-130">See Also</span></span>


[<span data-ttu-id="f3434-131">Удаление связей между областями сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3434-131">Deleting network region links in Lync Server 2013</span></span>](lync-server-2013-deleting-network-region-links.md)  


[<span data-ttu-id="f3434-132">New — Кснетворкрегионлинк</span><span class="sxs-lookup"><span data-stu-id="f3434-132">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  
[<span data-ttu-id="f3434-133">Set — Кснетворкрегионлинк</span><span class="sxs-lookup"><span data-stu-id="f3434-133">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  
[<span data-ttu-id="f3434-134">Remove — Кснетворкрегионлинк</span><span class="sxs-lookup"><span data-stu-id="f3434-134">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  
[<span data-ttu-id="f3434-135">Get — Кснетворкрегионлинк</span><span class="sxs-lookup"><span data-stu-id="f3434-135">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
