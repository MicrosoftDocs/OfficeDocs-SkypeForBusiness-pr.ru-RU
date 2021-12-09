---
title: Развертывание Комнаты Microsoft Teams с Microsoft 365 или Office 365
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
description: В этой теме вы можете найти сведения о развертывании Комнаты Microsoft Teams с Microsoft 365 или Office 365, где Teams или Skype для бизнеса и Exchange оба веб-магазина находятся в сети.
ms.openlocfilehash: e3f72c86f88ab449b48b80d6bef06d0858c44b53
ms.sourcegitcommit: 1165a74b1d2e79e1a085b01e0e00f7c65483d729
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/08/2021
ms.locfileid: "61355648"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a>Развертывание Комнаты Microsoft Teams с Microsoft 365 или Office 365

В этой теме вы можете найти сведения о развертывании Комнаты Microsoft Teams с Microsoft 365 или Office 365, где Microsoft Teams и Exchange находятся в сети.

## <a name="requirements"></a>Требования

Прежде чем Комнаты Microsoft Teams с Microsoft 365 или Office 365, убедитесь, что выполнены требования. Дополнительные сведения см. в Комнаты Microsoft Teams [требованиях.](requirements.md)

### <a name="add-a-resource-account"></a>Добавление учетной записи ресурса

1. Подключение Exchange Online PowerShell. Инструкции см. в Подключение [Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

2. В Exchange Online PowerShell создайте новый почтовый ящик комнаты или измените существующий почтовый ящик комнаты. По умолчанию у почтовых ящиков помещений нет связанных учетных записей, поэтому вам потребуется добавить учетную запись при создании или изменении почтового ящика комнаты, которая позволяет ей проверку подлинности с помощью Microsoft Teams.

   - Чтобы создать почтовый ящик помещения, используйте следующий синтаксис:

     ``` PowerShell
     New-Mailbox -MicrosoftOnlineServicesID <Office365 ID> -Name <String> -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```
     В этом примере создается почтовый ящик помещения со следующими настройками:

     - Учетная запись: ConferenceRoom01@contoso.com
  
     - Имя: конференц-зал01

     - Псевдоним: Конференц-зал01

     - Пароль учетной записи: P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -MicrosoftOnlineServicesID ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Чтобы изменить существующий почтовый ящик помещения, используйте следующий синтаксис:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     В этом примере включается учетная запись существующего почтового ящика комнаты со значением псевдонима ConferenceRoom02 и устанавливается пароль для 9898P@$$W 0rd. Обратите внимание, что учетная запись ConferenceRoom02@contoso.com из-за существующего значения псевдонима.

     ``` PowerShell
     Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   Подробные сведения о синтаксисе и параметрах см. в настройках [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) и [Set-Mailbox.](/powershell/module/exchange/mailboxes/set-mailbox)

3. В Exchange Online PowerShell настройте следующие параметры почтового ящика комнаты, чтобы улучшить собрание:

   - AutomateProcessing: автокадр (организаторы собраний получают решение о резервировании помещений напрямую без участия человека).)

   - AddOrganizerToSubject: $false (Организатор собрания не добавляется в тему запроса на собрание.)

   - DeleteComments: $false (Текст в тексте сообщения входящих запросов на собрания.)

   - DeleteSubject: $false (Тема входящих запросов на собрания.)

   - RemovePrivateProperty: $false (гарантирует, что личный флажок, отправленный организатором собрания в исходном запросе на собрание, не будет установлен.)

   - AddAdditionalResponse: $true (текст, заданный параметром AdditionalResponse, добавляется в запросы на собрания.)

   - AdditionalResponse: "Это Microsoft Teams собрание!" (Дополнительный текст, который нужно добавить в запрос на собрание.)

   В этом примере эти параметры настраиваются в почтовом ящике комнаты с именем Конференц-зал01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

   Подробные сведения о синтаксисе и параметрах см. в описании [set-CalendarProcessing.](/powershell/module/exchange/mailboxes/set-calendarprocessing)

4. Подключение ms Online PowerShell для настройки параметров Active Directory с помощью `Connect-MsolService` Cmdlet PowerShell. Подробные сведения об Active Directory см. в [azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0)

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) не поддерживается.

5. Установите пароль так, чтобы он никогда не истекал, используя следующий синтаксис:

   ```PowerShell
   Set-MsolUser -UserPrincipalName <UPN> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   В этом примере пароль учетной записи ConferenceRoom01@contoso.onmicrosoft.com никогда не истекает.

   ```PowerShell
   Set-MsolUser -UserPrincipalName "ConferenceRoom01@contoso.com" -PasswordNeverExpires $true
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -EnforceChangePasswordPolicy $false
   ``` -->

   Кроме того, вы можете настроить номер телефона для учетной записи, выстроив следующую команду:

   ```PowerShell
   Set-MsolUser -UserPrincipalName <UPN> -PhoneNumber <phone number>
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

    > [!NOTE]
    > Если для пароля не за установлено действие "Никогда не истекает", учетная запись больше не будет вводиться на устройстве, когда срок действия учетной записи истечет. Пароль потребуется изменить для учетной записи, а также обновить локально в Комнаты Teams. Пользователи не могут присоединяться к собраниям Комнаты Teams пока истек срок действия пароля.

6. У учетной записи ресурса должна быть действительная Microsoft 365 лицензия Office 365 или Exchange и Microsoft Teams не будет работать. Если у вас есть лицензия, необходимо назначить для нее место использования — это определяет, какие номера номеров лицензий доступны для вашей учетной записи. Вы можете использовать `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> чтобы получить список доступных skUs для вашей Microsoft 365 или Office 365 организации:

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   Затем вы можете добавить лицензию с помощью `Set-MsolUserLicense` <!--Set-AzureADUserLicense --> Командлет. В этом примере лицензия Конференц-зал к учетной записи:

   ```PowerShell
   Set-MsolUser -UserPrincipalName "ConferenceRoom01@contoso.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName "ConferenceRoom01@contoso.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   Подробные инструкции см. в описании назначения лицензий учетным записям пользователей с [помощью Office 365 PowerShell.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)

   Вы также можете телефонная система возможности для этой учетной записи, но сначала необходимо настроить ее. Дополнительные [сведения см. телефонная система в](../what-is-phone-system-in-office-365.md) этой области. В этом примере добавляется план внутренних и международных звонков по ДНР:

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName ConferenceRoom01@contoso.com -AddLicenses "Contoso:MCOPSTN2"
   ```


## <a name="validate"></a>Проверить

Для проверки вы можете войти в созданную учетную запись с помощью Microsoft Teams клиента.

## <a name="see-also"></a>См. также

[Настройка учетных записей для Комнаты Microsoft Teams](rooms-configure-accounts.md)

[Планирование комнат Microsoft Teams](rooms-plan.md)

[Развертывание комнат Microsoft Teams](rooms-deploy.md)

[Настройка консоли комнат Microsoft Teams](console.md)

[Управление комнатами Microsoft Teams](rooms-manage.md)

[Комнаты Microsoft Teams лицензирования](rooms-licensing.md)
