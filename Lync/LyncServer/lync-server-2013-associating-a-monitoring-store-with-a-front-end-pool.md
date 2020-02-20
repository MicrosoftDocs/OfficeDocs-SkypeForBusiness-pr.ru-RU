---
title: 'Lync Server 2013: связывание хранилища мониторинга с пулом переднего плана'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associating a monitoring store with a Front End pool
ms:assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205271(v=OCS.15)
ms:contentKeyID: 48185439
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f889179c5302a0ff8d59b5cf438c7ba0ab3c489f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associating-a-monitoring-store-with-a-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="ca33c-102">Связывание хранилища мониторинга с пулом переднего плана в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca33c-102">Associating a monitoring store with a Front End pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca33c-103">_**Последнее изменение темы:** 2013-04-22_</span><span class="sxs-lookup"><span data-stu-id="ca33c-103">_**Topic Last Modified:** 2013-04-22_</span></span>

<span data-ttu-id="ca33c-104">В данных мониторинга Microsoft Lync Server 2013, которые могут быть собраны только в интерфейсных пулах, связанных с хранилищем мониторинга, задача обычно выполняется определение пула переднего плана в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="ca33c-104">In Microsoft Lync Server 2013 monitoring data can only be collected on Front End pools that have been associated with a monitoring store, a task typically carried out you define a Front End pool in Topology Builder.</span></span> <span data-ttu-id="ca33c-105">Чтобы связать хранилище мониторинга с новым интерфейсным пулом, убедитесь, что выбран параметр **мониторинг (регистрация вызовов и ведение журнала показателей качества взаимодействия)** на странице **Выбор компонентов** мастера определение нового пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="ca33c-105">To associate a monitoring store with a new Front End pool, make sure that you select the option **Monitoring (call detail recording and logging of quality of experience metrics)** on the **Select Features** page of the Define New Front End Pool wizard.</span></span> <span data-ttu-id="ca33c-106">Обратите внимание, что при выборе этого параметра необходимо также указать хранилище SQL, чтобы завершить работу мастера. Однако это хранилище не обязательно должен существовать на момент запуска мастера.</span><span class="sxs-lookup"><span data-stu-id="ca33c-106">Note that, if you select this option, you must also specify a SQL store in order to complete the wizard; however, this store does not have to exist at the time you run the wizard.</span></span> <span data-ttu-id="ca33c-107">Это означает, что вы можете сначала связать пул с хранилищем мониторинга, а затем выполнить настройку этого хранилища.</span><span class="sxs-lookup"><span data-stu-id="ca33c-107">That means that you can first associate a pool with a monitoring store, then later setup and configure that store.</span></span>

<span data-ttu-id="ca33c-108">Или же вы можете связать существующий интерфейсный пул с новым или другим хранилищем мониторинга, выполнив следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ca33c-108">Alternatively, you can associate an existing Front End pool with a new or different monitoring store by completing the following procedure:</span></span>

1.  <span data-ttu-id="ca33c-109">Нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Построитель топологий Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ca33c-109">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="ca33c-110">В диалоговом окне **топологий** выберите **Загрузить топологию из существующего развертывания**, а затем щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ca33c-110">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>

3.  <span data-ttu-id="ca33c-p102">В диалоговом окне **Сохранить как** введите имя файла для текущей топологии, затем нажмите кнопку **Сохранить**. Сохраненную топологию можно позднее извлечь и опубликовать при наличии проблем с новой топологией.</span><span class="sxs-lookup"><span data-stu-id="ca33c-p102">In the **Save As** dialog box, enter a file name for your current topology and then click **Save**. The saved topology can later be retrieved and re-published in case there are problems with the new topology.</span></span>

4.  <span data-ttu-id="ca33c-113">В построителе топологий разверните узел **Lync Server 2013**, разверните имя сайта, содержащего пул переднего плана, а затем нажмите Развернуть **интерфейсные пулы Enterprise Edition**.</span><span class="sxs-lookup"><span data-stu-id="ca33c-113">In Topology Builder, expand **Lync Server 2013**, expand the name of the site containing the Front End pool, then click expand **Enterprise Edition Front End pools**.</span></span>

