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
ms.localizationpriority: medium
ms.assetid: 072b4bdc-0f1e-4fce-a41e-5c60d24556d5
description: В следующей таблице перечислены Skype для бизнеса Cloud Connector Edition командлеты с кратким описанием и ссылками на дополнительные сведения.
ms.openlocfilehash: efe4a048e939b6491acc93b7ccd4717ffc9aca8b
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676171"
---
# <a name="cloud-connector-cmdlet-reference"></a>Справочник по командлетам Cloud Connector

> [!Important]
> Выпуск Cloud Connector будет снят с учета 31 июля 2021 г. вместе с Skype для бизнеса Online. После обновления организации до Teams узнайте, как подключить локальную телефонную сеть к Teams с помощью прямой [маршрутизации](/MicrosoftTeams/direct-routing-landing-page).

В следующей таблице перечислены Skype для бизнеса Cloud Connector Edition командлеты с кратким описанием и ссылками на дополнительные сведения.
  
> [!NOTE]
> Необходимо выполнить все командлеты на хост-компьютере Cloud Connector и запустить сеанс PowerShell от имени администратора. 
  
|Имя командлета**|Описание|
|---|---|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <p> Версия 1.4.2 и более поздние|Создает резервную копию службы центра сертификации в файл и сохраняет его в папке ЦС в каталоге общего ресурса сайта.|
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md)|Создает базовый файл виртуального жесткого диска (VHDX), используя предоставленный клиентом Windows Server 2012 R2 ISO-файл. VHDX-файл будет использоваться во время развертывания СоединителяCloud.|
|[Enter-CcUpdate](enter-ccupdate.md)|Подготавливает сервер узла Cloud Connector к процессу обновления, помещая его в режим обслуживания. Устройство "размыкается"; То есть все существующие вызовы будут завершены, но новые вызовы будут отклонены.|
|[Exit-CcUpdate](exit-ccupdate.md)|Выход из режима обслуживания обновления на сервере узла Cloud Connector.|
|[Export-CcConfiguration](export-ccconfiguration.md)|Экспортирует конфигурацию Skype для бизнеса Cloud Connector Edition в локальный файл на сервере Skype для бизнеса Cloud Connector Edition узла.|
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md)|Экспортирует пример файла конфигурации Cloud Connector (.ini) в каталог устройства cloud Connector. Вы можете изменить и переименовать файл, который будет использовать для развертывания.|
|[Export-CcRootCertificate](export-ccrootcertificate.md) <p> Версия 1.4.2 и более поздние|Экспортирует сертификат корневого ЦС в локальный файл на сервере узла Cloud Connector.|
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md)|Извлекает рабочий каталог на сервере узла Cloud Connector. Все файлы развертывания хранятся в этом каталоге.|
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md)|Показывает текущий каталог, в котором хранятся журналы для устройства Cloud Connector.|
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <p> Версия 2.1 и более поздние|Предоставляет диагностические сведения для устройства Cloud Connector.|
|[Get-CcCredential](get-cccredential.md)|Возвращает учетные данные текущего развертывания Cloud Connector.|
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md)|Возвращает путь к файлу внешнего сертификата для развертывания Cloud Connector. Пользователь подготавливает этот сертификат.|
|[Get-CcSiteDirectory](get-ccsitedirectory.md)|Показывает текущий каталог, в котором хранятся файлы конфигурации уровня сайта. Папка содержит базовые файлы установки VHD и Cloud Connector. Эта папка должна совместно использоваться всеми другими устройствами сайта Cloud Connector.|
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md)|Показывает текущий каталог, в котором хранятся журналы уровня сайта для Cloud Connector.|
|[Get-CcVersion](get-ccversion.md) <p> Версия 2.0 и более поздние|Возвращает версию в экземпляре Cloud Connector. Get-CCVersion можно использовать только на хост-компьютере Cloud Connector.|
|[Import-CcConfiguration](import-ccconfiguration.md) <p> Версия 2.0 и более поздние|Импортирует конфигурацию Skype для бизнеса Cloud Connector Edition из локального файла на сервер узла Cloud Connector.|
|[Install-CcAppliance](install-ccappliance.md)|Устанавливает устройство Cloud Connector, включая AD, центральное хранилище управления, сервер-посредник и виртуальные машины пограничного сервера, на сервере узла.|
|[Publish-CcAppliance](publish-ccappliance.md)|Получает сведения о высокой доступности из сетевой конфигурации клиента и публикует их на устройстве Cloud Connector на сервере узла.|
|[Register-CcAppliance](register-ccappliance.md)|Регистрирует сведения об устройстве на сайте ТСОП в сетевой конфигурации клиента. Устройство должно быть зарегистрировано, прежде чем его можно будет развернуть и управлять службой управления Cloud Connector.|
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <p> Версия 1.4.2 и более поздние|Удаляет файл резервной копии службы центра сертификации \\<SiteRootDirectory\>CA\SfB CCE Root.p12 в папке ЦС в каталоге общего ресурса сайта для Cloud Connector.|
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <p> Версия 1.4.2 и более поздние|Удаляет устаревшие сертификаты сервера в центральном хранилище управления, сервере-посреднике и пограничном сервере после выполнения командлетов Renew-CcCACertificate или обновления CcServerCertificate.|
|[Renew-CcCACertificate](renew-cccacertificate.md) <p> Только версия 1.4.2|Переустановит сервер AD Службы центра сертификации, чтобы создать сертификат корневого ЦС.|
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <p> Только версия 1.4.2|Обновляет сертификаты для Cloud Connector, когда срок их действия истек или срок их действия истек.|
|[Reset-CcCACertificate](reset-cccacertificate.md) <p> Версия 1.4.2 и более поздние|Сбрасывает серверы центра сертификации для установки нового сертификата центра сертификации.|
|[Restore-CcCredentials](restore-cccredentials.md) <p> Версия 2.1 и более поздние|Очищает учетные данные и предлагает повторно ввести все учетные данные, используемые для текущего развертывания Cloud Connector.|
|[Search-CcLog](search-cclog.md)|Поиск журналов входящих и исходящих вызовов в каталоге журнала устройства Cloud Connector|
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md)|Задает рабочий каталог на сервере узла Cloud Connector. Все файлы развертывания хранятся в этом каталоге.|
|[Set-CcCredential](set-cccredential.md)|Задает учетные данные текущего развертывания Cloud Connector.|
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md)|Указывает путь, по которому хранится сертификат для сервера-посредника или пограничного сервера.|
|[Set-CcSiteDirectory](set-ccsitedirectory.md)|Задает каталог, в котором будут храниться файлы конфигурации уровня сайта для Cloud Connector. Папка будет содержать базовые файлы конфигурации VHD и Cloud Connector.|
|[Start-CcDownload](start-ccdownload.md)|Скачивает биты Cloud Connector и MSI-файл синхронно.|
|[Start-CcLogging](start-cclogging.md)|Создает журнал входящих и исходящих вызовов для устройства Cloud Connector.|
|[Stop-CcLogging](stop-cclogging.md)|Прекращает создание журнала входящих и исходящих вызовов для устройства Cloud Connector.|
|[Switch-CcVersion](switch-ccversion.md)|Отключает работающее устройство и переключается на только что развернутый или резервный модуль.|
|[Uninstall-CcAppliance](uninstall-ccappliance.md)|Удаляет работающее устройство Cloud Connector с сервера узла.|
|[Unregister-CcAppliance](unregister-ccappliance.md)|Отменяет регистрацию текущего устройства Cloud Connector на сайте ТСОП в конфигурации сетевого клиента.|
|[Update-CcCACertificate](update-cccacertificate.md) <p> Версия 2.0 и более поздние|Переустановит сервер AD Службы центра сертификации, чтобы создать сертификат корневого ЦС.|
|[Update-CcServerCertificate](update-ccservercertificate.md) <p> Версия 2.0 и более поздние|Обновляет сертификаты для Cloud Connector, когда срок их действия истек или срок их действия истек.|
