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
ms.openlocfilehash: bd649cea823ce13460de924ffc49741b3ca5c6d6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186792"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="ff64a-102">Исключения IPsec в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff64a-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff64a-103">_**Последнее изменение темы:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="ff64a-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="ff64a-p101">Для корпоративных сетей, где развернут протокол IPSec (см. документ IETF RFC 4301-4309), необходимо отключить IPSec для диапазона портов, используемых для доставки аудио, видео и панорамного видео. Это связано с необходимостью избежать каких-либо задержек при распределении портов мультимедиа из-за согласования IPsec.</span><span class="sxs-lookup"><span data-stu-id="ff64a-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="ff64a-106">В следующей таблице описаны рекомендуемые исключения IPsec.</span><span class="sxs-lookup"><span data-stu-id="ff64a-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="ff64a-107">Рекомендуемые исключения IPsec</span><span class="sxs-lookup"><span data-stu-id="ff64a-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="ff64a-108">Имя правила</span><span class="sxs-lookup"><span data-stu-id="ff64a-108">Rule name</span></span></th>
<th><span data-ttu-id="ff64a-109">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="ff64a-109">Source IP</span></span></th>
<th><span data-ttu-id="ff64a-110">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="ff64a-110">Destination IP</span></span></th>
<th><span data-ttu-id="ff64a-111">Протокол</span><span class="sxs-lookup"><span data-stu-id="ff64a-111">Protocol</span></span></th>
<th><span data-ttu-id="ff64a-112">Исходный порт</span><span class="sxs-lookup"><span data-stu-id="ff64a-112">Source port</span></span></th>
<th><span data-ttu-id="ff64a-113">Конечный порт</span><span class="sxs-lookup"><span data-stu-id="ff64a-113">Destination port</span></span></th>
<th><span data-ttu-id="ff64a-114">Требование проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="ff64a-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff64a-115">Внутренние входящие данные пограничного сервера аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="ff64a-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="ff64a-116">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-116">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-117">Внутренние данные пограничного сервера аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="ff64a-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="ff64a-118">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="ff64a-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="ff64a-119">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-119">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-120">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-120">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-121">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="ff64a-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff64a-122">Внешние входящие данные пограничного сервера аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="ff64a-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="ff64a-123">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-123">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-124">Внешние данные пограничного сервера аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="ff64a-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="ff64a-125">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="ff64a-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="ff64a-126">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-126">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-127">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-127">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-128">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="ff64a-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff64a-129">Внутренние исходящие данные пограничного сервера аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="ff64a-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="ff64a-130">Внутренние данные пограничного сервера аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="ff64a-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="ff64a-131">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-131">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-132">UDP &amp; TCP</span><span class="sxs-lookup"><span data-stu-id="ff64a-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="ff64a-133">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-133">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-134">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-134">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-135">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="ff64a-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff64a-136">Внешние исходящие данные пограничного сервера аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="ff64a-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="ff64a-137">Внешние данные пограничного сервера аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="ff64a-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="ff64a-138">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-138">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-139">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="ff64a-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="ff64a-140">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-140">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-141">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-141">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-142">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="ff64a-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff64a-143">Входящие данные сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="ff64a-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="ff64a-144">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-144">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-145">Сетью</span><span class="sxs-lookup"><span data-stu-id="ff64a-145">Mediation</span></span></p>
<p><span data-ttu-id="ff64a-146">Server (s)</span><span class="sxs-lookup"><span data-stu-id="ff64a-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="ff64a-147">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="ff64a-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="ff64a-148">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-148">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-149">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-149">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-150">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="ff64a-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff64a-151">Исходящие данные сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="ff64a-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="ff64a-152">Сетью</span><span class="sxs-lookup"><span data-stu-id="ff64a-152">Mediation</span></span></p>
<p><span data-ttu-id="ff64a-153">Server (s)</span><span class="sxs-lookup"><span data-stu-id="ff64a-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="ff64a-154">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-154">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-155">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="ff64a-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="ff64a-156">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-156">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-157">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-157">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-158">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="ff64a-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff64a-159">Входящие данные помощника по конференц-связи</span><span class="sxs-lookup"><span data-stu-id="ff64a-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="ff64a-160">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-160">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-161">Интерфейсный сервер с помощником по конференц-связи</span><span class="sxs-lookup"><span data-stu-id="ff64a-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="ff64a-162">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="ff64a-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="ff64a-163">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-163">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-164">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-164">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-165">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="ff64a-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff64a-166">Исходящие данные помощника по конференц-связи</span><span class="sxs-lookup"><span data-stu-id="ff64a-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="ff64a-167">Интерфейсный сервер с помощником по конференц-связи</span><span class="sxs-lookup"><span data-stu-id="ff64a-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="ff64a-168">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-168">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-169">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="ff64a-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="ff64a-170">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-170">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-171">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-171">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-172">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="ff64a-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff64a-173">Входящие данные аудио- и видеоконференций</span><span class="sxs-lookup"><span data-stu-id="ff64a-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="ff64a-174">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-174">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-175">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="ff64a-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ff64a-176">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="ff64a-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="ff64a-177">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-177">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-178">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-178">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-179">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="ff64a-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff64a-180">Исходящие данные аудио- и видеоконференций</span><span class="sxs-lookup"><span data-stu-id="ff64a-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="ff64a-181">Интерфейсные серверы</span><span class="sxs-lookup"><span data-stu-id="ff64a-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ff64a-182">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-182">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-183">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="ff64a-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="ff64a-184">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-184">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-185">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-185">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-186">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="ff64a-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff64a-187">Входящие данные Exchange</span><span class="sxs-lookup"><span data-stu-id="ff64a-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="ff64a-188">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-188">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-189">Единая система обмена сообщениями Exchange</span><span class="sxs-lookup"><span data-stu-id="ff64a-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="ff64a-190">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="ff64a-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="ff64a-191">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-191">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-192">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-192">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-193">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="ff64a-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff64a-194">Входящие данные серверов совместного использования приложений</span><span class="sxs-lookup"><span data-stu-id="ff64a-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="ff64a-195">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-195">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-196">Серверы совместного использования приложений</span><span class="sxs-lookup"><span data-stu-id="ff64a-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="ff64a-197">TCP</span><span class="sxs-lookup"><span data-stu-id="ff64a-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="ff64a-198">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-198">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-199">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-199">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-200">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="ff64a-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff64a-201">Исходящие данные серверов совместного использования приложений</span><span class="sxs-lookup"><span data-stu-id="ff64a-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="ff64a-202">Серверы совместного использования приложений</span><span class="sxs-lookup"><span data-stu-id="ff64a-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="ff64a-203">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-203">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-204">TCP</span><span class="sxs-lookup"><span data-stu-id="ff64a-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="ff64a-205">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-205">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-206">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-206">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-207">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="ff64a-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff64a-208">Исходящие данные Exchange</span><span class="sxs-lookup"><span data-stu-id="ff64a-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="ff64a-209">Единая система обмена сообщениями Exchange</span><span class="sxs-lookup"><span data-stu-id="ff64a-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="ff64a-210">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-210">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-211">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="ff64a-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="ff64a-212">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-212">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-213">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-213">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-214">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="ff64a-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff64a-215">Клиенты</span><span class="sxs-lookup"><span data-stu-id="ff64a-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="ff64a-216">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-216">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-217">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-217">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-218">ПРОТОКОЛА</span><span class="sxs-lookup"><span data-stu-id="ff64a-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="ff64a-219">Указанный диапазон портов мультимедиа</span><span class="sxs-lookup"><span data-stu-id="ff64a-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="ff64a-220">Любые</span><span class="sxs-lookup"><span data-stu-id="ff64a-220">Any</span></span></p></td>
<td><p><span data-ttu-id="ff64a-221">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="ff64a-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

