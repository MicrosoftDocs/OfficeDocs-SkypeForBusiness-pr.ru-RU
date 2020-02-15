---
title: Совместное размещение серверов Lync Server 2013 в развертывании сервера Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server collocation in a Standard Edition server deployment
ms:assetid: 0763ffab-4fd6-463a-8e62-d97876b376d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398131(v=OCS.15)
ms:contentKeyID: 48183314
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 428f666ade00d2f809f25cb7eb9ef1525d7f835c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048680"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-a-standard-edition-server-deployment-for-lync-server-2013"></a><span data-ttu-id="f597f-102">Выровненное размещение серверов в развертывании сервера Standard Edition для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f597f-102">Server collocation in a Standard Edition server deployment for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f597f-103">_**Последнее изменение темы:** 2013-01-20_</span><span class="sxs-lookup"><span data-stu-id="f597f-103">_**Topic Last Modified:** 2013-01-20_</span></span>

<span data-ttu-id="f597f-104">В этом разделе описываются роли сервера, базы данных и файловые ресурсы, которые можно совместно разместить в развертывании сервера Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f597f-104">This section describes the server roles, databases, and file shares that you can collocate in a Lync Server 2013 Standard Edition server deployment.</span></span>

<div>

## <a name="server-roles"></a><span data-ttu-id="f597f-105">Роли серверов</span><span class="sxs-lookup"><span data-stu-id="f597f-105">Server Roles</span></span>

<span data-ttu-id="f597f-106">В Lync Server 2013, служба аудио-и видеоконференций, служба-посредник, мониторинг и архивация размещаются на сервере Standard Edition, но для их включения требуется дополнительная настройка.</span><span class="sxs-lookup"><span data-stu-id="f597f-106">In Lync Server 2013, A/V Conferencing service, Mediation service, Monitoring, and Archiving are collocated on the Standard Edition Server, but additional configuration is required to enable them.</span></span> <span data-ttu-id="f597f-107">Вы можете развернуть службу-посредник на разных серверах.</span><span class="sxs-lookup"><span data-stu-id="f597f-107">You can choose to deploy Mediation service on separate servers.</span></span>

<span data-ttu-id="f597f-108">Можно совместно разместить доверенный сервер приложений с сервером Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f597f-108">You can collocate a trusted application server with a Standard Edition server.</span></span>

<span data-ttu-id="f597f-109">Следующие роли сервера должны быть развернуты на отдельном компьютере:</span><span class="sxs-lookup"><span data-stu-id="f597f-109">The following server roles must each be deployed on a separate computer:</span></span>

  - <span data-ttu-id="f597f-110">Режиссер</span><span class="sxs-lookup"><span data-stu-id="f597f-110">Director</span></span>

  - <span data-ttu-id="f597f-111">пограничный сервер;</span><span class="sxs-lookup"><span data-stu-id="f597f-111">Edge Server</span></span>

  - <span data-ttu-id="f597f-112">Сервер-посредник (при условии, что он не размещен на сервере Standard Edition)</span><span class="sxs-lookup"><span data-stu-id="f597f-112">Mediation Server (if not collocated with the Standard Edition server)</span></span>

  - <span data-ttu-id="f597f-113">Сервер Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="f597f-113">Office Web Apps Server</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="f597f-114">Databases</span><span class="sxs-lookup"><span data-stu-id="f597f-114">Databases</span></span>

<span data-ttu-id="f597f-115">По умолчанию фоновая база данных SQL Server Express размещена на сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f597f-115">By default, the SQL Server Express back-end database is collocated on the Standard Edition server.</span></span> <span data-ttu-id="f597f-116">Вы не можете переместить его на отдельный компьютер.</span><span class="sxs-lookup"><span data-stu-id="f597f-116">You cannot move it to a separate computer.</span></span> <span data-ttu-id="f597f-117">С одним исключением нельзя совместно размещать другие базы данных на сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f597f-117">With one exception, you cannot collocate other databases on the Standard Edition server.</span></span> <span data-ttu-id="f597f-118">Если вы решили развернуть сервер сохраняемого чата на сервере Standard Edition, вы можете разместить базу данных сохраняемого чата и базу данных соответствия сохраняемого чата на том же сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f597f-118">If you choose to deploy Persistent Chat Server on a Standard Edition server, you can collocate the Persistent chat database and the Persistent Chat Compliance database on the same Standard Edition server.</span></span>

