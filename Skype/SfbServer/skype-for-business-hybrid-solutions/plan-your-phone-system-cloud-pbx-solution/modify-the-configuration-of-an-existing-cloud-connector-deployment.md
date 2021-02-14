---
title: Изменение конфигурации существующего развертывания Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: Выполните действия в этом разделе, чтобы изменить конфигурацию существующего развертывания Skype для бизнеса Cloud Connector Edition 1.4.1 или более поздней версии.
ms.openlocfilehash: 2d70dfa9e25a0c89a31e25699e67a21f14e4f097
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359115"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>Изменение конфигурации существующего развертывания Cloud Connector

> [!Important]
> Выпуск Cloud Connector Edition завершится 31 июля 2021 г. вместе со Skype для бизнеса Online. После обновления вашей организации до Teams узнайте, как подключить свою локальной телефонной сети к Teams с помощью [прямой маршрутизации.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

Выполните действия в этом разделе, чтобы изменить конфигурацию существующего развертывания Skype для бизнеса Cloud Connector Edition 1.4.1 или более поздней версии. 
  
## <a name="modify-the-configuration-of-a-single-site"></a>Изменение конфигурации одного сайта
<a name="BKMK_SIngleSite"> </a>

Если на сайте имеется только одно устройство, то при изменении параметров конфигурации после его развертывания можно изменить файл CloudConnector.ini и снова запустить развертывание.
  
1. Чтобы удалить все существующие виртуальные машины на сервере хост-сервера, запустите следующий cmdlet: 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. Чтобы отоиметь регистрацию устройства, запустите следующий cmdlet:
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Обновим CloudConnector.ini в каталоге устройств.
    
4. Чтобы обновить конфигурацию, запустите следующий cmdlet: (Этот шаг применим только для версии 2; для предыдущих версий перешаговые перейти к следующему шагу.)
    
   ```powershell
   Import-CcConfiguration 
   ```

5. Чтобы снова зарегистрировать устройство, запустите следующий cmdlet:
    
   ```powershell
   Register-CcAppliance
   ```

6. Чтобы установить Skype для бизнеса Cloud Connector Edition, запустите следующий cmdlet:
    
   ```powershell
   Install-CcAppliance
   ```

Если на сайте несколько устройств, вам потребуется выполнять эти действия, изменять файл CloudConnector.ini и выполнять их развявку по одному.
  
1. Чтобы удалить все существующие виртуальные машины на текущем устройстве, запустите следующий cmdlet: 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. Чтобы отоиметь регистрацию устройства, запустите следующий cmdlet:
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Обновим CloudConnector.ini в каталоге устройств.
    
4. Чтобы обновить конфигурацию, запустите следующий cmdlet: (Этот шаг применим только для версии 2; для предыдущих версий перешаговые перейти к следующему шагу.)
    
   ```powershell
   Import-CcConfiguration 
   ```

5. Чтобы снова зарегистрировать устройство, запустите следующий cmdlet:
    
   ```powershell
   Register-CcAppliance
   ```

6. Чтобы получить последнюю конфигурацию, запустите следующий cmdlet на всех остальных устройствах на сайте:
    
   ```powershell
   Publish-CcAppliance
   ```

7. Чтобы выполнить перезапись Cloud Connector на текущем устройстве, запустите следующий cmdlet:
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a>Изменение конфигурации нескольких сайтов
<a name="BKMK_MultipleSites"> </a>

Чтобы изменить конфигурацию для нескольких сайтов в развертывании, выполните действия для одного сайта, обновляя по одному сайту за раз.
  
## <a name="modify-the-configuration-of-your-microsoft-365-or-office-365-organization-to-enable-automatic-updates"></a>Изменение конфигурации организации Microsoft 365 или Office 365 для автоматического обновления
<a name="BKMK_MultipleSites"> </a>

Чтобы включить автоматическое обновление операционной системы и автоматическое обновление bits, необходимо использовать учетную запись администратора клиента Skype для бизнеса для управления через Интернет и использовать удаленную долю PowerShell клиента следующим образом.
  
Если вы отключили автоматическое обновление операционной системы или bits automatic updates, ваш хост и виртуальная машина могут пропустить важные обновления Windows, и Cloud Connector не будет автоматически обновляться до новой версии. Настоятельно рекомендуется включить автоматические обновления.
  
1. Для свойства EnableAutoUpdate сайта должно быть установлено значение true (значение по умолчанию). Чтобы убедиться, что для EnableAutoUpdate установлено true, запустите следующий cmdlet:
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. Создание окна автоматического обновления для клиента.
    
    Период времени может быть ежедневным, еженедельным и ежемесячным. Все время в окнах требуется время начала и длительность.
    
   - Для ежедневного периода времени требуется только время начала и длительность. 
    
   - Для еженедельного окна времени необходимы дни недели, которые могут быть одним или несколькими днями.
    
   - В течение ежемесячного времени может быть два типа. Первый тип — указать день месяца, который может быть одним днем. Второй тип — указать недели месяца вместе с днями недели, которые могут быть как одним элементом, так и несколькими элементами.
    
   - Для каждого клиента может быть определено 20 периодов времени. По умолчанию для нового клиента будет создано окно времени по умолчанию для обновления операционной системы и bits. Запустите следующие cmdlets, чтобы установить ежедневный, еженедельный или ежемесячный период времени:
    
   ```powershell
   New-CsTenantUpdateTimeWindow -Identity Night -Daily -StartTime 22:00 -Duration 6:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity WeekdayNight -Weekly -DaysOfWeek Monday,Tuesday,Wednesday,Thursday,Friday -StartTime 22:00 -Duration 4:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity FirstAndLastWeekend -Monthly -WeeksOfMonth First,Last -DaysOfWeek Sunday,Saturday -StartTime 0:00 -Duration 10:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity MidDayOfMonth -Monthly -DayOfMonth 15 -StartTime 0:00 -Duration 1.00:00
   ```

   - Назначьте время обновления сайту. 
    
     Время обновления bits и время обновления ОС настраиваются отдельно. Обоим из них можно на назначены один или несколько периодов времени. Каждый период времени может быть назначен различным сайтам и их назначению (bits update and OS update). Чтобы установить время для сайта, запустите следующий cmdlet: 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>Обновление учетных данных администратора выделенного клиента
<a name="BKMK_MultipleSites"> </a>

Административные изменения в организации Microsoft 365 или Office 365 для Cloud Connector внося из учетной записи с необходимыми разрешениями. В Версиях Cloud Connector до версии 2.0 эта учетная запись является выделенной учетной записью глобального администратора клиента. В Cloud Connector версий 2.0 и более поздних версий эта учетная запись может быть учетной записью Microsoft 365 или Office 365 с правами администратора Skype для бизнеса.
  
Если учетные данные учетной записи администратора меняются в Microsoft 365 или Office 365, вам также потребуется обновить локально кэшные учетные данные в Cloud Connector, выведя следующую команду администратора PowerShell на каждом развернутом устройстве Cloud Connector:
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>Обновление пароля для сервера хост-сервера
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Этот раздел применим к Cloud Connector версии 2.0 и более поздних версий. 
  
Все учетные данные Cloud Connector хранятся в следующем файле: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml". При смене пароля на сервере на хост-сервере потребуется обновить локально сохраненные учетные данные.
  
Чтобы обновить локально хранимые учетные данные на устройстве Cloud Connector, выполните указанные ниже действия с помощью [get-CcCredential](get-cccredential.md) и [Set-CcCredential.](set-cccredential.md)
  
1. Чтобы получить пароли, необходимые позже, запустите следующие команды: 
    
   - Get-CcCredential -AccountType DomainAdmin -DisplayPassword
    
   - Get-CcCredential -AccountType VMAdmin -DisplayPassword
    
   - Get-CcCredential -AccountType CceService -DisplayPassword
    
2. Измените пароль учетной записи на сервере.
    
3. Перезапустите сервер хост-сервера.
    
4. Удалите следующий файл: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml".
    
5. Запустите консоль PowerShell от учетной записи администратора, а затем запустите "Register-CcAppliance -Local", чтобы повторно ввести пароли, следуя описанию. Обязательно введите тот же пароль, который был введен ранее для развертывания Cloud Connector.
    
По умолчанию VmAdmin и DomainAdmin используют тот же пароль, что и CceService. Если пароли DomainAdmin, VMAdmin и CceService, возвращенные на шаге 1, отличаются, необходимо выполнить следующие действия.
  
1. Выполните Set-CcCredential -AccountType DomainAdmin следующим образом:
    
1. При запросе учетных данных старой учетной записи введите учетные данные, использованные для пароля CceService.
    
2. При запросе учетных данных новой учетной записи введите пароль для пароля DomainAdmin, возвращенного на шаге 1.
    
2. Выполните Set-CcCredential -AccountType VmAdmin следующим образом:
    
1. При запросе учетных данных старой учетной записи введите учетные данные, использованные для пароля CceService.
    
2. При запросе учетных данных новой учетной записи введите пароль для пароля VmAdmin, возвращенного на шаге 1. 
    
## <a name="update-the-password-for-the-cceservice-account"></a>Обновление пароля учетной записи CceService
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Этот раздел применим к Cloud Connector версии 2.0.1 и более поздних версий. 
  
Служба Cloud Connector запускает службу управления Cloud Connector. Учетная запись CceService создается во время развертывания Cloud Connector Edition и сохраняется в следующих файлах: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml" и "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".
  
Чтобы обеспечить доступ всех устройств к совместному доступу к каталогу сайта, пароль для учетной записи CceService должен быть одинаковым на всех устройствах, развернутых на сайте. Учитывайте следующее:
  
- По умолчанию учетная запись CceService настроена как "Срок действия пароля не истекает". При обновлении пароля Корпорация Майкрософт рекомендует сохранить эту конфигурацию.
    
- Пароль следует обновлять в периоды не пиковой нагрузки и вне периода автоматического обновления для битов или обновлений Windows. При обновлении пароля необходимо опустить и перезапустить устройство, что занимает некоторое время. Перезапуск устройства прерывает операции автоматического обновления. 
    
- При изменении пароля учетной записи CceService необходимо указать все учетные данные и обновить их в локально сохраненном файле. 
    
Для каждого устройства, которое принадлежит к одному сайту STN, необходимо указать следующее: 
  
1. Чтобы получить имена и пароли учетных записей, которые будут использовать позже, запустите следующие команды:
    
   ```powershell
   Get-CcCredential -AccountType TenantAdmin -DisplayPassword
   Get-CcCredential -AccountType TenantAdmin
   Get-CcCredential -AccountType OMSWorkspace -DisplayPassword
   Get-CcCredential -AccountType OMSWorkspace 
   Get-CcCredential -AccountType ExternalCert -DisplayPassword
   Get-CcCredential -AccountType CABackupFile -DisplayPassword
   Get-CcCredential -AccountType CceService -DisplayPassword
   Get-CcCredential -AccountType VMAdmin -DisplayPassword
   Get-CcCredential -AccountType DomainAdmin -DisplayPassword
   ```

2. Запустите Enter-CcUpdate для истощать устройство и переходить в режим обслуживания вручную.
    
3. Обновите пароль учетной записи CceService на сервере.
    
4. Перезапустите сервер хост-сервера.
    
5. Запустите Restore-CcCredentials, чтобы повторно ввести пароли, следуя описанию. 
    
    Обязательно введите тот же пароль, который был введен ранее для развертывания Cloud Connector, за исключением учетной записи CceService. Для учетной записи CceService введите новый пароль. Убедитесь, что новый пароль для учетной записи CceService одинаковый для всех устройств на сайте STN.
    
6. По умолчанию VmAdmin и DomainAdmin используют тот же пароль, что и CceService. Если пароли DomainAdmin, VMAdmin и CceService, возвращенные на шаге 1, отличаются, необходимо выполнить следующие действия.
    
7. Выполните Set-CcCredential -AccountType DomainAdmin следующим образом:
    
   - При запросе учетных данных старой учетной записи введите учетные данные, использованные для пароля CceService.
    
   - При запросе учетных данных новой учетной записи введите пароль для пароля DomainAdmin, возвращенного на шаге 1.
    
8. Выполните Set-CcCredential -AccountType VmAdmin следующим образом:
    
   - При запросе учетных данных старой учетной записи введите учетные данные, использованные для пароля CceService.
    
   - При запросе учетных данных новой учетной записи введите пароль для пароля VmAdmin, возвращенного на шаге 1. 
    
9. Запустите Exit-CcUpdate для перемещения устройства из режима обслуживания вручную.
    
10. После выполнения этих действий на всех устройствах на одном сайте STN удалите следующие файлы в корневом каталоге сайта:
    
    - CcLockFile
    
    - Site_\<Edge External Sip Pool fqdn\>
    
    - Tenant_\<Edge External Sip Pool fqdn\>
    
    - TenantConfigLock_\<Edge External Sip Pool fqdn\>
    
## <a name="add-a-new-sip-domain"></a>Добавление нового домена SIP
<a name="BKMK_UpdatePassword"> </a>

Чтобы добавить новый домен SIP (или несколько доменов SIP) в существующее развертывание Cloud Connector, сделайте следующее:
  
1. Убедитесь, что вы выполнили действия по обновлению домена в Microsoft 365 или Office 365 и получили возможность добавлять записи DNS. Дополнительные сведения о том, как настроить домен в Microsoft 365 или Office 365, см. в подстройки "Добавление домена в [Microsoft 365" или "Office 365".](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)
    
