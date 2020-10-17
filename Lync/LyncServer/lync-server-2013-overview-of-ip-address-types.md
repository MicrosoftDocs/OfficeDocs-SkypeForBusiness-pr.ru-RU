---
title: 'Lync Server 2013: Обзор типов IP-адресов'
description: 'Lync Server 2013: Обзор типов IP-адресов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of IP address types for Lync Server
ms:assetid: ee9a695f-5cf5-441e-94fb-6adeca50e8d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205363(v=OCS.15)
ms:contentKeyID: 48185759
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81492b2e006a6f44f6deb78e6a0560f6e319992f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559225"
---
# <a name="overview-of-ip-address-types-for-lync-server-2013"></a><span data-ttu-id="78563-103">Обзор типов IP-адресов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78563-103">Overview of IP address types for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78563-104">_**Последнее изменение темы:** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="78563-104">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="78563-105">При настройке IP-адресов в Lync Server 2013 у вас есть три варианта.</span><span class="sxs-lookup"><span data-stu-id="78563-105">You have three options when configuring IP addresses in Lync Server 2013.</span></span> <span data-ttu-id="78563-106">Вы можете настроить Lync Server 2013 для поддержки только протокола IP версии 4 (IPv4), только протокола IP версии 6 (IPv6) или их комбинации (это называется *двойным стеком*).</span><span class="sxs-lookup"><span data-stu-id="78563-106">You can configure Lync Server 2013 to support only IP version 4 (IPv4), only IP version 6 (IPv6), or a combination of both (known as a *dual stack*).</span></span> <span data-ttu-id="78563-107">Для каждого типа конфигурации существует некоторое количество проблем, которые необходимо принимать во внимание.</span><span class="sxs-lookup"><span data-stu-id="78563-107">There are several issues to consider with each type of configuration:</span></span>

  - <span data-ttu-id="78563-108">**Только IPv4**     IPv6 был создан, так как в мире не хватает IPv4-адресов.</span><span class="sxs-lookup"><span data-stu-id="78563-108">**IPv4 only**   IPv6 was created because the world is running out of IPv4 addresses.</span></span> <span data-ttu-id="78563-109">В конечном итоге IPv6 будет полностью поддерживаться во всем мире, но в настоящее время многие компании и устройства, с которыми, возможно, приходится иметь дело вашей организации, пока не поддерживают IPv6, и не будут поддерживать еще какое-то время.</span><span class="sxs-lookup"><span data-stu-id="78563-109">Ultimately, IPv6 will be fully supported worldwide, but at this time, many companies and devices that your enterprise might need to communicate with do not yet support IPv6, and may not for some time.</span></span> <span data-ttu-id="78563-110">Конфигурация только с IPv4 поможет гарантировать, что реализация Lync Server сможет общаться с большинством существующих устройств.</span><span class="sxs-lookup"><span data-stu-id="78563-110">An IPv4-only configuration will help to ensure that your Lync Server implementation can communicate with most existing devices.</span></span>

  - <span data-ttu-id="78563-111">**Только IPv6**     В настоящее время полная реализация IPv6 будет исключать связь с множеством существующих устройств.</span><span class="sxs-lookup"><span data-stu-id="78563-111">**IPv6 only**   Conversely, a full IPv6 implementation, at this time, will exclude communication with many existing devices.</span></span>

  - <span data-ttu-id="78563-112">**Двойной стек**     Dual Stack — это сеть, в которой включены IPv4-и IPv6-адреса.</span><span class="sxs-lookup"><span data-stu-id="78563-112">**Dual Stack**   Dual stack is a network where both IPv4 and IPv6 addresses are enabled.</span></span> <span data-ttu-id="78563-113">Эта конфигурация поддерживается в Lync Server 2013, так как в большинстве случаев переход с полной (IPv4) на полный IPv6 займет несколько лет.</span><span class="sxs-lookup"><span data-stu-id="78563-113">This configuration is supported in Lync Server 2013 because in most cases the transition from full-IPv4 to full-IPv6 will take several years.</span></span>

