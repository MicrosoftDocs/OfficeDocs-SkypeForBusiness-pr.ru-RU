---
title: 'Lync Server 2013: процедура отработки отказа для пула переднего плана ABC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End pool ABC failover procedure
ms:assetid: 67763ad3-6796-45eb-a486-901f21ac1a95
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945635(v=OCS.15)
ms:contentKeyID: 51541486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f60ded6539f6d984662449562d0f978e98dc3078
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206555"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="front-end-pool-abc-failover-procedure-in-lync-server-2013"></a><span data-ttu-id="1b3a6-102">Процедура отработки отказа для пула переднего плана ABC в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b3a6-102">Front End pool ABC failover procedure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b3a6-103">_**Последнее изменение темы:** 2014-05-22_</span><span class="sxs-lookup"><span data-stu-id="1b3a6-103">_**Topic Last Modified:** 2014-05-22_</span></span>

<span data-ttu-id="1b3a6-104">Выполните следующие действия, чтобы выполнить процедуру отработки отказа ABC.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-104">Use the following steps to perform the ABC failover procedure.</span></span> <span data-ttu-id="1b3a6-105">Эта процедура содержит подробное описание каждого этапа, а затем команды и командлеты, которые необходимо выполнить для каждого этапа.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-105">This procedure contains a high-level description of each step, followed by commands and cmdlets to be run for each step.</span></span>

<span data-ttu-id="1b3a6-106">Чтобы запустить командлеты, откройте командную консоль Lync Server с помощью команды Запуск от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-106">To run the cmdlets, open a Lync Server Management Shell using Run as Administrator.</span></span>

<div>

## <a name="to-perform-an-abc-failover"></a><span data-ttu-id="1b3a6-107">Выполнение отработки отказа ABC</span><span class="sxs-lookup"><span data-stu-id="1b3a6-107">To Perform an ABC Failover</span></span>

1.  <span data-ttu-id="1b3a6-108">Проверьте, является ли пул A узлом для центрального сервера управления (CMS).</span><span class="sxs-lookup"><span data-stu-id="1b3a6-108">Check whether the pool A is the host for the Central Management Server (CMS).</span></span>
    
      - <span data-ttu-id="1b3a6-109">Выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="1b3a6-109">Run the following cmdlet:</span></span>
        
            Get-CsService -CentralManagement
        
        <span data-ttu-id="1b3a6-110">Если поле Identity активного сервера CMS указывает на полное доменное имя пула A, то сначала выполните шаги 2 и 3, чтобы сначала выполнить отработку отказа на центральном сервере управления.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-110">If the Identity field of the active CMS points to the fully qualified domain name (FQDN) of Pool A, then you use steps 2 and 3 of this procedure to fail over the Central Management Server first.</span></span> <span data-ttu-id="1b3a6-111">В противном случае перейдите к шагу 4.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-111">Otherwise, skip to step 4.</span></span>

2.  <span data-ttu-id="1b3a6-112">Отработка отказа для сервера CMS в пул B в режиме аварийного восстановления путем запуска следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="1b3a6-112">Fail over the CMS to Pool B in disaster recovery mode by running the following cmdlet:</span></span>
    
        Invoke-CsManagementServerFailover -BackupSqlServerFqdn <Pool B BE FQDN> -BackupSqlInstanceName <Pool B BE instance name> [-BackupMirrorSqlServerFqdn <Pool B Mirror BE FQDN> -BackupMirrorSqlInstanceName <Pool B Mirror BE Instance name>] -Force -Verbose
    
    <span data-ttu-id="1b3a6-113">После этого мы рекомендуем переместить CMS из пула б в другой существующий связанный пул для дополнительной устойчивости.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-113">After you do this, we recommend that you move the CMS from pool B to another existing paired pool for extra resiliency.</span></span> <span data-ttu-id="1b3a6-114">Дополнительные сведения см. в статье [Move – CsManagementServer](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)..</span><span class="sxs-lookup"><span data-stu-id="1b3a6-114">For details, see [Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)..</span></span>

