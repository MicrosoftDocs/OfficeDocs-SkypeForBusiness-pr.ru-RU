---
title: Исключения из антивирусной проверки для Skype для бизнеса Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/24/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Обзор взаимодействия антивирусную программу с Скайп для Business Server 2015.
ms.openlocfilehash: bb188b25c61269ee7c38829e1887a3443a0f77c4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server-2015"></a><span data-ttu-id="96760-103">Исключения из антивирусной проверки для Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="96760-103">Antivirus scanning exclusions for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="96760-104">Обзор взаимодействия антивирусную программу с Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="96760-104">Overview of antivirus scanner interoperation with Skype for Business Server 2015.</span></span> 
  
<span data-ttu-id="96760-105">Чтобы убедиться, что антивирусную программу не влияет на операции Скайп для Business Server 2015, необходимо исключить конкретные процессы и каталоги для каждого Скайп для Business Server 2015 сервер или роль сервера, на котором выполняется антивирусную программу.</span><span class="sxs-lookup"><span data-stu-id="96760-105">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server 2015, you must exclude specific processes and directories for each Skype for Business Server 2015 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="96760-106">Исключите перечисленные ниже процессы и каталоги.</span><span class="sxs-lookup"><span data-stu-id="96760-106">The following processes and directories should be excluded:</span></span>
  
> [!NOTE]
> <span data-ttu-id="96760-107">Папка и файл расположения, перечисленных ниже — это расположение по умолчанию для Скайп Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="96760-107">Folder and file locations listed below are the default locations for Skype for Business Server 2015.</span></span> <span data-ttu-id="96760-108">Если в вашей организации какие-либо из этих объектов расположены в других местах, укажите соответствующие пути.</span><span class="sxs-lookup"><span data-stu-id="96760-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="96760-109">Обратите внимание, что в некоторых антивирусных программах в списке исключений необходимо указывать абсолютные пути, а не относительные.</span><span class="sxs-lookup"><span data-stu-id="96760-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span> 
  
- <span data-ttu-id="96760-110">Скайп для процессов Business Server 2015:</span><span class="sxs-lookup"><span data-stu-id="96760-110">Skype for Business Server 2015 processes:</span></span>
    
  - <span data-ttu-id="96760-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="96760-111">ABServer.exe</span></span>
    
  - <span data-ttu-id="96760-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="96760-112">ASMCUSvc.exe</span></span>
    
  - <span data-ttu-id="96760-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="96760-113">AVMCUSvc.exe</span></span>
    
  - <span data-ttu-id="96760-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="96760-114">ChannelService.exe</span></span>
    
  - <span data-ttu-id="96760-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="96760-115">ClsAgent.exe</span></span>
    
  - <span data-ttu-id="96760-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="96760-116">ComplianceService.exe</span></span>
    
  - <span data-ttu-id="96760-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="96760-117">DataMCUSvc.exe</span></span>
    
  - <span data-ttu-id="96760-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="96760-118">DataProxy.exe</span></span>
    
  - <span data-ttu-id="96760-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="96760-119">FileTransferAgent.exe</span></span>
    
  - <span data-ttu-id="96760-120">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="96760-120">HealthAgent.exe</span></span>
    
  - <span data-ttu-id="96760-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="96760-121">IMMCUSvc.exe</span></span>
    
  - <span data-ttu-id="96760-122">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="96760-122">LysSvc.exe</span></span>
    
  - <span data-ttu-id="96760-123">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="96760-123">MasterReplicatorAgent.exe</span></span>
    
  - <span data-ttu-id="96760-124">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="96760-124">MediaRelaySvc.exe</span></span>
    
  - <span data-ttu-id="96760-125">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="96760-125">MediationServerSvc.exe</span></span>
    
  - <span data-ttu-id="96760-126">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="96760-126">MRASSvc.exe</span></span>
    
  - <span data-ttu-id="96760-127">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="96760-127">OcsAppServerHost.exe</span></span>
    
  - <span data-ttu-id="96760-128">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="96760-128">ReplicaReplicatorAgent.exe</span></span>
    
  - <span data-ttu-id="96760-129">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="96760-129">ReplicationApp.exe</span></span>
    
  - <span data-ttu-id="96760-130">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="96760-130">RtcHost.exe</span></span>
    
  - <span data-ttu-id="96760-131">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="96760-131">RTCSrv.exe</span></span>
    
  - <span data-ttu-id="96760-132">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="96760-132">XmppProxy.exe</span></span>
    
  - <span data-ttu-id="96760-133">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="96760-133">XmppTGW.exe</span></span>
    
