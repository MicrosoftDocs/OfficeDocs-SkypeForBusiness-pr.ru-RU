---
title: Перемещение сервера центрального управления Lync Server 2010 на Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move the Lync Server 2010 Central Management Server to Lync Server 2013
ms:assetid: 30cc98f2-1916-4dbe-99d0-8df5368ed3ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688013(v=OCS.15)
ms:contentKeyID: 49733602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b344ff2fb9fb4ed123d864e219f64d9c1f04202
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148718"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-the-lync-server-2010-central-management-server-to-lync-server-2013"></a><span data-ttu-id="42852-102">Перемещение сервера центрального управления Lync Server 2010 на Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42852-102">Move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42852-103">_**Последнее изменение темы:** 2013-11-25_</span><span class="sxs-lookup"><span data-stu-id="42852-103">_**Topic Last Modified:** 2013-11-25_</span></span>

<span data-ttu-id="42852-104">После перехода с Lync Server 2010 на Lync Server 2013 необходимо переместить сервер центрального управления Lync Server 2010 на сервер переднего плана Lync Server 2013 или в пул, прежде чем можно будет удалить устаревший сервер Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="42852-104">After migrating from Lync Server 2010 to Lync Server 2013, you need to move the Lync Server 2010 Central Management Server to the Lync Server 2013 Front End Server or pool, before you can remove the legacy Lync Server 2010 server.</span></span>

<span data-ttu-id="42852-105">Центральный сервер управления является единственной основной или множественной репликой, где сервер переднего плана, на котором размещен Центральный сервер управления, владеет копией базы данных, предназначенной для чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="42852-105">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="42852-106">На каждом компьютере в топологии, в том числе на сервере переднего плана, который содержит центральный сервер управления, доступна только для чтения копия данных центрального хранилища управления в базе данных SQL Server (с именем RTCLOCAL по умолчанию), установленной на компьютере во время установки, и развертывание.</span><span class="sxs-lookup"><span data-stu-id="42852-106">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="42852-107">Локальная база данных получает обновления реплики с помощью агента репликатора реплики Lync Server, выполняющегося как служба на всех компьютерах.</span><span class="sxs-lookup"><span data-stu-id="42852-107">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="42852-108">Имя фактической базы данных на центральном сервере управления и в локальной реплике — XDS, которая состоит из файлов XDS. mdf и XDS. ldf.</span><span class="sxs-lookup"><span data-stu-id="42852-108">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="42852-109">На расположение базы данных Master ссылается точка управления службой (SCP) в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="42852-109">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="42852-110">Все средства, которые используют центральный сервер управления для управления и настройки Lync Server, используют точку подключения службы для обнаружения центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="42852-110">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>

