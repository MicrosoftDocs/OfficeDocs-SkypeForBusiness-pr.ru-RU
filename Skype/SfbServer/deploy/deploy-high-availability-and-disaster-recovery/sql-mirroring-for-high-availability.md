---
title: Развертывание зеркального отображения SQL Server для обеспечения высокой доступности внутреннего сервера в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
description: 'Чтобы обеспечить возможность развертывания зеркального отображения SQL, серверы должны работать под управлением, как минимум, версии SQL Server 2008 R2. Эта версия должна выполнятся на всех серверах-участниках: на сервере-источнике, зеркальном сервере и следящем сервере. Подробности можно найти в разделе накопительный пакет обновления 9 для SQL Server 2008 с пакетом обновления 1.'
ms.openlocfilehash: 19f315d643ea5b9379445bf7571e49e7d658f5ab
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003589"
---
# <a name="deploy-sql-mirroring-for-back-end-server-high-availability-in-skype-for-business-server-2015"></a><span data-ttu-id="fe901-105">Развертывание зеркального отображения SQL для серверного сервера высокой доступности в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="fe901-105">Deploy SQL mirroring for Back End Server high availability in Skype for Business server 2015</span></span>


<span data-ttu-id="fe901-106">Чтобы обеспечить возможность развертывания зеркального отображения SQL, серверы должны работать под управлением, как минимум, версии SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="fe901-106">To be able to deploy SQL mirroring, your servers must run a minimum of SQL Server 2008 R2.</span></span> <span data-ttu-id="fe901-107">Эта версия должна выполнятся на всех серверах-участниках: на сервере-источнике, зеркальном сервере и следящем сервере.</span><span class="sxs-lookup"><span data-stu-id="fe901-107">This version must run on all the involved servers: the primary, mirror, and the witness.</span></span> <span data-ttu-id="fe901-108">Подробности можно найти в разделе [накопительный пакет обновления 9 для SQL server 2008 с пакетом обновления 1](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921).</span><span class="sxs-lookup"><span data-stu-id="fe901-108">For details, see [Cumulative update package 9 for SQL Server 2008 Service Pack 1](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921).</span></span>

<span data-ttu-id="fe901-109">В целом, для настройки зеркального отображения SQL между двумя внутренними серверами с ресурсом-свидетелем требуется следующее:</span><span class="sxs-lookup"><span data-stu-id="fe901-109">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>

- <span data-ttu-id="fe901-110">Версия SQL Server основного сервера должна поддерживать зеркальное отображение SQL.</span><span class="sxs-lookup"><span data-stu-id="fe901-110">The primary server's version of SQL Server must support SQL mirroring.</span></span>

- <span data-ttu-id="fe901-111">На основном ресурсе, зеркальном ресурсе и ресурсе-свидетеле (если развертывается) должна быть установлена одна и та же версия SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fe901-111">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span>

- <span data-ttu-id="fe901-p103">На основном и зеркальном ресурсах должен быть установлен один и тот же выпуск SQL Server. На ресурсе-свидетеле может быть установлен другой выпуск.</span><span class="sxs-lookup"><span data-stu-id="fe901-p103">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>

