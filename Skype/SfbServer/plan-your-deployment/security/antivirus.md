---
title: Антивирусная программа сканирования исключения для Скайп для Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Обзор взаимодействия антивирусную программу с Скайп для Business Server.
ms.openlocfilehash: 377c9e8fb9de71187978fe541a23f43cc2282749
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213671"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="eff44-103">Антивирусная программа сканирования исключения для Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="eff44-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="eff44-104">Обзор взаимодействия антивирусную программу с Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="eff44-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="eff44-105">В этой статье представлены рекомендации, которые могут помочь определить причину нестабильной на компьютере, на котором выполняется поддерживаемая версия Microsoft Windows при использовании с помощью антивирусных программ в домене Active Directory администратора среда или управляемой бизнес-среде.</span><span class="sxs-lookup"><span data-stu-id="eff44-105">This article contains recommendations that may help an administrator determine the cause of potential instability on a computer that is running a supported version of Microsoft Windows when it is used with antivirus software in an Active Directory domain environment or in a managed business environment.</span></span>

<span data-ttu-id="eff44-106">Мы рекомендуем временно применяются следующие действия, чтобы оценить в системе.</span><span class="sxs-lookup"><span data-stu-id="eff44-106">We recommend that you temporarily apply these procedures to evaluate a system.</span></span> <span data-ttu-id="eff44-107">Если производительность системы или стабильность улучшена благодаря рекомендации, которые выполняются в этой статье, обратитесь к поставщику антивирусной программы за инструкциями или обновленной версией антивирусное программное обеспечение.</span><span class="sxs-lookup"><span data-stu-id="eff44-107">If your system performance or stability is improved by the recommendations that are made in this article, contact your antivirus software vendor for instructions or for an updated version of the antivirus software.</span></span>

<span data-ttu-id="eff44-108">Эта статья содержит сведения, показано, как снижении уровня безопасности или временно отключить функции безопасности на компьютере.</span><span class="sxs-lookup"><span data-stu-id="eff44-108">This article contains information that shows how to help lower security settings or how to temporarily turn off security features on a computer.</span></span> <span data-ttu-id="eff44-109">Можно внести эти изменения, чтобы понять причину конкретной проблемы.</span><span class="sxs-lookup"><span data-stu-id="eff44-109">You can make these changes to understand the nature of a specific problem.</span></span> <span data-ttu-id="eff44-110">Прежде чем вносить изменения, рекомендуется оценить риски, связанные с ними в существующей среде.</span><span class="sxs-lookup"><span data-stu-id="eff44-110">Before you make these changes, we recommend that you evaluate the risks that are associated with implementing this workaround in your particular environment.</span></span> <span data-ttu-id="eff44-111">Если данный метод обхода, выполните все необходимые дополнительные меры для защиты компьютера и поиск файлов, которые больше не сканируются антивирусной программой.</span><span class="sxs-lookup"><span data-stu-id="eff44-111">If you implement this workaround, take any appropriate additional steps to help protect the computer for the files that are no longer being scanned by your antivirus software.</span></span>

<span data-ttu-id="eff44-112">Чтобы убедиться, что антивирусную программу не влияет на операции Скайп для Business Server, необходимо исключить конкретные процессы и каталоги для каждого Скайп для Business Server сервер или роль сервера, на котором выполняется антивирусную программу.</span><span class="sxs-lookup"><span data-stu-id="eff44-112">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="eff44-113">Исключите перечисленные ниже процессы и каталоги.</span><span class="sxs-lookup"><span data-stu-id="eff44-113">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="eff44-114">Папка и файл расположения, перечисленных ниже — это расположение по умолчанию для Скайп Business Server.</span><span class="sxs-lookup"><span data-stu-id="eff44-114">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="eff44-115">Если в вашей организации какие-либо из этих объектов расположены в других местах, укажите соответствующие пути.</span><span class="sxs-lookup"><span data-stu-id="eff44-115">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eff44-116">Обратите внимание, что в некоторых антивирусных программах в списке исключений необходимо указывать абсолютные пути, а не относительные.</span><span class="sxs-lookup"><span data-stu-id="eff44-116">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="eff44-117">Скайп для процессов Business Server:</span><span class="sxs-lookup"><span data-stu-id="eff44-117">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="eff44-118">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="eff44-118">ABServer.exe</span></span>

  - <span data-ttu-id="eff44-119">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="eff44-119">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="eff44-120">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="eff44-120">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="eff44-121">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="eff44-121">ChannelService.exe</span></span>

  - <span data-ttu-id="eff44-122">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="eff44-122">ClsAgent.exe</span></span>

  - <span data-ttu-id="eff44-123">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="eff44-123">ComplianceService.exe</span></span>

  - <span data-ttu-id="eff44-124">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="eff44-124">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="eff44-125">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="eff44-125">DataProxy.exe</span></span>

  - <span data-ttu-id="eff44-126">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="eff44-126">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="eff44-127">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="eff44-127">HealthAgent.exe</span></span>

  - <span data-ttu-id="eff44-128">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="eff44-128">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="eff44-129">LyncBackupService.exe</span><span class="sxs-lookup"><span data-stu-id="eff44-129">LyncBackupService.exe</span></span>

  - <span data-ttu-id="eff44-130">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="eff44-130">LysSvc.exe</span></span>

  - <span data-ttu-id="eff44-131">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="eff44-131">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="eff44-132">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="eff44-132">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="eff44-133">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="eff44-133">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="eff44-134">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="eff44-134">MRASSvc.exe</span></span>

  - <span data-ttu-id="eff44-135">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="eff44-135">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="eff44-136">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="eff44-136">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="eff44-137">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="eff44-137">ReplicationApp.exe</span></span>

  - <span data-ttu-id="eff44-138">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="eff44-138">RtcHost.exe</span></span>

  - <span data-ttu-id="eff44-139">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="eff44-139">RTCSrv.exe</span></span>

  - <span data-ttu-id="eff44-140">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="eff44-140">XmppProxy.exe</span></span>

  - <span data-ttu-id="eff44-141">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="eff44-141">XmppTGW.exe</span></span>

