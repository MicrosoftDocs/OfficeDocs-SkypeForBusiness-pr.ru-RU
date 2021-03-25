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
description: Выполните действия в этом разделе, чтобы изменить конфигурацию существующего облачного соединитетеля Skype для бизнеса Edition 1.4.1 или более позднего развертывания.
ms.openlocfilehash: 7fdfdd5ac5a76ebbc3ac58e12a69e2e3af1330cd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109175"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>Изменение конфигурации существующего развертывания Cloud Connector

> [!Important]
> Cloud Connector Edition завершит карьеру 31 июля 2021 г. вместе со Skype для бизнеса Online. После обновления организации до Teams узнайте, как подключить сеть локальной телефонии к Teams с помощью прямой [маршрутизации.](/MicrosoftTeams/direct-routing-landing-page)

Выполните действия в этом разделе, чтобы изменить конфигурацию существующего облачного соединитетеля Skype для бизнеса Edition 1.4.1 или более позднего развертывания. 
  
## <a name="modify-the-configuration-of-a-single-site"></a>Изменение конфигурации одного сайта
<a name="BKMK_SIngleSite"> </a>

Если на сайте есть только один прибор, при изменении параметров конфигурации после развертывания можно изменить файл CloudConnector.ini и запустить развертывание снова.
  
1. Запустите следующий cmdlet, чтобы удалить все существующие виртуальные машины на сервере хост-сервера: 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. Запустите следующий cmdlet, чтобы оторегистрить устройство:
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Обновление файла CloudConnector.ini в Каталоге приборов.
    
4. Запустите следующий комдлет для обновления конфигурации: (Этот шаг применим только для версии 2; для предыдущих версий пропустите следующий шаг.)
    
   ```powershell
   Import-CcConfiguration 
   ```

5. Запустите следующий cmdlet, чтобы зарегистрировать устройство снова:
    
   ```powershell
   Register-CcAppliance
   ```

6. Запустите следующий cmdlet, чтобы установить Skype для бизнеса Cloud Connector Edition:
    
   ```powershell
   Install-CcAppliance
   ```

Если на сайте имеется несколько устройств, необходимо следовать этим шагам, изменять файл CloudConnector.ini и передиплоять устройства по одному.
  
1. Запустите следующий cmdlet, чтобы удалить все существующие виртуальные машины на текущем устройстве: 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. Запустите следующий cmdlet, чтобы оторегистрить устройство:
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Обновление файла CloudConnector.ini в Каталоге приборов.
    
4. Запустите следующий комдлет для обновления конфигурации: (Этот шаг применим только для версии 2; для предыдущих версий пропустите следующий шаг.)
    
   ```powershell
   Import-CcConfiguration 
   ```

5. Запустите следующий cmdlet, чтобы зарегистрировать устройство снова:
    
   ```powershell
   Register-CcAppliance
   ```

6. Запустите следующий cmdlet на всех других устройствах на сайте, чтобы выбрать последнюю конфигурацию:
    
   ```powershell
   Publish-CcAppliance
   ```

7. Запустите следующий cmdlet для передиплойки облачного соединителя на текущем устройстве:
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a>Изменение конфигурации нескольких сайтов
<a name="BKMK_MultipleSites"> </a>

Чтобы изменить конфигурацию для нескольких сайтов в развертывании, выполните действия для одного сайта, обновляя по одному сайту одновременно.
  
## <a name="modify-the-configuration-of-your-microsoft-365-or-office-365-organization-to-enable-automatic-updates"></a>Измените конфигурацию организации Microsoft 365 или Office 365, чтобы включить автоматические обновления
<a name="BKMK_MultipleSites"> </a>

Чтобы включить автоматические обновления операционной системы и автоматические обновления Bits, необходимо использовать учетную запись администратора клиента Skype для бизнеса для управления интернетом и использовать удаленный powerShell клиента следующим образом.
  
Если вы отключили автоматические обновления операционной системы или автоматические обновления Bits, ваш хост и виртуальная машина могут пропустить важные обновления Windows, и облачный соединителю не будет автоматически обновляться до новой версии. Рекомендуется включить автоматические обновления.
  
1. Свойство EnableAutoUpdate сайта необходимо задать значение true (значение по умолчанию). Запустите следующий cmdlet, чтобы убедиться, что EnableAutoUpdate задавалось верно:
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. Создайте окно времени автоматического обновления для клиента.
    
    Окно времени может быть ежедневным, еженедельным и ежемесячным. Все окна времени требуют времени начала и продолжительности.
    
   - Для ежедневного окне времени требуется только время начала и продолжительность. 
    
   - Для еженедельного окна времени необходимы дни недели, которые могут быть одним днем или несколькими днями.
    
   - Для ежемесячного окне времени может быть два типа. Первый тип — указать день месяца, который может быть одним днем. Второй тип — указать недели месяца, а также дни недели, которые могут быть как одним элементом, так и несколькими элементами.
    
   - Каждый клиент может иметь 20 окон времени. Окно времени по умолчанию будет создано для нового клиента в качестве окна времени по умолчанию для обновления операционной системы и обновления битов. Запустите следующий cmdlet(s), чтобы установить дневное, еженедельное или ежемесячное окно времени:
    
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

   - Назначьте на сайт окна времени обновления. 
    
     Время обновления битов и окна времени обновления ОС настраиваются отдельно. Оба из них могут быть назначены одним или несколькими окнами времени. Каждое окно времени может быть назначено различным сайтам и различным целям (обновление битов и обновление ОС). Запустите следующий cmdlet, чтобы установить окно времени для сайта: 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>Обновление учетных данных администратора клиента
