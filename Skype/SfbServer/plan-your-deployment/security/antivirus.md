---
title: Исключения проверки антивирусной программы для Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Общие сведения о взаимодействиях антивирусных сканеров с Skype для бизнеса Server.
ms.openlocfilehash: 9ec13b31328744bb154c9eb5e09dff7665c4b540
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296975"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="3ced9-103">Исключения проверки антивирусной программы для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="3ced9-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="3ced9-104">Общие сведения о взаимодействиях антивирусных сканеров с Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="3ced9-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="3ced9-105">В этой статье приведены рекомендации, которые помогут администратору определить причину потенциальной нестабильности на компьютере с установленной версией Microsoft Windows при использовании антивирусной программы в домене Active Directory. среды или в управляемой бизнес-среде.</span><span class="sxs-lookup"><span data-stu-id="3ced9-105">This article contains recommendations that may help an administrator determine the cause of potential instability on a computer that is running a supported version of Microsoft Windows when it is used with antivirus software in an Active Directory domain environment or in a managed business environment.</span></span>

<span data-ttu-id="3ced9-106">Мы рекомендуем временно применять эти процедуры для оценки системы.</span><span class="sxs-lookup"><span data-stu-id="3ced9-106">We recommend that you temporarily apply these procedures to evaluate a system.</span></span> <span data-ttu-id="3ced9-107">Если производительность или стабильность системы улучшились согласно рекомендациям, описанным в этой статье, обратитесь к поставщику антивирусной программы за инструкциями или в обновленной версии антивирусной программы.</span><span class="sxs-lookup"><span data-stu-id="3ced9-107">If your system performance or stability is improved by the recommendations that are made in this article, contact your antivirus software vendor for instructions or for an updated version of the antivirus software.</span></span>

<span data-ttu-id="3ced9-108">В этой статье приведены сведения о том, как уменьшить параметры безопасности или временно отключить средства безопасности на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3ced9-108">This article contains information that shows how to help lower security settings or how to temporarily turn off security features on a computer.</span></span> <span data-ttu-id="3ced9-109">Вы можете внести эти изменения, чтобы понять природу определенной проблемы.</span><span class="sxs-lookup"><span data-stu-id="3ced9-109">You can make these changes to understand the nature of a specific problem.</span></span> <span data-ttu-id="3ced9-110">Прежде чем вносить эти изменения, рекомендуется оценить риски, связанные с реализацией этого обходного пути в конкретной среде.</span><span class="sxs-lookup"><span data-stu-id="3ced9-110">Before you make these changes, we recommend that you evaluate the risks that are associated with implementing this workaround in your particular environment.</span></span> <span data-ttu-id="3ced9-111">Если вы реализуете это временное решение, выполните все необходимые дополнительные действия, чтобы защитить компьютер от вирусов, которые больше не проверяются антивирусными программами.</span><span class="sxs-lookup"><span data-stu-id="3ced9-111">If you implement this workaround, take any appropriate additional steps to help protect the computer for the files that are no longer being scanned by your antivirus software.</span></span>

<span data-ttu-id="3ced9-112">Чтобы антивирусная программа не мешала работе со Skype для бизнеса Server, необходимо исключить определенные процессы и каталоги для каждого сервера Skype для бизнеса Server или серверной роли, для которой вы запускаете антивирусную программу.</span><span class="sxs-lookup"><span data-stu-id="3ced9-112">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="3ced9-113">Исключите перечисленные ниже процессы и каталоги.</span><span class="sxs-lookup"><span data-stu-id="3ced9-113">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="3ced9-114">Ниже указаны расположения файлов и папок, используемые в Skype для бизнеса Server по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3ced9-114">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="3ced9-115">Если в вашей организации какие-либо из этих объектов расположены в других местах, укажите соответствующие пути.</span><span class="sxs-lookup"><span data-stu-id="3ced9-115">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3ced9-116">Обратите внимание, что в некоторых антивирусных программах в списке исключений необходимо указывать абсолютные пути, а не относительные.</span><span class="sxs-lookup"><span data-stu-id="3ced9-116">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="3ced9-117">Серверные процессы Skype для бизнеса:</span><span class="sxs-lookup"><span data-stu-id="3ced9-117">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="3ced9-118">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="3ced9-118">ABServer.exe</span></span>

  - <span data-ttu-id="3ced9-119">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="3ced9-119">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="3ced9-120">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="3ced9-120">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="3ced9-121">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="3ced9-121">ChannelService.exe</span></span>

  - <span data-ttu-id="3ced9-122">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="3ced9-122">ClsAgent.exe</span></span>

  - <span data-ttu-id="3ced9-123">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="3ced9-123">ComplianceService.exe</span></span>

  - <span data-ttu-id="3ced9-124">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="3ced9-124">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="3ced9-125">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="3ced9-125">DataProxy.exe</span></span>

  - <span data-ttu-id="3ced9-126">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="3ced9-126">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="3ced9-127">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="3ced9-127">HealthAgent.exe</span></span>

  - <span data-ttu-id="3ced9-128">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="3ced9-128">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="3ced9-129">Линкбаккупсервице. exe</span><span class="sxs-lookup"><span data-stu-id="3ced9-129">LyncBackupService.exe</span></span>

  - <span data-ttu-id="3ced9-130">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="3ced9-130">LysSvc.exe</span></span>

  - <span data-ttu-id="3ced9-131">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="3ced9-131">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="3ced9-132">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="3ced9-132">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="3ced9-133">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="3ced9-133">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="3ced9-134">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="3ced9-134">MRASSvc.exe</span></span>

  - <span data-ttu-id="3ced9-135">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="3ced9-135">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="3ced9-136">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="3ced9-136">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="3ced9-137">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="3ced9-137">ReplicationApp.exe</span></span>

  - <span data-ttu-id="3ced9-138">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="3ced9-138">RtcHost.exe</span></span>

  - <span data-ttu-id="3ced9-139">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="3ced9-139">RTCSrv.exe</span></span>

  - <span data-ttu-id="3ced9-140">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="3ced9-140">XmppProxy.exe</span></span>

  - <span data-ttu-id="3ced9-141">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="3ced9-141">XmppTGW.exe</span></span>

