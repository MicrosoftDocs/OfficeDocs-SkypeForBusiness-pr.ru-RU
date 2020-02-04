---
title: 'Lync Server 2013: компоненты и топологии для постоянного сервера чата'
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
ms.openlocfilehash: 862635d091a216df61058c0f0ff00eaa9d32a0c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="3e40e-102">Компоненты и топологии для постоянного сервера чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e40e-102">Components and topologies for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e40e-103">_**Тема последнего изменения:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="3e40e-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="3e40e-104">Сервер сохраняемого чата поддерживает конфигурации с одним сервером и конфигурации с несколькими серверами.</span><span class="sxs-lookup"><span data-stu-id="3e40e-104">Persistent Chat Server supports both single-server configurations and multiple-server configurations.</span></span> <span data-ttu-id="3e40e-105">Сервер в Lync Server 2013 Standard Edition также может работать на сервере с постоянным чат.</span><span class="sxs-lookup"><span data-stu-id="3e40e-105">Persistent Chat Server can also run on a Lync Server 2013 Standard Edition server.</span></span> <span data-ttu-id="3e40e-106">Эти конфигурации включают следующие компоненты и топологии серверного чата.</span><span class="sxs-lookup"><span data-stu-id="3e40e-106">These configurations consist of the following Persistent Chat Server components and topologies.</span></span>

<div>

## <a name="persistent-chat-server-components"></a><span data-ttu-id="3e40e-107">Серверные компоненты для сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="3e40e-107">Persistent Chat Server Components</span></span>

<span data-ttu-id="3e40e-108">Для установки последней версии сервера сохраняемого чата требуются следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="3e40e-108">Installing the latest version of Persistent Chat Server requires the following components:</span></span>

  - <span data-ttu-id="3e40e-109">Один или несколько компьютеров, на которых запущен сохраняемый сервер чата, и предоставлены следующие службы:</span><span class="sxs-lookup"><span data-stu-id="3e40e-109">One or more computers running Persistent Chat Server and providing the following services:</span></span>
    
      - <span data-ttu-id="3e40e-110">Служба сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="3e40e-110">Persistent Chat service</span></span>
    
      - <span data-ttu-id="3e40e-111">Служба соответствия, которая включается, если включено соответствие</span><span class="sxs-lookup"><span data-stu-id="3e40e-111">Compliance service, which is turned on if compliance is enabled</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3e40e-112">В Lync Server 2013 веб-службы сохраняемого чата для отправки и скачивания файлов теперь сопоставлены с интерфейсом сервера&nbsp;Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3e40e-112">In Lync Server 2013, the Persistent Chat Web Services for File Upload/Download is now collocated with Lync Server 2013&nbsp;Front End Server.</span></span><BR><span data-ttu-id="3e40e-113">Веб-службы сохраняемого чата для управления комнатами в чате также размещается с&nbsp;помощью клиентского сервера Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3e40e-113">The Persistent Chat Web Services for Chat Room Management is also collocated with Lync Server 2013&nbsp;Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="3e40e-114">Сервер (-ы) (более одного сервера, если используется зеркальное отражение), на котором размещается база данных SQL Server для размещения сохраняемой базы данных контента, в которой хранятся содержимое, комнаты и категории чата.</span><span class="sxs-lookup"><span data-stu-id="3e40e-114">Server(s) (more than one server if mirroring is used) that host the SQL Server back-end database for hosting the Persistent Chat content database where chat room content, rooms, and categories are stored.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3e40e-115">Серверная база данных хранит данные журнала чата, в том числе сведения о категориях и сохраняемых комнатах чатов.</span><span class="sxs-lookup"><span data-stu-id="3e40e-115">The back-end database stores chat history data, including information about categories and Persistent Chat rooms that are created.</span></span>

    
    </div>

  - <span data-ttu-id="3e40e-116">Если включено соответствие, сервер (-ы) (более одного сервера при использовании зеркального отображения), на котором размещается серверная база данных SQL Server для размещения базы данных соответствия требованиям сохраняемого чата, в которой хранятся события соответствия и содержимое чата для целей соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="3e40e-116">If compliance was enabled, a server(s) (more than one server if mirroring is used) that host the SQL Server back-end database for hosting the Persistent Chat Compliance database, where compliance events and chat content for the purpose of compliance are stored.</span></span>

<span data-ttu-id="3e40e-117">Чтобы администрировать сохраняемый сервер чата с отдельного компьютера (например, из консоли администрирования), используйте панель управления Lync Server на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3e40e-117">To administer Persistent Chat Server from a separate computer (such as an administrative console), use the Lync Server Control Panel on the computer.</span></span> <span data-ttu-id="3e40e-118">После этого этот компьютер должен быть развернут в домен доменных служб Active Directory, но по крайней мере один сервер глобального каталога в корне леса.</span><span class="sxs-lookup"><span data-stu-id="3e40e-118">This computer must then be deployed in an Active Directory Domain Services domain, with at least one global catalog server in the forest root.</span></span>