<span data-ttu-id="78563-114">В следующих разделах описывается совместимость между этими тремя конфигурациями для различных функций Lync Server.</span><span class="sxs-lookup"><span data-stu-id="78563-114">The following sections outline the compatibility among these three configurations for various Lync Server features.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="78563-p104">Клиентская или серверная конфигурация только с IPv6 поддерживается только для целей проверки или обучения. Конфигурация только с IPv6 не поддерживается в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="78563-p104">Client or server configuration with IPv6 only is supported only for lab or validation purposes. IPv6 only configuration is not supported in the production deployment.</span></span>



</div>

<div>

## <a name="client-registration"></a><span data-ttu-id="78563-117">Регистрация клиентов</span><span class="sxs-lookup"><span data-stu-id="78563-117">Client Registration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="78563-118">Сеть конечной точки клиента</span><span class="sxs-lookup"><span data-stu-id="78563-118">Client endpoint network</span></span></th>
<th><span data-ttu-id="78563-119">Сеть сервера</span><span class="sxs-lookup"><span data-stu-id="78563-119">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="78563-120">IPv4</span><span class="sxs-lookup"><span data-stu-id="78563-120">IPv4</span></span></p></td>
<td><p><span data-ttu-id="78563-121">IPv4</span><span class="sxs-lookup"><span data-stu-id="78563-121">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78563-122">IPv4</span><span class="sxs-lookup"><span data-stu-id="78563-122">IPv4</span></span></p></td>
<td><p><span data-ttu-id="78563-123">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="78563-123">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78563-124">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="78563-124">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="78563-125">IPv4</span><span class="sxs-lookup"><span data-stu-id="78563-125">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78563-126">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="78563-126">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="78563-127">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="78563-127">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78563-128">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="78563-128">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="78563-129">IPv6</span><span class="sxs-lookup"><span data-stu-id="78563-129">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78563-130">IPv6</span><span class="sxs-lookup"><span data-stu-id="78563-130">IPv6</span></span></p></td>
<td><p><span data-ttu-id="78563-131">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="78563-131">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78563-132">IPv6</span><span class="sxs-lookup"><span data-stu-id="78563-132">IPv6</span></span></p></td>
<td><p><span data-ttu-id="78563-133">IPv6</span><span class="sxs-lookup"><span data-stu-id="78563-133">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="peer-to-peer-client"></a><span data-ttu-id="78563-134">Одноранговый клиент</span><span class="sxs-lookup"><span data-stu-id="78563-134">Peer-to-Peer Client</span></span>

<span data-ttu-id="78563-p105">Одноранговые коммуникации включают звуковую связь, видеосвязь, общий доступ к приложениям и передачу файлов. После успешной регистрации обоих клиентов поддерживаются следующие комбинации.</span><span class="sxs-lookup"><span data-stu-id="78563-p105">Peer-to-peer communications include audio, audio/video, application sharing, and file transfer. After both clients have successfully registered, the following combinations are supported.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="78563-137">Конечная точка клиента 1</span><span class="sxs-lookup"><span data-stu-id="78563-137">Client endpoint 1</span></span></th>
<th><span data-ttu-id="78563-138">Конечная точка клиента 2</span><span class="sxs-lookup"><span data-stu-id="78563-138">Client endpoint 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="78563-139">IPv4</span><span class="sxs-lookup"><span data-stu-id="78563-139">IPv4</span></span></p></td>
<td><p><span data-ttu-id="78563-140">IPv4</span><span class="sxs-lookup"><span data-stu-id="78563-140">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78563-141">IPv4</span><span class="sxs-lookup"><span data-stu-id="78563-141">IPv4</span></span></p></td>
<td><p><span data-ttu-id="78563-142">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="78563-142">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78563-143">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="78563-143">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="78563-144">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="78563-144">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78563-145">IPv6</span><span class="sxs-lookup"><span data-stu-id="78563-145">IPv6</span></span></p></td>
<td><p><span data-ttu-id="78563-146">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="78563-146">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78563-147">IPv6</span><span class="sxs-lookup"><span data-stu-id="78563-147">IPv6</span></span></p></td>
<td><p><span data-ttu-id="78563-148">IPv6</span><span class="sxs-lookup"><span data-stu-id="78563-148">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="conferencing"></a><span data-ttu-id="78563-149">Конференции</span><span class="sxs-lookup"><span data-stu-id="78563-149">Conferencing</span></span>

