---
title: Настройка высокой доступности и аварийного восстановления для сервера сохраняемого чата в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 'Сводка: Сведения в этой статье описывается настройка высокой доступности и аварийного восстановления для сервера сохраняемого чата в Скайп для Business Server 2015.'
ms.openlocfilehash: ccdaefe4c040cc75f16ebe054864c65046f89325
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894517"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="ed16a-103">Настройка высокой доступности и аварийного восстановления для сервера сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="ed16a-103">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ed16a-104">**Сводка:** В данном разделе приведены в этой статье описывается настройка высокой доступности и аварийного восстановления для сервера сохраняемого чата в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ed16a-104">**Summary:** Read this topic to learn how to configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="ed16a-105">Скайп для Business Server поддерживает несколько режимов обеспечения высокой доступности для вашей внутренними серверами, включая зеркальное отображение базы данных.</span><span class="sxs-lookup"><span data-stu-id="ed16a-105">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="ed16a-106">Дополнительные сведения см. в статье [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="ed16a-106">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ed16a-107">Группы обеспечения доступности AlwaysOn с серверов сохраняемого сеанса беседы не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="ed16a-107">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 

> [!NOTE] 
> <span data-ttu-id="ed16a-108">Сохраняемый чат доступна в Скайп для Business Server 2015, но больше не поддерживается в Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ed16a-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="ed16a-109">Те же функциональные возможности доступны в группах.</span><span class="sxs-lookup"><span data-stu-id="ed16a-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="ed16a-110">Для получения дополнительных сведений см [Реализация из Скайп для бизнеса для групп Майкрософт](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="ed16a-110">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="ed16a-111">Если необходимо использовать сохраняемого чата, возможны либо перенос пользователей, которым требуется эта функция групп, или для дальнейшего использования Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ed16a-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="ed16a-112">Перед настройкой развертывания Persistent Chat для обеспечения высокой доступности и аварийного восстановления, убедитесь, что вы знакомы с понятиями в [Планирование высокой доступности и аварийного восстановления для сервера сохраняемого чата в Скайп для Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="ed16a-112">Before you configure your Persistent Chat deployment for high availability and disaster recovery, be sure you are familiar with the concepts in [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="ed16a-113">Решение аварийного восстановления для сервера сохраняемого чата описаны в следующих разделах построена на вытянутый пул серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="ed16a-113">The disaster recovery solution for Persistent Chat Server described in these topics is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="ed16a-114">Планирования содержимого описание требований к ресурсам и топология растянутый пул, который позволяет высокой доступности и аварийного восстановления для сервера сохраняемого чата, включая использование зеркального отображения SQL Server для обеспечения высокой доступности и доставки журналов SQL Server аварийное восстановление.</span><span class="sxs-lookup"><span data-stu-id="ed16a-114">The planning content describes resource requirements, and the stretched pool topology that enables high availability and disaster recovery for Persistent Chat Server, including using SQL Server mirroring for high availability and SQL Server log shipping for disaster recovery.</span></span>
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a><span data-ttu-id="ed16a-115">Использование построителя топологий для настройки высокой доступности и аварийного восстановления</span><span class="sxs-lookup"><span data-stu-id="ed16a-115">Use Topology Builder to configure high availability and disaster recovery</span></span>

<span data-ttu-id="ed16a-116">В построителе топологий выполните указанные ниже действия, чтобы настроить высокую доступность и аварийное восстановление для сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="ed16a-116">Within Topology Builder, perform the following steps to configure high availability and disaster recovery for Persistent Chat Server.</span></span>
  
1. <span data-ttu-id="ed16a-117">Добавьте зеркальные базы данных и журнала доставки дополнительной базы данных хранилища SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ed16a-117">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>
    
