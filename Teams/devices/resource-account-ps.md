---
title: Создание Microsoft Teams ресурсов для полос совместной работы Microsoft Teams с помощью PowerShell
ms.author: czawideh
author: cazawideh
manager: ericwe
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Дополнительные сведения о развертывании полос совместной работы для Microsoft Teams.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 0bbafdfbfc9fb7e9b637216aeb9e5a0d6b470533
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503916"
---
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a>Создание учетной Microsoft 365 ресурса с помощью PowerShell

В этой теме вы можете найти сведения о том, как создавать учетные записи ресурсов для полос совместной работы Microsoft Teams с помощью PowerShell.

Проще всего создать учетную запись ресурса с помощью Центр администрирования Microsoft 365. [См. эту статью о том, как это сделать](resource-account-ui.md).

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a>Требования

Прежде чем Комнаты Microsoft Teams с Office 365, убедитесь, что выполнены требования. Дополнительные сведения см. в [этой](collab-bar-deploy.md) Microsoft Teams.

- Если для панели совместной работы необходимы возможности ННР, вам потребуется телефонная система лицензию.

- У учетных записей ресурсов должны быть Exchange почтовые ящики. Так как это учетные записи ресурсов, Exchange лицензия не требуется. Рекомендуем использовать лицензию "Комнаты собраний" для учетных записей ресурсов.


### <a name="add-a-resource-account"></a>Добавление учетной записи ресурса

1. Подключение Exchange Online PowerShell. Инструкции см. в Подключение [Exchange Online PowerShell](/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module).

2. В Exchange Online PowerShell создайте новый почтовый ящик комнаты или измените существующий почтовый ящик комнаты.

   - Чтобы создать почтовый ящик помещения, используйте следующий синтаксис:

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     В этом примере создается почтовый ящик помещения со следующими настройками:

     - Имя: Huddle-Room-01

     - Псевдоним: HuddleRoom01

     - Учетная запись: huddleroom01@contoso.onmicrosoft.com

     - Пароль учетной записи: P@$$W 0rd242

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - Чтобы изменить существующий почтовый ящик помещения, используйте следующий синтаксис:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     В этом примере включается учетная запись существующего почтового ящика комнаты со значением псевдонима HuddleRoom02 и устанавливается пароль 808P@$$W 0rd. Обратите внимание, что учетная запись будет HuddleRoom02@contoso.onmicrosoft.com из-за существующего значения псевдонима.

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   Подробные сведения о синтаксисе и параметрах см. в настройках [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) и [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).


3. В Exchange Online PowerShell настройте следующие параметры почтового ящика комнаты, чтобы улучшить собрание:

   - AutomateProcessing: autoAccept (организаторы собраний получают решение о резервировании помещений напрямую без участия человека: free = accept; busy = decline.)

   - AddOrganizerToSubject: $false (Организатор собрания не добавляется в тему запроса на собрание.)

   - DeleteComments: $false (Текст в тексте сообщения входящих запросов на собрания.)

   - DeleteSubject: $false (Тема входящих запросов на собрания.)

   - RemovePrivateProperty: $false (Гарантирует, что личный флаг, отправленный организатором собрания в исходном запросе на собрание, не будет установлен.)

   - AddAdditionalResponse: $true (текст, заданный параметром AdditionalResponse, добавляется в запросы на собрания.)

   - AdditionalResponse: "В этом помещении есть панели совместной работы для Microsoft Teams!" (Дополнительный текст, который нужно добавить в запрос на собрание.)

   В этом примере эти параметры настраиваются в почтовом ящике комнаты с именем Huddle-Room-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   Подробные сведения о синтаксисе и параметрах см. в описании [set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

4. Подключение в MS Online PowerShell, чтобы создать параметры Active Directory с `Connect-MsolService -Credential $cred` помощью этого mdlet.   Подробные сведения об Active Directory см. в [azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) не поддерживается. 

5. Установите пароль для huddleroom01@contoso.onmicrosoft.com, используя следующий синтаксис:

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. У учетной записи ресурса должна быть действительная Office 365 лицензия, предпочтительно Конференц-зал SKU. Кроме того, необходимо назначить учетной записи устройства место использования — это определяет, какие номера номеров лицензий доступны для вашей учетной записи. Вы можете получить `Get-MsolAccountSku` список доступных skUs для Office 365 клиента.

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    Лицензию можно назначить с помощью Set-MsolUserLicense. 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   Подробные инструкции см. в описании назначения лицензий учетным записям пользователей с [помощью Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).




[Настройка учетных записей для полос совместной работы Microsoft Teams с помощью PowerShell](resource-account-ps.md)

[Развертывание полос совместной работы Microsoft Teams](collab-bar-deploy.md)

[Полосы совместной работы для Microsoft Teams лицензирования](../rooms/rooms-licensing.md)