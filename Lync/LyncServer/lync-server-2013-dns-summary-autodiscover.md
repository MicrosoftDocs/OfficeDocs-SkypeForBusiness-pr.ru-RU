---
title: 'Lync Server 2013: сводка по DNS — автообнаружение'
description: 'Lync Server 2013: сводка по DNS — автообнаружение.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Autodiscover
ms:assetid: b336a2ae-0e58-4b74-b606-aedbbd411587
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945644(v=OCS.15)
ms:contentKeyID: 51541504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eef9bd6a2489561145718c7bbf2f710ab0b1f248
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574285"
---
# <a name="dns-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="a1435-103">Сводка по DNS — автообнаружение в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1435-103">DNS summary - Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1435-104">_**Последнее изменение темы:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="a1435-104">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="a1435-105">Автообнаружение — это гибкая служба, в которой она будет принимать связь по протоколу HTTP или HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a1435-105">Autodiscover is a flexible service in that it will accept communication over HTTP or HTTPS.</span></span> <span data-ttu-id="a1435-106">Для этого необходимо правильно настроить систему доменных имен (DNS) и сертификаты, используемые серверами, на которых размещается служба автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="a1435-106">To accomplish this, the domain name system (DNS) and the certificates used by servers that host the Autodiscover service must be configured correctly.</span></span> <span data-ttu-id="a1435-107">Требования к сертификатам описаны в разделе [сведения о сертификатах — автообнаружение в Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).</span><span class="sxs-lookup"><span data-stu-id="a1435-107">Certificate requirements are covered in [Certificate summary - Autodiscover in Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a1435-108">Логика поиска DNS для клиентов Lync Server использует определенный порядок разрешения.</span><span class="sxs-lookup"><span data-stu-id="a1435-108">DNS lookup logic for the Lync Server clients uses a specific order of resolution.</span></span> <span data-ttu-id="a1435-109">Всегда следует включать как lyncdiscoverinternal. &lt; Domain &gt; и lyncdiscover. &lt; домен &gt; в службе DNS.</span><span class="sxs-lookup"><span data-stu-id="a1435-109">You should always include both the lyncdiscoverinternal.&lt;domain&gt; and the lyncdiscover.&lt;domain&gt; in your DNS.</span></span> <span data-ttu-id="a1435-110">Исключение lyncdiscoverinternal. &lt; в &gt; результате записи домена внутренние клиенты не смогут подключаться к необходимым службам или получать неверный ответ автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="a1435-110">Excluding the lyncdiscoverinternal.&lt;domain&gt; record will cause internal clients to fail to connect to the intended services or receive the incorrect Autodiscover response.</span></span>



</div>

### <a name="internal-dns-records"></a><span data-ttu-id="a1435-111">Внутренние записи DNS</span><span class="sxs-lookup"><span data-stu-id="a1435-111">Internal DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a1435-112">Тип записи</span><span class="sxs-lookup"><span data-stu-id="a1435-112">Record type</span></span></th>
<th><span data-ttu-id="a1435-113">Имя узла</span><span class="sxs-lookup"><span data-stu-id="a1435-113">Host name</span></span></th>
<th><span data-ttu-id="a1435-114">Разрешается в</span><span class="sxs-lookup"><span data-stu-id="a1435-114">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a1435-115">CNAME</span><span class="sxs-lookup"><span data-stu-id="a1435-115">CNAME</span></span></p></td>
<td><p><span data-ttu-id="a1435-116">Lyncdiscoverinternal. &lt; внутреннее доменное имя&gt;</span><span class="sxs-lookup"><span data-stu-id="a1435-116">Lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="a1435-117">Полное доменное имя внутренних веб-служб для пула директоров, если таковой имеется, или для пула переднего плана, если у вас нет директора.</span><span class="sxs-lookup"><span data-stu-id="a1435-117">Internal Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1435-118">A (узел, если используется IPv6, AAAA)</span><span class="sxs-lookup"><span data-stu-id="a1435-118">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="a1435-119">lyncdiscoverinternal. &lt; внутреннее доменное имя&gt;</span><span class="sxs-lookup"><span data-stu-id="a1435-119">lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="a1435-120">IP-адрес внутренних веб-служб (виртуальный IP-адрес), если вы используете подсистему балансировки нагрузки для пула директоров (если у вас есть один или из интерфейсного пула, если у вас нет директора).</span><span class="sxs-lookup"><span data-stu-id="a1435-120">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a1435-121">Необходимо создать одну из следующих внешних DNS-записей:</span><span class="sxs-lookup"><span data-stu-id="a1435-121">You need to create one of the following external DNS records:</span></span>

