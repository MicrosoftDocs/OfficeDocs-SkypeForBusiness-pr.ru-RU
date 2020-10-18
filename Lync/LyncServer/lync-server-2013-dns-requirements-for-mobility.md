---
title: 'Lync Server 2013: требования к DNS для мобильных устройств'
description: 'Lync Server 2013: требования к DNS для мобильных устройств.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for mobility
ms:assetid: df6962bc-2a16-440e-a333-022ebd14f957
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690040(v=OCS.15)
ms:contentKeyID: 48185624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2a8377dc7c856bb7250817cb3b8b66ed7789d3b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574305"
---
# <a name="dns-requirements-for-mobility-with-lync-server-2013"></a><span data-ttu-id="65d0c-103">Требования DNS для мобильных устройств с Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65d0c-103">DNS requirements for mobility with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65d0c-104">_**Последнее изменение темы:** 2012-11-13_</span><span class="sxs-lookup"><span data-stu-id="65d0c-104">_**Topic Last Modified:** 2012-11-13_</span></span>

<span data-ttu-id="65d0c-105">При развертывании компонента Lync Server 2013 Mobility можно использовать новые URL-адреса, доступные в службе автообнаружения Microsoft Lync Server 2013, или использовать существующие URL-адреса веб-служб.</span><span class="sxs-lookup"><span data-stu-id="65d0c-105">When you deploy the Lync Server 2013 mobility feature, you can use the new URLs that are available with the Microsoft Lync Server 2013 Autodiscover Service, or you can use your existing Web Services URLs.</span></span> <span data-ttu-id="65d0c-106">Если вы используете существующие URL-адреса, пользователям необходимо вручную вводить эти URL-адреса в параметрах мобильного устройства.</span><span class="sxs-lookup"><span data-stu-id="65d0c-106">If you use your existing URLs, users need to manually enter the URLs in their mobile device settings.</span></span> <span data-ttu-id="65d0c-107">Данный вариант обычно используется для поиска и устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="65d0c-107">This option is typically used for troubleshooting.</span></span> <span data-ttu-id="65d0c-108">При использовании новых URL-адресов мобильные клиенты могут автоматически обнаруживать ресурсы Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="65d0c-108">When you use the new URLs, mobile clients can automatically discover Lync Server 2013 resources.</span></span> <span data-ttu-id="65d0c-109">В случае обеспечения поддержки автоматического обнаружения вам требуется добавить новые DNS-записи.</span><span class="sxs-lookup"><span data-stu-id="65d0c-109">When you support automatic discovery, you need to add new Domain Name System (DNS) records.</span></span> <span data-ttu-id="65d0c-110">В этом разделе описаны те DNS-записи, которые требуются для автоматического обнаружения.</span><span class="sxs-lookup"><span data-stu-id="65d0c-110">This section describes the DNS records that are required for automatic discovery.</span></span>

<span data-ttu-id="65d0c-111">Чтобы обеспечить поддержку автоматического обнаружения, вам необходимо создать следующие DNS-записи для каждого домена SIP:</span><span class="sxs-lookup"><span data-stu-id="65d0c-111">To support automatic discovery, you need to create the following DNS records for each SIP domain:</span></span>

  - <span data-ttu-id="65d0c-112">Внутренняя DNS-запись для поддержки мобильных пользователей, которые подключаются изнутри сети организации</span><span class="sxs-lookup"><span data-stu-id="65d0c-112">An internal DNS record to support mobile users who connect from within your organization's network</span></span>

  - <span data-ttu-id="65d0c-113">Внешняя ? или общая ? DNS-запись для поддержки мобильных пользователей, которые подключаются из Интернета</span><span class="sxs-lookup"><span data-stu-id="65d0c-113">An external, or public, DNS record to support mobile users who connect from the Internet</span></span>

<span data-ttu-id="65d0c-p102">Внутренний URL-адрес автообнаружения не должен поддерживать обращение извне сети. Внешний URL-адрес автообнаружения не должен поддерживать обращение из вашей сети. Однако если вы не можете выполнить данное условие для внешнего URL-адреса, это не окажет негативного влияния на функциональные возможности мобильного клиента.</span><span class="sxs-lookup"><span data-stu-id="65d0c-p102">The internal automatic discovery URL should not be addressable from outside your network. The external automatic discovery URL should not be addressable from within your network. However, if you cannot meet this requirement for the external URL, mobile client functionally should not be affected.</span></span>

<span data-ttu-id="65d0c-117">DNS-записи могут быть либо записями CNAME, либо A (узла).</span><span class="sxs-lookup"><span data-stu-id="65d0c-117">The DNS records can be either CNAME records or A (host) records.</span></span>

<span data-ttu-id="65d0c-118">**Внутренние DNS-записи**</span><span class="sxs-lookup"><span data-stu-id="65d0c-118">**Internal DNS records**</span></span>

