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
description: Выполните действия, описанные в этом разделе, чтобы изменить конфигурацию существующего развертывания Skype для бизнеса Cloud Connector Edition 1.4.1 или более поздней версии.
ms.openlocfilehash: 4b551d7cd7a61a1113b4b2bb05e2c0f5ca4f3288
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220299"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>Изменение конфигурации существующего развертывания Cloud Connector
 
Выполните действия, описанные в этом разделе, чтобы изменить конфигурацию существующего развертывания Skype для бизнеса Cloud Connector Edition 1.4.1 или более поздней версии. 
  
## <a name="modify-the-configuration-of-a-single-site"></a>Изменение конфигурации отдельного сайта
<a name="BKMK_SIngleSite"> </a>

Если на сайте имеется только одно устройство, то при необходимости изменить параметры конфигурации после развертывания устройства можно изменить файл CloudConnector. ini и снова запустить развертывание.
  
1. Выполните следующий командлет, чтобы удалить все существующие виртуальные машины на сервере узла: 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. Выполните следующий командлет, чтобы отменить регистрацию устройства:
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Обновите файл CloudConnector. ini в каталоге устройств.
    
4. Выполните следующий командлет, чтобы обновить конфигурацию: (этот шаг применим только для версии 2; для предыдущих версий перейдите к следующему шагу).
    
   ```powershell
   Import-CcConfiguration 
   ```

5. Выполните следующий командлет, чтобы снова зарегистрировать устройство:
    
   ```powershell
   Register-CcAppliance
   ```

6. Выполните следующий командлет, чтобы установить Skype для бизнеса Cloud Connector Edition:
    
   ```powershell
   Install-CcAppliance
   ```

Если на сайте несколько устройств, вам потребуется выполнить эти действия, изменить файл CloudConnector. ini и повторно развернуть устройства по одному.
  
1. Выполните следующий командлет, чтобы удалить все существующие виртуальные машины на текущем устройстве: 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. Выполните следующий командлет, чтобы отменить регистрацию устройства:
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Обновите файл CloudConnector. ini в каталоге устройств.
    
4. Выполните следующий командлет, чтобы обновить конфигурацию: (этот шаг применим только для версии 2; для предыдущих версий перейдите к следующему шагу).
    
   ```powershell
   Import-CcConfiguration 
   ```

5. Выполните следующий командлет, чтобы снова зарегистрировать устройство:
    
   ```powershell
   Register-CcAppliance
   ```

6. Выполните следующий командлет на всех остальных устройствах сайта, чтобы выбрать последнюю конфигурацию:
    
   ```powershell
   Publish-CcAppliance
   ```

7. Выполните следующий командлет, чтобы повторно развернуть Cloud Connector на текущем устройстве:
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a>Изменение конфигурации нескольких сайтов
<a name="BKMK_MultipleSites"> </a>

Чтобы изменить конфигурацию нескольких сайтов в развертывании, выполните действия для отдельного сайта, обновив по одному сайту за раз.
  
## <a name="modify-the-configuration-of-your-microsoft-365-or-office-365-organization-to-enable-automatic-updates"></a>Изменение конфигурации организации Microsoft 365 или Office 365 для включения автоматических обновлений
<a name="BKMK_MultipleSites"> </a>

Чтобы включить автоматическое обновление операционной системы и автоматическое обновление службы BITS, необходимо использовать учетную запись администратора клиента Skype для бизнеса для управления через Интернет и использовать удаленную оболочку PowerShell для клиента, как показано ниже.
  
Если вы отключили автоматические обновления операционной системы или автоматические обновления BITS, ваш узел и виртуальная машина могут пропустить важные обновления Windows, а Cloud Connector не будет автоматически обновляться до новой версии. Настоятельно рекомендуется включить автоматическое обновление.
  