- <span data-ttu-id="eff44-142">Процессы службы узла Windows Fabric</span><span class="sxs-lookup"><span data-stu-id="eff44-142">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="eff44-143">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="eff44-143">Fabric.exe</span></span>

  - <span data-ttu-id="eff44-144">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="eff44-144">FabricDCA.exe</span></span>

  - <span data-ttu-id="eff44-145">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="eff44-145">FabricHost.exe</span></span>

- <span data-ttu-id="eff44-146">Процессы IIS</span><span class="sxs-lookup"><span data-stu-id="eff44-146">IIS processes:</span></span>

  - <span data-ttu-id="eff44-147">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="eff44-147">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="eff44-148">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="eff44-148">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="eff44-149">Внутренние процессы сервера SQL Server</span><span class="sxs-lookup"><span data-stu-id="eff44-149">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="eff44-150">Обратите внимание, что эти пути зависят от версии SQL Server.</span><span class="sxs-lookup"><span data-stu-id="eff44-150">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="eff44-151">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="eff44-151">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="eff44-152">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="eff44-152">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="eff44-153">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="eff44-153">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="eff44-154">Внешние процессы сервера SQL Server</span><span class="sxs-lookup"><span data-stu-id="eff44-154">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="eff44-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="eff44-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="eff44-156">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="eff44-156">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="eff44-157">Экземпляр RTC установки Standard Edition</span><span class="sxs-lookup"><span data-stu-id="eff44-157">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="eff44-158">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="eff44-158">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="eff44-159">Каталоги и файлы</span><span class="sxs-lookup"><span data-stu-id="eff44-159">Directories and files:</span></span>

  - <span data-ttu-id="eff44-160">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="eff44-160">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="eff44-161">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="eff44-161">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="eff44-162">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="eff44-162">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="eff44-163">Обратите внимание на то, что эти пути относятся к Скайп для версии Business Server.</span><span class="sxs-lookup"><span data-stu-id="eff44-163">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="eff44-164">%programfiles%\Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="eff44-164">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="eff44-165">%programfiles%\Common Files\Skype для бизнеса Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="eff44-165">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="eff44-166">%programfiles%\Common Files\Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="eff44-166">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="eff44-167">%programfiles%\Common Files\Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="eff44-167">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="eff44-168">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="eff44-168">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="eff44-p105">Хранилище общих папок (указывается в построителе топологий). Хранилища файлов задаются в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="eff44-p105">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="eff44-p106">Файлы данных и журналов сервера SQL Server, включая объекты внутренней базы данных, хранилища пользователей, архивов, мониторинга и приложений. Файлы баз данных и журналов можно указать в построителе топологий. Подробные сведения о файлах данных и журналов для каждой базы, включая имена по умолчанию, см. в статье [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) в разделе, посвященном документации развертывания.</span><span class="sxs-lookup"><span data-stu-id="eff44-p106">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store. Database and log files can be specified in Topology Builder. For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

  - <span data-ttu-id="eff44-174">SQL Server файлов данных и журналов, в том числе для интерфейсных базы данных, Скайп для хранения бизнес и RtcDatabase хранилища.</span><span class="sxs-lookup"><span data-stu-id="eff44-174">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="eff44-175">Как правило, они находятся в папке %localdrive%\CSData.</span><span class="sxs-lookup"><span data-stu-id="eff44-175">They are normally under %localdrive%\CSData.</span></span>


