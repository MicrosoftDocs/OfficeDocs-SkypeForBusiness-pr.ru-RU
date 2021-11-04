---
title: Исключения для антивирусного сканирования для Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Обзор межоперации антивирусного сканера с Skype для бизнеса Server.
ms.openlocfilehash: 105abd3618c5e869681edc31321a07ab0bce9d57
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60737655"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a>Исключения для антивирусного сканирования для Skype для бизнеса Server

Обзор межоперации антивирусного сканера с Skype для бизнеса Server.

Чтобы антивирусный сканер не мешал работе Skype для бизнеса Server, необходимо исключить конкретные процессы и каталоги для каждой роли Skype для бизнеса Server сервера или сервера, на которой работает антивирусный сканер. Следует исключить следующие процессы и каталоги:

> [!NOTE]
> Папки и расположения файлов, перечисленные ниже, являются расположениями по умолчанию для Skype для бизнеса Server. Для любых местоположений, для которых не используется значение по умолчанию, исключите расположения, указанные для организации, а не расположения по умолчанию, указанные в этой теме.

> [!IMPORTANT]
> Обратите внимание, что некоторым антивирусным программам могут потребоваться абсолютные, а не относительные пути для списка исключений.

- Skype для бизнеса Server процессы:

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

- Windows Fabric Процессы службы host:

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

  - выпуск Standard Экземпляр установки RTC

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe

- Каталоги и файлы:

  - %systemroot%\System32\LogFiles

  - %systemroot%\SysWow64\LogFiles

  - %systemroot%\Microsoft.NET\assembly\GAC_MSIL

    > [!NOTE]
    > Обратите внимание, что эти пути являются определенными для Skype для бизнеса Server версии.

  - %programfiles%\Skype для бизнеса Server 2015

  - %programfiles%\Common Files\Skype для бизнеса Server 2015\Watcher Node

  - %programfiles%\Common Files\Skype для бизнеса Server 2015

  - %programfiles%\Common Files\Skype для бизнеса Online

  - %SystemDrive%\RtcReplicaRoot

  - Хранилище обмена файлами (указанное в topology Builder). Хранилища файлов указаны в Topology Builder.

  - SQL Server данных и файлов журналов, в том числе для базы данных, магазина пользователей, архивного магазина, магазина мониторинга и магазина приложений. Файлы баз данных и журналов могут быть указаны в Topology Builder. Сведения о данных и файлах журналов для каждой базы данных, включая имена по умолчанию, [см.](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) в SQL Server в документации по развертыванию.

  - SQL Server данных и файлов журналов, в том числе для базы данных front-end, Skype для бизнеса магазина и магазина RtcDatabase. Обычно они находятся под %localdrive%\CSData.