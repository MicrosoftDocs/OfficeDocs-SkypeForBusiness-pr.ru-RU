---
title: 'Lync Server 2013: обзор процесса резервного копирования и восстановления'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration process overview
ms:assetid: e0f23b21-070f-4df5-b795-cea2f5338d85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202192(v=OCS.15)
ms:contentKeyID: 51541524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd6efce509283d59c5cecc7325c35c9cf1ab371e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187082"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-process-overview-for-lync-server-2013"></a><span data-ttu-id="88e93-102">Общие сведения о процессе резервного копирования и восстановления для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88e93-102">Backup and restoration process overview for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88e93-103">_**Последнее изменение темы:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="88e93-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="88e93-104">В этом разделе представлены общие сведения о том, как процесс резервного копирования и восстановления работает для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88e93-104">This section provides an overview of how the backup and restoration process works for Lync Server 2013.</span></span> <span data-ttu-id="88e93-105">Вы используете один и тот же процесс для всех серверов Standard Edition и серверов Enterprise Edition, независимо от их местонахождения.</span><span class="sxs-lookup"><span data-stu-id="88e93-105">You use the same process for all Standard Edition servers and Enterprise Edition servers, regardless of their location.</span></span>

<span data-ttu-id="88e93-106">Как правило, процесс резервного копирования работает следующим образом:</span><span class="sxs-lookup"><span data-stu-id="88e93-106">In general, the backup process works as follows:</span></span>

  - <span data-ttu-id="88e93-107">Расположение резервной копии создается как общая папка на автономном компьютере, не входящем в пул.</span><span class="sxs-lookup"><span data-stu-id="88e93-107">You create a backup location as a shared folder on a stand-alone computer that is not part of any pool.</span></span> <span data-ttu-id="88e93-108">Ссылка на расположение резервной копии содержится в **$BACKUP**.</span><span class="sxs-lookup"><span data-stu-id="88e93-108">The location of the backup is referenced in **$Backup**.</span></span>

  - <span data-ttu-id="88e93-109">Регулярное резервное копирование всех баз данных Lync Server и всех хранилищ файлов, описанных в статье [требования к резервному копированию и восстановлению в Lync server 2013: Data](lync-server-2013-backup-and-restoration-requirements-data.md) , с помощью процедур, описанных в статье [резервное копирование Lync Server 2013](lync-server-2013-backing-up-lync-server.md) , включает в себя все параметры и конфигурации сервера.</span><span class="sxs-lookup"><span data-stu-id="88e93-109">On a regular, scheduled basis, you back up all the Lync Server databases and all the file stores that are described in [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md) by following the procedures described in [Backing up Lync Server 2013](lync-server-2013-backing-up-lync-server.md) The Central Management store includes all the server settings and configurations.</span></span>

  - <span data-ttu-id="88e93-110">Каждый раз при выполнении последующего резервного копирования создается новая общая папка и изменяется путь, **$BACKUP** ссылки.</span><span class="sxs-lookup"><span data-stu-id="88e93-110">Each time you run a subsequent backup, you create a new shared folder and change the path that **$Backup** references.</span></span>

<span data-ttu-id="88e93-111">В общем случае процесс восстановления работает следующим образом:</span><span class="sxs-lookup"><span data-stu-id="88e93-111">In general, the restoration process works as follows:</span></span>

  - <span data-ttu-id="88e93-112">При возникновении сбоя или сбоя восстанавливаются данные в расположении, на которые ссылаются **$BACKUP** на новые или чистые компьютеры.</span><span class="sxs-lookup"><span data-stu-id="88e93-112">When a failure or outage occurs, you restore the data in the location referenced by **$Backup** to new or clean computers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="88e93-113">Этот процесс восстановления не восстанавливает данные на существующем состоянии сервера.</span><span class="sxs-lookup"><span data-stu-id="88e93-113">This restoration process does not restore data onto an existing server state.</span></span> <span data-ttu-id="88e93-114">То есть этот процесс требует, чтобы сервер был нечетким или новым.</span><span class="sxs-lookup"><span data-stu-id="88e93-114">That is, this process requires that the server is clean or new.</span></span>

    
    </div>

  - <span data-ttu-id="88e93-115">Чтобы обеспечить возможность восстановления сведений о пользователях и конференциях до точки сбоя, можно реализовать топологию аварийного восстановления с подключенными пулами переднего плана, как описано в статье [Планирование обеспечения высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="88e93-115">To enable your user and conference information to be recoverable to the point of failure, you can implement a disaster recovery topology with paired Front End pools, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

  - <span data-ttu-id="88e93-116">Все настройки системы доменных имен (DNS), конфигурации протокола DHCP, доменных имен, полных доменных имен компьютера (FQDN), путей к хранилищу файлов и т. д. должны быть одинаковы во время выполнения восстановления. Подавай назад.</span><span class="sxs-lookup"><span data-stu-id="88e93-116">All Domain Name System (DNS) configuration, Dynamic Host Configuration Protocol (DHCP) configuration, domain names, computer fully qualified domain names (FQDNs), file store paths, and so on must be the same at the time of restoration that they were at the time of back up.</span></span>

<span data-ttu-id="88e93-117">Если сервер, на котором работает Lync Server, завершается с ошибкой, восстановление включает в себя следующие этапы:</span><span class="sxs-lookup"><span data-stu-id="88e93-117">If a server running Lync Server fails, recovery includes the following steps:</span></span>

  - <span data-ttu-id="88e93-118">Установите операционную систему на новом или чистом компьютере с таким же полным доменным именем, как и у неисправного компьютера.</span><span class="sxs-lookup"><span data-stu-id="88e93-118">Install the operating system on a new or clean computer with the same FQDN as the failed computer.</span></span>

  - <span data-ttu-id="88e93-119">Переустановите сертификаты.</span><span class="sxs-lookup"><span data-stu-id="88e93-119">Reinstall certificates.</span></span>

  - <span data-ttu-id="88e93-120">Если сервер размещает базу данных, установите Microsoft SQL Server 2012 или Microsoft SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="88e93-120">If the server hosted a database, install Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2.</span></span>

  - <span data-ttu-id="88e93-121">Как правило, если сервер размещает базу данных, запустите построитель топологий, чтобы создать и установить базу данных и настроить списки управления доступом (ACL).</span><span class="sxs-lookup"><span data-stu-id="88e93-121">In general, if the server hosted a database, run Topology Builder to create and install the database and set up access control lists (ACLs).</span></span>

  - <span data-ttu-id="88e93-122">Как правило, если сервер размещает роль сервера, выполните шаг 1 с шагом 4 из мастера развертывания Lync Server, чтобы установить локальные файлы конфигурации, установить компоненты роли сервера, назначить сертификаты и запустить службы.</span><span class="sxs-lookup"><span data-stu-id="88e93-122">In general, if the server hosted a server role, run step 1 through step 4 of the Lync Server Deployment Wizard to install the local configuration files, install the server role components, assign certificates, and start the services.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="88e93-123">Если сервер, на котором размещена база данных, сопоставленная с ролью сервера, при выполнении шага 2 мастера развертывания Lync Server повторно создаст базу данных.</span><span class="sxs-lookup"><span data-stu-id="88e93-123">If the server hosted a database collocated with the server role, running step 2 of the Lync Server Deployment Wizard recreates the database.</span></span>

    
    </div>

  - <span data-ttu-id="88e93-124">Если сервер размещает базу данных, Восстановите резервные копии данных.</span><span class="sxs-lookup"><span data-stu-id="88e93-124">If the server hosted a database, restore the backed up data.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

