---
title: 'Lync Server 2013: порты и протоколы для внутренних серверов'
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
ms.openlocfilehash: 858ec90cf3811318cc29a902b56ac8ff31c46a22
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513406"
---
# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="ed286-102">Порты и протоколы для внутренних серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed286-102">Ports and protocols for internal servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed286-103">_**Последнее изменение темы:** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="ed286-103">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="ed286-104">В этом разделе приведены общие сведения о портах и протоколах, используемых серверами, подсистемами балансировки нагрузки и клиентами в развертывании Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ed286-104">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ed286-105">Клиенты Lync и Communicator, участвующие в одном обмене данными, часто называют одноранговыми узлами.</span><span class="sxs-lookup"><span data-stu-id="ed286-105">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="ed286-106">С технической точки зрения два клиента взаимодействуют в одном сеансе, с помощью модуля управления мгновенными сообщениями MultiPoint (ИММКУ) в центре.</span><span class="sxs-lookup"><span data-stu-id="ed286-106">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="ed286-107">ИММКУ — это компонент сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="ed286-107">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="ed286-108">Размещение ИММКУ в требуемом рабочем канале связи позволяет записывать сведения о вызовах и другие функции, которые обеспечивает сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="ed286-108">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="ed286-109">Обмен данными осуществляется от динамического исходного порта на клиенте к порту TLS/TCP/5061 (при условии использования рекомендуемой безопасности транспортного уровня).</span><span class="sxs-lookup"><span data-stu-id="ed286-109">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="ed286-110">Одноранговая связь (а также поддержка обмена мгновенными сообщениями) возможна только в том случае, если Lync Server и ИММКУ активны и доступны.</span><span class="sxs-lookup"><span data-stu-id="ed286-110">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="ed286-111">Сведения о портах и протоколе</span><span class="sxs-lookup"><span data-stu-id="ed286-111">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ed286-112">Перед запуском служб Lync Server на сервере необходимо запустить брандмауэр Windows, так как в этом случае Lync Server открывает необходимые порты в брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="ed286-112">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="ed286-113">Подробные сведения о конфигурации брандмауэра для пограничных компонентов приведены [в статье Определение требований к портам внешнего аудио-и видеоподключения для Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed286-113">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="ed286-114">В следующей таблице приводится список портов, которые должны быть открыты для каждой роли внутреннего сервера.</span><span class="sxs-lookup"><span data-stu-id="ed286-114">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="ed286-115">Необходимые порты сервера (по ролям сервера)</span><span class="sxs-lookup"><span data-stu-id="ed286-115">Required Server Ports (by Server Role)</span></span>

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
<th><span data-ttu-id="ed286-116">Роль сервера</span><span class="sxs-lookup"><span data-stu-id="ed286-116">Server role</span></span></th>
<th><span data-ttu-id="ed286-117">Имя службы</span><span class="sxs-lookup"><span data-stu-id="ed286-117">Service name</span></span></th>
<th><span data-ttu-id="ed286-118">Порт</span><span class="sxs-lookup"><span data-stu-id="ed286-118">Port</span></span></th>
<th><span data-ttu-id="ed286-119">Протокол</span><span class="sxs-lookup"><span data-stu-id="ed286-119">Protocol</span></span></th>
<th><span data-ttu-id="ed286-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="ed286-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed286-121">Все серверы</span><span class="sxs-lookup"><span data-stu-id="ed286-121">All Servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-122">Браузер SQL</span><span class="sxs-lookup"><span data-stu-id="ed286-122">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="ed286-123">1434</span><span class="sxs-lookup"><span data-stu-id="ed286-123">1434</span></span></p></td>
<td><p><span data-ttu-id="ed286-124">ПРОТОКОЛА</span><span class="sxs-lookup"><span data-stu-id="ed286-124">UDP</span></span></p></td>
<td><p><span data-ttu-id="ed286-125">Браузер SQL для локальной реплицированной копии базы данных центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="ed286-125">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-126">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-126">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-127">Служба Front-End Lync Server</span><span class="sxs-lookup"><span data-stu-id="ed286-127">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="ed286-128">5060</span><span class="sxs-lookup"><span data-stu-id="ed286-128">5060</span></span></p></td>
<td><p><span data-ttu-id="ed286-129">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-129">TCP</span></span></p></td>
<td><p><span data-ttu-id="ed286-130">При необходимости используется для статических маршрутов к доверенным службам серверами Standard Edition и серверами переднего плана, например серверами удаленного управления звонками.</span><span class="sxs-lookup"><span data-stu-id="ed286-130">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-131">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-131">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-132">Служба Front-End Lync Server</span><span class="sxs-lookup"><span data-stu-id="ed286-132">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="ed286-133">5061</span><span class="sxs-lookup"><span data-stu-id="ed286-133">5061</span></span></p></td>
<td><p><span data-ttu-id="ed286-134">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ed286-134">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="ed286-p102">Используется серверами Standard Edition и серверами переднего плана для всех внутренних SIP-соединений между серверами (MTLS), для SIP-соединений между сервером и клиентом (TLS) и для SIP-соединений между серверами переднего плана и серверами-посредниками (MTLS). Также используется для соединений с сервером мониторинга.</span><span class="sxs-lookup"><span data-stu-id="ed286-p102">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS). Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-137">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-137">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-138">Служба Front-End Lync Server</span><span class="sxs-lookup"><span data-stu-id="ed286-138">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="ed286-139">444</span><span class="sxs-lookup"><span data-stu-id="ed286-139">444</span></span></p></td>
<td><p><span data-ttu-id="ed286-140">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ed286-140">HTTPS</span></span></p>
<p><span data-ttu-id="ed286-141">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-141">TCP</span></span></p></td>
<td><p><span data-ttu-id="ed286-142">Используется для взаимодействия по протоколу HTTPS между фокусом (компонентом Lync Server, который управляет состоянием конференции) и отдельными серверами.</span><span class="sxs-lookup"><span data-stu-id="ed286-142">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="ed286-143">Этот порт также используется для связи по протоколу TCP между устройствами для обеспечения связи в филиалах и серверами переднего плана.</span><span class="sxs-lookup"><span data-stu-id="ed286-143">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-144">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-144">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-145">Служба Front-End Lync Server</span><span class="sxs-lookup"><span data-stu-id="ed286-145">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="ed286-146">135</span><span class="sxs-lookup"><span data-stu-id="ed286-146">135</span></span></p></td>
<td><p><span data-ttu-id="ed286-147">DCOM и удаленный вызов процедур (RPC)</span><span class="sxs-lookup"><span data-stu-id="ed286-147">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="ed286-148">Используется для операций на базе DCOM, таких как перемещение пользователей, синхронизация репликаторов пользовательских данных и адресных книг.</span><span class="sxs-lookup"><span data-stu-id="ed286-148">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-149">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-149">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-150">Служба конференц-связи Lync Server для обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="ed286-150">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="ed286-151">5062</span><span class="sxs-lookup"><span data-stu-id="ed286-151">5062</span></span></p></td>
<td><p><span data-ttu-id="ed286-152">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-152">TCP</span></span></p></td>
<td><p><span data-ttu-id="ed286-153">Используется для входящих SIP-запросов в конференц-связи с использованием обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="ed286-153">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-154">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-154">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-155">Служба веб-конференций Lync Server</span><span class="sxs-lookup"><span data-stu-id="ed286-155">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="ed286-156">8057</span><span class="sxs-lookup"><span data-stu-id="ed286-156">8057</span></span></p></td>
<td><p><span data-ttu-id="ed286-157">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ed286-157">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="ed286-158">Используется для прослушивания подключений по протоколу PSOM от клиента.</span><span class="sxs-lookup"><span data-stu-id="ed286-158">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-159">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-159">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-160">Служба совместимости веб-конференций Lync Server</span><span class="sxs-lookup"><span data-stu-id="ed286-160">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="ed286-161">8058</span><span class="sxs-lookup"><span data-stu-id="ed286-161">8058</span></span></p></td>
<td><p><span data-ttu-id="ed286-162">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ed286-162">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="ed286-163">Используется для прослушивания подключений к постоянным общим объектным моделям (PSOM) из клиента Live Meeting и предыдущих версий Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ed286-163">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-164">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-164">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-165">Служба аудио-и видеоконференций Lync Server</span><span class="sxs-lookup"><span data-stu-id="ed286-165">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="ed286-166">5063</span><span class="sxs-lookup"><span data-stu-id="ed286-166">5063</span></span></p></td>
<td><p><span data-ttu-id="ed286-167">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-167">TCP</span></span></p></td>
<td><p><span data-ttu-id="ed286-168">Используется для входящих SIP-запросов на аудио- и видеоконференции.</span><span class="sxs-lookup"><span data-stu-id="ed286-168">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-169">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-169">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-170">Служба аудио-и видеоконференций Lync Server</span><span class="sxs-lookup"><span data-stu-id="ed286-170">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="ed286-171">57501-65535</span><span class="sxs-lookup"><span data-stu-id="ed286-171">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="ed286-172">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="ed286-172">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="ed286-173">Диапазон портов, используемых для видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="ed286-173">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-174">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-174">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-175">Служба веб-совместимости Lync Server</span><span class="sxs-lookup"><span data-stu-id="ed286-175">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="ed286-176">80</span><span class="sxs-lookup"><span data-stu-id="ed286-176">80</span></span></p></td>
<td><p><span data-ttu-id="ed286-177">HTTP</span><span class="sxs-lookup"><span data-stu-id="ed286-177">HTTP</span></span></p></td>
<td><p><span data-ttu-id="ed286-178">Используется для подключений от серверов переднего плана к полным доменным именам в веб-ферме (URL-адреса используются по веб-компонентам IIS), когда не используется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="ed286-178">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-179">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-179">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-180">Служба веб-совместимости Lync Server</span><span class="sxs-lookup"><span data-stu-id="ed286-180">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="ed286-181">443</span><span class="sxs-lookup"><span data-stu-id="ed286-181">443</span></span></p></td>
<td><p><span data-ttu-id="ed286-182">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ed286-182">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="ed286-183">Используется для подключений от серверов переднего плана к полным доменным именам в веб-ферме (URL-адреса используются по веб-компонентам IIS).</span><span class="sxs-lookup"><span data-stu-id="ed286-183">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-184">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-184">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-185">Служба веб-совместимости Lync Server</span><span class="sxs-lookup"><span data-stu-id="ed286-185">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="ed286-186">8080</span><span class="sxs-lookup"><span data-stu-id="ed286-186">8080</span></span></p></td>
<td><p><span data-ttu-id="ed286-187">TCP и HTTP</span><span class="sxs-lookup"><span data-stu-id="ed286-187">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="ed286-188">Используется веб-компонентами для внешнего доступа.</span><span class="sxs-lookup"><span data-stu-id="ed286-188">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-189">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-189">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-190">Компонент веб-сервера</span><span class="sxs-lookup"><span data-stu-id="ed286-190">Web server component</span></span></p></td>
<td><p><span data-ttu-id="ed286-191">4443</span><span class="sxs-lookup"><span data-stu-id="ed286-191">4443</span></span></p></td>
<td><p><span data-ttu-id="ed286-192">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ed286-192">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="ed286-193">Подключения HTTPS (от обратного прокси-сервера) и подключения между пулами HTTPS для входа в службу автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="ed286-193">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-194">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-194">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-195">Компонент веб-сервера</span><span class="sxs-lookup"><span data-stu-id="ed286-195">Web server component</span></span></p></td>
<td><p><span data-ttu-id="ed286-196">8060</span><span class="sxs-lookup"><span data-stu-id="ed286-196">8060</span></span></p></td>
<td><p><span data-ttu-id="ed286-197">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ed286-197">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-198">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-198">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-199">Компонент веб-сервера</span><span class="sxs-lookup"><span data-stu-id="ed286-199">Web server component</span></span></p></td>
<td><p><span data-ttu-id="ed286-200">8061</span><span class="sxs-lookup"><span data-stu-id="ed286-200">8061</span></span></p></td>
<td><p><span data-ttu-id="ed286-201">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ed286-201">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-202">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-202">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-203">Компонент служб Mobility Services</span><span class="sxs-lookup"><span data-stu-id="ed286-203">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="ed286-204">5086</span><span class="sxs-lookup"><span data-stu-id="ed286-204">5086</span></span></p></td>
<td><p><span data-ttu-id="ed286-205">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ed286-205">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="ed286-206">SIP-порт, используемый внутренними процессами служб Mobility Services</span><span class="sxs-lookup"><span data-stu-id="ed286-206">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-207">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-207">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-208">Компонент служб Mobility Services</span><span class="sxs-lookup"><span data-stu-id="ed286-208">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="ed286-209">5087</span><span class="sxs-lookup"><span data-stu-id="ed286-209">5087</span></span></p></td>
<td><p><span data-ttu-id="ed286-210">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ed286-210">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="ed286-211">SIP-порт, используемый внутренними процессами служб Mobility Services</span><span class="sxs-lookup"><span data-stu-id="ed286-211">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-212">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-212">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-213">Компонент служб Mobility Services</span><span class="sxs-lookup"><span data-stu-id="ed286-213">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="ed286-214">443</span><span class="sxs-lookup"><span data-stu-id="ed286-214">443</span></span></p></td>
<td><p><span data-ttu-id="ed286-215">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ed286-215">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-216">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-216">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-217">Служба помощника по конференц-связи Lync Server (Конференц-связь с телефонным подключением)</span><span class="sxs-lookup"><span data-stu-id="ed286-217">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="ed286-218">5064</span><span class="sxs-lookup"><span data-stu-id="ed286-218">5064</span></span></p></td>
<td><p><span data-ttu-id="ed286-219">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-219">TCP</span></span></p></td>
<td><p><span data-ttu-id="ed286-220">Используется для входящих SIP-запросов для конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="ed286-220">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-221">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-221">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-222">Служба помощника по конференц-связи Lync Server (Конференц-связь с телефонным подключением)</span><span class="sxs-lookup"><span data-stu-id="ed286-222">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="ed286-223">5072</span><span class="sxs-lookup"><span data-stu-id="ed286-223">5072</span></span></p></td>
<td><p><span data-ttu-id="ed286-224">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-224">TCP</span></span></p></td>
<td><p><span data-ttu-id="ed286-225">Используется для входящих SIP-запросов для помощника (конференц-связи с телефонным подключением).</span><span class="sxs-lookup"><span data-stu-id="ed286-225">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-226">Серверы переднего плана, на которых также работает соотнесенный сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="ed286-226">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="ed286-227">Служба-посредник по Lync Server</span><span class="sxs-lookup"><span data-stu-id="ed286-227">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="ed286-228">5070</span><span class="sxs-lookup"><span data-stu-id="ed286-228">5070</span></span></p></td>
<td><p><span data-ttu-id="ed286-229">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-229">TCP</span></span></p></td>
<td><p><span data-ttu-id="ed286-230">Используется сервером-посредником для входящих запросов от сервера переднего плана к серверу посреднику.</span><span class="sxs-lookup"><span data-stu-id="ed286-230">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-231">Серверы переднего плана, на которых также работает соотнесенный сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="ed286-231">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="ed286-232">Служба-посредник по Lync Server</span><span class="sxs-lookup"><span data-stu-id="ed286-232">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="ed286-233">5067</span><span class="sxs-lookup"><span data-stu-id="ed286-233">5067</span></span></p></td>
<td><p><span data-ttu-id="ed286-234">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ed286-234">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="ed286-235">Используется для входящих SIP-запросов от шлюза ТСОП к серверу-посреднику.</span><span class="sxs-lookup"><span data-stu-id="ed286-235">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-236">Серверы переднего плана, на которых также работает соотнесенный сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="ed286-236">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="ed286-237">Служба-посредник по Lync Server</span><span class="sxs-lookup"><span data-stu-id="ed286-237">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="ed286-238">5068</span><span class="sxs-lookup"><span data-stu-id="ed286-238">5068</span></span></p></td>
<td><p><span data-ttu-id="ed286-239">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-239">TCP</span></span></p></td>
<td><p><span data-ttu-id="ed286-240">Используется для входящих SIP-запросов от шлюза ТСОП к серверу-посреднику.</span><span class="sxs-lookup"><span data-stu-id="ed286-240">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-241">Серверы переднего плана, на которых также работает соотнесенный сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="ed286-241">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="ed286-242">Служба-посредник по Lync Server</span><span class="sxs-lookup"><span data-stu-id="ed286-242">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="ed286-243">5081</span><span class="sxs-lookup"><span data-stu-id="ed286-243">5081</span></span></p></td>
<td><p><span data-ttu-id="ed286-244">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-244">TCP</span></span></p></td>
<td><p><span data-ttu-id="ed286-245">Используется для исходящих SIP-запросов от сервера-посредника к шлюзу ТСОП.</span><span class="sxs-lookup"><span data-stu-id="ed286-245">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-246">Серверы переднего плана, на которых также работает соотнесенный сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="ed286-246">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="ed286-247">Служба-посредник по Lync Server</span><span class="sxs-lookup"><span data-stu-id="ed286-247">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="ed286-248">5082</span><span class="sxs-lookup"><span data-stu-id="ed286-248">5082</span></span></p></td>
<td><p><span data-ttu-id="ed286-249">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ed286-249">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="ed286-250">Используется для исходящих SIP-запросов от сервера-посредника к шлюзу ТСОП.</span><span class="sxs-lookup"><span data-stu-id="ed286-250">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-251">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-251">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-252">Служба общего доступа к приложениям Lync Server</span><span class="sxs-lookup"><span data-stu-id="ed286-252">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="ed286-253">5065</span><span class="sxs-lookup"><span data-stu-id="ed286-253">5065</span></span></p></td>
<td><p><span data-ttu-id="ed286-254">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-254">TCP</span></span></p></td>
<td><p><span data-ttu-id="ed286-255">Используется для входящих SIP-запросов на прослушивание для общего доступа к приложению.</span><span class="sxs-lookup"><span data-stu-id="ed286-255">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-256">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-256">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-257">Служба общего доступа к приложениям Lync Server</span><span class="sxs-lookup"><span data-stu-id="ed286-257">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="ed286-258">49152-65535</span><span class="sxs-lookup"><span data-stu-id="ed286-258">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="ed286-259">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-259">TCP</span></span></p></td>
<td><p><span data-ttu-id="ed286-260">Диапазон портов, используемых для общего доступа к приложению.</span><span class="sxs-lookup"><span data-stu-id="ed286-260">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-261">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-261">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-262">Служба объявлений Lync Server для конференц-связи</span><span class="sxs-lookup"><span data-stu-id="ed286-262">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="ed286-263">5073</span><span class="sxs-lookup"><span data-stu-id="ed286-263">5073</span></span></p></td>
<td><p><span data-ttu-id="ed286-264">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-264">TCP</span></span></p></td>
<td><p><span data-ttu-id="ed286-265">Используется для входящих SIP-запросов для службы оповещений конференц-связи Lync Server (то есть для конференц-связи с телефонным подключением).</span><span class="sxs-lookup"><span data-stu-id="ed286-265">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-266">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-266">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-267">Служба парковки вызовов Lync Server</span><span class="sxs-lookup"><span data-stu-id="ed286-267">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="ed286-268">5075</span><span class="sxs-lookup"><span data-stu-id="ed286-268">5075</span></span></p></td>
<td><p><span data-ttu-id="ed286-269">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-269">TCP</span></span></p></td>
<td><p><span data-ttu-id="ed286-270">Используется для входящих SIP-запросов для приложения приостановки звонков.</span><span class="sxs-lookup"><span data-stu-id="ed286-270">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-271">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-271">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-272">Служба проверки аудиоустройств Lync Server</span><span class="sxs-lookup"><span data-stu-id="ed286-272">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="ed286-273">5076</span><span class="sxs-lookup"><span data-stu-id="ed286-273">5076</span></span></p></td>
<td><p><span data-ttu-id="ed286-274">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-274">TCP</span></span></p></td>
<td><p><span data-ttu-id="ed286-275">Используется для входящих SIP-запросов для службы проверки аудиосвязи.</span><span class="sxs-lookup"><span data-stu-id="ed286-275">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-276">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-276">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-277">Не применимо</span><span class="sxs-lookup"><span data-stu-id="ed286-277">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="ed286-278">5066</span><span class="sxs-lookup"><span data-stu-id="ed286-278">5066</span></span></p></td>
<td><p><span data-ttu-id="ed286-279">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-279">TCP</span></span></p></td>
<td><p><span data-ttu-id="ed286-280">Используется для исходящего трафика в шлюзе службы Enhanced 9-1-1 (E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="ed286-280">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-281">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-281">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-282">Служба группы ответа Lync Server</span><span class="sxs-lookup"><span data-stu-id="ed286-282">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="ed286-283">5071</span><span class="sxs-lookup"><span data-stu-id="ed286-283">5071</span></span></p></td>
<td><p><span data-ttu-id="ed286-284">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-284">TCP</span></span></p></td>
<td><p><span data-ttu-id="ed286-285">Используется для входящих SIP-запросов для приложения группы ответа.</span><span class="sxs-lookup"><span data-stu-id="ed286-285">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-286">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-286">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-287">Служба группы ответа Lync Server</span><span class="sxs-lookup"><span data-stu-id="ed286-287">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="ed286-288">8404</span><span class="sxs-lookup"><span data-stu-id="ed286-288">8404</span></span></p></td>
<td><p><span data-ttu-id="ed286-289">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ed286-289">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="ed286-290">Используется для входящих SIP-запросов для приложения группы ответа.</span><span class="sxs-lookup"><span data-stu-id="ed286-290">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-291">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-291">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-292">Служба политики пропускной способности Lync Server</span><span class="sxs-lookup"><span data-stu-id="ed286-292">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="ed286-293">5080</span><span class="sxs-lookup"><span data-stu-id="ed286-293">5080</span></span></p></td>
<td><p><span data-ttu-id="ed286-294">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-294">TCP</span></span></p></td>
<td><p><span data-ttu-id="ed286-295">Используется для контроля допуска звонков, осуществляемого службой политики пропускной способности в отношении пограничного аудио-/видео-трафика @@TURN.</span><span class="sxs-lookup"><span data-stu-id="ed286-295">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-296">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-296">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-297">Служба политики пропускной способности Lync Server</span><span class="sxs-lookup"><span data-stu-id="ed286-297">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="ed286-298">448</span><span class="sxs-lookup"><span data-stu-id="ed286-298">448</span></span></p></td>
<td><p><span data-ttu-id="ed286-299">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-299">TCP</span></span></p></td>
<td><p><span data-ttu-id="ed286-300">Используется для контроля допуска звонков службой политики пропускной способности Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ed286-300">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-301">Серверы переднего плана, на которых размещается центральное хранилище управления</span><span class="sxs-lookup"><span data-stu-id="ed286-301">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="ed286-302">Служба агента главного репликатора Lync Server</span><span class="sxs-lookup"><span data-stu-id="ed286-302">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="ed286-303">445</span><span class="sxs-lookup"><span data-stu-id="ed286-303">445</span></span></p></td>
<td><p><span data-ttu-id="ed286-304">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-304">TCP</span></span></p></td>
<td><p><span data-ttu-id="ed286-305">Используется для принудительной передачи данных конфигурации из центрального хранилища управления на серверы, на которых работает Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ed286-305">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-306">Все серверы</span><span class="sxs-lookup"><span data-stu-id="ed286-306">All Servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-307">Браузер SQL</span><span class="sxs-lookup"><span data-stu-id="ed286-307">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="ed286-308">1434</span><span class="sxs-lookup"><span data-stu-id="ed286-308">1434</span></span></p></td>
<td><p><span data-ttu-id="ed286-309">ПРОТОКОЛА</span><span class="sxs-lookup"><span data-stu-id="ed286-309">UDP</span></span></p></td>
<td><p><span data-ttu-id="ed286-310">Браузер SQL для локальной реплицированной копии данных центрального хранилища управления в локальном экземпляре SQL Server</span><span class="sxs-lookup"><span data-stu-id="ed286-310">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-311">Все внутренние серверы</span><span class="sxs-lookup"><span data-stu-id="ed286-311">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-312">Разное</span><span class="sxs-lookup"><span data-stu-id="ed286-312">Various</span></span></p></td>
<td><p><span data-ttu-id="ed286-313">49152-57500</span><span class="sxs-lookup"><span data-stu-id="ed286-313">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="ed286-314">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="ed286-314">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="ed286-315">Диапазон портов, используемых для аудиоконференций на всех внутренних серверах.</span><span class="sxs-lookup"><span data-stu-id="ed286-315">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="ed286-316">Используется всеми серверами, которые завершают аудио: серверы переднего плана (служба помощника по конференц-связи Lync Server, служба оповещений конференц-связи Lync Server и служба аудио-и видеоконференций Lync Server) и сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="ed286-316">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-317">Серверы Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="ed286-317">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed286-318">443</span><span class="sxs-lookup"><span data-stu-id="ed286-318">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed286-319">Используется Lync Server 2013 для подключения к серверу Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="ed286-319">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-320">Директор</span><span class="sxs-lookup"><span data-stu-id="ed286-320">Directors</span></span></p></td>
<td><p><span data-ttu-id="ed286-321">Служба Front-End Lync Server</span><span class="sxs-lookup"><span data-stu-id="ed286-321">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="ed286-322">5060</span><span class="sxs-lookup"><span data-stu-id="ed286-322">5060</span></span></p></td>
<td><p><span data-ttu-id="ed286-323">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-323">TCP</span></span></p></td>
<td><p><span data-ttu-id="ed286-324">При необходимости используется для статических маршрутов к доверенным службам, таким как серверы удаленного управления звонками.</span><span class="sxs-lookup"><span data-stu-id="ed286-324">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-325">Директор</span><span class="sxs-lookup"><span data-stu-id="ed286-325">Directors</span></span></p></td>
<td><p><span data-ttu-id="ed286-326">Служба Front-End Lync Server</span><span class="sxs-lookup"><span data-stu-id="ed286-326">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="ed286-327">444</span><span class="sxs-lookup"><span data-stu-id="ed286-327">444</span></span></p></td>
<td><p><span data-ttu-id="ed286-328">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ed286-328">HTTPS</span></span></p>
<p><span data-ttu-id="ed286-329">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-329">TCP</span></span></p></td>
<td><p><span data-ttu-id="ed286-330">Inter-server communication between Front End and Director.</span><span class="sxs-lookup"><span data-stu-id="ed286-330">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="ed286-331">Кроме того, публикация сертификата клиента (на серверах переднего плана) или проверка того, был ли уже опубликован сертификат клиента.</span><span class="sxs-lookup"><span data-stu-id="ed286-331">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-332">Директор</span><span class="sxs-lookup"><span data-stu-id="ed286-332">Directors</span></span></p></td>
<td><p><span data-ttu-id="ed286-333">Служба веб-совместимости Lync Server</span><span class="sxs-lookup"><span data-stu-id="ed286-333">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="ed286-334">80</span><span class="sxs-lookup"><span data-stu-id="ed286-334">80</span></span></p></td>
<td><p><span data-ttu-id="ed286-335">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-335">TCP</span></span></p></td>
<td><p><span data-ttu-id="ed286-p105">Используется для исходного подключения от директоров к полным доменным именам в веб-ферме (URL-адреса используются по веб-компонентам IIS). При обычной работе происходит переключение на трафик HTTPS с использованием порта 443 и протокола TCP.</span><span class="sxs-lookup"><span data-stu-id="ed286-p105">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components). In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-338">Директор</span><span class="sxs-lookup"><span data-stu-id="ed286-338">Directors</span></span></p></td>
<td><p><span data-ttu-id="ed286-339">Служба веб-совместимости Lync Server</span><span class="sxs-lookup"><span data-stu-id="ed286-339">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="ed286-340">443</span><span class="sxs-lookup"><span data-stu-id="ed286-340">443</span></span></p></td>
<td><p><span data-ttu-id="ed286-341">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ed286-341">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="ed286-342">Используется для подключения от директоров к полным доменным именам в веб-ферме (URL-адреса используются по веб-компонентам IIS).</span><span class="sxs-lookup"><span data-stu-id="ed286-342">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-343">Директор</span><span class="sxs-lookup"><span data-stu-id="ed286-343">Directors</span></span></p></td>
<td><p><span data-ttu-id="ed286-344">Служба Front-End Lync Server</span><span class="sxs-lookup"><span data-stu-id="ed286-344">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="ed286-345">5061</span><span class="sxs-lookup"><span data-stu-id="ed286-345">5061</span></span></p></td>
<td><p><span data-ttu-id="ed286-346">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-346">TCP</span></span></p></td>
<td><p><span data-ttu-id="ed286-347">Используется для внутренних подключений между серверами и для клиентских подключений.</span><span class="sxs-lookup"><span data-stu-id="ed286-347">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-348">Серверы-посредники</span><span class="sxs-lookup"><span data-stu-id="ed286-348">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-349">Служба-посредник по Lync Server</span><span class="sxs-lookup"><span data-stu-id="ed286-349">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="ed286-350">5070</span><span class="sxs-lookup"><span data-stu-id="ed286-350">5070</span></span></p></td>
<td><p><span data-ttu-id="ed286-351">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-351">TCP</span></span></p></td>
<td><p><span data-ttu-id="ed286-352">Используется сервером-посредником для входящих запросов от сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="ed286-352">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-353">Серверы-посредники</span><span class="sxs-lookup"><span data-stu-id="ed286-353">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-354">Служба-посредник по Lync Server</span><span class="sxs-lookup"><span data-stu-id="ed286-354">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="ed286-355">5067</span><span class="sxs-lookup"><span data-stu-id="ed286-355">5067</span></span></p></td>
<td><p><span data-ttu-id="ed286-356">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ed286-356">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="ed286-357">Используется для входящих SIP-запросов от шлюза ТСОП.</span><span class="sxs-lookup"><span data-stu-id="ed286-357">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-358">Серверы-посредники</span><span class="sxs-lookup"><span data-stu-id="ed286-358">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-359">Служба-посредник по Lync Server</span><span class="sxs-lookup"><span data-stu-id="ed286-359">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="ed286-360">5068</span><span class="sxs-lookup"><span data-stu-id="ed286-360">5068</span></span></p></td>
<td><p><span data-ttu-id="ed286-361">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-361">TCP</span></span></p></td>
<td><p><span data-ttu-id="ed286-362">Используется для входящих SIP-запросов от шлюза ТСОП.</span><span class="sxs-lookup"><span data-stu-id="ed286-362">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-363">Серверы-посредники</span><span class="sxs-lookup"><span data-stu-id="ed286-363">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="ed286-364">Служба-посредник по Lync Server</span><span class="sxs-lookup"><span data-stu-id="ed286-364">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="ed286-365">5070</span><span class="sxs-lookup"><span data-stu-id="ed286-365">5070</span></span></p></td>
<td><p><span data-ttu-id="ed286-366">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ed286-366">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="ed286-367">Используется для SIP-запросов от серверов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="ed286-367">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-368">Сервер переднего плана сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="ed286-368">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="ed286-369">SIP-запрос сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="ed286-369">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="ed286-370">5041</span><span class="sxs-lookup"><span data-stu-id="ed286-370">5041</span></span></p></td>
<td><p><span data-ttu-id="ed286-371">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ed286-371">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-372">Сервер переднего плана сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="ed286-372">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="ed286-373">Платформа Windows Communication Foundation (WCF) для сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="ed286-373">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="ed286-374">881</span><span class="sxs-lookup"><span data-stu-id="ed286-374">881</span></span></p></td>
<td><p><span data-ttu-id="ed286-375">TCP (TLS) и TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ed286-375">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-376">Сервер переднего плана сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="ed286-376">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="ed286-377">Служба передачи файлов для сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="ed286-377">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="ed286-378">443</span><span class="sxs-lookup"><span data-stu-id="ed286-378">443</span></span></p></td>
<td><p><span data-ttu-id="ed286-379">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ed286-379">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="ed286-380">Для некоторых сценариев удаленного управления звонками требуется TCP-соединение между сервером переднего плана или директором и УАТС.</span><span class="sxs-lookup"><span data-stu-id="ed286-380">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="ed286-381">Несмотря на то, что Lync Server больше не использует TCP-порт 5060, во время развертывания удаленного управления звонками создается конфигурация доверенных серверов, которая связывает полное доменное имя сервера по линии RCC с портом TCP, который будет использоваться сервером переднего плана или директором для подключения к системе УАТС.</span><span class="sxs-lookup"><span data-stu-id="ed286-381">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="ed286-382">Для получения дополнительных сведений обратитесь к командлету <STRONG>кструстедаппликатионкомпутер</STRONG> в документации по консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ed286-382">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="ed286-383">Для пулов, использующих только аппаратную балансировку нагрузки (без балансировки нагрузки на DNS), в следующей таблице показаны порты, которые должны открыть аппаратную подсистему балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="ed286-383">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="ed286-384">Порты аппаратного балансировщика нагрузки при использовании только аппаратной балансировки нагрузки</span><span class="sxs-lookup"><span data-stu-id="ed286-384">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ed286-385">Балансировщик нагрузки</span><span class="sxs-lookup"><span data-stu-id="ed286-385">Load Balancer</span></span></th>
<th><span data-ttu-id="ed286-386">Порт</span><span class="sxs-lookup"><span data-stu-id="ed286-386">Port</span></span></th>
<th><span data-ttu-id="ed286-387">Протокол</span><span class="sxs-lookup"><span data-stu-id="ed286-387">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed286-388">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-388">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ed286-389">5061</span><span class="sxs-lookup"><span data-stu-id="ed286-389">5061</span></span></p></td>
<td><p><span data-ttu-id="ed286-390">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ed286-390">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-391">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-391">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ed286-392">444</span><span class="sxs-lookup"><span data-stu-id="ed286-392">444</span></span></p></td>
<td><p><span data-ttu-id="ed286-393">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ed286-393">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-394">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-394">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ed286-395">135</span><span class="sxs-lookup"><span data-stu-id="ed286-395">135</span></span></p></td>
<td><p><span data-ttu-id="ed286-396">DCOM и удаленный вызов процедур (RPC)</span><span class="sxs-lookup"><span data-stu-id="ed286-396">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-397">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-397">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ed286-398">80</span><span class="sxs-lookup"><span data-stu-id="ed286-398">80</span></span></p></td>
<td><p><span data-ttu-id="ed286-399">HTTP</span><span class="sxs-lookup"><span data-stu-id="ed286-399">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-400">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-400">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ed286-401">8080</span><span class="sxs-lookup"><span data-stu-id="ed286-401">8080</span></span></p></td>
<td><p><span data-ttu-id="ed286-402">TCP-получение клиентом и устройством корневого сертификата с сервера переднего плана — клиенты и устройства, прошедшие проверку подлинности NTLM</span><span class="sxs-lookup"><span data-stu-id="ed286-402">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-403">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-403">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ed286-404">443</span><span class="sxs-lookup"><span data-stu-id="ed286-404">443</span></span></p></td>
<td><p><span data-ttu-id="ed286-405">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ed286-405">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-406">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-406">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ed286-407">4443</span><span class="sxs-lookup"><span data-stu-id="ed286-407">4443</span></span></p></td>
<td><p><span data-ttu-id="ed286-408">HTTPS (от обратного прокси-сервера)</span><span class="sxs-lookup"><span data-stu-id="ed286-408">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-409">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-409">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ed286-410">5072</span><span class="sxs-lookup"><span data-stu-id="ed286-410">5072</span></span></p></td>
<td><p><span data-ttu-id="ed286-411">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-411">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-412">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-412">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ed286-413">5073</span><span class="sxs-lookup"><span data-stu-id="ed286-413">5073</span></span></p></td>
<td><p><span data-ttu-id="ed286-414">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-414">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-415">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-415">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ed286-416">5075</span><span class="sxs-lookup"><span data-stu-id="ed286-416">5075</span></span></p></td>
<td><p><span data-ttu-id="ed286-417">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-417">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-418">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-418">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ed286-419">5076</span><span class="sxs-lookup"><span data-stu-id="ed286-419">5076</span></span></p></td>
<td><p><span data-ttu-id="ed286-420">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-420">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-421">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-421">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ed286-422">5071</span><span class="sxs-lookup"><span data-stu-id="ed286-422">5071</span></span></p></td>
<td><p><span data-ttu-id="ed286-423">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-423">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-424">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-424">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ed286-425">5080</span><span class="sxs-lookup"><span data-stu-id="ed286-425">5080</span></span></p></td>
<td><p><span data-ttu-id="ed286-426">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-426">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-427">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-427">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ed286-428">448</span><span class="sxs-lookup"><span data-stu-id="ed286-428">448</span></span></p></td>
<td><p><span data-ttu-id="ed286-429">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-429">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-430">Балансировщик нагрузки сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="ed286-430">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ed286-431">5070</span><span class="sxs-lookup"><span data-stu-id="ed286-431">5070</span></span></p></td>
<td><p><span data-ttu-id="ed286-432">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-432">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-433">Балансировщик нагрузки на сервере переднего плана (если в пуле также работает сервер-посредник)</span><span class="sxs-lookup"><span data-stu-id="ed286-433">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="ed286-434">5070</span><span class="sxs-lookup"><span data-stu-id="ed286-434">5070</span></span></p></td>
<td><p><span data-ttu-id="ed286-435">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-435">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-436">Подсистема балансировки нагрузки режиссера</span><span class="sxs-lookup"><span data-stu-id="ed286-436">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="ed286-437">443</span><span class="sxs-lookup"><span data-stu-id="ed286-437">443</span></span></p></td>
<td><p><span data-ttu-id="ed286-438">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ed286-438">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-439">Подсистема балансировки нагрузки режиссера</span><span class="sxs-lookup"><span data-stu-id="ed286-439">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="ed286-440">444</span><span class="sxs-lookup"><span data-stu-id="ed286-440">444</span></span></p></td>
<td><p><span data-ttu-id="ed286-441">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ed286-441">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-442">Подсистема балансировки нагрузки режиссера</span><span class="sxs-lookup"><span data-stu-id="ed286-442">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="ed286-443">5061</span><span class="sxs-lookup"><span data-stu-id="ed286-443">5061</span></span></p></td>
<td><p><span data-ttu-id="ed286-444">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-444">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-445">Подсистема балансировки нагрузки режиссера</span><span class="sxs-lookup"><span data-stu-id="ed286-445">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="ed286-446">4443</span><span class="sxs-lookup"><span data-stu-id="ed286-446">4443</span></span></p></td>
<td><p><span data-ttu-id="ed286-447">HTTPS (от обратного прокси-сервера)</span><span class="sxs-lookup"><span data-stu-id="ed286-447">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ed286-448">Для пулов переднего плана и пулов директоров, использующих балансировку нагрузки на DNS, также должен быть развернут аппаратный балансировщик нагрузки.</span><span class="sxs-lookup"><span data-stu-id="ed286-448">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed.</span></span> <span data-ttu-id="ed286-449">В следующей таблице приведены порты, которые должны быть открыты на этих аппаратных подсистемах балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="ed286-449">The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="ed286-450">Порты аппаратного балансировщика нагрузки при использовании балансировки нагрузки на DNS</span><span class="sxs-lookup"><span data-stu-id="ed286-450">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ed286-451">Балансировщик нагрузки</span><span class="sxs-lookup"><span data-stu-id="ed286-451">Load Balancer</span></span></th>
<th><span data-ttu-id="ed286-452">Порт</span><span class="sxs-lookup"><span data-stu-id="ed286-452">Port</span></span></th>
<th><span data-ttu-id="ed286-453">Протокол</span><span class="sxs-lookup"><span data-stu-id="ed286-453">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed286-454">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-454">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ed286-455">80</span><span class="sxs-lookup"><span data-stu-id="ed286-455">80</span></span></p></td>
<td><p><span data-ttu-id="ed286-456">HTTP</span><span class="sxs-lookup"><span data-stu-id="ed286-456">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-457">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-457">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ed286-458">443</span><span class="sxs-lookup"><span data-stu-id="ed286-458">443</span></span></p></td>
<td><p><span data-ttu-id="ed286-459">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ed286-459">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-460">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-460">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ed286-461">8080</span><span class="sxs-lookup"><span data-stu-id="ed286-461">8080</span></span></p></td>
<td><p><span data-ttu-id="ed286-462">TCP-получение клиентом и устройством корневого сертификата с сервера переднего плана — клиенты и устройства, прошедшие проверку подлинности NTLM</span><span class="sxs-lookup"><span data-stu-id="ed286-462">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-463">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="ed286-463">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ed286-464">4443</span><span class="sxs-lookup"><span data-stu-id="ed286-464">4443</span></span></p></td>
<td><p><span data-ttu-id="ed286-465">HTTPS (от обратного прокси-сервера)</span><span class="sxs-lookup"><span data-stu-id="ed286-465">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-466">Подсистема балансировки нагрузки режиссера</span><span class="sxs-lookup"><span data-stu-id="ed286-466">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="ed286-467">443</span><span class="sxs-lookup"><span data-stu-id="ed286-467">443</span></span></p></td>
<td><p><span data-ttu-id="ed286-468">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ed286-468">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-469">Подсистема балансировки нагрузки режиссера</span><span class="sxs-lookup"><span data-stu-id="ed286-469">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="ed286-470">4443</span><span class="sxs-lookup"><span data-stu-id="ed286-470">4443</span></span></p></td>
<td><p><span data-ttu-id="ed286-471">HTTPS (от обратного прокси-сервера)</span><span class="sxs-lookup"><span data-stu-id="ed286-471">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="ed286-472">Необходимые порты клиента</span><span class="sxs-lookup"><span data-stu-id="ed286-472">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ed286-473">Компонент</span><span class="sxs-lookup"><span data-stu-id="ed286-473">Component</span></span></th>
<th><span data-ttu-id="ed286-474">Порт</span><span class="sxs-lookup"><span data-stu-id="ed286-474">Port</span></span></th>
<th><span data-ttu-id="ed286-475">Протокол</span><span class="sxs-lookup"><span data-stu-id="ed286-475">Protocol</span></span></th>
<th><span data-ttu-id="ed286-476">Примечания</span><span class="sxs-lookup"><span data-stu-id="ed286-476">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed286-477">Клиенты</span><span class="sxs-lookup"><span data-stu-id="ed286-477">Clients</span></span></p></td>
<td><p><span data-ttu-id="ed286-478">67/68</span><span class="sxs-lookup"><span data-stu-id="ed286-478">67/68</span></span></p></td>
<td><p><span data-ttu-id="ed286-479">-</span><span class="sxs-lookup"><span data-stu-id="ed286-479">DHCP</span></span></p></td>
<td><p><span data-ttu-id="ed286-480">Используется Lync Server для поиска полного доменного имени регистратора (то есть в случае сбоя DNS SRV и ненастроенных параметров вручную).</span><span class="sxs-lookup"><span data-stu-id="ed286-480">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-481">Клиенты</span><span class="sxs-lookup"><span data-stu-id="ed286-481">Clients</span></span></p></td>
<td><p><span data-ttu-id="ed286-482">443</span><span class="sxs-lookup"><span data-stu-id="ed286-482">443</span></span></p></td>
<td><p><span data-ttu-id="ed286-483">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ed286-483">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="ed286-484">Используется для трафика SIP от клиента к серверу для доступа внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="ed286-484">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-485">Клиенты</span><span class="sxs-lookup"><span data-stu-id="ed286-485">Clients</span></span></p></td>
<td><p><span data-ttu-id="ed286-486">443</span><span class="sxs-lookup"><span data-stu-id="ed286-486">443</span></span></p></td>
<td><p><span data-ttu-id="ed286-487">TCP (PSOM/TLS)</span><span class="sxs-lookup"><span data-stu-id="ed286-487">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="ed286-488">Используется для доступа внешних пользователей к сеансам веб-конференций.</span><span class="sxs-lookup"><span data-stu-id="ed286-488">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-489">Клиенты</span><span class="sxs-lookup"><span data-stu-id="ed286-489">Clients</span></span></p></td>
<td><p><span data-ttu-id="ed286-490">443</span><span class="sxs-lookup"><span data-stu-id="ed286-490">443</span></span></p></td>
<td><p><span data-ttu-id="ed286-491">TCP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="ed286-491">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="ed286-492">Используется для доступа внешних пользователей к сеансам аудио-и видеосвязи и мультимедиа (TCP)</span><span class="sxs-lookup"><span data-stu-id="ed286-492">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-493">Клиенты</span><span class="sxs-lookup"><span data-stu-id="ed286-493">Clients</span></span></p></td>
<td><p><span data-ttu-id="ed286-494">3478</span><span class="sxs-lookup"><span data-stu-id="ed286-494">3478</span></span></p></td>
<td><p><span data-ttu-id="ed286-495">UDP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="ed286-495">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="ed286-496">Используется для доступа внешних пользователей к сеансам аудио-и видеосвязи и мультимедиа (UDP)</span><span class="sxs-lookup"><span data-stu-id="ed286-496">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-497">Клиенты</span><span class="sxs-lookup"><span data-stu-id="ed286-497">Clients</span></span></p></td>
<td><p><span data-ttu-id="ed286-498">5061</span><span class="sxs-lookup"><span data-stu-id="ed286-498">5061</span></span></p></td>
<td><p><span data-ttu-id="ed286-499">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ed286-499">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="ed286-500">Используется для трафика SIP от клиента к серверу для доступа внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="ed286-500">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-501">Клиенты</span><span class="sxs-lookup"><span data-stu-id="ed286-501">Clients</span></span></p></td>
<td><p><span data-ttu-id="ed286-502">6891-6901</span><span class="sxs-lookup"><span data-stu-id="ed286-502">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="ed286-503">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-503">TCP</span></span></p></td>
<td><p><span data-ttu-id="ed286-504">Используется для передачи файлов между клиентами Lync и предыдущими клиентами (клиентами Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007 и Live Communications Server 2005).</span><span class="sxs-lookup"><span data-stu-id="ed286-504">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-505">Клиенты</span><span class="sxs-lookup"><span data-stu-id="ed286-505">Clients</span></span></p></td>
<td><p><span data-ttu-id="ed286-506">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="ed286-506">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="ed286-507">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="ed286-507">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="ed286-508">Диапазон портов аудиоподсистемы (необходимо минимум 20 портов)</span><span class="sxs-lookup"><span data-stu-id="ed286-508">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-509">Клиенты</span><span class="sxs-lookup"><span data-stu-id="ed286-509">Clients</span></span></p></td>
<td><p><span data-ttu-id="ed286-510">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="ed286-510">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="ed286-511">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="ed286-511">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="ed286-512">Диапазон портов для видео (необходимо минимум 20 портов).</span><span class="sxs-lookup"><span data-stu-id="ed286-512">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-513">Клиенты</span><span class="sxs-lookup"><span data-stu-id="ed286-513">Clients</span></span></p></td>
<td><p><span data-ttu-id="ed286-514">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="ed286-514">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="ed286-515">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-515">TCP</span></span></p></td>
<td><p><span data-ttu-id="ed286-516">Передача файлов в одноранговой сети (для передачи файлов конференц-связи клиенты используют PSOM).</span><span class="sxs-lookup"><span data-stu-id="ed286-516">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed286-517">Клиенты</span><span class="sxs-lookup"><span data-stu-id="ed286-517">Clients</span></span></p></td>
<td><p><span data-ttu-id="ed286-518">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="ed286-518">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="ed286-519">TCP</span><span class="sxs-lookup"><span data-stu-id="ed286-519">TCP</span></span></p></td>
<td><p><span data-ttu-id="ed286-520">Общий доступ к приложениям.</span><span class="sxs-lookup"><span data-stu-id="ed286-520">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed286-521">Телефон общего пользования Aastra 6721ip</span><span class="sxs-lookup"><span data-stu-id="ed286-521">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="ed286-522">Стационарный телефон Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="ed286-522">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="ed286-523">IP-телефон HP 4110 (телефон общего доступа)</span><span class="sxs-lookup"><span data-stu-id="ed286-523">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="ed286-524">IP-телефон HP 4120 (стационарный телефон)</span><span class="sxs-lookup"><span data-stu-id="ed286-524">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="ed286-525">IP-телефон общего доступа Polycom CX500</span><span class="sxs-lookup"><span data-stu-id="ed286-525">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="ed286-526">Настольный IP-телефон Polycom CX600</span><span class="sxs-lookup"><span data-stu-id="ed286-526">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="ed286-527">Настольный IP-телефон Polycom CX700</span><span class="sxs-lookup"><span data-stu-id="ed286-527">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="ed286-528">IP-телефон для конференций Polycom CX3000</span><span class="sxs-lookup"><span data-stu-id="ed286-528">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="ed286-529">67/68</span><span class="sxs-lookup"><span data-stu-id="ed286-529">67/68</span></span></p></td>
<td><p><span data-ttu-id="ed286-530">-</span><span class="sxs-lookup"><span data-stu-id="ed286-530">DHCP</span></span></p></td>
<td><p><span data-ttu-id="ed286-531">Используется перечисленными устройствами для поиска сертификата сервера Lync, подготовки полного доменного имени и полного доменного имени регистратора.</span><span class="sxs-lookup"><span data-stu-id="ed286-531">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ed286-532">**\*** Для настройки определенных портов для этих типов мультимедиа используйте командлет CsConferencingConfiguration (параметры параметры clientmediaportrangeenabled, ClientMediaPort и ClientMediaPortRange).</span><span class="sxs-lookup"><span data-stu-id="ed286-532">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ed286-533">Клиенты установки программ для Lync автоматически создают на клиентском компьютере необходимые исключения брандмауэра операционной системы.</span><span class="sxs-lookup"><span data-stu-id="ed286-533">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="ed286-534">Порты, используемые для доступа внешних пользователей, необходимы для любого сценария, в котором клиент должен пройти брандмауэр организации (например, любые внешние коммуникации или собрания, размещенные в других организациях).</span><span class="sxs-lookup"><span data-stu-id="ed286-534">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

