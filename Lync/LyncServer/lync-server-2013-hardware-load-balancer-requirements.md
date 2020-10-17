---
title: Требования к оборудованию балансировки нагрузки на Lync Server 2013
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
ms.openlocfilehash: 5c4aac657dd1e472068474a3a70d17f1a2a38c63
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530876"
---
# <a name="hardware-load-balancer-requirements-for-lync-server-2013"></a><span data-ttu-id="09c5c-102">Требования к аппаратному подсистеме балансировки нагрузки для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09c5c-102">Hardware load balancer requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09c5c-103">_**Последнее изменение темы:** 2015-05-11_</span><span class="sxs-lookup"><span data-stu-id="09c5c-103">_**Topic Last Modified:** 2015-05-11_</span></span>

<span data-ttu-id="09c5c-104">Масштабируемая масштабируемая консолидированная пограничная топология Lync Server 2013 оптимизирована для балансировки нагрузки на DNS для новых развертываний, которые в основном используются в других организациях, использующих Lync Server.</span><span class="sxs-lookup"><span data-stu-id="09c5c-104">The Lync Server 2013 scaled consolidated Edge topology is optimized for DNS load balancing for new deployments federating primarily with other organizations using Lync Server.</span></span> <span data-ttu-id="09c5c-105">Если для любого из следующих сценариев требуется высокая доступность, аппаратная подсистема балансировки нагрузки должна использоваться в пулах пограничных серверов для следующих целей:</span><span class="sxs-lookup"><span data-stu-id="09c5c-105">If high availability is required for any of the following scenarios, a hardware load balancer must be used on Edge Server pools for the following:</span></span>

  - <span data-ttu-id="09c5c-106">Федерация с организациями, использующими Office Communications Server 2007 R2 или Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="09c5c-106">Federation with organizations using Office Communications Server 2007 R2 or Office Communications Server 2007</span></span>

  - <span data-ttu-id="09c5c-107">Единая система обмена сообщениями Exchange для удаленных пользователей с использованием единой системы обмена сообщениями Exchange до Exchange 2010</span><span class="sxs-lookup"><span data-stu-id="09c5c-107">Exchange UM for remote users using Exchange UM prior to Exchange 2010 with SP1</span></span>

  - <span data-ttu-id="09c5c-108">Связь с пользователями общедоступных систем обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="09c5c-108">Connectivity to public IM users</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="09c5c-p102">Использование в одном интерфейсе балансировки нагрузки через DNS, а в другом аппаратной балансировки нагрузки не поддерживается. Необходимо использовать либо ту, либо другую систему балансировки нагрузки для обоих интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="09c5c-p102">Using DNS load balancing on one interface and hardware load balancing on the other is not supported. You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="09c5c-p103">При использовании аппаратной балансировки нагрузки балансировщик, развертываемый для соединений с внутренней сетью, необходимо настроить на балансировку нагрузки только трафика, идущего к серверам, на которых выполняются пограничная служба доступа и пограничная служба аудио- и видеоданных. Он не может балансировать нагрузку трафика, идущего ко внутренней пограничной службе веб-конференций или внутренней прокси-службе XMPP.</span><span class="sxs-lookup"><span data-stu-id="09c5c-p103">If you are using a hardware load balancer, the load balancer deployed for connections with the internal network must be configured to load balance only the traffic to servers running the Access Edge service and the A/V Edge service. It cannot load balance the traffic to the internal Web Conferencing Edge service or the internal XMPP Proxy service.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="09c5c-113">Сервер NAT с Lync Server 2013 не поддерживает протокол обмена данными с прямым возвратом (DSR).</span><span class="sxs-lookup"><span data-stu-id="09c5c-113">The direct server return (DSR) NAT is not supported with Lync Server 2013.</span></span>



</div>