<span data-ttu-id="78563-150">Конференц-связь включает видеосвязь, общий доступ к приложениям и совместную работу с данными (работу на доске и общий доступ к файлам).</span><span class="sxs-lookup"><span data-stu-id="78563-150">Conferencing includes audio/video, application sharing, and data collaboration (whiteboarding and file sharing).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="78563-151">Сеть конечной точки клиента</span><span class="sxs-lookup"><span data-stu-id="78563-151">Client endpoint network</span></span></th>
<th><span data-ttu-id="78563-152">Сеть сервера</span><span class="sxs-lookup"><span data-stu-id="78563-152">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="78563-153">IPv4</span><span class="sxs-lookup"><span data-stu-id="78563-153">IPv4</span></span></p></td>
<td><p><span data-ttu-id="78563-154">IPv4</span><span class="sxs-lookup"><span data-stu-id="78563-154">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78563-155">IPv4</span><span class="sxs-lookup"><span data-stu-id="78563-155">IPv4</span></span></p></td>
<td><p><span data-ttu-id="78563-156">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="78563-156">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78563-157">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="78563-157">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="78563-158">IPv4</span><span class="sxs-lookup"><span data-stu-id="78563-158">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78563-159">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="78563-159">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="78563-160">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="78563-160">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78563-161">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="78563-161">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="78563-162">IPv6</span><span class="sxs-lookup"><span data-stu-id="78563-162">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78563-163">IPv6</span><span class="sxs-lookup"><span data-stu-id="78563-163">IPv6</span></span></p></td>
<td><p><span data-ttu-id="78563-164">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="78563-164">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78563-165">IPv6</span><span class="sxs-lookup"><span data-stu-id="78563-165">IPv6</span></span></p></td>
<td><p><span data-ttu-id="78563-166">IPv6</span><span class="sxs-lookup"><span data-stu-id="78563-166">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="mediation-serverpstn"></a><span data-ttu-id="78563-167">Сервер-посредник/ТСОП</span><span class="sxs-lookup"><span data-stu-id="78563-167">Mediation Server/PSTN</span></span>

<span data-ttu-id="78563-168">Lync Server 2013 не поддерживает обход сервера-посредника для вызовов телефонной сети общего пользования (PSTN), если трафик проходит через интерфейс IPv6.</span><span class="sxs-lookup"><span data-stu-id="78563-168">Lync Server 2013 does not support media bypass for public switched telephone network (PSTN) calls if the traffic is through an IPv6 interface.</span></span> <span data-ttu-id="78563-169">Если требуется обход сервера-посредника, то рекомендуется настроить шлюз ТСОП для IPv4.</span><span class="sxs-lookup"><span data-stu-id="78563-169">If media bypass is required, we recommend that the PSTN gateway is configured to IPv4.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="78563-170">Основной интерфейс\*</span><span class="sxs-lookup"><span data-stu-id="78563-170">Primary interface\*</span></span></th>
<th><span data-ttu-id="78563-171">Интерфейс ТСОП (на сервере-посреднике)</span><span class="sxs-lookup"><span data-stu-id="78563-171">PSTN interface (on Mediation Server)</span></span></th>
<th><span data-ttu-id="78563-172">Настройка шлюза ТСОП</span><span class="sxs-lookup"><span data-stu-id="78563-172">PSTN gateway setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="78563-173">IPv4</span><span class="sxs-lookup"><span data-stu-id="78563-173">IPv4</span></span></p></td>
<td><p><span data-ttu-id="78563-174">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="78563-174">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="78563-175">IPv4</span><span class="sxs-lookup"><span data-stu-id="78563-175">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78563-176">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="78563-176">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="78563-177">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="78563-177">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="78563-178">IPv4</span><span class="sxs-lookup"><span data-stu-id="78563-178">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78563-179">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="78563-179">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="78563-180">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="78563-180">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="78563-181">IPv6</span><span class="sxs-lookup"><span data-stu-id="78563-181">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="78563-182">\* Основной интерфейс — это интерфейс, который обменивается данными с компонентами Lync Server.</span><span class="sxs-lookup"><span data-stu-id="78563-182">\* The primary interface is the interface that communicates with the Lync Server components.</span></span>

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a><span data-ttu-id="78563-183">Одноранговые коммуникации с удаленными пользователями</span><span class="sxs-lookup"><span data-stu-id="78563-183">Remote User Peer-to-Peer Communications</span></span>

