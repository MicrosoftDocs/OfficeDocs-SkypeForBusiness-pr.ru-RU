---
title: 'Lync Server 2013: Настройка оборудования'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware setup
ms:assetid: 37a9f295-cde3-4beb-9a6a-2580082798ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425852(v=OCS.15)
ms:contentKeyID: 48183834
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d55ac04a06984889a3038aceee7fd0f311efcfb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138020"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hardware-setup-for-lync-server-2013"></a><span data-ttu-id="36581-102">Настройка оборудования для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36581-102">Hardware setup for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36581-103">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="36581-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="36581-104">Для настройки оборудования и других компонентов, необходимых для реализации топологии, необходимо, прежде чем опубликовать топологию в построителе топологий, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="36581-104">Setting up the hardware and other components required in the infrastructure that you need to implement your topology requires that, prior to publishing your topology in Topology Builder, you do the following:</span></span>

  - <span data-ttu-id="36581-105">Установите оборудование для каждого компонента в структуре топологии, созданной и сохраненной с помощью построителя топологий, включая все необходимые компьютеры (серверы, на которых работает Lync Server 2013, серверы баз данных, серверы служб IIS и обратные прокси-серверы (при необходимости), сетевые адаптеры, аппаратные средства балансировки нагрузки и устройства хранения (например, файловые серверы).</span><span class="sxs-lookup"><span data-stu-id="36581-105">Install the hardware for each component in the topology design that you created and saved by using Topology Builder, including all required computers (servers running Lync Server 2013, database servers, servers running Internet Information Services (IIS), and reverse proxy servers, as appropriate), network adapters, hardware load balancers, and storage devices (such as file servers).</span></span> <span data-ttu-id="36581-106">Убедитесь в том, что выполнены рекомендации по числу и производительности сетевых адаптеров.</span><span class="sxs-lookup"><span data-stu-id="36581-106">Confirm that you have followed the recommendations for the number and speed for network adapters.</span></span> <span data-ttu-id="36581-107">Если вы будете использовать аппаратные средства балансировки нагрузки, убедитесь, что у вас есть соответствующие сведения у поставщика, чтобы настроить их для использования с Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="36581-107">If you will be using hardware load balancers, make sure that you have the proper information from the vendor to configure them for use with Lync Server 2013.</span></span> <span data-ttu-id="36581-108">Если вы планируете использовать файловый сервер или другой сервер для размещения общего файлового ресурса, необходимого для Lync Server, убедитесь, что сервер доступен и готов к настройке общего файлового ресурса.</span><span class="sxs-lookup"><span data-stu-id="36581-108">If you will be using a file server or other server to house the file share required by Lync Server, make sure that the server is available and ready for the configuration of the file share.</span></span> <span data-ttu-id="36581-109">Сведения об определении топологии, указывающей компоненты, необходимые для развертывания, приведены [в статье определение и Настройка топологии в Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="36581-109">For details about how to define a topology that specifies the components needed for your deployment, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span> <span data-ttu-id="36581-110">Для получения дополнительных сведений о требованиях к оборудованию для серверов ознакомьтесь со статьей [Supported Hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="36581-110">For details about hardware requirements for servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="36581-111">Убедитесь, что сетевая инфраструктура соответствует требованиям.</span><span class="sxs-lookup"><span data-stu-id="36581-111">Make sure that the networking infrastructure meets requirements.</span></span> <span data-ttu-id="36581-112">Дополнительные сведения приведены в статье [требования к сетевой инфраструктуре для Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="36581-112">For details, see [Network infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="36581-113">Настройка доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="36581-113">Set up Active Directory Domain Services.</span></span> <span data-ttu-id="36581-114">Настройка доменных служб Active Directory включает их подготовку и определение всех компонентов, которые вы хотите развернуть в них.</span><span class="sxs-lookup"><span data-stu-id="36581-114">Setting up AD DS includes preparing AD DS and defining all components that you want to deploy in AD DS.</span></span> <span data-ttu-id="36581-115">Сведения о подготовке AD DS приведены в статье [Подготовка доменных служб Active Directory для Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="36581-115">For details about preparing AD DS, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="36581-116">Настройте необходимые разрешения для создания общего файлового ресурса.</span><span class="sxs-lookup"><span data-stu-id="36581-116">Set up the required permissions for creating the file share.</span></span> <span data-ttu-id="36581-117">Разрешения на использование файлов общего доступа в Lync Server 2013 автоматически настраиваются построителем топологий при публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="36581-117">Permissions for use of file shares by Lync Server 2013 are automatically configured by Topology Builder when you publish your topology.</span></span> <span data-ttu-id="36581-118">Тем не менее, учетная запись пользователя, используемая для публикации топологии, должна иметь полный доступ (чтение, запись и изменение) к общему файловому ресурсу, чтобы построитель топологий мог настроить необходимые разрешения.</span><span class="sxs-lookup"><span data-stu-id="36581-118">However, the user account used to publish the topology must have full control (read/write/modify) on the file share in order for Topology Builder to configure the required permissions.</span></span> <span data-ttu-id="36581-119">Чтобы обеспечить правильную управляемость общего файлового ресурса во время публикации построителя топологий, пользователь или группа домена, участником которой является пользователь, должны быть членами локальной группы администраторов на компьютере, где находится файловый ресурс.</span><span class="sxs-lookup"><span data-stu-id="36581-119">To make sure that the file share can be managed properly during the Topology Builder publishing process, the user or domain group that the user is a member of should be made a member of the local Administrators group on the machine where the file share is located.</span></span> <span data-ttu-id="36581-120">В сценарии с несколькими доменами пользователя или группу в домене А следует добавить в группу локальных администраторов на компьютере в домене Б, на котором будет размещен общий файловый ресурс.</span><span class="sxs-lookup"><span data-stu-id="36581-120">In a multi-domain scenario, Domain A user or group should be made a member of the local Administrators group on the machine in Domain B where the file share will be located.</span></span>
    
    <span data-ttu-id="36581-121">Сведения об обновлении с использованием общих файловых ресурсов в распределенной файловой системе (DFS) можно найти в статье [Настройка хранилища файлов для Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span><span class="sxs-lookup"><span data-stu-id="36581-121">For details about updating using file shares in a Distributed File System (DFS), see [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="36581-122">Файловый ресурс для Lync Server 2013, Enterprise Edition не может находиться на сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="36581-122">The file share for Lync Server 2013, Enterprise Edition cannot be located on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="36581-123">Установите и настройте аппаратную подсистему балансировки нагрузки для веб-служб.</span><span class="sxs-lookup"><span data-stu-id="36581-123">Install and set up the hardware load balancer for Web Services.</span></span> <span data-ttu-id="36581-124">Если развернута балансировка нагрузки на DNS, вам по-прежнему необходимо использовать аппаратные балансировщики нагрузки для этих пулов, но только для трафика HTTP/HTTPS.</span><span class="sxs-lookup"><span data-stu-id="36581-124">With Domain Name System (DNS) load balancing deployed, you still need to also use hardware load balancers for these pools, but only for HTTP/HTTPS traffic.</span></span> <span data-ttu-id="36581-125">Аппаратный балансировщик нагрузки используется для трафика HTTPS, передаваемого из клиентов через порты 443 и 80.</span><span class="sxs-lookup"><span data-stu-id="36581-125">The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span> <span data-ttu-id="36581-126">Хотя потребность в аппаратных балансировщиках нагрузки для этих пулов не устраняется, их настройка и администрирование осуществляется в первую очередь применительно к трафику HTTP и HTTPS, с чем их администраторы хорошо знакомы.</span><span class="sxs-lookup"><span data-stu-id="36581-126">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTP/HTTPS traffic, which the administrators of the hardware load balancers are accustomed to.</span></span>

<span data-ttu-id="36581-127">Завершив все подготовительные действия, описанные в этом разделе, выполните также следующие задачи перед публикацией топологии.</span><span class="sxs-lookup"><span data-stu-id="36581-127">After you complete all of the preparation tasks as described in this topic, but prior to publishing the topology, you also need to:</span></span>

  - [<span data-ttu-id="36581-128">Установка операционных систем и необходимого программного обеспечения на серверы для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36581-128">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [<span data-ttu-id="36581-129">Настройка служб IIS для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36581-129">Configure IIS for Lync Server 2013</span></span>](lync-server-2013-configure-iis.md)

  - [<span data-ttu-id="36581-130">Настройка SQL Server для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36581-130">Configure SQL Server for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [<span data-ttu-id="36581-131">Настройка DNS-записей в Lync Server 2013 для пула переднего плана или сервера Standard Edition</span><span class="sxs-lookup"><span data-stu-id="36581-131">Configure DNS records in Lync Server 2013 for a Front End pool or Standard Edition server</span></span>](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

