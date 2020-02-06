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
description: В следующей таблице перечисляются командлеты Skype для бизнеса Cloud Connector Edition с кратким описанием их функций, а также приводятся ссылки на дополнительные сведения.
ms.openlocfilehash: c82d81fe19af7c0f305ce18e0bbce83f944b5d73
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803719"
---
# <a name="cloud-connector-cmdlet-reference"></a>Cloud Connector cmdlet reference
 
В следующей таблице перечисляются командлеты Skype для бизнеса Cloud Connector Edition с кратким описанием их функций, а также приводятся ссылки на дополнительные сведения.
  
> [!NOTE]
> Вы должны выполнить все командлеты на хостном компьютере облачного соединителя, и вы должны запустить сеанс PowerShell с правами администратора. 
  
|**Имя командлета**|**Описание**|
|:-----|:-----|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <br/> Версия 1.4.2 и более поздние версии  <br/> |Выполняет резервное копирование службы центра сертификации в файл и сохраняет его в папку ЦС в общем каталоге сайта.      <br/> |
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |Создает файл базового виртуального жесткого диска (VHDX) на основе предоставленного клиентом ISO-файла с образом Windows Server 2012 R2. VHDX-файл используется в процессе развертывания Cloud Connector.   <br/> |
|[Enter-CcUpdate](enter-ccupdate.md) <br/> |Подготавливает сервер хоста облачного соединителя для процесса обновления, переводя его в режим обслуживания. Устройство "застоко"; Это значит, что все существующие звонки будут выполнены, но новые звонки будут отвергнуты.  <br/> |
|[Exit-CcUpdate](exit-ccupdate.md) <br/> |Выход из режима обслуживания обновления на хостном сервере облачного соединителя.  <br/> |
|[Export-CcConfiguration](export-ccconfiguration.md) <br/> |  Экспортирует конфигурацию Skype для бизнеса Cloud Connector Edition в локальный файл на сервере узла Skype для бизнеса Cloud Connector Edition. <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |Экспорт файла конфигурации примера облачного соединителя (ini) в каталог управляющего устройства облачного соединителя. Вы можете изменить и переименовать этот файл, чтобы использовать его в своем развертывании.  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> Версия 1.4.2 и более поздние версии   <br/> |Экспорт сертификата корневого ЦС в локальный файл на хост-сервере облачного соединителя.  <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |Извлекает рабочий каталог на хостном сервере облачного соединителя. В этом каталоге хранятся все файлы развертывания.  <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |Показывает текущий каталог, в котором хранятся журналы для устройства облачного соединителя...  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> Версия 2,1 и более поздние версии  <br/> |Содержит диагностические сведения для устройства облачного соединителя.  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |Возвращает учетные данные развертывания текущего облачного соединителя.  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |Возвращает путь к файлу внешнего сертификата для развертывания облачного соединителя. Этот сертификат подготавливается пользователем.  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |Показывает текущий каталог, в котором хранятся файлы конфигурации уровня узла. В этой папке содержатся файлы установки базового виртуального жесткого диска и облачного соединителя. Эта папка должна быть предоставлена всем другим устройствам на сайте облачного соединителя.  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |Показывает текущий каталог, в котором хранятся журналы уровня сайта для облачного соединителя.  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> Версия 2.0 и более поздние версии  <br/> |Возвращает версию в экземпляр Cloud Connector. Использовать командлет Get-CCVersion можно только на хост-компьютере Cloud Connector.  <br/> |
|[Import-CcConfiguration](import-ccconfiguration.md) <br/> Версия 2.0 и более поздние версии  <br/> |Импорт конфигурации облачного соединителя Skype для бизнеса из локального файла на хост-сервер облачного соединителя.  <br/> |
|[Install-CcAppliance](install-ccappliance.md) <br/> |Установка управляющего устройства облака (в том числе рекламы, хранилища централизованного управления, сервера-посредника и виртуальных компьютеров пограничного сервера) на хост-сервере.  <br/> |
|[Publish-CcAppliance](publish-ccappliance.md) <br/> | Возвращает сведения о высокой доступности из конфигурации Интернет-клиента и публикует их на устройстве облачного соединителя на сервере узла. <br/> |
|[Register-CcAppliance](register-ccappliance.md) <br/> | Регистрирует сведения об устройстве на сайте ТСОП в конфигурации интерактивного клиента. Необходимо зарегистрировать устройство, прежде чем его можно будет развернуть и управлять с помощью службы управления облачным соединителем. <br/> |
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> Версия 1.4.2 и более поздние версии  <br/> |Удаление файла резервной копии службы центра сертификации\<"\>ситерутдиректори \ка\сфб кце root. p12" в папке CA в каталоге общего доступа к сайту для облачного соединителя.  <br/> |
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> Версия 1.4.2 и более поздние версии  <br/> |Удаляет прежние версии сертификатов сервера центрального хранилища управления, сервера-посредника и пограничного сервера после выполнения командлетов Renew-CcCACertificate или Renew CcServerCertificate.  <br/> |
|[Renew-CcCACertificate](renew-cccacertificate.md) <br/> Только для версии 1.4.2  <br/> |Переустанавливает сервер Active Directory службы центра сертификации для создания нового сертификата корневого центра сертификации.  <br/> |
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <br/> Только для версии 1.4.2  <br/> |Продлевает сертификаты для Cloud Connector, срок действия которых подходит к концу или уже истек.  <br/> |
|[Reset-CcCACertificate](reset-cccacertificate.md) <br/> Версия 1.4.2 и более поздние версии  <br/> |Сбрасывает серверы центра сертификации для установки нового сертификата центра сертификации.  <br/> |
|[Restore-CcCredentials](restore-cccredentials.md) <br/> Версия 2,1 и более поздние версии  <br/> |Очистка учетных данных и запрос на повторное ввод всех учетных данных, используемых для развертывания текущего облачного соединителя.  <br/> |
|[Search-CcLog](search-cclog.md) <br/> |Поиск в журналах входящих и исходящих вызовов в каталоге журнала на устройстве облачного соединителя  <br/> |
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |Задает рабочий каталог на хостном сервере облачного соединителя. В этом каталоге хранятся все файлы развертывания.  <br/> |
|[Set-CcCredential](set-cccredential.md) <br/> |Задает учетные данные развертывания текущего облачного соединителя.  <br/> |
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |Задает путь к сертификату для сервера-посредника или пограничного сервера.  <br/> |
|[Set-CcSiteDirectory](set-ccsitedirectory.md) <br/> |Задает каталог, в котором будут храниться файлы конфигурации уровня сайта для облачного соединителя. В папке будут находиться файлы конфигурации базового виртуального жесткого диска и Cloud Connector.  <br/> |
|[Start-CcDownload](start-ccdownload.md) <br/> |Синхронно загружает биты облачного соединителя и MSI-файл.  <br/> |
|[Start-CcLogging](start-cclogging.md) <br/> |Создание журнала входящих и исходящих вызовов для устройства облачного соединителя.  <br/> |
|[Stop-CcLogging](stop-cclogging.md) <br/> |Прекращение создания журнала входящих и исходящих вызовов для устройства облачного соединителя.  <br/> |
|[Switch-CcVersion](switch-ccversion.md) <br/> |Отключает работающее устройство и выполняет переключение на только что развернутое или резервное устройство.   <br/> |
|[Uninstall-CcAppliance](uninstall-ccappliance.md) <br/> |Удаляет запущенное приложение облачного соединителя с хостового сервера.  <br/> |
|[Unregister-CcAppliance](unregister-ccappliance.md) <br/> |Отменяет регистрацию текущего управляющего устройства облачного соединителя с сайта PSTN в конфигурации Интернет-клиента.  <br/> |
|[Update-CcCACertificate](update-cccacertificate.md) <br/> Версия 2.0 и более поздние версии  <br/> |Переустанавливает сервер Active Directory службы центра сертификации для создания нового сертификата корневого центра сертификации.  <br/> |
|[Update-CcServerCertificate](update-ccservercertificate.md) <br/> Версия 2.0 и более поздние версии  <br/> |Продлевает сертификаты для Cloud Connector, срок действия которых подходит к концу или уже истек.  <br/> |
   

