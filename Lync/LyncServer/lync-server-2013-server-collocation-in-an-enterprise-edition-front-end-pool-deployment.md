---
title: Совместное размещение серверов Lync Server 2013 в развертывании пула переднего плана Enterprise Edition
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
ms.openlocfilehash: 0162a4338a1504ed425015e5b9391fca9903d4ab
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510286"
---
# <a name="server-collocation-in-an-enterprise-edition-front-end-pool-deployment-for-lync-server-2013"></a><span data-ttu-id="abfe7-102">Выровненное размещение серверов в развертывании пула переднего плана Enterprise Edition для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abfe7-102">Server collocation in an Enterprise Edition Front End pool deployment for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abfe7-103">_**Последнее изменение темы:** 2013-11-11_</span><span class="sxs-lookup"><span data-stu-id="abfe7-103">_**Topic Last Modified:** 2013-11-11_</span></span>

<span data-ttu-id="abfe7-104">В этом разделе описываются роли сервера, базы данных и файловые ресурсы, которые можно разместить в развертывании пула переднего плана Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="abfe7-104">This section describes the server roles, databases, and file shares that you can collocate in a Lync Server 2013 Front End pool deployment.</span></span>

<div>

## <a name="server-roles"></a><span data-ttu-id="abfe7-105">Роли серверов</span><span class="sxs-lookup"><span data-stu-id="abfe7-105">Server Roles</span></span>

<span data-ttu-id="abfe7-106">В Lync Server 2013, служба аудио-и видеоконференций, служба-посредник, мониторинг и архивация размещаются на сервере переднего плана, но для их включения требуется дополнительная настройка.</span><span class="sxs-lookup"><span data-stu-id="abfe7-106">In Lync Server 2013, A/V Conferencing service, Mediation service, Monitoring, and Archiving are collocated on the Front End Server, but additional configuration is required to enable them.</span></span> <span data-ttu-id="abfe7-107">Если вы не хотите совместно размещать сервер-посредник с интерфейсным сервером, вы можете развернуть его как автономный сервер-посредник на отдельном компьютере.</span><span class="sxs-lookup"><span data-stu-id="abfe7-107">If you do not want to collocate the Mediation Server with the Front End Server, you can deploy it as a stand-alone Mediation Server on a separate computer.</span></span>

<span data-ttu-id="abfe7-108">Можно совместно расположить доверенный сервер приложений с интерфейсным сервером.</span><span class="sxs-lookup"><span data-stu-id="abfe7-108">You can collocate a trusted application server with the Front End Server.</span></span>

<span data-ttu-id="abfe7-109">Следующие роли сервера должны быть развернуты на отдельном компьютере:</span><span class="sxs-lookup"><span data-stu-id="abfe7-109">The following server roles must each be deployed on a separate computer:</span></span>

  - <span data-ttu-id="abfe7-110">Директор</span><span class="sxs-lookup"><span data-stu-id="abfe7-110">Director</span></span>

  - <span data-ttu-id="abfe7-111">пограничный сервер;</span><span class="sxs-lookup"><span data-stu-id="abfe7-111">Edge Server</span></span>

  - <span data-ttu-id="abfe7-112">сервер-посредник (если он не размещается совместно с интерфейсным сервером);</span><span class="sxs-lookup"><span data-stu-id="abfe7-112">Mediation Server (if not collocated with the Front End Server)</span></span>

  - <span data-ttu-id="abfe7-113">Сервер Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="abfe7-113">Office Web Apps Server</span></span>

<span data-ttu-id="abfe7-114">Вы не можете совместно разместить роль сервера сохраняемого чата с сервером переднего плана.</span><span class="sxs-lookup"><span data-stu-id="abfe7-114">You cannot collocate Persistent Chat server role with the Front End Server.</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="abfe7-115">Databases</span><span class="sxs-lookup"><span data-stu-id="abfe7-115">Databases</span></span>

<span data-ttu-id="abfe7-116">Следующие базы данных можно совместно расположить на одном сервере баз данных:</span><span class="sxs-lookup"><span data-stu-id="abfe7-116">You can collocate each of the following databases on the same database server:</span></span>

  - <span data-ttu-id="abfe7-117">фоновая база данных;</span><span class="sxs-lookup"><span data-stu-id="abfe7-117">Back-end database</span></span>

  - <span data-ttu-id="abfe7-118">база данных мониторинга;</span><span class="sxs-lookup"><span data-stu-id="abfe7-118">Monitoring database</span></span>

  - <span data-ttu-id="abfe7-119">база данных архивации;</span><span class="sxs-lookup"><span data-stu-id="abfe7-119">Archiving database</span></span>

  - <span data-ttu-id="abfe7-120">База данных сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="abfe7-120">Persistent Chat database</span></span>

  - <span data-ttu-id="abfe7-121">База данных соответствия сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="abfe7-121">Persistent Chat compliance database</span></span>

<span data-ttu-id="abfe7-122">В одном экземпляре SQL Server можно совместно использовать любые или все эти базы данных, а для каждого из них можно использовать отдельный экземпляр SQL Server со следующими ограничениями:</span><span class="sxs-lookup"><span data-stu-id="abfe7-122">You can collocate any or any or all of these databases in a single instance of SQL Server or use a separate instance of SQL Server for each, with the following limitations:</span></span>

  - <span data-ttu-id="abfe7-123">Каждый экземпляр SQL Server может содержать только одну серверную базу данных, одну базу данных мониторинга, одну базу данных архивации, одну базу данных сохраняемого чата, а также одну базу данных соответствия сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="abfe7-123">Each instance of SQL Server can contain only a single back-end database, a single Monitoring database, a single Archiving database, a single Persistent Chat database, and a single Persistent Chat compliance database.</span></span>

  - <span data-ttu-id="abfe7-124">Сервер баз данных не может поддерживать более одного интерфейсного пула, одного развертывания архивации и одного развертывания мониторинга, но он может поддерживать один из них независимо от того, используют ли базы данных один и тот же экземпляр SQL Server или отдельные экземпляры SQL Server.</span><span class="sxs-lookup"><span data-stu-id="abfe7-124">The database server cannot support more than one Front End pool, one Archiving deployment, and one Monitoring deployment, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

