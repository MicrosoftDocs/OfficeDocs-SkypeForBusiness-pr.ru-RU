---
title: 'Lync Server 2013: Настройка маршрутов голосовой связи для исходящих вызовов'
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
ms.openlocfilehash: 7c5c74a11adfb3785196352f3c03772028e73ec9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045851"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-routes-for-outbound-calls-in-lync-server-2013"></a><span data-ttu-id="c01a4-102">Настройка маршрутов голосовой связи для исходящих вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c01a4-102">Configuring voice routes for outbound calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c01a4-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c01a4-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c01a4-104">Маршрут голосовой связи Lync Server 2013 связывает номера телефонов назначения с одним или несколькими шлюзами телефонной сети общего пользования (PSTN) или магистрали SIP, а также с одной или несколькими записями использования PSTN.</span><span class="sxs-lookup"><span data-stu-id="c01a4-104">A Lync Server 2013 voice route associates destination phone numbers with one or more public switched telephone network (PSTN) gateways or SIP trunks and one or more PSTN usage records.</span></span>

<span data-ttu-id="c01a4-105">**Просмотр маршрутов голосовой связи с помощью панели управления Lync Server**</span><span class="sxs-lookup"><span data-stu-id="c01a4-105">**To view voice routes by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="c01a4-106">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c01a4-106">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c01a4-107">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c01a4-107">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="c01a4-108">Щелкните **Маршрутизация голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="c01a4-108">Click **Voice Routing**.</span></span>

3.  <span data-ttu-id="c01a4-109">Щелкните **Маршрут**.</span><span class="sxs-lookup"><span data-stu-id="c01a4-109">Click **Route**.</span></span>

4.  <span data-ttu-id="c01a4-p102">Дважды щелкните маршрут голосовой связи для просмотра дополнительных свойств в списке маршрутов голосовой связи или выберите маршрут и щелкните пункт **Изменить**. Затем щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="c01a4-p102">Double-click a voice route to view additional properties from the list of voice routes, or select the route and click **Edit**. Then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c01a4-112">Одновременно можно просматривать подробные сведения только по одному маршруту.</span><span class="sxs-lookup"><span data-stu-id="c01a4-112">You can only view detailed information for a single route at a time.</span></span>

    
    </div>

<span data-ttu-id="c01a4-113">**Просмотр маршрутов голосовой связи с помощью Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c01a4-113">**To view voice routes by using Windows PowerShell**</span></span>

  - <span data-ttu-id="c01a4-114">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="c01a4-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="c01a4-115">Маршруты голосовой связи можно просмотреть с помощью Windows PowerShell и командлета **Get – ксвоицерауте** .</span><span class="sxs-lookup"><span data-stu-id="c01a4-115">Voice routes can be viewed by using Windows PowerShell and the **Get-CsVoiceRoute** cmdlet.</span></span> <span data-ttu-id="c01a4-116">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c01a4-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c01a4-117">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="c01a4-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="c01a4-118">Чтобы просмотреть сведения обо всех маршрутах голосовой связи, введите следующую команду в командной консоли Lync Server, а затем нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="c01a4-118">To view information about all of your voice routes, type the following command in the Lync Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsVoiceRoute
    
    <span data-ttu-id="c01a4-119">Это приведет к возврату приблизительно такой информации:</span><span class="sxs-lookup"><span data-stu-id="c01a4-119">That will return information similar to this:</span></span>
    
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
> <span data-ttu-id="c01a4-120">Дополнительные сведения см в документации по планированию <A href="lync-server-2013-voice-routes.md">в Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="c01a4-120">For details, see <A href="lync-server-2013-voice-routes.md">Voice routes in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c01a4-121">Содержание</span><span class="sxs-lookup"><span data-stu-id="c01a4-121">In This Section</span></span>

  - [<span data-ttu-id="c01a4-122">Создание маршрута голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c01a4-122">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)

  - [<span data-ttu-id="c01a4-123">Изменение маршрута голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c01a4-123">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c01a4-124">См. также</span><span class="sxs-lookup"><span data-stu-id="c01a4-124">See Also</span></span>


[<span data-ttu-id="c01a4-125">Управление маршрутизацией голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c01a4-125">Managing voice routing in Lync Server 2013</span></span>](lync-server-2013-managing-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

