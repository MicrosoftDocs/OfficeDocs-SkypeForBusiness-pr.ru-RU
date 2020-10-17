---
title: 'Lync Server 2013: восстановление внутреннего сервера Enterprise Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition Back End Server
ms:assetid: 1450eb4e-3315-4d02-8f02-6e1791fb1550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202163(v=OCS.15)
ms:contentKeyID: 51541446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9780963614a1d0f5049fdc5226391e2ee2b6d59c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511546"
---
# <a name="restoring-an-enterprise-edition-back-end-server-in-lync-server-2013"></a><span data-ttu-id="f618d-102">Восстановление внутреннего сервера Enterprise Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f618d-102">Restoring an Enterprise Edition Back End Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f618d-103">_**Последнее изменение темы:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="f618d-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="f618d-104">Используйте процедуру, описанную в этом разделе, в следующих двух случаях:</span><span class="sxs-lookup"><span data-stu-id="f618d-104">Use the procedure described in this topic in the following two cases:</span></span>

  - <span data-ttu-id="f618d-105">Не удается выполнить как основную, так и зеркальную базы данных зеркального внутреннего сервера Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="f618d-105">Both the primary and mirror databases of a mirrored Enterprise Edition Back End Server fail.</span></span>

  - <span data-ttu-id="f618d-106">Не удается создать зеркальный сервер Enterprise Edition, не являющийся зеркальным.</span><span class="sxs-lookup"><span data-stu-id="f618d-106">An Enterprise Edition Back End Server that is not mirrored fails.</span></span>

<span data-ttu-id="f618d-107">Если имеется зеркальный сервер Enterprise Edition, и только зеркальная или основная база данных завершается сбоем, ознакомьтесь со статьей [восстановление зеркального внутреннего сервера Enterprise Edition в Lync server 2013 — основной](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) для восстановления основной базы данных и [восстановления зеркального сервера переднего планов Enterprise Edition в Lync Server 2013 — зеркало](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) для восстановления зеркала.</span><span class="sxs-lookup"><span data-stu-id="f618d-107">If you have a mirrored Enterprise Edition Back End and only the mirror or primary database fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) for restoring the primary database, and [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) for restoring the mirror.</span></span>

