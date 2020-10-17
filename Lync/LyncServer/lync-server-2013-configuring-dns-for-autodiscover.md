---
title: 'Lync Server 2013: Настройка DNS для службы автообнаружения'
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
ms.openlocfilehash: 249993e68930db1eb5dd5159633a73f80cef8c05
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520056"
---
# <a name="configuring-dns-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="61a88-102">Настройка DNS для автообнаружения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61a88-102">Configuring DNS for Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61a88-103">_**Последнее изменение темы:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="61a88-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="61a88-104">Чтобы обеспечить поддержку автообнаружения для клиентов Lync, необходимо создать следующие записи службы доменных имен (DNS):</span><span class="sxs-lookup"><span data-stu-id="61a88-104">To support autodiscovery for Lync clients, you need to create the following Domain Name System (DNS) records:</span></span>

  - <span data-ttu-id="61a88-105">Внутренняя запись DNS для поддержки клиентов Lync, подключающихся из сети Организации.</span><span class="sxs-lookup"><span data-stu-id="61a88-105">An internal DNS record to support Lync clients who connect from within your organization's network</span></span>

  - <span data-ttu-id="61a88-106">Внешняя (или общедоступная) запись DNS для поддержки клиентов Lync, подключающихся из Интернета</span><span class="sxs-lookup"><span data-stu-id="61a88-106">An external, or public, DNS record to support Lync clients who connect from the Internet</span></span>

<span data-ttu-id="61a88-107">Необходимо создать внутреннюю и внешнюю DNS-запись для каждого SIP-домена.</span><span class="sxs-lookup"><span data-stu-id="61a88-107">You must create an internal DNS record and an external DNS record for each SIP domain.</span></span>

<span data-ttu-id="61a88-108">DNS-записи могут быть либо записями (узла), либо записями CNAME, на основе возможности создавать новые сертификаты с дополнительным альтернативным именем субъекта (SAN).</span><span class="sxs-lookup"><span data-stu-id="61a88-108">The DNS records can be either A (host) records or CNAME records, based on your ability to create new certificates with the additional subject alternate name (SAN).</span></span> <span data-ttu-id="61a88-109">Если вы не можете запрашивать и развертывать новый внешний (общедоступный) сертификат с помощью lyncdiscover.\<domain name\></span><span class="sxs-lookup"><span data-stu-id="61a88-109">If you are not able to request and deploy a new external (public) certificate with the lyncdiscover.\<domain name\></span></span> <span data-ttu-id="61a88-110">SAN используйте процедуру для использования порта HTTP/TCP 80.</span><span class="sxs-lookup"><span data-stu-id="61a88-110">SAN, use the procedure for using HTTP/TCP port 80.</span></span> <span data-ttu-id="61a88-111">В последующих процедурах описано как создавать внешние и внутренние DNS-записи.</span><span class="sxs-lookup"><span data-stu-id="61a88-111">The following procedures describe how to create internal and external DNS records.</span></span>

<div>

## <a name="to-create-dns-cname-records"></a><span data-ttu-id="61a88-112">Создание DNS-записей CNAME</span><span class="sxs-lookup"><span data-stu-id="61a88-112">To create DNS CNAME records</span></span>

1.  <span data-ttu-id="61a88-113">Выполните вход на сервер DNS следующим образом:</span><span class="sxs-lookup"><span data-stu-id="61a88-113">Log on to a DNS server as follows:</span></span>
    
      - <span data-ttu-id="61a88-114">Чтобы создать внутреннюю DNS-запись, выполните вход на DNS-сервер вашей сети как член группы администраторов домена или член группы DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="61a88-114">To create an internal DNS record, log on to a DNS server in your network as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
    
      - <span data-ttu-id="61a88-115">Чтобы создать внешнюю DNS-запись подключитесь к внешнему поставщику DNS.</span><span class="sxs-lookup"><span data-stu-id="61a88-115">To create an external DNS record, connect to your public DNS provider.</span></span>

