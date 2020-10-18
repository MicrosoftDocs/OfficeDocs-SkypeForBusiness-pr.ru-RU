---
title: 'Lync Server 2013: компоненты и топологии для архивации'
description: 'Lync Server 2013: компоненты и топологии для архивации.'
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
ms.openlocfilehash: f6ccb62993dc6a8dbc098d4a9c5f28b9b3f7fac9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576925"
---
# <a name="components-and-topologies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="6c970-103">Компоненты и топологии для архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c970-103">Components and topologies for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c970-104">_**Последнее изменение темы:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="6c970-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="6c970-105">Если вы хотите архивировать контент Lync Server 2013 для обмена мгновенными сообщениями и конференц-связи, вы можете реализовать архивацию в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6c970-105">If you want to archive Lync Server 2013 IM and conferencing content, you can implement Archiving in Lync Server.</span></span>

<div>

## <a name="archiving-components"></a><span data-ttu-id="6c970-106">Компоненты функции архивации</span><span class="sxs-lookup"><span data-stu-id="6c970-106">Archiving Components</span></span>

<span data-ttu-id="6c970-107">Функция архивации включает следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="6c970-107">The Archiving feature includes the following components:</span></span>

  - <span data-ttu-id="6c970-p101">**Агенты архивации**. Агенты архивации (также известные как агенты сбора унифицированных данных) устанавливаются и активируются автоматически в каждом пуле переднего плана и на сервере Standard Edition. Хотя агенты архивации активируются автоматически, в действительность сбор сообщений не осуществляется, пока вы не активируете и не настроите функцию архивации должным образом.</span><span class="sxs-lookup"><span data-stu-id="6c970-p101">**Archiving agents**. Archiving agents (also known as unified data collection agents) are installed and activated automatically on every Front End pool and Standard Edition server. Although archiving agents are activated automatically, no messages are actually captured until Archiving is enabled and appropriately configured.</span></span>

  - <span data-ttu-id="6c970-111">**Хранилище данных архивации**.</span><span class="sxs-lookup"><span data-stu-id="6c970-111">**Archiving data storage**.</span></span> <span data-ttu-id="6c970-112">Хранилище данных для Lync Server 2013 может быть одним из следующих:</span><span class="sxs-lookup"><span data-stu-id="6c970-112">Data storage for Lync Server 2013 can be either of the following:</span></span>
    
      - <span data-ttu-id="6c970-113">Хранилище Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="6c970-113">Exchange 2013 storage.</span></span> <span data-ttu-id="6c970-114">Если включен параметр интеграции с Microsoft Exchange, почтовые ящики пользователей, размещенные на сервере Exchange 2013, используют хранилище Exchange 2013 для архивированных данных, но только если почтовые ящики размещены на In-Place удержании.</span><span class="sxs-lookup"><span data-stu-id="6c970-114">If you enable the Microsoft Exchange integration option, user mailboxes homed on the Exchange 2013 server use Exchange 2013 storage for archived data, but only if the mailboxes have been put on In-Place Hold.</span></span>
    
      - <span data-ttu-id="6c970-115">Хранилище SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6c970-115">SQL Server storage.</span></span> <span data-ttu-id="6c970-116">Если у вас есть пользователи в развертывании, размещенные на Lync Server 2013, вы можете настроить базы данных архивации, на которых выполняется поддерживаемая версия SQL Server, чтобы включить архивацию для этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="6c970-116">If you have users in your deployment who are homed on Lync Server 2013, you can set up Archiving databases that run a supported version of SQL Server to enable archiving for those users.</span></span>

<span data-ttu-id="6c970-117">Для функции архивации также требуется хранилище файлов, но функция архивации использует то же самое хранилище файлов, что и сервер переднего плана или сервер Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="6c970-117">Archiving also requires file storage, but Archiving uses the same file storage as the Front End Servers or Standard Edition server.</span></span>