<span data-ttu-id="78563-184">Одноранговые коммуникации с удаленными пользователями включают обмен мгновенными сообщениями, видеосвязь, общий доступ к приложениям и передачу файлов.</span><span class="sxs-lookup"><span data-stu-id="78563-184">Peer-to-peer communications with remote users include instant messaging, audio/video, application sharing, and file transfer.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="78563-185">Сеть удаленного пользователя</span><span class="sxs-lookup"><span data-stu-id="78563-185">Remote user network</span></span></th>
<th><span data-ttu-id="78563-186">Пограничный сервер (внешний периметр)</span><span class="sxs-lookup"><span data-stu-id="78563-186">Edge server (External edge)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="78563-187">IPv4</span><span class="sxs-lookup"><span data-stu-id="78563-187">IPv4</span></span></p></td>
<td><p><span data-ttu-id="78563-188">IPv4</span><span class="sxs-lookup"><span data-stu-id="78563-188">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78563-189">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="78563-189">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="78563-190">IPv4</span><span class="sxs-lookup"><span data-stu-id="78563-190">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78563-191">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="78563-191">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="78563-192">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="78563-192">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78563-193">IPv6</span><span class="sxs-lookup"><span data-stu-id="78563-193">IPv6</span></span></p></td>
<td><p><span data-ttu-id="78563-194">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="78563-194">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78563-195">IPv6</span><span class="sxs-lookup"><span data-stu-id="78563-195">IPv6</span></span></p></td>
<td><p><span data-ttu-id="78563-196">IPv6</span><span class="sxs-lookup"><span data-stu-id="78563-196">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a><span data-ttu-id="78563-197">Конфигурация интерфейсного пула и пограничного пула</span><span class="sxs-lookup"><span data-stu-id="78563-197">Front End Pool and Edge Pool Configuration</span></span>