5.  <span data-ttu-id="ca33c-114">Щелкните правой кнопкой имя пула, который нужно связать с хранилищем мониторинга, и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="ca33c-114">Right-click the name of the pool to be associated with the monitoring store and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="ca33c-p103">В диалоговом окне **Изменить свойства** на вкладке **Общие** выберите параметр **Мониторинг (показатели CDR и QoE)**, а затем выберите существующую базу данных SQL Server в раскрывающемся списке **Хранилище мониторинга SQL Server**. (Или нажмите кнопку **Создать**, чтобы связать пул с новым хранилищем базы данных.) Если вы решили использовать новое хранилище, то в диалоговом окне **Определение нового хранилища SQL** введите полное доменное имя компьютера с SQL Server в поле  **Полное доменное имя SQL Server**. Если вы хотите использовать экземпляр SQL Server по умолчанию для этого хранилища, выберите параметр **Экземпляр по умолчанию**; в противном случае выберите **Именованный экземпляр** и введите имя экземпляра в поле **Именованный экземпляр**.</span><span class="sxs-lookup"><span data-stu-id="ca33c-p103">In the **Edit Properties** dialog box, on the **General** tab, select the option **Monitoring (CDR and QoE metrics)** and then select an existing SQL Server database from the **Monitoring SQL Server store** dropdown list. (Or, click **New** to associate the pool with a new database store.) If you choose to use a new database store then, in the **Define New SQL Store** dialog box, enter the fully qualified domain name of the SQL Server computer in the **Sql Server FQDN** box. If you want to use the default SQL Server instance for that store select **Default Instance**; otherwise select **Named Instance** and enter the instance name in the **Named Instance** box.</span></span>
    
    <span data-ttu-id="ca33c-p104">В диалоговом окне **Изменить свойства** также представлена возможность создания зеркала SQL для базы данных мониторинга (зеркало SQL позволяет хранить две копии базы данных мониторинга, одна из которых хранится на компьютере хранилища мониторинга, а другая — на компьютере зеркала SQL). Чтобы включить зеркалирование, выберите параметр **Этот экземпляр SQL используется для зеркалирования** и введите номер порта зеркального сервера в поле **Номер порта зеркала**.</span><span class="sxs-lookup"><span data-stu-id="ca33c-p104">The **Edit Properties** dialog box also gives you the option of creating a SQL mirror for your monitoring database (a SQL mirror enables you to maintain two copies of your monitoring database, one copy stored on the monitoring store computer and the other on the SQL mirror computer). To enable mirroring, select T**his SQL instance is in mirroring relation** and enter the port number for the mirror server in the **Mirroring port number** box.</span></span>

7.  <span data-ttu-id="ca33c-120">В диалоговом окне **Свойства** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ca33c-120">In the **Edit Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="ca33c-p105">После связи хранилища мониторинга с интерфейсным пулом необходимо опубликовать новую топологию, чтобы изменения вступили в силу. Для этого выполните следующие действия в средстве построения топологии.</span><span class="sxs-lookup"><span data-stu-id="ca33c-p105">After associating the monitoring store with a Front End pool you must publish the new topology before the changes take effect. To publish your new topology, complete the following steps in Topology Builder:</span></span>

1.  <span data-ttu-id="ca33c-123">Щелкните **Действие**, наведите указатель на пункт **Топология**, а затем нажмите кнопку **Опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="ca33c-123">Click **Action**, point to **Topology**, and then click **Publish**.</span></span>

2.  <span data-ttu-id="ca33c-124">В мастере публикации топологии на странице **Опубликовать топологию** нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ca33c-124">In the Publish Topology wizard, on the **Publish the topology** page, click **Next**.</span></span>

3.  <span data-ttu-id="ca33c-125">На странице **Завершение мастера публикации** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="ca33c-125">On the **Publishing wizard complete** page, click **Finish**.</span></span>

<span data-ttu-id="ca33c-126">После публикации топологии вы можете установить базу данных мониторинга на компьютер, на котором будет размещено хранилище мониторинга.</span><span class="sxs-lookup"><span data-stu-id="ca33c-126">After the topology has been published you can then install the monitoring database on the computer that will host the monitoring store.</span></span> <span data-ttu-id="ca33c-127">Базу данных мониторинга можно установить с помощью командной консоли Lync Server и Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca33c-127">The monitoring database can be installed by using the Lync Server Management Shell and Windows PowerShell.</span></span> <span data-ttu-id="ca33c-128">Чтобы установить базу данных локально (то есть для установки базы данных на том же компьютере, на котором выполняется командная консоль Lync Server), запустите командную консоль на соответствующем компьютере, а затем введите следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="ca33c-128">To install the database locally (that is, to install the database on the same computer where you are running the Lync Server Management Shell), start the Management Shell on the appropriate computer, then type in the following command and press ENTER:</span></span>

    Install-CsDatabase -LocalDatabases

