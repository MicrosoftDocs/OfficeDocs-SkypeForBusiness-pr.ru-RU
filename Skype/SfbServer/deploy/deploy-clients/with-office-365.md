---
title: Развертывание Систем комнат Skype версии 2 в среде Office 365
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: В данном разделе приведены сведения о способах развертывания систем комнаты Скайп версии 2 с Office 365.
ms.openlocfilehash: b05afbf973e814c5adf7b8a8490aefa0cbb04886
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2-with-office-365"></a>Развертывание Систем комнат Skype версии 2 в среде Office 365 
 
В данном разделе приведены сведения о способах развертывания систем комнаты Скайп версии 2 с Office 365.
  
В этом разделе описывается добавление учетной записи устройства для систем комнаты Скайп v2 при наличии online развертывания Office 365.
  
## <a name="deploy-skype-room-systems-v2-with-office-365"></a>Развертывание Систем комнат Skype версии 2 в среде Office 365 

Перед развертыванием системы комнаты Скайп версии 2 с Office 365, убедитесь, что удовлетворены требования. Для получения дополнительных сведений см [систем комнаты Скайп версии 2](../../plan-your-deployment/clients-and-devices/requirements.md).
  
Чтобы включить Скайп для бизнеса, необходимо иметь следующее:
  
- Скайп для бизнеса Online (план 2) или более поздней версии в плане Office 365. План должен поддерживать функции конференц-связи.
    
- Если вам требуется корпоративной голосовой связи (телефонии PSTN) с помощью службы телефонии для систем комнаты Скайп версии 2 необходимо Скайп для бизнеса Online (план 3).
    
- Клиент пользователи должны иметь почтовые ящики Exchange.
    
- Вашей системы комнаты Скайп версии 2 для учетной записи требуются Скайп для бизнеса Online (план 2) или Скайп для бизнеса в Интернет (план 3) лицензии, но не требует лицензии Exchange Online.
    
### <a name="add-a-device-account"></a>Добавление учетной записи устройства

1. Для запуска удаленного сеанса Windows PowerShell на ПК и подключитесь к Exchange. Убедитесь, что у вас есть необходимые разрешения для выполнения соответствующих командлетов. Ниже приведен ряд примеров командлетов, которые можно использовать и изменять в своей среде.
    
   ```
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential 
   $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```