<span data-ttu-id="78563-198">В следующей таблице показана матрица поддержки между пулом серверов переднего плана и внутренним пулом пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="78563-198">The following table shows the support matrix between the Front End Server pool and the internal Edge Server pool.</span></span>

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a><span data-ttu-id="78563-199">Матрица интерфейсного пула и пограничного пула (внутренний периметр)</span><span class="sxs-lookup"><span data-stu-id="78563-199">Front End Pool and Edge Pool (Internal Edge) Matrix</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="78563-200"><strong>Пограничный пул: IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="78563-200"><strong>Edge Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="78563-201"><strong>Пограничный пул: двойной стек</strong></span><span class="sxs-lookup"><span data-stu-id="78563-201"><strong>Edge Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="78563-202"><strong>Пограничный пул: IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="78563-202"><strong>Edge Pool: IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78563-203"><strong>Интерфейсный пул: IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="78563-203"><strong>Front End Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="78563-204">Да</span><span class="sxs-lookup"><span data-stu-id="78563-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="78563-205">Да</span><span class="sxs-lookup"><span data-stu-id="78563-205">Yes</span></span></p></td>
<td><p><span data-ttu-id="78563-206">Нет</span><span class="sxs-lookup"><span data-stu-id="78563-206">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78563-207"><strong>Интерфейсный пул: двойной стек</strong></span><span class="sxs-lookup"><span data-stu-id="78563-207"><strong>Front End Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="78563-208">Да</span><span class="sxs-lookup"><span data-stu-id="78563-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="78563-209">Да</span><span class="sxs-lookup"><span data-stu-id="78563-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="78563-210">Нет</span><span class="sxs-lookup"><span data-stu-id="78563-210">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78563-211"><strong>Интерфейсный пул: IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="78563-211"><strong>Front End Pool: IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="78563-212">Нет</span><span class="sxs-lookup"><span data-stu-id="78563-212">No</span></span></p></td>
<td><p><span data-ttu-id="78563-213">Нет</span><span class="sxs-lookup"><span data-stu-id="78563-213">No</span></span></p></td>
<td><p><span data-ttu-id="78563-214">Да\*</span><span class="sxs-lookup"><span data-stu-id="78563-214">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="78563-215">\* Используйте это сочетание только в лабораторной среде.</span><span class="sxs-lookup"><span data-stu-id="78563-215">\* Use this combination only in a lab environment.</span></span>

