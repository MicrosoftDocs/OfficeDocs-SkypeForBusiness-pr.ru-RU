---
title: Исключения IPsec для Lync Server 2013
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
ms.openlocfilehash: 4ee06e4b7f3cabc606a612cd0f332aed47b46823
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514156"
---
# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="abe34-102">Исключения IPsec в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abe34-102">IPsec exceptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abe34-103">_**Последнее изменение темы:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="abe34-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="abe34-p101">Для корпоративных сетей, где развернут протокол IPSec (см. документ IETF RFC 4301-4309), необходимо отключить IPSec для диапазона портов, используемых для доставки аудио, видео и панорамного видео. Это связано с необходимостью избежать каких-либо задержек при распределении портов мультимедиа из-за согласования IPsec.</span><span class="sxs-lookup"><span data-stu-id="abe34-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="abe34-106">В следующей таблице описаны рекомендуемые исключения IPsec.</span><span class="sxs-lookup"><span data-stu-id="abe34-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="abe34-107">Рекомендуемые исключения IPsec</span><span class="sxs-lookup"><span data-stu-id="abe34-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="abe34-108">Имя правила</span><span class="sxs-lookup"><span data-stu-id="abe34-108">Rule name</span></span></th>
<th><span data-ttu-id="abe34-109">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="abe34-109">Source IP</span></span></th>
<th><span data-ttu-id="abe34-110">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="abe34-110">Destination IP</span></span></th>
<th><span data-ttu-id="abe34-111">Протокол</span><span class="sxs-lookup"><span data-stu-id="abe34-111">Protocol</span></span></th>
<th><span data-ttu-id="abe34-112">Исходный порт</span><span class="sxs-lookup"><span data-stu-id="abe34-112">Source port</span></span></th>
<th><span data-ttu-id="abe34-113">Конечный порт</span><span class="sxs-lookup"><span data-stu-id="abe34-113">Destination port</span></span></th>
<th><span data-ttu-id="abe34-114">Требование проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="abe34-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="abe34-115">Внутренние входящие данные пограничного сервера аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="abe34-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="abe34-116">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-116">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-117">Внутренние данные пограничного сервера аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="abe34-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="abe34-118">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="abe34-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="abe34-119">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-119">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-120">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-120">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-121">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="abe34-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abe34-122">Внешние входящие данные пограничного сервера аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="abe34-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="abe34-123">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-123">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-124">Внешние данные пограничного сервера аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="abe34-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="abe34-125">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="abe34-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="abe34-126">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-126">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-127">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-127">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-128">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="abe34-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abe34-129">Внутренние исходящие данные пограничного сервера аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="abe34-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="abe34-130">Внутренние данные пограничного сервера аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="abe34-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="abe34-131">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-131">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-132">UDP &amp; TCP</span><span class="sxs-lookup"><span data-stu-id="abe34-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="abe34-133">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-133">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-134">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-134">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-135">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="abe34-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abe34-136">Внешние исходящие данные пограничного сервера аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="abe34-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="abe34-137">Внешние данные пограничного сервера аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="abe34-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="abe34-138">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-138">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-139">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="abe34-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="abe34-140">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-140">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-141">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-141">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-142">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="abe34-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abe34-143">Входящие данные сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="abe34-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="abe34-144">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-144">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-145">Сетью</span><span class="sxs-lookup"><span data-stu-id="abe34-145">Mediation</span></span></p>
<p><span data-ttu-id="abe34-146">Server (s)</span><span class="sxs-lookup"><span data-stu-id="abe34-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="abe34-147">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="abe34-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="abe34-148">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-148">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-149">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-149">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-150">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="abe34-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abe34-151">Исходящие данные сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="abe34-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="abe34-152">Сетью</span><span class="sxs-lookup"><span data-stu-id="abe34-152">Mediation</span></span></p>
<p><span data-ttu-id="abe34-153">Server (s)</span><span class="sxs-lookup"><span data-stu-id="abe34-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="abe34-154">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-154">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-155">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="abe34-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="abe34-156">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-156">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-157">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-157">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-158">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="abe34-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abe34-159">Входящие данные помощника по конференц-связи</span><span class="sxs-lookup"><span data-stu-id="abe34-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="abe34-160">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-160">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-161">Интерфейсный сервер с помощником по конференц-связи</span><span class="sxs-lookup"><span data-stu-id="abe34-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="abe34-162">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="abe34-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="abe34-163">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-163">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-164">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-164">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-165">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="abe34-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abe34-166">Исходящие данные помощника по конференц-связи</span><span class="sxs-lookup"><span data-stu-id="abe34-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="abe34-167">Интерфейсный сервер с помощником по конференц-связи</span><span class="sxs-lookup"><span data-stu-id="abe34-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="abe34-168">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-168">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-169">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="abe34-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="abe34-170">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-170">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-171">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-171">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-172">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="abe34-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abe34-173">Входящие данные аудио- и видеоконференций</span><span class="sxs-lookup"><span data-stu-id="abe34-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="abe34-174">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-174">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-175">Интерфейсные серверы</span><span class="sxs-lookup"><span data-stu-id="abe34-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="abe34-176">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="abe34-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="abe34-177">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-177">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-178">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-178">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-179">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="abe34-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abe34-180">Исходящие данные аудио- и видеоконференций</span><span class="sxs-lookup"><span data-stu-id="abe34-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="abe34-181">Интерфейсные серверы</span><span class="sxs-lookup"><span data-stu-id="abe34-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="abe34-182">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-182">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-183">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="abe34-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="abe34-184">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-184">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-185">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-185">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-186">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="abe34-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abe34-187">Входящие данные Exchange</span><span class="sxs-lookup"><span data-stu-id="abe34-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="abe34-188">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-188">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-189">Единая система обмена сообщениями Exchange</span><span class="sxs-lookup"><span data-stu-id="abe34-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="abe34-190">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="abe34-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="abe34-191">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-191">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-192">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-192">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-193">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="abe34-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abe34-194">Входящие данные серверов совместного использования приложений</span><span class="sxs-lookup"><span data-stu-id="abe34-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="abe34-195">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-195">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-196">Серверы совместного использования приложений</span><span class="sxs-lookup"><span data-stu-id="abe34-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="abe34-197">TCP</span><span class="sxs-lookup"><span data-stu-id="abe34-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="abe34-198">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-198">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-199">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-199">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-200">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="abe34-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abe34-201">Исходящие данные серверов совместного использования приложений</span><span class="sxs-lookup"><span data-stu-id="abe34-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="abe34-202">Серверы совместного использования приложений</span><span class="sxs-lookup"><span data-stu-id="abe34-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="abe34-203">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-203">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-204">TCP</span><span class="sxs-lookup"><span data-stu-id="abe34-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="abe34-205">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-205">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-206">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-206">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-207">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="abe34-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abe34-208">Исходящие данные Exchange</span><span class="sxs-lookup"><span data-stu-id="abe34-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="abe34-209">Единая система обмена сообщениями Exchange</span><span class="sxs-lookup"><span data-stu-id="abe34-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="abe34-210">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-210">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-211">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="abe34-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="abe34-212">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-212">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-213">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-213">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-214">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="abe34-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abe34-215">Клиенты</span><span class="sxs-lookup"><span data-stu-id="abe34-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="abe34-216">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-216">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-217">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-217">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-218">ПРОТОКОЛА</span><span class="sxs-lookup"><span data-stu-id="abe34-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="abe34-219">Указанный диапазон портов мультимедиа</span><span class="sxs-lookup"><span data-stu-id="abe34-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="abe34-220">Любой</span><span class="sxs-lookup"><span data-stu-id="abe34-220">Any</span></span></p></td>
<td><p><span data-ttu-id="abe34-221">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="abe34-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