<span data-ttu-id="f618d-108">Если центральное хранилище управления завершается сбоем, ознакомьтесь со статьей [восстановление сервера, на котором размещается центральное хранилище управления, в Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span><span class="sxs-lookup"><span data-stu-id="f618d-108">If the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="f618d-109">В случае сбоя рядового сервера Enterprise Edition, который не является внутренним сервером, ознакомьтесь со статьей [Восстановление рядового сервера Enterprise Edition в Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="f618d-109">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="f618d-110">Перед началом восстановления рекомендуется использовать копию системы в виде образа.</span><span class="sxs-lookup"><span data-stu-id="f618d-110">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="f618d-111">Это изображение можно использовать в качестве точки отката, если в процессе восстановления что-то пойдет не так.</span><span class="sxs-lookup"><span data-stu-id="f618d-111">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="f618d-112">Вы можете использовать копию образа после установки операционной системы и SQL Server, а также для восстановления или повторной регистрации сертификатов.</span><span class="sxs-lookup"><span data-stu-id="f618d-112">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server"></a><span data-ttu-id="f618d-113">Восстановление внутреннего сервера Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="f618d-113">To restore an Enterprise Edition Back End Server</span></span>

1.  <span data-ttu-id="f618d-114">Начните с чистого или нового сервера с таким же полным доменным именем (FQDN) в качестве компьютера, на котором произошел сбой, установите операционную систему, а затем восстановите или повторно зарегистрируйте сертификаты.</span><span class="sxs-lookup"><span data-stu-id="f618d-114">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f618d-115">Для выполнения этого действия следуйте процедурам развертывания сервера в Организации.</span><span class="sxs-lookup"><span data-stu-id="f618d-115">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="f618d-116">Из учетной записи пользователя, входящей в группу RTCUniversalServerAdmins, войдите на сервер, который вы восстанавливаете.</span><span class="sxs-lookup"><span data-stu-id="f618d-116">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="f618d-117">Установите SQL Server 2012 или SQL Server 2008 R2, сохранив имена экземпляров так же, как и до сбоя.</span><span class="sxs-lookup"><span data-stu-id="f618d-117">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f618d-118">В зависимости от развертывания внутренний сервер может включать несколько размещенных или отдельных баз данных.</span><span class="sxs-lookup"><span data-stu-id="f618d-118">Depending on your deployment, the Back End Server might include multiple collocated or separate databases.</span></span> <span data-ttu-id="f618d-119">Выполните ту же процедуру, чтобы установить SQL Server, который использовался изначально для развертывания сервера, в том числе разрешения SQL Server и учетные данные для входа.</span><span class="sxs-lookup"><span data-stu-id="f618d-119">Follow the same procedure to install SQL Server that you used originally to deploy the server, including SQL Server permissions and logins.</span></span>

    
    </div>

4.  <span data-ttu-id="f618d-120">После установки SQL Server выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f618d-120">After you install SQL Server, perform the following:</span></span>
    
    1.  <span data-ttu-id="f618d-121">Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Построитель топологий Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f618d-121">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="f618d-122">Выберите **загрузить топологию из существующего развертывания**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f618d-122">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="f618d-123">Выберите топологию, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f618d-123">Select the topology, and then click **Save**.</span></span> <span data-ttu-id="f618d-124">Нажмите кнопку **Да** , чтобы подтвердить выбор.</span><span class="sxs-lookup"><span data-stu-id="f618d-124">Click **Yes** to confirm your selection.</span></span>
    
    4.  <span data-ttu-id="f618d-125">Щелкните правой кнопкой мыши узел **Lync Server 2013** и выберите команду **опубликовать топологию**.</span><span class="sxs-lookup"><span data-stu-id="f618d-125">Right-click the **Lync Server 2013** node, and then click **Publish Topology**.</span></span>
    
    5.  <span data-ttu-id="f618d-126">Следуйте инструкциям мастера **публикации топологии** .</span><span class="sxs-lookup"><span data-stu-id="f618d-126">Follow the **Publish the Topology** wizard.</span></span> <span data-ttu-id="f618d-127">На странице " **Создание баз данных** " выберите базы данных, которые требуется повторно создать.</span><span class="sxs-lookup"><span data-stu-id="f618d-127">On the **Create databases** page, select the databases that you want to re-create.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f618d-128">На странице <STRONG>Создание баз данных</STRONG> отображаются только изолированные базы данных.</span><span class="sxs-lookup"><span data-stu-id="f618d-128">Only stand-alone databases are displayed on the <STRONG>Create databases</STRONG> page.</span></span>

        
        </div>
    
    6.  <span data-ttu-id="f618d-129">При восстановлении серверной части, которая была зеркально отображена, продолжайте выполнять остальные действия мастера до тех пор, пока не появится запрос на **Создание зеркальной базы данных** .</span><span class="sxs-lookup"><span data-stu-id="f618d-129">If you are restoring a Back End that was mirrored, continue to follow the rest of the wizard until the prompt **Create Mirror Database** appears.</span></span> <span data-ttu-id="f618d-130">Выберите базу данных, которую требуется установить, и выполните процедуру.</span><span class="sxs-lookup"><span data-stu-id="f618d-130">Select the database that you want to install, and complete the process.</span></span>
    
    7.  <span data-ttu-id="f618d-131">Следуйте дальнейшим указаниям мастера, а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="f618d-131">Follow the rest of the wizard, and then click **Finish**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="f618d-132">Вместо того чтобы запустить построитель топологий, вы можете использовать командлет <STRONG>Install – CsDatabase</STRONG> для создания каждой базы данных и командлет <STRONG>Install – CsMirrorDatabase</STRONG> для настройки зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="f618d-132">Instead of running Topology Builder, you can use the <STRONG>Install-CsDatabase</STRONG> cmdlet to create each database, and the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="f618d-133">Дополнительные сведения см. в документации Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f618d-133">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

5.  <span data-ttu-id="f618d-134">Восстановите данные пользователя, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f618d-134">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="f618d-135">Копирование ExportedUserData.zip из $Backup \\ в локальный каталог.</span><span class="sxs-lookup"><span data-stu-id="f618d-135">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="f618d-136">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f618d-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    3.  <span data-ttu-id="f618d-137">Перед восстановлением данных пользователя необходимо остановить службы Lync.</span><span class="sxs-lookup"><span data-stu-id="f618d-137">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="f618d-138">Для этого введите:</span><span class="sxs-lookup"><span data-stu-id="f618d-138">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    4.  <span data-ttu-id="f618d-139">Чтобы восстановить данные пользователя, введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f618d-139">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="f618d-140">Например:</span><span class="sxs-lookup"><span data-stu-id="f618d-140">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  <span data-ttu-id="f618d-141">Перезапустите службы Lync, введя следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f618d-141">Restart Lync Services by typing:</span></span>
        
            Start-CsWindowsService

6.  <span data-ttu-id="f618d-142">Если вы развернули группу ответа в этом пуле, восстановите данные конфигурации группы ответа.</span><span class="sxs-lookup"><span data-stu-id="f618d-142">If you deployed Response Group on this pool, restore the Response Group configuration data.</span></span> <span data-ttu-id="f618d-143">Дополнительные сведения см [в разделе Восстановление параметров группы ответа в Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span><span class="sxs-lookup"><span data-stu-id="f618d-143">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

7.  <span data-ttu-id="f618d-144">При восстановлении внутреннего сервера, включающего в себя архивацию или мониторинг баз данных, восстановите данные архивации или мониторинга с помощью средства SQL Server, такого как SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="f618d-144">If you are restoring a Back End Server that included Archiving or Monitoring databases, restore the Archiving or Monitoring data by using a SQL Server tool, such as SQL Server Management Studio.</span></span> <span data-ttu-id="f618d-145">Дополнительные сведения см. [в статье восстановление данных мониторинга или архивации в Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span><span class="sxs-lookup"><span data-stu-id="f618d-145">For details, see [Restoring monitoring or archiving data in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