<span data-ttu-id="78563-216">В следующей таблице представлена матрица поддерживаемых комбинаций интерфейсов внешнего и внутреннего периметра.</span><span class="sxs-lookup"><span data-stu-id="78563-216">The following table is a matrix of the supported combinations of internal and external edge interfaces.</span></span>

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a><span data-ttu-id="78563-217">Матрица пограничного пула внутреннего периметра и пограничного пула внешнего периметра</span><span class="sxs-lookup"><span data-stu-id="78563-217">Edge Pool (Internal Edge) and Edge pool (External Edge) Matrix</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="78563-218"><strong>Пограничный пул (внешний периметр): IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="78563-218"><strong>Edge Pool (External Edge) : IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="78563-219"><strong>Пограничный пул (внешний периметр): двойной стек</strong></span><span class="sxs-lookup"><span data-stu-id="78563-219"><strong>Edge Pool (External Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="78563-220"><strong>Пограничный пул (внешний периметр): IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="78563-220"><strong>Edge Pool (External Edge): IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78563-221"><strong>Пограничный пул (внутренний периметр): IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="78563-221"><strong>Edge Pool (Internal Edge): IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="78563-222">Да</span><span class="sxs-lookup"><span data-stu-id="78563-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="78563-223">Да</span><span class="sxs-lookup"><span data-stu-id="78563-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="78563-224">Нет</span><span class="sxs-lookup"><span data-stu-id="78563-224">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78563-225"><strong>Пограничный пул (внутренний периметр): внутренний стек</strong></span><span class="sxs-lookup"><span data-stu-id="78563-225"><strong>Edge Pool (Internal Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="78563-226">Нет</span><span class="sxs-lookup"><span data-stu-id="78563-226">No</span></span></p></td>
<td><p><span data-ttu-id="78563-227">Да</span><span class="sxs-lookup"><span data-stu-id="78563-227">Yes</span></span></p></td>
<td><p><span data-ttu-id="78563-228">Нет</span><span class="sxs-lookup"><span data-stu-id="78563-228">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78563-229"><strong>Пограничный пул (внутренний периметр): IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="78563-229"><strong>Edge Pool (Internal Edge): IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="78563-230">Нет</span><span class="sxs-lookup"><span data-stu-id="78563-230">No</span></span></p></td>
<td><p><span data-ttu-id="78563-231">Нет</span><span class="sxs-lookup"><span data-stu-id="78563-231">No</span></span></p></td>
<td><p><span data-ttu-id="78563-232">Да\*</span><span class="sxs-lookup"><span data-stu-id="78563-232">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="78563-233">\* Используйте это сочетание только в лабораторной среде.</span><span class="sxs-lookup"><span data-stu-id="78563-233">\* Use this combination only in a lab environment.</span></span>

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a><span data-ttu-id="78563-234">Улучшенная поддержка корпоративной голосовой связи для IPv6</span><span class="sxs-lookup"><span data-stu-id="78563-234">Advanced Enterprise Voice Support for IPv6</span></span>

<span data-ttu-id="78563-235">Развертывания, включающие контроль допуска звонков (CAC), Enhanced 9-1-1 (E9-1-1) или обход сервера-посредника, должны настраиваться как реализация только IPv4 или реализация двойного стека.</span><span class="sxs-lookup"><span data-stu-id="78563-235">Deployments that include call admission control (CAC), Enhanced 9-1-1 (E9-1-1), or media bypass must be configured as IPv4 only or as a dual-stacked implementation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="78563-236">В развертывании с двойным стеком даже в том случае, если клиент Lync подключается к серверу Lync Server с помощью IPv6, Lync предоставит лучшие усилия для сопоставления соответствующего IPv4-адреса для поддержки E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="78563-236">In a dual-stacked deployment, even if a Lync client connects to a Lync Server by using IPv6, Lync will make a best effort to map an appropriate IPv4 address to support E9-1-1.</span></span>



</div>

<span data-ttu-id="78563-237">Служба сведений о местоположении с IPv6-адресами не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="78563-237">Location Information service with IPv6 addresses is not supported.</span></span>

<span data-ttu-id="78563-p107">Единая система обмена сообщениями Exchange не поддерживает IPv6. Для единой системы обмена сообщениями Exchange следует убедиться, что DNS-разрешение не возвращает IPv6-адрес. Использование IPv6 может привести к сбою при отправке вызовов в голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="78563-p107">Exchange Unified Messaging (UM) does not support IPv6. For Exchange UM, be sure that DNS resolution does not return an IPv6 address. Using IPv6 may cause failure when calls are sent to voice mail.</span></span>

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a><span data-ttu-id="78563-241">Другая поддержка функций Lync Server 2013 для IPv6</span><span class="sxs-lookup"><span data-stu-id="78563-241">Other Lync Server 2013 Feature Support for IPv6</span></span>

<span data-ttu-id="78563-242">В дополнение к функциям и компонентам, упомянутым выше, Lync Server 2013 поддерживает IPv6 для следующих функций:</span><span class="sxs-lookup"><span data-stu-id="78563-242">In addition to the features and components mentioned previously, Lync Server 2013 supports IPv6 for the following features:</span></span>

  - <span data-ttu-id="78563-243">**Сохраняемый чат**</span><span class="sxs-lookup"><span data-stu-id="78563-243">**Persistent Chat**</span></span>
    
    <span data-ttu-id="78563-244">Вы можете настроить IPv6 для сохраняемого чата с помощью построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="78563-244">You configure IPv6 for Persistent Chat by using Topology Builder.</span></span> <span data-ttu-id="78563-245">Дополнительные сведения о настройке сохраняемого чата содержатся в документации развертывание сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="78563-245">For details about configuring Persistent Chat, see the Deploying Persistent Chat Server documentation.</span></span>

  - <span data-ttu-id="78563-246">**Отчеты качества взаимодействия (QoE) и регистрации вызовов (CDR).**</span><span class="sxs-lookup"><span data-stu-id="78563-246">**Quality of Experience (QoE) and call detail recording (CDR) reports**</span></span>
    
    <span data-ttu-id="78563-247">Отчеты мониторинга включают IP-адрес в том виде, в каком он хранится в базе данных сервера мониторинга, типа IPv4 или IPv6.</span><span class="sxs-lookup"><span data-stu-id="78563-247">Monitoring reports include the IP address as it is stored in the Monitoring Server database, whether of type IPv4 or IPv6.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

