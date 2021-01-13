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
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a>Исключения антивирусной проверки для Skype для бизнеса Server

Обзор меж антивирусного сканера со Skype для бизнеса Server.

Чтобы антивирусная программа не помешала работе Skype для бизнеса Server, необходимо исключить определенные процессы и каталоги для каждого сервера или роли сервера Skype для бизнеса Server, на котором работает антивирусная программа. Следует исключить следующие процессы и каталоги:

> [!NOTE]
> Папки и расположения файлов, перечисленные ниже, являются расположениями по умолчанию для Skype для бизнеса Server. Для всех местоположений, для которых вы не использовали значение по умолчанию, исключите расположения, указанные для организации, а не расположения по умолчанию, указанные в этом разделе.

> [!IMPORTANT]
> Обратите внимание, что некоторым антивирусным программам могут потребоваться абсолютные, а не относительные пути, для списка исключений.

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

- Процессы службы windows Fabric Host Service:

  - Fabric.exe

  - FabricDCA.exe

  - FabricHost.exe

- Процессы IIS:

  - %systemroot%\system32\inetsrv\w3wp.exe

  - %systemroot%\SysWOW64\inetsrv\w3wp.exe

- SQL Server Back-End процессов:

    > [!NOTE]
    > Обратите внимание, что эти пути являются специфическими для SQL Server версии.

  - %ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe

  - %ProgramFiles%\Microsoft SQL Server\MSRS11. MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe

  - %ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe

- SQL Server Front-End процессов:

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe

  - Экземпляр RTC установки Standard Edition

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe

- Каталоги и файлы:

  - %systemroot%\System32\LogFiles

  - %systemroot%\SysWow64\LogFiles

  - %systemroot%\Microsoft.NET\assembly\GAC_MSIL

    > [!NOTE]
    > Обратите внимание, что эти пути являются специфическими для версии Skype для бизнеса Server.

  - %programfiles%\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Server 2015\Watcher Node

  - %programfiles%\Common Files\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Online

  - %SystemDrive%\RtcReplicaRoot

  - Хранилище файлового файла (указано в построителе топологий). Хранилища файлов указаны в построителье топологий.

  - SQL Server данных и журналов, в том числе для тыловой базы данных, пользовательского хранения, архивного хранения, мониторинга и приложения. Файлы базы данных и журналов можно у указаны в построителье топологий. Подробные сведения о данных и файлах журналов для каждой базы данных, включая имена по умолчанию, см. в SQL Server [data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.

  - SQL Server данных и журналов, в том числе для базы данных переднего входа, магазина Skype для бизнеса и хранения RtcDatabase. Обычно они находятся в %localdrive%\CSData.


