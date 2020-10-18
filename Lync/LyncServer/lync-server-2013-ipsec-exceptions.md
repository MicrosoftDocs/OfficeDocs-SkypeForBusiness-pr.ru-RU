---
title: Исключения IPsec для Lync Server 2013
description: Исключения IPsec для Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IPsec exceptions
ms:assetid: 241f1eca-6f2f-44de-90b1-2cb659cbe27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425719(v=OCS.15)
ms:contentKeyID: 48183627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b01264171592ec352b778e1aa7eee5861801991
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575005"
---
# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="a37e0-103">Исключения IPsec в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a37e0-103">IPsec exceptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a37e0-104">_**Последнее изменение темы:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="a37e0-104">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="a37e0-p101">Для корпоративных сетей, где развернут протокол IPSec (см. документ IETF RFC 4301-4309), необходимо отключить IPSec для диапазона портов, используемых для доставки аудио, видео и панорамного видео. Это связано с необходимостью избежать каких-либо задержек при распределении портов мультимедиа из-за согласования IPsec.</span><span class="sxs-lookup"><span data-stu-id="a37e0-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="a37e0-107">В следующей таблице описаны рекомендуемые исключения IPsec.</span><span class="sxs-lookup"><span data-stu-id="a37e0-107">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="a37e0-108">Рекомендуемые исключения IPsec</span><span class="sxs-lookup"><span data-stu-id="a37e0-108">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="a37e0-109">Имя правила</span><span class="sxs-lookup"><span data-stu-id="a37e0-109">Rule name</span></span></th>
<th><span data-ttu-id="a37e0-110">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="a37e0-110">Source IP</span></span></th>
<th><span data-ttu-id="a37e0-111">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="a37e0-111">Destination IP</span></span></th>
<th><span data-ttu-id="a37e0-112">Протокол</span><span class="sxs-lookup"><span data-stu-id="a37e0-112">Protocol</span></span></th>
<th><span data-ttu-id="a37e0-113">Исходный порт</span><span class="sxs-lookup"><span data-stu-id="a37e0-113">Source port</span></span></th>
<th><span data-ttu-id="a37e0-114">Конечный порт</span><span class="sxs-lookup"><span data-stu-id="a37e0-114">Destination port</span></span></th>
<th><span data-ttu-id="a37e0-115">Требование проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="a37e0-115">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a37e0-116">Внутренние входящие данные пограничного сервера аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="a37e0-116">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="a37e0-117">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-117">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-118">Внутренние данные пограничного сервера аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="a37e0-118">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="a37e0-119">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="a37e0-119">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="a37e0-120">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-120">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-121">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-121">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-122">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="a37e0-122">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a37e0-123">Внешние входящие данные пограничного сервера аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="a37e0-123">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="a37e0-124">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-124">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-125">Внешние данные пограничного сервера аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="a37e0-125">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="a37e0-126">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="a37e0-126">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="a37e0-127">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-127">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-128">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-128">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-129">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="a37e0-129">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a37e0-130">Внутренние исходящие данные пограничного сервера аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="a37e0-130">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="a37e0-131">Внутренние данные пограничного сервера аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="a37e0-131">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="a37e0-132">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-132">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-133">UDP &amp; TCP</span><span class="sxs-lookup"><span data-stu-id="a37e0-133">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="a37e0-134">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-134">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-135">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-135">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-136">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="a37e0-136">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a37e0-137">Внешние исходящие данные пограничного сервера аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="a37e0-137">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="a37e0-138">Внешние данные пограничного сервера аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="a37e0-138">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="a37e0-139">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-139">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-140">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="a37e0-140">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="a37e0-141">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-141">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-142">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-142">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-143">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="a37e0-143">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a37e0-144">Входящие данные сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="a37e0-144">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="a37e0-145">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-145">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-146">Сетью</span><span class="sxs-lookup"><span data-stu-id="a37e0-146">Mediation</span></span></p>
<p><span data-ttu-id="a37e0-147">Server (s)</span><span class="sxs-lookup"><span data-stu-id="a37e0-147">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="a37e0-148">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="a37e0-148">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="a37e0-149">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-149">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-150">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-150">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-151">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="a37e0-151">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a37e0-152">Исходящие данные сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="a37e0-152">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="a37e0-153">Сетью</span><span class="sxs-lookup"><span data-stu-id="a37e0-153">Mediation</span></span></p>
<p><span data-ttu-id="a37e0-154">Server (s)</span><span class="sxs-lookup"><span data-stu-id="a37e0-154">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="a37e0-155">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-155">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-156">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="a37e0-156">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="a37e0-157">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-157">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-158">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-158">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-159">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="a37e0-159">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a37e0-160">Входящие данные помощника по конференц-связи</span><span class="sxs-lookup"><span data-stu-id="a37e0-160">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="a37e0-161">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-161">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-162">Интерфейсный сервер с помощником по конференц-связи</span><span class="sxs-lookup"><span data-stu-id="a37e0-162">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="a37e0-163">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="a37e0-163">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="a37e0-164">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-164">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-165">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-165">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-166">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="a37e0-166">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a37e0-167">Исходящие данные помощника по конференц-связи</span><span class="sxs-lookup"><span data-stu-id="a37e0-167">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="a37e0-168">Интерфейсный сервер с помощником по конференц-связи</span><span class="sxs-lookup"><span data-stu-id="a37e0-168">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="a37e0-169">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-169">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-170">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="a37e0-170">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="a37e0-171">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-171">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-172">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-172">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-173">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="a37e0-173">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a37e0-174">Входящие данные аудио- и видеоконференций</span><span class="sxs-lookup"><span data-stu-id="a37e0-174">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="a37e0-175">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-175">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-176">Интерфейсные серверы</span><span class="sxs-lookup"><span data-stu-id="a37e0-176">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a37e0-177">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="a37e0-177">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="a37e0-178">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-178">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-179">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-179">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-180">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="a37e0-180">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a37e0-181">Исходящие данные аудио- и видеоконференций</span><span class="sxs-lookup"><span data-stu-id="a37e0-181">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="a37e0-182">Интерфейсные серверы</span><span class="sxs-lookup"><span data-stu-id="a37e0-182">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a37e0-183">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-183">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-184">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="a37e0-184">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="a37e0-185">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-185">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-186">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-186">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-187">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="a37e0-187">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a37e0-188">Входящие данные Exchange</span><span class="sxs-lookup"><span data-stu-id="a37e0-188">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="a37e0-189">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-189">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-190">Единая система обмена сообщениями Exchange</span><span class="sxs-lookup"><span data-stu-id="a37e0-190">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="a37e0-191">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="a37e0-191">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="a37e0-192">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-192">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-193">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-193">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-194">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="a37e0-194">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a37e0-195">Входящие данные серверов совместного использования приложений</span><span class="sxs-lookup"><span data-stu-id="a37e0-195">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="a37e0-196">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-196">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-197">Серверы совместного использования приложений</span><span class="sxs-lookup"><span data-stu-id="a37e0-197">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="a37e0-198">TCP</span><span class="sxs-lookup"><span data-stu-id="a37e0-198">TCP</span></span></p></td>
<td><p><span data-ttu-id="a37e0-199">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-199">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-200">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-200">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-201">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="a37e0-201">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a37e0-202">Исходящие данные серверов совместного использования приложений</span><span class="sxs-lookup"><span data-stu-id="a37e0-202">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="a37e0-203">Серверы совместного использования приложений</span><span class="sxs-lookup"><span data-stu-id="a37e0-203">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="a37e0-204">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-204">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-205">TCP</span><span class="sxs-lookup"><span data-stu-id="a37e0-205">TCP</span></span></p></td>
<td><p><span data-ttu-id="a37e0-206">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-206">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-207">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-207">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-208">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="a37e0-208">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a37e0-209">Исходящие данные Exchange</span><span class="sxs-lookup"><span data-stu-id="a37e0-209">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="a37e0-210">Единая система обмена сообщениями Exchange</span><span class="sxs-lookup"><span data-stu-id="a37e0-210">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="a37e0-211">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-211">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-212">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="a37e0-212">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="a37e0-213">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-213">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-214">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-214">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-215">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="a37e0-215">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a37e0-216">Клиенты</span><span class="sxs-lookup"><span data-stu-id="a37e0-216">Clients</span></span></p></td>
<td><p><span data-ttu-id="a37e0-217">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-217">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-218">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-218">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-219">ПРОТОКОЛА</span><span class="sxs-lookup"><span data-stu-id="a37e0-219">UDP</span></span></p></td>
<td><p><span data-ttu-id="a37e0-220">Указанный диапазон портов мультимедиа</span><span class="sxs-lookup"><span data-stu-id="a37e0-220">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="a37e0-221">Любой</span><span class="sxs-lookup"><span data-stu-id="a37e0-221">Any</span></span></p></td>
<td><p><span data-ttu-id="a37e0-222">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="a37e0-222">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