<span data-ttu-id="09c5c-114">Чтобы определить, поддерживает ли аппаратный балансировщик нагрузки необходимые компоненты, необходимые для Lync Server 2013, обратитесь к разделу "Партнеры балансировки нагрузки Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452) .</span><span class="sxs-lookup"><span data-stu-id="09c5c-114">To determine whether your hardware load balancer supports the necessary features required by Lync Server 2013, see "Lync Server 2010 Load Balancer Partners" at [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452).</span></span>

<div>

## <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a><span data-ttu-id="09c5c-115">Требования к аппаратному балансировщику нагрузки для пограничных серверов, использующих пограничную службу аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="09c5c-115">Hardware Load Balancer Requirements for Edge Servers Running the A/V Edge Service</span></span>

<span data-ttu-id="09c5c-116">Ниже приведены требования к аппаратному подсистеме балансировки нагрузки для пограничных серверов, на которых работает пограничная служба аудио-и видеоданных:</span><span class="sxs-lookup"><span data-stu-id="09c5c-116">Following are the hardware load balancer requirements for Edge Servers running the A/V Edge service:</span></span>

  - <span data-ttu-id="09c5c-p104">Отключите Nagle-оптимизацию TCP для внутреннего и внешнего портов 443. Оптимизация по алгоритму Nagle — это процесс объединения мелких пакетов сервера в один пакет большего размера для более эффективной передачи.</span><span class="sxs-lookup"><span data-stu-id="09c5c-p104">Turn off TCP nagling for both internal and external ports 443. Nagling is the process of combining several small packets into a single, larger packet for more efficient transmission.</span></span>

  - <span data-ttu-id="09c5c-119">Отключите Nagle-оптимизацию TCP для диапазона внешних портов 50 000 – 59 999.</span><span class="sxs-lookup"><span data-stu-id="09c5c-119">Turn off TCP nagling for external port range 50,000 – 59,999.</span></span>

  - <span data-ttu-id="09c5c-120">Не применяйте преобразование сетевых адресов на внутреннем или внешнем брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="09c5c-120">Do not use NAT on the internal or external firewall.</span></span>

  - <span data-ttu-id="09c5c-121">Внутренний интерфейс пограничного сервера должен находиться в другой сети, чем внешний интерфейс пограничного сервера, и маршрутизация между ними должна быть отключена.</span><span class="sxs-lookup"><span data-stu-id="09c5c-121">The edge internal interface must be on a different network than the Edge Server external interface and routing between them must be disabled.</span></span>

  - <span data-ttu-id="09c5c-122">Внешний интерфейс пограничного сервера, на котором работает пограничная служба аудио-и видеоданных, должен использовать общедоступные IP-адреса без NAT или преобразования портов на любом из внешних IP-адресов пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="09c5c-122">The external interface of the Edge Server running the A/V Edge Service must use publicly routable IP addresses and no NAT or port translation on any of the edge external IP addresses.</span></span>

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a><span data-ttu-id="09c5c-123">Требования к подсистеме балансировки нагрузки оборудования</span><span class="sxs-lookup"><span data-stu-id="09c5c-123">Hardware Load Balancer Requirements</span></span>

<span data-ttu-id="09c5c-124">Требования к сходству на основе файлов cookie значительно сокращаются в Lync Server 2013 для веб-служб.</span><span class="sxs-lookup"><span data-stu-id="09c5c-124">Cookie-based affinity requirements are greatly reduced in Lync Server 2013 for Web services.</span></span> <span data-ttu-id="09c5c-125">Если вы развертываете Lync Server 2013 и не сохраняете никакие серверы переднего плана Lync Server 2010 или внешние пулы, сохраняемость на основе файлов cookie не требуется.</span><span class="sxs-lookup"><span data-stu-id="09c5c-125">If you are deploying Lync Server 2013 and will not retain any Lync Server 2010 Front End Servers or Front End pools, you do not need cookie-based persistence.</span></span> <span data-ttu-id="09c5c-126">Тем не менее, если вы временно или окончательно сохранили все серверы переднего плана Lync Server 2010 или интерфейсные пулы, вы по-прежнему используете сохраняемость на основе файлов cookie, так как она разворачивается и настраивается для Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="09c5c-126">However, if you will temporarily or permanently retain any Lync Server 2010 Front End Servers or Front End pools, you still use cookie-based persistence as it is deployed and configured for Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="09c5c-127"><STRONG>Если вы все же решите использовать сходство на основе файлов cookie, хотя вашему развертыванию оно и не требуется</STRONG>, это не будет иметь никаких отрицательных последствий.</span><span class="sxs-lookup"><span data-stu-id="09c5c-127"><STRONG>If you decide to use cookie-based affinity even though your deployment does not require it</STRONG>, there is no negative impact to doing so.</span></span>



