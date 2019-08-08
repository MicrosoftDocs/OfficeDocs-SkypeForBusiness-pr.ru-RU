---
title: Настройка высокой доступности и аварийного восстановления для сервера сохраняемого чата в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 'Аннотация: Ознакомьтесь с этой статьей, чтобы научиться настраивать постоянный доступ и восстановление после аварии для постоянного сервера чата в Skype для бизнеса Server 2015.'
ms.openlocfilehash: cfc2843ceb3afba4813cc729856dcd35a4a6439e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240120"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="721bd-103">Настройка высокой доступности и аварийного восстановления для сервера сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="721bd-103">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="721bd-104">**Сводка:** В этой статье приведены сведения о том, как настроить высокую доступность и аварийное восстановление для постоянного сервера чата в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="721bd-104">**Summary:** Read this topic to learn how to configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="721bd-105">Skype для бизнеса Server поддерживает различные режимы высокой доступности серверных серверов, в том числе для зеркального отображения баз данных.</span><span class="sxs-lookup"><span data-stu-id="721bd-105">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="721bd-106">Дополнительные сведения см. в статье [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="721bd-106">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="721bd-107">Группы доступности AlwaysOn не поддерживаются на серверах сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="721bd-107">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="721bd-108">Перед настройкой развертывания сохраняемого чата для обеспечения высокой доступности и аварийного восстановления убедитесь, что вы знакомы с концепциями в [плане обеспечения высокой доступности и аварийного восстановления для постоянного сервера чата в Skype для бизнеса Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="721bd-108">Before you configure your Persistent Chat deployment for high availability and disaster recovery, be sure you are familiar with the concepts in [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="721bd-109">Решение для аварийного восстановления для сервера сохраняемого чата, описанное в этих статьях, построено на разтянутом пуле серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="721bd-109">The disaster recovery solution for Persistent Chat Server described in these topics is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="721bd-110">Материалы по планированию описывают требования к ресурсам и топологию растянутого пула, которая обеспечивает высокую доступность и аварийное восстановление для постоянного сервера чата, в том числе использование зеркального отображения SQL Server для обеспечения высокой доступности и доставки журналов SQL Server для Аварийное восстановление.</span><span class="sxs-lookup"><span data-stu-id="721bd-110">The planning content describes resource requirements, and the stretched pool topology that enables high availability and disaster recovery for Persistent Chat Server, including using SQL Server mirroring for high availability and SQL Server log shipping for disaster recovery.</span></span>
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a><span data-ttu-id="721bd-111">Использование построителя топологий для настройки высокой доступности и аварийного восстановления</span><span class="sxs-lookup"><span data-stu-id="721bd-111">Use Topology Builder to configure high availability and disaster recovery</span></span>

<span data-ttu-id="721bd-112">В построителе топологий выполните указанные ниже действия, чтобы настроить высокую доступность и аварийное восстановление для сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="721bd-112">Within Topology Builder, perform the following steps to configure high availability and disaster recovery for Persistent Chat Server.</span></span>
  
1. <span data-ttu-id="721bd-113">Добавьте зеркальные базы данных и хранилище журналов SQL Server, которые являются получателями.</span><span class="sxs-lookup"><span data-stu-id="721bd-113">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>
    
2. <span data-ttu-id="721bd-114">Измените параметры службы сервера для сохраняемого чата следующим образом:</span><span class="sxs-lookup"><span data-stu-id="721bd-114">Edit the Persistent Chat Server service properties to:</span></span>
    
    <span data-ttu-id="721bd-115">a)</span><span class="sxs-lookup"><span data-stu-id="721bd-115">a.</span></span> <span data-ttu-id="721bd-116">Включите зеркальное отображение для базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="721bd-116">Enable mirroring for the primary database.</span></span>
    
    <span data-ttu-id="721bd-117">б)</span><span class="sxs-lookup"><span data-stu-id="721bd-117">b.</span></span> <span data-ttu-id="721bd-118">Добавьте основное зеркальное хранилище SQL Server.</span><span class="sxs-lookup"><span data-stu-id="721bd-118">Add the primary mirror SQL Server store.</span></span>
    
    <span data-ttu-id="721bd-119">в.</span><span class="sxs-lookup"><span data-stu-id="721bd-119">c.</span></span> <span data-ttu-id="721bd-120">Включите базу данных доставки журналов SQL Server.</span><span class="sxs-lookup"><span data-stu-id="721bd-120">Enable the SQL Server Log Shipping database.</span></span>
    
    <span data-ttu-id="721bd-121">г.</span><span class="sxs-lookup"><span data-stu-id="721bd-121">d.</span></span> <span data-ttu-id="721bd-122">Добавьте хранилище журналов SQL Server с дополнительной доставкой.</span><span class="sxs-lookup"><span data-stu-id="721bd-122">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    <span data-ttu-id="721bd-123">учеб.</span><span class="sxs-lookup"><span data-stu-id="721bd-123">e.</span></span> <span data-ttu-id="721bd-124">Добавьте зеркало хранилища SQL Server для базы данных получателя.</span><span class="sxs-lookup"><span data-stu-id="721bd-124">Add the SQL Server store mirror for the secondary database.</span></span>
    
    <span data-ttu-id="721bd-125">н.</span><span class="sxs-lookup"><span data-stu-id="721bd-125">f.</span></span> <span data-ttu-id="721bd-126">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="721bd-126">Publish the topology.</span></span>
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="721bd-127">Настройка доставки журналов SQL Server для основной базы данных сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="721bd-127">Set up SQL Server log shipping for the Persistent Chat Server primary database</span></span>

