---
title: Развертывание Комнаты Microsoft Teams с Exchange локальной системы
ms.author: dstrome
author: dstrome
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
ms.openlocfilehash: 35b69e12c38991ecf8ac4d9c0f6f335a097da334
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58612988"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a>Развертывание комнаты Microsoft Teams в локальной среде Exchange

Дополнительные сведения о развертывании среды Комнаты Microsoft Teams в гибридной среде с локальной Exchange локальной Microsoft Teams или Skype для бизнеса Online.
  
Если в вашей организации есть несколько служб с некоторыми из локальной службы, а другие — через Интернет, то конфигурация будет зависеть от того, где именно находится та или иная служба. В этой теме описывается гибридное развертывание Комнаты Microsoft Teams с Exchange локально. Так как в таком развертывании очень много вариантов, предоставить подробные инструкции для всех из них невозможно. Следующий процесс будет работать для многих конфигураций. Если процесс не подгоняет под установку, рекомендуем использовать Windows PowerShell, чтобы получить такой же конечный результат, как здесь, а также для других параметров развертывания.

Корпорация Майкрософт [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), сценарий, который поможет создать новые учетные записи пользователей или проверить существующие учетные записи ресурсов, чтобы превратить их в совместимые Комнаты Microsoft Teams учетные записи пользователей. При этом вы можете настроить учетные записи, которые Комнаты Microsoft Teams устройство.
  
## <a name="requirements"></a>Требования

Прежде чем Комнаты Microsoft Teams развертывание с локальной Exchange, убедитесь, что выполнены требования. Дополнительные сведения см. в Комнаты Microsoft Teams [требованиях.](requirements.md)
  
При развертывании Комнаты Microsoft Teams локальной Exchange вы будете использовать средства администрирования Active Directory, чтобы добавить адрес электронной почты для локальной учетной записи домена. Эта учетная запись будет синхронизирована с Microsoft 365 или Office 365. Выполните указанные ниже действия.
  
- Создайте учетную запись и синхронизируйте ее с Active Directory.

- Включите удаленный почтовый ящик и задайте его свойства.

- Назначьте Microsoft 365 или Office 365 лицензию.

- В этой записи можно включить учетную запись Skype для бизнеса Server. Для включения учетной записи устройства в вашей среде должны выполняться указанные ниже предварительные требования.

  - Вам потребуется, чтобы Skype для бизнеса (план 2) или более Microsoft 365 или Office 365 план. План должен поддерживать функции конференц-связи.
  
  - Если для Корпоративная голосовая связь телефонии (телефонии STN) необходимо использовать поставщиков услуг телефонии Комнаты Microsoft Teams необходимо Skype для бизнеса Online (план 3).

  - При настройке учетной записи комнаты в Microsoft Teams или Skype для бизнеса Online номер телефона должен быть назначен до включения учетной записи в качестве учетной записи комнаты.
  
  - У пользователей клиента должны быть Exchange почтовые ящики.
  
  - Для Комнаты Microsoft Teams учетной записи требуется лицензия Skype для бизнеса Online (план 2) или Skype для бизнеса Online (план 3), но лицензия на Exchange Online не требуется.

- Назначьте Skype для бизнеса Server своей учетной записи Комнаты Microsoft Teams лицензии.

### <a name="create-an-account-and-synchronize-with-active-directory"></a>Создание учетной записи и ее синхронизация с Active Directory

1. В **средстве "Пользователи** и компьютеры" Active Directory щелкните правой кнопкой мыши папку или организационную единицу, в которую будут созданы учетные записи Комнаты Microsoft Teams, нажмите кнопку Создать **и** выберите пользователь **.**

2. Введите отображаемое имя из предыдущего командлета в поле **Полное имя**, а затем псевдоним в поле **Имя входа пользователя**. Нажмите кнопку **Далее**.

3. Введите пароль учетной записи. Подтвердите пароль. Убедитесь, что выбран только параметр **Срок действия пароля не ограничен**.

    > [!NOTE]
    > Выбор пароля **сроком действия не истекает** — это требование для Skype для бизнеса Server Комнаты Microsoft Teams. В некоторых случаях пароли с неограниченным сроком действия могут быть запрещены правилами домена. В этом случае необходимо создать исключение для каждой учетной записи Комнаты Microsoft Teams устройства.
  