3.  <span data-ttu-id="1b3a6-115">Если пул A содержит CMS, импортируйте конфигурацию LIS из пула а в базу данных LIS (LIS. mdf) пула.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-115">If Pool A contains CMS, import the LIS configuration from pool A into pool B’s LIS database (Lis.mdf).</span></span> <span data-ttu-id="1b3a6-116">Это будет работать только в том случае, если вы регулярно создаете резервную копию данных LIS.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-116">This will work only if you have been backing up LIS data on a regular basis.</span></span> <span data-ttu-id="1b3a6-117">Чтобы импортировать конфигурацию LIS, выполните следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="1b3a6-117">To import the LIS configuration, run the following cmdlets:</span></span>
    
        Import-CsLisConfiguration -FileName <String> 
        Publish-CsLisConfiguration

4.  <span data-ttu-id="1b3a6-118">Импортируйте резервные копии рабочих процессов службы группы ответа Lync Server из пула A в пул B.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-118">Import backed-up Lync Server Response Group service workflows from pool A into pool B.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1b3a6-119">В настоящее время командлету <STRONG>Import-CsRgsConfiguration</STRONG> требуется, чтобы имена очередей и рабочих процессов в пуле A отличались от имен очередей и рабочих процессов в пуле B. Если имена не отличаются, при выполнении командлета <STRONG>Import-CsRgsConfiguration</STRONG> возникает ошибка, и перед выполнением командлета <STRONG>Import-CsRgsConfiguration</STRONG> необходимо переименовать очереди и рабочие процессы в пуле B.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-119">Currently, the <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet requires that the queue and workflow names on pool A are distinct from the queue and workflow names on pool B. If the names are not distinct, you will get an error when running the <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet, and the queues and workflows will need to be renamed in pool B before proceeding with <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet.</span></span>

    
    </div>
    
    <span data-ttu-id="1b3a6-120">Существует два варианта импорта конфигурации группы ответа из пула A в пул B. Выбор варианта зависит от того, хотите ли вы перезаписать параметры уровня приложения для пула B с параметрами уровня приложения в пуле A.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-120">You have two options for importing the Response Group configuration from pool A to pool B. Which option you use depends on whether you want to overwrite the application-level settings of pool B with the application-level settings in pool A.</span></span>
    
      - <span data-ttu-id="1b3a6-121">Если вы хотите перезаписать параметры пула в, выполните командлет **Import – CsRgsConfiguration** с параметром **реплацеексистингсеттингс** :</span><span class="sxs-lookup"><span data-stu-id="1b3a6-121">If you want to overwrite the Pool B settings, run the **Import-CsRgsConfiguration** cmdlet with the **ReplaceExistingSettings** option:</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - <span data-ttu-id="1b3a6-122">Если вы не хотите перезаписывать параметры пула B, используйте командлет **Import – CsRgsConfiguration** без параметра **реплацеексистингсеттингс** .</span><span class="sxs-lookup"><span data-stu-id="1b3a6-122">If you do not want to overwrite the Pool B settings, use the **Import-CsRgsConfiguration** cmdlet without the **ReplaceExistingSettings** option.</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="1b3a6-123">Имейте в виду, что если вы не хотите перезаписывать параметры уровня приложения для резервного пула (пула б) с параметрами основного пула (Pool A), то параметры уровня приложения пула A будут потеряны при потере пула A, так как приложение группы ответа может Сохраните только один набор параметров уровня приложения для каждого пула.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-123">Keep in mind that if you do not want to overwrite the application-level settings of the backup pool (pool B) with the settings of the primary pool (pool A), pool A’s application-level settings will be lost if pool A is lost, because the Response Group application can store only one set of application-level settings per pool.</span></span> <span data-ttu-id="1b3a6-124">При развертывании Pool C для замены пула A параметры на уровне приложения должны быть перенастроены, включая звуковой файл по умолчанию для хранения музыки.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-124">When pool C is deployed to replace pool A, the application-level settings must be reconfigured, including the default music-on-hold audio file.</span></span>

    
    </div>

