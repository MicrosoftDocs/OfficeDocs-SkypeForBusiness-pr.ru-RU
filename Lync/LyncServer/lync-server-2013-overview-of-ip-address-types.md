---
title: 'Lync Server 2013: Обзор типов IP-адресов'
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
ms.openlocfilehash: 9663f7ee8b57ceba27e1a1892c30bb92a1c86ffc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521006"
---
# <a name="overview-of-ip-address-types-for-lync-server-2013"></a><span data-ttu-id="59209-102">Обзор типов IP-адресов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59209-102">Overview of IP address types for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59209-103">_**Последнее изменение темы:** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="59209-103">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="59209-104">При настройке IP-адресов в Lync Server 2013 у вас есть три варианта.</span><span class="sxs-lookup"><span data-stu-id="59209-104">You have three options when configuring IP addresses in Lync Server 2013.</span></span> <span data-ttu-id="59209-105">Вы можете настроить Lync Server 2013 для поддержки только протокола IP версии 4 (IPv4), только протокола IP версии 6 (IPv6) или их комбинации (это называется *двойным стеком*).</span><span class="sxs-lookup"><span data-stu-id="59209-105">You can configure Lync Server 2013 to support only IP version 4 (IPv4), only IP version 6 (IPv6), or a combination of both (known as a *dual stack*).</span></span> <span data-ttu-id="59209-106">Для каждого типа конфигурации существует некоторое количество проблем, которые необходимо принимать во внимание.</span><span class="sxs-lookup"><span data-stu-id="59209-106">There are several issues to consider with each type of configuration:</span></span>

  - <span data-ttu-id="59209-107">**Только IPv4**     IPv6 был создан, так как в мире не хватает IPv4-адресов.</span><span class="sxs-lookup"><span data-stu-id="59209-107">**IPv4 only**   IPv6 was created because the world is running out of IPv4 addresses.</span></span> <span data-ttu-id="59209-108">В конечном итоге IPv6 будет полностью поддерживаться во всем мире, но в настоящее время многие компании и устройства, с которыми, возможно, приходится иметь дело вашей организации, пока не поддерживают IPv6, и не будут поддерживать еще какое-то время.</span><span class="sxs-lookup"><span data-stu-id="59209-108">Ultimately, IPv6 will be fully supported worldwide, but at this time, many companies and devices that your enterprise might need to communicate with do not yet support IPv6, and may not for some time.</span></span> <span data-ttu-id="59209-109">Конфигурация только с IPv4 поможет гарантировать, что реализация Lync Server сможет общаться с большинством существующих устройств.</span><span class="sxs-lookup"><span data-stu-id="59209-109">An IPv4-only configuration will help to ensure that your Lync Server implementation can communicate with most existing devices.</span></span>

  - <span data-ttu-id="59209-110">**Только IPv6**     В настоящее время полная реализация IPv6 будет исключать связь с множеством существующих устройств.</span><span class="sxs-lookup"><span data-stu-id="59209-110">**IPv6 only**   Conversely, a full IPv6 implementation, at this time, will exclude communication with many existing devices.</span></span>

  - <span data-ttu-id="59209-111">**Двойной стек**     Dual Stack — это сеть, в которой включены IPv4-и IPv6-адреса.</span><span class="sxs-lookup"><span data-stu-id="59209-111">**Dual Stack**   Dual stack is a network where both IPv4 and IPv6 addresses are enabled.</span></span> <span data-ttu-id="59209-112">Эта конфигурация поддерживается в Lync Server 2013, так как в большинстве случаев переход с полной (IPv4) на полный IPv6 займет несколько лет.</span><span class="sxs-lookup"><span data-stu-id="59209-112">This configuration is supported in Lync Server 2013 because in most cases the transition from full-IPv4 to full-IPv6 will take several years.</span></span>

