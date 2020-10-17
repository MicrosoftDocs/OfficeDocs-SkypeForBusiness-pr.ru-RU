---
title: 'Lync Server 2013: восстановление сервера, на котором размещается центральное хранилище управления'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring the server hosting the Central Management store
ms:assetid: 3bd6c82c-07fb-4798-b8f9-e7c78a5a83d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202172(v=OCS.15)
ms:contentKeyID: 51541464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01d3912402b48ce8aede4a53efea208c96bff825
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511396"
---
# <a name="restoring-the-server-hosting-the-central-management-store-in-lync-server-2013"></a><span data-ttu-id="56197-102">Восстановление сервера, на котором размещается центральное хранилище управления, в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56197-102">Restoring the server hosting the Central Management store in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56197-103">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="56197-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="56197-104">В развертывании Lync Server имеется одно центральное хранилище управления, копия которого реплицируется на каждый сервер, на котором выполняется роль сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="56197-104">A Lync Server deployment has a single Central Management store, a copy of which is replicated to each server running a Lync Server server role.</span></span> <span data-ttu-id="56197-105">В этом разделе описывается восстановление внутреннего сервера или сервера Standard Edition, на котором размещается центральное хранилище управления.</span><span class="sxs-lookup"><span data-stu-id="56197-105">This topic describes how to restore a Back End Server or Standard Edition server that hosts the Central Management store.</span></span>

<span data-ttu-id="56197-106">Чтобы найти пул, в котором расположен центральный сервер управления, откройте построитель топологий, выберите **Lync Server**и посмотрите на правой панели в разделе **центральный сервер управления**.</span><span class="sxs-lookup"><span data-stu-id="56197-106">To find the pool where the Central Management Server is located, open Topology Builder, click **Lync Server**, and look in the right pane under **Central Management Server**.</span></span>

<span data-ttu-id="56197-107">Если фоновый сервер, на котором размещается центральное хранилище управления, находится в зеркальной установке, а зеркальная база данных по-прежнему работает, рекомендуется сделать резервную копию этого зеркального отображения, а затем выполнить полное восстановление как для основной базы данных, так и для зеркальной базы данных, используя эту резервную копию, следуя процедуре восстановления, приведенной ниже.</span><span class="sxs-lookup"><span data-stu-id="56197-107">If the Back End Server that hosts the Central Management store is in a mirrored setup and the mirror database is still functional, we recommend that you make a backup of this still-functioning mirror, and then perform a full restore on both the primary database and the mirror database, using this backup, by following the restoration procedure below.</span></span> <span data-ttu-id="56197-108">Это необходимо, так как для внутреннего восстановления требуется изменить и опубликовать топологию, и это можно сделать только в том случае, если база данных CMS размещена в рабочем состоянии.</span><span class="sxs-lookup"><span data-stu-id="56197-108">This is necessary because Back End restore requires modifying and publishing the topology, and this can be done only if the primary database hosting CMS is operational.</span></span> <span data-ttu-id="56197-109">Также обратите внимание на то, что роли основной и зеркальной базы данных невозможно изменить, если топология не может быть опубликована.</span><span class="sxs-lookup"><span data-stu-id="56197-109">Also note that the primary and mirror database roles cannot be interchanged if the topology cannot be published.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="56197-110">Если на внутреннем сервере или сервере Standard Edition, на котором не размещается центральное хранилище управления, произошел сбой, ознакомьтесь со статьей <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Восстановление внутреннего сервера Enterprise Edition в Lync server 2013</A> или <A href="lync-server-2013-restoring-a-standard-edition-server.md">восстановление сервера Standard Edition в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="56197-110">If a Back End Server or Standard Edition server that does not host the Central Management store failed, see <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restoring an Enterprise Edition Back End Server in Lync Server 2013</A> or <A href="lync-server-2013-restoring-a-standard-edition-server.md">Restoring a Standard Edition server in Lync Server 2013</A>.</span></span> <span data-ttu-id="56197-111">Если внутренний сервер, на котором размещается центральное хранилище управления, находится в зеркальной конфигурации и не удалось выполнить только зеркальное отображение, ознакомьтесь со статьей <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">восстановление зеркального внутреннего сервера Enterprise Edition в Lync Server 2013-Mirror</A>.</span><span class="sxs-lookup"><span data-stu-id="56197-111">If a Back End Server that hosts the Central Management store is in a mirrored configuration and only the mirror failed, see <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</A>.</span></span> <span data-ttu-id="56197-112">Если не удалось выполнить какой – либо другой сервер, ознакомьтесь со статьей <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Восстановление рядового сервера Enterprise Edition в Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="56197-112">If any other server failed, see <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restoring an Enterprise Edition member server in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="56197-113">Перед началом восстановления рекомендуется использовать копию системы в виде образа.</span><span class="sxs-lookup"><span data-stu-id="56197-113">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="56197-114">Это изображение можно использовать в качестве точки отката, если в процессе восстановления что-то пойдет не так.</span><span class="sxs-lookup"><span data-stu-id="56197-114">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="56197-115">Вы можете использовать копию образа после установки операционной системы и SQL Server, а также для восстановления или повторной регистрации сертификатов.</span><span class="sxs-lookup"><span data-stu-id="56197-115">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-the-central-management-store"></a><span data-ttu-id="56197-116">Восстановление центрального хранилища управления</span><span class="sxs-lookup"><span data-stu-id="56197-116">To restore the Central Management store</span></span>

