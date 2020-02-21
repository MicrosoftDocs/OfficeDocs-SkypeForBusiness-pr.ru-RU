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
ms.openlocfilehash: 46212fc9910885ed1d6d833ef0f4b30c3a49b7c4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publish-the-topology-in-lync-server-2013"></a><span data-ttu-id="1374e-102">Публикация топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1374e-102">Publish the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1374e-103">_**Последнее изменение темы:** 2013-10-01_</span><span class="sxs-lookup"><span data-stu-id="1374e-103">_**Topic Last Modified:** 2013-10-01_</span></span>

<span data-ttu-id="1374e-104">Чтобы успешно опубликовать, включить или отключить топологию при добавлении или удалении роли сервера, вам следует выполнить вход в качестве пользователя, являющегося членом группы RTCUniversalServerAdmins и группы администраторов домена.</span><span class="sxs-lookup"><span data-stu-id="1374e-104">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="1374e-105">Можно также делегировать подходящие права и разрешения.</span><span class="sxs-lookup"><span data-stu-id="1374e-105">It is also possible to delegate the proper administrator rights and permissions.</span></span> <span data-ttu-id="1374e-106">Дополнительные сведения см [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="1374e-106">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span> <span data-ttu-id="1374e-107">Для других изменений конфигурации требуется только членство в группе RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="1374e-107">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<span data-ttu-id="1374e-108">После определения топологии в построителе топологий необходимо опубликовать топологию в центральном хранилище управления.</span><span class="sxs-lookup"><span data-stu-id="1374e-108">After you define your topology in Topology Builder, you must publish the topology to the Central Management store.</span></span> <span data-ttu-id="1374e-109">Центральное хранилище управления предоставляет надежное хранилище схематизированные данных, необходимое для определения, настройки, обслуживания, администрирования, описания и работы с развертыванием Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1374e-109">The Central Management store provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync Server 2013 deployment.</span></span> <span data-ttu-id="1374e-110">Он также проверяет данные для обеспечения согласованности конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1374e-110">It also validates the data to help ensure configuration consistency.</span></span> <span data-ttu-id="1374e-111">Все изменения данных конфигурации происходят в центральном хранилище управления, устраняя проблемы, связанные с несинхронизированными.</span><span class="sxs-lookup"><span data-stu-id="1374e-111">All changes to this configuration data happen at the Central Management store, eliminating “out-of-sync” issues.</span></span> <span data-ttu-id="1374e-112">Доступные только для чтения копии данных реплицируются на все серверы в топологии, включая пограничные.</span><span class="sxs-lookup"><span data-stu-id="1374e-112">Read-only copies of the data are replicated to all servers in the topology, including Edge Servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1374e-113">Для успешной публикации начальной топологии SQL Server и создания центрального сервера управления требуется не менее 20 ГБ свободного места на диске.</span><span class="sxs-lookup"><span data-stu-id="1374e-113">SQL Server needs a minimum of 20 GB of free disk space to successfully publish the initial topology and create the Central Management Server.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="1374e-114">Только для Enterprise Edition: чтобы опубликовать топологию, внутренний сервер на базе SQL Server должен быть включен и доступен, то есть для него должны быть заданы исключения в брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="1374e-114">For Enterprise Edition only: In order to publish the topology, the SQL Server-based Back End Server must be online and accessible with firewall exceptions in place.</span></span> <span data-ttu-id="1374e-115">Дополнительные сведения об указании исключений брандмауэра приведены <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">в статье Общие сведения о требованиях к брандмауэру для SQL Server с Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1374e-115">For details about specifying firewall exceptions, see <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Understanding firewall requirements for SQL Server with Lync Server 2013</A>.</span></span> <span data-ttu-id="1374e-116">Подробнее о настройке SQL Server можно узнать в статье <A href="lync-server-2013-configure-sql-server-for-lync-server.md">Настройка SQL Server для Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1374e-116">For details about configuring SQL Server, see <A href="lync-server-2013-configure-sql-server-for-lync-server.md">Configure SQL Server for Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-publish-a-topology"></a><span data-ttu-id="1374e-117">Публикация топологии</span><span class="sxs-lookup"><span data-stu-id="1374e-117">To publish a topology</span></span>

1.  <span data-ttu-id="1374e-118">Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Построитель топологий Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="1374e-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="1374e-p104">Откройте топологию из локального файла, выбрав его. Если вы работаете за компьютером, на котором определяли данную топологию, файл находится там, где вы сохранили его ранее. Обычно это папка «Документы» пользователя, который определил топологию.</span><span class="sxs-lookup"><span data-stu-id="1374e-p104">Select to open the topology from a local file. If you are on the computer where you defined the topology, this will be in the location where you saved it in earlier steps. Typically, this will be the Documents folder of the user who configured the topology.</span></span>

3.  <span data-ttu-id="1374e-122">Щелкните правой кнопкой мыши узел **Lync Server 2013** и выберите команду **опубликовать топологию**.</span><span class="sxs-lookup"><span data-stu-id="1374e-122">Right-click the **Lync Server 2013** node, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="1374e-123">На странице **Publish the topology** (Публикация топологии) нажмите кнопку **Next** (Далее).</span><span class="sxs-lookup"><span data-stu-id="1374e-123">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="1374e-124">На странице **Create databases** (Создание баз данных) выберите публикуемые базы данных.</span><span class="sxs-lookup"><span data-stu-id="1374e-124">On the **Create databases** page, select the databases you want to publish.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1374e-125">Если у вас нет действительных прав на создание определенных баз данных, вы можете снять флажки рядом с этими базами данных, чтобы позже их мог создать другой пользователь с необходимыми правами.</span><span class="sxs-lookup"><span data-stu-id="1374e-125">If you don’t have the appropriate rights to create the databases, you can clear the check boxes next to those databases, and someone with appropriate rights can later create the databases.</span></span> <span data-ttu-id="1374e-126">Дополнительные сведения см <A href="lync-server-2013-deployment-permissions-for-sql-server.md">в разделе разрешения на развертывание для SQL Server в Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1374e-126">For details, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>

    
    </div>

6.  <span data-ttu-id="1374e-127">Можно также щелкнуть элемент **Advanced** (Дополнительно).</span><span class="sxs-lookup"><span data-stu-id="1374e-127">Optionally click **Advanced**.</span></span> <span data-ttu-id="1374e-128">Расширенные параметры размещения файлов данных SQL Server позволяют выбрать следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="1374e-128">The Advanced SQL Server data file placement options let you select between the following options:</span></span>
    
      - <span data-ttu-id="1374e-129">**Automatically determine database file location** (Автоматически определить расположение файла базы данных) — этот параметр определяет наилучшую рабочую производительность на основании конфигурации диска на сервере SQL Server, распространяя файлы данных и журналов в наилучшее расположение.</span><span class="sxs-lookup"><span data-stu-id="1374e-129">**Automatically determine database file location** – This option will determine the best operational performance based on the disk configuration on your SQL Server-based server by distributing the log and data files to the best location.</span></span>
    
      - <span data-ttu-id="1374e-p107">**Use SQL Server instance defaults** (Использовать значения по умолчанию экземпляра SQL Server) — этот параметр помещает файлы данных и журналов на сервер SQL Server, используя настройки экземпляра. Этот параметр не использует рабочие функциональные возможности сервера SQL Server, чтобы определить оптимальные расположения для журналов и данных. Обычно администратор SQL Server перемещает файлы данных и журналов в расположения, удобные для сервера SQL Server и процедур управления организацией.</span><span class="sxs-lookup"><span data-stu-id="1374e-p107">**Use SQL Server instance defaults** – This option puts log and data files onto the SQL Server-based server by using the instance settings. This option does not use the operational functionality of the SQL Server-based server to determine optimal locations for logs and data. The SQL Server administrator would typically move the log and data files to locations that are appropriate for the SQL Server-based server and organization management procedures.</span></span>
    
    <span data-ttu-id="1374e-133">Нажмите кнопку **OK** (ОК) и затем кнопку **Next** (Далее).</span><span class="sxs-lookup"><span data-stu-id="1374e-133">Click **OK**, and then click **Next**.</span></span>

7.  <span data-ttu-id="1374e-134">На странице **Выбор центрального сервера управления** выберите пул переднего плана.</span><span class="sxs-lookup"><span data-stu-id="1374e-134">On the **Select Central Management Server** page, select a Front End pool.</span></span>

8.  <span data-ttu-id="1374e-135">Можно также щелкнуть элемент **Advanced** (Дополнительно).</span><span class="sxs-lookup"><span data-stu-id="1374e-135">Optionally click **Advanced**.</span></span> <span data-ttu-id="1374e-136">Расширенные параметры размещения файлов данных SQL Server позволяют выбрать следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="1374e-136">The Advanced SQL Server data file placement options enables you to select between the following options:</span></span>
    
      - <span data-ttu-id="1374e-137">**Automatically determine database file location** (Автоматически определить расположение файла базы данных) — этот параметр определяет наилучшую рабочую производительность на основании конфигурации диска на сервере SQL Server, распространяя файлы данных и журналов в наилучшее расположение.</span><span class="sxs-lookup"><span data-stu-id="1374e-137">**Automatically determine database file location** – This option will determine the best operational performance based on the disk configuration on your SQL Server-based server by distributing the log and data files to the best location.</span></span>
    
      - <span data-ttu-id="1374e-p109">**Use SQL Server instance defaults** (Использовать значения по умолчанию экземпляра SQL Server) — этот параметр помещает файлы данных и журналов на сервер SQL Server, используя настройки экземпляра. Этот параметр не использует рабочие функциональные возможности сервера SQL Server, чтобы определить оптимальные расположения для журналов и данных. Обычно администратор SQL Server перемещает файлы данных и журналов в расположения, удобные для сервера SQL Server и процедур управления организацией.</span><span class="sxs-lookup"><span data-stu-id="1374e-p109">**Use SQL Server instance defaults** – This option puts log and data files onto the SQL Server-based server by using the instance settings. This option does not use the operational functionality of the SQL Server-based server to determine optimal locations for logs and data. The SQL Server administrator would typically move the log and data files to locations that are appropriate for the SQL Server-based server and organization management procedures.</span></span>
    
    <span data-ttu-id="1374e-141">Нажмите кнопку **OK** (ОК).</span><span class="sxs-lookup"><span data-stu-id="1374e-141">Click **OK**.</span></span>

9.  <span data-ttu-id="1374e-142">Нажмите кнопку **Next** (Далее) для завершения процесса публикации.</span><span class="sxs-lookup"><span data-stu-id="1374e-142">Click **Next** to complete the publishing process.</span></span>

10. <span data-ttu-id="1374e-143">После завершения процесса публикации нажмите кнопку **Finish** (Готово).</span><span class="sxs-lookup"><span data-stu-id="1374e-143">When the publish process has completed, click **Finish**.</span></span>
    
    <span data-ttu-id="1374e-144">После успешной публикации топологии можно приступить к установке локальной реплики центрального хранилища управления на каждом сервере, на котором выполняется Lync Server 2013, в вашей топологии.</span><span class="sxs-lookup"><span data-stu-id="1374e-144">When the topology has been published successfully, you can begin installing a local replica of the Central Management store on each server running Lync Server 2013 in your topology.</span></span> <span data-ttu-id="1374e-145">Рекомендуется начать с первого интерфейсного пула.</span><span class="sxs-lookup"><span data-stu-id="1374e-145">We recommend that you begin with the first Front End pool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1374e-146">См. также</span><span class="sxs-lookup"><span data-stu-id="1374e-146">See Also</span></span>


[<span data-ttu-id="1374e-147">Настройка серверов переднего плана и интерфейсных пулов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1374e-147">Setting up Front End Servers and Front End pools for Lync Server 2013</span></span>](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

