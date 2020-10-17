---
title: 'Lync Server 2013: исключения антивирусной проверки'
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
ms.openlocfilehash: 4b67f1472bbb8225bf952b5b678bcae8401d211d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508976"
---
# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a><span data-ttu-id="83433-102">Исключения антивирусной проверки для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83433-102">Antivirus scanning exclusions for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83433-103">_**Последнее изменение темы:** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="83433-103">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="83433-104">Чтобы антивирусное программное обеспечение не влияло на работу Lync Server 2013, необходимо исключить конкретные процессы и каталоги для каждого сервера или роли сервера Lync Server 2013, на которых запускается антивирусное программное обеспечение.</span><span class="sxs-lookup"><span data-stu-id="83433-104">To ensure that the antivirus scanner does not interfere with the operation of Lync Server 2013, you must exclude specific processes and directories for each Lync Server 2013 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="83433-105">Необходимо исключить следующие процессы и каталоги:</span><span class="sxs-lookup"><span data-stu-id="83433-105">The following processes and directories should be excluded:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="83433-106">Ниже указаны расположения файлов и папок по умолчанию для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="83433-106">Folder and file locations listed below are the default locations for Lync Server 2013.</span></span> <span data-ttu-id="83433-107">Для всех расположений, для которых не использовалось значение по умолчанию, исключите расположения, указанные для Организации, вместо расположений по умолчанию, указанных в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="83433-107">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="83433-108">Обратите внимание на то, что некоторым антивирусным программам могут понадобиться абсолютные, не относительные пути, для списка исключений.</span><span class="sxs-lookup"><span data-stu-id="83433-108">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>