<span data-ttu-id="6c970-118">Список требований к оборудованию и программному обеспечению для архивации приведен в статье Supported [Hardware for Lync server 2013](lync-server-2013-supported-hardware.md) and [Server Software and Infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="6c970-118">For a list of hardware and software requirements for Archiving, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="6c970-119">Поддерживаемые топологии</span><span class="sxs-lookup"><span data-stu-id="6c970-119">Supported Topologies</span></span>

<span data-ttu-id="6c970-120">Архивация разворачивается в каждом пуле, где есть пользователи, которым требуется поддержка архивации.</span><span class="sxs-lookup"><span data-stu-id="6c970-120">You deploy Archiving in each pool that has users that require archiving support.</span></span> <span data-ttu-id="6c970-121">Архивация выполняется на серверах переднего плана в пулах Enterprise Edition и на серверах Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="6c970-121">Archiving runs on Front End Servers in Enterprise Edition pools and on Standard Edition servers.</span></span> <span data-ttu-id="6c970-122">Хранение данных архивации может быть следующим:</span><span class="sxs-lookup"><span data-stu-id="6c970-122">Archiving data storage can be the following:</span></span>

  - <span data-ttu-id="6c970-123">Интеграция с хранилищем Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="6c970-123">Integrated with Exchange 2013 storage</span></span>

  - <span data-ttu-id="6c970-124">Развернуто с использованием отдельных баз данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="6c970-124">Deployed using separate SQL Server databases</span></span>

<span data-ttu-id="6c970-125">Если в развертывании Exchange 2013 не включены все пользователи в развертывании Lync Server, необходимо использовать интеграцию Microsoft Exchange для пользователей, чьи почтовые ящики находятся дома на серверах Exchange 2013, и необходимо развернуть отдельные базы данных SQL Server для всех остальных пользователей Lync, которые будут использоваться для архивации.</span><span class="sxs-lookup"><span data-stu-id="6c970-125">If your Exchange 2013 deployment does not include all users in your Lync Server deployment, you must use Microsoft Exchange integration for the users whose mailboxes are home on Exchange 2013 servers, and you must deploy separate SQL Server databases for all other Lync users to use for archiving.</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="6c970-126">Поддерживаемые режимы совместного размещения</span><span class="sxs-lookup"><span data-stu-id="6c970-126">Supported Collocation</span></span>

<span data-ttu-id="6c970-127">Lync Server 2013 поддерживает различные сценарии совместного использования, позволяя гибко сэкономить затраты на оборудование, выполняя несколько компонентов на одном сервере (при наличии небольшой организации) или для запуска отдельных компонентов на разных серверах (при наличии более крупной организации, требующей масштабируемость и производительность).</span><span class="sxs-lookup"><span data-stu-id="6c970-127">Lync Server 2013 supports a variety of collocation scenarios, allowing you flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="6c970-128">Факторы масштабируемости, безусловно, следует учитывать при принятии решения о размещении компонентов.</span><span class="sxs-lookup"><span data-stu-id="6c970-128">Scalability factors should certainly be considered before you decide whether to collocate components.</span></span>

<span data-ttu-id="6c970-129">Архивация разворачивается на серверах переднего плана или серверах Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="6c970-129">Archiving is deployed on the Front End Servers of a pool or Standard Edition servers.</span></span> <span data-ttu-id="6c970-130">Для получения дополнительных сведений о компонентах, которые можно разместить в этой статье, ознакомьтесь со страницей поддержка [выровненных серверов в Lync server 2013](lync-server-2013-supported-server-collocation.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="6c970-130">For details about components that can be collocated there, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="6c970-131">Если вы используете отдельные базы данных SQL Server для архивации, а не или в дополнение к интеграции хранилища с хранилищем Exchange 2013, вы можете разместить базу данных архивации с одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="6c970-131">If you use separate SQL Server databases for Archiving, instead of or in addition to integrating storage with Exchange 2013 storage, you can collocate the Archiving database with any of the following:</span></span>

  - <span data-ttu-id="6c970-132">База данных мониторинга</span><span class="sxs-lookup"><span data-stu-id="6c970-132">Monitoring database</span></span>

  - <span data-ttu-id="6c970-133">Серверная база данных пула переднего плана Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="6c970-133">Back-end database of an Enterprise Edition Front End pool</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6c970-p108">На сервере, на котором размещается база данных архивации, могут размещаться и другие базы данных. Однако, когда вы рассматриваете возможность выровненного размещения базы данных архивации совместно с другими базами данных, следует помнить, что при архивации сообщений большого количества пользователей для базы данных архивации может потребоваться очень большой объем дискового пространства. По этой причине не рекомендуется размещать базу данных архивации совместно с серверной базой данных.</span><span class="sxs-lookup"><span data-stu-id="6c970-p108">The server hosting the Archiving database can host other databases. However, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large. For this reason, we do not recommend collocating the Archiving database with the back-end database.</span></span>



</div>

<span data-ttu-id="6c970-137">При выровненном размещении базы данных архивации совместно с базой данных мониторинга, серверной базой данных или обеими этими базами данных можно также использовать один экземпляр SQL для любой из этих баз данных (или для всех баз данных) либо отдельный экземпляр SQL для каждой базы данных. При этом следует учитывать следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="6c970-137">If you collocate the Archiving database with the Monitoring database, back-end database, or both of these databases, you can either use a single SQL instance for any or all of the databases, or you can use a separate SQL instance for each database, with the following limitation:</span></span>

  - <span data-ttu-id="6c970-138">Каждый экземпляр SQL может содержать только одну серверную базу данных, одну базу данных мониторинга и одну базу данных архивации.</span><span class="sxs-lookup"><span data-stu-id="6c970-138">Each SQL instance can contain only a single back-end database, single Monitoring database, and single Archiving database.</span></span>

<span data-ttu-id="6c970-139">Сведения о совместном размещении всех ролей серверов и баз данных можно найти в статье поддержка [выровненных серверов в Lync server 2013](lync-server-2013-supported-server-collocation.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="6c970-139">For details about collocation of all server roles and databases, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

