---
title: Управление высокой доступностью и аварийным восстановлением для сервера сохраняемого чата в Skype для бизнеса Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: 'Сводка: Узнайте, как управлять сервера сохраняемого чата высокой доступности и аварийного восстановления в Скайп для Business Server 2015.'
ms.openlocfilehash: 8bc80ff6a38238b81b658a7f4d9620dc3a56b9be
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="69418-103">Управление высокой доступностью и аварийным восстановлением для сервера сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="69418-103">Manage high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="69418-104">**Сводка:** Сведения об управлении сервера сохраняемого чата высокой доступности и аварийного восстановления в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="69418-104">**Summary:** Learn how to manage Persistent Chat Server high availability and disaster recovery in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="69418-105">В этом разделе описывается, как выполнить отработку отказа и восстановления размещения обратно Persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="69418-105">This topic describes how to fail over and fail back Persistent Chat Server.</span></span> <span data-ttu-id="69418-106">Перед прочтением данного раздела, обязательно прочитайте [Планирование высокой доступности и аварийного восстановления для сервера сохраняемого чата в Скайп для Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) и [Настройка высокой доступности и аварийного восстановления для сервера сохраняемого чата в Скайп для Бизнес-2015 сервера](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="69418-106">Before reading this topic, be sure to read [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) and [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>
  
## <a name="fail-over-persistent-chat-server"></a><span data-ttu-id="69418-107">Переключения сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="69418-107">Fail over Persistent Chat Server</span></span>

<span data-ttu-id="69418-108">Отработка отказа для сервера сохраняемого чата разрабатывалась ориентирована на ручное выполнение.</span><span class="sxs-lookup"><span data-stu-id="69418-108">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>
  
<span data-ttu-id="69418-109">Процедура отработки отказа на основе предполагается, что центр дополнительных данных — это копирование и работает, но службы сервера сохраняемого чата, где расположена Persistent Chat базы данных-источника, полностью недоступен, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="69418-109">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>
  
- <span data-ttu-id="69418-110">Persistent Chat Server основной базы данных и сервера сохраняемого чата зеркальная база данных не работают.</span><span class="sxs-lookup"><span data-stu-id="69418-110">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>
    
- <span data-ttu-id="69418-111">Скайп для сервера переднего плана Business Server не работает.</span><span class="sxs-lookup"><span data-stu-id="69418-111">Skype for Business Server Front End Server is down.</span></span>
    
<span data-ttu-id="69418-112">Вся процедура состоит из двух основных этапов:</span><span class="sxs-lookup"><span data-stu-id="69418-112">The procedure is based on two basic steps:</span></span>
  
- <span data-ttu-id="69418-113">Восстановление Persistent Chat базы данных-источника (mgc).</span><span class="sxs-lookup"><span data-stu-id="69418-113">Recover the primary Persistent Chat database (mgc).</span></span>
    
- <span data-ttu-id="69418-114">Реализация зеркального отображения для новой базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="69418-114">Establish mirroring for the new primary database.</span></span>
    
<span data-ttu-id="69418-115">Сохраняемый чат база данных соответствия (mgccomp) не отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="69418-115">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="69418-116">Содержимое этой базы данных является временным и очищается по мере обработки данных адаптером соответствия.</span><span class="sxs-lookup"><span data-stu-id="69418-116">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="69418-117">Отвечает, администратор сохраняемого чата правильно управлять вывода адаптера, чтобы избежать потери данных.</span><span class="sxs-lookup"><span data-stu-id="69418-117">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>
  
<span data-ttu-id="69418-118">Порядок отработки отказа сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="69418-118">To fail over Persistent Chat Server:</span></span>
  
1. <span data-ttu-id="69418-119">Удалите доставку журналов из Persistent Chat Server резервного копирования базы данных доставки журналов.</span><span class="sxs-lookup"><span data-stu-id="69418-119">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
  - <span data-ttu-id="69418-120">С помощью SQL Server Management Studio, подключитесь к экземпляру базы данных, где расположена база данных mgc резервного копирования сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="69418-120">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
  - <span data-ttu-id="69418-121">Откройте окно отправки запроса в базу данных master.</span><span class="sxs-lookup"><span data-stu-id="69418-121">Open a query window to the master database.</span></span>
    
  - <span data-ttu-id="69418-122">Используйте следующую команду для сброса доставки журналов:</span><span class="sxs-lookup"><span data-stu-id="69418-122">Use the following command to drop log shipping:</span></span>
    
  ```
  exec sp_delete_log_shipping_secondary_database mgc
  ```

2. <span data-ttu-id="69418-123">Скопируйте все нескопированные файлы резервных копий из общей папки резервных копий в конечную папку копирования на резервном сервере.</span><span class="sxs-lookup"><span data-stu-id="69418-123">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>
    
3. <span data-ttu-id="69418-124">По порядку примените все непримененные резервные копии журналов транзакций к базе данных-получателю.</span><span class="sxs-lookup"><span data-stu-id="69418-124">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="69418-125">Дополнительные сведения см [как: применение резервной копии журнала транзакций (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).</span><span class="sxs-lookup"><span data-stu-id="69418-125">For details, see [How to: Apply a Transaction Log Backup (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).</span></span>
    
4. <span data-ttu-id="69418-p104">Подключите резервную базу данных mgc к сети. В окне запроса, которое было открыто в действии 1b, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="69418-p104">Bring the backup mgc database online. Using the query window that opens in step 1b, do the following:</span></span>
    
  - <span data-ttu-id="69418-128">Завершите все подключения к базе данных mgc при их наличии:</span><span class="sxs-lookup"><span data-stu-id="69418-128">End all connections to the mgc database, if there are any:</span></span>
    
  - <span data-ttu-id="69418-129">Выполните команду **exec sp_who2**, чтобы определить подключения к базе данных mgc.</span><span class="sxs-lookup"><span data-stu-id="69418-129">**exec sp_who2** to identify connections to the mgc database.</span></span>
    
  - <span data-ttu-id="69418-130">**kill \<spid\> ** для завершения этих подключений.</span><span class="sxs-lookup"><span data-stu-id="69418-130">**kill \<spid\>** to end these connections.</span></span>
    
  - <span data-ttu-id="69418-131">Подключите базу данных к сети:</span><span class="sxs-lookup"><span data-stu-id="69418-131">Bring the database online:</span></span>
    
  - <span data-ttu-id="69418-132">**restore database mgc with recovery**.</span><span class="sxs-lookup"><span data-stu-id="69418-132">**restore database mgc with recovery**.</span></span>
    
5. <span data-ttu-id="69418-133">В Скайп консоли Business Server, используйте команду **Set-CsPersistentChatState-Identity «служба: atl-cs-001.litwareinc.com» - PoolState FailedOver** отработки отказа для резервного копирования базы данных mgc.</span><span class="sxs-lookup"><span data-stu-id="69418-133">In Skype for Business Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" -PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="69418-134">Обязательно замените полное доменное имя в пуле Persistent Chat для узла atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="69418-134">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="69418-135">Резервная база данных mgc теперь выступает в качестве базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="69418-135">The mgc backup database now serves as the primary database.</span></span>
    
6. <span data-ttu-id="69418-136">В Скайп для консоли Business Server используйте командлет **Install-CsMirrorDatabase** зеркального высокой доступности для резервного копирования базы данных, теперь выступает в качестве базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="69418-136">In Skype for Business Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="69418-137">Используйте экземпляр резервной базы данных в качестве базы данных-источника и экземпляр резервной зеркальной базы данных в качестве экземпляра зеркала.</span><span class="sxs-lookup"><span data-stu-id="69418-137">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="69418-138">Это не то же самое зеркало, которое изначально было настроено для базы данных-источника в процессе установки.</span><span class="sxs-lookup"><span data-stu-id="69418-138">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span>
    
7. <span data-ttu-id="69418-139">Настройка сервера сохраняемого чата активных серверов.</span><span class="sxs-lookup"><span data-stu-id="69418-139">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="69418-140">Скайп для консоли Business Server используя командлет **Set-CsPersistentChatActiveServer** Установка списка активных серверов.</span><span class="sxs-lookup"><span data-stu-id="69418-140">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="69418-141">Все активные серверы должны быть расположены в том же центре обработки данных, что и новая база данных-источник, или подключенном к ней через соединение с низкой задержкой и высокой пропускной способностью.</span><span class="sxs-lookup"><span data-stu-id="69418-141">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
    <span data-ttu-id="69418-142">На этом этапе отработка отказа из базы данных-источника сервера сохраняемого чата для резервного копирования базы данных сервера сохраняемого чата выполняется успешно.</span><span class="sxs-lookup"><span data-stu-id="69418-142">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>
    
## <a name="fail-back-persistent-chat-server"></a><span data-ttu-id="69418-143">Сбой обратно Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="69418-143">Fail back Persistent Chat Server</span></span>

<span data-ttu-id="69418-144">В этом разделе описываются действия, необходимые для восстановления после сбоя сервера сохраняемого чата и возобновления взаимодействия с основным центром обработки данных.</span><span class="sxs-lookup"><span data-stu-id="69418-144">This procedure outlines the steps necessary to recover from a Persistent Chat Server failure, and to reestablish operations from the primary data center.</span></span>
  
<span data-ttu-id="69418-145">Во время сбоя сервера сохраняемого чата основным центром обработки данных приходится сталкиваться полный отказ и основной и зеркальной базы данных становятся недоступными.</span><span class="sxs-lookup"><span data-stu-id="69418-145">During Persistent Chat Server failure, the primary data center suffers complete outage, and the primary and mirror databases become unavailable.</span></span> <span data-ttu-id="69418-146">Основной центр обработки данных переключается на резервный сервер.</span><span class="sxs-lookup"><span data-stu-id="69418-146">The primary data center fails over to the backup server.</span></span>
  
<span data-ttu-id="69418-147">Ниже описывается процедура возобновления нормальной работы после восстановления базы данных-источника и подключения серверов.</span><span class="sxs-lookup"><span data-stu-id="69418-147">The following procedure restores normal operation after the primary data center is back up, and the servers have been rebuilt.</span></span> <span data-ttu-id="69418-148">В процедуре предполагается, что основным центром обработки данных были восстановлены из общий сбой, и, что базу данных mgc и базы данных mgccomp после перестроение и переустановить с помощью построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="69418-148">The procedure assumes that the primary data center has been recovered from total outage, and that the mgc database and the mgccomp database have been rebuilt and reinstalled by using Topology Builder.</span></span>
  
<span data-ttu-id="69418-149">Также предполагается, что в процессе отработки отказа не были развернуты новые зеркальные и резервные серверы и что единственный сервер, который был развернут, — это резервный и соответствующий зеркальный серверы, определенные в разделе "Отработка отказа сервером сохраняемого чата".</span><span class="sxs-lookup"><span data-stu-id="69418-149">The procedure also assumes that no new mirror and backup servers were deployed during the failover period, and that the only server deployed is the backup server and its mirror server, as defined in Fail over Persistent Chat Server previously.</span></span>
  
<span data-ttu-id="69418-150">Данные инструкции служат для восстановления исходной конфигурации, которая существовала до сбоя, приведшего к переключению с основного на резервный сервер.</span><span class="sxs-lookup"><span data-stu-id="69418-150">These steps are designed to recover configuration as it existed prior to the disaster, resulting in failover from the primary server to the backup server.</span></span>
  
1. <span data-ttu-id="69418-151">Снимите все серверы из списка Persistent Chat Server Active Server с помощью командлета **Set-CsPersistentChatActiveServer** из Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="69418-151">Clear all servers from the Persistent Chat Server Active Server list by using the **Set-CsPersistentChatActiveServer** cmdlet from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="69418-152">Это останавливает все Persistent Chat серверы из подключение к базе данных mgc и базы данных mgccomp во время восстановления размещения.</span><span class="sxs-lookup"><span data-stu-id="69418-152">This stops all Persistent Chat Servers from connecting to the mgc database and the mgccomp database during failback.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="69418-153">Агент SQL Server на базу данных-получатель Persistent Chat Server Тыловой сервер должен выполняться под привилегированной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="69418-153">The SQL Server agent on the secondary Persistent Chat Server Back End Server should be running under a privileged account.</span></span> <span data-ttu-id="69418-154">В частности, эта учетная запись должна иметь следующие разрешения:</span><span class="sxs-lookup"><span data-stu-id="69418-154">Specifically, the account must include:</span></span> 
  
   - <span data-ttu-id="69418-155">доступ на чтение к сетевой папке, в которую помещаются резервные копии;</span><span class="sxs-lookup"><span data-stu-id="69418-155">Read access to the network share that backups are being placed in.</span></span>
    
   - <span data-ttu-id="69418-156">доступ на запись к локальному каталогу, в который они копируются.</span><span class="sxs-lookup"><span data-stu-id="69418-156">Write access to the specific local directory that the backups are being copied to.</span></span>
    
2. <span data-ttu-id="69418-157">Отключите зеркальное отображение для резервной базы данных mgc.</span><span class="sxs-lookup"><span data-stu-id="69418-157">Disable mirroring on the backup mgc database:</span></span>
    
   - <span data-ttu-id="69418-158">С помощью SQL Server Management Studio, подключитесь к резервному экземпляру mgc.</span><span class="sxs-lookup"><span data-stu-id="69418-158">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="69418-159">Щелкните правой кнопкой мыши базу данных mgc, наведите указатель на пункт **Задачи** и выберите пункт **Зеркальное отображение**.</span><span class="sxs-lookup"><span data-stu-id="69418-159">Right-click the mgc database, point to **Tasks**, and then click **Mirror**.</span></span>
    
   - <span data-ttu-id="69418-160">Щелкните **Удалить зеркальное отображение**.</span><span class="sxs-lookup"><span data-stu-id="69418-160">Click **Remove Mirroring**.</span></span>
    
   - <span data-ttu-id="69418-161">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="69418-161">Click **OK**.</span></span>
    
   - <span data-ttu-id="69418-162">Выполните те же действия для базы данных mgccomp.</span><span class="sxs-lookup"><span data-stu-id="69418-162">Perform the same steps with the mgccomp database.</span></span>
    
3. <span data-ttu-id="69418-163">Создайте резервную копию базы данных mgc, чтобы ее можно было восстановить в новой основной базе данных.</span><span class="sxs-lookup"><span data-stu-id="69418-163">Back up the mgc database so that it can be restored to the new primary database:</span></span>
    
   - <span data-ttu-id="69418-164">С помощью SQL Server Management Studio, подключитесь к резервному экземпляру mgc.</span><span class="sxs-lookup"><span data-stu-id="69418-164">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="69418-p112">Щелкните правой кнопкой мыши базу данных mgc, наведите указатель на пункт **Задачи** и выберите пункт **Создать резервную копию**. Появится диалоговое окно **Резервное копирование базы данных**.</span><span class="sxs-lookup"><span data-stu-id="69418-p112">Right-click the mgc database, point to **Tasks**, and then click **Back Up**. The **Back Up Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="69418-167">В списке **Тип резервной копии** выберите пункт **Полная**.</span><span class="sxs-lookup"><span data-stu-id="69418-167">In **Backup type**, select **Full**.</span></span>
    
   - <span data-ttu-id="69418-168">В списке **Компонент резервного копирования** выберите пункт **База данных**.</span><span class="sxs-lookup"><span data-stu-id="69418-168">For **Backup component**, click **Database**.</span></span>
    
   - <span data-ttu-id="69418-169">В поле **Имя** оставьте имя резервного набора данных по умолчанию или введите другое имя.</span><span class="sxs-lookup"><span data-stu-id="69418-169">Either accept the default backup set name suggested in **Name**, or enter a different name for the backup set.</span></span>
    
   -  <span data-ttu-id="69418-170">* \<Необязательно\> *  В поле **Описание**введите описание резервного набора данных.</span><span class="sxs-lookup"><span data-stu-id="69418-170">*\<Optional\>*  In **Description**, enter a description of the backup set.</span></span>
    
   - <span data-ttu-id="69418-171">Удалите расположение резервной копии по умолчанию из списка назначений.</span><span class="sxs-lookup"><span data-stu-id="69418-171">Remove the default backup location from the destination list.</span></span>
    
   - <span data-ttu-id="69418-p113">Добавьте в список файл, указав путь к общей папке, которую вы выбрали для доставки журналов. Этот путь доступен как для основной, так и для резервной баз данных.</span><span class="sxs-lookup"><span data-stu-id="69418-p113">Add a file to the list by using the path to the share location that you established for log shipping. This path is available to the primary database and to the backup database.</span></span>
    
   - <span data-ttu-id="69418-174">Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно и начать процесс резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="69418-174">Click **OK** to close the dialog box and begin the backup process.</span></span>
    
4. <span data-ttu-id="69418-175">Восстановите основную базу данных с помощью резервной копии, созданной в предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="69418-175">Restore the primary database by using the backup database created in the previous step.</span></span>
    
   - <span data-ttu-id="69418-176">С помощью SQL Server Management Studio, подключитесь к основному экземпляру mgc.</span><span class="sxs-lookup"><span data-stu-id="69418-176">Using SQL Server Management Studio, connect to the primary mgc instance.</span></span>
    
   - <span data-ttu-id="69418-p114">Щелкните правой кнопкой мыши базу данных mgc, наведите указатель на пункт **Задачи**, выберите пункт **Восстановить**, а затем **База данных**. Появится диалоговое окно **Восстановление базы данных**.</span><span class="sxs-lookup"><span data-stu-id="69418-p114">Right-click the mgc database, point to **Tasks**, point to **Restore**, and then click **Database**. The **Restore Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="69418-179">Выберите пункт **С устройства**.</span><span class="sxs-lookup"><span data-stu-id="69418-179">Select **From Device**.</span></span>
    
   - <span data-ttu-id="69418-p115">Нажмите кнопку "Обзор". Откроется диалоговое окно **Указание резервной копии**. В списке **Резервные носители** выберите пункт **Файл**. Нажмите кнопку **Добавить**, выберите файл резервной копии, созданный в шаге 3, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="69418-p115">Click the browse button, which opens the **Specify Backup** dialog box. In **Backup media**, select **File**. Click **Add**, select the backup file that you created in step 3, and then click **OK**.</span></span>
    
   - <span data-ttu-id="69418-183">В таблице **Выберите резервные наборы данных для восстановления** выберите резервную копию.</span><span class="sxs-lookup"><span data-stu-id="69418-183">In **Select the backup sets to restore**, select the backup.</span></span>
    
   - <span data-ttu-id="69418-184">В области **Выбор страницы** щелкните **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="69418-184">Click **Options** in the **Select a page** pane.</span></span>
    
   - <span data-ttu-id="69418-185">В разделе **Параметры восстановления** выберите пункт **Перезаписать существующую базу данных**.</span><span class="sxs-lookup"><span data-stu-id="69418-185">In **Restore options**, select **Overwrite the existing database**.</span></span>
    
   - <span data-ttu-id="69418-186">На панели **Состояние восстановления** выберите пункт **Оставить базу данных готовой к использованию**.</span><span class="sxs-lookup"><span data-stu-id="69418-186">In **Recovery State**, select **Leave the database ready to use**.</span></span>
    
   - <span data-ttu-id="69418-187">Нажмите кнопку **ОК**, чтобы начать процесс восстановления.</span><span class="sxs-lookup"><span data-stu-id="69418-187">Click **OK** to begin the restoration process.</span></span>
    
5. <span data-ttu-id="69418-188">Настройка доставки журналов SQL Server для базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="69418-188">Configure SQL Server Log Shipping for the primary database.</span></span> <span data-ttu-id="69418-189">Следуйте инструкциям в разделе [Настройка высокой доступности и аварийного восстановления для сервера сохраняемого чата в Скайп для Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) для установления доставки журналов для базы данных основного mgc.</span><span class="sxs-lookup"><span data-stu-id="69418-189">Follow the procedures in [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) to establish log shipping for the primary mgc database.</span></span>
    
6. <span data-ttu-id="69418-190">Настройка сервера сохраняемого чата активных серверов.</span><span class="sxs-lookup"><span data-stu-id="69418-190">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="69418-191">Скайп для консоли Business Server используя командлет **Set-CsPersistentChatActiveServer** Установка списка активных серверов.</span><span class="sxs-lookup"><span data-stu-id="69418-191">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="69418-192">Все активные серверы должны быть расположены в том же центре обработки данных, что и новая база данных-источник, или подключенном к ней через соединение с низкой задержкой и высокой пропускной способностью.</span><span class="sxs-lookup"><span data-stu-id="69418-192">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
<span data-ttu-id="69418-193">Для восстановления в пул в обычном состоянии выполните следующую команду Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="69418-193">To restore the pool to its normal state run the following Windows PowerShell command:</span></span>
  
```
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

<span data-ttu-id="69418-194">Для получения дополнительных сведений см раздел справки для командлета [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="69418-194">For more information, see the help topic for the [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) cmdlet.</span></span>
  

