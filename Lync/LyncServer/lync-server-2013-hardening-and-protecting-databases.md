---
title: 'Lync Server 2013: усиление защиты и защита баз данных'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting the databases of Lync Server 2013
ms:assetid: 6953e721-3511-4235-b848-51bab093dc89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518330(v=OCS.15)
ms:contentKeyID: 62625490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5473638169f4a171dbf48adb3e85d7ac8d7f37d8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214254"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-the-databases-of-lync-server-2013"></a><span data-ttu-id="d22af-102">Усиление защиты и защита баз данных Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d22af-102">Hardening and protecting the databases of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d22af-103">_**Последнее изменение темы:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="d22af-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="d22af-104">Microsoft Lync Server 2013 также зависит от баз данных SQL Server для хранения сведений о пользователях, состояния конференций, архивных данных и записей сведений о вызовах (CDRs).</span><span class="sxs-lookup"><span data-stu-id="d22af-104">Microsoft Lync Server 2013 also depends on SQL Server databases for storing user information, conference state, archiving data, and Call Detail Records (CDRs).</span></span> <span data-ttu-id="d22af-105">Вы можете максимально увеличить доступность данных Lync Server 2013 для серверных баз данных Lync Server путем секционирования данных приложения таким образом, чтобы повысить отказоустойчивость и упростить устранение неполадок.</span><span class="sxs-lookup"><span data-stu-id="d22af-105">You can maximize the availability of Lync Server 2013 data on Lync Server back-end databases, by partitioning the application data in a way that improves fault tolerance and simplifies troubleshooting.</span></span> <span data-ttu-id="d22af-106">Для достижения этих целей Разбейте данные приложения, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="d22af-106">To achieve these goals, partition the application data by:</span></span>

  - <span data-ttu-id="d22af-107">**Использование практических рекомендаций**   по разбиению на разделы сервера для разделения файлов операционной системы, приложений и программ из файлов данных.</span><span class="sxs-lookup"><span data-stu-id="d22af-107">**Using server partitioning best practices**   Separate your operating system, application, and program files from your data files.</span></span>

  - <span data-ttu-id="d22af-108">**Хранение файлов журнала транзакций и файлов**   базы данных в отдельном хранилище для повышения отказоустойчивости и оптимизации восстановления и их хранение на зашифрованном диске или томе.</span><span class="sxs-lookup"><span data-stu-id="d22af-108">**Storing transaction log files and database files**   Store these files separately to increase fault tolerance and optimize recovery, and store them on an encrypted disk or volume.</span></span>

  - <span data-ttu-id="d22af-109">**Использование кластера кластеров серверов**   фоновые серверы для оптимизации доступности системы Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d22af-109">**Using server clustering**   Cluster the back-end servers to optimize Lync Server 2013 system availability.</span></span>

  - <span data-ttu-id="d22af-110">**Убедитесь, что все резервные копии данных шифруются и правильно обрабатывают**   потерянные, отброшенные или неправильно размещенные носители резервных копий, могут представлять значительную угрозу безопасности данных для развертываний Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d22af-110">**Ensure that all data backups are encrypted and properly handled**   Lost, discarded, or misplaced backup media can pose a significant threat to data security for Lync Server 2013 deployments</span></span>

