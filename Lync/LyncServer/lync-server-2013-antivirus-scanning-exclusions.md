---
title: 'Lync Server 2013: исключения антивирусной проверки'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Antivirus scanning exclusions for Lync Server 2013
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440138(v=OCS.15)
ms:contentKeyID: 57793042
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f6f3e9afc3bd17f5cba4caa7619cb562be069942
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187262"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a>Исключения антивирусной проверки для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2015-11-02_

Чтобы антивирусное программное обеспечение не влияло на работу Lync Server 2013, необходимо исключить конкретные процессы и каталоги для каждого сервера или роли сервера Lync Server 2013, на которых запускается антивирусное программное обеспечение. Необходимо исключить следующие процессы и каталоги:

<div>


> [!NOTE]  
> Ниже указаны расположения файлов и папок по умолчанию для Lync Server 2013. Для всех расположений, для которых не использовалось значение по умолчанию, исключите расположения, указанные для Организации, вместо расположений по умолчанию, указанных в этом разделе.



</div>

<div>


> [!IMPORTANT]  
> Обратите внимание на то, что некоторым антивирусным программам могут понадобиться абсолютные, не относительные пути, для списка исключений.



</div>

  - Lync Server 2013 процессы:
    
      - ABServer. exe
    
      - Акпмкусвк. exe
    
      - Асмкусвк. exe
    
      - Авмкусвк. exe
    
      - Чаннелсервице. exe
    
      - ClsAgent. exe
    
      - Комплианцесервице. exe
    
      - Датамкусвк. exe
    
      - Прокси-сервер данных. exe
    
      - Филетрансферажент. exe
    
      - Иммкусвк. exe
    
      - Лиссвк. exe
    
      - Мастеррепликаторажент. exe
    
      - Медиарелайсвк. exe
    
      - Медиатионсерверсвк. exe
    
      - Мрассвк. exe
    
      - Оксаппсерверхост. exe
    
      - Репликарепликаторажент. exe
    
      - Репликатионапп. exe
    
      - Ртчост. exe
    
      - RTCSrv. exe
    
      - Ксмпппрокси. exe
    
      - Ксмпптгв. exe

  - Процессы службы узла Windows Fabric:
    
      - Fabric. exe
    
      - Фабрикдка. exe
    
      - Фабричост. exe

  - Процессы IIS:
    
      - % SystemRoot%\\system32\\инетсрв\\w3wp. exe
    
      - % SystemRoot%\\SysWOW64\\инетсрв\\w3wp. exe

  - Фоновые процессы SQL Server:
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSSQL11. MSSQLSERVER\\MSSQL\\бинн\\SQLServr. exe
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSRS11. Репортингсервицессервице\\. exe\\Report\\Reporting Services: сервер_отчетов bin\\
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSAS11. MSSQLSERVER\\OLAP\\bin\\MSMDSrv. exe

  - Интерфейсные процессы SQL Server:
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSSQL11. ЛИНКЛОКАЛ\\MSSQL\\бинн\\SQLServr. exe
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSSQL11. RTCLOCAL\\MSSQL\\бинн\\SQLServr. exe

  - Каталоги и файлы:
    
      - % SystemRoot%\\system32\\файлов журнала
    
      - % SystemRoot%\\SysWOW64\\файлов журнала
    
      - % SystemRoot%\\Microsoft.NET\\сборки\\GAC\_
    
      - % ProgramFiles%\\Microsoft Lync Server 2013
    
      - % ProgramFiles%\\общих файлов\\для узла-наблюдателя\\Microsoft Lync Server 2013
    
      - % ProgramFiles%\\общих файлов\\, Microsoft Lync Server 2013
    
      - % SystemDrive%\\рткрепликарут
    
      - Хранилище файлового ресурса (указано в построителе топологий). Хранилища файлов указываются в построителе топологий.
    
      - Файлы данных и журналов SQL Server, в том числе для серверной базы данных, хранилища пользователей, архивного хранилища, мониторинга и хранилища приложений. В построителе топологий можно указать файлы баз данных и журналов. Сведения о файлах данных и журналов для каждой базы данных, включая имена по умолчанию, можно найти в разделе [Data SQL Server and File log Placement for Lync server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) в документации по развертыванию.
    
      - Файлы данных и журналов SQL Server, в том числе для интерфейсной базы данных, магазина Lync и хранилища Рткдатабасе. Обычно они находятся в папке% локалдриве\\% ксдата.

</div>

<span> </span>

</div>

</div>

</div>

