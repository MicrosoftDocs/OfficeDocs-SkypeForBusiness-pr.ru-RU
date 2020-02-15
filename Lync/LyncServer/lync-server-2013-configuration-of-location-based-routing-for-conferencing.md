---
title: 'Lync Server 2013: Настройка маршрутизации на основе расположения для конференц-связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration of Location-Based Routing for conferencing
ms:assetid: d8c708cc-a1b1-48b1-808c-a64df15f7701
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362846(v=OCS.15)
ms:contentKeyID: 56335088
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a959addbcd98e04d336ba380676399dbff2f586b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040788"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="7e1ad-102">Настройка маршрутизации на основе расположения для конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e1ad-102">Configuration of Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e1ad-103">_**Последнее изменение темы:** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="7e1ad-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="7e1ad-104">Приложение для конференц-связи с маршрутизацией на основе расположения использует конфигурацию маршрутизации на основе расположения Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7e1ad-104">The Location-Based Routing Conferencing application relies on the configuration of Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="7e1ad-105">Ниже приведены основные конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7e1ad-105">The main configurations are the following:</span></span>

  - <span data-ttu-id="7e1ad-106">Расположение участников, присоединяющихся к собранию, определяется на основе их сетевого сайта.</span><span class="sxs-lookup"><span data-stu-id="7e1ad-106">The location of participants joining a meeting is determined based on their network site.</span></span> <span data-ttu-id="7e1ad-107">Сетевой сайт и связанные с ним подсети должны быть определены в Lync Server, чтобы обеспечить маршрутизацию на основе расположения.</span><span class="sxs-lookup"><span data-stu-id="7e1ad-107">A network site and its associated network subnets must be defined in Lync Server in order to enforce Location-Based Routing.</span></span>

  - <span data-ttu-id="7e1ad-108">Для принудительной маршрутизации собраний на основе расположения для маршрутизации на основе расположения должны быть включены участники Lync.</span><span class="sxs-lookup"><span data-stu-id="7e1ad-108">To enforce Location-Based Routing of meetings, Lync participants must be enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="7e1ad-109">Для принудительной маршрутизации конечных точек PSTN с присоединением к собраниям необходимо настроить маршрутизацию на основе расположения с помощью магистральной линии SIP, используемой для подключения конечных точек PSTN.</span><span class="sxs-lookup"><span data-stu-id="7e1ad-109">To enforce Location-Based Routing of PSTN endpoints joining meetings, the SIP trunk used to connect the PSTN endpoints must be configured for Location-Based Routing.</span></span>

