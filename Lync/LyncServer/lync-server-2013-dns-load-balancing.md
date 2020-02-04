---
title: 'Lync Server 2013: Балансировка нагрузки DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS load balancing
ms:assetid: 7ed0ed20-33ad-4253-926d-21d392590ae7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398634(v=OCS.15)
ms:contentKeyID: 48184625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30d3b88ac66ad7dc6dd3216d941f4a99fc2feedd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-load-balancing-in-lync-server-2013"></a><span data-ttu-id="96a62-102">Балансировка нагрузки DNS в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96a62-102">DNS load balancing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96a62-103">_**Тема последнего изменения:** 2014-01-15_</span><span class="sxs-lookup"><span data-stu-id="96a62-103">_**Topic Last Modified:** 2014-01-15_</span></span>

<span data-ttu-id="96a62-104">Lync Server включает балансировку нагрузки DNS, программное решение, которое может значительно сократить расходы на администрирование для балансировки нагрузки в сети.</span><span class="sxs-lookup"><span data-stu-id="96a62-104">Lync Server enables DNS load balancing, a software solution that can greatly reduce the administration overhead for load balancing on your network.</span></span> <span data-ttu-id="96a62-105">Балансировка нагрузки DNS обеспечивает балансировку сетевого трафика, уникального для Lync Server, например трафик SIP и трафик мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="96a62-105">DNS load balancing balances the network traffic that is unique to Lync Server, such as SIP traffic and media traffic.</span></span>

<span data-ttu-id="96a62-106">При развертывании балансировки нагрузки DNS для аппаратной подсистем балансировки нагрузки будет минимизирована нагрузка на администрирование.</span><span class="sxs-lookup"><span data-stu-id="96a62-106">If you deploy DNS load balancing, your organization’s administration overhead for hardware load balancers will be minimized.</span></span> <span data-ttu-id="96a62-107">Кроме того, устранение неполадок, связанных с невозможностью устранения проблем с настройкой подсистем балансировки нагрузки для трафика SIP, будет исключено.</span><span class="sxs-lookup"><span data-stu-id="96a62-107">Additionally, complex troubleshooting of problems related to misconfiguration of load balancers for SIP traffic will be eliminated.</span></span> <span data-ttu-id="96a62-108">Кроме того, вы можете запретить соединение с сервером, чтобы вы могли перевести серверы в автономный режим.</span><span class="sxs-lookup"><span data-stu-id="96a62-108">You can also prevent server connections so that you can take servers offline.</span></span> <span data-ttu-id="96a62-109">Балансировка нагрузки DNS также гарантирует, что проблемы с подсистемой балансировки нагрузки не повлияют на элементы трафика SIP, такие как простой маршрут вызова.</span><span class="sxs-lookup"><span data-stu-id="96a62-109">DNS load balancing also ensures that hardware load balancer problems do not affect elements of SIP traffic such as basic call routing.</span></span>

<span data-ttu-id="96a62-110">При использовании балансировки нагрузки DNS вы также можете приобрести более низкие затраты на подсистемы балансировки нагрузки для оборудования, чем при использовании аппаратных подсистем балансировки нагрузки для всех типов трафика.</span><span class="sxs-lookup"><span data-stu-id="96a62-110">If you use DNS load balancing, you may also be able to purchase lower-cost hardware load balancers than if you used the hardware load balancers for all types of traffic.</span></span> <span data-ttu-id="96a62-111">Вы должны использовать балансировщик нагрузки, который прошел проверочное тестирование взаимодействия с Lync Server.</span><span class="sxs-lookup"><span data-stu-id="96a62-111">You should use load balancers that have passed interoperability qualification testing with Lync Server.</span></span> <span data-ttu-id="96a62-112">Подробнее об испытаниях о взаимодействии подсистемы балансировки нагрузки можно найти в [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452)разделе "Партнеры балансировки нагрузки для Lync Server 2010".</span><span class="sxs-lookup"><span data-stu-id="96a62-112">For details about load balancer interoperability testing, see "Lync Server 2010 Load Balancer Partners" at [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452).</span></span>

