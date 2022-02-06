---
title: Развертывание SQL для высокой доступности back End Server в Skype для бизнеса Server 2015 г.
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
description: 'Для развертывания зеркального SQL серверы должны запускать минимум SQL Server R2 2008. Эта версия должна работать на всех участвующих серверах: первичном, зеркальном и свидетельном. Подробные сведения см. в материале Накопительный пакет обновления 9 для SQL Server 2008 Пакет обновления 1 .'
---

# <a name="deploy-sql-mirroring-for-back-end-server-high-availability-in-skype-for-business-server-2015"></a>Развертывание SQL зеркального зеркала для высокой доступности back End Server в Skype для бизнеса сервере 2015 г.


Для развертывания зеркального SQL серверы должны запускать минимум SQL Server R2 2008. Эта версия должна работать на всех участвующих серверах: первичном, зеркальном и свидетельном. Подробные сведения см. в [материале Накопительный пакет обновления 9 для SQL Server 2008 Пакет обновления 1](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921).

В целом, для настройки зеркального отображения SQL между двумя внутренними серверами с ресурсом-свидетелем требуется следующее:

- Версия сервера основного сервера должна SQL Server зеркальное SQL.

- На основном ресурсе, зеркальном ресурсе и ресурсе-свидетеле (если развертывается) должна быть установлена одна и та же версия SQL Server.

- На основном и зеркальном ресурсах должен быть установлен один и тот же выпуск SQL Server. На ресурсе-свидетеле может быть установлен другой выпуск.

Для SQL с точки зрения того, SQL версии поддерживаются для роли свидетеля, см. в статью [Database Mirroring Witness](/sql/database-engine/database-mirroring/database-mirroring-witness).

Вы используете Topology Builder для развертывания SQL зеркального зеркального использования. Вы выбираете параметр в Topology Builder для зеркального выбора баз данных, а при публикации топологии Topology Builder настраивает зеркальное отражение (включая настройку свидетеля, если хотите). Обратите внимание, что настройка или удаление свидетеля выполняется одновременно с настройкой или удалением зеркала. Отдельной команды для развертывания или удаления только свидетеля не существует.

Для настройки зеркального отображения серверов сначала нужно правильно настроить разрешения базы данных SQL. Подробные сведения см. [в журнале Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)](/sql/database-engine/database-mirroring/set-up-login-accounts-database-mirroring-always-on-availability).

При SQL зеркальном окне режим восстановления базы данных всегда заданная для **Full**, что означает, что необходимо регулярно отслеживать размер журнала транзакций и регулярно восстанавливать журналы транзакций, чтобы не уходить из дискового пространства на серверах back end. Частота резервного копирования журналов транзакций зависит от скорости роста журнала, которая, в свою очередь, зависит от транзакций баз данных, понесенных действиями пользователей в пуле интерфейсного интерфейса. Рекомендуется определить, сколько ожидается роста журнала транзакций для рабочей нагрузки развертывания, чтобы можно было соответствующим образом планировать. В следующих статьях приводится дополнительная информация SQL резервного копирования и управления журналами:

- [Модели восстановления баз данных](/sql/relational-databases/backup-restore/recovery-models-sql-server)

- [Обзор резервного копирования](/sql/relational-databases/backup-restore/backup-overview-sql-server)

- [Журнал резервного копирования транзакций](/sql/relational-databases/backup-restore/back-up-a-transaction-log-sql-server)

При использовании зеркального отображения SQL топологию можно настроить при создании пулов или после их создания.

> [!IMPORTANT]
> Использование topology Builder или cmdlets для SQL зеркального зеркального SQL поддерживается только в том случае, если первичные, зеркальные и свидетельские (при желании) серверы относятся к одному домену. Если необходимо настроить зеркальное отображение SQL для серверов в других доменах, см. документацию по SQL Server.

> [!IMPORTANT]
> При внесении изменений в отношения зеркального отображения серверных баз данных необходимо перезагрузить все серверы переднего плана в пуле. > для изменения зеркального зеркала (например, изменения расположения зеркала) необходимо использовать Topology Builder для выполнения этих трех действий:

1. Удаление зеркального отображения со старого сервера-зеркала.

2. Добавление зеркального отображения на новый сервер-зеркало.

3. Публикация топологии.

> [!NOTE]
> Для записи зеркальных файлов необходимо создать файл файла SQL Server и SQL агента. Если служба SQL Server работает в контексте сетевой службы, \<Domain\>\\ можно добавить к разрешениям на совместное использование<SQLSERVERNAME\> $ как основного, так и зеркального серверов SQL. $ важно определить, что это учетная запись компьютера.

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a>Настройка зеркального SQL при создании пула в Topology Builder

