---
title: 'Lync Server 2013: развертывание сервера сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Persistent Chat Server
ms:assetid: e3b930fb-6855-47f0-b6b3-7dfae386540d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205357(v=OCS.15)
ms:contentKeyID: 48185717
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab8049097383932bacb198cd8eb4fe6e96917feb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043431"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="eb70a-102">Развертывание сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb70a-102">Deploying Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb70a-103">_**Последнее изменение темы:** 2014-03-31_</span><span class="sxs-lookup"><span data-stu-id="eb70a-103">_**Topic Last Modified:** 2014-03-31_</span></span>

<span data-ttu-id="eb70a-104">Lync Server 2013, сервер сохраняемого чата входит в состав инфраструктуры Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eb70a-104">Lync Server 2013, Persistent Chat Server is part of the Lync Server 2013 infrastructure.</span></span>

<span data-ttu-id="eb70a-105">При развертывании сервера сохраняемого чата необходимо выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="eb70a-105">Deploying Persistent Chat Server requires that you:</span></span>

  - <span data-ttu-id="eb70a-106">Используйте построитель топологий для определения или импорта и последующей публикации топологии и компонентов, которые требуется развернуть.</span><span class="sxs-lookup"><span data-stu-id="eb70a-106">Use Topology Builder to define, or import, and subsequently publish your topology and the components that you want to deploy.</span></span>

  - <span data-ttu-id="eb70a-107">Подготовьте среду для развертывания компонентов сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="eb70a-107">Prepare your environment for deploying Persistent Chat Server components.</span></span>

  - <span data-ttu-id="eb70a-108">Установите и настройте компоненты сервера сохраняемого чата для развертывания.</span><span class="sxs-lookup"><span data-stu-id="eb70a-108">Install and configure Persistent Chat Server components for your deployment.</span></span>

<span data-ttu-id="eb70a-109">Сервер сохраняемого чата доступен в составе Lync Server 2013 Enterprise Edition в виде отдельного пула (без совместного размещения на серверах переднего плана Enterprise Edition).</span><span class="sxs-lookup"><span data-stu-id="eb70a-109">Persistent Chat Server is available with Lync Server 2013 Enterprise Edition as a separate pool (not collocated with the Enterprise Edition Front End Servers).</span></span> <span data-ttu-id="eb70a-110">Сервер сохраняемого чата требует наличия внутреннего сервера SQL Server в пуле Enterprise Edition для хранения содержимого комнаты чата и других релевантных метаданных.</span><span class="sxs-lookup"><span data-stu-id="eb70a-110">Persistent Chat Server requires a SQL Server Back End Server in your Enterprise Edition pool to store the chat room content and other relevant metadata.</span></span> <span data-ttu-id="eb70a-111">Рекомендуется установить **PersistentChatStore** на выделенный сервер переднего плана SQL Server, хотя совместное размещение внешних серверов Lync Server 2013 и **PersistentChatStore** в одном экземпляре SQL Server поддерживается.</span><span class="sxs-lookup"><span data-stu-id="eb70a-111">We recommend that you install the **PersistentChatStore** on a dedicated SQL Server Back End Server, although collocating Lync Server 2013 Back End Server and **PersistentChatStore** on the same SQL Server instance is supported.</span></span>

<span data-ttu-id="eb70a-112">Сервер сохраняемого чата также можно развернуть с помощью Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="eb70a-112">Persistent Chat Server can also be deployed with Lync Server 2013 Standard Edition.</span></span> <span data-ttu-id="eb70a-113">В этом случае сервер переднего плана **PersistentChatService** размещается на компьютере Standard Edition, а внутренний сервер **PersistentChatStore** может быть развернут на локальном экземпляре SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="eb70a-113">In this case, the **PersistentChatService** Front End Server is collocated on the Standard Edition computer, and the **PersistentChatStore** Back End Server can be deployed on the local SQL Server Express instance.</span></span>

<span data-ttu-id="eb70a-114">Дополнительные сведения о поддерживаемых конфигурациях совместного расположения приведены [в разделе Поддержка выровненных серверов в Lync server 2013](lync-server-2013-supported-server-collocation.md).</span><span class="sxs-lookup"><span data-stu-id="eb70a-114">For details about supported colocation configurations, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="eb70a-115">Мы не поддерживаем высокий уровень доступности для сервера&nbsp;сохраняемого чата Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="eb70a-115">We do not support high availability for Persistent Chat Server&nbsp;Standard Edition.</span></span> <span data-ttu-id="eb70a-116">Производительность и масштабирование будут ограничены.</span><span class="sxs-lookup"><span data-stu-id="eb70a-116">Performance and scale will be limited.</span></span> <span data-ttu-id="eb70a-117">Кроме того, поддерживается только новый сервер сервера&nbsp;Standard Edition для сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="eb70a-117">Furthermore, we support only new Persistent Chat Server&nbsp;Standard Edition server.</span></span> <span data-ttu-id="eb70a-118">Мы не поддерживаем обновление Lync Server 2010, Group Chat Server до версии сервера&nbsp;&nbsp;сохраняемого чата для сервера Standard chat для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eb70a-118">We do not support upgrading Lync Server 2010, Group Chat Server to a Lync Server 2013&nbsp;Persistent Chat Server&nbsp;Standard Edition.</span></span>



</div>

<span data-ttu-id="eb70a-119">Если в Организации требуется поддержка соответствия требованиям, вы можете установить службу соответствия сервера сохраняемого чата на сервере переднего плана сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="eb70a-119">If your organization requires compliance support, you can install the Persistent Chat Server Compliance service on the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="eb70a-120">Для совместимости требуется отдельная база данных.</span><span class="sxs-lookup"><span data-stu-id="eb70a-120">A separate database is required for compliance.</span></span>

