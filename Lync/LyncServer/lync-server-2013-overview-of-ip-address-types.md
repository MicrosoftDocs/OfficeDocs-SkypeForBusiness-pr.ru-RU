---
title: 'Lync Server 2013: обзор типов IP-адресов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of IP address types for Lync Server
ms:assetid: ee9a695f-5cf5-441e-94fb-6adeca50e8d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205363(v=OCS.15)
ms:contentKeyID: 48185759
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90d31045879c4e6f488c232687346ed0413ef62b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825515"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-ip-address-types-for-lync-server-2013"></a><span data-ttu-id="ba982-102">Обзор типов IP-адресов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba982-102">Overview of IP address types for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba982-103">_**Тема последнего изменения:** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="ba982-103">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="ba982-104">При настройке IP-адресов в Lync Server 2013 у вас есть три варианта.</span><span class="sxs-lookup"><span data-stu-id="ba982-104">You have three options when configuring IP addresses in Lync Server 2013.</span></span> <span data-ttu-id="ba982-105">Вы можете настроить Lync Server 2013 таким образом, чтобы он поддерживал только IP версии 4 (IPv4), только IP версии 6 (IPv6) или сочетание обеих (называемых *двойных стеков*).</span><span class="sxs-lookup"><span data-stu-id="ba982-105">You can configure Lync Server 2013 to support only IP version 4 (IPv4), only IP version 6 (IPv6), or a combination of both (known as a *dual stack*).</span></span> <span data-ttu-id="ba982-106">Для каждого типа конфигурации существует некоторое количество проблем, которые необходимо принимать во внимание.</span><span class="sxs-lookup"><span data-stu-id="ba982-106">There are several issues to consider with each type of configuration:</span></span>

  - <span data-ttu-id="ba982-107">\*\*\*\*   Был создан только IPv4-адрес, так как в мире использующих IPv4-адреса.</span><span class="sxs-lookup"><span data-stu-id="ba982-107">**IPv4 only**   IPv6 was created because the world is running out of IPv4 addresses.</span></span> <span data-ttu-id="ba982-108">В конечном итоге IPv6 будет полностью поддерживаться во всем мире, но в настоящее время многие компании и устройства, с которыми, возможно, приходится иметь дело вашей организации, пока не поддерживают IPv6, и не будут поддерживать еще какое-то время.</span><span class="sxs-lookup"><span data-stu-id="ba982-108">Ultimately, IPv6 will be fully supported worldwide, but at this time, many companies and devices that your enterprise might need to communicate with do not yet support IPv6, and may not for some time.</span></span> <span data-ttu-id="ba982-109">Конфигурация, поддерживающая только IPv4-адреса, гарантирует, что реализация Lync Server сможет взаимодействовать с самыми существующими устройствами.</span><span class="sxs-lookup"><span data-stu-id="ba982-109">An IPv4-only configuration will help to ensure that your Lync Server implementation can communicate with most existing devices.</span></span>

  - <span data-ttu-id="ba982-110">**IPv6**   в настоящее время не поддерживает связь с большим количеством существующих устройств, а только в полной реализации IPv6.</span><span class="sxs-lookup"><span data-stu-id="ba982-110">**IPv6 only**   Conversely, a full IPv6 implementation, at this time, will exclude communication with many existing devices.</span></span>

  - <span data-ttu-id="ba982-111">\*\*\*\*   Двойная стопка стеков — сеть, в которой включены оба IPv4-и IPv6-адреса.</span><span class="sxs-lookup"><span data-stu-id="ba982-111">**Dual Stack**   Dual stack is a network where both IPv4 and IPv6 addresses are enabled.</span></span> <span data-ttu-id="ba982-112">Эта конфигурация поддерживается в Lync Server 2013, так как в большинстве случаев переход с полной-IPv4 на полный-IPv6 займет несколько лет.</span><span class="sxs-lookup"><span data-stu-id="ba982-112">This configuration is supported in Lync Server 2013 because in most cases the transition from full-IPv4 to full-IPv6 will take several years.</span></span>

