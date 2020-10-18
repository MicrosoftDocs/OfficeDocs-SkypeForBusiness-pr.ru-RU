---
title: 'Lync Server 2013: подготовка инфраструктуры и систем'
description: 'Lync Server 2013: подготовка инфраструктуры и систем.'
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
ms.openlocfilehash: bfabdda9d117af1534578c8543f9ce72808d5a53
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579995"
---
# <a name="preparing-the-infrastructure-and-systems-for-lync-server-2013"></a><span data-ttu-id="0b446-103">Подготовка инфраструктуры и систем для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b446-103">Preparing the infrastructure and systems for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b446-104">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="0b446-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="0b446-105">Для развертывания Lync Server 2013 необходимо использовать построитель топологий для определения и публикации структуры топологии.</span><span class="sxs-lookup"><span data-stu-id="0b446-105">Deployment of Lync Server 2013 requires the use of Topology Builder to define and publish the topology design.</span></span> <span data-ttu-id="0b446-106">Чтобы определить компоненты, необходимые для вашей топологии, используйте построитель топологий для создания и сохранения структуры топологии.</span><span class="sxs-lookup"><span data-stu-id="0b446-106">To identify the components required for your topology, you use Topology Builder to create and save a topology design.</span></span> <span data-ttu-id="0b446-107">Перед публикацией топологии в построителе топологии выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="0b446-107">Prior to publishing your topology in Topology Builder, you do the following:</span></span>

  - <span data-ttu-id="0b446-108">Приобретите и установите оборудование для каждого компонента в структуре топологии, которая была создана и сохранена с помощью построителя топологий, включая все необходимые компьютеры (серверы Lync Server 2013, серверы баз данных, серверы IIS и обратные прокси-серверы, при необходимости), сетевые адаптеры, аппаратные средства балансировки нагрузки и устройства хранения (например, файловые серверы).</span><span class="sxs-lookup"><span data-stu-id="0b446-108">Acquire and install the hardware for each component in the topology design that you created and saved by using Topology Builder, including all required computers (servers running Lync Server 2013, database servers, servers running Internet Information Services (IIS), and reverse proxy servers, as appropriate), network adapters, hardware load balancers, and storage devices (such as file servers).</span></span> <span data-ttu-id="0b446-109">Сведения об определении топологии, указывающей компоненты, необходимые для развертывания, приведены [в статье определение и Настройка топологии в Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="0b446-109">For details about how to define a topology that specifies the components needed for your deployment, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span> <span data-ttu-id="0b446-110">Для получения дополнительных сведений о требованиях к оборудованию для серверов ознакомьтесь со статьей [Supported Hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="0b446-110">For details about hardware requirements for servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="0b446-111">Убедитесь, что сетевая инфраструктура соответствует требованиям.</span><span class="sxs-lookup"><span data-stu-id="0b446-111">Make sure that the networking infrastructure meets requirements.</span></span> <span data-ttu-id="0b446-112">Дополнительные сведения приведены в статье [требования к сетевой инфраструктуре для Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="0b446-112">For details, see [Network infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="0b446-113">Настройка доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0b446-113">Set up Active Directory Domain Services.</span></span> <span data-ttu-id="0b446-114">Для публикации и активации топологии необходимо, чтобы внутренние серверы были представлены учетными записями компьютеров в AD DS.</span><span class="sxs-lookup"><span data-stu-id="0b446-114">To publish and enable the topology, you need the internal servers to be represented by computer accounts in AD DS.</span></span> <span data-ttu-id="0b446-115">Этого можно достичь, присоединив компьютеры к AD DS.</span><span class="sxs-lookup"><span data-stu-id="0b446-115">This is accomplished by joining the computers to AD DS.</span></span> <span data-ttu-id="0b446-116">Сведения о подготовке AD DS приведены в статье [Подготовка доменных служб Active Directory для Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="0b446-116">For details about preparing AD DS, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

  - <span data-ttu-id="0b446-117">Создайте общий файловый ресурс.</span><span class="sxs-lookup"><span data-stu-id="0b446-117">Create a file share.</span></span> <span data-ttu-id="0b446-118">Серверы Standard Edition могут разместить общий файловый ресурс для требуемого файла, а в развертывании Enterprise файловый ресурс не может размещаться на интерфейсном сервере.</span><span class="sxs-lookup"><span data-stu-id="0b446-118">Standard Edition servers can host the file share for the required file, while in an Enterprise deployment the file share cannot be hosted on the front end server.</span></span> <span data-ttu-id="0b446-119">Разрешения и членство в группах, необходимое для развертывания и настройки списка управления доступом (ACL) для папки и общего ресурса должны быть правильно установлены, чтобы построитель топологии успешно завершил работу.</span><span class="sxs-lookup"><span data-stu-id="0b446-119">The permissions and group memberships required for deploying and setting the access control list (ACL) on the folder and the share must be set correctly for Topology Builder to complete successfully.</span></span> <span data-ttu-id="0b446-120">Необходимо убедиться, что у пользователя, выполняющего построитель топологий, есть следующие разрешения и членство в группах:</span><span class="sxs-lookup"><span data-stu-id="0b446-120">You should make sure that the person running Topology Builder has the following permissions and group memberships:</span></span>
    
      - <span data-ttu-id="0b446-121">Участник группы "Локальные администраторы"</span><span class="sxs-lookup"><span data-stu-id="0b446-121">Member of Local Administrators</span></span>
    
      - <span data-ttu-id="0b446-122">Участник группы "Пользователи домена"</span><span class="sxs-lookup"><span data-stu-id="0b446-122">Member of Domain Users</span></span>
    
      - <span data-ttu-id="0b446-123">Полный доступ к общему файловому ресурсу и папке файлового хранилища</span><span class="sxs-lookup"><span data-stu-id="0b446-123">Full Control on share and folder of file store</span></span>

  - <span data-ttu-id="0b446-p106">Для Enterprise Edition установите и настройте SQL Server. Для успешной установки SQL Server сервер на основе SQL Server должен быть доступен, а пользователь, который публикует топологию, должен быть локальным администратором на сервере SQL Server, а также должен быть членом группы SQL Server sysadmin на экземпляре SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0b446-p106">For Enterprise Edition, install and configure SQL Server. For SQL Server setup to succeed the SQL Server-based server must be online and the person publishing the topology be a local admin on the SQL Server and must be a member of the SQL Server sysadmin group on the SQL Server instance.</span></span>

<span data-ttu-id="0b446-126">После завершения всех задач подготовки, описанных в этом разделе, но перед публикацией топологии, также требуется выполнить другие задачи, в том числе установить операционные системы Windows и другое необходимое ПО, настроить службы IIS и DNS.</span><span class="sxs-lookup"><span data-stu-id="0b446-126">After you complete all of the preparation tasks as described in this topic, but prior to publishing the topology, you also need to perform the other preparation tasks, including installing the Windows operating systems and other prerequisite software, setting up IIS, and configuring DNS.</span></span> <span data-ttu-id="0b446-127">Сведения об этих задачах приведены в разделе [требования к системе для серверов, на которых работает Lync server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [Настройка служб IIS для Lync Server 2013](lync-server-2013-configure-iis.md)и [Подготовка инфраструктуры и систем для Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md).</span><span class="sxs-lookup"><span data-stu-id="0b446-127">For details about these tasks, see [System requirements for servers running Lync Server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [Configure IIS for Lync Server 2013](lync-server-2013-configure-iis.md), and [Preparing the infrastructure and systems for Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md).</span></span> <span data-ttu-id="0b446-128">Кроме того, ознакомьтесь с клиентами и требованиями к клиентам.</span><span class="sxs-lookup"><span data-stu-id="0b446-128">Additionally, you should familiarize yourself with the clients and client requirements.</span></span> <span data-ttu-id="0b446-129">Дополнительные сведения см. [в статье Deploy clients and Devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).</span><span class="sxs-lookup"><span data-stu-id="0b446-129">For details, see [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0b446-130">Содержание</span><span class="sxs-lookup"><span data-stu-id="0b446-130">In This Section</span></span>

  - [<span data-ttu-id="0b446-131">Настройка оборудования для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b446-131">Hardware setup for Lync Server 2013</span></span>](lync-server-2013-hardware-setup.md)

  - [<span data-ttu-id="0b446-132">Настройка программного обеспечения для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b446-132">Software setup for Lync Server 2013</span></span>](lync-server-2013-software-setup.md)

  - [<span data-ttu-id="0b446-133">Подготовка доменных служб Active Directory для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b446-133">Preparing Active Directory Domain Services for Lync Server 2013</span></span>](lync-server-2013-preparing-active-directory-domain-services.md)

  - [<span data-ttu-id="0b446-134">Настройка SQL Server для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b446-134">Configure SQL Server for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [<span data-ttu-id="0b446-135">Настройка DNS-записей в Lync Server 2013 для пула переднего плана или сервера Standard Edition</span><span class="sxs-lookup"><span data-stu-id="0b446-135">Configure DNS records in Lync Server 2013 for a Front End pool or Standard Edition server</span></span>](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [<span data-ttu-id="0b446-136">Установка средств администрирования Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b446-136">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

