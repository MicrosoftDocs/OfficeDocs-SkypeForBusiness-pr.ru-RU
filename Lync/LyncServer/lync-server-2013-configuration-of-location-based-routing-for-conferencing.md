---
title: 'Lync Server 2013: конфигурация маршрутизации на основе расположения для конференций'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuration of Location-Based Routing for conferencing
ms:assetid: d8c708cc-a1b1-48b1-808c-a64df15f7701
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362846(v=OCS.15)
ms:contentKeyID: 56335088
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 657978ee622713ffd830d4aeb92a05d949287568
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841470"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="93f65-102">Конфигурация маршрутизации на основе расположения для конференций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93f65-102">Configuration of Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93f65-103">_**Тема последнего изменения:** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="93f65-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="93f65-104">Приложение для конференц-связи с маршрутизацией на основе местоположения основывается на настройке маршрутизации на основе расположения в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="93f65-104">The Location-Based Routing Conferencing application relies on the configuration of Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="93f65-105">Основные конфигурации следующие:</span><span class="sxs-lookup"><span data-stu-id="93f65-105">The main configurations are the following:</span></span>

  - <span data-ttu-id="93f65-106">Местоположение участников, присоединяющихся к собранию, определяется на основе их сетевого сайта.</span><span class="sxs-lookup"><span data-stu-id="93f65-106">The location of participants joining a meeting is determined based on their network site.</span></span> <span data-ttu-id="93f65-107">Чтобы обеспечить маршрутизацию на основе местоположения, необходимо определить сайт сети и связанные с ним подсети в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="93f65-107">A network site and its associated network subnets must be defined in Lync Server in order to enforce Location-Based Routing.</span></span>

  - <span data-ttu-id="93f65-108">Для принудительной маршрутизации собраний на основе местоположения участники Lync должны быть включены для маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="93f65-108">To enforce Location-Based Routing of meetings, Lync participants must be enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="93f65-109">Для принудительной маршрутизации конечных точек PSTN, присоединяющихся к собраниям, необходимо настроить для маршрутизации на основе местоположения магистраль SIP.</span><span class="sxs-lookup"><span data-stu-id="93f65-109">To enforce Location-Based Routing of PSTN endpoints joining meetings, the SIP trunk used to connect the PSTN endpoints must be configured for Location-Based Routing.</span></span>