1. На странице **Определение хранилища SQL** щелкните **Создать** рядом с окном **Хранилище SQL**.

2. На странице **Определение нового хранилища SQL** укажите основное хранилище, выберите **Этот образец SQL связан зеркальным отображением**, укажите номер порта для зеркального отображения SQL (по умолчанию — 5022), а затем щелкните **ОК**.

3. Вернитесь на страницу **Определение хранилища SQL** и выберите **Включить зеркальное отображение хранилища SQL**.

4. На странице **Определение нового хранилища SQL** укажите хранилище SQL, которое будет использоваться в качестве зеркала. Выберите **Этот образец SQL связан зеркальным отображением**, укажите номер порта (по умолчанию — 5022), а затем щелкните **ОК**.

5. Если необходимо использовать ресурс-свидетель для этого зеркала, выполните следующие действия:

    а. Выберите **Использовать ресурс-свидетель зеркального отображения SQL для включения автоматического переключения**.

    б. На странице **Определение хранилища SQL** выберите **Использовать ресурс-свидетель зеркального отображения SQL для включения автоматического переключения** и укажите хранилище SQL для использования в качестве ресурса-свидетеля.

    в. Укажите номер порта (по умолчанию — 7022) и щелкните **ОК**.

6. После окончания определения пула переднего плана и всех других ролей в топологии используйте топологию Builder для публикации топологии. Когда топология будет опубликована, если в пуле переднего SQL центрального магазина управления включено SQL зеркальное отражение, вы увидите возможность создания баз данных SQL и зеркальных SQL хранения.

    Щелкните **Настройки** и введите путь, который необходимо использовать в качестве пути к файловому ресурсу общего доступа для резервной копии зеркального отображения.

    Щелкните **ОК**, а затем щелкните **Далее** для создания баз данных и публикации топологии. Будут развернуты ресурс-зеркало и ресурс-свидетель (если указано).

С помощью Topology Builder можно изменить свойства уже существующего пула, чтобы включить SQL зеркальное отражение.

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a>Добавление зеркального SQL к существующему пулу передней части в Topology Builder

1. В Topology Builder щелкните правой кнопкой мыши пул и нажмите **кнопку Изменить свойства**.

2. Выберите **Включить зеркальное отображение хранилища SQL**, а затем щелкните **Создать** рядом с элементом **Зеркальное отображение хранилища SQL**.

3. Укажите хранилище SQL, которое необходимо использовать в качестве зеркала.

4. Выберите **Этот образец SQL связан зеркальным отображением**, укажите номер порта зеркального отображения SQL (порт по умолчанию — 5022), а затем щелкните **ОК**.

5. Если необходимо настроить ресурс-свидетель, выберите **Использовать ресурс-свидетель зеркального отображения SQL для включения автоматического переключения** и щелкните **Создать**.

6. Укажите хранилище SQL, которое необходимо использовать в качестве свидетеля.

7. Выберите **Этот образец SQL связан зеркальным отображением**, укажите номер порта зеркального отображения SQL (порт по умолчанию — 7022), а затем щелкните **ОК**.

8. Щелкните **ОК**.

9. Опубликуйте топологию. После этого появится запрос на установку базы данных.

    В процессе публикации топологии вам будет предложено определить путь к совместной обработке файлов. Серверы SQL, которые участвуют в зеркальном зеркальном окантовыве, должны иметь доступ к этой папке для чтения и записи для того, чтобы создать зеркальное зеркало.

Затем перед переходом к следующей процедуре необходимо установить базу данных.

При настройке зеркального отображения сервера SQL Server следует иметь в виду следующее:

- Если конечная точка зеркального отображения уже существует, она будет повторно использоваться с подключением по указанным портам, а порты, определенные в топологии, будут игнорироваться.

- Любой порт, уже выделенный для других приложений на том же сервере, включая порты для других экземпляров SQL, не должен использоваться для доступных установленных экземпляров SQL. Это означает, что при наличии нескольких экземпляров SQL Server, установленных на одном и том же сервере, они не должны использовать один и тот же порт для зеркального отображения. Для получения подробной информации см. следующие статьи:

  - [Укажите сетевой адрес сервера (зеркальное отражение базы данных)](/sql/database-engine/database-mirroring/specify-a-server-network-address-database-mirroring)

  - [Конечная точка зеркального SQL Server)](/sql/database-engine/database-mirroring/the-database-mirroring-endpoint-sql-server)

## <a name="using-skype-for-business-server-2015-management-shell-cmdlets-to-set-up-sql-mirroring"></a>Использование Skype для бизнеса Server 2015 г. Для SQL зеркального SQL

Самый простой способ настроить зеркальное отражение — с помощью Topology Builder, но вы также можете сделать это с помощью cmdlets.