<span data-ttu-id="721bd-128">Используя SQL Server Management Studio, подключитесь к дополнительному экземпляру базы данных доставки журналов сервера чатов и убедитесь, что агент SQL Server запущен.</span><span class="sxs-lookup"><span data-stu-id="721bd-128">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span> <span data-ttu-id="721bd-129">Затем подключитесь к экземпляру базы данных сохраняемого чата и выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="721bd-129">Then connect to the Persistent Chat primary database instance and perform the following steps:</span></span>
  
1. <span data-ttu-id="721bd-130">Щелкните базу данных mgc правой кнопкой мыши и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="721bd-130">Right-click the mgc database, and then click **Properties**.</span></span>
    
2. <span data-ttu-id="721bd-131">В области **Выбор страницы** выберите **Доставка журналов транзакций**.</span><span class="sxs-lookup"><span data-stu-id="721bd-131">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
3. <span data-ttu-id="721bd-132">Установите флажок **Включить эту базу данных в качестве источника в конфигурацию доставки журналов**.</span><span class="sxs-lookup"><span data-stu-id="721bd-132">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
4. <span data-ttu-id="721bd-133">В области **Резервные копии журналов транзакций** щелкните элемент **Параметры копирования**.</span><span class="sxs-lookup"><span data-stu-id="721bd-133">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
5. <span data-ttu-id="721bd-134">В поле **Сетевой путь к каталогу резервной копии** введите сетевой путь к общей папке, созданной для резервных копий журналов транзакций.</span><span class="sxs-lookup"><span data-stu-id="721bd-134">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>
    
6. <span data-ttu-id="721bd-p110">Если папка резервного копирования располагается на основном сервере, введите локальный путь к папке резервного копирования в поле **Если папка резервного копирования находится на сервере-источнике, укажите локальный путь к папке (пример: c:\backup)**. (Если папка резервного копирования находится не на основном сервере, это поле можно оставить пустым.)</span><span class="sxs-lookup"><span data-stu-id="721bd-p110">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\backup)** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="721bd-137">Если учетная запись службы SQL Server на сервере-источнике работает под учетной записью локальной системы, необходимо создать ее на сервере-источнике и указать локальный путь к этой папке.</span><span class="sxs-lookup"><span data-stu-id="721bd-137">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
7. <span data-ttu-id="721bd-138">Настройте параметры **Удалить файлы, созданные ранее** и **Предупредить, если резервное копирование не произошло в течение**.</span><span class="sxs-lookup"><span data-stu-id="721bd-138">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
8. <span data-ttu-id="721bd-139">Просмотрите расписание резервного копирования, приведенное в поле **Расписание** в разделе **Задание резервного копирования**.</span><span class="sxs-lookup"><span data-stu-id="721bd-139">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="721bd-140">Чтобы настроить расписание установки, нажмите кнопку **Расписание**и настройте расписание агента SQL Server в соответствии с требованиями.</span><span class="sxs-lookup"><span data-stu-id="721bd-140">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>
    
9. <span data-ttu-id="721bd-141">В разделе **Сжатие** выберите флажок **Использовать параметр сервера по умолчанию** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="721bd-141">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>
    
10. <span data-ttu-id="721bd-142">В области **Экземпляры сервера-получателя и базы данных** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="721bd-142">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
11. <span data-ttu-id="721bd-143">Нажмите кнопку **подключить** и подключитесь к экземпляру SQL Server, который вы настроили как дополнительный сервер.</span><span class="sxs-lookup"><span data-stu-id="721bd-143">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
12. <span data-ttu-id="721bd-144">В поле **База данных-получатель** выберите в списке базу данных **mgc**.</span><span class="sxs-lookup"><span data-stu-id="721bd-144">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
13. <span data-ttu-id="721bd-145">На вкладке **Инициализация базы данных-получателя** выберите вариант **Да**, создайте полную резервную копию базы данных-источника и выполните восстановление из нее в базу данных-получатель (и создайте базу данных-получатель, если она не существует).</span><span class="sxs-lookup"><span data-stu-id="721bd-145">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>
    