<span data-ttu-id="59209-113">В следующих разделах описывается совместимость между этими тремя конфигурациями для различных функций Lync Server.</span><span class="sxs-lookup"><span data-stu-id="59209-113">The following sections outline the compatibility among these three configurations for various Lync Server features.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="59209-p104">Клиентская или серверная конфигурация только с IPv6 поддерживается только для целей проверки или обучения. Конфигурация только с IPv6 не поддерживается в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="59209-p104">Client or server configuration with IPv6 only is supported only for lab or validation purposes. IPv6 only configuration is not supported in the production deployment.</span></span>



</div>

<div>

## <a name="client-registration"></a><span data-ttu-id="59209-116">Регистрация клиентов</span><span class="sxs-lookup"><span data-stu-id="59209-116">Client Registration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="59209-117">Сеть конечной точки клиента</span><span class="sxs-lookup"><span data-stu-id="59209-117">Client endpoint network</span></span></th>
<th><span data-ttu-id="59209-118">Сеть сервера</span><span class="sxs-lookup"><span data-stu-id="59209-118">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59209-119">IPv4</span><span class="sxs-lookup"><span data-stu-id="59209-119">IPv4</span></span></p></td>
<td><p><span data-ttu-id="59209-120">IPv4</span><span class="sxs-lookup"><span data-stu-id="59209-120">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59209-121">IPv4</span><span class="sxs-lookup"><span data-stu-id="59209-121">IPv4</span></span></p></td>
<td><p><span data-ttu-id="59209-122">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="59209-122">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59209-123">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="59209-123">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="59209-124">IPv4</span><span class="sxs-lookup"><span data-stu-id="59209-124">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59209-125">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="59209-125">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="59209-126">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="59209-126">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59209-127">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="59209-127">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="59209-128">IPv6</span><span class="sxs-lookup"><span data-stu-id="59209-128">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59209-129">IPv6</span><span class="sxs-lookup"><span data-stu-id="59209-129">IPv6</span></span></p></td>
<td><p><span data-ttu-id="59209-130">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="59209-130">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59209-131">IPv6</span><span class="sxs-lookup"><span data-stu-id="59209-131">IPv6</span></span></p></td>
<td><p><span data-ttu-id="59209-132">IPv6</span><span class="sxs-lookup"><span data-stu-id="59209-132">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="peer-to-peer-client"></a><span data-ttu-id="59209-133">Одноранговый клиент</span><span class="sxs-lookup"><span data-stu-id="59209-133">Peer-to-Peer Client</span></span>

<span data-ttu-id="59209-p105">Одноранговые коммуникации включают звуковую связь, видеосвязь, общий доступ к приложениям и передачу файлов. После успешной регистрации обоих клиентов поддерживаются следующие комбинации.</span><span class="sxs-lookup"><span data-stu-id="59209-p105">Peer-to-peer communications include audio, audio/video, application sharing, and file transfer. After both clients have successfully registered, the following combinations are supported.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="59209-136">Конечная точка клиента 1</span><span class="sxs-lookup"><span data-stu-id="59209-136">Client endpoint 1</span></span></th>
<th><span data-ttu-id="59209-137">Конечная точка клиента 2</span><span class="sxs-lookup"><span data-stu-id="59209-137">Client endpoint 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59209-138">IPv4</span><span class="sxs-lookup"><span data-stu-id="59209-138">IPv4</span></span></p></td>
<td><p><span data-ttu-id="59209-139">IPv4</span><span class="sxs-lookup"><span data-stu-id="59209-139">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59209-140">IPv4</span><span class="sxs-lookup"><span data-stu-id="59209-140">IPv4</span></span></p></td>
<td><p><span data-ttu-id="59209-141">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="59209-141">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59209-142">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="59209-142">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="59209-143">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="59209-143">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59209-144">IPv6</span><span class="sxs-lookup"><span data-stu-id="59209-144">IPv6</span></span></p></td>
<td><p><span data-ttu-id="59209-145">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="59209-145">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59209-146">IPv6</span><span class="sxs-lookup"><span data-stu-id="59209-146">IPv6</span></span></p></td>
<td><p><span data-ttu-id="59209-147">IPv6</span><span class="sxs-lookup"><span data-stu-id="59209-147">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="conferencing"></a><span data-ttu-id="59209-148">Конференции</span><span class="sxs-lookup"><span data-stu-id="59209-148">Conferencing</span></span>

