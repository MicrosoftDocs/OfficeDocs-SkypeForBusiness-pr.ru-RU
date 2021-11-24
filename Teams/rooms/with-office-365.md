---
title: Развертывание Комнаты Microsoft Teams с помощью Microsoft 365 или Office 365
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: В этой теме вы можете найти сведения о развертывании Комнаты Microsoft Teams с Microsoft 365 или Office 365, где Teams или Skype для бизнеса и Exchange находятся в сети.
ms.openlocfilehash: 948287d8a5711e1643605d147d1b25b28d764a42
ms.sourcegitcommit: 95c7603b47fcd5fba8f762a4590693ee9f026328
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2021
ms.locfileid: "61153302"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a>Развертывание Комнаты Microsoft Teams с помощью Microsoft 365 или Office 365

В этой теме вы можете найти сведения о развертывании Комнаты Microsoft Teams с Microsoft 365 или Office 365, где обе Microsoft Teams или Skype для бизнеса и Exchange находятся в сети.

Самый простой способ настроить учетные записи пользователей — настроить их с помощью удаленной Windows PowerShell. Корпорация Майкрософт [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), сценарий, который поможет создать новые учетные записи пользователей или проверить существующие учетные записи ресурсов, чтобы превратить их в совместимые Комнаты Microsoft Teams учетные записи пользователей. При этом вы можете настроить учетные записи, которые будут Комнаты Microsoft Teams устройство.

## <a name="requirements"></a>Требования

Прежде чем Комнаты Microsoft Teams с Microsoft 365 или Office 365, убедитесь, что выполнены требования. Дополнительные сведения см. в Комнаты Microsoft Teams [требованиях.](requirements.md)

Чтобы включить Skype для бизнеса, необходимо сделать следующее:

- Skype для бизнеса (план 2 или план Enterprise) или более высокого уровня в Microsoft 365 или Office 365 плана. В плане должны быть возможности для работы сконференцию с телефонным телефоном.

- Если на собрании вам нужны возможности телефонного дозвона, вам потребуется лицензия на аудиоконференцию и телефонная система аудиоконференцию.  Если на собрании вам нужны возможности для телефонного набора, вам потребуется лицензия на аудиоконференцию.

- У пользователей клиента должны быть Exchange почтовые ящики.

- Для Комнаты Microsoft Teams учетной записи требуется как минимум лицензия Skype для бизнеса Online (план 2), но лицензия на Exchange Online не требуется. Подробные [Комнаты Microsoft Teams лицензий.](rooms-licensing.md)

Подробные сведения о планах Skype для бизнеса Online см. в Skype для бизнеса [Online Service Description](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description).

### <a name="add-a-device-account"></a>Добавление учетной записи устройства

1. Подключение Exchange Online PowerShell. Инструкции см. в Подключение [Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

2. В Exchange Online PowerShell создайте новый почтовый ящик комнаты или измените существующий почтовый ящик комнаты. По умолчанию у почтовых ящиков помещений нет связанных учетных записей, поэтому вам потребуется добавить учетную запись при создании или изменении почтового ящика помещения, который позволяет ей проверку подлинности с помощью Skype Room Systems v2.

   - Чтобы создать почтовый ящик помещения, используйте следующий синтаксис:

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     В этом примере создается почтовый ящик помещения со следующими настройками:

     - Имя: Абсел-01

     - Псевдоним: Иван

     - Учетная запись: Rigel1@contoso.onmicrosoft.com

     - Пароль учетной записи: P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Чтобы изменить существующий почтовый ящик помещения, используйте следующий синтаксис:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     В этом примере включается учетная запись существующего почтового ящика комнаты со значением псевдонима «Иван2» и устанавливается значение 9898P@$$W 0rd. Обратите внимание, что учетная запись будет Rigel2@contoso.onmicrosoft.com из-за существующего значения псевдонима.

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   Подробные сведения о синтаксисе и параметрах см. в настройках [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) и [Set-Mailbox.](/powershell/module/exchange/mailboxes/set-mailbox)

3. В Exchange Online PowerShell настройте следующие параметры почтового ящика комнаты, чтобы улучшить собрание:

   - AutomateProcessing: autoAccept (организаторы собраний получают решение о резервировании помещений напрямую без участия человека: free = accept; busy = decline.)

   - AddOrganizerToSubject: $false (Организатор собрания не добавляется в тему запроса на собрание.)

   - DeleteComments: $false (Текст в тексте сообщения входящих запросов на собрания.)

   - DeleteSubject: $false (Тема входящих запросов на собрания.)

   - RemovePrivateProperty: $false (гарантирует, что личный флажок, отправленный организатором собрания в исходном запросе на собрание, останется указанным.)

   - AddAdditionalResponse: $true (текст, заданный параметром AdditionalResponse, добавляется в запросы на собрания.)

   - AdditionalResponse: "Это Microsoft Teams собрание!" (Дополнительный текст, который нужно добавить в запрос на собрание.)

   В этом примере эти параметры настраиваются для почтового ящика комнаты с именем Карель-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

   Подробные сведения о синтаксисе и параметрах см. в описании [set-CalendarProcessing.](/powershell/module/exchange/mailboxes/set-calendarprocessing)

4. Подключение ms Online PowerShell, чтобы создать параметры Active Directory с помощью `Connect-MsolService -Credential $cred` Cmdlet PowerShell. Подробные сведения об Active Directory см. в [azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0)

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) не поддерживается.

