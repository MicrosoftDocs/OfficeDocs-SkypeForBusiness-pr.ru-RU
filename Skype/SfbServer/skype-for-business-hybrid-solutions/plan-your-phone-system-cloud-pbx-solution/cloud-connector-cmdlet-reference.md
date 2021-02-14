---
title: Справочник по командлетам Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 072b4bdc-0f1e-4fce-a41e-5c60d24556d5
description: В следующей таблице перечислены cmdlets Skype для бизнеса Cloud Connector Edition с кратким описанием и ссылками на дополнительные сведения.
ms.openlocfilehash: 8d33cd8c493c3acc165661e5af80625e773e2d0d
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359055"
---
# <a name="cloud-connector-cmdlet-reference"></a>Справочник по командлетам Cloud Connector
 
> [!Important]
> Выпуск Cloud Connector Edition завершится 31 июля 2021 г. вместе со Skype для бизнеса Online. После обновления вашей организации до Teams узнайте, как подключить свою локальной телефонной сети к Teams с помощью [прямой маршрутизации.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

В следующей таблице перечислены cmdlets Skype для бизнеса Cloud Connector Edition с кратким описанием и ссылками на дополнительные сведения.
  
> [!NOTE]
> Необходимо выполнить все cmdlets на хост-компьютере Cloud Connector, а сеанс PowerShell необходимо запустить от администратора. 
  
|**Имя командлета**|**Описание**|
|:-----|:-----|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <br/> Версия 1.4.2 и более поздние  <br/> |Архивация службы центра сертификации в файл и сохранение его в папке ЦС в каталоге для совместной работы сайта.     <br/> |
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |Создает файл базового виртуального жесткого диска (VHDX) с помощью предоставленного клиентом ISO-файла Windows Server 2012 R2. VHDX-файл будет использоваться во время развертыванияCloud Connector.  <br/> |
|[Enter-CcUpdate](enter-ccupdate.md) <br/> |Подготавливает сервер хоста Cloud Connector к процессу обновления, переведя его в режим обслуживания. Устройство "разрядилось"; то есть все существующие вызовы будут завершены, но новые вызовы будут отклонены.  <br/> |
|[Exit-CcUpdate](exit-ccupdate.md) <br/> |Выходит из режима обслуживания обновлений на сервере хост-сервера Cloud Connector.  <br/> |
|[Export-CcConfiguration](export-ccconfiguration.md) <br/> | Экспортирует конфигурацию Skype для бизнеса Cloud Connector Edition в локальный файл на сервере хост-сервера Skype для бизнеса Cloud Connector Edition. <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |Экспортирует пример файла конфигурации Cloud Connector (INI) в каталог устройства устройства Cloud Connector. Вы можете изменить и переименовать файл для развертывания.  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> Версия 1.4.2 и более поздние  <br/> |Экспортирует сертификат корневого ЦС в локальный файл на сервере хост-сервера Cloud Connector.  <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |Извлекает рабочий каталог на сервере хост-сервера Cloud Connector. Все файлы развертывания хранятся в этом каталоге.  <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |Показывает текущий каталог, в котором хранятся журналы для устройства Cloud Connector.  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> Версия 2.1 и более поздние  <br/> |Предоставляет диагностические сведения для устройства Cloud Connector.  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |Возвращает учетные данные текущего развертывания Cloud Connector.  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |Возвращает путь к файлу внешнего сертификата для развертывания Cloud Connector. Пользователь подготавливает этот сертификат.  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |Показывает текущий каталог, в котором хранятся файлы конфигурации уровня сайта. Папка содержит файлы установки базового VHD и Cloud Connector. Эта папка должна совместно работать со всеми другими устройствами сайта Cloud Connector.  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |Показывает текущий каталог, в котором хранятся журналы уровня сайта для Cloud Connector.  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> Версия 2.0 и более поздние  <br/> |Возвращает версию экземпляра Cloud Connector. Get-CCVersion можно использовать только на хост-компьютере Cloud Connector.  <br/> |
|[Import-CcConfiguration](import-ccconfiguration.md) <br/> Версия 2.0 и более поздние  <br/> |Импортирует конфигурацию Skype для бизнеса Cloud Connector Edition из локального файла на сервер хост-сервера Cloud Connector.  <br/> |
|[Install-CcAppliance](install-ccappliance.md) <br/> |Устанавливает устройство Cloud Connector, включая виртуальные машины AD, центрального банка управления, сервера-посредника и сервера-посредника, на сервере хост-сервера.  <br/> |
|[Publish-CcAppliance](publish-ccappliance.md) <br/> | Получает сведения о высокой доступности из конфигурации интерактивного клиента и публикует их на устройстве Cloud Connector на сервере хост-сервера. <br/> |
|[Register-CcAppliance](register-ccappliance.md) <br/> | Регистрирует сведения об устройстве на сайте STN в конфигурации интерактивного клиента. Прежде чем развертывать устройство и управлять им с помощью службы управления Cloud Connector, необходимо зарегистрировать его. <br/> |
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> Версия 1.4.2 и более поздние  <br/> |Удаляет файл резервной копии службы центра сертификации \<SiteRootDirectory\> \CA\SfB CCE Root.p12" в папке ЦС в каталоге share сайта для Cloud Connector.  <br/> |
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> Версия 1.4.2 и более поздние  <br/> |Удаляет устаревшие сертификаты сервера в центральном хранилище управления, сервере-посреднике и на сервере-посреднике после выполнения Renew-CcCACertificate или обновления CcServerCertificate.  <br/> |
|[Renew-CcCACertificate](renew-cccacertificate.md) <br/> Только версия 1.4.2  <br/> |Переустановит сервер AD Службы сертификации для создания нового сертификата корневого ЦС.  <br/> |
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <br/> Только версия 1.4.2  <br/> |Обновляет сертификаты для Cloud Connector, когда они истекают или уже истекают.  <br/> |
|[Reset-CcCACertificate](reset-cccacertificate.md) <br/> Версия 1.4.2 и более поздние  <br/> |Сбрасывает серверы сертификации для установки нового сертификата.  <br/> |
|[Restore-CcCredentials](restore-cccredentials.md) <br/> Версия 2.1 и более поздние  <br/> |Очистка учетных данных и запрос на повторное ввод всех учетных данных, используемых для текущего развертывания Cloud Connector.  <br/> |
|[Search-CcLog](search-cclog.md) <br/> |Поиск журналов входящих и исходяющих вызовов в каталоге журнала устройств Cloud Connector  <br/> |
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |Задает рабочий каталог на сервере хост-сервера Cloud Connector. Все файлы развертывания хранятся в этом каталоге.  <br/> |
|[Set-CcCredential](set-cccredential.md) <br/> |Задает учетные данные текущего развертывания Cloud Connector.  <br/> |
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |Указывает путь, в котором хранится сертификат для сервера-посредника или сервера-посредника.  <br/> |
|[Set-CcSiteDirectory](set-ccsitedirectory.md) <br/> |Задает каталог, в котором будут храниться файлы конфигурации уровня сайта для Cloud Connector. Папка будет содержать файлы конфигурации базового VHD и Cloud Connector.  <br/> |
|[Start-CcDownload](start-ccdownload.md) <br/> |Синхронно скачивает биты Cloud Connector и MSI-файл.  <br/> |
|[Start-CcLogging](start-cclogging.md) <br/> |Создает журнал входящих и исходяющих вызовов для устройства Cloud Connector.  <br/> |
|[Stop-CcLogging](stop-cclogging.md) <br/> |Прекращает создание журнала входящих и исходяющих вызовов для устройства Cloud Connector.  <br/> |
|[Switch-CcVersion](switch-ccversion.md) <br/> |Отключает запущенные устройства и переключается на только что развернутые или резервные устройства.  <br/> |
|[Uninstall-CcAppliance](uninstall-ccappliance.md) <br/> |При этом запущенное устройство Cloud Connector будет выгрузлено с хост-сервера.  <br/> |
|[Unregister-CcAppliance](unregister-ccappliance.md) <br/> |Unregisters the current Cloud Connector appliance from a PSTN site in the online tenant configuration.  <br/> |
|[Update-CcCACertificate](update-cccacertificate.md) <br/> Версия 2.0 и более поздние  <br/> |Переустановит сервер AD Службы сертификации для создания нового сертификата корневого ЦС.  <br/> |
|[Update-CcServerCertificate](update-ccservercertificate.md) <br/> Версия 2.0 и более поздние  <br/> |Обновляет сертификаты для Cloud Connector, когда они истекают или уже истекают.  <br/> |
   

