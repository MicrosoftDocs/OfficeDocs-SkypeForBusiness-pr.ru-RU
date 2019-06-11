---
title: Развертывание зеркального отображения SQL Server для обеспечения высокой доступности внутреннего сервера
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying SQL mirroring for Back End Server high availability
ms:assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204992(v=OCS.15)
ms:contentKeyID: 48184451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8eb8c9647c24f326b1a2a51c99e7fa4ee5eafa23
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834539"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-sql-mirroring-for-back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="84ab9-102">Развертывание зеркального отображения SQL Server для обеспечения высокой доступности внутреннего сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84ab9-102">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84ab9-103">_**Тема последнего изменения:** 2014-01-08_</span><span class="sxs-lookup"><span data-stu-id="84ab9-103">_**Topic Last Modified:** 2014-01-08_</span></span>

<span data-ttu-id="84ab9-104">Чтобы обеспечить возможность развертывания зеркального отображения SQL, серверы должны работать под управлением, как минимум, версии SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="84ab9-104">To be able to deploy SQL mirroring, your servers must run a minimum of SQL Server 2008 R2.</span></span> <span data-ttu-id="84ab9-105">Эта версия должна выполнятся на всех серверах-участниках: на сервере-источнике, зеркальном сервере и следящем сервере.</span><span class="sxs-lookup"><span data-stu-id="84ab9-105">This version must run on all the involved servers: the primary, mirror, and the witness.</span></span> <span data-ttu-id="84ab9-106">Подробности можно найти в [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921)разделе.</span><span class="sxs-lookup"><span data-stu-id="84ab9-106">For details, see [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921).</span></span>

<span data-ttu-id="84ab9-107">В целом, для настройки зеркального отображения SQL между двумя внутренними серверами с ресурсом-свидетелем требуется следующее:</span><span class="sxs-lookup"><span data-stu-id="84ab9-107">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>

  - <span data-ttu-id="84ab9-108">Версия SQL Server основного сервера должна поддерживать зеркальное отображение SQL.</span><span class="sxs-lookup"><span data-stu-id="84ab9-108">The primary server’s version of SQL Server must support SQL mirroring.</span></span>

  - <span data-ttu-id="84ab9-109">На основном ресурсе, зеркальном ресурсе и ресурсе-свидетеле (если развертывается) должна быть установлена одна и та же версия SQL Server.</span><span class="sxs-lookup"><span data-stu-id="84ab9-109">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span>

  - <span data-ttu-id="84ab9-p102">На основном и зеркальном ресурсах должен быть установлен один и тот же выпуск SQL Server. На ресурсе-свидетеле может быть установлен другой выпуск.</span><span class="sxs-lookup"><span data-stu-id="84ab9-p102">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>