<span data-ttu-id="fe901-114">Рекомендации по SQL в отношении того, какие версии SQL поддерживаются для роли следящего сервера, описаны в разделе [следящий сервер зеркального отображения базы данных](https://go.microsoft.com/fwlink/p/?LinkId=247345).</span><span class="sxs-lookup"><span data-stu-id="fe901-114">For SQL best practices in terms of what SQL versions are supported for a Witness role, see [Database Mirroring Witness](https://go.microsoft.com/fwlink/p/?LinkId=247345).</span></span>

<span data-ttu-id="fe901-115">Для развертывания SQL Mirror используется Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="fe901-115">You use Topology Builder to deploy SQL mirroring.</span></span> <span data-ttu-id="fe901-116">Вы выбираете параметр в построителе топологии для отражения баз данных, а построитель топологии задает зеркальное отображение (в том числе настройку следящего сервера при необходимости) при публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="fe901-116">You select an option in Topology Builder to mirror the databases, and Topology Builder sets up the mirroring (including setting up a witness, if you want) when you publish the topology.</span></span> <span data-ttu-id="fe901-117">Обратите внимание, что настройка или удаление свидетеля выполняется одновременно с настройкой или удалением зеркала.</span><span class="sxs-lookup"><span data-stu-id="fe901-117">Note that you set up or remove the witness at the same time you set up or remove the mirror.</span></span> <span data-ttu-id="fe901-118">Отдельной команды для развертывания или удаления только свидетеля не существует.</span><span class="sxs-lookup"><span data-stu-id="fe901-118">There is no separate command to deploy or remove only a witness.</span></span>

<span data-ttu-id="fe901-119">Для настройки зеркального отображения серверов сначала нужно правильно настроить разрешения базы данных SQL.</span><span class="sxs-lookup"><span data-stu-id="fe901-119">To configure server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="fe901-120">Подробности можно найти в разделе [Настройка учетных записей входа для зеркального отображения базы данных или групп доступности AlwaysOn (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268454).</span><span class="sxs-lookup"><span data-stu-id="fe901-120">For details, see [Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268454).</span></span>

<span data-ttu-id="fe901-p106">При использовании зеркального отображения SQL режим восстановления базы данных всегда задан как **Полный**, т. е. вы должны регулярно отслеживать размер журнала транзакций и журналов транзакций резервного копирования, чтобы предотвратить нехватку места на диске на внутренних серверах. Частота резервного копирования журналов транзакций зависит от скорости роста журналов, которая в свою очередь зависит от транзакций баз данных в результате действий пользователей в интерфейсном пуле. Рекомендуется определить ожидаемую скорость роста журналов для полезной нагрузки развертывания, чтобы вы могли правильно провести планирование. В следующих статьях представлены дополнительные сведения об управлении резервным копированием и журналами SQL:</span><span class="sxs-lookup"><span data-stu-id="fe901-p106">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers. The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool. We recommend that you determine how much transaction log growth is expected for your deployment workload so that you can do the planning accordingly. The following articles provide additional information on SQL backup and log management:</span></span>

- [<span data-ttu-id="fe901-125">Модели восстановления базы данных</span><span class="sxs-lookup"><span data-stu-id="fe901-125">Database recovery models</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=268446)

- [<span data-ttu-id="fe901-126">Общие сведения о резервном копировании</span><span class="sxs-lookup"><span data-stu-id="fe901-126">Backup overview</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=268449)

- [<span data-ttu-id="fe901-127">Резервное копирование журнала транзакций</span><span class="sxs-lookup"><span data-stu-id="fe901-127">Backup transaction log</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=268452)

<span data-ttu-id="fe901-128">При использовании зеркального отображения SQL топологию можно настроить при создании пулов или после их создания.</span><span class="sxs-lookup"><span data-stu-id="fe901-128">With SQL mirroring, you can either configure the topology for mirroring when you create the pools, or after the pools are already created.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fe901-129">Использование построителя топологии или командлетов для настройки и удаления зеркального отображения SQL поддерживается только в том случае, если все серверы, которые являются основными, зеркальными и следящими (при необходимости), принадлежат одному домену.</span><span class="sxs-lookup"><span data-stu-id="fe901-129">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="fe901-130">Если необходимо настроить зеркальное отображение SQL для серверов в других доменах, см. документацию по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fe901-130">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fe901-131">При внесении изменений в отношения зеркального отображения внутренних баз данных необходимо перезагрузить все серверы переднего плана в пуле. </span><span class="sxs-lookup"><span data-stu-id="fe901-131">Whenever you make a change to a Back End Database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span> <span data-ttu-id="fe901-132">> изменения в зеркальном отображении (например, изменение расположения зеркала) для выполнения этих трех действий необходимо использовать Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="fe901-132">> For a change in mirroring, (such as changing the location of a mirror), you must use Topology Builder to perform these three steps:</span></span>

1. <span data-ttu-id="fe901-133">Удаление зеркального отображения со старого сервера-зеркала.</span><span class="sxs-lookup"><span data-stu-id="fe901-133">Remove mirroring from the old mirror server.</span></span>

2. <span data-ttu-id="fe901-134">Добавление зеркального отображения на новый сервер-зеркало.</span><span class="sxs-lookup"><span data-stu-id="fe901-134">Add mirroring to the new mirror server.</span></span>

3. <span data-ttu-id="fe901-135">Публикация топологии.</span><span class="sxs-lookup"><span data-stu-id="fe901-135">Publish the topology.</span></span>

> [!NOTE]
> <span data-ttu-id="fe901-136">Вам потребуется создать общую папку для записи в нее зеркальных файлов, кроме того, службе, от имени которой выполняются SQL Server и агент SQL, необходим доступ для записи и чтения.</span><span class="sxs-lookup"><span data-stu-id="fe901-136">A file share has to be created for the mirror files to be written to, and the service that SQL Server and SQL Agent are running under needs read/write access.</span></span> <span data-ttu-id="fe901-137">Если служба SQL Server выполняется в контексте сетевой службы, вы можете \<добавить Domain\> \\<склсервернаме\>$ для основного и зеркального серверов SQL в разрешения общего доступа.</span><span class="sxs-lookup"><span data-stu-id="fe901-137">If the SQL Server service is running under the context of Network Service, you can add \<Domain\>\\<SQLSERVERNAME\>$ of both the Principal and Mirror SQL Servers to the share permissions.</span></span> <span data-ttu-id="fe901-138">Использование символа $ важно для определения того, что это значение является учетной записью компьютера.</span><span class="sxs-lookup"><span data-stu-id="fe901-138">The $ is important to identify that this is a computer account.</span></span>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a><span data-ttu-id="fe901-139">Настройка зеркального отображения SQL при создании пула в построителе топологии</span><span class="sxs-lookup"><span data-stu-id="fe901-139">To configure SQL mirroring while creating a pool in Topology Builder</span></span>

1. <span data-ttu-id="fe901-140">На странице **Определение хранилища SQL** щелкните **Создать** рядом с полем **Хранилище SQL**. </span><span class="sxs-lookup"><span data-stu-id="fe901-140">On the **Define the SQL Store** page, click **New** next to the **SQL store** box.</span></span>

2. <span data-ttu-id="fe901-141">На странице **Определение нового хранилища SQL** укажите основное хранилище, выберите **Этот экземпляр SQL находится в отношении зеркального отображения**, укажите номер порта для зеркального отображения SQL (по умолчанию — 5022), а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fe901-141">On the **Define new SQL Store** page, specify the primary store, select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default is 5022), and then click **OK**.</span></span>

3. <span data-ttu-id="fe901-142">Вернитесь на страницу **Определение хранилища SQL** и выберите **Включить зеркальное отображение хранилища SQL**. </span><span class="sxs-lookup"><span data-stu-id="fe901-142">Back on the **Define the SQL store** page, select **Enable SQL Store mirroring**.</span></span>

4. <span data-ttu-id="fe901-p110">На странице **Определение нового хранилища SQL** укажите хранилище SQL, которое будет использоваться в качестве зеркала. Выберите **Этот экземпляр SQL находится в отношении зеркального отображения**, укажите номер порта (по умолчанию — 5022), а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fe901-p110">In the **Define new SQL Store** page, specify the SQL store to be used as the mirror. Select **This SQL instance is in mirroring relation**, specify the port number (the default is 5022), and then click **OK**.</span></span>

5. <span data-ttu-id="fe901-145">Если необходимо использовать ресурс-свидетель для этого зеркала, выполните следующие действия. </span><span class="sxs-lookup"><span data-stu-id="fe901-145">If you want a witness for this mirror, do the following:</span></span>

    <span data-ttu-id="fe901-146">a)</span><span class="sxs-lookup"><span data-stu-id="fe901-146">a.</span></span> <span data-ttu-id="fe901-147">Выберите **Использовать ресурс-свидетель зеркального отображения SQL для включения автоматического переключения**. </span><span class="sxs-lookup"><span data-stu-id="fe901-147">Select **Use SQL mirroring witness to enable automatic failover**.</span></span>

    <span data-ttu-id="fe901-148">б)</span><span class="sxs-lookup"><span data-stu-id="fe901-148">b.</span></span> <span data-ttu-id="fe901-149">На странице **Определение хранилища SQL** выберите **Использовать ресурс-свидетель зеркального отображения SQL для включения автоматического переключения** и укажите хранилище SQL для использования в качестве ресурса-свидетеля. </span><span class="sxs-lookup"><span data-stu-id="fe901-149">In the **Define the SQL Store** page, select **Use SQL mirroring witness to enable automatic failover**, and specify the SQL store to be used as the witness.</span></span>

    <span data-ttu-id="fe901-150">в.</span><span class="sxs-lookup"><span data-stu-id="fe901-150">c.</span></span> <span data-ttu-id="fe901-151">Укажите номер порта (по умолчанию — 7022) и щелкните **ОК**. </span><span class="sxs-lookup"><span data-stu-id="fe901-151">Specify the port number (the default is 7022) and click **OK**.</span></span>