<a name="BKMK_MultipleSites"> </a>

Административные изменения в организации Microsoft 365 или Office 365 для облачного соединитетеля внесения из учетной записи с необходимыми разрешениями. В версиях Cloud Connector до 2.0 эта учетная запись является выделенной глобальной учетной записью администратора клиента. В версиях Cloud Connector 2.0 и более поздней версии эта учетная запись может быть учетной записью Microsoft 365 или Office 365 с правами Администратора Skype для бизнеса.
  
Если учетные данные учетных данных учетных записей администратора изменяются в Microsoft 365 или Office 365, необходимо также обновить локализованные кэшные учетные данные в облачном соединителе, выведя следующую команду администратора PowerShell на каждом развернутом устройстве cloud Connector:
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>Обновление пароля для хост-сервера
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Этот раздел применим к версии Cloud Connector 2.0 и более поздней версии. 
  
Все учетные данные cloud Connector хранятся в следующем файле: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml". Когда пароль на сервере хост-сервера изменится, вам потребуется обновить учетные данные, хранимые на локальном уровне.
  
Чтобы обновить локально хранимые учетные данные в устройстве Облачного соединителя, используйте [cmdlets Get-CcCredential](get-cccredential.md) и [Set-CcCredential](set-cccredential.md) и выполните следующие действия:
  
1. Запустите следующие команды, чтобы получить необходимые пароли позже: 
    
   - Get-CcCredential-AccountType DomainAdmin-DisplayPassword
    
   - Get-CcCredential-AccountType VMAdmin-DisplayPassword
    
   - Get-CcCredential-AccountType CceService-DisplayPassword
    
2. Измените пароль учетной записи на сервере хост-сервера.
    
3. Перезапустите хост-сервер.
    
4. Удалите следующий файл: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml".
    
5. Запустите консоль PowerShell в качестве администратора, а затем запустите "Register-CcAppliance-Local", чтобы повторно ввести пароли, следующие описанию. Убедитесь, что вы вводите тот же пароль, который был введен ранее для развертывания облачного соединитела.
    
По умолчанию VmAdmin и DomainAdmin используют тот же пароль, что и CceService. Если пароли DomainAdmin, VMAdmin и CceService, возвращенные на шаге 1, отличаются, необходимо выполнить следующие действия:
  
1. Выполните Set-CcCredential-AccountType DomainAdmin следующим образом:
    
1. При запросе на старую учетную запись введите учетные данные, используемые для пароля CceService.
    
2. При запросе новой учетной записи введите пароль для пароля DomainAdmin, возвращенного на шаге 1.
    
2. Выполните Set-CcCredential-AccountType VmAdmin следующим образом:
    
1. При запросе на старую учетную запись введите учетные данные, используемые для пароля CceService.
    
2. При запросе новой учетной записи введите пароль для пароля VmAdmin, возвращенного на шаге 1. 
    
## <a name="update-the-password-for-the-cceservice-account"></a>Обновление пароля для учетной записи CceService
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Этот раздел применим к версии Cloud Connector 2.0.1 и более поздней версии. 
  
Служба облачного соединитела запускает службу управления облачным соединитетелем. Учетная запись CceService создается во время развертывания Cloud Connector Edition и хранится в следующих файлах: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml" и "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".
  
Чтобы все устройства могли получить доступ к совместной службе каталогов сайтов, пароль для учетной записи CceService должен быть одинаковым для всех устройств, развернутых на сайте. Учитывайте следующее:
  
- По умолчанию учетная запись CceService настроена как "Пароль никогда не истекает". При обновлении пароля Корпорация Майкрософт рекомендует сохранить эту конфигурацию.
    
- Необходимо обновить пароль во время периодов не пикового использования и вне автоматических окон времени обновления для битов или обновлений Windows. При обновлении пароля необходимо осушить и перезапустить устройство, что занимает некоторое время. Перезапуск устройства прерывает автоматические операции обновления. 
    
- При изменении пароля учетной записи CceService необходимо указать все учетные данные и обновить их в локальном файле. 
    
Для каждого устройства, принадлежаного одному и тому же сайту PSTN, необходимо указать следующее: 
  
1. Запустите следующие команды, чтобы получить имена и пароли учетных записей, которые будут использовать позже:
    
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

2. Запустите Enter-CcUpdate, чтобы слить устройство и переместить его в режим ручного обслуживания.
    
3. Обновление пароля учетной записи CceService на хост-сервере.
    
4. Перезапустите хост-сервер.
    
