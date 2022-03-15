---
title: Развертывание комнаты Microsoft Teams с Office 365
ms.author: czawideh
author: cazawideh
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Дополнительные сведения о развертывании Комнаты Microsoft Teams с помощью Office 365.
ms.openlocfilehash: f54e7f7e201127b0a61c99f09fee2084378dbbd9
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503716"
---
# <a name="deploy-microsoft-teams-rooms-with-office-365"></a>Развертывание комнаты Microsoft Teams с Office 365

Дополнительные сведения о развертывании Комнаты Microsoft Teams с помощью Office 365.

## <a name="requirements"></a>Требования

Прежде чем Комнаты Microsoft Teams с Office 365, убедитесь, что выполнены требования. Дополнительные сведения см. [в Комнаты Microsoft Teams требованиях](requirements.md).

### <a name="add-a-resource-account"></a>Добавление учетной записи ресурса

1. Подключение Exchange Online PowerShell. Инструкции см. в Подключение [Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

2. В Exchange Online PowerShell создайте новый почтовый ящик комнаты или измените существующий почтовый ящик комнаты. По умолчанию у почтовых ящиков помещений нет связанных учетных записей. При создании или изменении почтового ящика комнаты необходимо добавить учетную запись, которая позволяет ей проверить подлинность.

   - Чтобы создать почтовый ящик помещения, используйте следующий синтаксис:

     ``` PowerShell
     New-Mailbox -Name '<Unique Name>' -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     В этом примере создается почтовый ящик помещения со следующими настройками:

     - Имя: конференц-зал 01

     - Псевдоним: Конференц-зал01

     - Учетная запись: ConferenceRoom01@contoso.com

     - Пароль учетной записи: P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -Name 'Conference Room 01' -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID 'ConferenceRoom01@contoso.com' -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Чтобы изменить существующий почтовый ящик помещения, используйте следующий синтаксис:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     В этом примере включается учетная запись существующего почтового ящика комнаты со значением псевдонима ConferenceRoom02 и устанавливается пароль для 9898P@$$W 0rd.

     ``` PowerShell
     Set-Mailbox -Identity 'ConferenceRoom02' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   Подробные сведения о синтаксисе и параметрах см. в настройках [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) и [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).


3. В Exchange Online PowerShell настройте следующие параметры почтового ящика комнаты, чтобы улучшить собрание:

   - AutomateProcessing: автокадр (почтовый ящик автоматически принимает решение о резервировании помещений напрямую без участия человека).)

   - AddOrganizerToSubject: $false (Организатор собрания не добавляется в тему запроса на собрание.)

   - DeleteComments: $false (Текст в тексте сообщения входящих запросов на собрания.)

   - DeleteSubject: $false (Тема входящих запросов на собрания.)

   - RemovePrivateProperty: $false (Гарантирует, что личный флаг, отправленный организатором собрания в исходном запросе на собрание, не будет установлен.)

   - AddAdditionalResponse: $true (текст, заданный параметром AdditionalResponse, добавляется в запросы на собрания.)

   - AdditionalResponse: "Это Microsoft Teams собрание!" (Дополнительный текст, который нужно добавить в запрос на собрание.)

   В этом примере эти параметры настраиваются для почтового ящика комнаты Project-Изюмина-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity 'ConferenceRoom01' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse 'This is a Microsoft Teams meeting room!'
   ```

   Подробные сведения о синтаксисе и параметрах см. в описании [set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).
   
4. Подключение ms Online PowerShell задает значения Active Directory, выпустив Подключение-MsolService -Credential $cred PowerShell. Подробные сведения об Active Directory см. в [azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) не поддерживается. 

5. Настоятельно рекомендуется отключить срок действия паролей в Комнаты Teams учетных записях. Ниже приведен пример отключения срока действия пароля для учетной записи ConferenceRoom01:

    ``` PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -PasswordNeverExpires $true
    ```


1. Для подключения к Office 365 учетной записи ресурса должна быть действительная Microsoft Teams. Кроме того, необходимо назначить учетной записи устройства место использования — это определяет, какие номера номеров лицензий доступны для вашей учетной записи. Вы можете получить `Get-MsolAccountSku` список доступных skUs для Office 365 клиента. Вы можете добавить лицензию с помощью этого `Set-MsolUserLicense` cmdlet.

   В этом примере лицензия Конференц-зал лицензии пользователю из США.

  ``` PowerShell
   Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM'
  ``` 


   Подробные инструкции см. в описании назначения лицензий учетным записям пользователей с [помощью Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).


## <a name="validate"></a>Проверить

Для проверки вы можете использовать любой клиент Microsoft Teams, чтобы войти в созданную учетную запись.

## <a name="see-also"></a>См. также
[Обновление почтовых ящиков помещений с помощью дополнительных метаданных для улучшения поиска и предложения помещений](/powershell/module/exchange/set-place)

[Настройка учетных записей для Комнаты Microsoft Teams](rooms-configure-accounts.md)

[Планирование комнат Microsoft Teams](rooms-plan.md)

[Развертывание комнат Microsoft Teams](rooms-deploy.md)

[Настройка консоли комнат Microsoft Teams](console.md)

[Управление комнатами Microsoft Teams](rooms-manage.md)

[Комнаты Microsoft Teams лицензирования](rooms-licensing.md)