6. <span data-ttu-id="fe901-152">После того как вы закончите определение пула переднего плана и всех других ролей в топологии, используйте построитель топологии для публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="fe901-152">After you are done defining your Front End pool and all other roles in your topology, use Topology Builder to publish the topology.</span></span> <span data-ttu-id="fe901-153">Если топология опубликована, то если в пуле переднего плана, на котором размещается хранилище Центрального управления, включено зеркальное отображение SQL, вы увидите параметр для создания баз данных основного и зеркального хранилища SQL.</span><span class="sxs-lookup"><span data-stu-id="fe901-153">When the topology is published, if the Front End pool that hosts Central Management store has SQL mirroring enabled, you will see an option to create both primary and mirror SQL store databases.</span></span>

    <span data-ttu-id="fe901-154">Щелкните **Параметры** и введите путь, который необходимо использовать в качестве пути к общей папке для резервной копии зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="fe901-154">Click **Settings**, and type the path to use as the file share for the mirroring backup.</span></span>

    <span data-ttu-id="fe901-p115">Нажмите кнопку **ОК**, а затем кнопку **Далее** для создания баз данных и публикации топологии. Будут развернуты ресурс-зеркало и ресурс-свидетель (если указан).</span><span class="sxs-lookup"><span data-stu-id="fe901-p115">Click **OK** and then **Next** to create the databases and publish the topology. The mirroring and the witness (if specified) will be deployed.</span></span>

