---
title: 'Lync Server 2013: Балансировка нагрузки на DNS'
description: 'Lync Server 2013: Балансировка нагрузки на DNS.'
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
ms.openlocfilehash: ba95604ca8f4007c76cedea9bf2a16dbd7db455c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574425"
---
# <a name="dns-load-balancing-in-lync-server-2013"></a><span data-ttu-id="1c1e4-103">Балансировка нагрузки на DNS в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c1e4-103">DNS load balancing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c1e4-104">_**Последнее изменение темы:** 2014-01-15_</span><span class="sxs-lookup"><span data-stu-id="1c1e4-104">_**Topic Last Modified:** 2014-01-15_</span></span>

<span data-ttu-id="1c1e4-105">Lync Server включает балансировку нагрузки на DNS, программное решение, которое может значительно уменьшить затраты на администрирование для балансировки нагрузки в сети.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-105">Lync Server enables DNS load balancing, a software solution that can greatly reduce the administration overhead for load balancing on your network.</span></span> <span data-ttu-id="1c1e4-106">Балансировка нагрузки на DNS обеспечивает балансировку сетевого трафика, уникального для Lync Server, например трафика SIP и трафика мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-106">DNS load balancing balances the network traffic that is unique to Lync Server, such as SIP traffic and media traffic.</span></span>

<span data-ttu-id="1c1e4-p102">Если вы разворачиваете балансировку нагрузки на DNS, то нагрузка, связанная с администрированием аппаратных балансировщиков нагрузки в вашей организации, будет максимально сокращена. Кроме того, будет исключена комплексная диагностика проблем, связанных с неправильной конфигурацией аппаратных балансировщиков нагрузки для трафика SIP. Можно также запрещать серверные подключения, чтобы можно было переводить серверы в автономный режим. Балансировка нагрузки на DNS также гарантирует, что проблемы аппаратных балансировщиков нагрузки не будут оказывать влияние на элементы трафика SIP, такие как базовая маршрутизация вызовов.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-p102">If you deploy DNS load balancing, your organization’s administration overhead for hardware load balancers will be minimized. Additionally, complex troubleshooting of problems related to misconfiguration of load balancers for SIP traffic will be eliminated. You can also prevent server connections so that you can take servers offline. DNS load balancing also ensures that hardware load balancer problems do not affect elements of SIP traffic such as basic call routing.</span></span>

<span data-ttu-id="1c1e4-111">При использовании балансировки нагрузки на DNS может также появиться возможность приобретения аппаратных балансировщиков нагрузки меньшей стоимости, чем при использовании аппаратных балансировщиков нагрузки для всех типов трафика.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-111">If you use DNS load balancing, you may also be able to purchase lower-cost hardware load balancers than if you used the hardware load balancers for all types of traffic.</span></span> <span data-ttu-id="1c1e4-112">Следует использовать системы балансировки нагрузки, которые прошли проверочное тестирование взаимодействия с сервером Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-112">You should use load balancers that have passed interoperability qualification testing with Lync Server.</span></span> <span data-ttu-id="1c1e4-113">Подробные сведения о тестировании взаимодействия с подсистемой балансировки нагрузки приведены в разделе "Партнеры балансировки нагрузки Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452) .</span><span class="sxs-lookup"><span data-stu-id="1c1e4-113">For details about load balancer interoperability testing, see "Lync Server 2010 Load Balancer Partners" at [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452).</span></span>

<span data-ttu-id="1c1e4-114">Балансировка нагрузки на DNS поддерживается для интерфейсных пулов, пулов пограничных серверов, пулов "Директор" и пулов изолированных серверов-посредников.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-114">DNS load balancing is supported for Front End pools, Edge Server pools, Director pools, and stand-alone Mediation Server pools.</span></span>

<div>

