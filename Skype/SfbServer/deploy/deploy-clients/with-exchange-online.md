---
title: Развертывание Систем комнат Skype версии 2 в среде Exchange Online (гибридное)
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/18/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: В данном разделе приведены сведения о способах развертывания систем комнаты Скайп версии 2 с Exchange Online.
ms.openlocfilehash: f97b4a140a220440c18c5a3094af01299da9dddf
ms.sourcegitcommit: 6340d0050a51790e40b7ab8e4e89348251ba184f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2018
ms.locfileid: "19649614"
---
# <a name="deploy-skype-room-systems-v2-with-exchange-online-hybrid"></a>Развертывание Систем комнат Skype версии 2 в среде Exchange Online (гибридное)
 
В данном разделе приведены сведения о способах развертывания систем комнаты Скайп версии 2 с Exchange Online.
  
Если в организации имеется набор служб, с некоторыми размещенных в локальную организацию и некоторые размещаются в сети, конфигурации будут зависеть от размещение каждой службы. В этом разделе рассматривается гибридного развертывания в системах комнаты Скайп версии 2 с сервером Exchange, размещенных в Интернете. Из-за слишком большом числе различные варианты в этом типе развертывания, не поддерживается представлены подробные инструкции по их все. Процесс будет работать для многих конфигураций. Если процесс не подходит для вашей установки, мы рекомендуем использовать Windows PowerShell (содержатся в приложении: PowerShell) для достижения же конечный результат, как описано ниже, а также другие параметры развертывания. Затем следует использовать предоставленный сценарий Windows PowerShell для проверки установки версии 2 Скайп комнаты систем. (См. сценарий проверки учетной записи).
  
## <a name="deploy-skype-room-systems-v2-with-exchange-online"></a>Развертывание Систем комнат Skype версии 2 в среде Exchange Online

Перед развертыванием системы комнаты Скайп версии 2 с Exchange Online убедитесь, что удовлетворены требования. Для получения дополнительных сведений см [систем комнаты Скайп версии 2](../../plan-your-deployment/clients-and-devices/requirements.md).
  
Развертывание системы комнаты Скайп версии 2 с Exchange Online, выполните следующие действия. Убедитесь в том, что у вас есть необходимые разрешения для выполнения соответствующих командлетов. 
  
### <a name="create-an-account-and-set-exchange-properties"></a>Создание учетной записи и настройка свойств Exchange

1. Для запуска удаленного сеанса Windows PowerShell на ПК и подключитесь к Exchange Online, следующим образом:
    
```
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
```

2. После установки сеанса будет либо создать новый почтовый ящик и включение как RoomMailboxAccount или изменение параметров для существующего почтового ящика помещения. Это позволит учетной записи для проверки подлинности в системах комнаты Скайп версии 2.
    
   Изменение существующего почтового ящика ресурса:
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Если вы создаете новый почтовый ящик ресурса:
    
   ```
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Чтобы улучшить работу в собрание, то необходимо для задания свойств Exchange учетной записи пользователя следующим образом:
    
   ```
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

    
4. Для применения некоторых настроек учетной записи потребуется подключиться к Azure AD. Для подключения можно использовать следующий командлет.
    
   ```
   Connect-MsolService -Credential $cred
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>Добавление адреса электронной почты для локальной учетной записи домена

1. Средства **Active Directory — пользователи и компьютеры AD** щелкните правой кнопкой мыши папку или подразделение, что системы комнаты Скайп v2 учетные записи будут создаваться в, нажмите кнопку **Создать**и выберите пункт **пользователь**.
    
2. Введите отображаемое имя из предыдущего командлета в поле **Полное имя**, а затем псевдоним в поле **Имя входа пользователя**. Нажмите кнопку **Далее**.


3. Введите пароль учетной записи. Подтвердите пароль. Убедитесь, что выбран только параметр **Срок действия пароля не ограничен**.
    
    > [!NOTE]
    > Выбор **Срок действия пароля не ограничен** является обязательным требованием для Скайп для Business Server 2015 на систем комнаты Скайп версии 2. В некоторых случаях пароли с неограниченным сроком действия могут быть запрещены правилами домена. Если Да, необходимо создать исключение для каждой учетной записи пользователя систем комнаты Скайп версии 2.
  
4. Чтобы создать учетную запись, нажмите кнопку **Готово**.
    
5. После создания учетной записи выполните синхронизацию каталогов. По завершении этого процесса перейдите на страницу пользователей и убедитесь, что две созданные на предыдущих шагах учетные записи объединены.
    
### <a name="assign-an-office-365-license"></a>Назначение лицензии Office 365

1. Учетная запись должна иметь действительной лицензии Office 365, чтобы убедиться, что Скайп для Business Server 2015 и Exchange будут работать. При наличии лицензии вам необходимо назначить учетной записи устройства место использования, которое определяет, какие номера SKU лицензий будут доступны вашей учетной записи.
    
2. Затем используйте Get-MsolAccountSku для получения списка доступных номеров SKU для клиента Office 365.
    
3. После этого вы можете добавить лицензию с помощью командлета Set-MsolUserLicense. В этом случае будет отображаться код SKU $strLicense (например, contoso:STANDARDPACK).
    
   ```
   Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ```


### <a name="enable-the-user-account-with-skype-for-business-server-2015"></a>Включение учетной записи пользователя со Skype для бизнеса Server 2015

1. Создайте удаленного сеанса Windows PowerShell с ПК, как показано ниже:
    
    ```
    Import-Module LyncOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. Включение учетной записи системы комнаты Скайп версии 2 для Скайп для Business Server 2015, выполните следующую команду.
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    Если вы не уверены, используйте для параметра RegistrarPool в вашей среде, можно получить значение из существующего Скайп для пользователя Business Server 2015, с помощью этой команды
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-2015-license-to-your-skype-room-systems-v2-account"></a>Назначение лицензии Skype для бизнеса Server 2015 своей учетной записи Систем комнат Skype версии 2

1. Выполните вход в качестве администратора клиента, откройте административного портала Office 365 и щелкните приложения администрирования.
    
2. Выберите **Пользователи и группы**, после чего щелкните **Добавление пользователей, сброс паролей и другие действия**.
    
3. Щелкните учетную запись комнаты систем Скайп версии 2 и нажмите кнопку перо значок, чтобы изменить сведения об учетной записи.
    
4. Щелкните **Лицензии**.
    
5. В разделе **Назначение лицензий** выберите Skype для бизнеса (план 2) или Skype для бизнеса (план 3), в зависимости от требований к лицензированию и Корпоративной голосовой связи. Вам потребуется использовать лицензии планирование 3, если вы хотите использовать корпоративной голосовой связи на вашей версии 2 Скайп комнаты систем.
    
6. Также можно отправить электронное письмо пользователю с помощью параметров аудиоконференции, выбрав на странице свойств аудиоконференции для пользователя параметр **Отправить информацию о конференции по электронной почте**.
    
Для проверки можно использовать любой Скайп для бизнеса клиента для входа в эту учетную запись.
  
## <a name="see-also"></a>См. также

#### 

[Планирование для помещения Скайп систем версии 2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Развертывание Скайп комнаты систем версии 2](room-systems-v2.md)
  
[Настройка консоли систем комнаты Скайп версии 2](console.md)
  
[Управление Скайп комнаты систем версии 2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