2. <span data-ttu-id="ed16a-118">Измените свойства службы сервера сохраняемого чата в:</span><span class="sxs-lookup"><span data-stu-id="ed16a-118">Edit the Persistent Chat Server service properties to:</span></span>
    
    <span data-ttu-id="ed16a-119">a)</span><span class="sxs-lookup"><span data-stu-id="ed16a-119">a.</span></span> <span data-ttu-id="ed16a-120">Включите зеркальное отображение для базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="ed16a-120">Enable mirroring for the primary database.</span></span>
    
    <span data-ttu-id="ed16a-121">б)</span><span class="sxs-lookup"><span data-stu-id="ed16a-121">b.</span></span> <span data-ttu-id="ed16a-122">Добавьте основное зеркальное хранилище SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ed16a-122">Add the primary mirror SQL Server store.</span></span>
    
    <span data-ttu-id="ed16a-123">в.</span><span class="sxs-lookup"><span data-stu-id="ed16a-123">c.</span></span> <span data-ttu-id="ed16a-124">Настройка базы данных доставки журналов SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ed16a-124">Enable the SQL Server Log Shipping database.</span></span>
    
    <span data-ttu-id="ed16a-125">г.</span><span class="sxs-lookup"><span data-stu-id="ed16a-125">d.</span></span> <span data-ttu-id="ed16a-126">Добавление хранилища доставки журналов SQL Server дополнительного сервера SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ed16a-126">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    <span data-ttu-id="ed16a-127">e.</span><span class="sxs-lookup"><span data-stu-id="ed16a-127">e.</span></span> <span data-ttu-id="ed16a-128">Добавьте зеркало хранилища SQL Server для базы данных-получателя.</span><span class="sxs-lookup"><span data-stu-id="ed16a-128">Add the SQL Server store mirror for the secondary database.</span></span>
    
    <span data-ttu-id="ed16a-129">f.</span><span class="sxs-lookup"><span data-stu-id="ed16a-129">f.</span></span> <span data-ttu-id="ed16a-130">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="ed16a-130">Publish the topology.</span></span>
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="ed16a-131">Настройка доставки журналов SQL Server для основной базы данных сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="ed16a-131">Set up SQL Server log shipping for the Persistent Chat Server primary database</span></span>

<span data-ttu-id="ed16a-132">С помощью SQL Server Management Studio, подключиться к сервера сохраняемого чата экземпляру доставки журналов базы данных и убедитесь, что запущен агент SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ed16a-132">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span> <span data-ttu-id="ed16a-133">Затем подключитесь к экземпляру основной базы данных Persistent Chat и выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ed16a-133">Then connect to the Persistent Chat primary database instance and perform the following steps:</span></span>
  
1. <span data-ttu-id="ed16a-134">Щелкните базу данных mgc правой кнопкой мыши и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="ed16a-134">Right-click the mgc database, and then click **Properties**.</span></span>
    
2. <span data-ttu-id="ed16a-135">В области **Выбор страницы** выберите **Доставка журналов транзакций**.</span><span class="sxs-lookup"><span data-stu-id="ed16a-135">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
3. <span data-ttu-id="ed16a-136">Установите флажок **Включить эту базу данных в качестве источника в конфигурацию доставки журналов**.</span><span class="sxs-lookup"><span data-stu-id="ed16a-136">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
4. <span data-ttu-id="ed16a-137">В области **Резервные копии журналов транзакций** щелкните элемент **Параметры копирования**.</span><span class="sxs-lookup"><span data-stu-id="ed16a-137">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
5. <span data-ttu-id="ed16a-138">В поле **Сетевой путь к каталогу резервной копии** введите сетевой путь к общей папке, созданной для резервных копий журналов транзакций.</span><span class="sxs-lookup"><span data-stu-id="ed16a-138">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>
    