5. Запустите Restore-CcCredentials для повторного ввода паролей после описания. 
    
    Убедитесь, что вы вводите тот же пароль, который был введен ранее для развертывания облачного соединиттеля, за исключением учетной записи CceService. Для учетной записи CceService введите новый пароль. Убедитесь, что новый пароль для учетной записи CceService является одинаковым для всех устройств на сайте PSTN.
    
6. По умолчанию VmAdmin и DomainAdmin используют тот же пароль, что и CceService. Если пароли DomainAdmin, VMAdmin и CceService, возвращенные на шаге 1, отличаются, необходимо выполнить следующие действия:
    
7. Выполните Set-CcCredential-AccountType DomainAdmin следующим образом:
    
   - При запросе на старую учетную запись введите учетные данные, используемые для пароля CceService.
    
   - При запросе новой учетной записи введите пароль для пароля DomainAdmin, возвращенного на шаге 1.
    
8. Выполните Set-CcCredential-AccountType VmAdmin следующим образом:
    
   - При запросе на старую учетную запись введите учетные данные, используемые для пароля CceService.
    
   - При запросе новой учетной записи введите пароль для пароля VmAdmin, возвращенного на шаге 1. 
    
9. Запустите Exit-CcUpdate, чтобы переместить устройство из режима ручного обслуживания.
    
10. После выполнения этих действий на всех устройствах на одном сайте PSTN удалите следующие файлы в корневом каталоге сайта:
    
    - CcLockFile
    
    - Site_\<Edge External Sip Pool fqdn\>
    
    - Tenant_\<Edge External Sip Pool fqdn\>
    
    - TenantConfigLock_\<Edge External Sip Pool fqdn\>
    
## <a name="add-a-new-sip-domain"></a>Добавление нового домена SIP
<a name="BKMK_UpdatePassword"> </a>

Чтобы добавить новый домен SIP (или несколько SIP-доменов) в существующее развертывание облачного соединиттеля, сделайте следующее:
  
1. Убедитесь, что вы выполнили действия по обновлению домена в Microsoft 365 или Office 365 и получили возможность добавлять записи DNS. Дополнительные сведения о том, как настроить домен в Microsoft 365 или Office 365, см. в добавлении домена в [Microsoft 365 или Office 365.](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)
    
2. Обновление файла конфигурации облачного соединиттеля с помощью нового домена SIP или доменов.
    
3. Запросите новый внешний сертификат Edge с дополнительными именами SAN для sip.domain для каждого домена SIP, определенного в конфигурации облачного соединиттеля. 
    
4. Установите путь для нового внешнего сертификата Edge следующим образом:
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Следуйте инструкциям по [изменению](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) конфигурации одного сайта или [изменению конфигурации нескольких сайтов.](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)
    
## <a name="modify-the-primary-sip-domain"></a>Изменение основного домена SIP
<a name="BKMK_UpdatePassword"> </a>

Если вам необходимо изменить основной домен SIP в развертывании облачного соединитела, сделайте следующее:
  
1. Убедитесь, что вы выполнили действия по обновлению домена в Microsoft 365 или Office 365 и получили возможность добавлять записи DNS. Дополнительные сведения о том, как настроить домен в Microsoft 365 или Office 365, см. в добавлении домена в [Microsoft 365 или Office 365.](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)
    
2. Обновление файла конфигурации облачного соединиттеля с помощью нового домена SIP.
    
3. Запросите новый внешний сертификат Edge с дополнительными именами SAN для sip.domain для каждого домена SIP, определенного в конфигурации облачного соединиттеля. 
    
4. Установите путь для нового внешнего сертификата Edge следующим образом:
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Удалите регистрацию клиента для каждого устройства на сайте, заняв следующие cmdlet в администраторе PowerShell в Cloud Connector:
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    Удалите регистрацию сайта для каждого сайта, заняв следующие cmdlet в Skype для бизнеса Online PowerShell:
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    Удалить каждое устройство, запуская следующий комдлет в администраторе PowerShell в облачном соединителе:
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     Зарегистрируйте каждое устройство, задав следующий кодлет в администраторе PowerShell в облачном соединителе:
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     Установите каждое устройство по одному, запуская следующий комдлет в администраторе PowerShell на облачном соединителе:
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>Замените внешний сертификат Edge новым сертификатом
<a name="BKMK_UpdatePassword"> </a>

Если требуется заменить внешний сертификат Edge на устройствах облачного соединитела, вам потребуется получить новый сертификат Edge, подготовить файл PFX, содержащий закрытый ключ и цепочку полного сертификата, а затем сделать следующее на каждом устройстве:
  
1. Поместите устройство в режим обслуживания с помощью Enter-CcUpdate.
    
2. Выполните следующую команду: 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    Если пароль нового сертификата будет таким же, как и старый, импорт будет успешным. Если пароль отличается, вы получите ошибку, что пароль неправ, и вам нужно будет сбросить пароль, запуская Register-CcAppliance с параметром -Local, а затем повторяя шаг 2. 
    
4. Вытащайте устройство из режима обслуживания с помощью cmdlet Exit -CcUpdate.