<span data-ttu-id="ba982-113">В следующих разделах описаны вопросы, касающиеся этих трех конфигураций для различных функций Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ba982-113">The following sections outline the compatibility among these three configurations for various Lync Server features.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ba982-p104">Клиентская или серверная конфигурация только с IPv6 поддерживается только для целей проверки или обучения. Конфигурация только с IPv6 не поддерживается в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="ba982-p104">Client or server configuration with IPv6 only is supported only for lab or validation purposes. IPv6 only configuration is not supported in the production deployment.</span></span>



</div>

<div>

## <a name="client-registration"></a><span data-ttu-id="ba982-116">Регистрация клиентов</span><span class="sxs-lookup"><span data-stu-id="ba982-116">Client Registration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba982-117">Сеть конечной точки клиента</span><span class="sxs-lookup"><span data-stu-id="ba982-117">Client endpoint network</span></span></th>
<th><span data-ttu-id="ba982-118">Сеть сервера</span><span class="sxs-lookup"><span data-stu-id="ba982-118">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba982-119">IPv4</span><span class="sxs-lookup"><span data-stu-id="ba982-119">IPv4</span></span></p></td>
<td><p><span data-ttu-id="ba982-120">IPv4</span><span class="sxs-lookup"><span data-stu-id="ba982-120">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba982-121">IPv4</span><span class="sxs-lookup"><span data-stu-id="ba982-121">IPv4</span></span></p></td>
<td><p><span data-ttu-id="ba982-122">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="ba982-122">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba982-123">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="ba982-123">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="ba982-124">IPv4</span><span class="sxs-lookup"><span data-stu-id="ba982-124">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba982-125">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="ba982-125">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="ba982-126">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="ba982-126">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba982-127">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="ba982-127">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="ba982-128">IPv6</span><span class="sxs-lookup"><span data-stu-id="ba982-128">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba982-129">IPv6</span><span class="sxs-lookup"><span data-stu-id="ba982-129">IPv6</span></span></p></td>
<td><p><span data-ttu-id="ba982-130">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="ba982-130">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba982-131">IPv6</span><span class="sxs-lookup"><span data-stu-id="ba982-131">IPv6</span></span></p></td>
<td><p><span data-ttu-id="ba982-132">IPv6</span><span class="sxs-lookup"><span data-stu-id="ba982-132">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="peer-to-peer-client"></a><span data-ttu-id="ba982-133">Одноранговый клиент</span><span class="sxs-lookup"><span data-stu-id="ba982-133">Peer-to-Peer Client</span></span>

<span data-ttu-id="ba982-p105">Одноранговые коммуникации включают звуковую связь, видеосвязь, общий доступ к приложениям и передачу файлов. После успешной регистрации обоих клиентов поддерживаются следующие комбинации.</span><span class="sxs-lookup"><span data-stu-id="ba982-p105">Peer-to-peer communications include audio, audio/video, application sharing, and file transfer. After both clients have successfully registered, the following combinations are supported.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba982-136">Конечная точка клиента 1</span><span class="sxs-lookup"><span data-stu-id="ba982-136">Client endpoint 1</span></span></th>
<th><span data-ttu-id="ba982-137">Конечная точка клиента 2</span><span class="sxs-lookup"><span data-stu-id="ba982-137">Client endpoint 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba982-138">IPv4</span><span class="sxs-lookup"><span data-stu-id="ba982-138">IPv4</span></span></p></td>
<td><p><span data-ttu-id="ba982-139">IPv4</span><span class="sxs-lookup"><span data-stu-id="ba982-139">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba982-140">IPv4</span><span class="sxs-lookup"><span data-stu-id="ba982-140">IPv4</span></span></p></td>
<td><p><span data-ttu-id="ba982-141">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="ba982-141">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba982-142">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="ba982-142">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="ba982-143">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="ba982-143">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba982-144">IPv6</span><span class="sxs-lookup"><span data-stu-id="ba982-144">IPv6</span></span></p></td>
<td><p><span data-ttu-id="ba982-145">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="ba982-145">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba982-146">IPv6</span><span class="sxs-lookup"><span data-stu-id="ba982-146">IPv6</span></span></p></td>
<td><p><span data-ttu-id="ba982-147">IPv6</span><span class="sxs-lookup"><span data-stu-id="ba982-147">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="conferencing"></a><span data-ttu-id="ba982-148">конференц-связь</span><span class="sxs-lookup"><span data-stu-id="ba982-148">Conferencing</span></span>

