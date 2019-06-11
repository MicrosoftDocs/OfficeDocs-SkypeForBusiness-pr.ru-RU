---
title: 'Lync Server 2013: восстановление сервера, на котором размещается хранилище Центрального управления'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring the server hosting the Central Management store
ms:assetid: 3bd6c82c-07fb-4798-b8f9-e7c78a5a83d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202172(v=OCS.15)
ms:contentKeyID: 51541464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95696c682e7acfba32e4f9a2bfd71ba988f22243
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822449"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-the-server-hosting-the-central-management-store-in-lync-server-2013"></a><span data-ttu-id="078bc-102">Восстановление сервера, на котором размещается центральное хранилище для управления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="078bc-102">Restoring the server hosting the Central Management store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="078bc-103">_**Тема последнего изменения:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="078bc-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="078bc-104">В развертывании Lync Server есть единое центральное хранилище, копия которого реплицируется на каждый сервер, на котором запущена роль сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="078bc-104">A Lync Server deployment has a single Central Management store, a copy of which is replicated to each server running a Lync Server server role.</span></span> <span data-ttu-id="078bc-105">В этой статье описано, как восстановить сервер или сервер Standard Edition, на котором размещается хранилище Центрального управления.</span><span class="sxs-lookup"><span data-stu-id="078bc-105">This topic describes how to restore a Back End Server or Standard Edition server that hosts the Central Management store.</span></span>

<span data-ttu-id="078bc-106">Чтобы найти пул, в котором расположен центральный сервер управления, откройте конфигуратор топологии, выберите пункт **Lync Server**и просмотрите область справа на **центральном сервере управления**.</span><span class="sxs-lookup"><span data-stu-id="078bc-106">To find the pool where the Central Management Server is located, open Topology Builder, click **Lync Server**, and look in the right pane under **Central Management Server**.</span></span>

<span data-ttu-id="078bc-107">Если сервер, на котором размещается Центральный магазин, находится в зеркальной установке, а зеркальная база данных по-прежнему работает, мы рекомендуем создать резервную копию этого зеркального отражения, а затем выполнить полное восстановление для базы данных-источника и зеркальную базу данных с помощью этой резервной копии, следуя приведенной ниже процедуре восстановления.</span><span class="sxs-lookup"><span data-stu-id="078bc-107">If the Back End Server that hosts the Central Management store is in a mirrored setup and the mirror database is still functional, we recommend that you make a backup of this still-functioning mirror, and then perform a full restore on both the primary database and the mirror database, using this backup, by following the restoration procedure below.</span></span> <span data-ttu-id="078bc-108">Это необходимо, так как для обратного восстановления требуется изменить и опубликовать топологию, и это можно сделать только в том случае, если сервер CMS размещен на базе данных-источнике.</span><span class="sxs-lookup"><span data-stu-id="078bc-108">This is necessary because Back End restore requires modifying and publishing the topology, and this can be done only if the primary database hosting CMS is operational.</span></span> <span data-ttu-id="078bc-109">Также обратите внимание на то, что роли основной и зеркальной баз данных невозможно изменить, если топология не может быть опубликована.</span><span class="sxs-lookup"><span data-stu-id="078bc-109">Also note that the primary and mirror database roles cannot be interchanged if the topology cannot be published.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="078bc-110">Если сервер или сервер Standard Edition, на котором не размещено центральное хранилище управления, не удалось найти, ознакомьтесь со сведениями о восстановлении сервера <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">выпуска Enterprise Edition в Lync server 2013</A> или <A href="lync-server-2013-restoring-a-standard-edition-server.md">восстановлении стандартного сервера выпуска в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="078bc-110">If a Back End Server or Standard Edition server that does not host the Central Management store failed, see <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restoring an Enterprise Edition Back End Server in Lync Server 2013</A> or <A href="lync-server-2013-restoring-a-standard-edition-server.md">Restoring a Standard Edition server in Lync Server 2013</A>.</span></span> <span data-ttu-id="078bc-111">Если сервер, на котором размещен Центральный центр управления, находится в зеркальной конфигурации, а зеркальный сервер не прошел, ознакомьтесь со сведениями о <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">восстановлении зеркального сервера выпуска Enterprise Edition в Lync server 2013 — Mirror</A>.</span><span class="sxs-lookup"><span data-stu-id="078bc-111">If a Back End Server that hosts the Central Management store is in a mirrored configuration and only the mirror failed, see <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</A>.</span></span> <span data-ttu-id="078bc-112">В случае сбоя любого другого сервера ознакомьтесь со сведениями о <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">восстановлении рядового сервера выпуска Enterprise Edition в Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="078bc-112">If any other server failed, see <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restoring an Enterprise Edition member server in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="078bc-113">Прежде чем начать восстановление, мы рекомендуем использовать копию системы с изображением.</span><span class="sxs-lookup"><span data-stu-id="078bc-113">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="078bc-114">Вы можете использовать это изображение как точку отката, если что-то пойдет не так во время восстановления.</span><span class="sxs-lookup"><span data-stu-id="078bc-114">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="078bc-115">После установки операционной системы и сервера SQL Server вы можете использовать копию изображения, а также восстановить или подать заявку на сертификаты.</span><span class="sxs-lookup"><span data-stu-id="078bc-115">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-the-central-management-store"></a><span data-ttu-id="078bc-116">Восстановление хранилища центрального управления</span><span class="sxs-lookup"><span data-stu-id="078bc-116">To restore the Central Management store</span></span>

