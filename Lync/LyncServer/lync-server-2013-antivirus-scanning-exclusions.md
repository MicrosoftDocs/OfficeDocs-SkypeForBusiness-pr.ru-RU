---
title: 'Lync Server 2013: исключения антивирусной проверки'
description: 'Lync Server 2013: исключения антивирусной проверки.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Antivirus scanning exclusions for Lync Server 2013
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440138(v=OCS.15)
ms:contentKeyID: 57793042
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20c395f529cad91993d003efdeb231bd66f4b9bc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561915"
---
# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a><span data-ttu-id="10483-103">Исключения антивирусной проверки для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10483-103">Antivirus scanning exclusions for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10483-104">_**Последнее изменение темы:** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="10483-104">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="10483-105">Чтобы антивирусное программное обеспечение не влияло на работу Lync Server 2013, необходимо исключить конкретные процессы и каталоги для каждого сервера или роли сервера Lync Server 2013, на которых запускается антивирусное программное обеспечение.</span><span class="sxs-lookup"><span data-stu-id="10483-105">To ensure that the antivirus scanner does not interfere with the operation of Lync Server 2013, you must exclude specific processes and directories for each Lync Server 2013 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="10483-106">Необходимо исключить следующие процессы и каталоги:</span><span class="sxs-lookup"><span data-stu-id="10483-106">The following processes and directories should be excluded:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="10483-107">Ниже указаны расположения файлов и папок по умолчанию для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="10483-107">Folder and file locations listed below are the default locations for Lync Server 2013.</span></span> <span data-ttu-id="10483-108">Для всех расположений, для которых не использовалось значение по умолчанию, исключите расположения, указанные для Организации, вместо расположений по умолчанию, указанных в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="10483-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="10483-109">Обратите внимание на то, что некоторым антивирусным программам могут понадобиться абсолютные, не относительные пути, для списка исключений.</span><span class="sxs-lookup"><span data-stu-id="10483-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>