<span data-ttu-id="84ab9-112">Рекомендации по использованию SQL в отношении того, какие версии SQL поддерживаются для роли следящего сервера, описаны в разделе "следящий сервер зеркального отображения базы [http://go.microsoft.com/fwlink/p/?LinkId=247345](http://go.microsoft.com/fwlink/p/?linkid=247345)данных" в библиотеке MSDN по адресу.</span><span class="sxs-lookup"><span data-stu-id="84ab9-112">For SQL best practices in terms of what SQL versions are supported for a Witness role, see "Database Mirroring Witness" in the MSDN Library at [http://go.microsoft.com/fwlink/p/?LinkId=247345](http://go.microsoft.com/fwlink/p/?linkid=247345).</span></span>

<span data-ttu-id="84ab9-113">Для развертывания SQL Mirror используется Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="84ab9-113">You use Topology Builder to deploy SQL mirroring.</span></span> <span data-ttu-id="84ab9-114">Вы выбираете параметр в построителе топологии для отражения баз данных, а построитель топологии задает зеркальное отображение (в том числе настройку следящего сервера при необходимости) при публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="84ab9-114">You select an option in Topology Builder to mirror the databases, and Topology Builder sets up the mirroring (including setting up a witness, if you want) when you publish the topology.</span></span> <span data-ttu-id="84ab9-115">Обратите внимание, что настройка или удаление свидетеля выполняется одновременно с настройкой или удалением зеркала.</span><span class="sxs-lookup"><span data-stu-id="84ab9-115">Note that you set up or remove the witness at the same time you set up or remove the mirror.</span></span> <span data-ttu-id="84ab9-116">Отдельной команды для развертывания или удаления только свидетеля не существует.</span><span class="sxs-lookup"><span data-stu-id="84ab9-116">There is no separate command to deploy or remove only a witness.</span></span>

<span data-ttu-id="84ab9-117">Для настройки зеркального отображения серверов сначала нужно правильно настроить разрешения базы данных SQL.</span><span class="sxs-lookup"><span data-stu-id="84ab9-117">To configure server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="84ab9-118">Подробные сведения можно найти в [http://go.microsoft.com/fwlink/p/?LinkId=268454](http://go.microsoft.com/fwlink/p/?linkid=268454)разделе Настройка учетных записей входа для зеркального отображения или групп доступности ALWAYSON (SQL Server).</span><span class="sxs-lookup"><span data-stu-id="84ab9-118">For details, see "Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268454](http://go.microsoft.com/fwlink/p/?linkid=268454).</span></span>

<span data-ttu-id="84ab9-p105">При использовании зеркального отображения SQL режим восстановления базы данных всегда задан как**Полный**, т. е. вы должны регулярно внимательно следить за размером журнала транзакций и журналов транзакций резервного копирования, чтобы предотвратить нехватку места на диске на внутренних серверах. Частота резервного копирования журналов транзакций зависит от скорости роста журналов, которая в свою очередь зависит от транзакций баз данных в результате действий пользователей в интерфейсном пуле. Рекомендуется определить ожидаемую скорость роста журналов для полезной нагрузки развертывания Lync, чтобы вы могли правильно провести планирование. В следующих статьях представлены дополнительные сведения об управлении резервным копированием и журналами SQL.</span><span class="sxs-lookup"><span data-stu-id="84ab9-p105">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers. The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool. We recommend that you determine how much transaction log growth is expected for your Lync deployment workload so that you can do the planning accordingly. The following articles provide additional information on SQL backup and log management:</span></span>

  - <span data-ttu-id="84ab9-123">Модели восстановления базы данных: "модели восстановления (SQL Server)" в[http://go.microsoft.com/fwlink/p/?LinkId=268446](http://go.microsoft.com/fwlink/p/?linkid=268446)</span><span class="sxs-lookup"><span data-stu-id="84ab9-123">Database recovery models: "Recovery Models (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268446](http://go.microsoft.com/fwlink/p/?linkid=268446)</span></span>

  - <span data-ttu-id="84ab9-124">Обзор резервного копирования: "резервный обзор (SQL Server)" на[http://go.microsoft.com/fwlink/p/?LinkId=268449](http://go.microsoft.com/fwlink/p/?linkid=268449)</span><span class="sxs-lookup"><span data-stu-id="84ab9-124">Backup overview: "Backup Overview (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268449](http://go.microsoft.com/fwlink/p/?linkid=268449)</span></span>

  - <span data-ttu-id="84ab9-125">Резервное копирование журнала транзакций: "Создание резервной копии журнала транзакций (SQL Server)" на[http://go.microsoft.com/fwlink/p/?LinkId=268452](http://go.microsoft.com/fwlink/p/?linkid=268452)</span><span class="sxs-lookup"><span data-stu-id="84ab9-125">Backup transaction log: "Backup a Transaction Log (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268452](http://go.microsoft.com/fwlink/p/?linkid=268452)</span></span>

<span data-ttu-id="84ab9-126">При использовании зеркального отображения SQL топологию можно настроить при создании пулов или после их создания.</span><span class="sxs-lookup"><span data-stu-id="84ab9-126">With SQL mirroring, you can either configure the topology for mirroring when you create the pools, or after the pools are already created.</span></span>



> [!IMPORTANT]
> <span data-ttu-id="84ab9-127">Использование построителя топологии или командлетов для настройки и удаления зеркального отображения SQL поддерживается только в том случае, если все серверы, которые являются основными, зеркальными и следящими (при необходимости), принадлежат одному домену.</span><span class="sxs-lookup"><span data-stu-id="84ab9-127">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="84ab9-128">Если необходимо настроить зеркальное отображение SQL для серверов в других доменах, см. документацию по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="84ab9-128">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span>





> [!IMPORTANT]
> <span data-ttu-id="84ab9-129">При внесении изменений в отношения зеркального отображения внутренних баз данных необходимо перезагрузить все серверы переднего плана в пуле. </span><span class="sxs-lookup"><span data-stu-id="84ab9-129">Whenever you make a change to a Back End Database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span><BR><span data-ttu-id="84ab9-130">Чтобы изменить зеркальное отображение (например, изменить расположение зеркала), необходимо выполнить следующие три действия с помощью Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="84ab9-130">For a change in mirroring, (such as changing the location of a mirror), you must use Topology Builder to perform these three steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="84ab9-131">Удаление зеркального отображения со старого сервера-зеркала.</span><span class="sxs-lookup"><span data-stu-id="84ab9-131">Remove mirroring from the old mirror server.</span></span></P>
> <LI>
> <P><span data-ttu-id="84ab9-132">Добавление зеркального отображения на новый сервер-зеркало.</span><span class="sxs-lookup"><span data-stu-id="84ab9-132">Add mirroring to the new mirror server.</span></span></P>
> <LI>
> <P><span data-ttu-id="84ab9-133">Публикация топологии.</span><span class="sxs-lookup"><span data-stu-id="84ab9-133">Publish the topology.</span></span></P></LI></OL>




> [!NOTE]
> <span data-ttu-id="84ab9-134">Вам потребуется создать общую папку для записи в нее зеркальных файлов, кроме того, службе, от имени которой выполняются SQL Server и агент SQL, необходим доступ для записи и чтения.</span><span class="sxs-lookup"><span data-stu-id="84ab9-134">A file share has to be created for the mirror files to be written to, and the service that SQL Server and SQL Agent are running under needs read/write access.</span></span> <span data-ttu-id="84ab9-135">Если служба SQL Server выполняется в контексте сетевой службы, вы можете &lt;добавить Domain&gt;&#92;&lt;склсервернаме&gt;$ для основного и зеркального серверов SQL в разрешения общего доступа.</span><span class="sxs-lookup"><span data-stu-id="84ab9-135">If the SQL Server service is running under the context of Network Service, you can add &lt;Domain&gt;&#92;&lt;SQLSERVERNAME&gt;$ of both the Principal and Mirror SQL Servers to the share permissions.</span></span> <span data-ttu-id="84ab9-136">Использование символа $ важно для определения того, что это значение является учетной записью компьютера.</span><span class="sxs-lookup"><span data-stu-id="84ab9-136">The $ is important to identify that this is a computer account.</span></span>


<div>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a><span data-ttu-id="84ab9-137">Настройка зеркального отображения SQL при создании пула в построителе топологии</span><span class="sxs-lookup"><span data-stu-id="84ab9-137">To configure SQL mirroring while creating a pool in Topology Builder</span></span>

1.  <span data-ttu-id="84ab9-138">На странице **Определение хранилища SQL** щелкните **Создать** рядом с полем **Хранилище SQL**. </span><span class="sxs-lookup"><span data-stu-id="84ab9-138">On the **Define the SQL Store** page, click **New** next to the **SQL store** box.</span></span>

2.  <span data-ttu-id="84ab9-139">На странице **Определение нового хранилища SQL** укажите основное хранилище, выберите **Этот экземпляр SQL находится в отношении зеркального отображения**, укажите номер порта для зеркального отображения SQL (по умолчанию — 5022), а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="84ab9-139">On the **Define new SQL Store** page, specify the primary store, select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default is 5022), and then click **OK**.</span></span>

3.  <span data-ttu-id="84ab9-140">Вернитесь на страницу **Определение хранилища SQL** и выберите **Включить зеркальное отображение хранилища SQL**. </span><span class="sxs-lookup"><span data-stu-id="84ab9-140">Back on the **Define the SQL store** page, select **Enable SQL Store mirroring**.</span></span>

4.  <span data-ttu-id="84ab9-p108">На странице **Определение нового хранилища SQL** укажите хранилище SQL, которое будет использоваться в качестве зеркала. Выберите **Этот экземпляр SQL находится в отношении зеркального отображения**, укажите номер порта (по умолчанию — 5022), а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="84ab9-p108">In the **Define new SQL Store** page, specify the SQL store to be used as the mirror. Select **This SQL instance is in mirroring relation**, specify the port number (the default is 5022), and then click **OK**.</span></span>

5.  <span data-ttu-id="84ab9-143">Если необходимо использовать ресурс-свидетель для этого зеркала, выполните следующие действия. </span><span class="sxs-lookup"><span data-stu-id="84ab9-143">If you want a witness for this mirror, do the following:</span></span>
    
    1.  <span data-ttu-id="84ab9-144">Выберите **Использовать ресурс-свидетель зеркального отображения SQL для включения автоматического переключения**. </span><span class="sxs-lookup"><span data-stu-id="84ab9-144">Select **Use SQL mirroring witness to enable automatic failover**.</span></span>
    
    2.  <span data-ttu-id="84ab9-145">На странице **Определение хранилища SQL** выберите **Использовать ресурс-свидетель зеркального отображения SQL для включения автоматического переключения** и укажите хранилище SQL для использования в качестве ресурса-свидетеля. </span><span class="sxs-lookup"><span data-stu-id="84ab9-145">In the **Define the SQL Store** page, select **Use SQL mirroring witness to enable automatic failover**, and specify the SQL store to be used as the witness.</span></span>
    
    3.  <span data-ttu-id="84ab9-146">Укажите номер порта (по умолчанию — 7022) и щелкните **ОК**. </span><span class="sxs-lookup"><span data-stu-id="84ab9-146">Specify the port number (the default is 7022) and click **OK**.</span></span>

6.  <span data-ttu-id="84ab9-147">После того как вы закончите определение пула переднего плана и всех других ролей в топологии, используйте построитель топологии для публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="84ab9-147">After you are done defining your Front End pool and all other roles in your topology, use Topology Builder to publish the topology.</span></span> <span data-ttu-id="84ab9-148">Если топология опубликована, то если в пуле переднего плана, на котором размещается хранилище Центрального управления, включено зеркальное отображение SQL, вы увидите параметр для создания баз данных основного и зеркального хранилища SQL.</span><span class="sxs-lookup"><span data-stu-id="84ab9-148">When the topology is published, if the Front End pool that hosts Central Management store has SQL mirroring enabled, you will see an option to create both primary and mirror SQL store databases.</span></span>
    
    <span data-ttu-id="84ab9-149">Щелкните **Параметры** и введите путь, который необходимо использовать в качестве пути к общей папке для резервной копии зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="84ab9-149">Click **Settings**, and type the path to use as the file share for the mirroring backup.</span></span>
    
    <span data-ttu-id="84ab9-p110">Нажмите кнопку **ОК**, а затем кнопку **Далее** для создания баз данных и публикации топологии. Будут развернуты ресурс-зеркало и ресурс-свидетель (если указан).</span><span class="sxs-lookup"><span data-stu-id="84ab9-p110">Click **OK** and then **Next** to create the databases and publish the topology. The mirroring and the witness (if specified) will be deployed.</span></span>

<span data-ttu-id="84ab9-152">Вы можете использовать Topology Builder, чтобы изменить свойства уже существующего пула, чтобы включить зеркальное отображение SQL.</span><span class="sxs-lookup"><span data-stu-id="84ab9-152">You can use Topology Builder to edit the properties of an already existing pool to enable SQL mirroring.</span></span>

</div>

<div>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a><span data-ttu-id="84ab9-153">Добавление зеркального отображения SQL к существующему пулу переднего плана в построителе топологии</span><span class="sxs-lookup"><span data-stu-id="84ab9-153">To add SQL mirroring to an existing Front End pool in Topology Builder</span></span>

1.  <span data-ttu-id="84ab9-154">В построителе топологии щелкните пул правой кнопкой мыши и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="84ab9-154">In Topology Builder, right-click the pool and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="84ab9-155">Выберите **Включить зеркальное отображение хранилища SQL**, а затем щелкните **Создать** рядом с элементом **Зеркальное отображение хранилища SQL**. </span><span class="sxs-lookup"><span data-stu-id="84ab9-155">Select **Enable SQL Store Mirroring**, and then click **New** next to **Mirroring SQL Store**.</span></span>

3.  <span data-ttu-id="84ab9-156">Укажите хранилище SQL, которое необходимо использовать в качестве зеркала. </span><span class="sxs-lookup"><span data-stu-id="84ab9-156">Specify the SQL store that you want to use as the mirror.</span></span>

4.  <span data-ttu-id="84ab9-157">Выберите **Этот экземпляр SQL находится в отношении зеркального отображения**, укажите номер порта зеркального отображения SQL (порт по умолчанию — 5022), а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="84ab9-157">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number the default port is 5022), and then click **OK**.</span></span>

5.  <span data-ttu-id="84ab9-158">Если необходимо настроить ресурс-свидетель, выберите **Использовать свидетель зеркального отображения SQL для включения автоматической отработки отказа** и щелкните **Создать**. </span><span class="sxs-lookup"><span data-stu-id="84ab9-158">If you want to configure a witness, select **Use SQL mirroring witness to enable automatic failover**, and click **New**.</span></span>

6.  <span data-ttu-id="84ab9-159">Укажите хранилище SQL, которое необходимо использовать в качестве свидетеля. </span><span class="sxs-lookup"><span data-stu-id="84ab9-159">Specify the SQL store that you want to use as the witness.</span></span>

7.  <span data-ttu-id="84ab9-160">Выберите **Этот экземпляр SQL находится в отношении зеркального отображения**, укажите номер порта зеркального отображения SQL (порт по умолчанию — 7022), а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="84ab9-160">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default port is 7022), and then click **OK**.</span></span>

8.  <span data-ttu-id="84ab9-161">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="84ab9-161">Click **OK**.</span></span>

9.  <span data-ttu-id="84ab9-p111">Опубликуйте топологию. После этого появится запрос на установку базы данных. </span><span class="sxs-lookup"><span data-stu-id="84ab9-p111">Publish the topology. When you do so, you will be prompted to install the database.</span></span>
    
    <span data-ttu-id="84ab9-p112">В процессе публикации топологии отобразится запрос на определение пути к общей папке. Серверы SQL Server, которые участвуют в зеркалировании, должны иметь доступ на чтение и запись для этой общей папки для выполнения зеркалирования.</span><span class="sxs-lookup"><span data-stu-id="84ab9-p112">During the topology publishing process, you will be asked to define a file share path. The SQL Servers that participate in the mirroring must have read/write access to this file share for the mirror to be established.</span></span>

<span data-ttu-id="84ab9-166">Перед переходом к следующей процедуре необходимо установить базу данных.</span><span class="sxs-lookup"><span data-stu-id="84ab9-166">You must then install the database before going on to the next procedure.</span></span>

<span data-ttu-id="84ab9-167">При настройке зеркального отображения сервера SQL Server следует иметь в виду следующее.</span><span class="sxs-lookup"><span data-stu-id="84ab9-167">You should keep the following in mind when setting up SQL mirroring:</span></span>

  - <span data-ttu-id="84ab9-168">Если конечная точка зеркального отображения уже существует, она будет повторно использоваться с подключением по указанным портам, а порты, определенные в топологии, будут игнорироваться.</span><span class="sxs-lookup"><span data-stu-id="84ab9-168">If a mirroring endpoint already exists, it will be reused using the ports defined there, and will ignore the ones you specify in the topology.</span></span>

  - <span data-ttu-id="84ab9-p113">Любой порт, уже выделенный для других приложений на том же сервере, включая порты для других экземпляров SQL, не должен использоваться для доступных установленных экземпляров SQL. Это означает, что при наличии нескольких экземпляров SQL Server, установленных на одном и том же сервере, они не должны использовать один и тот же порт для зеркального отображения. Для получения подробной информации см. следующие статьи:</span><span class="sxs-lookup"><span data-stu-id="84ab9-p113">Any port already allocated for other applications on the same server, including those for other SQL instances, should not be used for the installed SQL instances at hand. This implies that if you have more than one SQL instance installed on the same server, they must not use the same port for mirroring. For details, see the following articles:</span></span>
    
      - <span data-ttu-id="84ab9-172">"Укажите сетевой адрес сервера (зеркальное отображение базы данных)" в библиотеке MSDN по адресу[http://go.microsoft.com/fwlink/p/?LinkId=247346](http://go.microsoft.com/fwlink/p/?linkid=247346)</span><span class="sxs-lookup"><span data-stu-id="84ab9-172">"Specify a Server Network Address (Database Mirroring)" in the MSDN Library at [http://go.microsoft.com/fwlink/p/?LinkId=247346](http://go.microsoft.com/fwlink/p/?linkid=247346)</span></span>
    
      - <span data-ttu-id="84ab9-173">"Конечная точка зеркального отображения базы данных (SQL Server)" в[http://go.microsoft.com/fwlink/p/?LinkId=247347](http://go.microsoft.com/fwlink/p/?linkid=247347)</span><span class="sxs-lookup"><span data-stu-id="84ab9-173">"The Database Mirroring Endpoint (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=247347](http://go.microsoft.com/fwlink/p/?linkid=247347)</span></span>

</div>

<div>

## <a name="using-lync-server-management-shell-cmdlets-to-set-up-sql-mirroring"></a><span data-ttu-id="84ab9-174">Использование командлетов командной консоли Lync Server для настройки зеркального отображения SQL</span><span class="sxs-lookup"><span data-stu-id="84ab9-174">Using Lync Server Management Shell Cmdlets to Set Up SQL Mirroring</span></span>

<span data-ttu-id="84ab9-175">Проще всего настроить зеркальное отображение с помощью построителя топологии, но вы также можете использовать командлеты.</span><span class="sxs-lookup"><span data-stu-id="84ab9-175">The easiest way to set up mirroring is by using Topology Builder, but you can also do so using cmdlets.</span></span>

1.  <span data-ttu-id="84ab9-176">Откройте окно командной консоли Lync Server и запустите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="84ab9-176">Open a Lync Server Management Shell window and run the following cmdlet:</span></span>
    
        Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose 
    
    <span data-ttu-id="84ab9-177">Например:</span><span class="sxs-lookup"><span data-stu-id="84ab9-177">For example:</span></span>
    
        Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose 
    
    <span data-ttu-id="84ab9-178">Отобразится следующее:</span><span class="sxs-lookup"><span data-stu-id="84ab9-178">You will see the following:</span></span>
    
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

2.  <span data-ttu-id="84ab9-179">Проверьте следующее:</span><span class="sxs-lookup"><span data-stu-id="84ab9-179">Verify the following:</span></span>
    
      - <span data-ttu-id="84ab9-180">Порт 5022 доступен через брандмауэр, если включен брандмауэр Windows на основном сервере SQL Server E04-OCS. Лос\_a. лсипт. местного\\времени.</span><span class="sxs-lookup"><span data-stu-id="84ab9-180">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the primary SQL Server e04-ocs.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="84ab9-181">Порт 5022 доступен через брандмауэр, если включен брандмауэр Windows на зеркальном сервере SQL Server K16-OCS. Лос\_a. лсипт. local\\RTC.</span><span class="sxs-lookup"><span data-stu-id="84ab9-181">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the mirror SQL Server K16-ocs.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="84ab9-182">Порт 7022 доступен через брандмауэр, если в свидетеле сервера SQL Server AB14-lct. Лос\_a. лсипт. local\\, включен брандмауэр Windows.</span><span class="sxs-lookup"><span data-stu-id="84ab9-182">Port 7022 is accessible through the firewall if Windows Firewall is enabled in the witness SQL Server AB14-lct.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="84ab9-183">Учетные записи, на которых запущены серверы SQL Server на всех основных и зеркальных серверах SQL, имеют \\ \\разрешение на чтение\\и запись в файл общего доступа E04-OCS ксдатабаккуп</span><span class="sxs-lookup"><span data-stu-id="84ab9-183">Accounts running the SQL Servers on all primary and mirror SQL servers have read/write permission to the file share \\\\E04-OCS\\csdatabackup</span></span>
    
      - <span data-ttu-id="84ab9-p114">Убедитесь, что поставщик инструментария управления Windows (WMI) работает на всех этих серверах. Командлет использует этот поставщик для поиска информации об учетных записях для служб SQL Server, которые выполняются на всех серверах-источниках, зеркальных серверах и следящих серверах. </span><span class="sxs-lookup"><span data-stu-id="84ab9-p114">Verify that the Windows Management Instrumentation (WMI) provider is running on all these servers. The cmdlet uses this provider to find the account information for SQL Server services running on all primary, mirror and witness servers.</span></span>
    
      - <span data-ttu-id="84ab9-186">Убедитесь, что учетная запись, выполняющая этот командлет, имеет разрешение на создание папок для данных и файлов журналов для всех зеркальных серверов. </span><span class="sxs-lookup"><span data-stu-id="84ab9-186">Verify that the account running this cmdlet has permission to create the folders for the data and log files for all the mirror servers.</span></span>
    
      - <span data-ttu-id="84ab9-p115">Обратите внимание, что учетная запись пользователя, используемая экземпляром SQL для запуска, должна обладать разрешениями на чтение и запись для общей папки. Если общая папка размещена на другом сервере, и экземпляр SQL использует локальную системную учетную запись, вы должны предоставить разрешения для общей папки серверу, на котором размещен экземпляр SQL.</span><span class="sxs-lookup"><span data-stu-id="84ab9-p115">Note that the user account that the SQL instance uses to run must have read/write permission to the file share. If the file share is on a different server, and the SQL instance runs a local system account, you must grant file share permissions to the server that hosts the SQL instance.</span></span>

3.  <span data-ttu-id="84ab9-189">Введите A и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="84ab9-189">Type A and press ENTER.</span></span>
    
    <span data-ttu-id="84ab9-190">Зеркальное отображение будет настроено.</span><span class="sxs-lookup"><span data-stu-id="84ab9-190">The mirroring will be configured.</span></span>

<span data-ttu-id="84ab9-191">**Install-ксмиррордатабасе** устанавливает зеркало и настраивает зеркальное отображение для всех баз данных, которые находятся в основном хранилище SQL.</span><span class="sxs-lookup"><span data-stu-id="84ab9-191">**Install-CsMirrorDatabase** installs the mirror and configures mirroring for all the databases that are present on the primary SQL store.</span></span> <span data-ttu-id="84ab9-192">Если вы хотите настроить зеркальное отображение только для определенных баз данных, можно использовать параметр – Датабасетипе или, если вы хотите настроить зеркальное отображение для всех баз данных, кроме нескольких, можно использовать параметр-Ексклудедатабаселист вместе с списком баз данных, разделенных запятыми. имена, которые нужно исключить.</span><span class="sxs-lookup"><span data-stu-id="84ab9-192">If you want to configure mirroring for only specific databases, you can use the –DatabaseType option, or if you want to configure mirroring for all databases except for a few, you can use the -ExcludeDatabaseList option, along with a comma-separated list of database names to exclude.</span></span>

<span data-ttu-id="84ab9-193">Например, если вы добавите в **Install-CsMirrorDatabase** следующий параметр, будет выполнено зеркальное отображение всех баз данных, кроме rtcxds.</span><span class="sxs-lookup"><span data-stu-id="84ab9-193">For example, if you add the following option to **Install-CsMirrorDatabase**, all databases except rtcab and rtcxds will be mirrored.</span></span>

`-ExcludeDatabaseList rtcab,rtcxds`

<span data-ttu-id="84ab9-194">Например, если вы добавите в **Install-CsMirrorDatabase**, следующий параметр, будет выполнено зеркальное отображение баз данных rtcab, rtcshared и rtcxds.</span><span class="sxs-lookup"><span data-stu-id="84ab9-194">For example, if you add the following option to **Install-CsMirrorDatabase**, only the rtcab, rtcshared, and rtcxds databases will be mirrored.</span></span>

`-DatabaseType User`

</div>

<div>

## <a name="removing-or-changing-sql-mirroring"></a><span data-ttu-id="84ab9-195">Удаление и изменение зеркального отображения SQL</span><span class="sxs-lookup"><span data-stu-id="84ab9-195">Removing or Changing SQL Mirroring</span></span>

<span data-ttu-id="84ab9-p117">Чтобы удалить зеркальное отображение SQL пула в построителе топологий, сначала следует использовать командлет для удаления зеркала в SQL Server. Затем вы можете использовать построитель топологий, чтобы удалить зеркало из топологии. Чтобы сделать это в SQL Server, запустите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="84ab9-p117">To remove the SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server. You can then use Topology Builder to remove the mirror from the topology. To remove the mirror in SQL Server, use the following cmdlet:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

<span data-ttu-id="84ab9-199">Например, чтобы удалить зеркальное отображение и сбросить базы данных для баз данных User, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="84ab9-199">For example, to remove mirroring and drop the databases for the User databases, type the following:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

<span data-ttu-id="84ab9-200">Этот `-DropExistingDatabasesOnMirror` параметр приводит к удалению затронутых баз данных из зеркала.</span><span class="sxs-lookup"><span data-stu-id="84ab9-200">The `-DropExistingDatabasesOnMirror` option causes the affected databases to be deleted from the mirror.</span></span>

<span data-ttu-id="84ab9-201">Чтобы затем удалить это зеркальное отображение из топологии, выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="84ab9-201">Then, to remove the mirror from the topology, do the following:</span></span>

1.  <span data-ttu-id="84ab9-202">В построителе топологии щелкните пул правой кнопкой мыши и выберите пункт **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="84ab9-202">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="84ab9-203">Снимите флажок **Включить зеркальное отображение хранилища SQL** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="84ab9-203">Uncheck **Enable SQL Store Mirroring** and click **OK**.</span></span>

3.  <span data-ttu-id="84ab9-204">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="84ab9-204">Publish the topology.</span></span>

</div>

<div>

## <a name="removing-a-mirroring-witness"></a><span data-ttu-id="84ab9-205">Удаление следящего сервера зеркального отображения</span><span class="sxs-lookup"><span data-stu-id="84ab9-205">Removing a Mirroring Witness</span></span>

<span data-ttu-id="84ab9-206">Используйте эту процедуру, если вам нужно удалить следящий сервер из конфигурации зеркального отображения на внутреннем сервере.</span><span class="sxs-lookup"><span data-stu-id="84ab9-206">Use this procedure if you need to remove the witness from a Back End Server mirroring configuration.</span></span>

1.  <span data-ttu-id="84ab9-207">В построителе топологии щелкните пул правой кнопкой мыши и выберите пункт **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="84ab9-207">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="84ab9-208">Снимите флажок **Использовать свидетель зеркального отображения SQL Server для автоматической отработки отказа** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="84ab9-208">Uncheck **Use SQL Server mirroring witness to enable automatic failover** and click **OK**.</span></span>

3.  <span data-ttu-id="84ab9-209">Публикация топологии.</span><span class="sxs-lookup"><span data-stu-id="84ab9-209">Publish the topology.</span></span>
    
    <span data-ttu-id="84ab9-210">После публикации топологии в построителе топологии появится сообщение с приведенными ниже инструкциями.</span><span class="sxs-lookup"><span data-stu-id="84ab9-210">After publishing the topology, Topology Builder you will see a message that includes the following</span></span>
    
        Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
    
    <span data-ttu-id="84ab9-211">Тем не менее, не Подпишитесь на этот шаг и `Uninstall-CsMirrorDatabase` не вводите так, как только это приведет к удалению всей конфигурации зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="84ab9-211">However, do not follow that step, and do not type `Uninstall-CsMirrorDatabase` as that would uninstall the entire mirroring configuration.</span></span>

4.  <span data-ttu-id="84ab9-212">Чтобы удалить только следящий сервер из конфигурации SQL Server, следуйте инструкциям в разделе "Удаление следящего сервера из сеанса зеркального отображения базы данных (SQL Server)" [http://go.microsoft.com/fwlink/p/?LinkId=268456](http://go.microsoft.com/fwlink/p/?linkid=268456)на.</span><span class="sxs-lookup"><span data-stu-id="84ab9-212">To remove just the witness from the SQL Server configuration, follow the instructions in "Remove the Witness from a Database Mirroring Session (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268456](http://go.microsoft.com/fwlink/p/?linkid=268456).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