1. Откройте окно Skype для бизнеса Server 2015 и запустите следующий cmdlet:

   ```powershell
   Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose
   ```

    Например:

   ```powershell
   Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose
   ```

    Отобразится следующее:

   <pre>
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
   </pre>

2. Проверьте следующее:

    - Порт 5022 доступен через брандмауэр, если брандмауэр Windows включен на основном ресурсе SQL Server e04-ocs.los_a.lsipt.local\rtc.

    - Порт 5022 доступен через брандмауэр, если брандмауэр Windows включен на зеркальном ресурсе SQL Server K16-ocs.los_a.lsipt.local\rtc.

    - Порт 7022 доступен через брандмауэр, если брандмауэр Windows включен на ресурсе-свидетеле SQL Server AB14-lct.los_a.lsipt.local\rtc.

   - Учетные записи SQL серверов на всех первичных и зеркальных серверах SQL имеют разрешение на чтение и \\запись в файле E04-OCS\csdatabackup

   - Убедитесь, что поставщик инструментария управления Windows (WMI) работает на всех этих серверах. Командлет использует этого поставщика для поиска информации об учетных записях для служб SQL Server, которые выполняются на всех основных, зеркальных серверах и серверах-свидетелях.

   - Убедитесь, что учетная запись, выполняющая этот командлет, имеет право на создание папок для данных и файлов журналов для всех зеркальных серверов.

   - Обратите внимание, что учетная запись пользователя, применяемая экземпляром SQL для запуска, должна обладать разрешениями на чтение и запись для файлового ресурса. Если ресурс размещен на другом сервере, экземпляр SQL использует локальную системную учетную запись, вы должны предоставить разрешения для файлового ресурса серверу, на котором размещен экземпляр SQL.

3. Введите A и нажмите клавишу ВВОД.

    Зеркальное отображение будет настроено.

    **Install-CsMirrorDatabase** устанавливает зеркало и настраивает зеркальное отражение для всех баз данных, присутствующих в основном SQL магазине. Если вы хотите настроить зеркальное отражение только для определенных баз данных, вы можете использовать параметр -DatabaseType или настроить зеркальное отражение для всех баз данных, за исключением нескольких, вы можете использовать параметр -ExcludeDatabaseList, а также список имен баз данных, разделенных запятой, чтобы исключить их.

    Например, если вы добавили в **Install-CsMirrorDatabase** следующую функцию, будет выполнено зеркальное отображение всех баз данных, кроме rtcxds.

    `-ExcludeDatabaseList rtcab,rtcxds`

   Например, если вы добавили в **Install-CsMirrorDatabase**, следующую функцию, будет выполнено зеркальное отображение баз данных rtcab, rtcshared и rtcxds.

    `-DatabaseType User`

## <a name="removing-or-changing-sql-mirroring"></a>Удаление и изменение зеркального отображения SQL

Чтобы удалить зеркальное отображение SQL пула в построителе топологий, сначала следует использовать командлет для удаления зеркала в SQL Server. Затем вы можете использовать построитель топологий, чтобы удалить зеркало из топологии. Чтобы сделать это в SQL Server, запустите следующий командлет:

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]
```

Например, чтобы удалить зеркальное отображение и сбросить базы данных для баз данных User, введите следующую команду:

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror
```

Этот  `-DropExistingDatabasesOnMirror` параметр приводит к удалению затронутых баз данных из зеркала.

Затем чтобы удалить зеркало из топологии, выполните следующие действия:

1. В построителе топологии щелкните пул правой кнопкой мыши и щелкните **Изменить свойства**.

2. Снимите флажок **Включить зеркальное отображение хранилища SQL** и щелкните **ОК**.

3. Опубликуйте топологию.

## <a name="removing-a-mirroring-witness"></a>Удаление следящего сервера зеркального отображения

Используйте эту процедуру, если необходимо удалить свидетель из конфигурации зеркального сервера заднего конца.

1. В построителе топологии щелкните пул правой кнопкой мыши и щелкните **Изменить свойства**.

2. Снимите флажок **Использовать свидетель зеркального отображения SQL Server для автоматического перехода на другой ресурс** и нажмите **ОК**.

3. Опубликуйте топологию.

    После публикации топологии Topology Builder вы увидите сообщение, которое включает в себя следующие

   ```console
   Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
   ```

    Однако не следуйте этому шагу и  `Uninstall-CsMirrorDatabase` не введите, так как это позволит удалить всю конфигурацию зеркального зеркала.

4. Чтобы удалить только свидетеля из конфигурации SQL Server, следуйте инструкциям в [Remove the Witness from a Database Mirroring Session (SQL Server)](/sql/database-engine/database-mirroring/remove-the-witness-from-a-database-mirroring-session-sql-server).