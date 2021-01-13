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
ms.openlocfilehash: 10d9e2eb76873cedc82daea817a732b8feb379da
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802139"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="763e7-103">Настройка высокой доступности и аварийного восстановления для сервера сохраняемой беседы в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="763e7-103">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="763e7-104">**Сводка:** В этом разделе вы узнаете, как настроить высокую доступность и аварийное восстановление для сервера сохраняемой беседы в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="763e7-104">**Summary:** Read this topic to learn how to configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="763e7-105">Skype для бизнеса Server поддерживает несколько режимов высокой доступности для серверов, включая зеркальное отражение базы данных.</span><span class="sxs-lookup"><span data-stu-id="763e7-105">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="763e7-106">Дополнительные сведения см. в плане высокой доступности и аварийного восстановления [в Skype для бизнеса Server 2015.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="763e7-106">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="763e7-107">Группы доступности AlwaysOn не поддерживаются серверами сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="763e7-107">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 

> [!NOTE] 
> <span data-ttu-id="763e7-108">Сохраняемая беседа доступна в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="763e7-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="763e7-109">Такие же функции доступны в Teams.</span><span class="sxs-lookup"><span data-stu-id="763e7-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="763e7-110">Дополнительные сведения [см. в сведениях о том,](/microsoftteams/upgrade-start-here)как начать обновление Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="763e7-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="763e7-111">Если необходимо использовать сохраняемого чата, вы можете либо перенести пользователей, которым требуются эти функции, в Teams, либо продолжить использование Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="763e7-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="763e7-112">Прежде чем настраивать развертывание сохраняемой беседы для высокой доступности и аварийного восстановления, ознакомьтесь с понятиями в плане высокой доступности и аварийного восстановления для сервера сохраняемой беседы в Skype для бизнеса [Server 2015.](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="763e7-112">Before you configure your Persistent Chat deployment for high availability and disaster recovery, be sure you are familiar with the concepts in [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="763e7-113">Решение аварийного восстановления для сервера сохраняемой беседы, описанное в этих темах, построено на растянутом пуле серверов сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="763e7-113">The disaster recovery solution for Persistent Chat Server described in these topics is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="763e7-114">В контенте планирования описываются требования к ресурсам и топология растянутой пула, которая обеспечивает высокую доступность и аварийное восстановление для сервера сохраняемой беседы, включая использование зеркального SQL Server для обеспечения высокой доступности и доставки журналов SQL Server для аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="763e7-114">The planning content describes resource requirements, and the stretched pool topology that enables high availability and disaster recovery for Persistent Chat Server, including using SQL Server mirroring for high availability and SQL Server log shipping for disaster recovery.</span></span>
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a><span data-ttu-id="763e7-115">Использование построитель топологий для настройки высокой доступности и аварийного восстановления</span><span class="sxs-lookup"><span data-stu-id="763e7-115">Use Topology Builder to configure high availability and disaster recovery</span></span>

<span data-ttu-id="763e7-116">В построитель топологий выполните следующие действия, чтобы настроить высокую доступность и аварийное восстановление для сервера сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="763e7-116">Within Topology Builder, perform the following steps to configure high availability and disaster recovery for Persistent Chat Server.</span></span>
  
1. <span data-ttu-id="763e7-117">Добавьте зеркальные базы данных и дополнительные базы данных доставки журналов SQL Server хранилищах.</span><span class="sxs-lookup"><span data-stu-id="763e7-117">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>
    
2. <span data-ttu-id="763e7-118">Изменить свойства службы сервера сохраняемой беседы, чтобы:</span><span class="sxs-lookup"><span data-stu-id="763e7-118">Edit the Persistent Chat Server service properties to:</span></span>
    
    <span data-ttu-id="763e7-119">а.</span><span class="sxs-lookup"><span data-stu-id="763e7-119">a.</span></span> <span data-ttu-id="763e7-120">Включите зеркальное отображение для базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="763e7-120">Enable mirroring for the primary database.</span></span>
    
    <span data-ttu-id="763e7-121">б.</span><span class="sxs-lookup"><span data-stu-id="763e7-121">b.</span></span> <span data-ttu-id="763e7-122">Добавьте основное хранилище SQL Server зеркала.</span><span class="sxs-lookup"><span data-stu-id="763e7-122">Add the primary mirror SQL Server store.</span></span>
    
    <span data-ttu-id="763e7-123">c.</span><span class="sxs-lookup"><span data-stu-id="763e7-123">c.</span></span> <span data-ttu-id="763e7-124">В SQL Server базы данных доставки журналов.</span><span class="sxs-lookup"><span data-stu-id="763e7-124">Enable the SQL Server Log Shipping database.</span></span>
    
    <span data-ttu-id="763e7-125">г.</span><span class="sxs-lookup"><span data-stu-id="763e7-125">d.</span></span> <span data-ttu-id="763e7-126">Добавьте дополнительный SQL Server доставки журналов SQL Server хранения.</span><span class="sxs-lookup"><span data-stu-id="763e7-126">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    <span data-ttu-id="763e7-127">д.</span><span class="sxs-lookup"><span data-stu-id="763e7-127">e.</span></span> <span data-ttu-id="763e7-128">Добавьте зеркальное SQL Server для базы данных-дополнительного.</span><span class="sxs-lookup"><span data-stu-id="763e7-128">Add the SQL Server store mirror for the secondary database.</span></span>
    
    <span data-ttu-id="763e7-129">е.</span><span class="sxs-lookup"><span data-stu-id="763e7-129">f.</span></span> <span data-ttu-id="763e7-130">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="763e7-130">Publish the topology.</span></span>
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="763e7-131">Настройка доставки SQL Server журналов для основной базы данных сервера сохраняемой беседы</span><span class="sxs-lookup"><span data-stu-id="763e7-131">Set up SQL Server log shipping for the Persistent Chat Server primary database</span></span>

<span data-ttu-id="763e7-132">С SQL Server Management Studio подключите дополнительный экземпляр базы данных доставки журналов сервера сохраняемого чата и убедитесь, что SQL Server агент запущен.</span><span class="sxs-lookup"><span data-stu-id="763e7-132">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span> <span data-ttu-id="763e7-133">Затем подключите основной экземпляр базы данных сохраняемой беседы и выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="763e7-133">Then connect to the Persistent Chat primary database instance and perform the following steps:</span></span>
  
1. <span data-ttu-id="763e7-134">Щелкните базу данных mgc правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="763e7-134">Right-click the mgc database, and then click **Properties**.</span></span>
    
2. <span data-ttu-id="763e7-135">В области **Выбор страницы** щелкните элемент **Доставка журналов транзакций**.</span><span class="sxs-lookup"><span data-stu-id="763e7-135">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
3. <span data-ttu-id="763e7-136">Установите флажок **Включить эту базу данных в качестве источника в конфигурацию доставки журналов**.</span><span class="sxs-lookup"><span data-stu-id="763e7-136">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
4. <span data-ttu-id="763e7-137">В области **Резервные копии журналов транзакций** щелкните элемент **Параметры копирования**.</span><span class="sxs-lookup"><span data-stu-id="763e7-137">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
5. <span data-ttu-id="763e7-138">В **сетевом пути к папке** резервной копии введите сетевой путь к папке, созданной для папки резервного копирования журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="763e7-138">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>
    
6. <span data-ttu-id="763e7-139">Если резервная папка расположена на основном сервере, введите локальный путь к папке резервного копирования в поле "Если резервная папка расположена на основном сервере", введите локальный путь к папке **(например, c:\backup).**</span><span class="sxs-lookup"><span data-stu-id="763e7-139">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\backup)** box.</span></span> <span data-ttu-id="763e7-140">(Если резервная папка находится не на основном сервере, вы можете оставить это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="763e7-140">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="763e7-141">Если учетная запись SQL Server на основном сервере работает под локальной системной учетной записью, необходимо создать папку резервного копирования на основном сервере и указать локальный путь к этой папке.</span><span class="sxs-lookup"><span data-stu-id="763e7-141">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
7. <span data-ttu-id="763e7-142">Настройте параметры **Удалить файлы, созданные ранее** и **Предупредить, если резервное копирование не произошло в течение**.</span><span class="sxs-lookup"><span data-stu-id="763e7-142">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
8. <span data-ttu-id="763e7-143">Просмотрите расписание резервного копирования, указанное в поле **Расписание** области **Задание резервного копирования**.</span><span class="sxs-lookup"><span data-stu-id="763e7-143">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="763e7-144">Чтобы настроить расписание установки, нажмите кнопку **"Расписание"** и SQL Server агента по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="763e7-144">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>
    
9. <span data-ttu-id="763e7-145">В **области "Сжатие"** **выберите "Использовать параметр сервера по умолчанию"** и нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="763e7-145">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>
    
10. <span data-ttu-id="763e7-146">В области **Экземпляры сервера-получателя и базы данных** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="763e7-146">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
11. <span data-ttu-id="763e7-147">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span><span class="sxs-lookup"><span data-stu-id="763e7-147">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
12. <span data-ttu-id="763e7-148">В поле **База данных-получатель** выберите в списке базу данных **mgc**.</span><span class="sxs-lookup"><span data-stu-id="763e7-148">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
13. <span data-ttu-id="763e7-149">На  вкладке "Инициализация базы данных-дополнительного" выберите вариант **"Да",** создайте полную резервную копию основной базы данных и восстановим ее во вторичной базе данных (и создайте вторичную базу данных, если она не существует).</span><span class="sxs-lookup"><span data-stu-id="763e7-149">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>
    
14. <span data-ttu-id="763e7-150">На **вкладке "Копирование** файлов" в папке **"Назначение"** для копирования файлов введите путь к папке, в которую следует скопировать резервные копии журналов транзакций.</span><span class="sxs-lookup"><span data-stu-id="763e7-150">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied.</span></span> <span data-ttu-id="763e7-151">Часто эта папка расположена на сервере-получателе.</span><span class="sxs-lookup"><span data-stu-id="763e7-151">This folder is often located on the secondary server.</span></span>
    
15. <span data-ttu-id="763e7-152">Обратите внимание на расписание копирования, перечисленное в **поле расписания** в **статье "Задание копирования".**</span><span class="sxs-lookup"><span data-stu-id="763e7-152">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="763e7-153">Чтобы настроить расписание установки, нажмите кнопку **"Расписание"** и SQL Server агента по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="763e7-153">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="763e7-154">Это расписание должно приблизительно быть таким же, как и расписание резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="763e7-154">This schedule should be approximately the same as the backup schedule.</span></span>
    
16. <span data-ttu-id="763e7-155">На **вкладке "Восстановление"** в области **"Состояние базы данных"** при восстановлении резервных копий выберите режим **"Нет восстановления".**</span><span class="sxs-lookup"><span data-stu-id="763e7-155">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>
    
17. <span data-ttu-id="763e7-156">Under **Delay restoring backups at least:**, select **0 minutes**.</span><span class="sxs-lookup"><span data-stu-id="763e7-156">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>
    
18. <span data-ttu-id="763e7-157">Выберите порог оповещения в области **"Оповещение", если восстановление в пределах не происходит.**</span><span class="sxs-lookup"><span data-stu-id="763e7-157">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>
    
19. <span data-ttu-id="763e7-158">Посмотрите на расписание восстановления, перечисленное в поле **"Расписание"** задания **"Восстановление".**</span><span class="sxs-lookup"><span data-stu-id="763e7-158">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="763e7-159">Чтобы настроить расписание установки, нажмите кнопку "Расписание", SQL Server агента по мере необходимости и нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="763e7-159">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="763e7-160">Это расписание должно приблизительно быть таким же, как и расписание резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="763e7-160">This schedule should be approximately the same as the backup schedule.</span></span>
    
20. <span data-ttu-id="763e7-161">В **диалоговом окне "Свойства** базы данных" нажмите кнопку "ОК", чтобы начать процесс настройки. </span><span class="sxs-lookup"><span data-stu-id="763e7-161">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a><span data-ttu-id="763e7-162">Настройка доставки SQL Server журналов между основным зеркальным и дополнительным базой данных</span><span class="sxs-lookup"><span data-stu-id="763e7-162">Set up SQL Server log shipping between the primary mirror and the secondary database</span></span>

<span data-ttu-id="763e7-163">Выполните следующие действия, чтобы доставка журналов продолжалась, если основная база данных сохраняемой беседы перенаправилась в зеркальную базу данных.</span><span class="sxs-lookup"><span data-stu-id="763e7-163">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>
  
1. <span data-ttu-id="763e7-164">Вручную перетасть основную базу данных сохраняемого чата на зеркальное.</span><span class="sxs-lookup"><span data-stu-id="763e7-164">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="763e7-165">Для этого используется оболочка управления Skype для бизнеса Server и **cmdlet Invoke-CsDatabaseFailover.**</span><span class="sxs-lookup"><span data-stu-id="763e7-165">This is done by using the Skype for Business Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    
2. <span data-ttu-id="763e7-166">С помощью SQL Server Management Studio подключите основной зеркальный экземпляр сервера сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="763e7-166">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>
    
3. <span data-ttu-id="763e7-167">Убедитесь, что агент SQL Server запущен.</span><span class="sxs-lookup"><span data-stu-id="763e7-167">Be sure that the SQL Server Agent is running.</span></span>
    
4. <span data-ttu-id="763e7-168">Щелкните базу данных mgc правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="763e7-168">Right-click the mgc database, and then click **Properties**.</span></span>
    
5. <span data-ttu-id="763e7-169">В области **Выбор страницы** щелкните элемент **Доставка журналов транзакций**.</span><span class="sxs-lookup"><span data-stu-id="763e7-169">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
6. <span data-ttu-id="763e7-170">Установите флажок **Включить эту базу данных в качестве источника в конфигурацию доставки журналов**.</span><span class="sxs-lookup"><span data-stu-id="763e7-170">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
7. <span data-ttu-id="763e7-171">В области **Резервные копии журналов транзакций** щелкните элемент **Параметры копирования**.</span><span class="sxs-lookup"><span data-stu-id="763e7-171">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
8. <span data-ttu-id="763e7-172">В поле **Network path to the backup folder** (Сетевой путь к каталогу резервной копии) введите сетевой путь к общей папке, созданной для резервной копии журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="763e7-172">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>
    
9. <span data-ttu-id="763e7-p117">Если резервная папка находится на основном сервере, введите локальный путь к этой резервной папке в поле **Если папка резервного копирования находится на сервере-источнике, укажите локальный путь к папке**. (Если резервная папка находится не на основном сервере, вы можете оставить это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="763e7-p117">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="763e7-175">Если учетная запись SQL Server на основном сервере работает под локальной системной учетной записью, необходимо создать папку резервного копирования на основном сервере и указать локальный путь к этой папке.</span><span class="sxs-lookup"><span data-stu-id="763e7-175">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
10. <span data-ttu-id="763e7-176">Настройте параметры **Удалить файлы, созданные ранее** и **Предупредить, если резервное копирование не произошло в течение**.</span><span class="sxs-lookup"><span data-stu-id="763e7-176">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
11. <span data-ttu-id="763e7-177">Просмотрите расписание резервного копирования, указанное в поле **Расписание** области **Задание резервного копирования**.</span><span class="sxs-lookup"><span data-stu-id="763e7-177">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="763e7-178">Чтобы настроить расписание установки, нажмите кнопку **"Расписание"** и SQL Server агента по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="763e7-178">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="763e7-179">Используйте те же параметры, которые применялись для основной базы данных.</span><span class="sxs-lookup"><span data-stu-id="763e7-179">Use the same settings that you used for the primary database.</span></span> 
  
12. <span data-ttu-id="763e7-180">В области **Сжатие** выберите **Использовать параметр сервера по умолчанию** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="763e7-180">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>
    
13. <span data-ttu-id="763e7-181">В области **Экземпляры сервера-получателя и базы данных** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="763e7-181">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
14. <span data-ttu-id="763e7-182">Щелкните элемент **Подключение** и подключитесь к экземпляру SQL Server, настроенному вами в качестве сервера-получателя.</span><span class="sxs-lookup"><span data-stu-id="763e7-182">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
15. <span data-ttu-id="763e7-183">В поле **База данных-получатель** выберите в списке базу данных **mgc**.</span><span class="sxs-lookup"><span data-stu-id="763e7-183">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
16. <span data-ttu-id="763e7-184">На вкладке **Инициализация базы данных-получателя** выберите параметр **Нет, база данных-получатель инициализирована**.</span><span class="sxs-lookup"><span data-stu-id="763e7-184">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>
    
17. <span data-ttu-id="763e7-p119">В поле **Папка назначения для копирования** на вкладке **Копирование файлов**  введите путь к папке, в которую следует копировать резервные копии журналов транзакций, и нажмите кнопку **ОК**. Часто эта папка расположена на сервере-получателе.</span><span class="sxs-lookup"><span data-stu-id="763e7-p119">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**. This folder is often located on the secondary server.</span></span>
    
18. <span data-ttu-id="763e7-187">Откройте раскрывающийся список **Скрипт конфигурации** и выберите **Вывести конфигурацию в новое окно запроса**.</span><span class="sxs-lookup"><span data-stu-id="763e7-187">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>
    
19. <span data-ttu-id="763e7-188">В разделе **Свойства базы данных** окна нового запроса нажмите кнопку **ОК**, чтобы начать процесс настройки.</span><span class="sxs-lookup"><span data-stu-id="763e7-188">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>
    
20. <span data-ttu-id="763e7-189">Выберите и запустите первую половину запроса (см. шаг 18) до строки: -- \* \* \* \* \* \* End: Script to be run at Primary: \* \* \* \* \* \* .</span><span class="sxs-lookup"><span data-stu-id="763e7-189">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="763e7-190">Ручной запуск этого сценария необходим, поскольку SQL Server Management Studio не поддерживает несколько основных баз данных в конфигурации SQL Server доставки журналов.</span><span class="sxs-lookup"><span data-stu-id="763e7-190">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span> 
  
21. <span data-ttu-id="763e7-191">Выберите **Отмена**, чтобы закрыть панель конфигурации доставки журналов и создать рабочую программу установки, которая правильно внедряет доставку файлов журналов как для основной, так и для зеркальной базы данных (в случае отработки отказа).</span><span class="sxs-lookup"><span data-stu-id="763e7-191">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>
    
22. <span data-ttu-id="763e7-192">Вручную вернуть основную базу данных сохраняемого чата в основную.</span><span class="sxs-lookup"><span data-stu-id="763e7-192">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="763e7-193">Для этого используется оболочка управления Skype для бизнеса Server и **cmdlet Invoke-CsDatabaseFailover.**</span><span class="sxs-lookup"><span data-stu-id="763e7-193">This is done by using the Skype for Business Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    

