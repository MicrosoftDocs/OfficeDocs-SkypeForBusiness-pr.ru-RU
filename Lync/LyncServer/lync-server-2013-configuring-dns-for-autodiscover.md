---
title: 'Lync Server 2013: Настройка DNS для автообнаружения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring DNS for Autodiscover
ms:assetid: f07a634c-3cf3-4958-8556-84596319ef54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945656(v=OCS.15)
ms:contentKeyID: 51541528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77cf81cd82655a37ad089d915e9e3799671025bb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736459"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-dns-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="f4f83-102">Настройка DNS для автообнаружения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4f83-102">Configuring DNS for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4f83-103">_**Тема последнего изменения:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="f4f83-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="f4f83-104">Для поддержки автообнаружение для клиентов Lync необходимо создать следующие записи DNS (Domain Name System):</span><span class="sxs-lookup"><span data-stu-id="f4f83-104">To support autodiscovery for Lync clients, you need to create the following Domain Name System (DNS) records:</span></span>

  - <span data-ttu-id="f4f83-105">Внутренняя запись DNS для поддержки клиентов Lync, подключающихся из сети Организации</span><span class="sxs-lookup"><span data-stu-id="f4f83-105">An internal DNS record to support Lync clients who connect from within your organization's network</span></span>

  - <span data-ttu-id="f4f83-106">Внешняя (или общедоступная) запись DNS для поддержки клиентов Lync, подключающихся из Интернета</span><span class="sxs-lookup"><span data-stu-id="f4f83-106">An external, or public, DNS record to support Lync clients who connect from the Internet</span></span>

<span data-ttu-id="f4f83-107">Вы должны создать внутреннюю запись DNS и внешнюю запись DNS для каждого домена SIP.</span><span class="sxs-lookup"><span data-stu-id="f4f83-107">You must create an internal DNS record and an external DNS record for each SIP domain.</span></span>

<span data-ttu-id="f4f83-108">DNS-записи могут быть либо записями (ведущими), либо записями CNAME, в зависимости от возможности создания новых сертификатов с помощью дополнительного имени альтернативной темы (SAN).</span><span class="sxs-lookup"><span data-stu-id="f4f83-108">The DNS records can be either A (host) records or CNAME records, based on your ability to create new certificates with the additional subject alternate name (SAN).</span></span> <span data-ttu-id="f4f83-109">Если вы не можете запросить и развернуть новый внешний (открытый) сертификат с помощью lyncdiscover. \<доменное\> имя San, используйте процедуру для использования порта HTTP/TCP 80.</span><span class="sxs-lookup"><span data-stu-id="f4f83-109">If you are not able to request and deploy a new external (public) certificate with the lyncdiscover.\<domain name\> SAN, use the procedure for using HTTP/TCP port 80.</span></span> <span data-ttu-id="f4f83-110">Ниже описана процедура создания внутренних и внешних записей DNS.</span><span class="sxs-lookup"><span data-stu-id="f4f83-110">The following procedures describe how to create internal and external DNS records.</span></span>

<div>

## <a name="to-create-dns-cname-records"></a><span data-ttu-id="f4f83-111">Создание записей CNAME DNS</span><span class="sxs-lookup"><span data-stu-id="f4f83-111">To create DNS CNAME records</span></span>

1.  <span data-ttu-id="f4f83-112">Войдите на DNS-сервер, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="f4f83-112">Log on to a DNS server as follows:</span></span>
    
      - <span data-ttu-id="f4f83-113">Чтобы создать внутреннюю DNS-запись, войдите в DNS-сервер в сети как член группы администраторов домена или участника группы Днсадминс.</span><span class="sxs-lookup"><span data-stu-id="f4f83-113">To create an internal DNS record, log on to a DNS server in your network as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
    
      - <span data-ttu-id="f4f83-114">Чтобы создать внешнюю запись DNS, подключитесь к общедоступному поставщику DNS.</span><span class="sxs-lookup"><span data-stu-id="f4f83-114">To create an external DNS record, connect to your public DNS provider.</span></span>

