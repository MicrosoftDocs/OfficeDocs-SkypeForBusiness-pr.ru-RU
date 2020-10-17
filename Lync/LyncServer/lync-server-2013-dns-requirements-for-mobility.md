---
title: 'Lync Server 2013: требования к DNS для мобильных устройств'
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
ms.openlocfilehash: 508e9c8e030de7aeb496a1285ff7b965e43c2a6b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501436"
---
# <a name="dns-requirements-for-mobility-with-lync-server-2013"></a><span data-ttu-id="aa94e-102">Требования DNS для мобильных устройств с Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa94e-102">DNS requirements for mobility with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa94e-103">_**Последнее изменение темы:** 2012-11-13_</span><span class="sxs-lookup"><span data-stu-id="aa94e-103">_**Topic Last Modified:** 2012-11-13_</span></span>

<span data-ttu-id="aa94e-104">При развертывании компонента Lync Server 2013 Mobility можно использовать новые URL-адреса, доступные в службе автообнаружения Microsoft Lync Server 2013, или использовать существующие URL-адреса веб-служб.</span><span class="sxs-lookup"><span data-stu-id="aa94e-104">When you deploy the Lync Server 2013 mobility feature, you can use the new URLs that are available with the Microsoft Lync Server 2013 Autodiscover Service, or you can use your existing Web Services URLs.</span></span> <span data-ttu-id="aa94e-105">Если вы используете существующие URL-адреса, пользователям необходимо вручную вводить эти URL-адреса в параметрах мобильного устройства.</span><span class="sxs-lookup"><span data-stu-id="aa94e-105">If you use your existing URLs, users need to manually enter the URLs in their mobile device settings.</span></span> <span data-ttu-id="aa94e-106">Данный вариант обычно используется для поиска и устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="aa94e-106">This option is typically used for troubleshooting.</span></span> <span data-ttu-id="aa94e-107">При использовании новых URL-адресов мобильные клиенты могут автоматически обнаруживать ресурсы Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aa94e-107">When you use the new URLs, mobile clients can automatically discover Lync Server 2013 resources.</span></span> <span data-ttu-id="aa94e-108">В случае обеспечения поддержки автоматического обнаружения вам требуется добавить новые DNS-записи.</span><span class="sxs-lookup"><span data-stu-id="aa94e-108">When you support automatic discovery, you need to add new Domain Name System (DNS) records.</span></span> <span data-ttu-id="aa94e-109">В этом разделе описаны те DNS-записи, которые требуются для автоматического обнаружения.</span><span class="sxs-lookup"><span data-stu-id="aa94e-109">This section describes the DNS records that are required for automatic discovery.</span></span>

<span data-ttu-id="aa94e-110">Чтобы обеспечить поддержку автоматического обнаружения, вам необходимо создать следующие DNS-записи для каждого домена SIP:</span><span class="sxs-lookup"><span data-stu-id="aa94e-110">To support automatic discovery, you need to create the following DNS records for each SIP domain:</span></span>

  - <span data-ttu-id="aa94e-111">Внутренняя DNS-запись для поддержки мобильных пользователей, которые подключаются изнутри сети организации</span><span class="sxs-lookup"><span data-stu-id="aa94e-111">An internal DNS record to support mobile users who connect from within your organization's network</span></span>

  - <span data-ttu-id="aa94e-112">Внешняя ? или общая ? DNS-запись для поддержки мобильных пользователей, которые подключаются из Интернета</span><span class="sxs-lookup"><span data-stu-id="aa94e-112">An external, or public, DNS record to support mobile users who connect from the Internet</span></span>

<span data-ttu-id="aa94e-p102">Внутренний URL-адрес автообнаружения не должен поддерживать обращение извне сети. Внешний URL-адрес автообнаружения не должен поддерживать обращение из вашей сети. Однако если вы не можете выполнить данное условие для внешнего URL-адреса, это не окажет негативного влияния на функциональные возможности мобильного клиента.</span><span class="sxs-lookup"><span data-stu-id="aa94e-p102">The internal automatic discovery URL should not be addressable from outside your network. The external automatic discovery URL should not be addressable from within your network. However, if you cannot meet this requirement for the external URL, mobile client functionally should not be affected.</span></span>

<span data-ttu-id="aa94e-116">DNS-записи могут быть либо записями CNAME, либо A (узла).</span><span class="sxs-lookup"><span data-stu-id="aa94e-116">The DNS records can be either CNAME records or A (host) records.</span></span>

<span data-ttu-id="aa94e-117">**Внутренние DNS-записи**</span><span class="sxs-lookup"><span data-stu-id="aa94e-117">**Internal DNS records**</span></span>

