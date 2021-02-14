---
title: Перемещение центрального сервера управления
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: After migrating to Skype for Business Server 2019, you need to move the Central Management Server to the Skype for Business Server 2019 Front End Server or pool, before you can remove the legacy server.
ms.openlocfilehash: b5412e1b538627c50c3f2a98a5b68c64364f00a9
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752471"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="203e9-103">Перемещение устаревшего центрального сервера управления в Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="203e9-103">Move the legacy Central Management Server to Skype for Business Server 2019</span></span>

<span data-ttu-id="203e9-104">After migrating to Skype for Business Server 2019, and before you can remove the legacy server, you need to move the Central Management Server to the Skype for Business Server 2019 Front End Server or pool.</span><span class="sxs-lookup"><span data-stu-id="203e9-104">After migrating to Skype for Business Server 2019, and before you can remove the legacy server, you need to move the Central Management Server to the Skype for Business Server 2019 Front End Server or pool.</span></span> 
  
<span data-ttu-id="203e9-105">Центральный сервер управления — это единая система реплики с несколькими хозяинами, где копия базы данных для чтения и записи хранится сервером переднего сервера, который содержит центральный сервер управления.</span><span class="sxs-lookup"><span data-stu-id="203e9-105">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="203e9-106">Каждый компьютер в топологии, включая сервер переднего сервера, содержащий центральный сервер управления, имеет доступную только для чтения копию данных центрального банка управления в базе данных SQL Server (с именем RTCLOCAL по умолчанию), установленной на компьютере во время установки и развертывания.</span><span class="sxs-lookup"><span data-stu-id="203e9-106">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="203e9-107">Локализованная база данных получает обновления реплики с помощью агента репликатора репликации Skype для бизнеса Server, который работает как служба на всех компьютерах.</span><span class="sxs-lookup"><span data-stu-id="203e9-107">The local database receives replica updates by way of the Skype for Business Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="203e9-108">Имя фактической базы данных на центральном сервере управления и локальной реплики — XDS, которая состоит из файлов xds.mdf и xds.ldf.</span><span class="sxs-lookup"><span data-stu-id="203e9-108">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="203e9-109">На расположение базы данных-хозяина ссылается точка управления службой (SCP) в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="203e9-109">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="203e9-110">Все средства, которые используют центральный сервер управления для управления и настройки Skype для бизнеса Server, используют SCP для поиска центрального банка управления.</span><span class="sxs-lookup"><span data-stu-id="203e9-110">All tools that use the Central Management Server to manage and configure Skype for Business Server use the SCP to locate the Central Management store.</span></span>
  
<span data-ttu-id="203e9-111">После успешного удаления центрального сервера управления следует удалить базы данных центрального сервера управления с исходного сервера переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="203e9-111">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="203e9-112">Сведения об удалении баз данных центрального сервера управления см. в SQL Server базы данных для [пула переднего сервера.](remove-the-sql-server-database-for-a-front-end-pool.md)</span><span class="sxs-lookup"><span data-stu-id="203e9-112">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>
  
<span data-ttu-id="203e9-113">Используйте Windows PowerShell **Move-CsManagementServer** в оболочке управления Skype для бизнеса Server для перемещения базы данных из устаревшей базы данных SQL Server в базу данных SQL Server Skype для бизнеса Server 2019, а затем обновим SCP так, чтобы она была указать на расположение центрального сервера управления Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="203e9-113">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Skype for Business Server Management Shell to move the database from the legacy install SQL Server database to the Skype for Business Server 2019 SQL Server database, and then update the SCP to point to the Skype for Business Server 2019 Central Management Server location.</span></span> 
  
<span data-ttu-id="203e9-114">Используйте процедуры в этом разделе для подготовки серверов переднего сервера Skype для бизнеса Server 2019 перед перемещением центрального сервера управления.</span><span class="sxs-lookup"><span data-stu-id="203e9-114">Use the procedures in this section to prepare the Skype for Business Server 2019 Front End Servers before you move the Central Management Server.</span></span>
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="203e9-115">Подготовка пула переднего конца Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="203e9-115">To prepare an Enterprise Edition Front End pool</span></span>

1. <span data-ttu-id="203e9-116">On the Skype for Business Server 2019 Enterprise Edition Front End pool where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span><span class="sxs-lookup"><span data-stu-id="203e9-116">On the Skype for Business Server 2019 Enterprise Edition Front End pool where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="203e9-117">Кроме того, SQL Server правами и разрешениями sysadmin базы данных, в которой необходимо установить центральное хранилище управления.</span><span class="sxs-lookup"><span data-stu-id="203e9-117">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span> 
    