<span data-ttu-id="93f65-110">Дополнительные сведения о развертывании и настройке маршрутизации на основе местоположения в Lync Server 2013 можно найти в разделе Настройка [маршрутизации на основе местоположения](lync-server-2013-configuring-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="93f65-110">For additional information on deploying and configuring Lync Server 2013 Location-Based Routing, please refer Configuring [Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a><span data-ttu-id="93f65-111">Включение приложения для конференц-связи с учетом расположения</span><span class="sxs-lookup"><span data-stu-id="93f65-111">Enabling the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="93f65-112">Приложение по умолчанию для конференц-связи с учетом расположения отключено.</span><span class="sxs-lookup"><span data-stu-id="93f65-112">The Location-Based Routing Conferencing application is disabled by default.</span></span> <span data-ttu-id="93f65-113">Перед включением этого приложения необходимо определить и назначить для него правильное значение приоритета.</span><span class="sxs-lookup"><span data-stu-id="93f65-113">Before enabling this application, you need to determine the right priority to assign for the application.</span></span> <span data-ttu-id="93f65-114">Чтобы определить этот приоритет, выполните в командной консоли Lync Server следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="93f65-114">To determine this priority, run the following cmdlet in Lync Server Management Shell:</span></span>

<span data-ttu-id="93f65-115">Get-Кссервераппликатион-Identity Service: регистратор:\<полное доменное имя пула\></span><span class="sxs-lookup"><span data-stu-id="93f65-115">Get-CsServerApplication -Identity Service:Registrar:\<Pool FQDN\></span></span>

<span data-ttu-id="93f65-116">В этом командлете \<доменное\> имя пула — это пул, в котором должно быть включено приложение для конференц-связи с использованием местоположения.</span><span class="sxs-lookup"><span data-stu-id="93f65-116">In this cmdlet, \<Pool FQDN\> is the pool in which the Location-Based Routing Conferencing application is to be enabled.</span></span>

<span data-ttu-id="93f65-117">Этот командлет вернет список приложений, размещенных на сервере Lync Server, и значение приоритета для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="93f65-117">This cmdlet will return the list of the applications hosted by Lync Server and the priority value for each of them.</span></span> <span data-ttu-id="93f65-118">Приложению для конференц-связи с учетом расположения необходимо назначить значение приоритета, большее, чем приложение "Удкажент", и меньше, чем приложения "Дефаултраутинг", "Ексумраутинг" и "Аутбаундраутинг".</span><span class="sxs-lookup"><span data-stu-id="93f65-118">The Location-Based Routing Conferencing application needs to be assigned a priority value larger than the “UdcAgent” application and smaller than the “DefaultRouting”, “ExumRouting” and “OutboundRouting” applications.</span></span> <span data-ttu-id="93f65-119">Мы рекомендуем назначить приложению для конференц-связи на основе местоположения значение приоритета, равное одной точке выше значения приоритета для приложения "Удкажент".</span><span class="sxs-lookup"><span data-stu-id="93f65-119">We recommend that you assign the Location-Based Routing Conferencing application a priority value that is one point higher than the priority value of the “UdcAgent” application.</span></span>

<span data-ttu-id="93f65-120">Например, если для приложения "Удкажент" установлено значение приоритета "2", в приложении "Дефаултраутинг" значение priority равно "8", а для приложения "Ексумраутинг" установлено значение Priority "9", а для приложения "Аутбаундраутинг" установлено значение приоритета "10". необходимо назначить приложению для конференц-связи на основе местоположения значение приоритета 3.</span><span class="sxs-lookup"><span data-stu-id="93f65-120">For example, if the “UdcAgent” application has a priority value of “2”, the “DefaultRouting” application has a priority value of “8”, the “ExumRouting” application has a priority value of “9” and the “OutboundRouting” application has a priority value of “10” then you should assign the Location-Based Routing Conferencing application a priority value of “3”.</span></span> <span data-ttu-id="93f65-121">В этом случае приоритет приложений будет выстроен в следующем порядке: другие приложения (приоритеты: от 0 до 1), "UdcAgent" (приоритет: 2), приложение для конференций с маршрутизацией на основе расположения (приоритет: 3), другие приложения (приоритеты: от 4 до 8), "DefaultRouting" (приоритет: 9), "ExumRouting" (приоритет: 10) и "OutboundRouting" (приоритет: 11).</span><span class="sxs-lookup"><span data-stu-id="93f65-121">Doing so would place the priority of the applications in the following order: Other applications (Priorities: 0 to 1), “UdcAgent” (Priority: 2), Location-Based Routing Conferencing application (Priority: 3), other applications (Priorities: 4 to 8), “DefaultRouting” (Priority: 9), “ExumRouting” (Priority: 10) and “OutboundRouting” (Priority: 11).</span></span>

<span data-ttu-id="93f65-122">После того как вы найдете правильное значение приоритета для приложения для конференц-связи с учетом расположения, введите следующий командлет для всех интерфейсных пулов и серверов Standard Edition, для которых включены пользователи для маршрутизации на основе местоположения:</span><span class="sxs-lookup"><span data-stu-id="93f65-122">After you find the correct priority value for the Location-Based Routing Conferencing application, type the following cmdlet for each Front-End pool or Standard Edition Server that homes users enabled for Location-Based Routing:</span></span>

<span data-ttu-id="93f65-123">New-Кссервераппликатион-Identity Service: регистратор:\<FQDN (\>полное доменное \<имя пула\> /лбраутинг) с поддержкой приоритетов приложений $true — критическое $true-URIhttp://www.microsoft.com/LCS/LBRouting</span><span class="sxs-lookup"><span data-stu-id="93f65-123">New-CsServerApplication -Identity Service:Registrar:\<Pool FQDN\>/LBRouting -Priority \<Application Priority\> -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting</span></span>

<span data-ttu-id="93f65-124">Например:</span><span class="sxs-lookup"><span data-stu-id="93f65-124">For example:</span></span>

<span data-ttu-id="93f65-125">Служба New-Кссервераппликатион-Identity:регистрар:LS2013CU2LBRPool. contoso. com/Лбраутинг-Priority $true — критический $true-URIhttp://www.microsoft.com/LCS/LBRouting</span><span class="sxs-lookup"><span data-stu-id="93f65-125">New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting</span></span>

<span data-ttu-id="93f65-126">После использования этого командлета перезапустите все серверы переднего плана в пуле или стандартные серверы выпусков, для которых включено приложение для Конференции с маршрутизацией на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="93f65-126">After using this cmdlet, restart all Front End servers in the pool or the Standard Edition Servers where the Location-Based Routing Conferencing application has been enabled.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="93f65-127">Принудительная маршрутизация на основе местоположения для конференций или консултативе передач не будет применена, пока не будут перезапускаются все серверы переднего плана в соответствующих пулах или на серверах стандартных выпусков.</span><span class="sxs-lookup"><span data-stu-id="93f65-127">Location-Based Routing enforcements to conferences or consultative transfers won’t be enforced until all the Front End Servers in the applicable pools or the Standard Edition Servers are restarted.</span></span>



</div>

<span data-ttu-id="93f65-128">После того как приложение для конференц-связи с учетом расположения успешно включено и все применимые серверы Lync будут перезапущены, все конференции, организованные пользователями Lync, включенные для маршрутизации на основе местоположения, отслеживаются для предотвращения бесплатных вызовов по коммутируемой телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="93f65-128">Once the Location-Based Routing Conferencing application has been successfully enabled and all applicable Lync servers have been restarted, all conferences organized by Lync users enabled for Location-Based Routing will be monitored to prevent PSTN toll bypass</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

