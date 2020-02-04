---
title: 'Lync Server 2013: компоненты и топологии для архивации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Archiving
ms:assetid: 5893063d-a44a-4034-aba9-cbe883ecf710
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204916(v=OCS.15)
ms:contentKeyID: 48184213
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3ccb77d8d2d0b7bd7d4d564087a69b7605863fe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="49173-102">Компоненты и топологии для архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49173-102">Components and topologies for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49173-103">_**Тема последнего изменения:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="49173-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="49173-104">Если вы хотите архивировать содержимое для обмена сообщениями в Lync Server 2013 и конференц-связи, вы можете использовать архивацию в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="49173-104">If you want to archive Lync Server 2013 IM and conferencing content, you can implement Archiving in Lync Server.</span></span>

<div>

## <a name="archiving-components"></a><span data-ttu-id="49173-105">Архивирование компонентов</span><span class="sxs-lookup"><span data-stu-id="49173-105">Archiving Components</span></span>

<span data-ttu-id="49173-106">Функция архивации включает следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="49173-106">The Archiving feature includes the following components:</span></span>

  - <span data-ttu-id="49173-107">**Агенты архивации**.</span><span class="sxs-lookup"><span data-stu-id="49173-107">**Archiving agents**.</span></span> <span data-ttu-id="49173-108">Агенты архивации (также называемые агентами Объединенных сборов данных) устанавливаются и активируются автоматически на всех интерфейсах пула и сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="49173-108">Archiving agents (also known as unified data collection agents) are installed and activated automatically on every Front End pool and Standard Edition server.</span></span> <span data-ttu-id="49173-109">Несмотря на то что агенты архивации активируются автоматически, никакие сообщения не фиксируются, пока не будет включена Архивация и не будут правильно настроены.</span><span class="sxs-lookup"><span data-stu-id="49173-109">Although archiving agents are activated automatically, no messages are actually captured until Archiving is enabled and appropriately configured.</span></span>

  - <span data-ttu-id="49173-110">**Хранилище данных архивации**.</span><span class="sxs-lookup"><span data-stu-id="49173-110">**Archiving data storage**.</span></span> <span data-ttu-id="49173-111">Хранилище данных для Lync Server 2013 может принимать одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="49173-111">Data storage for Lync Server 2013 can be either of the following:</span></span>
    
      - <span data-ttu-id="49173-112">Хранилище Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="49173-112">Exchange 2013 storage.</span></span> <span data-ttu-id="49173-113">Если вы включите параметр интеграция Microsoft Exchange, почтовые ящики пользователей, расположенные на сервере Exchange 2013, используют хранилище Exchange 2013 для архивированных данных, но только если почтовые ящики размещены на месте.</span><span class="sxs-lookup"><span data-stu-id="49173-113">If you enable the Microsoft Exchange integration option, user mailboxes homed on the Exchange 2013 server use Exchange 2013 storage for archived data, but only if the mailboxes have been put on In-Place Hold.</span></span>
    
      - <span data-ttu-id="49173-114">Хранилище SQL Server.</span><span class="sxs-lookup"><span data-stu-id="49173-114">SQL Server storage.</span></span> <span data-ttu-id="49173-115">Если у вас есть пользователи в развертывании, размещенные на Lync Server 2013, вы можете настроить базы данных архивации, которые работают с поддерживаемой версией SQL Server, чтобы включить архивацию для этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="49173-115">If you have users in your deployment who are homed on Lync Server 2013, you can set up Archiving databases that run a supported version of SQL Server to enable archiving for those users.</span></span>

<span data-ttu-id="49173-116">Для архивации также требуется хранилище файлов, но для архивации используется то же хранилище файлов, что и сервер переднего плана или стандартный выпуск.</span><span class="sxs-lookup"><span data-stu-id="49173-116">Archiving also requires file storage, but Archiving uses the same file storage as the Front End Servers or Standard Edition server.</span></span>