<span data-ttu-id="96a62-113">Балансировка нагрузки DNS поддерживается для пулов интерфейсов, пулов пограничного сервера, пулов и изолированных серверных пулов.</span><span class="sxs-lookup"><span data-stu-id="96a62-113">DNS load balancing is supported for Front End pools, Edge Server pools, Director pools, and stand-alone Mediation Server pools.</span></span>

<div>

## <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="96a62-114">Балансировка нагрузки DNS для пулов и пулов переднего плана</span><span class="sxs-lookup"><span data-stu-id="96a62-114">DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="96a62-115">Балансировку нагрузки DNS можно использовать для трафика SIP на пулах и пулах интерфейсов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="96a62-115">You can use DNS load balancing for the SIP traffic on Front End pools and Director pools.</span></span> <span data-ttu-id="96a62-116">После развертывания балансировки нагрузки DNS для этих пулов также необходимо использовать балансировку нагрузки оборудования, но только для трафика HTTPS между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="96a62-116">With DNS load balancing deployed, you still need to also use hardware load balancers for these pools, but only for client-to-server HTTPS traffic.</span></span> <span data-ttu-id="96a62-117">Подсистема балансировки нагрузки аппаратных средств используется для трафика HTTPS от клиентов через порты 443 и 80.</span><span class="sxs-lookup"><span data-stu-id="96a62-117">The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span>

<span data-ttu-id="96a62-118">Несмотря на то, что для этих пулов по-прежнему нужны подсистемы балансировки нагрузки, их настройка и администрирование будут главным образом для трафика HTTPS, с которыми связаны администраторы подсистемы балансировки нагрузки оборудования.</span><span class="sxs-lookup"><span data-stu-id="96a62-118">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTPS traffic, which the administrators of hardware load balancers are accustomed to.</span></span>

<div>

## <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a><span data-ttu-id="96a62-119">Балансировка нагрузки DNS и поддержка более ранних версий клиентов и серверов</span><span class="sxs-lookup"><span data-stu-id="96a62-119">DNS Load Balancing and Supporting Older Clients and Servers</span></span>

<span data-ttu-id="96a62-120">Балансировка нагрузки DNS поддерживает автоматический переход на другой ресурс только для серверов с Lync Server 2013 или Lync Server 2010, а также для пользователей Lync 2013 и Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="96a62-120">DNS load balancing supports automatic failover only for servers running Lync Server 2013 or Lync Server 2010, and for Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="96a62-121">Более ранние версии клиентов и Office Communications Server по-прежнему могут подключаться к пулам с помощью балансировки нагрузки DNS, но если им не удается подключиться к первому серверу, на котором они ссылаются, они не смогут переключиться на другой сервер в пуле. .</span><span class="sxs-lookup"><span data-stu-id="96a62-121">Earlier versions of clients and Office Communications Server can still connect to pools running DNS load balancing, but if they cannot make a connection to the first server that DNS load balancing refers them to, they are unable to fail over to another server in the pool.</span></span>

<span data-ttu-id="96a62-122">Кроме того, если вы используете единую систему обмена сообщениями Exchange, для получения поддержки балансировки нагрузки DNS для Lync Server необходимо использовать минимум Exchange 2010 с пакетом обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="96a62-122">Additionally, if you are using Exchange UM, you must use a minimum of Exchange 2010 SP1 to get support for Lync Server DNS load balancing.</span></span> <span data-ttu-id="96a62-123">Если вы используете более раннюю версию Exchange, для этих сценариев Exchange UM ваши пользователи не будут иметь возможности отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="96a62-123">If you use an earlier version of Exchange, your users will not have failover capabilities for these Exchange UM scenarios:</span></span>

  - <span data-ttu-id="96a62-124">Воспроизведение корпоративной голосовой почты на телефоне</span><span class="sxs-lookup"><span data-stu-id="96a62-124">Playing their Enterprise Voice voice mail on their phone</span></span>

  - <span data-ttu-id="96a62-125">Передача звонков из автосекретаря UM Exchange</span><span class="sxs-lookup"><span data-stu-id="96a62-125">Transferring calls from an Exchange UM Auto Attendant</span></span>

