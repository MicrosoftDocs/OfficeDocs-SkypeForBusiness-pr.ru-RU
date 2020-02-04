---
title: 'Lync Server 2013: требования к подсистеме балансировки нагрузки оборудования'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware load balancer requirements
ms:assetid: 32891268-2059-43d0-adf4-af4ff1e9ce66
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ656815(v=OCS.15)
ms:contentKeyID: 49287208
ms.date: 05/11/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85ed4195d80ecc755faea74ddedb790c9f41ebfb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727909"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-load-balancer-requirements-for-lync-server-2013"></a><span data-ttu-id="1e0b7-102">Требования к подсистеме балансировки нагрузки оборудования для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e0b7-102">Hardware load balancer requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e0b7-103">_**Тема последнего изменения:** 2015-05-11_</span><span class="sxs-lookup"><span data-stu-id="1e0b7-103">_**Topic Last Modified:** 2015-05-11_</span></span>

<span data-ttu-id="1e0b7-104">Масштабируемая консолидированная высокоэффективная топология Lync Server 2013 оптимизирована для балансировки нагрузки DNS для новых развертываний, которые главным образом используются в других организациях, использующих Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-104">The Lync Server 2013 scaled consolidated Edge topology is optimized for DNS load balancing for new deployments federating primarily with other organizations using Lync Server.</span></span> <span data-ttu-id="1e0b7-105">Если для любого из перечисленных ниже сценариев требуется высокая доступность, аппаратная подсистема балансировки нагрузки должна использоваться в пулах пограничного сервера для указанных ниже элементов.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-105">If high availability is required for any of the following scenarios, a hardware load balancer must be used on Edge Server pools for the following:</span></span>

  - <span data-ttu-id="1e0b7-106">Интеграция с организациями с помощью Office Communications Server 2007 R2 или Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="1e0b7-106">Federation with organizations using Office Communications Server 2007 R2 or Office Communications Server 2007</span></span>

  - <span data-ttu-id="1e0b7-107">UM Exchange для удаленных пользователей, использующих UM до Exchange 2010 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="1e0b7-107">Exchange UM for remote users using Exchange UM prior to Exchange 2010 with SP1</span></span>

  - <span data-ttu-id="1e0b7-108">Связь с пользователями общедоступных систем обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="1e0b7-108">Connectivity to public IM users</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1e0b7-p102">Использование в одном интерфейсе балансировки нагрузки через DNS, а в другом аппаратной балансировки нагрузки не поддерживается. Необходимо использовать либо ту, либо другую систему балансировки нагрузки для обоих интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-p102">Using DNS load balancing on one interface and hardware load balancing on the other is not supported. You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="1e0b7-p103">При использовании аппаратной балансировки нагрузки балансировщик, развертываемый для соединений с внутренней сетью, необходимо настроить на балансировку нагрузки только трафика, идущего к серверам, на которых выполняются пограничная служба доступа и пограничная служба аудио- и видеоданных. Он не может балансировать нагрузку трафика, идущего ко внутренней пограничной службе веб-конференций или внутренней прокси-службе XMPP.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-p103">If you are using a hardware load balancer, the load balancer deployed for connections with the internal network must be configured to load balance only the traffic to servers running the Access Edge service and the A/V Edge service. It cannot load balance the traffic to the internal Web Conferencing Edge service or the internal XMPP Proxy service.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="1e0b7-113">NAT сервера с Lync Server 2013 не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-113">The direct server return (DSR) NAT is not supported with Lync Server 2013.</span></span>



</div>

<span data-ttu-id="1e0b7-114">Чтобы определить, поддерживает ли ваш аппаратный балансировщик нагрузки необходимые функции, необходимые для Lync Server 2013, в [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452)разделе "участники подсистемы балансировки нагрузки lync Server 2010".</span><span class="sxs-lookup"><span data-stu-id="1e0b7-114">To determine whether your hardware load balancer supports the necessary features required by Lync Server 2013, see "Lync Server 2010 Load Balancer Partners" at [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452).</span></span>

<div>

## <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a><span data-ttu-id="1e0b7-115">Требования к аппаратному балансировщику нагрузки для пограничных серверов, использующих пограничную службу аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="1e0b7-115">Hardware Load Balancer Requirements for Edge Servers Running the A/V Edge Service</span></span>