5. Если вы не хотите, чтобы срок действия пароля истекал, используйте следующий синтаксис:

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   В этом примере пароль учетной записи Rigel1@contoso.onmicrosoft.com срок действия никогда не истекает.

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -PasswordNeverExpires $true
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -EnforceChangePasswordPolicy $false
   ``` -->

   Кроме того, вы можете настроить номер телефона для учетной записи, выстроив следующую команду:

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

    > [!NOTE]
    > Если для пароля не за установлено действие "Никогда не истекает", учетная запись больше не будет вводиться на устройстве, когда срок действия учетной записи истечет. Затем пароль потребуется изменить для учетной записи, а также обновить локально на устройстве MTR.

6. У учетной записи устройства должна быть действительная лицензия Microsoft 365 или Office 365 либо Exchange и Microsoft Teams или Skype для бизнеса не будет работать. При наличии лицензии вам необходимо назначить учетной записи устройства место использования, которое определяет, какие номера SKU лицензий будут доступны вашей учетной записи. Вы можете использовать `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> чтобы получить список доступных skUs для вашей Microsoft 365 или Office 365 организации:

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   Затем вы можете добавить лицензию с помощью `Set-MsolUserLicense` <!--Set-AzureADUserLicense --> Командлет. В этом примере лицензия Конференц-зал к учетной записи:

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   Подробные инструкции см. в описании назначения лицензий учетным записям пользователей с [помощью Office 365 PowerShell.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)

   Вы также можете телефонная система возможности для этой учетной записи, но сначала необходимо настроить ее. Дополнительные [сведения см. в телефонная система.](../what-is-phone-system-in-office-365.md) В этом примере добавляется план внутренних и международных звонков по ДНР:

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "Contoso:MCOPSTN2"
   ```

    > [!NOTE]
    > Если вы настраиваете Комнаты Teams только для того, чтобы Microsoft Teams собрания, не переходите к следующему шагу: Эти возможности необходимы только в том случае, если вы также включит поддержку Skype для бизнеса локальной службе.

7. Чтобы включить учетную запись устройства Skype для бизнеса локальной среде, убедитесь, что ваша среда соответствует требованиям, Комнаты Microsoft Teams [требованиям.](requirements.md)

   Начните сеанс [удаленного](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) Windows PowerShell (не забудьте установить компоненты [Skype для бизнеса Online PowerShell):](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)

   > [!NOTE]
   > Соединитель Skype для бизнеса Online в настоящее время является частью последнего модуля Teams PowerShell.
   >
   > Если вы используете последнюю версию [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать Skype для бизнеса Online Connector.

   ``` Powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

   Получите данные RegistrarPool из новой учетной записи пользователя, как показано в этом примере:

   ``` Powershell
    Get-CsOnlineUser -Identity "Rigel1@contoso.onmicrosoft.com" | Select -Expand RegistrarPool
   ```

   Затем в Комнаты Microsoft Teams учетную запись Skype для бизнеса Server с помощью следующего cmdlet:

   ``` Powershell
   Enable-CsMeetingRoom -Identity "Rigel1@contoso.onmicrosoft.com" -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   > [!NOTE]
   > Новые учетные записи пользователей могут не создаваться в том же реестре, что и существующие учетные записи пользователей в клиенте. Эта команда предотвращает ошибки при настройке учетной записи в связи с этой ситуацией.

## <a name="validate"></a>Проверить

Для проверки вы можете использовать любой клиент Skype для бизнеса войти в созданную учетную запись.

## <a name="see-also"></a>См. также

[Настройка учетных записей для Комнаты Microsoft Teams](rooms-configure-accounts.md)

[Планирование комнат Microsoft Teams](rooms-plan.md)

[Развертывание комнат Microsoft Teams](rooms-deploy.md)

[Настройка консоли комнат Microsoft Teams](console.md)

[Управление комнатами Microsoft Teams](rooms-manage.md)

[Комнаты Microsoft Teams лицензирования](rooms-licensing.md)