<span data-ttu-id="96a62-126">Все остальные сценарии UM Exchange будут работать правильно.</span><span class="sxs-lookup"><span data-stu-id="96a62-126">All other Exchange UM scenarios will work properly.</span></span>

</div>

<div>

## <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="96a62-127">Развертывание балансировки нагрузки DNS для пулов и пулов с интерфейсом на стороне сервера</span><span class="sxs-lookup"><span data-stu-id="96a62-127">Deploying DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="96a62-128">Для развертывания балансировки нагрузки DNS на интерфейсах пулов и пулов с внешним интерфейсом необходимо выполнить несколько дополнительных действий с полными доменными данными и DNS-записями.</span><span class="sxs-lookup"><span data-stu-id="96a62-128">Deploying DNS load balancing on Front End pools and Director pools requires you to perform a couple of extra steps with FQDNs and DNS records.</span></span>

  - <span data-ttu-id="96a62-129">Пул, использующий балансировку нагрузки DNS, должен иметь два полных доменных имен: обычное полное доменное имя пула, используемое службой балансировки нагрузки DNS (например, pool01.contoso.com), и разрешение на физические IP-адреса серверов в пуле, а также другое полное доменное имя (например, web01.contoso.com), который разрешается в виртуальный IP-адрес пула.</span><span class="sxs-lookup"><span data-stu-id="96a62-129">A pool that uses DNS load balancing must have two FQDNs: the regular pool FQDN that is used by DNS load balancing (such as pool01.contoso.com), and resolves to the physical IPs of the servers in the pool, and another FQDN for the pool’s Web services (such as web01.contoso.com), which resolves to virtual IP address of the pool.</span></span>
    
    <span data-ttu-id="96a62-130">В построителе топологии, если вы хотите развернуть балансировку нагрузки DNS для пула, чтобы создать это дополнительное полное доменное имя для веб-служб пула, необходимо установить флажок **переопределить полное доменное имя пула веб-служб** и ввести полное доменное имя в поле **указать URL-адреса для этой страницы пула** .</span><span class="sxs-lookup"><span data-stu-id="96a62-130">In Topology Builder, if you want to deploy DNS load balancing for a pool, to create this extra FQDN for the pool’s Web services you must select the **Override internal Web Services pool FQDN** check box and type the FQDN, in the **Specify the Web Services URLs for this Pool** page.</span></span>

  - <span data-ttu-id="96a62-131">Для поддержки полного доменного имени, используемого службой балансировки нагрузки DNS, необходимо подготовить DNS для разрешения полного доменного имени пула (например, pool01.contoso.com) в IP-адреса всех серверов в пуле (например, 192.168.1.1, 192.168.1.2 и т. д.).</span><span class="sxs-lookup"><span data-stu-id="96a62-131">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on).</span></span> <span data-ttu-id="96a62-132">Вы должны включать только IP-адреса серверов, которые развернут в данный момент.</span><span class="sxs-lookup"><span data-stu-id="96a62-132">You should include only the IP addresses of servers that are currently deployed.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="96a62-133">Если у вас более одного пула переднего плана или сервера переднего плана, полное доменное имя внешней веб-службы должно быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="96a62-133">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="96a62-134">Например, если вы определяете полное доменное имя внешней веб-службы на сервере переднего плана как <STRONG>pool01.contoso.com</STRONG>, вы не сможете использовать <STRONG>pool01.contoso.com</STRONG> для другого пула переднего плана или сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="96a62-134">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="96a62-135">Если вы также разворачиваете директоров, то полные доменные имена внешних веб-служб, определенные для любого режиссера или режиссера, должны быть уникальными из любого другого директора или пула и внешнего сервера.</span><span class="sxs-lookup"><span data-stu-id="96a62-135">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="96a62-136">Если вы решите переопределить внутренние веб-службы с помощью самоопределенного полного доменного имени, каждое полное доменное имя должно быть уникальным из любого другого пула переднего плана, режиссера или директора пула.</span><span class="sxs-lookup"><span data-stu-id="96a62-136">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