1.  <span data-ttu-id="078bc-117">Начните с чистого или нового сервера с таким же полным доменным именем (FQDN), как и у компьютера, на котором произошел сбой, установите операционную систему, а затем восстановите или порегистрируйте сертификаты.</span><span class="sxs-lookup"><span data-stu-id="078bc-117">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="078bc-118">Следуйте инструкциям по развертыванию сервера в своей организации, чтобы выполнить этот шаг.</span><span class="sxs-lookup"><span data-stu-id="078bc-118">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="078bc-119">Войдите в свою учетную запись пользователя, которая входит в группу Рткуниверсалсерверадминс и локальную группу администраторов, войдя на сервер, который вы хотите восстановить.</span><span class="sxs-lookup"><span data-stu-id="078bc-119">From a user account that is a member of the RTCUniversalServerAdmins group and the Local Administrators group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="078bc-120">Если вы восстанавливаете Стандартный сервер выпуска, восстановите хранилище файлов, скопировав соответствующее хранилище файлов из $Backup в расположение хранилища файлов на сервере, а затем предоставьте доступ к папке.</span><span class="sxs-lookup"><span data-stu-id="078bc-120">If you are restoring a Standard Edition server, restore the File Store by copying the appropriate File Store from $Backup to the File Store location on the server, and then share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="078bc-121">Путь и имя файла для восстановленного хранилища файлов должны совпадать с заархивированным хранилищем файлов, чтобы компоненты, использующие эти файлы, могли получать к ним доступ.</span><span class="sxs-lookup"><span data-stu-id="078bc-121">The path and file name for the restored File Store should be exactly the same as the backed up File Store so that components that use the files can access them.</span></span>

    
    </div>

