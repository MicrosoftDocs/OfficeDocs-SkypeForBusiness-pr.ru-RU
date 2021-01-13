---
title: Исключения антивирусной проверки для Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Обзор меж антивирусного сканера со Skype для бизнеса Server.
ms.openlocfilehash: b59a5c474a96d312ebe3a648536ebe827e684931
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832269"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="27bac-103">Исключения антивирусной проверки для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="27bac-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="27bac-104">Обзор меж антивирусного сканера со Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="27bac-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="27bac-105">Чтобы антивирусная программа не помешала работе Skype для бизнеса Server, необходимо исключить определенные процессы и каталоги для каждого сервера или роли сервера Skype для бизнеса Server, на котором работает антивирусная программа.</span><span class="sxs-lookup"><span data-stu-id="27bac-105">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="27bac-106">Следует исключить следующие процессы и каталоги:</span><span class="sxs-lookup"><span data-stu-id="27bac-106">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="27bac-107">Папки и расположения файлов, перечисленные ниже, являются расположениями по умолчанию для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="27bac-107">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="27bac-108">Для всех местоположений, для которых вы не использовали значение по умолчанию, исключите расположения, указанные для организации, а не расположения по умолчанию, указанные в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="27bac-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="27bac-109">Обратите внимание, что некоторым антивирусным программам могут потребоваться абсолютные, а не относительные пути, для списка исключений.</span><span class="sxs-lookup"><span data-stu-id="27bac-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="27bac-110">Процессы Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="27bac-110">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="27bac-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="27bac-111">ABServer.exe</span></span>

  - <span data-ttu-id="27bac-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="27bac-112">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="27bac-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="27bac-113">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="27bac-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="27bac-114">ChannelService.exe</span></span>

  - <span data-ttu-id="27bac-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="27bac-115">ClsAgent.exe</span></span>

  - <span data-ttu-id="27bac-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="27bac-116">ComplianceService.exe</span></span>

  - <span data-ttu-id="27bac-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="27bac-117">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="27bac-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="27bac-118">DataProxy.exe</span></span>

  - <span data-ttu-id="27bac-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="27bac-119">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="27bac-120">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="27bac-120">HealthAgent.exe</span></span>

  - <span data-ttu-id="27bac-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="27bac-121">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="27bac-122">LyncBackupService.exe</span><span class="sxs-lookup"><span data-stu-id="27bac-122">LyncBackupService.exe</span></span>

  - <span data-ttu-id="27bac-123">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="27bac-123">LysSvc.exe</span></span>

  - <span data-ttu-id="27bac-124">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="27bac-124">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="27bac-125">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="27bac-125">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="27bac-126">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="27bac-126">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="27bac-127">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="27bac-127">MRASSvc.exe</span></span>

  - <span data-ttu-id="27bac-128">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="27bac-128">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="27bac-129">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="27bac-129">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="27bac-130">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="27bac-130">ReplicationApp.exe</span></span>

  - <span data-ttu-id="27bac-131">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="27bac-131">RtcHost.exe</span></span>

  - <span data-ttu-id="27bac-132">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="27bac-132">RTCSrv.exe</span></span>

  - <span data-ttu-id="27bac-133">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="27bac-133">XmppProxy.exe</span></span>

  - <span data-ttu-id="27bac-134">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="27bac-134">XmppTGW.exe</span></span>

- <span data-ttu-id="27bac-135">Процессы службы windows Fabric Host Service:</span><span class="sxs-lookup"><span data-stu-id="27bac-135">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="27bac-136">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="27bac-136">Fabric.exe</span></span>

  - <span data-ttu-id="27bac-137">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="27bac-137">FabricDCA.exe</span></span>

  - <span data-ttu-id="27bac-138">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="27bac-138">FabricHost.exe</span></span>

- <span data-ttu-id="27bac-139">Процессы IIS:</span><span class="sxs-lookup"><span data-stu-id="27bac-139">IIS processes:</span></span>

  - <span data-ttu-id="27bac-140">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="27bac-140">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="27bac-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="27bac-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="27bac-142">SQL Server Back-End процессов:</span><span class="sxs-lookup"><span data-stu-id="27bac-142">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="27bac-143">Обратите внимание, что эти пути являются специфическими для SQL Server версии.</span><span class="sxs-lookup"><span data-stu-id="27bac-143">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="27bac-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="27bac-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="27bac-145">%ProgramFiles%\Microsoft SQL Server\MSRS11. MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="27bac-145">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="27bac-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="27bac-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="27bac-147">SQL Server Front-End процессов:</span><span class="sxs-lookup"><span data-stu-id="27bac-147">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="27bac-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="27bac-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="27bac-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="27bac-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="27bac-150">Экземпляр RTC установки Standard Edition</span><span class="sxs-lookup"><span data-stu-id="27bac-150">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="27bac-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="27bac-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="27bac-152">Каталоги и файлы:</span><span class="sxs-lookup"><span data-stu-id="27bac-152">Directories and files:</span></span>

  - <span data-ttu-id="27bac-153">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="27bac-153">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="27bac-154">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="27bac-154">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="27bac-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="27bac-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="27bac-156">Обратите внимание, что эти пути являются специфическими для версии Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="27bac-156">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="27bac-157">%programfiles%\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="27bac-157">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="27bac-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="27bac-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="27bac-159">%programfiles%\Common Files\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="27bac-159">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="27bac-160">%programfiles%\Common Files\Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="27bac-160">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="27bac-161">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="27bac-161">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="27bac-162">Хранилище файлового файла (указано в построителе топологий).</span><span class="sxs-lookup"><span data-stu-id="27bac-162">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="27bac-163">Хранилища файлов указаны в построителье топологий.</span><span class="sxs-lookup"><span data-stu-id="27bac-163">File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="27bac-164">SQL Server данных и журналов, в том числе для тыловой базы данных, пользовательского хранения, архивного хранения, мониторинга и приложения.</span><span class="sxs-lookup"><span data-stu-id="27bac-164">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="27bac-165">Файлы базы данных и журналов можно у указаны в построителье топологий.</span><span class="sxs-lookup"><span data-stu-id="27bac-165">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="27bac-166">Подробные сведения о данных и файлах журналов для каждой базы данных, включая имена по умолчанию, см. в SQL Server [data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span><span class="sxs-lookup"><span data-stu-id="27bac-166">For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

  - <span data-ttu-id="27bac-167">SQL Server данных и журналов, в том числе для базы данных переднего входа, магазина Skype для бизнеса и хранения RtcDatabase.</span><span class="sxs-lookup"><span data-stu-id="27bac-167">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="27bac-168">Обычно они находятся в %localdrive%\CSData.</span><span class="sxs-lookup"><span data-stu-id="27bac-168">They are normally under %localdrive%\CSData.</span></span>


