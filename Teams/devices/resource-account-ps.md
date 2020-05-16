---
title: Создание учетных записей Microsoft Teams для панелей совместной работы в Microsoft Teams с помощью PowerShell
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
description: В этой статье приведены сведения о том, как развертывать панели совместной работы в Microsoft Teams.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 0cb8043e0530c986b9ddcaa9a1022254939adfd2
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268049"
---
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a>Создание учетной записи ресурса Microsoft 365 с помощью PowerShell

В этой статье приведены сведения о том, как создавать учетные записи ресурсов для панелей совместной работы в Microsoft Teams с помощью PowerShell.

Самый простой способ создать учетную запись ресурса — с помощью центра администрирования Microsoft 365. [В этой статье показано, как это сделать](resource-account-ui.md).

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a>Требования

Перед развертыванием комнат Microsoft Teams с помощью Office 365 убедитесь, что вы удовлетворены требованиями. Дополнительные сведения можно найти в разделе [Развертывание панелей совместной работы в Microsoft Teams](collab-bar-deploy.md).

- Если вам понадобятся возможности PSTN для панели совместной работы, вам понадобится лицензия на телефонную систему.

- Ваши учетные записи ресурсов должны иметь почтовые ящики Exchange. Так как это учетные записи ресурсов, лицензия Exchange не требуется. Мы рекомендуем использовать лицензию на использование комнат для собраний для учетных записей ресурсов.


### <a name="add-a-resource-account"></a>Добавление учетной записи ресурса

1. Подключитесь к Exchange Online PowerShell. Инструкции можно найти [в разделе Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module).

2. В Exchange Online PowerShell создайте новый почтовый ящик помещения или измените существующий почтовый ящик помещения.

   - Чтобы создать новый почтовый ящик комнаты, используйте следующий синтаксис:

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     В этом примере создается новый почтовый ящик комнаты со следующими параметрами:

     - Name (имя): Huddle-Room-01

     - Alias (псевдоним): HuddleRoom01

     - Учетная запись: huddleroom01@contoso.onmicrosoft.com

     - Пароль учетной записи: P@ $ $W 0rd242

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - Чтобы изменить существующий почтовый ящик помещения, используйте следующий синтаксис:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     В этом примере включается учетная запись для почтового ящика помещения с параметром Alias HuddleRoom02 и устанавливается пароль для 808P@ $ $W 0rd. Обратите внимание, что учетная запись будет HuddleRoom02@contoso.onmicrosoft.com из-за существующего значения псевдонима.

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   Подробные сведения о синтаксисе и параметрах можно найти в разделе [Создание почтового ящика](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) и [Настройка почтового ящика](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).


3. В Exchange Online PowerShell настройте следующие параметры в почтовом ящике комнаты, чтобы улучшить процесс собрания:

   - AutomateProcessing: с помощью автопринятия (организаторов собраний) получайте решение о резервировании комнаты непосредственно без вмешательства человека: бесплатное = принять; занято = отклонить.)

   - AddOrganizerToSubject: $false (Организатор собрания не добавляется в тему приглашения на собрание.)

   - DeleteComments: $false (Храните текст в тексте сообщения для входящих приглашений на собрания.)

   - DeleteSubject: $false (сохранить тему приглашений на входящие собрания).

   - RemovePrivateProperty: $false (гарантируется, что частный флаг, отправленный организатором собрания в исходном приглашении на собрание, будет установлен.)

   - AddAdditionalResponse: $true (текст, указанный в параметре AdditionalResponse, добавляется в приглашения на собрание.)

   - AdditionalResponse: "в этой комнате есть панель совместной работы для Microsoft Teams!" (Дополнительный текст, добавляемый в приглашение на собрание.)

   В этом примере эти параметры настраиваются в почтовом ящике комнаты с именем Huddle-Room-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   Подробные сведения о синтаксисе и параметрах можно найти в разделе [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).

4. Подключитесь к MS Online PowerShell, чтобы настроить параметры Active Directory, запустив `Connect-MsolService -Credential $cred` командлет PowerShell.   Подробнее об Active Directory можно узнать в [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) не поддерживается. 

5. Установите для пароля huddleroom01@contoso.onmicrosoft.com значение Not Expires, используя следующий синтаксис:

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. Для учетной записи ресурса требуется действительная лицензия Office 365, предпочтительная SKU для помещения для собраний. Кроме того, необходимо назначить место использования учетной записи устройства, чтобы определить, какие SKU лицензий будут доступны для вашей учетной записи. Вы можете использовать `Get-MsolAccountSku` для получения списка доступных SKU для вашего клиента Office 365.

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    Вы можете назначить лицензию с помощью Set-MsolUserLicense. 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   Подробные инструкции приведены в разделе [Назначение лицензий учетным записям пользователей с помощью Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).




[Настройка учетных записей для панелей совместной работы в Microsoft Teams с помощью PowerShell](resource-account-ps.md)

[Развертывание панелей совместной работы в Microsoft Teams](collab-bar-deploy.md)

[Панели совместной работы для лицензирования Microsoft Teams](../rooms/rooms-licensing.md)