<span data-ttu-id="f597f-119">Каждую из следующих баз данных можно разместить на отдельном сервере баз данных:</span><span class="sxs-lookup"><span data-stu-id="f597f-119">You can collocate each of the following databases on a single database server:</span></span>

  - <span data-ttu-id="f597f-120">база данных мониторинга;</span><span class="sxs-lookup"><span data-stu-id="f597f-120">Monitoring database</span></span>

  - <span data-ttu-id="f597f-121">база данных архивации;</span><span class="sxs-lookup"><span data-stu-id="f597f-121">Archiving database</span></span>

  - <span data-ttu-id="f597f-122">Фоновая база данных для пула переднего плана Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="f597f-122">A back-end database for an Enterprise Edition Front End pool</span></span>

<span data-ttu-id="f597f-123">Вы можете разделять любые или все базы данных или все эти базы данных в одном экземпляре SQL или использовать отдельные экземпляры SQL для каждого из них со следующими ограничениями:</span><span class="sxs-lookup"><span data-stu-id="f597f-123">You can collocate any or any or all of these databases in a single SQL instance or use a separate SQL instances for each, with the following limitations:</span></span>

  - <span data-ttu-id="f597f-124">Каждый экземпляр SQL может содержать только одну серверную базу данных (для пула переднего плана Enterprise Edition), одну базу данных мониторинга, одну базу данных архивации, одну базу данных сохраняемого чата, а также одну базу данных соответствия сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="f597f-124">Each SQL instance can contain only a single back-end database (for an Enterprise Edition Front End pool), single Monitoring database, single Archiving database, single persistent chat database, and single persistent chat compliance database.</span></span>

  - <span data-ttu-id="f597f-125">Сервер баз данных не может поддерживать более одного интерфейсного пула Enterprise Edition, одного сервера, на котором выполняется архивация, одного сервера мониторинга, одной базы данных сохраняемого чата и единой базы данных соответствия сохраняемого чата, но она может поддерживать один из них. независимо от того, используют ли базы данных один и тот же экземпляр SQL Server или отдельные экземпляры SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f597f-125">The database server cannot support more than one Enterprise Edition Front End pool, one server running Archiving, one server running Monitoring, single Persistent Chat database, and single Persistent Chat compliance database, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

<span data-ttu-id="f597f-126">Можно расположить файловый ресурс совместно с базами данных, как описано далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="f597f-126">You can collocate a file share with the databases, as described later in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f597f-127">В Lync Server 2013 имеется возможность интеграции мониторинга и архивации хранилища с хранилищем Exchange 2013 для некоторых или всех пользователей в развертывании.</span><span class="sxs-lookup"><span data-stu-id="f597f-127">In Lync Server 2013, you have the option of integrating Monitoring and Archiving storage with Exchange 2013 storage for some or all users in your deployment.</span></span> <span data-ttu-id="f597f-128">Вы не можете развернуть серверы Lync Server или компоненты на тех же серверах, что и хранилище Exchange.</span><span class="sxs-lookup"><span data-stu-id="f597f-128">You cannot deploy any servers running Lync Server or components on the same servers as the Exchange storage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f597f-129">Хотя совместное размещение баз данных поддерживается, размер баз данных может быстро увеличиваться.</span><span class="sxs-lookup"><span data-stu-id="f597f-129">Although collocation of databases is supported, the size of the databases can grow quickly.</span></span> <span data-ttu-id="f597f-130">Например, при совместном размещении базы данных архивации с другими базами данных, следует помнить, что при архивации сообщений большого числа пользователей, размер дискового пространства, необходимый для базы данных архивации, может стать очень большим.</span><span class="sxs-lookup"><span data-stu-id="f597f-130">For example, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="f597f-131">По этой причине мы не рекомендуем размещать несколько баз данных, особенно базы данных архивации, сохраняемого чата и базы данных соответствия сохраняемого чата с внутренней базой данных корпоративного пула.</span><span class="sxs-lookup"><span data-stu-id="f597f-131">For this reason, we do not recommend collocating multiple databases, especially the Archiving database, Persistent Chat database, and Persistent Chat compliance database with the back-end database of an Enterprise pool.</span></span>



