---
title: Создание учетных записей ресурсов Microsoft Teams для полос совместной работы в Microsoft Teams с помощью PowerShell
ms.author: mitressl
author: flinchbot
manager: ericwe
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: В этой теме вы также начитайте сведения о том, как развернуть отлаголовки совместной работы в Microsoft Teams.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 0cb8043e0530c986b9ddcaa9a1022254939adfd2
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268049"
---
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a>Создание учетной записи ресурса Microsoft 365 с помощью PowerShell

В этой теме вы можете найти сведения о том, как создавать учетные записи ресурсов для отсчиток совместной работы в Microsoft Teams с помощью PowerShell.

Проще всего создать учетную запись ресурса с помощью Центра администрирования Microsoft 365. [См. статью о том, как это сделать.](resource-account-ui.md)

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a>Требования

Прежде чем развернуть комнаты Microsoft Teams с Office 365, убедитесь, что выполнили требования. Дополнительные сведения см. в [подмногих развертываниях совместной работы в Microsoft Teams.](collab-bar-deploy.md)

- Если для панели совместной работы нужны возможности ННР, вам потребуется лицензия на телефонную систему.

- Учетные записи ресурсов должны иметь почтовые ящики Exchange. Поскольку это учетные записи ресурсов, лицензия на Exchange не требуется. Рекомендуем использовать лицензию на комнаты собраний для учетных записей ресурсов.


### <a name="add-a-resource-account"></a>Добавление учетной записи ресурса

1. Подключите Exchange Online PowerShell. Инструкции см. в [инструкциях по подключению к Exchange Online PowerShell.](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)

2. В Exchange Online PowerShell создайте почтовый ящик новой комнаты или измените существующий.

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

   - Чтобы изменить почтовый ящик помещения, используйте следующий синтаксис:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     В этом примере включается учетная запись существующего почтового ящика помещения, который имеет значение псевдонима HuddleRoom02, и устанавливает пароль 808P@$$W 0rd. Обратите внимание, что учетная запись будет HuddleRoom02@contoso.onmicrosoft.com из-за существующего значения псевдонима.

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   Подробные сведения о синтаксисах и параметрах см. в настройках [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) [и Set-Mailbox.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)


3. В Exchange Online PowerShell настройте следующие параметры почтового ящика помещения, чтобы улучшить качество собрания:

   - AutomateProcessing: autoAccept (организаторы собраний принимают решение о резервировании помещений напрямую без участия человека: бесплатно = принять; занят = отклонуть.)

   - AddOrganizerToSubject: $false (организатор собрания не добавляется в тему запроса на собрание.)

   - DeleteComments: $false (текст должен быть в тексте входящих запросов на собрания).)

   - DeleteSubject: $false (Храните тему входящих запросов на собрания.)

   - RemovePrivateProperty: $false (Гарантирует, что личный флаг, отправленный организатором собрания в исходном запросе собрания, останется указанным.)

   - AddAdditionalResponse: $true (текст, заданный параметром AdditionalResponse, добавляется в запросы на собрания.)

   - AdditionalResponse: "В этой комнате есть панели совместной работы для Microsoft Teams!" (Дополнительный текст, который нужно добавить в запрос на собрание.)

   В этом примере эти параметры настраиваются для почтового ящика помещения Huddle-Room-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   Подробные сведения о синтаксисе и параметрах см. в описании [set-CalendarProcessing.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)

4. Подключите MS Online PowerShell, чтобы создать параметры Active Directory, задав его с помощью `Connect-MsolService -Credential $cred` cmdlet PowerShell.   Подробные сведения об Active Directory см. в [azure ActiveDirectory (MSOnline) 1.0.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) не поддерживается. 

5. Установите пароль для huddleroom01@contoso.onmicrosoft.com, используя следующий синтаксис:

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. У учетной записи ресурса должна быть действительная лицензия На Office 365 ( предпочтительно номер SKU комнаты для собраний). Кроме того, необходимо назначить учетной записи устройства место использования— от этого зависит, какие номера номеров лицензий доступны для вашей учетной записи. Вы можете получить список доступных skus для клиента `Get-MsolAccountSku` Office 365.

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    Вы можете назначить лицензию с помощью Set-MsolUserLicense. 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   Подробные инструкции см. в описании назначения лицензий учетным записям пользователей с [помощью Office 365 PowerShell.](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)




[Настройка учетных записей для полос совместной работы в Microsoft Teams с помощью PowerShell](resource-account-ps.md)

[Развертывание отетков совместной работы в Microsoft Teams](collab-bar-deploy.md)

[Полосы совместной работы для лицензирования Microsoft Teams](../rooms/rooms-licensing.md)