1. Свойству EnableAutoUpdate сайта необходимо присвоить значение true (значение по умолчанию). Выполните следующий командлет, чтобы убедиться, что для EnableAutoUpdate установлено значение true:
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. Создайте период автоматического обновления для клиента.
    
    Окно времени может быть ежедневно, еженедельно и ежемесячно. Все время, в течение которого Windows требует времени начала и длительности.
    
   - Для ежедневного периода времени требуются только время начала и длительность. 
    
   - Для еженедельного периода времени необходимо указать дни недели, которые могут быть представлены в течение одного дня или нескольких дней.
    
   - Для ежемесячного окна можно указать два типа. Первый тип — указать день месяца, который может быть одним днем. Второй тип — указать недели месяца, а также дни недели, которые могут быть одним элементом или несколькими элементами.
    
   - Для каждого клиента можно задать 20 окон времени. Окно времени по умолчанию будет создано для нового клиента в качестве стандартного периода обновления операционной системы и обновления BITS. Выполните следующие командлеты, чтобы установить ежедневный, еженедельный или ежемесячный период времени:
    
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

   - Назначьте сайт времени обновления сайту. 
    
     Окна "время обновления BITS" и "время обновления ОС" настраиваются отдельно. Обоим пользователям можно назначить один или несколько окон. Каждое временное окно может быть назначено разным сайтам и различное назначение (обновление BITS и обновление ОС). Выполните следующий командлет, чтобы задать временное окно для сайта: 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>Обновление выделенных учетных данных администратора клиента
<a name="BKMK_MultipleSites"> </a>

Административные изменения в организации Microsoft 365 или Office 365 для Cloud Connector выполняются из учетной записи с необходимыми разрешениями. В версиях Cloud Connector до 2,0 эта учетная запись является выделенной учетной записью глобального администратора клиента. В Cloud Connector версии 2,0 и более поздней эта учетная запись может быть учетной записью Microsoft 365 или Office 365 с правами администратора Skype для бизнеса.
  
Если учетные данные учетной записи администратора меняются в Microsoft 365 или Office 365, также необходимо обновить локально кэшированные учетные данные в Cloud Connector, выполнив следующую команду администратора PowerShell на каждом развертываемом устройстве Cloud Connector:
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>Обновление пароля для сервера узла
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Этот раздел относится к Cloud Connector версии 2,0 и более поздних версий. 
  
Все учетные данные Cloud Connector хранятся в следующем файле: "%SystemDrive%\Programdata\Cloudconnector\credentials. \< CurrentUser \> . XML ". При изменении пароля на сервере узла необходимо обновить локально хранимые учетные данные.
  
Чтобы обновить локально хранимые учетные данные на устройстве Cloud Connector, используйте командлеты [Get – CcCredential](get-cccredential.md) и [Set – CcCredential](set-cccredential.md) , а затем выполните указанные ниже действия.
  
1. Выполните следующие команды, чтобы получить пароли, которые вам понадобятся позже: 
    
   - Get – CcCredential — AccountType DomainAdmin — Дисплайпассворд
    
   - Get – CcCredential — AccountType VMAdmin — Дисплайпассворд
    
   - Get – CcCredential — AccountType CceService — Дисплайпассворд
    
2. Измените пароль учетной записи на сервере узла.
    
3. Перезапустите сервер узла.
    
4. Удалите следующий файл: "%SystemDrive%\Programdata\Cloudconnector\credentials. \< CurrentUser \> . XML ".
    
5. Запустите консоль PowerShell от имени администратора, а затем выполните команду "Register – CcAppliance — Local", чтобы повторно ввести пароли, указанные в описании. Убедитесь, что вы ввели тот же пароль, который вы ввели перед развертыванием Cloud Connector.
    
По умолчанию для VmAdmin и DomainAdmin используется тот же пароль, что и в CceService. Если пароли DomainAdmin, VMAdmin и CceService, возвращаемые на шаге 1, отличаются, необходимо выполнить следующие действия:
  
