---
title: 'Lync Server 2013: компоненты и топологии для сервера сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Persistent Chat Server
ms:assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398500(v=OCS.15)
ms:contentKeyID: 48184420
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 320605ab363ff4879811873cc9ce957520b91b29
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="f09ef-102">Компоненты и топологии для сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f09ef-102">Components and topologies for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f09ef-103">_**Последнее изменение темы:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="f09ef-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="f09ef-104">Сервер сохраняемого чата поддерживает конфигурации с одним сервером и конфигурации с несколькими серверами.</span><span class="sxs-lookup"><span data-stu-id="f09ef-104">Persistent Chat Server supports both single-server configurations and multiple-server configurations.</span></span> <span data-ttu-id="f09ef-105">Сервер сохраняемого чата также может выполняться на сервере Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f09ef-105">Persistent Chat Server can also run on a Lync Server 2013 Standard Edition server.</span></span> <span data-ttu-id="f09ef-106">Эти конфигурации состоят из следующих компонентов и топологий сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="f09ef-106">These configurations consist of the following Persistent Chat Server components and topologies.</span></span>

<div>

## <a name="persistent-chat-server-components"></a><span data-ttu-id="f09ef-107">Компоненты сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="f09ef-107">Persistent Chat Server Components</span></span>

<span data-ttu-id="f09ef-108">Для установки последней версии сервера сохраняемого чата необходимы следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="f09ef-108">Installing the latest version of Persistent Chat Server requires the following components:</span></span>

  - <span data-ttu-id="f09ef-109">Один или несколько компьютеров, на которых работает сервер сохраняемого чата, и предоставлены следующие службы:</span><span class="sxs-lookup"><span data-stu-id="f09ef-109">One or more computers running Persistent Chat Server and providing the following services:</span></span>
    
      - <span data-ttu-id="f09ef-110">Служба сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="f09ef-110">Persistent Chat service</span></span>
    
      - <span data-ttu-id="f09ef-111">Служба соответствия, которая включается, если включено соответствие</span><span class="sxs-lookup"><span data-stu-id="f09ef-111">Compliance service, which is turned on if compliance is enabled</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f09ef-112">В Lync Server 2013 веб-службы сохраняемого чата для отправки и загрузки файлов теперь сопоставлены с сервером переднего&nbsp;плана Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f09ef-112">In Lync Server 2013, the Persistent Chat Web Services for File Upload/Download is now collocated with Lync Server 2013&nbsp;Front End Server.</span></span><BR><span data-ttu-id="f09ef-113">Веб-службы сохраняемого чата для управления комнатами чата также размещается с помощью&nbsp;сервера переднего плана Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f09ef-113">The Persistent Chat Web Services for Chat Room Management is also collocated with Lync Server 2013&nbsp;Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="f09ef-114">Серверы (или несколько серверов, если используется зеркальное отображение), на котором размещается серверная база данных SQL Server для размещения базы данных контента сохраняемого чата, в которой хранятся содержимое комнаты чата, комнаты и категории.</span><span class="sxs-lookup"><span data-stu-id="f09ef-114">Server(s) (more than one server if mirroring is used) that host the SQL Server back-end database for hosting the Persistent Chat content database where chat room content, rooms, and categories are stored.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f09ef-115">В серверной базе данных хранятся данные журнала чата, в том числе сведения о категориях и комнатах сохраняемого чата, которые были созданы.</span><span class="sxs-lookup"><span data-stu-id="f09ef-115">The back-end database stores chat history data, including information about categories and Persistent Chat rooms that are created.</span></span>

    
    </div>

  - <span data-ttu-id="f09ef-116">Если включено соответствие, сервер (или несколько серверов, если используется зеркальное отображение), на котором размещается серверная база данных SQL Server, в которой размещается база данных соответствия сохраняемого чата, где хранятся события соответствия и содержимое чата для обеспечения соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="f09ef-116">If compliance was enabled, a server(s) (more than one server if mirroring is used) that host the SQL Server back-end database for hosting the Persistent Chat Compliance database, where compliance events and chat content for the purpose of compliance are stored.</span></span>

<span data-ttu-id="f09ef-117">Чтобы администрировать сервер сохраняемого чата с отдельного компьютера (например, консоли администрирования), используйте панель управления Lync Server на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f09ef-117">To administer Persistent Chat Server from a separate computer (such as an administrative console), use the Lync Server Control Panel on the computer.</span></span> <span data-ttu-id="f09ef-118">После этого этот компьютер должен быть развернут в домене доменных служб Active Directory, по крайней мере один сервер глобального каталога в корне леса.</span><span class="sxs-lookup"><span data-stu-id="f09ef-118">This computer must then be deployed in an Active Directory Domain Services domain, with at least one global catalog server in the forest root.</span></span>

