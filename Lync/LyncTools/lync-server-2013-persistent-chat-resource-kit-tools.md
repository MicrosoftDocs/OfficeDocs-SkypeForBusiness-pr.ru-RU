---
title: Средства набора ресурсов сохраняемого чата Lync Server 2013
description: Средства набора ресурсов сохраняемого чата Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Persistent Chat Resource Kit Tools
ms:assetid: 7a34d2ba-eb25-4e22-92d1-b9baf81b102c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945599(v=OCS.15)
ms:contentKeyID: 51541423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 336e81c97da73da47eee654161a7d8d8956f9edb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542355"
---
# <a name="lync-server-2013-persistent-chat-resource-kit-tools"></a>Средства набора ресурсов сохраняемого чата Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-24_

Средства набора ресурсов сохраняемого чата Lync Server 2013 помогают упростить выполнение повседневных задач для ИТ ИТ ИТ, которые развертывают и управляют Lync Server 2013 для сервера сохраняемого чата. В дополнение к инструкциям по установке в этом разделе описывается назначение каждого средства и приводятся примеры его использования.

<div>

## <a name="installation-of-the-resource-kit-tools"></a>Установка средств набора ресурсов

Для установки средств набора ресурсов Lync Server 2013, скачайте **PersistentChatReskit.msi**. Запустите **PersistentChatReskit.msi** , чтобы выполнить простую установку. MSI устанавливает все средства, указанные в следующем пути: \\ **Program Files \\ Microsoft Lync Server 2013 \\ Resource Chat Server Resource Kit**. В этой папке есть инструменты, которые представляют собой автономные исполняемые файлы. Средства, у которых также есть файлы, находятся в своих вложенных папках.

<div>


> [!IMPORTANT]  
> После установки средств набора ресурсов Lync Server 2013, необходимо установить <STRONG>PsExec.exe</STRONG> и скопировать <STRONG>PsExec.exe</STRONG> по следующему пути: \\ <STRONG>Program Files \ Microsoft Lync Server 2013 \ сервер ресурсов кит\чатстресстул</STRONG>. Если вы не копируете <STRONG>PsExec.exe</STRONG>, средство стрессового чата выполняет исключение ошибки и не выполняется должным образом. Перед запуском средства убедитесь, что выполнены соответствующие требования. Более подробную информацию об установке <STRONG>PsExec.exe</STRONG>можно узнать в разделе <A href="https://go.microsoft.com/fwlink/p/?linkid=282246">https://go.microsoft.com/fwlink/p/?LinkId=282246</A> .



</div>

</div>

<div>

## <a name="supported-environments"></a>Поддерживаемые среды

Для оптимальной производительности Lync Server 2013, средства набора ресурсов необходимо установить в той же среде и с теми же спецификациями, что и для Lync Server 2013.

</div>

<div>

## <a name="resource-kit-tools-overview"></a>Общие сведения о средствах набора ресурсов

Ниже приведены средства, доступные в наборе ресурсов сохраняемого чата Lync Server 2013. В следующем разделе представлено описание каждого средства, включая требования и примеры использования.

  - аффчекк

  - чатмониторингсуммари

  - Средство Чатстресс

  - чатупградеверифиер

  - чатусажерепорт

  - счедулеадсинкфорпринЦипал

</div>

<div>

## <a name="affcheck"></a>аффчекк

<div>

## <a name="description"></a>Описание

Средство Аффчекк проверяет, совпадают записи принадлежности пользователей и групп сохраняемого чата для доменных служб Active Directory.

</div>

<div>

## <a name="requirements"></a>Требования

Средство устанавливается вместе с установщиком Персистентчатрескит на компьютере, присоединенном к домену.

Учетная запись пользователя, с которой запускается средство, должна иметь доступ на чтение к базе данных сохраняемого чата и доменным службам Active Directory.

</div>

<div>

## <a name="usage"></a>Применение

Настройте файл AffCheck.exe.config в соответствии с инструкциями в файле конфигурации и запустите средство Аффчекк без параметров командной строки. Ниже приведено содержимое AffCheck.exe.config по умолчанию.