<span data-ttu-id="59209-149">Конференц-связь включает видеосвязь, общий доступ к приложениям и совместную работу с данными (работу на доске и общий доступ к файлам).</span><span class="sxs-lookup"><span data-stu-id="59209-149">Conferencing includes audio/video, application sharing, and data collaboration (whiteboarding and file sharing).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="59209-150">Сеть конечной точки клиента</span><span class="sxs-lookup"><span data-stu-id="59209-150">Client endpoint network</span></span></th>
<th><span data-ttu-id="59209-151">Сеть сервера</span><span class="sxs-lookup"><span data-stu-id="59209-151">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59209-152">IPv4</span><span class="sxs-lookup"><span data-stu-id="59209-152">IPv4</span></span></p></td>
<td><p><span data-ttu-id="59209-153">IPv4</span><span class="sxs-lookup"><span data-stu-id="59209-153">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59209-154">IPv4</span><span class="sxs-lookup"><span data-stu-id="59209-154">IPv4</span></span></p></td>
<td><p><span data-ttu-id="59209-155">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="59209-155">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59209-156">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="59209-156">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="59209-157">IPv4</span><span class="sxs-lookup"><span data-stu-id="59209-157">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59209-158">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="59209-158">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="59209-159">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="59209-159">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59209-160">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="59209-160">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="59209-161">IPv6</span><span class="sxs-lookup"><span data-stu-id="59209-161">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59209-162">IPv6</span><span class="sxs-lookup"><span data-stu-id="59209-162">IPv6</span></span></p></td>
<td><p><span data-ttu-id="59209-163">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="59209-163">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59209-164">IPv6</span><span class="sxs-lookup"><span data-stu-id="59209-164">IPv6</span></span></p></td>
<td><p><span data-ttu-id="59209-165">IPv6</span><span class="sxs-lookup"><span data-stu-id="59209-165">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="mediation-serverpstn"></a><span data-ttu-id="59209-166">Сервер-посредник/ТСОП</span><span class="sxs-lookup"><span data-stu-id="59209-166">Mediation Server/PSTN</span></span>

<span data-ttu-id="59209-167">Lync Server 2013 не поддерживает обход сервера-посредника для вызовов телефонной сети общего пользования (PSTN), если трафик проходит через интерфейс IPv6.</span><span class="sxs-lookup"><span data-stu-id="59209-167">Lync Server 2013 does not support media bypass for public switched telephone network (PSTN) calls if the traffic is through an IPv6 interface.</span></span> <span data-ttu-id="59209-168">Если требуется обход сервера-посредника, то рекомендуется настроить шлюз ТСОП для IPv4.</span><span class="sxs-lookup"><span data-stu-id="59209-168">If media bypass is required, we recommend that the PSTN gateway is configured to IPv4.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="59209-169">Основной интерфейс\*</span><span class="sxs-lookup"><span data-stu-id="59209-169">Primary interface\*</span></span></th>
<th><span data-ttu-id="59209-170">Интерфейс ТСОП (на сервере-посреднике)</span><span class="sxs-lookup"><span data-stu-id="59209-170">PSTN interface (on Mediation Server)</span></span></th>
<th><span data-ttu-id="59209-171">Настройка шлюза ТСОП</span><span class="sxs-lookup"><span data-stu-id="59209-171">PSTN gateway setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59209-172">IPv4</span><span class="sxs-lookup"><span data-stu-id="59209-172">IPv4</span></span></p></td>
<td><p><span data-ttu-id="59209-173">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="59209-173">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="59209-174">IPv4</span><span class="sxs-lookup"><span data-stu-id="59209-174">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59209-175">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="59209-175">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="59209-176">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="59209-176">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="59209-177">IPv4</span><span class="sxs-lookup"><span data-stu-id="59209-177">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59209-178">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="59209-178">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="59209-179">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="59209-179">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="59209-180">IPv6</span><span class="sxs-lookup"><span data-stu-id="59209-180">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="59209-181">\* Основной интерфейс — это интерфейс, который обменивается данными с компонентами Lync Server.</span><span class="sxs-lookup"><span data-stu-id="59209-181">\* The primary interface is the interface that communicates with the Lync Server components.</span></span>

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a><span data-ttu-id="59209-182">Одноранговые коммуникации с удаленными пользователями</span><span class="sxs-lookup"><span data-stu-id="59209-182">Remote User Peer-to-Peer Communications</span></span>

