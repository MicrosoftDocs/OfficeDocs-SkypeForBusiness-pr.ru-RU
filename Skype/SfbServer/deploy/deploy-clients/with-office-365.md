---
title: Развертывание Систем комнат Skype версии 2 в среде Office 365
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: В данном разделе приведены сведения о способах развертывания систем комнаты Скайп версии 2 с Office 365.
ms.openlocfilehash: 5d2a756fafe616db22d968a3e946e468a6d063b4
ms.sourcegitcommit: cad74f2546a6384747b1280c3d9244aa13fd0989
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2019
ms.locfileid: "30737850"
---
# <a name="deploy-skype-room-systems-v2-with-office-365"></a>Развертывание Систем комнат Skype версии 2 в среде Office 365 

В данном разделе приведены сведения о способах развертывания систем комнаты Скайп версии 2 с Office 365, где оба online находятся в Скайп для бизнеса и Exchange.

Настройка учетных записей пользователей проще всего настроить их с помощью удаленной оболочки Windows PowerShell. Корпорация Майкрософт предоставляет [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), сценарий, который поможет создать новые учетные записи пользователей, или validate существующие учетные записи ресурсов, что у вас есть помогающих перевод их в совместимые учетных записей пользователей системы комнаты Скайп версии 2. При необходимости можно выполните следующие действия, чтобы настроить учетные записи, используемые устройства версии 2 Скайп комнаты систем.

## <a name="requirements"></a>Требования

Перед развертыванием системы комнаты Скайп версии 2 с Office 365, убедитесь, что удовлетворены требования. Дополнительные сведения см. в разделе [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).

Чтобы включить Скайп для бизнеса, необходимо иметь следующее:

- Скайп для бизнеса в Интернет (план 2 или план на основе предприятия) или более поздней версии в плане Office 365. Планирование необходимо разрешить возможности конференц-связи.

- Если вам требуется-связь с возможностями собрания, необходимо будет аудиоконференций и лицензии телефонной системой.  Если вам требуется подключение по телефонной линии возможности из собрания, необходимо будет внутри страны или внутреннее и международное вызов план.

- Клиент пользователи должны иметь почтовые ящики Exchange.

- Учетной записи системы комнаты Скайп версии 2 требуется по крайней мере Скайп для бизнеса Online (план 2) лицензии, но не требует лицензии Exchange Online. Дополнительные сведения см [Лицензирование систем комнаты Скайп версии 2](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md) .