<span data-ttu-id="fe901-157">Вы можете использовать Topology Builder, чтобы изменить свойства уже существующего пула, чтобы включить зеркальное отображение SQL.</span><span class="sxs-lookup"><span data-stu-id="fe901-157">You can use Topology Builder to edit the properties of an already existing pool to enable SQL mirroring.</span></span>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a><span data-ttu-id="fe901-158">Добавление зеркального отображения SQL к существующему пулу переднего плана в построителе топологии</span><span class="sxs-lookup"><span data-stu-id="fe901-158">To add SQL mirroring to an existing Front End pool in Topology Builder</span></span>

1. <span data-ttu-id="fe901-159">В построителе топологии щелкните пул правой кнопкой мыши и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="fe901-159">In Topology Builder, right-click the pool and then click **Edit Properties**.</span></span>

2. <span data-ttu-id="fe901-160">Выберите **Включить зеркальное отображение хранилища SQL**, а затем щелкните **Создать** рядом с элементом **Зеркальное отображение хранилища SQL**. </span><span class="sxs-lookup"><span data-stu-id="fe901-160">Select **Enable SQL Store Mirroring**, and then click **New** next to **Mirroring SQL Store**.</span></span>

3. <span data-ttu-id="fe901-161">Укажите хранилище SQL, которое необходимо использовать в качестве зеркала. </span><span class="sxs-lookup"><span data-stu-id="fe901-161">Specify the SQL store that you want to use as the mirror.</span></span>

