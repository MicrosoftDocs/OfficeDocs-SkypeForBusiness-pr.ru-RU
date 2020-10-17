---
title: 'Lync Server 2013: Настройка доставки журналов SQL Server для основной базы данных сервера сохраняемого чата'
description: 'Lync Server 2013: Настройка доставки журналов SQL Server для основной базы данных сервера сохраняемого чата.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up SQL Server Log Shipping for the Persistent Chat Server primary database
ms:assetid: 088ea1c2-d592-4a11-b3b8-f1e2f8beae93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204653(v=OCS.15)
ms:contentKeyID: 48183337
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72b7e68bd0cb7b9f544b86a15204d3e832692ec1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554265"
---
# <a name="setting-up-sql-server-log-shipping-in-lync-server-2013-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="b3023-103">Настройка доставки журналов SQL Server в Lync Server 2013 для основной базы данных сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="b3023-103">Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3023-104">_**Последнее изменение темы:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="b3023-104">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="b3023-105">С помощью SQL Server Management Studio подключитесь к дополнительному экземпляру базы данных доставки журналов сервера сохраняемого чата и убедитесь, что запущен агент SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b3023-105">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span>

<span data-ttu-id="b3023-106">С помощью SQL Server Management Studio, подключенного к основному экземпляру базы данных сохраняемого чата, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="b3023-106">Using SQL Server Management Studio connected to the Persistent Chat primary database instance, perform the following steps:</span></span>

1.  <span data-ttu-id="b3023-107">Убедитесь, что запущен агент SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b3023-107">Be sure that the SQL Server Agent is running.</span></span>

2.  <span data-ttu-id="b3023-108">Щелкните базу данных mgc правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="b3023-108">Right-click the mgc database, and then click **Properties**.</span></span>

3.  <span data-ttu-id="b3023-109">В области **Выбор страницы** щелкните элемент **Доставка журналов транзакций**.</span><span class="sxs-lookup"><span data-stu-id="b3023-109">Under **Select a page**, click **Transaction Log Shipping**.</span></span>

4.  <span data-ttu-id="b3023-110">Установите флажок **Включить эту базу данных в качестве источника в конфигурацию доставки журналов**.</span><span class="sxs-lookup"><span data-stu-id="b3023-110">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>

5.  <span data-ttu-id="b3023-111">В области **Резервные копии журналов транзакций** щелкните элемент **Параметры копирования**.</span><span class="sxs-lookup"><span data-stu-id="b3023-111">Under **Transaction log backups**, click **Backup Settings**.</span></span>

6.  <span data-ttu-id="b3023-112">В поле **сетевой путь к папке резервной копии** введите сетевой путь к общему ресурсу, созданному для папки резервных копий журналов транзакций.</span><span class="sxs-lookup"><span data-stu-id="b3023-112">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>

