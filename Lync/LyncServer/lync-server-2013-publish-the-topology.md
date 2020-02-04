---
title: 'Lync Server 2013: публикация топологии'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the topology
ms:assetid: 3b5a744b-b3a8-4538-a55e-e2e4f72dff47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425880(v=OCS.15)
ms:contentKeyID: 48183866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5760315cc60aa53a40457423c2b5402896c2a90c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-topology-in-lync-server-2013"></a><span data-ttu-id="2d327-102">Публикация топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d327-102">Publish the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d327-103">_**Тема последнего изменения:** 2013-10-01_</span><span class="sxs-lookup"><span data-stu-id="2d327-103">_**Topic Last Modified:** 2013-10-01_</span></span>

<span data-ttu-id="2d327-104">Чтобы успешно публиковать, включать и отключать топологию при добавлении или удалении роли сервера, вы должны войти в систему как пользователь, который является членом группы администраторов Рткуниверсалсерверадминс и domain.</span><span class="sxs-lookup"><span data-stu-id="2d327-104">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="2d327-105">Кроме того, можно делегировать права и разрешения администраторам.</span><span class="sxs-lookup"><span data-stu-id="2d327-105">It is also possible to delegate the proper administrator rights and permissions.</span></span> <span data-ttu-id="2d327-106">Дополнительные сведения можно найти [в разделе Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="2d327-106">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span> <span data-ttu-id="2d327-107">Для других изменений конфигурации требуется только членство в группе Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="2d327-107">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<span data-ttu-id="2d327-108">Определив топологию в построителе топологии, необходимо опубликовать топологию в хранилище Центрального управления.</span><span class="sxs-lookup"><span data-stu-id="2d327-108">After you define your topology in Topology Builder, you must publish the topology to the Central Management store.</span></span> <span data-ttu-id="2d327-109">Хранилище Central Management предоставляет надежное хранилище счематизед данных, необходимое для определения, настройки, обслуживания, администрирования, описания и работы с развертыванием Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d327-109">The Central Management store provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync Server 2013 deployment.</span></span> <span data-ttu-id="2d327-110">Она также проверяет данные для обеспечения согласованности конфигураций.</span><span class="sxs-lookup"><span data-stu-id="2d327-110">It also validates the data to help ensure configuration consistency.</span></span> <span data-ttu-id="2d327-111">Все изменения данных конфигурации вносятся через центральное хранилище управления, что избавляет от проблем рассинхронизации.</span><span class="sxs-lookup"><span data-stu-id="2d327-111">All changes to this configuration data happen at the Central Management store, eliminating “out-of-sync” issues.</span></span> <span data-ttu-id="2d327-112">Копии данных, предназначенные только для чтения, реплицируются на все серверы в топологии, в том числе на пограничные серверы.</span><span class="sxs-lookup"><span data-stu-id="2d327-112">Read-only copies of the data are replicated to all servers in the topology, including Edge Servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2d327-113">Для успешной публикации начальной топологии и создания центрального сервера управления серверу SQL Server требуется не менее 20 ГБ свободного места на диске.</span><span class="sxs-lookup"><span data-stu-id="2d327-113">SQL Server needs a minimum of 20 GB of free disk space to successfully publish the initial topology and create the Central Management Server.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="2d327-114">Только для корпоративных выпусков: чтобы опубликовать топологию, сервер SQL Server с интерфейсом должен находиться в сети и иметь доступ к исключениям брандмауэра на месте.</span><span class="sxs-lookup"><span data-stu-id="2d327-114">For Enterprise Edition only: In order to publish the topology, the SQL Server-based Back End Server must be online and accessible with firewall exceptions in place.</span></span> <span data-ttu-id="2d327-115">Подробнее об указании исключений межсетевого экрана можно узнать <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">в разделе сведения о требованиях к межсетевому экрану SQL Server с помощью Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2d327-115">For details about specifying firewall exceptions, see <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Understanding firewall requirements for SQL Server with Lync Server 2013</A>.</span></span> <span data-ttu-id="2d327-116">Дополнительные сведения о настройке SQL Server можно найти в разделе <A href="lync-server-2013-configure-sql-server-for-lync-server.md">Настройка SQL Server для Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2d327-116">For details about configuring SQL Server, see <A href="lync-server-2013-configure-sql-server-for-lync-server.md">Configure SQL Server for Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-publish-a-topology"></a><span data-ttu-id="2d327-117">Публикация топологии</span><span class="sxs-lookup"><span data-stu-id="2d327-117">To publish a topology</span></span>

1.  <span data-ttu-id="2d327-118">Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**и нажмите кнопку **Построитель топологии Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2d327-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="2d327-119">Выберите этот пункт, чтобы открыть топологию из локального файла.</span><span class="sxs-lookup"><span data-stu-id="2d327-119">Select to open the topology from a local file.</span></span> <span data-ttu-id="2d327-120">Если вы используете компьютер, на котором вы определили топологию, это значение будет находиться в том месте, где вы его сохранили.</span><span class="sxs-lookup"><span data-stu-id="2d327-120">If you are on the computer where you defined the topology, this will be in the location where you saved it in earlier steps.</span></span> <span data-ttu-id="2d327-121">Обычно это будет папка "документы" пользователя, который настроил топологию.</span><span class="sxs-lookup"><span data-stu-id="2d327-121">Typically, this will be the Documents folder of the user who configured the topology.</span></span>

3.  <span data-ttu-id="2d327-122">Щелкните правой кнопкой мыши узел **Lync Server 2013** и выберите команду **топология публикации**.</span><span class="sxs-lookup"><span data-stu-id="2d327-122">Right-click the **Lync Server 2013** node, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="2d327-123">На странице **Публикация топологии** нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2d327-123">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="2d327-124">На странице **Создание баз данных** выберите базы данных, которые вы хотите опубликовать.</span><span class="sxs-lookup"><span data-stu-id="2d327-124">On the **Create databases** page, select the databases you want to publish.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2d327-125">Если у вас нет действительных прав на создание определенных баз данных, вы можете снять флажки рядом с этими базами данных, чтобы позже их мог создать другой пользователь с необходимыми правами.</span><span class="sxs-lookup"><span data-stu-id="2d327-125">If you don’t have the appropriate rights to create the databases, you can clear the check boxes next to those databases, and someone with appropriate rights can later create the databases.</span></span> <span data-ttu-id="2d327-126">Дополнительные сведения можно найти <A href="lync-server-2013-deployment-permissions-for-sql-server.md">в разделе разрешения на развертывание SQL Server в Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2d327-126">For details, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>

    
    </div>

6.  <span data-ttu-id="2d327-127">Можно также щелкнуть элемент **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="2d327-127">Optionally click **Advanced**.</span></span> <span data-ttu-id="2d327-128">Дополнительные параметры размещения файлов данных SQL Server позволяют выбрать один из указанных ниже вариантов.</span><span class="sxs-lookup"><span data-stu-id="2d327-128">The Advanced SQL Server data file placement options let you select between the following options:</span></span>
    
      - <span data-ttu-id="2d327-129">**Автоматически определять расположение файла базы данных** — этот параметр определяет оптимальную производительность на основе конфигурации диска на сервере SQL Server путем распространения файлов журнала и данных в оптимальное расположение.</span><span class="sxs-lookup"><span data-stu-id="2d327-129">**Automatically determine database file location** – This option will determine the best operational performance based on the disk configuration on your SQL Server-based server by distributing the log and data files to the best location.</span></span>
    
      - <span data-ttu-id="2d327-p107">**Использовать параметры по умолчанию экземпляра SQL Server** — этот параметр помещает файлы данных и журналов на сервер SQL Server, используя настройки экземпляра. Этот параметр не использует рабочие функциональные возможности сервера SQL Server, чтобы определить оптимальные расположения для журналов и данных. Обычно администратор SQL Server перемещает файлы данных и журналов в расположения, удобные для сервера SQL Server и процедур управления организацией.</span><span class="sxs-lookup"><span data-stu-id="2d327-p107">**Use SQL Server instance defaults** – This option puts log and data files onto the SQL Server-based server by using the instance settings. This option does not use the operational functionality of the SQL Server-based server to determine optimal locations for logs and data. The SQL Server administrator would typically move the log and data files to locations that are appropriate for the SQL Server-based server and organization management procedures.</span></span>
    
    <span data-ttu-id="2d327-133">Нажмите кнопку **ОК**, а затем кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2d327-133">Click **OK**, and then click **Next**.</span></span>

7.  <span data-ttu-id="2d327-134">На странице **Выбор сервера центрального управления** выберите пул переднего плана.</span><span class="sxs-lookup"><span data-stu-id="2d327-134">On the **Select Central Management Server** page, select a Front End pool.</span></span>

8.  <span data-ttu-id="2d327-135">Можно также щелкнуть элемент **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="2d327-135">Optionally click **Advanced**.</span></span> <span data-ttu-id="2d327-136">Дополнительные параметры размещения файлов данных SQL Server позволяют выбрать один из указанных ниже вариантов.</span><span class="sxs-lookup"><span data-stu-id="2d327-136">The Advanced SQL Server data file placement options enables you to select between the following options:</span></span>
    
      - <span data-ttu-id="2d327-137">**Автоматически определять расположение файла базы данных** — этот параметр определяет оптимальную производительность на основе конфигурации диска на сервере SQL Server путем распространения файлов журнала и данных в оптимальное расположение.</span><span class="sxs-lookup"><span data-stu-id="2d327-137">**Automatically determine database file location** – This option will determine the best operational performance based on the disk configuration on your SQL Server-based server by distributing the log and data files to the best location.</span></span>
    
      - <span data-ttu-id="2d327-p109">**Использовать параметры по умолчанию экземпляра SQL Server** — этот параметр помещает файлы данных и журналов на сервер SQL Server, используя настройки экземпляра. Этот параметр не использует рабочие функциональные возможности сервера SQL Server, чтобы определить оптимальные расположения для журналов и данных. Обычно администратор SQL Server перемещает файлы данных и журналов в расположения, удобные для сервера SQL Server и процедур управления организацией.</span><span class="sxs-lookup"><span data-stu-id="2d327-p109">**Use SQL Server instance defaults** – This option puts log and data files onto the SQL Server-based server by using the instance settings. This option does not use the operational functionality of the SQL Server-based server to determine optimal locations for logs and data. The SQL Server administrator would typically move the log and data files to locations that are appropriate for the SQL Server-based server and organization management procedures.</span></span>
    
    <span data-ttu-id="2d327-141">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2d327-141">Click **OK**.</span></span>

9.  <span data-ttu-id="2d327-142">Нажмите кнопку **Далее** для завершения процесса публикации.</span><span class="sxs-lookup"><span data-stu-id="2d327-142">Click **Next** to complete the publishing process.</span></span>

10. <span data-ttu-id="2d327-143">После завершения процесса публикации нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="2d327-143">When the publish process has completed, click **Finish**.</span></span>
    
    <span data-ttu-id="2d327-144">После того как топология успешно опубликована, вы можете приступить к установке локальной реплики центрального хранилища управления на каждом сервере, работающем под управлением Lync Server 2013 в вашей топологии.</span><span class="sxs-lookup"><span data-stu-id="2d327-144">When the topology has been published successfully, you can begin installing a local replica of the Central Management store on each server running Lync Server 2013 in your topology.</span></span> <span data-ttu-id="2d327-145">Мы рекомендуем вас начать с первого интерфейсного пула.</span><span class="sxs-lookup"><span data-stu-id="2d327-145">We recommend that you begin with the first Front End pool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2d327-146">См. также</span><span class="sxs-lookup"><span data-stu-id="2d327-146">See Also</span></span>


[<span data-ttu-id="2d327-147">Настройка серверов и пулов переднего плана для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d327-147">Setting up Front End Servers and Front End pools for Lync Server 2013</span></span>](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