4.  <span data-ttu-id="078bc-122">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="078bc-122">Do one of the following:</span></span>
    
      - <span data-ttu-id="078bc-123">Если вы устанавливаете сервер Standard Edition, перейдите в папку установки Lync Server или мультимедиа, а затем запустите мастер развертывания Lync Server, расположенный на странице \\Setup\\\\. exe.</span><span class="sxs-lookup"><span data-stu-id="078bc-123">If you are installing a Standard Edition server, browse to the Lync Server installation folder or media, and then start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="078bc-124">В мастере развертывания нажмите кнопку **подготовить первый сервер Standard Edition** и следуйте указаниям мастера, чтобы установить хранилище Центрального управления.</span><span class="sxs-lookup"><span data-stu-id="078bc-124">In the Deployment Wizard, click **Prepare first Standard Edition server** and follow the wizard to install the Central Management store.</span></span>
    
      - <span data-ttu-id="078bc-125">Если вы устанавливаете сервер корпоративного уровня, установите SQL Server 2012 или SQL Server 2008 R2, сохранив имена экземпляров так же, как и до сбоя.</span><span class="sxs-lookup"><span data-stu-id="078bc-125">If you are installing an Enterprise Back End Server, install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="078bc-126">В зависимости от сервера, который вы восстанавливаете, и при развертывании сервер может включать несколько размещенных или отдельных баз данных.</span><span class="sxs-lookup"><span data-stu-id="078bc-126">Depending on the server that you are restoring and on your deployment, the server might include multiple collocated or separate databases.</span></span> <span data-ttu-id="078bc-127">Выполните те же действия, чтобы установить SQL Server, который использовался изначально для развертывания сервера, включая разрешения SQL Server и учетные записи.</span><span class="sxs-lookup"><span data-stu-id="078bc-127">Follow the same procedure to install SQL Server that you used originally to deploy the server, including SQL Server permissions and logins.</span></span>

        
        </div>

5.  <span data-ttu-id="078bc-128">На сервере переднего плана запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="078bc-128">From a Front End Server, Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

6.  <span data-ttu-id="078bc-129">Повторно создайте хранилище Центрального управления.</span><span class="sxs-lookup"><span data-stu-id="078bc-129">Re-create the Central Management store.</span></span> <span data-ttu-id="078bc-130">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="078bc-130">At the command line, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    <span data-ttu-id="078bc-131">Например:</span><span class="sxs-lookup"><span data-stu-id="078bc-131">For example:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  <span data-ttu-id="078bc-132">Настройте контрольную точку доменных служб Active Directory для хранилища центрального управления.</span><span class="sxs-lookup"><span data-stu-id="078bc-132">Set the Active Directory Domain Services control point for the Central Management store.</span></span> <span data-ttu-id="078bc-133">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="078bc-133">At the command line, type:</span></span>
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    <span data-ttu-id="078bc-134">Например:</span><span class="sxs-lookup"><span data-stu-id="078bc-134">For example:</span></span>
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="078bc-135">Если вы потеряли точку соединения, вы можете повторно запустить этот командлет.</span><span class="sxs-lookup"><span data-stu-id="078bc-135">If you lose the connection point, you can rerun this cmdlet.</span></span>

    
    </div>

8.  <span data-ttu-id="078bc-136">Импортируйте данные из хранилища Central Management Store из $Backup.</span><span class="sxs-lookup"><span data-stu-id="078bc-136">Import the Central Management store data from $Backup.</span></span> <span data-ttu-id="078bc-137">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="078bc-137">At the command line, type:</span></span>
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    <span data-ttu-id="078bc-138">Например:</span><span class="sxs-lookup"><span data-stu-id="078bc-138">For example:</span></span>
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  <span data-ttu-id="078bc-139">Включите только что сделанные изменения.</span><span class="sxs-lookup"><span data-stu-id="078bc-139">Enable the changes you have just made.</span></span> <span data-ttu-id="078bc-140">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="078bc-140">At the command line, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="078bc-141">После включения топологии вы можете найти документ Topology в базе данных.</span><span class="sxs-lookup"><span data-stu-id="078bc-141">After you enable the topology, you can find the topology document in the database.</span></span>

    
    </div>

