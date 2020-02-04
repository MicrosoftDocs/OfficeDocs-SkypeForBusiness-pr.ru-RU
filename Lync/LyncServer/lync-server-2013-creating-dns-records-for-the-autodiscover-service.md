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
ms.openlocfilehash: d91c67620a87fdd91a1755592175e8cf2964d259
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-dns-records-for-the-autodiscover-service-in-lync-server-2013"></a><span data-ttu-id="50305-102">Создание DNS-записей для службы автообнаружения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50305-102">Creating DNS records for the Autodiscover Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50305-103">_**Тема последнего изменения:** 2014-06-20_</span><span class="sxs-lookup"><span data-stu-id="50305-103">_**Topic Last Modified:** 2014-06-20_</span></span>

<span data-ttu-id="50305-104">Пользователям Lync Mobile потребуется включить функцию автообнаружение, и в этом случае будет создаваться некоторые DNS-записи.</span><span class="sxs-lookup"><span data-stu-id="50305-104">Your Lync Mobile users will need you to enable autodiscovery, and a part of that involves creating some Domain Name System (DNS) records.</span></span> <span data-ttu-id="50305-105">В зависимости от потребностей вам потребуется следующее:</span><span class="sxs-lookup"><span data-stu-id="50305-105">Depending on your needs, you need the following:</span></span>

  - <span data-ttu-id="50305-106">Внутренняя запись DNS для поддержки мобильных пользователей, которые подключаются к сети Организации.</span><span class="sxs-lookup"><span data-stu-id="50305-106">An internal DNS record to support mobile users who’re connecting from within your organization's network.</span></span>

  - <span data-ttu-id="50305-107">Внешняя (или общедоступная) запись DNS для поддержки мобильных пользователей, подключающихся из Интернета;</span><span class="sxs-lookup"><span data-stu-id="50305-107">An external, or public, DNS record to support mobile users who’re connecting from the Internet</span></span>

<span data-ttu-id="50305-108">Зачем обе?</span><span class="sxs-lookup"><span data-stu-id="50305-108">Why both?</span></span> <span data-ttu-id="50305-109">Для каждого домена SIP необходимо создать как внутреннюю запись DNS, так и внешнюю запись DNS.</span><span class="sxs-lookup"><span data-stu-id="50305-109">You need to create both an internal DNS record and an external DNS record for each SIP domain.</span></span>

