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
ms.openlocfilehash: 7fe18bf750eabdb1f53c97a349b553da4f13dec8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740869"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="59262-102">Развертывание сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59262-102">Deploying Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59262-103">_**Тема последнего изменения:** 2014-03-31_</span><span class="sxs-lookup"><span data-stu-id="59262-103">_**Topic Last Modified:** 2014-03-31_</span></span>

<span data-ttu-id="59262-104">Lync Server 2013, сервер сохраняемого чата входит в состав инфраструктуры Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="59262-104">Lync Server 2013, Persistent Chat Server is part of the Lync Server 2013 infrastructure.</span></span>

<span data-ttu-id="59262-105">Для развертывания сохраняемого сервера чата необходимо:</span><span class="sxs-lookup"><span data-stu-id="59262-105">Deploying Persistent Chat Server requires that you:</span></span>

  - <span data-ttu-id="59262-106">С помощью Topology Builder вы можете определить (или импортировать) и затем опубликовать свою топологию и компоненты, которые вы хотите развернуть.</span><span class="sxs-lookup"><span data-stu-id="59262-106">Use Topology Builder to define, or import, and subsequently publish your topology and the components that you want to deploy.</span></span>

  - <span data-ttu-id="59262-107">Подготовка среды для развертывания постоянных серверных компонентов чата.</span><span class="sxs-lookup"><span data-stu-id="59262-107">Prepare your environment for deploying Persistent Chat Server components.</span></span>

  - <span data-ttu-id="59262-108">Установите и настройте компоненты сервера сохраняемого чата для развертывания.</span><span class="sxs-lookup"><span data-stu-id="59262-108">Install and configure Persistent Chat Server components for your deployment.</span></span>

<span data-ttu-id="59262-109">Сервер для Lync Server 2013 Enterprise Edition доступен в виде отдельного пула (не размещается вместе с серверами переднего плана Enterprise Edition).</span><span class="sxs-lookup"><span data-stu-id="59262-109">Persistent Chat Server is available with Lync Server 2013 Enterprise Edition as a separate pool (not collocated with the Enterprise Edition Front End Servers).</span></span> <span data-ttu-id="59262-110">Для хранения содержимого комнаты чата и других нужных метаданных сервер для работы с сохраняемым чат требуется сервер SQL Server из пула Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="59262-110">Persistent Chat Server requires a SQL Server Back End Server in your Enterprise Edition pool to store the chat room content and other relevant metadata.</span></span> <span data-ttu-id="59262-111">Мы рекомендуем установить **персистентчатсторе** на выделенный сервер SQL Server, несмотря на то, что размещение сервера Lync Server 2013 и **персистентчатсторе** на одном и том же экземпляре SQL Server поддерживается.</span><span class="sxs-lookup"><span data-stu-id="59262-111">We recommend that you install the **PersistentChatStore** on a dedicated SQL Server Back End Server, although collocating Lync Server 2013 Back End Server and **PersistentChatStore** on the same SQL Server instance is supported.</span></span>

<span data-ttu-id="59262-112">Кроме того, с помощью Lync Server 2013 Standard Edition можно развернуть сервер сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="59262-112">Persistent Chat Server can also be deployed with Lync Server 2013 Standard Edition.</span></span> <span data-ttu-id="59262-113">В этом случае сервер переднего плана **персистентчатсервице** размещается на компьютере Standard Edition, а сервер **персистентчатсторе** Server можно развернуть на локальном экземпляре SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="59262-113">In this case, the **PersistentChatService** Front End Server is collocated on the Standard Edition computer, and the **PersistentChatStore** Back End Server can be deployed on the local SQL Server Express instance.</span></span>

<span data-ttu-id="59262-114">Подробные сведения о поддерживаемых конфигурациях сорасположений можно найти в разделе Поддерживаемые параметры совместного расположения [серверов в Lync server 2013](lync-server-2013-supported-server-collocation.md).</span><span class="sxs-lookup"><span data-stu-id="59262-114">For details about supported colocation configurations, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="59262-115">Мы не поддерживаем высокий уровень доступности сохраняемого сервера&nbsp;для работы с версией Standard Chat.</span><span class="sxs-lookup"><span data-stu-id="59262-115">We do not support high availability for Persistent Chat Server&nbsp;Standard Edition.</span></span> <span data-ttu-id="59262-116">Производительность и масштаб будут ограничены.</span><span class="sxs-lookup"><span data-stu-id="59262-116">Performance and scale will be limited.</span></span> <span data-ttu-id="59262-117">Кроме того, мы поддерживаем только новый сервер&nbsp;стандартный выпуск для версии для постоянного чата.</span><span class="sxs-lookup"><span data-stu-id="59262-117">Furthermore, we support only new Persistent Chat Server&nbsp;Standard Edition server.</span></span> <span data-ttu-id="59262-118">Мы не поддерживаем обновление Lync Server 2010, групповой чат с сервером для Lync Server 2013&nbsp;для обычного чата Server&nbsp;Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="59262-118">We do not support upgrading Lync Server 2010, Group Chat Server to a Lync Server 2013&nbsp;Persistent Chat Server&nbsp;Standard Edition.</span></span>



</div>

<span data-ttu-id="59262-119">Если в вашей организации требуется поддержка соответствия требованиям, вы можете установить службу соответствия требованиям сервера для разговора на сервер переднего плана с постоянным участием.</span><span class="sxs-lookup"><span data-stu-id="59262-119">If your organization requires compliance support, you can install the Persistent Chat Server Compliance service on the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="59262-120">Для обеспечения соответствия требованиям требуется отдельная база данных.</span><span class="sxs-lookup"><span data-stu-id="59262-120">A separate database is required for compliance.</span></span>