**AffCheck.exe.config:**

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <appSettings>
        <!--Domain Controller IP Address-->
        <add key="LDAP" value="LDAP://0.0.0.0/"/>
        
        <!-- Domain DN  This is case sensitive, it must match exactly-->
        <add key="DomainComponent" value ="DC=DOMAIN,DC=COM"/>
        
        <!--Domain Administrator Login and Password-->
        <add key="DomainLogin" value="DOMAIN\Administrator"/>
        <add key="DomainPassword" value ="password"/>
        
        <!-- Connection string to Group Chat Database-->
        <add key="ConnectionString" value="data source=SQL_SERVER\INSTANCE;initial catalog=DATABASE_NAME;integrated security=SSPI"/>
        
        <!--Check group affiliations-->
        <add key="CheckGroups" value="true"/>
        
        <!--Check user affilations-->
        <add key="CheckUsers" value="true"/>
        
        <!--List all affiliations if there is a mismatch between database and active directory-->
        <add key="ListAffiliations" value="true"/>
    
        <!--If you need to offset the results of the number of affilations in AD(can be negative to add to AD parent count)-->
        <add key="Offset" value ="0"/>
    
        <!--If you need to ignore certain parents, provide a semi colon delimitted list.-->
        <add key="Ignore" value ="DC=uatest,DC=test,DC=contoso,DC=com;DC=test,DC=contoso,DC=com"/>
      </appSettings>
    </configuration>
  ```
</div>

</div>

<div>

## <a name="chatmonitoringsummary"></a>чатмониторингсуммари

<div>

## <a name="description"></a>Описание

Средство Персистентчатмониторингсуммари перемещает данные мониторинга сохраняемого чата из базы данных мониторинга в указанный CSV-файл журнала.

CSV-файл будет содержать разбиение сеансов сохраняемого чата по количеству сеансов, успешных сеансов, неожиданным сбоям, ожидаемым отказам и разбиению неожиданного сбоя по ИДЕНТИФИКАТОРу диагностики, количеству сбоев и описанию сбоя.

</div>

<div>

## <a name="requirements"></a>Требования

Установите средства набора ресурсов сохраняемого чата на компьютер, подключенный к домену, который имеет доступ к базе данных мониторинга.

Учетная запись пользователя, с помощью которой запускается средство, должна иметь доступ на чтение к базе данных мониторинга.

Файл PersistentChatMonitoringSummary.exe.config должен содержать \<connectionStrings\> раздел, определяющий строку подключения к базе данных мониторинга. Он также должен содержать ключ для Персистентчатендпоинтури, для которого будут собираться данные мониторинга, и путь к файлу для CSV-файла, который будет создан. Ознакомьтесь с примерами установленного файла конфигурации. Файл должен находиться в том же каталоге, что и средство.

</div>

<div>

## <a name="usage"></a>Применение

```Batch
    PersistentChatMonitoringSummary [-StartDateTime <date>] [-EndDateTime <date>]
```

Эти параметры определяют выбор данных:

**StartDateTime:** Дополнительно указывает дату начала периода выбора. Значение по умолчанию: 1/1/1753 12:00:00 AM

**EndDateTime:** При необходимости указывается последняя дата периода выбора. По умолчанию: Now

</div>

<div>

## <a name="example"></a>Пример

```Batch
    C:\Users\Administrator.VDOMAIN>Desktop\PersistentChatMonitoringSummary.exe
    Reading database connection information, Persistent Chat endpoint uri, and csv output path information from the application config file...
    Connecting to Monitoring database with connection string specified in the application config file...
    Gathering Persistent Chat Session Summary information between "1/1/1753 12:00:00 AM" and "11/19/2012 10:11:25 AM" for Persistent Chat Endpoint Uri "persistentChatEndpointUri@domain.com"...
    Press enter to continue or hit ctr-c if these settings are incorrect...
    
    The summary information about Persistent Chat sessions from the Monitoring database has been output to C:\PersistentChatMonitoring_dd4ace24-4c8a-4a3d-8fd4-591bdfacf47b.csv
    Press enter to exit...
