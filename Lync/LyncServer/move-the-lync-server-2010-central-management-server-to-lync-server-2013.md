---
title: Перемещение сервера центрального управления Lync Server 2010 на Lync Server 2013
description: Переместите сервер центрального управления Lync Server 2010 на Lync Server 2013.
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
ms.openlocfilehash: 19d53d797375b1eb8fde72f6b999e509b97f85ae
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571285"
---
# <a name="move-the-lync-server-2010-central-management-server-to-lync-server-2013"></a><span data-ttu-id="52628-103">Перемещение сервера центрального управления Lync Server 2010 на Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52628-103">Move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52628-104">_**Последнее изменение темы:** 2013-11-25_</span><span class="sxs-lookup"><span data-stu-id="52628-104">_**Topic Last Modified:** 2013-11-25_</span></span>

<span data-ttu-id="52628-105">После перехода с Lync Server 2010 на Lync Server 2013 необходимо переместить сервер центрального управления Lync Server 2010 на сервер переднего плана Lync Server 2013 или в пул, прежде чем можно будет удалить устаревший сервер Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="52628-105">After migrating from Lync Server 2010 to Lync Server 2013, you need to move the Lync Server 2010 Central Management Server to the Lync Server 2013 Front End Server or pool, before you can remove the legacy Lync Server 2010 server.</span></span>

<span data-ttu-id="52628-106">Центральный сервер управления является единственной основной или множественной репликой, где сервер переднего плана, на котором размещен Центральный сервер управления, владеет копией базы данных, предназначенной для чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="52628-106">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="52628-107">На каждом компьютере в топологии, в том числе на сервере переднего плана, который содержит центральный сервер управления, доступна только для чтения копия данных центрального хранилища управления в базе данных SQL Server (с именем RTCLOCAL по умолчанию), установленная на компьютере во время установки и развертывания.</span><span class="sxs-lookup"><span data-stu-id="52628-107">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="52628-108">Локальная база данных получает обновления реплики с помощью агента репликатора реплики Lync Server, выполняющегося как служба на всех компьютерах.</span><span class="sxs-lookup"><span data-stu-id="52628-108">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="52628-109">Имя фактической базы данных на центральном сервере управления и в локальной реплике — XDS, которая состоит из файлов XDS. mdf и XDS. ldf.</span><span class="sxs-lookup"><span data-stu-id="52628-109">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="52628-110">На расположение базы данных Master ссылается точка управления службой (SCP) в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="52628-110">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="52628-111">Все средства, которые используют центральный сервер управления для управления и настройки Lync Server, используют точку подключения службы для обнаружения центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="52628-111">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>

