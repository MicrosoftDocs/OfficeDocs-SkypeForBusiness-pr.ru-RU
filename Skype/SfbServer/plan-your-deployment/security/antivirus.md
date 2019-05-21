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
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a>Исключения проверки антивирусной программы для Skype для бизнеса Server

Общие сведения о взаимодействиях антивирусных сканеров с Skype для бизнеса Server.

В этой статье приведены рекомендации, которые помогут администратору определить причину потенциальной нестабильности на компьютере с установленной версией Microsoft Windows при использовании антивирусной программы в домене Active Directory. среды или в управляемой бизнес-среде.

Мы рекомендуем временно применять эти процедуры для оценки системы. Если производительность или стабильность системы улучшились согласно рекомендациям, описанным в этой статье, обратитесь к поставщику антивирусной программы за инструкциями или в обновленной версии антивирусной программы.

В этой статье приведены сведения о том, как уменьшить параметры безопасности или временно отключить средства безопасности на компьютере. Вы можете внести эти изменения, чтобы понять природу определенной проблемы. Прежде чем вносить эти изменения, рекомендуется оценить риски, связанные с реализацией этого обходного пути в конкретной среде. Если вы реализуете это временное решение, выполните все необходимые дополнительные действия, чтобы защитить компьютер от вирусов, которые больше не проверяются антивирусными программами.

Чтобы антивирусная программа не мешала работе со Skype для бизнеса Server, необходимо исключить определенные процессы и каталоги для каждого сервера Skype для бизнеса Server или серверной роли, для которой вы запускаете антивирусную программу. Исключите перечисленные ниже процессы и каталоги.

> [!NOTE]
> Ниже указаны расположения файлов и папок, используемые в Skype для бизнеса Server по умолчанию. Если в вашей организации какие-либо из этих объектов расположены в других местах, укажите соответствующие пути.

> [!IMPORTANT]
> Обратите внимание, что в некоторых антивирусных программах в списке исключений необходимо указывать абсолютные пути, а не относительные.

- Серверные процессы Skype для бизнеса:

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
  
  - Линкбаккупсервице. exe

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

  - %systemroot%\System32\LogFiles

  - %systemroot%\SysWow64\LogFiles

  - %systemroot%\Microsoft.NET\assembly\GAC_MSIL

    > [!NOTE]
    > Обратите внимание, что эти пути специфичны для версии Skype для бизнеса Server.

  - %programfiles%\Skype для бизнеса Server 2015

  - %programfiles%\Common Files\Skype для бизнеса Server 2015\Watcher Node

  - %programfiles%\Common Files\Skype для бизнеса Server 2015

  - %programfiles%\Common Files\Skype для бизнеса Online

  - %SystemDrive%\RtcReplicaRoot

  - Хранилище общих папок (указывается в построителе топологий). Хранилища файлов задаются в построителе топологий.

  - Файлы данных и журналов сервера SQL Server, включая объекты внутренней базы данных, хранилища пользователей, архивов, мониторинга и приложений. Файлы баз данных и журналов можно указать в построителе топологий. Подробные сведения о файлах данных и журналов для каждой базы, включая имена по умолчанию, см. в статье [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) в разделе, посвященном документации развертывания.

  - Файлы данных и журналов SQL Server, в том числе для интерфейсной базы данных, магазина Skype для бизнеса и Рткдатабасе магазина. Как правило, они находятся в папке %localdrive%\CSData.