1.  <span data-ttu-id="56197-117">Начните с чистого или нового сервера с таким же полным доменным именем (FQDN) в качестве компьютера, на котором произошел сбой, установите операционную систему, а затем восстановите или повторно зарегистрируйте сертификаты.</span><span class="sxs-lookup"><span data-stu-id="56197-117">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="56197-118">Для выполнения этого действия следуйте процедурам развертывания сервера в Организации.</span><span class="sxs-lookup"><span data-stu-id="56197-118">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="56197-119">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins и локальной группы администраторов, войдите на сервер, который вы восстанавливаете.</span><span class="sxs-lookup"><span data-stu-id="56197-119">From a user account that is a member of the RTCUniversalServerAdmins group and the Local Administrators group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="56197-120">При восстановлении сервера Standard Edition Восстановите хранилище файлов, скопировав соответствующее хранилище файлов из $Backup в расположение хранилища файлов на сервере, а затем предоставьте к ней общий доступ.</span><span class="sxs-lookup"><span data-stu-id="56197-120">If you are restoring a Standard Edition server, restore the File Store by copying the appropriate File Store from $Backup to the File Store location on the server, and then share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="56197-121">Путь и имя файла для восстановленного хранилища файлов должны совпадать с хранилищем файлов, сохраненным в резервной копии, чтобы компоненты, использующие эти файлы, могли получать к ним доступ.</span><span class="sxs-lookup"><span data-stu-id="56197-121">The path and file name for the restored File Store should be exactly the same as the backed up File Store so that components that use the files can access them.</span></span>

    
    </div>

4.  <span data-ttu-id="56197-122">Выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="56197-122">Do one of the following:</span></span>
    
      - <span data-ttu-id="56197-123">Если устанавливается сервер Standard Edition, перейдите в папку установки Lync Server или носитель, а затем запустите мастер развертывания Lync Server, расположенный в \\ программе установки \\ amd64 \\Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="56197-123">If you are installing a Standard Edition server, browse to the Lync Server installation folder or media, and then start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="56197-124">В мастере развертывания нажмите кнопку **подготовить первый сервер Standard Edition** и следуйте указаниям мастера для установки центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="56197-124">In the Deployment Wizard, click **Prepare first Standard Edition server** and follow the wizard to install the Central Management store.</span></span>
    
      - <span data-ttu-id="56197-125">При установке внутреннего сервера предприятия установите SQL Server 2012 или SQL Server 2008 R2, оставив имена экземпляров такими же, как и до сбоя.</span><span class="sxs-lookup"><span data-stu-id="56197-125">If you are installing an Enterprise Back End Server, install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="56197-126">В зависимости от восстанавливаемого сервера и развертывания сервер может включать несколько размещенных или отдельных баз данных.</span><span class="sxs-lookup"><span data-stu-id="56197-126">Depending on the server that you are restoring and on your deployment, the server might include multiple collocated or separate databases.</span></span> <span data-ttu-id="56197-127">Выполните ту же процедуру, чтобы установить SQL Server, который использовался изначально для развертывания сервера, в том числе разрешения SQL Server и учетные данные для входа.</span><span class="sxs-lookup"><span data-stu-id="56197-127">Follow the same procedure to install SQL Server that you used originally to deploy the server, including SQL Server permissions and logins.</span></span>

        
        </div>

5.  <span data-ttu-id="56197-128">На сервере переднего плана запустите командную консоль Lync Server: нажмите кнопку **Пуск**, выберите **все программы**, **Microsoft Lync Server 2013**и щелкните **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="56197-128">From a Front End Server, Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

6.  <span data-ttu-id="56197-129">Повторно создайте центральное хранилище управления.</span><span class="sxs-lookup"><span data-stu-id="56197-129">Re-create the Central Management store.</span></span> <span data-ttu-id="56197-130">В командной строке введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="56197-130">At the command line, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    <span data-ttu-id="56197-131">Пример:</span><span class="sxs-lookup"><span data-stu-id="56197-131">For example:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  <span data-ttu-id="56197-132">Установите точку управления доменными службами Active Directory для центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="56197-132">Set the Active Directory Domain Services control point for the Central Management store.</span></span> <span data-ttu-id="56197-133">В командной строке введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="56197-133">At the command line, type:</span></span>
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    <span data-ttu-id="56197-134">Пример:</span><span class="sxs-lookup"><span data-stu-id="56197-134">For example:</span></span>
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="56197-135">Если вы потеряли точку подключения, вы можете повторно запустить этот командлет.</span><span class="sxs-lookup"><span data-stu-id="56197-135">If you lose the connection point, you can rerun this cmdlet.</span></span>

    
    </div>

