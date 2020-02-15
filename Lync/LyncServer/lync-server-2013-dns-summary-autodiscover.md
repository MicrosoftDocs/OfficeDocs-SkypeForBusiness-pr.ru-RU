---
title: 'Lync Server 2013: сводка по DNS — автообнаружение'
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
ms.openlocfilehash: 236a3625b755697580e57c926dd5714a44c0347f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="a2b87-102">Сводка по DNS — автообнаружение в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2b87-102">DNS summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2b87-103">_**Последнее изменение темы:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="a2b87-103">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="a2b87-104">Автообнаружение — это гибкая служба, в которой она будет принимать связь по протоколу HTTP или HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a2b87-104">Autodiscover is a flexible service in that it will accept communication over HTTP or HTTPS.</span></span> <span data-ttu-id="a2b87-105">Для этого необходимо правильно настроить систему доменных имен (DNS) и сертификаты, используемые серверами, на которых размещается служба автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="a2b87-105">To accomplish this, the domain name system (DNS) and the certificates used by servers that host the Autodiscover service must be configured correctly.</span></span> <span data-ttu-id="a2b87-106">Требования к сертификатам описаны в разделе [сведения о сертификатах — автообнаружение в Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).</span><span class="sxs-lookup"><span data-stu-id="a2b87-106">Certificate requirements are covered in [Certificate summary - Autodiscover in Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a2b87-107">Логика поиска DNS для клиентов Lync Server использует определенный порядок разрешения.</span><span class="sxs-lookup"><span data-stu-id="a2b87-107">DNS lookup logic for the Lync Server clients uses a specific order of resolution.</span></span> <span data-ttu-id="a2b87-108">Всегда следует включать как lyncdiscoverinternal. &lt;Domain&gt; и lyncdiscover. &lt;домен&gt; в службе DNS.</span><span class="sxs-lookup"><span data-stu-id="a2b87-108">You should always include both the lyncdiscoverinternal.&lt;domain&gt; and the lyncdiscover.&lt;domain&gt; in your DNS.</span></span> <span data-ttu-id="a2b87-109">Исключение lyncdiscoverinternal. &lt;в&gt; результате записи домена внутренние клиенты не смогут подключаться к необходимым службам или получать неверный ответ автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="a2b87-109">Excluding the lyncdiscoverinternal.&lt;domain&gt; record will cause internal clients to fail to connect to the intended services or receive the incorrect Autodiscover response.</span></span>



</div>

### <a name="internal-dns-records"></a><span data-ttu-id="a2b87-110">Внутренние записи DNS</span><span class="sxs-lookup"><span data-stu-id="a2b87-110">Internal DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a2b87-111">Тип записи</span><span class="sxs-lookup"><span data-stu-id="a2b87-111">Record type</span></span></th>
<th><span data-ttu-id="a2b87-112">Имя узла</span><span class="sxs-lookup"><span data-stu-id="a2b87-112">Host name</span></span></th>
<th><span data-ttu-id="a2b87-113">Разрешается в</span><span class="sxs-lookup"><span data-stu-id="a2b87-113">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2b87-114">CNAME</span><span class="sxs-lookup"><span data-stu-id="a2b87-114">CNAME</span></span></p></td>
<td><p><span data-ttu-id="a2b87-115">Lyncdiscoverinternal. &lt;внутреннее доменное имя&gt;</span><span class="sxs-lookup"><span data-stu-id="a2b87-115">Lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="a2b87-116">Полное доменное имя внутренних веб-служб для пула директоров, если таковой имеется, или для пула переднего плана, если у вас нет директора.</span><span class="sxs-lookup"><span data-stu-id="a2b87-116">Internal Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2b87-117">A (узел, если используется IPv6, AAAA)</span><span class="sxs-lookup"><span data-stu-id="a2b87-117">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="a2b87-118">lyncdiscoverinternal. &lt;внутреннее доменное имя&gt;</span><span class="sxs-lookup"><span data-stu-id="a2b87-118">lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="a2b87-119">IP-адрес внутренних веб-служб (виртуальный IP-адрес), если вы используете подсистему балансировки нагрузки для пула директоров (если у вас есть один или из интерфейсного пула, если у вас нет директора).</span><span class="sxs-lookup"><span data-stu-id="a2b87-119">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a2b87-120">Необходимо создать одну из следующих внешних DNS-записей:</span><span class="sxs-lookup"><span data-stu-id="a2b87-120">You need to create one of the following external DNS records:</span></span>