2.  <span data-ttu-id="61a88-116">Откройте административную оснастку DNS: нажмите **Пуск**, **Инструменты администратора** и **DNS**.</span><span class="sxs-lookup"><span data-stu-id="61a88-116">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="61a88-117">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="61a88-117">Do one of the following:</span></span>
    
      - <span data-ttu-id="61a88-118">Для внутренней DNS-записи, в дереве консоли DNS-сервера разверните элемент **Зоны прямого просмотра** для вашего домена Active Directory (например, contoso.local).</span><span class="sxs-lookup"><span data-stu-id="61a88-118">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="61a88-119">Этот домен является доменом Active Directory, в котором &nbsp; установлены пул каталогов Lync Server 2013 и пул переднего плана.</span><span class="sxs-lookup"><span data-stu-id="61a88-119">This domain is the Active Directory domain where your Lync Server 2013&nbsp;Director pool and Front End pool are installed.</span></span>

        
        </div>
    
      - <span data-ttu-id="61a88-120">Для внешней DNS-записи в дереве консоли DNS-сервера разверните элемент **Зоны прямого просмотра** для вашего SIP-домена (например, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="61a88-120">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="61a88-121">Убедитесь, что для пула директоров существует запись A узла, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="61a88-121">Verify that a host A record exists for your Director pool as follows:</span></span>
    
      - <span data-ttu-id="61a88-122">Для внутренней DNS-записи должна существовать запись узла A для полного доменного имени внутренних веб-служб (FQDN) для пула директоров (например, lyncwebdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="61a88-122">For an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span>
    
      - <span data-ttu-id="61a88-123">Для внешней DNS-записи запись узла A должна существовать для полного доменного имени внешних веб-служб для пула директоров (например, lyncwebextdir.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="61a88-123">For an external DNS record, a host A record should exist for the external web services FQDN for your Director pool (for example, lyncwebextdir.contoso.com).</span></span>

5.  <span data-ttu-id="61a88-124">Убедитесь, что для пула переднего плана существует запись A Host, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="61a88-124">Verify that a host A record exists for your Front End pool as follows:</span></span>
    
      - <span data-ttu-id="61a88-125">Для внутренней DNS-записи запись A узла должна существовать для полного доменного имени внутренних веб-служб для пула переднего плана (например, lyncwebpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="61a88-125">For an internal DNS record, a host A record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span>
    
      - <span data-ttu-id="61a88-126">Для внешней DNS-записи запись узла A должна существовать для полного доменного имени внешних веб-служб для пула переднего плана (например, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="61a88-126">For an external DNS record, a host A record should exist for the external Web Services FQDN for your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>

6.  <span data-ttu-id="61a88-127">Для внутренней DNS-записи, в дереве консоли DNS-сервера разверните элемент **Зоны прямого просмотра** для вашего SIP-домена (например, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="61a88-127">For an internal DNS record, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="61a88-128">Если создается внешняя DNS-запись, <STRONG>Зоны прямого доступа</STRONG> уже были развернуты для вашего SIP-домена с шага 3.</span><span class="sxs-lookup"><span data-stu-id="61a88-128">If you are creating an external DNS record, <STRONG>Forward Lookup Zones</STRONG> is already expanded for your SIP domain from step 3.</span></span>

    
    </div>

7.  <span data-ttu-id="61a88-129">Щелкните правой кнопкой название SIP-домена, затем **Новый псевдоним (CNAME)**.</span><span class="sxs-lookup"><span data-stu-id="61a88-129">Right-click the SIP domain name, and then click **New Alias (CNAME)**.</span></span>

8.  <span data-ttu-id="61a88-130">В **Имя псевдонима**, введите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="61a88-130">In **Alias name**, type one of the following:</span></span>
    
      - <span data-ttu-id="61a88-131">Для внутренней DNS-записи, введите lyncdiscoverinternal в качестве имени узла для URL-адреса внутренней службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="61a88-131">For an internal DNS record, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>
    
      - <span data-ttu-id="61a88-132">Для внешней DNS-записи, введите lyncdiscover в качестве имени узла для URL-адреса внешней службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="61a88-132">For an external DNS record, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="61a88-133">В поле **Полное доменное имя для целевого узла**, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="61a88-133">In **Fully qualified domain name (FQDN) for target host**, do one of the following:</span></span>
    
      - <span data-ttu-id="61a88-134">Для внутренней DNS-записи введите или выберите полное доменное имя внутренних веб-служб для пула директоров (например, lyncwebdir01. contoso. local), а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="61a88-134">For an internal DNS record, type or browse to the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local), and then click **OK**.</span></span>
    
      - <span data-ttu-id="61a88-135">Для внешней записи DNS введите или выберите полное доменное имя внешних веб-служб для пула директоров (например, lyncwebextdir.contoso.com), а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="61a88-135">For an external DNS record, type or browse to the external Web Services FQDN for your Director pool (for example, lyncwebextdir.contoso.com), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="61a88-136">Если вы не используете директор, используйте полное доменное имя внутренних и внешних веб-служб для пула переднего плана или, для одного сервера, полное доменное имя сервера переднего плана или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="61a88-136">If you do not use a Director, use the internal and external Web Services FQDN for the Front End pool, or, for a single server, the FQDN for the Front End Server or Standard Edition server.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="61a88-137">Необходимо создать новую запись CNAME автообнаружения в зоне прямого просмотра для каждого домена SIP, который поддерживается в среде Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="61a88-137">You must create a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-dns-a-records"></a><span data-ttu-id="61a88-138">Создание записей DNS A</span><span class="sxs-lookup"><span data-stu-id="61a88-138">To create DNS A records</span></span>

1.  <span data-ttu-id="61a88-139">Выполните вход на DNS-сервер следующим образом:</span><span class="sxs-lookup"><span data-stu-id="61a88-139">Log on to a DNS server as follows:</span></span>
    
      - <span data-ttu-id="61a88-140">Чтобы создать внутреннюю DNS-запись, выполните вход на DNS-сервер вашей сети как член группы администраторов домена или член группы DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="61a88-140">To create an internal DNS record, log on to a DNS server in your network as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
    
      - <span data-ttu-id="61a88-141">Чтобы создать внешнюю DNS-запись, подключитесь к общедоступному поставщику услуг DNS или внешнему DNS-серверу.</span><span class="sxs-lookup"><span data-stu-id="61a88-141">To create an external DNS record, connect to your public DNS provider or external DNS server.</span></span>

2.  <span data-ttu-id="61a88-142">Откройте административную оснастку DNS: нажмите **Пуск**, **Инструменты администратора** и **DNS**.</span><span class="sxs-lookup"><span data-stu-id="61a88-142">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="61a88-143">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="61a88-143">Do one of the following:</span></span>
    
      - <span data-ttu-id="61a88-144">Для внутренней DNS-записи, в дереве консоли DNS-сервера разверните элемент **Зоны прямого просмотра** для вашего домена Active Directory (например, contoso.local).</span><span class="sxs-lookup"><span data-stu-id="61a88-144">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="61a88-145">Этот домен является доменом Active Directory, в котором &nbsp; установлены пул каталогов Lync Server 2013 и пул переднего плана.</span><span class="sxs-lookup"><span data-stu-id="61a88-145">This domain is the Active Directory domain where your Lync Server 2013&nbsp;Director pool and Front End pool are installed.</span></span>

        
        </div>
    
      - <span data-ttu-id="61a88-146">Для внешней DNS-записи в дереве консоли DNS-сервера разверните элемент **Зоны прямого просмотра** для вашего SIP-домена (например, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="61a88-146">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="61a88-147">Убедитесь, что запись узла A (для IPv6, AAAA) существует для пула директоров следующим образом:</span><span class="sxs-lookup"><span data-stu-id="61a88-147">Verify that a host A (for IPv6, AAAA) record exists for your Director pool as follows:</span></span>
    
      - <span data-ttu-id="61a88-148">Для внутренней DNS запись A (для IPv6, AAAA) должна существовать для полного доменного имени внутренних веб-служб для пула директоров (например, lyncwebdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="61a88-148">For an internal DNS record, a host A (for IPv6, AAAA) record should exist for the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local).</span></span>
    
      - <span data-ttu-id="61a88-149">Для внешней DNS-записи запись узла A (для IPv6, AAAA) должна существовать для полного доменного имени внешних веб-служб для пула директоров (например, lyncwebextdir.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="61a88-149">For an external DNS record, a host A (for IPv6, AAAA) record should exist for the external Web Services FQDN for your Director pool (for example, lyncwebextdir.contoso.com).</span></span>

5.  <span data-ttu-id="61a88-150">Убедитесь, что запись узла A (для IPv6, AAAA) существует для пула переднего плана следующим образом:</span><span class="sxs-lookup"><span data-stu-id="61a88-150">Verify that a host A (for IPv6, AAAA) record exists for your Front End pool as follows:</span></span>
    
      - <span data-ttu-id="61a88-151">Для внутренней DNS запись A (для IPv6, AAAA) должна существовать для полного доменного имени внутренних веб-служб для пула переднего плана (например, lyncwebpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="61a88-151">For an internal DNS record, a host A (for IPv6, AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span>
    
      - <span data-ttu-id="61a88-152">Для внешней DNS-записи запись узла A (для IPv6, AAAA) должна существовать для полного доменного имени внешних веб-служб для пула переднего плана (например, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="61a88-152">For an external DNS record, a host A (for IPv6, AAAA) record should exist for the external Web Services FQDN for your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>

6.  <span data-ttu-id="61a88-153">Для внутренней DNS-записи, в дереве консоли DNS-сервера разверните элемент **Зоны прямого просмотра** для вашего SIP-домена (например, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="61a88-153">For an internal DNS record, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="61a88-154">Если создается внешняя DNS-запись, <STRONG>Зоны прямого просмотра</STRONG> уже были развернуты для вашего SIP-домена с шага 3.</span><span class="sxs-lookup"><span data-stu-id="61a88-154">If you are creating an external DNS record, <STRONG>Forward Lookup Zones</STRONG> is already expanded for your SIP domain from step 3.</span></span>

    
    </div>

7.  <span data-ttu-id="61a88-155">Щелкните правой кнопкой имя SIP-домена и нажмите **Новый узел (A или AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="61a88-155">Right-click the SIP domain name, and then click **New Host (A or AAAA)**.</span></span>

8.  <span data-ttu-id="61a88-156">В поле **Имя**, введите имя узла:</span><span class="sxs-lookup"><span data-stu-id="61a88-156">In **Name**, type the host name as follows:</span></span>
    
      - <span data-ttu-id="61a88-157">Для внутренней записи DNS введите lyncdiscoverinternal как имя узла для внутреннего URL-адреса службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="61a88-157">For an internal DNS record, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>
    
      - <span data-ttu-id="61a88-158">Для внешней DNS-записи, введите lyncdiscover в качестве имени узла для URL-адреса внешней службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="61a88-158">For an external DNS record, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="61a88-159">Доменное имя берется из зоны, в которой определена запись, поэтому его не нужно вводить как часть записи A узла.</span><span class="sxs-lookup"><span data-stu-id="61a88-159">The domain name is assumed from the zone in which the record is defined and, therefore, does not need to be entered as part of the A record.</span></span>

    
    </div>

9.  <span data-ttu-id="61a88-160">В поле **IP-адрес**, введите адрес:</span><span class="sxs-lookup"><span data-stu-id="61a88-160">In **IP Address**, type the IP address as follows:</span></span>
    
      - <span data-ttu-id="61a88-161">Для внутренней DNS-записи введите IP-адрес внутренних веб-служб директора (или, если вы используете подсистему балансировки нагрузки, введите виртуальный IP-адрес (VIP) подсистемы балансировки нагрузки директора).</span><span class="sxs-lookup"><span data-stu-id="61a88-161">For an internal DNS record, type the internal Web Services IP address of the Director (or, if you use a load balancer, type the virtual IP (VIP) of the Director load balancer).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="61a88-162">Если вы не используете директор, введите IP-адрес сервера переднего плана или сервера Standard Edition или, если вы используете подсистему балансировки нагрузки, введите виртуальный IP-адрес балансировщика нагрузки пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="61a88-162">If you do not use a Director, type the IP address of the Front End Server or Standard Edition server, or, if you use a load balancer, type the VIP of the Front End pool load balancer.</span></span>

        
        </div>
    
      - <span data-ttu-id="61a88-163">Для внешней DNS-записи, введите внешний или публичный IP-адрес обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="61a88-163">For an external DNS record, type the external or public IP address of the reverse proxy.</span></span>

10. <span data-ttu-id="61a88-164">Нажмите **Добавить узел**, и затем **ОК**.</span><span class="sxs-lookup"><span data-stu-id="61a88-164">Click **Add Host**, and then click **OK**.</span></span>

11. <span data-ttu-id="61a88-165">Чтобы создать дополнительную запись A узла повторите шаги с 8 по 10.</span><span class="sxs-lookup"><span data-stu-id="61a88-165">To create an additional A record, repeat steps 8 through 10.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="61a88-166">Необходимо создать новые lyncdiscover и lyncdiscoverinternal записи в зоне прямого просмотра для каждого домена SIP, который поддерживается в среде Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="61a88-166">You must create a new lyncdiscover and lyncdiscoverinternal A records in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

    
    </div>

12. <span data-ttu-id="61a88-167">После завершения создания записей A узла (для IPv6, AAAA) нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="61a88-167">When you are finished creating A (for IPv6, AAAA) records, click **Done**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