<span data-ttu-id="59209-183">Одноранговые коммуникации с удаленными пользователями включают обмен мгновенными сообщениями, видеосвязь, общий доступ к приложениям и передачу файлов.</span><span class="sxs-lookup"><span data-stu-id="59209-183">Peer-to-peer communications with remote users include instant messaging, audio/video, application sharing, and file transfer.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="59209-184">Сеть удаленного пользователя</span><span class="sxs-lookup"><span data-stu-id="59209-184">Remote user network</span></span></th>
<th><span data-ttu-id="59209-185">Пограничный сервер (внешний периметр)</span><span class="sxs-lookup"><span data-stu-id="59209-185">Edge server (External edge)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59209-186">IPv4</span><span class="sxs-lookup"><span data-stu-id="59209-186">IPv4</span></span></p></td>
<td><p><span data-ttu-id="59209-187">IPv4</span><span class="sxs-lookup"><span data-stu-id="59209-187">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59209-188">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="59209-188">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="59209-189">IPv4</span><span class="sxs-lookup"><span data-stu-id="59209-189">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59209-190">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="59209-190">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="59209-191">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="59209-191">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59209-192">IPv6</span><span class="sxs-lookup"><span data-stu-id="59209-192">IPv6</span></span></p></td>
<td><p><span data-ttu-id="59209-193">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="59209-193">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59209-194">IPv6</span><span class="sxs-lookup"><span data-stu-id="59209-194">IPv6</span></span></p></td>
<td><p><span data-ttu-id="59209-195">IPv6</span><span class="sxs-lookup"><span data-stu-id="59209-195">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a><span data-ttu-id="59209-196">Конфигурация интерфейсного пула и пограничного пула</span><span class="sxs-lookup"><span data-stu-id="59209-196">Front End Pool and Edge Pool Configuration</span></span>