<span data-ttu-id="65d0c-119">Вам необходимо создать одну из следующих внутренних DNS-записей:</span><span class="sxs-lookup"><span data-stu-id="65d0c-119">You need to create one of the following internal DNS records:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="65d0c-120">Тип записи</span><span class="sxs-lookup"><span data-stu-id="65d0c-120">Record type</span></span></th>
<th><span data-ttu-id="65d0c-121">Имя узла или определение SRV</span><span class="sxs-lookup"><span data-stu-id="65d0c-121">Host name or SRV definition</span></span></th>
<th><span data-ttu-id="65d0c-122">Разрешается в</span><span class="sxs-lookup"><span data-stu-id="65d0c-122">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65d0c-123">CNAME</span><span class="sxs-lookup"><span data-stu-id="65d0c-123">CNAME</span></span></p></td>
<td><p><span data-ttu-id="65d0c-124">lyncdiscoverinternal. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="65d0c-124">lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="65d0c-125">Полное доменное имя внутренних веб-служб (полное доменное имя) для пула директоров (если у вас есть) или для пула переднего плана, если у вас нет директора</span><span class="sxs-lookup"><span data-stu-id="65d0c-125">Internal Web Services fully qualified domain name (FQDN) for your Director pool, if you have one, or for your Front End pool if you do not have a Director</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65d0c-126">A (узел)</span><span class="sxs-lookup"><span data-stu-id="65d0c-126">A (host)</span></span></p></td>
<td><p><span data-ttu-id="65d0c-127">lyncdiscoverinternal. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="65d0c-127">lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="65d0c-128">IP-адрес внутренних веб-служб (виртуальный IP-адрес, если вы используете подсистему балансировки нагрузки) пула директоров (если у вас есть один или из интерфейсного пула, если у вас нет директора)</span><span class="sxs-lookup"><span data-stu-id="65d0c-128">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="65d0c-129">**Внешние DNS-записи**</span><span class="sxs-lookup"><span data-stu-id="65d0c-129">**External DNS records**</span></span>

<span data-ttu-id="65d0c-130">Вам необходимо создать одну из следующих внешних DNS-записей:</span><span class="sxs-lookup"><span data-stu-id="65d0c-130">You need to create one of the following external DNS records:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="65d0c-131">Тип записи</span><span class="sxs-lookup"><span data-stu-id="65d0c-131">Record type</span></span></th>
<th><span data-ttu-id="65d0c-132">Имя узла</span><span class="sxs-lookup"><span data-stu-id="65d0c-132">Host name</span></span></th>
<th><span data-ttu-id="65d0c-133">Разрешается в</span><span class="sxs-lookup"><span data-stu-id="65d0c-133">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65d0c-134">CNAME</span><span class="sxs-lookup"><span data-stu-id="65d0c-134">CNAME</span></span></p></td>
<td><p><span data-ttu-id="65d0c-135">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="65d0c-135">lyncdiscover.</span></span> <span data-ttu-id="65d0c-136">&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="65d0c-136">&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="65d0c-137">Полное доменное имя внешних веб-служб для пула директоров, если таковой имеется, или для пула переднего плана, если у вас нет директора</span><span class="sxs-lookup"><span data-stu-id="65d0c-137">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65d0c-138">A (узел)</span><span class="sxs-lookup"><span data-stu-id="65d0c-138">A (host)</span></span></p></td>
<td><p><span data-ttu-id="65d0c-139">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="65d0c-139">lyncdiscover.</span></span> <span data-ttu-id="65d0c-140">&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="65d0c-140">&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="65d0c-141">Внешний или общий IP-адрес (виртуальный IP-адрес, если вы используете подсистему балансировки нагрузки) обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="65d0c-141">External or public IP address (VIP address if you use a load balancer) of the reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65d0c-142">SRV</span><span class="sxs-lookup"><span data-stu-id="65d0c-142">SRV</span></span></p></td>
<td><p><span data-ttu-id="65d0c-143">_sipfederationtls _sipfederationtls._tcp.</span><span class="sxs-lookup"><span data-stu-id="65d0c-143">_sipfederationtls._tcp.</span></span> <span data-ttu-id="65d0c-144">&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="65d0c-144">&lt;sipdomain&gt;</span></span></p>
<p><span data-ttu-id="65d0c-145">Разрешается в запись узла (A или AAAA) для службы пограничного доступа</span><span class="sxs-lookup"><span data-stu-id="65d0c-145">Resolves to host (A or AAAA) record for the Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="65d0c-146">Чтобы поддерживать службу push-уведомлений и службу push-уведомлений Apple, создайте одну запись SRV для каждого домена SIP с клиентами Microsoft Lync Mobile.</span><span class="sxs-lookup"><span data-stu-id="65d0c-146">To support Push Notification Service and Apple Push Notification service, you create one SRV record for each SIP domain that has Microsoft Lync Mobile clients.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="65d0c-147">Это требование относится только к клиентам Microsoft Lync Mobile на мобильных устройствах Apple и Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="65d0c-147">This requirement applies only to Microsoft Lync Mobile clients on Apple or Microsoft based mobile devices.</span></span> <span data-ttu-id="65d0c-148">Устройства Android и Nokia Symbian не используют push-уведомления.</span><span class="sxs-lookup"><span data-stu-id="65d0c-148">Andriod and Nokia Symbian devices do not use push notification.</span></span>


</div></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="65d0c-149">Lyncdiscover, также называемый автообнаружением, трафик проходит через обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="65d0c-149">Lyncdiscover, also known as autodiscover, traffic goes through the reverse proxy.</span></span> <span data-ttu-id="65d0c-150">Запись SRV указывает на запись, которая разрешается через пограничный сервер доступа.</span><span class="sxs-lookup"><span data-stu-id="65d0c-150">SRV record points to a record that resolves through the Access Edge service.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