<span data-ttu-id="f09ef-119">Дополнительные сведения о требованиях к оборудованию и программному обеспечению для сервера сохраняемого чата приведены [в статье технические требования для сервера сохраняемого чата в Lync server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [поддерживаемое оборудование для Lync Server 2013](lync-server-2013-supported-hardware.md), а также [Поддержка серверного программного обеспечения и инфраструктуры в Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="f09ef-119">For details about hardware and software requirements for Persistent Chat Server, see [Technical requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md), and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="f09ef-120">Поддерживаемые режимы совместного размещения</span><span class="sxs-lookup"><span data-stu-id="f09ef-120">Supported Collocation</span></span>

<span data-ttu-id="f09ef-121">Lync Server 2013 поддерживает различные сценарии совместного использования, что обеспечивает гибкость при использовании нескольких компонентов на одном сервере (если у вас небольшая организация) или для запуска отдельных компонентов на разных серверах (если у вас есть крупная организация, требующая масштабируемость и производительность;</span><span class="sxs-lookup"><span data-stu-id="f09ef-121">Lync Server 2013 supports a variety of collocation scenarios, providing you the flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="f09ef-122">Факторы масштабируемости, безусловно, следует учитывать при принятии решения о размещении компонентов.</span><span class="sxs-lookup"><span data-stu-id="f09ef-122">Scalability factors should certainly be considered before you decide whether to collocate components.</span></span>

<span data-ttu-id="f09ef-123">Служба соответствия сохраняемого чата, если соответствие включено, размещается совместно с сервером переднего плана Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f09ef-123">The Persistent Chat Compliance service, if compliance is enabled, is collocated with the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="f09ef-124">Сервер сохраняемого чата можно развертывать на сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f09ef-124">Persistent Chat Server can be deployed on the Standard Edition server.</span></span> <span data-ttu-id="f09ef-125">Сервер внутреннего сервера сохраняемого чата и база данных соответствия сохраняемого чата можно разместить на сервере Standard Edition на локальном внутреннем сервере SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="f09ef-125">The Persistent Chat Server Back End Server and the Persistent Chat Compliance database can be collocated on the Standard Edition server on the local SQL Server Express Back End Server.</span></span> <span data-ttu-id="f09ef-126">Для получения дополнительных сведений о компонентах, которые можно разместить в этой статье, ознакомьтесь со страницей поддержка [выровненных серверов в Lync server 2013](lync-server-2013-supported-server-collocation.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="f09ef-126">For details about components that can be collocated there, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="f09ef-127">Для Lync Server 2013 Enterprise Edition серверы сохраняемого чата невозможно разместить на сервере Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="f09ef-127">For Lync Server 2013 Enterprise Edition, Persistent Chat Servers cannot be collocated on the Enterprise Edition server.</span></span> <span data-ttu-id="f09ef-128">Базу данных SQL Server для сервера сохраняемого чата можно разместить совместно с базой данных внутреннего сервера пула переднего плана Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="f09ef-128">The SQL Server database for Persistent Chat Server can be collocated with the Back End Server database of an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="f09ef-129">База данных SQL Server для обеспечения соответствия сохраняемого чата также может быть размещена вместе с базой данных внутреннего сервера пула Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="f09ef-129">The SQL Server database for Persistent Chat compliance can also be collocated with the Back End Server database of an Enterprise Edition pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f09ef-130">На сервере, на котором размещена база данных сохраняемого чата, могут размещаться другие базы данных.</span><span class="sxs-lookup"><span data-stu-id="f09ef-130">The server hosting the Persistent Chat database can host other databases.</span></span> <span data-ttu-id="f09ef-131">Тем не менее, если вы рассматриваете размещение базы данных сохраняемого чата с другими базами данных, имейте в виду, что при хранении сообщений, отличных от нескольких пользователей, место на диске, необходимое для базы данных сохраняемого чата, может увеличиться очень большим.</span><span class="sxs-lookup"><span data-stu-id="f09ef-131">However, when you consider collocating the Persistent Chat database with other databases, be aware that if you are storing the messages of more than a few users, the disk space needed by the Persistent Chat database can grow very large.</span></span> <span data-ttu-id="f09ef-132">По этой причине мы не рекомендуем размещать базу данных сохраняемого чата в серверной базе данных.</span><span class="sxs-lookup"><span data-stu-id="f09ef-132">For this reason, we do not recommend collocating the Persistent Chat database with the back-end database.</span></span>



</div>

<span data-ttu-id="f09ef-133">При совместном размещении базы данных сохраняемого чата с серверной базой данных можно использовать один экземпляр SQL Server для любой или всех баз данных, либо можно использовать отдельный экземпляр SQL Server для каждой базы данных со следующими ограничениями:</span><span class="sxs-lookup"><span data-stu-id="f09ef-133">If you collocate the Persistent Chat database with the back-end database, you can either use a single instance of SQL Server for any or all of the databases, or you can use a separate instance of SQL Server for each database, with the following limitation:</span></span>

  - <span data-ttu-id="f09ef-134">Каждый экземпляр SQL Server может содержать только одну серверную базу данных и одну базу данных сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="f09ef-134">Each instance of SQL Server can contain only a single back-end database and a single Persistent Chat database.</span></span>

<span data-ttu-id="f09ef-135">Сведения о совместном размещении всех ролей серверов и баз данных можно найти в статье поддержка [выровненных серверов в Lync server 2013](lync-server-2013-supported-server-collocation.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="f09ef-135">For details about collocation of all server roles and databases, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="persistent-chat-server-topologies"></a><span data-ttu-id="f09ef-136">Топология сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="f09ef-136">Persistent Chat Server Topologies</span></span>

<span data-ttu-id="f09ef-137">Сервер сохраняемого чата поддерживает следующие топологии:</span><span class="sxs-lookup"><span data-stu-id="f09ef-137">Persistent Chat Server supports the following topologies:</span></span>

  - <span data-ttu-id="f09ef-138">Сервер переднего плана Lync Server 2013 Enterprise Edition с одним сервером сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="f09ef-138">Lync Server 2013 Enterprise Edition single server Persistent Chat Server Front End Server</span></span>

  - <span data-ttu-id="f09ef-139">Lync Server 2013 Enterprise Edition сервер переднего плана сервера сохраняемого чата на нескольких серверах</span><span class="sxs-lookup"><span data-stu-id="f09ef-139">Lync Server 2013 Enterprise Edition multiple server Persistent Chat Server Front End Server</span></span>

  - <span data-ttu-id="f09ef-140">Сервер Lync Server 2013 Standard Edition с использованием SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="f09ef-140">Lync Server 2013 Standard Edition server using SQL Server Express</span></span>

  - <span data-ttu-id="f09ef-141">Сервер Lync Server 2013 Standard Edition и сервер сохраняемого чата на отдельном сервере с сервером Standard Edition в качестве сервера следующего прыжка.</span><span class="sxs-lookup"><span data-stu-id="f09ef-141">Lync Server 2013 Standard Edition server and Persistent Chat Server on a separate server using Standard Edition server as the next hop server.</span></span>

<span data-ttu-id="f09ef-142">Сервер сохраняемого чата можно добавить в развертывание Lync Server 2013 с помощью построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="f09ef-142">You can add Persistent Chat Server to your Lync Server 2013 deployment by using Topology Builder.</span></span> <span data-ttu-id="f09ef-143">В топологию можно добавить один сервер или пул серверов сохраняемого чата для нескольких серверов.</span><span class="sxs-lookup"><span data-stu-id="f09ef-143">You can add a single server or a multiple server Persistent Chat Server pool to your topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f09ef-144">После создания пула серверов сохраняемого чата с одним сервером с помощью построителя топологий невозможно добавить в пул дополнительные серверы.</span><span class="sxs-lookup"><span data-stu-id="f09ef-144">After you create a Persistent Chat Server pool with a single server by using Topology Builder, you cannot add additional servers to the pool.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="f09ef-145">Топология с одним сервером</span><span class="sxs-lookup"><span data-stu-id="f09ef-145">Single-Server Topology</span></span>

<span data-ttu-id="f09ef-146">Минимальной конфигурацией и простейшим развертыванием для сервера сохраняемого чата является единая топология сервера сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="f09ef-146">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="f09ef-147">Для этого развертывания требуется один сервер, на котором выполняется сервер сохраняемого чата (при необходимости выполняется служба соответствия, если включено соответствие), сервер, на котором размещается база данных SQL Server, и если требуется соответствие требованиям, база данных SQL Server для хранения данные о соответствии требованиям.</span><span class="sxs-lookup"><span data-stu-id="f09ef-147">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f09ef-148">Невозможно добавить дополнительные серверы в пул серверов сохраняемого чата, который запускается в построителе топологий как развертывание с одним сервером.</span><span class="sxs-lookup"><span data-stu-id="f09ef-148">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="f09ef-149">Рекомендуется использовать топологию пула с несколькими серверами, даже если используется отдельный сервер, так как при необходимости позже можно добавить дополнительные серверы.</span><span class="sxs-lookup"><span data-stu-id="f09ef-149">We recommend using the multiple-server pool topology, even if you’re using a single server, so that you can add more servers later, if needed..</span></span>



</div>

<span data-ttu-id="f09ef-150">На следующем рисунке показаны все обязательные и необязательные компоненты топологии для одного сервера переднего плана сервера сохраняемого чата с соблюдением соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="f09ef-150">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="f09ef-151">**Единственный сервер сохраняемого чата**</span><span class="sxs-lookup"><span data-stu-id="f09ef-151">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="f09ef-152">![Топология с одним сервером со службой соответствия требованиям](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Топология с одним сервером со службой соответствия требованиям")</span><span class="sxs-lookup"><span data-stu-id="f09ef-152">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="f09ef-153">Топология с несколькими серверами</span><span class="sxs-lookup"><span data-stu-id="f09ef-153">Multiple-Server Topology</span></span>

<span data-ttu-id="f09ef-154">Чтобы повысить производительность и надежность, можно развернуть топологию с несколькими серверами, как описано в статье [Планирование сервера сохраняемого чата в Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="f09ef-154">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="f09ef-155">Многосерверная топология может включать до четырех активных компьютеров, на которых работает сервер сохраняемого чата (для конфигураций с высокой доступностью и аварийным восстановлением можно указать до восьми, но только четыре из них могут быть активными и оставшиеся четыре в ждущем режиме).</span><span class="sxs-lookup"><span data-stu-id="f09ef-155">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="f09ef-156">Каждый сервер может поддерживать до 20 000 одновременно работающих пользователей, общее 80 000 количество одновременных пользователей, подключенных к пулу серверов сохраняемого чата с 4 серверами.</span><span class="sxs-lookup"><span data-stu-id="f09ef-156">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="f09ef-157">Многосерверная топология такая же, как топология с одним сервером, за исключением того, что несколько серверов размещаются в сервере сохраняемого чата и могут масштабироваться на более высоком уровне.</span><span class="sxs-lookup"><span data-stu-id="f09ef-157">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="f09ef-158">Несколько компьютеров, на которых работает сервер сохраняемого чата, должны находиться в том же домене доменных служб Active Directory, что и Lync Server и служба соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="f09ef-158">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="f09ef-159">На следующем рисунке показаны все компоненты топологии с несколькими серверами с несколькими компьютерами, на которых работает сервер сохраняемого чата, дополнительная служба соответствия требованиям и отдельная база данных соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="f09ef-159">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="f09ef-160">**Несколько серверов сохраняемого чата**</span><span class="sxs-lookup"><span data-stu-id="f09ef-160">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="f09ef-161">![Топология с несколькими серверами](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Топология с несколькими серверами")</span><span class="sxs-lookup"><span data-stu-id="f09ef-161">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="f09ef-162">Топологии с несколькими серверами обеспечивают объединение функциональности серверов в пулы.</span><span class="sxs-lookup"><span data-stu-id="f09ef-162">Multiple-server topologies provide pooling of server functionality.</span></span> <span data-ttu-id="f09ef-163">В пуле серверов службы сохраняемого чата обмениваются данными и совместно используют их.</span><span class="sxs-lookup"><span data-stu-id="f09ef-163">In a server pool, the Persistent Chat services communicate and share data.</span></span> <span data-ttu-id="f09ef-164">Например, журнал чата, изначально Отправленный в одну службу сохраняемого чата, доступен из любой службы сохраняемого чата в системе.</span><span class="sxs-lookup"><span data-stu-id="f09ef-164">For example, chat history that was originally posted to one Persistent Chat service is available from any Persistent Chat service in the system.</span></span> <span data-ttu-id="f09ef-165">Доступ к файлу, отправляемому через одну службу сохраняемого чата, может осуществлять любой служба сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="f09ef-165">A file that is uploaded through one Persistent Chat service can be accessed by any Persistent Chat service.</span></span> <span data-ttu-id="f09ef-166">Пользователи могут подключаться к различным интерфейсным серверам сервера сохраняемого чата, а также могут общаться друг с другом.</span><span class="sxs-lookup"><span data-stu-id="f09ef-166">Users can be connected to different Persistent Chat Server Front End Servers and can be chatting and communicating with each other.</span></span>

<span data-ttu-id="f09ef-167">Порт по умолчанию TCP 8011 подключается к серверу в пул серверов и используется службой сохраняемого чата для взаимодействия между собой или для административных целей.</span><span class="sxs-lookup"><span data-stu-id="f09ef-167">The default port of TCP 8011 connects a server to a server pool, and is used by the Persistent Chat service to communicate between themselves, or for administrative purposes.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