</div>

</div>

<div>

## <a name="dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="96a62-137">Балансировка нагрузки DNS для пулов пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="96a62-137">DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="96a62-138">Вы можете развернуть балансировку нагрузки DNS для пулов пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="96a62-138">You can deploy DNS load balancing on Edge Server pools.</span></span> <span data-ttu-id="96a62-139">В противном случае необходимо учитывать некоторые моменты.</span><span class="sxs-lookup"><span data-stu-id="96a62-139">If you do, you must be aware of some considerations.</span></span>

<span data-ttu-id="96a62-140">Использование балансировки нагрузки DNS на пограничных серверах приводит к потере возможности отработки отказа в следующих сценариях.</span><span class="sxs-lookup"><span data-stu-id="96a62-140">Using DNS load balancing on your Edge Servers causes a loss of failover ability in the following scenarios:</span></span>

  - <span data-ttu-id="96a62-141">Интеграция с организациями, на которых запущены версии Office Communications Server, выпущенные до Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="96a62-141">Federation with organizations that are running versions of Office Communications Server released prior to Lync Server 2010.</span></span>

  - <span data-ttu-id="96a62-142">Обмен мгновенными сообщениями с пользователями общедоступных служб обмена мгновенными сообщениями (Аоланд Yahoo\!) в дополнение к поставщикам и серверам, поддерживающим КСМПП, например Google поговорить.</span><span class="sxs-lookup"><span data-stu-id="96a62-142">Instant message exchange with users of public instant messaging (IM) services AOLand Yahoo\!, in addition to XMPP-based providers and servers, such as Google Talk.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="96a62-143">В настоящее время Google поговорить является единственным поддерживаемым партнером КСМПП.</span><span class="sxs-lookup"><span data-stu-id="96a62-143">Google Talk is currently the only supported XMPP partner.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="96a62-144">По состоянию на 1 сентября 2012, лицензия на подписку на общедоступные службы обмена мгновенными сообщениями в Microsoft Lync ("PIC усл") больше недоступна для приобретения новых или обновленных договоров.</span><span class="sxs-lookup"><span data-stu-id="96a62-144">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="96a62-145">Пользователи с активными лицензиями смогут продолжать использовать федерацию с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="96a62-145">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="96a62-146">Messenger, пока служба не отключается.</span><span class="sxs-lookup"><span data-stu-id="96a62-146">Messenger until the service shut down date.</span></span> <span data-ttu-id="96a62-147">Дата окончания жизненного цикла 2014 для AOL и Yahoo! в течение июня.</span><span class="sxs-lookup"><span data-stu-id="96a62-147">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="96a62-148">было объявлено.</span><span class="sxs-lookup"><span data-stu-id="96a62-148">has been announced.</span></span> <span data-ttu-id="96a62-149">Подробности можно найти <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">в разделе Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="96a62-149">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P></LI></UL>

    
    </div>

<span data-ttu-id="96a62-150">Эти сценарии будут работать до тех пор, пока все пограничные серверы пула работают и выполняются, но если один пограничный сервер недоступен, любые запросы к этим сценариям, которые отправляются на него, будут завершаться сбоем вместо маршрутизации на другой пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="96a62-150">These scenarios will work as long as all Edge Servers in the pool are up and running, but if one Edge Server is unavailable, any requests for these scenarios that are sent to it will fail, instead of routing to another Edge Server.</span></span>