6. <span data-ttu-id="ed16a-p111">Если папка резервного копирования располагается на основном сервере, введите локальный путь к папке резервного копирования в поле **Если папка резервного копирования находится на сервере-источнике, укажите локальный путь к папке (пример: c:\backup)**. (Если папка резервного копирования находится не на основном сервере, это поле можно оставить пустым.)</span><span class="sxs-lookup"><span data-stu-id="ed16a-p111">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\backup)** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ed16a-141">Если учетная запись службы SQL Server на сервере-источнике выполняется от имени учетной записи локальной системы, необходимо создать папку резервного копирования на сервере-источнике и указать локальный путь к этой папке.</span><span class="sxs-lookup"><span data-stu-id="ed16a-141">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
7. <span data-ttu-id="ed16a-142">Настройте параметры **Удалить файлы, созданные ранее** и **Предупредить, если резервное копирование не произошло в течение**.</span><span class="sxs-lookup"><span data-stu-id="ed16a-142">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
8. <span data-ttu-id="ed16a-143">Просмотрите расписание резервного копирования, приведенное в поле **Расписание** в разделе **Задание резервного копирования**.</span><span class="sxs-lookup"><span data-stu-id="ed16a-143">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="ed16a-144">Чтобы настроить расписание для установки, нажмите кнопку **расписание**и настройте расписание агента SQL Server при необходимости.</span><span class="sxs-lookup"><span data-stu-id="ed16a-144">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>
    
9. <span data-ttu-id="ed16a-145">В разделе **Сжатие** выберите флажок **Использовать параметр сервера по умолчанию** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ed16a-145">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>
    
10. <span data-ttu-id="ed16a-146">В области **Экземпляры сервера-получателя и базы данных** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="ed16a-146">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
11. <span data-ttu-id="ed16a-147">Нажмите кнопку **Подключить** и подключитесь к экземпляру SQL Server, которая была выбрана в качестве сервера-получателя.</span><span class="sxs-lookup"><span data-stu-id="ed16a-147">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
12. <span data-ttu-id="ed16a-148">В поле **База данных-получатель** выберите в списке базу данных **mgc**.</span><span class="sxs-lookup"><span data-stu-id="ed16a-148">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
13. <span data-ttu-id="ed16a-149">На вкладке **Инициализация базы данных-получателя** выберите вариант **Да**, создайте полную резервную копию базы данных-источника и выполните восстановление из нее в базу данных-получатель (и создайте базу данных-получатель, если она не существует).</span><span class="sxs-lookup"><span data-stu-id="ed16a-149">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>
    
14. <span data-ttu-id="ed16a-p113">На вкладке **Копирование файлов** в поле **Папка назначения для копирования файлов** введите путь к папке, в которую необходимо копировать резервные копии журналов транзакций. Эта папка часто находится на дополнительном сервере.</span><span class="sxs-lookup"><span data-stu-id="ed16a-p113">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied. This folder is often located on the secondary server.</span></span>
    
15. <span data-ttu-id="ed16a-152">Обратите внимание на расписание копирования, приведенное в поле **Расписание** в разделе **Задание копирования**.</span><span class="sxs-lookup"><span data-stu-id="ed16a-152">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="ed16a-153">Чтобы настроить расписание для установки, нажмите кнопку **расписание**и настройте расписание агента SQL Server при необходимости.</span><span class="sxs-lookup"><span data-stu-id="ed16a-153">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="ed16a-154">Это расписание должно приблизительно совпадать с расписанием резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="ed16a-154">This schedule should be approximately the same as the backup schedule.</span></span>
    
16. <span data-ttu-id="ed16a-155">На вкладке **Восстановление** в разделе **Папка назначения для копирования файлов** выберите вариант **Режим без восстановления**.</span><span class="sxs-lookup"><span data-stu-id="ed16a-155">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>
    
17. <span data-ttu-id="ed16a-156">В списке **Отложить восстановление резервных копий по крайней мере на** выберите значение **0 минут**.</span><span class="sxs-lookup"><span data-stu-id="ed16a-156">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>
    
18. <span data-ttu-id="ed16a-157">В поле **Предупреждение, если восстановление не выполнено в течение** выберите порог оповещений.</span><span class="sxs-lookup"><span data-stu-id="ed16a-157">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>
    
