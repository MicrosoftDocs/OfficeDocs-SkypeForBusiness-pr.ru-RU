---
title: 'Lync Server 2013: подготовка инфраструктуры и систем'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the infrastructure and systems
ms:assetid: 1254ee38-0679-4714-b293-1050f107c158
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398205(v=OCS.15)
ms:contentKeyID: 48183458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fc49f5e246e69f600506d990ace7362d9666f1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-infrastructure-and-systems-for-lync-server-2013"></a><span data-ttu-id="42a05-102">Подготовка инфраструктуры и систем для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42a05-102">Preparing the infrastructure and systems for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42a05-103">_**Тема последнего изменения:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="42a05-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="42a05-104">Для развертывания Lync Server 2013 требуется использование построителя топологии для определения и публикации структуры топологии.</span><span class="sxs-lookup"><span data-stu-id="42a05-104">Deployment of Lync Server 2013 requires the use of Topology Builder to define and publish the topology design.</span></span> <span data-ttu-id="42a05-105">Чтобы определить компоненты, необходимые для вашей топологии, вы используете Topology Builder для создания и сохранения структуры топологии.</span><span class="sxs-lookup"><span data-stu-id="42a05-105">To identify the components required for your topology, you use Topology Builder to create and save a topology design.</span></span> <span data-ttu-id="42a05-106">Прежде чем публиковать топологию в построителе топологии, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="42a05-106">Prior to publishing your topology in Topology Builder, you do the following:</span></span>

  - <span data-ttu-id="42a05-107">Получение и установка оборудования для каждого компонента в структуре топологии, созданной и сохраненной с помощью построителя топологии, включая все необходимые компьютеры (серверы с Lync Server 2013, серверы баз данных, серверы с запущенными информационными службами Интернета) ( IIS) и обратные прокси-серверы, сетевые адаптеры, подсистемы балансировки нагрузки оборудования и запоминающие устройства (например, файловые серверы).</span><span class="sxs-lookup"><span data-stu-id="42a05-107">Acquire and install the hardware for each component in the topology design that you created and saved by using Topology Builder, including all required computers (servers running Lync Server 2013, database servers, servers running Internet Information Services (IIS), and reverse proxy servers, as appropriate), network adapters, hardware load balancers, and storage devices (such as file servers).</span></span> <span data-ttu-id="42a05-108">Подробные сведения о том, как определить топологию, указывающую компоненты, необходимые для вашего развертывания, приведены [в разделе Определение и Настройка топологии в Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="42a05-108">For details about how to define a topology that specifies the components needed for your deployment, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span> <span data-ttu-id="42a05-109">Дополнительные сведения о требованиях к оборудованию для серверов можно найти в документации о поддержке [оборудования для Lync Server 2013](lync-server-2013-supported-hardware.md) .</span><span class="sxs-lookup"><span data-stu-id="42a05-109">For details about hardware requirements for servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="42a05-110">Убедитесь, что сетевая инфраструктура соответствует требованиям.</span><span class="sxs-lookup"><span data-stu-id="42a05-110">Make sure that the networking infrastructure meets requirements.</span></span> <span data-ttu-id="42a05-111">Подробности можно найти в разделе [требования к сетевой инфраструктуре для Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="42a05-111">For details, see [Network infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="42a05-112">Настройте доменные службы Active Directory.</span><span class="sxs-lookup"><span data-stu-id="42a05-112">Set up Active Directory Domain Services.</span></span> <span data-ttu-id="42a05-113">Для публикации и включения топологии необходимы внутренние серверы, которые должны быть представлены учетными записями компьютеров в доменных СЛУЖБах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="42a05-113">To publish and enable the topology, you need the internal servers to be represented by computer accounts in AD DS.</span></span> <span data-ttu-id="42a05-114">Это можно сделать, присоединяя компьютеры к доменной службе Active Directory.</span><span class="sxs-lookup"><span data-stu-id="42a05-114">This is accomplished by joining the computers to AD DS.</span></span> <span data-ttu-id="42a05-115">Дополнительные сведения о подготовке доменных служб Active Directory можно найти в статьях [Подготовка службы AD DS для Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="42a05-115">For details about preparing AD DS, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

  - <span data-ttu-id="42a05-116">Создайте файловый общий доступ.</span><span class="sxs-lookup"><span data-stu-id="42a05-116">Create a file share.</span></span> <span data-ttu-id="42a05-117">Сервер стандартных выпусков может размещать общую файловую систему для нужного файла, в корпоративной среде общий доступ к файлам не может размещаться на сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="42a05-117">Standard Edition servers can host the file share for the required file, while in an Enterprise deployment the file share cannot be hosted on the front end server.</span></span> <span data-ttu-id="42a05-118">Разрешения и членство в группах, необходимые для развертывания и настройки списка управления доступом (ACL) в папке, и общий доступ должны быть правильно заданы для успешного завершения построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="42a05-118">The permissions and group memberships required for deploying and setting the access control list (ACL) on the folder and the share must be set correctly for Topology Builder to complete successfully.</span></span> <span data-ttu-id="42a05-119">Необходимо убедиться в том, что у пользователя, выполняющего Topology Builder, есть следующие разрешения и членство в группах.</span><span class="sxs-lookup"><span data-stu-id="42a05-119">You should make sure that the person running Topology Builder has the following permissions and group memberships:</span></span>
    
      - <span data-ttu-id="42a05-120">Член локальных администраторов</span><span class="sxs-lookup"><span data-stu-id="42a05-120">Member of Local Administrators</span></span>
    
      - <span data-ttu-id="42a05-121">Член группы пользователей домена</span><span class="sxs-lookup"><span data-stu-id="42a05-121">Member of Domain Users</span></span>
    
      - <span data-ttu-id="42a05-122">Полный контроль над папкой "общий доступ" и "папка" в хранилище файлов</span><span class="sxs-lookup"><span data-stu-id="42a05-122">Full Control on share and folder of file store</span></span>

  - <span data-ttu-id="42a05-123">Для выпуска Enterprise Edition установите и настройте SQL Server.</span><span class="sxs-lookup"><span data-stu-id="42a05-123">For Enterprise Edition, install and configure SQL Server.</span></span> <span data-ttu-id="42a05-124">Для успешного завершения установки SQL Server необходимо, чтобы сервер SQL Server был подключен к сети, а пользователь, публикующий топологию, был локальным администратором SQL Server и должен быть членом группы sysadmin SQL Server в экземпляре SQL Server.</span><span class="sxs-lookup"><span data-stu-id="42a05-124">For SQL Server setup to succeed the SQL Server-based server must be online and the person publishing the topology be a local admin on the SQL Server and must be a member of the SQL Server sysadmin group on the SQL Server instance.</span></span>

<span data-ttu-id="42a05-125">После выполнения всех задач подготовки, описанных в этой статье, но прежде чем публиковать топологию, вам также потребуется выполнить другие задачи подготовки, в том числе установка операционной системы Windows и другого необходимого программного обеспечения, Настройка IIS и настройка DNS.</span><span class="sxs-lookup"><span data-stu-id="42a05-125">After you complete all of the preparation tasks as described in this topic, but prior to publishing the topology, you also need to perform the other preparation tasks, including installing the Windows operating systems and other prerequisite software, setting up IIS, and configuring DNS.</span></span> <span data-ttu-id="42a05-126">Подробнее об этих задачах можно узнать в разделе [требования к системе для серверов с Lync server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [Настройка служб IIS для Lync Server 2013](lync-server-2013-configure-iis.md)и [Подготовка инфраструктуры и систем для Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md).</span><span class="sxs-lookup"><span data-stu-id="42a05-126">For details about these tasks, see [System requirements for servers running Lync Server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [Configure IIS for Lync Server 2013](lync-server-2013-configure-iis.md), and [Preparing the infrastructure and systems for Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md).</span></span> <span data-ttu-id="42a05-127">Кроме того, вы должны ознакомиться с требованиями клиентов и клиентов.</span><span class="sxs-lookup"><span data-stu-id="42a05-127">Additionally, you should familiarize yourself with the clients and client requirements.</span></span> <span data-ttu-id="42a05-128">Подробные сведения можно найти [в разделе Развертывание клиентов и устройств в Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).</span><span class="sxs-lookup"><span data-stu-id="42a05-128">For details, see [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="42a05-129">Содержание</span><span class="sxs-lookup"><span data-stu-id="42a05-129">In This Section</span></span>

  - [<span data-ttu-id="42a05-130">Настройка оборудования для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42a05-130">Hardware setup for Lync Server 2013</span></span>](lync-server-2013-hardware-setup.md)

  - [<span data-ttu-id="42a05-131">Установка программного обеспечения для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42a05-131">Software setup for Lync Server 2013</span></span>](lync-server-2013-software-setup.md)

  - [<span data-ttu-id="42a05-132">Подготовка доменных служб Active Directory для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42a05-132">Preparing Active Directory Domain Services for Lync Server 2013</span></span>](lync-server-2013-preparing-active-directory-domain-services.md)

  - [<span data-ttu-id="42a05-133">Настройка SQL Server для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42a05-133">Configure SQL Server for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [<span data-ttu-id="42a05-134">Настройка DNS-записей в Lync Server 2013 для пула переднего плана или сервера Standard Edition</span><span class="sxs-lookup"><span data-stu-id="42a05-134">Configure DNS records in Lync Server 2013 for a Front End pool or Standard Edition server</span></span>](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [<span data-ttu-id="42a05-135">Установка средств администрирования Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42a05-135">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