- <span data-ttu-id="3ced9-142">Процессы службы узла Windows Fabric</span><span class="sxs-lookup"><span data-stu-id="3ced9-142">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="3ced9-143">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="3ced9-143">Fabric.exe</span></span>

  - <span data-ttu-id="3ced9-144">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="3ced9-144">FabricDCA.exe</span></span>

  - <span data-ttu-id="3ced9-145">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="3ced9-145">FabricHost.exe</span></span>

- <span data-ttu-id="3ced9-146">Процессы IIS</span><span class="sxs-lookup"><span data-stu-id="3ced9-146">IIS processes:</span></span>

  - <span data-ttu-id="3ced9-147">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="3ced9-147">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="3ced9-148">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="3ced9-148">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="3ced9-149">Внутренние процессы сервера SQL Server</span><span class="sxs-lookup"><span data-stu-id="3ced9-149">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="3ced9-150">Обратите внимание, что эти пути зависят от версии SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3ced9-150">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="3ced9-151">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="3ced9-151">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="3ced9-152">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="3ced9-152">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="3ced9-153">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="3ced9-153">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="3ced9-154">Внешние процессы сервера SQL Server</span><span class="sxs-lookup"><span data-stu-id="3ced9-154">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="3ced9-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="3ced9-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="3ced9-156">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="3ced9-156">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="3ced9-157">Экземпляр RTC установки Standard Edition</span><span class="sxs-lookup"><span data-stu-id="3ced9-157">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="3ced9-158">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="3ced9-158">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="3ced9-159">Каталоги и файлы</span><span class="sxs-lookup"><span data-stu-id="3ced9-159">Directories and files:</span></span>

  - <span data-ttu-id="3ced9-160">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="3ced9-160">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="3ced9-161">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="3ced9-161">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="3ced9-162">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="3ced9-162">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="3ced9-163">Обратите внимание, что эти пути специфичны для версии Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="3ced9-163">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="3ced9-164">%programfiles%\Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="3ced9-164">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="3ced9-165">%programfiles%\Common Files\Skype для бизнеса Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="3ced9-165">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="3ced9-166">%programfiles%\Common Files\Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="3ced9-166">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="3ced9-167">%programfiles%\Common Files\Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="3ced9-167">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="3ced9-168">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="3ced9-168">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="3ced9-p105">Хранилище общих папок (указывается в построителе топологий). Хранилища файлов задаются в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="3ced9-p105">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="3ced9-p106">Файлы данных и журналов сервера SQL Server, включая объекты внутренней базы данных, хранилища пользователей, архивов, мониторинга и приложений. Файлы баз данных и журналов можно указать в построителе топологий. Подробные сведения о файлах данных и журналов для каждой базы, включая имена по умолчанию, см. в статье [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) в разделе, посвященном документации развертывания.</span><span class="sxs-lookup"><span data-stu-id="3ced9-p106">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store. Database and log files can be specified in Topology Builder. For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

  - <span data-ttu-id="3ced9-174">Файлы данных и журналов SQL Server, в том числе для интерфейсной базы данных, магазина Skype для бизнеса и Рткдатабасе магазина.</span><span class="sxs-lookup"><span data-stu-id="3ced9-174">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="3ced9-175">Как правило, они находятся в папке %localdrive%\CSData.</span><span class="sxs-lookup"><span data-stu-id="3ced9-175">They are normally under %localdrive%\CSData.</span></span>


