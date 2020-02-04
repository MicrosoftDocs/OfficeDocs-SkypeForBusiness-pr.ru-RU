---
title: Исключения для Lync Server 2013 IPsec
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
ms.openlocfilehash: 37d5becaab996d6fe4889086d3a68a45ffc1f6d7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733459"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="0e863-102">Исключения IPsec в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e863-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e863-103">_**Тема последнего изменения:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="0e863-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="0e863-104">Для корпоративных сетей, где развернута безопасность протокола IP (IPsec) (ознакомьтесь со статьей IETF RFC 4301-4309), необходимо отключить IPsec для диапазона портов, используемых для доставки звуковых, видеофайлов и панорамных видео.</span><span class="sxs-lookup"><span data-stu-id="0e863-104">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video.</span></span> <span data-ttu-id="0e863-105">Это связано с необходимостью избежать каких-либо задержек при распределении портов мультимедиа из-за согласования IPsec.</span><span class="sxs-lookup"><span data-stu-id="0e863-105">The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="0e863-106">В следующей таблице описаны рекомендуемые исключения IPsec.</span><span class="sxs-lookup"><span data-stu-id="0e863-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="0e863-107">Рекомендуемые исключения IPsec</span><span class="sxs-lookup"><span data-stu-id="0e863-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="0e863-108">Имя правила</span><span class="sxs-lookup"><span data-stu-id="0e863-108">Rule name</span></span></th>
<th><span data-ttu-id="0e863-109">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="0e863-109">Source IP</span></span></th>
<th><span data-ttu-id="0e863-110">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="0e863-110">Destination IP</span></span></th>
<th><span data-ttu-id="0e863-111">Протокол</span><span class="sxs-lookup"><span data-stu-id="0e863-111">Protocol</span></span></th>
<th><span data-ttu-id="0e863-112">Исходный порт</span><span class="sxs-lookup"><span data-stu-id="0e863-112">Source port</span></span></th>
<th><span data-ttu-id="0e863-113">Конечный порт</span><span class="sxs-lookup"><span data-stu-id="0e863-113">Destination port</span></span></th>
<th><span data-ttu-id="0e863-114">Требование проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="0e863-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e863-115">Внутренние входящие данные пограничного сервера аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="0e863-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="0e863-116">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-116">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-117">Внутренние данные пограничного сервера аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="0e863-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="0e863-118">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="0e863-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0e863-119">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-119">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-120">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-120">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-121">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="0e863-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e863-122">Внешние входящие данные пограничного сервера аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="0e863-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="0e863-123">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-123">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-124">Внешние данные пограничного сервера аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="0e863-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="0e863-125">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="0e863-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0e863-126">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-126">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-127">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-127">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-128">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="0e863-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e863-129">Внутренние исходящие данные пограничного сервера аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="0e863-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="0e863-130">Внутренние данные пограничного сервера аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="0e863-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="0e863-131">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-131">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-132">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="0e863-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="0e863-133">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-133">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-134">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-134">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-135">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="0e863-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e863-136">Внешние исходящие данные пограничного сервера аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="0e863-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="0e863-137">Внешние данные пограничного сервера аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="0e863-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="0e863-138">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-138">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-139">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="0e863-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0e863-140">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-140">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-141">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-141">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-142">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="0e863-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e863-143">Входящие данные сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="0e863-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="0e863-144">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-144">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-145">Серверы-</span><span class="sxs-lookup"><span data-stu-id="0e863-145">Mediation</span></span></p>
<p><span data-ttu-id="0e863-146">посредники</span><span class="sxs-lookup"><span data-stu-id="0e863-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="0e863-147">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="0e863-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0e863-148">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-148">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-149">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-149">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-150">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="0e863-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e863-151">Исходящие данные сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="0e863-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="0e863-152">Серверы-</span><span class="sxs-lookup"><span data-stu-id="0e863-152">Mediation</span></span></p>
<p><span data-ttu-id="0e863-153">посредники</span><span class="sxs-lookup"><span data-stu-id="0e863-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="0e863-154">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-154">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-155">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="0e863-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0e863-156">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-156">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-157">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-157">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-158">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="0e863-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e863-159">Входящие данные помощника по конференц-связи</span><span class="sxs-lookup"><span data-stu-id="0e863-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="0e863-160">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-160">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-161">Сервер переднего плана с помощником по конференц-связи</span><span class="sxs-lookup"><span data-stu-id="0e863-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="0e863-162">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="0e863-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0e863-163">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-163">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-164">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-164">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-165">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="0e863-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e863-166">Исходящие данные помощника по конференц-связи</span><span class="sxs-lookup"><span data-stu-id="0e863-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="0e863-167">Сервер переднего плана с помощником по конференц-связи</span><span class="sxs-lookup"><span data-stu-id="0e863-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="0e863-168">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-168">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-169">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="0e863-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0e863-170">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-170">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-171">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-171">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-172">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="0e863-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e863-173">Входящие данные аудио- и видеоконференций</span><span class="sxs-lookup"><span data-stu-id="0e863-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="0e863-174">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-174">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-175">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="0e863-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="0e863-176">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="0e863-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0e863-177">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-177">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-178">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-178">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-179">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="0e863-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e863-180">Исходящие данные аудио- и видеоконференций</span><span class="sxs-lookup"><span data-stu-id="0e863-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="0e863-181">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="0e863-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="0e863-182">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-182">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-183">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="0e863-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0e863-184">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-184">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-185">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-185">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-186">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="0e863-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e863-187">Входящие данные Exchange</span><span class="sxs-lookup"><span data-stu-id="0e863-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="0e863-188">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-188">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-189">Единая система обмена сообщениями Exchange</span><span class="sxs-lookup"><span data-stu-id="0e863-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="0e863-190">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="0e863-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0e863-191">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-191">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-192">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-192">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-193">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="0e863-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e863-194">Входящие данные серверов совместного использования приложений</span><span class="sxs-lookup"><span data-stu-id="0e863-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="0e863-195">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-195">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-196">Серверы совместного использования приложений</span><span class="sxs-lookup"><span data-stu-id="0e863-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="0e863-197">TCP</span><span class="sxs-lookup"><span data-stu-id="0e863-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="0e863-198">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-198">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-199">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-199">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-200">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="0e863-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e863-201">Исходящие данные серверов совместного использования приложений</span><span class="sxs-lookup"><span data-stu-id="0e863-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="0e863-202">Серверы совместного использования приложений</span><span class="sxs-lookup"><span data-stu-id="0e863-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="0e863-203">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-203">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-204">TCP</span><span class="sxs-lookup"><span data-stu-id="0e863-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="0e863-205">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-205">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-206">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-206">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-207">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="0e863-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e863-208">Исходящие данные Exchange</span><span class="sxs-lookup"><span data-stu-id="0e863-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="0e863-209">Единая система обмена сообщениями Exchange</span><span class="sxs-lookup"><span data-stu-id="0e863-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="0e863-210">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-210">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-211">UDP и TCP</span><span class="sxs-lookup"><span data-stu-id="0e863-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0e863-212">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-212">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-213">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-213">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-214">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="0e863-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e863-215">Клиенты</span><span class="sxs-lookup"><span data-stu-id="0e863-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="0e863-216">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-216">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-217">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-217">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-218">UDP</span><span class="sxs-lookup"><span data-stu-id="0e863-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="0e863-219">Указанный диапазон портов мультимедиа</span><span class="sxs-lookup"><span data-stu-id="0e863-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="0e863-220">Любой</span><span class="sxs-lookup"><span data-stu-id="0e863-220">Any</span></span></p></td>
<td><p><span data-ttu-id="0e863-221">Не выполнять проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="0e863-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