<span data-ttu-id="59262-121">Для каждой топологии требуется сервер с установленным Lync Server 2013 и сервер с установленным программным обеспечением базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="59262-121">At a minimum, each topology requires a server with Lync Server 2013 installed and a server with SQL Server database software installed.</span></span>

<span data-ttu-id="59262-122">Используйте построитель топологии, чтобы добавить сохраняемый сервер чата в развертывание Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="59262-122">Use Topology Builder to add Persistent Chat Server to your Lync Server 2013 deployments.</span></span> <span data-ttu-id="59262-123">Вы можете добавить один или несколько пулов серверов для постоянного чата с помощью Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="59262-123">You can choose to add one or more Persistent Chat Server pools using Topology Builder.</span></span> <span data-ttu-id="59262-124">Следуйте тем же инструкциям по развертыванию, чтобы развернуть несколько пулов серверов сохраняемого чата, как и в случае с пулом.</span><span class="sxs-lookup"><span data-stu-id="59262-124">Follow the same deployment instructions for deploying multiple Persistent Chat Server pools as you would for any pool.</span></span> <span data-ttu-id="59262-125">Подробные сведения можно найти в разделе [развертывание Lync Server 2013](lync-server-2013-deploying-lync-server.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="59262-125">For details, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="59262-126">Сведения о доступных топологиях, требованиях к техническим и программному обеспечению для установки постоянного сервера чата, приведены в разделе [планирование сохраняемого сервера чата в Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) в документации по планированию, [как сервер сохраняемого чата используется в Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) в документации по планированию, документации по развертыванию, документации по операциям и [поддерживаемому оборудованию для Lync Server 2013](lync-server-2013-supported-hardware.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="59262-126">For details about available topologies and the technical and software requirements for installing Persistent Chat Server, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation, [How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in the Planning documentation, Deployment documentation, or Operations documentation, and [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

<span data-ttu-id="59262-127">Подробные сведения о получении сертификатов, создании базы данных SQL Server и создании хранилищ файлов можно найти в разделе [развертывание Lync Server 2013](lync-server-2013-deploying-lync-server.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="59262-127">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="59262-128">Один сервер-сервер для входа в чате может поддерживать 20 000 активных пользователей.</span><span class="sxs-lookup"><span data-stu-id="59262-128">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="59262-129">Вы можете использовать серверный пул для постоянного чата с четырьмя активными серверами переднего плана, поддерживающими общее количество одновременных пользователей 80 000.</span><span class="sxs-lookup"><span data-stu-id="59262-129">You can have a Persistent Chat Server pool with up to 4 active Front End Servers supporting a total of 80,000 concurrent users.</span></span>

<span data-ttu-id="59262-130">На виртуальном сервере также поддерживается сохраняемый сервер чатов.</span><span class="sxs-lookup"><span data-stu-id="59262-130">Persistent Chat Server is also supported on a virtual server.</span></span> <span data-ttu-id="59262-131">Виртуальный сервер может поддерживать до 20 000 одновременных пользователей, если он соответствует спецификациям физического сервера.</span><span class="sxs-lookup"><span data-stu-id="59262-131">The virtual server can support up to 20,000 concurrent users if it matches the specifications of the physical server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="59262-132">Для обеспечения безопасности файловой системы необходимо установить сохраняемый сервер чата в файловой системе NTFS.</span><span class="sxs-lookup"><span data-stu-id="59262-132">Persistent Chat Server must be installed on an NTFS file system to help enforce file system security.</span></span> <span data-ttu-id="59262-133">Файловая система FAT32 не поддерживается для сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="59262-133">FAT32 is not a supported file system for Persistent Chat Server.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="59262-134">Содержание</span><span class="sxs-lookup"><span data-stu-id="59262-134">In This Section</span></span>

  - [<span data-ttu-id="59262-135">Как работает сервер сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59262-135">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="59262-136">Контрольный список развертывания для сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59262-136">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [<span data-ttu-id="59262-137">Технические требования для постоянного сервера чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59262-137">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="59262-138">Настройка систем и инфраструктуры для сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59262-138">Setting up systems and infrastructure for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [<span data-ttu-id="59262-139">Добавление сервера сохраняемого сеанса беседы в развертывание в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59262-139">Adding Persistent Chat Server to your deployment in Lync Server 2013</span></span>](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [<span data-ttu-id="59262-140">Установка сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59262-140">Installing Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-installing-persistent-chat-server.md)

  - [<span data-ttu-id="59262-141">Добавление администратора сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59262-141">Adding a Persistent Chat administrator in Lync Server 2013</span></span>](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [<span data-ttu-id="59262-142">Настройка сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59262-142">Configuring Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server.md)

  - [<span data-ttu-id="59262-143">Настройка сервера сохраняемого сеанса беседы с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="59262-143">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</span></span>](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [<span data-ttu-id="59262-144">Устранение неполадок конфигурации сервера сохраняемого чата с помощью командлетов Windows PowerShell в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59262-144">Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [<span data-ttu-id="59262-145">Настройка сервера сохраняемого чата для обеспечения высокой доступности и аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59262-145">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="59262-146">Отработка отказа и восстановление после сбоя сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59262-146">Failing over and failing back Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