2. <span data-ttu-id="203e9-118">Откройте оболочку управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="203e9-118">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="203e9-119">Чтобы создать новое центральное хранилище управления в базе данных SQL Server Skype для бизнеса Server 2019, введите в оболочке управления Skype для бизнеса Server 2019 2019:</span><span class="sxs-lookup"><span data-stu-id="203e9-119">To create the new Central Management store in the Skype for Business Server 2019 SQL Server database, in the Skype for Business Server Management Shell, type:</span></span>
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. <span data-ttu-id="203e9-120">Подтвердим, что состояние службы **переднего** сервера Skype для бизнеса Server **запущено.**</span><span class="sxs-lookup"><span data-stu-id="203e9-120">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="203e9-121">Подготовка сервера переднего сервера Standard Edition</span><span class="sxs-lookup"><span data-stu-id="203e9-121">To prepare a Standard Edition Front End Server</span></span>

1. <span data-ttu-id="203e9-122">On the Skype for Business Server 2019 Standard Edition Front End Server where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span><span class="sxs-lookup"><span data-stu-id="203e9-122">On the Skype for Business Server 2019 Standard Edition Front End Server where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> 
    
2. <span data-ttu-id="203e9-123">Откройте мастер развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="203e9-123">Open the Skype for Business Server Deployment Wizard.</span></span>
    
3. <span data-ttu-id="203e9-124">В мастере развертывания Skype для бизнеса Server щелкните **"Подготовить первый сервер Standard Edition".**</span><span class="sxs-lookup"><span data-stu-id="203e9-124">In the Skype for Business Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>
    
4. <span data-ttu-id="203e9-125">На странице **"Выполнение** команд SQL Server Express устанавливается в качестве центрального сервера управления.</span><span class="sxs-lookup"><span data-stu-id="203e9-125">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="203e9-126">Создаются необходимые правила брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="203e9-126">Necessary firewall rules are created.</span></span> <span data-ttu-id="203e9-127">После завершения установки базы данных и предварительно устанавливаемого ПО нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="203e9-127">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="203e9-128">При первоначальной установке может пройти некоторое время, прежде чем на экране вывода результатов команд появятся какие-либо изменения.</span><span class="sxs-lookup"><span data-stu-id="203e9-128">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="203e9-129">Это связано с установкой SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="203e9-129">This is due to the installation of SQL Server Express.</span></span> <span data-ttu-id="203e9-130">Если необходимо отслеживать установку базы данных, используйте для этого диспетчер задач.</span><span class="sxs-lookup"><span data-stu-id="203e9-130">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span> 
  
5. <span data-ttu-id="203e9-131">To create the new Central Management store on the Skype for Business Server 2019 Standard Edition Front End Server, in the Skype for Business Server Management Shell, type:</span><span class="sxs-lookup"><span data-stu-id="203e9-131">To create the new Central Management store on the Skype for Business Server 2019 Standard Edition Front End Server, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. <span data-ttu-id="203e9-132">Подтвердим, что состояние службы **переднего** сервера Skype для бизнеса Server **запущено.**</span><span class="sxs-lookup"><span data-stu-id="203e9-132">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="203e9-133">Перемещение устаревшей системы установки центрального сервера управления в Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="203e9-133">To move the legacy installs Central Management Server to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="203e9-134">On the Skype for Business Server 2019 server that will be the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span><span class="sxs-lookup"><span data-stu-id="203e9-134">On the Skype for Business Server 2019 server that will be the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="203e9-135">Необходимо также иметь права и разрешения администратора базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="203e9-135">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="203e9-136">Откройте Skype для бизнеса Server Management Shell (запуск от администратора).</span><span class="sxs-lookup"><span data-stu-id="203e9-136">Open Skype for Business Server Management Shell (run as administrator).</span></span>
    
3. <span data-ttu-id="203e9-137">In the Skype for Business Server Management Shell, type:</span><span class="sxs-lookup"><span data-stu-id="203e9-137">In the Skype for Business Server Management Shell, type:</span></span> 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > <span data-ttu-id="203e9-138">Если `Enable-CsTopology` это не удалось, уладим проблему, не мешая выполнению команды, прежде чем продолжить.</span><span class="sxs-lookup"><span data-stu-id="203e9-138">If `Enable-CsTopology` is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="203e9-139">Если **enable-CsTopology** не удается, перемещение не удастся и топология может оказаться в состоянии, когда центральное хранилище управления не существует.</span><span class="sxs-lookup"><span data-stu-id="203e9-139">If **Enable-CsTopology** is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span> 
  