2. Обновите файл конфигурации Cloud Connector с помощью нового домена или доменов SIP.
    
3. Запросите новый внешний сертификат Edge с дополнительными именами SAN для sip.domain для каждого домена SIP, определенного в конфигурации Cloud Connector. 
    
4. Задан путь к новому внешнему сертификату edge следующим образом:
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Следуйте инструкциям по [изменению конфигурации](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) одного сайта или [изменению конфигурации нескольких сайтов.](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)
    
## <a name="modify-the-primary-sip-domain"></a>Изменение основного домена SIP
<a name="BKMK_UpdatePassword"> </a>

Если необходимо изменить основной домен SIP в развертывании Cloud Connector, сделайте следующее:
  
1. Убедитесь, что вы выполнили действия по обновлению домена в Microsoft 365 или Office 365 и получили возможность добавлять записи DNS. Дополнительные сведения о том, как настроить домен в Microsoft 365 или Office 365, см. в подстройки "Добавление домена в [Microsoft 365" или "Office 365".](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)
    
2. Обновите файл конфигурации Cloud Connector с помощью нового домена SIP.
    
3. Запросите новый внешний сертификат Edge с дополнительными именами SAN для sip.domain для каждого домена SIP, определенного в конфигурации Cloud Connector. 
    
4. Задан путь к новому внешнему сертификату edge следующим образом:
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Удалите регистрацию клиента для каждого устройства на сайте, вынеся следующий cmdlet в powerShell администратора в Cloud Connector:
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    Удалите регистрацию сайта для каждого сайта, выдав следующий cmdlet в Skype для бизнеса Online PowerShell:
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    Чтобы удалить каждое устройство, с помощью администратора PowerShell в Cloud Connector выделили следующий cmdlet:
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     Зарегистрируйте каждое устройство с помощью следующего cmdlet в администраторе PowerShell в Cloud Connector:
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     Установите каждое устройство по одному, задав в администраторе PowerShell в Cloud Connector следующий cmdlet:
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>Замена внешнего сертификата edge новым сертификатом
<a name="BKMK_UpdatePassword"> </a>

Если необходимо заменить внешний сертификат edge на устройствах Cloud Connector, необходимо получить новый сертификат edge, подготовить PFX-файл, содержащий закрытый ключ и полную цепочку сертификатов, а затем сделать следующее на каждом устройстве:
  
1. Переставьте устройство в режим обслуживания с помощью Enter-CcUpdate управления.
    
2. Выполните следующую команду: 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    Если пароль нового сертификата такой же, как и старый, импорт будет успешным. Если пароль отличается, вы получите сообщение об ошибке пароля, и вам потребуется сбросить пароль, заведя Register-CcAppliance с параметром -Local, а затем повторите шаг 2. 
    
4. Выйдите из режима обслуживания устройства с помощью cmdlet Exit -CcUpdate.
    