<span data-ttu-id="ba982-149">Конференции включают звук и видео, общий доступ к приложениям и совместную работу с данными (доска и общий доступ к файлам).</span><span class="sxs-lookup"><span data-stu-id="ba982-149">Conferencing includes audio/video, application sharing, and data collaboration (whiteboarding and file sharing).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba982-150">Сеть конечной точки клиента</span><span class="sxs-lookup"><span data-stu-id="ba982-150">Client endpoint network</span></span></th>
<th><span data-ttu-id="ba982-151">Сеть сервера</span><span class="sxs-lookup"><span data-stu-id="ba982-151">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba982-152">IPv4</span><span class="sxs-lookup"><span data-stu-id="ba982-152">IPv4</span></span></p></td>
<td><p><span data-ttu-id="ba982-153">IPv4</span><span class="sxs-lookup"><span data-stu-id="ba982-153">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba982-154">IPv4</span><span class="sxs-lookup"><span data-stu-id="ba982-154">IPv4</span></span></p></td>
<td><p><span data-ttu-id="ba982-155">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="ba982-155">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba982-156">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="ba982-156">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="ba982-157">IPv4</span><span class="sxs-lookup"><span data-stu-id="ba982-157">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba982-158">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="ba982-158">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="ba982-159">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="ba982-159">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba982-160">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="ba982-160">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="ba982-161">IPv6</span><span class="sxs-lookup"><span data-stu-id="ba982-161">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba982-162">IPv6</span><span class="sxs-lookup"><span data-stu-id="ba982-162">IPv6</span></span></p></td>
<td><p><span data-ttu-id="ba982-163">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="ba982-163">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba982-164">IPv6</span><span class="sxs-lookup"><span data-stu-id="ba982-164">IPv6</span></span></p></td>
<td><p><span data-ttu-id="ba982-165">IPv6</span><span class="sxs-lookup"><span data-stu-id="ba982-165">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="mediation-serverpstn"></a><span data-ttu-id="ba982-166">Сервер-посредник/ТСОП</span><span class="sxs-lookup"><span data-stu-id="ba982-166">Mediation Server/PSTN</span></span>

<span data-ttu-id="ba982-167">Lync Server 2013 не поддерживает обмен мультимедийными звонками для коммутируемых коммутируемых телефонных сетей (PSTN), если трафик проходит через интерфейс IPv6.</span><span class="sxs-lookup"><span data-stu-id="ba982-167">Lync Server 2013 does not support media bypass for public switched telephone network (PSTN) calls if the traffic is through an IPv6 interface.</span></span> <span data-ttu-id="ba982-168">Если требуется обход сервера-посредника, то рекомендуется настроить шлюз ТСОП для IPv4.</span><span class="sxs-lookup"><span data-stu-id="ba982-168">If media bypass is required, we recommend that the PSTN gateway is configured to IPv4.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba982-169">Основной интерфейс\*</span><span class="sxs-lookup"><span data-stu-id="ba982-169">Primary interface\*</span></span></th>
<th><span data-ttu-id="ba982-170">Интерфейс ТСОП (на сервере-посреднике)</span><span class="sxs-lookup"><span data-stu-id="ba982-170">PSTN interface (on Mediation Server)</span></span></th>
<th><span data-ttu-id="ba982-171">Настройка шлюза ТСОП</span><span class="sxs-lookup"><span data-stu-id="ba982-171">PSTN gateway setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba982-172">IPv4</span><span class="sxs-lookup"><span data-stu-id="ba982-172">IPv4</span></span></p></td>
<td><p><span data-ttu-id="ba982-173">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="ba982-173">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="ba982-174">IPv4</span><span class="sxs-lookup"><span data-stu-id="ba982-174">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba982-175">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="ba982-175">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="ba982-176">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="ba982-176">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="ba982-177">IPv4</span><span class="sxs-lookup"><span data-stu-id="ba982-177">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba982-178">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="ba982-178">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="ba982-179">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="ba982-179">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="ba982-180">IPv6</span><span class="sxs-lookup"><span data-stu-id="ba982-180">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ba982-181">\*Основным интерфейсом является интерфейс, который взаимодействует с компонентами Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ba982-181">\* The primary interface is the interface that communicates with the Lync Server components.</span></span>

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a><span data-ttu-id="ba982-182">Одноранговые коммуникации с удаленными пользователями</span><span class="sxs-lookup"><span data-stu-id="ba982-182">Remote User Peer-to-Peer Communications</span></span>

