---
title: Исключения проверки антивирусной программы для Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Общие сведения о взаимодействиях антивирусных сканеров с Skype для бизнеса Server.
ms.openlocfilehash: 10d296e36324fdbc8bca8f7da48370d619774501
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815697"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="b38ed-103">Исключения проверки антивирусной программы для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="b38ed-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="b38ed-104">Общие сведения о взаимодействиях антивирусных сканеров с Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="b38ed-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="b38ed-105">Чтобы антивирусная программа не мешала работе со Skype для бизнеса Server, необходимо исключить определенные процессы и каталоги для каждого сервера Skype для бизнеса Server или серверной роли, для которой вы запускаете антивирусную программу.</span><span class="sxs-lookup"><span data-stu-id="b38ed-105">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="b38ed-106">Исключите перечисленные ниже процессы и каталоги.</span><span class="sxs-lookup"><span data-stu-id="b38ed-106">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="b38ed-107">Ниже указаны расположения файлов и папок, используемые в Skype для бизнеса Server по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b38ed-107">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="b38ed-108">Если в вашей организации какие-либо из этих объектов расположены в других местах, укажите соответствующие пути.</span><span class="sxs-lookup"><span data-stu-id="b38ed-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b38ed-109">Обратите внимание, что в некоторых антивирусных программах в списке исключений необходимо указывать абсолютные пути, а не относительные.</span><span class="sxs-lookup"><span data-stu-id="b38ed-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="b38ed-110">Серверные процессы Skype для бизнеса:</span><span class="sxs-lookup"><span data-stu-id="b38ed-110">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="b38ed-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="b38ed-111">ABServer.exe</span></span>

  - <span data-ttu-id="b38ed-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="b38ed-112">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="b38ed-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="b38ed-113">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="b38ed-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="b38ed-114">ChannelService.exe</span></span>

  - <span data-ttu-id="b38ed-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="b38ed-115">ClsAgent.exe</span></span>

  - <span data-ttu-id="b38ed-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="b38ed-116">ComplianceService.exe</span></span>

  - <span data-ttu-id="b38ed-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="b38ed-117">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="b38ed-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="b38ed-118">DataProxy.exe</span></span>

  - <span data-ttu-id="b38ed-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="b38ed-119">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="b38ed-120">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="b38ed-120">HealthAgent.exe</span></span>

  - <span data-ttu-id="b38ed-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="b38ed-121">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="b38ed-122">Линкбаккупсервице. exe</span><span class="sxs-lookup"><span data-stu-id="b38ed-122">LyncBackupService.exe</span></span>

  - <span data-ttu-id="b38ed-123">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="b38ed-123">LysSvc.exe</span></span>

  - <span data-ttu-id="b38ed-124">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="b38ed-124">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="b38ed-125">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="b38ed-125">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="b38ed-126">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="b38ed-126">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="b38ed-127">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="b38ed-127">MRASSvc.exe</span></span>

  - <span data-ttu-id="b38ed-128">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="b38ed-128">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="b38ed-129">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="b38ed-129">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="b38ed-130">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="b38ed-130">ReplicationApp.exe</span></span>

  - <span data-ttu-id="b38ed-131">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="b38ed-131">RtcHost.exe</span></span>

  - <span data-ttu-id="b38ed-132">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="b38ed-132">RTCSrv.exe</span></span>

  - <span data-ttu-id="b38ed-133">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="b38ed-133">XmppProxy.exe</span></span>

  - <span data-ttu-id="b38ed-134">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="b38ed-134">XmppTGW.exe</span></span>

- <span data-ttu-id="b38ed-135">Процессы службы узла Windows Fabric</span><span class="sxs-lookup"><span data-stu-id="b38ed-135">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="b38ed-136">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="b38ed-136">Fabric.exe</span></span>

  - <span data-ttu-id="b38ed-137">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="b38ed-137">FabricDCA.exe</span></span>

  - <span data-ttu-id="b38ed-138">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="b38ed-138">FabricHost.exe</span></span>

- <span data-ttu-id="b38ed-139">Процессы IIS</span><span class="sxs-lookup"><span data-stu-id="b38ed-139">IIS processes:</span></span>

  - <span data-ttu-id="b38ed-140">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="b38ed-140">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="b38ed-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="b38ed-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="b38ed-142">Внутренние процессы сервера SQL Server</span><span class="sxs-lookup"><span data-stu-id="b38ed-142">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="b38ed-143">Обратите внимание, что эти пути зависят от версии SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b38ed-143">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="b38ed-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="b38ed-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="b38ed-145">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="b38ed-145">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="b38ed-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="b38ed-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="b38ed-147">Внешние процессы сервера SQL Server</span><span class="sxs-lookup"><span data-stu-id="b38ed-147">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="b38ed-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="b38ed-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="b38ed-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="b38ed-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="b38ed-150">Экземпляр RTC установки Standard Edition</span><span class="sxs-lookup"><span data-stu-id="b38ed-150">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="b38ed-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="b38ed-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="b38ed-152">Каталоги и файлы</span><span class="sxs-lookup"><span data-stu-id="b38ed-152">Directories and files:</span></span>

  - <span data-ttu-id="b38ed-153">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="b38ed-153">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="b38ed-154">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="b38ed-154">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="b38ed-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="b38ed-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="b38ed-156">Обратите внимание, что эти пути специфичны для версии Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="b38ed-156">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="b38ed-157">%programfiles%\Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="b38ed-157">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="b38ed-158">%programfiles%\Common Files\Skype для бизнеса Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="b38ed-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="b38ed-159">%programfiles%\Common Files\Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="b38ed-159">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="b38ed-160">%programfiles%\Common Files\Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="b38ed-160">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="b38ed-161">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="b38ed-161">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="b38ed-p103">Хранилище общих папок (указывается в построителе топологий). Хранилища файлов задаются в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="b38ed-p103">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="b38ed-p104">Файлы данных и журналов сервера SQL Server, включая объекты внутренней базы данных, хранилища пользователей, архивов, мониторинга и приложений. Файлы баз данных и журналов можно указать в построителе топологий. Подробные сведения о файлах данных и журналов для каждой базы, включая имена по умолчанию, см. в статье [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) в разделе, посвященном документации развертывания.</span><span class="sxs-lookup"><span data-stu-id="b38ed-p104">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store. Database and log files can be specified in Topology Builder. For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

  - <span data-ttu-id="b38ed-167">Файлы данных и журналов SQL Server, в том числе для интерфейсной базы данных, магазина Skype для бизнеса и Рткдатабасе магазина.</span><span class="sxs-lookup"><span data-stu-id="b38ed-167">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="b38ed-168">Как правило, они находятся в папке %localdrive%\CSData.</span><span class="sxs-lookup"><span data-stu-id="b38ed-168">They are normally under %localdrive%\CSData.</span></span>