4. <span data-ttu-id="fe901-162">Выберите **Этот экземпляр SQL находится в отношении зеркального отображения**, укажите номер порта зеркального отображения SQL (порт по умолчанию — 5022), а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fe901-162">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number the default port is 5022), and then click **OK**.</span></span>

5. <span data-ttu-id="fe901-163">Если необходимо настроить ресурс-свидетель, выберите **Использовать свидетель зеркального отображения SQL для включения автоматической отработки отказа** и щелкните **Создать**. </span><span class="sxs-lookup"><span data-stu-id="fe901-163">If you want to configure a witness, select **Use SQL mirroring witness to enable automatic failover**, and click **New**.</span></span>

6. <span data-ttu-id="fe901-164">Укажите хранилище SQL, которое необходимо использовать в качестве свидетеля. </span><span class="sxs-lookup"><span data-stu-id="fe901-164">Specify the SQL store that you want to use as the witness.</span></span>

7. <span data-ttu-id="fe901-165">Выберите **Этот экземпляр SQL находится в отношении зеркального отображения**, укажите номер порта зеркального отображения SQL (порт по умолчанию — 7022), а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fe901-165">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default port is 7022), and then click **OK**.</span></span>

8. <span data-ttu-id="fe901-166">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fe901-166">Click **OK**.</span></span>

9. <span data-ttu-id="fe901-p116">Опубликуйте топологию. После этого появится запрос на установку базы данных. </span><span class="sxs-lookup"><span data-stu-id="fe901-p116">Publish the topology. When you do so, you will be prompted to install the database.</span></span>

    <span data-ttu-id="fe901-p117">В процессе публикации топологии отобразится запрос на определение пути к общей папке. Серверы SQL Server, которые участвуют в зеркалировании, должны иметь доступ на чтение и запись для этой общей папки для выполнения зеркалирования.</span><span class="sxs-lookup"><span data-stu-id="fe901-p117">During the topology publishing process, you will be asked to define a file share path. The SQL Servers that participate in the mirroring must have read/write access to this file share for the mirror to be established.</span></span>

<span data-ttu-id="fe901-171">Перед переходом к следующей процедуре необходимо установить базу данных.</span><span class="sxs-lookup"><span data-stu-id="fe901-171">You must then install the database before going on to the next procedure.</span></span>

<span data-ttu-id="fe901-172">При настройке зеркального отображения сервера SQL Server следует иметь в виду следующее.</span><span class="sxs-lookup"><span data-stu-id="fe901-172">You should keep the following in mind when setting up SQL mirroring:</span></span>

- <span data-ttu-id="fe901-173">Если конечная точка зеркального отображения уже существует, она будет повторно использоваться с подключением по указанным портам, а порты, определенные в топологии, будут игнорироваться.</span><span class="sxs-lookup"><span data-stu-id="fe901-173">If a mirroring endpoint already exists, it will be reused using the ports defined there, and will ignore the ones you specify in the topology.</span></span>

