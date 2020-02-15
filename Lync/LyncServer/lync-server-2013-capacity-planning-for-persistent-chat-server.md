---
title: 'Lync Server 2013: планирование мощности для сервера сохраняемого чата'
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
ms.openlocfilehash: f20d297e1d127d167aa8acc059f5b6f89cc96d13
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="77cda-102">Планирование емкости для сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77cda-102">Capacity planning for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77cda-103">_**Последнее изменение темы:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="77cda-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="77cda-104">Сервер сохраняемого чата может выполнять многопользовательский чат в режиме реального времени, который может оставаться недоступным для последующего извлечения и поиска.</span><span class="sxs-lookup"><span data-stu-id="77cda-104">Persistent Chat Server can perform multi-user real-time chat that can persist for future retrieval and search.</span></span> <span data-ttu-id="77cda-105">В отличие от службы обмена мгновенными сообщениями, сохраненных в почтовом ящике пользователя при настройке журнала бесед, сеанс сервера сохраняемого чата остается открытым дольше, а его содержимое сохраняется на сервере, а также сообщения, файлы, URL-адреса и другие данные, входящие в состав Текущая беседа.</span><span class="sxs-lookup"><span data-stu-id="77cda-105">Unlike group instant messaging (IM) that is saved in a user’s mailbox if conversation history is configured, a Persistent Chat Server session stays open longer, and the content is saved on a server, along with the messages, files, URLs, and other data that are part of an ongoing conversation.</span></span>

<span data-ttu-id="77cda-106">Планирование мощности является важной частью подготовки к развертыванию сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="77cda-106">Capacity planning is an important part of preparing to deploy Persistent Chat Server.</span></span> <span data-ttu-id="77cda-107">В этом разделе представлены сведения о поддерживаемых топологий сервера сохраняемого чата и таблицах планирования емкости, которые можно использовать для определения наилучшей конфигурации развертывания.</span><span class="sxs-lookup"><span data-stu-id="77cda-107">This topic provides details about supported Persistent Chat Server topologies and capacity planning tables that you can use to determine the best configuration for your deployment.</span></span> <span data-ttu-id="77cda-108">Здесь также описывается, как лучше управлять развертываниями сервера сохраняемого чата, требующими большей емкости в пиковое время.</span><span class="sxs-lookup"><span data-stu-id="77cda-108">It also describes how to best manage Persistent Chat Server deployments that require greater capacity at peak times.</span></span>

