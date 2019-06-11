---
title: Выровненное размещение серверов Lync Server 2013 в развертывании сервера Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server collocation in a Standard Edition server deployment
ms:assetid: 0763ffab-4fd6-463a-8e62-d97876b376d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398131(v=OCS.15)
ms:contentKeyID: 48183314
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 950f2ab06a146ec99ef9ebb2ecbc64c885c82d70
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821966"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-a-standard-edition-server-deployment-for-lync-server-2013"></a><span data-ttu-id="045e4-102">Выровненное размещение серверов в развертывании сервера Standard Edition для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="045e4-102">Server collocation in a Standard Edition server deployment for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="045e4-103">_**Тема последнего изменения:** 2013-01-20_</span><span class="sxs-lookup"><span data-stu-id="045e4-103">_**Topic Last Modified:** 2013-01-20_</span></span>

<span data-ttu-id="045e4-104">В этом разделе описаны роли сервера, базы данных и общие папки, которые можно отформатировать в развертывании сервера Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="045e4-104">This section describes the server roles, databases, and file shares that you can collocate in a Lync Server 2013 Standard Edition server deployment.</span></span>

<div>

## <a name="server-roles"></a><span data-ttu-id="045e4-105">Роли сервера</span><span class="sxs-lookup"><span data-stu-id="045e4-105">Server Roles</span></span>

<span data-ttu-id="045e4-106">В Lync Server 2013, служба конференц-связи, служба исправлений, мониторинг и архивация размещаются на сервере Standard Edition, но для их включения требуется дополнительная настройка.</span><span class="sxs-lookup"><span data-stu-id="045e4-106">In Lync Server 2013, A/V Conferencing service, Mediation service, Monitoring, and Archiving are collocated on the Standard Edition Server, but additional configuration is required to enable them.</span></span> <span data-ttu-id="045e4-107">Вы можете выбрать развертывание службы исправлений на отдельных серверах.</span><span class="sxs-lookup"><span data-stu-id="045e4-107">You can choose to deploy Mediation service on separate servers.</span></span>

<span data-ttu-id="045e4-108">Вы можете разпрограммировать доверенный сервер приложений с помощью стандартного сервера выпуска Standard.</span><span class="sxs-lookup"><span data-stu-id="045e4-108">You can collocate a trusted application server with a Standard Edition server.</span></span>

<span data-ttu-id="045e4-109">Следующие роли сервера должны развертываться на отдельном компьютере:</span><span class="sxs-lookup"><span data-stu-id="045e4-109">The following server roles must each be deployed on a separate computer:</span></span>

  - <span data-ttu-id="045e4-110">Директор</span><span class="sxs-lookup"><span data-stu-id="045e4-110">Director</span></span>

  - <span data-ttu-id="045e4-111">пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="045e4-111">Edge Server</span></span>

  - <span data-ttu-id="045e4-112">Сервер-посредник (если он не размещен на сервере Standard Edition)</span><span class="sxs-lookup"><span data-stu-id="045e4-112">Mediation Server (if not collocated with the Standard Edition server)</span></span>

  - <span data-ttu-id="045e4-113">Сервер Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="045e4-113">Office Web Apps Server</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="045e4-114">Базы данных</span><span class="sxs-lookup"><span data-stu-id="045e4-114">Databases</span></span>

<span data-ttu-id="045e4-115">По умолчанию серверная база данных SQL Server Express выровнена на сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="045e4-115">By default, the SQL Server Express back-end database is collocated on the Standard Edition server.</span></span> <span data-ttu-id="045e4-116">Вы не можете переместить его на отдельный компьютер.</span><span class="sxs-lookup"><span data-stu-id="045e4-116">You cannot move it to a separate computer.</span></span> <span data-ttu-id="045e4-117">С одним исключением нельзя выдавать общие базы данных на сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="045e4-117">With one exception, you cannot collocate other databases on the Standard Edition server.</span></span> <span data-ttu-id="045e4-118">Если вы решили развернуть сервер сохраняемого чата на сервере Standard Edition, вы можете разгруппировать базу данных сохраняемого чата и базу данных соответствия требованиям сохраняемого чата на одном стандартном сервере выпуске.</span><span class="sxs-lookup"><span data-stu-id="045e4-118">If you choose to deploy Persistent Chat Server on a Standard Edition server, you can collocate the Persistent chat database and the Persistent Chat Compliance database on the same Standard Edition server.</span></span>