<span data-ttu-id="1e0b7-116">Ниже приведены требования к оборудованию для подсистемы балансировки нагрузки для пограничного сервера, на котором работает служба Edge-V:</span><span class="sxs-lookup"><span data-stu-id="1e0b7-116">Following are the hardware load balancer requirements for Edge Servers running the A/V Edge service:</span></span>

  - <span data-ttu-id="1e0b7-p104">Отключите Nagle-оптимизацию TCP для внутреннего и внешнего портов 443. Оптимизация по алгоритму Nagle — это процесс объединения мелких пакетов сервера в один пакет большего размера для более эффективной передачи.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-p104">Turn off TCP nagling for both internal and external ports 443. Nagling is the process of combining several small packets into a single, larger packet for more efficient transmission.</span></span>

  - <span data-ttu-id="1e0b7-119">Отключите Nagle-оптимизацию TCP для диапазона внешних портов 50 000 - 59 999.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-119">Turn off TCP nagling for external port range 50,000 – 59,999.</span></span>

  - <span data-ttu-id="1e0b7-120">Не применяйте преобразование сетевых адресов на внутреннем или внешнем брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-120">Do not use NAT on the internal or external firewall.</span></span>

  - <span data-ttu-id="1e0b7-121">Внутренний интерфейс EDGE должен находиться в другой сети, чем внешний интерфейс пограничного сервера, и маршрутизация между ними должна быть отключена.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-121">The edge internal interface must be on a different network than the Edge Server external interface and routing between them must be disabled.</span></span>

  - <span data-ttu-id="1e0b7-122">Внешний интерфейс пограничного сервера, на котором работает служба EDGE, должен использовать общедоступные IP-адреса и не преобразованием NAT или порта на любые внешние IP-адреса Edge.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-122">The external interface of the Edge Server running the A/V Edge Service must use publicly routable IP addresses and no NAT or port translation on any of the edge external IP addresses.</span></span>

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a><span data-ttu-id="1e0b7-123">Требования к подсистеме балансировки нагрузки оборудования</span><span class="sxs-lookup"><span data-stu-id="1e0b7-123">Hardware Load Balancer Requirements</span></span>

<span data-ttu-id="1e0b7-124">В Lync Server 2013 для веб-служб значительно снижены требования к схожести на основе файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-124">Cookie-based affinity requirements are greatly reduced in Lync Server 2013 for Web services.</span></span> <span data-ttu-id="1e0b7-125">Если вы развертываете Lync Server 2013 и не сохраните ни один из серверных пулов Lync Server 2010 или внешних интерфейсов, не требуется постоянство на основе cookie-файлов.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-125">If you are deploying Lync Server 2013 and will not retain any Lync Server 2010 Front End Servers or Front End pools, you do not need cookie-based persistence.</span></span> <span data-ttu-id="1e0b7-126">Тем не менее, если вы временно или постоянно сохраняете все серверы переднего плана Lync Server 2010 или внешние пулы, вы по-прежнему используете сохраняемость на основе файлов cookie, так как она развернута и настроена для Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-126">However, if you will temporarily or permanently retain any Lync Server 2010 Front End Servers or Front End pools, you still use cookie-based persistence as it is deployed and configured for Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1e0b7-127"><STRONG>Если вы все же решите использовать сходство на основе файлов cookie, хотя вашему развертыванию оно и не требуется</STRONG>, это не будет иметь никаких отрицательных последствий.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-127"><STRONG>If you decide to use cookie-based affinity even though your deployment does not require it</STRONG>, there is no negative impact to doing so.</span></span>



</div>

<span data-ttu-id="1e0b7-128">Для развертываний, в которых **не будет использоваться** сходство на основе файлов cookie:</span><span class="sxs-lookup"><span data-stu-id="1e0b7-128">For deployments that **will not use** cookie-based affinity:</span></span>

  - <span data-ttu-id="1e0b7-129">В правиле публикации обратного прокси-сервера через порт 4443, установите значение True для параметра **Перенаправлять заголовок узла**.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-129">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True.</span></span> <span data-ttu-id="1e0b7-130">Это обеспечит перенаправление исходного URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-130">This will ensure that the original URL is forwarded.</span></span>