19. <span data-ttu-id="ed16a-158">Просмотрите расписание восстановления в поле **Расписание** в разделе **Задание восстановления**.</span><span class="sxs-lookup"><span data-stu-id="ed16a-158">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="ed16a-159">Чтобы настроить расписание для установки, нажмите кнопку **расписание**, измените его агента SQL Server при необходимости и нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="ed16a-159">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="ed16a-160">Это расписание должно приблизительно совпадать с расписанием резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="ed16a-160">This schedule should be approximately the same as the backup schedule.</span></span>
    
20. <span data-ttu-id="ed16a-161">В диалоговом окне **Свойства базы данных** нажмите кнопку **ОК**, чтобы приступить к настройке.</span><span class="sxs-lookup"><span data-stu-id="ed16a-161">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a><span data-ttu-id="ed16a-162">Настройка доставки журналов SQL Server между основным зеркалом и дополнительной базой данных</span><span class="sxs-lookup"><span data-stu-id="ed16a-162">Set up SQL Server log shipping between the primary mirror and the secondary database</span></span>

<span data-ttu-id="ed16a-163">Выполните следующие действия для доставки журналов для продолжения, если основной базы данных Persistent Chat отработка отказа для ее зеркальную базу данных.</span><span class="sxs-lookup"><span data-stu-id="ed16a-163">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>
  
1. <span data-ttu-id="ed16a-164">Ручное переключение Persistent Chat базы данных-источника с зеркальным сервером.</span><span class="sxs-lookup"><span data-stu-id="ed16a-164">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="ed16a-165">Это делается с помощью Скайп для консоли Business Server и командлет **Invoke-CsDatabaseFailover** .</span><span class="sxs-lookup"><span data-stu-id="ed16a-165">This is done by using the Skype for Business Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    
2. <span data-ttu-id="ed16a-166">С помощью SQL Server Management Studio, подключитесь к основной экземпляр зеркального сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="ed16a-166">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>
    
3. <span data-ttu-id="ed16a-167">Убедитесь, что запущен агент SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ed16a-167">Be sure that the SQL Server Agent is running.</span></span>
    
4. <span data-ttu-id="ed16a-168">Щелкните базу данных mgc правой кнопкой мыши и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="ed16a-168">Right-click the mgc database, and then click **Properties**.</span></span>
    
5. <span data-ttu-id="ed16a-169">В области **Выбор страницы** выберите **Доставка журналов транзакций**.</span><span class="sxs-lookup"><span data-stu-id="ed16a-169">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
6. <span data-ttu-id="ed16a-170">Установите флажок **Включить эту базу данных в качестве источника в конфигурацию доставки журналов**.</span><span class="sxs-lookup"><span data-stu-id="ed16a-170">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
7. <span data-ttu-id="ed16a-171">В области **Резервные копии журналов транзакций** щелкните элемент **Параметры копирования**.</span><span class="sxs-lookup"><span data-stu-id="ed16a-171">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
8. <span data-ttu-id="ed16a-172">В поле **Сетевой путь к каталогу резервной копии** введите сетевой путь к общей папке, созданной для резервной копии журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="ed16a-172">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>
    