- <span data-ttu-id="fe901-p118">Любой порт, уже выделенный для других приложений на том же сервере, включая порты для других экземпляров SQL, не должен использоваться для доступных установленных экземпляров SQL. Это означает, что при наличии нескольких экземпляров SQL Server, установленных на одном и том же сервере, они не должны использовать один и тот же порт для зеркального отображения. Для получения подробной информации см. следующие статьи:</span><span class="sxs-lookup"><span data-stu-id="fe901-p118">Any port already allocated for other applications on the same server, including those for other SQL instances, should not be used for the installed SQL instances at hand. This implies that if you have more than one SQL instance installed on the same server, they must not use the same port for mirroring. For details, see the following articles:</span></span>

  - [<span data-ttu-id="fe901-177">Указание сетевого адреса сервера (зеркальное отображение базы данных)</span><span class="sxs-lookup"><span data-stu-id="fe901-177">Specify a Server Network Address (Database Mirroring)</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=247346)

  - [<span data-ttu-id="fe901-178">Конечная точка зеркального отображения базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fe901-178">The Database Mirroring Endpoint (SQL Server)</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=247347)

## <a name="using-skype-for-business-server-2015-management-shell-cmdlets-to-set-up-sql-mirroring"></a><span data-ttu-id="fe901-179">Использование командлетов командной консоли Skype для бизнеса Server 2015 для настройки зеркального отображения SQL</span><span class="sxs-lookup"><span data-stu-id="fe901-179">Using Skype for Business Server 2015 Management Shell Cmdlets to Set Up SQL Mirroring</span></span>

<span data-ttu-id="fe901-180">Проще всего настроить зеркальное отображение с помощью построителя топологии, но вы также можете использовать командлеты.</span><span class="sxs-lookup"><span data-stu-id="fe901-180">The easiest way to set up mirroring is by using Topology Builder, but you can also do so using cmdlets.</span></span>

1. <span data-ttu-id="fe901-181">Откройте окно командной консоли Skype для бизнеса Server 2015 и запустите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="fe901-181">Open a Skype for Business Server 2015 Management Shell window and run the following cmdlet:</span></span>

   ```powershell
   Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose
   ```

    <span data-ttu-id="fe901-182">Например:</span><span class="sxs-lookup"><span data-stu-id="fe901-182">For example:</span></span>

   ```powershell
   Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose
   ```

    <span data-ttu-id="fe901-183">Отобразится следующее:</span><span class="sxs-lookup"><span data-stu-id="fe901-183">You will see the following:</span></span>

   <pre>
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
   </pre>

2. <span data-ttu-id="fe901-184">Проверьте следующее:</span><span class="sxs-lookup"><span data-stu-id="fe901-184">Verify the following:</span></span>

    - <span data-ttu-id="fe901-185">Порт 5022 доступен через брандмауэр, если брандмауэр Windows включен на сервере-источнике SQL Server e04-ocs.los_a.lsipt.local\rtc. </span><span class="sxs-lookup"><span data-stu-id="fe901-185">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the primary SQL Server e04-ocs.los_a.lsipt.local\rtc.</span></span>

    - <span data-ttu-id="fe901-186">Порт 5022 доступен через брандмауэр, если брандмауэр Windows включен на зеркальном ресурсе SQL Server K16-ocs.los_a.lsipt.local\rtc. </span><span class="sxs-lookup"><span data-stu-id="fe901-186">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the mirror SQL Server K16-ocs.los_a.lsipt.local\rtc.</span></span>

    - <span data-ttu-id="fe901-187">Порт 7022 доступен через брандмауэр, если брандмауэр Windows включен на следящем сервере SQL Server AB14-lct.los_a.lsipt.local\rtc. </span><span class="sxs-lookup"><span data-stu-id="fe901-187">Port 7022 is accessible through the firewall if Windows Firewall is enabled in the witness SQL Server AB14-lct.los_a.lsipt.local\rtc.</span></span>

   - <span data-ttu-id="fe901-188">Учетные записи, на которых запущены серверы SQL Server на всех основных и зеркальных серверах SQL, имеют \\разрешение на чтение и запись для E04-OCS\csdatabackup общего доступа к файлам.</span><span class="sxs-lookup"><span data-stu-id="fe901-188">Accounts running the SQL Servers on all primary and mirror SQL servers have read/write permission to the file share \\E04-OCS\csdatabackup</span></span>

   - <span data-ttu-id="fe901-p119">Убедитесь, что поставщик инструментария управления Windows (WMI) работает на всех этих серверах. Командлет использует этот поставщик для поиска информации об учетных записях для служб SQL Server, которые выполняются на всех серверах-источниках, зеркальных серверах и следящих серверах. </span><span class="sxs-lookup"><span data-stu-id="fe901-p119">Verify that the Windows Management Instrumentation (WMI) provider is running on all these servers. The cmdlet uses this provider to find the account information for SQL Server services running on all primary, mirror and witness servers.</span></span>

   - <span data-ttu-id="fe901-191">Убедитесь, что учетная запись, выполняющая этот командлет, имеет разрешение на создание папок для данных и файлов журналов для всех зеркальных серверов. </span><span class="sxs-lookup"><span data-stu-id="fe901-191">Verify that the account running this cmdlet has permission to create the folders for the data and log files for all the mirror servers.</span></span>

   - <span data-ttu-id="fe901-p120">Обратите внимание, что учетная запись пользователя, используемая экземпляром SQL для запуска, должна обладать разрешениями на чтение и запись для общей папки. Если общая папка размещена на другом сервере, и экземпляр SQL использует локальную системную учетную запись, вы должны предоставить разрешения для общей папки серверу, на котором размещен экземпляр SQL.</span><span class="sxs-lookup"><span data-stu-id="fe901-p120">Note that the user account that the SQL instance uses to run must have read/write permission to the file share. If the file share is on a different server, and the SQL instance runs a local system account, you must grant file share permissions to the server that hosts the SQL instance.</span></span>

3. <span data-ttu-id="fe901-194">Введите A и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="fe901-194">Type A and press ENTER.</span></span>

    <span data-ttu-id="fe901-195">Зеркальное отображение будет настроено.</span><span class="sxs-lookup"><span data-stu-id="fe901-195">The mirroring will be configured.</span></span>

    <span data-ttu-id="fe901-196">**Install-ксмиррордатабасе** устанавливает зеркало и настраивает зеркальное отображение для всех баз данных, которые находятся в основном хранилище SQL.</span><span class="sxs-lookup"><span data-stu-id="fe901-196">**Install-CsMirrorDatabase** installs the mirror and configures mirroring for all the databases that are present on the primary SQL store.</span></span> <span data-ttu-id="fe901-197">Если вы хотите настроить зеркальное отображение только для определенных баз данных, можно использовать параметр-Датабасетипе или, если вы хотите настроить зеркальное отображение для всех баз данных, кроме нескольких, можно использовать параметр-Ексклудедатабаселист вместе с списком баз данных, разделенных запятыми. имена, которые нужно исключить.</span><span class="sxs-lookup"><span data-stu-id="fe901-197">If you want to configure mirroring for only specific databases, you can use the -DatabaseType option, or if you want to configure mirroring for all databases except for a few, you can use the -ExcludeDatabaseList option, along with a comma-separated list of database names to exclude.</span></span>

    <span data-ttu-id="fe901-198">Например, если вы добавите в **Install-CsMirrorDatabase** следующий параметр, будет выполнено зеркальное отображение всех баз данных, кроме rtcxds.</span><span class="sxs-lookup"><span data-stu-id="fe901-198">For example, if you add the following option to **Install-CsMirrorDatabase**, all databases except rtcab and rtcxds will be mirrored.</span></span>

    `-ExcludeDatabaseList rtcab,rtcxds`

   <span data-ttu-id="fe901-199">Например, если вы добавите в **Install-CsMirrorDatabase**, следующий параметр, будет выполнено зеркальное отображение баз данных rtcab, rtcshared и rtcxds.</span><span class="sxs-lookup"><span data-stu-id="fe901-199">For example, if you add the following option to **Install-CsMirrorDatabase**, only the rtcab, rtcshared, and rtcxds databases will be mirrored.</span></span>

    `-DatabaseType User`

## <a name="removing-or-changing-sql-mirroring"></a><span data-ttu-id="fe901-200">Удаление и изменение зеркального отображения SQL</span><span class="sxs-lookup"><span data-stu-id="fe901-200">Removing or Changing SQL Mirroring</span></span>

<span data-ttu-id="fe901-p122">Чтобы удалить зеркальное отображение SQL пула в построителе топологий, сначала следует использовать командлет для удаления зеркала в SQL Server. Затем вы можете использовать построитель топологий, чтобы удалить зеркало из топологии. Чтобы сделать это в SQL Server, запустите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="fe901-p122">To remove the SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server. You can then use Topology Builder to remove the mirror from the topology. To remove the mirror in SQL Server, use the following cmdlet:</span></span>

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]
```

<span data-ttu-id="fe901-204">Например, чтобы удалить зеркальное отображение и сбросить базы данных для баз данных User, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fe901-204">For example, to remove mirroring and drop the databases for the User databases, type the following:</span></span>

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror
```

