---
title: Развертывание Комнаты Microsoft Teams с Exchange локальной системы
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
ms.openlocfilehash: 96d8a49cd75e3413739d36a3c86a91daa72b22e6
ms.sourcegitcommit: 115e44f33fc7993f6eb1bc781f83eb02a506e29b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2021
ms.locfileid: "60909540"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a>Развертывание комнаты Microsoft Teams в локальной среде Exchange

Дополнительные сведения о развертывании среды Комнаты Microsoft Teams в гибридной среде с Exchange локальной и Microsoft Teams.
  
Если в вашей организации есть несколько служб( одни из них — локально, а другие — в Интернете), то конфигурация будет зависеть от того, где именно находится та или иная служба. В этой теме описывается гибридное развертывание Комнаты Microsoft Teams с Exchange размещенной локальной службой. Так как в развертывании такого типа много разных вариантов, предоставить подробные инструкции для всех из них невозможно. Этот процесс будет работать для многих конфигураций. Если процесс не подстроен для настройки, рекомендуем использовать Windows PowerShell, чтобы получить такой же конечный результат, как описано здесь, а также для других вариантов развертывания.

Корпорация Майкрософт [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), сценарий, который поможет создать новые учетные записи пользователей или проверить существующие учетные записи ресурсов, чтобы превратить их в совместимые Комнаты Microsoft Teams пользователей. При этом вы можете настроить учетные записи, которые будут Комнаты Microsoft Teams устройство.
  
## <a name="requirements"></a>Требования

Прежде чем развертывать Комнаты Microsoft Teams с локальной Exchange, убедитесь, что выполнили требования. Дополнительные сведения см. [в Комнаты Microsoft Teams требованиях.](requirements.md)
  
При развертывании Комнаты Microsoft Teams с локальной Exchange, вы будете использовать средства администрирования Active Directory для добавления адреса электронной почты для локальной учетной записи домена. Эта учетная запись будет синхронизирована с Microsoft 365 или Office 365. Выполните указанные ниже действия.
  
- Создайте учетную запись и синхронизуйте ее с Azure Active Directory.

- Включите удаленный почтовый ящик и задайте его свойства.

- Назначьте Microsoft 365 или Office 365 лицензию.

### <a name="create-an-account-and-synchronize-with-azure-active-directory"></a>Создание учетной записи и синхронизация с Azure Active Directory

1. В **средстве "Пользователи** и компьютеры" Active Directory щелкните правой кнопкой мыши папку или организационную единицу, в которую будут созданы учетные записи Комнаты Microsoft Teams, нажмите кнопку Создать и выберите пользователь **.** 

2. Введите отображаемого имени в **поле** Полное имя, а псевдоним в поле **Имя пользователя.** Нажмите кнопку **Далее**.

3. Введите пароль учетной записи. Подтвердите пароль. Убедитесь, что выбран только параметр **Срок действия пароля не ограничен**.

    > [!NOTE]
    > Для **этого необходимо выбрать пароль без** Комнаты Microsoft Teams. В некоторых случаях пароли с неограниченным сроком действия могут быть запрещены правилами домена. В этом случае необходимо создать исключение для каждой учетной записи Комнаты Microsoft Teams устройства.
  
4. После создания учетной записи выполните синхронизацию каталогов. После этого перейдите на страницу пользователи в своей учетной записи Центр администрирования Microsoft 365 и убедитесь, что учетная запись, созданная на предыдущих шагах, была создана в Интернете.

### <a name="enable-the-remote-mailbox-and-set-properties"></a>Включите удаленный почтовый ящик и задайте его свойства.

1. [Откройте управляющую Exchange или](/powershell/exchange/exchange-server/open-the-exchange-management-shell) подключите его к серверу [Exchange с помощью удаленной оболочки PowerShell.](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)

2. В Exchange PowerShell создайте почтовый ящик для этой учетной записи (для этого можно включить учетную запись) с помощью следующей команды:

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   Подробные сведения о синтаксисе и параметрах см. в [описании Enable-Mailbox.](/powershell/module/exchange/mailboxes/enable-mailbox)

3. В Exchange PowerShell настройте следующие параметры почтового ящика комнаты, чтобы улучшить собрание:

   - AutomateProcessing: autoAccept (организаторы собраний получают решение о резервировании помещений напрямую без участия человека: free = accept; busy = decline.)

   - AddOrganizerToSubject: $false (Организатор собрания не добавляется в тему запроса на собрание.)

   - DeleteComments: $false (Текст в тексте сообщения входящих запросов на собрания.)

   - DeleteSubject: $false (Тема входящих запросов на собрания.)

   - RemovePrivateProperty: $false (Гарантирует, что личный флажок, отправленный организатором собрания в исходном запросе на собрание, останется указанным.)

   - AddAdditionalResponse: $true (текст, заданный параметром AdditionalResponse, добавляется в запросы на собрания.)

   - AdditionalResponse: "Это Microsoft Teams собрание!" (Дополнительный текст, который нужно добавить в запрос на собрание.)

   В этом примере эти параметры настраиваются для почтового ящика комнаты Project-Изюмина-01.

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

   Подробные сведения о синтаксисе и параметрах см. в описании [set-CalendarProcessing.](/powershell/module/exchange/mailboxes/set-calendarprocessing)

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Назначение лицензии Microsoft 365 или Office 365 лицензии

1. Подключение Azure Active Directory. Подробные сведения о Azure Active Directory см. в [azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0) 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) не поддерживается. 

2. У учетной записи устройства должна быть действительная Microsoft 365 или Office 365 лицензия либо Exchange и Microsoft Teams не будет работать. При наличии лицензии вам необходимо назначить учетной записи устройства место использования, которое определяет, какие номера SKU лицензий будут доступны вашей учетной записи. Вы можете использовать `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> , чтобы получить список доступных skus.

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. Затем вы можете добавить лицензию с помощью `Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> Командлет. В этом случае будет отображаться код SKU $strLicense (например, contoso:STANDARDPACK).

  ``` PowerShell
  Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
  Get-MsolAccountSku
  Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
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
