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
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server-2015"></a>Исключения из антивирусной проверки для Skype для бизнеса Server 2015
 
Обзор взаимодействия антивирусную программу с Скайп для Business Server 2015. 
  
Чтобы убедиться, что антивирусную программу не влияет на операции Скайп для Business Server 2015, необходимо исключить конкретные процессы и каталоги для каждого Скайп для Business Server 2015 сервер или роль сервера, на котором выполняется антивирусную программу. Исключите перечисленные ниже процессы и каталоги.
  
> [!NOTE]
> Папка и файл расположения, перечисленных ниже — это расположение по умолчанию для Скайп Business Server 2015. Если в вашей организации какие-либо из этих объектов расположены в других местах, укажите соответствующие пути. 
  
> [!IMPORTANT]
> Обратите внимание, что в некоторых антивирусных программах в списке исключений необходимо указывать абсолютные пути, а не относительные. 
  
- Скайп для процессов Business Server 2015:
    
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
    
- Процессы службы узла Windows Fabric
    
  - Fabric.exe
    
  - FabricDCA.exe
    
  - FabricHost.exe
    
- Процессы IIS
    
  - %systemroot%\system32\inetsrv\w3wp.exe
    
  - %systemroot%\SysWOW64\inetsrv\w3wp.exe
    
- Внутренние процессы сервера SQL Server
    
    > [!NOTE]
    > Обратите внимание, что эти пути зависят от версии SQL Server. 
  
  - %ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe
    
  - %ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe
    
  - %ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe
    
- Внешние процессы сервера SQL Server
    
  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe
    
  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe
    
  - Экземпляр RTC установки Standard Edition 
    
  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe
    
- Каталоги и файлы
    
  - %systemroot%\system32\LogFiles
    
  - %systemroot%\SysWow64\LogFiles
    
  - %systemroot%\Microsoft.NET\assembly\GAC_MSIL
    
  - %programfiles%\Skype для бизнеса Server 2015
    
  - %programfiles%\Common Files\Skype для бизнеса Server 2015\Watcher Node
    
  - %programfiles%\Common Files\Skype для бизнеса Server 2015
    
  - %programfiles%\Common Files\Skype для бизнеса Online
    
  - %SystemDrive%\RtcReplicaRoot
    
  - Хранилище общих папок (указывается в построителе топологий). Хранилища файлов задаются в построителе топологий.
    
  - Файлы данных и журналов сервера SQL Server, включая объекты внутренней базы данных, хранилища пользователей, архивов, мониторинга и приложений. Файлы баз данных и журналов можно указать в построителе топологий. Для получения дополнительных сведений о файлах данных и журналов для каждой базы данных, включая имена по умолчанию содержатся в документации по развертыванию [данных SQL Server и размещение файлов журнала](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) .
    
  - SQL Server файлов данных и журналов, в том числе для интерфейсных базы данных, Скайп для хранения бизнес и RtcDatabase хранилища. Как правило, они находятся в папке %localdrive%\CSData.
    

