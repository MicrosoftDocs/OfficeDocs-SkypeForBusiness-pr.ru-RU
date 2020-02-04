---
title: 'Lync Server 2013: Планирование производительности для постоянного сервера чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Persistent Chat Server
ms:assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615006(v=OCS.15)
ms:contentKeyID: 48184580
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dde4bcb499e38e729850f06bb08590bf537696e5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737029"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="e0675-102">Планирование мощностей для постоянного сервера чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0675-102">Capacity planning for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0675-103">_**Тема последнего изменения:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="e0675-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="e0675-104">Сервер сохраняемого чата может выполнять несколько пользователей в режиме реального времени, которое может быть сохранено для будущего поиска и получения.</span><span class="sxs-lookup"><span data-stu-id="e0675-104">Persistent Chat Server can perform multi-user real-time chat that can persist for future retrieval and search.</span></span> <span data-ttu-id="e0675-105">В отличие от группового обмена мгновенными сообщениями, сохраненных в почтовом ящике пользователя в случае настройки журнала бесед, сеанс сервера для работы с сохраняемым чат остается открытым дольше, а его содержимое сохраняется на сервере, а также сообщения, файлы, URL-адреса и другие данные, которые являются частью Текущая беседа.</span><span class="sxs-lookup"><span data-stu-id="e0675-105">Unlike group instant messaging (IM) that is saved in a user’s mailbox if conversation history is configured, a Persistent Chat Server session stays open longer, and the content is saved on a server, along with the messages, files, URLs, and other data that are part of an ongoing conversation.</span></span>

<span data-ttu-id="e0675-106">Планирование мощностей является важной частью подготовки к развертыванию сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="e0675-106">Capacity planning is an important part of preparing to deploy Persistent Chat Server.</span></span> <span data-ttu-id="e0675-107">Этот раздел содержит подробные сведения о поддерживаемых топологиях серверов и таблицах планирования мощностей, которые можно использовать для определения наилучшей конфигурации развертывания.</span><span class="sxs-lookup"><span data-stu-id="e0675-107">This topic provides details about supported Persistent Chat Server topologies and capacity planning tables that you can use to determine the best configuration for your deployment.</span></span> <span data-ttu-id="e0675-108">Кроме того, здесь описывается, как лучше управлять развертыванием сервера сохраняемого чата, требующего больших мощностей в пиковые значения.</span><span class="sxs-lookup"><span data-stu-id="e0675-108">It also describes how to best manage Persistent Chat Server deployments that require greater capacity at peak times.</span></span>