</div>

<span data-ttu-id="09c5c-128">Для развертываний, в которых **не будет использоваться** сходство на основе файлов cookie:</span><span class="sxs-lookup"><span data-stu-id="09c5c-128">For deployments that **will not use** cookie-based affinity:</span></span>

  - <span data-ttu-id="09c5c-p106">В правиле публикации обратного прокси-сервера через порт 4443, установите значение True для параметра **Перенаправлять заголовок узла**. Это обеспечит перенаправление исходного URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="09c5c-p106">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True. This will ensure that the original URL is forwarded.</span></span>

<span data-ttu-id="09c5c-131">Для развертываний, в которых **будет использоваться** сходство на основе файлов cookie:</span><span class="sxs-lookup"><span data-stu-id="09c5c-131">For deployments that **will use** cookie-based affinity:</span></span>

  - <span data-ttu-id="09c5c-p107">В правиле публикации обратного прокси-сервера через порт 4443, установите значение True для параметра **Перенаправлять заголовок узла**. Это обеспечит перенаправление исходного URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="09c5c-p107">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True. This will ensure that the original URL is forwarded.</span></span>

  - <span data-ttu-id="09c5c-134">Файл cookie для аппаратного балансировщика нагрузки НЕ ДОЛЖЕН помечаться как httpOnly</span><span class="sxs-lookup"><span data-stu-id="09c5c-134">Hardware load balancer cookie MUST NOT be marked httpOnly</span></span>

  - <span data-ttu-id="09c5c-135">Файл cookie для аппаратного балансировщика нагрузки НЕ ДОЛЖЕН быть ограничен сроком действия</span><span class="sxs-lookup"><span data-stu-id="09c5c-135">Hardware load balancer cookie MUST NOT have an expiration time</span></span>

  - <span data-ttu-id="09c5c-136">Файл cookie для аппаратного балансировщика нагрузки ДОЛЖЕН иметь имя **MS-WSMAN** (веб-службы ожидают это значение, его нельзя менять)</span><span class="sxs-lookup"><span data-stu-id="09c5c-136">Hardware load balancer cookie MUST be named **MS-WSMAN** (This is the value that the Web services expect, and cannot be changed)</span></span>

  - <span data-ttu-id="09c5c-p108">Режим использования файлов cookie ДОЛЖЕН задаваться в каждом ответе HTTP, для которого входящий запрос HTTP не имел файла cookie, даже если файл cookie был уже получен предыдущим ответом HTTP в том же соединении TCP. Если балансировщик нагрузки при оптимизации допускает только одну вставку файла cookie для каждого соединения TCP, такая оптимизация НЕ ДОЛЖНА применяться</span><span class="sxs-lookup"><span data-stu-id="09c5c-p108">Hardware load balancer cookie MUST be set in every HTTP response for which the incoming HTTP request did not have a cookie, regardless of whether a previous HTTP response on that same TCP connection had already obtained a cookie. If the load balancer optimizes cookie insert to only occur once per TCP connection, that optimization MUST NOT be used</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="09c5c-139">Типичные конфигурации аппаратных подсистем балансировки нагрузки используют сходство с исходным адресом и время жизни сеанса TCP min. TCP, что подходит для Lync Server и Lync 2013 для клиентов, так как состояние сеанса поддерживается посредством использования клиентов и/или взаимодействия приложений.</span><span class="sxs-lookup"><span data-stu-id="09c5c-139">Typical hardware load balancer configurations use source-address affinity and a 20 min. TCP session lifetime, which is fine for Lync Server and Lync 2013 clients because session state is maintained through client usage and/or and application interaction.</span></span>