<span data-ttu-id="96a62-151">Если вы используете Exchange UM, для получения поддержки балансировки нагрузки DNS для Lync Server в Edge необходимо использовать минимум Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="96a62-151">If you are using Exchange UM, you must use a minimum of Exchange 2013 to get support for Lync Server DNS load balancing on Edge.</span></span> <span data-ttu-id="96a62-152">Если вы используете более раннюю версию Exchange, удаленные пользователи не будут иметь возможности отработки отказа для этих сценариев Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="96a62-152">If you use an earlier version of Exchange, your remote users will not have failover capabilities for these Exchange UM scenarios:</span></span>

  - <span data-ttu-id="96a62-153">Воспроизведение корпоративной голосовой почты на телефоне</span><span class="sxs-lookup"><span data-stu-id="96a62-153">Playing their Enterprise Voice voice mail on their phone</span></span>

  - <span data-ttu-id="96a62-154">Передача звонков из автосекретаря UM Exchange</span><span class="sxs-lookup"><span data-stu-id="96a62-154">Transferring calls from an Exchange UM Auto Attendant</span></span>

<span data-ttu-id="96a62-155">Все остальные сценарии UM Exchange будут работать правильно.</span><span class="sxs-lookup"><span data-stu-id="96a62-155">All other Exchange UM scenarios will work properly.</span></span>

<span data-ttu-id="96a62-156">Балансировка нагрузки на внутреннем и внешнем пограничным интерфейсах должна относиться к одному и тому же типу.</span><span class="sxs-lookup"><span data-stu-id="96a62-156">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="96a62-157">Невозможно осуществлять балансировку нагрузки на одном пограничном интерфейсе средствами DNS, а на другом — аппаратными средствами.</span><span class="sxs-lookup"><span data-stu-id="96a62-157">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>

<div>

## <a name="deploying-dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="96a62-158">Развертывание балансировки нагрузки DNS для пулов пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="96a62-158">Deploying DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="96a62-159">Для развертывания балансировки нагрузки DNS на внешнем интерфейсе пула пограничного сервера вам понадобятся указанные ниже DNS-записи.</span><span class="sxs-lookup"><span data-stu-id="96a62-159">To deploy DNS load balancing on the external interface of your Edge Server pool, you need the following DNS entries:</span></span>

  - <span data-ttu-id="96a62-160">Для службы Edge Access требуется одна запись для каждого сервера в пуле.</span><span class="sxs-lookup"><span data-stu-id="96a62-160">For the Access Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="96a62-161">Каждая запись должна разрешать полное доменное имя службы пограничного доступа (например, sip.contoso.com) в IP-адрес службы пограничного доступа на одном из пограничных серверов в пуле.</span><span class="sxs-lookup"><span data-stu-id="96a62-161">Each entry must resolve the FQDN of the Access Edge service (for example, sip.contoso.com) to the IP address of the Access Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="96a62-162">Для службы Edge для веб-конференций требуется одна запись для каждого сервера в пуле.</span><span class="sxs-lookup"><span data-stu-id="96a62-162">For the Web Conferencing Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="96a62-163">Каждая запись должна разрешать полное доменное имя службы пограничного веб-конференции (например, webconf.contoso.com) в IP-адрес службы пограничного веб-конференции на одном из пограничных серверов в пуле.</span><span class="sxs-lookup"><span data-stu-id="96a62-163">Each entry must resolve the FQDN of the Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="96a62-164">Для службы аудио/видеоedge вам потребуется одна запись для каждого сервера в пуле.</span><span class="sxs-lookup"><span data-stu-id="96a62-164">For the Audio/Video Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="96a62-165">Каждая запись должна разрешать полное доменное имя (например, av.contoso.com) в IP-адресе службы EDGE на одном из пограничных серверов в пуле.</span><span class="sxs-lookup"><span data-stu-id="96a62-165">Each entry must resolve the FQDN of the Audio/Video Edge service (for example, av.contoso.com) to the IP address of the A/V Edge service on one of the Edge Servers in the pool.</span></span>