14. <span data-ttu-id="721bd-p112">На вкладке **Копирование файлов** в поле **Папка назначения для копирования файлов** введите путь к папке, в которую необходимо копировать резервные копии журналов транзакций. Эта папка часто находится на дополнительном сервере.</span><span class="sxs-lookup"><span data-stu-id="721bd-p112">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied. This folder is often located on the secondary server.</span></span>
    
15. <span data-ttu-id="721bd-148">Обратите внимание на расписание копирования, приведенное в поле **Расписание** в разделе **Задание копирования**.</span><span class="sxs-lookup"><span data-stu-id="721bd-148">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="721bd-149">Чтобы настроить расписание установки, нажмите кнопку **Расписание**и настройте расписание агента SQL Server в соответствии с требованиями.</span><span class="sxs-lookup"><span data-stu-id="721bd-149">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="721bd-150">Это расписание должно приблизительно совпадать с расписанием резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="721bd-150">This schedule should be approximately the same as the backup schedule.</span></span>
    
16. <span data-ttu-id="721bd-151">На вкладке **Восстановление** в разделе **Папка назначения для копирования файлов** выберите вариант **Режим без восстановления**.</span><span class="sxs-lookup"><span data-stu-id="721bd-151">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>
    
17. <span data-ttu-id="721bd-152">В списке **Отложить восстановление резервных копий по крайней мере на** выберите значение **0 минут**.</span><span class="sxs-lookup"><span data-stu-id="721bd-152">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>
    
18. <span data-ttu-id="721bd-153">В поле **Предупреждение, если восстановление не выполнено в течение** выберите порог оповещений.</span><span class="sxs-lookup"><span data-stu-id="721bd-153">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>
    
19. <span data-ttu-id="721bd-154">Просмотрите расписание восстановления в поле **Расписание** в разделе **Задание восстановления**.</span><span class="sxs-lookup"><span data-stu-id="721bd-154">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="721bd-155">Чтобы настроить расписание установки, нажмите кнопку **Расписание**, настройте расписание агента SQL Server и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="721bd-155">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="721bd-156">Это расписание должно приблизительно совпадать с расписанием резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="721bd-156">This schedule should be approximately the same as the backup schedule.</span></span>
    
20. <span data-ttu-id="721bd-157">В диалоговом окне **Свойства базы данных** нажмите кнопку **ОК**, чтобы приступить к настройке.</span><span class="sxs-lookup"><span data-stu-id="721bd-157">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a><span data-ttu-id="721bd-158">Настройка доставки журналов SQL Server между основным зеркалом и дополнительной базой данных</span><span class="sxs-lookup"><span data-stu-id="721bd-158">Set up SQL Server log shipping between the primary mirror and the secondary database</span></span>

<span data-ttu-id="721bd-159">Выполните указанные ниже действия, чтобы доставка журналов продолжала, если база данных основного сохраняемого чата не перемещается в зеркальную базу данных.</span><span class="sxs-lookup"><span data-stu-id="721bd-159">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>
  
1. <span data-ttu-id="721bd-160">Ручной переход на зеркальную базу данных основного сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="721bd-160">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="721bd-161">Это можно сделать с помощью командной консоли Skype для бизнеса Server и командлет **Invoke-ксдатабасефаиловер** .</span><span class="sxs-lookup"><span data-stu-id="721bd-161">This is done by using the Skype for Business Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    
2. <span data-ttu-id="721bd-162">Используя SQL Server Management Studio, подключитесь к экземпляру основного сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="721bd-162">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>
    
3. <span data-ttu-id="721bd-163">Убедитесь, что агент SQL Server запущен.</span><span class="sxs-lookup"><span data-stu-id="721bd-163">Be sure that the SQL Server Agent is running.</span></span>
    
4. <span data-ttu-id="721bd-164">Щелкните базу данных mgc правой кнопкой мыши и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="721bd-164">Right-click the mgc database, and then click **Properties**.</span></span>
    
5. <span data-ttu-id="721bd-165">В области **Выбор страницы** выберите **Доставка журналов транзакций**.</span><span class="sxs-lookup"><span data-stu-id="721bd-165">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
6. <span data-ttu-id="721bd-166">Установите флажок **Включить эту базу данных в качестве источника в конфигурацию доставки журналов**.</span><span class="sxs-lookup"><span data-stu-id="721bd-166">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
7. <span data-ttu-id="721bd-167">В области **Резервные копии журналов транзакций** щелкните элемент **Параметры копирования**.</span><span class="sxs-lookup"><span data-stu-id="721bd-167">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
8. <span data-ttu-id="721bd-168">В поле **Сетевой путь к каталогу резервной копии** введите сетевой путь к общей папке, созданной для резервной копии журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="721bd-168">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>
    
