---
title: 'Lync Server 2013: установка базы данных с помощью командной консоли Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Database installation using Lync Server Management Shell
ms:assetid: c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398832(v=OCS.15)
ms:contentKeyID: 48185401
ms.date: 06/16/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: deac68fb5f20066632bc48a9e9b6244a9bd34fe9
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a><span data-ttu-id="bd001-102">Установка базы данных с помощью командной консоли Lync Server в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd001-102">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd001-103">_**Тема последнего изменения:** 2016-06-16_</span><span class="sxs-lookup"><span data-stu-id="bd001-103">_**Topic Last Modified:** 2016-06-16_</span></span>

<span data-ttu-id="bd001-104">Разделение ролей и обязанностей между администраторами сервера и администраторами SQL Server может привести к задержкам при реализации.</span><span class="sxs-lookup"><span data-stu-id="bd001-104">Separation of roles and responsibilities between server administrators and SQL Server administrators can result in delays in implementation.</span></span> <span data-ttu-id="bd001-105">Lync Server 2013 использует управление доступом на основе ролей (RBAC) для устранения этих проблем.</span><span class="sxs-lookup"><span data-stu-id="bd001-105">Lync Server 2013 uses role-based access control (RBAC) to mitigate these difficulties.</span></span> <span data-ttu-id="bd001-106">В некоторых случаях администратор SQL Server должен управлять установкой баз данных на сервере SQL Server за пределами RBAC.</span><span class="sxs-lookup"><span data-stu-id="bd001-106">In some instances, the SQL Server administrator must manage the installation of databases on the SQL Server-based server outside RBAC.</span></span> <span data-ttu-id="bd001-107">Командная консоль Lync Server 2013 позволяет администратору SQL Server выполнять командлеты Windows PowerShell, предназначенные для настройки баз данных с правильными данными и файлами журнала.</span><span class="sxs-lookup"><span data-stu-id="bd001-107">The Lync Server 2013 Management Shell provides a way for the SQL Server administrator to run Windows PowerShell cmdlets designed to configure the databases with the correct data and log files.</span></span> <span data-ttu-id="bd001-108">Дополнительные сведения можно найти [в разделе разрешения на развертывание SQL Server в Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="bd001-108">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="bd001-109">В описанной ниже процедуре предполагается, что по крайней мере на сервере Lync Server 2013 Окскоре. msi, SQL Server Native Client (sqlncli. msi) есть управляющие объекты Microsoft SQL Server 2012, типы CLR для Microsoft SQL Server 2012 и Microsoft SQL Server 2012 ADOMD.NET установлены.</span><span class="sxs-lookup"><span data-stu-id="bd001-109">The following procedure assumes that at a minimum the Lync Server 2013 OCSCore.msi, SQL Server Native Client (sqlncli.msi) Microsoft SQL Server 2012 Management Objects, CLR Types for Microsoft SQL Server 2012 and Microsoft SQL Server 2012 ADOMD.NET are installed.</span></span> <span data-ttu-id="bd001-110">Файл Окскоре. msi находится на установочном носителе в каталоге \Setup\AMD64\Setup.</span><span class="sxs-lookup"><span data-stu-id="bd001-110">The OCSCore.msi is located on the installation media in the \Setup\AMD64\Setup directory.</span></span> <span data-ttu-id="bd001-111">Остальные компоненты находятся в \Setup\amd64.</span><span class="sxs-lookup"><span data-stu-id="bd001-111">The remaining components are located in \Setup\amd64.</span></span> <span data-ttu-id="bd001-112">Кроме того, подготовка Active Directory для Lync Server 2013 успешно завершена.</span><span class="sxs-lookup"><span data-stu-id="bd001-112">Additionally, Active Directory preparation for Lync Server 2013 has been successfully completed.</span></span>



</div>

<span data-ttu-id="bd001-113">**Install-ксдатабасе** — это командлет Windows PowerShell, который вы используете для установки баз данных.</span><span class="sxs-lookup"><span data-stu-id="bd001-113">**Install-CsDatabase** is the Windows PowerShell cmdlet you use to install the databases.</span></span> <span data-ttu-id="bd001-114">Командлет **Install-ксдатабасе** имеет большое количество параметров, и только некоторые из них обсуждаются здесь.</span><span class="sxs-lookup"><span data-stu-id="bd001-114">The **Install-CsDatabase** cmdlet has a large number of parameters, only a few of which are discussed here.</span></span> <span data-ttu-id="bd001-115">Подробнее об этих параметрах можно найти в документации по командной консоли Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bd001-115">For details about the possible parameters, see the Lync Server 2013 Management Shell documentation.</span></span>

<div class=" ">


> [!WARNING]  
> <span data-ttu-id="bd001-116">Чтобы избежать проблем с производительностью и возможной задержкой, всегда используйте полные доменные имена (FQDN) при ссылке на серверы SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bd001-116">To avoid performance and possible time-out issues, always use fully qualified domain names (FQDNs) when referring to SQL Server-based servers.</span></span> <span data-ttu-id="bd001-117">Старайтесь не использовать только ссылки на имена узлов.</span><span class="sxs-lookup"><span data-stu-id="bd001-117">Avoid using host name-only references.</span></span> <span data-ttu-id="bd001-118">Например, используйте sqlbe01.contoso.net, но не используйте SQLBE01.</span><span class="sxs-lookup"><span data-stu-id="bd001-118">For example, use sqlbe01.contoso.net, but avoid using SQLBE01.</span></span>



</div>

<span data-ttu-id="bd001-119">Для установки баз данных **Установка-ксдатабасе** использует три основных метода размещения баз данных на подготовленном сервере SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bd001-119">For installing databases, **Install-CsDatabase** uses three primary methods for placing the databases onto the prepared SQL Server-based server:</span></span>

  - <span data-ttu-id="bd001-120">Запустите **Install-ксдатабасе** без Датабасепасс или уседефаултсклпас.</span><span class="sxs-lookup"><span data-stu-id="bd001-120">Run **Install-CsDatabase** without DatabasePaths or UseDefaultSqlPath.</span></span> <span data-ttu-id="bd001-121">Командлет использует встроенный алгоритм для определения наилучшего размещения журнала и файлов данных.</span><span class="sxs-lookup"><span data-stu-id="bd001-121">The cmdlet uses a built in algorithm to determine the best placement for the log and data files.</span></span> <span data-ttu-id="bd001-122">Алгоритм работает только для отдельных реализаций SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bd001-122">The algorithm only works for stand-alone SQL Server implementations.</span></span>

  - <span data-ttu-id="bd001-123">Запустите **Install-ксдатабасе** с параметром датабасепасс.</span><span class="sxs-lookup"><span data-stu-id="bd001-123">Run **Install-CsDatabase** with the DatabasePaths parameter.</span></span> <span data-ttu-id="bd001-124">Встроенный алгоритм для оптимизации расположения файлов журнала и данных не используется, если определен параметр Датабасепасс.</span><span class="sxs-lookup"><span data-stu-id="bd001-124">The built-in algorithm to optimize log and data file locations is not used if the DatabasePaths parameter is defined.</span></span> <span data-ttu-id="bd001-125">С помощью этого параметра можно задать расположение для развертывания файлов журнала и данных.</span><span class="sxs-lookup"><span data-stu-id="bd001-125">Using this parameter allows you to define the locations where log and data files will be deployed.</span></span>

  - <span data-ttu-id="bd001-126">Запустите **Install-ксдатабасе** с уседефаултсклпасс.</span><span class="sxs-lookup"><span data-stu-id="bd001-126">Run **Install-CsDatabase** with UseDefaultSqlPaths.</span></span> <span data-ttu-id="bd001-127">Этот параметр не использует встроенный алгоритм для оптимизации расположения файлов журнала и данных.</span><span class="sxs-lookup"><span data-stu-id="bd001-127">This option does not use the built-in algorithm to optimize the log and data file locations.</span></span> <span data-ttu-id="bd001-128">Файлы журнала и данных развертываются в соответствии с параметрами по умолчанию, заданными администратором SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bd001-128">Log and data file are deployed according to the defaults set by the SQL Server administrator.</span></span> <span data-ttu-id="bd001-129">Эти пути обычно устанавливаются для автоматического администрирования файлов журнала и данных на сервере SQL Server и не связаны с установкой Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bd001-129">These paths are typically set for the purpose of automatic administration of log and data files on the SQL Server in advance, and are not associated with the setup of Lync Server 2013.</span></span>

  - <span data-ttu-id="bd001-130">Параметр Датабасепасмап также можно использовать для явного задания местоположения для каждой базы данных и соответствующего файла журнала.</span><span class="sxs-lookup"><span data-stu-id="bd001-130">The DatabasePathMap parameter can also be used to explicitly specify a location for each database and its respective log file.</span></span>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a><span data-ttu-id="bd001-131">Использование командлетов Windows PowerShell для настройки хранилища SQL Server Central Management</span><span class="sxs-lookup"><span data-stu-id="bd001-131">To use Windows PowerShell cmdlets to configure the SQL Server Central Management store</span></span>

1.  <span data-ttu-id="bd001-132">На любом компьютере войдите в систему с учетными данными администратора для создания баз данных на сервере SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bd001-132">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="bd001-133">Дополнительные сведения можно найти [в разделе разрешения на развертывание SQL Server в Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="bd001-133">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

2.  <span data-ttu-id="bd001-134">Откройте консоль управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bd001-134">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="bd001-135">Если вы не настроили политику выполнения для Windows PowerShell, необходимо настроить политику, чтобы разрешить запуск сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd001-135">If you have not adjusted the execution policy for Windows PowerShell, you must adjust the policy to allow Windows PowerShell scripts to run.</span></span> <span data-ttu-id="bd001-136">Подробные сведения можно найти в [http://go.microsoft.com/fwlink/p/?linkId=203093](http://go.microsoft.com/fwlink/p/?linkid=203093)разделе Проверка политики выполнения.</span><span class="sxs-lookup"><span data-stu-id="bd001-136">For details, see “Examining the Execution Policy” at [http://go.microsoft.com/fwlink/p/?linkId=203093](http://go.microsoft.com/fwlink/p/?linkid=203093).</span></span>

3.  <span data-ttu-id="bd001-137">С помощью командлета **Install-ксдатабасе** Установите центральное хранилище управления.</span><span class="sxs-lookup"><span data-stu-id="bd001-137">Use the **Install-CsDatabase** cmdlet to install the Central Management store.</span></span>
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <fully qualified domain name of SQL Server> 
        -SqlInstanceName <named instance> -DatabasePaths <logfile path>,<database file path> 
        -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn sqlbe.contoso.net -SqlInstanceName rtc -DatabasePaths "C:\CSDB-Logs","C:\CSDB-CMS" -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="bd001-138">Параметр Report является необязательным, но он полезен, если вы собираетесь документировать процесс установки.</span><span class="sxs-lookup"><span data-stu-id="bd001-138">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

4.  <span data-ttu-id="bd001-139">**Установка-ксдатабасе – датабасепасс** может использовать до шести параметров пути, каждый из которых определяет пути к дискам, заданным в данных SQL Server и размещении файлов журнала.</span><span class="sxs-lookup"><span data-stu-id="bd001-139">**Install-CsDatabase –DatabasePaths** can use up to six path parameters, each defining the paths for the drives as defined in SQL Server Data and Log File Placement.</span></span> <span data-ttu-id="bd001-140">По логическим правилам конфигурации базы данных в Lync Server 2013 диски разбиваются на сегменты двух, четырех или шести.</span><span class="sxs-lookup"><span data-stu-id="bd001-140">By the logical rules of the database configuration in Lync Server 2013, drives are parsed out into buckets of two, four, or six.</span></span> <span data-ttu-id="bd001-141">В зависимости от конфигурации SQL Server и количества сегментов вы будете указывать два пути, четыре пути или шесть путей.</span><span class="sxs-lookup"><span data-stu-id="bd001-141">Depending on your SQL Server configuration and the number of buckets, you will supply two paths, four paths, or six paths.</span></span>
    
    <span data-ttu-id="bd001-142">Если у вас три диска, журнал получает приоритет и файлы данных распределяются после.</span><span class="sxs-lookup"><span data-stu-id="bd001-142">If you have three drives, the log gets priority and the data files are distributed after.</span></span> <span data-ttu-id="bd001-143">Пример для сервера SQL Server, настроенного на шесть дисков:</span><span class="sxs-lookup"><span data-stu-id="bd001-143">An example for a SQL Server-based server configured with six drives:</span></span>
    ```powershell
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```
5.  <span data-ttu-id="bd001-144">После завершения установки базы данных вы можете закрыть командную консоль Lync Server 2013 или перейти к установке баз данных Lync Server 2013, указанных в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="bd001-144">When the database installation completes, you can close Lync Server 2013 Management Shell or proceed to the installation of the Lync Server 2013 configured databases defined in Topology Builder.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a><span data-ttu-id="bd001-145">Использование командлетов Windows PowerShell для настройки баз данных топологии SQL Server</span><span class="sxs-lookup"><span data-stu-id="bd001-145">To use Windows PowerShell cmdlets to configure the SQL Server topology configured databases</span></span>

1.  <span data-ttu-id="bd001-146">Чтобы установить базу данных Topology Builder для Lync Server 2013, администратор Lync Server 2013 должен опубликовать топологию.</span><span class="sxs-lookup"><span data-stu-id="bd001-146">To install the Topology Builder configured databases for Lync Server 2013, the Lync Server 2013 administrator must publish the topology.</span></span> <span data-ttu-id="bd001-147">Подробности можно найти [в разделе Публикация топологии в Lync Server 2013](lync-server-2013-publish-the-topology.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="bd001-147">For details, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="bd001-148">На любом компьютере войдите в систему с учетными данными администратора для создания баз данных на сервере SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bd001-148">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="bd001-149">В этой статье содержатся [разрешения на развертывание SQL Server в Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="bd001-149">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bd001-150">Чтобы настроить базы данных SQL Server, убедитесь в том, что учетная запись администратора SQL Server, используемая для выполнения описанных здесь действий, также входит в группу "Администраторы" (или аналогичную) на сервере SQL Server и на котором размещается центральное управление. Роль сервера.</span><span class="sxs-lookup"><span data-stu-id="bd001-150">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="bd001-151">Это особенно важно для проверки наличия дополнительных пулов Lync Server 2013, в которых требуется установка или Настройка базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bd001-151">This is especially important to check for any additional Lync Server 2013 pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="bd001-152">Например, если вы развертываете второй пул (pool02), но роль сервера центрального управления удерживает pool01.</span><span class="sxs-lookup"><span data-stu-id="bd001-152">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="bd001-153">Группа системного администратора SQL Server (или ее эквивалент) должна иметь разрешения на доступ к обеим базам данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bd001-153">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="bd001-154">Откройте консоль управления Lync Server 2013, если она еще не открыта.</span><span class="sxs-lookup"><span data-stu-id="bd001-154">Open Lync Server 2013 Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="bd001-155">С помощью командлета **Install-ксдатабасе** установите базу данных, настроенную на основе Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="bd001-155">Use the **Install-CsDatabase** cmdlet to install the Topology Builder configured databases.</span></span>
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <fully qualified domain name of SQL Server> 
         -DatabasePaths <logfile path>,<database file path> -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe.contoso.net 
        -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="bd001-156">Параметр Report является необязательным, но он полезен, если вы собираетесь документировать процесс установки.</span><span class="sxs-lookup"><span data-stu-id="bd001-156">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

5.  <span data-ttu-id="bd001-157">После завершения установки базы данных закройте консоль управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bd001-157">When the database installation completes, close Lync Server 2013 Management Shell.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a><span data-ttu-id="bd001-158">Использование командлетов Windows PowerShell для настройки топологии SQL Server с помощью параметра Датабасепасмап</span><span class="sxs-lookup"><span data-stu-id="bd001-158">To use Windows PowerShell cmdlets to configure the SQL Server topology using the DatabasePathMap parameter</span></span>

1.  <span data-ttu-id="bd001-159">Чтобы установить базу данных для Lync Server 2013, администратор Lync Server должен создать пути и развернуть файлы баз данных и файлы журнала согласно предопределенному набору правил.</span><span class="sxs-lookup"><span data-stu-id="bd001-159">To install databases for Lync Server 2013, the Lync Server administrator must create the paths and deploy the databases files and log files according to a predefined set of rules.</span></span>

2.  <span data-ttu-id="bd001-160">На любом компьютере войдите в систему с учетными данными администратора для создания баз данных на сервере SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bd001-160">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="bd001-161">В этой статье содержатся [разрешения на развертывание SQL Server в Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="bd001-161">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bd001-162">Чтобы настроить базы данных SQL Server, убедитесь в том, что учетная запись администратора SQL Server, используемая для выполнения описанных здесь действий, также входит в группу "Администраторы" (или аналогичную) на сервере SQL Server и на котором размещается центральное управление. Роль сервера.</span><span class="sxs-lookup"><span data-stu-id="bd001-162">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="bd001-163">Это особенно важно для проверки наличия дополнительных пулов серверов Lync, в которых требуется установка или Настройка базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bd001-163">This is especially important to check for any additional Lync Server pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="bd001-164">Например, если вы развертываете второй пул (pool02), но роль сервера центрального управления удерживает pool01.</span><span class="sxs-lookup"><span data-stu-id="bd001-164">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="bd001-165">Группа системного администратора SQL Server (или ее эквивалент) должна иметь разрешения на доступ к обеим базам данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bd001-165">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="bd001-166">Откройте консоль управления Lync Server, если она еще не открыта.</span><span class="sxs-lookup"><span data-stu-id="bd001-166">Open Lync Server Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="bd001-167">С помощью командлета **Install-ксдатабасе** с параметром датабасепасмап и хэш-таблицей PowerShell установите базу данных, настроенную на основе Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="bd001-167">Use the **Install-CsDatabase** cmdlet with the DatabasePathMap parameter and a PowerShell hash table to install the Topology Builder configured databases.</span></span>

5.  <span data-ttu-id="bd001-168">В примере кода пути, определенные для баз данных, можно определить с помощью параметра – Датабасепасмап и определенной хэш-таблицы, как показано ниже (в примере используется "C:\\ксдата" для всех файлов базы данных (MDF) и "C:\\кслогфилес" для всех файлов журнала (LDF).</span><span class="sxs-lookup"><span data-stu-id="bd001-168">In the example code, the paths defined for the databases can be determined in a granular manner by using the –DatabasePathMap parameter and a defined hash table as follows (the example uses “C:\\CSData” for all database (.mdf) files, and “C:\\CSLogFiles” for all log (.ldf) files.</span></span> <span data-ttu-id="bd001-169">При необходимости будет создана папка Install-Ксдатабасе):</span><span class="sxs-lookup"><span data-stu-id="bd001-169">Folder will be created as needed by Install-CsDatabase):</span></span>
    ```powershell
    $pathmap = @{
    "BackendStore:BlobStore:DbPath"="C:\CsData";"BackendStore:BlobStore:LogPath"="C:\CsLogFiles"
    "BackendStore:RtcSharedDatabase:DbPath"="C:\CsData";"BackendStore:RtcSharedDatabase:LogPath"="C:\CsLogFiles"
    "ABSStore:AbsDatabase:DbPath"="C:\CsData";"ABSStore:AbsDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:RgsConfigDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsConfigDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:RgsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsDynDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:CpsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:CpsDynDatabase:LogPath"="C:\CsLogFiles"
    "ArchivingStore:ArchivingDatabase:DbPath"="C:\CsData";"ArchivingStore:ArchivingDatabase:LogPath"="C:\CsLogFiles"
    "MonitoringStore:MonitoringDatabase:DbPath"="C:\CsData";"MonitoringStore:MonitoringDatabase:LogPath"="C:\CsLogFiles"
    "MonitoringStore:QoEMetricsDatabase:DbPath"="C:\CsData";"MonitoringStore:QoEMetricsDatabase:LogPath"="C:\CsLogFiles"
    }
    Install-CsDatabase -ConfigureDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap
    ```
6.  <span data-ttu-id="bd001-170">Так как файлы базы данных и журнала явным образом названы на целевом сервере базы данных, вы можете задать конкретные расположения для базы данных и журнала для каждого типа службы.</span><span class="sxs-lookup"><span data-stu-id="bd001-170">Because the database and log files are explicitly named with their location on the destination database server, you can define specific locations for each service type’s actual database and log location.</span></span> <span data-ttu-id="bd001-171">В следующем примере базы данных размещаются для каждого определенного типа службы на разных дисках, а связанные файлы журнала — на другом.</span><span class="sxs-lookup"><span data-stu-id="bd001-171">The following example puts databases for each specific service type on separate disks, and associated log files on another.</span></span> <span data-ttu-id="bd001-172">Например:</span><span class="sxs-lookup"><span data-stu-id="bd001-172">For example:</span></span>
    
      - <span data-ttu-id="bd001-173">Все базы данных RTC в "D\\: рткдатабасе"</span><span class="sxs-lookup"><span data-stu-id="bd001-173">All RTC databases to “D:\\RTCDatabase”</span></span>
    
      - <span data-ttu-id="bd001-174">Все файлы журнала RTC на "E:\\ртклогс"</span><span class="sxs-lookup"><span data-stu-id="bd001-174">All RTC log files to “E:\\RTCLogs”</span></span>
    
      - <span data-ttu-id="bd001-175">Все базы данных магазина приложений в "F\\: кпсдатабасес"</span><span class="sxs-lookup"><span data-stu-id="bd001-175">All application store databases to “F:\\CPSDatabases”</span></span>
    
      - <span data-ttu-id="bd001-176">Все журналы приложений для магазина в "G\\: кпслогс"</span><span class="sxs-lookup"><span data-stu-id="bd001-176">All application store logs to “G:\\CPSLogs”</span></span>
    
      - <span data-ttu-id="bd001-177">Все базы данных магазина группы ответа в "H\\: ргсдатабасес"</span><span class="sxs-lookup"><span data-stu-id="bd001-177">All response group store databases to “H:\\RGSDatabases”</span></span>
    
      - <span data-ttu-id="bd001-178">Все журналы магазина группы ответа в "I:\\ргслогс"</span><span class="sxs-lookup"><span data-stu-id="bd001-178">All response group store logs to “I:\\RGSLogs”</span></span>
    
      - <span data-ttu-id="bd001-179">Все базы данных из хранилища адресных книг в\\"J: абсдатабасес"</span><span class="sxs-lookup"><span data-stu-id="bd001-179">All address book store databases to “J:\\ABSDatabases”</span></span>
    
      - <span data-ttu-id="bd001-180">Все файлы журнала для хранения адресной книги в "K\\: абслогс"</span><span class="sxs-lookup"><span data-stu-id="bd001-180">All address book store log files to “K:\\ABSLogs”</span></span>
    
      - <span data-ttu-id="bd001-181">Все базы данных архивов из Store в\\"L: арчивингдатабасес"</span><span class="sxs-lookup"><span data-stu-id="bd001-181">All archiving store databases to “L:\\ArchivingDatabases”</span></span>
    
      - <span data-ttu-id="bd001-182">Все журналы архивирования в хранилище "м\\: арчивинглогс"</span><span class="sxs-lookup"><span data-stu-id="bd001-182">All archiving store logs to “M:\\ArchivingLogs”</span></span>
    
      - <span data-ttu-id="bd001-183">Все базы данных магазина мониторинга в "N\\: мониторингдатабасес"</span><span class="sxs-lookup"><span data-stu-id="bd001-183">All monitoring store databases to “N:\\MonitoringDatabases”</span></span>
    
      - <span data-ttu-id="bd001-184">Все файлы журнала мониторинга в магазине для "O\\: мониторинглогфилес"</span><span class="sxs-lookup"><span data-stu-id="bd001-184">All monitoring store log files to “O:\\MonitoringLogfiles”</span></span>
    
    <!-- end list -->
    
    ```powershell    
    $pathmap = @{
    "BackendStore:BlobStore:DbPath"="D:\RTCDatabase";"BackendStore:BlobStore:LogPath"="E:\RTCLogs"
    "BackendStore:RtcSharedDatabase:DbPath"="D:\RTCDatabase";"BackendStore:RtcSharedDatabase:LogPath"="E:\RTCLogs"
    "ABSStore:AbsDatabase:DbPath"="J:\ABSDatabases";"ABSStore:AbsDatabase:LogPath"="K:\ABSLogs"
    "ApplicationStore:RgsConfigDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsConfigDatabase:LogPath"="G:\CPSLogs"
    "ApplicationStore:RgsDynDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsDynDatabase:LogPath"="I:\RGSLogs"
    "ApplicationStore:CpsDynDatabase:DbPath"="F:\CPSDatabases";"ApplicationStore:CpsDynDatabase:LogPath"="G:\CsLogFiles"
    "ArchivingStore:ArchivingDatabase:DbPath"="M:\ArchivingLogs";"ArchivingStore:ArchivingDatabase:LogPath"="N:\MonitoringDatabases"
    "MonitoringStore:MonitoringDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:MonitoringDatabase:LogPath"="O:\MonitoringLogfiles"
    "MonitoringStore:QoEMetricsDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:QoEMetricsDatabase:LogPath"="O:\MonitoringLogfiles"
    }
    
    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap
    ```
    
    <span data-ttu-id="bd001-185">С помощью параметра – Датабасепасмап вы можете определить любую комбинацию сопоставления букв логических дисков, которая обеспечивает наилучшее решение для требований к производительности и размещению SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bd001-185">Using the –DatabasePathMap parameter, you can define any logical drive letter mapping combination that provides the best solution for your SQL Server performance and placement requirements.</span></span>

<span data-ttu-id="bd001-186">Если вы настроили файлы данных и журналы базы данных с помощью метода **датабасепасмап** , вам потребуется внести небольшие изменения в обычный процесс при использовании Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="bd001-186">If you configure your database data files and log files by using the **DatabasePathMap** method, you will need to make a slight change to your normal process when using Topology Builder.</span></span> <span data-ttu-id="bd001-187">Обычно определяются варианты топологии, публикуются топология и выбирается развертывание выбранных баз данных.</span><span class="sxs-lookup"><span data-stu-id="bd001-187">Typically, you would define your topology choices, publish the topology, and choose to deploy the database selections.</span></span>

<span data-ttu-id="bd001-188">Если вы использовали **датабасепасмап** , вы уже выполнили третью часть процесса Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="bd001-188">If you have used **DatabasePathMap** you have already accomplished the third part of the Topology Builder process.</span></span> <span data-ttu-id="bd001-189">В случае, если сервер базы данных полностью настроен на предварительный запуск построителя топологии, вы можете определить все роли и параметры сервера, но отменить выбор параметра для создания баз данных.</span><span class="sxs-lookup"><span data-stu-id="bd001-189">In the case of having a completely configured database server in advance of running Topology Builder, you would still define all of your server roles and options, but deselect the option to create the databases.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