```

</div>

</div>

<div>

## <a name="persistent-chat-stress-tool"></a>Средство нагрузочного тестирования сохраняемого чата

<div>

## <a name="description"></a>Описание

Средство стрессового чата позволяет легко имитировать использование сохраняемого чата для тестирования реальной производительности, в том числе разнообразных пользовательских моделей в соответствии с ожидаемыми сценариями использования.

</div>

<div>

## <a name="requirements"></a>Требования

Установите средства набора ресурсов сохраняемого чата на компьютер, присоединенный к домену, который имеет доступ к фоновой базе данных сохраняемого чата.

В дополнение к данному *контроллеру* компьютера потребуется несколько компьютеров *загрузчика* . Для каждых 10 000 пользователей в пользовательской модели вам потребуется по крайней мере 4 ГБ свободного ОЗУ на компьютере загрузчика. Например, для запуска с 80K пользователям потребуется около 32 ГБ ОЗУ на всех машинах загрузчика. Рекомендуется использовать по крайней мере три компьютера загрузчика, независимо от ожидаемой нагрузки.

На компьютерах загрузчика должна быть установлена платформа .NET 4,5 Framework, а также распространяемый компонент Visual C++ 2012.

</div>

<div>

## <a name="configuration"></a>Конфигурация

Скопируйте файлы Чатстресстул в общую папку, доступную на всех машинах загрузчика.

Создайте пользователей и каналы для использования при нагрузочном запуске:

  - Создайте как можно больше пользователей, для которых будет вызываться модель пользователя, включите их для Lync, а затем установите для их политики сохраняемого чата значение Enabled.

  - Создайте категорию для каналов стресса, а затем создайте столько комнат, сколько необходимо для этой категории. У категории должны быть все погрузки пользователей в список **разрешенных** пользователей (при добавлении подразделений), а для рабочих комнат — значение " **Открыть**".

  - Мы рекомендуем создавать лишние помещения для нагрузки. Вы можете создавать комнаты 50 000 с помощью следующей команды интерфейса командной строки Windows PowerShell:
    ```Powershell
        for ($i = 0; $i -le 50000; $i++) { New-CsPersistentChatRoom -Category <parent category> -Name "StressChan_$i" -Privacy Open }
    ```    

Измените файлы конфигурации в соответствии с вашей топологией:

В **LoaderProcess.exe.config**замените имя "Controller.contoso.com" на полное доменное имя компьютера контроллера (полное доменное имя).

В **StressLauncher.exe.config:**

1.  Измените значение параметра "Лоадербинари" на путь к общей папке.

2.  Замените "Админусер"/"Админпассворд" на учетные данные, которые имеют административный доступ к машинам загрузчика.

3.  Замените "Чаннелкатегори" на имя категории, в которой созданы каналы нагрузки в.

4.  Замените "Усернамепаттерн" и "Усерпассвордпаттерн" на шаблон, соответствующий вашим учетным данным пользователя. {0} заменяется номером индекса пользователя.

5.  Измените значение "Domain" на домен SIP для тестовой топологии.

6.  Замените строку "ConnectionString" на строку подключения для внутренней базы данных сохраняемого чата.

7.  Замените "Усериндексстарт" индексом первого пользователя нагрузки.

8.  Замените "Линкфкдн" на полное доменное имя интерфейсного пула.

9.  Измените список "machines", чтобы включить имена компьютеров для всех компьютеров загрузчика.

10. Измените значение baseAddress конечной точки службы (по умолчанию — "controller.contoso.com") до полного доменного имени компьютера контроллера.

</div>

<div>

## <a name="usage"></a>Применение

После завершения настройки откройте StressLauncher.exe на компьютере контроллера. Вы можете запустить Стресслаунчер как любой пользователь. Учетные данные, с которыми запускаются процессы загрузчика на машинах загрузчика, должны быть указаны в файле конфигурации. Кроме того, необходимо предоставить строку подключения, доступную для чтения, в фоновую базу данных сохраняемого чата. Если эта строка подключения использует встроенную проверку подлинности Windows, необходимо запустить Стресслаунчер в качестве пользователя, имеющего этот доступ.

При необходимости измените параметры пользовательской модели. Нажмите кнопку **начать загрузку** , чтобы начать выполнение. Через минуту пользователи начнут войти в систему, а индикатор выполнения начнет заполняться. На этом шаге контроллер может работать и принимать измерения производительности.

</div>

</div>

<div>

## <a name="chatupgradeverifier"></a>чатупградеверифиер

<div>

## <a name="description"></a>Описание

Чатупградеверифиер — это средство сравнения баз данных для сохраняемого чата. Средство сравнивает базу данных общения групп 2007 R2 или Group Chat 2010 (2007/2010Db) с базой данных сохраняемого чата 2013 (2013Db).

Средство проверит (по одному) каждую категорию, комнату сохраняемого чата и надстройку в версии 2007/2010Db, чтобы узнать, отображается ли она в 2013Db. Сравнение включает проверку всех параметров для категории, комнаты чата или надстройки, любых субъектов в области в категории и любой участник роли в категории либо в комнате чата. Если категория или комната чата не отображаются правильно в 2013Db, то различия будут выводиться в файл конфликтов. Если после обновления 2007/2010Db изменяется, а затем запускается это средство, в файл конфликтов будет выведено различие. Обратите внимание, что это приложение является только средством сравнения баз данных и не проверяет процесс обновления.

</div>

<div>

## <a name="requirements"></a>Требования

Установите средства набора ресурсов сохраняемого чата на компьютер, присоединенный к домену, который имеет доступ к внутренним базам данных сохраняемого чата (Предыдущая и текущая версии для сохраняемого чата).

Учетная запись пользователя, с помощью которой запускается средство, должна иметь доступ на чтение к базам данных сохраняемого чата.

Файл ChatUpgradeVerifier.exe.config должен содержать либо параметр GroupChat2007R2Db, либо параметр GroupChat2010Db со строкой подключения к соответствующей базе данных группового чата (Groupchat 2007R2 или 2010). Он также должен содержать параметр PersistentChat2013Db со строкой подключения к базе данных сохраняемого чата 2013.

</div>

<div>

## <a name="usage"></a>Применение

Запустите **чатупградеверифиер** без параметров.

</div>

<div>

## <a name="example"></a>Пример

![Выполнение ChatUpgradeVerifier.exe.](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "Выполнение ChatUpgradeVerifier.exe.")

</div>

</div>

<div>

## <a name="persistent-chat-usage-report"></a>Отчет об использовании сохраняемого чата

<div>

## <a name="description"></a>Описание

Средство Чатусажерепорт создает HTML-отчет об использовании службы сохраняемого чата.

</div>

<div>

## <a name="requirements"></a>Требования

Установите средства набора ресурсов сохраняемого чата на компьютер, присоединенный к домену, который имеет доступ к фоновой базе данных сохраняемого чата.

Учетная запись пользователя, с которой запускается средство, должна иметь доступ на чтение к базе данных сохраняемого чата.

Файл ChatUsageReport.exe.config должен содержать \<connectionStrings\> раздел, определяющий строку подключения для внутренней базы данных сохраняемого чата. Содержимое файла конфигурации по умолчанию включено в ссылку.

</div>

<div>

## <a name="usage"></a>Применение

```Powershell
    ChatUsageReport [-StartDate {date}] [-EndDate {date}] [-TopActiveUsers {n}] [-TopActiveRooms {n}] [-LeastActiveRooms {n}] [-RoomsInactiveSince {Date}] [-OutputFolder {path}]