</div>

  - <span data-ttu-id="83433-109">Lync Server 2013 процессы:</span><span class="sxs-lookup"><span data-stu-id="83433-109">Lync Server 2013 processes:</span></span>
    
      - <span data-ttu-id="83433-110">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="83433-110">ABServer.exe</span></span>
    
      - <span data-ttu-id="83433-111">AcpMcuSvc.exe</span><span class="sxs-lookup"><span data-stu-id="83433-111">AcpMcuSvc.exe</span></span>
    
      - <span data-ttu-id="83433-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="83433-112">ASMCUSvc.exe</span></span>
    
      - <span data-ttu-id="83433-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="83433-113">AVMCUSvc.exe</span></span>
    
      - <span data-ttu-id="83433-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="83433-114">ChannelService.exe</span></span>
    
      - <span data-ttu-id="83433-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="83433-115">ClsAgent.exe</span></span>
    
      - <span data-ttu-id="83433-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="83433-116">ComplianceService.exe</span></span>
    
      - <span data-ttu-id="83433-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="83433-117">DataMCUSvc.exe</span></span>
    
      - <span data-ttu-id="83433-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="83433-118">DataProxy.exe</span></span>
    
      - <span data-ttu-id="83433-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="83433-119">FileTransferAgent.exe</span></span>
    
      - <span data-ttu-id="83433-120">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="83433-120">IMMCUSvc.exe</span></span>
    
      - <span data-ttu-id="83433-121">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="83433-121">LysSvc.exe</span></span>
    
      - <span data-ttu-id="83433-122">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="83433-122">MasterReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="83433-123">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="83433-123">MediaRelaySvc.exe</span></span>
    
      - <span data-ttu-id="83433-124">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="83433-124">MediationServerSvc.exe</span></span>
    
      - <span data-ttu-id="83433-125">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="83433-125">MRASSvc.exe</span></span>
    
      - <span data-ttu-id="83433-126">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="83433-126">OcsAppServerHost.exe</span></span>
    
      - <span data-ttu-id="83433-127">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="83433-127">ReplicaReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="83433-128">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="83433-128">ReplicationApp.exe</span></span>
    
      - <span data-ttu-id="83433-129">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="83433-129">RtcHost.exe</span></span>
    
      - <span data-ttu-id="83433-130">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="83433-130">RTCSrv.exe</span></span>
    
      - <span data-ttu-id="83433-131">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="83433-131">XmppProxy.exe</span></span>
    
      - <span data-ttu-id="83433-132">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="83433-132">XmppTGW.exe</span></span>

  - <span data-ttu-id="83433-133">Процессы службы узла Windows Fabric:</span><span class="sxs-lookup"><span data-stu-id="83433-133">Windows Fabric Host Service processes:</span></span>
    
      - <span data-ttu-id="83433-134">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="83433-134">Fabric.exe</span></span>
    
      - <span data-ttu-id="83433-135">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="83433-135">FabricDCA.exe</span></span>
    
      - <span data-ttu-id="83433-136">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="83433-136">FabricHost.exe</span></span>

  - <span data-ttu-id="83433-137">Процессы IIS:</span><span class="sxs-lookup"><span data-stu-id="83433-137">IIS processes:</span></span>
    
      - <span data-ttu-id="83433-138">% SystemRoot% \\ system32 \\ инетсрв \\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="83433-138">%systemroot%\\system32\\inetsrv\\w3wp.exe</span></span>
    
      - <span data-ttu-id="83433-139">% SystemRoot% \\ SysWOW64 \\ инетсрв \\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="83433-139">%systemroot%\\SysWOW64\\inetsrv\\w3wp.exe</span></span>

  - <span data-ttu-id="83433-140">Процессы Back-End SQL Server:</span><span class="sxs-lookup"><span data-stu-id="83433-140">SQL Server Back-End processes:</span></span>
    
      - <span data-ttu-id="83433-141">% ProgramFiles% \\ Microsoft SQL Server \\ MSSQL11. MSSQLSERVER \\ MSSQL \\ бинн \\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="83433-141">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.MSSQLSERVER\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="83433-142">% ProgramFiles% \\ Microsoft SQL Server \\ MSRS11. \\ \\ \\ReportingServicesService.exe корзины служб отчетов MSSQLSERVER \\</span><span class="sxs-lookup"><span data-stu-id="83433-142">%ProgramFiles%\\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService.exe</span></span>
    
      - <span data-ttu-id="83433-143">% ProgramFiles% \\ Microsoft SQL Server \\ MSAS11. \\ \\MSMDSrv.exe корзины для MSSQLSERVER OLAP \\</span><span class="sxs-lookup"><span data-stu-id="83433-143">%ProgramFiles%\\Microsoft SQL Server\\MSAS11.MSSQLSERVER\\OLAP\\Bin\\MSMDSrv.exe</span></span>

  - <span data-ttu-id="83433-144">Процессы Front-End SQL Server:</span><span class="sxs-lookup"><span data-stu-id="83433-144">SQL Server Front-End processes:</span></span>
    
      - <span data-ttu-id="83433-145">% ProgramFiles% \\ Microsoft SQL Server \\ MSSQL11. ЛИНКЛОКАЛ \\ MSSQL \\ бинн \\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="83433-145">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.LYNCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="83433-146">% ProgramFiles% \\ Microsoft SQL Server \\ MSSQL11. RTCLOCAL \\ MSSQL \\ бинн \\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="83433-146">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.RTCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>

  - <span data-ttu-id="83433-147">Каталоги и файлы:</span><span class="sxs-lookup"><span data-stu-id="83433-147">Directories and files:</span></span>
    
      - <span data-ttu-id="83433-148">% SystemRoot% \\ system32 файлов \\ журнала</span><span class="sxs-lookup"><span data-stu-id="83433-148">%systemroot%\\System32\\LogFiles</span></span>
    
      - <span data-ttu-id="83433-149">% SystemRoot% \\ SysWOW64 файлов \\ журнала</span><span class="sxs-lookup"><span data-stu-id="83433-149">%systemroot%\\SysWow64\\LogFiles</span></span>
    
      - <span data-ttu-id="83433-150">% SystemRoot% \\ Microsoft.NET \\ сборки \\ GAC \_</span><span class="sxs-lookup"><span data-stu-id="83433-150">%systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL</span></span>
    
      - <span data-ttu-id="83433-151">% ProgramFiles% \\ Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83433-151">%programfiles%\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="83433-152">% ProgramFiles% \\ общих файлов для \\ узла-наблюдателя Microsoft Lync Server 2013 \\</span><span class="sxs-lookup"><span data-stu-id="83433-152">%programfiles%\\Common Files\\Microsoft Lync Server 2013\\Watcher Node</span></span>
    
      - <span data-ttu-id="83433-153">% ProgramFiles% \\ общих файлов, \\ Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83433-153">%programfiles%\\Common Files\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="83433-154">% SystemDrive% \\ рткрепликарут</span><span class="sxs-lookup"><span data-stu-id="83433-154">%SystemDrive%\\RtcReplicaRoot</span></span>
    
      - <span data-ttu-id="83433-155">Хранилище файлового ресурса (указано в построителе топологий).</span><span class="sxs-lookup"><span data-stu-id="83433-155">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="83433-156">Хранилища файлов указываются в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="83433-156">File stores are specified in Topology Builder.</span></span>
    
      - <span data-ttu-id="83433-157">Файлы данных и журналов SQL Server, в том числе для серверной базы данных, хранилища пользователей, архивного хранилища, мониторинга и хранилища приложений.</span><span class="sxs-lookup"><span data-stu-id="83433-157">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="83433-158">В построителе топологий можно указать файлы баз данных и журналов.</span><span class="sxs-lookup"><span data-stu-id="83433-158">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="83433-159">Сведения о файлах данных и журналов для каждой базы данных, включая имена по умолчанию, можно найти в разделе [Data SQL Server and File log Placement for Lync server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="83433-159">For details about the data and log files for each database, including default names, see [SQL Server data and log file placement for Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="83433-160">Файлы данных и журналов SQL Server, в том числе для интерфейсной базы данных, магазина Lync и хранилища Рткдатабасе.</span><span class="sxs-lookup"><span data-stu-id="83433-160">SQL Server data and log files, including those for the Front-end database, Lync store, and RtcDatabase store.</span></span> <span data-ttu-id="83433-161">Обычно они находятся в папке% локалдриве% \\ ксдата.</span><span class="sxs-lookup"><span data-stu-id="83433-161">They are normally under %localdrive%\\CSData.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

