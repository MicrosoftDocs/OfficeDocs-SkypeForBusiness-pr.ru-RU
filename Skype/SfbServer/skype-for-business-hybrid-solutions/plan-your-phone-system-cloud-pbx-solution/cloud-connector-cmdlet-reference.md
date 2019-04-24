---
title: Справочник по командлетам Cloud Connector
ms.reviewer: ''
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
ms.openlocfilehash: aa8b8ebe4ffd7d1cb2c405eae5fe6604c5f4c378
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234263"
---
# <a name="cloud-connector-cmdlet-reference"></a>Cloud Connector cmdlet reference
 
В следующей таблице перечисляются командлеты Skype для бизнеса Cloud Connector Edition с кратким описанием их функций, а также приводятся ссылки на дополнительные сведения.
  
> [!NOTE]
> Необходимо выполнить все командлеты на главном компьютере облачных соединителя и необходимо запустить сеанс PowerShell от имени администратора. 
  
|**Имя командлета**|**Описание**|
|:-----|:-----|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <br/> Версия 1.4.2 и более поздние версии  <br/> |Выполняет резервное копирование службы центра сертификации в файл и сохраняет его в папку ЦС в общем каталоге сайта.      <br/> |
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |Создает файл базового виртуального жесткого диска (VHDX) на основе предоставленного клиентом ISO-файла с образом Windows Server 2012 R2. VHDX-файл используется в процессе развертывания Cloud Connector.   <br/> |
|[Enter-CcUpdate](enter-ccupdate.md) <br/> |Подготавливает соединителя облачных хост-сервера для процесса обновления, поместив его в режиме обслуживания. Устройства «опустошены»; то есть все существующие звонки по выполнению, но новые звонки, отклоняются.  <br/> |
|[Exit-CcUpdate](exit-ccupdate.md) <br/> |Выход из обновление режим обслуживания на сервере размещения соединителя облака.  <br/> |
|[Export-CcConfiguration](export-ccconfiguration.md) <br/> |  Экспортирует конфигурацию Skype для бизнеса Cloud Connector Edition в локальный файл на сервере узла Skype для бизнеса Cloud Connector Edition. <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |Экспортирует соединителя облачных пример файла конфигурации (ini-) каталог appliance устройства соединителя облака. Вы можете изменить и переименовать этот файл, чтобы использовать его в своем развертывании.  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> Версия 1.4.2 и более поздние версии   <br/> |Экспортирует сертификат корневого центра сертификации локального файла на сервере размещения соединителя облака.  <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |Получает рабочий каталог на сервере размещения соединителя облака. В этом каталоге хранятся все файлы развертывания.  <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |Отображает текущий каталог котором хранятся журналы для соединителя облачных устройства.  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> Версия 2.1 и более поздних версий  <br/> |Предоставляет диагностические сведения для соединителя облачных устройства.  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |Возвращает учетные данные текущего развертывания облака соединителя.  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |Возвращает путь к файлу внешний сертификат для развертывания облака соединителя. Этот сертификат подготавливается пользователем.  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |Показывает текущий каталог, в котором хранятся файлы конфигурации уровня узла. Папка содержит базовый установочные файлы VHD и облачных соединителя. Эта папка должна быть общей с другими приложениями, соединитель облака сайта.  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |Отображает текущий каталог котором хранятся журналы уровня сайта для соединителя облака.  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> Версия 2.0 и более поздние версии  <br/> |Возвращает версию в экземпляр Cloud Connector. Использовать командлет Get-CCVersion можно только на хост-компьютере Cloud Connector.  <br/> |
|[Import-CcConfiguration](import-ccconfiguration.md) <br/> Версия 2.0 и более поздние версии  <br/> |Импортирует Скайп для конфигурации соединителя Cloud Business Edition из локального файла для соединителя облачных хост-сервера.  <br/> |
|[Install-CcAppliance](install-ccappliance.md) <br/> |Устанавливает appliance соединителя облака — включая AD, центрального хранилища управления, сервер-посредник и пограничного сервера виртуальных машин — на хост-сервера.  <br/> |
|[Publish-CcAppliance](publish-ccappliance.md) <br/> | Получает сведения о высокой доступности из конфигурации сети клиента и публикуется в облаке соединителя устройство на хост-сервера. <br/> |
|[Register-CcAppliance](register-ccappliance.md) <br/> | Регистрирует сведения об устройстве на сайте ТСОП в конфигурации интерактивного клиента. Устройства должны быть зарегистрированы перед его можно развернуть и управляемых службой управления облачных соединителя. <br/> |
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> Версия 1.4.2 и более поздние версии  <br/> |Удаляет файл резервной копии службы центра сертификации "\<SiteRootDirectory\>\CA\SfB системы CCE Root.p12» в папке ЦС совместный доступ в каталоге сайтов для облачных соединителя.  <br/> |
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> Версия 1.4.2 и более поздние версии  <br/> |Удаляет прежние версии сертификатов сервера центрального хранилища управления, сервера-посредника и пограничного сервера после выполнения командлетов Renew-CcCACertificate или Renew CcServerCertificate.  <br/> |
|[Renew-CcCACertificate](renew-cccacertificate.md) <br/> Только для версии 1.4.2  <br/> |Переустанавливает сервер Active Directory службы центра сертификации для создания нового сертификата корневого центра сертификации.  <br/> |
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <br/> Только для версии 1.4.2  <br/> |Продлевает сертификаты для Cloud Connector, срок действия которых подходит к концу или уже истек.  <br/> |
|[Reset-CcCACertificate](reset-cccacertificate.md) <br/> Версия 1.4.2 и более поздние версии  <br/> |Сбрасывает серверы центра сертификации для установки нового сертификата центра сертификации.  <br/> |
|[Restore-CcCredentials](restore-cccredentials.md) <br/> Версия 2.1 и более поздних версий  <br/> |Очищает учетные данные, необходимо повторно ввести все учетные данные, используемые для текущего развертывания облака соединителя.  <br/> |
|[Search-CcLog](search-cclog.md) <br/> |Поиск входящих и исходящих вызовов входит в каталог журнала appliance облачных соединителя  <br/> |
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |Задает рабочий каталог для соединителя облачных хост-сервера. В этом каталоге хранятся все файлы развертывания.  <br/> |
|[Set-CcCredential](set-cccredential.md) <br/> |Задает учетные данные текущего развертывания облака соединителя.  <br/> |
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |Задает путь к сертификату для сервера-посредника или пограничного сервера.  <br/> |
|[Set-CcSiteDirectory](set-ccsitedirectory.md) <br/> |Определяет каталог, в котором будут храниться файлы конфигурации уровня сайта для соединителя облачных. В папке будут находиться файлы конфигурации базового виртуального жесткого диска и Cloud Connector.  <br/> |
|[Start-CcDownload](start-ccdownload.md) <br/> |Загружаемые файлы для соединителя облачных бит и msi-файл синхронно.  <br/> |
|[Start-CcLogging](start-cclogging.md) <br/> |Создает журнала входящих и исходящих вызовов для соединителя облачных устройства.  <br/> |
|[Stop-CcLogging](stop-cclogging.md) <br/> |Останавливает Создание входящего и исходящего вызова журнала для соединителя облачных устройства.  <br/> |
|[Switch-CcVersion](switch-ccversion.md) <br/> |Отключает работающее устройство и выполняет переключение на только что развернутое или резервное устройство.   <br/> |
|[Uninstall-CcAppliance](uninstall-ccappliance.md) <br/> |Удаляет выполняемого appliance облачных соединителя с хост-сервера.  <br/> |
|[Unregister-CcAppliance](unregister-ccappliance.md) <br/> |Отменяет регистрацию текущего appliance облачных соединителя с сайта ТСОП в конфигурации интерактивного клиента.  <br/> |
|[Update-CcCACertificate](update-cccacertificate.md) <br/> Версия 2.0 и более поздние версии  <br/> |Переустанавливает сервер Active Directory службы центра сертификации для создания нового сертификата корневого центра сертификации.  <br/> |
|[Update-CcServerCertificate](update-ccservercertificate.md) <br/> Версия 2.0 и более поздние версии  <br/> |Продлевает сертификаты для Cloud Connector, срок действия которых подходит к концу или уже истек.  <br/> |
   

