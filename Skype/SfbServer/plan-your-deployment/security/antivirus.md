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
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895967"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a>Антивирусная программа сканирования исключения для Скайп для Business Server

Обзор взаимодействия антивирусную программу с Скайп для Business Server.

В этой статье представлены рекомендации, которые могут помочь определить причину нестабильной на компьютере, на котором выполняется поддерживаемая версия Microsoft Windows при использовании с помощью антивирусных программ в домене Active Directory администратора среда или управляемой бизнес-среде.

Мы рекомендуем временно применяются следующие действия, чтобы оценить в системе. Если производительность системы или стабильность улучшена благодаря рекомендации, которые выполняются в этой статье, обратитесь к поставщику антивирусной программы за инструкциями или обновленной версией антивирусное программное обеспечение.

Эта статья содержит сведения, показано, как снижении уровня безопасности или временно отключить функции безопасности на компьютере. Можно внести эти изменения, чтобы понять причину конкретной проблемы. Прежде чем вносить изменения, рекомендуется оценить риски, связанные с ними в существующей среде. Если данный метод обхода, выполните все необходимые дополнительные меры для защиты компьютера и поиск файлов, которые больше не сканируются антивирусной программой.

Чтобы убедиться, что антивирусную программу не влияет на операции Скайп для Business Server, необходимо исключить конкретные процессы и каталоги для каждого Скайп для Business Server сервер или роль сервера, на котором выполняется антивирусную программу. Исключите перечисленные ниже процессы и каталоги.

> [!NOTE]
> Папка и файл расположения, перечисленных ниже — это расположение по умолчанию для Скайп Business Server. Если в вашей организации какие-либо из этих объектов расположены в других местах, укажите соответствующие пути.

> [!IMPORTANT]
> Обратите внимание, что в некоторых антивирусных программах в списке исключений необходимо указывать абсолютные пути, а не относительные.

- Скайп для процессов Business Server:

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
    > Обратите внимание на то, что эти пути относятся к Скайп для версии Business Server.

  - %programfiles%\Skype для бизнеса Server 2015

  - %programfiles%\Common Files\Skype для бизнеса Server 2015\Watcher Node

  - %programfiles%\Common Files\Skype для бизнеса Server 2015

  - %programfiles%\Common Files\Skype для бизнеса Online

  - %SystemDrive%\RtcReplicaRoot

  - Хранилище общих папок (указывается в построителе топологий). Хранилища файлов задаются в построителе топологий.

  - Файлы данных и журналов сервера SQL Server, включая объекты внутренней базы данных, хранилища пользователей, архивов, мониторинга и приложений. Файлы баз данных и журналов можно указать в построителе топологий. Подробные сведения о файлах данных и журналов для каждой базы, включая имена по умолчанию, см. в статье [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) в разделе, посвященном документации развертывания.

  - SQL Server файлов данных и журналов, в том числе для интерфейсных базы данных, Скайп для хранения бизнес и RtcDatabase хранилища. Как правило, они находятся в папке %localdrive%\CSData.