9. <span data-ttu-id="ed16a-p117">Если резервная папка находится на основном сервере, введите локальный путь к этой резервной папке в поле **Если папка резервного копирования находится на сервере-источнике, укажите локальный путь к папке**. (Если резервная папка находится не на основном сервере, вы можете оставить это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="ed16a-p117">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ed16a-175">Если учетная запись службы SQL Server на сервере-источнике выполняется от имени учетной записи локальной системы, необходимо создать папку резервного копирования на сервере-источнике и указать локальный путь к этой папке.</span><span class="sxs-lookup"><span data-stu-id="ed16a-175">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
10. <span data-ttu-id="ed16a-176">Настройте параметры **Удалить файлы, созданные ранее** и **Предупредить, если резервное копирование не произошло в течение**.</span><span class="sxs-lookup"><span data-stu-id="ed16a-176">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
11. <span data-ttu-id="ed16a-177">Просмотрите расписание резервного копирования, приведенное в поле **Расписание** в разделе **Задание резервного копирования**.</span><span class="sxs-lookup"><span data-stu-id="ed16a-177">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="ed16a-178">Чтобы настроить расписание для установки, нажмите кнопку **расписание**и измените его агента SQL Server при необходимости.</span><span class="sxs-lookup"><span data-stu-id="ed16a-178">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ed16a-179">Используйте те же параметры, которые применялись для основной базы данных.</span><span class="sxs-lookup"><span data-stu-id="ed16a-179">Use the same settings that you used for the primary database.</span></span> 
  
12. <span data-ttu-id="ed16a-180">В области **Сжатие** выберите **Использовать параметр сервера по умолчанию** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ed16a-180">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>
    
13. <span data-ttu-id="ed16a-181">В области **Экземпляры сервера-получателя и базы данных** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="ed16a-181">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
14. <span data-ttu-id="ed16a-182">Щелкните элемент **Подключение** и подключитесь к экземпляру SQL Server, настроенному вами в качестве сервера-получателя.</span><span class="sxs-lookup"><span data-stu-id="ed16a-182">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
15. <span data-ttu-id="ed16a-183">В поле **База данных-получатель** выберите в списке базу данных **mgc**.</span><span class="sxs-lookup"><span data-stu-id="ed16a-183">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
16. <span data-ttu-id="ed16a-184">На вкладке **Инициализация базы данных-получателя** выберите вариант **Нет, база данных-получатель инициализирована**.</span><span class="sxs-lookup"><span data-stu-id="ed16a-184">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>
    
17. <span data-ttu-id="ed16a-p119">В поле **Папка назначения для копирования** на вкладке **Копирование файлов** введите путь к папке, в которую следует копировать резервные копии журналов транзакций, и нажмите кнопку **ОК**. Часто эта папка расположена на сервере-получателе.</span><span class="sxs-lookup"><span data-stu-id="ed16a-p119">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**. This folder is often located on the secondary server.</span></span>
    
18. <span data-ttu-id="ed16a-187">Откройте раскрывающийся список **Скрипт конфигурации** и выберите **Вывести конфигурацию в новое окно запроса**.</span><span class="sxs-lookup"><span data-stu-id="ed16a-187">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>
    
19. <span data-ttu-id="ed16a-188">В разделе **Свойства базы данных** окна нового запроса нажмите кнопку **ОК**, чтобы начать процесс настройки.</span><span class="sxs-lookup"><span data-stu-id="ed16a-188">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>
    
20. <span data-ttu-id="ed16a-189">Выберите и запустите первая часть запроса (см. шаг 18) вверх на строку:-- \* \* \* \* \* \* конец: сценарий для запуска на источнике: \* \* \* \* \* \*.</span><span class="sxs-lookup"><span data-stu-id="ed16a-189">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ed16a-190">Ручное выполнение этого скрипта является обязательным, поскольку SQL Server Management Studio не поддерживает несколько основных баз данных в конфигурации доставки журналов SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ed16a-190">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span> 
  
21. <span data-ttu-id="ed16a-191">Выберите **Отмена**, чтобы закрыть панель конфигурации доставки журналов и создать рабочую программу установки, которая правильно внедряет доставку файлов журналов как для основной, так и для зеркальной базы данных (в случае отработки отказа). </span><span class="sxs-lookup"><span data-stu-id="ed16a-191">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>
    
22. <span data-ttu-id="ed16a-192">Сохраняемый чат базы данных-источника на основную сбоя вручную.</span><span class="sxs-lookup"><span data-stu-id="ed16a-192">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="ed16a-193">Это делается с помощью Скайп для консоли Business Server и командлет **Invoke-CsDatabaseFailover** .</span><span class="sxs-lookup"><span data-stu-id="ed16a-193">This is done by using the Skype for Business Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    

