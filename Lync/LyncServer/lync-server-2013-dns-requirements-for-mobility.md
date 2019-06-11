---
title: 'Lync Server 2013: требования к DNS для мобильных устройств'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for mobility
ms:assetid: df6962bc-2a16-440e-a333-022ebd14f957
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690040(v=OCS.15)
ms:contentKeyID: 48185624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fb933e20b8da627ad48a30802ff86c7ed95faff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-mobility-with-lync-server-2013"></a><span data-ttu-id="e0605-102">Требования к DNS для мобильных устройств с помощью Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0605-102">DNS requirements for mobility with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0605-103">_**Тема последнего изменения:** 2012-11-13_</span><span class="sxs-lookup"><span data-stu-id="e0605-103">_**Topic Last Modified:** 2012-11-13_</span></span>

<span data-ttu-id="e0605-104">При развертывании функции Lync Server 2013 Mobility Service вы можете использовать новые URL-адреса, доступные в службе автообнаружения Microsoft Lync Server 2013, или использовать существующие URL.</span><span class="sxs-lookup"><span data-stu-id="e0605-104">When you deploy the Lync Server 2013 mobility feature, you can use the new URLs that are available with the Microsoft Lync Server 2013 Autodiscover Service, or you can use your existing Web Services URLs.</span></span> <span data-ttu-id="e0605-105">Если вы используете существующие URL-адреса, пользователи должны вручную ввести URL-адреса в параметры мобильного устройства.</span><span class="sxs-lookup"><span data-stu-id="e0605-105">If you use your existing URLs, users need to manually enter the URLs in their mobile device settings.</span></span> <span data-ttu-id="e0605-106">Этот параметр обычно используется для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="e0605-106">This option is typically used for troubleshooting.</span></span> <span data-ttu-id="e0605-107">При использовании новых URL-адресов мобильные клиенты могут автоматически определять ресурсы Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e0605-107">When you use the new URLs, mobile clients can automatically discover Lync Server 2013 resources.</span></span> <span data-ttu-id="e0605-108">Если вы поддерживаете автоматическое обнаружение, вам нужно добавить новые записи DNS.</span><span class="sxs-lookup"><span data-stu-id="e0605-108">When you support automatic discovery, you need to add new Domain Name System (DNS) records.</span></span> <span data-ttu-id="e0605-109">В этом разделе описаны записи DNS, необходимые для автоматического обнаружения.</span><span class="sxs-lookup"><span data-stu-id="e0605-109">This section describes the DNS records that are required for automatic discovery.</span></span>

<span data-ttu-id="e0605-110">Для поддержки автоматического обнаружения необходимо создать следующие записи DNS для каждого домена SIP:</span><span class="sxs-lookup"><span data-stu-id="e0605-110">To support automatic discovery, you need to create the following DNS records for each SIP domain:</span></span>

  - <span data-ttu-id="e0605-111">Внутренняя запись DNS для поддержки мобильных пользователей, которые подключаются из сети Организации</span><span class="sxs-lookup"><span data-stu-id="e0605-111">An internal DNS record to support mobile users who connect from within your organization's network</span></span>

  - <span data-ttu-id="e0605-112">Внешняя (или общедоступная) запись DNS для поддержки мобильных пользователей, подключающихся из Интернета;</span><span class="sxs-lookup"><span data-stu-id="e0605-112">An external, or public, DNS record to support mobile users who connect from the Internet</span></span>

<span data-ttu-id="e0605-113">Внутренний URL-адрес автоматического обнаружения не должен быть адресом за пределами вашей сети.</span><span class="sxs-lookup"><span data-stu-id="e0605-113">The internal automatic discovery URL should not be addressable from outside your network.</span></span> <span data-ttu-id="e0605-114">URL-адрес внешнего автоматического обнаружения не должен быть адресом в сети.</span><span class="sxs-lookup"><span data-stu-id="e0605-114">The external automatic discovery URL should not be addressable from within your network.</span></span> <span data-ttu-id="e0605-115">Тем не менее, если вы не можете выполнить это требование для внешнего URL-адреса, не следует повлиять на мобильный клиент.</span><span class="sxs-lookup"><span data-stu-id="e0605-115">However, if you cannot meet this requirement for the external URL, mobile client functionally should not be affected.</span></span>

<span data-ttu-id="e0605-116">DNS-записи могут быть либо записями CNAME, либо записями (ведущими).</span><span class="sxs-lookup"><span data-stu-id="e0605-116">The DNS records can be either CNAME records or A (host) records.</span></span>

<span data-ttu-id="e0605-117">**Внутренние DNS-записи**</span><span class="sxs-lookup"><span data-stu-id="e0605-117">**Internal DNS records**</span></span>