<span data-ttu-id="3e40e-119">Сведения о требованиях к оборудованию и программному обеспечению для постоянного сервера чата описаны в статьях [технические требования для сохраняемого сервера чата в Lync server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [поддерживаемом оборудовании для Lync Server 2013](lync-server-2013-supported-hardware.md), а также о [поддержке серверного программного обеспечения и инфраструктуры в Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="3e40e-119">For details about hardware and software requirements for Persistent Chat Server, see [Technical requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md), and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="3e40e-120">Поддерживаемое расвыровнение</span><span class="sxs-lookup"><span data-stu-id="3e40e-120">Supported Collocation</span></span>

<span data-ttu-id="3e40e-121">Lync Server 2013 поддерживает различные сценарии использования, обеспечивая гибкие возможности по экономии оборудования путем запуска нескольких компонентов на одном сервере (если у вас небольшая организация) или для запуска отдельных компонентов на разных серверах (если у вас есть крупная организация, требующая масштабируемость и производительность.</span><span class="sxs-lookup"><span data-stu-id="3e40e-121">Lync Server 2013 supports a variety of collocation scenarios, providing you the flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="3e40e-122">Необходимо учитывать коэффициенты масштабируемости, прежде чем решить, следует ли разносить компоненты.</span><span class="sxs-lookup"><span data-stu-id="3e40e-122">Scalability factors should certainly be considered before you decide whether to collocate components.</span></span>

<span data-ttu-id="3e40e-123">Служба соответствия требованиям к постоянному чат, если соответствие требованиям включена, размещается с помощью клиентского сервера Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3e40e-123">The Persistent Chat Compliance service, if compliance is enabled, is collocated with the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="3e40e-124">Сервер сохраняемого чата может быть развернут на сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="3e40e-124">Persistent Chat Server can be deployed on the Standard Edition server.</span></span> <span data-ttu-id="3e40e-125">Сервер "сохраняемый сервер обратного чата" и база данных соответствия требованиям сохраняемого чата могут быть выровнены на сервере Standard Edition на локальном сервере SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="3e40e-125">The Persistent Chat Server Back End Server and the Persistent Chat Compliance database can be collocated on the Standard Edition server on the local SQL Server Express Back End Server.</span></span> <span data-ttu-id="3e40e-126">Дополнительные сведения о компонентах, которые можно наследовать там, приведены в разделе [Поддерживаемые параметры расвыровненности сервера в Lync server 2013](lync-server-2013-supported-server-collocation.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="3e40e-126">For details about components that can be collocated there, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="3e40e-127">Для Lync Server 2013 Enterprise Edition на сервере Enterprise Edition нельзя предоставлять доступ к сохраняемым серверам чата.</span><span class="sxs-lookup"><span data-stu-id="3e40e-127">For Lync Server 2013 Enterprise Edition, Persistent Chat Servers cannot be collocated on the Enterprise Edition server.</span></span> <span data-ttu-id="3e40e-128">База данных SQL Server для сохраняемого сервера чатов может быть размещена вместе с базой данных сервера переднего плана Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="3e40e-128">The SQL Server database for Persistent Chat Server can be collocated with the Back End Server database of an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="3e40e-129">База данных SQL Server для обеспечения соответствия требованиям к сохраняемым Чатам также может доставляться вместе с базой данных сервера пула Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="3e40e-129">The SQL Server database for Persistent Chat compliance can also be collocated with the Back End Server database of an Enterprise Edition pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3e40e-130">Сервер, на котором размещена база данных сохраняемого чата, может размещать другие базы данных.</span><span class="sxs-lookup"><span data-stu-id="3e40e-130">The server hosting the Persistent Chat database can host other databases.</span></span> <span data-ttu-id="3e40e-131">Тем не менее, если вы рассматриваете различную базу данных чата с другими базами данных, имейте в виду, что при хранении сообщений, которые больше чем несколько пользователей, дискового пространства, необходимого для хранения данных, может увеличиваться очень большим.</span><span class="sxs-lookup"><span data-stu-id="3e40e-131">However, when you consider collocating the Persistent Chat database with other databases, be aware that if you are storing the messages of more than a few users, the disk space needed by the Persistent Chat database can grow very large.</span></span> <span data-ttu-id="3e40e-132">По этой причине мы не рекомендуем выписывать базу данных "сохраняемый чат" для серверной базы данных.</span><span class="sxs-lookup"><span data-stu-id="3e40e-132">For this reason, we do not recommend collocating the Persistent Chat database with the back-end database.</span></span>



</div>

<span data-ttu-id="3e40e-133">Если вы выделены друг от друга базой данных с серверной базой данных, то можете либо использовать один экземпляр SQL Server для любой базы данных, либо использовать отдельный экземпляр SQL Server для каждой из них, выполнив указанные ниже ограничения.</span><span class="sxs-lookup"><span data-stu-id="3e40e-133">If you collocate the Persistent Chat database with the back-end database, you can either use a single instance of SQL Server for any or all of the databases, or you can use a separate instance of SQL Server for each database, with the following limitation:</span></span>

  - <span data-ttu-id="3e40e-134">Каждый экземпляр SQL Server может содержать только одну серверную базу данных и одну базу данных сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="3e40e-134">Each instance of SQL Server can contain only a single back-end database and a single Persistent Chat database.</span></span>

<span data-ttu-id="3e40e-135">Подробнее о совместном использовании серверных ролей и баз данных можно узнать [в разделе Поддерживаемые параметры расвыровнений сервера в Lync server 2013](lync-server-2013-supported-server-collocation.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="3e40e-135">For details about collocation of all server roles and databases, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="persistent-chat-server-topologies"></a><span data-ttu-id="3e40e-136">Топологии серверов сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="3e40e-136">Persistent Chat Server Topologies</span></span>

<span data-ttu-id="3e40e-137">Сервер сохраняемого чата поддерживает следующие топологии:</span><span class="sxs-lookup"><span data-stu-id="3e40e-137">Persistent Chat Server supports the following topologies:</span></span>

  - <span data-ttu-id="3e40e-138">Внешний сервер для Lync Server 2013 Enterprise Edition на едином сервере, который является сервером единого чата</span><span class="sxs-lookup"><span data-stu-id="3e40e-138">Lync Server 2013 Enterprise Edition single server Persistent Chat Server Front End Server</span></span>

  - <span data-ttu-id="3e40e-139">Lync Server 2013 Enterprise Edition с несколькими серверными серверами серверного чата</span><span class="sxs-lookup"><span data-stu-id="3e40e-139">Lync Server 2013 Enterprise Edition multiple server Persistent Chat Server Front End Server</span></span>

  - <span data-ttu-id="3e40e-140">Сервер Lync Server 2013 Standard Edition, использующий SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="3e40e-140">Lync Server 2013 Standard Edition server using SQL Server Express</span></span>

  - <span data-ttu-id="3e40e-141">Сервер Lync Server 2013 Standard Edition Server и сохраняемый сервер чатов на отдельном сервере, использующем стандарт Server Standard Edition, в качестве сервера следующего прыжка.</span><span class="sxs-lookup"><span data-stu-id="3e40e-141">Lync Server 2013 Standard Edition server and Persistent Chat Server on a separate server using Standard Edition server as the next hop server.</span></span>

<span data-ttu-id="3e40e-142">Вы можете добавить сохраняемый сервер чата в развертывание Lync Server 2013 с помощью построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="3e40e-142">You can add Persistent Chat Server to your Lync Server 2013 deployment by using Topology Builder.</span></span> <span data-ttu-id="3e40e-143">Вы можете добавить в топологию один сервер или пул серверного постоянного чата для нескольких серверов.</span><span class="sxs-lookup"><span data-stu-id="3e40e-143">You can add a single server or a multiple server Persistent Chat Server pool to your topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3e40e-144">После того как вы создадите пул серверов для постоянного чата с одним сервером с помощью построителя топологии, вы не сможете добавить дополнительные серверы в пул.</span><span class="sxs-lookup"><span data-stu-id="3e40e-144">After you create a Persistent Chat Server pool with a single server by using Topology Builder, you cannot add additional servers to the pool.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="3e40e-145">Топология с одним сервером</span><span class="sxs-lookup"><span data-stu-id="3e40e-145">Single-Server Topology</span></span>

<span data-ttu-id="3e40e-146">Минимальной конфигурацией и простейшим развертыванием сервера сохраняемого чата является единая топология серверного сервера чата.</span><span class="sxs-lookup"><span data-stu-id="3e40e-146">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="3e40e-147">Для этого развертывания требуется один сервер, на котором запускается сохраняемый сервер чата (при условии, что при этом запускается служба соответствия, если она включена), сервер, на котором размещается база данных SQL Server, и, если требуется соответствие, база данных SQL Server для хранения данные о соответствии требованиям.</span><span class="sxs-lookup"><span data-stu-id="3e40e-147">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3e40e-148">Вы не можете добавлять дополнительные серверы в пул сервера сохраняемого чата, который запускается как развертывание на едином сервере в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="3e40e-148">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="3e40e-149">Мы рекомендуем использовать топологию пула с несколькими серверами, даже если вы используете один сервер, и при необходимости можете добавить дополнительные серверы.</span><span class="sxs-lookup"><span data-stu-id="3e40e-149">We recommend using the multiple-server pool topology, even if you’re using a single server, so that you can add more servers later, if needed..</span></span>



</div>

<span data-ttu-id="3e40e-150">На приведенном ниже рисунке показаны все обязательные и необязательные компоненты топологии для одного серверного переднего плана, в соответствии с требованиями.</span><span class="sxs-lookup"><span data-stu-id="3e40e-150">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="3e40e-151">**Одиночный сохраняемый сервер чата**</span><span class="sxs-lookup"><span data-stu-id="3e40e-151">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="3e40e-152">![Топология с одним сервером с помощью службы соответствия требованиям](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Топология с одним сервером с помощью службы соответствия требованиям")</span><span class="sxs-lookup"><span data-stu-id="3e40e-152">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="3e40e-153">Топология с несколькими серверами</span><span class="sxs-lookup"><span data-stu-id="3e40e-153">Multiple-Server Topology</span></span>

<span data-ttu-id="3e40e-154">Чтобы обеспечить повышенную емкость и надежность, вы можете развернуть топологию с несколькими серверами, как описано в разделе [планирование сохраняемого сервера чата в Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="3e40e-154">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="3e40e-155">Многосерверная топология может включать в себя до четырех активных компьютеров, использующих сохраняемый сервер чатов (для конфигураций с высокой доступностью и аварийного восстановления допускается до восьми, но только четыре из них могут быть активными, а оставшиеся четыре — в режиме ожидания).</span><span class="sxs-lookup"><span data-stu-id="3e40e-155">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="3e40e-156">Каждый сервер может поддерживать столько же пользователей, сколько и 20 000, а общее 80 000 количество одновременных пользователей, которые подключены к постоянному пулу серверов чатов с 4 серверами.</span><span class="sxs-lookup"><span data-stu-id="3e40e-156">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="3e40e-157">Многосерверная топология такая же, как топология с одним сервером, за исключением случаев, когда сервер размещается на нескольких серверах и может масштабироваться на более высоком уровне.</span><span class="sxs-lookup"><span data-stu-id="3e40e-157">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="3e40e-158">Несколько компьютеров, использующих сохраняемый сервер чата, должны находиться в том же домене доменных служб Active Directory, что и Lync Server, и служба соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="3e40e-158">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="3e40e-159">На приведенном ниже рисунке показаны все компоненты топологии с несколькими серверами с несколькими компьютерами, на которых запущены сохраняемый сервер чата, необязательная служба соответствия требованиям и отдельная база данных соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="3e40e-159">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="3e40e-160">**Несколько серверов для сохраняемого чата**</span><span class="sxs-lookup"><span data-stu-id="3e40e-160">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="3e40e-161">![Топология с несколькими серверами](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Топология с несколькими серверами")</span><span class="sxs-lookup"><span data-stu-id="3e40e-161">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="3e40e-162">Multiple-server topologies provide pooling of server functionality.</span><span class="sxs-lookup"><span data-stu-id="3e40e-162">Multiple-server topologies provide pooling of server functionality.</span></span> <span data-ttu-id="3e40e-163">В пуле серверов в службах сохраняемого чата осуществляется обмен данными и предоставление общего доступа к ним.</span><span class="sxs-lookup"><span data-stu-id="3e40e-163">In a server pool, the Persistent Chat services communicate and share data.</span></span> <span data-ttu-id="3e40e-164">Например, история чата, которая была изначально опубликована в одной службе сохраняемого чата, доступна из любой службы сохраняемого чата в системе.</span><span class="sxs-lookup"><span data-stu-id="3e40e-164">For example, chat history that was originally posted to one Persistent Chat service is available from any Persistent Chat service in the system.</span></span> <span data-ttu-id="3e40e-165">Файл, который передается через одну службу сохраняемого чата, может быть доступен любой из служб сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="3e40e-165">A file that is uploaded through one Persistent Chat service can be accessed by any Persistent Chat service.</span></span> <span data-ttu-id="3e40e-166">Пользователи могут подключаться к различным серверам переднего плана, а также общаться друг с другом.</span><span class="sxs-lookup"><span data-stu-id="3e40e-166">Users can be connected to different Persistent Chat Server Front End Servers and can be chatting and communicating with each other.</span></span>

<span data-ttu-id="3e40e-167">Порт по умолчанию TCP 8011 подключает сервер к группе серверов и используется службой сохраняемого чата для связи между собой и для целей администрирования.</span><span class="sxs-lookup"><span data-stu-id="3e40e-167">The default port of TCP 8011 connects a server to a server pool, and is used by the Persistent Chat service to communicate between themselves, or for administrative purposes.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

