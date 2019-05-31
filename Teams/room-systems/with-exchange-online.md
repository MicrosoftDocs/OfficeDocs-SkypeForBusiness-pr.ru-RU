---
title: Развертывание комнаты Microsoft Teams с Exchange Online
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Сведения о том, как развертывать комнаты Microsoft Teams с помощью Exchange Online, читайте в этой статье.
ms.openlocfilehash: 86290bdc8b198af5e4d41b8b90bd588ade5494a5
ms.sourcegitcommit: e487637fc122727b41b37961f208ddc0d20a3fce
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591706"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Развертывание комнаты Microsoft Teams с Exchange Online

В этой статье приведены сведения о том, как развертывать комнаты Microsoft Teams с помощью Exchange Online и Skype для бизнеса Server в локальной среде.
  
Если в вашей организации есть смесь служб, а некоторые размещены в локальной сети, а некоторые — в Интернете, ваша конфигурация будет зависеть от того, где размещена каждая служба. В этой статье рассказывается о гибридных развертываниях комнат Microsoft Teams с Exchange, размещенных в Интернете. Так как в этом типе развертывания существует множество различных вариантов, невозможно предоставить подробные инструкции для всех. Для многих конфигураций будет работать следующий процесс. Если вы не можете выполнить процесс настройки, мы рекомендуем использовать Windows PowerShell, чтобы получить тот же самый конечный результат, который вы описывали здесь, и для других вариантов развертывания.

