---
title: Развертывание групп Майкрософт комнат с Exchange Online
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: В данном разделе приведены сведения о развертывании Microsoft группами комнат с Exchange Online.
ms.openlocfilehash: 55b62656d5ddf7fdc7a1139f1c4eaf5c055437fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33916271"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Развертывание групп Майкрософт комнат с Exchange Online

В данном разделе приведены сведения о том, как развернуть комнатам группы Microsoft Exchange Online и Скайп для Business Server в локальной.
  
Если в организации имеется набор служб, с некоторыми размещенных в локальную организацию и некоторые размещаются в сети, конфигурации будут зависеть от размещение каждой службы. В этом разделе описываются гибридные развертывания для комнат группами Майкрософт с сервером Exchange, размещенных в Интернете. Из-за слишком большом числе различные варианты в этом типе развертывания, не поддерживается представлены подробные инструкции по их все. Процесс будет работать для многих конфигураций. Если процесс не подходит для вашей установки, мы рекомендуем использовать Windows PowerShell для достижения же конечный результат, как описано ниже, а также другие параметры развертывания.

Настройка учетных записей пользователей проще всего настроить их с помощью удаленной оболочки Windows PowerShell. Корпорация Майкрософт предоставляет [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), сценарий, который поможет создать новые учетные записи пользователей, или validate существующие учетные записи ресурсов, что у вас есть помогающих перевод их в совместимые учетных записей пользователей комнат группами Майкрософт. При необходимости можно выполните следующие действия, чтобы настроить учетные записи, используемые устройства комнат группами Майкрософт.

## <a name="requirements"></a>Требования

Перед развертыванием комнат группами Майкрософт с Exchange Online убедитесь, что удовлетворены требования. Для получения дополнительных сведений в разделе [requirements комнат группами Майкрософт](requirements.md).
  
Чтобы развернуть комнат группами Майкрософт с Exchange Online, выполните следующие действия. Убедитесь в том, что у вас есть необходимые разрешения для выполнения соответствующих командлетов.
  
### <a name="create-an-account-and-set-exchange-properties"></a>Создание учетной записи и настройка свойств Exchange

1. Для запуска удаленного сеанса Windows PowerShell на ПК и подключитесь к Exchange Online, следующим образом:

``` Powershell
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
```

2. После установки сеанса будет либо создать новый почтовый ящик и включение как RoomMailboxAccount или изменение параметров для существующего почтового ящика помещения. Это позволит учетной записи для проверки подлинности в комнатах группами Майкрософт.

   Изменение существующего почтового ящика ресурса:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Если вы создаете новый почтовый ящик ресурса:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Чтобы улучшить работу в собрание, то необходимо для задания свойств Exchange учетной записи пользователя следующим образом:

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```



### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>Добавление адреса электронной почты для локальной учетной записи домена

1. Средства **Active Directory — пользователи и компьютеры AD** щелкните правой кнопкой мыши контейнер или подразделение, что вашей комнат группами Майкрософт, учетные записи будут создаваться в, нажмите кнопку **Создать**и выберите пункт **пользователь**.
2. Введите отображаемое имя (-Identity) из предыдущего командлета (Set-Mailbox или New-Mailbox) в поле **полное имя** и адрес в поле **имя входа пользователя** . Нажмите кнопку **Далее**.
3. Введите пароль учетной записи. Подтвердите пароль. Убедитесь, что выбран только параметр **Срок действия пароля не ограничен**.

    > [!NOTE]
    > Выбор **Срок действия пароля не ограничен** является обязательным требованием для Скайп для Business Server на комнат группами Майкрософт. В некоторых случаях пароли с неограниченным сроком действия могут быть запрещены правилами домена. Если Да, необходимо создать исключение для каждой учетной записи пользователя комнат группами Майкрософт.
  
4. Чтобы создать учетную запись, нажмите кнопку **Готово**.
5. После создания учетной записи выполните синхронизацию каталогов. По завершении этого процесса перейдите на страницу пользователей и убедитесь, что две созданные на предыдущих шагах учетные записи объединены.

### <a name="assign-an-office-365-license"></a>Назначение лицензии Office 365

1. Во-первых подключение к Azure AD для применения некоторые параметры учетной записи. Для подключения можно использовать следующий командлет. Для получения дополнительных сведений об Active Directory просмотрите [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) не поддерживается. 

  ``` PowerShell
 Connect-MsolService -Credential $cred
  ```
<!--   ``` Powershell
   Connect-AzureAD -Credential $cred
   ``` -->

2. Учетная запись должна иметь действительной лицензии Office 365, чтобы убедиться, что Скайп для Business Server и Exchange будут работать. При наличии лицензии вам необходимо назначить учетной записи устройства место использования, которое определяет, какие номера SKU лицензий будут доступны вашей учетной записи. На следующем этапе будет внести назначения.
3. Затем используйте`Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> Для получения списка доступных номеров SKU для клиента Office 365.
4. После список масштабирование номера SKU, можно добавить лицензии с помощью`Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> командлет. В этом случае будет отображаться код SKU $strLicense (например, contoso:STANDARDPACK). 

  ```
    Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```
<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a>Включение учетной записи пользователя с помощью Скайп для Business Server

1. Создайте удаленного сеанса Windows PowerShell с ПК, как показано ниже:

    ``` Powershell
    Import-Module SkypeOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. Включение учетной записи Microsoft группами комнат для Скайп для Business Server, выполните следующую команду.

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    Если вы не уверены, используйте для параметра RegistrarPool в вашей среде, можно получить значение из существующего Скайп для пользователя Business Server, с помощью этой команды

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a>Назначение Скайп для лицензий Business Server свою учетную запись Microsoft группами комнат

1. Выполните вход в качестве администратора клиента, откройте административного портала Office 365 и щелкните приложения администрирования.
2. Выберите **Пользователи и группы**, после чего щелкните **Добавление пользователей, сброс паролей и другие действия**.
3. Щелкните учетную запись Microsoft группами комнат и нажмите кнопку перо значок, чтобы изменить сведения об учетной записи.
4. Щелкните **Лицензии**.
5. В разделе **Назначение лицензий** выберите Skype для бизнеса (план 2) или Skype для бизнеса (план 3), в зависимости от требований к лицензированию и Корпоративной голосовой связи. Вам потребуется использовать планирование 3 лицензии, если вы хотите использовать корпоративной голосовой связи на комнат группы Microsoft.
6. Нажмите кнопку **Сохранить**.

Для проверки можно использовать любой Скайп для бизнеса клиента для входа в эту учетную запись.
  
## <a name="see-also"></a>См. также

[Настройка учетных записей для комнат группами Майкрософт](room-systems-v2-configure-accounts.md)

[Планирование для групп Майкрософт комнат](skype-room-systems-v2-0.md)
  
[Развертывание групп Майкрософт комнат](room-systems-v2.md)
  
[Настройка консоли комнат группами Майкрософт](console.md)
  
[Управление приложением "Комнаты Microsoft Teams"](skype-room-systems-v2.md)