</div>

<span data-ttu-id="09c5c-140">При развертывании мобильных устройств ваш аппаратный балансировщик нагрузки должен поддерживать возможность балансировки нагрузки для индивидуальных запросов в рамках сеанса TCP (фактически необходима возможность балансировки нагрузки индивидуальных запросов на основе целевого IP-адреса).</span><span class="sxs-lookup"><span data-stu-id="09c5c-140">If you are deploying mobile devices, your hardware load balancer must be able to load balance individual request within a TCP session (in effect, you must be able to load balance an individual request based on the target IP address).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="09c5c-p109">В аппаратных балансировщиках нагрузки F5 имеется функция OneConnect, которая обеспечивает индивидуальную балансировку нагрузки для каждого запроса в соединении TCP. Если вы развертываете мобильные устройства, убедитесь, что поставщик вашего аппаратного балансировщика нагрузки поддерживает аналогичную функциональную возможность. Последним приложениям Apple iOS для мобильных устройств требуется протокол TLS версии 1.2. F5 предоставляет для этого специальные настройки.</span><span class="sxs-lookup"><span data-stu-id="09c5c-p109">F5 hardware load balancers have a feature called OneConnect that ensures each request within a TCP connection is individually load balanced. If you are deploying mobile devices, ensure your hardware load balancer vendor supports the same functionality. The latest Apple iOS mobile apps require Transport Layer Security (TLS) version 1.2. F5 provides specific settings for this.</span></span><BR><span data-ttu-id="09c5c-145">Более подробную информацию о аппаратных подсистемах балансировки нагрузки можно узнать в статье <A href="https://go.microsoft.com/fwlink/p/?linkid=230700">https://go.microsoft.com/fwlink/p/?linkId=230700</A></span><span class="sxs-lookup"><span data-stu-id="09c5c-145">For details on third party hardware load balancers, see <A href="https://go.microsoft.com/fwlink/p/?linkid=230700">https://go.microsoft.com/fwlink/p/?linkId=230700</A></span></span>



</div>

<span data-ttu-id="09c5c-146">Ниже приводятся требования к аппаратному балансировщику нагрузки для веб-служб директора и интерфейсного пула.</span><span class="sxs-lookup"><span data-stu-id="09c5c-146">Following are the hardware load balancer requirements for Director and Front End pool Web Services:</span></span>

  - <span data-ttu-id="09c5c-147">Для виртуальных IP-адресов внутренних веб-служб установите параметр \_ сохраняемости исходного адреса (внутренний порт 80, 443) на аппаратном подсистеме балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="09c5c-147">For internal Web Services VIPs, set Source\_addr persistence (internal port 80, 443) on the hardware load balancer.</span></span> <span data-ttu-id="09c5c-148">Для Lync Server 2013, \_ Сохранение исходного адреса означает, что несколько подключений, поступающих из одного IP-адреса, всегда отправляются на один сервер для обслуживания состояния сеанса.</span><span class="sxs-lookup"><span data-stu-id="09c5c-148">For Lync Server 2013, Source\_addr persistence means that multiple connections coming from a single IP address are always sent to one server to maintain session state.</span></span>

  - <span data-ttu-id="09c5c-149">В качестве таймаута простоя TCP используйте значение 1800 секунд.</span><span class="sxs-lookup"><span data-stu-id="09c5c-149">Use TCP idle timeout of 1800 seconds.</span></span>

  - <span data-ttu-id="09c5c-p111">На брандмауэре между обратным прокси-сервером и аппаратным балансировщиком нагрузки пула на следующем прыжке создайте правило, разрешающее HTTPS-трафик через порт 4443 из обратного прокси-сервера в аппаратный балансировщик нагрузки. В аппаратном балансировщике нагрузки необходимо настроить прослушивание портов 80, 443 и 4443.</span><span class="sxs-lookup"><span data-stu-id="09c5c-p111">On the firewall between the reverse proxy and the next hop pool’s hardware load balancer, create a rule to allow https: traffic on port 4443, from the reverse proxy to the hardware load balancer. The hardware load balancer must be configured to listen on ports 80, 443, and 4443.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="09c5c-152">Более подробную информацию о конфигурации аппаратного балансировщика нагрузки можно узнать в <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">разделе "Сводка по портам — масштабируемое объединение с аппаратным подсистемой балансировки нагрузки" в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="09c5c-152">For further reading on configuration of the hardware load balancer, please review <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="summary-of-hardware-load-balancer-affinity-requirements"></a><span data-ttu-id="09c5c-153">Сводка требований к сходству для аппаратного балансировщика нагрузки</span><span class="sxs-lookup"><span data-stu-id="09c5c-153">Summary of Hardware Load Balancer Affinity Requirements</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="09c5c-154">Расположение клиента или пользователя</span><span class="sxs-lookup"><span data-stu-id="09c5c-154">Client/user location</span></span></th>