- <span data-ttu-id="96760-134">Процессы службы узла Windows Fabric</span><span class="sxs-lookup"><span data-stu-id="96760-134">Windows Fabric Host Service processes:</span></span>
    
  - <span data-ttu-id="96760-135">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="96760-135">Fabric.exe</span></span>
    
  - <span data-ttu-id="96760-136">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="96760-136">FabricDCA.exe</span></span>
    
  - <span data-ttu-id="96760-137">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="96760-137">FabricHost.exe</span></span>
    
- <span data-ttu-id="96760-138">Процессы IIS</span><span class="sxs-lookup"><span data-stu-id="96760-138">IIS processes:</span></span>
    
  - <span data-ttu-id="96760-139">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="96760-139">%systemroot%\system32\inetsrv\w3wp.exe</span></span>
    
  - <span data-ttu-id="96760-140">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="96760-140">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>
    
- <span data-ttu-id="96760-141">Внутренние процессы сервера SQL Server</span><span class="sxs-lookup"><span data-stu-id="96760-141">SQL Server Back-End processes:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="96760-142">Обратите внимание, что эти пути зависят от версии SQL Server.</span><span class="sxs-lookup"><span data-stu-id="96760-142">Note that these paths are specific to SQL Server version.</span></span> 
  
  - <span data-ttu-id="96760-143">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="96760-143">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>
    
  - <span data-ttu-id="96760-144">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="96760-144">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>
    
  - <span data-ttu-id="96760-145">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="96760-145">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>
    
- <span data-ttu-id="96760-146">Внешние процессы сервера SQL Server</span><span class="sxs-lookup"><span data-stu-id="96760-146">SQL Server Front-End processes:</span></span>
    
  - <span data-ttu-id="96760-147">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="96760-147">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>
    
  - <span data-ttu-id="96760-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="96760-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>
    
  - <span data-ttu-id="96760-149">Экземпляр RTC установки Standard Edition</span><span class="sxs-lookup"><span data-stu-id="96760-149">Standard Edition Installation RTC Instance</span></span> 
    
  - <span data-ttu-id="96760-150">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="96760-150">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>
    
- <span data-ttu-id="96760-151">Каталоги и файлы</span><span class="sxs-lookup"><span data-stu-id="96760-151">Directories and files:</span></span>
    
  - <span data-ttu-id="96760-152">%systemroot%\system32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="96760-152">%systemroot%\System32\LogFiles</span></span>
    
  - <span data-ttu-id="96760-153">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="96760-153">%systemroot%\SysWow64\LogFiles</span></span>
    
  - <span data-ttu-id="96760-154">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="96760-154">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>
    
  - <span data-ttu-id="96760-155">%programfiles%\Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="96760-155">%programfiles%\Skype for Business Server 2015</span></span>
    
  - <span data-ttu-id="96760-156">%programfiles%\Common Files\Skype для бизнеса Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="96760-156">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>
    
  - <span data-ttu-id="96760-157">%programfiles%\Common Files\Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="96760-157">%programfiles%\Common Files\Skype for Business Server 2015</span></span>
    
  - <span data-ttu-id="96760-158">%programfiles%\Common Files\Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="96760-158">%programfiles%\Common Files\Skype for Business Online</span></span>
    
  - <span data-ttu-id="96760-159">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="96760-159">%SystemDrive%\RtcReplicaRoot</span></span>
    
  - <span data-ttu-id="96760-p103">Хранилище общих папок (указывается в построителе топологий). Хранилища файлов задаются в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="96760-p103">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>
    
  - <span data-ttu-id="96760-162">Файлы данных и журналов сервера SQL Server, включая объекты внутренней базы данных, хранилища пользователей, архивов, мониторинга и приложений.</span><span class="sxs-lookup"><span data-stu-id="96760-162">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="96760-163">Файлы баз данных и журналов можно указать в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="96760-163">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="96760-164">Для получения дополнительных сведений о файлах данных и журналов для каждой базы данных, включая имена по умолчанию содержатся в документации по развертыванию [данных SQL Server и размещение файлов журнала](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) .</span><span class="sxs-lookup"><span data-stu-id="96760-164">For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>
    
  - <span data-ttu-id="96760-165">SQL Server файлов данных и журналов, в том числе для интерфейсных базы данных, Скайп для хранения бизнес и RtcDatabase хранилища.</span><span class="sxs-lookup"><span data-stu-id="96760-165">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="96760-166">Как правило, они находятся в папке %localdrive%\CSData.</span><span class="sxs-lookup"><span data-stu-id="96760-166">They are normally under %localdrive%\CSData.</span></span>
    

