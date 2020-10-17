---
title: 'Lync Server 2013: определение требований к внешнему брандмауэру аудио-и видеоданных'
description: 'Lync Server 2013: определение требований к внешнему брандмауэру аудио-и видеоданных и портам.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine external A/V firewall and port requirements
ms:assetid: 3b849dc7-175d-40d1-820d-80e6ade6d332
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425882(v=OCS.15)
ms:contentKeyID: 48183872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38c2a8c1e8e332a4a1e65adb87a1e962e82941c2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550935"
---
# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a><span data-ttu-id="d2981-103">Определение требований к внешнему брандмауэру аудио-и видеоданных для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2981-103">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2981-104">_**Последнее изменение темы:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="d2981-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="d2981-p101">Аудио- и видеокоммуникации могут иметь сложную реализацию. В связи с природой протоколов для аудио и видео и способами их использования клиентами и серверами пояснение различий между клиентской и серверной версией вынесено в отдельный раздел.</span><span class="sxs-lookup"><span data-stu-id="d2981-p101">Audio/Video (A/V) communication can be a complex. Because of the nature of protocols used in A/V and how clients and servers use the protocols, a special section is warranted to explain the differences between client and server versions.</span></span>

<span data-ttu-id="d2981-107">Используйте следующую таблицу брандмауэра и портов для аудио- и видеоданных, чтобы определить требования к брандмауэру и открытым портам.</span><span class="sxs-lookup"><span data-stu-id="d2981-107">Use the following A/V Firewall and Port table to determine firewall requirements and which ports to open.</span></span> <span data-ttu-id="d2981-108">После этого изучите терминологию преобразования сетевых адресов (NAT), поскольку NAT может быть реализовано множеством разных способов.</span><span class="sxs-lookup"><span data-stu-id="d2981-108">Then, review the network address translation (NAT) terminology because NAT can be implemented in many different ways.</span></span> <span data-ttu-id="d2981-109">Подробный пример параметров порта брандмауэра приведен в статье Reference Architecture Architecture в [сценариях для доступа внешних пользователей в Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="d2981-109">For a detailed example of firewall port settings, see the reference architectures in [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a><span data-ttu-id="d2981-110">Общее использование протокола для UDP и TCP в аудио-и видеоматериалах и трафике мультимедиа</span><span class="sxs-lookup"><span data-stu-id="d2981-110">General Protocol Usage for UDP and TCP in Audio/Video and Media Traffic</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d2981-111">Транспорт аудио-и видеоданных</span><span class="sxs-lookup"><span data-stu-id="d2981-111">Audio/Video Transport</span></span></th>
<th><span data-ttu-id="d2981-112">Применение</span><span class="sxs-lookup"><span data-stu-id="d2981-112">Usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d2981-113">ПРОТОКОЛА</span><span class="sxs-lookup"><span data-stu-id="d2981-113">UDP</span></span></p></td>
<td><p><span data-ttu-id="d2981-114">Предпочтительный протокол транспортного уровня для аудио и видео</span><span class="sxs-lookup"><span data-stu-id="d2981-114">Preferred transport layer protocol for audio and video</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2981-115">TCP</span><span class="sxs-lookup"><span data-stu-id="d2981-115">TCP</span></span></p></td>
<td><p><span data-ttu-id="d2981-116">Резервный протокол транспортного уровня для аудио и видео</span><span class="sxs-lookup"><span data-stu-id="d2981-116">Fallback transport layer protocol for audio and video</span></span></p>
<p><span data-ttu-id="d2981-117">Обязательный протокол транспортного уровня для общего доступа к приложениям Office Communications Server 2007 R2, Lync Server 2010 и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2981-117">Required transport layer protocol for application sharing to Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013</span></span></p>
<p><span data-ttu-id="d2981-118">Обязательный протокол транспортного уровня для передачи файлов в Lync Server 2010 и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2981-118">Required transport layer protocol for file transfer to Lync Server 2010 and Lync Server 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a><span data-ttu-id="d2981-119">Требования к внешним портам брандмауэра и портам для аудио- и видеоданных для доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="d2981-119">External A/V Firewall Port Requirements for External User Access</span></span>

<span data-ttu-id="d2981-120">Требования к портам брандмауэра для внешних (и внутренних) интерфейсов SIP и конференций согласованы независимо от версии клиента или версии партнера Федерации.</span><span class="sxs-lookup"><span data-stu-id="d2981-120">The firewall port requirements for external (and internal) SIP and conferencing interfaces are consistent, regardless of the version of your client or the version of the federation partner.</span></span>

<span data-ttu-id="d2981-121">Однако это не распространяется на внешний интерфейс для пограничной службы обработки аудио- и видеоданных.</span><span class="sxs-lookup"><span data-stu-id="d2981-121">The same is not true for the Audio/Video Edge external interface.</span></span> <span data-ttu-id="d2981-122">Для Федерации с Office Communications Server 2007, пограничная служба аудио-и видеоданных требует, чтобы внешние правила брандмауэра допускали трафик RTP/TCP и RTP/UDP в диапазоне портов 50 000 – 59 999 для передачи в обоих направлениях.</span><span class="sxs-lookup"><span data-stu-id="d2981-122">For federation with Office Communications Server 2007, the A/V Edge service requires that external firewall rules allow RTP/TCP and RTP/UDP traffic in the 50,000 through 59,999 port range to flow in both directions.</span></span> <span data-ttu-id="d2981-123">В приведенной выше таблице предполагается, что Lync Server 2013 является основным партнером Федерации и настроен для общения с одним из указанных типов партнеров Федерации.</span><span class="sxs-lookup"><span data-stu-id="d2981-123">The previous table assumes that Lync Server 2013 is the primary federation partner and it is being configured to communicate with one of the other federation partner types listed.</span></span>

<span data-ttu-id="d2981-124">При настройке диапазона портов для аудио и видеопортов 50000-– 999 необходимо учитывать, что диапазон портов будет содержать исходные порты для связи с партнерами Федерации.</span><span class="sxs-lookup"><span data-stu-id="d2981-124">Configuring the Audio/Video port range of 50,000-59,999 must take into account that the port range will contain the source ports for communications to federation partners.</span></span> <span data-ttu-id="d2981-125">Обратите внимание, что связь инициируется партнером Федерации.</span><span class="sxs-lookup"><span data-stu-id="d2981-125">In detail, consider that a communication is initiated from a federation partner.</span></span> <span data-ttu-id="d2981-126">Связь из портов пограничной службы аудио-и видеоданных в диапазоне 50000-– 999 будет подключаться к ожидаемому порту TCP 443 для пограничной службы передачи аудио-и видеоданных партнера.</span><span class="sxs-lookup"><span data-stu-id="d2981-126">The communication from the A/V Edge service ports in the 50,000-59,999 range will connect to the expected port TCP 443 of the partner’s A/V Edge service.</span></span> <span data-ttu-id="d2981-127">И наоборот, входящий трафик на порт пограничной службы аудио-и видеосвязи TCP 443 будет иметь исходный порт в диапазоне 50000-– 999.</span><span class="sxs-lookup"><span data-stu-id="d2981-127">Conversely, inbound traffic to your A/V Edge service port TCP 443 will have a source port in the range of 50,000-59,999.</span></span>

<span data-ttu-id="d2981-128">Для разных брандмауэров и политик для администрирования брандмауэра может потребоваться настройка только правил назначения, а также может требоваться Настройка исходного и конечного адресов.</span><span class="sxs-lookup"><span data-stu-id="d2981-128">Different firewalls and policies for firewall administration may require only destination rules to be configured, or they may require both source and destination to be configured.</span></span> <span data-ttu-id="d2981-129">Если ваши требования относятся только к портам назначения, требования к аудио-и видеосигналам:</span><span class="sxs-lookup"><span data-stu-id="d2981-129">If your requirements are for destination ports only, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d2981-130">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="d2981-130">Source IP</span></span></th>
<th><span data-ttu-id="d2981-131">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="d2981-131">Destination IP</span></span></th>
<th><span data-ttu-id="d2981-132">Порт назначения</span><span class="sxs-lookup"><span data-stu-id="d2981-132">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d2981-133">Интерфейс пограничного сервера аудио-и видеоданных</span><span class="sxs-lookup"><span data-stu-id="d2981-133">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="d2981-134">Любой</span><span class="sxs-lookup"><span data-stu-id="d2981-134">Any</span></span></p></td>
<td><p><span data-ttu-id="d2981-135">TCP 443</span><span class="sxs-lookup"><span data-stu-id="d2981-135">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2981-136">Интерфейс пограничного сервера аудио-и видеоданных</span><span class="sxs-lookup"><span data-stu-id="d2981-136">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="d2981-137">Любой</span><span class="sxs-lookup"><span data-stu-id="d2981-137">Any</span></span></p></td>
<td><p><span data-ttu-id="d2981-138">UDP 3478;</span><span class="sxs-lookup"><span data-stu-id="d2981-138">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d2981-139">Любой</span><span class="sxs-lookup"><span data-stu-id="d2981-139">Any</span></span></p></td>
<td><p><span data-ttu-id="d2981-140">Интерфейс пограничного сервера аудио-и видеоданных</span><span class="sxs-lookup"><span data-stu-id="d2981-140">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="d2981-141">TCP 443</span><span class="sxs-lookup"><span data-stu-id="d2981-141">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2981-142">Любой</span><span class="sxs-lookup"><span data-stu-id="d2981-142">Any</span></span></p></td>
<td><p><span data-ttu-id="d2981-143">Интерфейс пограничного сервера аудио-и видеоданных</span><span class="sxs-lookup"><span data-stu-id="d2981-143">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="d2981-144">UDP 3478;</span><span class="sxs-lookup"><span data-stu-id="d2981-144">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d2981-145">Если для политик требуются определения правил брандмауэра для входящих и исходящих подключений, необходимы следующие требования к аудио-и видеосигналам.</span><span class="sxs-lookup"><span data-stu-id="d2981-145">If your policies require both inbound and outbound firewall rule definitions, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d2981-146">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="d2981-146">Source IP</span></span></th>
<th><span data-ttu-id="d2981-147">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="d2981-147">Destination IP</span></span></th>
<th><span data-ttu-id="d2981-148">Порт источника</span><span class="sxs-lookup"><span data-stu-id="d2981-148">Source Port</span></span></th>
<th><span data-ttu-id="d2981-149">Порт назначения</span><span class="sxs-lookup"><span data-stu-id="d2981-149">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d2981-150">Интерфейс пограничного сервера аудио-и видеоданных</span><span class="sxs-lookup"><span data-stu-id="d2981-150">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="d2981-151">Любой</span><span class="sxs-lookup"><span data-stu-id="d2981-151">Any</span></span></p></td>
<td><p><span data-ttu-id="d2981-152">TCP 50000 — – 999</span><span class="sxs-lookup"><span data-stu-id="d2981-152">TCP 50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="d2981-153">TCP 443</span><span class="sxs-lookup"><span data-stu-id="d2981-153">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2981-154">Интерфейс пограничного сервера аудио-и видеоданных</span><span class="sxs-lookup"><span data-stu-id="d2981-154">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="d2981-155">Любой</span><span class="sxs-lookup"><span data-stu-id="d2981-155">Any</span></span></p></td>
<td><p><span data-ttu-id="d2981-156">UDP 3478;</span><span class="sxs-lookup"><span data-stu-id="d2981-156">UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="d2981-157">UDP 3478;</span><span class="sxs-lookup"><span data-stu-id="d2981-157">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d2981-158">Любой</span><span class="sxs-lookup"><span data-stu-id="d2981-158">Any</span></span></p></td>
<td><p><span data-ttu-id="d2981-159">Интерфейс пограничного сервера аудио-и видеоданных</span><span class="sxs-lookup"><span data-stu-id="d2981-159">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="d2981-160">Любой</span><span class="sxs-lookup"><span data-stu-id="d2981-160">Any</span></span></p></td>
<td><p><span data-ttu-id="d2981-161">TCP 443</span><span class="sxs-lookup"><span data-stu-id="d2981-161">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2981-162">Любой</span><span class="sxs-lookup"><span data-stu-id="d2981-162">Any</span></span></p></td>
<td><p><span data-ttu-id="d2981-163">Интерфейс пограничного сервера аудио-и видеоданных</span><span class="sxs-lookup"><span data-stu-id="d2981-163">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="d2981-164">Любой</span><span class="sxs-lookup"><span data-stu-id="d2981-164">Any</span></span></p></td>
<td><p><span data-ttu-id="d2981-165">UDP 3478;</span><span class="sxs-lookup"><span data-stu-id="d2981-165">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="d2981-166">Microsoft Office Communications Server 2007 требует немного другой настройки.</span><span class="sxs-lookup"><span data-stu-id="d2981-166">Microsoft Office Communications Server 2007 requires a slightly different configuration.</span></span> <span data-ttu-id="d2981-167">Диапазон портов TCP и UDP (50000-– 999) должен быть открытым для входящих и исходящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="d2981-167">The TCP and UDP port range of 50,000-59,999 must be open inbound and outbound.</span></span> <span data-ttu-id="d2981-168">Это требование относится только к Office Communicator 2007.</span><span class="sxs-lookup"><span data-stu-id="d2981-168">This requirement is only for Office Communicator 2007.</span></span> <span data-ttu-id="d2981-169">Office Communications Server 2007 R2, Lync Server 2010 и Lync Server 2013 требуется только TCP Range 50000-– 999 Open Outbound.</span><span class="sxs-lookup"><span data-stu-id="d2981-169">Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013 only require TCP range 50,000-59,999 open outbound.</span></span>



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a><span data-ttu-id="d2981-170">Требования к NAT для пограничной службы</span><span class="sxs-lookup"><span data-stu-id="d2981-170">NAT requirements for the Edge service</span></span>

<span data-ttu-id="d2981-171">Если вы решили настроить частные IP-адреса без маршрутизации для пограничной службы, применяются следующие требования к NAT:</span><span class="sxs-lookup"><span data-stu-id="d2981-171">The following NAT requirements apply if you choose to configure non-routable private IP addresses for the Edge service:</span></span>

  - <span data-ttu-id="d2981-172">Преобразование сетевых адресов (NAT) можно использовать только с балансировкой нагрузки на DNS.</span><span class="sxs-lookup"><span data-stu-id="d2981-172">NAT can only be used with DNS load-balancing.</span></span> <span data-ttu-id="d2981-173">NAT не поддерживается в пограничной топологии аппаратной балансировки нагрузки (HLB).</span><span class="sxs-lookup"><span data-stu-id="d2981-173">NAT is not supported with a hardware load balancing (HLB) Edge topology.</span></span>

  - <span data-ttu-id="d2981-174">Преобразование сетевых адресов (NAT) можно использовать только для внешнего интерфейса пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="d2981-174">NAT can only be used on the external Edge interface.</span></span> <span data-ttu-id="d2981-175">NAT не поддерживается во внутреннем интерфейсе пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="d2981-175">NAT is not supported on the internal Edge interface.</span></span>

  - <span data-ttu-id="d2981-176">Для входящего и исходящего трафика NAT должен быть симметричным.</span><span class="sxs-lookup"><span data-stu-id="d2981-176">NAT must be symmetric for incoming and outgoing traffic.</span></span>
    
  - <span data-ttu-id="d2981-177">Для трафика из Интернета NAT необходимо изменить конечный IP-адрес с общедоступного IP-адреса, поддерживающего NAT, на внешний IP-адрес службы пограничного сервера аудио-и видеоданных.</span><span class="sxs-lookup"><span data-stu-id="d2981-177">For traffic from the Internet, NAT must change the destination IP address from the NAT-enabled public IP address of the A/V Edge service to its external IP address.</span></span> <span data-ttu-id="d2981-178">Исходный IP-адрес должен остаться без изменений, чтобы служба пограничного сервера аудио-и видеоданных могла найти оптимальный путь к носителю.</span><span class="sxs-lookup"><span data-stu-id="d2981-178">The source IP address must remain intact, so that the A/V Edge service can find the optimal media path.</span></span>
  
  <span data-ttu-id="d2981-179">Например, во входящем расположении на рисунке ниже общедоступный IP-адрес 131.107.155.30 был изменен на внешний (частный) IP-адрес 10.45.16.10.</span><span class="sxs-lookup"><span data-stu-id="d2981-179">For example, in the inbound direction in the figure below, the public IP address 131.107.155.30 was changed to the external (private) IP address 10.45.16.10.</span></span> <span data-ttu-id="d2981-180">Исходный IP-адрес остается неизменным.</span><span class="sxs-lookup"><span data-stu-id="d2981-180">The source IP address remained unchanged.</span></span>
  
  - <span data-ttu-id="d2981-181">Для трафика из пограничной службы аудио-и видеоданных в Интернете необходимо изменить исходный IP-адрес с внешнего IP-адреса службы пограничного сервера аудио-и видеоданных на общедоступный IP-адрес, поддерживающий NAT.</span><span class="sxs-lookup"><span data-stu-id="d2981-181">For traffic from the A/V Edge service to the Internet, NAT must change the source IP address from the external IP address of the A/V Edge service to the NAT-enabled public IP address.</span></span>

<span data-ttu-id="d2981-182">Например, в исходящем направлении на рисунке ниже внешний IP-адрес (частный) 10.45.16.10 был изменен на общедоступный IP-адрес 131.107.155.30.</span><span class="sxs-lookup"><span data-stu-id="d2981-182">For example, in the outbound direction in the figure below, the external (private) IP address 10.45.16.10 was changed to the public IP address 131.107.155.30.</span></span>

<span data-ttu-id="d2981-183">**На приведенном ниже рисунке показано, как NAT изменяет конечный IP-адрес для входящего трафика и исходный IP-адрес для исходящего трафика.**</span><span class="sxs-lookup"><span data-stu-id="d2981-183">**The figure below shows how NAT changes the destination IP address for inbound traffic and the source IP Address for outbound traffic.**</span></span>

<span data-ttu-id="d2981-184">![Изменение IP-адресов назначения и источника](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Изменение IP-адресов назначения и источника")</span><span class="sxs-lookup"><span data-stu-id="d2981-184">![Changing destination/source IP addresses](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Changing destination/source IP addresses")</span></span>

<span data-ttu-id="d2981-185">Ключевые моменты:</span><span class="sxs-lookup"><span data-stu-id="d2981-185">The key points are:</span></span>

  - <span data-ttu-id="d2981-186">Трафик, входящий на сервер, на котором работает пограничная служба аудио-и видеоданных, исходный IP-адрес не изменяется, но конечный IP-адрес изменяется с 131.107.155.30 на переведенный IP-адрес 10.45.16.10.</span><span class="sxs-lookup"><span data-stu-id="d2981-186">Traffic that is inbound to the server running the A/V Edge service, the source IP address does not change but the destination IP address changes from 131.107.155.30 to the translated IP address of 10.45.16.10.</span></span>

  - <span data-ttu-id="d2981-187">Трафик, исходящий с сервера, на котором запущена служба пограничного сервера аудио-и видеоданных на рабочей станции, исходный IP-адрес изменяется с общедоступного IP-адреса сервера на общедоступный IP-адрес сервера, на котором запущена служба аудио-и видеоданных.</span><span class="sxs-lookup"><span data-stu-id="d2981-187">Traffic that is outbound from the server running the A/V Edge service back to the workstation, the source IP address changes from the server’s public IP address to the public IP address of the server running the A/V Edge service.</span></span> <span data-ttu-id="d2981-188">При этом конечный IP-адрес остается общим IP-адресом рабочей станции.</span><span class="sxs-lookup"><span data-stu-id="d2981-188">The destination IP remains the workstation’s public IP address.</span></span> <span data-ttu-id="d2981-189">После того как пакет покидает первое исходящее устройство NAT, правило на устройстве NAT изменяет исходный IP-адрес сервера, на котором выполняется IP-адрес внешнего интерфейса пограничной службы аудио-и видеоданных (10.45.16.10), на общедоступный IP-адрес (131.107.155.30).</span><span class="sxs-lookup"><span data-stu-id="d2981-189">After the packet leaves the first NAT device outbound, the rule on the NAT device changes the source IP address of the server running the A/V Edge service external interface IP address (10.45.16.10) to its public IP address (131.107.155.30).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