4. <span data-ttu-id="203e9-140">On the Skype for Business Server 2019 Front End Server or Front End pool, in the Skype for Business Server Management Shell, type:</span><span class="sxs-lookup"><span data-stu-id="203e9-140">On the Skype for Business Server 2019 Front End Server or Front End pool, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. <span data-ttu-id="203e9-141">В оболочке управления Skype для бизнеса Server отображаются серверы, хранилища файлов, хранилища баз данных и точки подключения служб текущего состояния и предложенного состояния.</span><span class="sxs-lookup"><span data-stu-id="203e9-141">Skype for Business Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="203e9-142">Внимательно просмотрите сведения об исходном и целевом состоянии и убедитесь, что они правильны.</span><span class="sxs-lookup"><span data-stu-id="203e9-142">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="203e9-143">Введите **Y**, чтобы продолжить, или **N**, чтобы остановить перемещение.</span><span class="sxs-lookup"><span data-stu-id="203e9-143">Type **Y** to continue, or **N** to stop the move.</span></span> 
    
6. <span data-ttu-id="203e9-144">Проверьте все предупреждения и ошибки, сгенерированные командой **Move-CsManagementServer**, и устраните их.</span><span class="sxs-lookup"><span data-stu-id="203e9-144">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span> 
    
7. <span data-ttu-id="203e9-145">На сервере Skype для бизнеса Server 2019 откройте мастер развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="203e9-145">On the Skype for Business Server 2019 server, open the Skype for Business Server Deployment Wizard.</span></span> 
    
8. <span data-ttu-id="203e9-146">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click Step **2: Setup or Remove Skype for Business Server Components,** click **Next**, review the summary, and then click **Finish**.</span><span class="sxs-lookup"><span data-stu-id="203e9-146">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
9. <span data-ttu-id="203e9-147">На сервере установки прежних версиях откройте мастер развертывания.</span><span class="sxs-lookup"><span data-stu-id="203e9-147">On the legacy install server, open the Deployment Wizard.</span></span> 
    
10. <span data-ttu-id="203e9-148">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click Step **2: Setup or Remove Skype for Business Server Components,** click **Next**, review the summary, and then click **Finish**.</span><span class="sxs-lookup"><span data-stu-id="203e9-148">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
11. <span data-ttu-id="203e9-149">Перезагружает сервер Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="203e9-149">Reboot the Skype for Business Server 2019 server.</span></span> <span data-ttu-id="203e9-150">Это необходимо из-за изменения членства в группе для доступа к базе данных центрального сервера управления.</span><span class="sxs-lookup"><span data-stu-id="203e9-150">This is required because of a group membership change to access Central Management Server database.</span></span>
    
12. <span data-ttu-id="203e9-151">To confirm that replication with the new Central Management store is occurring, in the Skype for Business Server Management Shell, type:</span><span class="sxs-lookup"><span data-stu-id="203e9-151">To confirm that replication with the new Central Management store is occurring, in the Skype for Business Server Management Shell, type:</span></span> 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > <span data-ttu-id="203e9-152">Обновление всех текущих реплик может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="203e9-152">The replication may take some time to update all current replicas.</span></span> 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a><span data-ttu-id="203e9-153">Удаление устаревших файлов центрального банка управления после перемещения</span><span class="sxs-lookup"><span data-stu-id="203e9-153">To remove legacy install Central Management store files after a move</span></span>

1. <span data-ttu-id="203e9-154">On the legacy install server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span><span class="sxs-lookup"><span data-stu-id="203e9-154">On the legacy install server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="203e9-155">Необходимо также иметь права и разрешения администратора базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="203e9-155">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="203e9-156">Open Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="203e9-156">Open Skype for Business Server Management Shell</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="203e9-157">Не удаляйте файлы старой базы данных, пока репликация не завершится и не станет стабильной.</span><span class="sxs-lookup"><span data-stu-id="203e9-157">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="203e9-158">Если удалить файлы до завершения репликации, процесс репликации будет прерван и новый центральный сервер управления останется в неизвестном состоянии.</span><span class="sxs-lookup"><span data-stu-id="203e9-158">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="203e9-159">Используйте командлет **Get-CsManagementStoreReplicationStatus** для подтверждения состояния репликации.</span><span class="sxs-lookup"><span data-stu-id="203e9-159">Use the cmdlet **Get-CsManagementStoreReplicationStatus** to confirm the replication status.</span></span> 
  
3. <span data-ttu-id="203e9-160">Чтобы удалить файлы базы данных центрального банка управления из устаревшей установки центрального сервера управления, введите:</span><span class="sxs-lookup"><span data-stu-id="203e9-160">To remove the Central Management store database files from the legacy install Central Management Server, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    <span data-ttu-id="203e9-161">Пример:</span><span class="sxs-lookup"><span data-stu-id="203e9-161">For example:</span></span>
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    <span data-ttu-id="203e9-162">Где это либо устаревший сервер установки в развертывании Enterprise Edition, либо  _\<FQDN of SQL Server\>_ FQDN сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="203e9-162">Where the  _\<FQDN of SQL Server\>_ is either the legacy install Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span> 
    