<span data-ttu-id="e0675-109">Чтобы загрузить сохраняемый сервер чата, ознакомьтесь с [http://go.microsoft.com/fwlink/p/?linkId=209539](http://go.microsoft.com/fwlink/p/?linkid=209539)разрядом "Microsoft Lync Server 13 (сервер сохраняемого чата)".</span><span class="sxs-lookup"><span data-stu-id="e0675-109">To download Persistent Chat Server, see "Microsoft Lync Server 13 Persistent Chat Server" at [http://go.microsoft.com/fwlink/p/?linkId=209539](http://go.microsoft.com/fwlink/p/?linkid=209539).</span></span>

<span data-ttu-id="e0675-110">Подробнее об установке сервера сохраняемого чата можно узнать в разделе [Установка сохраняемого сервера чата в Lync server 2013](lync-server-2013-installing-persistent-chat-server.md) и [Настройка сервера сохраняемого чата в Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="e0675-110">For details about installing Persistent Chat Server, see [Installing Persistent Chat Server in Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md) and [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="e0675-111">Средства поддержки, такие как средство планирования Lync Server, могут помочь вам с планированием производственных мощностей.</span><span class="sxs-lookup"><span data-stu-id="e0675-111">Support tools, such as Lync Server Planning Tool, can further assist you with capacity planning.</span></span> <span data-ttu-id="e0675-112">Подробные сведения о средстве планирования можно найти в разделе [Начало процесса планирования для Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="e0675-112">For details about the Planning Tool, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<div>

## <a name="persistent-chat-server-supported-topologies"></a><span data-ttu-id="e0675-113">Топологии, поддерживаемые сервером сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="e0675-113">Persistent Chat Server Supported Topologies</span></span>

<span data-ttu-id="e0675-114">Вы можете развернуть сохраняемый сервер чата в одном или нескольких пулах серверов, а также с топологией с одним пулом или с несколькими пулами.</span><span class="sxs-lookup"><span data-stu-id="e0675-114">You can deploy Persistent Chat Server in single-server or multiple-server pools, and with single-pool or multiple-pool topology.</span></span>

<span data-ttu-id="e0675-115">Кроме того, мы также поддерживаем сервер стандартных чатов на сервере Standard Edition для новых развертываний Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e0675-115">We now also support Persistent Chat Server on Standard Edition server for new Lync Server 2013 deployments.</span></span> <span data-ttu-id="e0675-116">Тем не менее производительность и масштаб будут затронуты, и так как для этого нового развертывания отсутствует параметр высокой доступности, предполагается, что вы используете это в основном для целей проверки концепции, оценки и т. д.</span><span class="sxs-lookup"><span data-stu-id="e0675-116">However, performance and scale will be affected, and because there is no high availability option for this new deployment, we expect you to use this primarily for the purposes of proof of concept, evaluation, and so on.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e0675-117">За дополнительными сведениями о обеих топологиях ознакомьтесь со статьей <A href="lync-server-2013-planning-for-persistent-chat-server.md">планирование сохраняемого сервера чата в Lync server 2013</A> в этом руководстве и <A href="lync-server-2013-deploying-persistent-chat-server.md">Развертывание постоянного сервера чата в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="e0675-117">For additional details about both topologies, see <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planning for Persistent Chat Server in Lync Server 2013</A> in this documentation set and <A href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="e0675-118">Топология с одним сервером</span><span class="sxs-lookup"><span data-stu-id="e0675-118">Single-Server Topology</span></span>

<span data-ttu-id="e0675-119">Минимальной конфигурацией и простейшим развертыванием сервера сохраняемого чата является единая топология серверного сервера чата.</span><span class="sxs-lookup"><span data-stu-id="e0675-119">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="e0675-120">Для этого развертывания требуется один сервер, на котором запускается сохраняемый сервер чата (при условии, что при этом запускается служба соответствия, если она включена), сервер, на котором размещается база данных SQL Server, и, если требуется соответствие, база данных SQL Server для хранения данные о соответствии требованиям.</span><span class="sxs-lookup"><span data-stu-id="e0675-120">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e0675-121">Вы не можете добавлять дополнительные серверы в пул сервера сохраняемого чата, который запускается как развертывание на едином сервере в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="e0675-121">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="e0675-122">Рекомендуется использовать топологию пула из нескольких серверов, даже если вы используете один сервер.</span><span class="sxs-lookup"><span data-stu-id="e0675-122">We recommend using the multiple-server pool topology, even if you’re using a single server.</span></span> <span data-ttu-id="e0675-123">Это значит, что при необходимости вы сможете добавить дополнительные серверы позже.</span><span class="sxs-lookup"><span data-stu-id="e0675-123">This is so that you’ll be able to add more servers later, if it's necessary.</span></span> 


</div>

<span data-ttu-id="e0675-124">На приведенном ниже рисунке показаны все обязательные и необязательные компоненты топологии для одного серверного переднего плана, в соответствии с требованиями.</span><span class="sxs-lookup"><span data-stu-id="e0675-124">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="e0675-125">**Одиночный сохраняемый сервер чата**</span><span class="sxs-lookup"><span data-stu-id="e0675-125">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="e0675-126">![Топология с одним сервером с помощью службы соответствия требованиям](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Топология с одним сервером с помощью службы соответствия требованиям")</span><span class="sxs-lookup"><span data-stu-id="e0675-126">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="e0675-127">Топология с несколькими серверами</span><span class="sxs-lookup"><span data-stu-id="e0675-127">Multiple-Server Topology</span></span>

<span data-ttu-id="e0675-128">Чтобы обеспечить повышенную емкость и надежность, вы можете развернуть топологию с несколькими серверами, как описано в разделе [планирование сохраняемого сервера чата в Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="e0675-128">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="e0675-129">Многосерверная топология может включать в себя до четырех активных компьютеров, использующих сохраняемый сервер чатов (для конфигураций с высокой доступностью и аварийного восстановления допускается до восьми, но только четыре из них могут быть активными, а оставшиеся четыре — в режиме ожидания).</span><span class="sxs-lookup"><span data-stu-id="e0675-129">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="e0675-130">Каждый сервер может поддерживать столько же пользователей, сколько и 20 000, а общее 80 000 количество одновременных пользователей, которые подключены к постоянному пулу серверов чатов с 4 серверами.</span><span class="sxs-lookup"><span data-stu-id="e0675-130">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="e0675-131">Многосерверная топология такая же, как топология с одним сервером, за исключением случаев, когда сервер размещается на нескольких серверах и может масштабироваться на более высоком уровне.</span><span class="sxs-lookup"><span data-stu-id="e0675-131">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="e0675-132">Несколько компьютеров, использующих сохраняемый сервер чата, должны находиться в том же домене доменных служб Active Directory, что и Lync Server, и служба соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="e0675-132">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="e0675-133">На приведенном ниже рисунке показаны все компоненты топологии с несколькими серверами с несколькими компьютерами, на которых запущены сохраняемый сервер чата, необязательная служба соответствия требованиям и отдельная база данных соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="e0675-133">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="e0675-134">**Несколько серверов для сохраняемого чата**</span><span class="sxs-lookup"><span data-stu-id="e0675-134">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="e0675-135">![Топология с несколькими серверами](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Топология с несколькими серверами")</span><span class="sxs-lookup"><span data-stu-id="e0675-135">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="e0675-136">В развертывании сервера сохраняемого чата, где 80 000 пользователи могут одновременно входить в сохраняемый чат и использовать его, нагрузка распределяется равномерно с 20 000 пользователей на сервер.</span><span class="sxs-lookup"><span data-stu-id="e0675-136">In a four-server Persistent Chat Server deployment, where 80,000 users can be simultaneously signed in to and using Persistent Chat, the load is distributed evenly at 20,000 users per server.</span></span> <span data-ttu-id="e0675-137">Если один сервер становится недоступен, пользователи, подключенные к этому серверу, не смогут получить доступ к сохраняемому серверу чата.</span><span class="sxs-lookup"><span data-stu-id="e0675-137">If one server becomes unavailable, the users who are connected to that server will lose their access to Persistent Chat Server.</span></span> <span data-ttu-id="e0675-138">The disconnected users will be automatically transferred to the remaining servers until the unavailable server is restored.</span><span class="sxs-lookup"><span data-stu-id="e0675-138">The disconnected users will be automatically transferred to the remaining servers until the unavailable server is restored.</span></span> <span data-ttu-id="e0675-139">В зависимости от объема сохраняемого трафика чата в сети эта передача может занять несколько минут или более.</span><span class="sxs-lookup"><span data-stu-id="e0675-139">Depending on the amount of Persistent Chat traffic on the network, this transfer can take a few minutes or longer.</span></span> <span data-ttu-id="e0675-140">Поскольку каждый из оставшихся серверов может размещаться столько, сколько пользователей 30 000, мы рекомендуем восстановить недоступный сервер как можно скорее, чтобы избежать проблем с производительностью.</span><span class="sxs-lookup"><span data-stu-id="e0675-140">Because each of the remaining servers might be hosting as many as 30,000 users, we recommend that you restore the unavailable server as quickly as possible to avoid performance issues.</span></span> <span data-ttu-id="e0675-141">В противном случае можно сделать еще один сервер сохраняемого чата с помощью построителя топологии или командлета Windows PowerShell, **задав параметр-ксперсистентчатактивесервер**.</span><span class="sxs-lookup"><span data-stu-id="e0675-141">Otherwise, you can make another Persistent Chat Server available by using the Topology Builder or the Windows PowerShell cmdlet, **set-CsPersistentChatActiveServer**.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a><span data-ttu-id="e0675-142">Планирование мощности сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="e0675-142">Persistent Chat Server Capacity Planning</span></span>

<span data-ttu-id="e0675-143">Ниже приведены таблицы, с помощью которых можно выполнять планирование мощностей для постоянного сервера чата.</span><span class="sxs-lookup"><span data-stu-id="e0675-143">The following tables can help you with capacity planning for Persistent Chat Server.</span></span> <span data-ttu-id="e0675-144">Они моделируют, как изменение различных параметров сервера сохраняемого чата влияет на возможности мощностей.</span><span class="sxs-lookup"><span data-stu-id="e0675-144">They model how changing various Persistent Chat Server settings affect capacity capabilities.</span></span>

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a><span data-ttu-id="e0675-145">Планирование максимальной емкости сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="e0675-145">Planning Your Maximum Capacity for Persistent Chat Server</span></span>

<span data-ttu-id="e0675-146">Используйте следующую таблицу для определения, какое количество пользователей вы сможете поддерживать.</span><span class="sxs-lookup"><span data-stu-id="e0675-146">Use the following sample table to determine the number of users you will be able to support.</span></span>

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a><span data-ttu-id="e0675-147">Пример максимальной емкости пула серверов сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="e0675-147">Persistent Chat Server pool Maximum Capacity Sample</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0675-148">Активные экземпляры службы сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="e0675-148">Active Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="e0675-149"><em>4</em></span><span class="sxs-lookup"><span data-stu-id="e0675-149"><em>4</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-150">Экземпляры службы сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="e0675-150">Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="e0675-151"><em>8 (4 должны быть неактивными; активным может быть не более 4).</em></span><span class="sxs-lookup"><span data-stu-id="e0675-151"><em>8 (4 must be inactive; only a maximum of 4 can be active)</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0675-152">Активных подключенных пользователей</span><span class="sxs-lookup"><span data-stu-id="e0675-152">Active users connected</span></span></p></td>
<td><p><span data-ttu-id="e0675-153"><em>80,000</em></span><span class="sxs-lookup"><span data-stu-id="e0675-153"><em>80,000</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-154">Всего подготовленных пользователей</span><span class="sxs-lookup"><span data-stu-id="e0675-154">Total provisioned users</span></span></p></td>
<td><p><span data-ttu-id="e0675-155">150,000</span><span class="sxs-lookup"><span data-stu-id="e0675-155">150,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0675-156">Количество конечных точек</span><span class="sxs-lookup"><span data-stu-id="e0675-156">Number of endpoints</span></span></p></td>
<td><p><span data-ttu-id="e0675-157">120,000</span><span class="sxs-lookup"><span data-stu-id="e0675-157">120,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e0675-158">В предыдущем примере для поддержки максимального числа пользователей, которые поддерживаются с помощью сохраняемого сервера чата: четыре сервера или экземпляры службы сохраняемого чата (у них может быть четыре более пассивных сервера, на котором запущены сохраняемые серверы чатов для обеспечения высокой доступности и аварийного восстановления) и 20 000 пользователей на сервере, общее количество активных пользователей 80 000.</span><span class="sxs-lookup"><span data-stu-id="e0675-158">In the preceding sample, the plan is to support the maximum number of users that Persistent Chat Server allows: four servers/instances of the Persistent Chat service (can have four more passive servers running Persistent Chat Server for high availability and disaster recovery) and 20,000 users per server, for a total of 80,000 active users.</span></span>

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a><span data-ttu-id="e0675-159">Планирование мощностей для управления сохраняемым доступом к комнате чата</span><span class="sxs-lookup"><span data-stu-id="e0675-159">Capacity Planning for Managing Persistent Chat Room Access</span></span>

<span data-ttu-id="e0675-160">Приведенный ниже образец таблицы поможет вам спланировать управление сохраняемым доступом к комнатам чата в пуле серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="e0675-160">The following sample table can help you plan for managing Persistent Chat room access in a Persistent Chat Server pool.</span></span>

### <a name="managing-chat-room-access-sample"></a><span data-ttu-id="e0675-161">Пример управления доступом к комнате чата</span><span class="sxs-lookup"><span data-stu-id="e0675-161">Managing Chat Room Access Sample</span></span>

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
<th></th>
<th><span data-ttu-id="e0675-162">Малые комнаты чата</span><span class="sxs-lookup"><span data-stu-id="e0675-162">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="e0675-163">Средние комнаты чата</span><span class="sxs-lookup"><span data-stu-id="e0675-163">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="e0675-164">Большие комнаты чата</span><span class="sxs-lookup"><span data-stu-id="e0675-164">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="e0675-165">Всего</span><span class="sxs-lookup"><span data-stu-id="e0675-165">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0675-166">Размер комнат чата (количество подключенных пользователей)</span><span class="sxs-lookup"><span data-stu-id="e0675-166">Size of chat rooms (number of users connected)</span></span></p></td>
<td><p><span data-ttu-id="e0675-167">30 на комнату</span><span class="sxs-lookup"><span data-stu-id="e0675-167">30 per room</span></span></p></td>
<td><p><span data-ttu-id="e0675-168">150 на комнату</span><span class="sxs-lookup"><span data-stu-id="e0675-168">150 per room</span></span></p></td>
<td><p><span data-ttu-id="e0675-169">16 000 на комнату</span><span class="sxs-lookup"><span data-stu-id="e0675-169">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-170">Комнат чата</span><span class="sxs-lookup"><span data-stu-id="e0675-170">Chat rooms</span></span></p></td>
<td><p><span data-ttu-id="e0675-171">32,000</span><span class="sxs-lookup"><span data-stu-id="e0675-171">32,000</span></span></p></td>
<td><p><span data-ttu-id="e0675-172">1,067</span><span class="sxs-lookup"><span data-stu-id="e0675-172">1,067</span></span></p></td>
<td><p><span data-ttu-id="e0675-173">5-10</span><span class="sxs-lookup"><span data-stu-id="e0675-173">10</span></span></p></td>
<td><p><span data-ttu-id="e0675-174">33,077</span><span class="sxs-lookup"><span data-stu-id="e0675-174">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0675-175">% комнат, которые являются аудиториями</span><span class="sxs-lookup"><span data-stu-id="e0675-175">% of rooms that are auditorium</span></span></p></td>
<td><p><span data-ttu-id="e0675-176">1%</span><span class="sxs-lookup"><span data-stu-id="e0675-176">1%</span></span></p></td>
<td><p><span data-ttu-id="e0675-177">1%</span><span class="sxs-lookup"><span data-stu-id="e0675-177">1%</span></span></p></td>
<td><p><span data-ttu-id="e0675-178">50%</span><span class="sxs-lookup"><span data-stu-id="e0675-178">50%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-179">% открытых комнат</span><span class="sxs-lookup"><span data-stu-id="e0675-179">% of rooms that are open</span></span></p></td>
<td><p><span data-ttu-id="e0675-180">3%</span><span class="sxs-lookup"><span data-stu-id="e0675-180">3%</span></span></p></td>
<td><p><span data-ttu-id="e0675-181">3%</span><span class="sxs-lookup"><span data-stu-id="e0675-181">3%</span></span></p></td>
<td><p><span data-ttu-id="e0675-182">50%</span><span class="sxs-lookup"><span data-stu-id="e0675-182">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0675-183">Открытых комнат (без явного членства)</span><span class="sxs-lookup"><span data-stu-id="e0675-183">Open rooms (no explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="e0675-184">960</span><span class="sxs-lookup"><span data-stu-id="e0675-184">960</span></span></p></td>
<td><p><span data-ttu-id="e0675-185">32</span><span class="sxs-lookup"><span data-stu-id="e0675-185">32</span></span></p></td>
<td><p><span data-ttu-id="e0675-186">5</span><span class="sxs-lookup"><span data-stu-id="e0675-186">5</span></span></p></td>
<td><p><span data-ttu-id="e0675-187">997</span><span class="sxs-lookup"><span data-stu-id="e0675-187">997</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-188">Закрытых комнат (обычных комнат с явным членством)</span><span class="sxs-lookup"><span data-stu-id="e0675-188">Non-open rooms (regular rooms with explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="e0675-189">31,040</span><span class="sxs-lookup"><span data-stu-id="e0675-189">31,040</span></span></p></td>
<td><p><span data-ttu-id="e0675-190">1.035</span><span class="sxs-lookup"><span data-stu-id="e0675-190">1.035</span></span></p></td>
<td><p><span data-ttu-id="e0675-191">5</span><span class="sxs-lookup"><span data-stu-id="e0675-191">5</span></span></p></td>
<td><p><span data-ttu-id="e0675-192">32,080</span><span class="sxs-lookup"><span data-stu-id="e0675-192">32,080</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0675-193">Комнат-аудиторий (дополнительный вход для выступающих)</span><span class="sxs-lookup"><span data-stu-id="e0675-193">Auditorium rooms (additional presenters entry)</span></span></p></td>
<td><p><span data-ttu-id="e0675-194">до</span><span class="sxs-lookup"><span data-stu-id="e0675-194">0</span></span></p></td>
<td><p><span data-ttu-id="e0675-195">32</span><span class="sxs-lookup"><span data-stu-id="e0675-195">32</span></span></p></td>
<td><p><span data-ttu-id="e0675-196">5</span><span class="sxs-lookup"><span data-stu-id="e0675-196">5</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-197">Комнат, управляемых с помощью прямого членства</span><span class="sxs-lookup"><span data-stu-id="e0675-197">Rooms managed by direct membership</span></span></p></td>
<td><p><span data-ttu-id="e0675-198">50%</span><span class="sxs-lookup"><span data-stu-id="e0675-198">50%</span></span></p></td>
<td><p><span data-ttu-id="e0675-199">10%</span><span class="sxs-lookup"><span data-stu-id="e0675-199">10%</span></span></p></td>
<td><p><span data-ttu-id="e0675-200">0%</span><span class="sxs-lookup"><span data-stu-id="e0675-200">0%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0675-201">Комнат, управляемых с помощью групп пользователей</span><span class="sxs-lookup"><span data-stu-id="e0675-201">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="e0675-202">50%</span><span class="sxs-lookup"><span data-stu-id="e0675-202">50%</span></span></p></td>
<td><p><span data-ttu-id="e0675-203">90%</span><span class="sxs-lookup"><span data-stu-id="e0675-203">90%</span></span></p></td>
<td><p><span data-ttu-id="e0675-204">100%</span><span class="sxs-lookup"><span data-stu-id="e0675-204">100%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-205">Групп пользователей в каждом списке членов комнаты чата для открытых комнат (без явного указания)</span><span class="sxs-lookup"><span data-stu-id="e0675-205">User groups in each chat room's membership list for open rooms (not specified explicitly)</span></span></p></td>
<td><p><span data-ttu-id="e0675-206">до</span><span class="sxs-lookup"><span data-stu-id="e0675-206">0</span></span></p></td>
<td><p><span data-ttu-id="e0675-207">до</span><span class="sxs-lookup"><span data-stu-id="e0675-207">0</span></span></p></td>
<td><p><span data-ttu-id="e0675-208">до</span><span class="sxs-lookup"><span data-stu-id="e0675-208">0</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0675-209">Пользователей в каждом списке членов комнаты чата для закрытых комнат</span><span class="sxs-lookup"><span data-stu-id="e0675-209">Users in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="e0675-210">30</span><span class="sxs-lookup"><span data-stu-id="e0675-210">30</span></span></p></td>
<td><p><span data-ttu-id="e0675-211">150</span><span class="sxs-lookup"><span data-stu-id="e0675-211">150</span></span></p></td>
<td><p><span data-ttu-id="e0675-212">16,000</span><span class="sxs-lookup"><span data-stu-id="e0675-212">16,000</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-213">Групп пользователей в каждом списке членов комнаты чата для закрытых комнат</span><span class="sxs-lookup"><span data-stu-id="e0675-213">User groups in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="e0675-214">3</span><span class="sxs-lookup"><span data-stu-id="e0675-214">3</span></span></p></td>
<td><p><span data-ttu-id="e0675-215">5</span><span class="sxs-lookup"><span data-stu-id="e0675-215">5</span></span></p></td>
<td><p><span data-ttu-id="e0675-216">5-10</span><span class="sxs-lookup"><span data-stu-id="e0675-216">10</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0675-217">Пользователей и групп пользователей в каждом списке управляющих комнаты чата (для открытых и закрытых комнат)</span><span class="sxs-lookup"><span data-stu-id="e0675-217">Users and user groups in each chat room's manager list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="e0675-218">6</span><span class="sxs-lookup"><span data-stu-id="e0675-218">6</span></span></p></td>
<td><p><span data-ttu-id="e0675-219">6</span><span class="sxs-lookup"><span data-stu-id="e0675-219">6</span></span></p></td>
<td><p><span data-ttu-id="e0675-220">6</span><span class="sxs-lookup"><span data-stu-id="e0675-220">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-221">Пользователей и групп пользователей в каждом списке выступающих комнаты-аудитории чата (для открытых и закрытых комнат)</span><span class="sxs-lookup"><span data-stu-id="e0675-221">Users and user groups in each auditorium chat room's presenters list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="e0675-222">6</span><span class="sxs-lookup"><span data-stu-id="e0675-222">6</span></span></p></td>
<td><p><span data-ttu-id="e0675-223">6</span><span class="sxs-lookup"><span data-stu-id="e0675-223">6</span></span></p></td>
<td><p><span data-ttu-id="e0675-224">6</span><span class="sxs-lookup"><span data-stu-id="e0675-224">6</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0675-225">Субъектов членства на основе пользователей во всех закрытых комнатах</span><span class="sxs-lookup"><span data-stu-id="e0675-225">User-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="e0675-226">465,600</span><span class="sxs-lookup"><span data-stu-id="e0675-226">465,600</span></span></p></td>
<td><p><span data-ttu-id="e0675-227">15,520</span><span class="sxs-lookup"><span data-stu-id="e0675-227">15,520</span></span></p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-228">Субъектов членства на основе групп пользователей во всех закрытых комнатах</span><span class="sxs-lookup"><span data-stu-id="e0675-228">User-group-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="e0675-229">46,560</span><span class="sxs-lookup"><span data-stu-id="e0675-229">46,560</span></span></p></td>
<td><p><span data-ttu-id="e0675-230">4656</span><span class="sxs-lookup"><span data-stu-id="e0675-230">4656</span></span></p></td>
<td><p><span data-ttu-id="e0675-231">50</span><span class="sxs-lookup"><span data-stu-id="e0675-231">50</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0675-232">Субъектов на основе пользователей и групп пользователей во всех комнатах-аудиториях чата</span><span class="sxs-lookup"><span data-stu-id="e0675-232">Users and user groups based entities across all auditorium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="e0675-233">до</span><span class="sxs-lookup"><span data-stu-id="e0675-233">0</span></span></p></td>
<td><p><span data-ttu-id="e0675-234">192</span><span class="sxs-lookup"><span data-stu-id="e0675-234">192</span></span></p></td>
<td><p><span data-ttu-id="e0675-235">50</span><span class="sxs-lookup"><span data-stu-id="e0675-235">50</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-236">Субъектов управления на основе пользователей и групп пользователей во всех списках управляющих комнат чата</span><span class="sxs-lookup"><span data-stu-id="e0675-236">Users and user groups based manager entities across all chat rooms manager lists</span></span></p></td>
<td><p><span data-ttu-id="e0675-237">192,000</span><span class="sxs-lookup"><span data-stu-id="e0675-237">192,000</span></span></p></td>
<td><p><span data-ttu-id="e0675-238">6,400</span><span class="sxs-lookup"><span data-stu-id="e0675-238">6,400</span></span></p></td>
<td><p><span data-ttu-id="e0675-239">60</span><span class="sxs-lookup"><span data-stu-id="e0675-239">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0675-240">Активных пользователей на комнату чата</span><span class="sxs-lookup"><span data-stu-id="e0675-240">Active users per chat room</span></span></p></td>
<td><p><span data-ttu-id="e0675-241"><em>30</em></span><span class="sxs-lookup"><span data-stu-id="e0675-241"><em>30</em></span></span></p></td>
<td><p><span data-ttu-id="e0675-242"><em>150</em></span><span class="sxs-lookup"><span data-stu-id="e0675-242"><em>150</em></span></span></p></td>
<td><p><span data-ttu-id="e0675-243"><em>16,000</em></span><span class="sxs-lookup"><span data-stu-id="e0675-243"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-244">Комнат чата на пользователя</span><span class="sxs-lookup"><span data-stu-id="e0675-244">Chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="e0675-245"><em>12</em></span><span class="sxs-lookup"><span data-stu-id="e0675-245"><em>12</em></span></span></p></td>
<td><p><span data-ttu-id="e0675-246"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="e0675-246"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="e0675-247"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="e0675-247"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="e0675-248"><em>шестнадцат</em></span><span class="sxs-lookup"><span data-stu-id="e0675-248"><em>16</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0675-249">Групп пользователей в каждом списке членов комнаты чата</span><span class="sxs-lookup"><span data-stu-id="e0675-249">User groups in each chat room’s membership list</span></span></p></td>
<td><p><span data-ttu-id="e0675-250"><em>5-10</em></span><span class="sxs-lookup"><span data-stu-id="e0675-250"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="e0675-251"><em>5-10</em></span><span class="sxs-lookup"><span data-stu-id="e0675-251"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="e0675-252"><em>10-15</em></span><span class="sxs-lookup"><span data-stu-id="e0675-252"><em>15</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-253">Комнат, управляемых с помощью групп пользователей</span><span class="sxs-lookup"><span data-stu-id="e0675-253">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="e0675-254"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="e0675-254"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="e0675-255"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="e0675-255"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="e0675-256"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="e0675-256"><em>50%</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0675-257">Субъектов членства на основе групп пользователей во всех комнатах чата</span><span class="sxs-lookup"><span data-stu-id="e0675-257">User-group-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="e0675-258">155,200</span><span class="sxs-lookup"><span data-stu-id="e0675-258">155,200</span></span></p></td>
<td><p><span data-ttu-id="e0675-259">5173</span><span class="sxs-lookup"><span data-stu-id="e0675-259">5173</span></span></p></td>
<td><p><span data-ttu-id="e0675-260">68</span><span class="sxs-lookup"><span data-stu-id="e0675-260">68</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-261">Субъектов членства на основе пользователей во всех комнатах чата</span><span class="sxs-lookup"><span data-stu-id="e0675-261">User-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="e0675-262">465,600</span><span class="sxs-lookup"><span data-stu-id="e0675-262">465,600</span></span></p></td>
<td><p><span data-ttu-id="e0675-263">77,600</span><span class="sxs-lookup"><span data-stu-id="e0675-263">77,600</span></span></p></td>
<td><p><span data-ttu-id="e0675-264">72,000</span><span class="sxs-lookup"><span data-stu-id="e0675-264">72,000</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0675-265">Пользователей и групп пользователей в каждом списке управляющих, выступающих и областей комнаты чата</span><span class="sxs-lookup"><span data-stu-id="e0675-265">Users and user groups in each chat room's manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="e0675-266">6</span><span class="sxs-lookup"><span data-stu-id="e0675-266">6</span></span></p></td>
<td><p><span data-ttu-id="e0675-267">6</span><span class="sxs-lookup"><span data-stu-id="e0675-267">6</span></span></p></td>
<td><p><span data-ttu-id="e0675-268">6</span><span class="sxs-lookup"><span data-stu-id="e0675-268">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-269">Пользователей и групп пользователей во всех списках управляющих, выступающих и областей комнаты чата</span><span class="sxs-lookup"><span data-stu-id="e0675-269">Users and user groups across all chat rooms' manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="e0675-270">192,000</span><span class="sxs-lookup"><span data-stu-id="e0675-270">192,000</span></span></p></td>
<td><p><span data-ttu-id="e0675-271">6400</span><span class="sxs-lookup"><span data-stu-id="e0675-271">6400</span></span></p></td>
<td><p><span data-ttu-id="e0675-272">60</span><span class="sxs-lookup"><span data-stu-id="e0675-272">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0675-273">Элементов управления доступом</span><span class="sxs-lookup"><span data-stu-id="e0675-273">Access control entries</span></span></p></td>
<td><p><span data-ttu-id="e0675-274">704,160</span><span class="sxs-lookup"><span data-stu-id="e0675-274">704,160</span></span></p></td>
<td><p><span data-ttu-id="e0675-275">26,768</span><span class="sxs-lookup"><span data-stu-id="e0675-275">26,768</span></span></p></td>
<td><p><span data-ttu-id="e0675-276">160</span><span class="sxs-lookup"><span data-stu-id="e0675-276">160</span></span></p></td>
<td><p><span data-ttu-id="e0675-277">731,088</span><span class="sxs-lookup"><span data-stu-id="e0675-277">731,088</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-278">Максимальное количество элементов управления доступом</span><span class="sxs-lookup"><span data-stu-id="e0675-278">Maximum access control entries</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="e0675-279">2,000,000</span><span class="sxs-lookup"><span data-stu-id="e0675-279">2,000,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e0675-280">В предыдущем примере при развертывании серверов сохраняемого чата в соответствии с рекомендованными рекомендациями они могут поддерживать до 80 000 активных пользователей в пуле из четырех серверов с поддержкой соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="e0675-280">In the preceding sample, when you deploy the Persistent Chat Servers according to the recommended guidelines, they can handle up to 80,000 active users across a four-server pool with compliance enabled.</span></span>

<span data-ttu-id="e0675-281">В данном примере приведены комнаты чата, классифицируемые как малые (30 активных пользователей в любое время), средние (150 активных пользователей) и большие (16 000 активных пользователей).</span><span class="sxs-lookup"><span data-stu-id="e0675-281">This sample shows chat rooms categorized as small (30 active users at any given time), medium (150 active users), and large (16,000 active users).</span></span> <span data-ttu-id="e0675-282">Количество комнат чатов определенного размера вычисляется на основе общего числа:</span><span class="sxs-lookup"><span data-stu-id="e0675-282">The number of chat rooms of a certain size is computed based on the total number of:</span></span>

  - <span data-ttu-id="e0675-283">активных пользователей в системе;</span><span class="sxs-lookup"><span data-stu-id="e0675-283">Active users in the system</span></span>

  - <span data-ttu-id="e0675-284">активных пользователей в комнатах чата определенного размера;</span><span class="sxs-lookup"><span data-stu-id="e0675-284">Active users in chat rooms of the given size</span></span>

  - <span data-ttu-id="e0675-285">комнат чата определенного размера, к которым присоединяется один пользователь.</span><span class="sxs-lookup"><span data-stu-id="e0675-285">Chat rooms of the given size that a single user joins</span></span>

<span data-ttu-id="e0675-p111">В предыдущей таблице планирования мощности для каждой комнаты чата указывается число элементов управления доступом, связанных с этой комнатой чата, включая элементы, назначенные непосредственно этой комнате чата. Управлять доступом к отдельным комнатам чата можно с помощью списков управления доступом (ACL). Кроме того, можно управлять доступом на уровне категорий. В ACL отдельный элемент управления доступом может быть либо группой пользователей (такой как группа безопасности или список рассылки), либо одним пользователем. Можно определять элементы управления доступом для управляющих, выступающих и членов комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="e0675-p111">For each chat room, the preceding capacity planning table specifies the number of access control entries that are associated with the chat room, including entries that are assigned directly to the chat room. You can control access to individual chat rooms by using access control lists (ACLs). You can also control access at the category level. In an ACL, an individual access control entry can be either a user group—for example, a security group, a distribution list, or a single user. You can define access control entries for chat room managers, presenters, and members.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e0675-p112">При планировании стратегии управления комнатами чата следует иметь в виду, что разрешено 2 миллиона элементов управления доступом. Если вычисленное количество элементов управления доступом превышает 2 миллиона, это может значительно ухудшить производительность сервера. Чтобы такая проблема не возникала, везде, где это возможно, старайтесь использовать в элементах управления доступом группы пользователей, а не отдельных пользователей.</span><span class="sxs-lookup"><span data-stu-id="e0675-p112">In planning your strategy for managing chat rooms, keep in mind that the total number of allowed access control entries is 2 million. If the calculated access control entries exceed 2 million, server performance could degrade significantly. To avoid this issue, whenever possible, be sure that your access control entries are user groups instead of individual users.</span></span>



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a><span data-ttu-id="e0675-294">Планирование мощностей для управления доступом к комнате чата по приглашению</span><span class="sxs-lookup"><span data-stu-id="e0675-294">Capacity Planning for Managing Chat Room Access by Invitation</span></span>

<span data-ttu-id="e0675-295">Вы можете использовать следующую таблицу Планирование мощностей, чтобы узнать количество приглашений, которые будут создаваться и храниться в базе данных сохраняемого чата, если она настроена на отправку приглашений.</span><span class="sxs-lookup"><span data-stu-id="e0675-295">You can use the following capacity planning table to understand the number of invitations that Persistent Chat Server creates and stores in the Persistent Chat database when it is configured to send invitations.</span></span> <span data-ttu-id="e0675-296">Вы можете управлять приглашениями в категории с помощью страницы **параметров категории комнаты чата** на панели управления Lync Server или командлета Windows PowerShell **Set-ксперсистентчаткатегори**.</span><span class="sxs-lookup"><span data-stu-id="e0675-296">You manage invitations on the Category by using the **Chat Room Category settings** page in the Lync Server Control Panel, or by using the Windows PowerShell cmdlet, **set-csPersistentChatCategory**.</span></span> <span data-ttu-id="e0675-297">Вы можете управлять приглашениями в комнате чата (в строке с разрешающей категорией) с помощью страницы **управления комнатой** , запущенной из клиента Lync, или с помощью командлета Windows PowerShell **Set-ксперсистентчатрум**.</span><span class="sxs-lookup"><span data-stu-id="e0675-297">You can manage invitations on a chat room (in line with what the category allows) by using the **Room Management** page launched from the Lync client, or by using a Windows PowerShell cmdlet, **set-csPersistentChatRoom**.</span></span>

<span data-ttu-id="e0675-298">В данных примера в следующей таблице предполагается, что на странице параметров **Комнаты чата** для 50% всех комнат чата для параметра **Приглашения** установлено значение **Да**.</span><span class="sxs-lookup"><span data-stu-id="e0675-298">The sample data in the following table assumes that, on the **Chat room settings** page for 50 percent of all chat rooms, the **Invitations** option is set to **Yes**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e0675-299">Если рассчитанное количество приглашений, создаваемых сервером, превышает 1 миллион, то производительность сервера может значительно снизиться.</span><span class="sxs-lookup"><span data-stu-id="e0675-299">If the calculated value for the number of invitations that is generated by the server exceeds 1 million, server performance could degrade significantly.</span></span> <span data-ttu-id="e0675-300">Чтобы избежать этой ошибки, не забудьте минимизировать количество комнат чатов, настроенных для отправки приглашений, или ограничить количество пользователей, которые могут присоединиться к комнатам чатов, настроенным для отправки приглашений.</span><span class="sxs-lookup"><span data-stu-id="e0675-300">To avoid this issue, be sure that you minimize the number of chat rooms that are configured to send invitations or restrict the number of users who can join chat rooms that have been configured to send invitations.</span></span>



</div>

### <a name="chat-room-access-by-invitation-sample"></a><span data-ttu-id="e0675-301">Пример приглашения на доступ к комнате чата</span><span class="sxs-lookup"><span data-stu-id="e0675-301">Chat Room Access by Invitation Sample</span></span>

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
<th></th>
<th><span data-ttu-id="e0675-302">Малые комнаты чата</span><span class="sxs-lookup"><span data-stu-id="e0675-302">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="e0675-303">Средние комнаты чата</span><span class="sxs-lookup"><span data-stu-id="e0675-303">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="e0675-304">Большие комнаты чата</span><span class="sxs-lookup"><span data-stu-id="e0675-304">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="e0675-305">Всего</span><span class="sxs-lookup"><span data-stu-id="e0675-305">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0675-306">Пользователей, имеющих доступ к комнате чата</span><span class="sxs-lookup"><span data-stu-id="e0675-306">Users who can access chat room</span></span></p></td>
<td><p><span data-ttu-id="e0675-307">30 на комнату</span><span class="sxs-lookup"><span data-stu-id="e0675-307">30 per room</span></span></p></td>
<td><p><span data-ttu-id="e0675-308">150 на комнату</span><span class="sxs-lookup"><span data-stu-id="e0675-308">150 per room</span></span></p></td>
<td><p><span data-ttu-id="e0675-309">16 000 на комнату</span><span class="sxs-lookup"><span data-stu-id="e0675-309">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-310">Процент комнат, имеющих приглашения</span><span class="sxs-lookup"><span data-stu-id="e0675-310">Percentage of rooms that have invitations</span></span></p></td>
<td><p><span data-ttu-id="e0675-311">50%</span><span class="sxs-lookup"><span data-stu-id="e0675-311">50%</span></span></p></td>
<td><p><span data-ttu-id="e0675-312">50%</span><span class="sxs-lookup"><span data-stu-id="e0675-312">50%</span></span></p></td>
<td><p><span data-ttu-id="e0675-313">50%</span><span class="sxs-lookup"><span data-stu-id="e0675-313">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0675-314">Комнат чата, настроенных для отправки приглашений</span><span class="sxs-lookup"><span data-stu-id="e0675-314">Chat rooms configured to send invitations</span></span></p></td>
<td><p><span data-ttu-id="e0675-315"><em>16,000</em></span><span class="sxs-lookup"><span data-stu-id="e0675-315"><em>16,000</em></span></span></p></td>
<td><p><span data-ttu-id="e0675-316"><em>533</em></span><span class="sxs-lookup"><span data-stu-id="e0675-316"><em>533</em></span></span></p></td>
<td><p><span data-ttu-id="e0675-317"><em>5</em></span><span class="sxs-lookup"><span data-stu-id="e0675-317"><em>5</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-318">Пользователей, имеющих доступ к этой комнате чата</span><span class="sxs-lookup"><span data-stu-id="e0675-318">Users who can access the chat room</span></span></p></td>
<td><p><span data-ttu-id="e0675-319"><em>60</em></span><span class="sxs-lookup"><span data-stu-id="e0675-319"><em>60</em></span></span></p></td>
<td><p><span data-ttu-id="e0675-320"><em>225</em></span><span class="sxs-lookup"><span data-stu-id="e0675-320"><em>225</em></span></span></p></td>
<td><p><span data-ttu-id="e0675-321"><em>16,000</em></span><span class="sxs-lookup"><span data-stu-id="e0675-321"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0675-322">Приглашения, созданные с помощью сохраняемого сервера чата</span><span class="sxs-lookup"><span data-stu-id="e0675-322">Invitations generated by Persistent Chat Server</span></span></p></td>
<td><p><span data-ttu-id="e0675-323">960,000</span><span class="sxs-lookup"><span data-stu-id="e0675-323">960,000</span></span></p></td>
<td><p><span data-ttu-id="e0675-324">120,000</span><span class="sxs-lookup"><span data-stu-id="e0675-324">120,000</span></span></p></td>
<td><p><span data-ttu-id="e0675-325">80,000</span><span class="sxs-lookup"><span data-stu-id="e0675-325">80,000</span></span></p></td>
<td><p><span data-ttu-id="e0675-326">1,160,000</span><span class="sxs-lookup"><span data-stu-id="e0675-326">1,160,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-327">Максимально допустимое количество приглашений</span><span class="sxs-lookup"><span data-stu-id="e0675-327">Maximum allowable number of invitations</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="e0675-328">2,000,000</span><span class="sxs-lookup"><span data-stu-id="e0675-328">2,000,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0675-329">Модель 1. Начать с ожидаемого количества приглашений на комнату в день</span><span class="sxs-lookup"><span data-stu-id="e0675-329">Model 1 - Start with expected number of messages per room per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-330">Норма чата на комнату (в день)</span><span class="sxs-lookup"><span data-stu-id="e0675-330">Chat Rate Per Room (per day)</span></span></p></td>
<td><p><span data-ttu-id="e0675-331">50</span><span class="sxs-lookup"><span data-stu-id="e0675-331">50</span></span></p></td>
<td><p><span data-ttu-id="e0675-332">500</span><span class="sxs-lookup"><span data-stu-id="e0675-332">500</span></span></p></td>
<td><p><span data-ttu-id="e0675-333">100</span><span class="sxs-lookup"><span data-stu-id="e0675-333">100</span></span></p></td>
<td><p><span data-ttu-id="e0675-334">650</span><span class="sxs-lookup"><span data-stu-id="e0675-334">650</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0675-335">Норма чата (в секунду) во всех комнатах</span><span class="sxs-lookup"><span data-stu-id="e0675-335">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="e0675-336">55.56</span><span class="sxs-lookup"><span data-stu-id="e0675-336">55.56</span></span></p></td>
<td><p><span data-ttu-id="e0675-337">18.52</span><span class="sxs-lookup"><span data-stu-id="e0675-337">18.52</span></span></p></td>
<td><p><span data-ttu-id="e0675-338">0.03</span><span class="sxs-lookup"><span data-stu-id="e0675-338">0.03</span></span></p></td>
<td><p><span data-ttu-id="e0675-339">74</span><span class="sxs-lookup"><span data-stu-id="e0675-339">74</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-340">Модель 2. Начать с количества отправляемых сообщений на пользователя в день</span><span class="sxs-lookup"><span data-stu-id="e0675-340">Model 2 - Start with number of messages posted per user per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0675-341">Норма чата на пользователя в день</span><span class="sxs-lookup"><span data-stu-id="e0675-341">Chat rate per user per day</span></span></p></td>
<td><p><span data-ttu-id="e0675-342">10-15</span><span class="sxs-lookup"><span data-stu-id="e0675-342">15</span></span></p></td>
<td><p><span data-ttu-id="e0675-343">5</span><span class="sxs-lookup"><span data-stu-id="e0675-343">5</span></span></p></td>
<td><p><span data-ttu-id="e0675-344">0.1</span><span class="sxs-lookup"><span data-stu-id="e0675-344">0.1</span></span></p></td>
<td><p><span data-ttu-id="e0675-345">средняя</span><span class="sxs-lookup"><span data-stu-id="e0675-345">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-346">Норма чата на комнату (в день)</span><span class="sxs-lookup"><span data-stu-id="e0675-346">Chat rate per room (per day)</span></span></p></td>
<td><p><span data-ttu-id="e0675-347">38</span><span class="sxs-lookup"><span data-stu-id="e0675-347">38</span></span></p></td>
<td><p><span data-ttu-id="e0675-348">375</span><span class="sxs-lookup"><span data-stu-id="e0675-348">375</span></span></p></td>
<td><p><span data-ttu-id="e0675-349">800</span><span class="sxs-lookup"><span data-stu-id="e0675-349">800</span></span></p></td>
<td><p><span data-ttu-id="e0675-350">1,213</span><span class="sxs-lookup"><span data-stu-id="e0675-350">1,213</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0675-351">Норма чата (в секунду) во всех комнатах</span><span class="sxs-lookup"><span data-stu-id="e0675-351">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="e0675-352">41.67</span><span class="sxs-lookup"><span data-stu-id="e0675-352">41.67</span></span></p></td>
<td><p><span data-ttu-id="e0675-353">13.89</span><span class="sxs-lookup"><span data-stu-id="e0675-353">13.89</span></span></p></td>
<td><p><span data-ttu-id="e0675-354">0.28</span><span class="sxs-lookup"><span data-stu-id="e0675-354">0.28</span></span></p></td>
<td><p><span data-ttu-id="e0675-355">56</span><span class="sxs-lookup"><span data-stu-id="e0675-355">56</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="e0675-356">Пользовательская модель «производительность сервера» для сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="e0675-356">Persistent Chat Server Performance User Model</span></span>

<span data-ttu-id="e0675-357">В следующей таблице описаны пользовательские модели для сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="e0675-357">The following table describes the user model for Persistent Chat Server.</span></span> <span data-ttu-id="e0675-358">It provides the basis for the capacity planning requirements and represents a typical organization with 80,000 concurrent users on four servers.</span><span class="sxs-lookup"><span data-stu-id="e0675-358">It provides the basis for the capacity planning requirements and represents a typical organization with 80,000 concurrent users on four servers.</span></span>

### <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="e0675-359">Пользовательская модель «производительность сервера» для сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="e0675-359">Persistent Chat Server Performance User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0675-360">Количество подключенных активных пользователей</span><span class="sxs-lookup"><span data-stu-id="e0675-360">Number of active users connected</span></span></p></td>
<td><p><span data-ttu-id="e0675-361">80,000</span><span class="sxs-lookup"><span data-stu-id="e0675-361">80,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-362">Количество экземпляров службы сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="e0675-362">Number of Persistent Chat Server service instances</span></span></p></td>
<td><p><span data-ttu-id="e0675-363">4</span><span class="sxs-lookup"><span data-stu-id="e0675-363">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0675-364">Размер малых комнат чата</span><span class="sxs-lookup"><span data-stu-id="e0675-364">Size of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="e0675-365">30 пользователей</span><span class="sxs-lookup"><span data-stu-id="e0675-365">30 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-366">Размер средних комнат чата</span><span class="sxs-lookup"><span data-stu-id="e0675-366">Size of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="e0675-367">150 пользователей</span><span class="sxs-lookup"><span data-stu-id="e0675-367">150 users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0675-368">Размер больших комнат чата</span><span class="sxs-lookup"><span data-stu-id="e0675-368">Size of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="e0675-369">16 000 пользователей</span><span class="sxs-lookup"><span data-stu-id="e0675-369">16,000 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-370">Общее количество комнат чата</span><span class="sxs-lookup"><span data-stu-id="e0675-370">Total number of chat rooms</span></span></p></td>
<td><p><span data-ttu-id="e0675-371">33,077</span><span class="sxs-lookup"><span data-stu-id="e0675-371">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0675-372">Количество малых комнат чата</span><span class="sxs-lookup"><span data-stu-id="e0675-372">Number of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="e0675-373">32,000</span><span class="sxs-lookup"><span data-stu-id="e0675-373">32,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-374">Количество средних комнат чата</span><span class="sxs-lookup"><span data-stu-id="e0675-374">Number of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="e0675-375">1,067</span><span class="sxs-lookup"><span data-stu-id="e0675-375">1,067</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0675-376">Количество больших комнат чата</span><span class="sxs-lookup"><span data-stu-id="e0675-376">Number of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="e0675-377">5-10</span><span class="sxs-lookup"><span data-stu-id="e0675-377">10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-378">Общее количество комнат чата на пользователя</span><span class="sxs-lookup"><span data-stu-id="e0675-378">Total number of chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="e0675-379">шестнадцат</span><span class="sxs-lookup"><span data-stu-id="e0675-379">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0675-380">Количество малых комнат чата на пользователя</span><span class="sxs-lookup"><span data-stu-id="e0675-380">Number of small chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="e0675-381">12</span><span class="sxs-lookup"><span data-stu-id="e0675-381">12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-382">Количество средних комнат чата на пользователя</span><span class="sxs-lookup"><span data-stu-id="e0675-382">Number of medium chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="e0675-383">2</span><span class="sxs-lookup"><span data-stu-id="e0675-383">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0675-384">Количество больших комнат чата на пользователя</span><span class="sxs-lookup"><span data-stu-id="e0675-384">Number of large chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="e0675-385">2</span><span class="sxs-lookup"><span data-stu-id="e0675-385">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-386">Количество подключенных комнат на пользователя</span><span class="sxs-lookup"><span data-stu-id="e0675-386">Number of rooms joined per user</span></span></p></td>
<td><p><span data-ttu-id="e0675-387">24</span><span class="sxs-lookup"><span data-stu-id="e0675-387">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0675-388">Максимальная норма подключения</span><span class="sxs-lookup"><span data-stu-id="e0675-388">Peak join rate</span></span></p></td>
<td><p><span data-ttu-id="e0675-389">10 в секунду</span><span class="sxs-lookup"><span data-stu-id="e0675-389">10/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-390">Общая норма чата</span><span class="sxs-lookup"><span data-stu-id="e0675-390">Total chat rate</span></span></p></td>
<td><p><span data-ttu-id="e0675-391">24 в секунду</span><span class="sxs-lookup"><span data-stu-id="e0675-391">24/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0675-392">Норма чата для малых комнат чата</span><span class="sxs-lookup"><span data-stu-id="e0675-392">Chat rate for small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="e0675-393">22.22/second</span><span class="sxs-lookup"><span data-stu-id="e0675-393">22.22/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-394">Норма чата для средних комнат чата</span><span class="sxs-lookup"><span data-stu-id="e0675-394">Chat rate for medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="e0675-395">1.67/second</span><span class="sxs-lookup"><span data-stu-id="e0675-395">1.67/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0675-396">Норма чата для больших комнат чата</span><span class="sxs-lookup"><span data-stu-id="e0675-396">Chat rate for large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="e0675-397">~0.15/second</span><span class="sxs-lookup"><span data-stu-id="e0675-397">~0.15/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-398">Процент комнат чата, настроенных для отправки приглашений</span><span class="sxs-lookup"><span data-stu-id="e0675-398">Percentage of chat rooms configured for invitations</span></span></p></td>
<td><p><span data-ttu-id="e0675-399">50%</span><span class="sxs-lookup"><span data-stu-id="e0675-399">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0675-400">Процент комнат с прямым членством</span><span class="sxs-lookup"><span data-stu-id="e0675-400">Percentage of direct memberships</span></span></p></td>
<td><p><span data-ttu-id="e0675-401">50%</span><span class="sxs-lookup"><span data-stu-id="e0675-401">50%</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-402">Процент комнат с групповым членством</span><span class="sxs-lookup"><span data-stu-id="e0675-402">Percentage of group memberships</span></span></p></td>
<td><p><span data-ttu-id="e0675-403">50%</span><span class="sxs-lookup"><span data-stu-id="e0675-403">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0675-404">Среднее количество принадлежностей предков в доменных службах Active Directory</span><span class="sxs-lookup"><span data-stu-id="e0675-404">Average number of ancestor affiliations in Active Directory Domain Services</span></span></p></td>
<td><p><span data-ttu-id="e0675-405">100 - 200</span><span class="sxs-lookup"><span data-stu-id="e0675-405">100 - 200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-406">Количество подписанных контактов на пользователя</span><span class="sxs-lookup"><span data-stu-id="e0675-406">Number of subscribed contacts per user</span></span></p></td>
<td><p><span data-ttu-id="e0675-407">80</span><span class="sxs-lookup"><span data-stu-id="e0675-407">80</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0675-408">Среднее количество конечных точек на пользователя</span><span class="sxs-lookup"><span data-stu-id="e0675-408">Average number of endpoints per user</span></span></p></td>
<td><p><span data-ttu-id="e0675-409">1.5</span><span class="sxs-lookup"><span data-stu-id="e0675-409">1.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-410">Среднее количество видимых комнат чата на конечную точку</span><span class="sxs-lookup"><span data-stu-id="e0675-410">Average number of visible chat rooms per endpoint</span></span></p></td>
<td><p><span data-ttu-id="e0675-411">1.5</span><span class="sxs-lookup"><span data-stu-id="e0675-411">1.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0675-412">Среднее количество видимых комнат чата на пользователя</span><span class="sxs-lookup"><span data-stu-id="e0675-412">Average number of visible chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="e0675-413">2,25 (50% для 1 комнаты и 50% для 2 комнат); до 6 открытых комнат, по одной на монитор</span><span class="sxs-lookup"><span data-stu-id="e0675-413">2.25 (50% for 1 room and 50% for 2 rooms); Up to 6 rooms open, one per monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-414">Количество участников, опрашиваемых за определенный интервал опроса</span><span class="sxs-lookup"><span data-stu-id="e0675-414">Number of participants polled per interval</span></span></p></td>
<td><p><span data-ttu-id="e0675-415">25 на видимую комнату чата</span><span class="sxs-lookup"><span data-stu-id="e0675-415">25 per visible chat room</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0675-416">Продолжительность интервала опроса</span><span class="sxs-lookup"><span data-stu-id="e0675-416">Length of polling interval</span></span></p></td>
<td><p><span data-ttu-id="e0675-417">5 минут</span><span class="sxs-lookup"><span data-stu-id="e0675-417">5 minutes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-418">Количество опрашиваемых участников в секунду</span><span class="sxs-lookup"><span data-stu-id="e0675-418">Number of participants polled per second</span></span></p></td>
<td><p><span data-ttu-id="e0675-419">15,000</span><span class="sxs-lookup"><span data-stu-id="e0675-419">15,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0675-420">Количество изменений состояния присутствия в час на пользователя</span><span class="sxs-lookup"><span data-stu-id="e0675-420">Number of presence changes per hour per user</span></span></p></td>
<td><p><span data-ttu-id="e0675-421">6</span><span class="sxs-lookup"><span data-stu-id="e0675-421">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0675-422">Количество изменений состояния присутствия в секунду</span><span class="sxs-lookup"><span data-stu-id="e0675-422">Number of presence changes per second</span></span></p></td>
<td><p><span data-ttu-id="e0675-423">133.33</span><span class="sxs-lookup"><span data-stu-id="e0675-423">133.33</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