<span data-ttu-id="fe901-205">Этот `-DropExistingDatabasesOnMirror` параметр приводит к удалению затронутых баз данных из зеркала.</span><span class="sxs-lookup"><span data-stu-id="fe901-205">The  `-DropExistingDatabasesOnMirror` option causes the affected databases to be deleted from the mirror.</span></span>

<span data-ttu-id="fe901-206">Чтобы затем удалить это зеркальное отображение из топологии, выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="fe901-206">Then, to remove the mirror from the topology, do the following:</span></span>

1. <span data-ttu-id="fe901-207">В построителе топологии щелкните пул правой кнопкой мыши и выберите пункт **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="fe901-207">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2. <span data-ttu-id="fe901-208">Снимите флажок **Включить зеркальное отображение хранилища SQL** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fe901-208">Uncheck **Enable SQL Store Mirroring** and click **OK**.</span></span>

3. <span data-ttu-id="fe901-209">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="fe901-209">Publish the topology.</span></span>

## <a name="removing-a-mirroring-witness"></a><span data-ttu-id="fe901-210">Удаление следящего сервера зеркального отображения</span><span class="sxs-lookup"><span data-stu-id="fe901-210">Removing a Mirroring Witness</span></span>

<span data-ttu-id="fe901-211">Используйте эту процедуру, если вам нужно удалить следящий сервер из конфигурации зеркального отображения на внутреннем сервере.</span><span class="sxs-lookup"><span data-stu-id="fe901-211">Use this procedure if you need to remove the witness from a Back End Server mirroring configuration.</span></span>

