---
title: 'Lync Server 2013: восстановление сервера выпуска Enterprise Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring an Enterprise Edition Back End Server
ms:assetid: 1450eb4e-3315-4d02-8f02-6e1791fb1550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202163(v=OCS.15)
ms:contentKeyID: 51541446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e0121ee654846bcb60acc6da6847995b967a880
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823051"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-back-end-server-in-lync-server-2013"></a><span data-ttu-id="66686-102">Восстановление сервера выпуска Enterprise Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66686-102">Restoring an Enterprise Edition Back End Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66686-103">_**Тема последнего изменения:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="66686-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="66686-104">Выполните описанные в этой статье действия в следующих двух случаях.</span><span class="sxs-lookup"><span data-stu-id="66686-104">Use the procedure described in this topic in the following two cases:</span></span>

  - <span data-ttu-id="66686-105">Не удается выполнить как основную, так и зеркальную базы данных зеркального сервера выпуска Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="66686-105">Both the primary and mirror databases of a mirrored Enterprise Edition Back End Server fail.</span></span>

  - <span data-ttu-id="66686-106">Не удается выполнить зеркальный сервер выпуска Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="66686-106">An Enterprise Edition Back End Server that is not mirrored fails.</span></span>

<span data-ttu-id="66686-107">Если у вас есть зеркальная версия Enterprise Edition и только зеркальная или основная база данных завершает работу со сбоем, ознакомьтесь со сведениями о восстановлении [зеркального сервера выпуска Enterprise Edition в Lync server 2013 — PRIMARY](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) для восстановления базы данных-источника и восстановлении зеркальной копии [ Сервер заднего выпуска Enterprise Edition в Lync Server 2013 — зеркало](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) для восстановления зеркала.</span><span class="sxs-lookup"><span data-stu-id="66686-107">If you have a mirrored Enterprise Edition Back End and only the mirror or primary database fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) for restoring the primary database, and [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) for restoring the mirror.</span></span>