10. <span data-ttu-id="078bc-142">Если вы восстанавливаете сервер, на котором размещена версия Enterprise Edition, который также является сервером CMS, или вам нужно повторно создать зеркало для CMS, выполните это действие.</span><span class="sxs-lookup"><span data-stu-id="078bc-142">If you are restoring an Enterprise Edition Back End Server that also hosted the CMS, or if you need to re-create a mirror of the CMS, then follow this step.</span></span> <span data-ttu-id="078bc-143">В противном случае перейдите к шагу 11.</span><span class="sxs-lookup"><span data-stu-id="078bc-143">Otherwise, skip to step 11.</span></span>
    
    <span data-ttu-id="078bc-144">Установите автономные базы данных, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="078bc-144">Install the stand-alone databases by doing the following:</span></span>
    
    1.  <span data-ttu-id="078bc-145">Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**и нажмите кнопку Построитель **топологии Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="078bc-145">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="078bc-146">Нажмите кнопку **загрузить топологию из существующего развертывания**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="078bc-146">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="078bc-147">Выберите топологию и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="078bc-147">Select the topology, and then click **Save**.</span></span> <span data-ttu-id="078bc-148">Нажмите кнопку **Да** , чтобы подтвердить выбор.</span><span class="sxs-lookup"><span data-stu-id="078bc-148">Click **Yes** to confirm your selection.</span></span>
    
    4.  <span data-ttu-id="078bc-149">Щелкните правой кнопкой мыши узел **Lync Server 2013** и выберите команду **установить базу данных**.</span><span class="sxs-lookup"><span data-stu-id="078bc-149">Right-click the **Lync Server 2013** node, and then click **Install Database**.</span></span>
    
    5.  <span data-ttu-id="078bc-150">Следуйте указаниям мастера **установки базы данных** .</span><span class="sxs-lookup"><span data-stu-id="078bc-150">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="078bc-151">Если вы восстанавливаете базу данных, отличную от хранилища Central Management на этом сервере, на странице **Создание баз данных** выберите базы данных, которые вы хотите повторно создать.</span><span class="sxs-lookup"><span data-stu-id="078bc-151">If you are restoring a database other than the Central Management store on this server, on the **Create databases** page, select the databases you want to recreate.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="078bc-152">На странице <STRONG>Создание баз данных</STRONG> отображаются только отдельные базы данных.</span><span class="sxs-lookup"><span data-stu-id="078bc-152">Only stand-alone databases are displayed on the <STRONG>Create databases</STRONG> page.</span></span> <span data-ttu-id="078bc-153">Выровненные базы данных создаются при запуске мастера развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="078bc-153">Collocated databases are created when you run the Lync Server Deployment Wizard.</span></span>

        
        </div>
    
    6.  <span data-ttu-id="078bc-154">Если вы восстанавливаете зеркальный сервер, продолжайте подписаться на работу мастера, пока не появится запрос на создание зеркальной базы данных.</span><span class="sxs-lookup"><span data-stu-id="078bc-154">If you are restoring a mirrored Back End Server, continue to follow the rest of the wizard until you come to a prompt of Create Mirror Database.</span></span> <span data-ttu-id="078bc-155">Выберите базу данных, которую вы хотите установить, и выполните описанные выше действия.</span><span class="sxs-lookup"><span data-stu-id="078bc-155">Select the database you want to install, and complete the process.</span></span>
    
    7.  <span data-ttu-id="078bc-156">Следуйте дальнейшим указаниям мастера, а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="078bc-156">Follow the rest of the wizard, and then click **Finish**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="078bc-157">Вместо того чтобы запустить построитель топологии, вы можете использовать командлет <STRONG>Install-ксдатабасе</STRONG> для создания каждой базы данных и командлет <STRONG>Install-ксмиррордатабасе</STRONG> для настройки зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="078bc-157">Instead of running Topology Builder, you can use the <STRONG>Install-CsDatabase</STRONG> cmdlet to create each database, and the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="078bc-158">Подробные сведения можно найти в разделе <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">Install-ксдатабасе</A> и <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">Install-ксмиррордатабасе</A>.</span><span class="sxs-lookup"><span data-stu-id="078bc-158">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">Install-CsDatabase</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">Install-CsMirrorDatabase</A>.</span></span>

    
    </div>

