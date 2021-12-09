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
ms.openlocfilehash: 15936a805e45ce17ec35822bb02980b4d47499b8
ms.sourcegitcommit: 1165a74b1d2e79e1a085b01e0e00f7c65483d729
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/08/2021
ms.locfileid: "61355624"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises-hybrid"></a>Развертывание Комнаты Microsoft Teams с Exchange локальной (гибридная)

В этой теме вы также ознакомьтесь с информацией о развертывании Комнаты Microsoft Teams в гибридной среде с Exchange локальной и Microsoft Teams.
  
Если в вашей организации есть несколько служб( одни из них — локально, а другие — в Интернете), то конфигурация будет зависеть от того, где именно находится та или иная служба. В этой теме описывается гибридное развертывание Комнаты Microsoft Teams с Exchange локальной службой. Так как в развертывании такого типа много разных вариантов, предоставить подробные инструкции для всех из них невозможно. Этот процесс будет работать для многих конфигураций. Если процесс не подгоняет под установку, рекомендуем использовать Windows PowerShell, чтобы получить такой же конечный результат, как описано здесь, а также для других вариантов развертывания.
  
## <a name="requirements"></a>Требования

Прежде чем развертывать Комнаты Microsoft Teams с локальной Exchange, убедитесь, что выполнили требования. Дополнительные сведения см. в Комнаты Microsoft Teams [требованиях.](requirements.md)
  
При развертывании Комнаты Microsoft Teams локальной Exchange вы будете использовать средства администрирования Active Directory, чтобы добавить адрес электронной почты для локальной учетной записи домена. Эта учетная запись будет синхронизирована с Microsoft 365 или Office 365. Выполните указанные ниже действия.
  
- Создайте учетную запись и синхронизуйте ее с Azure Active Directory.

- Включите удаленный почтовый ящик и задайте его свойства.

- Назначьте Microsoft 365 или Office 365 лицензию.

### <a name="create-an-account-and-synchronize-with-azure-active-directory"></a>Создание учетной записи и синхронизация с Azure Active Directory

1. В **средстве "Пользователи** и компьютеры" Active Directory щелкните правой кнопкой мыши папку или организационную единицу, в которую будут созданы учетные записи Комнаты Microsoft Teams, нажмите кнопку Создать и выберите пользователь **.** 

2. Введите отображаемого имени в **поле** Полное имя, а псевдоним в поле **Имя пользователя.** Нажмите кнопку **Далее**.

3. Введите пароль учетной записи. Подтвердите пароль. Убедитесь, что выбран только параметр **Срок действия пароля не ограничен**.

    > [!NOTE]
    > Для **этого необходимо выбрать пароль без** Комнаты Microsoft Teams. В некоторых случаях пароли с неограниченным сроком действия могут быть запрещены правилами домена. В этом случае необходимо создать исключение для каждой учетной записи Комнаты Microsoft Teams учетной записи.
  
4. После создания учетной записи выполните синхронизацию каталогов. После этого перейдите на страницу пользователи в своей учетной записи Центр администрирования Microsoft 365 и убедитесь, что учетная запись, созданная на предыдущих шагах, синхронизирована с Интернетом.

### <a name="enable-the-remote-mailbox-and-set-properties"></a>Включите удаленный почтовый ящик и задайте его свойства.

1. [Откройте Exchange или](/powershell/exchange/exchange-server/open-the-exchange-management-shell) подключите его к серверу [Exchange с помощью удаленной оболочки PowerShell.](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)

2. В Exchange PowerShell создайте почтовый ящик для этой учетной записи (для этого можно включить учетную запись) с помощью следующей команды:

   ```PowerShell
   Enable-Mailbox ConferenceRoom01@contoso.com -Room
   ```

   Подробные сведения о синтаксисе и параметрах см. в [описании Enable-Mailbox.](/powershell/module/exchange/mailboxes/enable-mailbox)

3. В Exchange PowerShell настройте следующие параметры почтового ящика комнаты, чтобы улучшить собрание:

   - AutomateProcessing: автокадр (организаторы собраний принимают решения о резервировании помещений напрямую без участия человека).)

   - AddOrganizerToSubject: $false (Организатор собрания не добавляется в тему запроса на собрание.)

   - DeleteComments: $false (Текст в тексте сообщения входящих запросов на собрания.)

   - DeleteSubject: $false (Тема входящих запросов на собрания.)

   - RemovePrivateProperty: $false (гарантирует, что личный флажок, отправленный организатором собрания в исходном запросе на собрание, не будет установлен.)

   - AddAdditionalResponse: $true (текст, заданный параметром AdditionalResponse, добавляется в запросы на собрания.)

   - AdditionalResponse: "Это Microsoft Teams собрание!" (Дополнительный текст, который нужно добавить в запрос на собрание.)

   В этом примере эти параметры настраиваются в почтовом ящике комнаты с именем Конференц-зал01.

   ```PowerShell
   Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

   Подробные сведения о синтаксисе и параметрах см. в описании [set-CalendarProcessing.](/powershell/module/exchange/mailboxes/set-calendarprocessing)

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Назначение лицензии Microsoft 365 или Office 365 лицензии

1. Подключение Azure Active Directory. Подробные сведения о Azure Active Directory см. в [azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0) 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) не поддерживается. 

2. У учетной записи ресурса должна быть действительная Microsoft 365 лицензия Office 365 или Exchange и Microsoft Teams не будет работать. Если у вас есть лицензия, необходимо назначить для нее место использования — это определяет, какие номера номеров лицензий доступны для вашей учетной записи. Вы можете использовать `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> , чтобы получить список доступных skus.

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. Затем вы можете добавить лицензию с помощью `Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> Командлет. В этом случае будет отображаться код SKU $strLicense (например, contoso:STANDARDPACK).

  ``` PowerShell
  Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
  Get-MsolAccountSku
  Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses $strLicense
  ```

<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```  -->

   Подробные инструкции см. в описании назначения лицензий учетным записям пользователей с [помощью Office 365 PowerShell.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)

Для проверки вы сможете использовать любой клиент для входа в эту учетную запись.
  
## <a name="related-topics"></a>Статьи по теме

[Настройка учетных записей для Комнаты Microsoft Teams](rooms-configure-accounts.md)

[Планирование комнат Microsoft Teams](rooms-plan.md)
  
[Развертывание комнат Microsoft Teams](rooms-deploy.md)
  
[Настройка консоли комнат Microsoft Teams](console.md)
  
[Управление комнатами Microsoft Teams](rooms-manage.md)
