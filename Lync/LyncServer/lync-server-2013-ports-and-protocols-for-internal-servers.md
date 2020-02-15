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
ms.openlocfilehash: c748a79fe118c9b1d233a7a276bd8298a0e1c3e4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="22cef-102">Порты и протоколы для внутренних серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22cef-102">Ports and protocols for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22cef-103">_**Последнее изменение темы:** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="22cef-103">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="22cef-104">В этом разделе приведены общие сведения о портах и протоколах, используемых серверами, подсистемами балансировки нагрузки и клиентами в развертывании Lync Server.</span><span class="sxs-lookup"><span data-stu-id="22cef-104">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="22cef-105">Клиенты Lync и Communicator, участвующие в одном обмене данными, часто называют одноранговыми узлами.</span><span class="sxs-lookup"><span data-stu-id="22cef-105">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="22cef-106">С технической точки зрения два клиента взаимодействуют в одном сеансе, с помощью модуля управления мгновенными сообщениями MultiPoint (ИММКУ) в центре.</span><span class="sxs-lookup"><span data-stu-id="22cef-106">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="22cef-107">ИММКУ — это компонент сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="22cef-107">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="22cef-108">Размещение ИММКУ в требуемом рабочем канале связи позволяет записывать сведения о вызовах и другие функции, которые обеспечивает сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="22cef-108">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="22cef-109">Обмен данными осуществляется от динамического исходного порта на клиенте к порту TLS/TCP/5061 (при условии использования рекомендуемой безопасности транспортного уровня).</span><span class="sxs-lookup"><span data-stu-id="22cef-109">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="22cef-110">Одноранговая связь (а также поддержка обмена мгновенными сообщениями) возможна только в том случае, если Lync Server и ИММКУ активны и доступны.</span><span class="sxs-lookup"><span data-stu-id="22cef-110">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="22cef-111">Сведения о портах и протоколе</span><span class="sxs-lookup"><span data-stu-id="22cef-111">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="22cef-112">Перед запуском служб Lync Server на сервере необходимо запустить брандмауэр Windows, так как в этом случае Lync Server открывает необходимые порты в брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="22cef-112">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="22cef-113">Подробные сведения о конфигурации брандмауэра для пограничных компонентов приведены [в статье Определение требований к портам внешнего аудио-и видеоподключения для Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22cef-113">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="22cef-114">В следующей таблице приводится список портов, которые должны быть открыты для каждой роли внутреннего сервера.</span><span class="sxs-lookup"><span data-stu-id="22cef-114">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="22cef-115">Необходимые порты сервера (по ролям сервера)</span><span class="sxs-lookup"><span data-stu-id="22cef-115">Required Server Ports (by Server Role)</span></span>

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
<th><span data-ttu-id="22cef-116">Роль сервера</span><span class="sxs-lookup"><span data-stu-id="22cef-116">Server role</span></span></th>
<th><span data-ttu-id="22cef-117">Имя службы</span><span class="sxs-lookup"><span data-stu-id="22cef-117">Service name</span></span></th>
<th><span data-ttu-id="22cef-118">Порт</span><span class="sxs-lookup"><span data-stu-id="22cef-118">Port</span></span></th>
<th><span data-ttu-id="22cef-119">Протокол</span><span class="sxs-lookup"><span data-stu-id="22cef-119">Protocol</span></span></th>
<th><span data-ttu-id="22cef-120">Notes</span><span class="sxs-lookup"><span data-stu-id="22cef-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="22cef-121">Все серверы</span><span class="sxs-lookup"><span data-stu-id="22cef-121">All Servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-122">Браузер SQL</span><span class="sxs-lookup"><span data-stu-id="22cef-122">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="22cef-123">1434</span><span class="sxs-lookup"><span data-stu-id="22cef-123">1434</span></span></p></td>
<td><p><span data-ttu-id="22cef-124">ПРОТОКОЛА</span><span class="sxs-lookup"><span data-stu-id="22cef-124">UDP</span></span></p></td>
<td><p><span data-ttu-id="22cef-125">Браузер SQL для локальной реплицированной копии базы данных центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="22cef-125">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-126">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-126">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-127">Интерфейсная служба Lync Server</span><span class="sxs-lookup"><span data-stu-id="22cef-127">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="22cef-128">5060</span><span class="sxs-lookup"><span data-stu-id="22cef-128">5060</span></span></p></td>
<td><p><span data-ttu-id="22cef-129">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-129">TCP</span></span></p></td>
<td><p><span data-ttu-id="22cef-130">При необходимости используется для статических маршрутов к доверенным службам серверами Standard Edition и серверами переднего плана, например серверами удаленного управления звонками.</span><span class="sxs-lookup"><span data-stu-id="22cef-130">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-131">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-131">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-132">Интерфейсная служба Lync Server</span><span class="sxs-lookup"><span data-stu-id="22cef-132">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="22cef-133">5061</span><span class="sxs-lookup"><span data-stu-id="22cef-133">5061</span></span></p></td>
<td><p><span data-ttu-id="22cef-134">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="22cef-134">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="22cef-p102">Используется серверами Standard Edition и серверами переднего плана для всех внутренних SIP-соединений между серверами (MTLS), для SIP-соединений между сервером и клиентом (TLS) и для SIP-соединений между серверами переднего плана и серверами-посредниками (MTLS). Также используется для соединений с сервером мониторинга.</span><span class="sxs-lookup"><span data-stu-id="22cef-p102">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS). Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-137">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-137">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-138">Интерфейсная служба Lync Server</span><span class="sxs-lookup"><span data-stu-id="22cef-138">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="22cef-139">444</span><span class="sxs-lookup"><span data-stu-id="22cef-139">444</span></span></p></td>
<td><p><span data-ttu-id="22cef-140">HTTPS</span><span class="sxs-lookup"><span data-stu-id="22cef-140">HTTPS</span></span></p>
<p><span data-ttu-id="22cef-141">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-141">TCP</span></span></p></td>
<td><p><span data-ttu-id="22cef-142">Используется для взаимодействия по протоколу HTTPS между фокусом (компонентом Lync Server, который управляет состоянием конференции) и отдельными серверами.</span><span class="sxs-lookup"><span data-stu-id="22cef-142">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="22cef-143">Этот порт также используется для связи по протоколу TCP между устройствами для обеспечения связи в филиалах и серверами переднего плана.</span><span class="sxs-lookup"><span data-stu-id="22cef-143">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-144">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-144">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-145">Интерфейсная служба Lync Server</span><span class="sxs-lookup"><span data-stu-id="22cef-145">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="22cef-146">135</span><span class="sxs-lookup"><span data-stu-id="22cef-146">135</span></span></p></td>
<td><p><span data-ttu-id="22cef-147">DCOM и удаленный вызов процедур (RPC)</span><span class="sxs-lookup"><span data-stu-id="22cef-147">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="22cef-148">Используется для операций на базе DCOM, таких как перемещение пользователей, синхронизация репликаторов пользовательских данных и адресных книг.</span><span class="sxs-lookup"><span data-stu-id="22cef-148">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-149">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-149">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-150">Служба конференц-связи Lync Server для обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="22cef-150">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="22cef-151">5062</span><span class="sxs-lookup"><span data-stu-id="22cef-151">5062</span></span></p></td>
<td><p><span data-ttu-id="22cef-152">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-152">TCP</span></span></p></td>
<td><p><span data-ttu-id="22cef-153">Используется для входящих SIP-запросов в конференц-связи с использованием обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="22cef-153">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-154">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-154">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-155">Служба веб-конференций Lync Server</span><span class="sxs-lookup"><span data-stu-id="22cef-155">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="22cef-156">8057</span><span class="sxs-lookup"><span data-stu-id="22cef-156">8057</span></span></p></td>
<td><p><span data-ttu-id="22cef-157">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="22cef-157">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="22cef-158">Используется для прослушивания подключений по протоколу PSOM от клиента.</span><span class="sxs-lookup"><span data-stu-id="22cef-158">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-159">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-159">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-160">Служба совместимости веб-конференций Lync Server</span><span class="sxs-lookup"><span data-stu-id="22cef-160">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="22cef-161">8058</span><span class="sxs-lookup"><span data-stu-id="22cef-161">8058</span></span></p></td>
<td><p><span data-ttu-id="22cef-162">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="22cef-162">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="22cef-163">Используется для прослушивания подключений к постоянным общим объектным моделям (PSOM) из клиента Live Meeting и предыдущих версий Lync Server.</span><span class="sxs-lookup"><span data-stu-id="22cef-163">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-164">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-164">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-165">Служба аудио-и видеоконференций Lync Server</span><span class="sxs-lookup"><span data-stu-id="22cef-165">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="22cef-166">5063</span><span class="sxs-lookup"><span data-stu-id="22cef-166">5063</span></span></p></td>
<td><p><span data-ttu-id="22cef-167">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-167">TCP</span></span></p></td>
<td><p><span data-ttu-id="22cef-168">Используется для входящих SIP-запросов на аудио- и видеоконференции.</span><span class="sxs-lookup"><span data-stu-id="22cef-168">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-169">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-169">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-170">Служба аудио-и видеоконференций Lync Server</span><span class="sxs-lookup"><span data-stu-id="22cef-170">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="22cef-171">57501-65535</span><span class="sxs-lookup"><span data-stu-id="22cef-171">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="22cef-172">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="22cef-172">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="22cef-173">Диапазон портов, используемых для видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="22cef-173">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-174">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-174">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-175">Служба веб-совместимости Lync Server</span><span class="sxs-lookup"><span data-stu-id="22cef-175">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="22cef-176">80</span><span class="sxs-lookup"><span data-stu-id="22cef-176">80</span></span></p></td>
<td><p><span data-ttu-id="22cef-177">HTTP</span><span class="sxs-lookup"><span data-stu-id="22cef-177">HTTP</span></span></p></td>
<td><p><span data-ttu-id="22cef-178">Используется для подключений от серверов переднего плана к полным доменным именам в веб-ферме (URL-адреса используются по веб-компонентам IIS), когда не используется HTTPS.</span><span class="sxs-lookup"><span data-stu-id="22cef-178">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-179">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-179">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-180">Служба веб-совместимости Lync Server</span><span class="sxs-lookup"><span data-stu-id="22cef-180">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="22cef-181">443</span><span class="sxs-lookup"><span data-stu-id="22cef-181">443</span></span></p></td>
<td><p><span data-ttu-id="22cef-182">HTTPS</span><span class="sxs-lookup"><span data-stu-id="22cef-182">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="22cef-183">Используется для подключений от серверов переднего плана к полным доменным именам в веб-ферме (URL-адреса используются по веб-компонентам IIS).</span><span class="sxs-lookup"><span data-stu-id="22cef-183">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-184">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-184">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-185">Служба веб-совместимости Lync Server</span><span class="sxs-lookup"><span data-stu-id="22cef-185">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="22cef-186">8080</span><span class="sxs-lookup"><span data-stu-id="22cef-186">8080</span></span></p></td>
<td><p><span data-ttu-id="22cef-187">TCP и HTTP</span><span class="sxs-lookup"><span data-stu-id="22cef-187">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="22cef-188">Используется веб-компонентами для внешнего доступа.</span><span class="sxs-lookup"><span data-stu-id="22cef-188">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-189">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-189">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-190">Компонент веб-сервера</span><span class="sxs-lookup"><span data-stu-id="22cef-190">Web server component</span></span></p></td>
<td><p><span data-ttu-id="22cef-191">4443</span><span class="sxs-lookup"><span data-stu-id="22cef-191">4443</span></span></p></td>
<td><p><span data-ttu-id="22cef-192">HTTPS</span><span class="sxs-lookup"><span data-stu-id="22cef-192">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="22cef-193">Подключения HTTPS (от обратного прокси-сервера) и подключения между пулами HTTPS для входа в службу автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="22cef-193">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-194">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-194">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-195">Компонент веб-сервера</span><span class="sxs-lookup"><span data-stu-id="22cef-195">Web server component</span></span></p></td>
<td><p><span data-ttu-id="22cef-196">8060</span><span class="sxs-lookup"><span data-stu-id="22cef-196">8060</span></span></p></td>
<td><p><span data-ttu-id="22cef-197">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="22cef-197">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-198">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-198">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-199">Компонент веб-сервера</span><span class="sxs-lookup"><span data-stu-id="22cef-199">Web server component</span></span></p></td>
<td><p><span data-ttu-id="22cef-200">8061</span><span class="sxs-lookup"><span data-stu-id="22cef-200">8061</span></span></p></td>
<td><p><span data-ttu-id="22cef-201">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="22cef-201">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-202">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-202">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-203">Компонент служб Mobility Services</span><span class="sxs-lookup"><span data-stu-id="22cef-203">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="22cef-204">5086</span><span class="sxs-lookup"><span data-stu-id="22cef-204">5086</span></span></p></td>
<td><p><span data-ttu-id="22cef-205">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="22cef-205">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="22cef-206">SIP-порт, используемый внутренними процессами служб Mobility Services</span><span class="sxs-lookup"><span data-stu-id="22cef-206">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-207">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-207">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-208">Компонент служб Mobility Services</span><span class="sxs-lookup"><span data-stu-id="22cef-208">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="22cef-209">5087</span><span class="sxs-lookup"><span data-stu-id="22cef-209">5087</span></span></p></td>
<td><p><span data-ttu-id="22cef-210">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="22cef-210">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="22cef-211">SIP-порт, используемый внутренними процессами служб Mobility Services</span><span class="sxs-lookup"><span data-stu-id="22cef-211">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-212">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-212">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-213">Компонент служб Mobility Services</span><span class="sxs-lookup"><span data-stu-id="22cef-213">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="22cef-214">443</span><span class="sxs-lookup"><span data-stu-id="22cef-214">443</span></span></p></td>
<td><p><span data-ttu-id="22cef-215">HTTPS</span><span class="sxs-lookup"><span data-stu-id="22cef-215">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-216">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-216">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-217">Служба помощника по конференц-связи Lync Server (Конференц-связь с телефонным подключением)</span><span class="sxs-lookup"><span data-stu-id="22cef-217">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="22cef-218">5064</span><span class="sxs-lookup"><span data-stu-id="22cef-218">5064</span></span></p></td>
<td><p><span data-ttu-id="22cef-219">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-219">TCP</span></span></p></td>
<td><p><span data-ttu-id="22cef-220">Используется для входящих SIP-запросов для конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="22cef-220">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-221">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-221">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-222">Служба помощника по конференц-связи Lync Server (Конференц-связь с телефонным подключением)</span><span class="sxs-lookup"><span data-stu-id="22cef-222">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="22cef-223">5072</span><span class="sxs-lookup"><span data-stu-id="22cef-223">5072</span></span></p></td>
<td><p><span data-ttu-id="22cef-224">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-224">TCP</span></span></p></td>
<td><p><span data-ttu-id="22cef-225">Используется для входящих SIP-запросов для помощника (конференц-связи с телефонным подключением).</span><span class="sxs-lookup"><span data-stu-id="22cef-225">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-226">Серверы переднего плана, на которых также работает соотнесенный сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="22cef-226">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="22cef-227">Служба-посредник по Lync Server</span><span class="sxs-lookup"><span data-stu-id="22cef-227">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="22cef-228">5070</span><span class="sxs-lookup"><span data-stu-id="22cef-228">5070</span></span></p></td>
<td><p><span data-ttu-id="22cef-229">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-229">TCP</span></span></p></td>
<td><p><span data-ttu-id="22cef-230">Используется сервером-посредником для входящих запросов от сервера переднего плана к серверу посреднику.</span><span class="sxs-lookup"><span data-stu-id="22cef-230">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-231">Серверы переднего плана, на которых также работает соотнесенный сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="22cef-231">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="22cef-232">Служба-посредник по Lync Server</span><span class="sxs-lookup"><span data-stu-id="22cef-232">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="22cef-233">5067</span><span class="sxs-lookup"><span data-stu-id="22cef-233">5067</span></span></p></td>
<td><p><span data-ttu-id="22cef-234">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="22cef-234">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="22cef-235">Используется для входящих SIP-запросов от шлюза ТСОП к серверу-посреднику.</span><span class="sxs-lookup"><span data-stu-id="22cef-235">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-236">Серверы переднего плана, на которых также работает соотнесенный сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="22cef-236">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="22cef-237">Служба-посредник по Lync Server</span><span class="sxs-lookup"><span data-stu-id="22cef-237">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="22cef-238">5068</span><span class="sxs-lookup"><span data-stu-id="22cef-238">5068</span></span></p></td>
<td><p><span data-ttu-id="22cef-239">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-239">TCP</span></span></p></td>
<td><p><span data-ttu-id="22cef-240">Используется для входящих SIP-запросов от шлюза ТСОП к серверу-посреднику.</span><span class="sxs-lookup"><span data-stu-id="22cef-240">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-241">Серверы переднего плана, на которых также работает соотнесенный сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="22cef-241">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="22cef-242">Служба-посредник по Lync Server</span><span class="sxs-lookup"><span data-stu-id="22cef-242">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="22cef-243">5081</span><span class="sxs-lookup"><span data-stu-id="22cef-243">5081</span></span></p></td>
<td><p><span data-ttu-id="22cef-244">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-244">TCP</span></span></p></td>
<td><p><span data-ttu-id="22cef-245">Используется для исходящих SIP-запросов от сервера-посредника к шлюзу ТСОП.</span><span class="sxs-lookup"><span data-stu-id="22cef-245">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-246">Серверы переднего плана, на которых также работает соотнесенный сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="22cef-246">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="22cef-247">Служба-посредник по Lync Server</span><span class="sxs-lookup"><span data-stu-id="22cef-247">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="22cef-248">5082</span><span class="sxs-lookup"><span data-stu-id="22cef-248">5082</span></span></p></td>
<td><p><span data-ttu-id="22cef-249">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="22cef-249">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="22cef-250">Используется для исходящих SIP-запросов от сервера-посредника к шлюзу ТСОП.</span><span class="sxs-lookup"><span data-stu-id="22cef-250">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-251">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-251">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-252">Служба общего доступа к приложениям Lync Server</span><span class="sxs-lookup"><span data-stu-id="22cef-252">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="22cef-253">5065</span><span class="sxs-lookup"><span data-stu-id="22cef-253">5065</span></span></p></td>
<td><p><span data-ttu-id="22cef-254">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-254">TCP</span></span></p></td>
<td><p><span data-ttu-id="22cef-255">Используется для входящих SIP-запросов на прослушивание для общего доступа к приложению.</span><span class="sxs-lookup"><span data-stu-id="22cef-255">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-256">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-256">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-257">Служба общего доступа к приложениям Lync Server</span><span class="sxs-lookup"><span data-stu-id="22cef-257">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="22cef-258">49152-65535</span><span class="sxs-lookup"><span data-stu-id="22cef-258">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="22cef-259">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-259">TCP</span></span></p></td>
<td><p><span data-ttu-id="22cef-260">Диапазон портов, используемых для общего доступа к приложению.</span><span class="sxs-lookup"><span data-stu-id="22cef-260">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-261">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-261">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-262">Служба объявлений Lync Server для конференц-связи</span><span class="sxs-lookup"><span data-stu-id="22cef-262">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="22cef-263">5073</span><span class="sxs-lookup"><span data-stu-id="22cef-263">5073</span></span></p></td>
<td><p><span data-ttu-id="22cef-264">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-264">TCP</span></span></p></td>
<td><p><span data-ttu-id="22cef-265">Используется для входящих SIP-запросов для службы оповещений конференц-связи Lync Server (то есть для конференц-связи с телефонным подключением).</span><span class="sxs-lookup"><span data-stu-id="22cef-265">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-266">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-266">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-267">Служба парковки вызовов Lync Server</span><span class="sxs-lookup"><span data-stu-id="22cef-267">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="22cef-268">5075</span><span class="sxs-lookup"><span data-stu-id="22cef-268">5075</span></span></p></td>
<td><p><span data-ttu-id="22cef-269">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-269">TCP</span></span></p></td>
<td><p><span data-ttu-id="22cef-270">Используется для входящих SIP-запросов для приложения приостановки звонков.</span><span class="sxs-lookup"><span data-stu-id="22cef-270">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-271">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-271">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-272">Служба проверки аудиоустройств Lync Server</span><span class="sxs-lookup"><span data-stu-id="22cef-272">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="22cef-273">5076</span><span class="sxs-lookup"><span data-stu-id="22cef-273">5076</span></span></p></td>
<td><p><span data-ttu-id="22cef-274">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-274">TCP</span></span></p></td>
<td><p><span data-ttu-id="22cef-275">Используется для входящих SIP-запросов для службы проверки аудиосвязи.</span><span class="sxs-lookup"><span data-stu-id="22cef-275">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-276">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-276">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-277">Не применимо</span><span class="sxs-lookup"><span data-stu-id="22cef-277">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="22cef-278">5066</span><span class="sxs-lookup"><span data-stu-id="22cef-278">5066</span></span></p></td>
<td><p><span data-ttu-id="22cef-279">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-279">TCP</span></span></p></td>
<td><p><span data-ttu-id="22cef-280">Используется для исходящего трафика в шлюзе службы Enhanced 9-1-1 (E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="22cef-280">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-281">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-281">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-282">Служба группы ответа Lync Server</span><span class="sxs-lookup"><span data-stu-id="22cef-282">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="22cef-283">5071</span><span class="sxs-lookup"><span data-stu-id="22cef-283">5071</span></span></p></td>
<td><p><span data-ttu-id="22cef-284">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-284">TCP</span></span></p></td>
<td><p><span data-ttu-id="22cef-285">Используется для входящих SIP-запросов для приложения группы ответа.</span><span class="sxs-lookup"><span data-stu-id="22cef-285">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-286">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-286">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-287">Служба группы ответа Lync Server</span><span class="sxs-lookup"><span data-stu-id="22cef-287">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="22cef-288">8404</span><span class="sxs-lookup"><span data-stu-id="22cef-288">8404</span></span></p></td>
<td><p><span data-ttu-id="22cef-289">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="22cef-289">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="22cef-290">Используется для входящих SIP-запросов для приложения группы ответа.</span><span class="sxs-lookup"><span data-stu-id="22cef-290">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-291">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-291">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-292">Служба политики пропускной способности Lync Server</span><span class="sxs-lookup"><span data-stu-id="22cef-292">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="22cef-293">5080</span><span class="sxs-lookup"><span data-stu-id="22cef-293">5080</span></span></p></td>
<td><p><span data-ttu-id="22cef-294">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-294">TCP</span></span></p></td>
<td><p><span data-ttu-id="22cef-295">Используется для контроля допуска звонков, осуществляемого службой политики пропускной способности в отношении пограничного аудио-/видео-трафика @@TURN.</span><span class="sxs-lookup"><span data-stu-id="22cef-295">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-296">Серверы переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-296">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-297">Служба политики пропускной способности Lync Server</span><span class="sxs-lookup"><span data-stu-id="22cef-297">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="22cef-298">448</span><span class="sxs-lookup"><span data-stu-id="22cef-298">448</span></span></p></td>
<td><p><span data-ttu-id="22cef-299">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-299">TCP</span></span></p></td>
<td><p><span data-ttu-id="22cef-300">Используется для контроля допуска звонков службой политики пропускной способности Lync Server.</span><span class="sxs-lookup"><span data-stu-id="22cef-300">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-301">Серверы переднего плана, на которых размещается центральное хранилище управления</span><span class="sxs-lookup"><span data-stu-id="22cef-301">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="22cef-302">Служба агента главного репликатора Lync Server</span><span class="sxs-lookup"><span data-stu-id="22cef-302">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="22cef-303">445</span><span class="sxs-lookup"><span data-stu-id="22cef-303">445</span></span></p></td>
<td><p><span data-ttu-id="22cef-304">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-304">TCP</span></span></p></td>
<td><p><span data-ttu-id="22cef-305">Используется для принудительной передачи данных конфигурации из центрального хранилища управления на серверы, на которых работает Lync Server.</span><span class="sxs-lookup"><span data-stu-id="22cef-305">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-306">Все серверы</span><span class="sxs-lookup"><span data-stu-id="22cef-306">All Servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-307">Браузер SQL</span><span class="sxs-lookup"><span data-stu-id="22cef-307">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="22cef-308">1434</span><span class="sxs-lookup"><span data-stu-id="22cef-308">1434</span></span></p></td>
<td><p><span data-ttu-id="22cef-309">ПРОТОКОЛА</span><span class="sxs-lookup"><span data-stu-id="22cef-309">UDP</span></span></p></td>
<td><p><span data-ttu-id="22cef-310">Браузер SQL для локальной реплицированной копии данных центрального хранилища управления в локальном экземпляре SQL Server</span><span class="sxs-lookup"><span data-stu-id="22cef-310">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-311">Все внутренние серверы</span><span class="sxs-lookup"><span data-stu-id="22cef-311">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-312">Разное</span><span class="sxs-lookup"><span data-stu-id="22cef-312">Various</span></span></p></td>
<td><p><span data-ttu-id="22cef-313">49152-57500</span><span class="sxs-lookup"><span data-stu-id="22cef-313">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="22cef-314">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="22cef-314">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="22cef-315">Диапазон портов, используемых для аудиоконференций на всех внутренних серверах.</span><span class="sxs-lookup"><span data-stu-id="22cef-315">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="22cef-316">Используется всеми серверами, которые завершают аудио: серверы переднего плана (служба помощника по конференц-связи Lync Server, служба оповещений конференц-связи Lync Server и служба аудио-и видеоконференций Lync Server) и сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="22cef-316">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-317">Серверы Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="22cef-317">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="22cef-318">443</span><span class="sxs-lookup"><span data-stu-id="22cef-318">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="22cef-319">Используется Lync Server 2013 для подключения к серверу Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="22cef-319">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-320">Директор</span><span class="sxs-lookup"><span data-stu-id="22cef-320">Directors</span></span></p></td>
<td><p><span data-ttu-id="22cef-321">Интерфейсная служба Lync Server</span><span class="sxs-lookup"><span data-stu-id="22cef-321">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="22cef-322">5060</span><span class="sxs-lookup"><span data-stu-id="22cef-322">5060</span></span></p></td>
<td><p><span data-ttu-id="22cef-323">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-323">TCP</span></span></p></td>
<td><p><span data-ttu-id="22cef-324">При необходимости используется для статических маршрутов к доверенным службам, таким как серверы удаленного управления звонками.</span><span class="sxs-lookup"><span data-stu-id="22cef-324">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-325">Директор</span><span class="sxs-lookup"><span data-stu-id="22cef-325">Directors</span></span></p></td>
<td><p><span data-ttu-id="22cef-326">Интерфейсная служба Lync Server</span><span class="sxs-lookup"><span data-stu-id="22cef-326">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="22cef-327">444</span><span class="sxs-lookup"><span data-stu-id="22cef-327">444</span></span></p></td>
<td><p><span data-ttu-id="22cef-328">HTTPS</span><span class="sxs-lookup"><span data-stu-id="22cef-328">HTTPS</span></span></p>
<p><span data-ttu-id="22cef-329">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-329">TCP</span></span></p></td>
<td><p><span data-ttu-id="22cef-330">Inter-server communication between Front End and Director.</span><span class="sxs-lookup"><span data-stu-id="22cef-330">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="22cef-331">Кроме того, публикация сертификата клиента (на серверах переднего плана) или проверка того, был ли уже опубликован сертификат клиента.</span><span class="sxs-lookup"><span data-stu-id="22cef-331">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-332">Директор</span><span class="sxs-lookup"><span data-stu-id="22cef-332">Directors</span></span></p></td>
<td><p><span data-ttu-id="22cef-333">Служба веб-совместимости Lync Server</span><span class="sxs-lookup"><span data-stu-id="22cef-333">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="22cef-334">80</span><span class="sxs-lookup"><span data-stu-id="22cef-334">80</span></span></p></td>
<td><p><span data-ttu-id="22cef-335">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-335">TCP</span></span></p></td>
<td><p><span data-ttu-id="22cef-p105">Используется для исходного подключения от директоров к полным доменным именам в веб-ферме (URL-адреса используются по веб-компонентам IIS). При обычной работе происходит переключение на трафик HTTPS с использованием порта 443 и протокола TCP.</span><span class="sxs-lookup"><span data-stu-id="22cef-p105">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components). In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-338">Директор</span><span class="sxs-lookup"><span data-stu-id="22cef-338">Directors</span></span></p></td>
<td><p><span data-ttu-id="22cef-339">Служба веб-совместимости Lync Server</span><span class="sxs-lookup"><span data-stu-id="22cef-339">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="22cef-340">443</span><span class="sxs-lookup"><span data-stu-id="22cef-340">443</span></span></p></td>
<td><p><span data-ttu-id="22cef-341">HTTPS</span><span class="sxs-lookup"><span data-stu-id="22cef-341">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="22cef-342">Используется для подключения от директоров к полным доменным именам в веб-ферме (URL-адреса используются по веб-компонентам IIS).</span><span class="sxs-lookup"><span data-stu-id="22cef-342">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-343">Директор</span><span class="sxs-lookup"><span data-stu-id="22cef-343">Directors</span></span></p></td>
<td><p><span data-ttu-id="22cef-344">Интерфейсная служба Lync Server</span><span class="sxs-lookup"><span data-stu-id="22cef-344">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="22cef-345">5061</span><span class="sxs-lookup"><span data-stu-id="22cef-345">5061</span></span></p></td>
<td><p><span data-ttu-id="22cef-346">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-346">TCP</span></span></p></td>
<td><p><span data-ttu-id="22cef-347">Используется для внутренних подключений между серверами и для клиентских подключений.</span><span class="sxs-lookup"><span data-stu-id="22cef-347">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-348">Серверы-посредники</span><span class="sxs-lookup"><span data-stu-id="22cef-348">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-349">Служба-посредник по Lync Server</span><span class="sxs-lookup"><span data-stu-id="22cef-349">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="22cef-350">5070</span><span class="sxs-lookup"><span data-stu-id="22cef-350">5070</span></span></p></td>
<td><p><span data-ttu-id="22cef-351">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-351">TCP</span></span></p></td>
<td><p><span data-ttu-id="22cef-352">Используется сервером-посредником для входящих запросов от сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="22cef-352">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-353">Серверы-посредники</span><span class="sxs-lookup"><span data-stu-id="22cef-353">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-354">Служба-посредник по Lync Server</span><span class="sxs-lookup"><span data-stu-id="22cef-354">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="22cef-355">5067</span><span class="sxs-lookup"><span data-stu-id="22cef-355">5067</span></span></p></td>
<td><p><span data-ttu-id="22cef-356">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="22cef-356">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="22cef-357">Используется для входящих SIP-запросов от шлюза ТСОП.</span><span class="sxs-lookup"><span data-stu-id="22cef-357">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-358">Серверы-посредники</span><span class="sxs-lookup"><span data-stu-id="22cef-358">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-359">Служба-посредник по Lync Server</span><span class="sxs-lookup"><span data-stu-id="22cef-359">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="22cef-360">5068</span><span class="sxs-lookup"><span data-stu-id="22cef-360">5068</span></span></p></td>
<td><p><span data-ttu-id="22cef-361">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-361">TCP</span></span></p></td>
<td><p><span data-ttu-id="22cef-362">Используется для входящих SIP-запросов от шлюза ТСОП.</span><span class="sxs-lookup"><span data-stu-id="22cef-362">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-363">Серверы-посредники</span><span class="sxs-lookup"><span data-stu-id="22cef-363">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="22cef-364">Служба-посредник по Lync Server</span><span class="sxs-lookup"><span data-stu-id="22cef-364">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="22cef-365">5070</span><span class="sxs-lookup"><span data-stu-id="22cef-365">5070</span></span></p></td>
<td><p><span data-ttu-id="22cef-366">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="22cef-366">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="22cef-367">Используется для SIP-запросов от серверов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="22cef-367">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-368">Сервер переднего плана сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="22cef-368">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="22cef-369">SIP-запрос сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="22cef-369">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="22cef-370">5041</span><span class="sxs-lookup"><span data-stu-id="22cef-370">5041</span></span></p></td>
<td><p><span data-ttu-id="22cef-371">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="22cef-371">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-372">Сервер переднего плана сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="22cef-372">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="22cef-373">Платформа Windows Communication Foundation (WCF) для сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="22cef-373">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="22cef-374">881</span><span class="sxs-lookup"><span data-stu-id="22cef-374">881</span></span></p></td>
<td><p><span data-ttu-id="22cef-375">TCP (TLS) и TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="22cef-375">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-376">Сервер переднего плана сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="22cef-376">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="22cef-377">Служба передачи файлов для сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="22cef-377">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="22cef-378">443</span><span class="sxs-lookup"><span data-stu-id="22cef-378">443</span></span></p></td>
<td><p><span data-ttu-id="22cef-379">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="22cef-379">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="22cef-380">Для некоторых сценариев удаленного управления звонками требуется TCP-соединение между сервером переднего плана или директором и УАТС.</span><span class="sxs-lookup"><span data-stu-id="22cef-380">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="22cef-381">Несмотря на то, что Lync Server больше не использует TCP-порт 5060, во время развертывания удаленного управления звонками создается конфигурация доверенных серверов, которая связывает полное доменное имя сервера по линии RCC с портом TCP, который будет использоваться сервером переднего плана или директором для подключения к системе УАТС.</span><span class="sxs-lookup"><span data-stu-id="22cef-381">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="22cef-382">Для получения дополнительных сведений обратитесь к командлету <STRONG>кструстедаппликатионкомпутер</STRONG> в документации по консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="22cef-382">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="22cef-383">Для пулов, использующих только аппаратную балансировку нагрузки (без балансировки нагрузки на DNS), в следующей таблице показаны порты, которые должны открыть аппаратную подсистему балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="22cef-383">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="22cef-384">Порты аппаратного балансировщика нагрузки при использовании только аппаратной балансировки нагрузки</span><span class="sxs-lookup"><span data-stu-id="22cef-384">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="22cef-385">Подсистема балансировки нагрузки</span><span class="sxs-lookup"><span data-stu-id="22cef-385">Load Balancer</span></span></th>
<th><span data-ttu-id="22cef-386">Порт</span><span class="sxs-lookup"><span data-stu-id="22cef-386">Port</span></span></th>
<th><span data-ttu-id="22cef-387">Протокол</span><span class="sxs-lookup"><span data-stu-id="22cef-387">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="22cef-388">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-388">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="22cef-389">5061</span><span class="sxs-lookup"><span data-stu-id="22cef-389">5061</span></span></p></td>
<td><p><span data-ttu-id="22cef-390">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="22cef-390">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-391">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-391">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="22cef-392">444</span><span class="sxs-lookup"><span data-stu-id="22cef-392">444</span></span></p></td>
<td><p><span data-ttu-id="22cef-393">HTTPS</span><span class="sxs-lookup"><span data-stu-id="22cef-393">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-394">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-394">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="22cef-395">135</span><span class="sxs-lookup"><span data-stu-id="22cef-395">135</span></span></p></td>
<td><p><span data-ttu-id="22cef-396">DCOM и удаленный вызов процедур (RPC)</span><span class="sxs-lookup"><span data-stu-id="22cef-396">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-397">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-397">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="22cef-398">80</span><span class="sxs-lookup"><span data-stu-id="22cef-398">80</span></span></p></td>
<td><p><span data-ttu-id="22cef-399">HTTP</span><span class="sxs-lookup"><span data-stu-id="22cef-399">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-400">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-400">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="22cef-401">8080</span><span class="sxs-lookup"><span data-stu-id="22cef-401">8080</span></span></p></td>
<td><p><span data-ttu-id="22cef-402">TCP-получение клиентом и устройством корневого сертификата с сервера переднего плана — клиенты и устройства, прошедшие проверку подлинности NTLM</span><span class="sxs-lookup"><span data-stu-id="22cef-402">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-403">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-403">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="22cef-404">443</span><span class="sxs-lookup"><span data-stu-id="22cef-404">443</span></span></p></td>
<td><p><span data-ttu-id="22cef-405">HTTPS</span><span class="sxs-lookup"><span data-stu-id="22cef-405">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-406">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-406">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="22cef-407">4443</span><span class="sxs-lookup"><span data-stu-id="22cef-407">4443</span></span></p></td>
<td><p><span data-ttu-id="22cef-408">HTTPS (от обратного прокси-сервера)</span><span class="sxs-lookup"><span data-stu-id="22cef-408">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-409">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-409">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="22cef-410">5072</span><span class="sxs-lookup"><span data-stu-id="22cef-410">5072</span></span></p></td>
<td><p><span data-ttu-id="22cef-411">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-411">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-412">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-412">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="22cef-413">5073</span><span class="sxs-lookup"><span data-stu-id="22cef-413">5073</span></span></p></td>
<td><p><span data-ttu-id="22cef-414">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-414">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-415">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-415">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="22cef-416">5075</span><span class="sxs-lookup"><span data-stu-id="22cef-416">5075</span></span></p></td>
<td><p><span data-ttu-id="22cef-417">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-417">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-418">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-418">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="22cef-419">5076</span><span class="sxs-lookup"><span data-stu-id="22cef-419">5076</span></span></p></td>
<td><p><span data-ttu-id="22cef-420">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-420">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-421">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-421">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="22cef-422">5071</span><span class="sxs-lookup"><span data-stu-id="22cef-422">5071</span></span></p></td>
<td><p><span data-ttu-id="22cef-423">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-423">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-424">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-424">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="22cef-425">5080</span><span class="sxs-lookup"><span data-stu-id="22cef-425">5080</span></span></p></td>
<td><p><span data-ttu-id="22cef-426">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-426">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-427">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-427">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="22cef-428">448</span><span class="sxs-lookup"><span data-stu-id="22cef-428">448</span></span></p></td>
<td><p><span data-ttu-id="22cef-429">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-429">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-430">Балансировщик нагрузки сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="22cef-430">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="22cef-431">5070</span><span class="sxs-lookup"><span data-stu-id="22cef-431">5070</span></span></p></td>
<td><p><span data-ttu-id="22cef-432">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-432">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-433">Балансировщик нагрузки на сервере переднего плана (если в пуле также работает сервер-посредник)</span><span class="sxs-lookup"><span data-stu-id="22cef-433">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="22cef-434">5070</span><span class="sxs-lookup"><span data-stu-id="22cef-434">5070</span></span></p></td>
<td><p><span data-ttu-id="22cef-435">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-435">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-436">Подсистема балансировки нагрузки режиссера</span><span class="sxs-lookup"><span data-stu-id="22cef-436">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="22cef-437">443</span><span class="sxs-lookup"><span data-stu-id="22cef-437">443</span></span></p></td>
<td><p><span data-ttu-id="22cef-438">HTTPS</span><span class="sxs-lookup"><span data-stu-id="22cef-438">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-439">Подсистема балансировки нагрузки режиссера</span><span class="sxs-lookup"><span data-stu-id="22cef-439">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="22cef-440">444</span><span class="sxs-lookup"><span data-stu-id="22cef-440">444</span></span></p></td>
<td><p><span data-ttu-id="22cef-441">HTTPS</span><span class="sxs-lookup"><span data-stu-id="22cef-441">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-442">Подсистема балансировки нагрузки режиссера</span><span class="sxs-lookup"><span data-stu-id="22cef-442">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="22cef-443">5061</span><span class="sxs-lookup"><span data-stu-id="22cef-443">5061</span></span></p></td>
<td><p><span data-ttu-id="22cef-444">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-444">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-445">Подсистема балансировки нагрузки режиссера</span><span class="sxs-lookup"><span data-stu-id="22cef-445">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="22cef-446">4443</span><span class="sxs-lookup"><span data-stu-id="22cef-446">4443</span></span></p></td>
<td><p><span data-ttu-id="22cef-447">HTTPS (от обратного прокси-сервера)</span><span class="sxs-lookup"><span data-stu-id="22cef-447">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="22cef-448">Для пулов переднего плана и пулов директоров, использующих балансировку нагрузки на DNS, также должен быть развернут аппаратный балансировщик нагрузки.</span><span class="sxs-lookup"><span data-stu-id="22cef-448">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed.</span></span> <span data-ttu-id="22cef-449">В следующей таблице приведены порты, которые должны быть открыты на этих аппаратных подсистемах балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="22cef-449">The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="22cef-450">Порты аппаратного балансировщика нагрузки при использовании балансировки нагрузки на DNS</span><span class="sxs-lookup"><span data-stu-id="22cef-450">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="22cef-451">Подсистема балансировки нагрузки</span><span class="sxs-lookup"><span data-stu-id="22cef-451">Load Balancer</span></span></th>
<th><span data-ttu-id="22cef-452">Порт</span><span class="sxs-lookup"><span data-stu-id="22cef-452">Port</span></span></th>
<th><span data-ttu-id="22cef-453">Протокол</span><span class="sxs-lookup"><span data-stu-id="22cef-453">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="22cef-454">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-454">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="22cef-455">80</span><span class="sxs-lookup"><span data-stu-id="22cef-455">80</span></span></p></td>
<td><p><span data-ttu-id="22cef-456">HTTP</span><span class="sxs-lookup"><span data-stu-id="22cef-456">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-457">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-457">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="22cef-458">443</span><span class="sxs-lookup"><span data-stu-id="22cef-458">443</span></span></p></td>
<td><p><span data-ttu-id="22cef-459">HTTPS</span><span class="sxs-lookup"><span data-stu-id="22cef-459">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-460">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-460">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="22cef-461">8080</span><span class="sxs-lookup"><span data-stu-id="22cef-461">8080</span></span></p></td>
<td><p><span data-ttu-id="22cef-462">TCP-получение клиентом и устройством корневого сертификата с сервера переднего плана — клиенты и устройства, прошедшие проверку подлинности NTLM</span><span class="sxs-lookup"><span data-stu-id="22cef-462">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-463">Балансировщик нагрузки на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="22cef-463">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="22cef-464">4443</span><span class="sxs-lookup"><span data-stu-id="22cef-464">4443</span></span></p></td>
<td><p><span data-ttu-id="22cef-465">HTTPS (от обратного прокси-сервера)</span><span class="sxs-lookup"><span data-stu-id="22cef-465">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-466">Подсистема балансировки нагрузки режиссера</span><span class="sxs-lookup"><span data-stu-id="22cef-466">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="22cef-467">443</span><span class="sxs-lookup"><span data-stu-id="22cef-467">443</span></span></p></td>
<td><p><span data-ttu-id="22cef-468">HTTPS</span><span class="sxs-lookup"><span data-stu-id="22cef-468">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-469">Подсистема балансировки нагрузки режиссера</span><span class="sxs-lookup"><span data-stu-id="22cef-469">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="22cef-470">4443</span><span class="sxs-lookup"><span data-stu-id="22cef-470">4443</span></span></p></td>
<td><p><span data-ttu-id="22cef-471">HTTPS (от обратного прокси-сервера)</span><span class="sxs-lookup"><span data-stu-id="22cef-471">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="22cef-472">Необходимые порты клиента</span><span class="sxs-lookup"><span data-stu-id="22cef-472">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="22cef-473">Компонент</span><span class="sxs-lookup"><span data-stu-id="22cef-473">Component</span></span></th>
<th><span data-ttu-id="22cef-474">Порт</span><span class="sxs-lookup"><span data-stu-id="22cef-474">Port</span></span></th>
<th><span data-ttu-id="22cef-475">Протокол</span><span class="sxs-lookup"><span data-stu-id="22cef-475">Protocol</span></span></th>
<th><span data-ttu-id="22cef-476">Notes</span><span class="sxs-lookup"><span data-stu-id="22cef-476">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="22cef-477">Клиенты</span><span class="sxs-lookup"><span data-stu-id="22cef-477">Clients</span></span></p></td>
<td><p><span data-ttu-id="22cef-478">67/68</span><span class="sxs-lookup"><span data-stu-id="22cef-478">67/68</span></span></p></td>
<td><p><span data-ttu-id="22cef-479">-</span><span class="sxs-lookup"><span data-stu-id="22cef-479">DHCP</span></span></p></td>
<td><p><span data-ttu-id="22cef-480">Используется Lync Server для поиска полного доменного имени регистратора (то есть в случае сбоя DNS SRV и ненастроенных параметров вручную).</span><span class="sxs-lookup"><span data-stu-id="22cef-480">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-481">Клиенты</span><span class="sxs-lookup"><span data-stu-id="22cef-481">Clients</span></span></p></td>
<td><p><span data-ttu-id="22cef-482">443</span><span class="sxs-lookup"><span data-stu-id="22cef-482">443</span></span></p></td>
<td><p><span data-ttu-id="22cef-483">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="22cef-483">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="22cef-484">Используется для трафика SIP от клиента к серверу для доступа внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="22cef-484">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-485">Клиенты</span><span class="sxs-lookup"><span data-stu-id="22cef-485">Clients</span></span></p></td>
<td><p><span data-ttu-id="22cef-486">443</span><span class="sxs-lookup"><span data-stu-id="22cef-486">443</span></span></p></td>
<td><p><span data-ttu-id="22cef-487">TCP (PSOM/TLS)</span><span class="sxs-lookup"><span data-stu-id="22cef-487">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="22cef-488">Используется для доступа внешних пользователей к сеансам веб-конференций.</span><span class="sxs-lookup"><span data-stu-id="22cef-488">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-489">Клиенты</span><span class="sxs-lookup"><span data-stu-id="22cef-489">Clients</span></span></p></td>
<td><p><span data-ttu-id="22cef-490">443</span><span class="sxs-lookup"><span data-stu-id="22cef-490">443</span></span></p></td>
<td><p><span data-ttu-id="22cef-491">TCP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="22cef-491">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="22cef-492">Используется для доступа внешних пользователей к сеансам аудио-и видеосвязи и мультимедиа (TCP)</span><span class="sxs-lookup"><span data-stu-id="22cef-492">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-493">Клиенты</span><span class="sxs-lookup"><span data-stu-id="22cef-493">Clients</span></span></p></td>
<td><p><span data-ttu-id="22cef-494">3478</span><span class="sxs-lookup"><span data-stu-id="22cef-494">3478</span></span></p></td>
<td><p><span data-ttu-id="22cef-495">UDP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="22cef-495">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="22cef-496">Используется для доступа внешних пользователей к сеансам аудио-и видеосвязи и мультимедиа (UDP)</span><span class="sxs-lookup"><span data-stu-id="22cef-496">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-497">Клиенты</span><span class="sxs-lookup"><span data-stu-id="22cef-497">Clients</span></span></p></td>
<td><p><span data-ttu-id="22cef-498">5061</span><span class="sxs-lookup"><span data-stu-id="22cef-498">5061</span></span></p></td>
<td><p><span data-ttu-id="22cef-499">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="22cef-499">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="22cef-500">Используется для трафика SIP от клиента к серверу для доступа внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="22cef-500">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-501">Клиенты</span><span class="sxs-lookup"><span data-stu-id="22cef-501">Clients</span></span></p></td>
<td><p><span data-ttu-id="22cef-502">6891-6901</span><span class="sxs-lookup"><span data-stu-id="22cef-502">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="22cef-503">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-503">TCP</span></span></p></td>
<td><p><span data-ttu-id="22cef-504">Используется для передачи файлов между клиентами Lync и предыдущими клиентами (клиентами Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007 и Live Communications Server 2005).</span><span class="sxs-lookup"><span data-stu-id="22cef-504">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-505">Клиенты</span><span class="sxs-lookup"><span data-stu-id="22cef-505">Clients</span></span></p></td>
<td><p><span data-ttu-id="22cef-506">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="22cef-506">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="22cef-507">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="22cef-507">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="22cef-508">Диапазон портов аудиоподсистемы (необходимо минимум 20 портов)</span><span class="sxs-lookup"><span data-stu-id="22cef-508">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-509">Клиенты</span><span class="sxs-lookup"><span data-stu-id="22cef-509">Clients</span></span></p></td>
<td><p><span data-ttu-id="22cef-510">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="22cef-510">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="22cef-511">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="22cef-511">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="22cef-512">Диапазон портов для видео (необходимо минимум 20 портов).</span><span class="sxs-lookup"><span data-stu-id="22cef-512">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-513">Клиенты</span><span class="sxs-lookup"><span data-stu-id="22cef-513">Clients</span></span></p></td>
<td><p><span data-ttu-id="22cef-514">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="22cef-514">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="22cef-515">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-515">TCP</span></span></p></td>
<td><p><span data-ttu-id="22cef-516">Передача файлов в одноранговой сети (для передачи файлов конференц-связи клиенты используют PSOM).</span><span class="sxs-lookup"><span data-stu-id="22cef-516">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22cef-517">Клиенты</span><span class="sxs-lookup"><span data-stu-id="22cef-517">Clients</span></span></p></td>
<td><p><span data-ttu-id="22cef-518">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="22cef-518">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="22cef-519">TCP</span><span class="sxs-lookup"><span data-stu-id="22cef-519">TCP</span></span></p></td>
<td><p><span data-ttu-id="22cef-520">Общий доступ к приложениям.</span><span class="sxs-lookup"><span data-stu-id="22cef-520">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22cef-521">Телефон общего пользования Aastra 6721ip</span><span class="sxs-lookup"><span data-stu-id="22cef-521">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="22cef-522">Стационарный телефон Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="22cef-522">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="22cef-523">IP-телефон HP 4110 (телефон общего доступа)</span><span class="sxs-lookup"><span data-stu-id="22cef-523">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="22cef-524">IP-телефон HP 4120 (стационарный телефон)</span><span class="sxs-lookup"><span data-stu-id="22cef-524">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="22cef-525">IP-телефон общего доступа Polycom CX500</span><span class="sxs-lookup"><span data-stu-id="22cef-525">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="22cef-526">Настольный IP-телефон Polycom CX600</span><span class="sxs-lookup"><span data-stu-id="22cef-526">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="22cef-527">Настольный IP-телефон Polycom CX700</span><span class="sxs-lookup"><span data-stu-id="22cef-527">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="22cef-528">IP-телефон для конференций Polycom CX3000</span><span class="sxs-lookup"><span data-stu-id="22cef-528">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="22cef-529">67/68</span><span class="sxs-lookup"><span data-stu-id="22cef-529">67/68</span></span></p></td>
<td><p><span data-ttu-id="22cef-530">-</span><span class="sxs-lookup"><span data-stu-id="22cef-530">DHCP</span></span></p></td>
<td><p><span data-ttu-id="22cef-531">Используется перечисленными устройствами для поиска сертификата сервера Lync, подготовки полного доменного имени и полного доменного имени регистратора.</span><span class="sxs-lookup"><span data-stu-id="22cef-531">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="22cef-532">**\*** Для настройки определенных портов для этих типов мультимедиа используйте командлет CsConferencingConfiguration (параметры параметры clientmediaportrangeenabled, ClientMediaPort и ClientMediaPortRange).</span><span class="sxs-lookup"><span data-stu-id="22cef-532">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="22cef-533">Клиенты установки программ для Lync автоматически создают на клиентском компьютере необходимые исключения брандмауэра операционной системы.</span><span class="sxs-lookup"><span data-stu-id="22cef-533">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="22cef-534">Порты, используемые для доступа внешних пользователей, необходимы для любого сценария, в котором клиент должен пройти брандмауэр организации (например, любые внешние коммуникации или собрания, размещенные в других организациях).</span><span class="sxs-lookup"><span data-stu-id="22cef-534">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