<span data-ttu-id="1e0b7-131">Для развертываний, в которых **будет использоваться** сходство на основе файлов cookie:</span><span class="sxs-lookup"><span data-stu-id="1e0b7-131">For deployments that **will use** cookie-based affinity:</span></span>

  - <span data-ttu-id="1e0b7-p107">В правиле публикации обратного прокси-сервера через порт 4443, установите значение True для параметра **Перенаправлять заголовок узла**. Это обеспечит перенаправление исходного URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-p107">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True. This will ensure that the original URL is forwarded.</span></span>

  - <span data-ttu-id="1e0b7-134">Файл cookie для аппаратного балансировщика нагрузки НЕ ДОЛЖЕН помечаться как httpOnly</span><span class="sxs-lookup"><span data-stu-id="1e0b7-134">Hardware load balancer cookie MUST NOT be marked httpOnly</span></span>

  - <span data-ttu-id="1e0b7-135">Файл cookie для аппаратного балансировщика нагрузки НЕ ДОЛЖЕН быть ограничен сроком действия</span><span class="sxs-lookup"><span data-stu-id="1e0b7-135">Hardware load balancer cookie MUST NOT have an expiration time</span></span>

  - <span data-ttu-id="1e0b7-136">Файл cookie для аппаратного балансировщика нагрузки ДОЛЖЕН иметь имя **MS-WSMAN** (веб-службы ожидают это значение, его нельзя менять)</span><span class="sxs-lookup"><span data-stu-id="1e0b7-136">Hardware load balancer cookie MUST be named **MS-WSMAN** (This is the value that the Web services expect, and cannot be changed)</span></span>

  - <span data-ttu-id="1e0b7-p108">Режим использования файлов cookie ДОЛЖЕН задаваться в каждом ответе HTTP, для которого входящий запрос HTTP не имел файла cookie, даже если файл cookie был уже получен предыдущим ответом HTTP в том же соединении TCP. Если балансировщик нагрузки при оптимизации допускает только одну вставку файла cookie для каждого соединения TCP, такая оптимизация НЕ ДОЛЖНА применяться.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-p108">Hardware load balancer cookie MUST be set in every HTTP response for which the incoming HTTP request did not have a cookie, regardless of whether a previous HTTP response on that same TCP connection had already obtained a cookie. If the load balancer optimizes cookie insert to only occur once per TCP connection, that optimization MUST NOT be used</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1e0b7-139">Типичные конфигурации подсистемы балансировки нагрузки аппаратных средств используют сходство с исходным адресом и время жизни сеанса TCP мин., что подходит для клиентов Lync Server и Lync 2013, поскольку состояние сеанса поддерживается с помощью клиента и (или) взаимодействия с приложением.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-139">Typical hardware load balancer configurations use source-address affinity and a 20 min. TCP session lifetime, which is fine for Lync Server and Lync 2013 clients because session state is maintained through client usage and/or and application interaction.</span></span>



</div>

<span data-ttu-id="1e0b7-140">При развертывании мобильных устройств ваш аппаратный балансировщик нагрузки должен поддерживать возможность балансировки нагрузки для индивидуальных запросов в рамках сеанса TCP (фактически необходима возможность балансировки нагрузки индивидуальных запросов на основе целевого IP-адреса).</span><span class="sxs-lookup"><span data-stu-id="1e0b7-140">If you are deploying mobile devices, your hardware load balancer must be able to load balance individual request within a TCP session (in effect, you must be able to load balance an individual request based on the target IP address).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="1e0b7-p109">В аппаратных балансировщиках нагрузки F5 имеется функция OneConnect, которая обеспечивает индивидуальную балансировку нагрузки для каждого запроса в соединении TCP. Если вы развертываете мобильные устройства, убедитесь, что поставщик вашего аппаратного балансировщика нагрузки поддерживает аналогичную функциональную возможность. Последним приложениям Apple iOS для мобильных устройств требуется протокол TLS версии 1.2. F5 предоставляет для этого специальные настройки.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-p109">F5 hardware load balancers have a feature called OneConnect that ensures each request within a TCP connection is individually load balanced. If you are deploying mobile devices, ensure your hardware load balancer vendor supports the same functionality. The latest Apple iOS mobile apps require Transport Layer Security (TLS) version 1.2. F5 provides specific settings for this.</span></span><BR><span data-ttu-id="1e0b7-145">Подробнее о подсистемах балансировки нагрузки оборудования сторонних производителей можно найти в разделе<A href="http://go.microsoft.com/fwlink/p/?linkid=230700">http://go.microsoft.com/fwlink/p/?linkId=230700</A></span><span class="sxs-lookup"><span data-stu-id="1e0b7-145">For details on third party hardware load balancers, see <A href="http://go.microsoft.com/fwlink/p/?linkid=230700">http://go.microsoft.com/fwlink/p/?linkId=230700</A></span></span>



