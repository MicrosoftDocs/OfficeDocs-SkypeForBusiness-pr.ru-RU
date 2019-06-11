---
title: 'Lync Server 2013: усиление защиты и защита баз данных'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hardening and protecting the databases of Lync Server 2013
ms:assetid: 6953e721-3511-4235-b848-51bab093dc89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518330(v=OCS.15)
ms:contentKeyID: 62625490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 265ca1058b4f3b41c5f0dbc4c5b2cdcd631fa911
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834093"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-the-databases-of-lync-server-2013"></a><span data-ttu-id="cafbd-102">Усиление защиты и защита баз данных Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cafbd-102">Hardening and protecting the databases of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cafbd-103">_**Тема последнего изменения:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="cafbd-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="cafbd-104">Microsoft Lync Server 2013 также зависит от баз данных SQL Server для хранения сведений о пользователях, состояния конференций, архивации данных и записей о вызовах (Кдрс).</span><span class="sxs-lookup"><span data-stu-id="cafbd-104">Microsoft Lync Server 2013 also depends on SQL Server databases for storing user information, conference state, archiving data, and Call Detail Records (CDRs).</span></span> <span data-ttu-id="cafbd-105">Вы можете максимально увеличить доступность данных Lync Server 2013 на серверных базах данных Lync Server, разбить данные приложения таким образом, чтобы повысить устойчивость к сбоям и упростить устранение неполадок.</span><span class="sxs-lookup"><span data-stu-id="cafbd-105">You can maximize the availability of Lync Server 2013 data on Lync Server back-end databases, by partitioning the application data in a way that improves fault tolerance and simplifies troubleshooting.</span></span> <span data-ttu-id="cafbd-106">Для достижения этих целей Разбейте данные приложения, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="cafbd-106">To achieve these goals, partition the application data by:</span></span>

  - <span data-ttu-id="cafbd-107">**Использование**   рекомендаций по использованию разделов на серверах: файлы данных операционной системы, приложения и программы отдельно разделяются.</span><span class="sxs-lookup"><span data-stu-id="cafbd-107">**Using server partitioning best practices**   Separate your operating system, application, and program files from your data files.</span></span>

  - <span data-ttu-id="cafbd-108">**Хранение файлов журнала транзакций и файлов**   базы данных. Эти файлы хранятся отдельно для повышения отказоустойчивости и оптимизации восстановления и сохранения их на зашифрованном диске или томе.</span><span class="sxs-lookup"><span data-stu-id="cafbd-108">**Storing transaction log files and database files**   Store these files separately to increase fault tolerance and optimize recovery, and store them on an encrypted disk or volume.</span></span>

  - <span data-ttu-id="cafbd-109">**С помощью**   кластеров серверов кластеризация на внутреннем сервере Оптимизируйте доступность системы Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cafbd-109">**Using server clustering**   Cluster the back-end servers to optimize Lync Server 2013 system availability.</span></span>

  - <span data-ttu-id="cafbd-110">**Убедитесь, что все резервные копии данных зашифрованы и правильно обрабатывают**   потерянные, отброшенные или неправильно расположенные носители резервных копий могут значительно защитить данные для развертывания Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cafbd-110">**Ensure that all data backups are encrypted and properly handled**   Lost, discarded, or misplaced backup media can pose a significant threat to data security for Lync Server 2013 deployments</span></span>

