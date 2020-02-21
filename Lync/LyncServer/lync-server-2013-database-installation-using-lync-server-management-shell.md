---
title: 'Lync Server 2013: Установка базы данных с помощью командной консоли Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database installation using Lync Server Management Shell
ms:assetid: c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398832(v=OCS.15)
ms:contentKeyID: 48185401
ms.date: 06/16/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 443f353a43c2fdfd2f9fc8c7ce1a1b20c11a4a84
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a>Установка базы данных с помощью командной консоли Lync Server в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2016-06-16_

Разделение ролей и обязанностей между администраторами серверов и администраторами SQL Server может привести к задержкам при реализации. Для устранения этих проблем Lync Server 2013 использует управление доступом на основе ролей (RBAC). В некоторых случаях администратор SQL Server должен управлять установкой баз данных на сервере SQL Server вне RBAC. Консоль управления Lync Server 2013 позволяет администратору SQL Server запускать командлеты Windows PowerShell, предназначенные для настройки баз данных с использованием правильных файлов данных и журналов. Дополнительные сведения см [в разделе разрешения на развертывание для SQL Server в Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

<div class=" ">


> [!IMPORTANT]  
> В следующей процедуре предполагается, что по крайней мере на сервере Lync Server 2013 OCSCore. msi (sqlncli. msi) установлены объекты управления Microsoft SQL Server 2012 Microsoft SQL Server (sqlncli. msi), типы CLR для Microsoft SQL Server 2012 и Microsoft SQL Server 2012 ADOMD.NET. OCSCore. msi находится на установочном носителе в каталоге \Setup\AMD64\Setup Остальные компоненты находятся в \Setup\amd64. Кроме того, подготовка Active Directory для Lync Server 2013 успешно завершена.



</div>

**Install-CsDatabase** — это командлет Windows PowerShell, который используется для установки баз данных. Командлет **Install – CsDatabase** содержит большое количество параметров, которые рассматриваются в этом разделе. Дополнительные сведения о возможных параметрах см. в документации по командной консоли Lync Server 2013.

<div class=" ">


> [!WARNING]  
> Чтобы избежать снижения производительности и возможных проблем с истечением времени, всегда используйте полные доменные имена при обращении к серверам на основе SQL Server. Избегайте использования ссылок только на имена узлов. Например, используйте sqlbe01.contoso.net, но не используйте SQLBE01.



</div>

Для установки баз данных **Install – CsDatabase** использует три основных метода размещения баз данных на подготовленном сервере на основе SQL Server:

  - Выполните командлет **Install CsDatabase** без Датабасепасс или уседефаултсклпас. Командлет использует встроенный алгоритм для определения лучшего размещения файлов журнала и данных. Алгоритм работает только для изолированных реализаций SQL Server.

  - Выполните командлет **Install — CsDatabase** с параметром датабасепасс. Встроенный алгоритм оптимизации расположений журналов и файлов данных не используется, если задан параметр Датабасепасс. С помощью этого параметра можно определить расположения, в которых будут развернуты файлы журнала и данных.

  - Выполните командлет **Install — CsDatabase** с уседефаултсклпасс. Этот параметр не использует встроенный алгоритм для оптимизации расположений файлов журнала и данных. Файл журнала и данных развертывается в соответствии с параметрами по умолчанию, установленными администратором SQL Server. Эти пути обычно задаются для автоматического администрирования файлов журналов и данных на SQL Server заранее и не связаны с настройкой Lync Server 2013.

  - Параметр DatabasePathMap также можно использовать для явного указания расположения для каждой базы данных и соответствующего файла журнала.

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a>Использование командлетов Windows PowerShell для настройки центрального хранилища управления SQL Server

1.  Войдите на любой компьютер, используя учетные данные администратора для создания баз данных на сервере SQL Server. Дополнительные сведения см [в разделе разрешения на развертывание для SQL Server в Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

2.  Откройте консоль управления Lync Server 2013. Если вы не настроили политику выполнения для Windows PowerShell, необходимо настроить политику, чтобы разрешить выполнение сценариев Windows PowerShell. Дополнительные сведения см. в [https://go.microsoft.com/fwlink/p/?linkId=203093](https://go.microsoft.com/fwlink/p/?linkid=203093)разделе "Проверка политики выполнения".

3.  Используйте командлет **Install – CsDatabase** для установки центрального хранилища управления.
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <fully qualified domain name of SQL Server> 
        -SqlInstanceName <named instance> -DatabasePaths <logfile path>,<database file path> 
        -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn sqlbe.contoso.net -SqlInstanceName rtc -DatabasePaths "C:\CSDB-Logs","C:\CSDB-CMS" -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > Параметр Report является необязательным, но его можно использовать при документировании процесса установки.

    
    </div>

4.  **Install-CsDatabase – датабасепасс** может использовать до шести параметров Path, каждый из которых определяет пути для дисков, определенных в данных SQL Server и размещении файлов журналов. По логическим правилам конфигурации базы данных в Lync Server 2013 диски разбиваются на сегменты двух, четырех или шести. В зависимости от конфигурации SQL Server и количества сегментов вы будете предоставлять два пути, четыре пути или шесть путей.
    
    Если у вас три диска, журнал получает приоритет и файлы данных распределяются по завершении. Пример для сервера SQL Server, настроенного на шесть дисков:
    ```powershell
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```
5.  По завершении установки базы данных можно закрыть Lync Server 2013 Management Shell или перейти к установке баз данных, настроенных для Lync Server 2013, определенных в построителе топологий.

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a>Использование командлетов Windows PowerShell для настройки баз данных, настроенных для топологии SQL Server

1.  Чтобы установить базы данных, настроенные в построителе топологий для Lync Server 2013, администратор Lync Server 2013 должен опубликовать эту топологию. Дополнительные сведения см в статье [Publishing Topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) в документации по развертыванию.

2.  Войдите на любой компьютер, используя учетные данные администратора для создания баз данных на сервере SQL Server. В этом разделе представлены [разрешения на развертывание SQL Server в Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Чтобы настроить базы данных на основе SQL Server, убедитесь, что учетная запись администратора SQL Server, используемая для выполнения описанных здесь действий, также является членом группы "Администраторы" (или аналогичной) на сервере SQL Server, где размещается центральное управление Роль сервера. Это особенно важно для проверки наличия дополнительных пулов Lync Server 2013, требующих установки или настройки базы данных SQL Server. Например, если развертывается второй пул (pool02), но роль сервера центрального управления удерживается pool01. Группа администраторов SQL Server (или аналогичная) должна иметь разрешения для баз данных на основе SQL Server.

    
    </div>

3.  Откройте Lync Server 2013 Management Shell, если она еще не открыта.

4.  Командлет **Install – CsDatabase** используется для установки баз данных, настроенных в построителе топологий.
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <fully qualified domain name of SQL Server> 
         -DatabasePaths <logfile path>,<database file path> -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe.contoso.net 
        -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > Параметр Report является необязательным, но его можно использовать при документировании процесса установки.

    
    </div>

5.  После завершения установки базы данных закройте консоль управления Lync Server 2013.

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a>Использование командлетов Windows PowerShell для настройки топологии SQL Server с помощью параметра DatabasePathMap

1.  Чтобы установить базы данных для Lync Server 2013, администратор Lync Server должен создать пути и развернуть файлы баз данных и файлы журнала в соответствии с предварительно определенным набором правил.

2.  Войдите на любой компьютер, используя учетные данные администратора для создания баз данных на сервере SQL Server. В этом разделе представлены [разрешения на развертывание SQL Server в Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Чтобы настроить базы данных на основе SQL Server, убедитесь, что учетная запись администратора SQL Server, используемая для выполнения описанных здесь действий, также является членом группы "Администраторы" (или аналогичной) на сервере SQL Server, где размещается центральное управление Роль сервера. Это особенно важно для проверки наличия дополнительных пулов Lync Server, в которых требуется установка или Настройка базы данных SQL Server. Например, если развертывается второй пул (pool02), но роль сервера центрального управления удерживается pool01. Группа администраторов SQL Server (или аналогичная) должна иметь разрешения для баз данных на основе SQL Server.

    
    </div>

3.  Откройте командную консоль Lync Server, если она еще не открыта.

4.  Используйте командлет **Install-CsDatabase** с параметром DatabasePathMap и хэш-таблицей PowerShell для установки баз данных, настроенных в построителе топологий.

5.  В примере кода пути, определенные для баз данных, можно определить с помощью параметра – DatabasePathMap и указанной хэш-таблицы, как показано ниже (в примере используется "C:\\ксдата" для всех файлов базы данных (MDF) и "C:\\кслогфилес" для всех файлов журнала (LDF). Папка будет создана при необходимости в Install-CsDatabase):
    ```powershell
    $pathmap = @{
    "BackendStore:BlobStore:DbPath"="C:\CsData";"BackendStore:BlobStore:LogPath"="C:\CsLogFiles"
    "BackendStore:RtcSharedDatabase:DbPath"="C:\CsData";"BackendStore:RtcSharedDatabase:LogPath"="C:\CsLogFiles"
    "ABSStore:AbsDatabase:DbPath"="C:\CsData";"ABSStore:AbsDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:RgsConfigDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsConfigDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:RgsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsDynDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:CpsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:CpsDynDatabase:LogPath"="C:\CsLogFiles"
    "ArchivingStore:ArchivingDatabase:DbPath"="C:\CsData";"ArchivingStore:ArchivingDatabase:LogPath"="C:\CsLogFiles"
    "MonitoringStore:MonitoringDatabase:DbPath"="C:\CsData";"MonitoringStore:MonitoringDatabase:LogPath"="C:\CsLogFiles"
    "MonitoringStore:QoEMetricsDatabase:DbPath"="C:\CsData";"MonitoringStore:QoEMetricsDatabase:LogPath"="C:\CsLogFiles"
    }
    Install-CsDatabase -ConfigureDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap
    ```
6.  Так как база данных и файлы журнала явно называются их расположением на целевом сервере баз данных, можно определить конкретные расположения для базы данных и журнала каждой службы. В следующем примере базы данных размещаются для каждого конкретного типа службы на разных дисках, а связанные файлы журналов — на другом. Например:
    
      - Все базы данных RTC до "D\\: рткдатабасе"
    
      - Все файлы журналов RTC в "E:\\ртклогс"
    
      - Все базы данных хранилища приложений в "F\\: кпсдатабасес"
    
      - Все журналы хранилища приложений в "G:\\кпслогс"
    
      - Все базы данных хранилища группы ответа в "H\\: ргсдатабасес"
    
      - Все журналы хранилища группы ответа в "I:\\ргслогс"
    
      - Все базы данных хранилища адресных книг в "\\J: абсдатабасес"
    
      - Все файлы журнала хранилища адресной книги в "K:\\абслогс"
    
      - Все базы данных хранилища архива в "L\\: арчивингдатабасес"
    
      - Все журналы хранилища архивации в "M\\: арчивинглогс"
    
      - Все базы данных хранилища данных мониторинга в "\\N: мониторингдатабасес"
    
      - Все файлы журналов хранилища мониторинга в "O:\\мониторинглогфилес"
    
    <!-- end list -->
    
    ```powershell    
    $pathmap = @{
    "BackendStore:BlobStore:DbPath"="D:\RTCDatabase";"BackendStore:BlobStore:LogPath"="E:\RTCLogs"
    "BackendStore:RtcSharedDatabase:DbPath"="D:\RTCDatabase";"BackendStore:RtcSharedDatabase:LogPath"="E:\RTCLogs"
    "ABSStore:AbsDatabase:DbPath"="J:\ABSDatabases";"ABSStore:AbsDatabase:LogPath"="K:\ABSLogs"
    "ApplicationStore:RgsConfigDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsConfigDatabase:LogPath"="G:\CPSLogs"
    "ApplicationStore:RgsDynDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsDynDatabase:LogPath"="I:\RGSLogs"
    "ApplicationStore:CpsDynDatabase:DbPath"="F:\CPSDatabases";"ApplicationStore:CpsDynDatabase:LogPath"="G:\CsLogFiles"
    "ArchivingStore:ArchivingDatabase:DbPath"="M:\ArchivingLogs";"ArchivingStore:ArchivingDatabase:LogPath"="N:\MonitoringDatabases"
    "MonitoringStore:MonitoringDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:MonitoringDatabase:LogPath"="O:\MonitoringLogfiles"
    "MonitoringStore:QoEMetricsDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:QoEMetricsDatabase:LogPath"="O:\MonitoringLogfiles"
    }
    
    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap
    ```
    
    С помощью параметра – DatabasePathMap можно определить любую комбинацию сопоставления букв логических дисков, которая обеспечивает наилучшее решение для требований к производительности и размещению SQL Server.

Если вы настраиваете файлы данных и файлы журналов базы данных с помощью метода **DatabasePathMap** , вам потребуется внести небольшое изменение в обычный процесс при использовании построителя топологий. Как правило, необходимо определить варианты топологии, опубликовать топологию и выбрать развертывание выбранных баз данных.

Если вы использовали **DatabasePathMap** , вы уже выполнили третью часть процесса построителя топологии. В случае, если полностью настроенный сервер базы данных был предварительно настроен в построителе топологий, вы все равно должны определить все роли сервера и параметры, а затем отменить выбор параметра для создания баз данных.

</div>

</div>

<span> </span>

</div>

</div>

</div>