<span data-ttu-id="ba982-183">Одноранговые коммуникации с удаленными пользователями включают обмен мгновенными сообщениями, видеосвязь, общий доступ к приложениям и передачу файлов.</span><span class="sxs-lookup"><span data-stu-id="ba982-183">Peer-to-peer communications with remote users include instant messaging, audio/video, application sharing, and file transfer.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba982-184">Сеть удаленного пользователя</span><span class="sxs-lookup"><span data-stu-id="ba982-184">Remote user network</span></span></th>
<th><span data-ttu-id="ba982-185">Пограничный сервер (внешний периметр)</span><span class="sxs-lookup"><span data-stu-id="ba982-185">Edge server (External edge)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba982-186">IPv4</span><span class="sxs-lookup"><span data-stu-id="ba982-186">IPv4</span></span></p></td>
<td><p><span data-ttu-id="ba982-187">IPv4</span><span class="sxs-lookup"><span data-stu-id="ba982-187">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba982-188">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="ba982-188">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="ba982-189">IPv4</span><span class="sxs-lookup"><span data-stu-id="ba982-189">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba982-190">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="ba982-190">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="ba982-191">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="ba982-191">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba982-192">IPv6</span><span class="sxs-lookup"><span data-stu-id="ba982-192">IPv6</span></span></p></td>
<td><p><span data-ttu-id="ba982-193">Двойной стек</span><span class="sxs-lookup"><span data-stu-id="ba982-193">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba982-194">IPv6</span><span class="sxs-lookup"><span data-stu-id="ba982-194">IPv6</span></span></p></td>
<td><p><span data-ttu-id="ba982-195">IPv6</span><span class="sxs-lookup"><span data-stu-id="ba982-195">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a><span data-ttu-id="ba982-196">Конфигурация интерфейсного пула и пограничного пула</span><span class="sxs-lookup"><span data-stu-id="ba982-196">Front End Pool and Edge Pool Configuration</span></span>