<span data-ttu-id="42852-111">После успешного перемещения центрального сервера управления необходимо удалить базы данных центрального сервера управления с исходного сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="42852-111">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="42852-112">Сведения об удалении баз данных центрального сервера управления приведены в статье [Удаление базы данных SQL Server для пула переднего плана](remove-the-sql-server-database-for-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="42852-112">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>

<span data-ttu-id="42852-113">Командлет Windows PowerShell **Move — CsManagementServer** в командной консоли Lync Server для перемещения базы данных из базы данных sql Server 2010 SQL Server в базу данных SQL Server с lync Server 2013 и последующего обновления точки подключения службы, чтобы она ссылалась на расположение сервера центрального управления lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42852-113">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Lync Server Management Shell to move the database from the Lync Server 2010 SQL Server database to the Lync Server 2013 SQL Server database, and then update the SCP to point to the Lync Server 2013 Central Management Server location.</span></span>

<div>

## <a name="preparing-lync-server-2013front-end-servers-before-moving-the-central-management-server"></a><span data-ttu-id="42852-114">Подготовка серверов переднего плана Lync Server 2013 перед перемещением центрального сервера управления</span><span class="sxs-lookup"><span data-stu-id="42852-114">Preparing Lync Server 2013 Front End Servers before moving the Central Management Server</span></span>

<span data-ttu-id="42852-115">С помощью процедур, описанных в этом разделе, можно подготовить серверы переднего плана Lync Server 2013 перед перемещением центрального сервера управления Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="42852-115">Use the procedures in this section to prepare the Lync Server 2013 Front End Servers before you move the Lync Server 2010 Central Management Server.</span></span>

<div>

## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="42852-116">Подготовка пула переднего плана Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="42852-116">To prepare an Enterprise Edition Front End pool</span></span>

1.  <span data-ttu-id="42852-117">На интерфейсном пуле Lync Server 2013 Enterprise Edition, где необходимо переместить сервер центрального управления: Войдите на компьютер, на котором установлена командная консоль Lync Server, в качестве члена группы **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="42852-117">On the Lync Server 2013 Enterprise Edition Front End pool where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="42852-118">Кроме того, необходимо иметь права и разрешения администратора базы данных SQL Server для базы данных, в которой необходимо установить центральное хранилище управления.</span><span class="sxs-lookup"><span data-stu-id="42852-118">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span>

2.  <span data-ttu-id="42852-119">Откройте командную консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="42852-119">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="42852-120">Чтобы создать новое центральное хранилище управления в базе данных SQL Server 2013, в консоли управления Lync Server, введите:</span><span class="sxs-lookup"><span data-stu-id="42852-120">To create the new Central Management store in the Lync Server 2013 SQL Server database, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  <span data-ttu-id="42852-121">Убедитесь, что состояние службы **интерфейсного сервера Lync** указано как **Запущена**.</span><span class="sxs-lookup"><span data-stu-id="42852-121">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

<div>

## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="42852-122">Подготовка сервера переднего плана Standard Edition</span><span class="sxs-lookup"><span data-stu-id="42852-122">To prepare a Standard Edition Front End Server</span></span>

1.  <span data-ttu-id="42852-123">На сервере переднего плана Lync Server 2013 Standard Edition, на котором требуется переместить сервер центрального управления: Войдите на компьютер, на котором установлена командная консоль Lync Server, в качестве члена группы **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="42852-123">On the Lync Server 2013 Standard Edition Front End Server where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span>

2.  <span data-ttu-id="42852-124">Откройте мастер развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="42852-124">Open the Lync Server Deployment Wizard.</span></span>

3.  <span data-ttu-id="42852-125">В мастере развертывания Lync Server нажмите кнопку **подготовить первый сервер Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="42852-125">In the Lync Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>

4.  <span data-ttu-id="42852-126">На странице **выполнение команд** SQL Server Express устанавливается в качестве центрального сервера управления.</span><span class="sxs-lookup"><span data-stu-id="42852-126">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="42852-127">Создаются необходимые правила брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="42852-127">Necessary firewall rules are created.</span></span> <span data-ttu-id="42852-128">После завершения установки базы данных и предварительно устанавливаемого ПО нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="42852-128">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="42852-129">При первоначальной установке может пройти некоторое время, прежде чем на экране вывода результатов команд появятся какие-либо изменения.</span><span class="sxs-lookup"><span data-stu-id="42852-129">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="42852-130">Это обусловлено установкой SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="42852-130">This is due to the installation of the SQL Server Express.</span></span> <span data-ttu-id="42852-131">Если необходимо отслеживать установку базы данных, используйте для этого диспетчер задач.</span><span class="sxs-lookup"><span data-stu-id="42852-131">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span>

    
    </div>

5.  <span data-ttu-id="42852-132">Для создания нового центрального хранилища управления на сервере переднего плана Lync Server 2013 Standard Edition в командной консоли Lync Server введите:</span><span class="sxs-lookup"><span data-stu-id="42852-132">To create the new Central Management store on the Lync Server 2013 Standard Edition Front End Server, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  <span data-ttu-id="42852-133">Убедитесь, что состояние службы **интерфейсного сервера Lync** указано как **Запущена**.</span><span class="sxs-lookup"><span data-stu-id="42852-133">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

</div>

<div>

## <a name="to-move-the-lync-server-2010central-management-server-to-lync-server-2013"></a><span data-ttu-id="42852-134">Порядок перемещения сервера центрального управления Lync Server 2010 на Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42852-134">To move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

1.  <span data-ttu-id="42852-135">На сервере Lync Server 2013, который будет центральным сервером управления: Войдите на компьютер, на котором установлена командная консоль Lync Server, в качестве члена группы **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="42852-135">On the Lync Server 2013 server that will be the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="42852-136">Необходимо также иметь права и разрешения администратора базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="42852-136">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="42852-137">Откройте консоль управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="42852-137">Open Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="42852-138">В командной консоли Lync Server введите:</span><span class="sxs-lookup"><span data-stu-id="42852-138">In the Lync Server Management Shell, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="42852-139">Если <CODE>Enable-CsTopology</CODE> это не удалось, устраните проблему, препятствующую выполнению команды перед продолжением.</span><span class="sxs-lookup"><span data-stu-id="42852-139">If <CODE>Enable-CsTopology</CODE> is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="42852-140">Если не удается <STRONG>Enable-CsTopology</STRONG> , перемещение завершится ошибкой, и она может оставить топологию в состоянии, в котором нет центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="42852-140">If <STRONG>Enable-CsTopology</STRONG> is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span>

    
    </div>

4.  <span data-ttu-id="42852-141">На сервере переднего плана Lync Server 2013 или интерфейсном пуле в командной консоли Lync Server введите:</span><span class="sxs-lookup"><span data-stu-id="42852-141">On the Lync Server 2013 Front End Server or Front End pool, in the Lync Server Management Shell, type:</span></span>
    
        Move-CsManagementServer

5.  <span data-ttu-id="42852-142">В командной консоли Lync Server отображаются серверы, хранилища файлов, хранилища баз данных, а также точки подключения служб текущего состояния и предлагаемое состояние.</span><span class="sxs-lookup"><span data-stu-id="42852-142">Lync Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="42852-143">Внимательно просмотрите сведения об исходном и целевом состоянии и убедитесь, что они правильны.</span><span class="sxs-lookup"><span data-stu-id="42852-143">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="42852-144">Введите **Y**, чтобы продолжить, или **N**, чтобы остановить перемещение.</span><span class="sxs-lookup"><span data-stu-id="42852-144">Type **Y** to continue, or **N** to stop the move.</span></span>

6.  <span data-ttu-id="42852-145">Проверьте все предупреждения и ошибки, сгенерированные командой **Move-CsManagementServer**, и устраните их.</span><span class="sxs-lookup"><span data-stu-id="42852-145">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span>

7.  <span data-ttu-id="42852-146">На сервере Lync Server 2013 откройте мастер развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="42852-146">On the Lync Server 2013 server, open the Lync Server Deployment Wizard.</span></span>

8.  <span data-ttu-id="42852-147">В мастере развертывания Lync Server щелкните **установить или обновить систему Lync Server**, выберите **Шаг 2: Установка или удаление компонентов Lync Server**, нажмите кнопку **Далее**, просмотрите сводку и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="42852-147">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

9.  <span data-ttu-id="42852-148">На сервере Lync Server 2010 откройте мастер развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="42852-148">On the Lync Server 2010 server, open the Lync Server Deployment Wizard.</span></span>

10. <span data-ttu-id="42852-149">В мастере развертывания Lync Server щелкните **установить или обновить систему Lync Server**, выберите **Шаг 2: Установка или удаление компонентов Lync Server**, нажмите кнопку **Далее**, просмотрите сводку и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="42852-149">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

11. <span data-ttu-id="42852-150">Перезагрузите сервер Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42852-150">Reboot the Lync Server 2013 server.</span></span> <span data-ttu-id="42852-151">Это необходимо из-за того, что членство в группе изменяется на доступ к базе данных центрального сервера управления.</span><span class="sxs-lookup"><span data-stu-id="42852-151">This is required because of a group membership change to access Central Management Server database.</span></span>

12. <span data-ttu-id="42852-152">Чтобы убедиться в том, что происходит репликация с новым центральным хранилищем управления, в командной консоли Lync Server введите:</span><span class="sxs-lookup"><span data-stu-id="42852-152">To confirm that replication with the new Central Management store is occurring, in the Lync Server Management Shell, type:</span></span>
    
        Get-CsManagementStoreReplicationStatus
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="42852-153">Обновление всех текущих реплик может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="42852-153">The replication may take some time to update all current replicas.</span></span>

    
    </div>

</div>

<div>

## <a name="to-remove-lync-server-2010central-management-store-files-after-a-move"></a><span data-ttu-id="42852-154">Удаление файлов центрального хранилища управления Lync Server 2010 после перемещения</span><span class="sxs-lookup"><span data-stu-id="42852-154">To remove Lync Server 2010 Central Management store files after a move</span></span>

1.  <span data-ttu-id="42852-155">На сервере Lync Server 2010 Server: Войдите на компьютер, на котором установлена командная консоль Lync Server, в качестве члена группы **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="42852-155">On the Lync Server 2010 server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="42852-156">Необходимо также иметь права и разрешения администратора базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="42852-156">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="42852-157">Открытие консоли управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="42852-157">Open Lync Server Management Shell</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="42852-158">Не удаляйте файлы старой базы данных, пока репликация не завершится и не станет стабильной.</span><span class="sxs-lookup"><span data-stu-id="42852-158">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="42852-159">Если удалить файлы перед выполнением репликации, процесс репликации будет нарушен, а перемещенный центральный сервер управления останется в неизвестном состоянии.</span><span class="sxs-lookup"><span data-stu-id="42852-159">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="42852-160">Используйте командлет <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> для подтверждения состояния репликации.</span><span class="sxs-lookup"><span data-stu-id="42852-160">Use the cmdlet <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> to confirm the replication status.</span></span>

    
    </div>

3.  <span data-ttu-id="42852-161">Чтобы удалить файлы баз данных центрального хранилища управления с сервера центрального управления Lync Server 2010, введите:</span><span class="sxs-lookup"><span data-stu-id="42852-161">To remove the Central Management store database files from the Lync Server 2010 Central Management Server, type:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    <span data-ttu-id="42852-162">Например:</span><span class="sxs-lookup"><span data-stu-id="42852-162">For example:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    <span data-ttu-id="42852-163">Где \<полное доменное имя SQL\> Server — это внутренний сервер Lync Server 2010 в развертывании Enterprise Edition или полное доменное имя сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="42852-163">Where the \<FQDN of SQL Server\> is either the Lync Server 2010 Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