<span data-ttu-id="e0605-118">Вам нужно создать одну из следующих внутренних DNS-записей:</span><span class="sxs-lookup"><span data-stu-id="e0605-118">You need to create one of the following internal DNS records:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0605-119">Тип записи</span><span class="sxs-lookup"><span data-stu-id="e0605-119">Record type</span></span></th>
<th><span data-ttu-id="e0605-120">Определение имени узла или SRV</span><span class="sxs-lookup"><span data-stu-id="e0605-120">Host name or SRV definition</span></span></th>
<th><span data-ttu-id="e0605-121">Разрешается в</span><span class="sxs-lookup"><span data-stu-id="e0605-121">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0605-122">CNAME</span><span class="sxs-lookup"><span data-stu-id="e0605-122">CNAME</span></span></p></td>
<td><p><span data-ttu-id="e0605-123">линкдисковеринтернал. &lt;сипдомаин&gt;</span><span class="sxs-lookup"><span data-stu-id="e0605-123">lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="e0605-124">Полное доменное имя (FQDN) внутренних веб-служб для пула, если у вас есть один из них или для пула переднего плана, если у вас нет директора</span><span class="sxs-lookup"><span data-stu-id="e0605-124">Internal Web Services fully qualified domain name (FQDN) for your Director pool, if you have one, or for your Front End pool if you do not have a Director</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0605-125">A (узел)</span><span class="sxs-lookup"><span data-stu-id="e0605-125">A (host)</span></span></p></td>
<td><p><span data-ttu-id="e0605-126">линкдисковеринтернал. &lt;сипдомаин&gt;</span><span class="sxs-lookup"><span data-stu-id="e0605-126">lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="e0605-127">IP-адрес внутренних веб-служб (VIP) (виртуальный IP-адрес) Если вы используете подсистему балансировки нагрузки в вашем пуле, если у вас есть один из них или у вас нет интерфейса, если у вас нет директора</span><span class="sxs-lookup"><span data-stu-id="e0605-127">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e0605-128">**Внешние записи DNS**</span><span class="sxs-lookup"><span data-stu-id="e0605-128">**External DNS records**</span></span>

<span data-ttu-id="e0605-129">Вам необходимо создать одну из следующих внешних DNS-записей:</span><span class="sxs-lookup"><span data-stu-id="e0605-129">You need to create one of the following external DNS records:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0605-130">Тип записи</span><span class="sxs-lookup"><span data-stu-id="e0605-130">Record type</span></span></th>
<th><span data-ttu-id="e0605-131">Имя узла</span><span class="sxs-lookup"><span data-stu-id="e0605-131">Host name</span></span></th>
<th><span data-ttu-id="e0605-132">Разрешается в</span><span class="sxs-lookup"><span data-stu-id="e0605-132">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0605-133">CNAME</span><span class="sxs-lookup"><span data-stu-id="e0605-133">CNAME</span></span></p></td>
<td><p><span data-ttu-id="e0605-134">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="e0605-134">lyncdiscover.</span></span> <span data-ttu-id="e0605-135">&lt;сипдомаин&gt;</span><span class="sxs-lookup"><span data-stu-id="e0605-135">&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="e0605-136">Внешнее полное доменное имя веб-служб для пула, если у вас есть один из них или для пула переднего плана, если у вас нет директора</span><span class="sxs-lookup"><span data-stu-id="e0605-136">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0605-137">A (узел)</span><span class="sxs-lookup"><span data-stu-id="e0605-137">A (host)</span></span></p></td>
<td><p><span data-ttu-id="e0605-138">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="e0605-138">lyncdiscover.</span></span> <span data-ttu-id="e0605-139">&lt;сипдомаин&gt;</span><span class="sxs-lookup"><span data-stu-id="e0605-139">&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="e0605-140">Внешний или общий IP-адрес (VIP, если вы используете подсистему балансировки нагрузки) для обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="e0605-140">External or public IP address (VIP address if you use a load balancer) of the reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0605-141">SRV</span><span class="sxs-lookup"><span data-stu-id="e0605-141">SRV</span></span></p></td>
<td><p><span data-ttu-id="e0605-142">_sipfederationtls._tcp.</span><span class="sxs-lookup"><span data-stu-id="e0605-142">_sipfederationtls._tcp.</span></span> <span data-ttu-id="e0605-143">&lt;сипдомаин&gt;</span><span class="sxs-lookup"><span data-stu-id="e0605-143">&lt;sipdomain&gt;</span></span></p>
<p><span data-ttu-id="e0605-144">Разрешение на запись узла (A или AAAA) для службы пограничного доступа</span><span class="sxs-lookup"><span data-stu-id="e0605-144">Resolves to host (A or AAAA) record for the Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="e0605-145">Для поддержки службы push-уведомлений и службы push-уведомлений Apple вы создаете одну запись SRV для каждого домена SIP, у которого есть мобильные клиенты Microsoft Lync.</span><span class="sxs-lookup"><span data-stu-id="e0605-145">To support Push Notification Service and Apple Push Notification service, you create one SRV record for each SIP domain that has Microsoft Lync Mobile clients.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="e0605-146">Это требование относится только к клиентам Microsoft Lync Mobile на мобильных устройствах Apple и Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e0605-146">This requirement applies only to Microsoft Lync Mobile clients on Apple or Microsoft based mobile devices.</span></span> <span data-ttu-id="e0605-147">Устройства андриод и Nokia Symbian не используют push-уведомление.</span><span class="sxs-lookup"><span data-stu-id="e0605-147">Andriod and Nokia Symbian devices do not use push notification.</span></span>


</div></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="e0605-148">Lyncdiscover, также называемый автообнаружением, трафик проходит через обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="e0605-148">Lyncdiscover, also known as autodiscover, traffic goes through the reverse proxy.</span></span> <span data-ttu-id="e0605-149">Запись SRV указывает на запись, которая разрешается службой Edge Access.</span><span class="sxs-lookup"><span data-stu-id="e0605-149">SRV record points to a record that resolves through the Access Edge service.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