<span data-ttu-id="ba982-197">В таблице ниже показана матрица поддержки между пулом сервер переднего плана и внутренним пулом пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="ba982-197">The following table shows the support matrix between the Front End Server pool and the internal Edge Server pool.</span></span>

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a><span data-ttu-id="ba982-198">Матрица интерфейсного пула и пограничного пула (внутренний периметр)</span><span class="sxs-lookup"><span data-stu-id="ba982-198">Front End Pool and Edge Pool (Internal Edge) Matrix</span></span>

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
<td><p><span data-ttu-id="ba982-199"><strong>Пограничный пул: IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="ba982-199"><strong>Edge Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="ba982-200"><strong>Пограничный пул: двойной стек</strong></span><span class="sxs-lookup"><span data-stu-id="ba982-200"><strong>Edge Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="ba982-201"><strong>Пограничный пул: IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="ba982-201"><strong>Edge Pool: IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba982-202"><strong>Интерфейсный пул: IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="ba982-202"><strong>Front End Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="ba982-203">Да</span><span class="sxs-lookup"><span data-stu-id="ba982-203">Yes</span></span></p></td>
<td><p><span data-ttu-id="ba982-204">Да</span><span class="sxs-lookup"><span data-stu-id="ba982-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="ba982-205">Да</span><span class="sxs-lookup"><span data-stu-id="ba982-205">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba982-206"><strong>Интерфейсный пул: двойной стек</strong></span><span class="sxs-lookup"><span data-stu-id="ba982-206"><strong>Front End Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="ba982-207">Да </span><span class="sxs-lookup"><span data-stu-id="ba982-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="ba982-208">Да</span><span class="sxs-lookup"><span data-stu-id="ba982-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="ba982-209">Да</span><span class="sxs-lookup"><span data-stu-id="ba982-209">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba982-210"><strong>Интерфейсный пул: IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="ba982-210"><strong>Front End Pool: IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="ba982-211">Возможность идентификации любого пользователя в организации с помощью ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="ba982-211">No</span></span></p></td>
<td><p><span data-ttu-id="ba982-212">Нет</span><span class="sxs-lookup"><span data-stu-id="ba982-212">No</span></span></p></td>
<td><p><span data-ttu-id="ba982-213">Да\*</span><span class="sxs-lookup"><span data-stu-id="ba982-213">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ba982-214">\*Используйте это сочетание только в лабораторной среде.</span><span class="sxs-lookup"><span data-stu-id="ba982-214">\* Use this combination only in a lab environment.</span></span>

