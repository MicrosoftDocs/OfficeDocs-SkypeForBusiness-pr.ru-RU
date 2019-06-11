---
title: 'Lync Server 2013: исключения из антивирусной проверки'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Antivirus scanning exclusions for Lync Server 2013
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440138(v=OCS.15)
ms:contentKeyID: 57793042
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6f354b93bf21f054e9b5b24e3befd1787279bbe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a>Исключения из антивирусной проверки для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2015-11-02_

Чтобы антивирусная программа не мешала работе с Lync Server 2013, необходимо исключить определенные процессы и каталоги для каждого сервера или серверной роли Lync Server 2013, на которых вы запускаете антивирусную программу. Исключите перечисленные ниже процессы и каталоги.

<div>


> [!NOTE]  
> Ниже указаны расположения файлов и папок для Lync Server 2013 по умолчанию. Если в вашей организации какие-либо из этих объектов расположены в других местах, укажите соответствующие пути.



</div>

<div>


> [!IMPORTANT]  
> Обратите внимание, что в некоторых антивирусных программах в списке исключений необходимо указывать абсолютные пути, а не относительные.



</div>

  - Lync Server 2013 процессы:
    
      - ABServer.exe
    
      - Акпмкусвк. exe
    
      - ASMCUSvc.exe
    
      - AVMCUSvc.exe
    
      - ChannelService.exe
    
      - ClsAgent.exe
    
      - ComplianceService.exe
    
      - DataMCUSvc.exe
    
      - DataProxy.exe
    
      - FileTransferAgent.exe
    
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
    
      - % SystemRoot%\\system32\\инетсрв\\w3wp. exe
    
      - % SystemRoot%\\SysWOW64\\инетсрв\\w3wp. exe

  - Внутренние процессы сервера SQL Server
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSSQL11. MSSQLSERVER\\MSSQL\\бинн\\SQLServr. exe
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSRS11. ReportServer\\\\в службах\\отчетов\\репортингсервицессервице. exe
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSAS11. MSSQLSERVER\\OLAP\\bin\\, программа MSMDSrv. exe

  - Внешние процессы сервера SQL Server
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSSQL11. ЛИНКЛОКАЛ\\MSSQL\\бинн\\SQLServr. exe
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSSQL11. РТКЛОКАЛ\\MSSQL\\бинн\\SQLServr. exe

  - Каталоги и файлы
    
      - файлы журнала%\\systemroot\\% system32
    
      - журналы% systemroot\\%\\SysWOW64
    
      - MSIL% systemroot\\%\\Microsoft.NET\\Assembly\_GAC
    
      - % ProgramFiles%\\Microsoft Lync Server 2013
    
      - % ProgramFiles%\\общие файлы\\, узел наблюдателя Microsoft\\Lync Server 2013
    
      - % ProgramFiles%\\распространенных файлов\\в Microsoft Lync Server 2013
    
      - % SystemDrive%\\рткрепликарут
    
      - Хранилище общих папок (указывается в построителе топологий). Хранилища файлов задаются в построителе топологий.
    
      - Файлы данных и журналов сервера SQL Server, включая объекты внутренней базы данных, хранилища пользователей, архивов, мониторинга и приложений. Файлы баз данных и журналов можно указать в построителе топологий. Дополнительные сведения о файлах данных и журналов для каждой базы данных, включая имена по умолчанию, можно найти в разделе [данные и расположение файлов журнала SQL Server для Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) в документации по развертыванию.
    
      - Файлы данных и журналов SQL Server, в том числе для интерфейсной базы данных, магазина Lync и Рткдатабасе Store. Обычно они находятся в рамках% локалдриве\\% ксдата.

</div>

<span> </span>

</div>

</div>

</div>

