---
title: Перемещение центрального сервера управления
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: После перехода на Skype для бизнеса Server 2019 необходимо переместить центральный сервер управления на сервер или в пул Skype для бизнеса Server 2019, прежде чем можно будет удалить старый сервер.
ms.openlocfilehash: b6a2dd08949b5b15370f27e1da936009048982f6
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40990934"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="fd7ad-103">Перемещение устаревшего центрального сервера управления в Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="fd7ad-103">Move the legacy Central Management Server to Skype for Business Server 2019</span></span>

<span data-ttu-id="fd7ad-104">После перехода на Skype для бизнеса Server 2019 и перед удалением устаревшего сервера необходимо переместить центральный сервер управления на сервер или в пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-104">After migrating to Skype for Business Server 2019, and before you can remove the legacy server, you need to move the Central Management Server to the Skype for Business Server 2019 Front End Server or pool.</span></span> 
  
<span data-ttu-id="fd7ad-105">Центральный сервер управления — это единая Главная или несколько реплик, где сервер переднего плана, на котором находится база данных для чтения и записи, находится на сервере, который содержит центральный сервер управления.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-105">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="fd7ad-106">На каждом компьютере в топологии, включая сервер переднего плана, на котором находится центральный сервер управления, доступна только для чтения копия данных центрального хранилища в базе данных SQL Server (с именем РТКЛОКАЛ по умолчанию), установленной на компьютере во время установки и среде.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-106">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="fd7ad-107">Локальная база данных получает обновления реплики с помощью агента репликатора реплики в Skype для бизнеса Server, который запускается как служба на всех компьютерах.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-107">The local database receives replica updates by way of the Skype for Business Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="fd7ad-108">Имя реальной базы данных на центральном сервере управления и в локальной реплике — XDS, которая состоит из файлов XDS. mdf и XDS. ldf.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-108">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="fd7ad-109">На расположение базы данных Master ссылается точка управления службой (SCP) доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-109">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="fd7ad-110">Все средства, использующие центральный сервер управления для управления и настройки Skype для бизнеса Server, используют точку подключения службы для поиска хранилища центрального управления.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-110">All tools that use the Central Management Server to manage and configure Skype for Business Server use the SCP to locate the Central Management store.</span></span>
  
<span data-ttu-id="fd7ad-111">После успешного перемещения центрального сервера управления необходимо удалить базы данных центрального сервера управления с исходного сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-111">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="fd7ad-112">Сведения об удалении баз данных центрального сервера управления можно найти в разделе [Удаление базы данных SQL Server для пула переднего плана](remove-the-sql-server-database-for-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="fd7ad-112">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>
  
<span data-ttu-id="fd7ad-113">С помощью командлета Windows PowerShell **Remove-ксманажементсервер** в командной консоли управления Skype для бизнеса Server можно переместить базу данных из базы данных SQL Server из устаревшей версии в базу данных сервера sql Server 2019, а затем обновить точку входа, чтобы она указывала на расположение сервера центра администрирования Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-113">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Skype for Business Server Management Shell to move the database from the legacy install SQL Server database to the Skype for Business Server 2019 SQL Server database, and then update the SCP to point to the Skype for Business Server 2019 Central Management Server location.</span></span> 
  
<span data-ttu-id="fd7ad-114">С помощью описанных в этом разделе процедур вы сможете подготовить серверные серверы Skype для бизнеса Server 2019 перед перемещением центрального сервера управления.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-114">Use the procedures in this section to prepare the Skype for Business Server 2019 Front End Servers before you move the Central Management Server.</span></span>
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="fd7ad-115">Подготовка пула переднего плана Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="fd7ad-115">To prepare an Enterprise Edition Front End pool</span></span>

1. <span data-ttu-id="fd7ad-116">В пуле внешних интерфейсов в Skype для бизнеса Server 2019 Enterprise Edition, где вы хотите переместить сервер центрального управления, войдите в систему с компьютера, на котором установлена консоль управления Skype для бизнеса Server, в качестве участника группы **рткуниверсалсерверадминс** .</span><span class="sxs-lookup"><span data-stu-id="fd7ad-116">On the Skype for Business Server 2019 Enterprise Edition Front End pool where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="fd7ad-117">Кроме того, необходимо иметь права и разрешения администратора базы данных SQL Server для базы данных, в которой вы хотите установить хранилище Центрального управления.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-117">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span> 
    
