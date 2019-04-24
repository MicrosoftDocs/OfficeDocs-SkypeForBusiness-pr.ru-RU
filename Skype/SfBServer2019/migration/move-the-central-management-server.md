---
title: Переместить центральный сервер управления
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: После миграции на Скайп для Business Server 2019, необходимо переместить центральный сервер управления Скайп для сервера переднего плана Business Server 2019 или пула, прежде чем удалять устаревшего сервера.
ms.openlocfilehash: dc85548a3c81e55267bc0ed3a32e53860e4bce09
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231576"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="68724-103">Перемещение устаревшего сервера централизованного управления Скайп для Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="68724-103">Move the legacy Central Management Server to Skype for Business Server 2019</span></span>

<span data-ttu-id="68724-104">После миграции на Скайп для Business Server 2019, а также, прежде чем удалять устаревшего сервера, необходимо переместить центральный сервер управления Скайп для сервера переднего плана Business Server 2019 или пула.</span><span class="sxs-lookup"><span data-stu-id="68724-104">After migrating to Skype for Business Server 2019, and before you can remove the legacy server, you need to move the Central Management Server to the Skype for Business Server 2019 Front End Server or pool.</span></span> 
  
<span data-ttu-id="68724-105">Центральный сервер управления — это система единого главных/несколькими реплики, где хранится чтение/запись копии базы данных сервера переднего плана, содержащий центральный сервер управления.</span><span class="sxs-lookup"><span data-stu-id="68724-105">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="68724-106">На каждом компьютере в топологии, в том числе сервера переднего плана, содержащий центральный сервер управления имеется только для чтения копию данных хранилища централизованного управления базы данных SQL Server (с именем RTCLOCAL по умолчанию) установлен на компьютере во время установки и развертывание.</span><span class="sxs-lookup"><span data-stu-id="68724-106">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="68724-107">Локальной базы данных получает обновления реплики путем получения Скайп Репликатор Business Server реплики агента, на котором выполняется как служба на всех компьютерах.</span><span class="sxs-lookup"><span data-stu-id="68724-107">The local database receives replica updates by way of the Skype for Business Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="68724-108">Имя базы данных на центральный сервер управления и локальной реплики — XDS, которая включает в себя файлы xds.mdf и xds.ldf.</span><span class="sxs-lookup"><span data-stu-id="68724-108">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="68724-109">Расположение базы данных master ссылаются точки управления службой (SCP) в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="68724-109">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="68724-110">Все средства, управление и настройка Скайп для Business Server с помощью центральный сервер управления используйте точку подключения службы для указания центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="68724-110">All tools that use the Central Management Server to manage and configure Skype for Business Server use the SCP to locate the Central Management store.</span></span>
  