1. <span data-ttu-id="fe901-212">В построителе топологии щелкните пул правой кнопкой мыши и выберите пункт **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="fe901-212">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2. <span data-ttu-id="fe901-213">Снимите флажок **Использовать свидетель зеркального отображения SQL Server для автоматической отработки отказа** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fe901-213">Uncheck **Use SQL Server mirroring witness to enable automatic failover** and click **OK**.</span></span>

3. <span data-ttu-id="fe901-214">Публикация топологии.</span><span class="sxs-lookup"><span data-stu-id="fe901-214">Publish the topology.</span></span>

    <span data-ttu-id="fe901-215">После публикации топологии в построителе топологии появится сообщение с приведенными ниже инструкциями.</span><span class="sxs-lookup"><span data-stu-id="fe901-215">After publishing the topology, Topology Builder you will see a message that includes the following</span></span>

   ```console
   Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
   ```

    <span data-ttu-id="fe901-216">Тем не менее, не Подпишитесь на этот шаг и `Uninstall-CsMirrorDatabase` не вводите так, как только это приведет к удалению всей конфигурации зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="fe901-216">However, do not follow that step, and do not type  `Uninstall-CsMirrorDatabase` as that would uninstall the entire mirroring configuration.</span></span>

4. <span data-ttu-id="fe901-217">Чтобы удалить только следящий сервер из конфигурации SQL Server, следуйте инструкциям, приведенным в разделе [Удаление следящего сервера в сеансе зеркального отображения базы данных (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268456).</span><span class="sxs-lookup"><span data-stu-id="fe901-217">To remove just the witness from the SQL Server configuration, follow the instructions in [Remove the Witness from a Database Mirroring Session (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268456).</span></span>