### <a name="external-dns-records"></a><span data-ttu-id="a1435-122">Внешние записи DNS</span><span class="sxs-lookup"><span data-stu-id="a1435-122">External DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a1435-123">Тип записи</span><span class="sxs-lookup"><span data-stu-id="a1435-123">Record type</span></span></th>
<th><span data-ttu-id="a1435-124">Имя узла</span><span class="sxs-lookup"><span data-stu-id="a1435-124">Host name</span></span></th>
<th><span data-ttu-id="a1435-125">Разрешается в</span><span class="sxs-lookup"><span data-stu-id="a1435-125">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a1435-126">CNAME</span><span class="sxs-lookup"><span data-stu-id="a1435-126">CNAME</span></span></p></td>
<td><p><span data-ttu-id="a1435-127">lyncdiscover. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="a1435-127">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="a1435-128">Полное доменное имя внешних веб-служб для пула директоров, если таковой имеется, или для пула переднего плана, если у вас нет директора.</span><span class="sxs-lookup"><span data-stu-id="a1435-128">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1435-129">A (узел, если используется IPv6, AAAA)</span><span class="sxs-lookup"><span data-stu-id="a1435-129">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="a1435-130">lyncdiscover. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="a1435-130">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="a1435-131">Внешний или общедоступный IP-адрес обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="a1435-131">External or public IP address of the reverse proxy.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="a1435-132">Внешний трафик проходит через обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="a1435-132">External traffic goes through the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="a1435-133">Клиенты мобильных устройств не поддерживают множество сертификатов SSL из разных доменов.</span><span class="sxs-lookup"><span data-stu-id="a1435-133">Mobile device clients do not support multiple Secure Sockets Layer (SSL) certificates from different domains.</span></span> <span data-ttu-id="a1435-134">Поэтому перенаправление CNAME в различные домены по протоколу HTTPS не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="a1435-134">Therefore, CNAME redirection to different domains is not supported over HTTPS.</span></span> <span data-ttu-id="a1435-135">Например, запись DNS CNAME для домена lyncdiscover.contoso.com, которая выполняет перенаправление на адрес director.contoso.net, не поддерживается по протоколу HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a1435-135">For example, a DNS CNAME record for lyncdiscover.contoso.com that redirects to an address of director.contoso.net is not supported over HTTPS.</span></span> <span data-ttu-id="a1435-136">В такой топологии клиент мобильного устройства должен использовать HTTP для первого запроса, чтобы перенаправление CNAME разрешалось по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="a1435-136">In such a topology, a mobile device client needs to use HTTP for the first request, so that the CNAME redirection is resolved over HTTP.</span></span> <span data-ttu-id="a1435-137">Последующие запросы могут использовать HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a1435-137">Subsequent requests then use HTTPS.</span></span> <span data-ttu-id="a1435-138">Для поддержки этого сценария необходимо настроить обратный прокси-сервер с использованием правила веб-публикации для порта 80 (HTTP).</span><span class="sxs-lookup"><span data-stu-id="a1435-138">To support this scenario, you need to configure your reverse proxy with a web publishing rule for port 80 (HTTP).</span></span> <span data-ttu-id="a1435-139">Сведения о том, как создать правило веб-публикации для порта 80 "в разделе <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Настройка обратного прокси-сервера для мобильной работы в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a1435-139">For details, see "To create a web publishing rule for port 80" in <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</A>.</span></span> <span data-ttu-id="a1435-140">Перенаправление CNAME в тот же домен поддерживается по протоколу HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a1435-140">CNAME redirection to the same domain is supported over HTTPS.</span></span> <span data-ttu-id="a1435-141">В этом случае сертификат конечного домена охватывает исходный домен.</span><span class="sxs-lookup"><span data-stu-id="a1435-141">In this case, the destination domain's certificate covers the originating domain.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a1435-142">См. также</span><span class="sxs-lookup"><span data-stu-id="a1435-142">See Also</span></span>


[<span data-ttu-id="a1435-143">Настройка обратного прокси-сервера для мобильной работы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1435-143">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[<span data-ttu-id="a1435-144">Сводка по сертификатам — автообнаружение в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1435-144">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