```
Эти параметры определяют выбор данных:

**StartDate:** При необходимости определяет дату начала периода выбора в формате UTC. Значение по умолчанию: самая ранняя дата

**Дата окончания:** При необходимости указывает дату окончания периода выбора в формате UTC. По умолчанию: Now

Эти параметры определяют, как и какие данные отображаются:

**Топактивеусерс:** Если этот параметр указан, то отчет будет включать в себя n наиболее активных пользователей с точки зрения числа сообщений, которые пользователь опубликовал в комнате чата для выбранного периода. По умолчанию: 10

**Топактиверумс:** Если этот параметр указан, в отчет будут включены n большинства активных комнат чата с точки зрения числа сообщений, опубликованных в комнате за выбранный период. По умолчанию: 10

**Леастактиверумс:** Если этот параметр указан, в отчет будут включены n наименее активные комнаты чата с точки зрения числа сообщений, опубликованных в комнате чата для выбранного периода. В комнатах будет размещено по крайней мере одно сообщение. По умолчанию: 10

**Румсинактивесинце:** Если этот параметр указан, отчет будет включать список комнат чата, которые были неактивны с момента указанной даты. Значение по умолчанию: полное время

**Аутпутфолдер:** Папка, в которой будут размещены ChatUsageReport.html и изображения графиков. Это значение должно быть определено в файле конфигурации или в командной строке.

Все значения параметров командной строки также можно указать в файле ChatUsageReport.exe.config, расположенном в том же каталоге, что и средство. Если какое-либо значение указано как в файле конфигурации, так и в командной строке, значение в командной строке переопределит значение файла конфигурации.

</div>

<div>

## <a name="output"></a>Output

Отчет всегда будет включать следующие выходные данные:

  - Первые n большинства активных комнат чата по количеству записей сообщений за выбранный период.

  - Первые n наиболее активных пользователей по количеству записей сообщений за выбранный период.

  - Первые n наименее активные комнаты чата по количеству записей сообщений за выбранный период.

  - Комнаты чата, неактивные для всей жизни базы данных или с момента указанной даты.

  - Тенденция при отправке ежедневных сообщений за выбранный период.

  - Еженедельное сообщение об тренде для выбранного периода.

  - Месячная тенденция при отправке сообщения за выбранный период.

  - Общее количество записей в сообщениях за выбранный период.

  - Общее количество включенных комнат.

</div>

<div>

## <a name="example"></a>Пример

В следующем примере показано создание отчета об использовании за весь год 2001 и помещение отчета в Аутпутфолдер, указанный в ChatUsageReport.exe.config.

```Powershell
    ChatUsageReport -RoomsInactiveSince 06-20-2010
