---
title: 'Lync Server 2013: установка доставки журналов SQL Server между основным зеркалом и базой данных-получателем доставки журналов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database
ms:assetid: 4e8e9ce9-4301-47f2-a0c3-669afeb53295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204887(v=OCS.15)
ms:contentKeyID: 48184119
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3758e654826de42f6bf6bed8ead29ce03adb6ca5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-sql-server-log-shipping-between-the-primary-mirror-and-the-log-shipping-secondary-database-in-lync-server-2013"></a><span data-ttu-id="38214-102">Установка доставки журналов SQL Server между основным зеркалом и базой данных-получателем доставки журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38214-102">Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38214-103">_**Тема последнего изменения:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="38214-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="38214-104">Выполните указанные ниже действия, чтобы доставка журналов продолжала, если база данных основного сохраняемого чата не перемещается в зеркальную базу данных.</span><span class="sxs-lookup"><span data-stu-id="38214-104">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>

1.  <span data-ttu-id="38214-105">Ручной переход на зеркальную базу данных основного сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="38214-105">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="38214-106">Это можно сделать с помощью командной консоли Lync Server Management Shell и командлет **Invoke-ксдатабасефаиловер** .</span><span class="sxs-lookup"><span data-stu-id="38214-106">This is done by using the Lync Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span> <span data-ttu-id="38214-107">Дополнительные сведения можно найти в разделе "использование командлетов командной консоли Lync Server" в [развертывании SQL Server для обеспечения высокой доступности серверной части Lync server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="38214-107">For details, see "Using Lync Server Management Shell Cmdlets" in [Deploying SQL mirroring for Back End Server high availability in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span></span>

2.  <span data-ttu-id="38214-108">Используя SQL Server Management Studio, подключитесь к экземпляру основного сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="38214-108">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>

3.  <span data-ttu-id="38214-109">Убедитесь, что агент SQL Server запущен.</span><span class="sxs-lookup"><span data-stu-id="38214-109">Be sure that the SQL Server Agent is running.</span></span>

4.  <span data-ttu-id="38214-110">Щелкните базу данных mgc правой кнопкой мыши и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="38214-110">Right-click the mgc database, and then click **Properties**.</span></span>

5.  <span data-ttu-id="38214-111">В области **Выбор страницы** выберите **Доставка журналов транзакций**.</span><span class="sxs-lookup"><span data-stu-id="38214-111">Under **Select a page**, click **Transaction Log Shipping**.</span></span>

6.  <span data-ttu-id="38214-112">Установите флажок **Включить эту базу данных в качестве источника в конфигурацию доставки журналов**.</span><span class="sxs-lookup"><span data-stu-id="38214-112">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>

7.  <span data-ttu-id="38214-113">В области **Резервные копии журналов транзакций** щелкните элемент **Параметры копирования**.</span><span class="sxs-lookup"><span data-stu-id="38214-113">Under **Transaction log backups**, click **Backup Settings**.</span></span>

8.  <span data-ttu-id="38214-114">В поле **Сетевой путь к каталогу резервной копии** введите сетевой путь к общей папке, созданной для резервной копии журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="38214-114">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>

9.  <span data-ttu-id="38214-p102">Если резервная папка находится на основном сервере, введите локальный путь к этой резервной папке в поле **Если папка резервного копирования находится на сервере-источнике, укажите локальный путь к папке**. (Если резервная папка находится не на основном сервере, вы можете оставить это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="38214-p102">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="38214-117">Если учетная запись службы SQL Server на сервере-источнике работает под учетной записью локальной системы, необходимо создать ее на сервере-источнике и указать локальный путь к этой папке.</span><span class="sxs-lookup"><span data-stu-id="38214-117">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span>

    
    </div>

10. <span data-ttu-id="38214-118">Настройте параметры **Удалить файлы, созданные ранее** и **Предупредить, если резервное копирование не произошло в течение**.</span><span class="sxs-lookup"><span data-stu-id="38214-118">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>

11. <span data-ttu-id="38214-119">Просмотрите расписание резервного копирования, приведенное в поле **Расписание** в разделе **Задание резервного копирования**.</span><span class="sxs-lookup"><span data-stu-id="38214-119">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="38214-120">Чтобы настроить расписание установки, нажмите кнопку **Расписание**и настройте расписание агента SQL Server по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="38214-120">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="38214-121">Используйте те же параметры, которые применялись для основной базы данных.</span><span class="sxs-lookup"><span data-stu-id="38214-121">Use the same settings that you used for the primary database.</span></span>

    
    </div>

12. <span data-ttu-id="38214-122">В области **Сжатие** выберите **Использовать параметр сервера по умолчанию** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="38214-122">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>

13. <span data-ttu-id="38214-123">В области **Экземпляры сервера-получателя и базы данных** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="38214-123">Under **Secondary server instances and databases**, click **Add**.</span></span>

14. <span data-ttu-id="38214-124">Щелкните элемент **Подключение** и подключитесь к экземпляру SQL Server, настроенному вами в качестве сервера-получателя.</span><span class="sxs-lookup"><span data-stu-id="38214-124">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>

15. <span data-ttu-id="38214-125">В поле **База данных-получатель** выберите в списке базу данных **mgc**.</span><span class="sxs-lookup"><span data-stu-id="38214-125">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>

16. <span data-ttu-id="38214-126">На вкладке **Инициализация базы данных-получателя** выберите вариант **Нет, база данных-получатель инициализирована**.</span><span class="sxs-lookup"><span data-stu-id="38214-126">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>

17. <span data-ttu-id="38214-p104">В поле **Папка назначения для копирования** на вкладке **Копирование файлов** введите путь к папке, в которую следует копировать резервные копии журналов транзакций, и нажмите кнопку **ОК**. Часто эта папка расположена на сервере-получателе.</span><span class="sxs-lookup"><span data-stu-id="38214-p104">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**. This folder is often located on the secondary server.</span></span>

18. <span data-ttu-id="38214-129">Откройте раскрывающийся список **Скрипт конфигурации** и выберите **Вывести конфигурацию в новое окно запроса**.</span><span class="sxs-lookup"><span data-stu-id="38214-129">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>

19. <span data-ttu-id="38214-130">В разделе **Свойства базы данных** окна нового запроса нажмите кнопку **ОК**, чтобы начать процесс настройки.</span><span class="sxs-lookup"><span data-stu-id="38214-130">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>

20. <span data-ttu-id="38214-131">Выберите и запустите первую половину запроса (см. шаг 18) до строки:-- \* \* \* \* \* \* End: сценарий для выполнения \* \* \* \* \* \*на основном уровне:.</span><span class="sxs-lookup"><span data-stu-id="38214-131">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="38214-132">Ручной запуск этого сценария необходим, так как SQL Server Management Studio не поддерживает несколько баз данных-источника в конфигурации доставки журналов SQL Server.</span><span class="sxs-lookup"><span data-stu-id="38214-132">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span>

    
    </div>

21. <span data-ttu-id="38214-133">Выберите **Отмена**, чтобы закрыть панель конфигурации доставки журналов и создать рабочую программу установки, которая правильно внедряет доставку файлов журналов как для основной, так и для зеркальной базы данных (в случае отработки отказа). </span><span class="sxs-lookup"><span data-stu-id="38214-133">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>

22. <span data-ttu-id="38214-134">Вручную не удается вернуть основную базу данных в основное окно чата.</span><span class="sxs-lookup"><span data-stu-id="38214-134">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="38214-135">Это можно сделать с помощью командной консоли Lync Server Management Shell и командлет **Invoke-ксдатабасефаиловер** .</span><span class="sxs-lookup"><span data-stu-id="38214-135">This is done by using the Lync Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span> <span data-ttu-id="38214-136">Дополнительные сведения можно найти в разделе "использование командлетов командной консоли Lync Server" в [развертывании SQL Server для обеспечения высокой доступности серверной части Lync server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="38214-136">For details, see "Using Lync Server Management Shell Cmdlets" in [Deploying SQL mirroring for Back End Server high availability in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="38214-137">См. также</span><span class="sxs-lookup"><span data-stu-id="38214-137">See Also</span></span>


[<span data-ttu-id="38214-138">Развертывание зеркального отображения SQL Server для обеспечения высокой доступности внутреннего сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38214-138">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
[<span data-ttu-id="38214-139">Развертывание зеркального отображения SQL Server для обеспечения высокой доступности внутреннего сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38214-139">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

