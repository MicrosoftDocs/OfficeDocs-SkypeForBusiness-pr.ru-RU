---
title: 'Lync Server 2013: выровненное размещение серверов в развертывании пула переднего плана Enterprise Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server collocation in an Enterprise Edition Front End pool deployment
ms:assetid: 0516b18d-14c0-4237-9279-0f92e341b1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398102(v=OCS.15)
ms:contentKeyID: 48183287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6947d732cf17cc053e48596ffd310f5df3b11636
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822022"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-an-enterprise-edition-front-end-pool-deployment-for-lync-server-2013"></a><span data-ttu-id="f3263-102">Выровненное размещение серверов в развертывании пула переднего плана Enterprise Edition для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3263-102">Server collocation in an Enterprise Edition Front End pool deployment for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3263-103">_**Тема последнего изменения:** 2013-11-11_</span><span class="sxs-lookup"><span data-stu-id="f3263-103">_**Topic Last Modified:** 2013-11-11_</span></span>

<span data-ttu-id="f3263-104">В этом разделе описаны роли сервера, базы данных и общие папки, которые можно отформатировать в рамках развертывания пула интерфейсов на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f3263-104">This section describes the server roles, databases, and file shares that you can collocate in a Lync Server 2013 Front End pool deployment.</span></span>

<div>

## <a name="server-roles"></a><span data-ttu-id="f3263-105">Роли сервера</span><span class="sxs-lookup"><span data-stu-id="f3263-105">Server Roles</span></span>

<span data-ttu-id="f3263-106">В Lync Server 2013, служба конференц-связи, служба исправлений, мониторинг и архивация размещаются на сервере переднего плана, но для их включения требуется дополнительная настройка.</span><span class="sxs-lookup"><span data-stu-id="f3263-106">In Lync Server 2013, A/V Conferencing service, Mediation service, Monitoring, and Archiving are collocated on the Front End Server, but additional configuration is required to enable them.</span></span> <span data-ttu-id="f3263-107">Если вы не хотите выделять сервер-посредник с помощью сервера переднего плана, вы можете развернуть его как изолированный сервер в отдельном компьютере.</span><span class="sxs-lookup"><span data-stu-id="f3263-107">If you do not want to collocate the Mediation Server with the Front End Server, you can deploy it as a stand-alone Mediation Server on a separate computer.</span></span>

<span data-ttu-id="f3263-108">Вы можете использовать доверенный сервер приложений на сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="f3263-108">You can collocate a trusted application server with the Front End Server.</span></span>

<span data-ttu-id="f3263-109">Следующие роли сервера должны развертываться на отдельном компьютере:</span><span class="sxs-lookup"><span data-stu-id="f3263-109">The following server roles must each be deployed on a separate computer:</span></span>

  - <span data-ttu-id="f3263-110">Директор</span><span class="sxs-lookup"><span data-stu-id="f3263-110">Director</span></span>

  - <span data-ttu-id="f3263-111">пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="f3263-111">Edge Server</span></span>

  - <span data-ttu-id="f3263-112">Сервер-посредник (если он не выровнен на сервере переднего плана)</span><span class="sxs-lookup"><span data-stu-id="f3263-112">Mediation Server (if not collocated with the Front End Server)</span></span>

  - <span data-ttu-id="f3263-113">Сервер Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="f3263-113">Office Web Apps Server</span></span>

<span data-ttu-id="f3263-114">Вы не можете разгруппировать роль сервера "сохраняемый чат" на сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="f3263-114">You cannot collocate Persistent Chat server role with the Front End Server.</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="f3263-115">Базы данных</span><span class="sxs-lookup"><span data-stu-id="f3263-115">Databases</span></span>

<span data-ttu-id="f3263-116">Вы можете разадресовать каждую из следующих баз данных на одном сервере базы данных:</span><span class="sxs-lookup"><span data-stu-id="f3263-116">You can collocate each of the following databases on the same database server:</span></span>

  - <span data-ttu-id="f3263-117">Серверная база данных</span><span class="sxs-lookup"><span data-stu-id="f3263-117">Back-end database</span></span>

  - <span data-ttu-id="f3263-118">данных мониторинга</span><span class="sxs-lookup"><span data-stu-id="f3263-118">Monitoring database</span></span>

  - <span data-ttu-id="f3263-119">данных архивации</span><span class="sxs-lookup"><span data-stu-id="f3263-119">Archiving database</span></span>

  - <span data-ttu-id="f3263-120">База данных сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="f3263-120">Persistent Chat database</span></span>

  - <span data-ttu-id="f3263-121">База данных соответствия требованиям сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="f3263-121">Persistent Chat compliance database</span></span>

<span data-ttu-id="f3263-122">Вы можете выделять любые из этих баз данных или любые из них в одном экземпляре SQL Server или использовать отдельный экземпляр SQL Server для каждого из них с указанными ниже ограничениями.</span><span class="sxs-lookup"><span data-stu-id="f3263-122">You can collocate any or any or all of these databases in a single instance of SQL Server or use a separate instance of SQL Server for each, with the following limitations:</span></span>

  - <span data-ttu-id="f3263-123">Каждый экземпляр SQL Server может содержать только одну серверную базу данных, одну базу данных мониторинга, одну базу данных для хранения данных, одну из них, а также единственную постоянную базу данных соответствия чатов.</span><span class="sxs-lookup"><span data-stu-id="f3263-123">Each instance of SQL Server can contain only a single back-end database, a single Monitoring database, a single Archiving database, a single Persistent Chat database, and a single Persistent Chat compliance database.</span></span>

  - <span data-ttu-id="f3263-124">Сервер базы данных не может поддерживать более одного пула переднего плана, одно развертывание архивации и одно развертывание мониторинга, но может поддерживать один из них вне зависимости от того, используют ли базы данных один и тот же экземпляр SQL Server или отдельные экземпляры SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f3263-124">The database server cannot support more than one Front End pool, one Archiving deployment, and one Monitoring deployment, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