1. Выполните командлет Set – CcCredential – AccountType DomainAdmin, как показано ниже.
    
1. При запросе учетных данных старой учетной записи введите учетные данные, которые использовались для пароля CceService.
    
2. При запросе учетных данных новой учетной записи введите пароль для пароля DomainAdmin, возвращенного на шаге 1.
    
2. Выполните командлет Set – CcCredential – AccountType VmAdmin, как показано ниже.
    
1. При запросе учетных данных старой учетной записи введите учетные данные, которые использовались для пароля CceService.
    
2. При запросе учетных данных новой учетной записи введите пароль для пароля VmAdmin, возвращенного на шаге 1. 
    
## <a name="update-the-password-for-the-cceservice-account"></a>Обновление пароля учетной записи CceService
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Этот раздел относится к Cloud Connector версии 2.0.1 и более поздних версий. 
  
Служба Cloud Connector выполняет службу управления Cloud Connector. Учетная запись CceService создается во время развертывания Cloud Connector Edition и хранится в следующих файлах: "%SystemDrive%\Programdata\Cloudconnector\credentials. \< CurrentUser \> . XML "и"%системдриве%\програмдата\клаудконнектор\кредентиалс.. CceService. XML ".
  
Чтобы все устройства могли получать доступ к общему ресурсу каталога сайтов, пароль для учетной записи CceService должен быть одинаковым на всех устройствах, развернутых на сайте. Учитывайте следующее:
  
- По умолчанию учетная запись CceService настроена как "срок действия пароля не ограничен". При обновлении пароля Корпорация Майкрософт рекомендует оставить эту конфигурацию.
    
- Вы должны обновить пароль во время непиковых периодов использования и из окон автоматических периодов обновления для BITS или обновлений Windows. При обновлении пароля необходимо выполнить сток и перезапустить устройство, что занимает некоторое время. Перезапуск устройства приведет к прерыванию операций автоматического обновления. 
    
- При изменении пароля учетной записи CceService необходимо указать все учетные данные и обновить их в локально сохраненном файле. 
    
Для каждого устройства, входящего в один сайт PSTN, необходимо указать следующее: 
  
1. Чтобы получить имена и пароли учетных записей, которые будут использоваться позже, выполните следующие команды:
    
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

2. Выполните командлет Enter – CcUpdate, чтобы очистить устройство и переместить его в режим ручного обслуживания.
    
3. Обновите пароль учетной записи CceService на сервере узла.
    
4. Перезапустите сервер узла.
    
5. Запустите командлет Restore – Кккредентиалс, чтобы повторно ввести пароли, следуя описанию. 
    
    Убедитесь, что вы ввели тот же пароль, который вы ввели перед развертыванием Cloud Connector, кроме учетной записи CceService. В поле Учетная запись CceService введите новый пароль. Убедитесь, что новый пароль для учетной записи CceService одинаков для всех устройств на сайте PSTN.
    
6. По умолчанию для VmAdmin и DomainAdmin используется тот же пароль, что и в CceService. Если пароли DomainAdmin, VMAdmin и CceService, возвращаемые на шаге 1, отличаются, необходимо выполнить следующие действия:
    
7. Выполните командлет Set – CcCredential – AccountType DomainAdmin, как показано ниже.
    
   - При запросе учетных данных старой учетной записи введите учетные данные, которые использовались для пароля CceService.
    
   - При запросе учетных данных новой учетной записи введите пароль для пароля DomainAdmin, возвращенного на шаге 1.
    
8. Выполните командлет Set – CcCredential – AccountType VmAdmin, как показано ниже.
    
   - При запросе учетных данных старой учетной записи введите учетные данные, которые использовались для пароля CceService.
    
   - При запросе учетных данных новой учетной записи введите пароль для пароля VmAdmin, возвращенного на шаге 1. 
    
9. Выполните командлет Exit – CcUpdate, чтобы переместить устройство из режима ручного обслуживания.
    
