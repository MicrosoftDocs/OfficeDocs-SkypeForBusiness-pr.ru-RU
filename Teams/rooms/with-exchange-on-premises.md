---
title: Развертывание Комнаты Microsoft Teams с Exchange локальной (гибридной)
ms.author: czawideh
author: cazawideh
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: В этой теме вы также ознакомьтесь с информацией о развертывании Комнаты Microsoft Teams в гибридной среде с Exchange локальной среде.
ms.openlocfilehash: ea05ef6b6bf6e13ee907d84d1d48200c0cea5a09
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767232"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises-hybrid"></a>Развертывание Комнаты Microsoft Teams с локальной Exchange (гибридная)

В этой теме вы также ознакомьтесь с информацией о развертывании Комнаты Microsoft Teams в гибридной среде с Exchange локальной и Microsoft Teams.
  
Если в вашей организации есть несколько служб( одни из них — локально, а другие — в Интернете), то конфигурация будет зависеть от того, где именно находится та или иная служба. В этой теме описывается гибридное развертывание Комнаты Microsoft Teams с Exchange размещенной локальной службой. Так как в развертывании такого типа много разных вариантов, предоставить подробные инструкции для всех из них невозможно. Этот процесс будет работать для многих конфигураций. Если процесс не подстроен для настройки, рекомендуем использовать Windows PowerShell, чтобы получить такой же конечный результат, как описано здесь, а также для других вариантов развертывания.
  
## <a name="requirements"></a>Требования

Прежде чем Комнаты Microsoft Teams развертывание Exchange локально, убедитесь, что выполнили требования. Дополнительные сведения см. в Комнаты Microsoft Teams [требованиях.](requirements.md)

### <a name="enable-the-remote-mailbox-and-set-properties"></a>Включите удаленный почтовый ящик и задайте его свойства.

1. [Откройте Exchange или](/powershell/exchange/exchange-server/open-the-exchange-management-shell) подключите его к серверу [Exchange с помощью удаленной оболочки PowerShell.](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)

2. В Exchange PowerShell создайте новый почтовый ящик комнаты или измените существующий почтовый ящик комнаты. По умолчанию у почтовых ящиков помещений нет связанных учетных записей, поэтому при создании или изменении почтового ящика комнаты вам потребуется добавить учетную запись, которая позволяет ей проверку подлинности с помощью Microsoft Teams.

   - Чтобы создать почтовый ящик помещения, используйте следующий синтаксис:

     ``` PowerShell
     New-Mailbox -UserPrincipalName <UPN> -Name <String> -Alias <String> -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```
     
     В этом примере создается почтовый ящик помещения со следующими настройками:

     - Учетная запись: ConferenceRoom01@contoso.com
  
     - Имя: конференц-зал01

     - Псевдоним: Конференц-зал01

     - Пароль учетной записи: P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Чтобы изменить существующий почтовый ящик помещения, используйте следующий синтаксис:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     В этом примере включается учетная запись существующего почтового ящика комнаты со значением псевдонима ConferenceRoom02 и устанавливается пароль 9898P@$$W 0rd. Обратите внимание, что учетная запись ConferenceRoom02@contoso.com из-за существующего значения псевдонима.

     ``` PowerShell
     Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   Подробные сведения о синтаксисе и параметрах см. в настройках [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) и [Set-Mailbox.](/powershell/module/exchange/mailboxes/set-mailbox)

3. В Exchange PowerShell настройте следующие параметры почтового ящика комнаты, чтобы улучшить собрание:

   - AutomateProcessing: автокадр (организаторы собраний принимают решения о резервировании помещений напрямую без участия человека).)

   - AddOrganizerToSubject: $false (Организатор собрания не добавляется в тему запроса на собрание.)

   - DeleteComments: $false (Текст в тексте сообщения входящих запросов на собрания.)

   - DeleteSubject: $false (Тема входящих запросов на собрания.)

   - RemovePrivateProperty: $false (гарантирует, что личный флажок, отправленный организатором собрания в исходном запросе на собрание, останется указанным.)

   - AddAdditionalResponse: $true (текст, заданный параметром AdditionalResponse, добавляется в запросы на собрания.)

   - AdditionalResponse: "Это Microsoft Teams собрание!" (Дополнительный текст, который нужно добавить в запрос на собрание.)

   В этом примере эти параметры настраиваются в почтовом ящике комнаты с именем Конференц-зал01.

   ```PowerShell
   Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

   Подробные сведения о синтаксисе и параметрах см. в описании [set-CalendarProcessing.](/powershell/module/exchange/mailboxes/set-calendarprocessing)

### <a name="set-password-to-never-expire"></a>Установить срок действия пароля

1. В **средстве "Пользователи** и компьютеры" Active Directory найдите учетную запись Комнаты Microsoft Teams, щелкните ее правой кнопкой мыши и выберите **Свойства**.

2. Выберите **пароль, срок действия которого никогда** не истекает, и нажмите кнопку **ОК.**

   > [!NOTE]
   > Для этого **необходимо выбрать пароль,** срок действия которого никогда Комнаты Microsoft Teams не истекает. В некоторых случаях пароли с неограниченным сроком действия могут быть запрещены правилами домена. В этом случае необходимо создать исключение для каждой учетной записи Комнаты Microsoft Teams учетной записи.

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Назначение лицензии Microsoft 365 или Office 365 лицензии

1. Подключение Azure Active Directory. Подробные сведения о Azure Active Directory см. в [azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0) 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) не поддерживается. 

2. У учетной записи ресурса должна быть действительная Microsoft 365 лицензия Office 365 или Exchange и Microsoft Teams не будет работать. Если у вас есть лицензия, необходимо назначить для нее место использования — это определяет, какие номера номеров лицензий доступны для вашей учетной записи. Вы можете использовать `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> , чтобы получить список доступных skus.

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

3. Затем вы можете добавить лицензию с помощью `Set-MsolUserLicense` <!--Set-AzureADUserLicense --> Командлет. В этом примере лицензия Конференц-зал к учетной записи:

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

Для проверки вы сможете использовать любой клиент для входа в эту учетную запись.
  
## <a name="related-topics"></a>Статьи по теме

[Настройка учетных записей для Комнаты Microsoft Teams](rooms-configure-accounts.md)

[Планирование комнат Microsoft Teams](rooms-plan.md)
  
[Развертывание комнат Microsoft Teams](rooms-deploy.md)
  
[Настройка консоли комнат Microsoft Teams](console.md)
  
[Управление комнатами Microsoft Teams](rooms-manage.md)
