---
title: Справочник по командлетам Cloud Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 072b4bdc-0f1e-4fce-a41e-5c60d24556d5
description: В следующей таблице перечисляются командлеты Skype для бизнеса Cloud Connector Edition с кратким описанием их функций, а также приводятся ссылки на дополнительные сведения.
ms.openlocfilehash: 5528b7ef5d2fe0ccfab680f2300b444f0532a059
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="cloud-connector-cmdlet-reference"></a>Справочник по командлетам Cloud Connector
 
В следующей таблице перечисляются командлеты Skype для бизнеса Cloud Connector Edition с кратким описанием их функций, а также приводятся ссылки на дополнительные сведения.
  
> [!NOTE]
> Все командлеты необходимо выполнять на главном компьютере. Сеанс PowerShell должен быть открыт с использованием прав администратора. 
  
|**Имя командлета**|**Описание**|
|:-----|:-----|
|[Резервное копирование CcCertificationAuthority](backup-cccertificationauthority.md) <br/> Версия 1.4.2 и более поздние версии  <br/> |Выполняет резервное копирование службы центра сертификации в файл и сохраняет его в папку ЦС в общем каталоге сайта.      <br/> |
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |Создает файл базового виртуального жесткого диска (VHDX) на основе предоставленного клиентом ISO-файла с образом Windows Server 2012 R2. VHDX-файл используется в процессе развертывания Cloud Connector.   <br/> |
|[Введите CcUpdate](enter-ccupdate.md) <br/> |Подготавливает сервер узла Cloud Connector к процессу обновления, переводя его в режим обслуживания. Устройства «опустошены»; то есть все существующие звонки по выполнению, но новые звонки, отклоняются.  <br/> |
|[Выход CcUpdate](exit-ccupdate.md) <br/> |Выполняет выход из режима обслуживания обновления на сервере узла Cloud Connector.    <br/> |
|[Export-CcConfiguration](export-ccconfiguration.md) <br/> |  Экспортирует конфигурацию Skype для бизнеса Cloud Connector Edition в локальный файл на сервере узла Skype для бизнеса Cloud Connector Edition. <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |Экспортирует соединителя облачных пример файла конфигурации (ini-) каталог appliance устройства соединителя облака. Вы можете изменить и переименовать этот файл, чтобы использовать его в своем развертывании.  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> Версия 1.4.2 и более поздние версии  <br/> |Экспортирует корневой сертификат ЦС на локальный файл на сервере узла Cloud Connector.   <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |Извлекает рабочий каталог на сервере узла Cloud Connector. В этом каталоге хранятся все файлы развертывания.    <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |Отображает текущий каталог котором хранятся журналы для соединителя облачных устройства.  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> Версия 2.1 и более поздних версий  <br/> |Предоставляет диагностические сведения для соединителя облачных устройства.  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |Возвращает учетные данные текущего развертывания Cloud Connector.  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |Возвращает путь к файлу внешнего сертификата для развертывания Cloud Connector. Этот сертификат подготавливается пользователем.  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |Показывает текущий каталог, в котором хранятся файлы конфигурации уровня сайта. Папка содержит базовый установочные файлы VHD и облачных соединителя. Эта папка должна быть общей с другими приложениями, соединитель облака сайта.  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |Отображает текущий каталог котором хранятся журналы уровня сайта для соединителя облака.  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> Версия 2.0 и более поздние версии  <br/> |Возвращает версию в экземпляр Cloud Connector. Использовать командлет Get-CCVersion можно только на хост-компьютере Cloud Connector.  <br/> |
|[Импорт CcConfiguration](import-ccconfiguration.md) <br/> Версия 2.0 и более поздние версии  <br/> |Импортирует Скайп для конфигурации соединителя Cloud Business Edition из локального файла для соединителя облачных хост-сервера.  <br/> |
|[Install-CcAppliance](install-ccappliance.md) <br/> |Устанавливает appliance соединителя облака — включая AD, центрального хранилища управления, сервер-посредник и пограничного сервера виртуальных машин — на хост-сервера.  <br/> |
|[Публикация CcAppliance](publish-ccappliance.md) <br/> | Получает сведения о высокой доступности из конфигурации сети клиента и публикуется в облаке соединителя устройство на хост-сервера. <br/> |
|[Register-CcAppliance](register-ccappliance.md) <br/> | Регистрирует сведения об устройстве на сайте ТСОП в конфигурации интерактивного клиента. Устройства должны быть зарегистрированы перед его можно развернуть и управляемых службой управления облачных соединителя. <br/> |
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> Версия 1.4.2 и более поздние версии  <br/> |Удаляет файл резервной копии службы центра сертификации "\<SiteRootDirectory\>\CA\SfB системы CCE Root.p12» в папке ЦС совместный доступ в каталоге сайтов для облачных соединителя.  <br/> |
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> Версия 1.4.2 и более поздние версии  <br/> |Удаляет прежние версии сертификатов сервера центрального хранилища управления, сервера-посредника и пограничного сервера после выполнения командлетов Renew-CcCACertificate или Renew CcServerCertificate.  <br/> |
|[Обновить CcCACertificate](renew-cccacertificate.md) <br/> Только для версии 1.4.2  <br/> |Переустанавливает сервер Active Directory службы центра сертификации для создания нового сертификата корневого центра сертификации.  <br/> |
|[Обновить CcServerCertificate](renew-ccservercertificate.md) <br/> Только для версии 1.4.2  <br/> |Продлевает сертификаты для Cloud Connector, срок действия которых подходит к концу или уже истек.  <br/> |
|[Сброс CcCACertificate](reset-cccacertificate.md) <br/> Версия 1.4.2 и более поздние версии  <br/> |Сбрасывает серверы центра сертификации для установки нового сертификата центра сертификации.  <br/> |
|[Восстановление CcCredentials](restore-cccredentials.md) <br/> Версия 2.1 и более поздних версий  <br/> |Очищает учетные данные, необходимо повторно ввести все учетные данные, используемые для текущего развертывания облака соединителя.  <br/> |
|[CcLog поиска](search-cclog.md) <br/> |Выполняет поиск в журналах входящих и исходящих вызовов в каталоге журнала устройства Cloud Connector.  <br/> |
|[SET-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |Задает рабочий каталог для соединителя облачных хост-сервера. В этом каталоге хранятся все файлы развертывания.  <br/> |
|[SET-CcCredential](set-cccredential.md) <br/> |Задает учетные данные текущего развертывания Cloud Connector.  <br/> |
|[SET-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |Задает путь к сертификату для сервера-посредника или пограничного сервера.  <br/> |
|[SET-CcSiteDirectory](set-ccsitedirectory.md) <br/> |Задает каталог, в котором будут храниться файлы конфигурации уровня сайта для Cloud Connector. В папке будут находиться файлы конфигурации базового виртуального жесткого диска и Cloud Connector.  <br/> |
|[Start-CcDownload](start-ccdownload.md) <br/> |Загружаемые файлы для соединителя облачных бит и msi-файл синхронно.  <br/> |
|[Start-CcLogging](start-cclogging.md) <br/> |Создает журнала входящих и исходящих вызовов для соединителя облачных устройства.  <br/> |
|[STOP-CcLogging](stop-cclogging.md) <br/> |Останавливает Создание входящего и исходящего вызова журнала для соединителя облачных устройства.  <br/> |
|[Переключатель CcVersion](switch-ccversion.md) <br/> |Отключает работающее устройство и выполняет переключение на только что развернутое или резервное устройство.   <br/> |
|[Удаление CcAppliance](uninstall-ccappliance.md) <br/> |Удаляет выполняемого appliance облачных соединителя с хост-сервера.  <br/> |
|[Отмена регистрации CcAppliance](unregister-ccappliance.md) <br/> |Отменяет регистрацию текущего appliance облачных соединителя с сайта ТСОП в конфигурации интерактивного клиента.  <br/> |
|[Обновление CcCACertificate](update-cccacertificate.md) <br/> Версия 2.0 и более поздние версии  <br/> |Переустанавливает сервер Active Directory службы центра сертификации для создания нового сертификата корневого центра сертификации.  <br/> |
|[Обновление CcServerCertificate](update-ccservercertificate.md) <br/> Версия 2.0 и более поздние версии  <br/> |Продлевает сертификаты для Cloud Connector, срок действия которых подходит к концу или уже истек.  <br/> |
   

