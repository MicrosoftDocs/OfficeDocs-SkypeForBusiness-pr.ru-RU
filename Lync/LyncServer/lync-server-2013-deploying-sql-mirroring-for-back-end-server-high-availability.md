---
title: Развертывание зеркального отображения SQL для обеспечения высокой доступности внутреннего сервера
description: Развертывание зеркального отображения SQL для обеспечения высокой доступности внутреннего сервера.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying SQL mirroring for Back End Server high availability
ms:assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204992(v=OCS.15)
ms:contentKeyID: 48184451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a2ab2d598249c12231668a888b442f830c5d65f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566005"
---
# <a name="deploying-sql-mirroring-for-back-end-server-high-availability-in-lync-server-2013"></a>Развертывание зеркального отображения SQL для обеспечения высокой доступности внутреннего сервера в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-01-08_

Чтобы можно было развернуть зеркальное отображение SQL, на серверах должен быть установлен минимум SQL Server 2008 R2. Эта версия должна выполняться на всех связанных серверах: основной, зеркальный и следящий. Дополнительные сведения см [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921) .

В целом, для настройки зеркального отображения SQL между двумя внутренними серверами с ресурсом-свидетелем требуется следующее:

  - Версия SQL Server основного сервера должна поддерживать зеркальное отображение SQL.

  - На основном ресурсе, зеркальном ресурсе и ресурсе-свидетеле (если развертывается) должна быть установлена одна и та же версия SQL Server.

  - На основном и зеркальном ресурсах должен быть установлен один и тот же выпуск SQL Server. На ресурсе-свидетеле может быть установлен другой выпуск.

