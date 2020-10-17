---
title: 'Lync Server 2013: Настройка маршрутов голосовой связи для исходящих вызовов'
description: 'Lync Server 2013: Настройка маршрутов голосовой связи для исходящих вызовов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice routes for outbound calls
ms:assetid: 3c182cdd-7a4a-4a9d-bdac-4199f0abd947
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425890(v=OCS.15)
ms:contentKeyID: 48183875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2dd0d712295ecdd0e9a517330abcff36021e996d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542215"
---
# <a name="configuring-voice-routes-for-outbound-calls-in-lync-server-2013"></a><span data-ttu-id="3312c-103">Настройка маршрутов голосовой связи для исходящих вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3312c-103">Configuring voice routes for outbound calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3312c-104">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3312c-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3312c-105">Маршрут голосовой связи Lync Server 2013 связывает номера телефонов назначения с одним или несколькими шлюзами телефонной сети общего пользования (PSTN) или магистрали SIP, а также с одной или несколькими записями использования PSTN.</span><span class="sxs-lookup"><span data-stu-id="3312c-105">A Lync Server 2013 voice route associates destination phone numbers with one or more public switched telephone network (PSTN) gateways or SIP trunks and one or more PSTN usage records.</span></span>

<span data-ttu-id="3312c-106">**Просмотр маршрутов голосовой связи с помощью панели управления Lync Server**</span><span class="sxs-lookup"><span data-stu-id="3312c-106">**To view voice routes by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="3312c-107">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3312c-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3312c-108">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3312c-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="3312c-109">Щелкните **Маршрутизация голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="3312c-109">Click **Voice Routing**.</span></span>

3.  <span data-ttu-id="3312c-110">Щелкните **Маршрут**.</span><span class="sxs-lookup"><span data-stu-id="3312c-110">Click **Route**.</span></span>

4.  <span data-ttu-id="3312c-p102">Дважды щелкните маршрут голосовой связи для просмотра дополнительных свойств в списке маршрутов голосовой связи или выберите маршрут и щелкните пункт **Изменить**. Затем щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="3312c-p102">Double-click a voice route to view additional properties from the list of voice routes, or select the route and click **Edit**. Then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3312c-113">Одновременно можно просматривать подробные сведения только по одному маршруту.</span><span class="sxs-lookup"><span data-stu-id="3312c-113">You can only view detailed information for a single route at a time.</span></span>

    
    </div>

<span data-ttu-id="3312c-114">**Просмотр маршрутов голосовой связи с помощью Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="3312c-114">**To view voice routes by using Windows PowerShell**</span></span>

  - <span data-ttu-id="3312c-115">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="3312c-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="3312c-116">Маршруты голосовой связи можно просмотреть с помощью Windows PowerShell и командлета **Get – ксвоицерауте** .</span><span class="sxs-lookup"><span data-stu-id="3312c-116">Voice routes can be viewed by using Windows PowerShell and the **Get-CsVoiceRoute** cmdlet.</span></span> <span data-ttu-id="3312c-117">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3312c-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3312c-118">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="3312c-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="3312c-119">Чтобы просмотреть сведения обо всех маршрутах голосовой связи, введите следующую команду в командной консоли Lync Server, а затем нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="3312c-119">To view information about all of your voice routes, type the following command in the Lync Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsVoiceRoute
    
    <span data-ttu-id="3312c-120">Это приведет к возврату приблизительно такой информации:</span><span class="sxs-lookup"><span data-stu-id="3312c-120">That will return information similar to this:</span></span>
    
        Identity          : global
        Priority          : -1
        Description       :
        NumberPattern     : ^(\+1[0-9]{10})$
        PstnUsages        : {}
        PstnGatewayList   : {}
        Name              : global
        SuppressCallerId  :
        AlternateCallerId :

<div>


> [!NOTE]  
> <span data-ttu-id="3312c-121">Дополнительные сведения см в документации по планированию <A href="lync-server-2013-voice-routes.md">в Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="3312c-121">For details, see <A href="lync-server-2013-voice-routes.md">Voice routes in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3312c-122">Содержание</span><span class="sxs-lookup"><span data-stu-id="3312c-122">In This Section</span></span>

  - [<span data-ttu-id="3312c-123">Создание маршрута голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3312c-123">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)

  - [<span data-ttu-id="3312c-124">Изменение маршрута голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3312c-124">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3312c-125">См. также</span><span class="sxs-lookup"><span data-stu-id="3312c-125">See Also</span></span>


[<span data-ttu-id="3312c-126">Управление маршрутизацией голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3312c-126">Managing voice routing in Lync Server 2013</span></span>](lync-server-2013-managing-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

