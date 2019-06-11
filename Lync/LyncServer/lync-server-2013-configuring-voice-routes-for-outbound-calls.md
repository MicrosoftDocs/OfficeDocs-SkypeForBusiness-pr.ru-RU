---
title: 'Lync Server 2013: настройка маршрутов голосовой связи для исходящих звонков'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring voice routes for outbound calls
ms:assetid: 3c182cdd-7a4a-4a9d-bdac-4199f0abd947
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425890(v=OCS.15)
ms:contentKeyID: 48183875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e91525f5d35110560b28059f774be8d2cb5df6d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-routes-for-outbound-calls-in-lync-server-2013"></a><span data-ttu-id="c59ca-102">Настройка маршрутов голосовой связи для исходящих звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c59ca-102">Configuring voice routes for outbound calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c59ca-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c59ca-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c59ca-104">Голосовой маршрут Lync Server 2013 связывает конечные телефонные номера с помощью одного или нескольких шлюзов или магистральных каналов коммутируемой телефонной сети, а также одной или нескольких записей об использовании КТСОП.</span><span class="sxs-lookup"><span data-stu-id="c59ca-104">A Lync Server 2013 voice route associates destination phone numbers with one or more public switched telephone network (PSTN) gateways or SIP trunks and one or more PSTN usage records.</span></span>

<span data-ttu-id="c59ca-105">**Просмотр маршрутов голосовой связи с помощью панели управления Lync Server**</span><span class="sxs-lookup"><span data-stu-id="c59ca-105">**To view voice routes by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="c59ca-106">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c59ca-106">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c59ca-107">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c59ca-107">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="c59ca-108">Нажмите кнопку **Маршрутизация голоса**.</span><span class="sxs-lookup"><span data-stu-id="c59ca-108">Click **Voice Routing**.</span></span>

3.  <span data-ttu-id="c59ca-109">Щелкните **Маршрут**.</span><span class="sxs-lookup"><span data-stu-id="c59ca-109">Click **Route**.</span></span>

4.  <span data-ttu-id="c59ca-110">Дважды щелкните голосовой маршрут для просмотра дополнительных свойств из списка голосовых маршрутов или выберите маршрут и нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="c59ca-110">Double-click a voice route to view additional properties from the list of voice routes, or select the route and click **Edit**.</span></span> <span data-ttu-id="c59ca-111">Затем нажмите кнопку **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="c59ca-111">Then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c59ca-112">Вы можете просматривать только подробные сведения по одному маршруту за раз.</span><span class="sxs-lookup"><span data-stu-id="c59ca-112">You can only view detailed information for a single route at a time.</span></span>

    
    </div>

<span data-ttu-id="c59ca-113">**Просмотр маршрутов голосовой связи с помощью Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c59ca-113">**To view voice routes by using Windows PowerShell**</span></span>

  - <span data-ttu-id="c59ca-114">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c59ca-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="c59ca-115">Голосовые маршруты можно просматривать с помощью Windows PowerShell и командлета **Get-ксвоицерауте** .</span><span class="sxs-lookup"><span data-stu-id="c59ca-115">Voice routes can be viewed by using Windows PowerShell and the **Get-CsVoiceRoute** cmdlet.</span></span> <span data-ttu-id="c59ca-116">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c59ca-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c59ca-117">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c59ca-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="c59ca-118">Чтобы просмотреть сведения о всех голосовых маршрутах, введите следующую команду в командной консоли Lync Server Management Shell и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="c59ca-118">To view information about all of your voice routes, type the following command in the Lync Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsVoiceRoute
    
    <span data-ttu-id="c59ca-119">Команда возвращает примерно следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="c59ca-119">That will return information similar to this:</span></span>
    
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
> <span data-ttu-id="c59ca-120">Подробности можно найти <A href="lync-server-2013-voice-routes.md">в разделе маршруты к голосовой связи в Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="c59ca-120">For details, see <A href="lync-server-2013-voice-routes.md">Voice routes in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c59ca-121">Содержание</span><span class="sxs-lookup"><span data-stu-id="c59ca-121">In This Section</span></span>

  - [<span data-ttu-id="c59ca-122">Создание голосового маршрута в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c59ca-122">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)

  - [<span data-ttu-id="c59ca-123">Изменение маршрута голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c59ca-123">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c59ca-124">См. также</span><span class="sxs-lookup"><span data-stu-id="c59ca-124">See Also</span></span>


[<span data-ttu-id="c59ca-125">Управление маршрутизацией голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c59ca-125">Managing voice routing in Lync Server 2013</span></span>](lync-server-2013-managing-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