4. После создания учетной записи выполните синхронизацию каталогов. После этого перейдите на страницу пользователи в своей учетной Центр администрирования Microsoft 365 и убедитесь, что учетная запись, созданная на предыдущих шагах, была создана в Интернете.

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

   - DeleteComments: $false (Хранить текст в тексте сообщения входящих запросов на собрания).)

   - DeleteSubject: $false (Тема входящих запросов на собрание.)

   - RemovePrivateProperty: $false (гарантирует, что личный флажок, отправленный организатором собрания в исходном запросе на собрание, останется указанным.)

   - AddAdditionalResponse: $true (Текст, заданный параметром AdditionalResponse, добавляется в запросы на собрания.)

   - AdditionalResponse: "Это Skype собрание!" (Дополнительный текст, который нужно добавить в запрос на собрание.)

   В этом примере эти параметры настраиваются для почтового ящика комнаты Project-Рубель-01.

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Подробные сведения о синтаксисе и параметрах см. в описании [set-CalendarProcessing.](/powershell/module/exchange/mailboxes/set-calendarprocessing)

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Назначение лицензии Microsoft 365 или Office 365 лицензии

1. Подключение Azure Active Directory. Подробные сведения об Active Directory см. в [azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0) 

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

### <a name="enable-the-device-account"></a>Включить учетную запись устройства

Skype для бизнеса Online PowerShell используется для управления службами как для Microsoft Teams, так и Skype для бизнеса Online.

1. Создайте удаленный Windows PowerShell с компьютера следующим образом:
> [!NOTE]
> Соединитель Skype для бизнеса Online в настоящее время является частью последнего модуля Teams PowerShell.
>
> Если вы используете последний общедоступный [выпуск Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать Skype для бизнеса Online Connector.

   ``` Powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

2. Получить SIP-адрес учетной записи:

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. **Необязательный**. Если вы хотите назначить номер телефона учетной записи, необходимо выполнить операцию на этом этапе. Если вы хотите назначить номер телефона прямой маршрутии:

   ``` Powershell
    Set-CsUser -Identity $rm -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:+14255550012
    ```
    Если вы назначаете номер телефона, предоставленный Корпорацией Майкрософт, воспользуйтесь приведенным ниже cmdlet после предоставления пользователю лицензии на план звонков:
    
    ``` Powershell
    Set-CsOnlineVoiceUser -Identity $rm -TelephoneNumber +14255550011 -LocationID xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
    ```
    
4. Чтобы включить учетную запись Комнаты Microsoft Teams, с помощью этой команды:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   Если вы не знаете, какое значение нужно использовать для параметра RegistrarPool в своей среде, вы можете получить это значение от существующего пользователя с помощью этой команды:

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a>Назначение лицензии учетной записи Комнаты Microsoft Teams

1. Войдите в систему как администратор клиента, откройте Центр администрирования Microsoft 365 и щелкните приложение Администратор.
2. Выберите **Пользователи и группы**, после чего щелкните **Добавление пользователей, сброс паролей и другие действия**.
3. Щелкните Комнаты Microsoft Teams учетной записи, а затем щелкните значок пера, чтобы изменить сведения об учетной записи.
4. Щелкните **Лицензии**.
5. В разделе **Назначение лицензий** выберите Skype для бизнеса (план 2) или Skype для бизнеса (план 3), в зависимости от требований к лицензированию и Корпоративной голосовой связи. Если вы хотите использовать лицензию на план 3, Корпоративная голосовая связь на Комнаты Microsoft Teams.
6. Нажмите кнопку **Сохранить**.

Для проверки вы сможете использовать любой клиент для входа в эту учетную запись.
  
## <a name="related-topics"></a>Статьи по теме

[Настройка учетных записей для Комнаты Microsoft Teams](rooms-configure-accounts.md)

[Планирование комнат Microsoft Teams](rooms-plan.md)
  
[Развертывание комнат Microsoft Teams](rooms-deploy.md)
  
[Настройка консоли комнат Microsoft Teams](console.md)
  
[Управление комнатами Microsoft Teams](rooms-manage.md)