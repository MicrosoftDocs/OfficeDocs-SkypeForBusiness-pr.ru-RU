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
ms.openlocfilehash: 054ed03146964de7ec0621138186e3c41843c236
ms.sourcegitcommit: 1cb8ab7d1e3debb84f051be404403e4a116ee741
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2018
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server-2015"></a><span data-ttu-id="f32ee-103">Исключения из антивирусной проверки для Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="f32ee-103">Antivirus scanning exclusions for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f32ee-104">Обзор взаимодействия антивирусную программу с Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f32ee-104">Overview of antivirus scanner interoperation with Skype for Business Server 2015.</span></span>

<span data-ttu-id="f32ee-105">В этой статье представлены рекомендации, которые могут помочь определить причину нестабильной на компьютере, на котором выполняется поддерживаемая версия Microsoft Windows при использовании с помощью антивирусных программ в домене Active Directory администратора среда или управляемой бизнес-среде.</span><span class="sxs-lookup"><span data-stu-id="f32ee-105">This article contains recommendations that may help an administrator determine the cause of potential instability on a computer that is running a supported version of Microsoft Windows when it is used with antivirus software in an Active Directory domain environment or in a managed business environment.</span></span>

<span data-ttu-id="f32ee-106">Мы рекомендуем временно применяются следующие действия, чтобы оценить в системе.</span><span class="sxs-lookup"><span data-stu-id="f32ee-106">We recommend that you temporarily apply these procedures to evaluate a system.</span></span> <span data-ttu-id="f32ee-107">Если производительность системы или стабильность улучшена благодаря рекомендации, которые выполняются в этой статье, обратитесь к поставщику антивирусной программы за инструкциями или обновленной версией антивирусное программное обеспечение.</span><span class="sxs-lookup"><span data-stu-id="f32ee-107">If your system performance or stability is improved by the recommendations that are made in this article, contact your antivirus software vendor for instructions or for an updated version of the antivirus software.</span></span>

<span data-ttu-id="f32ee-108">Эта статья содержит сведения, показано, как снижении уровня безопасности или временно отключить функции безопасности на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f32ee-108">This article contains information that shows how to help lower security settings or how to temporarily turn off security features on a computer.</span></span> <span data-ttu-id="f32ee-109">Можно внести эти изменения, чтобы понять причину конкретной проблемы.</span><span class="sxs-lookup"><span data-stu-id="f32ee-109">You can make these changes to understand the nature of a specific problem.</span></span> <span data-ttu-id="f32ee-110">Прежде чем вносить изменения, рекомендуется оценить риски, связанные с ними в существующей среде.</span><span class="sxs-lookup"><span data-stu-id="f32ee-110">Before you make these changes, we recommend that you evaluate the risks that are associated with implementing this workaround in your particular environment.</span></span> <span data-ttu-id="f32ee-111">Если данный метод обхода, выполните все необходимые дополнительные меры для защиты компьютера и поиск файлов, которые больше не сканируются антивирусной программой.</span><span class="sxs-lookup"><span data-stu-id="f32ee-111">If you implement this workaround, take any appropriate additional steps to help protect the computer for the files that are no longer being scanned by your antivirus software.</span></span>
  
<span data-ttu-id="f32ee-112">Чтобы убедиться, что антивирусную программу не влияет на операции Скайп для Business Server 2015, необходимо исключить конкретные процессы и каталоги для каждого Скайп для Business Server 2015 сервер или роль сервера, на котором выполняется антивирусную программу.</span><span class="sxs-lookup"><span data-stu-id="f32ee-112">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server 2015, you must exclude specific processes and directories for each Skype for Business Server 2015 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="f32ee-113">Исключите перечисленные ниже процессы и каталоги.</span><span class="sxs-lookup"><span data-stu-id="f32ee-113">The following processes and directories should be excluded:</span></span>
  