Рекомендации по SQL в терминах того, какие версии SQL поддерживаются для роли следящего сервера, можно найти в разделе "следящий сервер зеркального отображения баз данных" в библиотеке MSDN по адресу [https://go.microsoft.com/fwlink/p/?LinkId=247345](https://go.microsoft.com/fwlink/p/?linkid=247345) .

Для развертывания зеркального отображения SQL используется построитель топологий. Выберите параметр в построителе топологий, чтобы зеркально отобразить базы данных, а в построителе топологий настраивается зеркальное отображение (в том числе Настройка следящего сервера при необходимости) при публикации топологии. Обратите внимание, что настройка или удаление свидетеля выполняется одновременно с настройкой или удалением зеркала. Отдельной команды для развертывания или удаления только свидетеля не существует.

Для настройки зеркального отображения серверов сначала нужно правильно настроить разрешения базы данных SQL. Подробнее: "Настройка учетных записей входа для зеркального отображения баз данных или групп доступности AlwaysOn (SQL Server)" по адресу [https://go.microsoft.com/fwlink/p/?LinkId=268454](https://go.microsoft.com/fwlink/p/?linkid=268454) .

При использовании зеркального отображения SQL режим восстановления базы данных всегда задан как **Полный**, т. е. вы должны регулярно внимательно следить за размером журнала транзакций и журналов транзакций резервного копирования, чтобы предотвратить нехватку места на диске на фоновых серверах. Частота резервного копирования журналов транзакций зависит от скорости роста журналов, которая в свою очередь зависит от транзакций баз данных в результате действий пользователей в пуле переднего плана. Рекомендуется определить ожидаемую скорость роста журналов для полезной нагрузки развертывания Lync, чтобы вы могли правильно провести планирование. В следующих статьях представлены дополнительные сведения об управлении резервным копированием и журналами SQL:

  - Модели восстановления баз данных: "модели восстановления (SQL Server)" по адресу [https://go.microsoft.com/fwlink/p/?LinkId=268446](https://go.microsoft.com/fwlink/p/?linkid=268446)

  - Общие сведения о резервном копировании: "Обзор резервного копирования (SQL Server)" в [https://go.microsoft.com/fwlink/p/?LinkId=268449](https://go.microsoft.com/fwlink/p/?linkid=268449)

  - Резервное копирование журнала транзакций: "Создание резервной копии журнала транзакций (SQL Server)" по адресу [https://go.microsoft.com/fwlink/p/?LinkId=268452](https://go.microsoft.com/fwlink/p/?linkid=268452)

При использовании зеркального отображения SQL топологию можно настроить при создании пулов или после их создания.



> [!IMPORTANT]
> Использование построителя топологий или командлетов для настройки и удаления зеркального отображения SQL поддерживается только в том случае, если основной, зеркальный и следящий серверы принадлежат к одному и тому же домену. Если необходимо настроить зеркальное отображение SQL для серверов в других доменах, см. документацию по SQL Server.





> [!IMPORTANT]
> При внесении изменений в отношения зеркального отображения серверных баз данных необходимо перезагрузить все серверы переднего плана в пуле.<BR>Чтобы изменить зеркальное отображение (например, изменить расположение зеркала), необходимо использовать построитель топологий для выполнения этих трех действий: 
> <OL>
> <LI>
> <P>Удаление зеркального отображения со старого сервера-зеркала.</P>
> <LI>
> <P>Добавление зеркального отображения на новый сервер-зеркало.</P>
> <LI>
> <P>Публикация топологии.</P></LI></OL>




> [!NOTE]
> Необходимо создать общий файловый ресурс для записи в нее зеркальных файлов, а служба, в которой выполняются SQL Server и агент SQL, должна иметь доступ для чтения и записи. Если служба SQL Server выполняется в контексте сетевой службы, вы можете добавить &lt; домен &gt;&#92;&lt; SQLSERVERNAME &gt; $ как для основного, так и для зеркального серверов SQL в разрешения общего доступа. $ Важно определить, что это учетная запись компьютера.


<div>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a>Настройка зеркального отображения SQL при создании пула в построителе топологий

1.  На странице **Определение хранилища SQL** щелкните **Создать** рядом с окном **Хранилище SQL**.

2.  На странице **Определение нового хранилища SQL** укажите основное хранилище, выберите **Этот образец SQL связан зеркальным отображением**, укажите номер порта для зеркального отображения SQL (по умолчанию — 5022), а затем щелкните **ОК**.

3.  Вернитесь на страницу **Определение хранилища SQL** и выберите **Включить зеркальное отображение хранилища SQL**.

4.  На странице **Определение нового хранилища SQL** укажите хранилище SQL, которое будет использоваться в качестве зеркала. Выберите **Этот образец SQL связан зеркальным отображением**, укажите номер порта (по умолчанию — 5022), а затем щелкните **ОК**.

5.  Если необходимо использовать ресурс-свидетель для этого зеркала, выполните следующие действия:
    
    1.  Выберите **Использовать ресурс-свидетель зеркального отображения SQL для включения автоматического переключения**.
    
    2.  На странице **Определение хранилища SQL** выберите **Использовать ресурс-свидетель зеркального отображения SQL для включения автоматического переключения** и укажите хранилище SQL для использования в качестве ресурса-свидетеля.
    
    3.  Укажите номер порта (по умолчанию — 7022) и щелкните **ОК**.

6.  После определения пула переднего плана и всех остальных ролей в топологии используйте построитель топологий для публикации топологии. Когда топология публикуется, если для пула переднего плана, на котором размещается центральное хранилище управления, включено зеркальное отображение SQL, вы увидите вариант, позволяющий создать как основные, так и зеркальные базы данных хранилища SQL.
    
    Щелкните **Настройки** и введите путь, который необходимо использовать в качестве пути к файловому ресурсу общего доступа для резервной копии зеркального отображения.
    
    Щелкните **ОК**, а затем щелкните **Далее** для создания баз данных и публикации топологии. Будут развернуты ресурс-зеркало и ресурс-свидетель (если указано).

Вы можете использовать построитель топологий для изменения свойств уже существующего пула, чтобы включить зеркальное отображение SQL.

</div>

<div>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a>Добавление зеркального отображения SQL в существующий интерфейсный пул в построителе топологий

1.  В построителе топологий щелкните пул правой кнопкой мыши и выберите команду **изменить свойства**.

2.  Выберите **Включить зеркальное отображение хранилища SQL**, а затем щелкните **Создать** рядом с элементом **Зеркальное отображение хранилища SQL**.

3.  Укажите хранилище SQL, которое необходимо использовать в качестве зеркала.

4.  Выберите **Этот образец SQL связан зеркальным отображением**, укажите номер порта зеркального отображения SQL (порт по умолчанию — 5022), а затем щелкните **ОК**.

5.  Если необходимо настроить ресурс-свидетель, выберите **Использовать ресурс-свидетель зеркального отображения SQL для включения автоматического переключения** и щелкните **Создать**.

6.  Укажите хранилище SQL, которое необходимо использовать в качестве свидетеля.

7.  Выберите **Этот образец SQL связан зеркальным отображением**, укажите номер порта зеркального отображения SQL (порт по умолчанию — 7022), а затем щелкните **ОК**.

8.  Щелкните **ОК**.

9.  Опубликуйте топологию. После этого появится запрос на установку базы данных.
    
    В процессе публикации топологии вам будет предложено указать путь к общему файловому ресурсу. Серверы SQL Server, которые участвуют в зеркальном отображении, должны иметь доступ на чтение и запись к этому общему файловому ресурсу для установки зеркала.

Затем перед переходом к следующей процедуре необходимо установить базу данных.

При настройке зеркального отображения сервера SQL Server следует иметь в виду следующее:

  - Если конечная точка зеркального отображения уже существует, она будет повторно использоваться с подключением по указанным портам, а порты, определенные в топологии, будут игнорироваться.

  - Любой порт, уже выделенный для других приложений на том же сервере, включая порты для других экземпляров SQL, не должен использоваться для доступных установленных экземпляров SQL. Это означает, что при наличии нескольких экземпляров SQL Server, установленных на одном и том же сервере, они не должны использовать один и тот же порт для зеркального отображения. Для получения подробной информации см. следующие статьи:
    
      - "Укажите сетевой адрес сервера (зеркальное отображение базы данных)" в библиотеке MSDN по адресу [https://go.microsoft.com/fwlink/p/?LinkId=247346](https://go.microsoft.com/fwlink/p/?linkid=247346)
    
      - "Конечная точка зеркального отображения базы данных (SQL Server)" по адресу [https://go.microsoft.com/fwlink/p/?LinkId=247347](https://go.microsoft.com/fwlink/p/?linkid=247347)

</div>

<div>

## <a name="using-lync-server-management-shell-cmdlets-to-set-up-sql-mirroring"></a>Настройка зеркального отображения SQL с помощью командлетов командной консоли Lync Server

Самый простой способ настроить зеркальное отображение с помощью построителя топологий, но вы также можете использовать командлеты.

1.  Откройте окно командной консоли Lync Server и выполните следующий командлет:
    
        Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose 
    
    Например:
    
        Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose 
    
    Отобразится следующее:
    
        Database Name:rtcxds 
                Data File:D:\CsData\BackendStore\rtc\DbPath\rtcxds.mdf 
                 Log File:D:\CsData\BackendStore\rtc\LogPath\rtcxds.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rtcshared 
                Data File:D:\CsData\BackendStore\rtc\DbPath\rtcshared.mdf 
                 Log File:D:\CsData\BackendStore\rtc\LogPath\rtcshared.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rtcab 
                Data File:D:\CsData\ABSStore\rtc\DbPath\rtcab.mdf 
                 Log File:D:\CsData\ABSStore\rtc\LogPath\rtcab.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rgsconfig 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsconfig.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsconfig.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rgsdyn 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsdyn.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsdyn.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:cpsdyn 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\cpsdyn.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\cpsdyn.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:xds 
                Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\xds.mdf 
                 Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\xds.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:lis 
                Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\lis.mdf 
                 Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\lis.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$
        [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): 

2.  Проверьте следующее:
    
      - Порт 5022 доступен через брандмауэр, если брандмауэр Windows включен на основном сервере SQL Server E04-OCS. Los \_ a. lsipt. local \\ RTC.
    
      - Порт 5022 доступен через брандмауэр, если брандмауэр Windows включен на зеркальном сервере SQL Server K16-OCS. Los \_ a. lsipt. local \\ RTC.
    
      - Порт 7022 доступен через брандмауэр, если брандмауэр Windows включен на свидетеле SQL Server AB14-lct. Los \_ a. lsipt. local \\ RTC.
    
      - Учетные записи, на которых запущены серверы SQL Server на всех основных и зеркальных серверах SQL, имеют разрешения на чтение и запись для файлового ресурса \\ \\ E04-OCS \\ ксдатабаккуп
    
      - Убедитесь, что поставщик инструментария управления Windows (WMI) работает на всех этих серверах. Командлет использует этого поставщика для поиска информации об учетных записях для служб SQL Server, которые выполняются на всех основных, зеркальных серверах и серверах-свидетелях.
    
      - Убедитесь, что учетная запись, выполняющая этот командлет, имеет право на создание папок для данных и файлов журналов для всех зеркальных серверов.
    
      - Обратите внимание, что учетная запись пользователя, применяемая экземпляром SQL для запуска, должна обладать разрешениями на чтение и запись для файлового ресурса. Если ресурс размещен на другом сервере, экземпляр SQL использует локальную системную учетную запись, вы должны предоставить разрешения для файлового ресурса серверу, на котором размещен экземпляр SQL.

3.  Введите A и нажмите клавишу ВВОД.
    
    Зеркальное отображение будет настроено.

**Install — CsMirrorDatabase** устанавливает зеркало и настраивает зеркальное отображение для всех баз данных, присутствующих в основном хранилище SQL. Если требуется настроить зеркальное отображение только для определенных баз данных, можно использовать параметр – Датабасетипе или, если необходимо настроить зеркальное отображение для всех баз данных, кроме нескольких, можно использовать параметр-Ексклудедатабаселист, а также список имен баз данных с разделителями-запятыми.

Например, если вы добавили в **Install-CsMirrorDatabase** следующую функцию, будет выполнено зеркальное отображение всех баз данных, кроме rtcxds.

`-ExcludeDatabaseList rtcab,rtcxds`

Например, если вы добавили в **Install-CsMirrorDatabase**, следующую функцию, будет выполнено зеркальное отображение баз данных rtcab, rtcshared и rtcxds.

`-DatabaseType User`

</div>

<div>

## <a name="removing-or-changing-sql-mirroring"></a>Удаление и изменение зеркального отображения SQL

Чтобы удалить зеркальное отображение SQL пула в построителе топологий, сначала следует использовать командлет для удаления зеркала в SQL Server. Затем вы можете использовать построитель топологий, чтобы удалить зеркало из топологии. Чтобы сделать это в SQL Server, запустите следующий командлет:

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

Например, чтобы удалить зеркальное отображение и сбросить базы данных для баз данных User, введите следующую команду:

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

Этот `-DropExistingDatabasesOnMirror` параметр приводит к удалению затронутых баз данных из зеркала.

Затем чтобы удалить зеркало из топологии, выполните следующие действия:

1.  В построителе топологии щелкните пул правой кнопкой мыши и щелкните **Изменить свойства**.

2.  Снимите флажок **Включить зеркальное отображение хранилища SQL** и щелкните **ОК**.

3.  Опубликуйте топологию.

</div>

<div>

## <a name="removing-a-mirroring-witness"></a>Удаление следящего сервера зеркального отображения

Используйте эту процедуру, если необходимо удалить следящий сервер из конфигурации зеркального отображения внутреннего сервера.

1.  В построителе топологии щелкните пул правой кнопкой мыши и щелкните **Изменить свойства**.

2.  Снимите флажок **Использовать свидетель зеркального отображения SQL Server для автоматического перехода на другой ресурс** и нажмите **ОК**.

3.  Опубликуйте топологию.
    
    После публикации топологии построитель топологий отобразит сообщение, содержащее следующие
    
        Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
    
    Тем не менее, не выполняйте это действие и не вводите `Uninstall-CsMirrorDatabase` так, как это приведет к удалению всей конфигурации зеркального отображения.

4.  Чтобы удалить только следящий сервер из конфигурации SQL Server, следуйте инструкциям в разделе "Удаление следящего сервера из сеанса зеркального отображения базы данных (SQL Server)" по адресу [https://go.microsoft.com/fwlink/p/?LinkId=268456](https://go.microsoft.com/fwlink/p/?linkid=268456) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

