---
title: 'Lync Server 2013: создание DNS-записей для службы автообнаружения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating DNS records for the Autodiscover Service
ms:assetid: 3756ffe4-c6b1-492d-850e-42a832e06567
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690010(v=OCS.15)
ms:contentKeyID: 48183823
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 921db63f02be50866e6d26cb33007ac8ddbb32eb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198752"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-dns-records-for-the-autodiscover-service-in-lync-server-2013"></a><span data-ttu-id="9c2c0-102">Создание DNS-записей для службы автообнаружения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c2c0-102">Creating DNS records for the Autodiscover Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c2c0-103">_**Последнее изменение темы:** 2014-06-20_</span><span class="sxs-lookup"><span data-stu-id="9c2c0-103">_**Topic Last Modified:** 2014-06-20_</span></span>

<span data-ttu-id="9c2c0-104">Пользователям Lync Mobile потребуется включить автообнаружение, а часть, включающую создание некоторых записей системы доменных имен (DNS).</span><span class="sxs-lookup"><span data-stu-id="9c2c0-104">Your Lync Mobile users will need you to enable autodiscovery, and a part of that involves creating some Domain Name System (DNS) records.</span></span> <span data-ttu-id="9c2c0-105">В зависимости от ваших потребностей вам потребуются следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="9c2c0-105">Depending on your needs, you need the following:</span></span>

  - <span data-ttu-id="9c2c0-106">Внутренняя запись DNS для поддержки мобильных пользователей, подключающихся из сети Организации.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-106">An internal DNS record to support mobile users who’re connecting from within your organization's network.</span></span>

  - <span data-ttu-id="9c2c0-107">Внешняя (или общедоступная) запись DNS для поддержки мобильных пользователей, подключающихся из Интернета.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-107">An external, or public, DNS record to support mobile users who’re connecting from the Internet</span></span>

<span data-ttu-id="9c2c0-108">Почему?</span><span class="sxs-lookup"><span data-stu-id="9c2c0-108">Why both?</span></span> <span data-ttu-id="9c2c0-109">Необходимо создать как внутреннюю, так и внешнюю DNS-запись для каждого домена SIP.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-109">You need to create both an internal DNS record and an external DNS record for each SIP domain.</span></span>