<span data-ttu-id="59209-197">В следующей таблице показана матрица поддержки между пулом серверов переднего плана и внутренним пулом пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="59209-197">The following table shows the support matrix between the Front End Server pool and the internal Edge Server pool.</span></span>

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a><span data-ttu-id="59209-198">Матрица интерфейсного пула и пограничного пула (внутренний периметр)</span><span class="sxs-lookup"><span data-stu-id="59209-198">Front End Pool and Edge Pool (Internal Edge) Matrix</span></span>

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
<td><p><span data-ttu-id="59209-199"><strong>Пограничный пул: IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="59209-199"><strong>Edge Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="59209-200"><strong>Пограничный пул: двойной стек</strong></span><span class="sxs-lookup"><span data-stu-id="59209-200"><strong>Edge Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="59209-201"><strong>Пограничный пул: IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="59209-201"><strong>Edge Pool: IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59209-202"><strong>Интерфейсный пул: IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="59209-202"><strong>Front End Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="59209-203">Да</span><span class="sxs-lookup"><span data-stu-id="59209-203">Yes</span></span></p></td>
<td><p><span data-ttu-id="59209-204">Да</span><span class="sxs-lookup"><span data-stu-id="59209-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="59209-205">Нет</span><span class="sxs-lookup"><span data-stu-id="59209-205">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59209-206"><strong>Интерфейсный пул: двойной стек</strong></span><span class="sxs-lookup"><span data-stu-id="59209-206"><strong>Front End Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="59209-207">Да</span><span class="sxs-lookup"><span data-stu-id="59209-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="59209-208">Да</span><span class="sxs-lookup"><span data-stu-id="59209-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="59209-209">Нет</span><span class="sxs-lookup"><span data-stu-id="59209-209">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59209-210"><strong>Интерфейсный пул: IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="59209-210"><strong>Front End Pool: IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="59209-211">Нет</span><span class="sxs-lookup"><span data-stu-id="59209-211">No</span></span></p></td>
<td><p><span data-ttu-id="59209-212">Нет</span><span class="sxs-lookup"><span data-stu-id="59209-212">No</span></span></p></td>
<td><p><span data-ttu-id="59209-213">Да\*</span><span class="sxs-lookup"><span data-stu-id="59209-213">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="59209-214">\* Используйте это сочетание только в лабораторной среде.</span><span class="sxs-lookup"><span data-stu-id="59209-214">\* Use this combination only in a lab environment.</span></span>