8.  <span data-ttu-id="56197-136">Импортируйте данные центрального хранилища управления из $Backup.</span><span class="sxs-lookup"><span data-stu-id="56197-136">Import the Central Management store data from $Backup.</span></span> <span data-ttu-id="56197-137">В командной строке введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="56197-137">At the command line, type:</span></span>
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    <span data-ttu-id="56197-138">Пример:</span><span class="sxs-lookup"><span data-stu-id="56197-138">For example:</span></span>
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  <span data-ttu-id="56197-139">Включите только что внесенные изменения.</span><span class="sxs-lookup"><span data-stu-id="56197-139">Enable the changes you have just made.</span></span> <span data-ttu-id="56197-140">В командной строке введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="56197-140">At the command line, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="56197-141">После включения топологии можно найти документ топологии в базе данных.</span><span class="sxs-lookup"><span data-stu-id="56197-141">After you enable the topology, you can find the topology document in the database.</span></span>

    
    </div>

10. <span data-ttu-id="56197-142">При восстановлении внутреннего сервера Enterprise Edition, который также размещает CMS, или необходимо повторно создать зеркало сервера CMS, а затем выполнить этот шаг.</span><span class="sxs-lookup"><span data-stu-id="56197-142">If you are restoring an Enterprise Edition Back End Server that also hosted the CMS, or if you need to re-create a mirror of the CMS, then follow this step.</span></span> <span data-ttu-id="56197-143">В противном случае перейдите к шагу 11.</span><span class="sxs-lookup"><span data-stu-id="56197-143">Otherwise, skip to step 11.</span></span>
    
    <span data-ttu-id="56197-144">Установите автономные базы данных, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="56197-144">Install the stand-alone databases by doing the following:</span></span>
    
    1.  <span data-ttu-id="56197-145">Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Построитель топологий Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="56197-145">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="56197-146">Выберите **загрузить топологию из существующего развертывания**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="56197-146">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="56197-147">Выберите топологию, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="56197-147">Select the topology, and then click **Save**.</span></span> <span data-ttu-id="56197-148">Нажмите кнопку **Да** , чтобы подтвердить выбор.</span><span class="sxs-lookup"><span data-stu-id="56197-148">Click **Yes** to confirm your selection.</span></span>
    
    4.  <span data-ttu-id="56197-149">Щелкните правой кнопкой мыши узел **Lync Server 2013** и выберите команду **установить базу данных**.</span><span class="sxs-lookup"><span data-stu-id="56197-149">Right-click the **Lync Server 2013** node, and then click **Install Database**.</span></span>
    
    5.  <span data-ttu-id="56197-150">Следуйте инструкциям мастера **установки базы данных** .</span><span class="sxs-lookup"><span data-stu-id="56197-150">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="56197-151">При восстановлении базы данных, отличной от центрального хранилища управления на этом сервере, на странице **Создание баз данных** выберите базы данных, которые необходимо повторно создать.</span><span class="sxs-lookup"><span data-stu-id="56197-151">If you are restoring a database other than the Central Management store on this server, on the **Create databases** page, select the databases you want to recreate.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="56197-152">На странице <STRONG>Создание баз данных</STRONG> отображаются только изолированные базы данных.</span><span class="sxs-lookup"><span data-stu-id="56197-152">Only stand-alone databases are displayed on the <STRONG>Create databases</STRONG> page.</span></span> <span data-ttu-id="56197-153">Размещенные базы данных создаются при запуске мастера развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="56197-153">Collocated databases are created when you run the Lync Server Deployment Wizard.</span></span>

        
        </div>
    
    6.  <span data-ttu-id="56197-154">Если восстанавливается зеркальный сервер, следуйте дальнейшим действиям мастера до тех пор, пока не будет выводиться запрос на создание зеркальной базы данных.</span><span class="sxs-lookup"><span data-stu-id="56197-154">If you are restoring a mirrored Back End Server, continue to follow the rest of the wizard until you come to a prompt of Create Mirror Database.</span></span> <span data-ttu-id="56197-155">Выберите базу данных, которую требуется установить, и выполните процедуру.</span><span class="sxs-lookup"><span data-stu-id="56197-155">Select the database you want to install, and complete the process.</span></span>
    
    7.  <span data-ttu-id="56197-156">Следуйте дальнейшим указаниям мастера, а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="56197-156">Follow the rest of the wizard, and then click **Finish**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="56197-157">Вместо того чтобы запустить построитель топологий, вы можете использовать командлет <STRONG>Install – CsDatabase</STRONG> для создания каждой базы данных и командлет <STRONG>Install – CsMirrorDatabase</STRONG> для настройки зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="56197-157">Instead of running Topology Builder, you can use the <STRONG>Install-CsDatabase</STRONG> cmdlet to create each database, and the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="56197-158">Дополнительные сведения см. в <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">статье Install — CsDatabase</A> и <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">Installing — CsMirrorDatabase</A>.</span><span class="sxs-lookup"><span data-stu-id="56197-158">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">Install-CsDatabase</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">Install-CsMirrorDatabase</A>.</span></span>

    
    </div>