11. <span data-ttu-id="078bc-159">Если вы восстанавливаете сервер Standard Edition, перейдите в папку установки Lync Server или мультимедиа, а затем запустите мастер развертывания Lync Server, расположенный на странице \\Setup\\\\. exe.</span><span class="sxs-lookup"><span data-stu-id="078bc-159">If you are restoring a Standard Edition server, browse to the Lync Server installation folder or media, and start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="078bc-160">С помощью мастера развертывания Lync Server выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="078bc-160">Use the Lync Server Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="078bc-161">Выполните **Шаг 1: установите локальное хранилище конфигураций** , чтобы установить локальные файлы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="078bc-161">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="078bc-162">Запустите **Шаг 2: Настройка или удаление компонентов Lync Server** для установки ролей сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="078bc-162">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server roles.</span></span>
    
    3.  <span data-ttu-id="078bc-163">Запустите **Шаг 3: запросите, установите или назначьте сертификаты** для назначения сертификатов.</span><span class="sxs-lookup"><span data-stu-id="078bc-163">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="078bc-164">Выполните **Шаг 4: запуск служб** для запуска служб на сервере.</span><span class="sxs-lookup"><span data-stu-id="078bc-164">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="078bc-165">Дополнительные сведения о запуске мастера развертывания можно найти в документации по развертыванию роли сервера, которую вы восстанавливаете.</span><span class="sxs-lookup"><span data-stu-id="078bc-165">For details about running the Deployment Wizard, see the Deployment documentation for the server role that you are restoring.</span></span>

12. <span data-ttu-id="078bc-166">Восстановите данные пользователя, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="078bc-166">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="078bc-167">Скопируйте Експортедусердата. zip из $Backup\\ в локальный каталог.</span><span class="sxs-lookup"><span data-stu-id="078bc-167">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="078bc-168">Прежде чем восстанавливать данные пользователя, необходимо остановить службы Lync.</span><span class="sxs-lookup"><span data-stu-id="078bc-168">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="078bc-169">Для этого введите:</span><span class="sxs-lookup"><span data-stu-id="078bc-169">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    3.  <span data-ttu-id="078bc-170">Чтобы восстановить данные пользователя, в командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="078bc-170">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="078bc-171">Например:</span><span class="sxs-lookup"><span data-stu-id="078bc-171">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  <span data-ttu-id="078bc-172">Перезапустите службы Lync, введя:</span><span class="sxs-lookup"><span data-stu-id="078bc-172">Restart Lync services by typing:</span></span>
        
            Start-CsWindowsService

13. <span data-ttu-id="078bc-173">Восстановите данные о расположении в хранилище Центрального управления.</span><span class="sxs-lookup"><span data-stu-id="078bc-173">Restore Location Information data to the Central Management store.</span></span> <span data-ttu-id="078bc-174">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="078bc-174">At the command line, type:</span></span>
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    <span data-ttu-id="078bc-175">Например:</span><span class="sxs-lookup"><span data-stu-id="078bc-175">For example:</span></span>
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. <span data-ttu-id="078bc-176">Если вы развернули группу ответа в этом пуле или на сервере Standard Edition, восстановите данные конфигурации группы ответа.</span><span class="sxs-lookup"><span data-stu-id="078bc-176">If you deployed Response Group on this pool or Standard Edition server, restore the Response Group configuration data.</span></span> <span data-ttu-id="078bc-177">Подробности можно найти [в разделе Восстановление параметров группы ответов в Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span><span class="sxs-lookup"><span data-stu-id="078bc-177">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

15. <span data-ttu-id="078bc-178">Если вы восстанавливаете резервный сервер, который включает в себя архивирование и мониторинг баз данных, восстановите данные архивации или наблюдения с помощью средства управления SQL Server, например SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="078bc-178">If you are restoring a Back End Server that includes Archiving or Monitoring databases, restore the Archiving or Monitoring data by using a SQL Server management tool, such as SQL Server Management Studio.</span></span> <span data-ttu-id="078bc-179">Подробности можно найти [в разделе Восстановление мониторинга или архивация данных в Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span><span class="sxs-lookup"><span data-stu-id="078bc-179">For details, see [Restoring monitoring or archiving data in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