<th><span data-ttu-id="09c5c-155">Требования к сходству внешних доменных имен веб-служб</span><span class="sxs-lookup"><span data-stu-id="09c5c-155">External web services FQDN affinity requirements</span></span></th>
<th><span data-ttu-id="09c5c-156">Требования к сходству внутренних доменных имен веб-служб</span><span class="sxs-lookup"><span data-stu-id="09c5c-156">Internal web services FQDN affinity requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09c5c-157">Lync Web App (внутренние и внешние пользователи)</span><span class="sxs-lookup"><span data-stu-id="09c5c-157">Lync Web App (internal and external users)</span></span></p>
<p><span data-ttu-id="09c5c-158">Мобильное устройство (внутренние и внешние пользователи)</span><span class="sxs-lookup"><span data-stu-id="09c5c-158">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="09c5c-159">Без сходства</span><span class="sxs-lookup"><span data-stu-id="09c5c-159">No affinity</span></span></p></td>
<td><p><span data-ttu-id="09c5c-160">Сходство исходных адресов</span><span class="sxs-lookup"><span data-stu-id="09c5c-160">Source address affinity</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09c5c-161">Lync Web App (только внешние пользователи)</span><span class="sxs-lookup"><span data-stu-id="09c5c-161">Lync Web App (external users only)</span></span></p>
<p><span data-ttu-id="09c5c-162">Мобильное устройство (внутренние и внешние пользователи)</span><span class="sxs-lookup"><span data-stu-id="09c5c-162">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="09c5c-163">Без сходства</span><span class="sxs-lookup"><span data-stu-id="09c5c-163">No affinity</span></span></p></td>
<td><p><span data-ttu-id="09c5c-164">Сходство исходных адресов</span><span class="sxs-lookup"><span data-stu-id="09c5c-164">Source address affinity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09c5c-165">Lync Web App (только внутренние пользователи)</span><span class="sxs-lookup"><span data-stu-id="09c5c-165">Lync Web App (internal users only)</span></span></p>
<p><span data-ttu-id="09c5c-166">Мобильное устройство (без развертывания)</span><span class="sxs-lookup"><span data-stu-id="09c5c-166">Mobile device (not deployed)</span></span></p></td>
<td><p><span data-ttu-id="09c5c-167">Без сходства</span><span class="sxs-lookup"><span data-stu-id="09c5c-167">No affinity</span></span></p></td>
<td><p><span data-ttu-id="09c5c-168">Сходство исходных адресов</span><span class="sxs-lookup"><span data-stu-id="09c5c-168">Source address affinity</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="port-monitoring-for-hardware-load-balancers"></a><span data-ttu-id="09c5c-169">Мониторинг порта для аппаратных балансировщиков нагрузки</span><span class="sxs-lookup"><span data-stu-id="09c5c-169">Port Monitoring for Hardware Load Balancers</span></span>

