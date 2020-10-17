---
title: Развертывание зеркального отображения SQL для обеспечения высокой доступности внутреннего сервера
description: Развертывание зеркального отображения SQL для обеспечения высокой доступности внутреннего сервера.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying SQL mirroring for Back End Server high availability
ms:assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204992(v=OCS.15)
ms:contentKeyID: 48184451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a2ab2d598249c12231668a888b442f830c5d65f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566005"
---
# <a name="deploying-sql-mirroring-for-back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="fe1dc-103">Развертывание зеркального отображения SQL для обеспечения высокой доступности внутреннего сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe1dc-103">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe1dc-104">_**Последнее изменение темы:** 2014-01-08_</span><span class="sxs-lookup"><span data-stu-id="fe1dc-104">_**Topic Last Modified:** 2014-01-08_</span></span>

<span data-ttu-id="fe1dc-105">Чтобы можно было развернуть зеркальное отображение SQL, на серверах должен быть установлен минимум SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-105">To be able to deploy SQL mirroring, your servers must run a minimum of SQL Server 2008 R2.</span></span> <span data-ttu-id="fe1dc-106">Эта версия должна выполняться на всех связанных серверах: основной, зеркальный и следящий.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-106">This version must run on all the involved servers: the primary, mirror, and the witness.</span></span> <span data-ttu-id="fe1dc-107">Дополнительные сведения см [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921) .</span><span class="sxs-lookup"><span data-stu-id="fe1dc-107">For details, see [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921).</span></span>

<span data-ttu-id="fe1dc-108">В целом, для настройки зеркального отображения SQL между двумя внутренними серверами с ресурсом-свидетелем требуется следующее:</span><span class="sxs-lookup"><span data-stu-id="fe1dc-108">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>

  - <span data-ttu-id="fe1dc-109">Версия SQL Server основного сервера должна поддерживать зеркальное отображение SQL.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-109">The primary server’s version of SQL Server must support SQL mirroring.</span></span>

  - <span data-ttu-id="fe1dc-110">На основном ресурсе, зеркальном ресурсе и ресурсе-свидетеле (если развертывается) должна быть установлена одна и та же версия SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-110">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span>

  - <span data-ttu-id="fe1dc-p102">На основном и зеркальном ресурсах должен быть установлен один и тот же выпуск SQL Server. На ресурсе-свидетеле может быть установлен другой выпуск.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-p102">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>

