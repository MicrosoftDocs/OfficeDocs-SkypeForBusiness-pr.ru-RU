---
title: Настройка высокой доступности и аварийного восстановления для сервера сохраняемого чата в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 'Сводка: Сведения в этой статье описывается настройка высокой доступности и аварийного восстановления для сервера сохраняемого чата в Скайп для Business Server 2015.'
ms.openlocfilehash: 5c53652cf5084b5a6c021c38f71f1cccc0322efa
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880485"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="d64cd-103">Настройка высокой доступности и аварийного восстановления для сервера сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="d64cd-103">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d64cd-104">**Сводка:** В данном разделе приведены в этой статье описывается настройка высокой доступности и аварийного восстановления для сервера сохраняемого чата в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d64cd-104">**Summary:** Read this topic to learn how to configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="d64cd-105">Скайп для Business Server поддерживает несколько режимов обеспечения высокой доступности для вашей внутренними серверами, включая зеркальное отображение базы данных.</span><span class="sxs-lookup"><span data-stu-id="d64cd-105">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="d64cd-106">Дополнительные сведения см. в статье [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="d64cd-106">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d64cd-107">Группы обеспечения доступности AlwaysOn с серверов сохраняемого сеанса беседы не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="d64cd-107">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="d64cd-108">Перед настройкой развертывания Persistent Chat для обеспечения высокой доступности и аварийного восстановления, убедитесь, что вы знакомы с понятиями в [Планирование высокой доступности и аварийного восстановления для сервера сохраняемого чата в Скайп для Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="d64cd-108">Before you configure your Persistent Chat deployment for high availability and disaster recovery, be sure you are familiar with the concepts in [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="d64cd-109">Решение аварийного восстановления для сервера сохраняемого чата описаны в следующих разделах построена на вытянутый пул серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="d64cd-109">The disaster recovery solution for Persistent Chat Server described in these topics is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="d64cd-110">Планирования содержимого описание требований к ресурсам и топология растянутый пул, который позволяет высокой доступности и аварийного восстановления для сервера сохраняемого чата, включая использование зеркального отображения SQL Server для обеспечения высокой доступности и доставки журналов SQL Server аварийное восстановление.</span><span class="sxs-lookup"><span data-stu-id="d64cd-110">The planning content describes resource requirements, and the stretched pool topology that enables high availability and disaster recovery for Persistent Chat Server, including using SQL Server mirroring for high availability and SQL Server log shipping for disaster recovery.</span></span>
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a><span data-ttu-id="d64cd-111">Использование построителя топологий для настройки высокой доступности и аварийного восстановления</span><span class="sxs-lookup"><span data-stu-id="d64cd-111">Use Topology Builder to configure high availability and disaster recovery</span></span>

<span data-ttu-id="d64cd-112">В построителе топологий выполните указанные ниже действия, чтобы настроить высокую доступность и аварийное восстановление для сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="d64cd-112">Within Topology Builder, perform the following steps to configure high availability and disaster recovery for Persistent Chat Server.</span></span>
  
1. <span data-ttu-id="d64cd-113">Добавьте зеркальные базы данных и журнала доставки дополнительной базы данных хранилища SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d64cd-113">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>
    
2. <span data-ttu-id="d64cd-114">Измените свойства службы сервера сохраняемого чата в:</span><span class="sxs-lookup"><span data-stu-id="d64cd-114">Edit the Persistent Chat Server service properties to:</span></span>
    
    <span data-ttu-id="d64cd-115">а.</span><span class="sxs-lookup"><span data-stu-id="d64cd-115">a.</span></span> <span data-ttu-id="d64cd-116">Включите зеркальное отображение для базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="d64cd-116">Enable mirroring for the primary database.</span></span>
    
    <span data-ttu-id="d64cd-117">б.</span><span class="sxs-lookup"><span data-stu-id="d64cd-117">b.</span></span> <span data-ttu-id="d64cd-118">Добавьте основное зеркальное хранилище SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d64cd-118">Add the primary mirror SQL Server store.</span></span>
    
    <span data-ttu-id="d64cd-119">в.</span><span class="sxs-lookup"><span data-stu-id="d64cd-119">c.</span></span> <span data-ttu-id="d64cd-120">Настройка базы данных доставки журналов SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d64cd-120">Enable the SQL Server Log Shipping database.</span></span>
    
    <span data-ttu-id="d64cd-121">г.</span><span class="sxs-lookup"><span data-stu-id="d64cd-121">d.</span></span> <span data-ttu-id="d64cd-122">Добавление хранилища доставки журналов SQL Server дополнительного сервера SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d64cd-122">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    <span data-ttu-id="d64cd-123">e.</span><span class="sxs-lookup"><span data-stu-id="d64cd-123">e.</span></span> <span data-ttu-id="d64cd-124">Добавьте зеркало хранилища SQL Server для базы данных-получателя.</span><span class="sxs-lookup"><span data-stu-id="d64cd-124">Add the SQL Server store mirror for the secondary database.</span></span>
    
    <span data-ttu-id="d64cd-125">f.</span><span class="sxs-lookup"><span data-stu-id="d64cd-125">f.</span></span> <span data-ttu-id="d64cd-126">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="d64cd-126">Publish the topology.</span></span>
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="d64cd-127">Настройка доставки журналов SQL Server для основной базы данных сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="d64cd-127">Set up SQL Server log shipping for the Persistent Chat Server primary database</span></span>

<span data-ttu-id="d64cd-128">С помощью SQL Server Management Studio, подключиться к сервера сохраняемого чата экземпляру доставки журналов базы данных и убедитесь, что запущен агент SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d64cd-128">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span> <span data-ttu-id="d64cd-129">Затем подключитесь к экземпляру основной базы данных Persistent Chat и выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="d64cd-129">Then connect to the Persistent Chat primary database instance and perform the following steps:</span></span>
  
1. <span data-ttu-id="d64cd-130">Щелкните базу данных mgc правой кнопкой мыши и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="d64cd-130">Right-click the mgc database, and then click **Properties**.</span></span>
    
2. <span data-ttu-id="d64cd-131">В области **Выбор страницы** выберите **Доставка журналов транзакций**.</span><span class="sxs-lookup"><span data-stu-id="d64cd-131">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
3. <span data-ttu-id="d64cd-132">Установите флажок **Включить эту базу данных в качестве источника в конфигурацию доставки журналов**.</span><span class="sxs-lookup"><span data-stu-id="d64cd-132">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
4. <span data-ttu-id="d64cd-133">В области **Резервные копии журналов транзакций** щелкните элемент **Параметры копирования**.</span><span class="sxs-lookup"><span data-stu-id="d64cd-133">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
5. <span data-ttu-id="d64cd-134">В поле **Сетевой путь к каталогу резервной копии** введите сетевой путь к общей папке, созданной для резервных копий журналов транзакций.</span><span class="sxs-lookup"><span data-stu-id="d64cd-134">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>
    
6. <span data-ttu-id="d64cd-p110">Если папка резервного копирования располагается на основном сервере, введите локальный путь к папке резервного копирования в поле **Если папка резервного копирования находится на сервере-источнике, укажите локальный путь к папке (пример: c:\backup)**. (Если папка резервного копирования находится не на основном сервере, это поле можно оставить пустым.)</span><span class="sxs-lookup"><span data-stu-id="d64cd-p110">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\backup)** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d64cd-137">Если учетная запись службы SQL Server на сервере-источнике выполняется от имени учетной записи локальной системы, необходимо создать папку резервного копирования на сервере-источнике и указать локальный путь к этой папке.</span><span class="sxs-lookup"><span data-stu-id="d64cd-137">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
7. <span data-ttu-id="d64cd-138">Настройте параметры **Удалить файлы, созданные ранее** и **Предупредить, если резервное копирование не произошло в течение**.</span><span class="sxs-lookup"><span data-stu-id="d64cd-138">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
8. <span data-ttu-id="d64cd-139">Просмотрите расписание резервного копирования, приведенное в поле **Расписание** в разделе **Задание резервного копирования**.</span><span class="sxs-lookup"><span data-stu-id="d64cd-139">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="d64cd-140">Чтобы настроить расписание для установки, нажмите кнопку **расписание**и настройте расписание агента SQL Server при необходимости.</span><span class="sxs-lookup"><span data-stu-id="d64cd-140">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>
    
9. <span data-ttu-id="d64cd-141">В разделе **Сжатие** выберите флажок **Использовать параметр сервера по умолчанию** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d64cd-141">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>
    
10. <span data-ttu-id="d64cd-142">В области **Экземпляры сервера-получателя и базы данных** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d64cd-142">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
11. <span data-ttu-id="d64cd-143">Нажмите кнопку **Подключить** и подключитесь к экземпляру SQL Server, которая была выбрана в качестве сервера-получателя.</span><span class="sxs-lookup"><span data-stu-id="d64cd-143">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
12. <span data-ttu-id="d64cd-144">В поле **База данных-получатель** выберите в списке базу данных **mgc**.</span><span class="sxs-lookup"><span data-stu-id="d64cd-144">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
13. <span data-ttu-id="d64cd-145">На вкладке **Инициализация базы данных-получателя** выберите вариант **Да**, создайте полную резервную копию базы данных-источника и выполните восстановление из нее в базу данных-получатель (и создайте базу данных-получатель, если она не существует).</span><span class="sxs-lookup"><span data-stu-id="d64cd-145">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>
    
14. <span data-ttu-id="d64cd-p112">На вкладке **Копирование файлов** в поле **Папка назначения для копирования файлов** введите путь к папке, в которую необходимо копировать резервные копии журналов транзакций. Эта папка часто находится на дополнительном сервере.</span><span class="sxs-lookup"><span data-stu-id="d64cd-p112">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied. This folder is often located on the secondary server.</span></span>
    
15. <span data-ttu-id="d64cd-148">Обратите внимание на расписание копирования, приведенное в поле **Расписание** в разделе **Задание копирования**.</span><span class="sxs-lookup"><span data-stu-id="d64cd-148">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="d64cd-149">Чтобы настроить расписание для установки, нажмите кнопку **расписание**и настройте расписание агента SQL Server при необходимости.</span><span class="sxs-lookup"><span data-stu-id="d64cd-149">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="d64cd-150">Это расписание должно приблизительно совпадать с расписанием резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="d64cd-150">This schedule should be approximately the same as the backup schedule.</span></span>
    
16. <span data-ttu-id="d64cd-151">На вкладке **Восстановление** в разделе **Папка назначения для копирования файлов** выберите вариант **Режим без восстановления**.</span><span class="sxs-lookup"><span data-stu-id="d64cd-151">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>
    
17. <span data-ttu-id="d64cd-152">В списке **Отложить восстановление резервных копий по крайней мере на** выберите значение **0 минут**.</span><span class="sxs-lookup"><span data-stu-id="d64cd-152">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>
    
18. <span data-ttu-id="d64cd-153">В поле **Предупреждение, если восстановление не выполнено в течение** выберите порог оповещений.</span><span class="sxs-lookup"><span data-stu-id="d64cd-153">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>
    
19. <span data-ttu-id="d64cd-154">Просмотрите расписание восстановления в поле **Расписание** в разделе **Задание восстановления**.</span><span class="sxs-lookup"><span data-stu-id="d64cd-154">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="d64cd-155">Чтобы настроить расписание для установки, нажмите кнопку **расписание**, измените его агента SQL Server при необходимости и нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="d64cd-155">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="d64cd-156">Это расписание должно приблизительно совпадать с расписанием резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="d64cd-156">This schedule should be approximately the same as the backup schedule.</span></span>
    
20. <span data-ttu-id="d64cd-157">В диалоговом окне **Свойства базы данных** нажмите кнопку **ОК**, чтобы приступить к настройке.</span><span class="sxs-lookup"><span data-stu-id="d64cd-157">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a><span data-ttu-id="d64cd-158">Настройка доставки журналов SQL Server между основным зеркалом и дополнительной базой данных</span><span class="sxs-lookup"><span data-stu-id="d64cd-158">Set up SQL Server log shipping between the primary mirror and the secondary database</span></span>

<span data-ttu-id="d64cd-159">Выполните следующие действия для доставки журналов для продолжения, если основной базы данных Persistent Chat отработка отказа для ее зеркальную базу данных.</span><span class="sxs-lookup"><span data-stu-id="d64cd-159">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>
  
1. <span data-ttu-id="d64cd-160">Ручное переключение Persistent Chat базы данных-источника с зеркальным сервером.</span><span class="sxs-lookup"><span data-stu-id="d64cd-160">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="d64cd-161">Это делается с помощью Скайп для консоли Business Server и командлет **Invoke-CsDatabaseFailover** .</span><span class="sxs-lookup"><span data-stu-id="d64cd-161">This is done by using the Skype for Business Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    
2. <span data-ttu-id="d64cd-162">С помощью SQL Server Management Studio, подключитесь к основной экземпляр зеркального сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="d64cd-162">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>
    
3. <span data-ttu-id="d64cd-163">Убедитесь, что запущен агент SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d64cd-163">Be sure that the SQL Server Agent is running.</span></span>
    
4. <span data-ttu-id="d64cd-164">Щелкните базу данных mgc правой кнопкой мыши и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="d64cd-164">Right-click the mgc database, and then click **Properties**.</span></span>
    
5. <span data-ttu-id="d64cd-165">В области **Выбор страницы** выберите **Доставка журналов транзакций**.</span><span class="sxs-lookup"><span data-stu-id="d64cd-165">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
6. <span data-ttu-id="d64cd-166">Установите флажок **Включить эту базу данных в качестве источника в конфигурацию доставки журналов**.</span><span class="sxs-lookup"><span data-stu-id="d64cd-166">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
7. <span data-ttu-id="d64cd-167">В области **Резервные копии журналов транзакций** щелкните элемент **Параметры копирования**.</span><span class="sxs-lookup"><span data-stu-id="d64cd-167">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
8. <span data-ttu-id="d64cd-168">В поле **Сетевой путь к каталогу резервной копии** введите сетевой путь к общей папке, созданной для резервной копии журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="d64cd-168">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>
    
9. <span data-ttu-id="d64cd-p116">Если резервная папка находится на основном сервере, введите локальный путь к этой резервной папке в поле **Если папка резервного копирования находится на сервере-источнике, укажите локальный путь к папке**. (Если резервная папка находится не на основном сервере, вы можете оставить это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="d64cd-p116">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d64cd-171">Если учетная запись службы SQL Server на сервере-источнике выполняется от имени учетной записи локальной системы, необходимо создать папку резервного копирования на сервере-источнике и указать локальный путь к этой папке.</span><span class="sxs-lookup"><span data-stu-id="d64cd-171">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
10. <span data-ttu-id="d64cd-172">Настройте параметры **Удалить файлы, созданные ранее** и **Предупредить, если резервное копирование не произошло в течение**.</span><span class="sxs-lookup"><span data-stu-id="d64cd-172">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
11. <span data-ttu-id="d64cd-173">Просмотрите расписание резервного копирования, приведенное в поле **Расписание** в разделе **Задание резервного копирования**.</span><span class="sxs-lookup"><span data-stu-id="d64cd-173">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="d64cd-174">Чтобы настроить расписание для установки, нажмите кнопку **расписание**и измените его агента SQL Server при необходимости.</span><span class="sxs-lookup"><span data-stu-id="d64cd-174">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d64cd-175">Используйте те же параметры, которые применялись для основной базы данных.</span><span class="sxs-lookup"><span data-stu-id="d64cd-175">Use the same settings that you used for the primary database.</span></span> 
  
12. <span data-ttu-id="d64cd-176">В области **Сжатие** выберите **Использовать параметр сервера по умолчанию** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d64cd-176">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>
    
13. <span data-ttu-id="d64cd-177">В области **Экземпляры сервера-получателя и базы данных** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d64cd-177">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
14. <span data-ttu-id="d64cd-178">Щелкните элемент **Подключение** и подключитесь к экземпляру SQL Server, настроенному вами в качестве сервера-получателя.</span><span class="sxs-lookup"><span data-stu-id="d64cd-178">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
15. <span data-ttu-id="d64cd-179">В поле **База данных-получатель** выберите в списке базу данных **mgc**.</span><span class="sxs-lookup"><span data-stu-id="d64cd-179">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
16. <span data-ttu-id="d64cd-180">На вкладке **Инициализация базы данных-получателя** выберите вариант **Нет, база данных-получатель инициализирована**.</span><span class="sxs-lookup"><span data-stu-id="d64cd-180">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>
    
17. <span data-ttu-id="d64cd-p118">В поле **Папка назначения для копирования** на вкладке **Копирование файлов** введите путь к папке, в которую следует копировать резервные копии журналов транзакций, и нажмите кнопку **ОК**. Часто эта папка расположена на сервере-получателе.</span><span class="sxs-lookup"><span data-stu-id="d64cd-p118">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**. This folder is often located on the secondary server.</span></span>
    
18. <span data-ttu-id="d64cd-183">Откройте раскрывающийся список **Скрипт конфигурации** и выберите **Вывести конфигурацию в новое окно запроса**.</span><span class="sxs-lookup"><span data-stu-id="d64cd-183">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>
    
19. <span data-ttu-id="d64cd-184">В разделе **Свойства базы данных** окна нового запроса нажмите кнопку **ОК**, чтобы начать процесс настройки.</span><span class="sxs-lookup"><span data-stu-id="d64cd-184">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>
    
20. <span data-ttu-id="d64cd-185">Выберите и запустите первая часть запроса (см. шаг 18) вверх на строку:-- \* \* \* \* \* \* конец: сценарий для запуска на источнике: \* \* \* \* \* \*.</span><span class="sxs-lookup"><span data-stu-id="d64cd-185">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d64cd-186">Ручное выполнение этого скрипта является обязательным, поскольку SQL Server Management Studio не поддерживает несколько основных баз данных в конфигурации доставки журналов SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d64cd-186">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span> 
  
21. <span data-ttu-id="d64cd-187">Выберите **Отмена**, чтобы закрыть панель конфигурации доставки журналов и создать рабочую программу установки, которая правильно внедряет доставку файлов журналов как для основной, так и для зеркальной базы данных (в случае отработки отказа). </span><span class="sxs-lookup"><span data-stu-id="d64cd-187">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>
    
22. <span data-ttu-id="d64cd-188">Сохраняемый чат базы данных-источника на основную сбоя вручную.</span><span class="sxs-lookup"><span data-stu-id="d64cd-188">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="d64cd-189">Это делается с помощью Скайп для консоли Business Server и командлет **Invoke-CsDatabaseFailover** .</span><span class="sxs-lookup"><span data-stu-id="d64cd-189">This is done by using the Skype for Business Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    