<span data-ttu-id="d22af-111">На любом сервере Lync Server 2013, кроме сервера Standard Edition, экземпляр SQL Server Express (экземпляр RTCLOCAL) недоступен для удаленного доступа, а исключения локального брандмауэра не создаются, за исключением SQL Server Express на сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="d22af-111">On any Lync Server 2013 server except Standard Edition server, the SQL Server Express instance (RTCLOCAL instance) is not remotely accessible, and no local firewall exceptions are created, except for SQL Server Express on a Standard Edition server.</span></span> <span data-ttu-id="d22af-112">На сервере Standard Edition для удаленного доступа к серверной базе данных и центральному хранилищу управления (CMS) можно использовать удаленный доступ.</span><span class="sxs-lookup"><span data-stu-id="d22af-112">On a Standard Edition server, both the back-end database and the Central Management store (CMS) are set up to be remotely accessible.</span></span> <span data-ttu-id="d22af-113">Для защиты баз данных SQL Server можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="d22af-113">To harden SQL Server databases, you can do the following:</span></span>

  - <span data-ttu-id="d22af-114">Настройте брандмауэр SQL Server Express на серверах Standard Edition, ограничивая область серверов, которые могут осуществлять удаленный доступ к базе данных.</span><span class="sxs-lookup"><span data-stu-id="d22af-114">Customize the SQL Server Express firewall on Standard Edition servers, limiting the scope of servers that can remotely access the database.</span></span> <span data-ttu-id="d22af-115">По умолчанию любой IP-адрес может получить удаленный доступ к базе данных.</span><span class="sxs-lookup"><span data-stu-id="d22af-115">By default, any IP address can remotely access the database.</span></span>

  - <span data-ttu-id="d22af-116">С помощью диспетчера конфигураций SQL Server укажите протоколы, IP-адреса и порты для удаленного доступа SQL Server:</span><span class="sxs-lookup"><span data-stu-id="d22af-116">Use SQL Server Configuration Manager to specify the protocols, IP addresses, and ports for SQL Server remote access:</span></span>
    
      - <span data-ttu-id="d22af-117">Lync Server 2013 использует протокол TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="d22af-117">Lync Server 2013 uses the TCP/IP protocol.</span></span> <span data-ttu-id="d22af-118">Он поддерживает протокол IP версии 4 (IPv4), но не IP версии 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="d22af-118">It supports IP version 4 (IPv4), but not IP version 6 (IPv6).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="d22af-119">Lync Server 2013 может работать в сети с включенным двойным стеком IP.</span><span class="sxs-lookup"><span data-stu-id="d22af-119">Lync Server 2013 can function in a network with dual IP stack enabled.</span></span>

        
        </div>
    
      - <span data-ttu-id="d22af-120">Lync Server 2013 поддерживает несколько IP-адресов (сетевых карт с несколькими сетевыми адресами).</span><span class="sxs-lookup"><span data-stu-id="d22af-120">Lync Server 2013 supports multiple IP address (multi-homed network address cards).</span></span> <span data-ttu-id="d22af-121">Можно указать, что SQL Server прослушивает только определенные IP-адреса (индивидуальный адрес или подсеть) и используют только определенные протоколы.</span><span class="sxs-lookup"><span data-stu-id="d22af-121">You can specify that SQL Server listen only to specific IP addresses (individual address or by subnet) and only use specific protocols.</span></span>
    
      - <span data-ttu-id="d22af-122">Lync Server 2013 поддерживает статические и динамические порты SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d22af-122">Lync Server 2013 supports static and dynamic SQL Server ports.</span></span>

  - <span data-ttu-id="d22af-123">Запустите SQL Server на статическом (не по умолчанию) порту и не запускайте браузер SQL Server (поэтому он не может сообщить прослушивающий порт клиенту).</span><span class="sxs-lookup"><span data-stu-id="d22af-123">Run SQL Server on a static (non-default) port, and do not run SQL Server Browser (so it cannot report the listening port to the client).</span></span> <span data-ttu-id="d22af-124">Для этого требуется настраиваемая конфигурация для каждого клиента SQL Server, включая серверы переднего плана, сервер мониторинга, сервер архивации и консоль администрирования (с помощью Командная консоль Lync Server, панель управления Lync Server или построитель топологий), а также все остальные серверы, на которых выполняются базы данных Lync Server).</span><span class="sxs-lookup"><span data-stu-id="d22af-124">This requires a custom configuration on each SQL Server client, including Front End Servers, Monitoring Server, Archiving Server, and administrative consoles (running Lync Server Management Shell, Lync Server Control Panel, or Topology Builder), and all other servers running Lync Server databases).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d22af-125">Доступ к базам данных должен быть ограничен только доверенными администраторами баз данных.</span><span class="sxs-lookup"><span data-stu-id="d22af-125">Access to databases must be limited to trusted database administrators.</span></span> <span data-ttu-id="d22af-126">Злонамеренный администратор базы данных может вставлять или изменять данные в базах данных для получения доступа к серверам Lync Server 2013 или получения конфиденциальной информации от служб, даже если администратору базы данных не предоставлен прямой доступ или Управление серверами Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d22af-126">A malicious database administrator could insert or modify data into the databases to acquire privileges over the Lync Server 2013 servers or obtain sensitive information from the services, even if the database administrator has not been granted direct access or control of the Lync Server 2013 servers.</span></span>



</div>

<span data-ttu-id="d22af-127">Для получения подробных сведений о настраиваемых конфигурациях и усилении безопасности баз данных SQL Server ознакомьтесь со статьей "Использование Lync Server 2010 с настраиваемой конфигурацией сети [https://go.microsoft.com/fwlink/p/?LinkId=214008](https://go.microsoft.com/fwlink/p/?linkid=214008)SQL Server" в блоге.</span><span class="sxs-lookup"><span data-stu-id="d22af-127">For details about custom configurations and hardening SQL Server databases, see the NextHop blog article, "Using Lync Server 2010 with a Custom SQL Server Network Configuration," at [https://go.microsoft.com/fwlink/p/?LinkId=214008](https://go.microsoft.com/fwlink/p/?linkid=214008).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d22af-128">Кроме того, можно зафиксировать операционные системы и серверы приложений, а также использовать групповую политику для реализации блокирования безопасности в развертывании Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d22af-128">You can also harden operating systems and applications servers, and you can use Group Policy to implement security lockdowns in your Lync Server deployment.</span></span> <span data-ttu-id="d22af-129">Дополнительные сведения: <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">усиление защиты и защита серверов и приложений для Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d22af-129">For details, see <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">Hardening and protecting servers and applications for Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