<span data-ttu-id="96a62-166">Для развертывания балансировки нагрузки DNS на внутреннем интерфейсе пула пограничного сервера необходимо добавить одну запись DNS A, которая разрешает внутреннее полное доменное имя пула пограничного сервера в IP-адрес каждого сервера в пуле.</span><span class="sxs-lookup"><span data-stu-id="96a62-166">To deploy DNS load balancing on the internal interface of your Edge Server pool, you must add one DNS A record, which resolves the internal FQDN of the Edge Server pool to the IP address of each server in the pool.</span></span>

</div>

</div>

<div>

## <a name="using-dns-load-balancing-on-mediation-server-pools"></a><span data-ttu-id="96a62-167">Использование балансировки нагрузки DNS для пулов серверов исправлений</span><span class="sxs-lookup"><span data-stu-id="96a62-167">Using DNS Load Balancing on Mediation Server Pools</span></span>

<span data-ttu-id="96a62-168">Вы можете использовать балансировку нагрузки DNS для пулов серверов с изолированными исправлениями.</span><span class="sxs-lookup"><span data-stu-id="96a62-168">You can use DNS load balancing on stand-alone Mediation Server pools.</span></span> <span data-ttu-id="96a62-169">Весь трафик SIP и мультимедиа сбалансирован с помощью балансировки нагрузки DNS.</span><span class="sxs-lookup"><span data-stu-id="96a62-169">All SIP and media traffic is balanced by DNS load balancing.</span></span>

<span data-ttu-id="96a62-170">Для развертывания балансировки нагрузки DNS в пуле серверов-исправлений необходимо подготовить DNS для разрешения полного доменного имени пула (например, mediationpool1.contoso.com) в IP-адреса всех серверов в пуле (например, 192.168.1.1, 192.168.1.2 и т. д.).</span><span class="sxs-lookup"><span data-stu-id="96a62-170">To deploy DNS load balancing on a Mediation Server pool, you must provision DNS to resolve the pool FQDN (for example, mediationpool1.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on).</span></span>

</div>

<div>

## <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a><span data-ttu-id="96a62-171">Блокировка трафика на сервер с помощью балансировки нагрузки DNS</span><span class="sxs-lookup"><span data-stu-id="96a62-171">Blocking Traffic to a Server With DNS Load Balancing</span></span>

<span data-ttu-id="96a62-p117">Если используется балансировка DNS-нагрузки и требуется блокировать трафик на конкретный компьютер, недостаточно просто удалить записи IP-адреса из полного имени домена пула. Необходимо также удалить DNS-запись для этого компьютера.</span><span class="sxs-lookup"><span data-stu-id="96a62-p117">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN. You must remove the DNS entry for the computer as well.</span></span>

<span data-ttu-id="96a62-174">Обратите внимание, что при использовании трафика "сервер-сервер" в Lync Server 2013 используется балансировка нагрузки, учитывающая топологию.</span><span class="sxs-lookup"><span data-stu-id="96a62-174">Note that for server-to-server traffic, Lync Server 2013 uses topology-aware load balancing.</span></span> <span data-ttu-id="96a62-175">Серверы считывают опубликованную топологию в хранилище Центрального управления для получения полных доменных имен серверов в топологии и автоматически распространяют трафик между серверами.</span><span class="sxs-lookup"><span data-stu-id="96a62-175">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="96a62-176">Чтобы запретить серверу принимать трафик "сервер-сервер", необходимо удалить сервер из топологии.</span><span class="sxs-lookup"><span data-stu-id="96a62-176">To block a server from receiving server-to-server traffic, you must remove the server from the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