> [!NOTE]
> <span data-ttu-id="f32ee-114">Папка и файл расположения, перечисленных ниже — это расположение по умолчанию для Скайп Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f32ee-114">Folder and file locations listed below are the default locations for Skype for Business Server 2015.</span></span> <span data-ttu-id="f32ee-115">Если в вашей организации какие-либо из этих объектов расположены в других местах, укажите соответствующие пути.</span><span class="sxs-lookup"><span data-stu-id="f32ee-115">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="f32ee-116">Обратите внимание, что в некоторых антивирусных программах в списке исключений необходимо указывать абсолютные пути, а не относительные.</span><span class="sxs-lookup"><span data-stu-id="f32ee-116">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span> 
  
- <span data-ttu-id="f32ee-117">Скайп для процессов Business Server 2015:</span><span class="sxs-lookup"><span data-stu-id="f32ee-117">Skype for Business Server 2015 processes:</span></span>
    
  - <span data-ttu-id="f32ee-118">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="f32ee-118">ABServer.exe</span></span>
    
  - <span data-ttu-id="f32ee-119">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="f32ee-119">ASMCUSvc.exe</span></span>
    
  - <span data-ttu-id="f32ee-120">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="f32ee-120">AVMCUSvc.exe</span></span>
    
  - <span data-ttu-id="f32ee-121">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="f32ee-121">ChannelService.exe</span></span>
    
  - <span data-ttu-id="f32ee-122">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="f32ee-122">ClsAgent.exe</span></span>
    
  - <span data-ttu-id="f32ee-123">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="f32ee-123">ComplianceService.exe</span></span>
    
  - <span data-ttu-id="f32ee-124">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="f32ee-124">DataMCUSvc.exe</span></span>
    
  - <span data-ttu-id="f32ee-125">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="f32ee-125">DataProxy.exe</span></span>
    
  - <span data-ttu-id="f32ee-126">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="f32ee-126">FileTransferAgent.exe</span></span>
    
  - <span data-ttu-id="f32ee-127">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="f32ee-127">HealthAgent.exe</span></span>
    
  - <span data-ttu-id="f32ee-128">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="f32ee-128">IMMCUSvc.exe</span></span>
    
  - <span data-ttu-id="f32ee-129">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="f32ee-129">LysSvc.exe</span></span>
    
  - <span data-ttu-id="f32ee-130">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="f32ee-130">MasterReplicatorAgent.exe</span></span>
    
  - <span data-ttu-id="f32ee-131">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="f32ee-131">MediaRelaySvc.exe</span></span>
    
  - <span data-ttu-id="f32ee-132">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="f32ee-132">MediationServerSvc.exe</span></span>
    
  - <span data-ttu-id="f32ee-133">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="f32ee-133">MRASSvc.exe</span></span>
    
  - <span data-ttu-id="f32ee-134">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="f32ee-134">OcsAppServerHost.exe</span></span>
    
  - <span data-ttu-id="f32ee-135">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="f32ee-135">ReplicaReplicatorAgent.exe</span></span>
    
  - <span data-ttu-id="f32ee-136">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="f32ee-136">ReplicationApp.exe</span></span>
    
  - <span data-ttu-id="f32ee-137">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="f32ee-137">RtcHost.exe</span></span>
    
  - <span data-ttu-id="f32ee-138">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="f32ee-138">RTCSrv.exe</span></span>
    
  - <span data-ttu-id="f32ee-139">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="f32ee-139">XmppProxy.exe</span></span>
    
  - <span data-ttu-id="f32ee-140">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="f32ee-140">XmppTGW.exe</span></span>
    
- <span data-ttu-id="f32ee-141">Процессы службы узла Windows Fabric</span><span class="sxs-lookup"><span data-stu-id="f32ee-141">Windows Fabric Host Service processes:</span></span>
    
  - <span data-ttu-id="f32ee-142">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="f32ee-142">Fabric.exe</span></span>
    
  - <span data-ttu-id="f32ee-143">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="f32ee-143">FabricDCA.exe</span></span>
    
  - <span data-ttu-id="f32ee-144">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="f32ee-144">FabricHost.exe</span></span>
    
- <span data-ttu-id="f32ee-145">Процессы IIS</span><span class="sxs-lookup"><span data-stu-id="f32ee-145">IIS processes:</span></span>
    
  - <span data-ttu-id="f32ee-146">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="f32ee-146">%systemroot%\system32\inetsrv\w3wp.exe</span></span>
    
  - <span data-ttu-id="f32ee-147">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="f32ee-147">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>
    
