---
title: 'Lync Server 2013: порты и протоколы для внутренних серверов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Ports and protocols for internal servers
ms:assetid: c94063f1-e802-4a61-be90-022fc185335e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398833(v=OCS.15)
ms:contentKeyID: 48185402
ms.date: 04/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 026843216e433ebea120384209ed90f38be3437b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824374"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="f198f-102">Порты и протоколы для внутренних серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f198f-102">Ports and protocols for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f198f-103">_**Тема последнего изменения:** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="f198f-103">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="f198f-104">В этом разделе приведены общие сведения о портах и протоколах, используемых серверами, подсистемами балансировки нагрузки и клиентами в развертывании Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f198f-104">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f198f-105">Клиенты Lync и Communicator, вовлеченные в одну и ту же связь, часто называют одноранговой.</span><span class="sxs-lookup"><span data-stu-id="f198f-105">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="f198f-106">Технически, эти два клиента взаимодействуют между собой в одном сеансе, с помощью управляющего блока обмена мгновенными сообщениями (ИММКУ) в центре.</span><span class="sxs-lookup"><span data-stu-id="f198f-106">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="f198f-107">ИММКУ является компонентом сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="f198f-107">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="f198f-108">Размещение ИММКУ в требуемом рабочем канале связи позволяет записывать сведения о вызове и другие возможности, которые сервер переднего плана включит.</span><span class="sxs-lookup"><span data-stu-id="f198f-108">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="f198f-109">Взаимодействие осуществляется из динамического исходного порта на клиенте на серверный порт TLS/TCP/5061 (предполагается использование рекомендуемой безопасности транспортного уровня).</span><span class="sxs-lookup"><span data-stu-id="f198f-109">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="f198f-110">Связь между одноранговым и одноранговой связью (а также многосторонним СООБЩЕНИЕм) возможна только в том случае, если Lync Server и ИММКУ активны и доступны.</span><span class="sxs-lookup"><span data-stu-id="f198f-110">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="f198f-111">Сведения о портах и протоколах</span><span class="sxs-lookup"><span data-stu-id="f198f-111">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f198f-112">Перед запуском служб Lync Server на сервере необходимо запустить брандмауэр Windows, так как это происходит в том случае, если Lync Server открывает нужные порты в брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="f198f-112">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="f198f-113">Подробнее о настройке брандмауэра для компонентов EDGE можно узнать в статьях [Определение внешних параметров брандмауэра/V и требований к портам для Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f198f-113">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="f198f-114">В следующей таблице приводится список портов, которые должны быть открыты для каждой роли внутреннего сервера.</span><span class="sxs-lookup"><span data-stu-id="f198f-114">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="f198f-115">Необходимые порты сервера (по ролям сервера)</span><span class="sxs-lookup"><span data-stu-id="f198f-115">Required Server Ports (by Server Role)</span></span>

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
<th><span data-ttu-id="f198f-116">Роль сервера</span><span class="sxs-lookup"><span data-stu-id="f198f-116">Server role</span></span></th>
<th><span data-ttu-id="f198f-117">Имя службы</span><span class="sxs-lookup"><span data-stu-id="f198f-117">Service name</span></span></th>
<th><span data-ttu-id="f198f-118">Порт</span><span class="sxs-lookup"><span data-stu-id="f198f-118">Port</span></span></th>
<th><span data-ttu-id="f198f-119">Протокол</span><span class="sxs-lookup"><span data-stu-id="f198f-119">Protocol</span></span></th>
<th><span data-ttu-id="f198f-120">Примечания.</span><span class="sxs-lookup"><span data-stu-id="f198f-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f198f-121">Все серверы</span><span class="sxs-lookup"><span data-stu-id="f198f-121">All Servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-122">Браузер SQL</span><span class="sxs-lookup"><span data-stu-id="f198f-122">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="f198f-123">1434</span><span class="sxs-lookup"><span data-stu-id="f198f-123">1434</span></span></p></td>
<td><p><span data-ttu-id="f198f-124">UDP</span><span class="sxs-lookup"><span data-stu-id="f198f-124">UDP</span></span></p></td>
<td><p><span data-ttu-id="f198f-125">Браузер SQL для локальной реплицированной копии базы данных хранилища центрального управления.</span><span class="sxs-lookup"><span data-stu-id="f198f-125">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-126">переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-126">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-127">Клиентская служба Lync Server</span><span class="sxs-lookup"><span data-stu-id="f198f-127">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="f198f-128">5060</span><span class="sxs-lookup"><span data-stu-id="f198f-128">5060</span></span></p></td>
<td><p><span data-ttu-id="f198f-129">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-129">TCP</span></span></p></td>
<td><p><span data-ttu-id="f198f-130">При необходимости используется для статических маршрутов к доверенным службам серверами Standard Edition и серверами переднего плана, например серверами удаленного управления звонками.</span><span class="sxs-lookup"><span data-stu-id="f198f-130">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-131">переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-131">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-132">Клиентская служба Lync Server</span><span class="sxs-lookup"><span data-stu-id="f198f-132">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="f198f-133">5061</span><span class="sxs-lookup"><span data-stu-id="f198f-133">5061</span></span></p></td>
<td><p><span data-ttu-id="f198f-134">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="f198f-134">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="f198f-135">Используется серверами Standard Edition и серверами переднего плана для всех внутренних SIP-соединений между серверами (MTLS), для SIP-соединений между сервером и клиентом (TLS) и для SIP-соединений между серверами переднего плана и серверами-посредниками (MTLS).</span><span class="sxs-lookup"><span data-stu-id="f198f-135">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS).</span></span> <span data-ttu-id="f198f-136">Также используется для связи с сервером мониторинга.</span><span class="sxs-lookup"><span data-stu-id="f198f-136">Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-137">переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-137">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-138">Клиентская служба Lync Server</span><span class="sxs-lookup"><span data-stu-id="f198f-138">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="f198f-139">444</span><span class="sxs-lookup"><span data-stu-id="f198f-139">444</span></span></p></td>
<td><p><span data-ttu-id="f198f-140">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f198f-140">HTTPS</span></span></p>
<p><span data-ttu-id="f198f-141">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-141">TCP</span></span></p></td>
<td><p><span data-ttu-id="f198f-142">Используется для взаимодействия по протоколу HTTPS между фокусом (компонент Lync Server, управляющий состоянием конференции) и отдельными серверами.</span><span class="sxs-lookup"><span data-stu-id="f198f-142">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="f198f-143">Этот порт также используется для взаимодействия по протоколу TCP между бесперебойно работающими управляющими устройствами филиалов и серверами переднего плана.</span><span class="sxs-lookup"><span data-stu-id="f198f-143">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-144">переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-144">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-145">Клиентская служба Lync Server</span><span class="sxs-lookup"><span data-stu-id="f198f-145">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="f198f-146">135</span><span class="sxs-lookup"><span data-stu-id="f198f-146">135</span></span></p></td>
<td><p><span data-ttu-id="f198f-147">DCOM и удаленный вызов процедур (RPC)</span><span class="sxs-lookup"><span data-stu-id="f198f-147">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="f198f-148">Используется для операций на базе DCOM, таких как перемещение пользователей, синхронизация репликаторов пользовательских данных и адресных книг.</span><span class="sxs-lookup"><span data-stu-id="f198f-148">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-149">переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-149">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-150">Служба конференц-связи Lync Server для обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="f198f-150">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="f198f-151">5062</span><span class="sxs-lookup"><span data-stu-id="f198f-151">5062</span></span></p></td>
<td><p><span data-ttu-id="f198f-152">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-152">TCP</span></span></p></td>
<td><p><span data-ttu-id="f198f-153">Используется для входящих SIP-запросов в конференц-связи с использованием обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="f198f-153">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-154">переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-154">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-155">Служба веб-конференций Lync Server</span><span class="sxs-lookup"><span data-stu-id="f198f-155">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="f198f-156">8057</span><span class="sxs-lookup"><span data-stu-id="f198f-156">8057</span></span></p></td>
<td><p><span data-ttu-id="f198f-157">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="f198f-157">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="f198f-158">Используется для прослушивания подключений по протоколу PSOM от клиента.</span><span class="sxs-lookup"><span data-stu-id="f198f-158">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-159">переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-159">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-160">Служба совместимости веб-конференций Lync Server</span><span class="sxs-lookup"><span data-stu-id="f198f-160">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="f198f-161">8058</span><span class="sxs-lookup"><span data-stu-id="f198f-161">8058</span></span></p></td>
<td><p><span data-ttu-id="f198f-162">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="f198f-162">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="f198f-163">Используется для прослушивания подключений к постоянной общей объектной модели (PSOM) из клиента Live Meeting и предыдущих версий Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f198f-163">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-164">переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-164">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-165">Служба голосовой и видеоконференций Lync Server</span><span class="sxs-lookup"><span data-stu-id="f198f-165">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="f198f-166">5063</span><span class="sxs-lookup"><span data-stu-id="f198f-166">5063</span></span></p></td>
<td><p><span data-ttu-id="f198f-167">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-167">TCP</span></span></p></td>
<td><p><span data-ttu-id="f198f-168">Используется для входящих SIP-запросов на аудио- и видеоконференции.</span><span class="sxs-lookup"><span data-stu-id="f198f-168">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-169">переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-169">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-170">Служба голосовой и видеоконференций Lync Server</span><span class="sxs-lookup"><span data-stu-id="f198f-170">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="f198f-171">57501-65535</span><span class="sxs-lookup"><span data-stu-id="f198f-171">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="f198f-172">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="f198f-172">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="f198f-173">Диапазон портов, используемых для видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="f198f-173">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-174">переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-174">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-175">Служба веб-совместимости Lync Server</span><span class="sxs-lookup"><span data-stu-id="f198f-175">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="f198f-176">80</span><span class="sxs-lookup"><span data-stu-id="f198f-176">80</span></span></p></td>
<td><p><span data-ttu-id="f198f-177">HTTP</span><span class="sxs-lookup"><span data-stu-id="f198f-177">HTTP</span></span></p></td>
<td><p><span data-ttu-id="f198f-178">Используется для подключений от серверов переднего плана к полным доменным именам в веб-ферме (URL-адреса используются по веб-компонентам IIS), когда не используется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f198f-178">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-179">переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-179">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-180">Служба веб-совместимости Lync Server</span><span class="sxs-lookup"><span data-stu-id="f198f-180">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="f198f-181">443</span><span class="sxs-lookup"><span data-stu-id="f198f-181">443</span></span></p></td>
<td><p><span data-ttu-id="f198f-182">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f198f-182">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="f198f-183">Используется для подключений от серверов переднего плана к полным доменным именам в веб-ферме (URL-адреса используются по веб-компонентам IIS).</span><span class="sxs-lookup"><span data-stu-id="f198f-183">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-184">переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-184">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-185">Служба веб-совместимости Lync Server</span><span class="sxs-lookup"><span data-stu-id="f198f-185">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="f198f-186">8080</span><span class="sxs-lookup"><span data-stu-id="f198f-186">8080</span></span></p></td>
<td><p><span data-ttu-id="f198f-187">TCP и HTTP</span><span class="sxs-lookup"><span data-stu-id="f198f-187">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="f198f-188">Используется веб-компонентами для внешнего доступа.</span><span class="sxs-lookup"><span data-stu-id="f198f-188">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-189">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-189">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-190">Компонент веб-сервера</span><span class="sxs-lookup"><span data-stu-id="f198f-190">Web server component</span></span></p></td>
<td><p><span data-ttu-id="f198f-191">4443</span><span class="sxs-lookup"><span data-stu-id="f198f-191">4443</span></span></p></td>
<td><p><span data-ttu-id="f198f-192">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f198f-192">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="f198f-193">Связь по протоколу HTTPS (от обратного прокси-сервера) и по протоколу HTTPS между пулами переднего плана для автообнаружения входа.</span><span class="sxs-lookup"><span data-stu-id="f198f-193">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-194">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-194">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-195">Компонент веб-сервера</span><span class="sxs-lookup"><span data-stu-id="f198f-195">Web server component</span></span></p></td>
<td><p><span data-ttu-id="f198f-196">8060</span><span class="sxs-lookup"><span data-stu-id="f198f-196">8060</span></span></p></td>
<td><p><span data-ttu-id="f198f-197">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="f198f-197">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-198">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-198">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-199">Компонент веб-сервера</span><span class="sxs-lookup"><span data-stu-id="f198f-199">Web server component</span></span></p></td>
<td><p><span data-ttu-id="f198f-200">8061</span><span class="sxs-lookup"><span data-stu-id="f198f-200">8061</span></span></p></td>
<td><p><span data-ttu-id="f198f-201">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="f198f-201">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-202">переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-202">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-203">Компонент служб Mobility Services</span><span class="sxs-lookup"><span data-stu-id="f198f-203">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="f198f-204">5086</span><span class="sxs-lookup"><span data-stu-id="f198f-204">5086</span></span></p></td>
<td><p><span data-ttu-id="f198f-205">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="f198f-205">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="f198f-206">SIP-порт, используемый внутренними процессами служб Mobility Services.</span><span class="sxs-lookup"><span data-stu-id="f198f-206">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-207">переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-207">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-208">Компонент служб Mobility Services</span><span class="sxs-lookup"><span data-stu-id="f198f-208">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="f198f-209">5087</span><span class="sxs-lookup"><span data-stu-id="f198f-209">5087</span></span></p></td>
<td><p><span data-ttu-id="f198f-210">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="f198f-210">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="f198f-211">SIP-порт, используемый внутренними процессами служб Mobility Services.</span><span class="sxs-lookup"><span data-stu-id="f198f-211">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-212">переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-212">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-213">Компонент служб Mobility Services</span><span class="sxs-lookup"><span data-stu-id="f198f-213">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="f198f-214">443</span><span class="sxs-lookup"><span data-stu-id="f198f-214">443</span></span></p></td>
<td><p><span data-ttu-id="f198f-215">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f198f-215">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-216">переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-216">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-217">Служба помощника по конференциям Lync Server (Конференц-связь с телефонным подключением)</span><span class="sxs-lookup"><span data-stu-id="f198f-217">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="f198f-218">5064</span><span class="sxs-lookup"><span data-stu-id="f198f-218">5064</span></span></p></td>
<td><p><span data-ttu-id="f198f-219">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-219">TCP</span></span></p></td>
<td><p><span data-ttu-id="f198f-220">Используется для входящих SIP-запросов для конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="f198f-220">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-221">переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-221">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-222">Служба помощника по конференциям Lync Server (Конференц-связь с телефонным подключением)</span><span class="sxs-lookup"><span data-stu-id="f198f-222">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="f198f-223">5072</span><span class="sxs-lookup"><span data-stu-id="f198f-223">5072</span></span></p></td>
<td><p><span data-ttu-id="f198f-224">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-224">TCP</span></span></p></td>
<td><p><span data-ttu-id="f198f-225">Используется для входящих запросов SIP для помощника (Конференц-связь с телефонным подключением).</span><span class="sxs-lookup"><span data-stu-id="f198f-225">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-226">Серверы переднего плана, на которых также работает соотнесенный сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="f198f-226">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="f198f-227">Служба "серверное исправление Lync"</span><span class="sxs-lookup"><span data-stu-id="f198f-227">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="f198f-228">5070</span><span class="sxs-lookup"><span data-stu-id="f198f-228">5070</span></span></p></td>
<td><p><span data-ttu-id="f198f-229">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-229">TCP</span></span></p></td>
<td><p><span data-ttu-id="f198f-230">Используется сервером-посредником для входящих запросов от сервера переднего плана к серверу посреднику.</span><span class="sxs-lookup"><span data-stu-id="f198f-230">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-231">Серверы переднего плана, на которых также работает соотнесенный сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="f198f-231">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="f198f-232">Служба "серверное исправление Lync"</span><span class="sxs-lookup"><span data-stu-id="f198f-232">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="f198f-233">5067</span><span class="sxs-lookup"><span data-stu-id="f198f-233">5067</span></span></p></td>
<td><p><span data-ttu-id="f198f-234">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="f198f-234">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="f198f-235">Используется для входящих SIP-запросов от шлюза ТСОП к серверу-посреднику.</span><span class="sxs-lookup"><span data-stu-id="f198f-235">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-236">Серверы переднего плана, на которых также работает соотнесенный сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="f198f-236">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="f198f-237">Служба "серверное исправление Lync"</span><span class="sxs-lookup"><span data-stu-id="f198f-237">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="f198f-238">5068</span><span class="sxs-lookup"><span data-stu-id="f198f-238">5068</span></span></p></td>
<td><p><span data-ttu-id="f198f-239">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-239">TCP</span></span></p></td>
<td><p><span data-ttu-id="f198f-240">Используется для входящих SIP-запросов от шлюза ТСОП к серверу-посреднику.</span><span class="sxs-lookup"><span data-stu-id="f198f-240">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-241">Серверы переднего плана, на которых также работает соотнесенный сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="f198f-241">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="f198f-242">Служба "серверное исправление Lync"</span><span class="sxs-lookup"><span data-stu-id="f198f-242">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="f198f-243">5081</span><span class="sxs-lookup"><span data-stu-id="f198f-243">5081</span></span></p></td>
<td><p><span data-ttu-id="f198f-244">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-244">TCP</span></span></p></td>
<td><p><span data-ttu-id="f198f-245">Используется для исходящих SIP-запросов от сервера-посредника к шлюзу ТСОП.</span><span class="sxs-lookup"><span data-stu-id="f198f-245">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-246">Серверы переднего плана, на которых также работает соотнесенный сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="f198f-246">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="f198f-247">Служба "серверное исправление Lync"</span><span class="sxs-lookup"><span data-stu-id="f198f-247">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="f198f-248">5082</span><span class="sxs-lookup"><span data-stu-id="f198f-248">5082</span></span></p></td>
<td><p><span data-ttu-id="f198f-249">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="f198f-249">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="f198f-250">Используется для исходящих SIP-запросов от сервера-посредника к шлюзу ТСОП.</span><span class="sxs-lookup"><span data-stu-id="f198f-250">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-251">переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-251">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-252">Служба общего обмена приложениями в Lync Server</span><span class="sxs-lookup"><span data-stu-id="f198f-252">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="f198f-253">5065</span><span class="sxs-lookup"><span data-stu-id="f198f-253">5065</span></span></p></td>
<td><p><span data-ttu-id="f198f-254">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-254">TCP</span></span></p></td>
<td><p><span data-ttu-id="f198f-255">Используется для входящих SIP-запросов на прослушивание для общего доступа к приложению.</span><span class="sxs-lookup"><span data-stu-id="f198f-255">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-256">переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-256">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-257">Служба общего обмена приложениями в Lync Server</span><span class="sxs-lookup"><span data-stu-id="f198f-257">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="f198f-258">49152-65535</span><span class="sxs-lookup"><span data-stu-id="f198f-258">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="f198f-259">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-259">TCP</span></span></p></td>
<td><p><span data-ttu-id="f198f-260">Диапазон портов, используемых для общего доступа к приложению.</span><span class="sxs-lookup"><span data-stu-id="f198f-260">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-261">переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-261">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-262">Служба объявлений Lync Server конференций</span><span class="sxs-lookup"><span data-stu-id="f198f-262">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="f198f-263">5073</span><span class="sxs-lookup"><span data-stu-id="f198f-263">5073</span></span></p></td>
<td><p><span data-ttu-id="f198f-264">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-264">TCP</span></span></p></td>
<td><p><span data-ttu-id="f198f-265">Используется для входящих запросов SIP для службы объявления конференций Lync Server (то есть для конференц-связи с телефонным подключением).</span><span class="sxs-lookup"><span data-stu-id="f198f-265">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-266">переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-266">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-267">приостановки вызовов Lync Server</span><span class="sxs-lookup"><span data-stu-id="f198f-267">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="f198f-268">5075</span><span class="sxs-lookup"><span data-stu-id="f198f-268">5075</span></span></p></td>
<td><p><span data-ttu-id="f198f-269">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-269">TCP</span></span></p></td>
<td><p><span data-ttu-id="f198f-270">Используется для входящих SIP-запросов для приложения парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="f198f-270">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-271">переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-271">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-272">Служба проверки звука в Lync Server</span><span class="sxs-lookup"><span data-stu-id="f198f-272">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="f198f-273">5076</span><span class="sxs-lookup"><span data-stu-id="f198f-273">5076</span></span></p></td>
<td><p><span data-ttu-id="f198f-274">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-274">TCP</span></span></p></td>
<td><p><span data-ttu-id="f198f-275">Используется для входящих SIP-запросов для службы проверки аудиосвязи.</span><span class="sxs-lookup"><span data-stu-id="f198f-275">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-276">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-276">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-277">Не применимо</span><span class="sxs-lookup"><span data-stu-id="f198f-277">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="f198f-278">5066</span><span class="sxs-lookup"><span data-stu-id="f198f-278">5066</span></span></p></td>
<td><p><span data-ttu-id="f198f-279">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-279">TCP</span></span></p></td>
<td><p><span data-ttu-id="f198f-280">Используется для исходящего трафика в шлюзе службы Enhanced 9-1-1 (E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="f198f-280">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-281">переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-281">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-282">группы ответа Lync Server</span><span class="sxs-lookup"><span data-stu-id="f198f-282">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="f198f-283">5071</span><span class="sxs-lookup"><span data-stu-id="f198f-283">5071</span></span></p></td>
<td><p><span data-ttu-id="f198f-284">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-284">TCP</span></span></p></td>
<td><p><span data-ttu-id="f198f-285">Используется для входящих SIP-запросов для приложения группы ответа.</span><span class="sxs-lookup"><span data-stu-id="f198f-285">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-286">переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-286">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-287">группы ответа Lync Server</span><span class="sxs-lookup"><span data-stu-id="f198f-287">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="f198f-288">8404</span><span class="sxs-lookup"><span data-stu-id="f198f-288">8404</span></span></p></td>
<td><p><span data-ttu-id="f198f-289">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="f198f-289">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="f198f-290">Используется для входящих SIP-запросов для приложения группы ответа.</span><span class="sxs-lookup"><span data-stu-id="f198f-290">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-291">переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-291">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-292">Служба политики пропускной способности Lync Server</span><span class="sxs-lookup"><span data-stu-id="f198f-292">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="f198f-293">5080</span><span class="sxs-lookup"><span data-stu-id="f198f-293">5080</span></span></p></td>
<td><p><span data-ttu-id="f198f-294">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-294">TCP</span></span></p></td>
<td><p><span data-ttu-id="f198f-295">Используется для контроля допуска звонков, осуществляемого службой политики пропускной способности в отношении пограничного аудио-/видео-трафика "TURN".</span><span class="sxs-lookup"><span data-stu-id="f198f-295">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-296">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-296">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-297">Служба политики пропускной способности Lync Server</span><span class="sxs-lookup"><span data-stu-id="f198f-297">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="f198f-298">448</span><span class="sxs-lookup"><span data-stu-id="f198f-298">448</span></span></p></td>
<td><p><span data-ttu-id="f198f-299">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-299">TCP</span></span></p></td>
<td><p><span data-ttu-id="f198f-300">Используется службой политики пропускной способности Lync Server для управления допуском звонков.</span><span class="sxs-lookup"><span data-stu-id="f198f-300">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-301">Серверы переднего плана, на которых расположено центральное хранилище</span><span class="sxs-lookup"><span data-stu-id="f198f-301">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="f198f-302">Служба агента репликатора главной реплики Lync Server</span><span class="sxs-lookup"><span data-stu-id="f198f-302">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="f198f-303">445</span><span class="sxs-lookup"><span data-stu-id="f198f-303">445</span></span></p></td>
<td><p><span data-ttu-id="f198f-304">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-304">TCP</span></span></p></td>
<td><p><span data-ttu-id="f198f-305">Используется для принудительной отправки данных конфигурации из хранилища центрального управления на серверы Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f198f-305">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-306">Все серверы</span><span class="sxs-lookup"><span data-stu-id="f198f-306">All Servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-307">Браузер SQL</span><span class="sxs-lookup"><span data-stu-id="f198f-307">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="f198f-308">1434</span><span class="sxs-lookup"><span data-stu-id="f198f-308">1434</span></span></p></td>
<td><p><span data-ttu-id="f198f-309">UDP</span><span class="sxs-lookup"><span data-stu-id="f198f-309">UDP</span></span></p></td>
<td><p><span data-ttu-id="f198f-310">Браузер SQL для локальной реплицированной копии данных из хранилища центрального управления Central Management в локальном экземпляре SQL Server</span><span class="sxs-lookup"><span data-stu-id="f198f-310">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-311">Все внутренние серверы</span><span class="sxs-lookup"><span data-stu-id="f198f-311">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-312">Различные</span><span class="sxs-lookup"><span data-stu-id="f198f-312">Various</span></span></p></td>
<td><p><span data-ttu-id="f198f-313">49152-57500</span><span class="sxs-lookup"><span data-stu-id="f198f-313">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="f198f-314">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="f198f-314">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="f198f-315">Диапазон портов, используемых для аудиоконференций на всех внутренних серверах.</span><span class="sxs-lookup"><span data-stu-id="f198f-315">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="f198f-316">Используется всеми серверами, которые применяют звуковое сопровождение: серверы переднего плана (служба помощника по конференциям Lync Server, служба объявления конференций Lync Server) и сервер исправлений.</span><span class="sxs-lookup"><span data-stu-id="f198f-316">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-317">Серверы Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="f198f-317">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f198f-318">443</span><span class="sxs-lookup"><span data-stu-id="f198f-318">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f198f-319">Используется в Lync Server 2013 для подключения к серверу Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="f198f-319">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-320">Директор</span><span class="sxs-lookup"><span data-stu-id="f198f-320">Directors</span></span></p></td>
<td><p><span data-ttu-id="f198f-321">Клиентская служба Lync Server</span><span class="sxs-lookup"><span data-stu-id="f198f-321">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="f198f-322">5060</span><span class="sxs-lookup"><span data-stu-id="f198f-322">5060</span></span></p></td>
<td><p><span data-ttu-id="f198f-323">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-323">TCP</span></span></p></td>
<td><p><span data-ttu-id="f198f-324">При необходимости используется для статических маршрутов к доверенным службам, таким как серверы удаленного управления звонками.</span><span class="sxs-lookup"><span data-stu-id="f198f-324">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-325">Директор</span><span class="sxs-lookup"><span data-stu-id="f198f-325">Directors</span></span></p></td>
<td><p><span data-ttu-id="f198f-326">Клиентская служба Lync Server</span><span class="sxs-lookup"><span data-stu-id="f198f-326">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="f198f-327">444</span><span class="sxs-lookup"><span data-stu-id="f198f-327">444</span></span></p></td>
<td><p><span data-ttu-id="f198f-328">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f198f-328">HTTPS</span></span></p>
<p><span data-ttu-id="f198f-329">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-329">TCP</span></span></p></td>
<td><p><span data-ttu-id="f198f-330">Обмен данными между сервером переднего плана и сервером Директора.</span><span class="sxs-lookup"><span data-stu-id="f198f-330">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="f198f-331">Кроме того, публикация сертификата клиента (на серверах переднего плана) или проверка того, был ли сертификат уже опубликован.</span><span class="sxs-lookup"><span data-stu-id="f198f-331">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-332">Директор</span><span class="sxs-lookup"><span data-stu-id="f198f-332">Directors</span></span></p></td>
<td><p><span data-ttu-id="f198f-333">Служба веб-совместимости Lync Server</span><span class="sxs-lookup"><span data-stu-id="f198f-333">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="f198f-334">80</span><span class="sxs-lookup"><span data-stu-id="f198f-334">80</span></span></p></td>
<td><p><span data-ttu-id="f198f-335">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-335">TCP</span></span></p></td>
<td><p><span data-ttu-id="f198f-p105">Используется для исходного подключения от директоров к полным доменным именам в веб-ферме (URL-адреса используются по веб-компонентам IIS). При обычной работе происходит переключение на трафик HTTPS с использованием порта 443 и протокола TCP.</span><span class="sxs-lookup"><span data-stu-id="f198f-p105">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components). In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-338">Директор</span><span class="sxs-lookup"><span data-stu-id="f198f-338">Directors</span></span></p></td>
<td><p><span data-ttu-id="f198f-339">Служба веб-совместимости Lync Server</span><span class="sxs-lookup"><span data-stu-id="f198f-339">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="f198f-340">443</span><span class="sxs-lookup"><span data-stu-id="f198f-340">443</span></span></p></td>
<td><p><span data-ttu-id="f198f-341">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f198f-341">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="f198f-342">Используется для подключения от директоров к полным доменным именам в веб-ферме (URL-адреса используются по веб-компонентам IIS).</span><span class="sxs-lookup"><span data-stu-id="f198f-342">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-343">Директоры</span><span class="sxs-lookup"><span data-stu-id="f198f-343">Directors</span></span></p></td>
<td><p><span data-ttu-id="f198f-344">Клиентская служба Lync Server</span><span class="sxs-lookup"><span data-stu-id="f198f-344">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="f198f-345">5061</span><span class="sxs-lookup"><span data-stu-id="f198f-345">5061</span></span></p></td>
<td><p><span data-ttu-id="f198f-346">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-346">TCP</span></span></p></td>
<td><p><span data-ttu-id="f198f-347">Используется для внутренних подключений между серверами и для клиентских подключений.</span><span class="sxs-lookup"><span data-stu-id="f198f-347">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-348">посредники</span><span class="sxs-lookup"><span data-stu-id="f198f-348">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-349">Служба "серверное исправление Lync"</span><span class="sxs-lookup"><span data-stu-id="f198f-349">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="f198f-350">5070</span><span class="sxs-lookup"><span data-stu-id="f198f-350">5070</span></span></p></td>
<td><p><span data-ttu-id="f198f-351">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-351">TCP</span></span></p></td>
<td><p><span data-ttu-id="f198f-352">Используется сервером-посредником для входящих запросов от сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="f198f-352">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-353">посредники</span><span class="sxs-lookup"><span data-stu-id="f198f-353">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-354">Служба "серверное исправление Lync"</span><span class="sxs-lookup"><span data-stu-id="f198f-354">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="f198f-355">5067</span><span class="sxs-lookup"><span data-stu-id="f198f-355">5067</span></span></p></td>
<td><p><span data-ttu-id="f198f-356">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="f198f-356">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="f198f-357">Используется для входящих SIP-запросов от шлюза ТСОП.</span><span class="sxs-lookup"><span data-stu-id="f198f-357">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-358">Серверы-посредники</span><span class="sxs-lookup"><span data-stu-id="f198f-358">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-359">Служба "серверное исправление Lync"</span><span class="sxs-lookup"><span data-stu-id="f198f-359">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="f198f-360">5068</span><span class="sxs-lookup"><span data-stu-id="f198f-360">5068</span></span></p></td>
<td><p><span data-ttu-id="f198f-361">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-361">TCP</span></span></p></td>
<td><p><span data-ttu-id="f198f-362">Используется для входящих SIP-запросов от шлюза ТСОП.</span><span class="sxs-lookup"><span data-stu-id="f198f-362">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-363">Серверы-посредники</span><span class="sxs-lookup"><span data-stu-id="f198f-363">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="f198f-364">Служба "серверное исправление Lync"</span><span class="sxs-lookup"><span data-stu-id="f198f-364">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="f198f-365">5070</span><span class="sxs-lookup"><span data-stu-id="f198f-365">5070</span></span></p></td>
<td><p><span data-ttu-id="f198f-366">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="f198f-366">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="f198f-367">Используется для SIP-запросов от серверов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="f198f-367">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-368">Сервер переднего плана сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="f198f-368">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="f198f-369">SIP-запрос сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="f198f-369">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="f198f-370">5041</span><span class="sxs-lookup"><span data-stu-id="f198f-370">5041</span></span></p></td>
<td><p><span data-ttu-id="f198f-371">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="f198f-371">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-372">Сервер переднего плана сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="f198f-372">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="f198f-373">Платформа Windows Communication Foundation (WCF) для сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="f198f-373">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="f198f-374">881</span><span class="sxs-lookup"><span data-stu-id="f198f-374">881</span></span></p></td>
<td><p><span data-ttu-id="f198f-375">TCP (TLS) и TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="f198f-375">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-376">Сервер переднего плана сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="f198f-376">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="f198f-377">Служба передачи файлов для сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="f198f-377">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="f198f-378">443</span><span class="sxs-lookup"><span data-stu-id="f198f-378">443</span></span></p></td>
<td><p><span data-ttu-id="f198f-379">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="f198f-379">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="f198f-380">Для некоторых сценариев с удаленным управлением звонками требуется TCP-соединение между сервером переднего плана или Директором и УАТС.</span><span class="sxs-lookup"><span data-stu-id="f198f-380">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="f198f-381">Несмотря на то, что Lync Server больше не использует TCP-порт 5060, при развертывании удаленного управления звонками вы создаете конфигурацию доверенного сервера, которая связывает полное доменное имя сервера для подключений по протоколу RCC с портом TCP, который будет использоваться интерфейсом Front End Server для подключения к системе УАТС.</span><span class="sxs-lookup"><span data-stu-id="f198f-381">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="f198f-382">Дополнительные сведения можно найти в командлете <STRONG>кструстедаппликатионкомпутер</STRONG> в документации по среде управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f198f-382">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="f198f-383">Для пулов, использующих только аппаратную балансировку нагрузки (но не балансировку нагрузки DNS), в таблице ниже приведены порты, которые должны быть открыты для аппаратной балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="f198f-383">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="f198f-384">Порт подсистемы балансировки нагрузки для оборудования, если используется только балансировка нагрузки аппаратных средств</span><span class="sxs-lookup"><span data-stu-id="f198f-384">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f198f-385">Балансировщик нагрузки</span><span class="sxs-lookup"><span data-stu-id="f198f-385">Load Balancer</span></span></th>
<th><span data-ttu-id="f198f-386">Порт</span><span class="sxs-lookup"><span data-stu-id="f198f-386">Port</span></span></th>
<th><span data-ttu-id="f198f-387">Протокол</span><span class="sxs-lookup"><span data-stu-id="f198f-387">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f198f-388">Служба балансировки нагрузки для сервера переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-388">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f198f-389">5061</span><span class="sxs-lookup"><span data-stu-id="f198f-389">5061</span></span></p></td>
<td><p><span data-ttu-id="f198f-390">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="f198f-390">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-391">Служба балансировки нагрузки для сервера переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-391">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f198f-392">444</span><span class="sxs-lookup"><span data-stu-id="f198f-392">444</span></span></p></td>
<td><p><span data-ttu-id="f198f-393">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f198f-393">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-394">Служба балансировки нагрузки для сервера переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-394">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f198f-395">135</span><span class="sxs-lookup"><span data-stu-id="f198f-395">135</span></span></p></td>
<td><p><span data-ttu-id="f198f-396">DCOM и удаленный вызов процедур (RPC)</span><span class="sxs-lookup"><span data-stu-id="f198f-396">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-397">Служба балансировки нагрузки для сервера переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-397">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f198f-398">80</span><span class="sxs-lookup"><span data-stu-id="f198f-398">80</span></span></p></td>
<td><p><span data-ttu-id="f198f-399">HTTP</span><span class="sxs-lookup"><span data-stu-id="f198f-399">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-400">Служба балансировки нагрузки для сервера переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-400">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f198f-401">8080</span><span class="sxs-lookup"><span data-stu-id="f198f-401">8080</span></span></p></td>
<td><p><span data-ttu-id="f198f-402">TCP-клиенты и устройства, подлинность которых проверяется с помощью NTLM на сервере переднего плана и на устройствах.</span><span class="sxs-lookup"><span data-stu-id="f198f-402">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-403">Служба балансировки нагрузки для сервера переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-403">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f198f-404">443</span><span class="sxs-lookup"><span data-stu-id="f198f-404">443</span></span></p></td>
<td><p><span data-ttu-id="f198f-405">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f198f-405">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-406">Служба балансировки нагрузки для сервера переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-406">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f198f-407">4443</span><span class="sxs-lookup"><span data-stu-id="f198f-407">4443</span></span></p></td>
<td><p><span data-ttu-id="f198f-408">HTTPS (от обратного прокси-сервера)</span><span class="sxs-lookup"><span data-stu-id="f198f-408">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-409">Служба балансировки нагрузки для сервера переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-409">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f198f-410">5072</span><span class="sxs-lookup"><span data-stu-id="f198f-410">5072</span></span></p></td>
<td><p><span data-ttu-id="f198f-411">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-411">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-412">Служба балансировки нагрузки для сервера переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-412">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f198f-413">5073</span><span class="sxs-lookup"><span data-stu-id="f198f-413">5073</span></span></p></td>
<td><p><span data-ttu-id="f198f-414">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-414">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-415">Служба балансировки нагрузки для сервера переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-415">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f198f-416">5075</span><span class="sxs-lookup"><span data-stu-id="f198f-416">5075</span></span></p></td>
<td><p><span data-ttu-id="f198f-417">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-417">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-418">Служба балансировки нагрузки для сервера переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-418">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f198f-419">5076</span><span class="sxs-lookup"><span data-stu-id="f198f-419">5076</span></span></p></td>
<td><p><span data-ttu-id="f198f-420">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-420">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-421">Служба балансировки нагрузки для сервера переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-421">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f198f-422">5071</span><span class="sxs-lookup"><span data-stu-id="f198f-422">5071</span></span></p></td>
<td><p><span data-ttu-id="f198f-423">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-423">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-424">Служба балансировки нагрузки для сервера переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-424">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f198f-425">5080</span><span class="sxs-lookup"><span data-stu-id="f198f-425">5080</span></span></p></td>
<td><p><span data-ttu-id="f198f-426">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-426">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-427">Служба балансировки нагрузки для сервера переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-427">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f198f-428">448</span><span class="sxs-lookup"><span data-stu-id="f198f-428">448</span></span></p></td>
<td><p><span data-ttu-id="f198f-429">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-429">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-430">Балансировщик нагрузки сервера исправлений</span><span class="sxs-lookup"><span data-stu-id="f198f-430">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f198f-431">5070</span><span class="sxs-lookup"><span data-stu-id="f198f-431">5070</span></span></p></td>
<td><p><span data-ttu-id="f198f-432">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-432">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-433">Подсистема балансировки нагрузки на сервер переднего плана (если пул также запускает сервер-посредник)</span><span class="sxs-lookup"><span data-stu-id="f198f-433">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="f198f-434">5070</span><span class="sxs-lookup"><span data-stu-id="f198f-434">5070</span></span></p></td>
<td><p><span data-ttu-id="f198f-435">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-435">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-436">Подсистема балансировки нагрузки режиссера</span><span class="sxs-lookup"><span data-stu-id="f198f-436">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="f198f-437">443</span><span class="sxs-lookup"><span data-stu-id="f198f-437">443</span></span></p></td>
<td><p><span data-ttu-id="f198f-438">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f198f-438">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-439">Подсистема балансировки нагрузки режиссера</span><span class="sxs-lookup"><span data-stu-id="f198f-439">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="f198f-440">444</span><span class="sxs-lookup"><span data-stu-id="f198f-440">444</span></span></p></td>
<td><p><span data-ttu-id="f198f-441">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f198f-441">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-442">Подсистема балансировки нагрузки режиссера</span><span class="sxs-lookup"><span data-stu-id="f198f-442">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="f198f-443">5061</span><span class="sxs-lookup"><span data-stu-id="f198f-443">5061</span></span></p></td>
<td><p><span data-ttu-id="f198f-444">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-444">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-445">Подсистема балансировки нагрузки режиссера</span><span class="sxs-lookup"><span data-stu-id="f198f-445">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="f198f-446">4443</span><span class="sxs-lookup"><span data-stu-id="f198f-446">4443</span></span></p></td>
<td><p><span data-ttu-id="f198f-447">HTTPS (от обратного прокси-сервера)</span><span class="sxs-lookup"><span data-stu-id="f198f-447">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f198f-448">Для пулов и пулов, использующих балансировку нагрузки DNS, также должны быть развернуты аппаратные средства балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="f198f-448">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed.</span></span> <span data-ttu-id="f198f-449">В таблице ниже показаны порты, которые должны быть открыты на этих аппаратных подсистемах балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="f198f-449">The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="f198f-450">Порт подсистемы балансировки нагрузки для оборудования при использовании балансировки нагрузки DNS</span><span class="sxs-lookup"><span data-stu-id="f198f-450">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f198f-451">Балансировщик нагрузки</span><span class="sxs-lookup"><span data-stu-id="f198f-451">Load Balancer</span></span></th>
<th><span data-ttu-id="f198f-452">Порт</span><span class="sxs-lookup"><span data-stu-id="f198f-452">Port</span></span></th>
<th><span data-ttu-id="f198f-453">Протокол</span><span class="sxs-lookup"><span data-stu-id="f198f-453">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f198f-454">Служба балансировки нагрузки для сервера переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-454">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f198f-455">80</span><span class="sxs-lookup"><span data-stu-id="f198f-455">80</span></span></p></td>
<td><p><span data-ttu-id="f198f-456">HTTP</span><span class="sxs-lookup"><span data-stu-id="f198f-456">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-457">Служба балансировки нагрузки для сервера переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-457">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f198f-458">443</span><span class="sxs-lookup"><span data-stu-id="f198f-458">443</span></span></p></td>
<td><p><span data-ttu-id="f198f-459">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f198f-459">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-460">Служба балансировки нагрузки для сервера переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-460">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f198f-461">8080</span><span class="sxs-lookup"><span data-stu-id="f198f-461">8080</span></span></p></td>
<td><p><span data-ttu-id="f198f-462">TCP-клиенты и устройства, подлинность которых проверяется с помощью NTLM на сервере переднего плана и на устройствах.</span><span class="sxs-lookup"><span data-stu-id="f198f-462">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-463">Служба балансировки нагрузки для сервера переднего плана</span><span class="sxs-lookup"><span data-stu-id="f198f-463">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f198f-464">4443</span><span class="sxs-lookup"><span data-stu-id="f198f-464">4443</span></span></p></td>
<td><p><span data-ttu-id="f198f-465">HTTPS (от обратного прокси-сервера)</span><span class="sxs-lookup"><span data-stu-id="f198f-465">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-466">Подсистема балансировки нагрузки режиссера</span><span class="sxs-lookup"><span data-stu-id="f198f-466">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="f198f-467">443</span><span class="sxs-lookup"><span data-stu-id="f198f-467">443</span></span></p></td>
<td><p><span data-ttu-id="f198f-468">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f198f-468">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-469">Подсистема балансировки нагрузки режиссера</span><span class="sxs-lookup"><span data-stu-id="f198f-469">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="f198f-470">4443</span><span class="sxs-lookup"><span data-stu-id="f198f-470">4443</span></span></p></td>
<td><p><span data-ttu-id="f198f-471">HTTPS (от обратного прокси-сервера)</span><span class="sxs-lookup"><span data-stu-id="f198f-471">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="f198f-472">Требуемые клиентские порты</span><span class="sxs-lookup"><span data-stu-id="f198f-472">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f198f-473">Компонент</span><span class="sxs-lookup"><span data-stu-id="f198f-473">Component</span></span></th>
<th><span data-ttu-id="f198f-474">Порт</span><span class="sxs-lookup"><span data-stu-id="f198f-474">Port</span></span></th>
<th><span data-ttu-id="f198f-475">Протокол</span><span class="sxs-lookup"><span data-stu-id="f198f-475">Protocol</span></span></th>
<th><span data-ttu-id="f198f-476">Примечания.</span><span class="sxs-lookup"><span data-stu-id="f198f-476">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f198f-477">Клиенты</span><span class="sxs-lookup"><span data-stu-id="f198f-477">Clients</span></span></p></td>
<td><p><span data-ttu-id="f198f-478">67/68</span><span class="sxs-lookup"><span data-stu-id="f198f-478">67/68</span></span></p></td>
<td><p><span data-ttu-id="f198f-479">Протокол</span><span class="sxs-lookup"><span data-stu-id="f198f-479">DHCP</span></span></p></td>
<td><p><span data-ttu-id="f198f-480">Используется приложением Lync Server для поиска полного доменного имени регистратора (то есть в случае сбоя DNS SRV и ненастроенных параметров вручную).</span><span class="sxs-lookup"><span data-stu-id="f198f-480">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-481">Клиенты</span><span class="sxs-lookup"><span data-stu-id="f198f-481">Clients</span></span></p></td>
<td><p><span data-ttu-id="f198f-482">443</span><span class="sxs-lookup"><span data-stu-id="f198f-482">443</span></span></p></td>
<td><p><span data-ttu-id="f198f-483">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="f198f-483">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="f198f-484">Используется для трафика SIP между клиентом и сервером для внешнего доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="f198f-484">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-485">Клиенты</span><span class="sxs-lookup"><span data-stu-id="f198f-485">Clients</span></span></p></td>
<td><p><span data-ttu-id="f198f-486">443</span><span class="sxs-lookup"><span data-stu-id="f198f-486">443</span></span></p></td>
<td><p><span data-ttu-id="f198f-487">TCP (PSOM/TLS)</span><span class="sxs-lookup"><span data-stu-id="f198f-487">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="f198f-488">Используется для доступа внешних пользователей к сеансам веб-конференций.</span><span class="sxs-lookup"><span data-stu-id="f198f-488">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-489">Клиенты</span><span class="sxs-lookup"><span data-stu-id="f198f-489">Clients</span></span></p></td>
<td><p><span data-ttu-id="f198f-490">443</span><span class="sxs-lookup"><span data-stu-id="f198f-490">443</span></span></p></td>
<td><p><span data-ttu-id="f198f-491">TCP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="f198f-491">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="f198f-492">Используется для доступа внешних пользователей к аудио- и видеосеансам и сеансам мультимедиа (TCP)</span><span class="sxs-lookup"><span data-stu-id="f198f-492">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-493">Клиенты</span><span class="sxs-lookup"><span data-stu-id="f198f-493">Clients</span></span></p></td>
<td><p><span data-ttu-id="f198f-494">3478</span><span class="sxs-lookup"><span data-stu-id="f198f-494">3478</span></span></p></td>
<td><p><span data-ttu-id="f198f-495">UDP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="f198f-495">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="f198f-496">Используется для доступа внешних пользователей к аудио- и видеосеансам и сеансам мультимедиа (UDP)</span><span class="sxs-lookup"><span data-stu-id="f198f-496">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-497">Клиенты</span><span class="sxs-lookup"><span data-stu-id="f198f-497">Clients</span></span></p></td>
<td><p><span data-ttu-id="f198f-498">5061</span><span class="sxs-lookup"><span data-stu-id="f198f-498">5061</span></span></p></td>
<td><p><span data-ttu-id="f198f-499">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="f198f-499">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="f198f-500">Используется для трафика SIP между клиентом и сервером для внешнего доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="f198f-500">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-501">Клиенты</span><span class="sxs-lookup"><span data-stu-id="f198f-501">Clients</span></span></p></td>
<td><p><span data-ttu-id="f198f-502">6891-6901</span><span class="sxs-lookup"><span data-stu-id="f198f-502">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="f198f-503">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-503">TCP</span></span></p></td>
<td><p><span data-ttu-id="f198f-504">Используется для передачи файлов между клиентами Lync и предыдущими клиентами (клиенты из Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007 и Live Communications Server 2005).</span><span class="sxs-lookup"><span data-stu-id="f198f-504">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-505">Клиенты</span><span class="sxs-lookup"><span data-stu-id="f198f-505">Clients</span></span></p></td>
<td><p><span data-ttu-id="f198f-506">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="f198f-506">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="f198f-507">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="f198f-507">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="f198f-508">Диапазон портов для передачи аудио (требуется минимум 20 портов).</span><span class="sxs-lookup"><span data-stu-id="f198f-508">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-509">Клиенты</span><span class="sxs-lookup"><span data-stu-id="f198f-509">Clients</span></span></p></td>
<td><p><span data-ttu-id="f198f-510">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="f198f-510">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="f198f-511">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="f198f-511">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="f198f-512">Диапазон портов для передачи видео (требуется минимум 20 портов).</span><span class="sxs-lookup"><span data-stu-id="f198f-512">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-513">Клиенты</span><span class="sxs-lookup"><span data-stu-id="f198f-513">Clients</span></span></p></td>
<td><p><span data-ttu-id="f198f-514">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="f198f-514">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="f198f-515">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-515">TCP</span></span></p></td>
<td><p><span data-ttu-id="f198f-516">Одноранговая передача файлов (для передачи файлов в конференц-связи клиенты используют PSOM).</span><span class="sxs-lookup"><span data-stu-id="f198f-516">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f198f-517">Клиенты</span><span class="sxs-lookup"><span data-stu-id="f198f-517">Clients</span></span></p></td>
<td><p><span data-ttu-id="f198f-518">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="f198f-518">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="f198f-519">TCP</span><span class="sxs-lookup"><span data-stu-id="f198f-519">TCP</span></span></p></td>
<td><p><span data-ttu-id="f198f-520">Общий доступ к приложениям.</span><span class="sxs-lookup"><span data-stu-id="f198f-520">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f198f-521">общего пользования Aastra 6721ip</span><span class="sxs-lookup"><span data-stu-id="f198f-521">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="f198f-522">Стационарный телефон Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="f198f-522">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="f198f-523">HP 4110 (телефон общего пользования)</span><span class="sxs-lookup"><span data-stu-id="f198f-523">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="f198f-524">HP 4120 (стационарный телефон)</span><span class="sxs-lookup"><span data-stu-id="f198f-524">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="f198f-525">Polycom CX500 IP Common Area Phone</span><span class="sxs-lookup"><span data-stu-id="f198f-525">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="f198f-526">Стационарный IP-телефон Polycom CX600</span><span class="sxs-lookup"><span data-stu-id="f198f-526">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="f198f-527">Стационарный IP-телефон Polycom CX700</span><span class="sxs-lookup"><span data-stu-id="f198f-527">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="f198f-528">для IP-конференций Polycom CX3000</span><span class="sxs-lookup"><span data-stu-id="f198f-528">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="f198f-529">67/68</span><span class="sxs-lookup"><span data-stu-id="f198f-529">67/68</span></span></p></td>
<td><p><span data-ttu-id="f198f-530">Протокол</span><span class="sxs-lookup"><span data-stu-id="f198f-530">DHCP</span></span></p></td>
<td><p><span data-ttu-id="f198f-531">Используется в списке устройств для поиска сертификата сервера Lync, подготовки полного доменного имени и полного доменного имени регистратора.</span><span class="sxs-lookup"><span data-stu-id="f198f-531">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f198f-532">**\*** Чтобы настроить определенные порты для этих типов мультимедиа, используйте командлет КсконференЦингконфигуратион (Клиентмедиапортранжеенаблед, Клиентмедиапорт и Клиентмедиапортранже).</span><span class="sxs-lookup"><span data-stu-id="f198f-532">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f198f-533">Программа Set для клиентов Lync автоматически создает необходимые исключения брандмауэра операционной системы на клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="f198f-533">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="f198f-534">Порты, используемые для внешнего доступа пользователей, необходимы для любого сценария, в котором клиент должен пройти межсетевой экран Организации (например, любые внешние коммуникации или собрания, размещенные в других организациях).</span><span class="sxs-lookup"><span data-stu-id="f198f-534">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