<span data-ttu-id="045e4-119">Вы можете разадресовать каждую из следующих баз данных на одном сервере базы данных.</span><span class="sxs-lookup"><span data-stu-id="045e4-119">You can collocate each of the following databases on a single database server:</span></span>

  - <span data-ttu-id="045e4-120">данных мониторинга</span><span class="sxs-lookup"><span data-stu-id="045e4-120">Monitoring database</span></span>

  - <span data-ttu-id="045e4-121">данных архивации</span><span class="sxs-lookup"><span data-stu-id="045e4-121">Archiving database</span></span>

  - <span data-ttu-id="045e4-122">Серверная база данных для пула предварительных интерфейсов Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="045e4-122">A back-end database for an Enterprise Edition Front End pool</span></span>

<span data-ttu-id="045e4-123">Вы можете выделять любые из этих баз данных или любые из них в одном экземпляре SQL или использовать отдельные экземпляры SQL для каждого из них с указанными ниже ограничениями.</span><span class="sxs-lookup"><span data-stu-id="045e4-123">You can collocate any or any or all of these databases in a single SQL instance or use a separate SQL instances for each, with the following limitations:</span></span>

  - <span data-ttu-id="045e4-124">Каждый экземпляр SQL может содержать только одну серверную базу данных (для пула переднего плана Enterprise Edition), одну базу данных мониторинга, одну базу данных для архивации, единую базу данных чата и единую постоянную базу данных соответствия чатов.</span><span class="sxs-lookup"><span data-stu-id="045e4-124">Each SQL instance can contain only a single back-end database (for an Enterprise Edition Front End pool), single Monitoring database, single Archiving database, single persistent chat database, and single persistent chat compliance database.</span></span>

  - <span data-ttu-id="045e4-125">Сервер базы данных не может поддерживать более одного пула переднего плана выпуска Enterprise Edition, один сервер, на котором выполняется архивация, один сервер, на котором запущена система мониторинга, единая база данных чата и единая сохраняемая база данных для проверки подлинности, но она поддерживает один из них. независимо от того, используют ли базы данных один и тот же экземпляр SQL Server или отдельные экземпляры SQL Server.</span><span class="sxs-lookup"><span data-stu-id="045e4-125">The database server cannot support more than one Enterprise Edition Front End pool, one server running Archiving, one server running Monitoring, single Persistent Chat database, and single Persistent Chat compliance database, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

<span data-ttu-id="045e4-126">Вы можете предоставить общий доступ к файлам с помощью баз данных, как описано далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="045e4-126">You can collocate a file share with the databases, as described later in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="045e4-127">В Lync Server 2013 имеется возможность интеграции наблюдения и архивации данных с хранилищем Exchange 2013 для некоторых или всех пользователей в развертывании.</span><span class="sxs-lookup"><span data-stu-id="045e4-127">In Lync Server 2013, you have the option of integrating Monitoring and Archiving storage with Exchange 2013 storage for some or all users in your deployment.</span></span> <span data-ttu-id="045e4-128">Вы не можете развернуть серверы, на которых запущен Lync Server или компоненты, на тех же серверах, что и в хранилище Exchange.</span><span class="sxs-lookup"><span data-stu-id="045e4-128">You cannot deploy any servers running Lync Server or components on the same servers as the Exchange storage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="045e4-129">Несмотря на то, что размещение баз данных поддерживается, размер баз данных может быстро увеличиваться.</span><span class="sxs-lookup"><span data-stu-id="045e4-129">Although collocation of databases is supported, the size of the databases can grow quickly.</span></span> <span data-ttu-id="045e4-130">Например, если вы рассматриваете различную базу данных архивации с другими базами данных, имейте в виду, что при архивации сообщений, которые не являются несколькими пользователями, объем дискового пространства, необходимого для базы данных архивации, может увеличиваться очень большим.</span><span class="sxs-lookup"><span data-stu-id="045e4-130">For example, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="045e4-131">По этой причине мы не рекомендуем выписывать несколько баз данных, особенно базу данных архивации, сохраняемый чат и сохраняемую базу данных соответствия чатов с серверной базой данных корпоративного пула.</span><span class="sxs-lookup"><span data-stu-id="045e4-131">For this reason, we do not recommend collocating multiple databases, especially the Archiving database, Persistent Chat database, and Persistent Chat compliance database with the back-end database of an Enterprise pool.</span></span>