- <span data-ttu-id="f32ee-148">Внутренние процессы сервера SQL Server</span><span class="sxs-lookup"><span data-stu-id="f32ee-148">SQL Server Back-End processes:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f32ee-149">Обратите внимание, что эти пути зависят от версии SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f32ee-149">Note that these paths are specific to SQL Server version.</span></span> 
  
  - <span data-ttu-id="f32ee-150">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="f32ee-150">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>
    
  - <span data-ttu-id="f32ee-151">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="f32ee-151">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>
    
  - <span data-ttu-id="f32ee-152">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="f32ee-152">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>
    
- <span data-ttu-id="f32ee-153">Внешние процессы сервера SQL Server</span><span class="sxs-lookup"><span data-stu-id="f32ee-153">SQL Server Front-End processes:</span></span>
    
  - <span data-ttu-id="f32ee-154">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="f32ee-154">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>
    
  - <span data-ttu-id="f32ee-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="f32ee-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>
    
  - <span data-ttu-id="f32ee-156">Экземпляр RTC установки Standard Edition</span><span class="sxs-lookup"><span data-stu-id="f32ee-156">Standard Edition Installation RTC Instance</span></span> 
    
  - <span data-ttu-id="f32ee-157">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="f32ee-157">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>
    
- <span data-ttu-id="f32ee-158">Каталоги и файлы</span><span class="sxs-lookup"><span data-stu-id="f32ee-158">Directories and files:</span></span>
    
  - <span data-ttu-id="f32ee-159">%systemroot%\system32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="f32ee-159">%systemroot%\System32\LogFiles</span></span>
    
  - <span data-ttu-id="f32ee-160">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="f32ee-160">%systemroot%\SysWow64\LogFiles</span></span>
    
  - <span data-ttu-id="f32ee-161">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="f32ee-161">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>
    
  - <span data-ttu-id="f32ee-162">%programfiles%\Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="f32ee-162">%programfiles%\Skype for Business Server 2015</span></span>
    
  - <span data-ttu-id="f32ee-163">%programfiles%\Common Files\Skype для бизнеса Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="f32ee-163">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>
    
  - <span data-ttu-id="f32ee-164">%programfiles%\Common Files\Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="f32ee-164">%programfiles%\Common Files\Skype for Business Server 2015</span></span>
    
  - <span data-ttu-id="f32ee-165">%programfiles%\Common Files\Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="f32ee-165">%programfiles%\Common Files\Skype for Business Online</span></span>
    
  - <span data-ttu-id="f32ee-166">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="f32ee-166">%SystemDrive%\RtcReplicaRoot</span></span>
    
  - <span data-ttu-id="f32ee-p105">Хранилище общих папок (указывается в построителе топологий). Хранилища файлов задаются в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="f32ee-p105">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>
    
  - <span data-ttu-id="f32ee-169">Файлы данных и журналов сервера SQL Server, включая объекты внутренней базы данных, хранилища пользователей, архивов, мониторинга и приложений.</span><span class="sxs-lookup"><span data-stu-id="f32ee-169">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="f32ee-170">Файлы баз данных и журналов можно указать в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="f32ee-170">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="f32ee-171">Для получения дополнительных сведений о файлах данных и журналов для каждой базы данных, включая имена по умолчанию содержатся в документации по развертыванию [данных SQL Server и размещение файлов журнала](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) .</span><span class="sxs-lookup"><span data-stu-id="f32ee-171">For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>
    
  - <span data-ttu-id="f32ee-172">SQL Server файлов данных и журналов, в том числе для интерфейсных базы данных, Скайп для хранения бизнес и RtcDatabase хранилища.</span><span class="sxs-lookup"><span data-stu-id="f32ee-172">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="f32ee-173">Как правило, они находятся в папке %localdrive%\CSData.</span><span class="sxs-lookup"><span data-stu-id="f32ee-173">They are normally under %localdrive%\CSData.</span></span>
    