2.  <span data-ttu-id="f4f83-115">Откройте оснастку администрирование DNS: нажмите кнопку **Пуск**, выберите пункт **Администрирование**, а затем — **DNS**.</span><span class="sxs-lookup"><span data-stu-id="f4f83-115">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="f4f83-116">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="f4f83-116">Do one of the following:</span></span>
    
      - <span data-ttu-id="f4f83-117">Для внутренней записи DNS в дереве консоли DNS-сервера разверните **зоны прямого просмотра** для домена Active Directory (например, contoso. local).</span><span class="sxs-lookup"><span data-stu-id="f4f83-117">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f4f83-118">Этот домен является доменом Active Directory, в котором установлен пул&nbsp;каталогов Lync Server 2013 и пул внешних интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="f4f83-118">This domain is the Active Directory domain where your Lync Server 2013&nbsp;Director pool and Front End pool are installed.</span></span>

        
        </div>
    
      - <span data-ttu-id="f4f83-119">Для внешней записи DNS в дереве консоли DNS-сервера разверните **зоны прямого просмотра** для домена SIP (например, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="f4f83-119">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="f4f83-120">Убедитесь в том, что для пула каталогов существует запись узла, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="f4f83-120">Verify that a host A record exists for your Director pool as follows:</span></span>
    
      - <span data-ttu-id="f4f83-121">Для внутренней записи DNS должно существовать запись узла A для полного доменного имени (например, lyncwebdir01. contoso. local) для внутренних веб-служб (FQDN).</span><span class="sxs-lookup"><span data-stu-id="f4f83-121">For an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span>
    
      - <span data-ttu-id="f4f83-122">Для внешней записи DNS для пула каталогов внешних веб-служб (например, lyncwebextdir.contoso.com) должна существовать запись узла A.</span><span class="sxs-lookup"><span data-stu-id="f4f83-122">For an external DNS record, a host A record should exist for the external web services FQDN for your Director pool (for example, lyncwebextdir.contoso.com).</span></span>

5.  <span data-ttu-id="f4f83-123">Убедитесь в том, что для пула переднего плана существует запись с узлом, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="f4f83-123">Verify that a host A record exists for your Front End pool as follows:</span></span>
    
      - <span data-ttu-id="f4f83-124">Для внутренней записи DNS должна существовать запись узла A для внутреннего доменного имени внутренней веб-службы для пула переднего плана (например, lyncwebpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="f4f83-124">For an internal DNS record, a host A record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span>
    
      - <span data-ttu-id="f4f83-125">Для внешней записи DNS должна существовать запись узла A для внешнего доменного имени внешней веб-службы для пула переднего плана (например, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="f4f83-125">For an external DNS record, a host A record should exist for the external Web Services FQDN for your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>

6.  <span data-ttu-id="f4f83-126">Для внутренней записи DNS в дереве консоли DNS-сервера разверните **зоны прямого просмотра** для домена SIP (например, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="f4f83-126">For an internal DNS record, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f4f83-127">Если вы создаете внешнюю запись DNS, <STRONG>зоны прямого просмотра</STRONG> уже развернуты для вашего домена SIP на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="f4f83-127">If you are creating an external DNS record, <STRONG>Forward Lookup Zones</STRONG> is already expanded for your SIP domain from step 3.</span></span>

    
    </div>

7.  <span data-ttu-id="f4f83-128">Щелкните имя домена SIP правой кнопкой мыши и выберите команду **создать псевдоним (CNAME)**.</span><span class="sxs-lookup"><span data-stu-id="f4f83-128">Right-click the SIP domain name, and then click **New Alias (CNAME)**.</span></span>

8.  <span data-ttu-id="f4f83-129">В поле **Alias Name (псевдоним**) введите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="f4f83-129">In **Alias name**, type one of the following:</span></span>
    
      - <span data-ttu-id="f4f83-130">Для внутренней записи DNS введите линкдисковеринтернал в качестве имени узла для URL-адреса внутренней службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="f4f83-130">For an internal DNS record, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>
    
      - <span data-ttu-id="f4f83-131">Для внешней записи DNS введите lyncdiscover в качестве имени узла для URL-адреса внешней службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="f4f83-131">For an external DNS record, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="f4f83-132">В поле полное **доменное имя (FQDN) целевого узла**выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="f4f83-132">In **Fully qualified domain name (FQDN) for target host**, do one of the following:</span></span>
    
      - <span data-ttu-id="f4f83-133">Для внутренней записи DNS введите или выберите полное доменное имя внутренней веб-службы для своего пула (например, lyncwebdir01. contoso. local), а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f4f83-133">For an internal DNS record, type or browse to the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local), and then click **OK**.</span></span>
    
      - <span data-ttu-id="f4f83-134">Для внешней записи DNS введите или найдите полное доменное имя внешней веб-службы для своего пула (например, lyncwebextdir.contoso.com), а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f4f83-134">For an external DNS record, type or browse to the external Web Services FQDN for your Director pool (for example, lyncwebextdir.contoso.com), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f4f83-135">Если вы не используете режиссер, используйте внутреннее и внешнее полное доменное имя веб-служб для пула переднего плана или, для одного сервера, полное доменное имя сервера переднего плана или стандартного сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f4f83-135">If you do not use a Director, use the internal and external Web Services FQDN for the Front End pool, or, for a single server, the FQDN for the Front End Server or Standard Edition server.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f4f83-136">В зоне прямого просмотра каждого домена SIP, который поддерживается в среде Lync Server 2013, необходимо создать новую запись автообнаружения CNAME.</span><span class="sxs-lookup"><span data-stu-id="f4f83-136">You must create a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-dns-a-records"></a><span data-ttu-id="f4f83-137">Создание записей DNS A</span><span class="sxs-lookup"><span data-stu-id="f4f83-137">To create DNS A records</span></span>

1.  <span data-ttu-id="f4f83-138">Войдите на DNS-сервер, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="f4f83-138">Log on to a DNS server as follows:</span></span>
    
      - <span data-ttu-id="f4f83-139">Чтобы создать внутреннюю DNS-запись, войдите в DNS-сервер в сети как член группы администраторов домена или участника группы Днсадминс.</span><span class="sxs-lookup"><span data-stu-id="f4f83-139">To create an internal DNS record, log on to a DNS server in your network as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
    
      - <span data-ttu-id="f4f83-140">Чтобы создать внешнюю запись DNS, подключитесь к общедоступному поставщику услуг DNS или внешнему DNS-серверу.</span><span class="sxs-lookup"><span data-stu-id="f4f83-140">To create an external DNS record, connect to your public DNS provider or external DNS server.</span></span>

2.  <span data-ttu-id="f4f83-141">Откройте оснастку администрирование DNS: нажмите кнопку **Пуск**, выберите пункт **Администрирование**, а затем — **DNS**.</span><span class="sxs-lookup"><span data-stu-id="f4f83-141">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="f4f83-142">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="f4f83-142">Do one of the following:</span></span>
    
      - <span data-ttu-id="f4f83-143">Для внутренней записи DNS в дереве консоли DNS-сервера разверните **зоны прямого просмотра** для домена Active Directory (например, contoso. local).</span><span class="sxs-lookup"><span data-stu-id="f4f83-143">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f4f83-144">Этот домен является доменом Active Directory, в котором установлен пул&nbsp;каталогов Lync Server 2013 и пул внешних интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="f4f83-144">This domain is the Active Directory domain where your Lync Server 2013&nbsp;Director pool and Front End pool are installed.</span></span>

        
        </div>
    
      - <span data-ttu-id="f4f83-145">Для внешней записи DNS в дереве консоли DNS-сервера разверните **зоны прямого просмотра** для домена SIP (например, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="f4f83-145">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="f4f83-146">Убедитесь в том, что для вашего пула режиссера существует запись узла A (для IPv6, AAAA), как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="f4f83-146">Verify that a host A (for IPv6, AAAA) record exists for your Director pool as follows:</span></span>
    
      - <span data-ttu-id="f4f83-147">Для внутренней записи DNS должна существовать запись узла A (для IPv6, AAAA) для полного доменного имени (например, lyncwebdir01. contoso. local) внутренних веб-служб для пула каталогов.</span><span class="sxs-lookup"><span data-stu-id="f4f83-147">For an internal DNS record, a host A (for IPv6, AAAA) record should exist for the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local).</span></span>
    
      - <span data-ttu-id="f4f83-148">Для внешней записи DNS для пула каталогов внешних веб-служб (например, lyncwebextdir.contoso.com) должна существовать запись узла A (для IPv6, AAAA).</span><span class="sxs-lookup"><span data-stu-id="f4f83-148">For an external DNS record, a host A (for IPv6, AAAA) record should exist for the external Web Services FQDN for your Director pool (for example, lyncwebextdir.contoso.com).</span></span>

5.  <span data-ttu-id="f4f83-149">Убедитесь в том, что для пула переднего плана существует запись узла A (для IPv6, AAAA), как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="f4f83-149">Verify that a host A (for IPv6, AAAA) record exists for your Front End pool as follows:</span></span>
    
      - <span data-ttu-id="f4f83-150">Для внутренней записи DNS должна существовать запись Host A (для IPv6, AAAA) для полного доменного имени внутренней веб-службы для пула переднего плана (например, lyncwebpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="f4f83-150">For an internal DNS record, a host A (for IPv6, AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span>
    
      - <span data-ttu-id="f4f83-151">Для внешней записи DNS должна существовать запись Host A (для IPv6, AAAA) для полного доменного имени внешней веб-службы для пула переднего плана (например, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="f4f83-151">For an external DNS record, a host A (for IPv6, AAAA) record should exist for the external Web Services FQDN for your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>

6.  <span data-ttu-id="f4f83-152">Для внутренней записи DNS в дереве консоли DNS-сервера разверните **зоны прямого просмотра** для домена SIP (например, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="f4f83-152">For an internal DNS record, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f4f83-153">Если вы создаете внешнюю запись DNS, <STRONG>зоны прямого просмотра</STRONG> уже развернуты для вашего домена SIP на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="f4f83-153">If you are creating an external DNS record, <STRONG>Forward Lookup Zones</STRONG> is already expanded for your SIP domain from step 3.</span></span>

    
    </div>

7.  <span data-ttu-id="f4f83-154">Щелкните имя домена SIP правой кнопкой мыши и выберите команду **создать узел (A или AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="f4f83-154">Right-click the SIP domain name, and then click **New Host (A or AAAA)**.</span></span>

8.  <span data-ttu-id="f4f83-155">В поле **Name (имя**) введите имя узла, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="f4f83-155">In **Name**, type the host name as follows:</span></span>
    
      - <span data-ttu-id="f4f83-156">Для внутренней записи DNS введите линкдисковеринтернал в качестве имени узла для URL-адреса внутренней службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="f4f83-156">For an internal DNS record, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>
    
      - <span data-ttu-id="f4f83-157">Для внешней записи DNS введите lyncdiscover в качестве имени узла для URL-адреса внешней службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="f4f83-157">For an external DNS record, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f4f83-158">Доменное имя считается от зоны, в которой определена запись, поэтому ее не нужно вводить как часть записи A.</span><span class="sxs-lookup"><span data-stu-id="f4f83-158">The domain name is assumed from the zone in which the record is defined and, therefore, does not need to be entered as part of the A record.</span></span>

    
    </div>

9.  <span data-ttu-id="f4f83-159">В поле **IP-адрес**введите IP-адрес, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="f4f83-159">In **IP Address**, type the IP address as follows:</span></span>
    
      - <span data-ttu-id="f4f83-160">Для внутренней записи DNS введите IP-адрес внутренней веб-службы режиссера (или, если вы используете подсистему балансировку нагрузки, введите виртуальные IP-адреса (VIP) для подсистемы балансировки нагрузки режиссера).</span><span class="sxs-lookup"><span data-stu-id="f4f83-160">For an internal DNS record, type the internal Web Services IP address of the Director (or, if you use a load balancer, type the virtual IP (VIP) of the Director load balancer).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f4f83-161">Если вы не используете режиссер, введите IP-адрес сервера переднего плана или сервера Standard Edition или, если вы используете подсистему балансировки нагрузки, введите VIP для подсистемы балансировки нагрузки пула из состава переднего плана.</span><span class="sxs-lookup"><span data-stu-id="f4f83-161">If you do not use a Director, type the IP address of the Front End Server or Standard Edition server, or, if you use a load balancer, type the VIP of the Front End pool load balancer.</span></span>

        
        </div>
    
      - <span data-ttu-id="f4f83-162">Для внешней записи DNS введите внешний или общедоступный IP-адрес обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="f4f83-162">For an external DNS record, type the external or public IP address of the reverse proxy.</span></span>

10. <span data-ttu-id="f4f83-163">Нажмите кнопку **Добавить узел**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f4f83-163">Click **Add Host**, and then click **OK**.</span></span>

11. <span data-ttu-id="f4f83-164">Чтобы создать дополнительную запись, повторите шаги 8 – 10.</span><span class="sxs-lookup"><span data-stu-id="f4f83-164">To create an additional A record, repeat steps 8 through 10.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f4f83-165">Вы должны создать новый lyncdiscover и линкдисковеринтернал записи в зоне прямого просмотра каждого домена SIP, который поддерживается в среде Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4f83-165">You must create a new lyncdiscover and lyncdiscoverinternal A records in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

    
    </div>

12. <span data-ttu-id="f4f83-166">Завершив создание записей A (для IPv6, AAAA), нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="f4f83-166">When you are finished creating A (for IPv6, AAAA) records, click **Done**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