<span data-ttu-id="ca33c-129">При выполнении предыдущей команды install-CsDatabase будет читать текущую топологию Lync Server, определить, какие базы данных необходимо установить на локальном компьютере, а затем автоматически установить и настроить каждую из этих баз данных.</span><span class="sxs-lookup"><span data-stu-id="ca33c-129">When you run the preceding command, Install-CsDatabase will read the current Lync Server topology, determine which databases need to be installed on the local computer, and then automatically install and configure each of those databases.</span></span>

<span data-ttu-id="ca33c-130">Чтобы установить базу данных на удаленном компьютере (т. е. на компьютере, отличном от того, на котором запущена командная консоль), вы должны указать по крайней мере два параметра: ConfiguredDatabases и SqlServerFqdn.</span><span class="sxs-lookup"><span data-stu-id="ca33c-130">To install the database on a remote computer (that is, a computer other than the computer where the Management Shell is running) you must include at least two parameters: the ConfiguredDatabases parameter and the SqlServerFqdn parameter.</span></span> <span data-ttu-id="ca33c-131">Эти параметры указывают командлету Install – CsDatabase получить топологию Lync Server, а затем установите и настройте необходимые базы данных на компьютере, указанном с помощью параметра SqlServerFqdn.</span><span class="sxs-lookup"><span data-stu-id="ca33c-131">These parameters tell the Install-CsDatabase cmdlet to retrieve the Lync Server topology and then install and configure the required databases on the computer specified by the SqlServerFqdn parameter.</span></span> <span data-ttu-id="ca33c-132">Для параметра SqlServerFqdn должно использоваться значение, представляющее полное доменное имя компьютера, на котором будут установлены базы данных.</span><span class="sxs-lookup"><span data-stu-id="ca33c-132">The SqlServerFqdn parameter must use a parameter value representing the fully qualified domain name of the computer where the databases are to be installed.</span></span>

<span data-ttu-id="ca33c-133">Например, следующая команда устанавливает базу данных мониторинга на компьютер atl-sql-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="ca33c-133">For example, this command installs the monitoring database on the computer atl-sql-001.litwareinc.com:</span></span>

    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com

<span data-ttu-id="ca33c-134">Кроме того, вы можете установить базу данных мониторинга, запустив мастер развертывания Lync Server на компьютере, на котором будет размещаться хранилище мониторинга.</span><span class="sxs-lookup"><span data-stu-id="ca33c-134">Alternatively, you can install the monitoring database by running the Lync Server Deployment Wizard on the computer that will host the monitoring store.</span></span> <span data-ttu-id="ca33c-135">Для этого войдите на соответствующий компьютер и выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ca33c-135">To do this, log on to the appropriate computer and complete the following procedure:</span></span>

1.  <span data-ttu-id="ca33c-136">Нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Мастер развертывания Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ca33c-136">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="ca33c-137">В мастере развертывания выберите **Установить или обновить систему Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ca33c-137">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="ca33c-138">На странице **Развертывание** в разделе **Шаг 2. Установка и удаление компонентов Lync Server** нажмите кнопку **Запустить снова**.</span><span class="sxs-lookup"><span data-stu-id="ca33c-138">On the **Deploy** page, under **Step 2: Setup or Remove Lync Server Components**, click **Run Again**.</span></span>

4.  <span data-ttu-id="ca33c-139">В мастере настройки компонентов Lync Server на странице **Настройка компонентов Lync Server** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ca33c-139">In the Setup Lync Server components wizard, on the **Setup Lync Server components** page, click **Next**.</span></span>

5.  <span data-ttu-id="ca33c-140">На странице **укажите путь к MSI** -файлу введите путь к файлу OCSCore. msi (файлу, включенному на установочный носитель Lync Server), а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ca33c-140">On the **Specify path to MSIs** page, type the path to the file Ocscore.msi (a file included with your Lync Server installation media) and then click **Next**.</span></span>

6.  <span data-ttu-id="ca33c-141">На странице **выполнения команд** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="ca33c-141">On the **Executing Commands** page, click **Finish**.</span></span>

<span data-ttu-id="ca33c-142">Чтобы убедиться, что все необходимые службы Lync Server запущены, нажмите кнопку **выполнить** под заголовком **Шаг 4: запуск служб** на странице **развертывания**</span><span class="sxs-lookup"><span data-stu-id="ca33c-142">To ensure that all the required Lync Server services have started, click **Run** under the heading **Step 4: Start Services** on the **Deploy** page</span></span>

</div>

<span> </span>

</div>

</div>

</div>