<span data-ttu-id="cafbd-111">На любом сервере Lync Server 2013, кроме сервера Standard Edition, экземпляр SQL Server Express (экземпляр РТКЛОКАЛ) не доступен для удаленного доступа, кроме случаев, когда SQL Server Express на сервере Standard Edition не создает никаких локальных исключений брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="cafbd-111">On any Lync Server 2013 server except Standard Edition server, the SQL Server Express instance (RTCLOCAL instance) is not remotely accessible, and no local firewall exceptions are created, except for SQL Server Express on a Standard Edition server.</span></span> <span data-ttu-id="cafbd-112">На сервере Standard Edition серверная база данных и хранилище Центрального управления (CMS) настроены для удаленного доступа.</span><span class="sxs-lookup"><span data-stu-id="cafbd-112">On a Standard Edition server, both the back-end database and the Central Management store (CMS) are set up to be remotely accessible.</span></span> <span data-ttu-id="cafbd-113">Для защиты баз данных SQL Server вы можете сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="cafbd-113">To harden SQL Server databases, you can do the following:</span></span>

  - <span data-ttu-id="cafbd-114">Настройте брандмауэр SQL Server Express на серверах Standard Edition, ограничивая диапазон серверов, которые могут удаленно получать доступ к базе данных.</span><span class="sxs-lookup"><span data-stu-id="cafbd-114">Customize the SQL Server Express firewall on Standard Edition servers, limiting the scope of servers that can remotely access the database.</span></span> <span data-ttu-id="cafbd-115">По умолчанию любой IP-адрес может удаленно получить доступ к базе данных.</span><span class="sxs-lookup"><span data-stu-id="cafbd-115">By default, any IP address can remotely access the database.</span></span>

  - <span data-ttu-id="cafbd-116">С помощью диспетчера конфигурации SQL Server можно задать протоколы, IP-адреса и порты для удаленного доступа SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cafbd-116">Use SQL Server Configuration Manager to specify the protocols, IP addresses, and ports for SQL Server remote access:</span></span>
    
      - <span data-ttu-id="cafbd-117">Lync Server 2013 использует протокол TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="cafbd-117">Lync Server 2013 uses the TCP/IP protocol.</span></span> <span data-ttu-id="cafbd-118">Она поддерживает протокол IP версии 4 (IPv4), но не IP версии 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="cafbd-118">It supports IP version 4 (IPv4), but not IP version 6 (IPv6).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="cafbd-119">Lync Server 2013 может работать в сети с поддержкой двух стеков IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="cafbd-119">Lync Server 2013 can function in a network with dual IP stack enabled.</span></span>

        
        </div>
    
      - <span data-ttu-id="cafbd-120">Lync Server 2013 поддерживает несколько IP-адресов (сетевых адресных карт с несколькими сетевыми интерфейсами).</span><span class="sxs-lookup"><span data-stu-id="cafbd-120">Lync Server 2013 supports multiple IP address (multi-homed network address cards).</span></span> <span data-ttu-id="cafbd-121">Вы можете указать, что SQL Server должен прослушивать только определенные IP-адреса (индивидуальный адрес или подсеть) и использовать только определенные протоколы.</span><span class="sxs-lookup"><span data-stu-id="cafbd-121">You can specify that SQL Server listen only to specific IP addresses (individual address or by subnet) and only use specific protocols.</span></span>
    
      - <span data-ttu-id="cafbd-122">Lync Server 2013 поддерживает статические и динамические порты SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cafbd-122">Lync Server 2013 supports static and dynamic SQL Server ports.</span></span>

  - <span data-ttu-id="cafbd-123">Запустите SQL Server на статическом порту (не по умолчанию) и не запускайте браузер SQL Server (поэтому он не может сообщить о порте прослушивания клиенту).</span><span class="sxs-lookup"><span data-stu-id="cafbd-123">Run SQL Server on a static (non-default) port, and do not run SQL Server Browser (so it cannot report the listening port to the client).</span></span> <span data-ttu-id="cafbd-124">Для этого требуется настраиваемая конфигурация для каждого клиента SQL Server, включая серверы переднего плана, сервер мониторинга, сервер архивации и консоль администрирования (с помощью командной консоли Lync Server Management Shell, панель управления Lync Server или построитель топологии), а также все остальные серверы с запущенными базами данных Lync Server).</span><span class="sxs-lookup"><span data-stu-id="cafbd-124">This requires a custom configuration on each SQL Server client, including Front End Servers, Monitoring Server, Archiving Server, and administrative consoles (running Lync Server Management Shell, Lync Server Control Panel, or Topology Builder), and all other servers running Lync Server databases).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cafbd-125">Доступ к базам данных должен быть ограничен администраторами доверенных баз данных.</span><span class="sxs-lookup"><span data-stu-id="cafbd-125">Access to databases must be limited to trusted database administrators.</span></span> <span data-ttu-id="cafbd-126">Злоумышленник может добавить или изменить данные в базе данных, чтобы получить доступ к данным на серверах Lync Server 2013 или получить конфиденциальную информацию от служб, даже если администратору базы данных не предоставлен прямой доступ или Управление серверами Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cafbd-126">A malicious database administrator could insert or modify data into the databases to acquire privileges over the Lync Server 2013 servers or obtain sensitive information from the services, even if the database administrator has not been granted direct access or control of the Lync Server 2013 servers.</span></span>



</div>

<span data-ttu-id="cafbd-127">Сведения о настраиваемых конфигурациях и усилении защиты баз данных SQL Server можно найти в статье блога для NextHop: "Использование Lync Server 2010 с настраиваемой сетевой конфигурацией [http://go.microsoft.com/fwlink/p/?LinkId=214008](http://go.microsoft.com/fwlink/p/?linkid=214008)SQL Server".</span><span class="sxs-lookup"><span data-stu-id="cafbd-127">For details about custom configurations and hardening SQL Server databases, see the NextHop blog article, "Using Lync Server 2010 with a Custom SQL Server Network Configuration," at [http://go.microsoft.com/fwlink/p/?LinkId=214008](http://go.microsoft.com/fwlink/p/?linkid=214008).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cafbd-128">Вы также можете зафиксировать операционные системы и серверы приложений, а также использовать групповую политику для реализации блокировки безопасности в развертывании Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cafbd-128">You can also harden operating systems and applications servers, and you can use Group Policy to implement security lockdowns in your Lync Server deployment.</span></span> <span data-ttu-id="cafbd-129">Подробные сведения можно найти в разделе <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">Защита серверов и приложений для Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="cafbd-129">For details, see <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">Hardening and protecting servers and applications for Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