## <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="1c1e4-115">Балансировка нагрузки на DNS в интерфейсных пулах и в пулах "Директор"</span><span class="sxs-lookup"><span data-stu-id="1c1e4-115">DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="1c1e4-p104">Балансировку нагрузки на DNS можно использовать для трафика SIP в интерфейсных пулах и в пулах "Директор". Если развернута балансировка нагрузки на DNS, то все еще требуется использовать в этих пулах аппаратные балансировщики нагрузки, но только для HTTPS-трафика с клиента на сервер. Аппаратный балансировщик нагрузки используется для HTTPS-трафика от клиентов через порты 443 и 80.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-p104">You can use DNS load balancing for the SIP traffic on Front End pools and Director pools. With DNS load balancing deployed, you still need to also use hardware load balancers for these pools, but only for client-to-server HTTPS traffic. The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span>

<span data-ttu-id="1c1e4-119">Хотя для этих пулов еще нужны аппаратные балансировщики нагрузки, их настройка и администрирование будет в основном выполняться для HTTPS-трафика, который привычен для администраторов аппаратных балансировщиков нагрузки.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-119">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTPS traffic, which the administrators of hardware load balancers are accustomed to.</span></span>

<div>

## <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a><span data-ttu-id="1c1e4-120">Балансировка нагрузки на DNS и поддержка устаревших версий клиентов и серверов</span><span class="sxs-lookup"><span data-stu-id="1c1e4-120">DNS Load Balancing and Supporting Older Clients and Servers</span></span>

<span data-ttu-id="1c1e4-121">Балансировка нагрузки на DNS поддерживает автоматическую отработку отказа только для серверов, на которых работает Lync Server 2013 или Lync Server 2010, а также для клиентов Lync 2013 и Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-121">DNS load balancing supports automatic failover only for servers running Lync Server 2013 or Lync Server 2010, and for Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="1c1e4-122">Более ранние версии клиентов и Office Communications Server по-прежнему могут подключаться к пулам с балансировкой нагрузки на DNS, но если не удается установить подключение к первому серверу, на который ссылается балансировка нагрузки DNS, они не смогут выполнить отработку отказа на другой сервер в пуле.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-122">Earlier versions of clients and Office Communications Server can still connect to pools running DNS load balancing, but if they cannot make a connection to the first server that DNS load balancing refers them to, they are unable to fail over to another server in the pool.</span></span>

<span data-ttu-id="1c1e4-123">Кроме того, если вы используете единую систему обмена сообщениями Exchange, то для получения поддержки балансировки нагрузки на Lync Server необходимо использовать как минимум Exchange 2010 с пакетом обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="1c1e4-123">Additionally, if you are using Exchange UM, you must use a minimum of Exchange 2010 SP1 to get support for Lync Server DNS load balancing.</span></span> <span data-ttu-id="1c1e4-124">Если используется более ранняя версия Exchange, то пользователи не будут иметь возможности отработки отказа в следующих сценариях единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-124">If you use an earlier version of Exchange, your users will not have failover capabilities for these Exchange UM scenarios:</span></span>

  - <span data-ttu-id="1c1e4-125">Воспроизведение голосовой почты корпоративной голосовой связи на своем телефоне.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-125">Playing their Enterprise Voice voice mail on their phone</span></span>

  - <span data-ttu-id="1c1e4-126">Передача вызовов из автосекретаря единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-126">Transferring calls from an Exchange UM Auto Attendant</span></span>

<span data-ttu-id="1c1e4-127">Все остальные сценарии единой системы обмена сообщениями Exchange будут работать должным образом.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-127">All other Exchange UM scenarios will work properly.</span></span>

</div>

<div>

