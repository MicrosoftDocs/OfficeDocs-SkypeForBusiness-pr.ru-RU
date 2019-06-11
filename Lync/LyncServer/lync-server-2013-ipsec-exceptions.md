---
title: Исключения для Lync Server 2013 IPsec
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IPsec exceptions
ms:assetid: 241f1eca-6f2f-44de-90b1-2cb659cbe27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425719(v=OCS.15)
ms:contentKeyID: 48183627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eae9061036c91793800fd744338347196d60494c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="f165b-102">Исключения IPsec в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f165b-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f165b-103">_**Тема последнего изменения:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="f165b-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="f165b-104">Для корпоративных сетей, где развернута безопасность протокола IP (IPsec) (ознакомьтесь со статьей IETF RFC 4301-4309), необходимо отключить IPsec для диапазона портов, используемых для доставки звуковых, видеофайлов и панорамных видео.</span><span class="sxs-lookup"><span data-stu-id="f165b-104">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video.</span></span> <span data-ttu-id="f165b-105">Согласно рекомендациям, необходимо избегать задержек при выделении портов носителей из-за согласования IPsec.</span><span class="sxs-lookup"><span data-stu-id="f165b-105">The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="f165b-106">В приведенной ниже таблице описаны рекомендуемые параметры исключений IPsec.</span><span class="sxs-lookup"><span data-stu-id="f165b-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="f165b-107">Рекомендуемые исключения IPsec</span><span class="sxs-lookup"><span data-stu-id="f165b-107">Recommended IPsec Exceptions</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f165b-108">Имя правила</span><span class="sxs-lookup"><span data-stu-id="f165b-108">Rule name</span></span></th>
<th><span data-ttu-id="f165b-109">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="f165b-109">Source IP</span></span></th>
<th><span data-ttu-id="f165b-110">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="f165b-110">Destination IP</span></span></th>
<th><span data-ttu-id="f165b-111">Протокол</span><span class="sxs-lookup"><span data-stu-id="f165b-111">Protocol</span></span></th>
<th><span data-ttu-id="f165b-112">Исходный порт</span><span class="sxs-lookup"><span data-stu-id="f165b-112">Source port</span></span></th>
<th><span data-ttu-id="f165b-113">Конечный порт</span><span class="sxs-lookup"><span data-stu-id="f165b-113">Destination port</span></span></th>
<th><span data-ttu-id="f165b-114">Требование для проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="f165b-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f165b-115">Внутренний Входящий сервер пограничного сервера/V</span><span class="sxs-lookup"><span data-stu-id="f165b-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="f165b-116">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-116">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-117">Внутренний сервер пограничного сервера/V</span><span class="sxs-lookup"><span data-stu-id="f165b-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="f165b-118">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="f165b-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="f165b-119">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-119">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-120">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-120">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-121">Без проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="f165b-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f165b-122">Внешний Входящий сервер пограничного сервера/V</span><span class="sxs-lookup"><span data-stu-id="f165b-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="f165b-123">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-123">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-124">Внешний сервер пограничного сервера/V</span><span class="sxs-lookup"><span data-stu-id="f165b-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="f165b-125">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="f165b-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="f165b-126">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-126">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-127">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-127">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-128">Без проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="f165b-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f165b-129">Внутренний исходящий сервер пограничного сервера/V</span><span class="sxs-lookup"><span data-stu-id="f165b-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="f165b-130">Внутренний сервер пограничного сервера/V</span><span class="sxs-lookup"><span data-stu-id="f165b-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="f165b-131">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-131">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-132">UDP &amp; -TCP</span><span class="sxs-lookup"><span data-stu-id="f165b-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="f165b-133">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-133">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-134">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-134">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-135">Без проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="f165b-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f165b-136">Внешний исходящий сервер пограничного сервера/V</span><span class="sxs-lookup"><span data-stu-id="f165b-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="f165b-137">Внешний сервер пограничного сервера/V</span><span class="sxs-lookup"><span data-stu-id="f165b-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="f165b-138">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-138">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-139">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="f165b-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="f165b-140">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-140">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-141">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-141">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-142">Без проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="f165b-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f165b-143">Входящее на сервер обновлений</span><span class="sxs-lookup"><span data-stu-id="f165b-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="f165b-144">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-144">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-145">Посредник</span><span class="sxs-lookup"><span data-stu-id="f165b-145">Mediation</span></span></p>
<p><span data-ttu-id="f165b-146">Сервер (-ы)</span><span class="sxs-lookup"><span data-stu-id="f165b-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="f165b-147">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="f165b-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="f165b-148">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-148">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-149">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-149">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-150">Без проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="f165b-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f165b-151">Исходящие запросы сервера исправлений</span><span class="sxs-lookup"><span data-stu-id="f165b-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="f165b-152">Посредник</span><span class="sxs-lookup"><span data-stu-id="f165b-152">Mediation</span></span></p>
<p><span data-ttu-id="f165b-153">Сервер (-ы)</span><span class="sxs-lookup"><span data-stu-id="f165b-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="f165b-154">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-154">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-155">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="f165b-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="f165b-156">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-156">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-157">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-157">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-158">Без проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="f165b-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f165b-159">Входящее участие в конференциях</span><span class="sxs-lookup"><span data-stu-id="f165b-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="f165b-160">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-160">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-161">Сервер переднего плана с запущенным помощником по конференциям</span><span class="sxs-lookup"><span data-stu-id="f165b-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="f165b-162">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="f165b-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="f165b-163">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-163">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-164">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-164">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-165">Без проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="f165b-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f165b-166">Исходящие участники конференц-связи</span><span class="sxs-lookup"><span data-stu-id="f165b-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="f165b-167">Сервер переднего плана с запущенным помощником по конференциям</span><span class="sxs-lookup"><span data-stu-id="f165b-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="f165b-168">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-168">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-169">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="f165b-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="f165b-170">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-170">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-171">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-171">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-172">Без проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="f165b-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f165b-173">Входящее видеоконференции/V</span><span class="sxs-lookup"><span data-stu-id="f165b-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="f165b-174">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-174">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-175">переднего плана</span><span class="sxs-lookup"><span data-stu-id="f165b-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f165b-176">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="f165b-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="f165b-177">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-177">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-178">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-178">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-179">Без проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="f165b-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f165b-180">Исходящие подключения к конференциям/V</span><span class="sxs-lookup"><span data-stu-id="f165b-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="f165b-181">переднего плана</span><span class="sxs-lookup"><span data-stu-id="f165b-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f165b-182">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-182">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-183">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="f165b-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="f165b-184">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-184">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-185">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-185">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-186">Без проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="f165b-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f165b-187">Входящее на Exchange</span><span class="sxs-lookup"><span data-stu-id="f165b-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="f165b-188">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-188">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-189">Единая система обмена сообщениями Exchange</span><span class="sxs-lookup"><span data-stu-id="f165b-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="f165b-190">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="f165b-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="f165b-191">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-191">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-192">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-192">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-193">Без проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="f165b-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f165b-194">Серверы общего обмена приложениями, входящие</span><span class="sxs-lookup"><span data-stu-id="f165b-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="f165b-195">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-195">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-196">Серверы общего обмена приложениями</span><span class="sxs-lookup"><span data-stu-id="f165b-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="f165b-197">TCP</span><span class="sxs-lookup"><span data-stu-id="f165b-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="f165b-198">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-198">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-199">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-199">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-200">Без проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="f165b-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f165b-201">Исходящие запросы сервера общего приложения</span><span class="sxs-lookup"><span data-stu-id="f165b-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="f165b-202">Серверы общего обмена приложениями</span><span class="sxs-lookup"><span data-stu-id="f165b-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="f165b-203">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-203">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-204">TCP</span><span class="sxs-lookup"><span data-stu-id="f165b-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="f165b-205">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-205">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-206">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-206">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-207">Без проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="f165b-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f165b-208">Исходящие сообщения Exchange</span><span class="sxs-lookup"><span data-stu-id="f165b-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="f165b-209">Единая система обмена сообщениями Exchange</span><span class="sxs-lookup"><span data-stu-id="f165b-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="f165b-210">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-210">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-211">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="f165b-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="f165b-212">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-212">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-213">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-213">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-214">Без проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="f165b-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f165b-215">Клиенты</span><span class="sxs-lookup"><span data-stu-id="f165b-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="f165b-216">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-216">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-217">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-217">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-218">UDP</span><span class="sxs-lookup"><span data-stu-id="f165b-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="f165b-219">Указанный диапазон портов мультимедиа</span><span class="sxs-lookup"><span data-stu-id="f165b-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="f165b-220">Любой</span><span class="sxs-lookup"><span data-stu-id="f165b-220">Any</span></span></p></td>
<td><p><span data-ttu-id="f165b-221">Без проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="f165b-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

