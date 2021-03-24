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
description: В следующей таблице перечислены комлеты Skype for Business Cloud Connector Edition с кратким описанием и ссылками на дополнительные сведения.
ms.openlocfilehash: 3739518dd8ddcd17bce8108228d0d643ebaa79a4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092937"
---
# <a name="cloud-connector-cmdlet-reference"></a>Справочник по командлетам Cloud Connector
 
> [!Important]
> Cloud Connector Edition завершит карьеру 31 июля 2021 г. вместе со Skype для бизнеса Online. После обновления организации до Teams узнайте, как подключить сеть локальной телефонии к Teams с помощью прямой [маршрутизации.](/MicrosoftTeams/direct-routing-landing-page)

В следующей таблице перечислены комлеты Skype for Business Cloud Connector Edition с кратким описанием и ссылками на дополнительные сведения.
  
> [!NOTE]
> Необходимо выполнить все cmdlets на хост-машине облачного соединителя и запустить сеанс PowerShell в качестве администратора. 
  
|**Имя командлета**|**Описание**|
|:-----|:-----|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <br/> Версия 1.4.2 и более поздние версии  <br/> |Возвращает службу сертификации в файл и сохраняет его в папке ЦС в каталоге акций сайта.     <br/> |
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |Создает базовый виртуальный жесткий дисковый файл (VHDX) с помощью клиентского ИСО-файла Windows Server 2012 R2. Файл VHDX будет использоваться во время развертывания connectorCloud.  <br/> |
|[Enter-CcUpdate](enter-ccupdate.md) <br/> |Подготавливает хост-сервер облачного соединителю для процесса обновления, вводя его в режим обслуживания. Устройство "осушили"; то есть все существующие вызовы будут завершены, но новые вызовы будут отклонены.  <br/> |
|[Exit-CcUpdate](exit-ccupdate.md) <br/> |Выходы из режима обслуживания обновления на сервере хост-сервера облачного соединитела.  <br/> |
|[Export-CcConfiguration](export-ccconfiguration.md) <br/> | Экспорт конфигурации Skype для бизнеса cloud Connector Edition в локальный файл на хост-сервере Skype для бизнеса Cloud Connector Edition. <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |Экспортирует файл конфигурации образца облачного соединитела (.ini) в каталог устройств устройства устройства Cloud Connector. Вы можете изменить и переименовать файл для развертывания.  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> Версия 1.4.2 и более поздние версии  <br/> |Экспорт корневого сертификата ЦС в локальный файл на сервере хост-сервера Cloud Connector.  <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |Извлекает рабочий каталог на сервере хост-сервера Cloud Connector. Все файлы развертывания хранятся в этом каталоге.  <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |Показывает текущий каталог, в котором хранятся журналы для устройства облачного соединитела..  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> Версия 2.1 и более поздние версии  <br/> |Предоставляет диагностические сведения для устройства Cloud Connector.  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |Возвращает учетные данные текущего развертывания облачного соединитела.  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |Возвращает путь внешнего файла сертификата для развертывания облачного соединитела. Пользователь готовит этот сертификат.  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |Показывает текущий каталог, в котором хранятся файлы конфигурации уровня сайта. Папка содержит базовые файлы установки VHD и облачного соединителя. Эта папка должна быть совместной со всеми другими устройствами сайта Cloud Connector.  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |Показывает текущий каталог, в котором хранятся журналы уровня сайта для облачного соединитела.  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> Версия 2.0 и более поздние версии  <br/> |Возвращает версию в экземпляре Cloud Connector. Get-CCVersion можно использовать только в хост-машине Cloud Connector.  <br/> |
|[Import-CcConfiguration](import-ccconfiguration.md) <br/> Версия 2.0 и более поздние версии  <br/> |Импорт конфигурации Skype для бизнеса cloud Connector Edition из локального файла на сервер хост-сервера облачного соединитетеля.  <br/> |
|[Install-CcAppliance](install-ccappliance.md) <br/> |Устанавливает устройство облачного соединителя, включая виртуальные машины AD, Центрального магазина управления, сервера-посредника и edge Server на сервере хост-сервера.  <br/> |
|[Publish-CcAppliance](publish-ccappliance.md) <br/> | Получает сведения о высокой доступности из конфигурации клиента в Интернете и публикует ее в устройство Cloud Connector на сервере хост-сервера. <br/> |
|[Register-CcAppliance](register-ccappliance.md) <br/> | Регистрирует сведения о устройстве на сайте PSTN в конфигурации онлайн-клиента. Перед развертыванием и управлением устройством должна быть зарегистрирована служба управления облачным соединитетелем. <br/> |
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> Версия 1.4.2 и более поздние версии  <br/> |Удаляет файл резервного копирования службы сертификации \<SiteRootDirectory\> \CA\SfB CCE Root.p12" в папке ЦС в каталоге совместной работы сайта для cloud Connector.  <br/> |
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> Версия 1.4.2 и более поздние версии  <br/> |Удаляет устаревшие сертификаты сервера в Центральном хранилище управления, сервере-посреднике и edge Server после выполнения Renew-CcCACertificate или обновления CcServerCertificate.  <br/> |
|[Renew-CcCACertificate](renew-cccacertificate.md) <br/> Только версия 1.4.2  <br/> |Переустановка сервера AD Server службы сертификации для создания нового корневого сертификата ЦС.  <br/> |
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <br/> Только версия 1.4.2  <br/> |Обновляет сертификаты для облачного соединитетеля, когда они истекли или уже истекли.  <br/> |
|[Reset-CcCACertificate](reset-cccacertificate.md) <br/> Версия 1.4.2 и более поздние версии  <br/> |Сбрасывает серверы полномочий сертификата для установки нового сертификата.  <br/> |
|[Restore-CcCredentials](restore-cccredentials.md) <br/> Версия 2.1 и более поздние версии  <br/> |Очистка учетных данных и повторное ввод всех учетных данных, используемых для текущего развертывания облачного соединитела.  <br/> |
|[Search-CcLog](search-cclog.md) <br/> |Поиск журналов входящих и исходяющих вызовов в каталоге журнала устройств cloud Connector  <br/> |
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |Задает рабочий каталог на сервере хост-сервера Cloud Connector. Все файлы развертывания хранятся в этом каталоге.  <br/> |
|[Set-CcCredential](set-cccredential.md) <br/> |Задает учетные данные текущего развертывания облачного соединитела.  <br/> |
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |Указывает путь, по котором хранится сертификат для сервера-посредника или edge Server.  <br/> |
|[Set-CcSiteDirectory](set-ccsitedirectory.md) <br/> |Задает каталог, в котором будут храниться файлы конфигурации уровня сайта для облачного соединитела. Папка будет содержать базовые файлы конфигурации VHD и облачного соединитела.  <br/> |
|[Start-CcDownload](start-ccdownload.md) <br/> |Синхронно загружает биты облачного соединитетеля и файл msi.  <br/> |
|[Start-CcLogging](start-cclogging.md) <br/> |Создает журнал входящих и исходяющих вызовов для устройства облачного соединитела.  <br/> |
|[Stop-CcLogging](stop-cclogging.md) <br/> |Перестает создавать журнал входящих и исходяющих вызовов для устройства облачного соединитела.  <br/> |
|[Switch-CcVersion](switch-ccversion.md) <br/> |Отключает запущенный прибор и переключается на недавно развернутый или резервный.  <br/> |
|[Uninstall-CcAppliance](uninstall-ccappliance.md) <br/> |Uninstalls the running Cloud Connector appliance from the host server.  <br/> |
|[Unregister-CcAppliance](unregister-ccappliance.md) <br/> |Unregisters the current Cloud Connector appliance from a PSTN site in the online tenant configuration.  <br/> |
|[Update-CcCACertificate](update-cccacertificate.md) <br/> Версия 2.0 и более поздние версии  <br/> |Переустановка сервера AD Server службы сертификации для создания нового корневого сертификата ЦС.  <br/> |
|[Update-CcServerCertificate](update-ccservercertificate.md) <br/> Версия 2.0 и более поздние версии  <br/> |Обновляет сертификаты для облачного соединитетеля, когда они истекли или уже истекли.  <br/> |