## <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="1c1e4-128">Развертывание балансировки нагрузки на DNS в интерфейсных пулах и в пулах "Директор"</span><span class="sxs-lookup"><span data-stu-id="1c1e4-128">Deploying DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="1c1e4-129">Для развертывания балансировки нагрузки на DNS в интерфейсных пулах и в пулах "Директор" потребуется выполнить пару дополнительных действий с полными доменными именами и записями DNS.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-129">Deploying DNS load balancing on Front End pools and Director pools requires you to perform a couple of extra steps with FQDNs and DNS records.</span></span>

  - <span data-ttu-id="1c1e4-130">Пул, который использует балансировку нагрузки на DNS, должен иметь два полных доменных имени: обычное полное доменное имя пула, которое используется балансировкой нагрузки на DNS (такое как pool01.contoso.com) и сводится к физическим IP-адресам серверов в пуле, и другое полное доменное имя для веб-служб пула (такое как web01.contoso.com), которое сводится к виртуальным IP-адресам пула.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-130">A pool that uses DNS load balancing must have two FQDNs: the regular pool FQDN that is used by DNS load balancing (such as pool01.contoso.com), and resolves to the physical IPs of the servers in the pool, and another FQDN for the pool’s Web services (such as web01.contoso.com), which resolves to virtual IP address of the pool.</span></span>
    
    <span data-ttu-id="1c1e4-131">В построителе топологий, если необходимо развернуть балансировку нагрузки на DNS для пула, чтобы создать дополнительное полное доменное имя для веб-служб пула, установите флажок **переопределить полное доменное имя пула внутренних веб-служб** и введите полное доменное имя в поле **укажите URL-адреса веб-служб для этой страницы пула** .</span><span class="sxs-lookup"><span data-stu-id="1c1e4-131">In Topology Builder, if you want to deploy DNS load balancing for a pool, to create this extra FQDN for the pool’s Web services you must select the **Override internal Web Services pool FQDN** check box and type the FQDN, in the **Specify the Web Services URLs for this Pool** page.</span></span>

  - <span data-ttu-id="1c1e4-p107">Для поддержки полного доменного имени, используемого балансировкой нагрузки на DNS, необходимо подготовить DNS, чтобы полное доменное имя пула (такое как pool01.contoso.com) сводилось к IP-адресам всех серверов в пуле (например, 192.168.1.1, 192.168.1.2 и т.д.). Следует включать IP-адреса только тех серверов которые развернуты в текущий момент.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-p107">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on). You should include only the IP addresses of servers that are currently deployed.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="1c1e4-134">Если у вас больше одного интерфейсного пула или сервера переднего плана, полное доменное имя внешних веб-служб должно быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-134">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="1c1e4-135">Например, если вы определили полное доменное имя внешних веб-служб для сервера переднего плана как <STRONG>pool01.contoso.com</STRONG>, вы не сможете использовать <STRONG>pool01.contoso.com</STRONG> для другого пула переднего плана или сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-135">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="1c1e4-136">Если вы также развертываете директоров, то полное доменное имя внешних веб-служб, определенное для любого директора или пула директоров, должно быть уникальным в любом другом директоре или пуле, а также в любом пуле переднего плана или сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-136">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="1c1e4-137">Если решено переопределить внутренние веб-службы с самоопределенным полным доменным именем, каждое полное доменное имя должно быть уникальным в любом другом интерфейсном пуле, директоре или в пуле директоров.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-137">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

</div>

</div>

<div>

## <a name="dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="1c1e4-138">Балансировка нагрузки на DNS в пулах пограничных серверов</span><span class="sxs-lookup"><span data-stu-id="1c1e4-138">DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="1c1e4-p109">Балансировку нагрузки на DNS можно разворачивать в пулах пограничных серверов. Для этого необходимо быть в курсе некоторых обстоятельств.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-p109">You can deploy DNS load balancing on Edge Server pools. If you do, you must be aware of some considerations.</span></span>

<span data-ttu-id="1c1e4-141">При использовании балансировки нагрузки на DNS на пограничных серверах будет потеряна возможность отработки отказа в следующих сценариях.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-141">Using DNS load balancing on your Edge Servers causes a loss of failover ability in the following scenarios:</span></span>

  - <span data-ttu-id="1c1e4-142">Федерация с организациями, на которых запущены версии Office Communications Server, выпущенные до Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-142">Federation with organizations that are running versions of Office Communications Server released prior to Lync Server 2010.</span></span>

  - <span data-ttu-id="1c1e4-143">Обмен мгновенными сообщениями с пользователями общедоступных служб обмена мгновенными сообщениями Аоланд Yahoo \! в дополнение к поставщикам и серверам на основе XMPP, таким как Google говорите.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-143">Instant message exchange with users of public instant messaging (IM) services AOLand Yahoo\!, in addition to XMPP-based providers and servers, such as Google Talk.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="1c1e4-144">В настоящее время Google говорите является единственным поддерживаемым партнером XMPP.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-144">Google Talk is currently the only supported XMPP partner.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="1c1e4-145">С 1 сентября 2012 г. лицензия подписки на общедоступные службы обмена мгновенными сообщениями Microsoft Lync ("PIC усл") больше недоступна для приобретения новых или обновленных договоров.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-145">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="1c1e4-146">Клиенты с активными лицензиями смогут продолжать Федерацию с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="1c1e4-146">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="1c1e4-147">Messenger до даты завершения работы службы.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-147">Messenger until the service shut down date.</span></span> <span data-ttu-id="1c1e4-148">Дата окончания срока жизни 2014 для AOL и Yahoo!</span><span class="sxs-lookup"><span data-stu-id="1c1e4-148">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="1c1e4-149">объявлено.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-149">has been announced.</span></span> <span data-ttu-id="1c1e4-150">Дополнительные сведения см <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">в разделе Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-150">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P></LI></UL>

    
    </div>

