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
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a>Исключения для антивирусного сканирования для Skype для бизнес-сервера

Обзор межоперации антивирусного сканера с Skype для бизнеса Server.

Чтобы антивирусный сканер не мешал работе Skype для бизнес-сервера, необходимо исключить определенные процессы и каталоги для каждого сервера Skype для бизнес-сервера или роли сервера, на котором вы запустите антивирусный сканер. Следует исключить следующие процессы и каталоги:

> [!NOTE]
> Папки и расположения файлов, перечисленные ниже, являются расположениями по умолчанию для Skype для бизнеса Server. Для любых местоположений, для которых не используется значение по умолчанию, исключите расположения, указанные для организации, а не расположения по умолчанию, указанные в этой теме.

> [!IMPORTANT]
> Обратите внимание, что некоторым антивирусным программам могут потребоваться абсолютные, а не относительные пути для списка исключений.

- Процессы Skype для бизнеса Server:

  - ABServer.exe

  - ASMCUSvc.exe

  - AVMCUSvc.exe

  - ChannelService.exe

  - ClsAgent.exe

  - ComplianceService.exe

  - DataMCUSvc.exe

  - DataProxy.exe

  - FileTransferAgent.exe

  - HealthAgent.exe

  - IMMCUSvc.exe
  
  - LyncBackupService.exe

  - LysSvc.exe

  - MasterReplicatorAgent.exe

  - MediaRelaySvc.exe

  - MediationServerSvc.exe

  - MRASSvc.exe

  - OcsAppServerHost.exe

  - ReplicaReplicatorAgent.exe

  - ReplicationApp.exe

  - RtcHost.exe

  - RTCSrv.exe

  - XmppProxy.exe

  - XmppTGW.exe

- Процессы службы хост-службы Windows Fabric:

  - Fabric.exe

  - FabricDCA.exe

  - FabricHost.exe

- Процессы IIS:

  - %systemroot%\system32\inetsrv\w3wp.exe

  - %systemroot%\SysWOW64\inetsrv\w3wp.exe

- SQL Server Back-End процессы:

    > [!NOTE]
    > Обратите внимание, что эти пути являются специфическими для SQL Server версии.

  - %ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe

  - %ProgramFiles%\Microsoft SQL Server\MSRS11. MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe

  - %ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe

- SQL Server Front-End процессы:

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe

  - Экземпляр установки стандартного выпуска RTC

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe

- Каталоги и файлы:

  - %systemroot%\System32\LogFiles

  - %systemroot%\SysWow64\LogFiles

  - %systemroot%\Microsoft.NET\assembly\GAC_MSIL

    > [!NOTE]
    > Обратите внимание, что эти пути являются специфическими для версии Skype для бизнес-сервера.

  - %programfiles%\Skype для бизнеса Server 2015

  - %programfiles%\Common Files\Skype for Business Server 2015\Watcher Node

  - %programfiles%\Common Files\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype для бизнеса Online

  - %SystemDrive%\RtcReplicaRoot

  - Хранилище обмена файлами (указанное в topology Builder). Хранилища файлов указаны в Topology Builder.

  - SQL Server данных и файлов журналов, в том числе для базы данных, магазина пользователей, архивного магазина, магазина мониторинга и магазина приложений. Файлы баз данных и журналов могут быть указаны в Topology Builder. Подробные сведения о данных и файлах журналов для каждой базы данных, включая имена по умолчанию, [см.](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) в SQL Server data and Log File Placement in the Deployment documentation.

  - SQL Server данных и файлов журналов, в том числе для базы данных front-end, магазина Skype для бизнеса и магазина RtcDatabase. Обычно они находятся под %localdrive%\CSData.