</div>

<span data-ttu-id="1e0b7-146">Ниже приводятся требования к аппаратному балансировщику нагрузки для веб-служб директора и интерфейсного пула.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-146">Following are the hardware load balancer requirements for Director and Front End pool Web Services:</span></span>

  - <span data-ttu-id="1e0b7-147">Для внутренних виртуальных IP-адресов укажите параметр\_сохраняемости исходного адреса (внутренний порт 80, 443) в подсистеме балансировки нагрузки оборудования.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-147">For internal Web Services VIPs, set Source\_addr persistence (internal port 80, 443) on the hardware load balancer.</span></span> <span data-ttu-id="1e0b7-148">Для Lync Server 2013, сохранение\_исходного адреса означает, что несколько подключений, поступающих из одного IP-адреса, всегда отправляются на один сервер для сохранения состояния сеанса.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-148">For Lync Server 2013, Source\_addr persistence means that multiple connections coming from a single IP address are always sent to one server to maintain session state.</span></span>

  - <span data-ttu-id="1e0b7-149">В качестве таймаута простоя TCP используйте значение 1800 секунд.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-149">Use TCP idle timeout of 1800 seconds.</span></span>

  - <span data-ttu-id="1e0b7-p111">На брандмауэре между обратным прокси-сервером и аппаратным балансировщиком нагрузки пула на следующем прыжке создайте правило, разрешающее HTTPS-трафик через порт 4443 из обратного прокси-сервера в аппаратный балансировщик нагрузки. В аппаратном балансировщике нагрузки необходимо настроить прослушивание портов 80, 443 и 4443.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-p111">On the firewall between the reverse proxy and the next hop pool’s hardware load balancer, create a rule to allow https: traffic on port 4443, from the reverse proxy to the hardware load balancer. The hardware load balancer must be configured to listen on ports 80, 443, and 4443.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1e0b7-152">Для дальнейшего ознакомления с конфигурацией подсистемы балансировки нагрузки для оборудования ознакомьтесь со сведенным <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">масштабированным краем по порту с помощью подсистем балансировки нагрузки для оборудования в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-152">For further reading on configuration of the hardware load balancer, please review <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="summary-of-hardware-load-balancer-affinity-requirements"></a><span data-ttu-id="1e0b7-153">Сводка требований к сходству для аппаратного балансировщика нагрузки</span><span class="sxs-lookup"><span data-stu-id="1e0b7-153">Summary of Hardware Load Balancer Affinity Requirements</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1e0b7-154">Расположение клиента или пользователя</span><span class="sxs-lookup"><span data-stu-id="1e0b7-154">Client/user location</span></span></th>
<th><span data-ttu-id="1e0b7-155">Требования к сходству внешних доменных имен веб-служб</span><span class="sxs-lookup"><span data-stu-id="1e0b7-155">External web services FQDN affinity requirements</span></span></th>
<th><span data-ttu-id="1e0b7-156">Требования к сходству внутренних доменных имен веб-служб</span><span class="sxs-lookup"><span data-stu-id="1e0b7-156">Internal web services FQDN affinity requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1e0b7-157">Lync Web App (внутренние и внешние пользователи)</span><span class="sxs-lookup"><span data-stu-id="1e0b7-157">Lync Web App (internal and external users)</span></span></p>
<p><span data-ttu-id="1e0b7-158">Мобильное устройство (внутренние и внешние пользователи)</span><span class="sxs-lookup"><span data-stu-id="1e0b7-158">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="1e0b7-159">Без сходства</span><span class="sxs-lookup"><span data-stu-id="1e0b7-159">No affinity</span></span></p></td>
<td><p><span data-ttu-id="1e0b7-160">Сходство исходных адресов</span><span class="sxs-lookup"><span data-stu-id="1e0b7-160">Source address affinity</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e0b7-161">Lync Web App (только для внешних пользователей)</span><span class="sxs-lookup"><span data-stu-id="1e0b7-161">Lync Web App (external users only)</span></span></p>
<p><span data-ttu-id="1e0b7-162">Мобильное устройство (внутренние и внешние пользователи)</span><span class="sxs-lookup"><span data-stu-id="1e0b7-162">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="1e0b7-163">Без сходства</span><span class="sxs-lookup"><span data-stu-id="1e0b7-163">No affinity</span></span></p></td>
<td><p><span data-ttu-id="1e0b7-164">Сходство исходных адресов</span><span class="sxs-lookup"><span data-stu-id="1e0b7-164">Source address affinity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e0b7-165">Lync Web App (только для внутренних пользователей)</span><span class="sxs-lookup"><span data-stu-id="1e0b7-165">Lync Web App (internal users only)</span></span></p>
<p><span data-ttu-id="1e0b7-166">Мобильное устройство (без развертывания)</span><span class="sxs-lookup"><span data-stu-id="1e0b7-166">Mobile device (not deployed)</span></span></p></td>
<td><p><span data-ttu-id="1e0b7-167">Без сходства</span><span class="sxs-lookup"><span data-stu-id="1e0b7-167">No affinity</span></span></p></td>
<td><p><span data-ttu-id="1e0b7-168">Сходство исходных адресов</span><span class="sxs-lookup"><span data-stu-id="1e0b7-168">Source address affinity</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="port-monitoring-for-hardware-load-balancers"></a><span data-ttu-id="1e0b7-169">Мониторинг порта для аппаратных балансировщиков нагрузки</span><span class="sxs-lookup"><span data-stu-id="1e0b7-169">Port Monitoring for Hardware Load Balancers</span></span>