<span data-ttu-id="1c1e4-151">Эти сценарии будут работать, пока работают все пограничные серверы в пуле, но если один пограничный сервер станет недоступен, то вместо перенаправления на другой пограничный сервер будет происходить сбой всех запросов этих сценариев, отправляемых на этот сервер.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-151">These scenarios will work as long as all Edge Servers in the pool are up and running, but if one Edge Server is unavailable, any requests for these scenarios that are sent to it will fail, instead of routing to another Edge Server.</span></span>

<span data-ttu-id="1c1e4-152">Если вы используете единую систему обмена сообщениями Exchange, то для получения поддержки балансировки нагрузки DNS Lync Server в пограничной системе необходимо использовать как минимум Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-152">If you are using Exchange UM, you must use a minimum of Exchange 2013 to get support for Lync Server DNS load balancing on Edge.</span></span> <span data-ttu-id="1c1e4-153">Если вы используете более раннюю версию Exchange, удаленные пользователи не будут иметь возможности отработки отказа для этих сценариев единой системы обмена сообщениями Exchange:</span><span class="sxs-lookup"><span data-stu-id="1c1e4-153">If you use an earlier version of Exchange, your remote users will not have failover capabilities for these Exchange UM scenarios:</span></span>

  - <span data-ttu-id="1c1e4-154">Воспроизведение голосовой почты корпоративной голосовой связи на своем телефоне.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-154">Playing their Enterprise Voice voice mail on their phone</span></span>

  - <span data-ttu-id="1c1e4-155">Передача вызовов из автосекретаря единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-155">Transferring calls from an Exchange UM Auto Attendant</span></span>

<span data-ttu-id="1c1e4-156">Все остальные сценарии единой системы обмена сообщениями Exchange будут работать должным образом.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-156">All other Exchange UM scenarios will work properly.</span></span>

<span data-ttu-id="1c1e4-p112">Внутренний пограничный интерфейс и внешний пограничный интерфейс должны использовать один тип балансировки нагрузки. Нельзя использовать балансировку нагрузки на DNS в одном пограничном интерфейсе и аппаратную балансировку нагрузки в другом пограничном интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-p112">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>

<div>

## <a name="deploying-dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="1c1e4-159">Развертывание балансировки нагрузки на DNS в пулах пограничных серверов</span><span class="sxs-lookup"><span data-stu-id="1c1e4-159">Deploying DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="1c1e4-160">Чтобы развернуть балансировку нагрузки на DNS во внешнем интерфейсе пула пограничных серверов, необходимы следующие записи DNS.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-160">To deploy DNS load balancing on the external interface of your Edge Server pool, you need the following DNS entries:</span></span>

  - <span data-ttu-id="1c1e4-161">Для службы пограничного доступа потребуется по одной записи для каждого сервера в пуле.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-161">For the Access Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="1c1e4-162">Каждая запись должна разрешать полное доменное имя службы пограничного доступа (например, sip.contoso.com) в IP-адрес пограничной службы доступа на одном из пограничных серверов в пуле.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-162">Each entry must resolve the FQDN of the Access Edge service (for example, sip.contoso.com) to the IP address of the Access Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="1c1e4-163">Для пограничной службы веб-конференций необходимо по одной записи на каждый сервер в пуле.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-163">For the Web Conferencing Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="1c1e4-164">Каждая запись должна разрешать полное доменное имя пограничной службы веб-конференций (например, webconf.contoso.com) в IP-адрес пограничной службы веб-конференций на одном из пограничных серверов в пуле.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-164">Each entry must resolve the FQDN of the Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="1c1e4-165">Для пограничной службы аудио-и видеоданных необходимо по одной записи на каждый сервер в пуле.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-165">For the Audio/Video Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="1c1e4-166">Каждая запись должна разрешать полное доменное имя пограничной службы аудио-и видеоданных (например, av.contoso.com) в IP-адрес пограничной службы аудио-и видеосвязи на одном из пограничных серверов в пуле.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-166">Each entry must resolve the FQDN of the Audio/Video Edge service (for example, av.contoso.com) to the IP address of the A/V Edge service on one of the Edge Servers in the pool.</span></span>

