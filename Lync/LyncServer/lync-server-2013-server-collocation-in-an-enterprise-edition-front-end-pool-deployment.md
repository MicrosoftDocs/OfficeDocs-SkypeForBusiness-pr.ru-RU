---
title: Совместное размещение серверов Lync Server 2013 в развертывании пула переднего плана Enterprise Edition
description: Совместное размещение серверов Lync Server 2013 в развертывании пула переднего плана Enterprise Edition.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server collocation in an Enterprise Edition Front End pool deployment
ms:assetid: 0516b18d-14c0-4237-9279-0f92e341b1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398102(v=OCS.15)
ms:contentKeyID: 48183287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a937cd2d58e41d56fec3c7898ebcf6725086d51
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576555"
---
# <a name="server-collocation-in-an-enterprise-edition-front-end-pool-deployment-for-lync-server-2013"></a><span data-ttu-id="4c707-103">Выровненное размещение серверов в развертывании пула переднего плана Enterprise Edition для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c707-103">Server collocation in an Enterprise Edition Front End pool deployment for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c707-104">_**Последнее изменение темы:** 2013-11-11_</span><span class="sxs-lookup"><span data-stu-id="4c707-104">_**Topic Last Modified:** 2013-11-11_</span></span>

<span data-ttu-id="4c707-105">В этом разделе описываются роли сервера, базы данных и файловые ресурсы, которые можно разместить в развертывании пула переднего плана Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4c707-105">This section describes the server roles, databases, and file shares that you can collocate in a Lync Server 2013 Front End pool deployment.</span></span>

<div>

## <a name="server-roles"></a><span data-ttu-id="4c707-106">Роли серверов</span><span class="sxs-lookup"><span data-stu-id="4c707-106">Server Roles</span></span>

<span data-ttu-id="4c707-107">В Lync Server 2013, служба аудио-и видеоконференций, служба-посредник, мониторинг и архивация размещаются на сервере переднего плана, но для их включения требуется дополнительная настройка.</span><span class="sxs-lookup"><span data-stu-id="4c707-107">In Lync Server 2013, A/V Conferencing service, Mediation service, Monitoring, and Archiving are collocated on the Front End Server, but additional configuration is required to enable them.</span></span> <span data-ttu-id="4c707-108">Если вы не хотите совместно размещать сервер-посредник с интерфейсным сервером, вы можете развернуть его как автономный сервер-посредник на отдельном компьютере.</span><span class="sxs-lookup"><span data-stu-id="4c707-108">If you do not want to collocate the Mediation Server with the Front End Server, you can deploy it as a stand-alone Mediation Server on a separate computer.</span></span>

<span data-ttu-id="4c707-109">Можно совместно расположить доверенный сервер приложений с интерфейсным сервером.</span><span class="sxs-lookup"><span data-stu-id="4c707-109">You can collocate a trusted application server with the Front End Server.</span></span>

<span data-ttu-id="4c707-110">Следующие роли сервера должны быть развернуты на отдельном компьютере:</span><span class="sxs-lookup"><span data-stu-id="4c707-110">The following server roles must each be deployed on a separate computer:</span></span>

  - <span data-ttu-id="4c707-111">Директор</span><span class="sxs-lookup"><span data-stu-id="4c707-111">Director</span></span>

  - <span data-ttu-id="4c707-112">пограничный сервер;</span><span class="sxs-lookup"><span data-stu-id="4c707-112">Edge Server</span></span>

  - <span data-ttu-id="4c707-113">сервер-посредник (если он не размещается совместно с интерфейсным сервером);</span><span class="sxs-lookup"><span data-stu-id="4c707-113">Mediation Server (if not collocated with the Front End Server)</span></span>

  - <span data-ttu-id="4c707-114">Сервер Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="4c707-114">Office Web Apps Server</span></span>

<span data-ttu-id="4c707-115">Вы не можете совместно разместить роль сервера сохраняемого чата с сервером переднего плана.</span><span class="sxs-lookup"><span data-stu-id="4c707-115">You cannot collocate Persistent Chat server role with the Front End Server.</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="4c707-116">Databases</span><span class="sxs-lookup"><span data-stu-id="4c707-116">Databases</span></span>

<span data-ttu-id="4c707-117">Следующие базы данных можно совместно расположить на одном сервере баз данных:</span><span class="sxs-lookup"><span data-stu-id="4c707-117">You can collocate each of the following databases on the same database server:</span></span>

  - <span data-ttu-id="4c707-118">фоновая база данных;</span><span class="sxs-lookup"><span data-stu-id="4c707-118">Back-end database</span></span>

  - <span data-ttu-id="4c707-119">база данных мониторинга;</span><span class="sxs-lookup"><span data-stu-id="4c707-119">Monitoring database</span></span>

  - <span data-ttu-id="4c707-120">база данных архивации;</span><span class="sxs-lookup"><span data-stu-id="4c707-120">Archiving database</span></span>

  - <span data-ttu-id="4c707-121">База данных сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="4c707-121">Persistent Chat database</span></span>

  - <span data-ttu-id="4c707-122">База данных соответствия сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="4c707-122">Persistent Chat compliance database</span></span>