<span data-ttu-id="77cda-109">Чтобы скачать сервер сохраняемого чата, обратитесь к разделу "сервер сохраняемого чата Microsoft [http://go.microsoft.com/fwlink/p/?linkId=209539](http://go.microsoft.com/fwlink/p/?linkid=209539)Lync Server 13" по адресу.</span><span class="sxs-lookup"><span data-stu-id="77cda-109">To download Persistent Chat Server, see "Microsoft Lync Server 13 Persistent Chat Server" at [http://go.microsoft.com/fwlink/p/?linkId=209539](http://go.microsoft.com/fwlink/p/?linkid=209539).</span></span>

<span data-ttu-id="77cda-110">Сведения об установке сервера сохраняемого чата приведены в статье Установка сервера сохраняемого [чата в Lync server 2013](lync-server-2013-installing-persistent-chat-server.md) и [Настройка сервера сохраняемого чата в Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="77cda-110">For details about installing Persistent Chat Server, see [Installing Persistent Chat Server in Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md) and [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="77cda-111">Средства поддержки, такие как средство планирования Lync Server, предоставят дополнительную помощь в планировании мощности.</span><span class="sxs-lookup"><span data-stu-id="77cda-111">Support tools, such as Lync Server Planning Tool, can further assist you with capacity planning.</span></span> <span data-ttu-id="77cda-112">Подробнее о средстве планирования можно узнать в статье [Начало процесса планирования для Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="77cda-112">For details about the Planning Tool, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<div>

## <a name="persistent-chat-server-supported-topologies"></a><span data-ttu-id="77cda-113">Поддерживаемые топологии сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="77cda-113">Persistent Chat Server Supported Topologies</span></span>

<span data-ttu-id="77cda-114">Сервер сохраняемого чата можно развернуть в пулах с одним или несколькими серверами, а также с топологией с одним или несколькими пулами.</span><span class="sxs-lookup"><span data-stu-id="77cda-114">You can deploy Persistent Chat Server in single-server or multiple-server pools, and with single-pool or multiple-pool topology.</span></span>

<span data-ttu-id="77cda-115">Теперь мы также поддерживаем сервер сохраняемого чата на сервере Standard Edition для новых развертываний Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77cda-115">We now also support Persistent Chat Server on Standard Edition server for new Lync Server 2013 deployments.</span></span> <span data-ttu-id="77cda-116">Однако будут затронуты производительность и масштаб, и поскольку для этого нового развертывания отсутствует вариант высокого уровня доступности, мы предполагаем, что вы будете использовать это в целях эксперимента или оценки.</span><span class="sxs-lookup"><span data-stu-id="77cda-116">However, performance and scale will be affected, and because there is no high availability option for this new deployment, we expect you to use this primarily for the purposes of proof of concept, evaluation, and so on.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="77cda-117">Для получения дополнительных сведений о обеих топологиях ознакомьтесь с разделом <A href="lync-server-2013-planning-for-persistent-chat-server.md">Планирование сервера сохраняемого чата в Lync server 2013</A> в этом наборе документации и <A href="lync-server-2013-deploying-persistent-chat-server.md">развертывании сервера сохраняемого чата в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="77cda-117">For additional details about both topologies, see <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planning for Persistent Chat Server in Lync Server 2013</A> in this documentation set and <A href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="77cda-118">Топология с одним сервером</span><span class="sxs-lookup"><span data-stu-id="77cda-118">Single-Server Topology</span></span>

<span data-ttu-id="77cda-119">Минимальной конфигурацией и простейшим развертыванием для сервера сохраняемого чата является единая топология сервера сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="77cda-119">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="77cda-120">Для этого развертывания требуется один сервер, на котором выполняется сервер сохраняемого чата (при необходимости выполняется служба соответствия, если включено соответствие), сервер, на котором размещается база данных SQL Server, и если требуется соответствие требованиям, база данных SQL Server для хранения данные о соответствии требованиям.</span><span class="sxs-lookup"><span data-stu-id="77cda-120">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="77cda-121">Невозможно добавить дополнительные серверы в пул серверов сохраняемого чата, который запускается в построителе топологий как развертывание с одним сервером.</span><span class="sxs-lookup"><span data-stu-id="77cda-121">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="77cda-122">Рекомендуется использовать топологию пула с несколькими серверами, даже если вы используете один сервер.</span><span class="sxs-lookup"><span data-stu-id="77cda-122">We recommend using the multiple-server pool topology, even if you’re using a single server.</span></span> <span data-ttu-id="77cda-123">Это значит, что при необходимости вы сможете добавить дополнительные серверы позже.</span><span class="sxs-lookup"><span data-stu-id="77cda-123">This is so that you’ll be able to add more servers later, if it's necessary.</span></span> 


</div>

<span data-ttu-id="77cda-124">На следующем рисунке показаны все обязательные и необязательные компоненты топологии для одного сервера переднего плана сервера сохраняемого чата с соблюдением соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="77cda-124">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="77cda-125">**Единственный сервер сохраняемого чата**</span><span class="sxs-lookup"><span data-stu-id="77cda-125">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="77cda-126">![Топология с одним сервером со службой соответствия требованиям](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Топология с одним сервером со службой соответствия требованиям")</span><span class="sxs-lookup"><span data-stu-id="77cda-126">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="77cda-127">Топология с несколькими серверами</span><span class="sxs-lookup"><span data-stu-id="77cda-127">Multiple-Server Topology</span></span>

<span data-ttu-id="77cda-128">Чтобы повысить производительность и надежность, можно развернуть топологию с несколькими серверами, как описано в статье [Планирование сервера сохраняемого чата в Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="77cda-128">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="77cda-129">Многосерверная топология может включать до четырех активных компьютеров, на которых работает сервер сохраняемого чата (для конфигураций с высокой доступностью и аварийным восстановлением можно указать до восьми, но только четыре из них могут быть активными и оставшиеся четыре в ждущем режиме).</span><span class="sxs-lookup"><span data-stu-id="77cda-129">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="77cda-130">Каждый сервер может поддерживать до 20 000 одновременно работающих пользователей, общее 80 000 количество одновременных пользователей, подключенных к пулу серверов сохраняемого чата с 4 серверами.</span><span class="sxs-lookup"><span data-stu-id="77cda-130">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="77cda-131">Многосерверная топология такая же, как топология с одним сервером, за исключением того, что несколько серверов размещаются в сервере сохраняемого чата и могут масштабироваться на более высоком уровне.</span><span class="sxs-lookup"><span data-stu-id="77cda-131">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="77cda-132">Несколько компьютеров, на которых работает сервер сохраняемого чата, должны находиться в том же домене доменных служб Active Directory, что и Lync Server и служба соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="77cda-132">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="77cda-133">На следующем рисунке показаны все компоненты топологии с несколькими серверами с несколькими компьютерами, на которых работает сервер сохраняемого чата, дополнительная служба соответствия требованиям и отдельная база данных соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="77cda-133">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="77cda-134">**Несколько серверов сохраняемого чата**</span><span class="sxs-lookup"><span data-stu-id="77cda-134">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="77cda-135">![Топология с несколькими серверами](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Топология с несколькими серверами")</span><span class="sxs-lookup"><span data-stu-id="77cda-135">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="77cda-136">В развертывании сервера сохраняемого чата с четырьмя серверами, где 80 000 пользователи могут одновременно войти в сохраняемый чат и использовать сохраняемый чат, нагрузка распределяется равномерно по 20 000 пользователей на сервер.</span><span class="sxs-lookup"><span data-stu-id="77cda-136">In a four-server Persistent Chat Server deployment, where 80,000 users can be simultaneously signed in to and using Persistent Chat, the load is distributed evenly at 20,000 users per server.</span></span> <span data-ttu-id="77cda-137">Если один сервер становится недоступен, то пользователи, подключенные к этому серверу, будут потеряют доступ к серверу сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="77cda-137">If one server becomes unavailable, the users who are connected to that server will lose their access to Persistent Chat Server.</span></span> <span data-ttu-id="77cda-138">Эти отключенные пользователи будут автоматически перемещены на оставшиеся серверы на время восстановления недоступного сервера.</span><span class="sxs-lookup"><span data-stu-id="77cda-138">The disconnected users will be automatically transferred to the remaining servers until the unavailable server is restored.</span></span> <span data-ttu-id="77cda-139">В зависимости от объема трафика сохраняемого чата в сети эта передача может занять несколько минут или более.</span><span class="sxs-lookup"><span data-stu-id="77cda-139">Depending on the amount of Persistent Chat traffic on the network, this transfer can take a few minutes or longer.</span></span> <span data-ttu-id="77cda-140">Поскольку на каждом из оставшихся серверов может оказаться до 30 000 пользователей, рекомендуется восстановить недоступный сервер как можно быстрее, чтобы избежать проблем с производительностью.</span><span class="sxs-lookup"><span data-stu-id="77cda-140">Because each of the remaining servers might be hosting as many as 30,000 users, we recommend that you restore the unavailable server as quickly as possible to avoid performance issues.</span></span> <span data-ttu-id="77cda-141">В противном случае можно сделать еще один сервер сохраняемого чата с помощью построителя топологий или командлета Windows PowerShell **Set – CsPersistentChatActiveServer**.</span><span class="sxs-lookup"><span data-stu-id="77cda-141">Otherwise, you can make another Persistent Chat Server available by using the Topology Builder or the Windows PowerShell cmdlet, **set-CsPersistentChatActiveServer**.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a><span data-ttu-id="77cda-142">Планирование емкости сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="77cda-142">Persistent Chat Server Capacity Planning</span></span>

<span data-ttu-id="77cda-143">Приведенные ниже таблицы помогут при планировании емкости для сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="77cda-143">The following tables can help you with capacity planning for Persistent Chat Server.</span></span> <span data-ttu-id="77cda-144">Они моделируют влияние изменения различных параметров сервера сохраняемого чата на возможности мощности.</span><span class="sxs-lookup"><span data-stu-id="77cda-144">They model how changing various Persistent Chat Server settings affect capacity capabilities.</span></span>

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a><span data-ttu-id="77cda-145">Планирование максимальной емкости для сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="77cda-145">Planning Your Maximum Capacity for Persistent Chat Server</span></span>

<span data-ttu-id="77cda-146">Используйте следующую таблицу для определения, какое количество пользователей вы сможете поддерживать.</span><span class="sxs-lookup"><span data-stu-id="77cda-146">Use the following sample table to determine the number of users you will be able to support.</span></span>

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a><span data-ttu-id="77cda-147">Пример максимальной емкости пула серверов сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="77cda-147">Persistent Chat Server pool Maximum Capacity Sample</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="77cda-148">Активные экземпляры службы сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="77cda-148">Active Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="77cda-149"><em>SP4</em></span><span class="sxs-lookup"><span data-stu-id="77cda-149"><em>4</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-150">Экземпляры службы сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="77cda-150">Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="77cda-151"><em>8 (4 должны быть неактивными; активным может быть не более 4)</em></span><span class="sxs-lookup"><span data-stu-id="77cda-151"><em>8 (4 must be inactive; only a maximum of 4 can be active)</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77cda-152">Активных подключенных пользователей</span><span class="sxs-lookup"><span data-stu-id="77cda-152">Active users connected</span></span></p></td>
<td><p><span data-ttu-id="77cda-153"><em>80 000</em></span><span class="sxs-lookup"><span data-stu-id="77cda-153"><em>80,000</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-154">Всего подготовленных пользователей</span><span class="sxs-lookup"><span data-stu-id="77cda-154">Total provisioned users</span></span></p></td>
<td><p><span data-ttu-id="77cda-155">150 000</span><span class="sxs-lookup"><span data-stu-id="77cda-155">150,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77cda-156">Количество конечных точек</span><span class="sxs-lookup"><span data-stu-id="77cda-156">Number of endpoints</span></span></p></td>
<td><p><span data-ttu-id="77cda-157">120 000</span><span class="sxs-lookup"><span data-stu-id="77cda-157">120,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="77cda-158">В предыдущем примере планируется поддержка максимального числа пользователей, которые поддерживаются сервером сохраняемого чата: четыре сервера/экземпляры службы сохраняемого чата (может иметь до четырех пассивных серверов, на которых работает сервер сохраняемого чата, для обеспечения высокой доступности и аварийного восстановления) и 20 000 пользователей на сервер, общее количество активных пользователей 80 000.</span><span class="sxs-lookup"><span data-stu-id="77cda-158">In the preceding sample, the plan is to support the maximum number of users that Persistent Chat Server allows: four servers/instances of the Persistent Chat service (can have four more passive servers running Persistent Chat Server for high availability and disaster recovery) and 20,000 users per server, for a total of 80,000 active users.</span></span>

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a><span data-ttu-id="77cda-159">Планирование мощности для управления доступом к комнатам сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="77cda-159">Capacity Planning for Managing Persistent Chat Room Access</span></span>

<span data-ttu-id="77cda-160">Приведенный ниже образец таблицы поможет спланировать управление доступом к комнатам сохраняемого чата в пуле серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="77cda-160">The following sample table can help you plan for managing Persistent Chat room access in a Persistent Chat Server pool.</span></span>

### <a name="managing-chat-room-access-sample"></a><span data-ttu-id="77cda-161">Пример управления доступом к комнатам чата</span><span class="sxs-lookup"><span data-stu-id="77cda-161">Managing Chat Room Access Sample</span></span>

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
<th><span data-ttu-id="77cda-162">Малые комнаты чата</span><span class="sxs-lookup"><span data-stu-id="77cda-162">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="77cda-163">Средние комнаты чата</span><span class="sxs-lookup"><span data-stu-id="77cda-163">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="77cda-164">Большие комнаты чата</span><span class="sxs-lookup"><span data-stu-id="77cda-164">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="77cda-165">Всего</span><span class="sxs-lookup"><span data-stu-id="77cda-165">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="77cda-166">Размер комнат чата (количество подключенных пользователей)</span><span class="sxs-lookup"><span data-stu-id="77cda-166">Size of chat rooms (number of users connected)</span></span></p></td>
<td><p><span data-ttu-id="77cda-167">30 на комнату</span><span class="sxs-lookup"><span data-stu-id="77cda-167">30 per room</span></span></p></td>
<td><p><span data-ttu-id="77cda-168">150 на комнату</span><span class="sxs-lookup"><span data-stu-id="77cda-168">150 per room</span></span></p></td>
<td><p><span data-ttu-id="77cda-169">16 000 на комнату</span><span class="sxs-lookup"><span data-stu-id="77cda-169">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-170">Комнат чата</span><span class="sxs-lookup"><span data-stu-id="77cda-170">Chat rooms</span></span></p></td>
<td><p><span data-ttu-id="77cda-171">32 000</span><span class="sxs-lookup"><span data-stu-id="77cda-171">32,000</span></span></p></td>
<td><p><span data-ttu-id="77cda-172">1 067</span><span class="sxs-lookup"><span data-stu-id="77cda-172">1,067</span></span></p></td>
<td><p><span data-ttu-id="77cda-173">10 </span><span class="sxs-lookup"><span data-stu-id="77cda-173">10</span></span></p></td>
<td><p><span data-ttu-id="77cda-174">33 077</span><span class="sxs-lookup"><span data-stu-id="77cda-174">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77cda-175">% комнат, которые являются аудиториями</span><span class="sxs-lookup"><span data-stu-id="77cda-175">% of rooms that are auditorium</span></span></p></td>
<td><p><span data-ttu-id="77cda-176">1 %</span><span class="sxs-lookup"><span data-stu-id="77cda-176">1%</span></span></p></td>
<td><p><span data-ttu-id="77cda-177">1 %</span><span class="sxs-lookup"><span data-stu-id="77cda-177">1%</span></span></p></td>
<td><p><span data-ttu-id="77cda-178">50%</span><span class="sxs-lookup"><span data-stu-id="77cda-178">50%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-179">% открытых комнат</span><span class="sxs-lookup"><span data-stu-id="77cda-179">% of rooms that are open</span></span></p></td>
<td><p><span data-ttu-id="77cda-180">3 %</span><span class="sxs-lookup"><span data-stu-id="77cda-180">3%</span></span></p></td>
<td><p><span data-ttu-id="77cda-181">3 %</span><span class="sxs-lookup"><span data-stu-id="77cda-181">3%</span></span></p></td>
<td><p><span data-ttu-id="77cda-182">50%</span><span class="sxs-lookup"><span data-stu-id="77cda-182">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77cda-183">Открытых комнат (без явного членства)</span><span class="sxs-lookup"><span data-stu-id="77cda-183">Open rooms (no explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="77cda-184">960</span><span class="sxs-lookup"><span data-stu-id="77cda-184">960</span></span></p></td>
<td><p><span data-ttu-id="77cda-185">32</span><span class="sxs-lookup"><span data-stu-id="77cda-185">32</span></span></p></td>
<td><p><span data-ttu-id="77cda-186">5 </span><span class="sxs-lookup"><span data-stu-id="77cda-186">5</span></span></p></td>
<td><p><span data-ttu-id="77cda-187">997</span><span class="sxs-lookup"><span data-stu-id="77cda-187">997</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-188">Закрытых комнат (обычных комнат с явным членством)</span><span class="sxs-lookup"><span data-stu-id="77cda-188">Non-open rooms (regular rooms with explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="77cda-189">31 040</span><span class="sxs-lookup"><span data-stu-id="77cda-189">31,040</span></span></p></td>
<td><p><span data-ttu-id="77cda-190">1,035</span><span class="sxs-lookup"><span data-stu-id="77cda-190">1.035</span></span></p></td>
<td><p><span data-ttu-id="77cda-191">5 </span><span class="sxs-lookup"><span data-stu-id="77cda-191">5</span></span></p></td>
<td><p><span data-ttu-id="77cda-192">32 080</span><span class="sxs-lookup"><span data-stu-id="77cda-192">32,080</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77cda-193">Комнат-аудиторий (дополнительный вход для выступающих)</span><span class="sxs-lookup"><span data-stu-id="77cda-193">Auditorium rooms (additional presenters entry)</span></span></p></td>
<td><p><span data-ttu-id="77cda-194">нуль</span><span class="sxs-lookup"><span data-stu-id="77cda-194">0</span></span></p></td>
<td><p><span data-ttu-id="77cda-195">32</span><span class="sxs-lookup"><span data-stu-id="77cda-195">32</span></span></p></td>
<td><p><span data-ttu-id="77cda-196">5 </span><span class="sxs-lookup"><span data-stu-id="77cda-196">5</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-197">Комнат, управляемых с помощью прямого членства</span><span class="sxs-lookup"><span data-stu-id="77cda-197">Rooms managed by direct membership</span></span></p></td>
<td><p><span data-ttu-id="77cda-198">50%</span><span class="sxs-lookup"><span data-stu-id="77cda-198">50%</span></span></p></td>
<td><p><span data-ttu-id="77cda-199">10 %</span><span class="sxs-lookup"><span data-stu-id="77cda-199">10%</span></span></p></td>
<td><p><span data-ttu-id="77cda-200">0 %</span><span class="sxs-lookup"><span data-stu-id="77cda-200">0%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77cda-201">Комнат, управляемых с помощью групп пользователей</span><span class="sxs-lookup"><span data-stu-id="77cda-201">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="77cda-202">50%</span><span class="sxs-lookup"><span data-stu-id="77cda-202">50%</span></span></p></td>
<td><p><span data-ttu-id="77cda-203">90%</span><span class="sxs-lookup"><span data-stu-id="77cda-203">90%</span></span></p></td>
<td><p><span data-ttu-id="77cda-204">100 %</span><span class="sxs-lookup"><span data-stu-id="77cda-204">100%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-205">Групп пользователей в каждом списке членов комнаты чата для открытых комнат (без явного указания)</span><span class="sxs-lookup"><span data-stu-id="77cda-205">User groups in each chat room's membership list for open rooms (not specified explicitly)</span></span></p></td>
<td><p><span data-ttu-id="77cda-206">нуль</span><span class="sxs-lookup"><span data-stu-id="77cda-206">0</span></span></p></td>
<td><p><span data-ttu-id="77cda-207">нуль</span><span class="sxs-lookup"><span data-stu-id="77cda-207">0</span></span></p></td>
<td><p><span data-ttu-id="77cda-208">нуль</span><span class="sxs-lookup"><span data-stu-id="77cda-208">0</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77cda-209">Пользователей в каждом списке членов комнаты чата для закрытых комнат</span><span class="sxs-lookup"><span data-stu-id="77cda-209">Users in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="77cda-210">более</span><span class="sxs-lookup"><span data-stu-id="77cda-210">30</span></span></p></td>
<td><p><span data-ttu-id="77cda-211">150</span><span class="sxs-lookup"><span data-stu-id="77cda-211">150</span></span></p></td>
<td><p><span data-ttu-id="77cda-212">16 000</span><span class="sxs-lookup"><span data-stu-id="77cda-212">16,000</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-213">Групп пользователей в каждом списке членов комнаты чата для закрытых комнат</span><span class="sxs-lookup"><span data-stu-id="77cda-213">User groups in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="77cda-214">3 </span><span class="sxs-lookup"><span data-stu-id="77cda-214">3</span></span></p></td>
<td><p><span data-ttu-id="77cda-215">5 </span><span class="sxs-lookup"><span data-stu-id="77cda-215">5</span></span></p></td>
<td><p><span data-ttu-id="77cda-216">10 </span><span class="sxs-lookup"><span data-stu-id="77cda-216">10</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77cda-217">Пользователей и групп пользователей в каждом списке управляющих комнаты чата (для открытых и закрытых комнат)</span><span class="sxs-lookup"><span data-stu-id="77cda-217">Users and user groups in each chat room's manager list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="77cda-218">6 </span><span class="sxs-lookup"><span data-stu-id="77cda-218">6</span></span></p></td>
<td><p><span data-ttu-id="77cda-219">6 </span><span class="sxs-lookup"><span data-stu-id="77cda-219">6</span></span></p></td>
<td><p><span data-ttu-id="77cda-220">6 </span><span class="sxs-lookup"><span data-stu-id="77cda-220">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-221">Пользователей и групп пользователей в каждом списке выступающих комнаты-аудитории чата (для открытых и закрытых комнат)</span><span class="sxs-lookup"><span data-stu-id="77cda-221">Users and user groups in each auditorium chat room's presenters list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="77cda-222">6 </span><span class="sxs-lookup"><span data-stu-id="77cda-222">6</span></span></p></td>
<td><p><span data-ttu-id="77cda-223">6 </span><span class="sxs-lookup"><span data-stu-id="77cda-223">6</span></span></p></td>
<td><p><span data-ttu-id="77cda-224">6 </span><span class="sxs-lookup"><span data-stu-id="77cda-224">6</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77cda-225">Субъектов членства на основе пользователей во всех закрытых комнатах</span><span class="sxs-lookup"><span data-stu-id="77cda-225">User-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="77cda-226">465 600</span><span class="sxs-lookup"><span data-stu-id="77cda-226">465,600</span></span></p></td>
<td><p><span data-ttu-id="77cda-227">15 520</span><span class="sxs-lookup"><span data-stu-id="77cda-227">15,520</span></span></p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-228">Субъектов членства на основе групп пользователей во всех закрытых комнатах</span><span class="sxs-lookup"><span data-stu-id="77cda-228">User-group-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="77cda-229">46 560</span><span class="sxs-lookup"><span data-stu-id="77cda-229">46,560</span></span></p></td>
<td><p><span data-ttu-id="77cda-230">4656</span><span class="sxs-lookup"><span data-stu-id="77cda-230">4656</span></span></p></td>
<td><p><span data-ttu-id="77cda-231">50</span><span class="sxs-lookup"><span data-stu-id="77cda-231">50</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77cda-232">Субъектов на основе пользователей и групп пользователей во всех комнатах-аудиториях чата</span><span class="sxs-lookup"><span data-stu-id="77cda-232">Users and user groups based entities across all auditorium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="77cda-233">нуль</span><span class="sxs-lookup"><span data-stu-id="77cda-233">0</span></span></p></td>
<td><p><span data-ttu-id="77cda-234">192</span><span class="sxs-lookup"><span data-stu-id="77cda-234">192</span></span></p></td>
<td><p><span data-ttu-id="77cda-235">50</span><span class="sxs-lookup"><span data-stu-id="77cda-235">50</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-236">Субъектов управления на основе пользователей и групп пользователей во всех списках управляющих комнат чата</span><span class="sxs-lookup"><span data-stu-id="77cda-236">Users and user groups based manager entities across all chat rooms manager lists</span></span></p></td>
<td><p><span data-ttu-id="77cda-237">192 000</span><span class="sxs-lookup"><span data-stu-id="77cda-237">192,000</span></span></p></td>
<td><p><span data-ttu-id="77cda-238">6 400</span><span class="sxs-lookup"><span data-stu-id="77cda-238">6,400</span></span></p></td>
<td><p><span data-ttu-id="77cda-239">60</span><span class="sxs-lookup"><span data-stu-id="77cda-239">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77cda-240">Активных пользователей на комнату чата</span><span class="sxs-lookup"><span data-stu-id="77cda-240">Active users per chat room</span></span></p></td>
<td><p><span data-ttu-id="77cda-241"><em>более</em></span><span class="sxs-lookup"><span data-stu-id="77cda-241"><em>30</em></span></span></p></td>
<td><p><span data-ttu-id="77cda-242"><em>150</em></span><span class="sxs-lookup"><span data-stu-id="77cda-242"><em>150</em></span></span></p></td>
<td><p><span data-ttu-id="77cda-243"><em>16 000</em></span><span class="sxs-lookup"><span data-stu-id="77cda-243"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-244">Комнат чата на пользователя</span><span class="sxs-lookup"><span data-stu-id="77cda-244">Chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="77cda-245"><em>12</em></span><span class="sxs-lookup"><span data-stu-id="77cda-245"><em>12</em></span></span></p></td>
<td><p><span data-ttu-id="77cda-246"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="77cda-246"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="77cda-247"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="77cda-247"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="77cda-248"><em>столбцов</em></span><span class="sxs-lookup"><span data-stu-id="77cda-248"><em>16</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77cda-249">Групп пользователей в каждом списке членов комнаты чата</span><span class="sxs-lookup"><span data-stu-id="77cda-249">User groups in each chat room’s membership list</span></span></p></td>
<td><p><span data-ttu-id="77cda-250"><em>десяти</em></span><span class="sxs-lookup"><span data-stu-id="77cda-250"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="77cda-251"><em>десяти</em></span><span class="sxs-lookup"><span data-stu-id="77cda-251"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="77cda-252"><em>означает</em></span><span class="sxs-lookup"><span data-stu-id="77cda-252"><em>15</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-253">Комнат, управляемых с помощью групп пользователей</span><span class="sxs-lookup"><span data-stu-id="77cda-253">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="77cda-254"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="77cda-254"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="77cda-255"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="77cda-255"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="77cda-256"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="77cda-256"><em>50%</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77cda-257">Субъектов членства на основе групп пользователей во всех комнатах чата</span><span class="sxs-lookup"><span data-stu-id="77cda-257">User-group-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="77cda-258">155 200</span><span class="sxs-lookup"><span data-stu-id="77cda-258">155,200</span></span></p></td>
<td><p><span data-ttu-id="77cda-259">5173</span><span class="sxs-lookup"><span data-stu-id="77cda-259">5173</span></span></p></td>
<td><p><span data-ttu-id="77cda-260">68</span><span class="sxs-lookup"><span data-stu-id="77cda-260">68</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-261">Субъектов членства на основе пользователей во всех комнатах чата</span><span class="sxs-lookup"><span data-stu-id="77cda-261">User-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="77cda-262">465 600</span><span class="sxs-lookup"><span data-stu-id="77cda-262">465,600</span></span></p></td>
<td><p><span data-ttu-id="77cda-263">77 600</span><span class="sxs-lookup"><span data-stu-id="77cda-263">77,600</span></span></p></td>
<td><p><span data-ttu-id="77cda-264">72 000</span><span class="sxs-lookup"><span data-stu-id="77cda-264">72,000</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77cda-265">Пользователей и групп пользователей в каждом списке управляющих, выступающих и областей комнаты чата</span><span class="sxs-lookup"><span data-stu-id="77cda-265">Users and user groups in each chat room's manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="77cda-266">6 </span><span class="sxs-lookup"><span data-stu-id="77cda-266">6</span></span></p></td>
<td><p><span data-ttu-id="77cda-267">6 </span><span class="sxs-lookup"><span data-stu-id="77cda-267">6</span></span></p></td>
<td><p><span data-ttu-id="77cda-268">6 </span><span class="sxs-lookup"><span data-stu-id="77cda-268">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-269">Пользователей и групп пользователей во всех списках управляющих, выступающих и областей комнаты чата</span><span class="sxs-lookup"><span data-stu-id="77cda-269">Users and user groups across all chat rooms' manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="77cda-270">192 000</span><span class="sxs-lookup"><span data-stu-id="77cda-270">192,000</span></span></p></td>
<td><p><span data-ttu-id="77cda-271">6400</span><span class="sxs-lookup"><span data-stu-id="77cda-271">6400</span></span></p></td>
<td><p><span data-ttu-id="77cda-272">60</span><span class="sxs-lookup"><span data-stu-id="77cda-272">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77cda-273">Элементов управления доступом</span><span class="sxs-lookup"><span data-stu-id="77cda-273">Access control entries</span></span></p></td>
<td><p><span data-ttu-id="77cda-274">704 160</span><span class="sxs-lookup"><span data-stu-id="77cda-274">704,160</span></span></p></td>
<td><p><span data-ttu-id="77cda-275">26 768</span><span class="sxs-lookup"><span data-stu-id="77cda-275">26,768</span></span></p></td>
<td><p><span data-ttu-id="77cda-276">160</span><span class="sxs-lookup"><span data-stu-id="77cda-276">160</span></span></p></td>
<td><p><span data-ttu-id="77cda-277">731 088</span><span class="sxs-lookup"><span data-stu-id="77cda-277">731,088</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-278">Максимальное количество элементов управления доступом</span><span class="sxs-lookup"><span data-stu-id="77cda-278">Maximum access control entries</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="77cda-279">2 000 000</span><span class="sxs-lookup"><span data-stu-id="77cda-279">2,000,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="77cda-280">В предыдущем примере, при развертывании серверов сохраняемого чата в соответствии с рекомендациями, они могут обрабатывать до 80 000 активных пользователей в пуле из четырех серверов с включенной поддержкой соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="77cda-280">In the preceding sample, when you deploy the Persistent Chat Servers according to the recommended guidelines, they can handle up to 80,000 active users across a four-server pool with compliance enabled.</span></span>

<span data-ttu-id="77cda-p110">В данном примере приведены комнаты чата, классифицируемые как малые (30 активных пользователей в любое время), средние (150 активных пользователей) и большие (16 000 активных пользователей). Количество комнат чата разного размера зависит от общего числа:</span><span class="sxs-lookup"><span data-stu-id="77cda-p110">This sample shows chat rooms categorized as small (30 active users at any given time), medium (150 active users), and large (16,000 active users). The number of chat rooms of a certain size is computed based on the total number of:</span></span>

  - <span data-ttu-id="77cda-283">активных пользователей в системе;</span><span class="sxs-lookup"><span data-stu-id="77cda-283">Active users in the system</span></span>

  - <span data-ttu-id="77cda-284">активных пользователей в комнатах чата определенного размера;</span><span class="sxs-lookup"><span data-stu-id="77cda-284">Active users in chat rooms of the given size</span></span>

  - <span data-ttu-id="77cda-285">комнат чата определенного размера, к которым присоединяется один пользователь.</span><span class="sxs-lookup"><span data-stu-id="77cda-285">Chat rooms of the given size that a single user joins</span></span>

<span data-ttu-id="77cda-p111">В предыдущей таблице планирования мощности для каждой комнаты чата указывается число элементов управления доступом, связанных с этой комнатой чата, включая элементы, назначенные непосредственно этой комнате чата. Управлять доступом к отдельным комнатам чата можно с помощью списков управления доступом (ACL). Кроме того, можно управлять доступом на уровне категорий. В ACL отдельный элемент управления доступом может быть либо группой пользователей (такой как группа безопасности или список рассылки), либо одним пользователем. Можно определять элементы управления доступом для управляющих, выступающих и членов комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="77cda-p111">For each chat room, the preceding capacity planning table specifies the number of access control entries that are associated with the chat room, including entries that are assigned directly to the chat room. You can control access to individual chat rooms by using access control lists (ACLs). You can also control access at the category level. In an ACL, an individual access control entry can be either a user group—for example, a security group, a distribution list, or a single user. You can define access control entries for chat room managers, presenters, and members.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="77cda-p112">При планировании стратегии управления комнатами чата следует иметь в виду, что разрешено 2 миллиона элементов управления доступом. Если вычисленное количество элементов управления доступом превышает 2 миллиона, это может значительно ухудшить серверную производительность. Чтобы такая проблема не возникала, везде, где это возможно, старайтесь использовать в элементах управления доступом группы пользователей, а не отдельных пользователей.</span><span class="sxs-lookup"><span data-stu-id="77cda-p112">In planning your strategy for managing chat rooms, keep in mind that the total number of allowed access control entries is 2 million. If the calculated access control entries exceed 2 million, server performance could degrade significantly. To avoid this issue, whenever possible, be sure that your access control entries are user groups instead of individual users.</span></span>



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a><span data-ttu-id="77cda-294">Планирование мощности для управления доступом к комнатам чата по приглашению</span><span class="sxs-lookup"><span data-stu-id="77cda-294">Capacity Planning for Managing Chat Room Access by Invitation</span></span>

<span data-ttu-id="77cda-295">Можно использовать следующую таблицу планирования мощности, чтобы определить количество приглашений, которые сервер сохраняемого чата создает и сохраняет в базе данных сохраняемого чата, когда она настроена на отправку приглашений.</span><span class="sxs-lookup"><span data-stu-id="77cda-295">You can use the following capacity planning table to understand the number of invitations that Persistent Chat Server creates and stores in the Persistent Chat database when it is configured to send invitations.</span></span> <span data-ttu-id="77cda-296">Управление приглашениями для категории осуществляется с помощью страницы **Параметры категории комнаты чата** в панели управления Lync Server или с помощью командлета Windows PowerShell **Set-csPersistentChatCategory**.</span><span class="sxs-lookup"><span data-stu-id="77cda-296">You manage invitations on the Category by using the **Chat Room Category settings** page in the Lync Server Control Panel, or by using the Windows PowerShell cmdlet, **set-csPersistentChatCategory**.</span></span> <span data-ttu-id="77cda-297">Вы можете управлять приглашениями в комнате чата (в разделе с возможностью категорий) с помощью страницы **управления комнатами** , запущенной из клиента Lync, или с помощью командлета Windows PowerShell **Set-csPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="77cda-297">You can manage invitations on a chat room (in line with what the category allows) by using the **Room Management** page launched from the Lync client, or by using a Windows PowerShell cmdlet, **set-csPersistentChatRoom**.</span></span>

<span data-ttu-id="77cda-298">В демонстрационных данных следующей таблицы предполагается, что на странице **Chat room settings (Параметры комнаты чата)** для 50% всех комнат чата параметр **Invitations (Приглашения)** установлен в значение **Yes (Да)**.</span><span class="sxs-lookup"><span data-stu-id="77cda-298">The sample data in the following table assumes that, on the **Chat room settings** page for 50 percent of all chat rooms, the **Invitations** option is set to **Yes**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="77cda-299">Если рассчитанное количество приглашений, создаваемых сервером, превышает 1 миллион, то производительность сервера может значительно снизиться.</span><span class="sxs-lookup"><span data-stu-id="77cda-299">If the calculated value for the number of invitations that is generated by the server exceeds 1 million, server performance could degrade significantly.</span></span> <span data-ttu-id="77cda-300">Чтобы избежать этой ситуации, не забудьте минимизировать количество комнат чата, настроенных для отправки приглашений, или ограничить количество пользователей, которые могут присоединиться к комнатам чата, настроенным для отправки приглашений.</span><span class="sxs-lookup"><span data-stu-id="77cda-300">To avoid this issue, be sure that you minimize the number of chat rooms that are configured to send invitations or restrict the number of users who can join chat rooms that have been configured to send invitations.</span></span>



</div>

### <a name="chat-room-access-by-invitation-sample"></a><span data-ttu-id="77cda-301">Пример доступа к комнате чата по приглашению</span><span class="sxs-lookup"><span data-stu-id="77cda-301">Chat Room Access by Invitation Sample</span></span>

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
<th><span data-ttu-id="77cda-302">Малые комнаты чата</span><span class="sxs-lookup"><span data-stu-id="77cda-302">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="77cda-303">Средние комнаты чата</span><span class="sxs-lookup"><span data-stu-id="77cda-303">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="77cda-304">Большие комнаты чата</span><span class="sxs-lookup"><span data-stu-id="77cda-304">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="77cda-305">Всего</span><span class="sxs-lookup"><span data-stu-id="77cda-305">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="77cda-306">Пользователей, имеющих доступ к комнате чата</span><span class="sxs-lookup"><span data-stu-id="77cda-306">Users who can access chat room</span></span></p></td>
<td><p><span data-ttu-id="77cda-307">30 на комнату</span><span class="sxs-lookup"><span data-stu-id="77cda-307">30 per room</span></span></p></td>
<td><p><span data-ttu-id="77cda-308">150 на комнату</span><span class="sxs-lookup"><span data-stu-id="77cda-308">150 per room</span></span></p></td>
<td><p><span data-ttu-id="77cda-309">16 000 на комнату</span><span class="sxs-lookup"><span data-stu-id="77cda-309">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-310">Процент комнат, имеющих приглашения</span><span class="sxs-lookup"><span data-stu-id="77cda-310">Percentage of rooms that have invitations</span></span></p></td>
<td><p><span data-ttu-id="77cda-311">50%</span><span class="sxs-lookup"><span data-stu-id="77cda-311">50%</span></span></p></td>
<td><p><span data-ttu-id="77cda-312">50%</span><span class="sxs-lookup"><span data-stu-id="77cda-312">50%</span></span></p></td>
<td><p><span data-ttu-id="77cda-313">50%</span><span class="sxs-lookup"><span data-stu-id="77cda-313">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77cda-314">Комнат чата, настроенных для отправки приглашений</span><span class="sxs-lookup"><span data-stu-id="77cda-314">Chat rooms configured to send invitations</span></span></p></td>
<td><p><span data-ttu-id="77cda-315"><em>16 000</em></span><span class="sxs-lookup"><span data-stu-id="77cda-315"><em>16,000</em></span></span></p></td>
<td><p><span data-ttu-id="77cda-316"><em>533</em></span><span class="sxs-lookup"><span data-stu-id="77cda-316"><em>533</em></span></span></p></td>
<td><p><span data-ttu-id="77cda-317"><em>17:00</em></span><span class="sxs-lookup"><span data-stu-id="77cda-317"><em>5</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-318">Пользователей, имеющих доступ к этой комнате чата</span><span class="sxs-lookup"><span data-stu-id="77cda-318">Users who can access the chat room</span></span></p></td>
<td><p><span data-ttu-id="77cda-319"><em>60</em></span><span class="sxs-lookup"><span data-stu-id="77cda-319"><em>60</em></span></span></p></td>
<td><p><span data-ttu-id="77cda-320"><em>225</em></span><span class="sxs-lookup"><span data-stu-id="77cda-320"><em>225</em></span></span></p></td>
<td><p><span data-ttu-id="77cda-321"><em>16 000</em></span><span class="sxs-lookup"><span data-stu-id="77cda-321"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77cda-322">Приглашения, созданные сервером сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="77cda-322">Invitations generated by Persistent Chat Server</span></span></p></td>
<td><p><span data-ttu-id="77cda-323">960 000</span><span class="sxs-lookup"><span data-stu-id="77cda-323">960,000</span></span></p></td>
<td><p><span data-ttu-id="77cda-324">120 000</span><span class="sxs-lookup"><span data-stu-id="77cda-324">120,000</span></span></p></td>
<td><p><span data-ttu-id="77cda-325">80 000</span><span class="sxs-lookup"><span data-stu-id="77cda-325">80,000</span></span></p></td>
<td><p><span data-ttu-id="77cda-326">1 160 000</span><span class="sxs-lookup"><span data-stu-id="77cda-326">1,160,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-327">Максимально допустимое количество приглашений</span><span class="sxs-lookup"><span data-stu-id="77cda-327">Maximum allowable number of invitations</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="77cda-328">2 000 000</span><span class="sxs-lookup"><span data-stu-id="77cda-328">2,000,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77cda-329">Модель 1. Начать с ожидаемого количества приглашений на комнату в день</span><span class="sxs-lookup"><span data-stu-id="77cda-329">Model 1 - Start with expected number of messages per room per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-330">Норма чата на комнату (в день)</span><span class="sxs-lookup"><span data-stu-id="77cda-330">Chat Rate Per Room (per day)</span></span></p></td>
<td><p><span data-ttu-id="77cda-331">50</span><span class="sxs-lookup"><span data-stu-id="77cda-331">50</span></span></p></td>
<td><p><span data-ttu-id="77cda-332">500</span><span class="sxs-lookup"><span data-stu-id="77cda-332">500</span></span></p></td>
<td><p><span data-ttu-id="77cda-333">100</span><span class="sxs-lookup"><span data-stu-id="77cda-333">100</span></span></p></td>
<td><p><span data-ttu-id="77cda-334">650</span><span class="sxs-lookup"><span data-stu-id="77cda-334">650</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77cda-335">Норма чата (в секунду) во всех комнатах</span><span class="sxs-lookup"><span data-stu-id="77cda-335">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="77cda-336">55,56</span><span class="sxs-lookup"><span data-stu-id="77cda-336">55.56</span></span></p></td>
<td><p><span data-ttu-id="77cda-337">18,52</span><span class="sxs-lookup"><span data-stu-id="77cda-337">18.52</span></span></p></td>
<td><p><span data-ttu-id="77cda-338">0,03</span><span class="sxs-lookup"><span data-stu-id="77cda-338">0.03</span></span></p></td>
<td><p><span data-ttu-id="77cda-339">74</span><span class="sxs-lookup"><span data-stu-id="77cda-339">74</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-340">Модель 2. Начать с количества отправляемых сообщений на пользователя в день</span><span class="sxs-lookup"><span data-stu-id="77cda-340">Model 2 - Start with number of messages posted per user per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77cda-341">Норма чата на пользователя в день</span><span class="sxs-lookup"><span data-stu-id="77cda-341">Chat rate per user per day</span></span></p></td>
<td><p><span data-ttu-id="77cda-342">15 </span><span class="sxs-lookup"><span data-stu-id="77cda-342">15</span></span></p></td>
<td><p><span data-ttu-id="77cda-343">5 </span><span class="sxs-lookup"><span data-stu-id="77cda-343">5</span></span></p></td>
<td><p><span data-ttu-id="77cda-344">0,1</span><span class="sxs-lookup"><span data-stu-id="77cda-344">0.1</span></span></p></td>
<td><p><span data-ttu-id="77cda-345">двадцать</span><span class="sxs-lookup"><span data-stu-id="77cda-345">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-346">Норма чата на комнату (в день)</span><span class="sxs-lookup"><span data-stu-id="77cda-346">Chat rate per room (per day)</span></span></p></td>
<td><p><span data-ttu-id="77cda-347">38</span><span class="sxs-lookup"><span data-stu-id="77cda-347">38</span></span></p></td>
<td><p><span data-ttu-id="77cda-348">375</span><span class="sxs-lookup"><span data-stu-id="77cda-348">375</span></span></p></td>
<td><p><span data-ttu-id="77cda-349">800</span><span class="sxs-lookup"><span data-stu-id="77cda-349">800</span></span></p></td>
<td><p><span data-ttu-id="77cda-350">1 213</span><span class="sxs-lookup"><span data-stu-id="77cda-350">1,213</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77cda-351">Норма чата (в секунду) во всех комнатах</span><span class="sxs-lookup"><span data-stu-id="77cda-351">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="77cda-352">41,67</span><span class="sxs-lookup"><span data-stu-id="77cda-352">41.67</span></span></p></td>
<td><p><span data-ttu-id="77cda-353">13,89</span><span class="sxs-lookup"><span data-stu-id="77cda-353">13.89</span></span></p></td>
<td><p><span data-ttu-id="77cda-354">0,28</span><span class="sxs-lookup"><span data-stu-id="77cda-354">0.28</span></span></p></td>
<td><p><span data-ttu-id="77cda-355">56</span><span class="sxs-lookup"><span data-stu-id="77cda-355">56</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="77cda-356">Пользовательская модель производительности сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="77cda-356">Persistent Chat Server Performance User Model</span></span>

<span data-ttu-id="77cda-357">В следующей таблице описывается пользовательская модель для сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="77cda-357">The following table describes the user model for Persistent Chat Server.</span></span> <span data-ttu-id="77cda-358">Эта модель обеспечивает основу для требований планирования мощности и представляет типичную организацию с 80 000 одновременных пользователей на четырех серверах.</span><span class="sxs-lookup"><span data-stu-id="77cda-358">It provides the basis for the capacity planning requirements and represents a typical organization with 80,000 concurrent users on four servers.</span></span>

### <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="77cda-359">Пользовательская модель производительности сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="77cda-359">Persistent Chat Server Performance User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="77cda-360">Количество подключенных активных пользователей</span><span class="sxs-lookup"><span data-stu-id="77cda-360">Number of active users connected</span></span></p></td>
<td><p><span data-ttu-id="77cda-361">80 000</span><span class="sxs-lookup"><span data-stu-id="77cda-361">80,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-362">Количество экземпляров службы сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="77cda-362">Number of Persistent Chat Server service instances</span></span></p></td>
<td><p><span data-ttu-id="77cda-363">4 </span><span class="sxs-lookup"><span data-stu-id="77cda-363">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77cda-364">Размер малых комнат чата</span><span class="sxs-lookup"><span data-stu-id="77cda-364">Size of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="77cda-365">30 пользователей</span><span class="sxs-lookup"><span data-stu-id="77cda-365">30 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-366">Размер средних комнат чата</span><span class="sxs-lookup"><span data-stu-id="77cda-366">Size of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="77cda-367">150 пользователей</span><span class="sxs-lookup"><span data-stu-id="77cda-367">150 users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77cda-368">Размер больших комнат чата</span><span class="sxs-lookup"><span data-stu-id="77cda-368">Size of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="77cda-369">16 000 пользователей</span><span class="sxs-lookup"><span data-stu-id="77cda-369">16,000 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-370">Общее количество комнат чата</span><span class="sxs-lookup"><span data-stu-id="77cda-370">Total number of chat rooms</span></span></p></td>
<td><p><span data-ttu-id="77cda-371">33 077</span><span class="sxs-lookup"><span data-stu-id="77cda-371">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77cda-372">Количество малых комнат чата</span><span class="sxs-lookup"><span data-stu-id="77cda-372">Number of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="77cda-373">32 000</span><span class="sxs-lookup"><span data-stu-id="77cda-373">32,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-374">Количество средних комнат чата</span><span class="sxs-lookup"><span data-stu-id="77cda-374">Number of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="77cda-375">1 067</span><span class="sxs-lookup"><span data-stu-id="77cda-375">1,067</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77cda-376">Количество больших комнат чата</span><span class="sxs-lookup"><span data-stu-id="77cda-376">Number of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="77cda-377">10 </span><span class="sxs-lookup"><span data-stu-id="77cda-377">10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-378">Общее количество комнат чата на пользователя</span><span class="sxs-lookup"><span data-stu-id="77cda-378">Total number of chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="77cda-379">16 </span><span class="sxs-lookup"><span data-stu-id="77cda-379">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77cda-380">Количество малых комнат чата на пользователя</span><span class="sxs-lookup"><span data-stu-id="77cda-380">Number of small chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="77cda-381">12 </span><span class="sxs-lookup"><span data-stu-id="77cda-381">12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-382">Количество средних комнат чата на пользователя</span><span class="sxs-lookup"><span data-stu-id="77cda-382">Number of medium chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="77cda-383">2 </span><span class="sxs-lookup"><span data-stu-id="77cda-383">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77cda-384">Количество больших комнат чата на пользователя</span><span class="sxs-lookup"><span data-stu-id="77cda-384">Number of large chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="77cda-385">2 </span><span class="sxs-lookup"><span data-stu-id="77cda-385">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-386">Количество подключенных комнат на пользователя</span><span class="sxs-lookup"><span data-stu-id="77cda-386">Number of rooms joined per user</span></span></p></td>
<td><p><span data-ttu-id="77cda-387">открыт</span><span class="sxs-lookup"><span data-stu-id="77cda-387">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77cda-388">Максимальная норма подключения</span><span class="sxs-lookup"><span data-stu-id="77cda-388">Peak join rate</span></span></p></td>
<td><p><span data-ttu-id="77cda-389">10/сек</span><span class="sxs-lookup"><span data-stu-id="77cda-389">10/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-390">Общая норма чата</span><span class="sxs-lookup"><span data-stu-id="77cda-390">Total chat rate</span></span></p></td>
<td><p><span data-ttu-id="77cda-391">24 в секунду</span><span class="sxs-lookup"><span data-stu-id="77cda-391">24/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77cda-392">Норма чата для малых комнат чата</span><span class="sxs-lookup"><span data-stu-id="77cda-392">Chat rate for small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="77cda-393">22.22/сек</span><span class="sxs-lookup"><span data-stu-id="77cda-393">22.22/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-394">Норма чата для средних комнат чата</span><span class="sxs-lookup"><span data-stu-id="77cda-394">Chat rate for medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="77cda-395">1.67/сек</span><span class="sxs-lookup"><span data-stu-id="77cda-395">1.67/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77cda-396">Норма чата для больших комнат чата</span><span class="sxs-lookup"><span data-stu-id="77cda-396">Chat rate for large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="77cda-397">~ 0,15/сек</span><span class="sxs-lookup"><span data-stu-id="77cda-397">~0.15/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-398">Процент комнат чата, настроенных для отправки приглашений</span><span class="sxs-lookup"><span data-stu-id="77cda-398">Percentage of chat rooms configured for invitations</span></span></p></td>
<td><p><span data-ttu-id="77cda-399">50%</span><span class="sxs-lookup"><span data-stu-id="77cda-399">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77cda-400">Процент комнат с прямым членством</span><span class="sxs-lookup"><span data-stu-id="77cda-400">Percentage of direct memberships</span></span></p></td>
<td><p><span data-ttu-id="77cda-401">50%</span><span class="sxs-lookup"><span data-stu-id="77cda-401">50%</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-402">Процент комнат с групповым членством</span><span class="sxs-lookup"><span data-stu-id="77cda-402">Percentage of group memberships</span></span></p></td>
<td><p><span data-ttu-id="77cda-403">50%</span><span class="sxs-lookup"><span data-stu-id="77cda-403">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77cda-404">Среднее количество принадлежностей предков в доменных службах Active Directory</span><span class="sxs-lookup"><span data-stu-id="77cda-404">Average number of ancestor affiliations in Active Directory Domain Services</span></span></p></td>
<td><p><span data-ttu-id="77cda-405">100 - 200</span><span class="sxs-lookup"><span data-stu-id="77cda-405">100 - 200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-406">Количество подписанных контактов на пользователя</span><span class="sxs-lookup"><span data-stu-id="77cda-406">Number of subscribed contacts per user</span></span></p></td>
<td><p><span data-ttu-id="77cda-407">80</span><span class="sxs-lookup"><span data-stu-id="77cda-407">80</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77cda-408">Среднее количество конечных точек на пользователя</span><span class="sxs-lookup"><span data-stu-id="77cda-408">Average number of endpoints per user</span></span></p></td>
<td><p><span data-ttu-id="77cda-409">1.5</span><span class="sxs-lookup"><span data-stu-id="77cda-409">1.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-410">Среднее количество видимых комнат чата на конечную точку</span><span class="sxs-lookup"><span data-stu-id="77cda-410">Average number of visible chat rooms per endpoint</span></span></p></td>
<td><p><span data-ttu-id="77cda-411">1.5</span><span class="sxs-lookup"><span data-stu-id="77cda-411">1.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77cda-412">Среднее количество видимых комнат чата на пользователя</span><span class="sxs-lookup"><span data-stu-id="77cda-412">Average number of visible chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="77cda-413">2,25 (50% для 1 комнаты и 50% для 2 комнат); до 6 открытых комнат, по одной на монитор</span><span class="sxs-lookup"><span data-stu-id="77cda-413">2.25 (50% for 1 room and 50% for 2 rooms); Up to 6 rooms open, one per monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-414">Количество участников, опрашиваемых за определенный интервал опроса</span><span class="sxs-lookup"><span data-stu-id="77cda-414">Number of participants polled per interval</span></span></p></td>
<td><p><span data-ttu-id="77cda-415">25 на видимую комнату чата</span><span class="sxs-lookup"><span data-stu-id="77cda-415">25 per visible chat room</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77cda-416">Продолжительность интервала опроса</span><span class="sxs-lookup"><span data-stu-id="77cda-416">Length of polling interval</span></span></p></td>
<td><p><span data-ttu-id="77cda-417">5 минут</span><span class="sxs-lookup"><span data-stu-id="77cda-417">5 minutes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-418">Количество участников, опрашиваемых в секунду</span><span class="sxs-lookup"><span data-stu-id="77cda-418">Number of participants polled per second</span></span></p></td>
<td><p><span data-ttu-id="77cda-419">15,000</span><span class="sxs-lookup"><span data-stu-id="77cda-419">15,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77cda-420">Количество изменений состояния присутствия в час на пользователя</span><span class="sxs-lookup"><span data-stu-id="77cda-420">Number of presence changes per hour per user</span></span></p></td>
<td><p><span data-ttu-id="77cda-421">6 </span><span class="sxs-lookup"><span data-stu-id="77cda-421">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77cda-422">Количество изменений состояния присутствия в секунду</span><span class="sxs-lookup"><span data-stu-id="77cda-422">Number of presence changes per second</span></span></p></td>
<td><p><span data-ttu-id="77cda-423">133,33</span><span class="sxs-lookup"><span data-stu-id="77cda-423">133.33</span></span></p></td>
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

