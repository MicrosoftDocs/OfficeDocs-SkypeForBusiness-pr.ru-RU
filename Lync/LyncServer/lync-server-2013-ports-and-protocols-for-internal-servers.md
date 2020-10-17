---
title: 'Lync Server 2013: порты и протоколы для внутренних серверов'
description: 'Lync Server 2013: порты и протоколы для внутренних серверов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Ports and protocols for internal servers
ms:assetid: c94063f1-e802-4a61-be90-022fc185335e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398833(v=OCS.15)
ms:contentKeyID: 48185402
ms.date: 04/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7d8f12c78c5dec5caacaeb1156f4d228b7cd591
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566364"
---
# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="11206-103">Порты и протоколы для внутренних серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11206-103">Ports and protocols for internal servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11206-104">_**Последнее изменение темы:** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="11206-104">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="11206-105">В этом разделе приведены общие сведения о портах и протоколах, используемых серверами, подсистемами балансировки нагрузки и клиентами в развертывании Lync Server.</span><span class="sxs-lookup"><span data-stu-id="11206-105">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="11206-106">Клиенты Lync и Communicator, участвующие в одном обмене данными, часто называют одноранговыми узлами.</span><span class="sxs-lookup"><span data-stu-id="11206-106">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="11206-107">С технической точки зрения два клиента взаимодействуют в одном сеансе, с помощью модуля управления мгновенными сообщениями MultiPoint (ИММКУ) в центре.</span><span class="sxs-lookup"><span data-stu-id="11206-107">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="11206-108">ИММКУ — это компонент сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="11206-108">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="11206-109">Размещение ИММКУ в требуемом рабочем канале связи позволяет записывать сведения о вызовах и другие функции, которые обеспечивает сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="11206-109">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="11206-110">Обмен данными осуществляется от динамического исходного порта на клиенте к порту TLS/TCP/5061 (при условии использования рекомендуемой безопасности транспортного уровня).</span><span class="sxs-lookup"><span data-stu-id="11206-110">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="11206-111">Одноранговая связь (а также поддержка обмена мгновенными сообщениями) возможна только в том случае, если Lync Server и ИММКУ активны и доступны.</span><span class="sxs-lookup"><span data-stu-id="11206-111">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="11206-112">Сведения о портах и протоколе</span><span class="sxs-lookup"><span data-stu-id="11206-112">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="11206-113">Перед запуском служб Lync Server на сервере необходимо запустить брандмауэр Windows, так как в этом случае Lync Server открывает необходимые порты в брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="11206-113">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="11206-114">Подробные сведения о конфигурации брандмауэра для пограничных компонентов приведены [в статье Определение требований к портам внешнего аудио-и видеоподключения для Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11206-114">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="11206-115">В следующей таблице приводится список портов, которые должны быть открыты для каждой роли внутреннего сервера.</span><span class="sxs-lookup"><span data-stu-id="11206-115">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="11206-116">Необходимые порты сервера (по ролям сервера)</span><span class="sxs-lookup"><span data-stu-id="11206-116">Required Server Ports (by Server Role)</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11206-117">Роль сервера</span><span class="sxs-lookup"><span data-stu-id="11206-117">Server role</span></span></th>
<th><span data-ttu-id="11206-118">Имя службы</span><span class="sxs-lookup"><span data-stu-id="11206-118">Service name</span></span></th>
<th><span data-ttu-id="11206-119">Порт</span><span class="sxs-lookup"><span data-stu-id="11206-119">Port</span></span></th>
<th><span data-ttu-id="11206-120">Протокол</span><span class="sxs-lookup"><span data-stu-id="11206-120">Protocol</span></span></th>
<th><span data-ttu-id="11206-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="11206-121">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11206-122">Все серверы</span><span class="sxs-lookup"><span data-stu-id="11206-122">All Servers</span></span></p></td>
<td><p><span data-ttu-id="11206-123">Браузер SQL</span><span class="sxs-lookup"><span data-stu-id="11206-123">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="11206-124">1434</span><span class="sxs-lookup"><span data-stu-id="11206-124">1434</span></span></p></td>
<td><p><span data-ttu-id="11206-125">ПРОТОКОЛА</span><span class="sxs-lookup"><span data-stu-id="11206-125">UDP</span></span></p></td>
<td><p><span data-ttu-id="11206-126">Браузер SQL для локальной реплицированной копии базы данных центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="11206-126">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-127">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-127">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="11206-128">Служба Front-End Lync Server</span><span class="sxs-lookup"><span data-stu-id="11206-128">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="11206-129">5060</span><span class="sxs-lookup"><span data-stu-id="11206-129">5060</span></span></p></td>
<td><p><span data-ttu-id="11206-130">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-130">TCP</span></span></p></td>
<td><p><span data-ttu-id="11206-131">При необходимости используется для статических маршрутов к доверенным службам серверами Standard Edition и серверами переднего плана, например серверами удаленного управления звонками.</span><span class="sxs-lookup"><span data-stu-id="11206-131">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-132">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-132">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="11206-133">Служба Front-End Lync Server</span><span class="sxs-lookup"><span data-stu-id="11206-133">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="11206-134">5061</span><span class="sxs-lookup"><span data-stu-id="11206-134">5061</span></span></p></td>
<td><p><span data-ttu-id="11206-135">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="11206-135">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="11206-p102">Используется серверами Standard Edition и серверами переднего плана для всех внутренних SIP-соединений между серверами (MTLS), для SIP-соединений между сервером и клиентом (TLS) и для SIP-соединений между серверами переднего плана и серверами-посредниками (MTLS). Также используется для соединений с сервером мониторинга.</span><span class="sxs-lookup"><span data-stu-id="11206-p102">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS). Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-138">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-138">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="11206-139">Служба Front-End Lync Server</span><span class="sxs-lookup"><span data-stu-id="11206-139">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="11206-140">444</span><span class="sxs-lookup"><span data-stu-id="11206-140">444</span></span></p></td>
<td><p><span data-ttu-id="11206-141">HTTPS</span><span class="sxs-lookup"><span data-stu-id="11206-141">HTTPS</span></span></p>
<p><span data-ttu-id="11206-142">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-142">TCP</span></span></p></td>
<td><p><span data-ttu-id="11206-143">Используется для взаимодействия по протоколу HTTPS между фокусом (компонентом Lync Server, который управляет состоянием конференции) и отдельными серверами.</span><span class="sxs-lookup"><span data-stu-id="11206-143">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="11206-144">Этот порт также используется для связи по протоколу TCP между устройствами для обеспечения связи в филиалах и серверами переднего плана.</span><span class="sxs-lookup"><span data-stu-id="11206-144">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-145">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-145">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="11206-146">Служба Front-End Lync Server</span><span class="sxs-lookup"><span data-stu-id="11206-146">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="11206-147">135</span><span class="sxs-lookup"><span data-stu-id="11206-147">135</span></span></p></td>
<td><p><span data-ttu-id="11206-148">DCOM и удаленный вызов процедур (RPC)</span><span class="sxs-lookup"><span data-stu-id="11206-148">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="11206-149">Используется для операций на базе DCOM, таких как перемещение пользователей, синхронизация репликаторов пользовательских данных и адресных книг.</span><span class="sxs-lookup"><span data-stu-id="11206-149">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-150">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-150">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="11206-151">Служба конференц-связи Lync Server для обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="11206-151">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="11206-152">5062</span><span class="sxs-lookup"><span data-stu-id="11206-152">5062</span></span></p></td>
<td><p><span data-ttu-id="11206-153">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-153">TCP</span></span></p></td>
<td><p><span data-ttu-id="11206-154">Используется для входящих SIP-запросов в конференц-связи с использованием обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="11206-154">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-155">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-155">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="11206-156">Служба веб-конференций Lync Server</span><span class="sxs-lookup"><span data-stu-id="11206-156">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="11206-157">8057</span><span class="sxs-lookup"><span data-stu-id="11206-157">8057</span></span></p></td>
<td><p><span data-ttu-id="11206-158">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="11206-158">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="11206-159">Используется для прослушивания подключений по протоколу PSOM от клиента.</span><span class="sxs-lookup"><span data-stu-id="11206-159">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-160">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-160">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="11206-161">Служба совместимости веб-конференций Lync Server</span><span class="sxs-lookup"><span data-stu-id="11206-161">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="11206-162">8058</span><span class="sxs-lookup"><span data-stu-id="11206-162">8058</span></span></p></td>
<td><p><span data-ttu-id="11206-163">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="11206-163">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="11206-164">Используется для прослушивания подключений к постоянным общим объектным моделям (PSOM) из клиента Live Meeting и предыдущих версий Lync Server.</span><span class="sxs-lookup"><span data-stu-id="11206-164">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-165">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-165">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="11206-166">Служба аудио-и видеоконференций Lync Server</span><span class="sxs-lookup"><span data-stu-id="11206-166">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="11206-167">5063</span><span class="sxs-lookup"><span data-stu-id="11206-167">5063</span></span></p></td>
<td><p><span data-ttu-id="11206-168">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-168">TCP</span></span></p></td>
<td><p><span data-ttu-id="11206-169">Используется для входящих SIP-запросов на аудио- и видеоконференции.</span><span class="sxs-lookup"><span data-stu-id="11206-169">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-170">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-170">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="11206-171">Служба аудио-и видеоконференций Lync Server</span><span class="sxs-lookup"><span data-stu-id="11206-171">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="11206-172">57501-65535</span><span class="sxs-lookup"><span data-stu-id="11206-172">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="11206-173">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="11206-173">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="11206-174">Диапазон портов, используемых для видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="11206-174">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-175">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="11206-176">Служба веб-совместимости Lync Server</span><span class="sxs-lookup"><span data-stu-id="11206-176">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="11206-177">80</span><span class="sxs-lookup"><span data-stu-id="11206-177">80</span></span></p></td>
<td><p><span data-ttu-id="11206-178">HTTP</span><span class="sxs-lookup"><span data-stu-id="11206-178">HTTP</span></span></p></td>
<td><p><span data-ttu-id="11206-179">Используется для подключений от серверов переднего плана к полным доменным именам в веб-ферме (URL-адреса используются по веб-компонентам IIS), когда не используется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="11206-179">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-180">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-180">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="11206-181">Служба веб-совместимости Lync Server</span><span class="sxs-lookup"><span data-stu-id="11206-181">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="11206-182">443</span><span class="sxs-lookup"><span data-stu-id="11206-182">443</span></span></p></td>
<td><p><span data-ttu-id="11206-183">HTTPS</span><span class="sxs-lookup"><span data-stu-id="11206-183">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="11206-184">Используется для подключений от серверов переднего плана к полным доменным именам в веб-ферме (URL-адреса используются по веб-компонентам IIS).</span><span class="sxs-lookup"><span data-stu-id="11206-184">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-185">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-185">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="11206-186">Служба веб-совместимости Lync Server</span><span class="sxs-lookup"><span data-stu-id="11206-186">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="11206-187">8080</span><span class="sxs-lookup"><span data-stu-id="11206-187">8080</span></span></p></td>
<td><p><span data-ttu-id="11206-188">TCP и HTTP</span><span class="sxs-lookup"><span data-stu-id="11206-188">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="11206-189">Используется веб-компонентами для внешнего доступа.</span><span class="sxs-lookup"><span data-stu-id="11206-189">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-190">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-190">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="11206-191">Компонент веб-сервера</span><span class="sxs-lookup"><span data-stu-id="11206-191">Web server component</span></span></p></td>
<td><p><span data-ttu-id="11206-192">4443</span><span class="sxs-lookup"><span data-stu-id="11206-192">4443</span></span></p></td>
<td><p><span data-ttu-id="11206-193">HTTPS</span><span class="sxs-lookup"><span data-stu-id="11206-193">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="11206-194">Подключения HTTPS (от обратного прокси-сервера) и подключения между пулами HTTPS для входа в службу автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="11206-194">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-195">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-195">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="11206-196">Компонент веб-сервера</span><span class="sxs-lookup"><span data-stu-id="11206-196">Web server component</span></span></p></td>
<td><p><span data-ttu-id="11206-197">8060</span><span class="sxs-lookup"><span data-stu-id="11206-197">8060</span></span></p></td>
<td><p><span data-ttu-id="11206-198">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="11206-198">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-199">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-199">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="11206-200">Компонент веб-сервера</span><span class="sxs-lookup"><span data-stu-id="11206-200">Web server component</span></span></p></td>
<td><p><span data-ttu-id="11206-201">8061</span><span class="sxs-lookup"><span data-stu-id="11206-201">8061</span></span></p></td>
<td><p><span data-ttu-id="11206-202">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="11206-202">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-203">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-203">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="11206-204">Компонент служб Mobility Services</span><span class="sxs-lookup"><span data-stu-id="11206-204">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="11206-205">5086</span><span class="sxs-lookup"><span data-stu-id="11206-205">5086</span></span></p></td>
<td><p><span data-ttu-id="11206-206">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="11206-206">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="11206-207">SIP-порт, используемый внутренними процессами служб Mobility Services</span><span class="sxs-lookup"><span data-stu-id="11206-207">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-208">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-208">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="11206-209">Компонент служб Mobility Services</span><span class="sxs-lookup"><span data-stu-id="11206-209">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="11206-210">5087</span><span class="sxs-lookup"><span data-stu-id="11206-210">5087</span></span></p></td>
<td><p><span data-ttu-id="11206-211">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="11206-211">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="11206-212">SIP-порт, используемый внутренними процессами служб Mobility Services</span><span class="sxs-lookup"><span data-stu-id="11206-212">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-213">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-213">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="11206-214">Компонент служб Mobility Services</span><span class="sxs-lookup"><span data-stu-id="11206-214">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="11206-215">443</span><span class="sxs-lookup"><span data-stu-id="11206-215">443</span></span></p></td>
<td><p><span data-ttu-id="11206-216">HTTPS</span><span class="sxs-lookup"><span data-stu-id="11206-216">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-217">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-217">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="11206-218">Служба помощника по конференц-связи Lync Server (Конференц-связь с телефонным подключением)</span><span class="sxs-lookup"><span data-stu-id="11206-218">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="11206-219">5064</span><span class="sxs-lookup"><span data-stu-id="11206-219">5064</span></span></p></td>
<td><p><span data-ttu-id="11206-220">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-220">TCP</span></span></p></td>
<td><p><span data-ttu-id="11206-221">Используется для входящих SIP-запросов для конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="11206-221">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-222">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-222">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="11206-223">Служба помощника по конференц-связи Lync Server (Конференц-связь с телефонным подключением)</span><span class="sxs-lookup"><span data-stu-id="11206-223">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="11206-224">5072</span><span class="sxs-lookup"><span data-stu-id="11206-224">5072</span></span></p></td>
<td><p><span data-ttu-id="11206-225">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-225">TCP</span></span></p></td>
<td><p><span data-ttu-id="11206-226">Используется для входящих SIP-запросов для помощника (конференц-связи с телефонным подключением).</span><span class="sxs-lookup"><span data-stu-id="11206-226">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-227">Серверы переднего плана, на которых также работает соотнесенный сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="11206-227">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="11206-228">Служба-посредник по Lync Server</span><span class="sxs-lookup"><span data-stu-id="11206-228">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="11206-229">5070</span><span class="sxs-lookup"><span data-stu-id="11206-229">5070</span></span></p></td>
<td><p><span data-ttu-id="11206-230">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-230">TCP</span></span></p></td>
<td><p><span data-ttu-id="11206-231">Используется сервером-посредником для входящих запросов от сервера переднего плана к серверу посреднику.</span><span class="sxs-lookup"><span data-stu-id="11206-231">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-232">Серверы переднего плана, на которых также работает соотнесенный сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="11206-232">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="11206-233">Служба-посредник по Lync Server</span><span class="sxs-lookup"><span data-stu-id="11206-233">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="11206-234">5067</span><span class="sxs-lookup"><span data-stu-id="11206-234">5067</span></span></p></td>
<td><p><span data-ttu-id="11206-235">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="11206-235">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="11206-236">Используется для входящих SIP-запросов от шлюза ТСОП к серверу-посреднику.</span><span class="sxs-lookup"><span data-stu-id="11206-236">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-237">Серверы переднего плана, на которых также работает соотнесенный сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="11206-237">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="11206-238">Служба-посредник по Lync Server</span><span class="sxs-lookup"><span data-stu-id="11206-238">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="11206-239">5068</span><span class="sxs-lookup"><span data-stu-id="11206-239">5068</span></span></p></td>
<td><p><span data-ttu-id="11206-240">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-240">TCP</span></span></p></td>
<td><p><span data-ttu-id="11206-241">Используется для входящих SIP-запросов от шлюза ТСОП к серверу-посреднику.</span><span class="sxs-lookup"><span data-stu-id="11206-241">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-242">Серверы переднего плана, на которых также работает соотнесенный сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="11206-242">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="11206-243">Служба-посредник по Lync Server</span><span class="sxs-lookup"><span data-stu-id="11206-243">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="11206-244">5081</span><span class="sxs-lookup"><span data-stu-id="11206-244">5081</span></span></p></td>
<td><p><span data-ttu-id="11206-245">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-245">TCP</span></span></p></td>
<td><p><span data-ttu-id="11206-246">Используется для исходящих SIP-запросов от сервера-посредника к шлюзу ТСОП.</span><span class="sxs-lookup"><span data-stu-id="11206-246">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-247">Серверы переднего плана, на которых также работает соотнесенный сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="11206-247">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="11206-248">Служба-посредник по Lync Server</span><span class="sxs-lookup"><span data-stu-id="11206-248">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="11206-249">5082</span><span class="sxs-lookup"><span data-stu-id="11206-249">5082</span></span></p></td>
<td><p><span data-ttu-id="11206-250">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="11206-250">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="11206-251">Используется для исходящих SIP-запросов от сервера-посредника к шлюзу ТСОП.</span><span class="sxs-lookup"><span data-stu-id="11206-251">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-252">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-252">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="11206-253">Служба общего доступа к приложениям Lync Server</span><span class="sxs-lookup"><span data-stu-id="11206-253">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="11206-254">5065</span><span class="sxs-lookup"><span data-stu-id="11206-254">5065</span></span></p></td>
<td><p><span data-ttu-id="11206-255">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-255">TCP</span></span></p></td>
<td><p><span data-ttu-id="11206-256">Используется для входящих SIP-запросов на прослушивание для общего доступа к приложению.</span><span class="sxs-lookup"><span data-stu-id="11206-256">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-257">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-257">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="11206-258">Служба общего доступа к приложениям Lync Server</span><span class="sxs-lookup"><span data-stu-id="11206-258">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="11206-259">49152-65535</span><span class="sxs-lookup"><span data-stu-id="11206-259">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="11206-260">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-260">TCP</span></span></p></td>
<td><p><span data-ttu-id="11206-261">Диапазон портов, используемых для общего доступа к приложению.</span><span class="sxs-lookup"><span data-stu-id="11206-261">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-262">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-262">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="11206-263">Служба объявлений Lync Server для конференц-связи</span><span class="sxs-lookup"><span data-stu-id="11206-263">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="11206-264">5073</span><span class="sxs-lookup"><span data-stu-id="11206-264">5073</span></span></p></td>
<td><p><span data-ttu-id="11206-265">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-265">TCP</span></span></p></td>
<td><p><span data-ttu-id="11206-266">Используется для входящих SIP-запросов для службы оповещений конференц-связи Lync Server (то есть для конференц-связи с телефонным подключением).</span><span class="sxs-lookup"><span data-stu-id="11206-266">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-267">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-267">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="11206-268">Служба парковки вызовов Lync Server</span><span class="sxs-lookup"><span data-stu-id="11206-268">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="11206-269">5075</span><span class="sxs-lookup"><span data-stu-id="11206-269">5075</span></span></p></td>
<td><p><span data-ttu-id="11206-270">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-270">TCP</span></span></p></td>
<td><p><span data-ttu-id="11206-271">Используется для входящих SIP-запросов для приложения приостановки звонков.</span><span class="sxs-lookup"><span data-stu-id="11206-271">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-272">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-272">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="11206-273">Служба проверки аудиоустройств Lync Server</span><span class="sxs-lookup"><span data-stu-id="11206-273">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="11206-274">5076</span><span class="sxs-lookup"><span data-stu-id="11206-274">5076</span></span></p></td>
<td><p><span data-ttu-id="11206-275">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-275">TCP</span></span></p></td>
<td><p><span data-ttu-id="11206-276">Используется для входящих SIP-запросов для службы проверки аудиосвязи.</span><span class="sxs-lookup"><span data-stu-id="11206-276">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-277">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-277">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="11206-278">Не применимо</span><span class="sxs-lookup"><span data-stu-id="11206-278">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="11206-279">5066</span><span class="sxs-lookup"><span data-stu-id="11206-279">5066</span></span></p></td>
<td><p><span data-ttu-id="11206-280">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-280">TCP</span></span></p></td>
<td><p><span data-ttu-id="11206-281">Используется для исходящего трафика в шлюзе службы Enhanced 9-1-1 (E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="11206-281">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-282">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-282">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="11206-283">Служба группы ответа Lync Server</span><span class="sxs-lookup"><span data-stu-id="11206-283">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="11206-284">5071</span><span class="sxs-lookup"><span data-stu-id="11206-284">5071</span></span></p></td>
<td><p><span data-ttu-id="11206-285">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-285">TCP</span></span></p></td>
<td><p><span data-ttu-id="11206-286">Используется для входящих SIP-запросов для приложения группы ответа.</span><span class="sxs-lookup"><span data-stu-id="11206-286">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-287">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-287">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="11206-288">Служба группы ответа Lync Server</span><span class="sxs-lookup"><span data-stu-id="11206-288">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="11206-289">8404</span><span class="sxs-lookup"><span data-stu-id="11206-289">8404</span></span></p></td>
<td><p><span data-ttu-id="11206-290">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="11206-290">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="11206-291">Используется для входящих SIP-запросов для приложения группы ответа.</span><span class="sxs-lookup"><span data-stu-id="11206-291">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-292">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-292">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="11206-293">Служба политики пропускной способности Lync Server</span><span class="sxs-lookup"><span data-stu-id="11206-293">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="11206-294">5080</span><span class="sxs-lookup"><span data-stu-id="11206-294">5080</span></span></p></td>
<td><p><span data-ttu-id="11206-295">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-295">TCP</span></span></p></td>
<td><p><span data-ttu-id="11206-296">Используется для контроля допуска звонков, осуществляемого службой политики пропускной способности в отношении пограничного аудио-/видео-трафика @@TURN.</span><span class="sxs-lookup"><span data-stu-id="11206-296">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-297">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-297">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="11206-298">Служба политики пропускной способности Lync Server</span><span class="sxs-lookup"><span data-stu-id="11206-298">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="11206-299">448</span><span class="sxs-lookup"><span data-stu-id="11206-299">448</span></span></p></td>
<td><p><span data-ttu-id="11206-300">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-300">TCP</span></span></p></td>
<td><p><span data-ttu-id="11206-301">Используется для контроля допуска звонков службой политики пропускной способности Lync Server.</span><span class="sxs-lookup"><span data-stu-id="11206-301">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-302">Серверы переднего плана, на которых размещается центральное хранилище управления</span><span class="sxs-lookup"><span data-stu-id="11206-302">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="11206-303">Служба агента главного репликатора Lync Server</span><span class="sxs-lookup"><span data-stu-id="11206-303">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="11206-304">445</span><span class="sxs-lookup"><span data-stu-id="11206-304">445</span></span></p></td>
<td><p><span data-ttu-id="11206-305">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-305">TCP</span></span></p></td>
<td><p><span data-ttu-id="11206-306">Используется для принудительной передачи данных конфигурации из центрального хранилища управления на серверы, на которых работает Lync Server.</span><span class="sxs-lookup"><span data-stu-id="11206-306">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-307">Все серверы</span><span class="sxs-lookup"><span data-stu-id="11206-307">All Servers</span></span></p></td>
<td><p><span data-ttu-id="11206-308">Браузер SQL</span><span class="sxs-lookup"><span data-stu-id="11206-308">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="11206-309">1434</span><span class="sxs-lookup"><span data-stu-id="11206-309">1434</span></span></p></td>
<td><p><span data-ttu-id="11206-310">ПРОТОКОЛА</span><span class="sxs-lookup"><span data-stu-id="11206-310">UDP</span></span></p></td>
<td><p><span data-ttu-id="11206-311">Браузер SQL для локальной реплицированной копии данных центрального хранилища управления в локальном экземпляре SQL Server</span><span class="sxs-lookup"><span data-stu-id="11206-311">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-312">Все внутренние серверы</span><span class="sxs-lookup"><span data-stu-id="11206-312">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="11206-313">Разное</span><span class="sxs-lookup"><span data-stu-id="11206-313">Various</span></span></p></td>
<td><p><span data-ttu-id="11206-314">49152-57500</span><span class="sxs-lookup"><span data-stu-id="11206-314">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="11206-315">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="11206-315">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="11206-316">Диапазон портов, используемых для аудиоконференций на всех внутренних серверах.</span><span class="sxs-lookup"><span data-stu-id="11206-316">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="11206-317">Используется всеми серверами, которые завершают аудио: серверы переднего плана (служба помощника по конференц-связи Lync Server, служба оповещений конференц-связи Lync Server и служба аудио-и видеоконференций Lync Server) и сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="11206-317">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-318">Серверы Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="11206-318">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="11206-319">443</span><span class="sxs-lookup"><span data-stu-id="11206-319">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="11206-320">Используется Lync Server 2013 для подключения к серверу Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="11206-320">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-321">Директор</span><span class="sxs-lookup"><span data-stu-id="11206-321">Directors</span></span></p></td>
<td><p><span data-ttu-id="11206-322">Служба Front-End Lync Server</span><span class="sxs-lookup"><span data-stu-id="11206-322">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="11206-323">5060</span><span class="sxs-lookup"><span data-stu-id="11206-323">5060</span></span></p></td>
<td><p><span data-ttu-id="11206-324">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-324">TCP</span></span></p></td>
<td><p><span data-ttu-id="11206-325">При необходимости используется для статических маршрутов к доверенным службам, таким как серверы удаленного управления звонками.</span><span class="sxs-lookup"><span data-stu-id="11206-325">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-326">Директор</span><span class="sxs-lookup"><span data-stu-id="11206-326">Directors</span></span></p></td>
<td><p><span data-ttu-id="11206-327">Служба Front-End Lync Server</span><span class="sxs-lookup"><span data-stu-id="11206-327">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="11206-328">444</span><span class="sxs-lookup"><span data-stu-id="11206-328">444</span></span></p></td>
<td><p><span data-ttu-id="11206-329">HTTPS</span><span class="sxs-lookup"><span data-stu-id="11206-329">HTTPS</span></span></p>
<p><span data-ttu-id="11206-330">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-330">TCP</span></span></p></td>
<td><p><span data-ttu-id="11206-331">Inter-server communication between Front End and Director.</span><span class="sxs-lookup"><span data-stu-id="11206-331">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="11206-332">Кроме того, публикация сертификата клиента (на серверах переднего плана) или проверка того, был ли уже опубликован сертификат клиента.</span><span class="sxs-lookup"><span data-stu-id="11206-332">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-333">Директор</span><span class="sxs-lookup"><span data-stu-id="11206-333">Directors</span></span></p></td>
<td><p><span data-ttu-id="11206-334">Служба веб-совместимости Lync Server</span><span class="sxs-lookup"><span data-stu-id="11206-334">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="11206-335">80</span><span class="sxs-lookup"><span data-stu-id="11206-335">80</span></span></p></td>
<td><p><span data-ttu-id="11206-336">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-336">TCP</span></span></p></td>
<td><p><span data-ttu-id="11206-p105">Используется для исходного подключения от директоров к полным доменным именам в веб-ферме (URL-адреса используются по веб-компонентам IIS). При обычной работе происходит переключение на трафик HTTPS с использованием порта 443 и протокола TCP.</span><span class="sxs-lookup"><span data-stu-id="11206-p105">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components). In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-339">Директор</span><span class="sxs-lookup"><span data-stu-id="11206-339">Directors</span></span></p></td>
<td><p><span data-ttu-id="11206-340">Служба веб-совместимости Lync Server</span><span class="sxs-lookup"><span data-stu-id="11206-340">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="11206-341">443</span><span class="sxs-lookup"><span data-stu-id="11206-341">443</span></span></p></td>
<td><p><span data-ttu-id="11206-342">HTTPS</span><span class="sxs-lookup"><span data-stu-id="11206-342">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="11206-343">Используется для подключения от директоров к полным доменным именам в веб-ферме (URL-адреса используются по веб-компонентам IIS).</span><span class="sxs-lookup"><span data-stu-id="11206-343">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-344">Директор</span><span class="sxs-lookup"><span data-stu-id="11206-344">Directors</span></span></p></td>
<td><p><span data-ttu-id="11206-345">Служба Front-End Lync Server</span><span class="sxs-lookup"><span data-stu-id="11206-345">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="11206-346">5061</span><span class="sxs-lookup"><span data-stu-id="11206-346">5061</span></span></p></td>
<td><p><span data-ttu-id="11206-347">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-347">TCP</span></span></p></td>
<td><p><span data-ttu-id="11206-348">Используется для внутренних подключений между серверами и для клиентских подключений.</span><span class="sxs-lookup"><span data-stu-id="11206-348">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-349">Серверы-посредники</span><span class="sxs-lookup"><span data-stu-id="11206-349">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="11206-350">Служба-посредник по Lync Server</span><span class="sxs-lookup"><span data-stu-id="11206-350">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="11206-351">5070</span><span class="sxs-lookup"><span data-stu-id="11206-351">5070</span></span></p></td>
<td><p><span data-ttu-id="11206-352">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-352">TCP</span></span></p></td>
<td><p><span data-ttu-id="11206-353">Используется сервером-посредником для входящих запросов от сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="11206-353">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-354">Серверы-посредники</span><span class="sxs-lookup"><span data-stu-id="11206-354">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="11206-355">Служба-посредник по Lync Server</span><span class="sxs-lookup"><span data-stu-id="11206-355">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="11206-356">5067</span><span class="sxs-lookup"><span data-stu-id="11206-356">5067</span></span></p></td>
<td><p><span data-ttu-id="11206-357">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="11206-357">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="11206-358">Используется для входящих SIP-запросов от шлюза ТСОП.</span><span class="sxs-lookup"><span data-stu-id="11206-358">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-359">Серверы-посредники</span><span class="sxs-lookup"><span data-stu-id="11206-359">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="11206-360">Служба-посредник по Lync Server</span><span class="sxs-lookup"><span data-stu-id="11206-360">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="11206-361">5068</span><span class="sxs-lookup"><span data-stu-id="11206-361">5068</span></span></p></td>
<td><p><span data-ttu-id="11206-362">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-362">TCP</span></span></p></td>
<td><p><span data-ttu-id="11206-363">Используется для входящих SIP-запросов от шлюза ТСОП.</span><span class="sxs-lookup"><span data-stu-id="11206-363">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-364">Серверы-посредники</span><span class="sxs-lookup"><span data-stu-id="11206-364">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="11206-365">Служба-посредник по Lync Server</span><span class="sxs-lookup"><span data-stu-id="11206-365">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="11206-366">5070</span><span class="sxs-lookup"><span data-stu-id="11206-366">5070</span></span></p></td>
<td><p><span data-ttu-id="11206-367">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="11206-367">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="11206-368">Используется для SIP-запросов от серверов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="11206-368">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-369">Сервер переднего плана сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="11206-369">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="11206-370">SIP-запрос сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="11206-370">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="11206-371">5041</span><span class="sxs-lookup"><span data-stu-id="11206-371">5041</span></span></p></td>
<td><p><span data-ttu-id="11206-372">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="11206-372">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-373">Сервер переднего плана сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="11206-373">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="11206-374">Платформа Windows Communication Foundation (WCF) для сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="11206-374">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="11206-375">881</span><span class="sxs-lookup"><span data-stu-id="11206-375">881</span></span></p></td>
<td><p><span data-ttu-id="11206-376">TCP (TLS) и TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="11206-376">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-377">Сервер переднего плана сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="11206-377">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="11206-378">Служба передачи файлов для сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="11206-378">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="11206-379">443</span><span class="sxs-lookup"><span data-stu-id="11206-379">443</span></span></p></td>
<td><p><span data-ttu-id="11206-380">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="11206-380">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="11206-381">Для некоторых сценариев удаленного управления звонками требуется TCP-соединение между сервером переднего плана или директором и УАТС.</span><span class="sxs-lookup"><span data-stu-id="11206-381">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="11206-382">Несмотря на то, что Lync Server больше не использует TCP-порт 5060, во время развертывания удаленного управления звонками создается конфигурация доверенных серверов, которая связывает полное доменное имя сервера по линии RCC с портом TCP, который будет использоваться сервером переднего плана или директором для подключения к системе УАТС.</span><span class="sxs-lookup"><span data-stu-id="11206-382">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="11206-383">Для получения дополнительных сведений обратитесь к командлету <STRONG>кструстедаппликатионкомпутер</STRONG> в документации по консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="11206-383">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="11206-384">Для пулов, использующих только аппаратную балансировку нагрузки (без балансировки нагрузки на DNS), в следующей таблице показаны порты, которые должны открыть аппаратную подсистему балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="11206-384">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="11206-385">Порты аппаратного балансировщика нагрузки при использовании только аппаратной балансировки нагрузки</span><span class="sxs-lookup"><span data-stu-id="11206-385">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11206-386">Балансировщик нагрузки</span><span class="sxs-lookup"><span data-stu-id="11206-386">Load Balancer</span></span></th>
<th><span data-ttu-id="11206-387">Порт</span><span class="sxs-lookup"><span data-stu-id="11206-387">Port</span></span></th>
<th><span data-ttu-id="11206-388">Протокол</span><span class="sxs-lookup"><span data-stu-id="11206-388">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11206-389">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-389">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="11206-390">5061</span><span class="sxs-lookup"><span data-stu-id="11206-390">5061</span></span></p></td>
<td><p><span data-ttu-id="11206-391">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="11206-391">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-392">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-392">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="11206-393">444</span><span class="sxs-lookup"><span data-stu-id="11206-393">444</span></span></p></td>
<td><p><span data-ttu-id="11206-394">HTTPS</span><span class="sxs-lookup"><span data-stu-id="11206-394">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-395">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-395">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="11206-396">135</span><span class="sxs-lookup"><span data-stu-id="11206-396">135</span></span></p></td>
<td><p><span data-ttu-id="11206-397">DCOM и удаленный вызов процедур (RPC)</span><span class="sxs-lookup"><span data-stu-id="11206-397">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-398">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-398">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="11206-399">80</span><span class="sxs-lookup"><span data-stu-id="11206-399">80</span></span></p></td>
<td><p><span data-ttu-id="11206-400">HTTP</span><span class="sxs-lookup"><span data-stu-id="11206-400">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-401">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-401">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="11206-402">8080</span><span class="sxs-lookup"><span data-stu-id="11206-402">8080</span></span></p></td>
<td><p><span data-ttu-id="11206-403">TCP-получение клиентом и устройством корневого сертификата с сервера переднего плана — клиенты и устройства, прошедшие проверку подлинности NTLM</span><span class="sxs-lookup"><span data-stu-id="11206-403">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-404">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-404">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="11206-405">443</span><span class="sxs-lookup"><span data-stu-id="11206-405">443</span></span></p></td>
<td><p><span data-ttu-id="11206-406">HTTPS</span><span class="sxs-lookup"><span data-stu-id="11206-406">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-407">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-407">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="11206-408">4443</span><span class="sxs-lookup"><span data-stu-id="11206-408">4443</span></span></p></td>
<td><p><span data-ttu-id="11206-409">HTTPS (от обратного прокси-сервера)</span><span class="sxs-lookup"><span data-stu-id="11206-409">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-410">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-410">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="11206-411">5072</span><span class="sxs-lookup"><span data-stu-id="11206-411">5072</span></span></p></td>
<td><p><span data-ttu-id="11206-412">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-412">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-413">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-413">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="11206-414">5073</span><span class="sxs-lookup"><span data-stu-id="11206-414">5073</span></span></p></td>
<td><p><span data-ttu-id="11206-415">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-415">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-416">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-416">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="11206-417">5075</span><span class="sxs-lookup"><span data-stu-id="11206-417">5075</span></span></p></td>
<td><p><span data-ttu-id="11206-418">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-418">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-419">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-419">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="11206-420">5076</span><span class="sxs-lookup"><span data-stu-id="11206-420">5076</span></span></p></td>
<td><p><span data-ttu-id="11206-421">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-421">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-422">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-422">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="11206-423">5071</span><span class="sxs-lookup"><span data-stu-id="11206-423">5071</span></span></p></td>
<td><p><span data-ttu-id="11206-424">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-424">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-425">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-425">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="11206-426">5080</span><span class="sxs-lookup"><span data-stu-id="11206-426">5080</span></span></p></td>
<td><p><span data-ttu-id="11206-427">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-427">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-428">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-428">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="11206-429">448</span><span class="sxs-lookup"><span data-stu-id="11206-429">448</span></span></p></td>
<td><p><span data-ttu-id="11206-430">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-430">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-431">Балансировщик нагрузки сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="11206-431">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="11206-432">5070</span><span class="sxs-lookup"><span data-stu-id="11206-432">5070</span></span></p></td>
<td><p><span data-ttu-id="11206-433">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-433">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-434">Балансировщик нагрузки на сервере переднего плана (если в пуле также работает сервер-посредник)</span><span class="sxs-lookup"><span data-stu-id="11206-434">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="11206-435">5070</span><span class="sxs-lookup"><span data-stu-id="11206-435">5070</span></span></p></td>
<td><p><span data-ttu-id="11206-436">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-436">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-437">Подсистема балансировки нагрузки режиссера</span><span class="sxs-lookup"><span data-stu-id="11206-437">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="11206-438">443</span><span class="sxs-lookup"><span data-stu-id="11206-438">443</span></span></p></td>
<td><p><span data-ttu-id="11206-439">HTTPS</span><span class="sxs-lookup"><span data-stu-id="11206-439">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-440">Подсистема балансировки нагрузки режиссера</span><span class="sxs-lookup"><span data-stu-id="11206-440">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="11206-441">444</span><span class="sxs-lookup"><span data-stu-id="11206-441">444</span></span></p></td>
<td><p><span data-ttu-id="11206-442">HTTPS</span><span class="sxs-lookup"><span data-stu-id="11206-442">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-443">Подсистема балансировки нагрузки режиссера</span><span class="sxs-lookup"><span data-stu-id="11206-443">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="11206-444">5061</span><span class="sxs-lookup"><span data-stu-id="11206-444">5061</span></span></p></td>
<td><p><span data-ttu-id="11206-445">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-445">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-446">Подсистема балансировки нагрузки режиссера</span><span class="sxs-lookup"><span data-stu-id="11206-446">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="11206-447">4443</span><span class="sxs-lookup"><span data-stu-id="11206-447">4443</span></span></p></td>
<td><p><span data-ttu-id="11206-448">HTTPS (от обратного прокси-сервера)</span><span class="sxs-lookup"><span data-stu-id="11206-448">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="11206-449">Для пулов переднего плана и пулов директоров, использующих балансировку нагрузки на DNS, также должен быть развернут аппаратный балансировщик нагрузки.</span><span class="sxs-lookup"><span data-stu-id="11206-449">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed.</span></span> <span data-ttu-id="11206-450">В следующей таблице приведены порты, которые должны быть открыты на этих аппаратных подсистемах балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="11206-450">The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="11206-451">Порты аппаратного балансировщика нагрузки при использовании балансировки нагрузки на DNS</span><span class="sxs-lookup"><span data-stu-id="11206-451">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11206-452">Балансировщик нагрузки</span><span class="sxs-lookup"><span data-stu-id="11206-452">Load Balancer</span></span></th>
<th><span data-ttu-id="11206-453">Порт</span><span class="sxs-lookup"><span data-stu-id="11206-453">Port</span></span></th>
<th><span data-ttu-id="11206-454">Протокол</span><span class="sxs-lookup"><span data-stu-id="11206-454">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11206-455">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-455">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="11206-456">80</span><span class="sxs-lookup"><span data-stu-id="11206-456">80</span></span></p></td>
<td><p><span data-ttu-id="11206-457">HTTP</span><span class="sxs-lookup"><span data-stu-id="11206-457">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-458">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-458">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="11206-459">443</span><span class="sxs-lookup"><span data-stu-id="11206-459">443</span></span></p></td>
<td><p><span data-ttu-id="11206-460">HTTPS</span><span class="sxs-lookup"><span data-stu-id="11206-460">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-461">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-461">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="11206-462">8080</span><span class="sxs-lookup"><span data-stu-id="11206-462">8080</span></span></p></td>
<td><p><span data-ttu-id="11206-463">TCP-получение клиентом и устройством корневого сертификата с сервера переднего плана — клиенты и устройства, прошедшие проверку подлинности NTLM</span><span class="sxs-lookup"><span data-stu-id="11206-463">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-464">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="11206-464">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="11206-465">4443</span><span class="sxs-lookup"><span data-stu-id="11206-465">4443</span></span></p></td>
<td><p><span data-ttu-id="11206-466">HTTPS (от обратного прокси-сервера)</span><span class="sxs-lookup"><span data-stu-id="11206-466">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-467">Подсистема балансировки нагрузки режиссера</span><span class="sxs-lookup"><span data-stu-id="11206-467">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="11206-468">443</span><span class="sxs-lookup"><span data-stu-id="11206-468">443</span></span></p></td>
<td><p><span data-ttu-id="11206-469">HTTPS</span><span class="sxs-lookup"><span data-stu-id="11206-469">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-470">Подсистема балансировки нагрузки режиссера</span><span class="sxs-lookup"><span data-stu-id="11206-470">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="11206-471">4443</span><span class="sxs-lookup"><span data-stu-id="11206-471">4443</span></span></p></td>
<td><p><span data-ttu-id="11206-472">HTTPS (от обратного прокси-сервера)</span><span class="sxs-lookup"><span data-stu-id="11206-472">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="11206-473">Необходимые порты клиента</span><span class="sxs-lookup"><span data-stu-id="11206-473">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11206-474">Компонент</span><span class="sxs-lookup"><span data-stu-id="11206-474">Component</span></span></th>
<th><span data-ttu-id="11206-475">Порт</span><span class="sxs-lookup"><span data-stu-id="11206-475">Port</span></span></th>
<th><span data-ttu-id="11206-476">Протокол</span><span class="sxs-lookup"><span data-stu-id="11206-476">Protocol</span></span></th>
<th><span data-ttu-id="11206-477">Примечания</span><span class="sxs-lookup"><span data-stu-id="11206-477">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11206-478">Клиенты</span><span class="sxs-lookup"><span data-stu-id="11206-478">Clients</span></span></p></td>
<td><p><span data-ttu-id="11206-479">67/68</span><span class="sxs-lookup"><span data-stu-id="11206-479">67/68</span></span></p></td>
<td><p><span data-ttu-id="11206-480">-</span><span class="sxs-lookup"><span data-stu-id="11206-480">DHCP</span></span></p></td>
<td><p><span data-ttu-id="11206-481">Используется Lync Server для поиска полного доменного имени регистратора (то есть в случае сбоя DNS SRV и ненастроенных параметров вручную).</span><span class="sxs-lookup"><span data-stu-id="11206-481">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-482">Клиенты</span><span class="sxs-lookup"><span data-stu-id="11206-482">Clients</span></span></p></td>
<td><p><span data-ttu-id="11206-483">443</span><span class="sxs-lookup"><span data-stu-id="11206-483">443</span></span></p></td>
<td><p><span data-ttu-id="11206-484">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="11206-484">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="11206-485">Используется для трафика SIP от клиента к серверу для доступа внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="11206-485">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-486">Клиенты</span><span class="sxs-lookup"><span data-stu-id="11206-486">Clients</span></span></p></td>
<td><p><span data-ttu-id="11206-487">443</span><span class="sxs-lookup"><span data-stu-id="11206-487">443</span></span></p></td>
<td><p><span data-ttu-id="11206-488">TCP (PSOM/TLS)</span><span class="sxs-lookup"><span data-stu-id="11206-488">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="11206-489">Используется для доступа внешних пользователей к сеансам веб-конференций.</span><span class="sxs-lookup"><span data-stu-id="11206-489">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-490">Клиенты</span><span class="sxs-lookup"><span data-stu-id="11206-490">Clients</span></span></p></td>
<td><p><span data-ttu-id="11206-491">443</span><span class="sxs-lookup"><span data-stu-id="11206-491">443</span></span></p></td>
<td><p><span data-ttu-id="11206-492">TCP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="11206-492">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="11206-493">Используется для доступа внешних пользователей к сеансам аудио-и видеосвязи и мультимедиа (TCP)</span><span class="sxs-lookup"><span data-stu-id="11206-493">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-494">Клиенты</span><span class="sxs-lookup"><span data-stu-id="11206-494">Clients</span></span></p></td>
<td><p><span data-ttu-id="11206-495">3478</span><span class="sxs-lookup"><span data-stu-id="11206-495">3478</span></span></p></td>
<td><p><span data-ttu-id="11206-496">UDP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="11206-496">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="11206-497">Используется для доступа внешних пользователей к сеансам аудио-и видеосвязи и мультимедиа (UDP)</span><span class="sxs-lookup"><span data-stu-id="11206-497">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-498">Клиенты</span><span class="sxs-lookup"><span data-stu-id="11206-498">Clients</span></span></p></td>
<td><p><span data-ttu-id="11206-499">5061</span><span class="sxs-lookup"><span data-stu-id="11206-499">5061</span></span></p></td>
<td><p><span data-ttu-id="11206-500">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="11206-500">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="11206-501">Используется для трафика SIP от клиента к серверу для доступа внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="11206-501">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-502">Клиенты</span><span class="sxs-lookup"><span data-stu-id="11206-502">Clients</span></span></p></td>
<td><p><span data-ttu-id="11206-503">6891-6901</span><span class="sxs-lookup"><span data-stu-id="11206-503">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="11206-504">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-504">TCP</span></span></p></td>
<td><p><span data-ttu-id="11206-505">Используется для передачи файлов между клиентами Lync и предыдущими клиентами (клиентами Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007 и Live Communications Server 2005).</span><span class="sxs-lookup"><span data-stu-id="11206-505">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-506">Клиенты</span><span class="sxs-lookup"><span data-stu-id="11206-506">Clients</span></span></p></td>
<td><p><span data-ttu-id="11206-507">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="11206-507">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="11206-508">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="11206-508">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="11206-509">Диапазон портов аудиоподсистемы (необходимо минимум 20 портов)</span><span class="sxs-lookup"><span data-stu-id="11206-509">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-510">Клиенты</span><span class="sxs-lookup"><span data-stu-id="11206-510">Clients</span></span></p></td>
<td><p><span data-ttu-id="11206-511">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="11206-511">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="11206-512">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="11206-512">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="11206-513">Диапазон портов для видео (необходимо минимум 20 портов).</span><span class="sxs-lookup"><span data-stu-id="11206-513">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-514">Клиенты</span><span class="sxs-lookup"><span data-stu-id="11206-514">Clients</span></span></p></td>
<td><p><span data-ttu-id="11206-515">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="11206-515">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="11206-516">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-516">TCP</span></span></p></td>
<td><p><span data-ttu-id="11206-517">Передача файлов в одноранговой сети (для передачи файлов конференц-связи клиенты используют PSOM).</span><span class="sxs-lookup"><span data-stu-id="11206-517">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11206-518">Клиенты</span><span class="sxs-lookup"><span data-stu-id="11206-518">Clients</span></span></p></td>
<td><p><span data-ttu-id="11206-519">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="11206-519">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="11206-520">TCP</span><span class="sxs-lookup"><span data-stu-id="11206-520">TCP</span></span></p></td>
<td><p><span data-ttu-id="11206-521">Общий доступ к приложениям.</span><span class="sxs-lookup"><span data-stu-id="11206-521">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11206-522">Телефон общего пользования Aastra 6721ip</span><span class="sxs-lookup"><span data-stu-id="11206-522">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="11206-523">Стационарный телефон Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="11206-523">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="11206-524">IP-телефон HP 4110 (телефон общего доступа)</span><span class="sxs-lookup"><span data-stu-id="11206-524">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="11206-525">IP-телефон HP 4120 (стационарный телефон)</span><span class="sxs-lookup"><span data-stu-id="11206-525">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="11206-526">IP-телефон общего доступа Polycom CX500</span><span class="sxs-lookup"><span data-stu-id="11206-526">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="11206-527">Настольный IP-телефон Polycom CX600</span><span class="sxs-lookup"><span data-stu-id="11206-527">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="11206-528">Настольный IP-телефон Polycom CX700</span><span class="sxs-lookup"><span data-stu-id="11206-528">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="11206-529">IP-телефон для конференций Polycom CX3000</span><span class="sxs-lookup"><span data-stu-id="11206-529">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="11206-530">67/68</span><span class="sxs-lookup"><span data-stu-id="11206-530">67/68</span></span></p></td>
<td><p><span data-ttu-id="11206-531">-</span><span class="sxs-lookup"><span data-stu-id="11206-531">DHCP</span></span></p></td>
<td><p><span data-ttu-id="11206-532">Используется перечисленными устройствами для поиска сертификата сервера Lync, подготовки полного доменного имени и полного доменного имени регистратора.</span><span class="sxs-lookup"><span data-stu-id="11206-532">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="11206-533">**\*** Для настройки определенных портов для этих типов мультимедиа используйте командлет CsConferencingConfiguration (параметры параметры clientmediaportrangeenabled, ClientMediaPort и ClientMediaPortRange).</span><span class="sxs-lookup"><span data-stu-id="11206-533">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="11206-534">Клиенты установки программ для Lync автоматически создают на клиентском компьютере необходимые исключения брандмауэра операционной системы.</span><span class="sxs-lookup"><span data-stu-id="11206-534">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="11206-535">Порты, используемые для доступа внешних пользователей, необходимы для любого сценария, в котором клиент должен пройти брандмауэр организации (например, любые внешние коммуникации или собрания, размещенные в других организациях).</span><span class="sxs-lookup"><span data-stu-id="11206-535">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

