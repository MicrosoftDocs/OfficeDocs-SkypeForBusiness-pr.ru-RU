---
title: 'Lync Server 2013: исключения из антивирусной проверки'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Antivirus scanning exclusions for Lync Server 2013
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440138(v=OCS.15)
ms:contentKeyID: 57793042
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6f354b93bf21f054e9b5b24e3befd1787279bbe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a><span data-ttu-id="987e4-102">Исключения из антивирусной проверки для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="987e4-102">Antivirus scanning exclusions for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="987e4-103">_**Тема последнего изменения:** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="987e4-103">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="987e4-104">Чтобы антивирусная программа не мешала работе с Lync Server 2013, необходимо исключить определенные процессы и каталоги для каждого сервера или серверной роли Lync Server 2013, на которых вы запускаете антивирусную программу.</span><span class="sxs-lookup"><span data-stu-id="987e4-104">To ensure that the antivirus scanner does not interfere with the operation of Lync Server 2013, you must exclude specific processes and directories for each Lync Server 2013 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="987e4-105">Исключите перечисленные ниже процессы и каталоги.</span><span class="sxs-lookup"><span data-stu-id="987e4-105">The following processes and directories should be excluded:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="987e4-106">Ниже указаны расположения файлов и папок для Lync Server 2013 по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="987e4-106">Folder and file locations listed below are the default locations for Lync Server 2013.</span></span> <span data-ttu-id="987e4-107">Если в вашей организации какие-либо из этих объектов расположены в других местах, укажите соответствующие пути.</span><span class="sxs-lookup"><span data-stu-id="987e4-107">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="987e4-108">Обратите внимание, что в некоторых антивирусных программах в списке исключений необходимо указывать абсолютные пути, а не относительные.</span><span class="sxs-lookup"><span data-stu-id="987e4-108">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>