<span data-ttu-id="f3263-125">Вы можете предоставить общий доступ к файлам с помощью баз данных, как описано далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="f3263-125">You can collocate a file share with the databases, as described later in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f3263-126">В Lync Server 2013 имеется возможность интеграции хранилища архивации с хранилищем Exchange 2013 для некоторых или всех пользователей в развертывании.</span><span class="sxs-lookup"><span data-stu-id="f3263-126">In Lync Server 2013, you have the option of integrating Archiving storage with Exchange 2013 storage for some or all users in your deployment.</span></span> <span data-ttu-id="f3263-127">Вы не можете развернуть серверы, на которых запущен Lync Server или компоненты, на тех же серверах, что и в хранилище Exchange.</span><span class="sxs-lookup"><span data-stu-id="f3263-127">You cannot deploy any servers running Lync Server or components on the same servers as the Exchange storage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f3263-128">Несмотря на то, что размещение баз данных поддерживается, размер баз данных может быстро увеличиваться.</span><span class="sxs-lookup"><span data-stu-id="f3263-128">Although collocation of databases is supported, the size of the databases can grow quickly.</span></span> <span data-ttu-id="f3263-129">Например, если вы рассматриваете различную базу данных архивации с другими базами данных, имейте в виду, что при архивации сообщений, которые не являются несколькими пользователями, объем дискового пространства, необходимого для базы данных архивации, может увеличиваться очень большим.</span><span class="sxs-lookup"><span data-stu-id="f3263-129">For example, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="f3263-130">По этой причине мы не рекомендуем выписывать несколько баз данных, особенно базу данных архивации, базу данных сохраняемого чата или базу данных соответствия требованиям к сохраненной базе данных.</span><span class="sxs-lookup"><span data-stu-id="f3263-130">For this reason, we do not recommend collocating multiple databases, especially the Archiving database, the Persistent Chat database, or the Persistent Chat compliance database with the back-end database.</span></span>



</div>

</div>

<div>

## <a name="file-share"></a><span data-ttu-id="f3263-131">Файловый ресурс</span><span class="sxs-lookup"><span data-stu-id="f3263-131">File Share</span></span>

<span data-ttu-id="f3263-132">Общий файловый объект может быть размещен на отдельном сервере или может быть размещен на том же сервере, что и любые из указанных ниже элементов.</span><span class="sxs-lookup"><span data-stu-id="f3263-132">The file share can be a separate server or can be collocated on the same server as any or all of the following:</span></span>

  - <span data-ttu-id="f3263-133">Сервер базы данных, включая сервер переднего плана для пула выпусков Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="f3263-133">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

  - <span data-ttu-id="f3263-134">данных архивации</span><span class="sxs-lookup"><span data-stu-id="f3263-134">Archiving database</span></span>

  - <span data-ttu-id="f3263-135">данных мониторинга</span><span class="sxs-lookup"><span data-stu-id="f3263-135">Monitoring database</span></span>

  - <span data-ttu-id="f3263-136">База данных сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="f3263-136">Persistent Chat database</span></span>

  - <span data-ttu-id="f3263-137">База данных соответствия требованиям сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="f3263-137">Persistent Chat compliance database</span></span>

<span data-ttu-id="f3263-138">Один общий файловый объект может использоваться для нескольких пулов переднего плана, серверов Standard Edition (на одном сайте).</span><span class="sxs-lookup"><span data-stu-id="f3263-138">A single file share can be used for multiple Front End pools, Standard Edition servers (all in the same site).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f3263-139">В Lync Server 2013 для мониторинга и архивации используется общий доступ к файлам Lync Server в качестве сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="f3263-139">In Lync Server 2013, Monitoring and Archiving use the Lync Server file share as the Front End Server.</span></span>



</div>

</div>

<div>

## <a name="other-components"></a><span data-ttu-id="f3263-140">Другие компоненты</span><span class="sxs-lookup"><span data-stu-id="f3263-140">Other Components</span></span>

<span data-ttu-id="f3263-141">Вы не можете разадресовать обратный прокси-сервер, который не является компонентом Lync Server 2013, но является обязательным в развертывании, если вы хотите поддерживать общий доступ к веб-контенту для федеративных пользователей с любой ролью сервера Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f3263-141">You cannot collocate a reverse proxy server, which is not a Lync Server 2013 component, but is required in your deployment if you want to support sharing of web content for federated users with any Lync Server 2013 server role.</span></span> <span data-ttu-id="f3263-142">Однако вы можете реализовать обратную поддержку прокси-сервера для развертывания Lync Server 2013, настроив поддержку на существующем обратном прокси-сервере в Организации, который используется для других приложений.</span><span class="sxs-lookup"><span data-stu-id="f3263-142">You can, however, implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span>

<span data-ttu-id="f3263-143">Вы не можете использовать один и тот же компонент единой системы обмена сообщениями Exchange (UM) или компонент SharePoint для любой роли SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="f3263-143">You cannot collocate any Exchange Unified Messaging (UM) component or SharePoint component with any SharePoint Server role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