<span data-ttu-id="abfe7-125">Можно расположить файловый ресурс совместно с базами данных, как описано далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="abfe7-125">You can collocate a file share with the databases, as described later in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="abfe7-126">В Lync Server 2013 имеется возможность интеграции хранилища архивации с хранилищем Exchange 2013 для некоторых или всех пользователей в развертывании.</span><span class="sxs-lookup"><span data-stu-id="abfe7-126">In Lync Server 2013, you have the option of integrating Archiving storage with Exchange 2013 storage for some or all users in your deployment.</span></span> <span data-ttu-id="abfe7-127">Вы не можете развернуть серверы Lync Server или компоненты на тех же серверах, что и хранилище Exchange.</span><span class="sxs-lookup"><span data-stu-id="abfe7-127">You cannot deploy any servers running Lync Server or components on the same servers as the Exchange storage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="abfe7-128">Хотя совместное размещение баз данных поддерживается, размер баз данных может быстро увеличиваться.</span><span class="sxs-lookup"><span data-stu-id="abfe7-128">Although collocation of databases is supported, the size of the databases can grow quickly.</span></span> <span data-ttu-id="abfe7-129">Например, при совместном размещении базы данных архивации с другими базами данных, следует помнить, что при архивации сообщений большого числа пользователей, размер дискового пространства, необходимый для базы данных архивации, может стать очень большим.</span><span class="sxs-lookup"><span data-stu-id="abfe7-129">For example, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="abfe7-130">По этой причине мы не рекомендуем размещать несколько баз данных, особенно базы данных архивации, базы данных сохраняемого чата или базы данных соответствия сохраняемого чата с серверной базой данных.</span><span class="sxs-lookup"><span data-stu-id="abfe7-130">For this reason, we do not recommend collocating multiple databases, especially the Archiving database, the Persistent Chat database, or the Persistent Chat compliance database with the back-end database.</span></span>



</div>

</div>

<div>

## <a name="file-share"></a><span data-ttu-id="abfe7-131">Файловый ресурс</span><span class="sxs-lookup"><span data-stu-id="abfe7-131">File Share</span></span>

<span data-ttu-id="abfe7-132">Общий файловый ресурс может быть отдельным сервером или можно размещаться совместно на том же сервере, что следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="abfe7-132">The file share can be a separate server or can be collocated on the same server as any or all of the following:</span></span>

  - <span data-ttu-id="abfe7-133">сервер баз данных, в том числе фоновый сервер из интерфейсного пула Enterprise Edition;</span><span class="sxs-lookup"><span data-stu-id="abfe7-133">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

  - <span data-ttu-id="abfe7-134">база данных архивации;</span><span class="sxs-lookup"><span data-stu-id="abfe7-134">Archiving database</span></span>

  - <span data-ttu-id="abfe7-135">база данных мониторинга;</span><span class="sxs-lookup"><span data-stu-id="abfe7-135">Monitoring database</span></span>

  - <span data-ttu-id="abfe7-136">База данных сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="abfe7-136">Persistent Chat database</span></span>

  - <span data-ttu-id="abfe7-137">База данных соответствия сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="abfe7-137">Persistent Chat compliance database</span></span>

<span data-ttu-id="abfe7-138">Одно файловое хранилище можно использовать для нескольких интерфейсных пулов и серверов Standard Edition (все на одном узле).</span><span class="sxs-lookup"><span data-stu-id="abfe7-138">A single file share can be used for multiple Front End pools, Standard Edition servers (all in the same site).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="abfe7-139">В Lync Server 2013 мониторинг и архивация используют общий файловый ресурс Lync Server в качестве сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="abfe7-139">In Lync Server 2013, Monitoring and Archiving use the Lync Server file share as the Front End Server.</span></span>



</div>

</div>

<div>

## <a name="other-components"></a><span data-ttu-id="abfe7-140">Другие компоненты</span><span class="sxs-lookup"><span data-stu-id="abfe7-140">Other Components</span></span>

<span data-ttu-id="abfe7-141">Вы не можете совместно использовать обратный прокси-сервер, который не является компонентом Lync Server 2013, но требуется в развертывании, если вы хотите поддерживать общий доступ к веб-контенту для федеративных пользователей с любой ролью сервера Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="abfe7-141">You cannot collocate a reverse proxy server, which is not a Lync Server 2013 component, but is required in your deployment if you want to support sharing of web content for federated users with any Lync Server 2013 server role.</span></span> <span data-ttu-id="abfe7-142">Тем не менее, вы можете реализовать поддержку обратного прокси-сервера для развертывания Lync Server 2013, настроив поддержку существующего обратного прокси-сервера в Организации, используемого для других приложений.</span><span class="sxs-lookup"><span data-stu-id="abfe7-142">You can, however, implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span>

<span data-ttu-id="abfe7-143">Совместное размещение компонентов единой системы обмена сообщениями Exchange и компонентов SharePoint с любой ролью SharePoint Server невозможно.</span><span class="sxs-lookup"><span data-stu-id="abfe7-143">You cannot collocate any Exchange Unified Messaging (UM) component or SharePoint component with any SharePoint Server role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