</div>

  - <span data-ttu-id="10483-110">Lync Server 2013 процессы:</span><span class="sxs-lookup"><span data-stu-id="10483-110">Lync Server 2013 processes:</span></span>
    
      - <span data-ttu-id="10483-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="10483-111">ABServer.exe</span></span>
    
      - <span data-ttu-id="10483-112">AcpMcuSvc.exe</span><span class="sxs-lookup"><span data-stu-id="10483-112">AcpMcuSvc.exe</span></span>
    
      - <span data-ttu-id="10483-113">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="10483-113">ASMCUSvc.exe</span></span>
    
      - <span data-ttu-id="10483-114">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="10483-114">AVMCUSvc.exe</span></span>
    
      - <span data-ttu-id="10483-115">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="10483-115">ChannelService.exe</span></span>
    
      - <span data-ttu-id="10483-116">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="10483-116">ClsAgent.exe</span></span>
    
      - <span data-ttu-id="10483-117">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="10483-117">ComplianceService.exe</span></span>
    
      - <span data-ttu-id="10483-118">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="10483-118">DataMCUSvc.exe</span></span>
    
      - <span data-ttu-id="10483-119">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="10483-119">DataProxy.exe</span></span>
    
      - <span data-ttu-id="10483-120">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="10483-120">FileTransferAgent.exe</span></span>
    
      - <span data-ttu-id="10483-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="10483-121">IMMCUSvc.exe</span></span>
    
      - <span data-ttu-id="10483-122">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="10483-122">LysSvc.exe</span></span>
    
      - <span data-ttu-id="10483-123">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="10483-123">MasterReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="10483-124">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="10483-124">MediaRelaySvc.exe</span></span>
    
      - <span data-ttu-id="10483-125">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="10483-125">MediationServerSvc.exe</span></span>
    
      - <span data-ttu-id="10483-126">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="10483-126">MRASSvc.exe</span></span>
    
      - <span data-ttu-id="10483-127">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="10483-127">OcsAppServerHost.exe</span></span>
    
      - <span data-ttu-id="10483-128">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="10483-128">ReplicaReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="10483-129">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="10483-129">ReplicationApp.exe</span></span>
    
      - <span data-ttu-id="10483-130">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="10483-130">RtcHost.exe</span></span>
    
      - <span data-ttu-id="10483-131">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="10483-131">RTCSrv.exe</span></span>
    
      - <span data-ttu-id="10483-132">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="10483-132">XmppProxy.exe</span></span>
    
      - <span data-ttu-id="10483-133">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="10483-133">XmppTGW.exe</span></span>

  - <span data-ttu-id="10483-134">Процессы службы узла Windows Fabric:</span><span class="sxs-lookup"><span data-stu-id="10483-134">Windows Fabric Host Service processes:</span></span>
    
      - <span data-ttu-id="10483-135">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="10483-135">Fabric.exe</span></span>
    
      - <span data-ttu-id="10483-136">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="10483-136">FabricDCA.exe</span></span>
    
      - <span data-ttu-id="10483-137">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="10483-137">FabricHost.exe</span></span>

  - <span data-ttu-id="10483-138">Процессы IIS:</span><span class="sxs-lookup"><span data-stu-id="10483-138">IIS processes:</span></span>
    
      - <span data-ttu-id="10483-139">% SystemRoot% \\ system32 \\ инетсрв \\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="10483-139">%systemroot%\\system32\\inetsrv\\w3wp.exe</span></span>
    
      - <span data-ttu-id="10483-140">% SystemRoot% \\ SysWOW64 \\ инетсрв \\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="10483-140">%systemroot%\\SysWOW64\\inetsrv\\w3wp.exe</span></span>

  - <span data-ttu-id="10483-141">Процессы Back-End SQL Server:</span><span class="sxs-lookup"><span data-stu-id="10483-141">SQL Server Back-End processes:</span></span>
    
      - <span data-ttu-id="10483-142">% ProgramFiles% \\ Microsoft SQL Server \\ MSSQL11. MSSQLSERVER \\ MSSQL \\ бинн \\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="10483-142">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.MSSQLSERVER\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="10483-143">% ProgramFiles% \\ Microsoft SQL Server \\ MSRS11. \\ \\ \\ReportingServicesService.exe корзины служб отчетов MSSQLSERVER \\</span><span class="sxs-lookup"><span data-stu-id="10483-143">%ProgramFiles%\\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService.exe</span></span>
    
      - <span data-ttu-id="10483-144">% ProgramFiles% \\ Microsoft SQL Server \\ MSAS11. \\ \\MSMDSrv.exe корзины для MSSQLSERVER OLAP \\</span><span class="sxs-lookup"><span data-stu-id="10483-144">%ProgramFiles%\\Microsoft SQL Server\\MSAS11.MSSQLSERVER\\OLAP\\Bin\\MSMDSrv.exe</span></span>

  - <span data-ttu-id="10483-145">Процессы Front-End SQL Server:</span><span class="sxs-lookup"><span data-stu-id="10483-145">SQL Server Front-End processes:</span></span>
    
      - <span data-ttu-id="10483-146">% ProgramFiles% \\ Microsoft SQL Server \\ MSSQL11. ЛИНКЛОКАЛ \\ MSSQL \\ бинн \\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="10483-146">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.LYNCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="10483-147">% ProgramFiles% \\ Microsoft SQL Server \\ MSSQL11. RTCLOCAL \\ MSSQL \\ бинн \\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="10483-147">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.RTCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>

  - <span data-ttu-id="10483-148">Каталоги и файлы:</span><span class="sxs-lookup"><span data-stu-id="10483-148">Directories and files:</span></span>
    
      - <span data-ttu-id="10483-149">% SystemRoot% \\ system32 файлов \\ журнала</span><span class="sxs-lookup"><span data-stu-id="10483-149">%systemroot%\\System32\\LogFiles</span></span>
    
      - <span data-ttu-id="10483-150">% SystemRoot% \\ SysWOW64 файлов \\ журнала</span><span class="sxs-lookup"><span data-stu-id="10483-150">%systemroot%\\SysWow64\\LogFiles</span></span>
    
      - <span data-ttu-id="10483-151">% SystemRoot% \\ Microsoft.NET \\ сборки \\ GAC \_</span><span class="sxs-lookup"><span data-stu-id="10483-151">%systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL</span></span>
    
      - <span data-ttu-id="10483-152">% ProgramFiles% \\ Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10483-152">%programfiles%\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="10483-153">% ProgramFiles% \\ общих файлов для \\ узла-наблюдателя Microsoft Lync Server 2013 \\</span><span class="sxs-lookup"><span data-stu-id="10483-153">%programfiles%\\Common Files\\Microsoft Lync Server 2013\\Watcher Node</span></span>
    
      - <span data-ttu-id="10483-154">% ProgramFiles% \\ общих файлов, \\ Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10483-154">%programfiles%\\Common Files\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="10483-155">% SystemDrive% \\ рткрепликарут</span><span class="sxs-lookup"><span data-stu-id="10483-155">%SystemDrive%\\RtcReplicaRoot</span></span>
    
      - <span data-ttu-id="10483-156">Хранилище файлового ресурса (указано в построителе топологий).</span><span class="sxs-lookup"><span data-stu-id="10483-156">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="10483-157">Хранилища файлов указываются в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="10483-157">File stores are specified in Topology Builder.</span></span>
    
      - <span data-ttu-id="10483-158">Файлы данных и журналов SQL Server, в том числе для серверной базы данных, хранилища пользователей, архивного хранилища, мониторинга и хранилища приложений.</span><span class="sxs-lookup"><span data-stu-id="10483-158">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="10483-159">В построителе топологий можно указать файлы баз данных и журналов.</span><span class="sxs-lookup"><span data-stu-id="10483-159">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="10483-160">Сведения о файлах данных и журналов для каждой базы данных, включая имена по умолчанию, можно найти в разделе [Data SQL Server and File log Placement for Lync server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="10483-160">For details about the data and log files for each database, including default names, see [SQL Server data and log file placement for Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="10483-161">Файлы данных и журналов SQL Server, в том числе для интерфейсной базы данных, магазина Lync и хранилища Рткдатабасе.</span><span class="sxs-lookup"><span data-stu-id="10483-161">SQL Server data and log files, including those for the Front-end database, Lync store, and RtcDatabase store.</span></span> <span data-ttu-id="10483-162">Обычно они находятся в папке% локалдриве% \\ ксдата.</span><span class="sxs-lookup"><span data-stu-id="10483-162">They are normally under %localdrive%\\CSData.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