<span data-ttu-id="09c5c-170">Мониторинг порта на аппаратных балансировщиках нагрузки позволяет определить, когда конкретные службы становятся недоступными из-за ошибки оборудования или связи.</span><span class="sxs-lookup"><span data-stu-id="09c5c-170">You define port monitoring on the hardware load balancers to determine when specific services are no longer available due to hardware or communications failure.</span></span> <span data-ttu-id="09c5c-171">Например, если служба сервера переднего плана (RTCSRV) останавливается из-за сбоя сервера переднего плана или пула переднего плана, то мониторинг HLB также должен прекратить прием трафика в веб-службах.</span><span class="sxs-lookup"><span data-stu-id="09c5c-171">For example, if the Front End Server service (RTCSRV) stops because the Front End Server or Front End pool fails, the HLB monitoring should also stop receiving traffic on the Web Services.</span></span> <span data-ttu-id="09c5c-172">Благодаря использованию функции мониторинга порта в аппаратном балансировщике нагрузки можно отслеживать следующее:</span><span class="sxs-lookup"><span data-stu-id="09c5c-172">You implement port monitoring on the HLB to monitor the following:</span></span>

### <a name="front-end-server-user-pool--hlb-internal-interface"></a><span data-ttu-id="09c5c-173">Пул пользователей сервера переднего плана — внутренний интерфейс HLB</span><span class="sxs-lookup"><span data-stu-id="09c5c-173">Front End Server User Pool – HLB Internal Interface</span></span>

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
<th><span data-ttu-id="09c5c-174">Виртуальный IP-адрес/порт</span><span class="sxs-lookup"><span data-stu-id="09c5c-174">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="09c5c-175">Порт узла</span><span class="sxs-lookup"><span data-stu-id="09c5c-175">Node Port</span></span></th>
<th><span data-ttu-id="09c5c-176">Компьютер/монитор узла</span><span class="sxs-lookup"><span data-stu-id="09c5c-176">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="09c5c-177">Профиль сохраняемости</span><span class="sxs-lookup"><span data-stu-id="09c5c-177">Persistence Profile</span></span></th>
<th><span data-ttu-id="09c5c-178">Примечания</span><span class="sxs-lookup"><span data-stu-id="09c5c-178">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09c5c-179">&lt;&gt;веб-int_mco_443_vs пула</span><span class="sxs-lookup"><span data-stu-id="09c5c-179">&lt;pool&gt;web-int_mco_443_vs</span></span></p>
<p><span data-ttu-id="09c5c-180">443</span><span class="sxs-lookup"><span data-stu-id="09c5c-180">443</span></span></p></td>
<td><p><span data-ttu-id="09c5c-181">443</span><span class="sxs-lookup"><span data-stu-id="09c5c-181">443</span></span></p></td>
<td><p><span data-ttu-id="09c5c-182">Сервер переднего плана</span><span class="sxs-lookup"><span data-stu-id="09c5c-182">Front End</span></span></p>
<p><span data-ttu-id="09c5c-183">5061</span><span class="sxs-lookup"><span data-stu-id="09c5c-183">5061</span></span></p></td>
<td><p><span data-ttu-id="09c5c-184">Источник</span><span class="sxs-lookup"><span data-stu-id="09c5c-184">Source</span></span></p></td>
<td><p><span data-ttu-id="09c5c-185">HTTPS</span><span class="sxs-lookup"><span data-stu-id="09c5c-185">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09c5c-186">&lt;&gt;веб-int_mco_80_vs пула</span><span class="sxs-lookup"><span data-stu-id="09c5c-186">&lt;pool&gt;web-int_mco_80_vs</span></span></p>
<p><span data-ttu-id="09c5c-187">80</span><span class="sxs-lookup"><span data-stu-id="09c5c-187">80</span></span></p></td>
<td><p><span data-ttu-id="09c5c-188">80</span><span class="sxs-lookup"><span data-stu-id="09c5c-188">80</span></span></p></td>
<td><p><span data-ttu-id="09c5c-189">Сервер переднего плана</span><span class="sxs-lookup"><span data-stu-id="09c5c-189">Front End</span></span></p>
<p><span data-ttu-id="09c5c-190">5061</span><span class="sxs-lookup"><span data-stu-id="09c5c-190">5061</span></span></p></td>
<td><p><span data-ttu-id="09c5c-191">Источник</span><span class="sxs-lookup"><span data-stu-id="09c5c-191">Source</span></span></p></td>
<td><p><span data-ttu-id="09c5c-192">HTTP</span><span class="sxs-lookup"><span data-stu-id="09c5c-192">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="front-end-server-user-pool--hlb-external-interface"></a><span data-ttu-id="09c5c-193">Пул пользователей сервера переднего плана — внешний интерфейс HLB</span><span class="sxs-lookup"><span data-stu-id="09c5c-193">Front End Server User Pool – HLB External Interface</span></span>

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
<th><span data-ttu-id="09c5c-194">Виртуальный IP-адрес/порт</span><span class="sxs-lookup"><span data-stu-id="09c5c-194">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="09c5c-195">Порт узла</span><span class="sxs-lookup"><span data-stu-id="09c5c-195">Node Port</span></span></th>
<th><span data-ttu-id="09c5c-196">Компьютер/монитор узла</span><span class="sxs-lookup"><span data-stu-id="09c5c-196">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="09c5c-197">Профиль сохраняемости</span><span class="sxs-lookup"><span data-stu-id="09c5c-197">Persistence Profile</span></span></th>
<th><span data-ttu-id="09c5c-198">Примечания</span><span class="sxs-lookup"><span data-stu-id="09c5c-198">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09c5c-199">&lt;&gt;web_mco_443_vs пула</span><span class="sxs-lookup"><span data-stu-id="09c5c-199">&lt;pool&gt;web_mco_443_vs</span></span></p>
<p><span data-ttu-id="09c5c-200">443</span><span class="sxs-lookup"><span data-stu-id="09c5c-200">443</span></span></p></td>
<td><p><span data-ttu-id="09c5c-201">4443</span><span class="sxs-lookup"><span data-stu-id="09c5c-201">4443</span></span></p></td>
<td><p><span data-ttu-id="09c5c-202">Сервер переднего плана</span><span class="sxs-lookup"><span data-stu-id="09c5c-202">Front End</span></span></p>
<p><span data-ttu-id="09c5c-203">5061</span><span class="sxs-lookup"><span data-stu-id="09c5c-203">5061</span></span></p></td>
<td><p><span data-ttu-id="09c5c-204">Нет</span><span class="sxs-lookup"><span data-stu-id="09c5c-204">None</span></span></p></td>
<td><p><span data-ttu-id="09c5c-205">HTTPS</span><span class="sxs-lookup"><span data-stu-id="09c5c-205">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09c5c-206">&lt;&gt;web_mco_80_vs пула</span><span class="sxs-lookup"><span data-stu-id="09c5c-206">&lt;pool&gt;web_mco_80_vs</span></span></p>
<p><span data-ttu-id="09c5c-207">80</span><span class="sxs-lookup"><span data-stu-id="09c5c-207">80</span></span></p></td>
<td><p><span data-ttu-id="09c5c-208">8080</span><span class="sxs-lookup"><span data-stu-id="09c5c-208">8080</span></span></p></td>
<td><p><span data-ttu-id="09c5c-209">Сервер переднего плана</span><span class="sxs-lookup"><span data-stu-id="09c5c-209">Front End</span></span></p>
<p><span data-ttu-id="09c5c-210">5061</span><span class="sxs-lookup"><span data-stu-id="09c5c-210">5061</span></span></p></td>
<td><p><span data-ttu-id="09c5c-211">Нет</span><span class="sxs-lookup"><span data-stu-id="09c5c-211">None</span></span></p></td>
<td><p><span data-ttu-id="09c5c-212">HTTP</span><span class="sxs-lookup"><span data-stu-id="09c5c-212">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

