---
title: Развертывание комнаты Microsoft Teams с Office 365
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Сведения о том, как развертывать комнаты Microsoft Teams с помощью Office 365, читайте в этой статье.
ms.openlocfilehash: 8e41b06b8f5cf76a45fd09f4b8820fb2fcaaa6d5
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775034"
---
# <a name="deploy-microsoft-teams-rooms-with-office-365"></a>Развертывание комнаты Microsoft Teams с Office 365

В этой статье приведены сведения о том, как развертывать комнаты Microsoft Teams в Office 365, где Microsoft Teams или Skype для бизнеса и Exchange находятся в сети.

Самый простой способ настроить учетные записи пользователей — настроить их с помощью удаленной оболочки Windows PowerShell. Корпорация Майкрософт предоставляет [скиперумпровисионингскрипт. ps1](https://go.microsoft.com/fwlink/?linkid=870105), сценарий, который поможет создать новые учетные записи пользователей, или проверить имеющиеся учетные записи ресурсов, чтобы их можно было превратить в совместимые учетные записи Microsoft Teams. Если вы предпочитаете, выполните указанные ниже действия, чтобы настроить учетные записи, которые будут использоваться на устройстве комнат Microsoft Teams.

## <a name="requirements"></a>Требования

Перед развертыванием комнат Microsoft Teams с помощью Office 365 убедитесь, что вы удовлетворены требованиями. Дополнительные сведения можно найти в разделе [требования к комнатам Microsoft Teams](requirements.md).

Чтобы включить Skype для бизнеса, необходимо выполнить указанные ниже действия.

- Skype для бизнеса Online (план 2 или план на основе предприятия) или более позднюю версию в плане Office 365. План должен разрешить возможности конференц-связи с телефонным подключением.

- Если вам понадобятся возможности телефонного подключения к собранию, вам потребуется голосовой Конференц-связь и лицензия на телефонную систему.  Если вам нужны возможности исходящих звонков с собрания, вам понадобится план внутренних или внутренних и международных звонков.

- Ваши пользователи клиента должны иметь почтовые ящики Exchange.

- Для учетной записи Microsoft Team комнат требуется лицензия Skype для бизнеса Online (план 2), но для нее не требуется лицензия на Exchange Online. Дополнительные сведения см. в разделе [лицензии на комнаты Microsoft Teams](skype-room-systems-v2.md) .

Подробнее о тарифах Skype для бизнеса Online можно найти в [описании службы Skype для бизнеса Online](https://technet.microsoft.com/library/jj822172.aspx).

### <a name="add-a-device-account"></a>Добавление учетной записи устройства

1. Подключитесь к Exchange Online PowerShell. Инструкции можно найти [в разделе Подключение к Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

2. В Exchange Online PowerShell создайте новый почтовый ящик помещения или измените существующий почтовый ящик помещения. По умолчанию для почтовых ящиков в комнате не предусмотрены связанные учетные записи, поэтому при создании или изменении почтового ящика помещения, позволяющего проверять подлинность с помощью системы комнат Skype v2, необходимо добавить учетную запись.

   - Чтобы создать новый почтовый ящик комнаты, используйте следующий синтаксис:

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     В этом примере создается новый почтовый ящик комнаты со следующими параметрами:

     - Имя: Project-Рижел-01

     - Alias (псевдоним): ProjectRigel01

     - Учетная запись: ProjectRigel01@contoso.onmicrosoft.com

     - Пароль учетной записи: P @ $ $W 0rd5959

     ``` PowerShell
     New-Mailbox -Name "Project-Rigel-01" -Alias ProjectRigel01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID ProjectRigel01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Чтобы изменить существующий почтовый ящик помещения, используйте следующий синтаксис:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     В этом примере включается учетная запись для почтового ящика помещения, имеющего значение псевдонима ProjectRigel02, и пароль для 9898P @ $ $W 0rd. Обратите внимание, что учетная запись будет ProjectRigel02@contoso.onmicrosoft.com из-за существующего значения псевдонима.

     ``` PowerShell
     Set-Mailbox -Identity ProjectRigel02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   Подробные сведения о синтаксисе и параметрах можно найти в разделе [Создание почтового ящика](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) и [Настройка почтового ящика](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).


3. В Exchange Online PowerShell настройте следующие параметры в почтовом ящике комнаты, чтобы улучшить процесс собрания:

   - Аутоматепроцессинг: с помощью автопринятия (организаторов собраний) получайте решение о резервировании комнаты непосредственно без вмешательства человека: бесплатное = принять; занято = отклонить.)

   - Аддорганизертосубжект: $false (Организатор собрания не добавляется в тему приглашения на собрание.)

   - Делетекомментс: $false (Храните текст в тексте сообщения для входящих приглашений на собрания.)

   - Делетесубжект: $false (сохранить тему приглашений на входящие собрания).

   - Ремовеприватепроперти: $false (гарантируется, что частный флаг, отправленный организатором собрания в исходном приглашении на собрание, будет установлен.)

   - Аддаддитионалреспонсе: $true (текст, указанный в параметре Аддитионалреспонсе, добавляется в приглашения на собрание.)

   - Аддитионалреспонсе: "это комната для собраний Skype!" (Дополнительный текст, добавляемый в приглашение на собрание.)

   Этот пример настраивает эти параметры в почтовом ящике комнаты с именем Project-Рижел-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Подробные сведения о синтаксисе и параметрах можно найти в разделе [Set-календарпроцессинг](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).

4. Подключитесь к MS Online PowerShell, чтобы настроить параметры Active Directory, `Connect-MsolService -Credential $cred` запустив командлет PowerShell.   Подробнее об Active Directory можно узнать в [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) не поддерживается. 

5. Если вы не хотите ограничивать срок действия пароля, используйте следующий синтаксис:

    ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
    ```
<!--
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   В этом примере в качестве пароля для учетной записи ProjectRigel01@contoso.onmicrosoft.com никогда не задается срок действия.

  ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName ProjectRigel01@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   Вы также можете задать номер телефона для учетной записи, выполнив следующую команду:

  ``` PowerShell
    Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. Учетная запись устройства должна иметь действительную лицензию на Office 365, либо Exchange и Microsoft Teams или Skype для бизнеса не будут работать. При наличии лицензии вам необходимо назначить учетной записи устройства место использования, которое определяет, какие номера SKU лицензий будут доступны вашей учетной записи. Вы можете использовать`Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> чтобы получить список доступных SKU для клиента Office 365, выполните указанные ниже действия.

  ``` Powershell
  Get-MsolAccountSku
  ```
<!--
   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   Затем вы можете добавить лицензию с помощью`Set-MsolUserLicense` <!--Set-AzureADUserLicense --> Командлет. В этом случае будет отображаться код SKU $strLicense (например, contoso:STANDARDPACK).

  ``` PowerShell
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
  ``` 
<!-- 
   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```   -->

   Подробные инструкции приведены в разделе [Назначение лицензий учетным записям пользователей с помощью Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).

7. Затем вам нужно включить учетную запись устройства в Skype для бизнеса. Убедитесь, что ваша среда соответствует требованиям, определенным в [требованиях к комнатам Microsoft Teams](requirements.md).

   Запустите удаленный [сеанс Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) следующим образом (не забудьте [установить компоненты PowerShell для Skype для бизнеса Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   Затем включите на сервер Skype для бизнеса учетную запись Microsoft Teams, выполнив следующий командлет:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   Получите сведения о Регистрарпул из новой учетной записи пользователя, как показано в следующем примере:

    ``` Powershell
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > Новые учетные записи пользователей могут не создаваться в том же пуле регистраторов, что и существующие учетные записи пользователей в клиенте. Приведенная выше команда будет препятствовать ошибкам в настройке учетной записи из-за этой ситуации.

После выполнения описанных выше действий для включения учетной записи Microsoft Teams в Microsoft Teams или Skype для бизнеса Online необходимо назначить лицензию для устройства Microsoft Teams. С помощью административного портала Office 365 Назначьте устройству Skype для бизнеса Online (план 2) или лицензию Skype для бизнеса Online (план 3).

### <a name="assign-a-license-to-your-account"></a>Назначение лицензии учетной записи

1. Войдите в систему как администратор клиента, откройте административный портал Office 365 и щелкните Приложение администратор.

2. Выберите **Пользователи и группы**, после чего щелкните **Добавление пользователей, сброс паролей и другие действия**.

3. Выберите учетную запись комнаты Microsoft Teams, а затем щелкните значок пера, который означает редактирование.

4. Щелкните **Лицензии**.

5. В разделе **Назначение лицензий** вам нужно выбрать Skype для бизнеса Online (план 2) или Skype для бизнеса Online (план 3), в зависимости от вашего лицензирования и от того, что вы решили в условиях потребности в корпоративной голосовой связи. Если вы хотите использовать облачную УАТС в комнатах Microsoft Teams, вам придется использовать лицензию план 3. Облачная УАТС потребуется как минимум для подключения к голосовому каналу. Затем настройте гибридную голосовую связь или звонки по ТСОП в соответствии со способом связи с ТСОП. Дополнительные сведения см. в разделе [лицензии на комнаты Microsoft Teams](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2) .

6. Чтобы завершить задачу, нажмите кнопку **Сохранить**.

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a>Пример: Настройка учетной записи комнаты в Exchange Online и Skype для бизнеса Online

Команды PowerShell для Exchange Online:

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept-AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

Команды PowerShell для Azure Active Directory:

``` PowerShell
Set-MsolUser -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```

<!-- 
``` PowerShell
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```  -->

Команда PowerShell для Skype для бизнеса:

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> Будут добавлены CloudPBX и PSTNCallingDomesticAndInternational. Кроме того, вы должны использовать интерфейс администратора для назначения номера телефона.

## <a name="validate"></a>Действитель

Для проверки подлинности вы можете использовать любой клиент Skype для бизнеса для входа в созданную учетную запись.

## <a name="see-also"></a>См. также

[Настройка учетных записей для комнат Microsoft Teams](room-systems-v2-configure-accounts.md)

[Планирование комнат Microsoft Teams](skype-room-systems-v2-0.md)

[Развертывание комнат Microsoft Teams](room-systems-v2.md)

[Настройка консоли Microsoft Teams](console.md)

[Управление приложением "Комнаты Microsoft Teams"](skype-room-systems-v2.md)

[Лицензирование комнат Microsoft Teams](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md)