Дополнительные сведения о Скайп для бизнеса Online планы см [Скайп для описания службы Online бизнеса](https://technet.microsoft.com/library/jj822172.aspx).

### <a name="add-a-device-account"></a>Добавление учетной записи устройства

1. Подключение к Exchange Online PowerShell. Сведения содержатся в разделе [подключение к Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

2. В Exchange Online PowerShell создание почтового ящика комнаты или изменения существующего почтового ящика помещения. По умолчанию почтовый ящик помещения не имеют связанных учетных записей, поэтому вам потребуется добавить учетную запись, при создании или изменении почтового ящика помещения, который будет выполнять проверку подлинности с системами комнаты Скайп версии 2.

   - Чтобы создать новый почтовый ящик помещения, используйте следующий синтаксис:

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     В этом примере создается новый почтовый ящик места со следующими параметрами:

     - Имя: Проект Rigel-01

     - Псевдоним: ProjectRigel01

     - Учетная запись: ProjectRigel01@contoso.onmicrosoft.com

     - Пароль для учетной записи: P@$$W0rd5959

     ``` PowerShell
     New-Mailbox -Name "Project-Rigel-01" -Alias ProjectRigel01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID ProjectRigel01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Для изменения существующего почтового ящика помещения, используйте следующий синтаксис:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     В этом примере включается учетная запись для существующего почтового ящика помещения, который имеет значение псевдоним ProjectRigel02 и задает пароль для 9898P@$$W0rd. Обратите внимание на то, что учетной записи будет ProjectRigel02@contoso.onmicrosoft.com из-за существующее значение псевдоним.

     ``` PowerShell
     Set-Mailbox -Identity ProjectRigel02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   Подробный синтаксис и сведений о параметрах в разделе [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) и [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).


3. В Exchange Online PowerShell настройте следующие параметры на почтовый ящик помещения, чтобы улучшить работу в собрание:

   - AutomateProcessing: AutoAccept (организаторам собрания принимать решение резервирования помещений напрямую без участия: свободен = принять; занят = отклонить.)

   - AddOrganizerToSubject: $false (организатор собрания не добавляется к теме запроса на проведение собрания).

   - DeleteComments: $false (сохранения любого текста в теле сообщения входящих приглашений на собрания).

   - DeleteSubject: $false (Keep темы входящих приглашений на собрания).

   - RemovePrivateProperty: $false (гарантирует пометку "частное", которые были отправлены организатором собрания в исходное приглашение на собрание запросить остается как указано).

   - AddAdditionalResponse: $true (текста, указанного с помощью параметра AdditionalResponse добавляется для приглашений на собрания).

   - AdditionalResponse: «это Скайп конференц-зала!» (Дополнительный текст для добавления в запрос на собрание.)

   В этом примере настраивается эти параметры в почтовый ящик помещения, с именем Project-Rigel-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Подробный синтаксис и сведений о параметрах в разделе [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).

4. Подключение к MS Online PowerShell, чтобы сделать параметрами Active directory, выполнив `Connect-MsolService -Credential $cred` уже For сведения в статье [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0). <!-- or [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) for the new module -->  
    1. Если вы не хотите истечения срока действия пароля, используйте следующий синтаксис:

    ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
    ```
<!--
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   В этом примере задается пароль для учетной записи ProjectRigel01@contoso.onmicrosoft.com никогда не истек.

  ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName ProjectRigel01@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   Также можно задать номер телефона для учетной записи, выполнив следующую команду:

  ``` PowerShell
    Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. Учетная запись устройства должна быть действительной лицензии Office 365 или Exchange и Скайп для бизнеса не будут работать. При наличии лицензии вам необходимо назначить учетной записи устройства место использования, которое определяет, какие номера SKU лицензий будут доступны вашей учетной записи. Вы можете использовать`Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> Для получения списка доступных номеров SKU для клиента Office 365 следующим образом:

  ``` Powershell
  Get-MsolAccountSku
  ```
<!--
   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   Теперь можно добавить лицензии с помощью`Set-MsolUserLicense` <!--Set-AzureADUserLicense --> командлет. В этом случае будет отображаться код SKU $strLicense (например, contoso:STANDARDPACK).

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

   Подробные сведения содержатся в разделе [Назначение лицензий для учетных записей пользователей с Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).

7. Затем необходимо включить запись устройства с Скайп для бизнеса. Ваша среда должна соответствовать требованиям, определенным в разделе [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).

   Для запуска удаленного [сеанса Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) (не забудьте [установить Скайп для компонентов Business Online PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)) следующим образом:

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   Затем включите свою учетную запись комнаты систем Скайп версии 2 для Скайп для Business Server, выполнив следующий командлет:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   Получите сведения о RegistrarPool из учетной записи пользователя, программа установки, как показано в следующем примере:

    ``` Powershell
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

5. В разделе **Назначение лицензий** необходимо выбрать Скайп для бизнеса Online (план 2) или Скайп для бизнеса в Интернет (план 3), в зависимости от вашей лицензирования и очевидна с точки зрения применения какого корпоративной голосовой связи. Вам потребуется использовать планирование 3 лицензии, если вы хотите использовать облачных УАТС на систем комнаты Скайп версии 2. Облачная УАТС потребуется как минимум для подключения к голосовому каналу. Затем настройте гибридную голосовую связь или звонки по ТСОП в соответствии со способом связи с ТСОП. В разделе [лицензий v2 систем комнаты Скайп](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2) более подробных сведений.

6. Чтобы завершить задачу, нажмите кнопку **Сохранить**.

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a>Пример: Комнаты учетной записи программы установки в Exchange Online и Скайп для бизнеса в Интернет

Exchange Online PowerShell команды:

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept-AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

Команды Azure Active Directory PowerShell:

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

Скайп для команды PowerShell бизнеса:

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> Будут добавлены CloudPBX и PSTNCallingDomesticAndInternational. Кроме того необходимо использовать в интерфейс администратора для назначения номера телефона.

## <a name="validate"></a>Проверка

Для проверки можно использовать любой Скайп для бизнеса клиента для входа в учетную запись, которую вы создали.

## <a name="see-also"></a>См. также

[Настройка учетных записей для систем комнаты Скайп версии 2](room-systems-v2-configure-accounts.md)

[Plan for Skype Room Systems v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)

[Развертывание Систем комнат Skype версии 2](room-systems-v2.md)

[Настройка консоли для Систем комнат Skype версии 2](console.md)

[Управление Системами комнат Skype версии 2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

[Лицензирование v2 систем Скайп комнаты](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md)