<span data-ttu-id="eb70a-121">Для каждой топологии требуется как минимум сервер с установленным Lync Server 2013 и сервер с установленным программным обеспечением баз данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="eb70a-121">At a minimum, each topology requires a server with Lync Server 2013 installed and a server with SQL Server database software installed.</span></span>

<span data-ttu-id="eb70a-122">Используйте построитель топологий, чтобы добавить сервер сохраняемого чата в развертывания Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eb70a-122">Use Topology Builder to add Persistent Chat Server to your Lync Server 2013 deployments.</span></span> <span data-ttu-id="eb70a-123">Вы можете добавить один или несколько пулов серверов сохраняемого чата с помощью построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="eb70a-123">You can choose to add one or more Persistent Chat Server pools using Topology Builder.</span></span> <span data-ttu-id="eb70a-124">Следуйте тем же инструкциям по развертыванию, чтобы развернуть несколько пулов серверов сохраняемого чата, как и для любого пула.</span><span class="sxs-lookup"><span data-stu-id="eb70a-124">Follow the same deployment instructions for deploying multiple Persistent Chat Server pools as you would for any pool.</span></span> <span data-ttu-id="eb70a-125">Дополнительные сведения см. в разделе [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="eb70a-125">For details, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="eb70a-126">Сведения о доступных топологиях, а также требованиях к техническим и программному обеспечению для установки сервера сохраняемого чата приведены в статье [Планирование сервера сохраняемого чата в Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) в документации по планированию, [как сервер сохраняемого чата в Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) в документации по планированию, документации по развертыванию или документации по работе, а также [поддерживаемое оборудование для Lync Server 2013](lync-server-2013-supported-hardware.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="eb70a-126">For details about available topologies and the technical and software requirements for installing Persistent Chat Server, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation, [How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in the Planning documentation, Deployment documentation, or Operations documentation, and [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

<span data-ttu-id="eb70a-127">Для получения дополнительных сведений о получении сертификатов, создании базы данных SQL Server и создании хранилищ файлов ознакомьтесь со статьей [deploy Lync Server 2013](lync-server-2013-deploying-lync-server.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="eb70a-127">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="eb70a-128">Один сервер переднего плана сервера сохраняемого чата может поддерживать 20 000 активных пользователей.</span><span class="sxs-lookup"><span data-stu-id="eb70a-128">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="eb70a-129">Пул серверов сохраняемого чата может иметь до четырех активных серверов переднего плана, поддерживающих всего 80 000 одновременно работающих пользователей.</span><span class="sxs-lookup"><span data-stu-id="eb70a-129">You can have a Persistent Chat Server pool with up to 4 active Front End Servers supporting a total of 80,000 concurrent users.</span></span>

<span data-ttu-id="eb70a-130">Сервер сохраняемого чата также поддерживается на виртуальном сервере.</span><span class="sxs-lookup"><span data-stu-id="eb70a-130">Persistent Chat Server is also supported on a virtual server.</span></span> <span data-ttu-id="eb70a-131">Виртуальный сервер может поддерживать до 20000 пользователей при условии соответствия характеристикам физического сервера.</span><span class="sxs-lookup"><span data-stu-id="eb70a-131">The virtual server can support up to 20,000 concurrent users if it matches the specifications of the physical server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="eb70a-132">Для обеспечения безопасности файловой системы необходимо установить сервер сохраняемого чата в файловой системе NTFS.</span><span class="sxs-lookup"><span data-stu-id="eb70a-132">Persistent Chat Server must be installed on an NTFS file system to help enforce file system security.</span></span> <span data-ttu-id="eb70a-133">Файловая система FAT32 не поддерживается для сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="eb70a-133">FAT32 is not a supported file system for Persistent Chat Server.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="eb70a-134">Содержание</span><span class="sxs-lookup"><span data-stu-id="eb70a-134">In This Section</span></span>

  - [<span data-ttu-id="eb70a-135">Принцип работы сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb70a-135">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="eb70a-136">Контрольный список развертывания для сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb70a-136">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [<span data-ttu-id="eb70a-137">Технические требования для сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb70a-137">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="eb70a-138">Настройка систем и инфраструктуры для сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb70a-138">Setting up systems and infrastructure for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [<span data-ttu-id="eb70a-139">Добавление сервера сохраняемого чата в развертывание в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb70a-139">Adding Persistent Chat Server to your deployment in Lync Server 2013</span></span>](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [<span data-ttu-id="eb70a-140">Установка сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb70a-140">Installing Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-installing-persistent-chat-server.md)

  - [<span data-ttu-id="eb70a-141">Добавление администратора сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb70a-141">Adding a Persistent Chat administrator in Lync Server 2013</span></span>](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [<span data-ttu-id="eb70a-142">Настройка сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb70a-142">Configuring Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server.md)

  - [<span data-ttu-id="eb70a-143">Настройка сервера сохраняемого чата с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="eb70a-143">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</span></span>](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [<span data-ttu-id="eb70a-144">Устранение неполадок конфигурации сервера сохраняемого чата с помощью командлетов Windows PowerShell в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb70a-144">Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [<span data-ttu-id="eb70a-145">Настройка сервера сохраняемого чата для обеспечения высокой доступности и аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb70a-145">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="eb70a-146">Отработка отказа и отработка отказа сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb70a-146">Failing over and failing back Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