Самый простой способ настроить учетные записи пользователей — настроить их с помощью удаленной оболочки Windows PowerShell. Корпорация Майкрософт предоставляет [скиперумпровисионингскрипт. ps1](https://go.microsoft.com/fwlink/?linkid=870105), сценарий, который поможет создать новые учетные записи пользователей, или проверить имеющиеся учетные записи ресурсов, чтобы их можно было превратить в совместимые учетные записи Microsoft Teams. Если вы предпочитаете, выполните указанные ниже действия, чтобы настроить учетные записи, которые будут использоваться на устройстве комнат Microsoft Teams.

## <a name="requirements"></a>Требования

Перед развертыванием комнат Microsoft Teams в Exchange Online убедитесь, что вы удовлетворены требованиями. Дополнительные сведения можно найти в разделе [требования к комнатам Microsoft Teams](requirements.md).
  
Чтобы развернуть комнаты Microsoft Teams в Exchange Online, выполните указанные ниже действия. Убедитесь в том, что у вас есть необходимые разрешения для выполнения соответствующих командлетов.
  
### <a name="create-an-account-and-set-exchange-properties"></a>Создание учетной записи и настройка свойств Exchange

1. Запустите удаленный сеанс Windows PowerShell на компьютере и подключитесь к Exchange Online, как описано ниже.

``` Powershell
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
```

2. После установления сеанса вы сможете создать новый почтовый ящик и включить его в качестве Руммаилбоксаккаунт или изменить параметры существующего почтового ящика помещения. Это позволит вашей учетной записи проходить проверку подлинности в комнатах Microsoft Teams.

   Изменение существующего почтового ящика ресурса:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Если вы создаете новый почтовый ящик ресурса, сделайте следующее:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Чтобы улучшить взаимодействие с собраниями, необходимо настроить свойства Exchange для учетной записи пользователя следующим образом:

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```



### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>Добавление адреса электронной почты для локальной учетной записи домена

1. В средстве **AD Active Directory — пользователи и компьютеры** , щелкните правой кнопкой мыши контейнер или подразделение, в котором будут создаваться учетные записи Microsoft Teams, а затем нажмите кнопку " **создать**", а затем выберите пункт " **пользователь**".
2. Введите отображаемое имя (-Identity) из предыдущего командлета (Set-Mailbox или New-Mailbox) в поле **полное имя** и псевдоним в поле **имя пользователя для входа** . Нажмите кнопку **Далее**.
3. Введите пароль учетной записи. Подтвердите пароль. Убедитесь, что выбран только параметр **Срок действия пароля не ограничен**.

    > [!NOTE]
    > Выбор **срока действия пароля неограничен** — требование для сервера Skype для бизнеса в комнатах Microsoft Teams. В некоторых случаях пароли с неограниченным сроком действия могут быть запрещены правилами домена. Если да, вам потребуется создать исключение для каждой учетной записи пользователя комнат Microsoft Teams.
  
4. Чтобы создать учетную запись, нажмите кнопку **Готово**.
5. Создав учетную запись, выполните синхронизацию службы каталогов. Это можно сделать с помощью [Set-мсолдирсинкконфигуратион](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) в PowerShell. После этого перейдите на страницу "Пользователи" и убедитесь в том, что две учетные записи, созданные в предыдущих шагах, объединены.

### <a name="assign-an-office-365-license"></a>Назначение лицензии Office 365

1. Сначала подключитесь к Azure AD, чтобы применить некоторые параметры учетной записи. Для подключения можно использовать следующий командлет. Подробнее об Active Directory можно узнать в [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) не поддерживается. 

  ``` PowerShell
 Connect-MsolService -Credential $cred
  ```
<!--   ``` Powershell
   Connect-AzureAD -Credential $cred
   ``` -->

2. Для обеспечения работоспособности Exchange и Skype для бизнеса сервер учетной записи пользователя должен быть действительной лицензией Office 365. При наличии лицензии вам необходимо назначить учетной записи устройства место использования, которое определяет, какие номера SKU лицензий будут доступны вашей учетной записи. Назначение будет проводиться на следующем этапе.
3. Затем используйте`Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> Получение списка доступных SKU для клиента Office 365.
4. После того как вы выйдете список SKU, вы можете добавить лицензию с помощью`Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> Командлет. В этом случае будет отображаться код SKU $strLicense (например, contoso:STANDARDPACK). 

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

### <a name="enable-the-user-account-with-skype-for-business-server"></a>Включение учетной записи пользователя в Skype для бизнеса Server

1. Создайте удаленный сеанс Windows PowerShell на компьютере, выполнив указанные ниже действия.

    ``` Powershell
    Import-Module SkypeOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. Чтобы включить учетные записи Microsoft Teams для Skype для бизнеса Server, выполните следующую команду:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    Если вы не знаете, какое значение использовать для параметра Регистрарпул в вашей среде, вы можете получить значение из существующего пользователя Skype для бизнеса Server с помощью этой команды.

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a>Назначение лицензии Skype для бизнеса Server для учетной записи комнат Microsoft Teams

1. Войдите в систему как администратор клиента, откройте административный портал Office 365 и щелкните Приложение администратор.
2. Выберите **Пользователи и группы**, после чего щелкните **Добавление пользователей, сброс паролей и другие действия**.
3. Щелкните учетную запись комнаты Microsoft Teams, а затем щелкните значок пера, чтобы изменить данные учетной записи.
4. Щелкните **Лицензии**.
5. В разделе **Назначение лицензий** выберите Skype для бизнеса (план 2) или Skype для бизнеса (план 3), в зависимости от требований к лицензированию и Корпоративной голосовой связи. Если вы хотите использовать корпоративную голосовую связь в комнатах Microsoft Teams, вам придется использовать лицензию на план 3.
6. Нажмите кнопку **Сохранить**.

Для проверки подлинности вы можете войти в эту учетную запись с помощью любого клиента Skype для бизнеса.
  
## <a name="see-also"></a>См. также

[Настройка учетных записей для комнат Microsoft Teams](room-systems-v2-configure-accounts.md)

[Планирование комнат Microsoft Teams](skype-room-systems-v2-0.md)
  
[Развертывание комнат Microsoft Teams](room-systems-v2.md)
  
[Настройка консоли Microsoft Teams](console.md)
  
[Управление приложением "Комнаты Microsoft Teams"](skype-room-systems-v2.md)