11. <span data-ttu-id="56197-159">Если восстанавливается сервер Standard Edition, перейдите к папке установки Lync Server или носителю и запустите мастер развертывания Lync Server, расположенный в \\ программе установки \\ amd64 \\Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="56197-159">If you are restoring a Standard Edition server, browse to the Lync Server installation folder or media, and start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="56197-160">С помощью мастера развертывания Lync Server выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="56197-160">Use the Lync Server Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="56197-161">Выполните **Шаг 1: установите локальное хранилище конфигураций** , чтобы установить локальные файлы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="56197-161">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="56197-162">Выполните **Шаг 2: Установка или удаление компонентов Lync Server** для установки ролей сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="56197-162">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server roles.</span></span>
    
    3.  <span data-ttu-id="56197-163">Выполните **Шаг 3: запрос, установка или назначение сертификатов** для назначения сертификатов.</span><span class="sxs-lookup"><span data-stu-id="56197-163">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="56197-164">Выполните **Шаг 4: запуск служб** для запуска служб на сервере.</span><span class="sxs-lookup"><span data-stu-id="56197-164">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="56197-165">Для получения дополнительных сведений о запуске мастера развертывания обратитесь к документации по развертыванию для восстанавливаемой роли сервера.</span><span class="sxs-lookup"><span data-stu-id="56197-165">For details about running the Deployment Wizard, see the Deployment documentation for the server role that you are restoring.</span></span>

12. <span data-ttu-id="56197-166">Восстановите данные пользователя, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="56197-166">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="56197-167">Копирование ExportedUserData.zip из $Backup \\ в локальный каталог.</span><span class="sxs-lookup"><span data-stu-id="56197-167">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="56197-168">Перед восстановлением данных пользователя необходимо остановить службы Lync.</span><span class="sxs-lookup"><span data-stu-id="56197-168">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="56197-169">Для этого введите:</span><span class="sxs-lookup"><span data-stu-id="56197-169">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    3.  <span data-ttu-id="56197-170">Чтобы восстановить данные пользователя, введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="56197-170">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="56197-171">Например:</span><span class="sxs-lookup"><span data-stu-id="56197-171">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  <span data-ttu-id="56197-172">Перезапустите службы Lync, введя следующую команду:</span><span class="sxs-lookup"><span data-stu-id="56197-172">Restart Lync services by typing:</span></span>
        
            Start-CsWindowsService

13. <span data-ttu-id="56197-173">Восстановление данных о расположении в центральном хранилище управления.</span><span class="sxs-lookup"><span data-stu-id="56197-173">Restore Location Information data to the Central Management store.</span></span> <span data-ttu-id="56197-174">В командной строке введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="56197-174">At the command line, type:</span></span>
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    <span data-ttu-id="56197-175">Пример:</span><span class="sxs-lookup"><span data-stu-id="56197-175">For example:</span></span>
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. <span data-ttu-id="56197-176">Если вы развернули группу ответа в этом пуле или на сервере Standard Edition, восстановите данные конфигурации группы ответа.</span><span class="sxs-lookup"><span data-stu-id="56197-176">If you deployed Response Group on this pool or Standard Edition server, restore the Response Group configuration data.</span></span> <span data-ttu-id="56197-177">Дополнительные сведения см [в разделе Восстановление параметров группы ответа в Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span><span class="sxs-lookup"><span data-stu-id="56197-177">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

15. <span data-ttu-id="56197-178">При восстановлении внутреннего сервера, который включает в себя архивацию или мониторинг баз данных, восстановите данные архивации или мониторинга с помощью средства управления SQL Server, такого как SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="56197-178">If you are restoring a Back End Server that includes Archiving or Monitoring databases, restore the Archiving or Monitoring data by using a SQL Server management tool, such as SQL Server Management Studio.</span></span> <span data-ttu-id="56197-179">Дополнительные сведения см. [в статье восстановление данных мониторинга или архивации в Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span><span class="sxs-lookup"><span data-stu-id="56197-179">For details, see [Restoring monitoring or archiving data in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