2. <span data-ttu-id="fd7ad-118">Откройте консоль управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-118">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="fd7ad-119">Чтобы создать новое хранилище Central Management в базе данных SQL Server в Skype для бизнеса Server 2019, в командной консоли Skype для бизнеса Server введите:</span><span class="sxs-lookup"><span data-stu-id="fd7ad-119">To create the new Central Management store in the Skype for Business Server 2019 SQL Server database, in the Skype for Business Server Management Shell, type:</span></span>
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. <span data-ttu-id="fd7ad-120">Убедитесь в том, что **запущена**служба **клиентской службы Skype для бизнеса Server** .</span><span class="sxs-lookup"><span data-stu-id="fd7ad-120">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="fd7ad-121">Подготовка сервера переднего плана Standard Edition к выпуску</span><span class="sxs-lookup"><span data-stu-id="fd7ad-121">To prepare a Standard Edition Front End Server</span></span>

1. <span data-ttu-id="fd7ad-122">На сервере переднего плана Skype для бизнеса Server 2019 Standard Edition, на котором вы хотите переместить сервер центрального управления, войдите в систему с компьютера, на котором установлена консоль управления Skype для бизнеса Server, в качестве участника группы **рткуниверсалсерверадминс** .</span><span class="sxs-lookup"><span data-stu-id="fd7ad-122">On the Skype for Business Server 2019 Standard Edition Front End Server where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> 
    
2. <span data-ttu-id="fd7ad-123">Запустите мастер развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-123">Open the Skype for Business Server Deployment Wizard.</span></span>
    
3. <span data-ttu-id="fd7ad-124">В мастере развертывания Skype для бизнеса Server нажмите кнопку **подготовить первый сервер Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-124">In the Skype for Business Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>
    
4. <span data-ttu-id="fd7ad-125">На странице **выполнение команд** SQL Server Express установлен в качестве центрального сервера управления.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-125">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="fd7ad-126">Создаются необходимые правила брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-126">Necessary firewall rules are created.</span></span> <span data-ttu-id="fd7ad-127">После завершения установки базы данных и необходимого программного обеспечения нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-127">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fd7ad-128">Начальная установка может занять некоторое время и не отменять заметные обновления экрана сводки вывода команды.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-128">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="fd7ad-129">Это происходит из-за установки SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-129">This is due to the installation of SQL Server Express.</span></span> <span data-ttu-id="fd7ad-130">Если вам нужно наблюдать за установкой базы данных, используйте диспетчер задач для наблюдения за настройкой.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-130">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span> 
  
5. <span data-ttu-id="fd7ad-131">Чтобы создать новое хранилище Central Management на сервере переднего плана Skype для бизнеса Server 2019 Standard Edition, в командной консоли Skype для бизнеса Server введите:</span><span class="sxs-lookup"><span data-stu-id="fd7ad-131">To create the new Central Management store on the Skype for Business Server 2019 Standard Edition Front End Server, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. <span data-ttu-id="fd7ad-132">Убедитесь в том, что **запущена**служба **клиентской службы Skype для бизнеса Server** .</span><span class="sxs-lookup"><span data-stu-id="fd7ad-132">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="fd7ad-133">Перемещение устаревшего сервера центра администрирования в Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="fd7ad-133">To move the legacy installs Central Management Server to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="fd7ad-134">На сервере 2019 Skype для бизнеса Server, который будет основным сервером управления, войдите в систему с компьютера, на котором установлена командная консоль Skype для Business Server, в качестве участника группы **рткуниверсалсерверадминс** .</span><span class="sxs-lookup"><span data-stu-id="fd7ad-134">On the Skype for Business Server 2019 server that will be the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="fd7ad-135">Кроме того, необходимо иметь права и разрешения администратора базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-135">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="fd7ad-136">Откройте командную консоль управления Skype для бизнеса Server (Запуск от имени администратора).</span><span class="sxs-lookup"><span data-stu-id="fd7ad-136">Open Skype for Business Server Management Shell (run as administrator).</span></span>
    
3. <span data-ttu-id="fd7ad-137">В командной консоли Skype для бизнеса Server введите:</span><span class="sxs-lookup"><span data-stu-id="fd7ad-137">In the Skype for Business Server Management Shell, type:</span></span> 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > <span data-ttu-id="fd7ad-138">Если `Enable-CsTopology` это не помогло, устраните проблему, так как она не может завершиться, прежде чем продолжить.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-138">If `Enable-CsTopology` is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="fd7ad-139">Если **параметр Enable-кстопологи** не прошел успешно, перемещение завершится сбоем, и ваша топология может остаться в состоянии, в котором нет центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-139">If **Enable-CsTopology** is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span> 
  
4. <span data-ttu-id="fd7ad-140">На сервере переднего плана или пуле из Skype для бизнеса Server 2019 в командной консоли Skype для бизнеса Server введите:</span><span class="sxs-lookup"><span data-stu-id="fd7ad-140">On the Skype for Business Server 2019 Front End Server or Front End pool, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. <span data-ttu-id="fd7ad-141">Консоль управления в Skype для бизнеса Server отображает серверы, хранилища файлов, хранилища баз данных и точки соединения служб для текущего состояния и предложенное состояние.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-141">Skype for Business Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="fd7ad-142">Внимательно прочтите информацию и подтвердите, что это предполагаемый источник и назначение.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-142">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="fd7ad-143">Введите **Y** , чтобы продолжить, или **N** , чтобы прервать перемещение.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-143">Type **Y** to continue, or **N** to stop the move.</span></span> 
    