5.  <span data-ttu-id="1b3a6-125">Убедитесь, что импорт конфигурации группы ответа выполнен успешно, выполнив следующие командлеты, чтобы отобразить импортированные группы ответа.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-125">Verify that the Response Group configuration import was successful by running the following cmdlets to display the imported response groups.</span></span> <span data-ttu-id="1b3a6-126">Обратите внимание на то, что импортированные группы ответа по-прежнему принадлежат пулу A.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-126">Note that the imported response groups are still owned by pool A.</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"

6.  <span data-ttu-id="1b3a6-127">Для неназначенных номеров переместите диапазоны неназначенных номеров, которые используют "извещение", в качестве выбранной службы объявлений из пула A в пул B. Для этого выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-127">For Unassigned Numbers, move the Unassigned Number ranges that are using "Announcement" as the selected announcement service from pool A to pool B. To do so:</span></span>
    
      - <span data-ttu-id="1b3a6-128">Повторно создайте все объявления, развернутые в пуле A, в пуле B. Если при развертывании объявлений в пуле A использовались какие бы то ни были звуковые файлы, эти файлы понадобятся для повторного создания объявлений в пуле B. Чтобы повторно создать объявления в пуле б, используйте командлеты **New – ксаннаунцемент** с пулом B в качестве родительской службы.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-128">Re-create all announcements that were deployed in pool A on pool B. If any audio files were used when deploying the announcements in pool A, these files will be needed to re-create the announcements in pool B. To re-create the announcements in pool B, use the **New-CsAnnouncement** cmdlets, with pool B as the Parent service.</span></span>
    
      - <span data-ttu-id="1b3a6-129">Переназначьте все диапазоны неназначенных номеров, которые нацелены на оповещение в пуле а, в новые развернутые объявления в пуле б. выполните следующий командлет для каждого диапазона неназначенных номеров, предназначенного для объявления пула а:</span><span class="sxs-lookup"><span data-stu-id="1b3a6-129">Retarget all the Unassigned Number ranges that are targeting an announcement in pool A to the newly deployed announcements in pool B. Run the following cmdlet for every Unassigned Number range targeting an announcement of pool A:</span></span>
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool B FQDN>" -AnnouncementName "<New Announcement in pool B>"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1b3a6-130">Этот шаг не нужен для диапазонов неназначенных номеров, в которых выбрана служба обмена единой системой обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-130">This step is not required for unassigned number ranges that use "Exchange UM" as the selected announcement service.</span></span>

    
    </div>

7.  <span data-ttu-id="1b3a6-131">Отработка отказа пула A to Pool B в режиме аварийного восстановления (DR), выполнив следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="1b3a6-131">Fail over Pool A to Pool B in Disaster Recovery (DR) mode, by running the following cmdlet:</span></span>
    
        Invoke-CsPoolFailover -PoolFqdn <Pool A FQDN> -DisasterMode

8.  <span data-ttu-id="1b3a6-132">Создать пул C, но не запускать службы в пуле C.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-132">Build pool C, but do not start any services on pool C.</span></span>
    
    <span data-ttu-id="1b3a6-133">Обратите внимание, что это действие можно выполнить одновременно с действиями 5 и 6.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-133">Note that this step can be carried out concurrently with steps 5 and 6.</span></span>

