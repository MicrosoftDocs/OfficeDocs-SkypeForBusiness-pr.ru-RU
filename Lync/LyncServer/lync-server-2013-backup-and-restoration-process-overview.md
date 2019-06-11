---
title: 'Lync Server 2013: Общие сведения о процессе резервного копирования и восстановления'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backup and restoration process overview
ms:assetid: e0f23b21-070f-4df5-b795-cea2f5338d85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202192(v=OCS.15)
ms:contentKeyID: 51541524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b01230e84c9278d5540c21d41d9af1342479e6a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841887"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-process-overview-for-lync-server-2013"></a><span data-ttu-id="1b76b-102">Обзор процесса резервного копирования и восстановления для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b76b-102">Backup and restoration process overview for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b76b-103">_**Тема последнего изменения:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="1b76b-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="1b76b-104">В этом разделе приводятся общие сведения о том, как выполняется резервное копирование и восстановление для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1b76b-104">This section provides an overview of how the backup and restoration process works for Lync Server 2013.</span></span> <span data-ttu-id="1b76b-105">Вы используете один и тот же процесс для всех серверов стандартных выпусков и серверов выпуска Enterprise Edition, независимо от того, где они находятся.</span><span class="sxs-lookup"><span data-stu-id="1b76b-105">You use the same process for all Standard Edition servers and Enterprise Edition servers, regardless of their location.</span></span>

<span data-ttu-id="1b76b-106">Как правило, процесс резервного копирования выполняется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1b76b-106">In general, the backup process works as follows:</span></span>

  - <span data-ttu-id="1b76b-107">Расположение резервной копии создается как общая папка на отдельном компьютере, который не входит ни в один пул.</span><span class="sxs-lookup"><span data-stu-id="1b76b-107">You create a backup location as a shared folder on a stand-alone computer that is not part of any pool.</span></span> <span data-ttu-id="1b76b-108">Ссылка на расположение резервной копии содержится в **$BACKUP**.</span><span class="sxs-lookup"><span data-stu-id="1b76b-108">The location of the backup is referenced in **$Backup**.</span></span>

  - <span data-ttu-id="1b76b-109">Регулярно заархивированные базы данных Lync Server и все хранилища файлов, описанные в статье [требования к резервному копированию и восстановлению в Lync server 2013: данные](lync-server-2013-backup-and-restoration-requirements-data.md) , выполнив действия, описанные в статье Создание резервной копии [Lync Server 2013 ](lync-server-2013-backing-up-lync-server.md)В хранилище Central Management входят все параметры и конфигурации сервера.</span><span class="sxs-lookup"><span data-stu-id="1b76b-109">On a regular, scheduled basis, you back up all the Lync Server databases and all the file stores that are described in [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md) by following the procedures described in [Backing up Lync Server 2013](lync-server-2013-backing-up-lync-server.md) The Central Management store includes all the server settings and configurations.</span></span>

  - <span data-ttu-id="1b76b-110">Каждый раз, когда вы запускаете последующую архивацию, вы создаете новую общую папку и изменяете путь, который **$BACKUP** ссылок.</span><span class="sxs-lookup"><span data-stu-id="1b76b-110">Each time you run a subsequent backup, you create a new shared folder and change the path that **$Backup** references.</span></span>