```
ChatUsageReport.exe.config:

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <connectionStrings>
        <!-- The PersistentChat connection string must be defined in this file. -->
        <add name="PersistentChat" connectionString="Data Source=contoso.com\RTC;Initial Catalog=mgc;Integrated Security=SSPI"/>
      </connectionStrings>
      <appSettings>
        <!-- The OutputFolder must be defined here or on the command line. -->
        <add key="OutputFolder" value="."/>
        <!-- The values below are the same as the application defaults. -->
        <add key="StartDate" value="01/01/0001"/>
        <add key="EndDate" value="12/31/9999"/>
        <add key="TopActiveUsers" value="10"/>
        <add key="TopActiveRooms" value="10"/>
        <add key="LeastActiveRooms" value="10"/>
        <add key="RoomsInactiveSince" value="01/01/0001"/>
      </appSettings>
    </configuration></configuration>
```
</div>

</div>

<div>

## <a name="scheduleadsyncforprincipal"></a>счедулеадсинкфорпринЦипал

<div>

## <a name="description"></a>Описание

СчедулеадсинкфорпринЦипал — это скрипт Microsoft SQL Server 2012, который необходимо запускать непосредственно из SQL Server Management Studio при подключении к базе данных сохраняемого чата. Этот сценарий позволяет принудительно применять сохраняемый чат для синхронизации записей пользователя с ними из доменных служб Active Directory, а не ждать запланированного времени синхронизации.

</div>

<div>

## <a name="requirements"></a>Требования

Учетная запись пользователя, с помощью которой запускается сценарий, должна иметь доступ владельца к внутренней базе данных сохраняемого чата.

</div>

<div>

## <a name="usage"></a>Применение

Ниже приведено содержимое скрипта по умолчанию.

```Powershell
    /*
    This script will schedule a principal for a forced AD synchronization cycle
    
    If you're using Sql Server Management Studio, pressing Ctrl+Shift+M will 
    allow you to specify values for the template parameter.
    */
    
        insert into
          tblPrincipalMeta
          (
           prinID
          ,prinAffiliationsDirty
          ,prinAttributesDirty
          ,prinDeleted
          )
          select
            prinID
           ,1
           ,1
           ,0
          from
            tblPrincipal
          where
            prinID not in (select prinID from tblPrincipalMeta) and
            prinID = <PrinID,int,0>
     
        update
          tblPrincipalMeta
        set
          prinAffiliationsDirty = 1
         ,prinAttributesDirty = 1
         ,tryCount = 0
         ,nextTry = null
        where
         prinID = <PrinID,int,0>
```

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