9. <span data-ttu-id="721bd-p116">Если резервная папка находится на основном сервере, введите локальный путь к этой резервной папке в поле **Если папка резервного копирования находится на сервере-источнике, укажите локальный путь к папке**. (Если резервная папка находится не на основном сервере, вы можете оставить это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="721bd-p116">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="721bd-171">Если учетная запись службы SQL Server на сервере-источнике работает под учетной записью локальной системы, необходимо создать ее на сервере-источнике и указать локальный путь к этой папке.</span><span class="sxs-lookup"><span data-stu-id="721bd-171">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
10. <span data-ttu-id="721bd-172">Настройте параметры **Удалить файлы, созданные ранее** и **Предупредить, если резервное копирование не произошло в течение**.</span><span class="sxs-lookup"><span data-stu-id="721bd-172">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
11. <span data-ttu-id="721bd-173">Просмотрите расписание резервного копирования, приведенное в поле **Расписание** в разделе **Задание резервного копирования**.</span><span class="sxs-lookup"><span data-stu-id="721bd-173">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="721bd-174">Чтобы настроить расписание установки, нажмите кнопку **Расписание**и настройте расписание агента SQL Server по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="721bd-174">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="721bd-175">Используйте те же параметры, которые применялись для основной базы данных.</span><span class="sxs-lookup"><span data-stu-id="721bd-175">Use the same settings that you used for the primary database.</span></span> 
  
12. <span data-ttu-id="721bd-176">В области **Сжатие** выберите **Использовать параметр сервера по умолчанию** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="721bd-176">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>
    
13. <span data-ttu-id="721bd-177">В области **Экземпляры сервера-получателя и базы данных** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="721bd-177">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
14. <span data-ttu-id="721bd-178">Щелкните элемент **Подключение** и подключитесь к экземпляру SQL Server, настроенному вами в качестве сервера-получателя.</span><span class="sxs-lookup"><span data-stu-id="721bd-178">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
15. <span data-ttu-id="721bd-179">В поле **База данных-получатель** выберите в списке базу данных **mgc**.</span><span class="sxs-lookup"><span data-stu-id="721bd-179">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
16. <span data-ttu-id="721bd-180">На вкладке **Инициализация базы данных-получателя** выберите вариант **Нет, база данных-получатель инициализирована**.</span><span class="sxs-lookup"><span data-stu-id="721bd-180">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>
    
17. <span data-ttu-id="721bd-p118">В поле **Папка назначения для копирования** на вкладке **Копирование файлов** введите путь к папке, в которую следует копировать резервные копии журналов транзакций, и нажмите кнопку **ОК**. Часто эта папка расположена на сервере-получателе.</span><span class="sxs-lookup"><span data-stu-id="721bd-p118">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**. This folder is often located on the secondary server.</span></span>
    
18. <span data-ttu-id="721bd-183">Откройте раскрывающийся список **Скрипт конфигурации** и выберите **Вывести конфигурацию в новое окно запроса**.</span><span class="sxs-lookup"><span data-stu-id="721bd-183">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>
    
19. <span data-ttu-id="721bd-184">В разделе **Свойства базы данных** окна нового запроса нажмите кнопку **ОК**, чтобы начать процесс настройки.</span><span class="sxs-lookup"><span data-stu-id="721bd-184">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>
    
20. <span data-ttu-id="721bd-185">Выберите и запустите первую половину запроса (см. шаг 18) до строки:-- \* \* \* \* \* \* End: сценарий для выполнения \* \* \* \* \* \*на основном уровне:.</span><span class="sxs-lookup"><span data-stu-id="721bd-185">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="721bd-186">Ручной запуск этого сценария необходим, так как SQL Server Management Studio не поддерживает несколько баз данных-источника в конфигурации доставки журналов SQL Server.</span><span class="sxs-lookup"><span data-stu-id="721bd-186">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span> 
  
21. <span data-ttu-id="721bd-187">Выберите **Отмена**, чтобы закрыть панель конфигурации доставки журналов и создать рабочую программу установки, которая правильно внедряет доставку файлов журналов как для основной, так и для зеркальной базы данных (в случае отработки отказа). </span><span class="sxs-lookup"><span data-stu-id="721bd-187">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>
    
22. <span data-ttu-id="721bd-188">Вручную не удается вернуть основную базу данных в основное окно чата.</span><span class="sxs-lookup"><span data-stu-id="721bd-188">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="721bd-189">Это можно сделать с помощью командной консоли Skype для бизнеса Server и командлет **Invoke-ксдатабасефаиловер** .</span><span class="sxs-lookup"><span data-stu-id="721bd-189">This is done by using the Skype for Business Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    