9.  <span data-ttu-id="1b3a6-134">Принудительное перемещение пользователей, размещенных в пуле а, в пул C с помощью следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="1b3a6-134">Force users homed on pool A to move to pool C by running the following cmdlet:</span></span>
    
        Get-csuser -Filter {RegistrarPool -eq "<Pool A FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force
    
    <span data-ttu-id="1b3a6-135">На этом шаге пользователи, размещенные в пуле, начнут испытывать сбой службы.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-135">At this point, users homed on pool A will begin to experience a service outage.</span></span> <span data-ttu-id="1b3a6-136">Этот сбой будет продолжен до этапа 16, после чего службы будут запущены в пуле C.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-136">This outage will continue until step 16, at which point services are started on pool C.</span></span>

10. <span data-ttu-id="1b3a6-137">Принудительно переместите каталог конференций пула A в пул C, выполнив следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="1b3a6-137">Force the conference directory of pool A to move to pool C by running the following cmdlet:</span></span>
    
        Move-CsConferenceDirectory -Identity <Conference Directory ID of Pool A> -TargetPool <Pool C FQDN> -Force

11. <span data-ttu-id="1b3a6-138">Принудительно переместите объект контакта автосекретаря конференц-связи (CAA) из пула A в пул C, выполнив следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="1b3a6-138">Force the Conference Auto Attendant (CAA) Contact Object to move from pool A to pool C by running the following cmdlet:</span></span>
    
        Move-csApplicationEndpoint -Identity "<Pool A CAA Uri>" -targetApplicationPool <Pool C FQDN> -force

12. <span data-ttu-id="1b3a6-139">Скопируйте содержимое конференций из пула B в пул C.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-139">Copy conference content from pool B to pool C.</span></span>

13. <span data-ttu-id="1b3a6-140">Экспортируйте данные пользователя из пула б и импортируйте данные пользователя в пул C, выполнив следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="1b3a6-140">Export user data from pool B and import the user data into pool C by running the following cmdlets:</span></span>
    
        Export-CsUserData -PoolFqdn <Pool B Fqdn> -FileName <String>
        Import-CsUserData -PoolFqdn <Pool C Fqdn> -FileName <String>

14. <span data-ttu-id="1b3a6-141">Восстановите резервные копии данных приложения парковки вызовов из пула A в пул C и назначьте Диапазоны орбит парковки вызовов для пула а в пул C.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-141">Restore backed-up Call Park application data from pool A into pool C and assign the Call Park orbit ranges of pool A to pool C.</span></span>
    
      - <span data-ttu-id="1b3a6-142">С помощью панели управления Lync Server или командной консоли Lync Server вы можете переназначить диапазон орбиты для парковки вызовов пула A в пул C.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-142">You can reassign a Call Park orbit range of pool A to pool C either through the Lync Server Control Panel or the Lync Server Management Shell.</span></span> <span data-ttu-id="1b3a6-143">Для командной консоли Lync Server выполните следующий командлет для каждого диапазона орбит парковки вызовов, назначенного пулу A (Обратите внимание, что параметр Identity указывает на диапазоны орбит парковки вызовов, принадлежащие пулу A):</span><span class="sxs-lookup"><span data-stu-id="1b3a6-143">For the Lync Server Management Shell, run the following cmdlet for every Call Park orbit range assigned to pool A (note that the Identity parameter refers to the Call Park Orbit Ranges that belong to pool A):</span></span>
        
            Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Pool C FQDN>"
    
      - <span data-ttu-id="1b3a6-144">Если настроенная музыка заблокирована для парковки вызовов в пуле A, восстановите настроенный в пуле C файл музыки для парковки на удержание вызовов.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-144">If a customized music-on-hold has been configured for Call Park in pool A, restore the Call Park customized music-on-hold file in pool C.</span></span>
        
            Xcopy <Source> <Destination: Pool C CPS File Store Path>
        
        <span data-ttu-id="1b3a6-145">Например:</span><span class="sxs-lookup"><span data-stu-id="1b3a6-145">For example:</span></span>
        
            Xcopy "Source Path" "<Pool C File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"
    
      - <span data-ttu-id="1b3a6-146">Наконец, перенастройте параметры парковки вызовов в пуле C с помощью командлета **Set – CsCpsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="1b3a6-146">Finally, reconfigure the Call Park settings on pool C by using the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="1b3a6-147">Приложение парковки вызовов может хранить только один набор параметров и один настроенный звуковой файл музыки при удержании на пул, и эти параметры не будут создаваться и сохраняться в случае аварии.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-147">The Call Park application can store only one set of settings and one customized music-on-hold audio file per pool, and these settings are not backed up or preserved in the event of a disaster.</span></span>

15. <span data-ttu-id="1b3a6-148">Если следующий пул прыжков для сохраняемого чата указывает на пул A, сделайте и опубликуйте изменения топологии, чтобы сервер следующего прыжка указывал на пул C.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-148">If the next hop pool for Persistent Chat is pointing to pool A, make and publish topology changes so that the next hop server points to pool C.</span></span>
    
      - <span data-ttu-id="1b3a6-149">В построителе топологий измените пул сохраняемого чата, чтобы он ссылался на пул C в качестве следующего прыжка.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-149">In Topology Builder, change the Persistent Chat pool to point to Pool C as its next hop.</span></span> <span data-ttu-id="1b3a6-150">Для этого щелкните правой кнопкой мыши пул сохраняемого чата, перейдите на вкладку **Общие** , а затем введите имя пула C в поле **пул следующего прыжка**.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-150">To do so, right-click on the Persistent Chat pool, then click the **General** tab, and then type the name of Pool C in **Next Hop Pool**.</span></span>
    
      - <span data-ttu-id="1b3a6-151">Запустите службы из пула C, выполнив следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="1b3a6-151">Start services on pool C by running the following cmdlet:</span></span>
        
            Start-csWindowsService
    
    <span data-ttu-id="1b3a6-152">На этом шаге сбой службы завершается для пользователей, изначально размещенных в пуле A.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-152">At this point, the service outage ends for users originally homed on pool A.</span></span>

16. <span data-ttu-id="1b3a6-153">Экспортируйте рабочие процессы службы группы ответа Lync Server из пула б, владельцем которых является пул A, для импорта в пул C, выполнив следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="1b3a6-153">Export Lync Server Response Group service workflows from pool B owned by pool A for import into pool C by running the following cmdlet:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" 

17. <span data-ttu-id="1b3a6-154">Импортируйте рабочие процессы службы группы ответа Lync Server в пул C из пула B.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-154">Import Lync Server Response Group service workflows into pool C from pool B.</span></span>
    
    <span data-ttu-id="1b3a6-155">Существует два варианта импорта конфигурации группы ответа из пула б в пул C. Выбор варианта зависит от того, хотите ли вы перезаписать параметры уровня приложения для пула C с параметрами уровня приложения в пуле B.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-155">You have two options are for importing the Response Group configuration from pool B to pool C. Which option you use depends on whether you want to overwrite the application-level settings of pool C with the application-level settings in pool B.</span></span>
    
      - <span data-ttu-id="1b3a6-156">Если вы хотите перезаписать параметры пула в C, выполните командлет **Import – CsRgsConfiguration** с параметром **реплацеексистингсеттингс** :</span><span class="sxs-lookup"><span data-stu-id="1b3a6-156">If you want to overwrite the Pool C settings, run the **Import-CsRgsConfiguration** cmdlet with the **ReplaceExistingSettings** option:</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool C FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - <span data-ttu-id="1b3a6-157">Если вы не хотите перезаписывать параметры пула в C, используйте командлет **Import – CsRgsConfiguration** без параметра **реплацеексистингсеттингс** .</span><span class="sxs-lookup"><span data-stu-id="1b3a6-157">If you do not want to overwrite the Pool C settings, use the **Import-CsRgsConfiguration** cmdlet without the **ReplaceExistingSettings** option.</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="1b3a6-158">Имейте в виду, что если вы не хотите перезаписывать параметры уровня приложения для пула C с параметрами резервного пула (пула B), то параметры уровня приложения пула B будут потеряны, так как приложение группы ответа может хранить только один набор уровня приложения. параметры для каждого пула.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-158">Keep in mind that if you do not want to overwrite the application-level settings of Pool C with the settings of the backup pool (pool B), pool B’s application-level settings will be lost because the Response Group application can store only one set of application-level settings per pool.</span></span>

    
    </div>

18. <span data-ttu-id="1b3a6-159">Убедитесь, что импорт конфигурации группы ответа выполнен успешно, выполнив следующие командлеты, чтобы отобразить группы ответа, импортированные в пул C.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-159">Verify that the Response Group configuration import was successful by running the following cmdlets to display the response groups that have been imported to Pool C.</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
         Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll

19. <span data-ttu-id="1b3a6-160">После проверки импортированной конфигурации в пуле C удалите группы ответа, принадлежащие основному пулу из пула B. Это снизит время простоя групп ответа.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-160">When the imported configuration has been verified in pool C, remove the response groups owned by the primary pool from pool B. This will minimize the downtime of the response groups.</span></span>
    
    <span data-ttu-id="1b3a6-161">На этом этапе создается новый файл с экспортированной конфигурацией, после чего он удаляется из пула B.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-161">This step creates a new file with the exported configuration, and then removes the file from pool B.</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration

20. <span data-ttu-id="1b3a6-162">Переместить в пул C диапазоны неназначенных номеров, перемещенных из пула A в пул B.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-162">Move to pool C the Unassigned Number ranges that were moved from pool A to pool B.</span></span>
    
      - <span data-ttu-id="1b3a6-163">Повторное создание в пуле с все объявления, которые были повторно созданы из пула A в пуле B. Если при развертывании извещений использовались какие бы то ни были звуковые файлы, их необходимо будет использовать для повторного создания объявлений в пуле C. Чтобы повторно создать объявления в пуле C, используйте командлеты **New – ксаннаунцемент** с пулом C в качестве родительской службы.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-163">Re-create in pool C all announcements that were re-created from pool A in pool B. If any audio files were used when deploying the announcements to be moved, you will need to use these files to re-create the announcements in pool C. To re-create the announcements in pool C, use the **New-CsAnnouncement** cmdlets, with pool C as the Parent service.</span></span>
    
      - <span data-ttu-id="1b3a6-164">Перенаправлять в пул C все диапазоны неназначенных номеров, которые были перенацелены из пула A в пул б. выполните следующий командлет для каждого диапазона неназначенных номеров, которые необходимо переадресовать:</span><span class="sxs-lookup"><span data-stu-id="1b3a6-164">Retarget to pool C all the unassigned number ranges that were retargeted from pool A to pool B. Run the following cmdlet for every Unassigned Number range that needs to be retargeted:</span></span>
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool C FQDN>" -AnnouncementName "<New Announcement in pool C>"
    
      - <span data-ttu-id="1b3a6-165">Необязательно Удалить из пула б объявления, которые были повторно созданы в пуле C, если они больше не используются в пуле B. Чтобы удалить объявления, используйте командлет **Remove – ксаннаунцемент** .</span><span class="sxs-lookup"><span data-stu-id="1b3a6-165">(Optional) Remove from pool B the announcements that were re-created in pool C if they are no longer in use in pool B. To remove announcements, use the **Remove-CsAnnouncement** cmdlet.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="1b3a6-166">Этот шаг не нужен для диапазонов неназначенных номеров, в которых служба извещения использует "Единая система обмена сообщениями".</span><span class="sxs-lookup"><span data-stu-id="1b3a6-166">This step is not required for unassigned number ranges that use "Exchange UM" as the announcement service.</span></span>

        
        </div>

21. <span data-ttu-id="1b3a6-167">Очистите данные пользователя пула A в пуле б, выполнив следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="1b3a6-167">Clean up user data of pool A in pool B by running the following cmdlet:</span></span>
    
        Remove-CsUserStoreBackupData -PoolFqdn <Pool B FQDN> -Verbose

22. <span data-ttu-id="1b3a6-168">Выполните указанные ниже действия в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-168">Do the following in Topology Builder:</span></span>
    
      - <span data-ttu-id="1b3a6-169">Несвязанный пул A и пул B. Свяжите пул б и пул C. Затем удалите пул A из топологии и опубликуйте его.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-169">Unpair pool A and pool B. Pair pool B and pool C. Then remove Pool A from the topology and publish it.</span></span> <span data-ttu-id="1b3a6-170">Для этого:</span><span class="sxs-lookup"><span data-stu-id="1b3a6-170">To do so:</span></span>
        
          - <span data-ttu-id="1b3a6-171">В построителе топологий щелкните пул б правой кнопкой мыши и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-171">In Topology Builder, right-click on Pool B, and then click **Edit Properties**.</span></span>
        
          - <span data-ttu-id="1b3a6-172">Нажмите кнопку **устойчивости** на левой панели.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-172">Click **Resiliency** in the left pane.</span></span>
        
          - <span data-ttu-id="1b3a6-173">В поле под **сопоставленным резервным пулом**выберите пул C. Обратите внимание, что в поле выбора связанного резервного пула изначально отображается пул A, так как пул B был ранее связан с этим пулом.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-173">In the box below **Associated Backup Pool**, select Pool C. Note that the Associated Backup Pool selection box will initially display pool A, because pool B was previously associated with this pool.</span></span>
        
          - <span data-ttu-id="1b3a6-174">Выберите **Automatic failover and failback for Voice** (Автоматическая отработка отказа и восстановление размещения для голосовой связи) и нажмите кнопку **OK** (ОК).</span><span class="sxs-lookup"><span data-stu-id="1b3a6-174">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
            
            <span data-ttu-id="1b3a6-175">Теперь при просмотре сведений о данном пуле связанный с ним пул отображается на правой панели в области **Resiliency** (Устойчивость).</span><span class="sxs-lookup"><span data-stu-id="1b3a6-175">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span>
        
          - <span data-ttu-id="1b3a6-176">В дереве консоли щелкните правой кнопкой мыши пул A, а затем выберите команду Удалить.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-176">In the console tree, right-click pool A, and then click Delete.</span></span>
        
          - <span data-ttu-id="1b3a6-177">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-177">Publish the topology.</span></span>

23. <span data-ttu-id="1b3a6-178">Запустите приложение начальной загрузки в пуле C, чтобы установить приложение службы резервного копирования, а затем запустите приложение службы резервного копирования, выполнив следующие действия в папке Deployment локального компьютера в пуле C:</span><span class="sxs-lookup"><span data-stu-id="1b3a6-178">Run the bootstrapping application on pool C to install the backup service application, and then start the backup service application by running the following from the deployment folder on a local machine in pool C:</span></span>
    
        Run "%SYSTEMROOT%\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe"
        Start-CsWindowsService -name LyncBackup

24. <span data-ttu-id="1b3a6-179">Перезапустите приложение службы резервного копирования в пуле б, выполнив следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="1b3a6-179">Restart the backup service application on pool B by running the following cmdlets:</span></span>
    
        Stop-CsWindowsService -name LyncBackup
        Start-CsWindowsService -name LyncBackup

25. <span data-ttu-id="1b3a6-180">Если пул C является пулом Standard Edition (SE), а пул B имеет CMS, установите базу данных CMS вручную в пуле C, выполнив следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="1b3a6-180">If pool C is a Standard Edition (SE) Pool and pool B has CMS, install the CMS database manually on pool C by running the following cmdlet:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <Pool C FQDN> -SqlInstanceName rtc

26. <span data-ttu-id="1b3a6-181">Запустите службу резервного копирования, чтобы синхронизировать старое содержимое конференций из пула B с пулом C, созданным до совместной связи B и C, и для синхронизации нового контента конференций из пула C в пул B, который был создан после объединения групп C и до B и C.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-181">Invoke the backup service to sync old conferencing content from pool B to pool C that was generated before pairing B and C together, and to sync new conferencing content from pool C to pool B that was generated after starting pool C and before B and C were paired together.</span></span> <span data-ttu-id="1b3a6-182">Чтобы сделать это, выполните следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="1b3a6-182">To do so, run the following cmdlets:</span></span>
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool C FQDN>
        Invoke-CsBackupServiceSync -PoolFqdn <Pool B FQDN>

27. <span data-ttu-id="1b3a6-183">Для каждого устройства для обеспечения связи в филиале, сопоставленного с пулом A:</span><span class="sxs-lookup"><span data-stu-id="1b3a6-183">For each Survivable Branch Appliance X associated with pool A:</span></span>
    
      - <span data-ttu-id="1b3a6-184">Завершите работу SBA X, выполнив следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="1b3a6-184">Shut down SBA X by running the following cmdlet:</span></span>
        
            Stop-CsWindowsService
    
      - <span data-ttu-id="1b3a6-185">Создайте файл, содержащий список пользователей, размещенных на SBA X. Список потребуется, когда пользователи перемещаются обратно в SBA X на шаге 30.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-185">Create a file that contains a list of users homed on SBA X. The list will be needed when the users are moved back to SBA X in step 30.</span></span> <span data-ttu-id="1b3a6-186">Для этого выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="1b3a6-186">To do so, run the following cmdlet:</span></span>
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Export-Csv d:\sbaxusers.txt
    
      - <span data-ttu-id="1b3a6-187">Принудительное перемещение пользователей, размещенных на SBA X, в пул C с помощью следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="1b3a6-187">Force users homed on SBA X to move to pool C by running the following cmdlet:</span></span>
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force -Verbose
    
      - <span data-ttu-id="1b3a6-188">Обновите данные этих пользователей, выполнив следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="1b3a6-188">Update the data of these users by first running the following cmdlets:</span></span>
        
            Convert-csUserData -InputFile <Data file exported from PoolB> -OutputFile c:\Logs\ExportedUserData.xml -TargetVersionLync2010 
            $a=get-csuser -Filter {RegistrarPool -eq "FQDN of SBA X"} | select SipAddress
            foreach($x in $a) {$x.SipAddress.Substring(4) >> users.txt}
        
        <span data-ttu-id="1b3a6-189">Затем выполните следующий сценарий:</span><span class="sxs-lookup"><span data-stu-id="1b3a6-189">And then run this script:</span></span>
        
            $users=gc c:\logs\users.txt
            foreach ($user in $users)
            {
            Update-CsUserData -FileName c:\logs\exportedUserDAta.xml -UserFilter $user - 
            }
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="1b3a6-190">Отказ службы будет выполняться для пользователей, размещенных в устройства, связанных с пулом A до тех пор, пока эти пользователи не будут перемещены в пул C.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-190">A service outage will occur for users who are homed on SBAs that are associated with pool A until these users are moved to pool C.</span></span>

        
        </div>

28. <span data-ttu-id="1b3a6-191">В построителе топологий для каждого SBA X, ранее связанных с пулом A, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="1b3a6-191">In Topology Builder, for each SBA X previously associated with Pool A, do the following:</span></span>
    
      - <span data-ttu-id="1b3a6-192">Измените связь на Pool C. Для этого щелкните сайт филиала, разверните узел устройства для обеспечения связи или серверы для обеспечения связи в филиалах и выберите устройство для обеспечения связи в **филиалах**.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-192">Change the association to Pool C. To do so, click the branch site, expand the Survivable Branch Appliances or Servers node, and click **Survivable Branch Appliance**.</span></span> <span data-ttu-id="1b3a6-193">Затем выберите **интерфейсный пул, пул служб пользователя** , который будет подключаться к этому устройству для обеспечения связи в филиалах, как пул C, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-193">Then select the **Front End pool, User Services Pool** that this Survivable Branch Appliance will connect to as Pool C, and then click **Next**.</span></span>
    
      - <span data-ttu-id="1b3a6-194">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-194">Publish the topology.</span></span> <span data-ttu-id="1b3a6-195">Для этого в дереве консоли щелкните правой кнопкой мыши новое устройство для обеспечения связи в **филиалах**, выберите **топология**, а затем нажмите кнопку **опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-195">To do so, in the console tree, right-click the new **Survivable Branch Appliance**, click **Topology**, and then click **Publish**.</span></span>

29. <span data-ttu-id="1b3a6-196">Для каждого SBA X теперь связан с пулом C:</span><span class="sxs-lookup"><span data-stu-id="1b3a6-196">For each SBA X now associated with pool C:</span></span>
    
      - <span data-ttu-id="1b3a6-197">Запустите SBA X, выполнив следующий командлет на устройстве для обеспечения связи в филиалах:</span><span class="sxs-lookup"><span data-stu-id="1b3a6-197">Start SBA X by running the following cmdlet on the survivable branch appliance:</span></span>
        
            Start-CsWindowsService
    
      - <span data-ttu-id="1b3a6-198">Переместите пользователей, которые изначально были размещены в SBA X из пула C, в SBA X, выполнив следующий командлет.</span><span class="sxs-lookup"><span data-stu-id="1b3a6-198">Move users who were originally homed on SBA X from pool C to SBA X by running the following cmdlet.</span></span>
        
            Import-Csv d:\sbaxusers.txt | Move-CsUser -Target <SBA X FQDN> -Force

</div>

</div>

<span> </span>

</div>

</div>

</div>

