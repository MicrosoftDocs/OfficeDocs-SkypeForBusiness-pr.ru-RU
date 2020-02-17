---
title: 'Lync Server 2013: Установка базы данных с помощью командной консоли Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database installation using Lync Server Management Shell
ms:assetid: c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398832(v=OCS.15)
ms:contentKeyID: 48185401
ms.date: 06/16/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d46d3bc2ce881edc183e4996c0c71d6a90af4e6a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a><span data-ttu-id="b3139-102">Установка базы данных с помощью командной консоли Lync Server в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3139-102">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3139-103">_**Последнее изменение темы:** 2016-06-16_</span><span class="sxs-lookup"><span data-stu-id="b3139-103">_**Topic Last Modified:** 2016-06-16_</span></span>

<span data-ttu-id="b3139-104">Разделение ролей и обязанностей между администраторами серверов и администраторами SQL Server может привести к задержкам при реализации.</span><span class="sxs-lookup"><span data-stu-id="b3139-104">Separation of roles and responsibilities between server administrators and SQL Server administrators can result in delays in implementation.</span></span> <span data-ttu-id="b3139-105">Для устранения этих проблем Lync Server 2013 использует управление доступом на основе ролей (RBAC).</span><span class="sxs-lookup"><span data-stu-id="b3139-105">Lync Server 2013 uses role-based access control (RBAC) to mitigate these difficulties.</span></span> <span data-ttu-id="b3139-106">В некоторых случаях администратор SQL Server должен управлять установкой баз данных на сервере SQL Server вне RBAC.</span><span class="sxs-lookup"><span data-stu-id="b3139-106">In some instances, the SQL Server administrator must manage the installation of databases on the SQL Server-based server outside RBAC.</span></span> <span data-ttu-id="b3139-107">Консоль управления Lync Server 2013 позволяет администратору SQL Server запускать командлеты Windows PowerShell, предназначенные для настройки баз данных с использованием правильных файлов данных и журналов.</span><span class="sxs-lookup"><span data-stu-id="b3139-107">The Lync Server 2013 Management Shell provides a way for the SQL Server administrator to run Windows PowerShell cmdlets designed to configure the databases with the correct data and log files.</span></span> <span data-ttu-id="b3139-108">Дополнительные сведения см [в разделе разрешения на развертывание для SQL Server в Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b3139-108">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="b3139-109">В следующей процедуре предполагается, что по крайней мере на сервере Lync Server 2013 OCSCore. msi (sqlncli. msi) установлены объекты управления Microsoft SQL Server 2012 Microsoft SQL Server (sqlncli. msi), типы CLR для Microsoft SQL Server 2012 и Microsoft SQL Server 2012 ADOMD.NET.</span><span class="sxs-lookup"><span data-stu-id="b3139-109">The following procedure assumes that at a minimum the Lync Server 2013 OCSCore.msi, SQL Server Native Client (sqlncli.msi) Microsoft SQL Server 2012 Management Objects, CLR Types for Microsoft SQL Server 2012 and Microsoft SQL Server 2012 ADOMD.NET are installed.</span></span> <span data-ttu-id="b3139-110">OCSCore. msi находится на установочном носителе в каталоге \Setup\AMD64\Setup</span><span class="sxs-lookup"><span data-stu-id="b3139-110">The OCSCore.msi is located on the installation media in the \Setup\AMD64\Setup directory.</span></span> <span data-ttu-id="b3139-111">Остальные компоненты находятся в \Setup\amd64.</span><span class="sxs-lookup"><span data-stu-id="b3139-111">The remaining components are located in \Setup\amd64.</span></span> <span data-ttu-id="b3139-112">Кроме того, подготовка Active Directory для Lync Server 2013 успешно завершена.</span><span class="sxs-lookup"><span data-stu-id="b3139-112">Additionally, Active Directory preparation for Lync Server 2013 has been successfully completed.</span></span>



</div>

<span data-ttu-id="b3139-113">**Install-CsDatabase** — это командлет Windows PowerShell, который используется для установки баз данных.</span><span class="sxs-lookup"><span data-stu-id="b3139-113">**Install-CsDatabase** is the Windows PowerShell cmdlet you use to install the databases.</span></span> <span data-ttu-id="b3139-114">Командлет **Install – CsDatabase** содержит большое количество параметров, которые рассматриваются в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="b3139-114">The **Install-CsDatabase** cmdlet has a large number of parameters, only a few of which are discussed here.</span></span> <span data-ttu-id="b3139-115">Дополнительные сведения о возможных параметрах см. в документации по командной консоли Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b3139-115">For details about the possible parameters, see the Lync Server 2013 Management Shell documentation.</span></span>

<div class=" ">


> [!WARNING]  
> <span data-ttu-id="b3139-116">Чтобы избежать снижения производительности и возможных проблем с истечением времени, всегда используйте полные доменные имена при обращении к серверам на основе SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b3139-116">To avoid performance and possible time-out issues, always use fully qualified domain names (FQDNs) when referring to SQL Server-based servers.</span></span> <span data-ttu-id="b3139-117">Избегайте использования ссылок только на имена узлов.</span><span class="sxs-lookup"><span data-stu-id="b3139-117">Avoid using host name-only references.</span></span> <span data-ttu-id="b3139-118">Например, используйте sqlbe01.contoso.net, но не используйте SQLBE01.</span><span class="sxs-lookup"><span data-stu-id="b3139-118">For example, use sqlbe01.contoso.net, but avoid using SQLBE01.</span></span>



</div>

<span data-ttu-id="b3139-119">Для установки баз данных **Install – CsDatabase** использует три основных метода размещения баз данных на подготовленном сервере на основе SQL Server:</span><span class="sxs-lookup"><span data-stu-id="b3139-119">For installing databases, **Install-CsDatabase** uses three primary methods for placing the databases onto the prepared SQL Server-based server:</span></span>

  - <span data-ttu-id="b3139-120">Выполните командлет **Install CsDatabase** без Датабасепасс или уседефаултсклпас.</span><span class="sxs-lookup"><span data-stu-id="b3139-120">Run **Install-CsDatabase** without DatabasePaths or UseDefaultSqlPath.</span></span> <span data-ttu-id="b3139-121">Командлет использует встроенный алгоритм для определения лучшего размещения файлов журнала и данных.</span><span class="sxs-lookup"><span data-stu-id="b3139-121">The cmdlet uses a built in algorithm to determine the best placement for the log and data files.</span></span> <span data-ttu-id="b3139-122">Алгоритм работает только для изолированных реализаций SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b3139-122">The algorithm only works for stand-alone SQL Server implementations.</span></span>

  - <span data-ttu-id="b3139-123">Выполните командлет **Install — CsDatabase** с параметром датабасепасс.</span><span class="sxs-lookup"><span data-stu-id="b3139-123">Run **Install-CsDatabase** with the DatabasePaths parameter.</span></span> <span data-ttu-id="b3139-124">Встроенный алгоритм оптимизации расположений журналов и файлов данных не используется, если задан параметр Датабасепасс.</span><span class="sxs-lookup"><span data-stu-id="b3139-124">The built-in algorithm to optimize log and data file locations is not used if the DatabasePaths parameter is defined.</span></span> <span data-ttu-id="b3139-125">С помощью этого параметра можно определить расположения, в которых будут развернуты файлы журнала и данных.</span><span class="sxs-lookup"><span data-stu-id="b3139-125">Using this parameter allows you to define the locations where log and data files will be deployed.</span></span>

  - <span data-ttu-id="b3139-126">Выполните командлет **Install — CsDatabase** с уседефаултсклпасс.</span><span class="sxs-lookup"><span data-stu-id="b3139-126">Run **Install-CsDatabase** with UseDefaultSqlPaths.</span></span> <span data-ttu-id="b3139-127">Этот параметр не использует встроенный алгоритм для оптимизации расположений файлов журнала и данных.</span><span class="sxs-lookup"><span data-stu-id="b3139-127">This option does not use the built-in algorithm to optimize the log and data file locations.</span></span> <span data-ttu-id="b3139-128">Файл журнала и данных развертывается в соответствии с параметрами по умолчанию, установленными администратором SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b3139-128">Log and data file are deployed according to the defaults set by the SQL Server administrator.</span></span> <span data-ttu-id="b3139-129">Эти пути обычно задаются для автоматического администрирования файлов журналов и данных на SQL Server заранее и не связаны с настройкой Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b3139-129">These paths are typically set for the purpose of automatic administration of log and data files on the SQL Server in advance, and are not associated with the setup of Lync Server 2013.</span></span>

  - <span data-ttu-id="b3139-130">Параметр DatabasePathMap также можно использовать для явного указания расположения для каждой базы данных и соответствующего файла журнала.</span><span class="sxs-lookup"><span data-stu-id="b3139-130">The DatabasePathMap parameter can also be used to explicitly specify a location for each database and its respective log file.</span></span>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a><span data-ttu-id="b3139-131">Использование командлетов Windows PowerShell для настройки центрального хранилища управления SQL Server</span><span class="sxs-lookup"><span data-stu-id="b3139-131">To use Windows PowerShell cmdlets to configure the SQL Server Central Management store</span></span>

1.  <span data-ttu-id="b3139-132">Войдите на любой компьютер, используя учетные данные администратора для создания баз данных на сервере SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b3139-132">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="b3139-133">Дополнительные сведения см [в разделе разрешения на развертывание для SQL Server в Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b3139-133">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

2.  <span data-ttu-id="b3139-134">Откройте консоль управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b3139-134">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="b3139-135">Если вы не настроили политику выполнения для Windows PowerShell, необходимо настроить политику, чтобы разрешить выполнение сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b3139-135">If you have not adjusted the execution policy for Windows PowerShell, you must adjust the policy to allow Windows PowerShell scripts to run.</span></span> <span data-ttu-id="b3139-136">Дополнительные сведения см. в [http://go.microsoft.com/fwlink/p/?linkId=203093](http://go.microsoft.com/fwlink/p/?linkid=203093)разделе "Проверка политики выполнения".</span><span class="sxs-lookup"><span data-stu-id="b3139-136">For details, see “Examining the Execution Policy” at [http://go.microsoft.com/fwlink/p/?linkId=203093](http://go.microsoft.com/fwlink/p/?linkid=203093).</span></span>

3.  <span data-ttu-id="b3139-137">Используйте командлет **Install – CsDatabase** для установки центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="b3139-137">Use the **Install-CsDatabase** cmdlet to install the Central Management store.</span></span>
    
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
    > <span data-ttu-id="b3139-138">Параметр Report является необязательным, но его можно использовать при документировании процесса установки.</span><span class="sxs-lookup"><span data-stu-id="b3139-138">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

4.  <span data-ttu-id="b3139-139">**Install-CsDatabase – датабасепасс** может использовать до шести параметров Path, каждый из которых определяет пути для дисков, определенных в данных SQL Server и размещении файлов журналов.</span><span class="sxs-lookup"><span data-stu-id="b3139-139">**Install-CsDatabase –DatabasePaths** can use up to six path parameters, each defining the paths for the drives as defined in SQL Server Data and Log File Placement.</span></span> <span data-ttu-id="b3139-140">По логическим правилам конфигурации базы данных в Lync Server 2013 диски разбиваются на сегменты двух, четырех или шести.</span><span class="sxs-lookup"><span data-stu-id="b3139-140">By the logical rules of the database configuration in Lync Server 2013, drives are parsed out into buckets of two, four, or six.</span></span> <span data-ttu-id="b3139-141">В зависимости от конфигурации SQL Server и количества сегментов вы будете предоставлять два пути, четыре пути или шесть путей.</span><span class="sxs-lookup"><span data-stu-id="b3139-141">Depending on your SQL Server configuration and the number of buckets, you will supply two paths, four paths, or six paths.</span></span>
    
    <span data-ttu-id="b3139-142">Если у вас три диска, журнал получает приоритет и файлы данных распределяются по завершении.</span><span class="sxs-lookup"><span data-stu-id="b3139-142">If you have three drives, the log gets priority and the data files are distributed after.</span></span> <span data-ttu-id="b3139-143">Пример для сервера SQL Server, настроенного на шесть дисков:</span><span class="sxs-lookup"><span data-stu-id="b3139-143">An example for a SQL Server-based server configured with six drives:</span></span>
    ```powershell
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```
5.  <span data-ttu-id="b3139-144">По завершении установки базы данных можно закрыть Lync Server 2013 Management Shell или перейти к установке баз данных, настроенных для Lync Server 2013, определенных в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="b3139-144">When the database installation completes, you can close Lync Server 2013 Management Shell or proceed to the installation of the Lync Server 2013 configured databases defined in Topology Builder.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a><span data-ttu-id="b3139-145">Использование командлетов Windows PowerShell для настройки баз данных, настроенных для топологии SQL Server</span><span class="sxs-lookup"><span data-stu-id="b3139-145">To use Windows PowerShell cmdlets to configure the SQL Server topology configured databases</span></span>

1.  <span data-ttu-id="b3139-146">Чтобы установить базы данных, настроенные в построителе топологий для Lync Server 2013, администратор Lync Server 2013 должен опубликовать эту топологию.</span><span class="sxs-lookup"><span data-stu-id="b3139-146">To install the Topology Builder configured databases for Lync Server 2013, the Lync Server 2013 administrator must publish the topology.</span></span> <span data-ttu-id="b3139-147">Дополнительные сведения см в статье [Publishing Topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="b3139-147">For details, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="b3139-148">Войдите на любой компьютер, используя учетные данные администратора для создания баз данных на сервере SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b3139-148">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="b3139-149">В этом разделе представлены [разрешения на развертывание SQL Server в Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b3139-149">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b3139-150">Чтобы настроить базы данных на основе SQL Server, убедитесь, что учетная запись администратора SQL Server, используемая для выполнения описанных здесь действий, также является членом группы "Администраторы" (или аналогичной) на сервере SQL Server, где размещается центральное управление Роль сервера.</span><span class="sxs-lookup"><span data-stu-id="b3139-150">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="b3139-151">Это особенно важно для проверки наличия дополнительных пулов Lync Server 2013, требующих установки или настройки базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b3139-151">This is especially important to check for any additional Lync Server 2013 pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="b3139-152">Например, если развертывается второй пул (pool02), но роль сервера центрального управления удерживается pool01.</span><span class="sxs-lookup"><span data-stu-id="b3139-152">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="b3139-153">Группа администраторов SQL Server (или аналогичная) должна иметь разрешения для баз данных на основе SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b3139-153">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="b3139-154">Откройте Lync Server 2013 Management Shell, если она еще не открыта.</span><span class="sxs-lookup"><span data-stu-id="b3139-154">Open Lync Server 2013 Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="b3139-155">Командлет **Install – CsDatabase** используется для установки баз данных, настроенных в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="b3139-155">Use the **Install-CsDatabase** cmdlet to install the Topology Builder configured databases.</span></span>
    
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
    > <span data-ttu-id="b3139-156">Параметр Report является необязательным, но его можно использовать при документировании процесса установки.</span><span class="sxs-lookup"><span data-stu-id="b3139-156">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

5.  <span data-ttu-id="b3139-157">После завершения установки базы данных закройте консоль управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b3139-157">When the database installation completes, close Lync Server 2013 Management Shell.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a><span data-ttu-id="b3139-158">Использование командлетов Windows PowerShell для настройки топологии SQL Server с помощью параметра DatabasePathMap</span><span class="sxs-lookup"><span data-stu-id="b3139-158">To use Windows PowerShell cmdlets to configure the SQL Server topology using the DatabasePathMap parameter</span></span>

1.  <span data-ttu-id="b3139-159">Чтобы установить базы данных для Lync Server 2013, администратор Lync Server должен создать пути и развернуть файлы баз данных и файлы журнала в соответствии с предварительно определенным набором правил.</span><span class="sxs-lookup"><span data-stu-id="b3139-159">To install databases for Lync Server 2013, the Lync Server administrator must create the paths and deploy the databases files and log files according to a predefined set of rules.</span></span>

2.  <span data-ttu-id="b3139-160">Войдите на любой компьютер, используя учетные данные администратора для создания баз данных на сервере SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b3139-160">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="b3139-161">В этом разделе представлены [разрешения на развертывание SQL Server в Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b3139-161">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b3139-162">Чтобы настроить базы данных на основе SQL Server, убедитесь, что учетная запись администратора SQL Server, используемая для выполнения описанных здесь действий, также является членом группы "Администраторы" (или аналогичной) на сервере SQL Server, где размещается центральное управление Роль сервера.</span><span class="sxs-lookup"><span data-stu-id="b3139-162">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="b3139-163">Это особенно важно для проверки наличия дополнительных пулов Lync Server, в которых требуется установка или Настройка базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b3139-163">This is especially important to check for any additional Lync Server pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="b3139-164">Например, если развертывается второй пул (pool02), но роль сервера центрального управления удерживается pool01.</span><span class="sxs-lookup"><span data-stu-id="b3139-164">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="b3139-165">Группа администраторов SQL Server (или аналогичная) должна иметь разрешения для баз данных на основе SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b3139-165">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="b3139-166">Откройте командную консоль Lync Server, если она еще не открыта.</span><span class="sxs-lookup"><span data-stu-id="b3139-166">Open Lync Server Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="b3139-167">Используйте командлет **Install-CsDatabase** с параметром DatabasePathMap и хэш-таблицей PowerShell для установки баз данных, настроенных в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="b3139-167">Use the **Install-CsDatabase** cmdlet with the DatabasePathMap parameter and a PowerShell hash table to install the Topology Builder configured databases.</span></span>

5.  <span data-ttu-id="b3139-168">В примере кода пути, определенные для баз данных, можно определить с помощью параметра – DatabasePathMap и указанной хэш-таблицы, как показано ниже (в примере используется "C:\\ксдата" для всех файлов базы данных (MDF) и "C:\\кслогфилес" для всех файлов журнала (LDF).</span><span class="sxs-lookup"><span data-stu-id="b3139-168">In the example code, the paths defined for the databases can be determined in a granular manner by using the –DatabasePathMap parameter and a defined hash table as follows (the example uses “C:\\CSData” for all database (.mdf) files, and “C:\\CSLogFiles” for all log (.ldf) files.</span></span> <span data-ttu-id="b3139-169">Папка будет создана при необходимости в Install-CsDatabase):</span><span class="sxs-lookup"><span data-stu-id="b3139-169">Folder will be created as needed by Install-CsDatabase):</span></span>
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
6.  <span data-ttu-id="b3139-170">Так как база данных и файлы журнала явно называются их расположением на целевом сервере баз данных, можно определить конкретные расположения для базы данных и журнала каждой службы.</span><span class="sxs-lookup"><span data-stu-id="b3139-170">Because the database and log files are explicitly named with their location on the destination database server, you can define specific locations for each service type’s actual database and log location.</span></span> <span data-ttu-id="b3139-171">В следующем примере базы данных размещаются для каждого конкретного типа службы на разных дисках, а связанные файлы журналов — на другом.</span><span class="sxs-lookup"><span data-stu-id="b3139-171">The following example puts databases for each specific service type on separate disks, and associated log files on another.</span></span> <span data-ttu-id="b3139-172">Например:</span><span class="sxs-lookup"><span data-stu-id="b3139-172">For example:</span></span>
    
      - <span data-ttu-id="b3139-173">Все базы данных RTC до "D\\: рткдатабасе"</span><span class="sxs-lookup"><span data-stu-id="b3139-173">All RTC databases to “D:\\RTCDatabase”</span></span>
    
      - <span data-ttu-id="b3139-174">Все файлы журналов RTC в "E:\\ртклогс"</span><span class="sxs-lookup"><span data-stu-id="b3139-174">All RTC log files to “E:\\RTCLogs”</span></span>
    
      - <span data-ttu-id="b3139-175">Все базы данных хранилища приложений в "F\\: кпсдатабасес"</span><span class="sxs-lookup"><span data-stu-id="b3139-175">All application store databases to “F:\\CPSDatabases”</span></span>
    
      - <span data-ttu-id="b3139-176">Все журналы хранилища приложений в "G:\\кпслогс"</span><span class="sxs-lookup"><span data-stu-id="b3139-176">All application store logs to “G:\\CPSLogs”</span></span>
    
      - <span data-ttu-id="b3139-177">Все базы данных хранилища группы ответа в "H\\: ргсдатабасес"</span><span class="sxs-lookup"><span data-stu-id="b3139-177">All response group store databases to “H:\\RGSDatabases”</span></span>
    
      - <span data-ttu-id="b3139-178">Все журналы хранилища группы ответа в "I:\\ргслогс"</span><span class="sxs-lookup"><span data-stu-id="b3139-178">All response group store logs to “I:\\RGSLogs”</span></span>
    
      - <span data-ttu-id="b3139-179">Все базы данных хранилища адресных книг в "\\J: абсдатабасес"</span><span class="sxs-lookup"><span data-stu-id="b3139-179">All address book store databases to “J:\\ABSDatabases”</span></span>
    
      - <span data-ttu-id="b3139-180">Все файлы журнала хранилища адресной книги в "K:\\абслогс"</span><span class="sxs-lookup"><span data-stu-id="b3139-180">All address book store log files to “K:\\ABSLogs”</span></span>
    
      - <span data-ttu-id="b3139-181">Все базы данных хранилища архива в "L\\: арчивингдатабасес"</span><span class="sxs-lookup"><span data-stu-id="b3139-181">All archiving store databases to “L:\\ArchivingDatabases”</span></span>
    
      - <span data-ttu-id="b3139-182">Все журналы хранилища архивации в "M\\: арчивинглогс"</span><span class="sxs-lookup"><span data-stu-id="b3139-182">All archiving store logs to “M:\\ArchivingLogs”</span></span>
    
      - <span data-ttu-id="b3139-183">Все базы данных хранилища данных мониторинга в "\\N: мониторингдатабасес"</span><span class="sxs-lookup"><span data-stu-id="b3139-183">All monitoring store databases to “N:\\MonitoringDatabases”</span></span>
    
      - <span data-ttu-id="b3139-184">Все файлы журналов хранилища мониторинга в "O:\\мониторинглогфилес"</span><span class="sxs-lookup"><span data-stu-id="b3139-184">All monitoring store log files to “O:\\MonitoringLogfiles”</span></span>
    
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
    
    <span data-ttu-id="b3139-185">С помощью параметра – DatabasePathMap можно определить любую комбинацию сопоставления букв логических дисков, которая обеспечивает наилучшее решение для требований к производительности и размещению SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b3139-185">Using the –DatabasePathMap parameter, you can define any logical drive letter mapping combination that provides the best solution for your SQL Server performance and placement requirements.</span></span>

<span data-ttu-id="b3139-186">Если вы настраиваете файлы данных и файлы журналов базы данных с помощью метода **DatabasePathMap** , вам потребуется внести небольшое изменение в обычный процесс при использовании построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="b3139-186">If you configure your database data files and log files by using the **DatabasePathMap** method, you will need to make a slight change to your normal process when using Topology Builder.</span></span> <span data-ttu-id="b3139-187">Как правило, необходимо определить варианты топологии, опубликовать топологию и выбрать развертывание выбранных баз данных.</span><span class="sxs-lookup"><span data-stu-id="b3139-187">Typically, you would define your topology choices, publish the topology, and choose to deploy the database selections.</span></span>

<span data-ttu-id="b3139-188">Если вы использовали **DatabasePathMap** , вы уже выполнили третью часть процесса построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="b3139-188">If you have used **DatabasePathMap** you have already accomplished the third part of the Topology Builder process.</span></span> <span data-ttu-id="b3139-189">В случае, если полностью настроенный сервер базы данных был предварительно настроен в построителе топологий, вы все равно должны определить все роли сервера и параметры, а затем отменить выбор параметра для создания баз данных.</span><span class="sxs-lookup"><span data-stu-id="b3139-189">In the case of having a completely configured database server in advance of running Topology Builder, you would still define all of your server roles and options, but deselect the option to create the databases.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