### <a name="external-dns-records"></a><span data-ttu-id="a2b87-121">Внешние записи DNS</span><span class="sxs-lookup"><span data-stu-id="a2b87-121">External DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a2b87-122">Тип записи</span><span class="sxs-lookup"><span data-stu-id="a2b87-122">Record type</span></span></th>
<th><span data-ttu-id="a2b87-123">Имя узла</span><span class="sxs-lookup"><span data-stu-id="a2b87-123">Host name</span></span></th>
<th><span data-ttu-id="a2b87-124">Разрешается в</span><span class="sxs-lookup"><span data-stu-id="a2b87-124">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2b87-125">CNAME</span><span class="sxs-lookup"><span data-stu-id="a2b87-125">CNAME</span></span></p></td>
<td><p><span data-ttu-id="a2b87-126">lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="a2b87-126">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="a2b87-127">Полное доменное имя внешних веб-служб для пула директоров, если таковой имеется, или для пула переднего плана, если у вас нет директора.</span><span class="sxs-lookup"><span data-stu-id="a2b87-127">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2b87-128">A (узел, если используется IPv6, AAAA)</span><span class="sxs-lookup"><span data-stu-id="a2b87-128">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="a2b87-129">lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="a2b87-129">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="a2b87-130">Внешний или общедоступный IP-адрес обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="a2b87-130">External or public IP address of the reverse proxy.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="a2b87-131">Внешний трафик проходит через обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="a2b87-131">External traffic goes through the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="a2b87-132">Клиенты мобильных устройств не поддерживают множество сертификатов SSL из разных доменов.</span><span class="sxs-lookup"><span data-stu-id="a2b87-132">Mobile device clients do not support multiple Secure Sockets Layer (SSL) certificates from different domains.</span></span> <span data-ttu-id="a2b87-133">Поэтому перенаправление CNAME в различные домены по протоколу HTTPS не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="a2b87-133">Therefore, CNAME redirection to different domains is not supported over HTTPS.</span></span> <span data-ttu-id="a2b87-134">Например, запись DNS CNAME для домена lyncdiscover.contoso.com, которая выполняет перенаправление на адрес director.contoso.net, не поддерживается по протоколу HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a2b87-134">For example, a DNS CNAME record for lyncdiscover.contoso.com that redirects to an address of director.contoso.net is not supported over HTTPS.</span></span> <span data-ttu-id="a2b87-135">В такой топологии клиент мобильного устройства должен использовать HTTP для первого запроса, чтобы перенаправление CNAME разрешалось по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="a2b87-135">In such a topology, a mobile device client needs to use HTTP for the first request, so that the CNAME redirection is resolved over HTTP.</span></span> <span data-ttu-id="a2b87-136">Последующие запросы могут использовать HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a2b87-136">Subsequent requests then use HTTPS.</span></span> <span data-ttu-id="a2b87-137">Для поддержки этого сценария необходимо настроить обратный прокси-сервер с использованием правила веб-публикации для порта 80 (HTTP).</span><span class="sxs-lookup"><span data-stu-id="a2b87-137">To support this scenario, you need to configure your reverse proxy with a web publishing rule for port 80 (HTTP).</span></span> <span data-ttu-id="a2b87-138">Сведения о том, как создать правило веб-публикации для порта 80 "в разделе <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Настройка обратного прокси-сервера для мобильной работы в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a2b87-138">For details, see "To create a web publishing rule for port 80" in <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</A>.</span></span> <span data-ttu-id="a2b87-139">Перенаправление CNAME в тот же домен поддерживается по протоколу HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a2b87-139">CNAME redirection to the same domain is supported over HTTPS.</span></span> <span data-ttu-id="a2b87-140">В этом случае сертификат конечного домена охватывает исходный домен.</span><span class="sxs-lookup"><span data-stu-id="a2b87-140">In this case, the destination domain's certificate covers the originating domain.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a2b87-141">См. также</span><span class="sxs-lookup"><span data-stu-id="a2b87-141">See Also</span></span>


[<span data-ttu-id="a2b87-142">Настройка обратного прокси-сервера для мобильной работы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2b87-142">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[<span data-ttu-id="a2b87-143">Сводка по сертификатам — автообнаружение в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2b87-143">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