</div>

  - <span data-ttu-id="987e4-109">Lync Server 2013 процессы:</span><span class="sxs-lookup"><span data-stu-id="987e4-109">Lync Server 2013 processes:</span></span>
    
      - <span data-ttu-id="987e4-110">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="987e4-110">ABServer.exe</span></span>
    
      - <span data-ttu-id="987e4-111">Акпмкусвк. exe</span><span class="sxs-lookup"><span data-stu-id="987e4-111">AcpMcuSvc.exe</span></span>
    
      - <span data-ttu-id="987e4-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="987e4-112">ASMCUSvc.exe</span></span>
    
      - <span data-ttu-id="987e4-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="987e4-113">AVMCUSvc.exe</span></span>
    
      - <span data-ttu-id="987e4-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="987e4-114">ChannelService.exe</span></span>
    
      - <span data-ttu-id="987e4-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="987e4-115">ClsAgent.exe</span></span>
    
      - <span data-ttu-id="987e4-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="987e4-116">ComplianceService.exe</span></span>
    
      - <span data-ttu-id="987e4-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="987e4-117">DataMCUSvc.exe</span></span>
    
      - <span data-ttu-id="987e4-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="987e4-118">DataProxy.exe</span></span>
    
      - <span data-ttu-id="987e4-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="987e4-119">FileTransferAgent.exe</span></span>
    
      - <span data-ttu-id="987e4-120">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="987e4-120">IMMCUSvc.exe</span></span>
    
      - <span data-ttu-id="987e4-121">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="987e4-121">LysSvc.exe</span></span>
    
      - <span data-ttu-id="987e4-122">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="987e4-122">MasterReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="987e4-123">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="987e4-123">MediaRelaySvc.exe</span></span>
    
      - <span data-ttu-id="987e4-124">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="987e4-124">MediationServerSvc.exe</span></span>
    
      - <span data-ttu-id="987e4-125">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="987e4-125">MRASSvc.exe</span></span>
    
      - <span data-ttu-id="987e4-126">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="987e4-126">OcsAppServerHost.exe</span></span>
    
      - <span data-ttu-id="987e4-127">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="987e4-127">ReplicaReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="987e4-128">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="987e4-128">ReplicationApp.exe</span></span>
    
      - <span data-ttu-id="987e4-129">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="987e4-129">RtcHost.exe</span></span>
    
      - <span data-ttu-id="987e4-130">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="987e4-130">RTCSrv.exe</span></span>
    
      - <span data-ttu-id="987e4-131">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="987e4-131">XmppProxy.exe</span></span>
    
      - <span data-ttu-id="987e4-132">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="987e4-132">XmppTGW.exe</span></span>

  - <span data-ttu-id="987e4-133">Процессы службы узла Windows Fabric</span><span class="sxs-lookup"><span data-stu-id="987e4-133">Windows Fabric Host Service processes:</span></span>
    
      - <span data-ttu-id="987e4-134">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="987e4-134">Fabric.exe</span></span>
    
      - <span data-ttu-id="987e4-135">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="987e4-135">FabricDCA.exe</span></span>
    
      - <span data-ttu-id="987e4-136">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="987e4-136">FabricHost.exe</span></span>

  - <span data-ttu-id="987e4-137">Процессы IIS</span><span class="sxs-lookup"><span data-stu-id="987e4-137">IIS processes:</span></span>
    
      - <span data-ttu-id="987e4-138">% SystemRoot%\\system32\\инетсрв\\w3wp. exe</span><span class="sxs-lookup"><span data-stu-id="987e4-138">%systemroot%\\system32\\inetsrv\\w3wp.exe</span></span>
    
      - <span data-ttu-id="987e4-139">% SystemRoot%\\SysWOW64\\инетсрв\\w3wp. exe</span><span class="sxs-lookup"><span data-stu-id="987e4-139">%systemroot%\\SysWOW64\\inetsrv\\w3wp.exe</span></span>

  - <span data-ttu-id="987e4-140">Внутренние процессы сервера SQL Server</span><span class="sxs-lookup"><span data-stu-id="987e4-140">SQL Server Back-End processes:</span></span>
    
      - <span data-ttu-id="987e4-141">% ProgramFiles%\\Microsoft SQL Server\\MSSQL11. MSSQLSERVER\\MSSQL\\бинн\\SQLServr. exe</span><span class="sxs-lookup"><span data-stu-id="987e4-141">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.MSSQLSERVER\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="987e4-142">% ProgramFiles%\\Microsoft SQL Server\\MSRS11. ReportServer\\\\в службах\\отчетов\\репортингсервицессервице. exe</span><span class="sxs-lookup"><span data-stu-id="987e4-142">%ProgramFiles%\\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService.exe</span></span>
    
      - <span data-ttu-id="987e4-143">% ProgramFiles%\\Microsoft SQL Server\\MSAS11. MSSQLSERVER\\OLAP\\bin\\, программа MSMDSrv. exe</span><span class="sxs-lookup"><span data-stu-id="987e4-143">%ProgramFiles%\\Microsoft SQL Server\\MSAS11.MSSQLSERVER\\OLAP\\Bin\\MSMDSrv.exe</span></span>

  - <span data-ttu-id="987e4-144">Внешние процессы сервера SQL Server</span><span class="sxs-lookup"><span data-stu-id="987e4-144">SQL Server Front-End processes:</span></span>
    
      - <span data-ttu-id="987e4-145">% ProgramFiles%\\Microsoft SQL Server\\MSSQL11. ЛИНКЛОКАЛ\\MSSQL\\бинн\\SQLServr. exe</span><span class="sxs-lookup"><span data-stu-id="987e4-145">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.LYNCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="987e4-146">% ProgramFiles%\\Microsoft SQL Server\\MSSQL11. РТКЛОКАЛ\\MSSQL\\бинн\\SQLServr. exe</span><span class="sxs-lookup"><span data-stu-id="987e4-146">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.RTCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>

  - <span data-ttu-id="987e4-147">Каталоги и файлы</span><span class="sxs-lookup"><span data-stu-id="987e4-147">Directories and files:</span></span>
    
      - <span data-ttu-id="987e4-148">файлы журнала%\\systemroot\\% system32</span><span class="sxs-lookup"><span data-stu-id="987e4-148">%systemroot%\\System32\\LogFiles</span></span>
    
      - <span data-ttu-id="987e4-149">журналы% systemroot\\%\\SysWOW64</span><span class="sxs-lookup"><span data-stu-id="987e4-149">%systemroot%\\SysWow64\\LogFiles</span></span>
    
      - <span data-ttu-id="987e4-150">MSIL% systemroot\\%\\Microsoft.NET\\Assembly\_GAC</span><span class="sxs-lookup"><span data-stu-id="987e4-150">%systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL</span></span>
    
      - <span data-ttu-id="987e4-151">% ProgramFiles%\\Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="987e4-151">%programfiles%\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="987e4-152">% ProgramFiles%\\общие файлы\\, узел наблюдателя Microsoft\\Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="987e4-152">%programfiles%\\Common Files\\Microsoft Lync Server 2013\\Watcher Node</span></span>
    
      - <span data-ttu-id="987e4-153">% ProgramFiles%\\распространенных файлов\\в Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="987e4-153">%programfiles%\\Common Files\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="987e4-154">% SystemDrive%\\рткрепликарут</span><span class="sxs-lookup"><span data-stu-id="987e4-154">%SystemDrive%\\RtcReplicaRoot</span></span>
    
      - <span data-ttu-id="987e4-155">Хранилище общих папок (указывается в построителе топологий).</span><span class="sxs-lookup"><span data-stu-id="987e4-155">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="987e4-156">Хранилища файлов задаются в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="987e4-156">File stores are specified in Topology Builder.</span></span>
    
      - <span data-ttu-id="987e4-157">Файлы данных и журналов сервера SQL Server, включая объекты внутренней базы данных, хранилища пользователей, архивов, мониторинга и приложений.</span><span class="sxs-lookup"><span data-stu-id="987e4-157">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="987e4-158">Файлы баз данных и журналов можно указать в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="987e4-158">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="987e4-159">Дополнительные сведения о файлах данных и журналов для каждой базы данных, включая имена по умолчанию, можно найти в разделе [данные и расположение файлов журнала SQL Server для Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="987e4-159">For details about the data and log files for each database, including default names, see [SQL Server data and log file placement for Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="987e4-160">Файлы данных и журналов SQL Server, в том числе для интерфейсной базы данных, магазина Lync и Рткдатабасе Store.</span><span class="sxs-lookup"><span data-stu-id="987e4-160">SQL Server data and log files, including those for the Front-end database, Lync store, and RtcDatabase store.</span></span> <span data-ttu-id="987e4-161">Обычно они находятся в рамках% локалдриве\\% ксдата.</span><span class="sxs-lookup"><span data-stu-id="987e4-161">They are normally under %localdrive%\\CSData.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