<span data-ttu-id="66686-108">Если центральное хранилище Management завершается сбоем, ознакомьтесь со сведениями о том, как [восстановить сервер, на котором размещено центральное хранилище, в Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span><span class="sxs-lookup"><span data-stu-id="66686-108">If the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="66686-109">Если сервер, на котором выводится сообщение, не входит в состав сервера Enterprise Edition, ознакомьтесь со сведениями о [восстановлении рядового сервера выпуска Enterprise Edition в Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="66686-109">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="66686-110">Прежде чем начать восстановление, мы рекомендуем использовать копию системы с изображением.</span><span class="sxs-lookup"><span data-stu-id="66686-110">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="66686-111">Вы можете использовать это изображение как точку отката, если что-то пойдет не так во время восстановления.</span><span class="sxs-lookup"><span data-stu-id="66686-111">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="66686-112">После установки операционной системы и сервера SQL Server вы можете использовать копию изображения, а также восстановить или подать заявку на сертификаты.</span><span class="sxs-lookup"><span data-stu-id="66686-112">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server"></a><span data-ttu-id="66686-113">Восстановление сервера выпуска Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="66686-113">To restore an Enterprise Edition Back End Server</span></span>

1.  <span data-ttu-id="66686-114">Начните с чистого или нового сервера с таким же полным доменным именем (FQDN), как и у компьютера, на котором произошел сбой, установите операционную систему, а затем восстановите или порегистрируйте сертификаты.</span><span class="sxs-lookup"><span data-stu-id="66686-114">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="66686-115">Следуйте инструкциям по развертыванию сервера в своей организации, чтобы выполнить этот шаг.</span><span class="sxs-lookup"><span data-stu-id="66686-115">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="66686-116">Войдите в учетную запись пользователя, которая входит в группу Рткуниверсалсерверадминс, на сервере, который вы хотите восстановить.</span><span class="sxs-lookup"><span data-stu-id="66686-116">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="66686-117">Установите SQL Server 2012 или SQL Server 2008 R2, сохранив имена экземпляров так же, как и до сбоя.</span><span class="sxs-lookup"><span data-stu-id="66686-117">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="66686-118">В зависимости от развертывания сервер может включать несколько размещенных или отдельных баз данных.</span><span class="sxs-lookup"><span data-stu-id="66686-118">Depending on your deployment, the Back End Server might include multiple collocated or separate databases.</span></span> <span data-ttu-id="66686-119">Выполните те же действия, чтобы установить SQL Server, который использовался изначально для развертывания сервера, включая разрешения SQL Server и учетные записи.</span><span class="sxs-lookup"><span data-stu-id="66686-119">Follow the same procedure to install SQL Server that you used originally to deploy the server, including SQL Server permissions and logins.</span></span>

    
    </div>

4.  <span data-ttu-id="66686-120">После установки SQL Server выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="66686-120">After you install SQL Server, perform the following:</span></span>
    
    1.  <span data-ttu-id="66686-121">Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**и нажмите кнопку Построитель **топологии Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="66686-121">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="66686-122">Нажмите кнопку **загрузить топологию из существующего развертывания**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="66686-122">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="66686-123">Выберите топологию и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="66686-123">Select the topology, and then click **Save**.</span></span> <span data-ttu-id="66686-124">Нажмите кнопку **Да** , чтобы подтвердить выбор.</span><span class="sxs-lookup"><span data-stu-id="66686-124">Click **Yes** to confirm your selection.</span></span>
    
    4.  <span data-ttu-id="66686-125">Щелкните правой кнопкой мыши узел **Lync Server 2013** и выберите команду **топология публикации**.</span><span class="sxs-lookup"><span data-stu-id="66686-125">Right-click the **Lync Server 2013** node, and then click **Publish Topology**.</span></span>
    
    5.  <span data-ttu-id="66686-126">Следуйте указаниям мастера **публикации топологии** .</span><span class="sxs-lookup"><span data-stu-id="66686-126">Follow the **Publish the Topology** wizard.</span></span> <span data-ttu-id="66686-127">На странице **Создание баз данных** выберите базы данных, которые вы хотите повторно создать.</span><span class="sxs-lookup"><span data-stu-id="66686-127">On the **Create databases** page, select the databases that you want to re-create.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="66686-128">На странице <STRONG>Создание баз данных</STRONG> отображаются только отдельные базы данных.</span><span class="sxs-lookup"><span data-stu-id="66686-128">Only stand-alone databases are displayed on the <STRONG>Create databases</STRONG> page.</span></span>

        
        </div>
    
    6.  <span data-ttu-id="66686-129">Если вы восстанавливаете серверную часть, которая была зеркально отображена, продолжайте подписаться на работу мастера, пока не появится сообщение **Создание зеркальной базы данных** .</span><span class="sxs-lookup"><span data-stu-id="66686-129">If you are restoring a Back End that was mirrored, continue to follow the rest of the wizard until the prompt **Create Mirror Database** appears.</span></span> <span data-ttu-id="66686-130">Выберите базу данных, которую вы хотите установить, и выполните описанные выше действия.</span><span class="sxs-lookup"><span data-stu-id="66686-130">Select the database that you want to install, and complete the process.</span></span>
    
    7.  <span data-ttu-id="66686-131">Следуйте дальнейшим указаниям мастера, а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="66686-131">Follow the rest of the wizard, and then click **Finish**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="66686-132">Вместо того чтобы запустить построитель топологии, вы можете использовать командлет <STRONG>Install-ксдатабасе</STRONG> для создания каждой базы данных и командлет <STRONG>Install-ксмиррордатабасе</STRONG> для настройки зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="66686-132">Instead of running Topology Builder, you can use the <STRONG>Install-CsDatabase</STRONG> cmdlet to create each database, and the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="66686-133">Подробные сведения можно найти в руководстве по среде Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="66686-133">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

5.  <span data-ttu-id="66686-134">Восстановите данные пользователя, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="66686-134">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="66686-135">Скопируйте Експортедусердата. zip из $Backup\\ в локальный каталог.</span><span class="sxs-lookup"><span data-stu-id="66686-135">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="66686-136">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="66686-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    3.  <span data-ttu-id="66686-137">Прежде чем восстанавливать данные пользователя, необходимо остановить службы Lync.</span><span class="sxs-lookup"><span data-stu-id="66686-137">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="66686-138">Для этого введите:</span><span class="sxs-lookup"><span data-stu-id="66686-138">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    4.  <span data-ttu-id="66686-139">Чтобы восстановить данные пользователя, в командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="66686-139">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="66686-140">Например:</span><span class="sxs-lookup"><span data-stu-id="66686-140">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  <span data-ttu-id="66686-141">Перезапустите службы Lync, введя:</span><span class="sxs-lookup"><span data-stu-id="66686-141">Restart Lync Services by typing:</span></span>
        
            Start-CsWindowsService

6.  <span data-ttu-id="66686-142">Если вы развернули группу ответа в этом пуле, восстановите данные конфигурации группы ответа.</span><span class="sxs-lookup"><span data-stu-id="66686-142">If you deployed Response Group on this pool, restore the Response Group configuration data.</span></span> <span data-ttu-id="66686-143">Подробности можно найти [в разделе Восстановление параметров группы ответов в Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span><span class="sxs-lookup"><span data-stu-id="66686-143">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

7.  <span data-ttu-id="66686-144">Если вы восстанавливаете резервный сервер, который включает в себя архивирование и мониторинг баз данных, восстановите данные архивации или наблюдения с помощью средства SQL Server, например SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="66686-144">If you are restoring a Back End Server that included Archiving or Monitoring databases, restore the Archiving or Monitoring data by using a SQL Server tool, such as SQL Server Management Studio.</span></span> <span data-ttu-id="66686-145">Подробности можно найти [в разделе Восстановление мониторинга или архивация данных в Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span><span class="sxs-lookup"><span data-stu-id="66686-145">For details, see [Restoring monitoring or archiving data in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