</div>

</div>

<div>

## <a name="file-shares"></a><span data-ttu-id="045e4-132">Общие файлы</span><span class="sxs-lookup"><span data-stu-id="045e4-132">File Shares</span></span>

<span data-ttu-id="045e4-133">Общий файловый объект может быть размещен на отдельном сервере или может быть размещен на том же сервере, что и любые из указанных ниже элементов.</span><span class="sxs-lookup"><span data-stu-id="045e4-133">The file share can be a separate server or can be collocated on the same server as any or all of the following:</span></span>

  - <span data-ttu-id="045e4-134">Сервер базы данных, включая сервер переднего плана для пула выпусков Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="045e4-134">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

  - <span data-ttu-id="045e4-135">данных архивации</span><span class="sxs-lookup"><span data-stu-id="045e4-135">Archiving database</span></span>

  - <span data-ttu-id="045e4-136">данных мониторинга</span><span class="sxs-lookup"><span data-stu-id="045e4-136">Monitoring database</span></span>

  - <span data-ttu-id="045e4-137">База данных сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="045e4-137">Persistent Chat database</span></span>

  - <span data-ttu-id="045e4-138">База данных соответствия требованиям сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="045e4-138">Persistent Chat compliance database</span></span>

<span data-ttu-id="045e4-139">Один общий файловый объект может использоваться для нескольких пулов переднего плана, серверов Standard Edition (на одном сайте).</span><span class="sxs-lookup"><span data-stu-id="045e4-139">A single file share can be used for multiple Front End pools, Standard Edition servers (all in the same site).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="045e4-140">В Lync Server 2013 для мониторинга и архивации используется общий доступ к файлам Lync Server в качестве сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="045e4-140">In Lync Server 2013, Monitoring and Archiving use the Lync Server file share as the Standard Edition server.</span></span>



</div>

</div>

<div>

## <a name="other-components"></a><span data-ttu-id="045e4-141">Другие компоненты</span><span class="sxs-lookup"><span data-stu-id="045e4-141">Other Components</span></span>

<span data-ttu-id="045e4-142">Вы не можете разадресовать обратный прокси-сервер, который не является компонентом Lync Server 2013, но является обязательным в развертывании, если вы хотите поддерживать общий доступ к веб-контенту для федеративных пользователей с любой ролью сервера Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="045e4-142">You cannot collocate a reverse proxy server, which is not a Lync Server 2013 component, but is required in your deployment if you want to support sharing of web content for federated users with any Lync Server 2013 server role.</span></span> <span data-ttu-id="045e4-143">Однако вы можете реализовать обратную поддержку прокси-сервера для развертывания Lync Server 2013, настроив поддержку на существующем обратном прокси-сервере в Организации, который используется для других приложений.</span><span class="sxs-lookup"><span data-stu-id="045e4-143">You can, however, implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span>

<span data-ttu-id="045e4-144">Вы не можете разгруппировать любой компонент Exchange UM или компонент SharePoint с помощью любой роли Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="045e4-144">You cannot collocate any Exchange UM component or SharePoint component with any Lync Server 2013 role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