<span data-ttu-id="50305-110">Создаваемые записи DNS могут быть либо записями (ведущими), либо записями CNAME.</span><span class="sxs-lookup"><span data-stu-id="50305-110">The DNS records you create can be either A (host) records or CNAME records.</span></span> <span data-ttu-id="50305-111">Чтобы помочь вам, мы рассмотрим, как создать эти внутренние и внешние записи DNS ниже.</span><span class="sxs-lookup"><span data-stu-id="50305-111">To help you out, we’ll walk through how to create these internal and external DNS records below.</span></span> <span data-ttu-id="50305-112">Дополнительные сведения о требованиях к DNS для мобильных пользователей вы можете найти [в статье технические требования для мобильных устройств в Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="50305-112">If you need to do some further reading about the DNS requirements for mobile users, you can check out [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

<div>

## <a name="creating-an-internal-dns-cname-record"></a><span data-ttu-id="50305-113">Создание внутренней записи CNAME DNS</span><span class="sxs-lookup"><span data-stu-id="50305-113">Creating an internal DNS CNAME record</span></span>

1.  <span data-ttu-id="50305-114">Чтобы создать внутреннюю DNS-запись, необходимо войти на DNS-сервер в сети с учетной записью домена, которая является либо членом группы администраторов домена, либо членом группы Днсадминс.</span><span class="sxs-lookup"><span data-stu-id="50305-114">To make an internal DNS record, you’ll need to log on to a DNS server in your network with a domain account that’s either a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="50305-115">Откройте оснастку администрирование DNS: нажмите кнопку **Пуск**, выберите пункт **Администрирование**, а затем — **DNS**.</span><span class="sxs-lookup"><span data-stu-id="50305-115">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="50305-116">В дереве консоли DNS-сервера разверните раздел **зоны прямого просмотра** для домена Active Directory, на котором установлен пул каталогов Lync Server 2013 и пул внешних интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="50305-116">In the console tree of the DNS server, expand **Forward Lookup Zones** for the Active Directory domain where your Lync Server 2013 Director pool and Front End pool are installed.</span></span> <span data-ttu-id="50305-117">(например, contoso. local).</span><span class="sxs-lookup"><span data-stu-id="50305-117">(for example, contoso.local).</span></span>

4.  <span data-ttu-id="50305-118">Проверьте и посмотрите, есть ли в вашем пуле для внутренней записи DNS запись A (AAAA для IPv6), а для своего пула используется полное доменное имя (например, lyncwebdir01. contoso. local) для своего режиссера.</span><span class="sxs-lookup"><span data-stu-id="50305-118">Check and see if a host A (AAAA for IPv6) record exists for your Director pool for an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span> <span data-ttu-id="50305-119">Если это не так, то, возможно, вы не используете пул режиссеров, и вам потребуется использовать полное доменное имя для пула переднего плана или даже одно полное доменное имя, если это ваша Настройка.</span><span class="sxs-lookup"><span data-stu-id="50305-119">If it’s not here, you may not be using a Director pool, and you’ll need to use the FQDN for your Front End pool or even a single server FQDN, if that’s your setup.</span></span>

5.  <span data-ttu-id="50305-120">Учитывая это, проверьте, есть ли у вас запись A (AAAA для IPv6) для своего пула переднего плана для внутренней записи DNS, должна существовать запись узла A (или AAAA) для внутреннего доменного имени внутренней веб-службы для пула переднего плана (например, , lyncwebpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="50305-120">Keeping that in mind, check and see if a host A (AAAA for IPv6) record exists for your Front End pool for an internal DNS record, a host A (or AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span> <span data-ttu-id="50305-121">Если это не так, вам нужно будет заметку полного доменного имени сервера переднего плана или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="50305-121">If it doesn’t, you’ll need to make note of the FQDN for the Front End Server or Standard Edition server.</span></span>

6.  <span data-ttu-id="50305-122">После того как вы узнаете, какие записи узла A (или AAAA) существуют, в дереве консоли сервера DNS разверните раздел **зоны прямого просмотра** для вашего домена SIP (например, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="50305-122">Once you know what host A (or AAAA) records exist, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

7.  <span data-ttu-id="50305-123">Щелкните имя домена SIP правой кнопкой мыши и выберите команду **создать псевдоним (CNAME)**.</span><span class="sxs-lookup"><span data-stu-id="50305-123">Right-click the SIP domain name, and then click **New Alias (CNAME)**.</span></span>

8.  <span data-ttu-id="50305-124">В поле **Alias Name (имя псевдонима**) введите линкдисковеринтернал в качестве имени узла для URL-адреса внутренней службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="50305-124">In **Alias name**, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="50305-125">В **качестве полного доменного имени (FQDN) для целевого узла**введите или найдите полное доменное имя внутренних веб-служб для вашего пула (например, lyncwebdir01. contoso. local) и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="50305-125">In **Fully qualified domain name (FQDN) for target host**, type or browse to the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local) and then click **OK**.</span></span>

10. <span data-ttu-id="50305-126">В зоне прямого просмотра каждого домена SIP, который поддерживается в среде Lync Server 2013, необходимо создать новую запись автообнаружения CNAME.</span><span class="sxs-lookup"><span data-stu-id="50305-126">You must create a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

</div>

<div>

## <a name="creating-an-external-dns-cname-record"></a><span data-ttu-id="50305-127">Создание внешней записи CNAME DNS</span><span class="sxs-lookup"><span data-stu-id="50305-127">Creating an external DNS CNAME record</span></span>

1.  <span data-ttu-id="50305-128">Для создания внешней записи CNAME DNS необходимо подключиться к общедоступному поставщику услуг DNS и выполнить необходимые действия.</span><span class="sxs-lookup"><span data-stu-id="50305-128">To create an external DNS CNAME record, you’re going to need to connect to your public DNS provider, and then follow our steps.</span></span> <span data-ttu-id="50305-129">Мы не можем описать, где вы находитесь в среде вашего поставщика услуг DNS, так как у вас могут быть различные способы управления внешней службой DNS, но мы надеемся, что эти действия помогут вам.</span><span class="sxs-lookup"><span data-stu-id="50305-129">We can’t describe exactly where you’re going in your DNS provider’s environment as there may be different ways of managing your external DNS, but we hope these steps help.</span></span>

2.  <span data-ttu-id="50305-130">Войдите в свой внешний поставщик DNS с помощью учетной записи, которая может создавать записи DNS в этой среде.</span><span class="sxs-lookup"><span data-stu-id="50305-130">Log into your external DNS provider with an account that can create DNS records in that environment.</span></span>

3.  <span data-ttu-id="50305-131">Для этой среды уже должен быть создан домен SIP.</span><span class="sxs-lookup"><span data-stu-id="50305-131">You should have a SIP domain created for this environment already.</span></span> <span data-ttu-id="50305-132">Разверните **зону прямого просмотра** для этого домена SIP или выберите его в зависимости от того, какой внешний интерфейс DNS используется.</span><span class="sxs-lookup"><span data-stu-id="50305-132">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise select it depending on the external DNS interface being used.</span></span>

4.  <span data-ttu-id="50305-133">Вы уже должны видеть запись узла A (AAAA для IPv6) для своего пула (например, lyncwebexdir01.contoso.com), поэтому убедитесь, что она есть.</span><span class="sxs-lookup"><span data-stu-id="50305-133">You should already see a host A (AAAA for IPv6) record for your Director pool (such as lyncwebexdir01.contoso.com), so confirm that it’s there.</span></span> <span data-ttu-id="50305-134">Если это не так, вы, возможно, используете пул режиссеров.</span><span class="sxs-lookup"><span data-stu-id="50305-134">If it’s not, then you may not be using a Director pool.</span></span> <span data-ttu-id="50305-135">В этом случае вам потребуется использовать полное доменное имя своего пула переднего плана или, если это делается для одного сервера, на сервере переднего плана или стандартном сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="50305-135">If that’s the case, you’ll need to use the FQDN of your Front End Pool, or if you’re doing this for a single server, for your Front-End server or Standard Edition server.</span></span>

5.  <span data-ttu-id="50305-136">Кроме того, вам нужно подтвердить, что в качестве внешнего доменного имени (например, lyncwebextpool01.contoso.com) для внешней веб-службы в пуле, а также в том случае, если у вас нет пула переднего плана, существует запись узла A (AAAA для IPv6).</span><span class="sxs-lookup"><span data-stu-id="50305-136">You’ll also need to confirm that a host A (AAAA for IPv6) record exists for your external Web Services Fully Qualified Domain Name (FQDN) for your Front End pool (such as lyncwebextpool01.contoso.com), or a FQDN for your single-server FQDN if you have no Front End pool.</span></span> <span data-ttu-id="50305-137">Как отмечалось на предыдущем этапе, вам понадобится это, если у вас нет директора пула.</span><span class="sxs-lookup"><span data-stu-id="50305-137">As noted in the previous step, you’ll need this below if you don’t have a Director pool.</span></span>

6.  <span data-ttu-id="50305-138">В соответствии с форматом внешнего поставщика услуг DNS выберите вариант создания **нового псевдонима (CNAME)** (это может быть параметр меню или ссылка в зависимости от формата поставщика DNS).</span><span class="sxs-lookup"><span data-stu-id="50305-138">Now, in the appropriate format for your external DNS provider, choose the option for creating a **New Alias (CNAME)** (this may be a menu option or a link, depending on the format of the DNS provider).</span></span>

7.  <span data-ttu-id="50305-139">В качестве псевдонима для внутреннего URL-адреса службы автоавтообнаружения должно быть задано текстовое поле с **именем alias Name** (имя узла).</span><span class="sxs-lookup"><span data-stu-id="50305-139">There should be some form of **Alias name** text box as with the internal DNS, you should enter lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

8.  <span data-ttu-id="50305-140">Кроме того, должно быть задано полное **доменное имя (FQDN) для текстового поля target Host** (например, lyncwebexdir01.contoso.com), а затем нажмите кнопку ОК или сделайте любое действие в ВНЕШНем DNS, чтобы принять его на создание.</span><span class="sxs-lookup"><span data-stu-id="50305-140">There should also be some form of a **Fully qualified domain name (FQDN) for target host** text box, here’s where you’ll enter the external Web Services FQDN for your Director pool (for example, lyncwebexdir01.contoso.com) and then click OK or take whatever action in the external DNS to accept the creation of this entry.</span></span> <span data-ttu-id="50305-141">Как указано в действии 4, выше, если у вас нет режиссера, вы должны использовать пул доменных имен переднего плана или одно и то же полное доменное имя (FQDN) для одного сервера, если это уместно.</span><span class="sxs-lookup"><span data-stu-id="50305-141">As noted in Step 4, above, if you don’t have a Director pool, you’ll need to use the Front End pool FQDN or the single-server FQDN you have set up, as appropriate.</span></span>

9.  <span data-ttu-id="50305-142">Вам потребуется создать новую запись автообнаружения CNAME в зоне прямого просмотра каждого домена SIP, который поддерживается в среде Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="50305-142">You’ll need to make a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that’s supported in your Lync 2013 environment.</span></span>

</div>

<div>

## <a name="creating-an-internal-dns-a-record"></a><span data-ttu-id="50305-143">Создание записи внутренней DNS</span><span class="sxs-lookup"><span data-stu-id="50305-143">Creating an internal DNS A record</span></span>

1.  <span data-ttu-id="50305-144">Чтобы сделать внутреннюю DNS-запись, войдите на DNS-сервер в сети с учетной записью домена, которая является членом группы администраторов домена или участником группы Днсадминс.</span><span class="sxs-lookup"><span data-stu-id="50305-144">To make an internal DNS record, log on to a DNS server in your network with a domain account that’s a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="50305-145">Откройте оснастку администрирование DNS: нажмите кнопку **Пуск**, выберите пункт **Администрирование**, а затем — **DNS**.</span><span class="sxs-lookup"><span data-stu-id="50305-145">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="50305-146">Для внутренней записи DNS в дереве консоли DNS-сервера разверните **зоны прямого просмотра** для домена службы каталогов Active Directory (например, contoso. local), где установлен пул ресурсов Lync Server 2013 и пул внешних интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="50305-146">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local) where your Lync Server 2013 Director pool and Front End pool are installed.</span></span>

4.  <span data-ttu-id="50305-147">Проверьте и посмотрите, есть ли в вашем пуле для внутренней записи DNS запись A (AAAA для IPv6), а для своего пула используется полное доменное имя (например, lyncwebdir01. contoso. local) для своего режиссера.</span><span class="sxs-lookup"><span data-stu-id="50305-147">Check and see if a host A (AAAA for IPv6) record exists for your Director pool for an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span> <span data-ttu-id="50305-148">Если это не так, возможно, вы не используете пул режиссеров, и вам потребуется использовать IP-адрес для пула переднего плана или даже IP-адрес сервера, если это ваша Настройка.</span><span class="sxs-lookup"><span data-stu-id="50305-148">If it’s not here, you may not be using a Director pool, and you’ll need to use the IP address for your Front End pool or even a single server IP address, if that’s your setup.</span></span>

5.  <span data-ttu-id="50305-149">Учитывая это, проверьте, есть ли у вас запись A (AAAA для IPv6) для своего пула переднего плана для внутренней записи DNS, должна существовать запись узла A (или AAAA) для внутреннего доменного имени внутренней веб-службы для пула переднего плана (например, , lyncwebpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="50305-149">Keeping that in mind, check and see if a host A (AAAA for IPv6) record exists for your Front End pool for an internal DNS record, a host A (or AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span> <span data-ttu-id="50305-150">Если это не так, необходимо заметку IP-адреса для сервера переднего плана или стандартного выпуска Standard.</span><span class="sxs-lookup"><span data-stu-id="50305-150">If it doesn’t, you’ll need to make note of the IP address for the Front End Server or Standard Edition server.</span></span>

6.  <span data-ttu-id="50305-151">После того как вы узнаете, какие записи узла A (или AAAA) существуют, в дереве консоли сервера DNS разверните раздел **зоны прямого просмотра** для вашего домена SIP (например, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="50305-151">Once you know what host A (or AAAA) records exist, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

7.  <span data-ttu-id="50305-152">Щелкните имя домена SIP правой кнопкой мыши и выберите команду **создать узел (A или AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="50305-152">Right-click the SIP domain name, and then click **New Host (A or AAAA)**.</span></span>

8.  <span data-ttu-id="50305-153">В поле **Name (имя**) введите линкдисковеринтернал в качестве имени узла для URL-адреса внутренней службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="50305-153">In **Name**, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="50305-154">В поле **IP-адрес**введите IP-адрес внутренней веб-службы режиссера (или, если вы используете подсистему балансировку нагрузки, введите виртуальные IP-адреса (VIP) для подсистемы балансировки нагрузки режиссера).</span><span class="sxs-lookup"><span data-stu-id="50305-154">In **IP Address**, type the internal Web Services IP address of the Director (or, if you use a load balancer, type the virtual IP (VIP) of the Director load balancer).</span></span> <span data-ttu-id="50305-155">Как отмечалось на этапе 4 выше, если вы не используете режиссер, вам может потребоваться ввести IP-адрес сервера переднего плана или сервера Standard Edition либо, если вы используете подсистему балансировки нагрузки, введите VIP для подсистемы балансировки нагрузки пула из состава переднего плана.</span><span class="sxs-lookup"><span data-stu-id="50305-155">As noted in Step 4 above, if you aren’t using a Director, you may need to enter the IP address of the Front End Server or Standard Edition server or, if you use a load balancer, type the VIP of the Front End pool load balancer.</span></span>

10. <span data-ttu-id="50305-156">Нажмите кнопку **Добавить узел**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="50305-156">Click **Add Host**, and then click **OK**.</span></span>

11. <span data-ttu-id="50305-157">Чтобы создать дополнительную запись A или AAAA, повторите шаги 8 – 10, помните о том, что для каждого домена SIP, поддерживаемого в среде Lync Server 2013, необходимо создать новые записи A и AAAA для автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="50305-157">To create an additional A or AAAA record, repeat steps 8 through 10, keeping in mind that you’ll need to create new Autodiscover A or AAAA records in the forward lookup zone of each SIP domain that’s supported in your Lync Server 2013 environment.</span></span>

12. <span data-ttu-id="50305-158">Завершив создание записей A (для IPv6, AAAA), нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="50305-158">When you are finished creating A (for IPv6, AAAA) records, click **Done**.</span></span>

</div>

<div>

## <a name="creating-an-external-dns-a-record"></a><span data-ttu-id="50305-159">Создание записи внешней DNS A</span><span class="sxs-lookup"><span data-stu-id="50305-159">Creating an external DNS A record</span></span>

1.  <span data-ttu-id="50305-160">Чтобы создать внешнюю DNS-запись, подключитесь к общедоступному поставщику услуг DNS и выполните действия, описанные ниже.</span><span class="sxs-lookup"><span data-stu-id="50305-160">To create an external DNS record, connect to your public DNS provider, and then follow our steps.</span></span> <span data-ttu-id="50305-161">Мы не можем описать, где вы находитесь в среде вашего поставщика услуг DNS, так как у вас могут быть различные способы управления внешней службой DNS, но мы надеемся, что эти действия помогут вам.</span><span class="sxs-lookup"><span data-stu-id="50305-161">We can’t describe exactly where you’re going in your DNS provider’s environment as there may be different ways of managing your external DNS, but we hope these steps help.</span></span>

2.  <span data-ttu-id="50305-162">Вы должны войти в систему как учетную запись, которая может создавать записи DNS в этой среде.</span><span class="sxs-lookup"><span data-stu-id="50305-162">You’ll need to be logged in as an account that can create DNS records in that environment.</span></span>

3.  <span data-ttu-id="50305-163">Для внешней записи DNS в дереве консоли DNS-сервера разверните **зоны прямого просмотра** для домена SIP (например, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="50305-163">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span> <span data-ttu-id="50305-164">Для внешней записи DNS в дереве консоли DNS-сервера разверните **зоны прямого просмотра** для домена SIP (например, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="50305-164">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="50305-165">Вы уже должны видеть запись узла A (AAAA для IPv6) для своего пула (например, lyncwebexdir01.contoso.com), поэтому убедитесь, что он есть и что такое IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="50305-165">You should already see a host A (AAAA for IPv6) record for your Director pool (such as lyncwebexdir01.contoso.com), so confirm that it’s there and what the IP address is.</span></span> <span data-ttu-id="50305-166">Если это не так, вы, возможно, используете пул режиссеров.</span><span class="sxs-lookup"><span data-stu-id="50305-166">If it’s not, then you may not be using a Director pool.</span></span> <span data-ttu-id="50305-167">В этом случае вам потребуется использовать IP-адрес своего пула переднего плана или, если это вы делаете для одного сервера, на сервере переднего плана или стандартном сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="50305-167">If that’s the case, you’ll need to use the IP address of your Front End Pool, or if you’re doing this for a single server, for your Front-End server or Standard Edition server.</span></span> <span data-ttu-id="50305-168">Имейте в виду, что серверы могут также находиться за пределами подсистемы балансировки нагрузки или использовать обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="50305-168">Keep in mind that your servers may also be behind a load-balancer, or using a reverse proxy.</span></span> <span data-ttu-id="50305-169">Запишите IP-адреса и выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="50305-169">Make note of the IP addresses as well for following the steps below.</span></span>

5.  <span data-ttu-id="50305-170">Кроме того, вам нужно подтвердить, что для внешних доменных имен (например, lyncwebextpool01.contoso.com) или IP-адреса для односерверной установки в Lync используется запись узла A (AAAA для IPv6) для своего пула переднего плана. нет пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="50305-170">You’ll also need to confirm that a host A (AAAA for IPv6) record exists for your external Web Services Fully Qualified Domain Name (FQDN) for your Front End pool (such as lyncwebextpool01.contoso.com), or an IP address for your single-server Lync installation if you have no Front End pool.</span></span> <span data-ttu-id="50305-171">Как отмечалось на предыдущем этапе, вам понадобится это, если у вас нет директора пула.</span><span class="sxs-lookup"><span data-stu-id="50305-171">As noted in the previous step, you’ll need this below if you don’t have a Director pool.</span></span>

6.  <span data-ttu-id="50305-172">В соответствии с форматом внешнего поставщика услуг DNS выберите вариант создания **нового узла a или AAAA** (это может быть параметр меню или ссылка в зависимости от формата поставщика DNS).</span><span class="sxs-lookup"><span data-stu-id="50305-172">Now, in the appropriate format for your external DNS provider, choose the option for creating a **New Host A or AAAA** (this may be a menu option or a link, depending on the format of the DNS provider).</span></span>

7.  <span data-ttu-id="50305-173">Укажите место для ввода **имени**, а затем введите lyncdiscover в качестве имени узла для URL-адреса внешней службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="50305-173">There should be a place to enter a **Name**, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

8.  <span data-ttu-id="50305-174">Кроме того, необходимо указать текстовое поле **IP Address** (например, lyncwebexdir01.contoso.com) или IP-адрес для подсистемы балансировки нагрузки пула (или обратный IP-адрес, который ведет себя), а затем нажать кнопку ОК или предпринять любое действие во внешнем DNS, чтобы подтвердить создание этой записи.</span><span class="sxs-lookup"><span data-stu-id="50305-174">There should also be an **IP Address** text box, here’s where you’ll enter the IP for your for your Director pool (for example, lyncwebexdir01.contoso.com) or possibly the IP of your pool’s load balancer (or a reverse proxy IP that leads to the same) and then click OK or take whatever action in the external DNS to accept the creation of this entry.</span></span> <span data-ttu-id="50305-175">Как указано в действии 4, выше, если у вас нет режиссера, вы должны использовать IP-адрес пула переднего плана или односерверный IP-адрес, настроенный по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="50305-175">As noted in Step 4, above, if you don’t have a Director pool, you’ll need to use the Front End pool IP address or the single-server IP address you have set up, as appropriate.</span></span>

9.  <span data-ttu-id="50305-176">Вам потребуется создать новую запись автообнаружения A или AAAA в зоне прямого просмотра каждого домена SIP, который поддерживается в среде Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="50305-176">You’ll need to make a new Autodiscover A or AAAA record in the forward lookup zone of each SIP domain that’s supported in your Lync 2013 environment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