2. После установки сеанса будет либо создать новый почтовый ящик и включение как RoomMailboxAccount или изменение параметров для существующего почтового ящика помещения. Это позволит учетной записи для проверки подлинности системы комнаты Скайп версии 2.
    
  Изменение существующего почтового ящика ресурса:
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

  Если вы создаете новый почтовый ящик ресурса:
    
   ```
   New-Mailbox -MicrosoftOnlineServicesID PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 
-Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword
 (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Чтобы оптимизировать интерфейс собрания, можно настроить различные свойства Exchange для учетной записи устройства. Описание необходимых настроек приводится в разделе "Свойства Exchange".
    
   ```
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false
   -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"

   ```

4. Для применения некоторых настроек учетной записи потребуется подключиться к Azure Active Directory. Чтобы подключиться к Azure AD, выполните следующий командлет.
    
   ```
   Connect-MsolService -Credential $cred
   ```

5. 	Чтобы использовать пароль с неограниченным сроком действия, выполните командлет Set-MsolUser с параметром PasswordNeverExpires.   
    
   ```
   Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
   ```

   Вы также можете задать номер телефона для комнаты следующим образом.
    
   ```
   Set-MsolUser -UniversalPrincipalName <upn> -PhoneNumber <phone number>
   ```

6. Учетная запись устройства должна быть действительной лицензии Office 365 или Exchange и Скайп для бизнеса не будут работать. При наличии лицензии вам необходимо назначить учетной записи устройства место использования, которое определяет, какие номера SKU лицензий будут доступны вашей учетной записи. Get-MsolAccountSku можно использовать для получения списка доступных номеров SKU для клиента Office 365 следующим образом:
    
   ```
   Get-MsolAccountSku
   ```

   Далее можно добавить лицензию с помощью командлета Set-MsolUserLicense. В этом случае будет отображаться код SKU $strLicense (например, contoso:STANDARDPACK).
    
   ```
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```

7. Затем необходимо включить запись устройства с Скайп для бизнеса. Убедитесь, что в вашей среде соответствует требованиям, определенным в [системах комнаты Скайп требования к версии 2](../../plan-your-deployment/clients-and-devices/requirements.md).
    
   Для запуска удаленного сеанса Windows PowerShell следующим образом (не забудьте установить Скайп для компонентов Business Online PowerShell):
    
   ```
   Import-Module LyncOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   Затем включите свою учетную запись комнаты систем Скайп версии 2 для Скайп для Business Server, выполнив следующий командлет:
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   Получите сведения о RegistrarPool из учетной записи пользователя, программа установки, как показано в следующем примере:
    
    ```
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > Новые учетные записи пользователей не могут быть созданы на тот же самый пул регистратора, как существующие учетные записи пользователей в клиентов. Команды выше не позволит ошибок в учетной записи программы установки из-за этой ситуации. 
  
После выполнения предыдущего действия, чтобы включить учетную запись комнаты систем Скайп версии 2 в Скайп для бизнеса в Интернет, им необходимо назначить лицензию на устройство систем комнаты Скайп версии 2. Использование портала администрирования Office 365, назначьте либо Скайп для бизнеса Online (план 2) или Скайп для бизнеса в Интернет (план 3) лицензии на устройство.
  
### <a name="assign-a-license-to-your-account"></a>Назначение лицензии учетной записи

1. Входа в систему как администратор клиента откройте административного портала Office 365 и щелкните на приложение администрирования.
    
2. Выберите **Пользователи и группы**, после чего щелкните **Добавление пользователей, сброс паролей и другие действия**.
    
3. Выберите учетную запись версии 2 Скайп комнаты систем и щелкните или нажмите значок перо, который означает, что изменение.
    
4. Щелкните **Лицензии**.
    
5. В разделе **Назначение лицензий** необходимо выбрать Скайп для бизнеса Online (план 2) или Скайп для бизнеса в Интернет (план 3), в зависимости от вашей лицензирования и очевидна с точки зрения применения какого корпоративной голосовой связи. Вам потребуется использовать планирование 3 лицензии, если вы хотите использовать облачных УАТС на систем комнаты Скайп версии 2. Облачная УАТС потребуется как минимум для подключения к голосовому каналу. Затем настройте гибридную голосовую связь или звонки по ТСОП в соответствии со способом связи с ТСОП.
    
6. Чтобы завершить задачу, нажмите кнопку **Сохранить**.
    
## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a>Пример: Комнаты учетной записи программы установки в Exchange Online и Скайп для бизнеса в Интернет

```
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com
 -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true
 -RoomMailboxPassword (ConvertTo-SecureString -String "" -AsPlainText -Force)
 
Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept 
-AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments 
$false -DeleteSubject $false -RemovePrivateProperty $false
 
Set-CalendarProcessing -Identity rigel1 -AddAdditionalResponse $true 
-AdditionalResponse "This is a Rigel room!"
 
Set-MsolUser -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
 
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
 
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress

```

> [!NOTE]
> Будут добавлены CloudPBX и PSTNCallingDomesticAndInternational. Кроме того, вам потребуется назначить номер телефона с помощью интерфейса администрирования. 
  
## <a name="see-also"></a>См. также

#### 

[Планирование для помещения Скайп систем версии 2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Развертывание Скайп комнаты систем версии 2](room-systems-v2.md)
  
[Настройка консоли систем комнаты Скайп версии 2](console.md)
  
[Управление Скайп комнаты систем версии 2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