<span data-ttu-id="fe1dc-113">Рекомендации по SQL в терминах того, какие версии SQL поддерживаются для роли следящего сервера, можно найти в разделе "следящий сервер зеркального отображения баз данных" в библиотеке MSDN по адресу [https://go.microsoft.com/fwlink/p/?LinkId=247345](https://go.microsoft.com/fwlink/p/?linkid=247345) .</span><span class="sxs-lookup"><span data-stu-id="fe1dc-113">For SQL best practices in terms of what SQL versions are supported for a Witness role, see "Database Mirroring Witness" in the MSDN Library at [https://go.microsoft.com/fwlink/p/?LinkId=247345](https://go.microsoft.com/fwlink/p/?linkid=247345).</span></span>

<span data-ttu-id="fe1dc-114">Для развертывания зеркального отображения SQL используется построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-114">You use Topology Builder to deploy SQL mirroring.</span></span> <span data-ttu-id="fe1dc-115">Выберите параметр в построителе топологий, чтобы зеркально отобразить базы данных, а в построителе топологий настраивается зеркальное отображение (в том числе Настройка следящего сервера при необходимости) при публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-115">You select an option in Topology Builder to mirror the databases, and Topology Builder sets up the mirroring (including setting up a witness, if you want) when you publish the topology.</span></span> <span data-ttu-id="fe1dc-116">Обратите внимание, что настройка или удаление свидетеля выполняется одновременно с настройкой или удалением зеркала.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-116">Note that you set up or remove the witness at the same time you set up or remove the mirror.</span></span> <span data-ttu-id="fe1dc-117">Отдельной команды для развертывания или удаления только свидетеля не существует.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-117">There is no separate command to deploy or remove only a witness.</span></span>

<span data-ttu-id="fe1dc-118">Для настройки зеркального отображения серверов сначала нужно правильно настроить разрешения базы данных SQL.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-118">To configure server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="fe1dc-119">Подробнее: "Настройка учетных записей входа для зеркального отображения баз данных или групп доступности AlwaysOn (SQL Server)" по адресу [https://go.microsoft.com/fwlink/p/?LinkId=268454](https://go.microsoft.com/fwlink/p/?linkid=268454) .</span><span class="sxs-lookup"><span data-stu-id="fe1dc-119">For details, see "Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268454](https://go.microsoft.com/fwlink/p/?linkid=268454).</span></span>

<span data-ttu-id="fe1dc-p105">При использовании зеркального отображения SQL режим восстановления базы данных всегда задан как **Полный**, т. е. вы должны регулярно внимательно следить за размером журнала транзакций и журналов транзакций резервного копирования, чтобы предотвратить нехватку места на диске на фоновых серверах. Частота резервного копирования журналов транзакций зависит от скорости роста журналов, которая в свою очередь зависит от транзакций баз данных в результате действий пользователей в пуле переднего плана. Рекомендуется определить ожидаемую скорость роста журналов для полезной нагрузки развертывания Lync, чтобы вы могли правильно провести планирование. В следующих статьях представлены дополнительные сведения об управлении резервным копированием и журналами SQL:</span><span class="sxs-lookup"><span data-stu-id="fe1dc-p105">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers. The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool. We recommend that you determine how much transaction log growth is expected for your Lync deployment workload so that you can do the planning accordingly. The following articles provide additional information on SQL backup and log management:</span></span>

  - <span data-ttu-id="fe1dc-124">Модели восстановления баз данных: "модели восстановления (SQL Server)" по адресу [https://go.microsoft.com/fwlink/p/?LinkId=268446](https://go.microsoft.com/fwlink/p/?linkid=268446)</span><span class="sxs-lookup"><span data-stu-id="fe1dc-124">Database recovery models: "Recovery Models (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268446](https://go.microsoft.com/fwlink/p/?linkid=268446)</span></span>

  - <span data-ttu-id="fe1dc-125">Общие сведения о резервном копировании: "Обзор резервного копирования (SQL Server)" в [https://go.microsoft.com/fwlink/p/?LinkId=268449](https://go.microsoft.com/fwlink/p/?linkid=268449)</span><span class="sxs-lookup"><span data-stu-id="fe1dc-125">Backup overview: "Backup Overview (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268449](https://go.microsoft.com/fwlink/p/?linkid=268449)</span></span>

  - <span data-ttu-id="fe1dc-126">Резервное копирование журнала транзакций: "Создание резервной копии журнала транзакций (SQL Server)" по адресу [https://go.microsoft.com/fwlink/p/?LinkId=268452](https://go.microsoft.com/fwlink/p/?linkid=268452)</span><span class="sxs-lookup"><span data-stu-id="fe1dc-126">Backup transaction log: "Backup a Transaction Log (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268452](https://go.microsoft.com/fwlink/p/?linkid=268452)</span></span>

<span data-ttu-id="fe1dc-127">При использовании зеркального отображения SQL топологию можно настроить при создании пулов или после их создания.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-127">With SQL mirroring, you can either configure the topology for mirroring when you create the pools, or after the pools are already created.</span></span>



> [!IMPORTANT]
> <span data-ttu-id="fe1dc-128">Использование построителя топологий или командлетов для настройки и удаления зеркального отображения SQL поддерживается только в том случае, если основной, зеркальный и следящий серверы принадлежат к одному и тому же домену.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-128">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="fe1dc-129">Если необходимо настроить зеркальное отображение SQL для серверов в других доменах, см. документацию по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-129">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span>





> [!IMPORTANT]
> <span data-ttu-id="fe1dc-130">При внесении изменений в отношения зеркального отображения серверных баз данных необходимо перезагрузить все серверы переднего плана в пуле.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-130">Whenever you make a change to a Back End Database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span><BR><span data-ttu-id="fe1dc-131">Чтобы изменить зеркальное отображение (например, изменить расположение зеркала), необходимо использовать построитель топологий для выполнения этих трех действий:</span><span class="sxs-lookup"><span data-stu-id="fe1dc-131">For a change in mirroring, (such as changing the location of a mirror), you must use Topology Builder to perform these three steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="fe1dc-132">Удаление зеркального отображения со старого сервера-зеркала.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-132">Remove mirroring from the old mirror server.</span></span></P>
> <LI>
> <P><span data-ttu-id="fe1dc-133">Добавление зеркального отображения на новый сервер-зеркало.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-133">Add mirroring to the new mirror server.</span></span></P>
> <LI>
> <P><span data-ttu-id="fe1dc-134">Публикация топологии.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-134">Publish the topology.</span></span></P></LI></OL>




> [!NOTE]
> <span data-ttu-id="fe1dc-135">Необходимо создать общий файловый ресурс для записи в нее зеркальных файлов, а служба, в которой выполняются SQL Server и агент SQL, должна иметь доступ для чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-135">A file share has to be created for the mirror files to be written to, and the service that SQL Server and SQL Agent are running under needs read/write access.</span></span> <span data-ttu-id="fe1dc-136">Если служба SQL Server выполняется в контексте сетевой службы, вы можете добавить &lt; домен &gt;&#92;&lt; SQLSERVERNAME &gt; $ как для основного, так и для зеркального серверов SQL в разрешения общего доступа.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-136">If the SQL Server service is running under the context of Network Service, you can add &lt;Domain&gt;&#92;&lt;SQLSERVERNAME&gt;$ of both the Principal and Mirror SQL Servers to the share permissions.</span></span> <span data-ttu-id="fe1dc-137">$ Важно определить, что это учетная запись компьютера.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-137">The $ is important to identify that this is a computer account.</span></span>


<div>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a><span data-ttu-id="fe1dc-138">Настройка зеркального отображения SQL при создании пула в построителе топологий</span><span class="sxs-lookup"><span data-stu-id="fe1dc-138">To configure SQL mirroring while creating a pool in Topology Builder</span></span>

1.  <span data-ttu-id="fe1dc-139">На странице **Определение хранилища SQL** щелкните **Создать** рядом с окном **Хранилище SQL**.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-139">On the **Define the SQL Store** page, click **New** next to the **SQL store** box.</span></span>

2.  <span data-ttu-id="fe1dc-140">На странице **Определение нового хранилища SQL** укажите основное хранилище, выберите **Этот образец SQL связан зеркальным отображением**, укажите номер порта для зеркального отображения SQL (по умолчанию — 5022), а затем щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-140">On the **Define new SQL Store** page, specify the primary store, select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default is 5022), and then click **OK**.</span></span>

3.  <span data-ttu-id="fe1dc-141">Вернитесь на страницу **Определение хранилища SQL** и выберите **Включить зеркальное отображение хранилища SQL**.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-141">Back on the **Define the SQL store** page, select **Enable SQL Store mirroring**.</span></span>

4.  <span data-ttu-id="fe1dc-p108">На странице **Определение нового хранилища SQL** укажите хранилище SQL, которое будет использоваться в качестве зеркала. Выберите **Этот образец SQL связан зеркальным отображением**, укажите номер порта (по умолчанию — 5022), а затем щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-p108">In the **Define new SQL Store** page, specify the SQL store to be used as the mirror. Select **This SQL instance is in mirroring relation**, specify the port number (the default is 5022), and then click **OK**.</span></span>

5.  <span data-ttu-id="fe1dc-144">Если необходимо использовать ресурс-свидетель для этого зеркала, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="fe1dc-144">If you want a witness for this mirror, do the following:</span></span>
    
    1.  <span data-ttu-id="fe1dc-145">Выберите **Использовать ресурс-свидетель зеркального отображения SQL для включения автоматического переключения**.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-145">Select **Use SQL mirroring witness to enable automatic failover**.</span></span>
    
    2.  <span data-ttu-id="fe1dc-146">На странице **Определение хранилища SQL** выберите **Использовать ресурс-свидетель зеркального отображения SQL для включения автоматического переключения** и укажите хранилище SQL для использования в качестве ресурса-свидетеля.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-146">In the **Define the SQL Store** page, select **Use SQL mirroring witness to enable automatic failover**, and specify the SQL store to be used as the witness.</span></span>
    
    3.  <span data-ttu-id="fe1dc-147">Укажите номер порта (по умолчанию — 7022) и щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-147">Specify the port number (the default is 7022) and click **OK**.</span></span>

6.  <span data-ttu-id="fe1dc-148">После определения пула переднего плана и всех остальных ролей в топологии используйте построитель топологий для публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-148">After you are done defining your Front End pool and all other roles in your topology, use Topology Builder to publish the topology.</span></span> <span data-ttu-id="fe1dc-149">Когда топология публикуется, если для пула переднего плана, на котором размещается центральное хранилище управления, включено зеркальное отображение SQL, вы увидите вариант, позволяющий создать как основные, так и зеркальные базы данных хранилища SQL.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-149">When the topology is published, if the Front End pool that hosts Central Management store has SQL mirroring enabled, you will see an option to create both primary and mirror SQL store databases.</span></span>
    
    <span data-ttu-id="fe1dc-150">Щелкните **Настройки** и введите путь, который необходимо использовать в качестве пути к файловому ресурсу общего доступа для резервной копии зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-150">Click **Settings**, and type the path to use as the file share for the mirroring backup.</span></span>
    
    <span data-ttu-id="fe1dc-p110">Щелкните **ОК**, а затем щелкните **Далее** для создания баз данных и публикации топологии. Будут развернуты ресурс-зеркало и ресурс-свидетель (если указано).</span><span class="sxs-lookup"><span data-stu-id="fe1dc-p110">Click **OK** and then **Next** to create the databases and publish the topology. The mirroring and the witness (if specified) will be deployed.</span></span>

<span data-ttu-id="fe1dc-153">Вы можете использовать построитель топологий для изменения свойств уже существующего пула, чтобы включить зеркальное отображение SQL.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-153">You can use Topology Builder to edit the properties of an already existing pool to enable SQL mirroring.</span></span>

</div>

<div>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a><span data-ttu-id="fe1dc-154">Добавление зеркального отображения SQL в существующий интерфейсный пул в построителе топологий</span><span class="sxs-lookup"><span data-stu-id="fe1dc-154">To add SQL mirroring to an existing Front End pool in Topology Builder</span></span>

1.  <span data-ttu-id="fe1dc-155">В построителе топологий щелкните пул правой кнопкой мыши и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-155">In Topology Builder, right-click the pool and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="fe1dc-156">Выберите **Включить зеркальное отображение хранилища SQL**, а затем щелкните **Создать** рядом с элементом **Зеркальное отображение хранилища SQL**.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-156">Select **Enable SQL Store Mirroring**, and then click **New** next to **Mirroring SQL Store**.</span></span>

3.  <span data-ttu-id="fe1dc-157">Укажите хранилище SQL, которое необходимо использовать в качестве зеркала.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-157">Specify the SQL store that you want to use as the mirror.</span></span>

4.  <span data-ttu-id="fe1dc-158">Выберите **Этот образец SQL связан зеркальным отображением**, укажите номер порта зеркального отображения SQL (порт по умолчанию — 5022), а затем щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-158">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number the default port is 5022), and then click **OK**.</span></span>

5.  <span data-ttu-id="fe1dc-159">Если необходимо настроить ресурс-свидетель, выберите **Использовать ресурс-свидетель зеркального отображения SQL для включения автоматического переключения** и щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-159">If you want to configure a witness, select **Use SQL mirroring witness to enable automatic failover**, and click **New**.</span></span>

6.  <span data-ttu-id="fe1dc-160">Укажите хранилище SQL, которое необходимо использовать в качестве свидетеля.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-160">Specify the SQL store that you want to use as the witness.</span></span>

7.  <span data-ttu-id="fe1dc-161">Выберите **Этот образец SQL связан зеркальным отображением**, укажите номер порта зеркального отображения SQL (порт по умолчанию — 7022), а затем щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-161">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default port is 7022), and then click **OK**.</span></span>

8.  <span data-ttu-id="fe1dc-162">Щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-162">Click **OK**.</span></span>

9.  <span data-ttu-id="fe1dc-p111">Опубликуйте топологию. После этого появится запрос на установку базы данных.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-p111">Publish the topology. When you do so, you will be prompted to install the database.</span></span>
    
    <span data-ttu-id="fe1dc-165">В процессе публикации топологии вам будет предложено указать путь к общему файловому ресурсу.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-165">During the topology publishing process, you will be asked to define a file share path.</span></span> <span data-ttu-id="fe1dc-166">Серверы SQL Server, которые участвуют в зеркальном отображении, должны иметь доступ на чтение и запись к этому общему файловому ресурсу для установки зеркала.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-166">The SQL Servers that participate in the mirroring must have read/write access to this file share for the mirror to be established.</span></span>

<span data-ttu-id="fe1dc-167">Затем перед переходом к следующей процедуре необходимо установить базу данных.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-167">You must then install the database before going on to the next procedure.</span></span>

<span data-ttu-id="fe1dc-168">При настройке зеркального отображения сервера SQL Server следует иметь в виду следующее:</span><span class="sxs-lookup"><span data-stu-id="fe1dc-168">You should keep the following in mind when setting up SQL mirroring:</span></span>

  - <span data-ttu-id="fe1dc-169">Если конечная точка зеркального отображения уже существует, она будет повторно использоваться с подключением по указанным портам, а порты, определенные в топологии, будут игнорироваться.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-169">If a mirroring endpoint already exists, it will be reused using the ports defined there, and will ignore the ones you specify in the topology.</span></span>

  - <span data-ttu-id="fe1dc-p113">Любой порт, уже выделенный для других приложений на том же сервере, включая порты для других экземпляров SQL, не должен использоваться для доступных установленных экземпляров SQL. Это означает, что при наличии нескольких экземпляров SQL Server, установленных на одном и том же сервере, они не должны использовать один и тот же порт для зеркального отображения. Для получения подробной информации см. следующие статьи:</span><span class="sxs-lookup"><span data-stu-id="fe1dc-p113">Any port already allocated for other applications on the same server, including those for other SQL instances, should not be used for the installed SQL instances at hand. This implies that if you have more than one SQL instance installed on the same server, they must not use the same port for mirroring. For details, see the following articles:</span></span>
    
      - <span data-ttu-id="fe1dc-173">"Укажите сетевой адрес сервера (зеркальное отображение базы данных)" в библиотеке MSDN по адресу [https://go.microsoft.com/fwlink/p/?LinkId=247346](https://go.microsoft.com/fwlink/p/?linkid=247346)</span><span class="sxs-lookup"><span data-stu-id="fe1dc-173">"Specify a Server Network Address (Database Mirroring)" in the MSDN Library at [https://go.microsoft.com/fwlink/p/?LinkId=247346](https://go.microsoft.com/fwlink/p/?linkid=247346)</span></span>
    
      - <span data-ttu-id="fe1dc-174">"Конечная точка зеркального отображения базы данных (SQL Server)" по адресу [https://go.microsoft.com/fwlink/p/?LinkId=247347](https://go.microsoft.com/fwlink/p/?linkid=247347)</span><span class="sxs-lookup"><span data-stu-id="fe1dc-174">"The Database Mirroring Endpoint (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=247347](https://go.microsoft.com/fwlink/p/?linkid=247347)</span></span>

</div>

<div>

## <a name="using-lync-server-management-shell-cmdlets-to-set-up-sql-mirroring"></a><span data-ttu-id="fe1dc-175">Настройка зеркального отображения SQL с помощью командлетов командной консоли Lync Server</span><span class="sxs-lookup"><span data-stu-id="fe1dc-175">Using Lync Server Management Shell Cmdlets to Set Up SQL Mirroring</span></span>

<span data-ttu-id="fe1dc-176">Самый простой способ настроить зеркальное отображение с помощью построителя топологий, но вы также можете использовать командлеты.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-176">The easiest way to set up mirroring is by using Topology Builder, but you can also do so using cmdlets.</span></span>

1.  <span data-ttu-id="fe1dc-177">Откройте окно командной консоли Lync Server и выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="fe1dc-177">Open a Lync Server Management Shell window and run the following cmdlet:</span></span>
    
        Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose 
    
    <span data-ttu-id="fe1dc-178">Например:</span><span class="sxs-lookup"><span data-stu-id="fe1dc-178">For example:</span></span>
    
        Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose 
    
    <span data-ttu-id="fe1dc-179">Отобразится следующее:</span><span class="sxs-lookup"><span data-stu-id="fe1dc-179">You will see the following:</span></span>
    
        Database Name:rtcxds 
                Data File:D:\CsData\BackendStore\rtc\DbPath\rtcxds.mdf 
                 Log File:D:\CsData\BackendStore\rtc\LogPath\rtcxds.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rtcshared 
                Data File:D:\CsData\BackendStore\rtc\DbPath\rtcshared.mdf 
                 Log File:D:\CsData\BackendStore\rtc\LogPath\rtcshared.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rtcab 
                Data File:D:\CsData\ABSStore\rtc\DbPath\rtcab.mdf 
                 Log File:D:\CsData\ABSStore\rtc\LogPath\rtcab.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rgsconfig 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsconfig.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsconfig.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rgsdyn 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsdyn.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsdyn.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:cpsdyn 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\cpsdyn.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\cpsdyn.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:xds 
                Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\xds.mdf 
                 Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\xds.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:lis 
                Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\lis.mdf 
                 Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\lis.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$
        [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): 

2.  <span data-ttu-id="fe1dc-180">Проверьте следующее:</span><span class="sxs-lookup"><span data-stu-id="fe1dc-180">Verify the following:</span></span>
    
      - <span data-ttu-id="fe1dc-181">Порт 5022 доступен через брандмауэр, если брандмауэр Windows включен на основном сервере SQL Server E04-OCS. Los \_ a. lsipt. local \\ RTC.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-181">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the primary SQL Server e04-ocs.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="fe1dc-182">Порт 5022 доступен через брандмауэр, если брандмауэр Windows включен на зеркальном сервере SQL Server K16-OCS. Los \_ a. lsipt. local \\ RTC.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-182">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the mirror SQL Server K16-ocs.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="fe1dc-183">Порт 7022 доступен через брандмауэр, если брандмауэр Windows включен на свидетеле SQL Server AB14-lct. Los \_ a. lsipt. local \\ RTC.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-183">Port 7022 is accessible through the firewall if Windows Firewall is enabled in the witness SQL Server AB14-lct.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="fe1dc-184">Учетные записи, на которых запущены серверы SQL Server на всех основных и зеркальных серверах SQL, имеют разрешения на чтение и запись для файлового ресурса \\ \\ E04-OCS \\ ксдатабаккуп</span><span class="sxs-lookup"><span data-stu-id="fe1dc-184">Accounts running the SQL Servers on all primary and mirror SQL servers have read/write permission to the file share \\\\E04-OCS\\csdatabackup</span></span>
    
      - <span data-ttu-id="fe1dc-p114">Убедитесь, что поставщик инструментария управления Windows (WMI) работает на всех этих серверах. Командлет использует этого поставщика для поиска информации об учетных записях для служб SQL Server, которые выполняются на всех основных, зеркальных серверах и серверах-свидетелях.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-p114">Verify that the Windows Management Instrumentation (WMI) provider is running on all these servers. The cmdlet uses this provider to find the account information for SQL Server services running on all primary, mirror and witness servers.</span></span>
    
      - <span data-ttu-id="fe1dc-187">Убедитесь, что учетная запись, выполняющая этот командлет, имеет право на создание папок для данных и файлов журналов для всех зеркальных серверов.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-187">Verify that the account running this cmdlet has permission to create the folders for the data and log files for all the mirror servers.</span></span>
    
      - <span data-ttu-id="fe1dc-p115">Обратите внимание, что учетная запись пользователя, применяемая экземпляром SQL для запуска, должна обладать разрешениями на чтение и запись для файлового ресурса. Если ресурс размещен на другом сервере, экземпляр SQL использует локальную системную учетную запись, вы должны предоставить разрешения для файлового ресурса серверу, на котором размещен экземпляр SQL.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-p115">Note that the user account that the SQL instance uses to run must have read/write permission to the file share. If the file share is on a different server, and the SQL instance runs a local system account, you must grant file share permissions to the server that hosts the SQL instance.</span></span>

3.  <span data-ttu-id="fe1dc-190">Введите A и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-190">Type A and press ENTER.</span></span>
    
    <span data-ttu-id="fe1dc-191">Зеркальное отображение будет настроено.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-191">The mirroring will be configured.</span></span>

<span data-ttu-id="fe1dc-192">**Install — CsMirrorDatabase** устанавливает зеркало и настраивает зеркальное отображение для всех баз данных, присутствующих в основном хранилище SQL.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-192">**Install-CsMirrorDatabase** installs the mirror and configures mirroring for all the databases that are present on the primary SQL store.</span></span> <span data-ttu-id="fe1dc-193">Если требуется настроить зеркальное отображение только для определенных баз данных, можно использовать параметр – Датабасетипе или, если необходимо настроить зеркальное отображение для всех баз данных, кроме нескольких, можно использовать параметр-Ексклудедатабаселист, а также список имен баз данных с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-193">If you want to configure mirroring for only specific databases, you can use the –DatabaseType option, or if you want to configure mirroring for all databases except for a few, you can use the -ExcludeDatabaseList option, along with a comma-separated list of database names to exclude.</span></span>

<span data-ttu-id="fe1dc-194">Например, если вы добавили в **Install-CsMirrorDatabase** следующую функцию, будет выполнено зеркальное отображение всех баз данных, кроме rtcxds.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-194">For example, if you add the following option to **Install-CsMirrorDatabase**, all databases except rtcab and rtcxds will be mirrored.</span></span>

`-ExcludeDatabaseList rtcab,rtcxds`

<span data-ttu-id="fe1dc-195">Например, если вы добавили в **Install-CsMirrorDatabase**, следующую функцию, будет выполнено зеркальное отображение баз данных rtcab, rtcshared и rtcxds.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-195">For example, if you add the following option to **Install-CsMirrorDatabase**, only the rtcab, rtcshared, and rtcxds databases will be mirrored.</span></span>

`-DatabaseType User`

</div>

<div>

## <a name="removing-or-changing-sql-mirroring"></a><span data-ttu-id="fe1dc-196">Удаление и изменение зеркального отображения SQL</span><span class="sxs-lookup"><span data-stu-id="fe1dc-196">Removing or Changing SQL Mirroring</span></span>

<span data-ttu-id="fe1dc-p117">Чтобы удалить зеркальное отображение SQL пула в построителе топологий, сначала следует использовать командлет для удаления зеркала в SQL Server. Затем вы можете использовать построитель топологий, чтобы удалить зеркало из топологии. Чтобы сделать это в SQL Server, запустите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="fe1dc-p117">To remove the SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server. You can then use Topology Builder to remove the mirror from the topology. To remove the mirror in SQL Server, use the following cmdlet:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

<span data-ttu-id="fe1dc-200">Например, чтобы удалить зеркальное отображение и сбросить базы данных для баз данных User, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fe1dc-200">For example, to remove mirroring and drop the databases for the User databases, type the following:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

<span data-ttu-id="fe1dc-201">Этот `-DropExistingDatabasesOnMirror` параметр приводит к удалению затронутых баз данных из зеркала.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-201">The `-DropExistingDatabasesOnMirror` option causes the affected databases to be deleted from the mirror.</span></span>

<span data-ttu-id="fe1dc-202">Затем чтобы удалить зеркало из топологии, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="fe1dc-202">Then, to remove the mirror from the topology, do the following:</span></span>

1.  <span data-ttu-id="fe1dc-203">В построителе топологии щелкните пул правой кнопкой мыши и щелкните **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-203">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="fe1dc-204">Снимите флажок **Включить зеркальное отображение хранилища SQL** и щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-204">Uncheck **Enable SQL Store Mirroring** and click **OK**.</span></span>

3.  <span data-ttu-id="fe1dc-205">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-205">Publish the topology.</span></span>

</div>

<div>

## <a name="removing-a-mirroring-witness"></a><span data-ttu-id="fe1dc-206">Удаление следящего сервера зеркального отображения</span><span class="sxs-lookup"><span data-stu-id="fe1dc-206">Removing a Mirroring Witness</span></span>

<span data-ttu-id="fe1dc-207">Используйте эту процедуру, если необходимо удалить следящий сервер из конфигурации зеркального отображения внутреннего сервера.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-207">Use this procedure if you need to remove the witness from a Back End Server mirroring configuration.</span></span>

1.  <span data-ttu-id="fe1dc-208">В построителе топологии щелкните пул правой кнопкой мыши и щелкните **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-208">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="fe1dc-209">Снимите флажок **Использовать свидетель зеркального отображения SQL Server для автоматического перехода на другой ресурс** и нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-209">Uncheck **Use SQL Server mirroring witness to enable automatic failover** and click **OK**.</span></span>

3.  <span data-ttu-id="fe1dc-210">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-210">Publish the topology.</span></span>
    
    <span data-ttu-id="fe1dc-211">После публикации топологии построитель топологий отобразит сообщение, содержащее следующие</span><span class="sxs-lookup"><span data-stu-id="fe1dc-211">After publishing the topology, Topology Builder you will see a message that includes the following</span></span>
    
        Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
    
    <span data-ttu-id="fe1dc-212">Тем не менее, не выполняйте это действие и не вводите `Uninstall-CsMirrorDatabase` так, как это приведет к удалению всей конфигурации зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="fe1dc-212">However, do not follow that step, and do not type `Uninstall-CsMirrorDatabase` as that would uninstall the entire mirroring configuration.</span></span>

4.  <span data-ttu-id="fe1dc-213">Чтобы удалить только следящий сервер из конфигурации SQL Server, следуйте инструкциям в разделе "Удаление следящего сервера из сеанса зеркального отображения базы данных (SQL Server)" по адресу [https://go.microsoft.com/fwlink/p/?LinkId=268456](https://go.microsoft.com/fwlink/p/?linkid=268456) .</span><span class="sxs-lookup"><span data-stu-id="fe1dc-213">To remove just the witness from the SQL Server configuration, follow the instructions in "Remove the Witness from a Database Mirroring Session (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268456](https://go.microsoft.com/fwlink/p/?linkid=268456).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