<span data-ttu-id="1e0b7-170">You define port monitoring on the hardware load balancers to determine when specific services are no longer available due to hardware or communications failure.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-170">You define port monitoring on the hardware load balancers to determine when specific services are no longer available due to hardware or communications failure.</span></span> <span data-ttu-id="1e0b7-171">Например, если служба сервера переднего плана (РТКСРВ) останавливается из-за того, что сервер переднего плана или пул переднего плана завершает работу с ошибкой, то в этом случае монитор ХЛБ должен прекратить получать трафик на веб – службах.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-171">For example, if the Front End Server service (RTCSRV) stops because the Front End Server or Front End pool fails, the HLB monitoring should also stop receiving traffic on the Web Services.</span></span> <span data-ttu-id="1e0b7-172">You implement port monitoring on the HLB to monitor the following:</span><span class="sxs-lookup"><span data-stu-id="1e0b7-172">You implement port monitoring on the HLB to monitor the following:</span></span>

### <a name="front-end-server-user-pool--hlb-internal-interface"></a><span data-ttu-id="1e0b7-173">Пул пользователей переднего плана сервера — внутренний интерфейс ХЛБ</span><span class="sxs-lookup"><span data-stu-id="1e0b7-173">Front End Server User Pool – HLB Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1e0b7-174">Виртуальный IP-адрес/порт</span><span class="sxs-lookup"><span data-stu-id="1e0b7-174">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="1e0b7-175">Порт узла</span><span class="sxs-lookup"><span data-stu-id="1e0b7-175">Node Port</span></span></th>
<th><span data-ttu-id="1e0b7-176">Компьютер/монитор узла</span><span class="sxs-lookup"><span data-stu-id="1e0b7-176">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="1e0b7-177">Профиль сохраняемости</span><span class="sxs-lookup"><span data-stu-id="1e0b7-177">Persistence Profile</span></span></th>
<th><span data-ttu-id="1e0b7-178">Примечания.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-178">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1e0b7-179">&lt;веб&gt;-сайт пула — int_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="1e0b7-179">&lt;pool&gt;web-int_mco_443_vs</span></span></p>
<p><span data-ttu-id="1e0b7-180">443</span><span class="sxs-lookup"><span data-stu-id="1e0b7-180">443</span></span></p></td>
<td><p><span data-ttu-id="1e0b7-181">443</span><span class="sxs-lookup"><span data-stu-id="1e0b7-181">443</span></span></p></td>
<td><p><span data-ttu-id="1e0b7-182">Сервер переднего плана</span><span class="sxs-lookup"><span data-stu-id="1e0b7-182">Front End</span></span></p>
<p><span data-ttu-id="1e0b7-183">5061</span><span class="sxs-lookup"><span data-stu-id="1e0b7-183">5061</span></span></p></td>
<td><p><span data-ttu-id="1e0b7-184">Источник</span><span class="sxs-lookup"><span data-stu-id="1e0b7-184">Source</span></span></p></td>
<td><p><span data-ttu-id="1e0b7-185">HTTPS</span><span class="sxs-lookup"><span data-stu-id="1e0b7-185">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e0b7-186">&lt;веб&gt;-сайт пула — int_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="1e0b7-186">&lt;pool&gt;web-int_mco_80_vs</span></span></p>
<p><span data-ttu-id="1e0b7-187">80</span><span class="sxs-lookup"><span data-stu-id="1e0b7-187">80</span></span></p></td>
<td><p><span data-ttu-id="1e0b7-188">80</span><span class="sxs-lookup"><span data-stu-id="1e0b7-188">80</span></span></p></td>
<td><p><span data-ttu-id="1e0b7-189">Сервер переднего плана</span><span class="sxs-lookup"><span data-stu-id="1e0b7-189">Front End</span></span></p>
<p><span data-ttu-id="1e0b7-190">5061</span><span class="sxs-lookup"><span data-stu-id="1e0b7-190">5061</span></span></p></td>
<td><p><span data-ttu-id="1e0b7-191">Источник</span><span class="sxs-lookup"><span data-stu-id="1e0b7-191">Source</span></span></p></td>
<td><p><span data-ttu-id="1e0b7-192">HTTP</span><span class="sxs-lookup"><span data-stu-id="1e0b7-192">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="front-end-server-user-pool--hlb-external-interface"></a><span data-ttu-id="1e0b7-193">Пул пользователей переднего плана сервера — внешний интерфейс ХЛБ</span><span class="sxs-lookup"><span data-stu-id="1e0b7-193">Front End Server User Pool – HLB External Interface</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1e0b7-194">Виртуальный IP-адрес/порт</span><span class="sxs-lookup"><span data-stu-id="1e0b7-194">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="1e0b7-195">Порт узла</span><span class="sxs-lookup"><span data-stu-id="1e0b7-195">Node Port</span></span></th>
<th><span data-ttu-id="1e0b7-196">Компьютер/монитор узла</span><span class="sxs-lookup"><span data-stu-id="1e0b7-196">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="1e0b7-197">Профиль сохраняемости</span><span class="sxs-lookup"><span data-stu-id="1e0b7-197">Persistence Profile</span></span></th>
<th><span data-ttu-id="1e0b7-198">Примечания.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-198">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1e0b7-199">&lt;web_mco_443_vs&gt;пула</span><span class="sxs-lookup"><span data-stu-id="1e0b7-199">&lt;pool&gt;web_mco_443_vs</span></span></p>
<p><span data-ttu-id="1e0b7-200">443</span><span class="sxs-lookup"><span data-stu-id="1e0b7-200">443</span></span></p></td>
<td><p><span data-ttu-id="1e0b7-201">4443</span><span class="sxs-lookup"><span data-stu-id="1e0b7-201">4443</span></span></p></td>
<td><p><span data-ttu-id="1e0b7-202">Сервер переднего плана</span><span class="sxs-lookup"><span data-stu-id="1e0b7-202">Front End</span></span></p>
<p><span data-ttu-id="1e0b7-203">5061</span><span class="sxs-lookup"><span data-stu-id="1e0b7-203">5061</span></span></p></td>
<td><p><span data-ttu-id="1e0b7-204">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="1e0b7-204">None</span></span></p></td>
<td><p><span data-ttu-id="1e0b7-205">HTTPS</span><span class="sxs-lookup"><span data-stu-id="1e0b7-205">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e0b7-206">&lt;web_mco_80_vs&gt;пула</span><span class="sxs-lookup"><span data-stu-id="1e0b7-206">&lt;pool&gt;web_mco_80_vs</span></span></p>
<p><span data-ttu-id="1e0b7-207">80</span><span class="sxs-lookup"><span data-stu-id="1e0b7-207">80</span></span></p></td>
<td><p><span data-ttu-id="1e0b7-208">8080</span><span class="sxs-lookup"><span data-stu-id="1e0b7-208">8080</span></span></p></td>
<td><p><span data-ttu-id="1e0b7-209">Сервер переднего плана</span><span class="sxs-lookup"><span data-stu-id="1e0b7-209">Front End</span></span></p>
<p><span data-ttu-id="1e0b7-210">5061</span><span class="sxs-lookup"><span data-stu-id="1e0b7-210">5061</span></span></p></td>
<td><p><span data-ttu-id="1e0b7-211">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="1e0b7-211">None</span></span></p></td>
<td><p><span data-ttu-id="1e0b7-212">HTTP</span><span class="sxs-lookup"><span data-stu-id="1e0b7-212">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

