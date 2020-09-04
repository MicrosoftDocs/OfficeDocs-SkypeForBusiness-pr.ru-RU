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
description: В следующей таблице приведены командлеты Skype для бизнеса Cloud Connector Edition с кратким описанием и ссылки на дополнительные сведения.
ms.openlocfilehash: 8d33cd8c493c3acc165661e5af80625e773e2d0d
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359055"
---
# <a name="cloud-connector-cmdlet-reference"></a>Справочник по командлетам Cloud Connector
 
> [!Important]
> Cloud Connector Edition выйдет 31 июля 2021 вместе со Skype для бизнеса Online. После обновления вашей организации до Teams Узнайте, как подключить локальную телефонную сеть к Teams с помощью [прямой маршрутизации](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).

В следующей таблице приведены командлеты Skype для бизнеса Cloud Connector Edition с кратким описанием и ссылки на дополнительные сведения.
  
> [!NOTE]
> Необходимо выполнить все командлеты на компьютере узла Cloud Connector, а сеанс PowerShell необходимо запустить от имени администратора. 
  
|**Имя командлета**|**Описание**|
|:-----|:-----|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <br/> Версия 1.4.2 и более поздняя  <br/> |Выполняет резервное копирование службы центра сертификации в файл и сохраняет его в папке CA в общем каталоге сайта.     <br/> |
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |Создает файл базового виртуального жесткого диска (VHDX) с помощью предоставленного клиентом ISO-файла Windows Server 2012 R2. VHDX файл будет использоваться в Cloud Connector развертывания.  <br/> |
|[Enter-CcUpdate](enter-ccupdate.md) <br/> |Подготавливает сервер узла Cloud Connector для процесса обновления, переводя его в режим обслуживания. Устройство "Сток"; то есть все существующие звонки будут выполнены, но новые звонки отклоняются.  <br/> |
|[Exit-CcUpdate](exit-ccupdate.md) <br/> |Выполняет выход из режима обслуживания обновления на сервере узла Cloud Connector.  <br/> |
|[Export-CcConfiguration](export-ccconfiguration.md) <br/> | Экспортирует конфигурацию Skype для бизнеса Cloud Connector Edition в локальный файл на сервере узла Skype для бизнеса Cloud Connector Edition. <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |Экспортирует пример файла конфигурации Cloud Connector (ini) в каталог устройства для устройства Cloud Connector. Вы можете изменить и переименовать файл для использования в развертывании.  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> Версия 1.4.2 и более поздняя  <br/> |Экспортирует корневой сертификат ЦС в локальный файл на сервере узла Cloud Connector.  <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |Извлекает рабочий каталог на сервере узла Cloud Connector. Все файлы развертывания хранятся в этом каталоге.  <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |Показывает текущий каталог, в котором хранятся журналы для устройства Cloud Connector..  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> Версия 2,1 и более поздние версии  <br/> |Предоставляет диагностические сведения для устройства Cloud Connector.  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |Возвращает учетные данные текущего развертывания Cloud Connector.  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |Возвращает путь к файлу внешнего сертификата для развертывания Cloud Connector. Пользователь подготавливает этот сертификат.  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |Показывает текущий каталог, в котором хранятся файлы конфигурации уровня сайта. Папка содержит файлы установки базовых VHD и Cloud Connector. Эта папка должна быть общей для всех других устройств сайта Cloud Connector.  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |Показывает текущий каталог, в котором хранятся журналы уровня сайта для Cloud Connector.  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> Версия 2,0 и более поздние версии  <br/> |Возвращает версию в экземпляре Cloud Connector. Get – CCVersion можно использовать только на хостном компьютере Cloud Connector.  <br/> |
|[Import-CcConfiguration](import-ccconfiguration.md) <br/> Версия 2,0 и более поздние версии  <br/> |Импортирует конфигурацию Skype для бизнеса Cloud Connector Edition из локального файла на сервер узла Cloud Connector.  <br/> |
|[Install-CcAppliance](install-ccappliance.md) <br/> |Устанавливает устройство Cloud Connector, в том числе виртуальные машины Active Directory, центрального хранилища управления, сервера-посредника и пограничного сервера, на сервере узла.  <br/> |
|[Publish-CcAppliance](publish-ccappliance.md) <br/> | Получает сведения о высокой доступности из конфигурации интерактивного клиента и публикует их на устройстве Cloud Connector на сервере узла. <br/> |
|[Register-CcAppliance](register-ccappliance.md) <br/> | Регистрирует сведения об устройстве на сайте PSTN в конфигурации интерактивного клиента. Необходимо зарегистрировать устройство, прежде чем его можно будет развернуть и управлять с помощью службы управления Cloud Connector. <br/> |
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> Версия 1.4.2 и более поздняя  <br/> |Удаляет файл резервной копии службы центра сертификации " \<SiteRootDirectory\> \CA\SFB CCE root. p12" в папке CA в общем каталоге сайта для Cloud Connector.  <br/> |
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> Версия 1.4.2 и более поздняя  <br/> |Удаляет устаревшие сертификаты сервера центрального хранилища управления, сервера-посредника и пограничного сервера после выполнения командлетов обновления CcCACertificate или продления CcServerCertificate.  <br/> |
|[Renew-CcCACertificate](renew-cccacertificate.md) <br/> Только версия 1.4.2  <br/> |Переустанавливает сервер Active Directory службы центра сертификации для создания нового сертификата корневого центра сертификации.  <br/> |
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <br/> Только версия 1.4.2  <br/> |Обновляет сертификаты для Cloud Connector, срок действия которых истекает или уже истек.  <br/> |
|[Reset-CcCACertificate](reset-cccacertificate.md) <br/> Версия 1.4.2 и более поздняя  <br/> |Сбрасывает серверы центра сертификации для установки нового сертификата центра сертификации.  <br/> |
|[Restore-CcCredentials](restore-cccredentials.md) <br/> Версия 2,1 и более поздние версии  <br/> |Удаляет учетные данные и предлагает повторно ввести все учетные данные, используемые для текущего развертывания Cloud Connector.  <br/> |
|[Search-CcLog](search-cclog.md) <br/> |Выполняет поиск в журналах входящих и исходящих звонков в каталоге журнала устройства Cloud Connector  <br/> |
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |Задает рабочий каталог на сервере узла Cloud Connector. Все файлы развертывания хранятся в этом каталоге.  <br/> |
|[Set-CcCredential](set-cccredential.md) <br/> |Задает учетные данные текущего развертывания Cloud Connector.  <br/> |
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |Указывает путь, по которому хранится сертификат сервера-посредника или пограничного сервера  <br/> |
|[Set-CcSiteDirectory](set-ccsitedirectory.md) <br/> |Задает каталог, в котором будут храниться файлы конфигурации уровня сайта для Cloud Connector. В папке будут содержаться файлы конфигурации базового виртуального жесткого диска и Cloud Connector.  <br/> |
|[Start-CcDownload](start-ccdownload.md) <br/> |Синхронно загружает BITS и MSI Cloud Connector.  <br/> |
|[Start-CcLogging](start-cclogging.md) <br/> |Создает журнал входящих и исходящих вызовов для устройства Cloud Connector.  <br/> |
|[Stop-CcLogging](stop-cclogging.md) <br/> |Прекращение создания журнала входящих и исходящих вызовов для устройства Cloud Connector.  <br/> |
|[Switch-CcVersion](switch-ccversion.md) <br/> |Отключает работающее устройство и выполняет переключение на только что развернутое или резервное устройство.  <br/> |
|[Uninstall-CcAppliance](uninstall-ccappliance.md) <br/> |Удаляет запущенное устройство Cloud Connector с сервера узла.  <br/> |
|[Unregister-CcAppliance](unregister-ccappliance.md) <br/> |Отменяет регистрацию текущего устройства Cloud Connector на сайте PSTN в конфигурации интерактивного клиента.  <br/> |
|[Update-CcCACertificate](update-cccacertificate.md) <br/> Версия 2,0 и более поздние версии  <br/> |Переустанавливает сервер Active Directory службы центра сертификации для создания нового сертификата корневого центра сертификации.  <br/> |
|[Update-CcServerCertificate](update-ccservercertificate.md) <br/> Версия 2,0 и более поздние версии  <br/> |Обновляет сертификаты для Cloud Connector, срок действия которых истекает или уже истек.  <br/> |
   