<span data-ttu-id="9c2c0-110">Создаваемые записи DNS могут быть либо записями (ведущими), либо записями CNAME.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-110">The DNS records you create can be either A (host) records or CNAME records.</span></span> <span data-ttu-id="9c2c0-111">Чтобы помочь вам, мы покажем, как создавать эти внутренние и внешние DNS-записи ниже.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-111">To help you out, we’ll walk through how to create these internal and external DNS records below.</span></span> <span data-ttu-id="9c2c0-112">Если вам необходимо прочесть дополнительные сведения о требованиях к DNS для мобильных пользователей, вы можете ознакомиться с [техническими требованиями для мобильных устройств в Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="9c2c0-112">If you need to do some further reading about the DNS requirements for mobile users, you can check out [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

<div>

## <a name="creating-an-internal-dns-cname-record"></a><span data-ttu-id="9c2c0-113">Создание внутренней записи CNAME DNS</span><span class="sxs-lookup"><span data-stu-id="9c2c0-113">Creating an internal DNS CNAME record</span></span>

1.  <span data-ttu-id="9c2c0-114">Чтобы сделать внутреннюю DNS-запись, необходимо войти на DNS-сервер в сети с учетной записью домена, которая является членом группы "Администраторы домена" или членом группы DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-114">To make an internal DNS record, you’ll need to log on to a DNS server in your network with a domain account that’s either a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="9c2c0-115">Откройте административную оснастку DNS: нажмите **Пуск**, **Инструменты администратора** и **DNS**.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-115">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="9c2c0-116">В дереве консоли DNS-сервера разверните узел **зоны прямого просмотра** для домена Active Directory, в котором установлены пул каталогов Lync Server 2013 и пул переднего плана.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-116">In the console tree of the DNS server, expand **Forward Lookup Zones** for the Active Directory domain where your Lync Server 2013 Director pool and Front End pool are installed.</span></span> <span data-ttu-id="9c2c0-117">(например, contoso. local).</span><span class="sxs-lookup"><span data-stu-id="9c2c0-117">(for example, contoso.local).</span></span>

4.  <span data-ttu-id="9c2c0-118">Проверьте, существует ли запись A (AAAA для IPv6) для пула директоров для внутренней DNS-записи, должна существовать запись узла A для полного доменного имени (FQDN) внутренних веб-служб для пула директоров (например, lyncwebdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="9c2c0-118">Check and see if a host A (AAAA for IPv6) record exists for your Director pool for an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span> <span data-ttu-id="9c2c0-119">Если это не так, пул директоров не используется, и вам потребуется использовать полное доменное имя для пула переднего плана или даже полное доменное имя сервера, если это настроено.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-119">If it’s not here, you may not be using a Director pool, and you’ll need to use the FQDN for your Front End pool or even a single server FQDN, if that’s your setup.</span></span>

5.  <span data-ttu-id="9c2c0-120">Учитывая это, проверьте, существует ли запись A (AAAA для IPv6) для пула переднего плана для внутренней DNS-записи, должна существовать запись узла A (или AAAA) для полного доменного имени внутренних веб-служб для пула переднего плана (например, , lyncwebpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="9c2c0-120">Keeping that in mind, check and see if a host A (AAAA for IPv6) record exists for your Front End pool for an internal DNS record, a host A (or AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span> <span data-ttu-id="9c2c0-121">В противном случае необходимо отметить полное доменное имя сервера переднего плана или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-121">If it doesn’t, you’ll need to make note of the FQDN for the Front End Server or Standard Edition server.</span></span>

6.  <span data-ttu-id="9c2c0-122">Когда вы узнаете, какие записи узла A (или AAAA) существуют, в дереве консоли DNS-сервера разверните узел **зоны прямого просмотра** для домена SIP (например, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="9c2c0-122">Once you know what host A (or AAAA) records exist, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

7.  <span data-ttu-id="9c2c0-123">Щелкните правой кнопкой название SIP-домена, затем **Новый псевдоним (CNAME)**.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-123">Right-click the SIP domain name, and then click **New Alias (CNAME)**.</span></span>

8.  <span data-ttu-id="9c2c0-124">В поле **имя псевдонима**введите lyncdiscoverinternal в качестве имени узла для внутреннего URL-адреса службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-124">In **Alias name**, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="9c2c0-125">В поле полное **доменное имя (FQDN) конечного узла**введите или выберите полное доменное имя внутренних веб-служб для пула директоров (например, lyncwebdir01. contoso. local), а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-125">In **Fully qualified domain name (FQDN) for target host**, type or browse to the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local) and then click **OK**.</span></span>

10. <span data-ttu-id="9c2c0-126">Необходимо создать новую запись CNAME автообнаружения в зоне прямого просмотра для каждого домена SIP, который поддерживается в среде Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-126">You must create a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

</div>

<div>

## <a name="creating-an-external-dns-cname-record"></a><span data-ttu-id="9c2c0-127">Создание внешней записи CNAME DNS</span><span class="sxs-lookup"><span data-stu-id="9c2c0-127">Creating an external DNS CNAME record</span></span>

1.  <span data-ttu-id="9c2c0-128">Чтобы создать внешнюю DNS-запись CNAME, необходимо подключиться к общедоступному поставщику услуг DNS и выполнить действия, описанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-128">To create an external DNS CNAME record, you’re going to need to connect to your public DNS provider, and then follow our steps.</span></span> <span data-ttu-id="9c2c0-129">Мы не можем точно описать, где вы находитесь в среде поставщика DNS, так как у вас могут быть различные способы управления внешней DNS, но мы надеемся, что эти действия помогут вам.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-129">We can’t describe exactly where you’re going in your DNS provider’s environment as there may be different ways of managing your external DNS, but we hope these steps help.</span></span>

2.  <span data-ttu-id="9c2c0-130">Войдите в свой внешний поставщик DNS с помощью учетной записи, которая может создавать записи DNS в этой среде.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-130">Log into your external DNS provider with an account that can create DNS records in that environment.</span></span>

3.  <span data-ttu-id="9c2c0-131">Для этой среды уже должен быть создан домен SIP.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-131">You should have a SIP domain created for this environment already.</span></span> <span data-ttu-id="9c2c0-132">Разверните **зону прямого просмотра** для этого домена SIP или выберите ее в зависимости от используемого внешнего интерфейса DNS.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-132">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise select it depending on the external DNS interface being used.</span></span>

4.  <span data-ttu-id="9c2c0-133">Вы уже видите запись узла A (AAAA для IPv6) для пула директоров (например, lyncwebexdir01.contoso.com), поэтому убедитесь, что она есть.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-133">You should already see a host A (AAAA for IPv6) record for your Director pool (such as lyncwebexdir01.contoso.com), so confirm that it’s there.</span></span> <span data-ttu-id="9c2c0-134">В противном случае пул директоров может не использоваться.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-134">If it’s not, then you may not be using a Director pool.</span></span> <span data-ttu-id="9c2c0-135">В этом случае необходимо использовать полное доменное имя интерфейсного пула или, если это делается для одного сервера, для сервера переднего плана или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-135">If that’s the case, you’ll need to use the FQDN of your Front End Pool, or if you’re doing this for a single server, for your Front-End server or Standard Edition server.</span></span>

5.  <span data-ttu-id="9c2c0-136">Кроме того, необходимо подтвердить, что запись узла A (AAAA для IPv6) существует для полного доменного имени (FQDN) для внешнего доменного пула (например, lyncwebextpool01.contoso.com), или полное доменное имя для односерверного полного доменного пула, если у вас нет интерфейсного пула.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-136">You’ll also need to confirm that a host A (AAAA for IPv6) record exists for your external Web Services Fully Qualified Domain Name (FQDN) for your Front End pool (such as lyncwebextpool01.contoso.com), or a FQDN for your single-server FQDN if you have no Front End pool.</span></span> <span data-ttu-id="9c2c0-137">Как отмечалось на предыдущем шаге, вам потребуется это так, если у вас нет пула директоров.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-137">As noted in the previous step, you’ll need this below if you don’t have a Director pool.</span></span>

6.  <span data-ttu-id="9c2c0-138">Теперь в соответствующем формате для внешнего поставщика DNS выберите вариант для создания **нового псевдонима (CNAME)** (это может быть параметр меню или ссылка в зависимости от формата поставщика DNS).</span><span class="sxs-lookup"><span data-stu-id="9c2c0-138">Now, in the appropriate format for your external DNS provider, choose the option for creating a **New Alias (CNAME)** (this may be a menu option or a link, depending on the format of the DNS provider).</span></span>

7.  <span data-ttu-id="9c2c0-139">В качестве имени узла для внутреннего URL-адреса службы автообнаружения должно быть определено текстовое поле **имя псевдонима** .</span><span class="sxs-lookup"><span data-stu-id="9c2c0-139">There should be some form of **Alias name** text box as with the internal DNS, you should enter lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

8.  <span data-ttu-id="9c2c0-140">Кроме того, должно быть определено полное **доменное имя (FQDN) для текстового поля конечного узла** , где вы вводите полное доменное имя внешних веб-служб для пула директоров (например, lyncwebexdir01.contoso.com), а затем нажмите кнопку ОК или сделайте любое действие во внешней службе DNS, чтобы принять создание этой записи.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-140">There should also be some form of a **Fully qualified domain name (FQDN) for target host** text box, here’s where you’ll enter the external Web Services FQDN for your Director pool (for example, lyncwebexdir01.contoso.com) and then click OK or take whatever action in the external DNS to accept the creation of this entry.</span></span> <span data-ttu-id="9c2c0-141">Как отмечалось на шаге 4, выше, если у вас нет пула директоров, то необходимо использовать полное доменное имя пула переднего плана или односерверное полное доменное имя, которое необходимо настроить.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-141">As noted in Step 4, above, if you don’t have a Director pool, you’ll need to use the Front End pool FQDN or the single-server FQDN you have set up, as appropriate.</span></span>

9.  <span data-ttu-id="9c2c0-142">Необходимо создать новую запись CNAME автообнаружения в зоне прямого просмотра для каждого домена SIP, поддерживаемого в среде Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-142">You’ll need to make a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that’s supported in your Lync 2013 environment.</span></span>

</div>

<div>

## <a name="creating-an-internal-dns-a-record"></a><span data-ttu-id="9c2c0-143">Создание внутренней записи A DNS</span><span class="sxs-lookup"><span data-stu-id="9c2c0-143">Creating an internal DNS A record</span></span>

1.  <span data-ttu-id="9c2c0-144">Чтобы сделать внутреннюю DNS-запись, выполните вход на DNS-сервер в сети с учетной записью домена, которая является членом группы "Администраторы домена" или членом группы DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-144">To make an internal DNS record, log on to a DNS server in your network with a domain account that’s a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="9c2c0-145">Откройте административную оснастку DNS: нажмите **Пуск**, **Инструменты администратора** и **DNS**.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-145">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="9c2c0-146">Для внутренней DNS-записи в дереве консоли DNS-сервера разверните узел **зоны прямого просмотра** для домена Active Directory (например, contoso. local), где установлены пул пула и интерфейсного пула Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-146">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local) where your Lync Server 2013 Director pool and Front End pool are installed.</span></span>

4.  <span data-ttu-id="9c2c0-147">Проверьте, существует ли запись A (AAAA для IPv6) для пула директоров для внутренней DNS-записи, должна существовать запись узла A для полного доменного имени (FQDN) внутренних веб-служб для пула директоров (например, lyncwebdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="9c2c0-147">Check and see if a host A (AAAA for IPv6) record exists for your Director pool for an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span> <span data-ttu-id="9c2c0-148">Если это не так, пул директоров, возможно, не используется, и вам потребуется использовать IP-адрес для пула переднего плана или даже IP-адрес одного сервера, если это ваша Настройка.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-148">If it’s not here, you may not be using a Director pool, and you’ll need to use the IP address for your Front End pool or even a single server IP address, if that’s your setup.</span></span>

5.  <span data-ttu-id="9c2c0-149">Учитывая это, проверьте, существует ли запись A (AAAA для IPv6) для пула переднего плана для внутренней DNS-записи, должна существовать запись узла A (или AAAA) для полного доменного имени внутренних веб-служб для пула переднего плана (например, , lyncwebpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="9c2c0-149">Keeping that in mind, check and see if a host A (AAAA for IPv6) record exists for your Front End pool for an internal DNS record, a host A (or AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span> <span data-ttu-id="9c2c0-150">В противном случае необходимо заметку IP-адреса для сервера переднего плана или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-150">If it doesn’t, you’ll need to make note of the IP address for the Front End Server or Standard Edition server.</span></span>

6.  <span data-ttu-id="9c2c0-151">Когда вы узнаете, какие записи узла A (или AAAA) существуют, в дереве консоли DNS-сервера разверните узел **зоны прямого просмотра** для домена SIP (например, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="9c2c0-151">Once you know what host A (or AAAA) records exist, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

7.  <span data-ttu-id="9c2c0-152">Щелкните правой кнопкой имя SIP-домена и нажмите **Новый узел (A или AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-152">Right-click the SIP domain name, and then click **New Host (A or AAAA)**.</span></span>

8.  <span data-ttu-id="9c2c0-153">В поле **имя**введите lyncdiscoverinternal в качестве имени узла для внутреннего URL-адреса службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-153">In **Name**, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="9c2c0-154">В поле **IP-адрес**введите IP-адрес внутренних веб-служб директора (или, если вы используете подсистему балансировки нагрузки, введите виртуальный IP-адрес (VIP) подсистемы балансировки нагрузки директора).</span><span class="sxs-lookup"><span data-stu-id="9c2c0-154">In **IP Address**, type the internal Web Services IP address of the Director (or, if you use a load balancer, type the virtual IP (VIP) of the Director load balancer).</span></span> <span data-ttu-id="9c2c0-155">Как отмечалось на шаге 4 выше, если вы не используете директор, может потребоваться ввести IP-адрес сервера переднего плана или сервера Standard Edition или, если вы используете подсистему балансировки нагрузки, введите виртуальный IP-адрес балансировщика нагрузки пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-155">As noted in Step 4 above, if you aren’t using a Director, you may need to enter the IP address of the Front End Server or Standard Edition server or, if you use a load balancer, type the VIP of the Front End pool load balancer.</span></span>

10. <span data-ttu-id="9c2c0-156">Щелкните **Добавить узел**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-156">Click **Add Host**, and then click **OK**.</span></span>

11. <span data-ttu-id="9c2c0-157">Чтобы создать дополнительную запись A или AAAA, повторите шаги 8 – 10, учитывая, что вам потребуется создать новые записи A или AAAA для автообнаружения в зоне прямого просмотра каждого домена SIP, поддерживаемого в среде Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-157">To create an additional A or AAAA record, repeat steps 8 through 10, keeping in mind that you’ll need to create new Autodiscover A or AAAA records in the forward lookup zone of each SIP domain that’s supported in your Lync Server 2013 environment.</span></span>

12. <span data-ttu-id="9c2c0-158">После завершения создания записей A узла (для IPv6, AAAA) нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-158">When you are finished creating A (for IPv6, AAAA) records, click **Done**.</span></span>

</div>

<div>

## <a name="creating-an-external-dns-a-record"></a><span data-ttu-id="9c2c0-159">Создание записи A внешней DNS</span><span class="sxs-lookup"><span data-stu-id="9c2c0-159">Creating an external DNS A record</span></span>

1.  <span data-ttu-id="9c2c0-160">Чтобы создать внешнюю DNS-запись, подключитесь к общедоступному поставщику услуг DNS и выполните действия, описанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-160">To create an external DNS record, connect to your public DNS provider, and then follow our steps.</span></span> <span data-ttu-id="9c2c0-161">Мы не можем точно описать, где вы находитесь в среде поставщика DNS, так как у вас могут быть различные способы управления внешней DNS, но мы надеемся, что эти действия помогут вам.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-161">We can’t describe exactly where you’re going in your DNS provider’s environment as there may be different ways of managing your external DNS, but we hope these steps help.</span></span>

2.  <span data-ttu-id="9c2c0-162">Вам потребуется войти в систему с учетной записью, которая может создавать записи DNS в этой среде.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-162">You’ll need to be logged in as an account that can create DNS records in that environment.</span></span>

3.  <span data-ttu-id="9c2c0-163">Для внешней DNS-записи в дереве консоли DNS-сервера разверните элемент **Зоны прямого просмотра** для вашего SIP-домена (например, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="9c2c0-163">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span> <span data-ttu-id="9c2c0-164">Для внешней DNS-записи в дереве консоли DNS-сервера разверните элемент **Зоны прямого просмотра** для вашего SIP-домена (например, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="9c2c0-164">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="9c2c0-165">Вы уже видите запись узла A (AAAA для IPv6) для своего пула директоров (например, lyncwebexdir01.contoso.com), поэтому убедитесь, что она есть и каков IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-165">You should already see a host A (AAAA for IPv6) record for your Director pool (such as lyncwebexdir01.contoso.com), so confirm that it’s there and what the IP address is.</span></span> <span data-ttu-id="9c2c0-166">В противном случае пул директоров может не использоваться.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-166">If it’s not, then you may not be using a Director pool.</span></span> <span data-ttu-id="9c2c0-167">В этом случае вам потребуется использовать IP-адрес пула переднего плана или, если это делается, для одного сервера, для сервера переднего плана или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-167">If that’s the case, you’ll need to use the IP address of your Front End Pool, or if you’re doing this for a single server, for your Front-End server or Standard Edition server.</span></span> <span data-ttu-id="9c2c0-168">Имейте в виду, что серверы могут также находиться за пределами подсистемы балансировки нагрузки или с помощью обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-168">Keep in mind that your servers may also be behind a load-balancer, or using a reverse proxy.</span></span> <span data-ttu-id="9c2c0-169">Запишите IP-адреса и выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-169">Make note of the IP addresses as well for following the steps below.</span></span>

5.  <span data-ttu-id="9c2c0-170">Кроме того, необходимо подтвердить, что запись узла A (AAAA для IPv6) существует для полного доменного имени внешних веб-служб (FQDN) для пула переднего плана (например, lyncwebextpool01.contoso.com) или IP-адреса для установки на односерверной версии Lync Интерфейсный пул отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-170">You’ll also need to confirm that a host A (AAAA for IPv6) record exists for your external Web Services Fully Qualified Domain Name (FQDN) for your Front End pool (such as lyncwebextpool01.contoso.com), or an IP address for your single-server Lync installation if you have no Front End pool.</span></span> <span data-ttu-id="9c2c0-171">Как отмечалось на предыдущем шаге, вам потребуется это так, если у вас нет пула директоров.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-171">As noted in the previous step, you’ll need this below if you don’t have a Director pool.</span></span>

6.  <span data-ttu-id="9c2c0-172">Теперь в соответствующем формате для внешнего поставщика DNS выберите вариант для создания **нового узла a или AAAA** (это может быть пункт меню или ссылка в зависимости от формата поставщика DNS).</span><span class="sxs-lookup"><span data-stu-id="9c2c0-172">Now, in the appropriate format for your external DNS provider, choose the option for creating a **New Host A or AAAA** (this may be a menu option or a link, depending on the format of the DNS provider).</span></span>

7.  <span data-ttu-id="9c2c0-173">Должно быть место для ввода **имени**, введите lyncdiscover в качестве имени узла для внешнего URL-адреса службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-173">There should be a place to enter a **Name**, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

8.  <span data-ttu-id="9c2c0-174">Кроме того, должно быть поле **IP-адрес** , где вы вводите IP-адрес для пула директоров (например, lyncwebexdir01.contoso.com) или IP-адрес балансировщика нагрузки пула (или IP-адрес обратного прокси-сервера, который ведет себя), а затем нажмите кнопку ОК или сделайте любое действие во внешней службе DNS, чтобы принять создание этой записи.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-174">There should also be an **IP Address** text box, here’s where you’ll enter the IP for your for your Director pool (for example, lyncwebexdir01.contoso.com) or possibly the IP of your pool’s load balancer (or a reverse proxy IP that leads to the same) and then click OK or take whatever action in the external DNS to accept the creation of this entry.</span></span> <span data-ttu-id="9c2c0-175">Как отмечалось на шаге 4, выше, если у вас нет пула директоров, то необходимо использовать IP-адрес пула переднего плана или односерверный IP-адрес, который был настроен соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-175">As noted in Step 4, above, if you don’t have a Director pool, you’ll need to use the Front End pool IP address or the single-server IP address you have set up, as appropriate.</span></span>

9.  <span data-ttu-id="9c2c0-176">Необходимо создать новую запись A или AAAA для автообнаружения в зоне прямого просмотра для каждого домена SIP, поддерживаемого в среде Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="9c2c0-176">You’ll need to make a new Autodiscover A or AAAA record in the forward lookup zone of each SIP domain that’s supported in your Lync 2013 environment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