10. После выполнения этих действий для всех устройств на одном сайте PSTN удалите следующие файлы в корневом каталоге сайта:
    
    - кклоккфиле
    
    - \<Полное доменное имя внешнего SIP пула Site_ пограничного сервера\>
    
    - \<Полное доменное имя внешнего SIP пула Tenant_ пограничного сервера\>
    
    - \<Полное доменное имя внешнего SIP пула TenantConfigLock_ пограничного сервера\>
    
## <a name="add-a-new-sip-domain"></a>Добавление нового домена SIP
<a name="BKMK_UpdatePassword"> </a>

Чтобы добавить новый домен SIP (или несколько доменов SIP) к существующему развертыванию Cloud Connector, выполните следующие действия:
  
1. Убедитесь, что вы выполнили действия по обновлению домена в Microsoft 365 или Office 365, а также можете добавлять записи DNS. Для получения дополнительных сведений о настройке домена в Microsoft 365 или Office 365, ознакомьтесь со статьей [Добавление домена в microsoft 365 или office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
    
2. Обновите файл конфигурации Cloud Connector с помощью нового домена SIP или доменов.
    
3. Запросите новый внешний сертификат пограничного сервера с дополнительными именами SAN для каждого домена SIP, определенного в конфигурации Cloud Connector. 
    
4. Задайте путь к новому внешнему сертификату пограничного сервера следующим образом:
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Следуйте инструкциям, чтобы [изменить конфигурацию отдельного сайта](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) или [изменить конфигурацию нескольких сайтов](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).
    
## <a name="modify-the-primary-sip-domain"></a>Изменение основного домена SIP
<a name="BKMK_UpdatePassword"> </a>

Если необходимо изменить основной домен SIP в развертывании Cloud Connector, выполните следующие действия:
  
1. Убедитесь, что вы выполнили действия по обновлению домена в Microsoft 365 или Office 365, а также можете добавлять записи DNS. Для получения дополнительных сведений о настройке домена в Microsoft 365 или Office 365, ознакомьтесь со статьей [Добавление домена в microsoft 365 или office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
    
2. Обновите файл конфигурации Cloud Connector с помощью нового домена SIP.
    
3. Запросите новый внешний сертификат пограничного сервера с дополнительными именами SAN для каждого домена SIP, определенного в конфигурации Cloud Connector. 
    
4. Задайте путь к новому внешнему сертификату пограничного сервера следующим образом:
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Удалите регистрацию клиента для каждого устройства на сайте, выполнив следующий командлет в оболочке PowerShell в Cloud Connector:
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    Удалите регистрацию сайта для каждого сайта, выполнив следующий командлет в Skype для бизнеса Online PowerShell:
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    Удалите каждое устройство, выполнив следующий командлет в консоли администрирования PowerShell на облачном соединителе:
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     Зарегистрируйте каждое устройство, выполнив следующий командлет в консоли PowerShell администратора Cloud Connector:
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     Установите каждое устройство по одному, выполнив следующий командлет в оболочке PowerShell в Cloud Connector:
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>Замена внешнего сертификата пограничного сервера на новый
<a name="BKMK_UpdatePassword"> </a>

Когда вам потребуется заменить внешний пограничный сертификат на устройствах Cloud Connector, необходимо получить новый пограничный сертификат, подготовить PFX-файл, содержащий закрытый ключ и цепочку сертификатов, а затем выполнить следующие действия на каждом устройстве:
  
1. Перевести устройство в режим обслуживания с помощью командлета Enter – CcUpdate.
    
2. Выполните следующую команду. 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    Если пароль нового сертификата совпадает со старым, импорт будет успешным. Если пароль отличается, появится сообщение о том, что пароль неверный, а пароль необходимо сбросить, запустив командлет Register-CcAppliance с параметром-Local, а затем повторив шаг 2. 
    
4. Переведите устройство из режима обслуживания с помощью командлета Exit – CcUpdate.
    