<span data-ttu-id="49173-117">Список требований к оборудованию и программному обеспечению для архивации: [поддерживаемое оборудование для Lync server 2013](lync-server-2013-supported-hardware.md) и [серверного программного обеспечения и поддержки инфраструктуры в Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="49173-117">For a list of hardware and software requirements for Archiving, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="49173-118">Поддерживаемые топологии</span><span class="sxs-lookup"><span data-stu-id="49173-118">Supported Topologies</span></span>

<span data-ttu-id="49173-119">Архивация развертывается в каждом пуле, где есть пользователи, которым требуется поддержка архивирования.</span><span class="sxs-lookup"><span data-stu-id="49173-119">You deploy Archiving in each pool that has users that require archiving support.</span></span> <span data-ttu-id="49173-120">Архивация выполняется на серверах переднего плана в пулах Enterprise Edition и на серверах Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="49173-120">Archiving runs on Front End Servers in Enterprise Edition pools and on Standard Edition servers.</span></span> <span data-ttu-id="49173-121">Архивирование хранилища данных может быть следующим:</span><span class="sxs-lookup"><span data-stu-id="49173-121">Archiving data storage can be the following:</span></span>

  - <span data-ttu-id="49173-122">Интеграция с хранилищем Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="49173-122">Integrated with Exchange 2013 storage</span></span>

  - <span data-ttu-id="49173-123">Развернуто с использованием отдельных баз данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="49173-123">Deployed using separate SQL Server databases</span></span>

<span data-ttu-id="49173-124">Если в развертывании Exchange 2013 не включены все пользователи в развертывание Lync Server, необходимо использовать Microsoft Exchange Integration для пользователей, чьи почтовые ящики находятся дома на серверах Exchange 2013, и вы должны развертывать отдельные базы данных SQL Server для всех остальных. Пользователи Lync, которые используются для архивации.</span><span class="sxs-lookup"><span data-stu-id="49173-124">If your Exchange 2013 deployment does not include all users in your Lync Server deployment, you must use Microsoft Exchange integration for the users whose mailboxes are home on Exchange 2013 servers, and you must deploy separate SQL Server databases for all other Lync users to use for archiving.</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="49173-125">Поддерживаемое расвыровнение</span><span class="sxs-lookup"><span data-stu-id="49173-125">Supported Collocation</span></span>

<span data-ttu-id="49173-126">Lync Server 2013 поддерживает разнообразные сценарии, позволяющие экономить аппаратную стоимость за счет запуска нескольких компонентов на одном сервере (если у вас небольшая организация) или для запуска отдельных компонентов на разных серверах (если у вас больше организациям, которым требуется масштабируемость и производительность.</span><span class="sxs-lookup"><span data-stu-id="49173-126">Lync Server 2013 supports a variety of collocation scenarios, allowing you flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="49173-127">Необходимо учитывать коэффициенты масштабируемости, прежде чем решить, следует ли разносить компоненты.</span><span class="sxs-lookup"><span data-stu-id="49173-127">Scalability factors should certainly be considered before you decide whether to collocate components.</span></span>

<span data-ttu-id="49173-128">Архивация разворачивается на серверах переднего плана или стандартных серверах пула.</span><span class="sxs-lookup"><span data-stu-id="49173-128">Archiving is deployed on the Front End Servers of a pool or Standard Edition servers.</span></span> <span data-ttu-id="49173-129">Дополнительные сведения о компонентах, которые можно наследовать там, приведены в разделе [Поддерживаемые параметры расвыровненности сервера в Lync server 2013](lync-server-2013-supported-server-collocation.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="49173-129">For details about components that can be collocated there, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="49173-130">Если вы используете отдельную базу данных SQL Server для архивации, вместо или помимо интеграции хранилища с хранилищем Exchange 2013, вы можете разбить ее на следующие части:</span><span class="sxs-lookup"><span data-stu-id="49173-130">If you use separate SQL Server databases for Archiving, instead of or in addition to integrating storage with Exchange 2013 storage, you can collocate the Archiving database with any of the following:</span></span>

  - <span data-ttu-id="49173-131">База данных мониторинга</span><span class="sxs-lookup"><span data-stu-id="49173-131">Monitoring database</span></span>

  - <span data-ttu-id="49173-132">Внутренняя база данных пула переднего плана Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="49173-132">Back-end database of an Enterprise Edition Front End pool</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="49173-p108">На сервере, на котором размещается база данных архивации, могут размещаться и другие базы данных. Но когда вы рассматриваете возможность совместного размещения базы данных архивации с другими базами данных, следует помнить, что при архивации сообщений большого количества пользователей для базы данных архивации может потребоваться очень большой объем дискового пространства. По этой причине не рекомендуется размещать базу данных архивации совместно с внутренней базой данных.</span><span class="sxs-lookup"><span data-stu-id="49173-p108">The server hosting the Archiving database can host other databases. However, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large. For this reason, we do not recommend collocating the Archiving database with the back-end database.</span></span>



</div>

<span data-ttu-id="49173-136">Если вы разместите базу данных архивации с помощью базы данных мониторинга, серверной базы данных или обеих баз данных, вы можете использовать один экземпляр SQL для любой базы данных или для каждой из них, выполнив указанные ниже действия. ограничение</span><span class="sxs-lookup"><span data-stu-id="49173-136">If you collocate the Archiving database with the Monitoring database, back-end database, or both of these databases, you can either use a single SQL instance for any or all of the databases, or you can use a separate SQL instance for each database, with the following limitation:</span></span>

  - <span data-ttu-id="49173-137">Каждый экземпляр SQL может содержать только одну серверную базу данных, единую базу данных мониторинга и единую базу данных для архивации.</span><span class="sxs-lookup"><span data-stu-id="49173-137">Each SQL instance can contain only a single back-end database, single Monitoring database, and single Archiving database.</span></span>

<span data-ttu-id="49173-138">Подробнее о совместном использовании серверных ролей и баз данных можно узнать [в разделе Поддерживаемые параметры расвыровнений сервера в Lync server 2013](lync-server-2013-supported-server-collocation.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="49173-138">For details about collocation of all server roles and databases, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