<span data-ttu-id="ba982-215">В следующей таблице представлена матрица поддерживаемых комбинаций интерфейсов внешнего и внутреннего периметра.</span><span class="sxs-lookup"><span data-stu-id="ba982-215">The following table is a matrix of the supported combinations of internal and external edge interfaces.</span></span>

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a><span data-ttu-id="ba982-216">Матрица пограничного пула внутреннего периметра и пограничного пула внешнего периметра</span><span class="sxs-lookup"><span data-stu-id="ba982-216">Edge Pool (Internal Edge) and Edge pool (External Edge) Matrix</span></span>

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
<td><p><span data-ttu-id="ba982-217"><strong>Пограничный пул (внешний периметр): IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="ba982-217"><strong>Edge Pool (External Edge) : IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="ba982-218"><strong>Пограничный пул (внешний периметр): двойной стек</strong></span><span class="sxs-lookup"><span data-stu-id="ba982-218"><strong>Edge Pool (External Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="ba982-219"><strong>Пограничный пул (внешний периметр): IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="ba982-219"><strong>Edge Pool (External Edge): IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba982-220"><strong>Пограничный пул (внутренний периметр): IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="ba982-220"><strong>Edge Pool (Internal Edge): IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="ba982-221">Да</span><span class="sxs-lookup"><span data-stu-id="ba982-221">Yes</span></span></p></td>
<td><p><span data-ttu-id="ba982-222">Да</span><span class="sxs-lookup"><span data-stu-id="ba982-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="ba982-223">Да</span><span class="sxs-lookup"><span data-stu-id="ba982-223">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba982-224"><strong>Пограничный пул (внутренний периметр): двойной стек</strong></span><span class="sxs-lookup"><span data-stu-id="ba982-224"><strong>Edge Pool (Internal Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="ba982-225">Нет</span><span class="sxs-lookup"><span data-stu-id="ba982-225">No</span></span></p></td>
<td><p><span data-ttu-id="ba982-226">Да</span><span class="sxs-lookup"><span data-stu-id="ba982-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="ba982-227">Нет</span><span class="sxs-lookup"><span data-stu-id="ba982-227">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba982-228"><strong>Пограничный пул (внутренний периметр): IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="ba982-228"><strong>Edge Pool (Internal Edge): IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="ba982-229">Нет</span><span class="sxs-lookup"><span data-stu-id="ba982-229">No</span></span></p></td>
<td><p><span data-ttu-id="ba982-230">Нет</span><span class="sxs-lookup"><span data-stu-id="ba982-230">No</span></span></p></td>
<td><p><span data-ttu-id="ba982-231">Да\*</span><span class="sxs-lookup"><span data-stu-id="ba982-231">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ba982-232">\*Используйте это сочетание только в лабораторной среде.</span><span class="sxs-lookup"><span data-stu-id="ba982-232">\* Use this combination only in a lab environment.</span></span>

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a><span data-ttu-id="ba982-233">Улучшенная поддержка корпоративной голосовой связи для IPv6</span><span class="sxs-lookup"><span data-stu-id="ba982-233">Advanced Enterprise Voice Support for IPv6</span></span>

<span data-ttu-id="ba982-234">Развертывания, включающие контроль допуска звонков (CAC), Enhanced 9-1-1 (E9-1-1) или обход сервера-посредника, должны настраиваться как реализация только IPv4 или реализация двойного стека.</span><span class="sxs-lookup"><span data-stu-id="ba982-234">Deployments that include call admission control (CAC), Enhanced 9-1-1 (E9-1-1), or media bypass must be configured as IPv4 only or as a dual-stacked implementation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ba982-235">В двухсерверной среде, даже если клиент Lync подключается к серверу Lync Server с помощью IPv6, Lync обеспечивает наилучший способ сопоставления соответствующего адреса IPv4 для поддержки E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="ba982-235">In a dual-stacked deployment, even if a Lync client connects to a Lync Server by using IPv6, Lync will make a best effort to map an appropriate IPv4 address to support E9-1-1.</span></span>



</div>

<span data-ttu-id="ba982-236">Служба сведений о расположении с IPv6-адресами не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="ba982-236">Location Information service with IPv6 addresses is not supported.</span></span>

<span data-ttu-id="ba982-p107">Единая система обмена сообщениями Exchange не поддерживает IPv6. Для единой системы обмена сообщениями Exchange следует убедиться, что DNS-разрешение не возвращает IPv6-адрес. Использование IPv6 может привести к сбою при отправке вызовов в голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="ba982-p107">Exchange Unified Messaging (UM) does not support IPv6. For Exchange UM, be sure that DNS resolution does not return an IPv6 address. Using IPv6 may cause failure when calls are sent to voice mail.</span></span>

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a><span data-ttu-id="ba982-240">Другие поддерживаемые возможности Lync Server 2013 для IPv6</span><span class="sxs-lookup"><span data-stu-id="ba982-240">Other Lync Server 2013 Feature Support for IPv6</span></span>

<span data-ttu-id="ba982-241">Помимо описанных выше функций и компонентов, Lync Server 2013 поддерживает IPv6 для следующих функций:</span><span class="sxs-lookup"><span data-stu-id="ba982-241">In addition to the features and components mentioned previously, Lync Server 2013 supports IPv6 for the following features:</span></span>

  - <span data-ttu-id="ba982-242">**Сохраняемый чат**</span><span class="sxs-lookup"><span data-stu-id="ba982-242">**Persistent Chat**</span></span>
    
    <span data-ttu-id="ba982-243">Вы можете настроить IPv6 для сохраняемого чата с помощью построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="ba982-243">You configure IPv6 for Persistent Chat by using Topology Builder.</span></span> <span data-ttu-id="ba982-244">Сведения о настройке сохраняемого чата можно найти в документации развертывание сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="ba982-244">For details about configuring Persistent Chat, see the Deploying Persistent Chat Server documentation.</span></span>

  - <span data-ttu-id="ba982-245">**Отчеты качества взаимодействия (QoE) и регистрации вызовов (CDR).**</span><span class="sxs-lookup"><span data-stu-id="ba982-245">**Quality of Experience (QoE) and call detail recording (CDR) reports**</span></span>
    
    <span data-ttu-id="ba982-246">Отчеты мониторинга включают IP-адрес в том виде, в каком он хранится в базе данных сервера мониторинга, типа IPv4 или IPv6.</span><span class="sxs-lookup"><span data-stu-id="ba982-246">Monitoring reports include the IP address as it is stored in the Monitoring Server database, whether of type IPv4 or IPv6.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