<span data-ttu-id="68724-111">После успешного перемещения центральный сервер управления, следует удалить центральный сервер управления базами данных с исходного сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="68724-111">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="68724-112">Сведения об удалении базы данных центрального сервера управления в разделе [Удалить базу данных SQL Server для пула переднего плана](remove-the-sql-server-database-for-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="68724-112">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>
  
<span data-ttu-id="68724-113">Использование Windows PowerShell командлета **Move-CsManagementServer** в Скайп для Business Server командную консоль, чтобы переместить базы данных из базы данных SQL Server прежних версий установки на Скайп для базы данных Business Server 2019 SQL Server, а затем обновить Точки подключения службы для указания на Скайп для центрального сервера управления Business Server 2019 расположения.</span><span class="sxs-lookup"><span data-stu-id="68724-113">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Skype for Business Server Management Shell to move the database from the legacy install SQL Server database to the Skype for Business Server 2019 SQL Server database, and then update the SCP to point to the Skype for Business Server 2019 Central Management Server location.</span></span> 
  
<span data-ttu-id="68724-114">Используйте процедуры, описанные в этом разделе для подготовки Скайп для серверов переднего плана Business Server 2019 перед перемещением центрального сервера управления.</span><span class="sxs-lookup"><span data-stu-id="68724-114">Use the procedures in this section to prepare the Skype for Business Server 2019 Front End Servers before you move the Central Management Server.</span></span>
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="68724-115">Подготовка для пула переднего плана Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="68724-115">To prepare an Enterprise Edition Front End pool</span></span>

1. <span data-ttu-id="68724-116">На Скайп для пула переднего плана Business Server 2019 Enterprise Edition, где следует разместить центральный сервер управления Войдите на компьютер, где установлена Скайп для консоли Business Server как член \*\*RTCUniversalServerAdmins \*\*группы.</span><span class="sxs-lookup"><span data-stu-id="68724-116">On the Skype for Business Server 2019 Enterprise Edition Front End pool where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="68724-117">Также должны иметь права пользователя sysadmin базы данных SQL Server и разрешения на базу данных, где необходимо установить центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="68724-117">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span> 
    
2. <span data-ttu-id="68724-118">Откройте Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="68724-118">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="68724-119">Для создания нового центрального хранилища управления в Скайп Business Server 2019 базы данных SQL Server, в Скайп для консоли Business Server, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="68724-119">To create the new Central Management store in the Skype for Business Server 2019 SQL Server database, in the Skype for Business Server Management Shell, type:</span></span>
    
   ```
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. <span data-ttu-id="68724-120">Подтвердите, что состояние службы **Скайп для интерфейсного сервера Business** **работы**.</span><span class="sxs-lookup"><span data-stu-id="68724-120">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="68724-121">Подготовка сервера переднего плана выпуска Standard</span><span class="sxs-lookup"><span data-stu-id="68724-121">To prepare a Standard Edition Front End Server</span></span>

1. <span data-ttu-id="68724-122">На Скайп для Business Server 2019 Standard Edition Front End Server, где следует разместить центральный сервер управления Войдите на компьютер, где установлена Скайп для консоли Business Server как член \*\*RTCUniversalServerAdmins \*\*группы.</span><span class="sxs-lookup"><span data-stu-id="68724-122">On the Skype for Business Server 2019 Standard Edition Front End Server where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> 
    
2. <span data-ttu-id="68724-123">Откройте Скайп для мастер развертывания Business Server.</span><span class="sxs-lookup"><span data-stu-id="68724-123">Open the Skype for Business Server Deployment Wizard.</span></span>
    
3. <span data-ttu-id="68724-124">В Скайп для мастер развертывания Business Server щелкните **подготовить первый сервер Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="68724-124">In the Skype for Business Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>
    
4. <span data-ttu-id="68724-125">На странице **Выполнение команд** SQL Server Express установлен как центральный сервер управления.</span><span class="sxs-lookup"><span data-stu-id="68724-125">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="68724-126">Создаются необходимые правила брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="68724-126">Necessary firewall rules are created.</span></span> <span data-ttu-id="68724-127">После завершения установки базы данных и необходимого программного обеспечения, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="68724-127">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="68724-128">Первоначальной установки может занять некоторое время с помощью обновления не отображается в окне сводки выходных данных команды.</span><span class="sxs-lookup"><span data-stu-id="68724-128">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="68724-129">Это из-за установки SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="68724-129">This is due to the installation of SQL Server Express.</span></span> <span data-ttu-id="68724-130">Мониторинг установки базы данных, используйте диспетчер задач для отслеживания программы установки.</span><span class="sxs-lookup"><span data-stu-id="68724-130">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span> 
  
5. <span data-ttu-id="68724-131">Для создания нового центрального хранилища управления на Скайп для Business Server 2019 Standard Edition Front End Server, в Скайп для консоли Business Server, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="68724-131">To create the new Central Management store on the Skype for Business Server 2019 Standard Edition Front End Server, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. <span data-ttu-id="68724-132">Подтвердите, что состояние службы **Скайп для интерфейсного сервера Business** **работы**.</span><span class="sxs-lookup"><span data-stu-id="68724-132">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="68724-133">Чтобы переместить устаревший устанавливает центральный сервер управления Скайп для Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="68724-133">To move the legacy installs Central Management Server to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="68724-134">На Скайп для сервера Business Server 2019, который будет центральный сервер управления Войдите на компьютер, где установлена Скайп для консоли Business Server как член группы **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="68724-134">On the Skype for Business Server 2019 server that will be the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="68724-135">Вы также должны иметь права администратора базы данных SQL Server и разрешения.</span><span class="sxs-lookup"><span data-stu-id="68724-135">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="68724-136">Откройте Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="68724-136">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="68724-137">В поле Скайп для консоли Business Server введите:</span><span class="sxs-lookup"><span data-stu-id="68724-137">In the Skype for Business Server Management Shell, type:</span></span> 
    
   ```
   Enable-CsTopology
   ```

    > [!CAUTION]
    > <span data-ttu-id="68724-138">Если `Enable-CsTopology` не завершена, устранить проблему, предотвращая команда завершения перед продолжением.</span><span class="sxs-lookup"><span data-stu-id="68724-138">If `Enable-CsTopology` is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="68724-139">Если **Командлет Enable-CsTopology** не был выполнен успешно, move завершится с ошибкой, и он может привести к топологии где у пользователей нет центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="68724-139">If **Enable-CsTopology** is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span> 
  
4. <span data-ttu-id="68724-140">На Скайп для пула переднего плана или сервера переднего плана Business Server 2019, в Скайп для консоли Business Server введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="68724-140">On the Skype for Business Server 2019 Front End Server or Front End pool, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```
   Move-CsManagementServer
   ```

5. <span data-ttu-id="68724-141">Скайп для консоли Business Server отображает серверы, файловых хранилищ, хранилищ баз данных и точек подключения службы для текущего состояния и состояния предложено.</span><span class="sxs-lookup"><span data-stu-id="68724-141">Skype for Business Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="68724-142">Внимательно ознакомьтесь с информацией и убедитесь, что это предполагаемая источника и назначения.</span><span class="sxs-lookup"><span data-stu-id="68724-142">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="68724-143">Введите **Y** , чтобы продолжить или **N** , чтобы остановить перемещение.</span><span class="sxs-lookup"><span data-stu-id="68724-143">Type **Y** to continue, or **N** to stop the move.</span></span> 
    
6. <span data-ttu-id="68724-144">Просмотрите все предупреждения и ошибки, сгенерированные командой **Move-CsManagementServer** и устраните их.</span><span class="sxs-lookup"><span data-stu-id="68724-144">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span> 
    
7. <span data-ttu-id="68724-145">На Скайп для сервера Business Server 2019 откройте Скайп для мастер развертывания Business Server.</span><span class="sxs-lookup"><span data-stu-id="68724-145">On the Skype for Business Server 2019 server, open the Skype for Business Server Deployment Wizard.</span></span> 
    
8. <span data-ttu-id="68724-146">В Скайп мастер развертывания Business Server, щелкните элемент **Установка или обновление Скайп для бизнес-системе сервера**, выберите **Шаг 2: программа установки или удаления Скайп компонентов сервера Business**, нажмите кнопку **Далее**, просмотрите сводку и нажмите кнопку Готово \*\* \*\*.</span><span class="sxs-lookup"><span data-stu-id="68724-146">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
9. <span data-ttu-id="68724-147">Установите на устаревший сервер, откройте мастер развертывания.</span><span class="sxs-lookup"><span data-stu-id="68724-147">On the legacy install server, open the Deployment Wizard.</span></span> 
    
10. <span data-ttu-id="68724-148">В Скайп мастер развертывания Business Server, щелкните элемент **Установка или обновление Скайп для бизнес-системе сервера**, выберите **Шаг 2: программа установки или удаления Скайп компонентов сервера Business**, нажмите кнопку **Далее**, просмотрите сводку и нажмите кнопку Готово \*\* \*\*.</span><span class="sxs-lookup"><span data-stu-id="68724-148">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
11. <span data-ttu-id="68724-149">Перезагрузите Скайп для сервера Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="68724-149">Reboot the Skype for Business Server 2019 server.</span></span> <span data-ttu-id="68724-150">Это необходимо из-за изменения членства в группах для доступа к базе данных центрального сервера управления.</span><span class="sxs-lookup"><span data-stu-id="68724-150">This is required because of a group membership change to access Central Management Server database.</span></span>
    
12. <span data-ttu-id="68724-151">Чтобы подтвердить репликации с помощью нового управления повторяться хранилища, в Скайп для консоли Business Server, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="68724-151">To confirm that replication with the new Central Management store is occurring, in the Skype for Business Server Management Shell, type:</span></span> 
    
    ```
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > <span data-ttu-id="68724-152">Репликация может занять некоторое время для обновления всех текущих реплик.</span><span class="sxs-lookup"><span data-stu-id="68724-152">The replication may take some time to update all current replicas.</span></span> 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a><span data-ttu-id="68724-153">Для удаления устаревших установить файлы хранилища централизованного управления после перемещения</span><span class="sxs-lookup"><span data-stu-id="68724-153">To remove legacy install Central Management store files after a move</span></span>

1. <span data-ttu-id="68724-154">На устаревший установки сервера, выполните вход на компьютер, где установлена Скайп для консоли Business Server, как должна быть членом группы **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="68724-154">On the legacy install server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="68724-155">Вы также должны иметь права администратора базы данных SQL Server и разрешения.</span><span class="sxs-lookup"><span data-stu-id="68724-155">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="68724-156">Откройте Скайп для консоли Business Server</span><span class="sxs-lookup"><span data-stu-id="68724-156">Open Skype for Business Server Management Shell</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="68724-157">Не продолжить удаление предыдущих файлов базы данных до завершения репликации и находится в стабильном состоянии.</span><span class="sxs-lookup"><span data-stu-id="68724-157">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="68724-158">Если удалить файлы перед завершением репликации будет нарушить процесс репликации и оставьте вновь перемещенной центральный сервер управления в неизвестное состояние.</span><span class="sxs-lookup"><span data-stu-id="68724-158">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="68724-159">Командлет **Get-CsManagementStoreReplicationStatus** Чтобы проверить состояние репликации.</span><span class="sxs-lookup"><span data-stu-id="68724-159">Use the cmdlet **Get-CsManagementStoreReplicationStatus** to confirm the replication status.</span></span> 
  
3. <span data-ttu-id="68724-160">Чтобы удалить файлы базы данных хранилища централизованного управления из устаревшего установки сервера централизованного управления, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="68724-160">To remove the Central Management store database files from the legacy install Central Management Server, type:</span></span>
    
   ```
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    <span data-ttu-id="68724-161">Например:</span><span class="sxs-lookup"><span data-stu-id="68724-161">For example:</span></span>
    
   ```
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    <span data-ttu-id="68724-162">Где _ \<полное доменное имя SQL Server\> _ — это либо устаревший установите Тыловой сервер в развертывании Enterprise Edition или полное доменное имя сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="68724-162">Where the  _\<FQDN of SQL Server\>_ is either the legacy install Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span> 
    