6. <span data-ttu-id="fd7ad-144">Проверьте все предупреждения и ошибки, созданные командой **Move-ксманажементсервер** , и устраните их.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-144">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span> 
    
7. <span data-ttu-id="fd7ad-145">На сервере 2019 Skype для бизнеса Server откройте мастер развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-145">On the Skype for Business Server 2019 server, open the Skype for Business Server Deployment Wizard.</span></span> 
    
8. <span data-ttu-id="fd7ad-146">В мастере развертывания Skype для бизнеса Server нажмите кнопку **установить или обновить серверную систему Skype**для бизнеса, выберите **Шаг 2: Настройка или удаление компонентов Skype для бизнеса Server**, нажмите кнопку **Далее**, просмотрите сводку и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-146">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
9. <span data-ttu-id="fd7ad-147">На сервере с установленной старой версии откройте мастер развертывания.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-147">On the legacy install server, open the Deployment Wizard.</span></span> 
    
10. <span data-ttu-id="fd7ad-148">В мастере развертывания Skype для бизнеса Server нажмите кнопку **установить или обновить серверную систему Skype**для бизнеса, выберите **Шаг 2: Настройка или удаление компонентов Skype для бизнеса Server**, нажмите кнопку **Далее**, просмотрите сводку и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-148">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
11. <span data-ttu-id="fd7ad-149">Перезагрузите сервер 2019 в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-149">Reboot the Skype for Business Server 2019 server.</span></span> <span data-ttu-id="fd7ad-150">Это необходимо из-за изменения членства в группе на доступ к базе данных центрального сервера управления.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-150">This is required because of a group membership change to access Central Management Server database.</span></span>
    
12. <span data-ttu-id="fd7ad-151">Чтобы убедиться в том, что репликация выполняется с новым хранилищем центрального управления, в командной консоли Skype для бизнеса Server введите:</span><span class="sxs-lookup"><span data-stu-id="fd7ad-151">To confirm that replication with the new Central Management store is occurring, in the Skype for Business Server Management Shell, type:</span></span> 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > <span data-ttu-id="fd7ad-152">Для обновления всех текущих реплик репликации может потребоваться некоторое время.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-152">The replication may take some time to update all current replicas.</span></span> 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a><span data-ttu-id="fd7ad-153">Удаление файлов из хранилища для централизованного управления установкой из устаревшего режима после перемещения</span><span class="sxs-lookup"><span data-stu-id="fd7ad-153">To remove legacy install Central Management store files after a move</span></span>

1. <span data-ttu-id="fd7ad-154">На сервере, где установлен старый сервер, войдите в систему с компьютера, на котором установлена консоль управления Skype для бизнеса Server, в качестве участника группы **рткуниверсалсерверадминс** .</span><span class="sxs-lookup"><span data-stu-id="fd7ad-154">On the legacy install server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="fd7ad-155">Кроме того, необходимо иметь права и разрешения администратора базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-155">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="fd7ad-156">Открытие командной консоли Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="fd7ad-156">Open Skype for Business Server Management Shell</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="fd7ad-157">Не продолжайте удалять предыдущие файлы базы данных, пока репликация не будет завершена и является стабильной.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-157">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="fd7ad-158">Если вы удалите файлы перед выполнением репликации, процесс репликации будет прерван, а новый сервер центрального управления останется в неизвестном состоянии.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-158">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="fd7ad-159">С помощью командлета **Get-ксманажементсторерепликатионстатус** можно подтвердить состояние репликации.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-159">Use the cmdlet **Get-CsManagementStoreReplicationStatus** to confirm the replication status.</span></span> 
  
3. <span data-ttu-id="fd7ad-160">Чтобы удалить файлы базы данных центрального хранилища из сервера централизованного управления установкой из устаревшего центра управления, введите:</span><span class="sxs-lookup"><span data-stu-id="fd7ad-160">To remove the Central Management store database files from the legacy install Central Management Server, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    <span data-ttu-id="fd7ad-161">Например:</span><span class="sxs-lookup"><span data-stu-id="fd7ad-161">For example:</span></span>
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    <span data-ttu-id="fd7ad-162">Там, где _ \<полное доменное\> имя SQL Server_ является либо конечным сервером установки на начальном сервере в развертывании Enterprise Edition, либо полным доменным именем сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-162">Where the  _\<FQDN of SQL Server\>_ is either the legacy install Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span> 
    

