---
title: 'Lync Server 2013: определение требований к внешнему брандмауэру аудио-и видеоданных'
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
ms.openlocfilehash: c6f44e23cdc60251df4ea3f4071805d9367eef84
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a><span data-ttu-id="37e91-102">Определение требований к внешнему брандмауэру аудио-и видеоданных для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37e91-102">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37e91-103">_**Последнее изменение темы:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="37e91-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="37e91-p101">Аудио- и видеокоммуникации могут иметь сложную реализацию. В связи с природой протоколов для аудио и видео и способами их использования клиентами и серверами пояснение различий между клиентской и серверной версией вынесено в отдельный раздел.</span><span class="sxs-lookup"><span data-stu-id="37e91-p101">Audio/Video (A/V) communication can be a complex. Because of the nature of protocols used in A/V and how clients and servers use the protocols, a special section is warranted to explain the differences between client and server versions.</span></span>

<span data-ttu-id="37e91-106">Используйте следующую таблицу брандмауэра и портов для аудио- и видеоданных, чтобы определить требования к брандмауэру и открытым портам.</span><span class="sxs-lookup"><span data-stu-id="37e91-106">Use the following A/V Firewall and Port table to determine firewall requirements and which ports to open.</span></span> <span data-ttu-id="37e91-107">После этого изучите терминологию преобразования сетевых адресов (NAT), поскольку NAT может быть реализовано множеством разных способов.</span><span class="sxs-lookup"><span data-stu-id="37e91-107">Then, review the network address translation (NAT) terminology because NAT can be implemented in many different ways.</span></span> <span data-ttu-id="37e91-108">Подробный пример параметров порта брандмауэра приведен в статье Reference Architecture Architecture в [сценариях для доступа внешних пользователей в Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="37e91-108">For a detailed example of firewall port settings, see the reference architectures in [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a><span data-ttu-id="37e91-109">Общее использование протокола для UDP и TCP в аудио-и видеоматериалах и трафике мультимедиа</span><span class="sxs-lookup"><span data-stu-id="37e91-109">General Protocol Usage for UDP and TCP in Audio/Video and Media Traffic</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="37e91-110">Транспорт аудио-и видеоданных</span><span class="sxs-lookup"><span data-stu-id="37e91-110">Audio/Video Transport</span></span></th>
<th><span data-ttu-id="37e91-111">Применение</span><span class="sxs-lookup"><span data-stu-id="37e91-111">Usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="37e91-112">ПРОТОКОЛА</span><span class="sxs-lookup"><span data-stu-id="37e91-112">UDP</span></span></p></td>
<td><p><span data-ttu-id="37e91-113">Предпочтительный протокол транспортного уровня для аудио и видео</span><span class="sxs-lookup"><span data-stu-id="37e91-113">Preferred transport layer protocol for audio and video</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37e91-114">TCP</span><span class="sxs-lookup"><span data-stu-id="37e91-114">TCP</span></span></p></td>
<td><p><span data-ttu-id="37e91-115">Резервный протокол транспортного уровня для аудио и видео</span><span class="sxs-lookup"><span data-stu-id="37e91-115">Fallback transport layer protocol for audio and video</span></span></p>
<p><span data-ttu-id="37e91-116">Обязательный протокол транспортного уровня для общего доступа к приложениям Office Communications Server 2007 R2, Lync Server 2010 и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37e91-116">Required transport layer protocol for application sharing to Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013</span></span></p>
<p><span data-ttu-id="37e91-117">Обязательный протокол транспортного уровня для передачи файлов в Lync Server 2010 и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37e91-117">Required transport layer protocol for file transfer to Lync Server 2010 and Lync Server 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a><span data-ttu-id="37e91-118">Требования к внешним портам брандмауэра и портам для аудио- и видеоданных для доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="37e91-118">External A/V Firewall Port Requirements for External User Access</span></span>

<span data-ttu-id="37e91-119">Требования к портам брандмауэра для внешних (и внутренних) интерфейсов SIP и конференций согласованы независимо от версии клиента или версии партнера Федерации.</span><span class="sxs-lookup"><span data-stu-id="37e91-119">The firewall port requirements for external (and internal) SIP and conferencing interfaces are consistent, regardless of the version of your client or the version of the federation partner.</span></span>

<span data-ttu-id="37e91-120">Однако это не распространяется на внешний интерфейс для пограничной службы обработки аудио- и видеоданных.</span><span class="sxs-lookup"><span data-stu-id="37e91-120">The same is not true for the Audio/Video Edge external interface.</span></span> <span data-ttu-id="37e91-121">Для Федерации с Office Communications Server 2007, пограничная служба аудио-и видеоданных требует, чтобы внешние правила брандмауэра допускали трафик RTP/TCP и RTP/UDP в диапазоне портов 50 000 – 59 999 для передачи в обоих направлениях.</span><span class="sxs-lookup"><span data-stu-id="37e91-121">For federation with Office Communications Server 2007, the A/V Edge service requires that external firewall rules allow RTP/TCP and RTP/UDP traffic in the 50,000 through 59,999 port range to flow in both directions.</span></span> <span data-ttu-id="37e91-122">В приведенной выше таблице предполагается, что Lync Server 2013 является основным партнером Федерации и настроен для общения с одним из указанных типов партнеров Федерации.</span><span class="sxs-lookup"><span data-stu-id="37e91-122">The previous table assumes that Lync Server 2013 is the primary federation partner and it is being configured to communicate with one of the other federation partner types listed.</span></span>

<span data-ttu-id="37e91-123">При настройке диапазона портов для аудио и видеопортов 50000-– 999 необходимо учитывать, что диапазон портов будет содержать исходные порты для связи с партнерами Федерации.</span><span class="sxs-lookup"><span data-stu-id="37e91-123">Configuring the Audio/Video port range of 50,000-59,999 must take into account that the port range will contain the source ports for communications to federation partners.</span></span> <span data-ttu-id="37e91-124">Обратите внимание, что связь инициируется партнером Федерации.</span><span class="sxs-lookup"><span data-stu-id="37e91-124">In detail, consider that a communication is initiated from a federation partner.</span></span> <span data-ttu-id="37e91-125">Связь из портов пограничной службы аудио-и видеоданных в диапазоне 50000-– 999 будет подключаться к ожидаемому порту TCP 443 для пограничной службы передачи аудио-и видеоданных партнера.</span><span class="sxs-lookup"><span data-stu-id="37e91-125">The communication from the A/V Edge service ports in the 50,000-59,999 range will connect to the expected port TCP 443 of the partner’s A/V Edge service.</span></span> <span data-ttu-id="37e91-126">И наоборот, входящий трафик на порт пограничной службы аудио-и видеосвязи TCP 443 будет иметь исходный порт в диапазоне 50000-– 999.</span><span class="sxs-lookup"><span data-stu-id="37e91-126">Conversely, inbound traffic to your A/V Edge service port TCP 443 will have a source port in the range of 50,000-59,999.</span></span>

<span data-ttu-id="37e91-127">Для разных брандмауэров и политик для администрирования брандмауэра может потребоваться настройка только правил назначения, а также может требоваться Настройка исходного и конечного адресов.</span><span class="sxs-lookup"><span data-stu-id="37e91-127">Different firewalls and policies for firewall administration may require only destination rules to be configured, or they may require both source and destination to be configured.</span></span> <span data-ttu-id="37e91-128">Если ваши требования относятся только к портам назначения, требования к аудио-и видеосигналам:</span><span class="sxs-lookup"><span data-stu-id="37e91-128">If your requirements are for destination ports only, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="37e91-129">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="37e91-129">Source IP</span></span></th>
<th><span data-ttu-id="37e91-130">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="37e91-130">Destination IP</span></span></th>
<th><span data-ttu-id="37e91-131">Порт назначения</span><span class="sxs-lookup"><span data-stu-id="37e91-131">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="37e91-132">Интерфейс пограничного сервера аудио-и видеоданных</span><span class="sxs-lookup"><span data-stu-id="37e91-132">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="37e91-133">Любые</span><span class="sxs-lookup"><span data-stu-id="37e91-133">Any</span></span></p></td>
<td><p><span data-ttu-id="37e91-134">TCP 443</span><span class="sxs-lookup"><span data-stu-id="37e91-134">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37e91-135">Интерфейс пограничного сервера аудио-и видеоданных</span><span class="sxs-lookup"><span data-stu-id="37e91-135">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="37e91-136">Любые</span><span class="sxs-lookup"><span data-stu-id="37e91-136">Any</span></span></p></td>
<td><p><span data-ttu-id="37e91-137">UDP 3478;</span><span class="sxs-lookup"><span data-stu-id="37e91-137">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37e91-138">Любые</span><span class="sxs-lookup"><span data-stu-id="37e91-138">Any</span></span></p></td>
<td><p><span data-ttu-id="37e91-139">Интерфейс пограничного сервера аудио-и видеоданных</span><span class="sxs-lookup"><span data-stu-id="37e91-139">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="37e91-140">TCP 443</span><span class="sxs-lookup"><span data-stu-id="37e91-140">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37e91-141">Любые</span><span class="sxs-lookup"><span data-stu-id="37e91-141">Any</span></span></p></td>
<td><p><span data-ttu-id="37e91-142">Интерфейс пограничного сервера аудио-и видеоданных</span><span class="sxs-lookup"><span data-stu-id="37e91-142">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="37e91-143">UDP 3478;</span><span class="sxs-lookup"><span data-stu-id="37e91-143">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="37e91-144">Если для политик требуются определения правил брандмауэра для входящих и исходящих подключений, необходимы следующие требования к аудио-и видеосигналам.</span><span class="sxs-lookup"><span data-stu-id="37e91-144">If your policies require both inbound and outbound firewall rule definitions, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="37e91-145">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="37e91-145">Source IP</span></span></th>
<th><span data-ttu-id="37e91-146">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="37e91-146">Destination IP</span></span></th>
<th><span data-ttu-id="37e91-147">Порт источника</span><span class="sxs-lookup"><span data-stu-id="37e91-147">Source Port</span></span></th>
<th><span data-ttu-id="37e91-148">Порт назначения</span><span class="sxs-lookup"><span data-stu-id="37e91-148">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="37e91-149">Интерфейс пограничного сервера аудио-и видеоданных</span><span class="sxs-lookup"><span data-stu-id="37e91-149">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="37e91-150">Любые</span><span class="sxs-lookup"><span data-stu-id="37e91-150">Any</span></span></p></td>
<td><p><span data-ttu-id="37e91-151">TCP 50000 — – 999</span><span class="sxs-lookup"><span data-stu-id="37e91-151">TCP 50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="37e91-152">TCP 443</span><span class="sxs-lookup"><span data-stu-id="37e91-152">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37e91-153">Интерфейс пограничного сервера аудио-и видеоданных</span><span class="sxs-lookup"><span data-stu-id="37e91-153">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="37e91-154">Любые</span><span class="sxs-lookup"><span data-stu-id="37e91-154">Any</span></span></p></td>
<td><p><span data-ttu-id="37e91-155">UDP 3478;</span><span class="sxs-lookup"><span data-stu-id="37e91-155">UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="37e91-156">UDP 3478;</span><span class="sxs-lookup"><span data-stu-id="37e91-156">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37e91-157">Любые</span><span class="sxs-lookup"><span data-stu-id="37e91-157">Any</span></span></p></td>
<td><p><span data-ttu-id="37e91-158">Интерфейс пограничного сервера аудио-и видеоданных</span><span class="sxs-lookup"><span data-stu-id="37e91-158">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="37e91-159">Любые</span><span class="sxs-lookup"><span data-stu-id="37e91-159">Any</span></span></p></td>
<td><p><span data-ttu-id="37e91-160">TCP 443</span><span class="sxs-lookup"><span data-stu-id="37e91-160">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37e91-161">Любые</span><span class="sxs-lookup"><span data-stu-id="37e91-161">Any</span></span></p></td>
<td><p><span data-ttu-id="37e91-162">Интерфейс пограничного сервера аудио-и видеоданных</span><span class="sxs-lookup"><span data-stu-id="37e91-162">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="37e91-163">Любые</span><span class="sxs-lookup"><span data-stu-id="37e91-163">Any</span></span></p></td>
<td><p><span data-ttu-id="37e91-164">UDP 3478;</span><span class="sxs-lookup"><span data-stu-id="37e91-164">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="37e91-165">Microsoft Office Communications Server 2007 требует немного другой настройки.</span><span class="sxs-lookup"><span data-stu-id="37e91-165">Microsoft Office Communications Server 2007 requires a slightly different configuration.</span></span> <span data-ttu-id="37e91-166">Диапазон портов TCP и UDP (50000-– 999) должен быть открытым для входящих и исходящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="37e91-166">The TCP and UDP port range of 50,000-59,999 must be open inbound and outbound.</span></span> <span data-ttu-id="37e91-167">Это требование относится только к Office Communicator 2007.</span><span class="sxs-lookup"><span data-stu-id="37e91-167">This requirement is only for Office Communicator 2007.</span></span> <span data-ttu-id="37e91-168">Office Communications Server 2007 R2, Lync Server 2010 и Lync Server 2013 требуется только TCP Range 50000-– 999 Open Outbound.</span><span class="sxs-lookup"><span data-stu-id="37e91-168">Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013 only require TCP range 50,000-59,999 open outbound.</span></span>



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a><span data-ttu-id="37e91-169">Требования к NAT для пограничной службы</span><span class="sxs-lookup"><span data-stu-id="37e91-169">NAT requirements for the Edge service</span></span>

<span data-ttu-id="37e91-170">Если вы решили настроить частные IP-адреса без маршрутизации для пограничной службы, применяются следующие требования к NAT:</span><span class="sxs-lookup"><span data-stu-id="37e91-170">The following NAT requirements apply if you choose to configure non-routable private IP addresses for the Edge service:</span></span>

  - <span data-ttu-id="37e91-171">Преобразование сетевых адресов (NAT) можно использовать только с балансировкой нагрузки на DNS.</span><span class="sxs-lookup"><span data-stu-id="37e91-171">NAT can only be used with DNS load-balancing.</span></span> <span data-ttu-id="37e91-172">NAT не поддерживается в пограничной топологии аппаратной балансировки нагрузки (HLB).</span><span class="sxs-lookup"><span data-stu-id="37e91-172">NAT is not supported with a hardware load balancing (HLB) Edge topology.</span></span>

  - <span data-ttu-id="37e91-173">Преобразование сетевых адресов (NAT) можно использовать только для внешнего интерфейса пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="37e91-173">NAT can only be used on the external Edge interface.</span></span> <span data-ttu-id="37e91-174">NAT не поддерживается во внутреннем интерфейсе пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="37e91-174">NAT is not supported on the internal Edge interface.</span></span>

  - <span data-ttu-id="37e91-175">Для входящего и исходящего трафика NAT должен быть симметричным.</span><span class="sxs-lookup"><span data-stu-id="37e91-175">NAT must be symmetric for incoming and outgoing traffic.</span></span>
    
  - <span data-ttu-id="37e91-176">Для трафика из Интернета NAT необходимо изменить конечный IP-адрес с общедоступного IP-адреса, поддерживающего NAT, на внешний IP-адрес службы пограничного сервера аудио-и видеоданных.</span><span class="sxs-lookup"><span data-stu-id="37e91-176">For traffic from the Internet, NAT must change the destination IP address from the NAT-enabled public IP address of the A/V Edge service to its external IP address.</span></span> <span data-ttu-id="37e91-177">Исходный IP-адрес должен остаться без изменений, чтобы служба пограничного сервера аудио-и видеоданных могла найти оптимальный путь к носителю.</span><span class="sxs-lookup"><span data-stu-id="37e91-177">The source IP address must remain intact, so that the A/V Edge service can find the optimal media path.</span></span>
  
  <span data-ttu-id="37e91-178">Например, во входящем расположении на рисунке ниже общедоступный IP-адрес 131.107.155.30 был изменен на внешний (частный) IP-адрес 10.45.16.10.</span><span class="sxs-lookup"><span data-stu-id="37e91-178">For example, in the inbound direction in the figure below, the public IP address 131.107.155.30 was changed to the external (private) IP address 10.45.16.10.</span></span> <span data-ttu-id="37e91-179">Исходный IP-адрес остается неизменным.</span><span class="sxs-lookup"><span data-stu-id="37e91-179">The source IP address remained unchanged.</span></span>
  
  - <span data-ttu-id="37e91-180">Для трафика из пограничной службы аудио-и видеоданных в Интернете необходимо изменить исходный IP-адрес с внешнего IP-адреса службы пограничного сервера аудио-и видеоданных на общедоступный IP-адрес, поддерживающий NAT.</span><span class="sxs-lookup"><span data-stu-id="37e91-180">For traffic from the A/V Edge service to the Internet, NAT must change the source IP address from the external IP address of the A/V Edge service to the NAT-enabled public IP address.</span></span>

<span data-ttu-id="37e91-181">Например, в исходящем направлении на рисунке ниже внешний IP-адрес (частный) 10.45.16.10 был изменен на общедоступный IP-адрес 131.107.155.30.</span><span class="sxs-lookup"><span data-stu-id="37e91-181">For example, in the outbound direction in the figure below, the external (private) IP address 10.45.16.10 was changed to the public IP address 131.107.155.30.</span></span>

<span data-ttu-id="37e91-182">**На приведенном ниже рисунке показано, как NAT изменяет конечный IP-адрес для входящего трафика и исходный IP-адрес для исходящего трафика.**</span><span class="sxs-lookup"><span data-stu-id="37e91-182">**The figure below shows how NAT changes the destination IP address for inbound traffic and the source IP Address for outbound traffic.**</span></span>

<span data-ttu-id="37e91-183">![Изменение IP-адресов назначения и источника](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Изменение IP-адресов назначения и источника")</span><span class="sxs-lookup"><span data-stu-id="37e91-183">![Changing destination/source IP addresses](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Changing destination/source IP addresses")</span></span>

<span data-ttu-id="37e91-184">Ключевые моменты:</span><span class="sxs-lookup"><span data-stu-id="37e91-184">The key points are:</span></span>

  - <span data-ttu-id="37e91-185">Трафик, входящий на сервер, на котором работает пограничная служба аудио-и видеоданных, исходный IP-адрес не изменяется, но конечный IP-адрес изменяется с 131.107.155.30 на переведенный IP-адрес 10.45.16.10.</span><span class="sxs-lookup"><span data-stu-id="37e91-185">Traffic that is inbound to the server running the A/V Edge service, the source IP address does not change but the destination IP address changes from 131.107.155.30 to the translated IP address of 10.45.16.10.</span></span>

  - <span data-ttu-id="37e91-186">Трафик, исходящий с сервера, на котором запущена служба пограничного сервера аудио-и видеоданных на рабочей станции, исходный IP-адрес изменяется с общедоступного IP-адреса сервера на общедоступный IP-адрес сервера, на котором запущена служба аудио-и видеоданных.</span><span class="sxs-lookup"><span data-stu-id="37e91-186">Traffic that is outbound from the server running the A/V Edge service back to the workstation, the source IP address changes from the server’s public IP address to the public IP address of the server running the A/V Edge service.</span></span> <span data-ttu-id="37e91-187">При этом конечный IP-адрес остается общим IP-адресом рабочей станции.</span><span class="sxs-lookup"><span data-stu-id="37e91-187">The destination IP remains the workstation’s public IP address.</span></span> <span data-ttu-id="37e91-188">После того как пакет покидает первое исходящее устройство NAT, правило на устройстве NAT изменяет исходный IP-адрес сервера, на котором выполняется IP-адрес внешнего интерфейса пограничной службы аудио-и видеоданных (10.45.16.10), на общедоступный IP-адрес (131.107.155.30).</span><span class="sxs-lookup"><span data-stu-id="37e91-188">After the packet leaves the first NAT device outbound, the rule on the NAT device changes the source IP address of the server running the A/V Edge service external interface IP address (10.45.16.10) to its public IP address (131.107.155.30).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