<span data-ttu-id="59209-215">В следующей таблице представлена матрица поддерживаемых комбинаций интерфейсов внешнего и внутреннего периметра.</span><span class="sxs-lookup"><span data-stu-id="59209-215">The following table is a matrix of the supported combinations of internal and external edge interfaces.</span></span>

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a><span data-ttu-id="59209-216">Матрица пограничного пула внутреннего периметра и пограничного пула внешнего периметра</span><span class="sxs-lookup"><span data-stu-id="59209-216">Edge Pool (Internal Edge) and Edge pool (External Edge) Matrix</span></span>

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
<td><p><span data-ttu-id="59209-217"><strong>Пограничный пул (внешний периметр): IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="59209-217"><strong>Edge Pool (External Edge) : IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="59209-218"><strong>Пограничный пул (внешний периметр): двойной стек</strong></span><span class="sxs-lookup"><span data-stu-id="59209-218"><strong>Edge Pool (External Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="59209-219"><strong>Пограничный пул (внешний периметр): IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="59209-219"><strong>Edge Pool (External Edge): IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59209-220"><strong>Пограничный пул (внутренний периметр): IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="59209-220"><strong>Edge Pool (Internal Edge): IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="59209-221">Да</span><span class="sxs-lookup"><span data-stu-id="59209-221">Yes</span></span></p></td>
<td><p><span data-ttu-id="59209-222">Да</span><span class="sxs-lookup"><span data-stu-id="59209-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="59209-223">Нет</span><span class="sxs-lookup"><span data-stu-id="59209-223">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59209-224"><strong>Пограничный пул (внутренний периметр): внутренний стек</strong></span><span class="sxs-lookup"><span data-stu-id="59209-224"><strong>Edge Pool (Internal Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="59209-225">Нет</span><span class="sxs-lookup"><span data-stu-id="59209-225">No</span></span></p></td>
<td><p><span data-ttu-id="59209-226">Да</span><span class="sxs-lookup"><span data-stu-id="59209-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="59209-227">Нет</span><span class="sxs-lookup"><span data-stu-id="59209-227">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59209-228"><strong>Пограничный пул (внутренний периметр): IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="59209-228"><strong>Edge Pool (Internal Edge): IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="59209-229">Нет</span><span class="sxs-lookup"><span data-stu-id="59209-229">No</span></span></p></td>
<td><p><span data-ttu-id="59209-230">Нет</span><span class="sxs-lookup"><span data-stu-id="59209-230">No</span></span></p></td>
<td><p><span data-ttu-id="59209-231">Да\*</span><span class="sxs-lookup"><span data-stu-id="59209-231">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="59209-232">\* Используйте это сочетание только в лабораторной среде.</span><span class="sxs-lookup"><span data-stu-id="59209-232">\* Use this combination only in a lab environment.</span></span>

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a><span data-ttu-id="59209-233">Улучшенная поддержка корпоративной голосовой связи для IPv6</span><span class="sxs-lookup"><span data-stu-id="59209-233">Advanced Enterprise Voice Support for IPv6</span></span>

<span data-ttu-id="59209-234">Развертывания, включающие контроль допуска звонков (CAC), Enhanced 9-1-1 (E9-1-1) или обход сервера-посредника, должны настраиваться как реализация только IPv4 или реализация двойного стека.</span><span class="sxs-lookup"><span data-stu-id="59209-234">Deployments that include call admission control (CAC), Enhanced 9-1-1 (E9-1-1), or media bypass must be configured as IPv4 only or as a dual-stacked implementation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="59209-235">В развертывании с двойным стеком даже в том случае, если клиент Lync подключается к серверу Lync Server с помощью IPv6, Lync предоставит лучшие усилия для сопоставления соответствующего IPv4-адреса для поддержки E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="59209-235">In a dual-stacked deployment, even if a Lync client connects to a Lync Server by using IPv6, Lync will make a best effort to map an appropriate IPv4 address to support E9-1-1.</span></span>



</div>

<span data-ttu-id="59209-236">Служба сведений о местоположении с IPv6-адресами не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="59209-236">Location Information service with IPv6 addresses is not supported.</span></span>

<span data-ttu-id="59209-p107">Единая система обмена сообщениями Exchange не поддерживает IPv6. Для единой системы обмена сообщениями Exchange следует убедиться, что DNS-разрешение не возвращает IPv6-адрес. Использование IPv6 может привести к сбою при отправке вызовов в голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="59209-p107">Exchange Unified Messaging (UM) does not support IPv6. For Exchange UM, be sure that DNS resolution does not return an IPv6 address. Using IPv6 may cause failure when calls are sent to voice mail.</span></span>

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a><span data-ttu-id="59209-240">Другая поддержка функций Lync Server 2013 для IPv6</span><span class="sxs-lookup"><span data-stu-id="59209-240">Other Lync Server 2013 Feature Support for IPv6</span></span>

<span data-ttu-id="59209-241">В дополнение к функциям и компонентам, упомянутым выше, Lync Server 2013 поддерживает IPv6 для следующих функций:</span><span class="sxs-lookup"><span data-stu-id="59209-241">In addition to the features and components mentioned previously, Lync Server 2013 supports IPv6 for the following features:</span></span>

  - <span data-ttu-id="59209-242">**Сохраняемый чат**</span><span class="sxs-lookup"><span data-stu-id="59209-242">**Persistent Chat**</span></span>
    
    <span data-ttu-id="59209-243">Вы можете настроить IPv6 для сохраняемого чата с помощью построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="59209-243">You configure IPv6 for Persistent Chat by using Topology Builder.</span></span> <span data-ttu-id="59209-244">Дополнительные сведения о настройке сохраняемого чата содержатся в документации развертывание сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="59209-244">For details about configuring Persistent Chat, see the Deploying Persistent Chat Server documentation.</span></span>

  - <span data-ttu-id="59209-245">**Отчеты качества взаимодействия (QoE) и регистрации вызовов (CDR).**</span><span class="sxs-lookup"><span data-stu-id="59209-245">**Quality of Experience (QoE) and call detail recording (CDR) reports**</span></span>
    
    <span data-ttu-id="59209-246">Отчеты мониторинга включают IP-адрес в том виде, в каком он хранится в базе данных сервера мониторинга, типа IPv4 или IPv6.</span><span class="sxs-lookup"><span data-stu-id="59209-246">Monitoring reports include the IP address as it is stored in the Monitoring Server database, whether of type IPv4 or IPv6.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