<span data-ttu-id="aa94e-118">Вам необходимо создать одну из следующих внутренних DNS-записей:</span><span class="sxs-lookup"><span data-stu-id="aa94e-118">You need to create one of the following internal DNS records:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa94e-119">Тип записи</span><span class="sxs-lookup"><span data-stu-id="aa94e-119">Record type</span></span></th>
<th><span data-ttu-id="aa94e-120">Имя узла или определение SRV</span><span class="sxs-lookup"><span data-stu-id="aa94e-120">Host name or SRV definition</span></span></th>
<th><span data-ttu-id="aa94e-121">Разрешается в</span><span class="sxs-lookup"><span data-stu-id="aa94e-121">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa94e-122">CNAME</span><span class="sxs-lookup"><span data-stu-id="aa94e-122">CNAME</span></span></p></td>
<td><p><span data-ttu-id="aa94e-123">lyncdiscoverinternal. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="aa94e-123">lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="aa94e-124">Полное доменное имя внутренних веб-служб (полное доменное имя) для пула директоров (если у вас есть) или для пула переднего плана, если у вас нет директора</span><span class="sxs-lookup"><span data-stu-id="aa94e-124">Internal Web Services fully qualified domain name (FQDN) for your Director pool, if you have one, or for your Front End pool if you do not have a Director</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa94e-125">A (узел)</span><span class="sxs-lookup"><span data-stu-id="aa94e-125">A (host)</span></span></p></td>
<td><p><span data-ttu-id="aa94e-126">lyncdiscoverinternal. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="aa94e-126">lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="aa94e-127">IP-адрес внутренних веб-служб (виртуальный IP-адрес, если вы используете подсистему балансировки нагрузки) пула директоров (если у вас есть один или из интерфейсного пула, если у вас нет директора)</span><span class="sxs-lookup"><span data-stu-id="aa94e-127">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="aa94e-128">**Внешние DNS-записи**</span><span class="sxs-lookup"><span data-stu-id="aa94e-128">**External DNS records**</span></span>

<span data-ttu-id="aa94e-129">Вам необходимо создать одну из следующих внешних DNS-записей:</span><span class="sxs-lookup"><span data-stu-id="aa94e-129">You need to create one of the following external DNS records:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa94e-130">Тип записи</span><span class="sxs-lookup"><span data-stu-id="aa94e-130">Record type</span></span></th>
<th><span data-ttu-id="aa94e-131">Имя узла</span><span class="sxs-lookup"><span data-stu-id="aa94e-131">Host name</span></span></th>
<th><span data-ttu-id="aa94e-132">Разрешается в</span><span class="sxs-lookup"><span data-stu-id="aa94e-132">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa94e-133">CNAME</span><span class="sxs-lookup"><span data-stu-id="aa94e-133">CNAME</span></span></p></td>
<td><p><span data-ttu-id="aa94e-134">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="aa94e-134">lyncdiscover.</span></span> <span data-ttu-id="aa94e-135">&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="aa94e-135">&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="aa94e-136">Полное доменное имя внешних веб-служб для пула директоров, если таковой имеется, или для пула переднего плана, если у вас нет директора</span><span class="sxs-lookup"><span data-stu-id="aa94e-136">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa94e-137">A (узел)</span><span class="sxs-lookup"><span data-stu-id="aa94e-137">A (host)</span></span></p></td>
<td><p><span data-ttu-id="aa94e-138">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="aa94e-138">lyncdiscover.</span></span> <span data-ttu-id="aa94e-139">&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="aa94e-139">&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="aa94e-140">Внешний или общий IP-адрес (виртуальный IP-адрес, если вы используете подсистему балансировки нагрузки) обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="aa94e-140">External or public IP address (VIP address if you use a load balancer) of the reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa94e-141">SRV</span><span class="sxs-lookup"><span data-stu-id="aa94e-141">SRV</span></span></p></td>
<td><p><span data-ttu-id="aa94e-142">_sipfederationtls _sipfederationtls._tcp.</span><span class="sxs-lookup"><span data-stu-id="aa94e-142">_sipfederationtls._tcp.</span></span> <span data-ttu-id="aa94e-143">&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="aa94e-143">&lt;sipdomain&gt;</span></span></p>
<p><span data-ttu-id="aa94e-144">Разрешается в запись узла (A или AAAA) для службы пограничного доступа</span><span class="sxs-lookup"><span data-stu-id="aa94e-144">Resolves to host (A or AAAA) record for the Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="aa94e-145">Чтобы поддерживать службу push-уведомлений и службу push-уведомлений Apple, создайте одну запись SRV для каждого домена SIP с клиентами Microsoft Lync Mobile.</span><span class="sxs-lookup"><span data-stu-id="aa94e-145">To support Push Notification Service and Apple Push Notification service, you create one SRV record for each SIP domain that has Microsoft Lync Mobile clients.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="aa94e-146">Это требование относится только к клиентам Microsoft Lync Mobile на мобильных устройствах Apple и Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="aa94e-146">This requirement applies only to Microsoft Lync Mobile clients on Apple or Microsoft based mobile devices.</span></span> <span data-ttu-id="aa94e-147">Устройства Android и Nokia Symbian не используют push-уведомления.</span><span class="sxs-lookup"><span data-stu-id="aa94e-147">Andriod and Nokia Symbian devices do not use push notification.</span></span>


</div></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="aa94e-148">Lyncdiscover, также называемый автообнаружением, трафик проходит через обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="aa94e-148">Lyncdiscover, also known as autodiscover, traffic goes through the reverse proxy.</span></span> <span data-ttu-id="aa94e-149">Запись SRV указывает на запись, которая разрешается через пограничный сервер доступа.</span><span class="sxs-lookup"><span data-stu-id="aa94e-149">SRV record points to a record that resolves through the Access Edge service.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