<span data-ttu-id="1c1e4-167">Для развертывания балансировки нагрузки DNS во внутреннем интерфейсе пула пограничных серверов необходимо добавить одну запись A DNS, которая сводит внутреннее полное доменное имя пула пограничных серверов к IP-адресу каждого сервера в пуле.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-167">To deploy DNS load balancing on the internal interface of your Edge Server pool, you must add one DNS A record, which resolves the internal FQDN of the Edge Server pool to the IP address of each server in the pool.</span></span>

</div>

</div>

<div>

## <a name="using-dns-load-balancing-on-mediation-server-pools"></a><span data-ttu-id="1c1e4-168">Использование балансировки нагрузки на DNS в пулах серверов-посредников</span><span class="sxs-lookup"><span data-stu-id="1c1e4-168">Using DNS Load Balancing on Mediation Server Pools</span></span>

<span data-ttu-id="1c1e4-p116">Балансировку нагрузки на DNS можно использовать в пулах изолированных серверов-посредников. Весь трафик SIP и мультимедиа балансируется с помощью балансировки нагрузки на DNS.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-p116">You can use DNS load balancing on stand-alone Mediation Server pools. All SIP and media traffic is balanced by DNS load balancing.</span></span>

<span data-ttu-id="1c1e4-171">Чтобы развернуть балансировку нагрузки на DNS в пуле серверов посредников, необходимо подготовить DNS, чтобы полное доменное имя пула (например, mediationpool1.contoso.com) сводилось к IP-адресам всех серверов в пуле (например, 192.168.1.1, 192.168.1.2 и т.п.).</span><span class="sxs-lookup"><span data-stu-id="1c1e4-171">To deploy DNS load balancing on a Mediation Server pool, you must provision DNS to resolve the pool FQDN (for example, mediationpool1.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on).</span></span>

</div>

<div>

## <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a><span data-ttu-id="1c1e4-172">Блокировка трафика на сервер с балансировкой нагрузки на DNS</span><span class="sxs-lookup"><span data-stu-id="1c1e4-172">Blocking Traffic to a Server With DNS Load Balancing</span></span>

<span data-ttu-id="1c1e4-p117">Если используется балансировка DNS-нагрузки и требуется блокировать трафик на конкретный компьютер, недостаточно просто удалить записи IP-адреса из полного имени домена пула. Необходимо также удалить DNS-запись для этого компьютера.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-p117">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN. You must remove the DNS entry for the computer as well.</span></span>

<span data-ttu-id="1c1e4-175">Обратите внимание, что для трафика между серверами в Lync Server 2013 используется балансировка нагрузки с поддержкой топологии.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-175">Note that for server-to-server traffic, Lync Server 2013 uses topology-aware load balancing.</span></span> <span data-ttu-id="1c1e4-176">Серверы прочитают опубликованную топологию в центральном хранилище управления для получения полных доменных имен серверов в топологии и автоматически распределяют трафик между серверами.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-176">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="1c1e4-177">Чтобы запретить серверу принимать трафик между серверами, следует удалить сервер из топологии.</span><span class="sxs-lookup"><span data-stu-id="1c1e4-177">To block a server from receiving server-to-server traffic, you must remove the server from the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