<span data-ttu-id="4c707-123">В одном экземпляре SQL Server можно совместно использовать любые или все эти базы данных, а для каждого из них можно использовать отдельный экземпляр SQL Server со следующими ограничениями:</span><span class="sxs-lookup"><span data-stu-id="4c707-123">You can collocate any or any or all of these databases in a single instance of SQL Server or use a separate instance of SQL Server for each, with the following limitations:</span></span>

  - <span data-ttu-id="4c707-124">Каждый экземпляр SQL Server может содержать только одну серверную базу данных, одну базу данных мониторинга, одну базу данных архивации, одну базу данных сохраняемого чата, а также одну базу данных соответствия сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="4c707-124">Each instance of SQL Server can contain only a single back-end database, a single Monitoring database, a single Archiving database, a single Persistent Chat database, and a single Persistent Chat compliance database.</span></span>

  - <span data-ttu-id="4c707-125">Сервер баз данных не может поддерживать более одного интерфейсного пула, одного развертывания архивации и одного развертывания мониторинга, но он может поддерживать один из них независимо от того, используют ли базы данных один и тот же экземпляр SQL Server или отдельные экземпляры SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4c707-125">The database server cannot support more than one Front End pool, one Archiving deployment, and one Monitoring deployment, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

<span data-ttu-id="4c707-126">Можно расположить файловый ресурс совместно с базами данных, как описано далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="4c707-126">You can collocate a file share with the databases, as described later in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4c707-127">В Lync Server 2013 имеется возможность интеграции хранилища архивации с хранилищем Exchange 2013 для некоторых или всех пользователей в развертывании.</span><span class="sxs-lookup"><span data-stu-id="4c707-127">In Lync Server 2013, you have the option of integrating Archiving storage with Exchange 2013 storage for some or all users in your deployment.</span></span> <span data-ttu-id="4c707-128">Вы не можете развернуть серверы Lync Server или компоненты на тех же серверах, что и хранилище Exchange.</span><span class="sxs-lookup"><span data-stu-id="4c707-128">You cannot deploy any servers running Lync Server or components on the same servers as the Exchange storage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4c707-129">Хотя совместное размещение баз данных поддерживается, размер баз данных может быстро увеличиваться.</span><span class="sxs-lookup"><span data-stu-id="4c707-129">Although collocation of databases is supported, the size of the databases can grow quickly.</span></span> <span data-ttu-id="4c707-130">Например, при совместном размещении базы данных архивации с другими базами данных, следует помнить, что при архивации сообщений большого числа пользователей, размер дискового пространства, необходимый для базы данных архивации, может стать очень большим.</span><span class="sxs-lookup"><span data-stu-id="4c707-130">For example, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="4c707-131">По этой причине мы не рекомендуем размещать несколько баз данных, особенно базы данных архивации, базы данных сохраняемого чата или базы данных соответствия сохраняемого чата с серверной базой данных.</span><span class="sxs-lookup"><span data-stu-id="4c707-131">For this reason, we do not recommend collocating multiple databases, especially the Archiving database, the Persistent Chat database, or the Persistent Chat compliance database with the back-end database.</span></span>



</div>

</div>

<div>

## <a name="file-share"></a><span data-ttu-id="4c707-132">Файловый ресурс</span><span class="sxs-lookup"><span data-stu-id="4c707-132">File Share</span></span>

<span data-ttu-id="4c707-133">Общий файловый ресурс может быть отдельным сервером или можно размещаться совместно на том же сервере, что следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="4c707-133">The file share can be a separate server or can be collocated on the same server as any or all of the following:</span></span>

  - <span data-ttu-id="4c707-134">сервер баз данных, в том числе фоновый сервер из интерфейсного пула Enterprise Edition;</span><span class="sxs-lookup"><span data-stu-id="4c707-134">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

  - <span data-ttu-id="4c707-135">база данных архивации;</span><span class="sxs-lookup"><span data-stu-id="4c707-135">Archiving database</span></span>

  - <span data-ttu-id="4c707-136">база данных мониторинга;</span><span class="sxs-lookup"><span data-stu-id="4c707-136">Monitoring database</span></span>

  - <span data-ttu-id="4c707-137">База данных сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="4c707-137">Persistent Chat database</span></span>

  - <span data-ttu-id="4c707-138">База данных соответствия сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="4c707-138">Persistent Chat compliance database</span></span>

<span data-ttu-id="4c707-139">Одно файловое хранилище можно использовать для нескольких интерфейсных пулов и серверов Standard Edition (все на одном узле).</span><span class="sxs-lookup"><span data-stu-id="4c707-139">A single file share can be used for multiple Front End pools, Standard Edition servers (all in the same site).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4c707-140">В Lync Server 2013 мониторинг и архивация используют общий файловый ресурс Lync Server в качестве сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="4c707-140">In Lync Server 2013, Monitoring and Archiving use the Lync Server file share as the Front End Server.</span></span>



</div>

</div>

<div>

## <a name="other-components"></a><span data-ttu-id="4c707-141">Другие компоненты</span><span class="sxs-lookup"><span data-stu-id="4c707-141">Other Components</span></span>

<span data-ttu-id="4c707-142">Вы не можете совместно использовать обратный прокси-сервер, который не является компонентом Lync Server 2013, но требуется в развертывании, если вы хотите поддерживать общий доступ к веб-контенту для федеративных пользователей с любой ролью сервера Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4c707-142">You cannot collocate a reverse proxy server, which is not a Lync Server 2013 component, but is required in your deployment if you want to support sharing of web content for federated users with any Lync Server 2013 server role.</span></span> <span data-ttu-id="4c707-143">Тем не менее, вы можете реализовать поддержку обратного прокси-сервера для развертывания Lync Server 2013, настроив поддержку существующего обратного прокси-сервера в Организации, используемого для других приложений.</span><span class="sxs-lookup"><span data-stu-id="4c707-143">You can, however, implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span>

<span data-ttu-id="4c707-144">Совместное размещение компонентов единой системы обмена сообщениями Exchange и компонентов SharePoint с любой ролью SharePoint Server невозможно.</span><span class="sxs-lookup"><span data-stu-id="4c707-144">You cannot collocate any Exchange Unified Messaging (UM) component or SharePoint component with any SharePoint Server role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