<span data-ttu-id="1b76b-111">Как правило, процесс восстановления выполняется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1b76b-111">In general, the restoration process works as follows:</span></span>

  - <span data-ttu-id="1b76b-112">При возникновении ошибки или сбоя вы восстанавливаете данные в расположении, на которое ссылается **$BACKUP** , на новые или чистые компьютеры.</span><span class="sxs-lookup"><span data-stu-id="1b76b-112">When a failure or outage occurs, you restore the data in the location referenced by **$Backup** to new or clean computers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1b76b-113">Этот процесс восстановления не восстанавливает данные на существующем состоянии сервера.</span><span class="sxs-lookup"><span data-stu-id="1b76b-113">This restoration process does not restore data onto an existing server state.</span></span> <span data-ttu-id="1b76b-114">Это значит, что для этого процесса требуется, чтобы сервер был чистым или новым.</span><span class="sxs-lookup"><span data-stu-id="1b76b-114">That is, this process requires that the server is clean or new.</span></span>

    
    </div>

  - <span data-ttu-id="1b76b-115">Чтобы обеспечить возможность восстановления сведений о пользователях и конференциях в точке сбоя, вы можете реализовать топологию аварийной проверки с помощью связанных пулов переднего плана, как описано в разделе [Планирование обеспечения высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="1b76b-115">To enable your user and conference information to be recoverable to the point of failure, you can implement a disaster recovery topology with paired Front End pools, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

  - <span data-ttu-id="1b76b-116">Все конфигурации системы доменных имен (DNS), конфигурации протокола DHCP, доменных имен, полных доменных имен, путей к файлам и т. д. должны быть одинаковыми на момент восстановления Подавай назад.</span><span class="sxs-lookup"><span data-stu-id="1b76b-116">All Domain Name System (DNS) configuration, Dynamic Host Configuration Protocol (DHCP) configuration, domain names, computer fully qualified domain names (FQDNs), file store paths, and so on must be the same at the time of restoration that they were at the time of back up.</span></span>

<span data-ttu-id="1b76b-117">Если сервер, на котором работает Lync Server, не проходит, восстановление включает в себя следующие шаги:</span><span class="sxs-lookup"><span data-stu-id="1b76b-117">If a server running Lync Server fails, recovery includes the following steps:</span></span>

  - <span data-ttu-id="1b76b-118">Установите операционную систему на новом компьютере или удалите его с полным доменным именем, совпадающим с неисправной компьютером.</span><span class="sxs-lookup"><span data-stu-id="1b76b-118">Install the operating system on a new or clean computer with the same FQDN as the failed computer.</span></span>

  - <span data-ttu-id="1b76b-119">Переустановите сертификаты.</span><span class="sxs-lookup"><span data-stu-id="1b76b-119">Reinstall certificates.</span></span>

  - <span data-ttu-id="1b76b-120">Если сервер размещается в базе данных, установите Microsoft SQL Server 2012 или Microsoft SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="1b76b-120">If the server hosted a database, install Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2.</span></span>

  - <span data-ttu-id="1b76b-121">Как правило, если сервер размещает базу данных, запустите Topology Builder, чтобы создать и установить базу данных и настроить списки управления доступом (ACL).</span><span class="sxs-lookup"><span data-stu-id="1b76b-121">In general, if the server hosted a database, run Topology Builder to create and install the database and set up access control lists (ACLs).</span></span>

  - <span data-ttu-id="1b76b-122">В общем случае сервер, на котором размещена роль сервера, выполните шаг 1 до шага 4 мастера развертывания Lync Server для установки локальных файлов конфигурации, установки компонентов роли сервера, назначения сертификатов и запуска служб.</span><span class="sxs-lookup"><span data-stu-id="1b76b-122">In general, if the server hosted a server role, run step 1 through step 4 of the Lync Server Deployment Wizard to install the local configuration files, install the server role components, assign certificates, and start the services.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1b76b-123">Если сервер размещает базу данных, сопоставленную с ролью сервера, при выполнении шага 2 мастера развертывания Lync Server повторно создается база данных.</span><span class="sxs-lookup"><span data-stu-id="1b76b-123">If the server hosted a database collocated with the server role, running step 2 of the Lync Server Deployment Wizard recreates the database.</span></span>

    
    </div>

  - <span data-ttu-id="1b76b-124">Если сервер размещает базу данных, Восстановите резервные копии данных.</span><span class="sxs-lookup"><span data-stu-id="1b76b-124">If the server hosted a database, restore the backed up data.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

