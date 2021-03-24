---
title: Исключения для антивирусного сканирования для Skype для бизнес-сервера
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
description: Обзор межоперации антивирусного сканера с Skype для бизнеса Server.
ms.openlocfilehash: 64646304b98de075fd9af0a82096da8c0bff2f12
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104245"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="6f921-103">Исключения для антивирусного сканирования для Skype для бизнес-сервера</span><span class="sxs-lookup"><span data-stu-id="6f921-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="6f921-104">Обзор межоперации антивирусного сканера с Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6f921-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="6f921-105">Чтобы антивирусный сканер не мешал работе Skype для бизнес-сервера, необходимо исключить определенные процессы и каталоги для каждого сервера Skype для бизнес-сервера или роли сервера, на котором вы запустите антивирусный сканер.</span><span class="sxs-lookup"><span data-stu-id="6f921-105">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="6f921-106">Следует исключить следующие процессы и каталоги:</span><span class="sxs-lookup"><span data-stu-id="6f921-106">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="6f921-107">Папки и расположения файлов, перечисленные ниже, являются расположениями по умолчанию для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6f921-107">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="6f921-108">Для любых местоположений, для которых не используется значение по умолчанию, исключите расположения, указанные для организации, а не расположения по умолчанию, указанные в этой теме.</span><span class="sxs-lookup"><span data-stu-id="6f921-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6f921-109">Обратите внимание, что некоторым антивирусным программам могут потребоваться абсолютные, а не относительные пути для списка исключений.</span><span class="sxs-lookup"><span data-stu-id="6f921-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="6f921-110">Процессы Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="6f921-110">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="6f921-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="6f921-111">ABServer.exe</span></span>

  - <span data-ttu-id="6f921-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="6f921-112">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="6f921-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="6f921-113">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="6f921-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="6f921-114">ChannelService.exe</span></span>

  - <span data-ttu-id="6f921-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="6f921-115">ClsAgent.exe</span></span>

  - <span data-ttu-id="6f921-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="6f921-116">ComplianceService.exe</span></span>

  - <span data-ttu-id="6f921-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="6f921-117">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="6f921-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="6f921-118">DataProxy.exe</span></span>

  - <span data-ttu-id="6f921-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="6f921-119">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="6f921-120">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="6f921-120">HealthAgent.exe</span></span>

  - <span data-ttu-id="6f921-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="6f921-121">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="6f921-122">LyncBackupService.exe</span><span class="sxs-lookup"><span data-stu-id="6f921-122">LyncBackupService.exe</span></span>

  - <span data-ttu-id="6f921-123">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="6f921-123">LysSvc.exe</span></span>

  - <span data-ttu-id="6f921-124">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="6f921-124">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="6f921-125">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="6f921-125">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="6f921-126">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="6f921-126">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="6f921-127">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="6f921-127">MRASSvc.exe</span></span>

  - <span data-ttu-id="6f921-128">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="6f921-128">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="6f921-129">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="6f921-129">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="6f921-130">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="6f921-130">ReplicationApp.exe</span></span>

  - <span data-ttu-id="6f921-131">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="6f921-131">RtcHost.exe</span></span>

  - <span data-ttu-id="6f921-132">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="6f921-132">RTCSrv.exe</span></span>

  - <span data-ttu-id="6f921-133">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="6f921-133">XmppProxy.exe</span></span>

  - <span data-ttu-id="6f921-134">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="6f921-134">XmppTGW.exe</span></span>

- <span data-ttu-id="6f921-135">Процессы службы хост-службы Windows Fabric:</span><span class="sxs-lookup"><span data-stu-id="6f921-135">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="6f921-136">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="6f921-136">Fabric.exe</span></span>

  - <span data-ttu-id="6f921-137">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="6f921-137">FabricDCA.exe</span></span>

  - <span data-ttu-id="6f921-138">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="6f921-138">FabricHost.exe</span></span>

- <span data-ttu-id="6f921-139">Процессы IIS:</span><span class="sxs-lookup"><span data-stu-id="6f921-139">IIS processes:</span></span>

  - <span data-ttu-id="6f921-140">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="6f921-140">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="6f921-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="6f921-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="6f921-142">SQL Server Back-End процессы:</span><span class="sxs-lookup"><span data-stu-id="6f921-142">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="6f921-143">Обратите внимание, что эти пути являются специфическими для SQL Server версии.</span><span class="sxs-lookup"><span data-stu-id="6f921-143">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="6f921-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="6f921-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="6f921-145">%ProgramFiles%\Microsoft SQL Server\MSRS11. MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="6f921-145">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="6f921-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="6f921-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="6f921-147">SQL Server Front-End процессы:</span><span class="sxs-lookup"><span data-stu-id="6f921-147">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="6f921-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="6f921-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="6f921-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="6f921-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="6f921-150">Экземпляр установки стандартного выпуска RTC</span><span class="sxs-lookup"><span data-stu-id="6f921-150">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="6f921-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="6f921-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="6f921-152">Каталоги и файлы:</span><span class="sxs-lookup"><span data-stu-id="6f921-152">Directories and files:</span></span>

  - <span data-ttu-id="6f921-153">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="6f921-153">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="6f921-154">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="6f921-154">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="6f921-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="6f921-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="6f921-156">Обратите внимание, что эти пути являются специфическими для версии Skype для бизнес-сервера.</span><span class="sxs-lookup"><span data-stu-id="6f921-156">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="6f921-157">%programfiles%\Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="6f921-157">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="6f921-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="6f921-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="6f921-159">%programfiles%\Common Files\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="6f921-159">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="6f921-160">%programfiles%\Common Files\Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="6f921-160">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="6f921-161">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="6f921-161">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="6f921-162">Хранилище обмена файлами (указанное в topology Builder).</span><span class="sxs-lookup"><span data-stu-id="6f921-162">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="6f921-163">Хранилища файлов указаны в Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="6f921-163">File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="6f921-164">SQL Server данных и файлов журналов, в том числе для базы данных, магазина пользователей, архивного магазина, магазина мониторинга и магазина приложений.</span><span class="sxs-lookup"><span data-stu-id="6f921-164">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="6f921-165">Файлы баз данных и журналов могут быть указаны в Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="6f921-165">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="6f921-166">Подробные сведения о данных и файлах журналов для каждой базы данных, включая имена по умолчанию, [см.](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) в SQL Server data and Log File Placement in the Deployment documentation.</span><span class="sxs-lookup"><span data-stu-id="6f921-166">For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) in the Deployment documentation.</span></span>

  - <span data-ttu-id="6f921-167">SQL Server данных и файлов журналов, в том числе для базы данных front-end, магазина Skype для бизнеса и магазина RtcDatabase.</span><span class="sxs-lookup"><span data-stu-id="6f921-167">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="6f921-168">Обычно они находятся под %localdrive%\CSData.</span><span class="sxs-lookup"><span data-stu-id="6f921-168">They are normally under %localdrive%\CSData.</span></span>