7.  <span data-ttu-id="b3023-113">Если папка резервного копирования расположена на основном сервере, введите локальный путь к папке резервного копирования в том **случае, если папка резервного копирования расположена на основном сервере, введите в поле Локальный путь к папке (например: c: \\ Backup)** .</span><span class="sxs-lookup"><span data-stu-id="b3023-113">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\\backup)** box.</span></span> <span data-ttu-id="b3023-114">(Если резервная папка находится не на основном сервере, вы можете оставить это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="b3023-114">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b3023-115">Если учетная запись службы SQL Server на основном сервере работает под учетной записью локальной системы, необходимо создать папку резервного копирования на основном сервере и указать локальный путь к этой папке.</span><span class="sxs-lookup"><span data-stu-id="b3023-115">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span>

    
    </div>

8.  <span data-ttu-id="b3023-116">Настройте параметры **Удалить файлы, созданные ранее** и **Предупредить, если резервное копирование не произошло в течение**.</span><span class="sxs-lookup"><span data-stu-id="b3023-116">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>

9.  <span data-ttu-id="b3023-117">Просмотрите расписание резервного копирования, указанное в поле **Расписание** области **Задание резервного копирования**.</span><span class="sxs-lookup"><span data-stu-id="b3023-117">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="b3023-118">Чтобы настроить расписание установки, нажмите кнопку **Расписание**и скорректируйте расписание агента SQL Server в соответствии с требованиями.</span><span class="sxs-lookup"><span data-stu-id="b3023-118">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>

10. <span data-ttu-id="b3023-119">В разделе **Сжатие**выберите **использовать параметр сервера по умолчанию**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b3023-119">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>

11. <span data-ttu-id="b3023-120">В области **Экземпляры сервера-получателя и базы данных** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b3023-120">Under **Secondary server instances and databases**, click **Add**.</span></span>

12. <span data-ttu-id="b3023-121">Нажмите кнопку **подключить** и подключитесь к экземпляру SQL Server, настроенному в качестве сервера вторичного сервера.</span><span class="sxs-lookup"><span data-stu-id="b3023-121">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>

13. <span data-ttu-id="b3023-122">В поле **База данных-получатель** выберите в списке базу данных **mgc**.</span><span class="sxs-lookup"><span data-stu-id="b3023-122">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>

14. <span data-ttu-id="b3023-123">На вкладке **Инициализация базы данных-получателя** выберите параметр **Да, создайте полную резервную копию базы данных-источника и восстановите ее в базу данных-получатель (и создайте базу данных-получатель, если она не существует)**.</span><span class="sxs-lookup"><span data-stu-id="b3023-123">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>

15. <span data-ttu-id="b3023-124">На вкладке **копирование файлов** в поле **Папка назначения для скопированных файлов** введите путь к папке, в которую необходимо скопировать резервные копии журналов транзакций.</span><span class="sxs-lookup"><span data-stu-id="b3023-124">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied.</span></span> <span data-ttu-id="b3023-125">Часто эта папка расположена на сервере-получателе.</span><span class="sxs-lookup"><span data-stu-id="b3023-125">This folder is often located on the secondary server.</span></span>

16. <span data-ttu-id="b3023-126">Обратите внимание на расписание копирования, указанное в поле **Расписание** в разделе **Задание копирования**.</span><span class="sxs-lookup"><span data-stu-id="b3023-126">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="b3023-127">Чтобы настроить расписание установки, нажмите кнопку **Расписание**и скорректируйте расписание агента SQL Server в соответствии с требованиями.</span><span class="sxs-lookup"><span data-stu-id="b3023-127">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="b3023-128">Это расписание должно приблизительно совпадать с расписанием резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="b3023-128">This schedule should be approximately the same as the backup schedule.</span></span>

17. <span data-ttu-id="b3023-129">На вкладке **Восстановление** в разделе **состояние базы данных при восстановлении резервных копий**выберите параметр **нет режима восстановления** .</span><span class="sxs-lookup"><span data-stu-id="b3023-129">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>

18. <span data-ttu-id="b3023-130">В разделе **Задержка восстановления резервных копий по крайней мере:** выберите **0 минут**.</span><span class="sxs-lookup"><span data-stu-id="b3023-130">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>

19. <span data-ttu-id="b3023-131">В разделе Alert (предупреждение) выберите порог оповещений, **Если восстановление не выполняется**.</span><span class="sxs-lookup"><span data-stu-id="b3023-131">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>

20. <span data-ttu-id="b3023-132">Просмотрите расписание восстановления, указанное в поле **Расписание** в разделе **Задание восстановления**.</span><span class="sxs-lookup"><span data-stu-id="b3023-132">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="b3023-133">Чтобы настроить расписание установки, нажмите кнопку **Расписание**, измените расписание агента SQL Server, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b3023-133">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="b3023-134">Это расписание должно приблизительно совпадать с расписанием резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="b3023-134">This schedule should be approximately the same as the backup schedule.</span></span>

21. <span data-ttu-id="b3023-135">В диалоговом окне **Свойства базы данных** нажмите кнопку **ОК** , чтобы начать процесс настройки.</span><span class="sxs-lookup"><span data-stu-id="b3023-135">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

