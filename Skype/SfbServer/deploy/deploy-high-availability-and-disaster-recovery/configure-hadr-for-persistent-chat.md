---
title: Настройка высокой доступности и аварийного восстановления для сервера сохраняемой беседы в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: Сводка. В этом разделе вы узнаете, как настроить высокую доступность и аварийное восстановление для сервера сохраняемой беседы в Skype для бизнеса Server 2015.
ms.openlocfilehash: 0b58f820c1157da8ff36f8dcc68d9e08465bcddc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830629"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="c8df4-103">Настройка высокой доступности и аварийного восстановления для сервера сохраняемой беседы в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="c8df4-103">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c8df4-104">**Сводка:** В этом разделе вы узнаете, как настроить высокую доступность и аварийное восстановление для сервера сохраняемой беседы в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c8df4-104">**Summary:** Read this topic to learn how to configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="c8df4-105">Skype для бизнеса Server поддерживает несколько режимов высокой доступности для серверов, в том числе зеркальное отражение базы данных.</span><span class="sxs-lookup"><span data-stu-id="c8df4-105">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="c8df4-106">Дополнительные сведения см. в плане высокой доступности и аварийного восстановления [в Skype для бизнеса Server 2015.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="c8df4-106">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c8df4-107">Группы доступности AlwaysOn не поддерживаются серверами сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="c8df4-107">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="c8df4-108">Прежде чем настраивать развертывание сохраняемой беседы для высокой доступности и аварийного восстановления, ознакомьтесь с понятиями в плане высокой доступности и аварийного восстановления для сервера сохраняемой беседы в Skype для бизнеса [Server 2015.](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="c8df4-108">Before you configure your Persistent Chat deployment for high availability and disaster recovery, be sure you are familiar with the concepts in [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="c8df4-109">Решение аварийного восстановления для сервера сохраняемой беседы, описанное в этих темах, построено на растянутом пуле серверов сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="c8df4-109">The disaster recovery solution for Persistent Chat Server described in these topics is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="c8df4-110">В контенте планирования описываются требования к ресурсам и топология растянутой пула, которая обеспечивает высокую доступность и аварийное восстановление для сервера сохраняемой беседы, включая использование зеркального SQL Server для обеспечения высокой доступности и доставки журналов SQL Server для аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="c8df4-110">The planning content describes resource requirements, and the stretched pool topology that enables high availability and disaster recovery for Persistent Chat Server, including using SQL Server mirroring for high availability and SQL Server log shipping for disaster recovery.</span></span>
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a><span data-ttu-id="c8df4-111">Использование построитель топологий для настройки высокой доступности и аварийного восстановления</span><span class="sxs-lookup"><span data-stu-id="c8df4-111">Use Topology Builder to configure high availability and disaster recovery</span></span>

<span data-ttu-id="c8df4-112">В построитель топологий выполните следующие действия, чтобы настроить высокую доступность и аварийное восстановление для сервера сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="c8df4-112">Within Topology Builder, perform the following steps to configure high availability and disaster recovery for Persistent Chat Server.</span></span>
  
1. <span data-ttu-id="c8df4-113">Добавьте зеркальные базы данных и дополнительные базы данных доставки журналов SQL Server хранилищах.</span><span class="sxs-lookup"><span data-stu-id="c8df4-113">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>
    
2. <span data-ttu-id="c8df4-114">Изменить свойства службы сервера сохраняемой беседы, чтобы:</span><span class="sxs-lookup"><span data-stu-id="c8df4-114">Edit the Persistent Chat Server service properties to:</span></span>
    
    <span data-ttu-id="c8df4-115">а.</span><span class="sxs-lookup"><span data-stu-id="c8df4-115">a.</span></span> <span data-ttu-id="c8df4-116">Включите зеркальное отображение для базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="c8df4-116">Enable mirroring for the primary database.</span></span>
    
    <span data-ttu-id="c8df4-117">б.</span><span class="sxs-lookup"><span data-stu-id="c8df4-117">b.</span></span> <span data-ttu-id="c8df4-118">Добавьте основное зеркальное SQL Server хранения.</span><span class="sxs-lookup"><span data-stu-id="c8df4-118">Add the primary mirror SQL Server store.</span></span>
    
    <span data-ttu-id="c8df4-119">c.</span><span class="sxs-lookup"><span data-stu-id="c8df4-119">c.</span></span> <span data-ttu-id="c8df4-120">В SQL Server базы данных доставки журналов.</span><span class="sxs-lookup"><span data-stu-id="c8df4-120">Enable the SQL Server Log Shipping database.</span></span>
    
    <span data-ttu-id="c8df4-121">г.</span><span class="sxs-lookup"><span data-stu-id="c8df4-121">d.</span></span> <span data-ttu-id="c8df4-122">Добавьте дополнительный SQL Server доставки журналов SQL Server хранения.</span><span class="sxs-lookup"><span data-stu-id="c8df4-122">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    <span data-ttu-id="c8df4-123">д.</span><span class="sxs-lookup"><span data-stu-id="c8df4-123">e.</span></span> <span data-ttu-id="c8df4-124">Добавьте зеркальное SQL Server для базы данных-дополнительного.</span><span class="sxs-lookup"><span data-stu-id="c8df4-124">Add the SQL Server store mirror for the secondary database.</span></span>
    
    <span data-ttu-id="c8df4-125">е.</span><span class="sxs-lookup"><span data-stu-id="c8df4-125">f.</span></span> <span data-ttu-id="c8df4-126">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="c8df4-126">Publish the topology.</span></span>
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="c8df4-127">Настройка доставки SQL Server журналов для основной базы данных сервера сохраняемой беседы</span><span class="sxs-lookup"><span data-stu-id="c8df4-127">Set up SQL Server log shipping for the Persistent Chat Server primary database</span></span>

<span data-ttu-id="c8df4-128">С SQL Server Management Studio подключите дополнительный экземпляр базы данных доставки журналов сервера сохраняемого чата и убедитесь, что SQL Server агент запущен.</span><span class="sxs-lookup"><span data-stu-id="c8df4-128">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span> <span data-ttu-id="c8df4-129">Затем подключите основной экземпляр базы данных сохраняемой беседы и выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="c8df4-129">Then connect to the Persistent Chat primary database instance and perform the following steps:</span></span>
  
1. <span data-ttu-id="c8df4-130">Щелкните базу данных mgc правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="c8df4-130">Right-click the mgc database, and then click **Properties**.</span></span>
    
2. <span data-ttu-id="c8df4-131">В области **Выбор страницы** щелкните элемент **Доставка журналов транзакций**.</span><span class="sxs-lookup"><span data-stu-id="c8df4-131">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
3. <span data-ttu-id="c8df4-132">Установите флажок **Включить эту базу данных в качестве источника в конфигурацию доставки журналов**.</span><span class="sxs-lookup"><span data-stu-id="c8df4-132">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
4. <span data-ttu-id="c8df4-133">В области **Резервные копии журналов транзакций** щелкните элемент **Параметры копирования**.</span><span class="sxs-lookup"><span data-stu-id="c8df4-133">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
5. <span data-ttu-id="c8df4-134">В **сетевом пути к папке** резервной копии введите сетевой путь к папке, созданной для папки резервного копирования журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="c8df4-134">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>
    
6. <span data-ttu-id="c8df4-135">Если резервная папка расположена на основном сервере, введите локальный путь к папке резервного копирования в поле "Если резервная папка расположена на основном сервере", введите локальный путь к папке **(например, c:\backup).**</span><span class="sxs-lookup"><span data-stu-id="c8df4-135">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\backup)** box.</span></span> <span data-ttu-id="c8df4-136">(Если резервная папка находится не на основном сервере, вы можете оставить это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="c8df4-136">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c8df4-137">Если учетная запись SQL Server на основном сервере работает под локальной системной учетной записью, необходимо создать папку резервного копирования на основном сервере и указать локальный путь к этой папке.</span><span class="sxs-lookup"><span data-stu-id="c8df4-137">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
7. <span data-ttu-id="c8df4-138">Настройте параметры **Удалить файлы, созданные ранее** и **Предупредить, если резервное копирование не произошло в течение**.</span><span class="sxs-lookup"><span data-stu-id="c8df4-138">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
8. <span data-ttu-id="c8df4-139">Просмотрите расписание резервного копирования, указанное в поле **Расписание** области **Задание резервного копирования**.</span><span class="sxs-lookup"><span data-stu-id="c8df4-139">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="c8df4-140">Чтобы настроить расписание установки, нажмите кнопку **"Расписание"** и SQL Server агента по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="c8df4-140">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>
    
9. <span data-ttu-id="c8df4-141">В **области "Сжатие"** **выберите "Использовать параметр сервера по умолчанию"** и нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="c8df4-141">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>
    
10. <span data-ttu-id="c8df4-142">В области **Экземпляры сервера-получателя и базы данных** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="c8df4-142">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
11. <span data-ttu-id="c8df4-143">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span><span class="sxs-lookup"><span data-stu-id="c8df4-143">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
12. <span data-ttu-id="c8df4-144">В поле **База данных-получатель** выберите в списке базу данных **mgc**.</span><span class="sxs-lookup"><span data-stu-id="c8df4-144">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
13. <span data-ttu-id="c8df4-145">На  вкладке "Инициализация базы данных-дополнительного" выберите вариант **"Да",** создайте полную резервную копию основной базы данных и восстановим ее во вторичной базе данных (и создайте вторичную базу данных, если она не существует).</span><span class="sxs-lookup"><span data-stu-id="c8df4-145">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>
    
14. <span data-ttu-id="c8df4-146">На **вкладке "Копирование** файлов" в папке **назначения** для копирования файлов введите путь к папке, в которую следует скопировать резервные копии журналов транзакций.</span><span class="sxs-lookup"><span data-stu-id="c8df4-146">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied.</span></span> <span data-ttu-id="c8df4-147">Часто эта папка расположена на сервере-получателе.</span><span class="sxs-lookup"><span data-stu-id="c8df4-147">This folder is often located on the secondary server.</span></span>
    
15. <span data-ttu-id="c8df4-148">Обратите внимание на расписание копирования, перечисленное в **поле расписания** в **статье "Задание копирования".**</span><span class="sxs-lookup"><span data-stu-id="c8df4-148">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="c8df4-149">Чтобы настроить расписание установки, нажмите кнопку **"Расписание"** и SQL Server агента по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="c8df4-149">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="c8df4-150">Это расписание должно приблизительно быть таким же, как и расписание резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="c8df4-150">This schedule should be approximately the same as the backup schedule.</span></span>
    
16. <span data-ttu-id="c8df4-151">На **вкладке "Восстановление"** в области **"Состояние базы данных"** при восстановлении резервных копий выберите режим **"Нет восстановления".**</span><span class="sxs-lookup"><span data-stu-id="c8df4-151">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>
    
17. <span data-ttu-id="c8df4-152">Under **Delay restoring backups at least:**, select **0 minutes**.</span><span class="sxs-lookup"><span data-stu-id="c8df4-152">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>
    
18. <span data-ttu-id="c8df4-153">Выберите порог оповещения в области **"Оповещение", если восстановление в пределах не происходит.**</span><span class="sxs-lookup"><span data-stu-id="c8df4-153">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>
    
19. <span data-ttu-id="c8df4-154">Посмотрите на расписание восстановления, перечисленное в поле **"Расписание"** задания **"Восстановление".**</span><span class="sxs-lookup"><span data-stu-id="c8df4-154">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="c8df4-155">Чтобы настроить расписание установки, нажмите кнопку "Расписание", SQL Server агента по мере необходимости и нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="c8df4-155">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="c8df4-156">Это расписание должно приблизительно быть таким же, как и расписание резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="c8df4-156">This schedule should be approximately the same as the backup schedule.</span></span>
    
20. <span data-ttu-id="c8df4-157">В **диалоговом окне "Свойства** базы данных" нажмите кнопку "ОК", чтобы начать процесс настройки. </span><span class="sxs-lookup"><span data-stu-id="c8df4-157">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a><span data-ttu-id="c8df4-158">Настройка доставки SQL Server журналов между основным зеркалом и базой данных-дополнительным</span><span class="sxs-lookup"><span data-stu-id="c8df4-158">Set up SQL Server log shipping between the primary mirror and the secondary database</span></span>

<span data-ttu-id="c8df4-159">Выполните следующие действия, чтобы продолжить доставку журналов, если основная база данных сохраняемой беседы перенаправилась в зеркальную базу данных.</span><span class="sxs-lookup"><span data-stu-id="c8df4-159">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>
  
1. <span data-ttu-id="c8df4-160">Вручную перетасть основную базу данных сохраняемого чата на зеркальное.</span><span class="sxs-lookup"><span data-stu-id="c8df4-160">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="c8df4-161">Для этого используется оболочка управления Skype для бизнеса Server и **cmdlet Invoke-CsDatabaseFailover.**</span><span class="sxs-lookup"><span data-stu-id="c8df4-161">This is done by using the Skype for Business Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    
2. <span data-ttu-id="c8df4-162">С помощью SQL Server Management Studio подключите основной зеркальный экземпляр сервера сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="c8df4-162">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>
    
3. <span data-ttu-id="c8df4-163">Убедитесь, что агент SQL Server запущен.</span><span class="sxs-lookup"><span data-stu-id="c8df4-163">Be sure that the SQL Server Agent is running.</span></span>
    
4. <span data-ttu-id="c8df4-164">Щелкните базу данных mgc правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="c8df4-164">Right-click the mgc database, and then click **Properties**.</span></span>
    
5. <span data-ttu-id="c8df4-165">В области **Выбор страницы** щелкните элемент **Доставка журналов транзакций**.</span><span class="sxs-lookup"><span data-stu-id="c8df4-165">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
6. <span data-ttu-id="c8df4-166">Установите флажок **Включить эту базу данных в качестве источника в конфигурацию доставки журналов**.</span><span class="sxs-lookup"><span data-stu-id="c8df4-166">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
7. <span data-ttu-id="c8df4-167">В области **Резервные копии журналов транзакций** щелкните элемент **Параметры копирования**.</span><span class="sxs-lookup"><span data-stu-id="c8df4-167">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
8. <span data-ttu-id="c8df4-168">В поле **Network path to the backup folder** (Сетевой путь к каталогу резервной копии) введите сетевой путь к общей папке, созданной для резервной копии журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="c8df4-168">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>
    
9. <span data-ttu-id="c8df4-p116">Если резервная папка находится на основном сервере, введите локальный путь к этой резервной папке в поле **Если папка резервного копирования находится на сервере-источнике, укажите локальный путь к папке**. (Если резервная папка находится не на основном сервере, вы можете оставить это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="c8df4-p116">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c8df4-171">Если учетная запись SQL Server на основном сервере работает под локальной системной учетной записью, необходимо создать папку резервного копирования на основном сервере и указать локальный путь к этой папке.</span><span class="sxs-lookup"><span data-stu-id="c8df4-171">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
10. <span data-ttu-id="c8df4-172">Настройте параметры **Удалить файлы, созданные ранее** и **Предупредить, если резервное копирование не произошло в течение**.</span><span class="sxs-lookup"><span data-stu-id="c8df4-172">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
11. <span data-ttu-id="c8df4-173">Просмотрите расписание резервного копирования, указанное в поле **Расписание** области **Задание резервного копирования**.</span><span class="sxs-lookup"><span data-stu-id="c8df4-173">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="c8df4-174">Чтобы настроить расписание установки, щелкните "Расписание" и SQL Server агента по мере необходимости. </span><span class="sxs-lookup"><span data-stu-id="c8df4-174">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c8df4-175">Используйте те же параметры, которые применялись для основной базы данных.</span><span class="sxs-lookup"><span data-stu-id="c8df4-175">Use the same settings that you used for the primary database.</span></span> 
  
12. <span data-ttu-id="c8df4-176">В области **Сжатие** выберите **Использовать параметр сервера по умолчанию** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c8df4-176">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>
    
13. <span data-ttu-id="c8df4-177">В области **Экземпляры сервера-получателя и базы данных** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="c8df4-177">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
14. <span data-ttu-id="c8df4-178">Щелкните элемент **Подключение** и подключитесь к экземпляру SQL Server, настроенному вами в качестве сервера-получателя.</span><span class="sxs-lookup"><span data-stu-id="c8df4-178">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
15. <span data-ttu-id="c8df4-179">В поле **База данных-получатель** выберите в списке базу данных **mgc**.</span><span class="sxs-lookup"><span data-stu-id="c8df4-179">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
16. <span data-ttu-id="c8df4-180">На вкладке **Инициализация базы данных-получателя** выберите параметр **Нет, база данных-получатель инициализирована**.</span><span class="sxs-lookup"><span data-stu-id="c8df4-180">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>
    
17. <span data-ttu-id="c8df4-p118">В поле **Папка назначения для копирования** на вкладке **Копирование файлов**  введите путь к папке, в которую следует копировать резервные копии журналов транзакций, и нажмите кнопку **ОК**. Часто эта папка расположена на сервере-получателе.</span><span class="sxs-lookup"><span data-stu-id="c8df4-p118">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**. This folder is often located on the secondary server.</span></span>
    
18. <span data-ttu-id="c8df4-183">Откройте раскрывающийся список **Скрипт конфигурации** и выберите **Вывести конфигурацию в новое окно запроса**.</span><span class="sxs-lookup"><span data-stu-id="c8df4-183">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>
    
19. <span data-ttu-id="c8df4-184">В разделе **Свойства базы данных** окна нового запроса нажмите кнопку **ОК**, чтобы начать процесс настройки.</span><span class="sxs-lookup"><span data-stu-id="c8df4-184">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>
    
20. <span data-ttu-id="c8df4-185">Выберите и запустите первую половину запроса (см. шаг 18) до строки: -- \* \* \* \* \* \* End: Script to be run at Primary: \* \* \* \* \* \* .</span><span class="sxs-lookup"><span data-stu-id="c8df4-185">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c8df4-186">Запуск этого сценария вручную необходим, SQL Server Management Studio не поддерживает несколько основных баз данных в конфигурации SQL Server доставки журналов.</span><span class="sxs-lookup"><span data-stu-id="c8df4-186">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span> 
  
21. <span data-ttu-id="c8df4-187">Выберите **Отмена**, чтобы закрыть панель конфигурации доставки журналов и создать рабочую программу установки, которая правильно внедряет доставку файлов журналов как для основной, так и для зеркальной базы данных (в случае отработки отказа).</span><span class="sxs-lookup"><span data-stu-id="c8df4-187">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>
    
22. <span data-ttu-id="c8df4-188">Вручную вернуть основную базу данных сохраняемого чата в основную.</span><span class="sxs-lookup"><span data-stu-id="c8df4-188">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="c8df4-189">Для этого используется оболочка управления Skype для бизнеса Server и **cmdlet Invoke-CsDatabaseFailover.**</span><span class="sxs-lookup"><span data-stu-id="c8df4-189">This is done by using the Skype for Business Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    