<span data-ttu-id="52628-112">После успешного перемещения центрального сервера управления необходимо удалить базы данных центрального сервера управления с исходного сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="52628-112">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="52628-113">Сведения об удалении баз данных центрального сервера управления приведены в статье [Удаление базы данных SQL Server для пула переднего плана](remove-the-sql-server-database-for-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="52628-113">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>

<span data-ttu-id="52628-114">Командлет Windows PowerShell **Move — CsManagementServer** в командной консоли Lync Server для перемещения базы данных из базы данных sql Server 2010 SQL Server в базу данных SQL Server с lync Server 2013 и последующего обновления точки подключения службы, чтобы она ссылалась на расположение сервера центрального управления lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52628-114">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Lync Server Management Shell to move the database from the Lync Server 2010 SQL Server database to the Lync Server 2013 SQL Server database, and then update the SCP to point to the Lync Server 2013 Central Management Server location.</span></span>

<div>

## <a name="preparing-lync-server-2013front-end-servers-before-moving-the-central-management-server"></a><span data-ttu-id="52628-115">Подготовка серверов переднего плана Lync Server 2013 перед перемещением центрального сервера управления</span><span class="sxs-lookup"><span data-stu-id="52628-115">Preparing Lync Server 2013 Front End Servers before moving the Central Management Server</span></span>

<span data-ttu-id="52628-116">С помощью процедур, описанных в этом разделе, можно подготовить серверы переднего плана Lync Server 2013 перед перемещением центрального сервера управления Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="52628-116">Use the procedures in this section to prepare the Lync Server 2013 Front End Servers before you move the Lync Server 2010 Central Management Server.</span></span>

<div>

## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="52628-117">Подготовка пула переднего плана Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="52628-117">To prepare an Enterprise Edition Front End pool</span></span>

1.  <span data-ttu-id="52628-118">На интерфейсном пуле Lync Server 2013 Enterprise Edition, где необходимо переместить сервер центрального управления: Войдите на компьютер, на котором установлена командная консоль Lync Server, в качестве члена группы **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="52628-118">On the Lync Server 2013 Enterprise Edition Front End pool where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="52628-119">Кроме того, необходимо иметь права и разрешения администратора базы данных SQL Server для базы данных, в которой необходимо установить центральное хранилище управления.</span><span class="sxs-lookup"><span data-stu-id="52628-119">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span>

2.  <span data-ttu-id="52628-120">Откройте командную консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="52628-120">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="52628-121">Чтобы создать новое центральное хранилище управления в базе данных SQL Server 2013, в консоли управления Lync Server, введите:</span><span class="sxs-lookup"><span data-stu-id="52628-121">To create the new Central Management store in the Lync Server 2013 SQL Server database, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  <span data-ttu-id="52628-122">Убедитесь, что состояние службы **интерфейсного сервера Lync** указано как **Запущена**.</span><span class="sxs-lookup"><span data-stu-id="52628-122">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

<div>

## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="52628-123">Подготовка сервера переднего плана Standard Edition</span><span class="sxs-lookup"><span data-stu-id="52628-123">To prepare a Standard Edition Front End Server</span></span>

1.  <span data-ttu-id="52628-124">На сервере переднего плана Lync Server 2013 Standard Edition, на котором требуется переместить сервер центрального управления: Войдите на компьютер, на котором установлена командная консоль Lync Server, в качестве члена группы **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="52628-124">On the Lync Server 2013 Standard Edition Front End Server where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span>

2.  <span data-ttu-id="52628-125">Откройте мастер развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="52628-125">Open the Lync Server Deployment Wizard.</span></span>

3.  <span data-ttu-id="52628-126">В мастере развертывания Lync Server нажмите кнопку **подготовить первый сервер Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="52628-126">In the Lync Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>

4.  <span data-ttu-id="52628-127">На странице **выполнение команд** SQL Server Express устанавливается в качестве центрального сервера управления.</span><span class="sxs-lookup"><span data-stu-id="52628-127">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="52628-128">Создаются необходимые правила брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="52628-128">Necessary firewall rules are created.</span></span> <span data-ttu-id="52628-129">После завершения установки базы данных и предварительно устанавливаемого ПО нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="52628-129">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="52628-130">При первоначальной установке может пройти некоторое время, прежде чем на экране вывода результатов команд появятся какие-либо изменения.</span><span class="sxs-lookup"><span data-stu-id="52628-130">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="52628-131">Это обусловлено установкой SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="52628-131">This is due to the installation of the SQL Server Express.</span></span> <span data-ttu-id="52628-132">Если необходимо отслеживать установку базы данных, используйте для этого диспетчер задач.</span><span class="sxs-lookup"><span data-stu-id="52628-132">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span>

    
    </div>

5.  <span data-ttu-id="52628-133">Для создания нового центрального хранилища управления на сервере переднего плана Lync Server 2013 Standard Edition в командной консоли Lync Server введите:</span><span class="sxs-lookup"><span data-stu-id="52628-133">To create the new Central Management store on the Lync Server 2013 Standard Edition Front End Server, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  <span data-ttu-id="52628-134">Убедитесь, что состояние службы **интерфейсного сервера Lync** указано как **Запущена**.</span><span class="sxs-lookup"><span data-stu-id="52628-134">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

</div>

<div>

## <a name="to-move-the-lync-server-2010central-management-server-to-lync-server-2013"></a><span data-ttu-id="52628-135">Порядок перемещения сервера центрального управления Lync Server 2010 на Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52628-135">To move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

1.  <span data-ttu-id="52628-136">На сервере Lync Server 2013, который будет центральным сервером управления: Войдите на компьютер, на котором установлена командная консоль Lync Server, в качестве члена группы **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="52628-136">On the Lync Server 2013 server that will be the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="52628-137">Необходимо также иметь права и разрешения администратора базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="52628-137">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="52628-138">Откройте консоль управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="52628-138">Open Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="52628-139">В командной консоли Lync Server введите:</span><span class="sxs-lookup"><span data-stu-id="52628-139">In the Lync Server Management Shell, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="52628-140">Если <CODE>Enable-CsTopology</CODE> это не удалось, устраните проблему, препятствующую выполнению команды перед продолжением.</span><span class="sxs-lookup"><span data-stu-id="52628-140">If <CODE>Enable-CsTopology</CODE> is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="52628-141">Если не удается <STRONG>Enable-CsTopology</STRONG> , перемещение завершится ошибкой, и она может оставить топологию в состоянии, в котором нет центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="52628-141">If <STRONG>Enable-CsTopology</STRONG> is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span>

    
    </div>

4.  <span data-ttu-id="52628-142">На сервере переднего плана Lync Server 2013 или интерфейсном пуле в командной консоли Lync Server введите:</span><span class="sxs-lookup"><span data-stu-id="52628-142">On the Lync Server 2013 Front End Server or Front End pool, in the Lync Server Management Shell, type:</span></span>
    
        Move-CsManagementServer

5.  <span data-ttu-id="52628-143">В командной консоли Lync Server отображаются серверы, хранилища файлов, хранилища баз данных, а также точки подключения служб текущего состояния и предлагаемое состояние.</span><span class="sxs-lookup"><span data-stu-id="52628-143">Lync Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="52628-144">Внимательно просмотрите сведения об исходном и целевом состоянии и убедитесь, что они правильны.</span><span class="sxs-lookup"><span data-stu-id="52628-144">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="52628-145">Введите **Y**, чтобы продолжить, или **N**, чтобы остановить перемещение.</span><span class="sxs-lookup"><span data-stu-id="52628-145">Type **Y** to continue, or **N** to stop the move.</span></span>

6.  <span data-ttu-id="52628-146">Проверьте все предупреждения и ошибки, сгенерированные командой **Move-CsManagementServer**, и устраните их.</span><span class="sxs-lookup"><span data-stu-id="52628-146">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span>

7.  <span data-ttu-id="52628-147">На сервере Lync Server 2013 откройте мастер развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="52628-147">On the Lync Server 2013 server, open the Lync Server Deployment Wizard.</span></span>

8.  <span data-ttu-id="52628-148">В мастере развертывания Lync Server щелкните **установить или обновить систему Lync Server**, выберите **Шаг 2: Установка или удаление компонентов Lync Server**, нажмите кнопку **Далее**, просмотрите сводку и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="52628-148">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

9.  <span data-ttu-id="52628-149">На сервере Lync Server 2010 откройте мастер развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="52628-149">On the Lync Server 2010 server, open the Lync Server Deployment Wizard.</span></span>

10. <span data-ttu-id="52628-150">В мастере развертывания Lync Server щелкните **установить или обновить систему Lync Server**, выберите **Шаг 2: Установка или удаление компонентов Lync Server**, нажмите кнопку **Далее**, просмотрите сводку и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="52628-150">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

11. <span data-ttu-id="52628-151">Перезагрузите сервер Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52628-151">Reboot the Lync Server 2013 server.</span></span> <span data-ttu-id="52628-152">Это необходимо из-за того, что членство в группе изменяется на доступ к базе данных центрального сервера управления.</span><span class="sxs-lookup"><span data-stu-id="52628-152">This is required because of a group membership change to access Central Management Server database.</span></span>

12. <span data-ttu-id="52628-153">Чтобы убедиться в том, что происходит репликация с новым центральным хранилищем управления, в командной консоли Lync Server введите:</span><span class="sxs-lookup"><span data-stu-id="52628-153">To confirm that replication with the new Central Management store is occurring, in the Lync Server Management Shell, type:</span></span>
    
        Get-CsManagementStoreReplicationStatus
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="52628-154">Обновление всех текущих реплик может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="52628-154">The replication may take some time to update all current replicas.</span></span>

    
    </div>

</div>

<div>

## <a name="to-remove-lync-server-2010central-management-store-files-after-a-move"></a><span data-ttu-id="52628-155">Удаление файлов центрального хранилища управления Lync Server 2010 после перемещения</span><span class="sxs-lookup"><span data-stu-id="52628-155">To remove Lync Server 2010 Central Management store files after a move</span></span>

1.  <span data-ttu-id="52628-156">На сервере Lync Server 2010 Server: Войдите на компьютер, на котором установлена командная консоль Lync Server, в качестве члена группы **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="52628-156">On the Lync Server 2010 server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="52628-157">Необходимо также иметь права и разрешения администратора базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="52628-157">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="52628-158">Открытие консоли управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="52628-158">Open Lync Server Management Shell</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="52628-159">Не удаляйте файлы старой базы данных, пока репликация не завершится и не станет стабильной.</span><span class="sxs-lookup"><span data-stu-id="52628-159">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="52628-160">Если удалить файлы перед выполнением репликации, процесс репликации будет нарушен, а перемещенный центральный сервер управления останется в неизвестном состоянии.</span><span class="sxs-lookup"><span data-stu-id="52628-160">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="52628-161">Используйте командлет <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> для подтверждения состояния репликации.</span><span class="sxs-lookup"><span data-stu-id="52628-161">Use the cmdlet <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> to confirm the replication status.</span></span>

    
    </div>

3.  <span data-ttu-id="52628-162">Чтобы удалить файлы баз данных центрального хранилища управления с сервера центрального управления Lync Server 2010, введите:</span><span class="sxs-lookup"><span data-stu-id="52628-162">To remove the Central Management store database files from the Lync Server 2010 Central Management Server, type:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    <span data-ttu-id="52628-163">Например:</span><span class="sxs-lookup"><span data-stu-id="52628-163">For example:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    <span data-ttu-id="52628-164">Где \<FQDN of SQL Server\> — это внутренний сервер Lync server 2010 в развертывании Enterprise Edition или полное доменное имя сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="52628-164">Where the \<FQDN of SQL Server\> is either the Lync Server 2010 Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