<span data-ttu-id="7e1ad-110">Для получения дополнительных сведений о развертывании и настройке маршрутизации на основе расположения Lync Server 2013, обратитесь к разделу Настройка [маршрутизации на основе расположения](lync-server-2013-configuring-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="7e1ad-110">For additional information on deploying and configuring Lync Server 2013 Location-Based Routing, please refer Configuring [Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a><span data-ttu-id="7e1ad-111">Включение приложения для конференц-связи с маршрутизацией на основе расположения</span><span class="sxs-lookup"><span data-stu-id="7e1ad-111">Enabling the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="7e1ad-112">По умолчанию приложение для конференц-связи с маршрутизацией на основе расположения отключено.</span><span class="sxs-lookup"><span data-stu-id="7e1ad-112">The Location-Based Routing Conferencing application is disabled by default.</span></span> <span data-ttu-id="7e1ad-113">Перед включением этого приложения необходимо определить правильный приоритет, назначаемый приложению.</span><span class="sxs-lookup"><span data-stu-id="7e1ad-113">Before enabling this application, you need to determine the right priority to assign for the application.</span></span> <span data-ttu-id="7e1ad-114">Чтобы определить этот приоритет, выполните следующий командлет в командной консоли Lync Server:</span><span class="sxs-lookup"><span data-stu-id="7e1ad-114">To determine this priority, run the following cmdlet in Lync Server Management Shell:</span></span>

<span data-ttu-id="7e1ad-115">Get – CsServerApplication — Identity Service: регистратор:\<полное доменное имя пула\></span><span class="sxs-lookup"><span data-stu-id="7e1ad-115">Get-CsServerApplication -Identity Service:Registrar:\<Pool FQDN\></span></span>

<span data-ttu-id="7e1ad-116">В этом командлете \<полное доменное имя\> пула — это пул, в котором необходимо включить приложение для конференц-связи с маршрутизацией на основе расположения.</span><span class="sxs-lookup"><span data-stu-id="7e1ad-116">In this cmdlet, \<Pool FQDN\> is the pool in which the Location-Based Routing Conferencing application is to be enabled.</span></span>

<span data-ttu-id="7e1ad-117">Этот командлет возвращает список приложений, размещенных в Lync Server, и значение приоритета для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="7e1ad-117">This cmdlet will return the list of the applications hosted by Lync Server and the priority value for each of them.</span></span> <span data-ttu-id="7e1ad-118">Для приложения для конференц-связи с маршрутизацией на основе расположения необходимо назначить значение приоритета, превышающее приложение "Удкажент" и меньше, чем приложения "Дефаултраутинг", "ExumRouting" и "Аутбаундраутинг".</span><span class="sxs-lookup"><span data-stu-id="7e1ad-118">The Location-Based Routing Conferencing application needs to be assigned a priority value larger than the “UdcAgent” application and smaller than the “DefaultRouting”, “ExumRouting” and “OutboundRouting” applications.</span></span> <span data-ttu-id="7e1ad-119">Рекомендуется назначить приложению для конференц-связи с маршрутизацией на основе расположения значение приоритета на одну точку выше, чем значение приоритета приложения "Удкажент".</span><span class="sxs-lookup"><span data-stu-id="7e1ad-119">We recommend that you assign the Location-Based Routing Conferencing application a priority value that is one point higher than the priority value of the “UdcAgent” application.</span></span>

<span data-ttu-id="7e1ad-120">Например, если для приложения "Удкажент" задано значение приоритета "2", то приложение "Дефаултраутинг" имеет значение Priority "8", для приложения "ExumRouting" задано значение приоритета "9", а для приложения "Аутбаундраутинг" значение priority равно "10". необходимо назначить приложению конференц-связи с маршрутизацией на основе расположения значение приоритета "3".</span><span class="sxs-lookup"><span data-stu-id="7e1ad-120">For example, if the “UdcAgent” application has a priority value of “2”, the “DefaultRouting” application has a priority value of “8”, the “ExumRouting” application has a priority value of “9” and the “OutboundRouting” application has a priority value of “10” then you should assign the Location-Based Routing Conferencing application a priority value of “3”.</span></span> <span data-ttu-id="7e1ad-121">Это приведет к порядку приоритетов приложений в следующем порядке: другие приложения (приоритеты: от 0 до 1), "Удкажент" (приоритет: 2), приложение для конференц-связи с маршрутизацией (приоритет: 3), другие приложения (приоритеты: от 4 до 8), " Дефаултраутинг "(приоритет: 9)," ExumRouting "(приоритет: 10) и" Аутбаундраутинг "(приоритет: 11).</span><span class="sxs-lookup"><span data-stu-id="7e1ad-121">Doing so would place the priority of the applications in the following order: Other applications (Priorities: 0 to 1), “UdcAgent” (Priority: 2), Location-Based Routing Conferencing application (Priority: 3), other applications (Priorities: 4 to 8), “DefaultRouting” (Priority: 9), “ExumRouting” (Priority: 10) and “OutboundRouting” (Priority: 11).</span></span>

<span data-ttu-id="7e1ad-122">После того как вы найдете правильное значение приоритета для приложения для конференц-связи с маршрутизацией на основе расположения, введите следующий командлет для каждого интерфейсного пула или сервера Standard Edition, для которых пользователи жилых подключений включены для маршрутизации на основе расположения:</span><span class="sxs-lookup"><span data-stu-id="7e1ad-122">After you find the correct priority value for the Location-Based Routing Conferencing application, type the following cmdlet for each Front-End pool or Standard Edition Server that homes users enabled for Location-Based Routing:</span></span>

<span data-ttu-id="7e1ad-123">New — CsServerApplication — Identity Service: регистратор:\<полное доменное имя\>пула \</Лбраутинг приоритет\> приложения с поддержкой $true критически важный $true – URIhttp://www.microsoft.com/LCS/LBRouting</span><span class="sxs-lookup"><span data-stu-id="7e1ad-123">New-CsServerApplication -Identity Service:Registrar:\<Pool FQDN\>/LBRouting -Priority \<Application Priority\> -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting</span></span>

<span data-ttu-id="7e1ad-124">Пример:</span><span class="sxs-lookup"><span data-stu-id="7e1ad-124">For example:</span></span>

<span data-ttu-id="7e1ad-125">New-CsServerApplication-Identity Service:регистрар:LS2013CU2LBRPool. contoso. com/Лбраутинг-Priority 3-enabled $true-Critical $true-URIhttp://www.microsoft.com/LCS/LBRouting</span><span class="sxs-lookup"><span data-stu-id="7e1ad-125">New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting</span></span>

<span data-ttu-id="7e1ad-126">После использования этого командлета перезапустите все серверы переднего плана в пуле или серверы Standard Edition, на которых включено приложение для конференц-связи с маршрутизацией на основе расположения.</span><span class="sxs-lookup"><span data-stu-id="7e1ad-126">After using this cmdlet, restart all Front End servers in the pool or the Standard Edition Servers where the Location-Based Routing Conferencing application has been enabled.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7e1ad-127">Принудительная маршрутизация на основе расположения для конференций или передач Консультативного не будет применяться, пока не будут перезапущены все серверы переднего плана в соответствующих пулах или серверы Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="7e1ad-127">Location-Based Routing enforcements to conferences or consultative transfers won’t be enforced until all the Front End Servers in the applicable pools or the Standard Edition Servers are restarted.</span></span>



</div>

<span data-ttu-id="7e1ad-128">Если приложение для конференц-связи с маршрутизацией на основе расположения успешно включено и все соответствующие серверы Lync Server были перезапущены, все конференции, организованные пользователями Lync, для которых включена маршрутизация на основе расположения, будут отслеживаться, чтобы предотвратить обход бесплатных звонков по сети PSTN.</span><span class="sxs-lookup"><span data-stu-id="7e1ad-128">Once the Location-Based Routing Conferencing application has been successfully enabled and all applicable Lync servers have been restarted, all conferences organized by Lync users enabled for Location-Based Routing will be monitored to prevent PSTN toll bypass</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