</div>

</div>

<div>

## <a name="file-shares"></a><span data-ttu-id="f597f-132">Общие файловые ресурсы</span><span class="sxs-lookup"><span data-stu-id="f597f-132">File Shares</span></span>

<span data-ttu-id="f597f-133">Общий файловый ресурс может быть отдельным сервером или можно размещаться совместно на том же сервере, что следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="f597f-133">The file share can be a separate server or can be collocated on the same server as any or all of the following:</span></span>

  - <span data-ttu-id="f597f-134">сервер баз данных, в том числе фоновый сервер из интерфейсного пула Enterprise Edition;</span><span class="sxs-lookup"><span data-stu-id="f597f-134">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

  - <span data-ttu-id="f597f-135">база данных архивации;</span><span class="sxs-lookup"><span data-stu-id="f597f-135">Archiving database</span></span>

  - <span data-ttu-id="f597f-136">база данных мониторинга;</span><span class="sxs-lookup"><span data-stu-id="f597f-136">Monitoring database</span></span>

  - <span data-ttu-id="f597f-137">База данных сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="f597f-137">Persistent Chat database</span></span>

  - <span data-ttu-id="f597f-138">База данных соответствия сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="f597f-138">Persistent Chat compliance database</span></span>

<span data-ttu-id="f597f-139">Одно файловое хранилище можно использовать для нескольких интерфейсных пулов и серверов Standard Edition (все на одном узле).</span><span class="sxs-lookup"><span data-stu-id="f597f-139">A single file share can be used for multiple Front End pools, Standard Edition servers (all in the same site).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f597f-140">В Lync Server 2013 мониторинг и архивация используют файловый ресурс Lync Server в качестве сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f597f-140">In Lync Server 2013, Monitoring and Archiving use the Lync Server file share as the Standard Edition server.</span></span>



</div>

</div>

<div>

## <a name="other-components"></a><span data-ttu-id="f597f-141">Другие компоненты</span><span class="sxs-lookup"><span data-stu-id="f597f-141">Other Components</span></span>

<span data-ttu-id="f597f-142">Вы не можете совместно использовать обратный прокси-сервер, который не является компонентом Lync Server 2013, но требуется в развертывании, если вы хотите поддерживать общий доступ к веб-контенту для федеративных пользователей с любой ролью сервера Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f597f-142">You cannot collocate a reverse proxy server, which is not a Lync Server 2013 component, but is required in your deployment if you want to support sharing of web content for federated users with any Lync Server 2013 server role.</span></span> <span data-ttu-id="f597f-143">Тем не менее, вы можете реализовать поддержку обратного прокси-сервера для развертывания Lync Server 2013, настроив поддержку существующего обратного прокси-сервера в Организации, используемого для других приложений.</span><span class="sxs-lookup"><span data-stu-id="f597f-143">You can, however, implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span>

<span data-ttu-id="f597f-144">Вы не можете совместно размещать любой компонент единой системы обмена сообщениями Exchange или компонент SharePoint с любой ролью Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f597f-144">You cannot collocate any Exchange UM component or SharePoint component with any Lync Server 2013 role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

