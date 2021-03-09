---
title: Развертывание комнат Microsoft Teams с Microsoft 365 или Office 365
ms.author: v-cichur
author: cichur
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
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: В этой теме вы можете найти сведения о развертывании комнат Microsoft Teams с Microsoft 365 или Office 365, где обе службы Teams или Skype для бизнеса и Exchange находятся в сети.
ms.openlocfilehash: 7a25fb17e4b9fce4a51c6e2be5828ecafff59894
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569125"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a>Развертывание комнат Microsoft Teams с Microsoft 365 или Office 365

В этой теме вы можете найти сведения о развертывании комнат Microsoft Teams с Microsoft 365 или Office 365, где microsoft Teams, Skype для бизнеса и Exchange находятся в сети.

Проще всего настроить учетные записи пользователей с помощью удаленного Windows PowerShell. Корпорация Майкрософт [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), сценарий, который помогает создавать новые учетные записи пользователей или проверять существующие учетные записи ресурсов, чтобы превратить их в совместимые учетные записи пользователей комнат Microsoft Teams. При этом вы можете настроить учетные записи, которые будут использовать ваше устройство Microsoft Teams Rooms, следуя этим шагам.

## <a name="requirements"></a>Требования

Прежде чем развернуть комнаты Microsoft Teams с Microsoft 365 или Office 365, убедитесь, что выполнили требования. Дополнительные сведения см. в требованиях к комнатам [Microsoft Teams.](requirements.md)

Чтобы включить Skype для бизнеса, у вас должны быть следующие возможности:

- Skype для бизнеса Online (план 2 или корпоративный план) или более высокого уровня в вашем плане Microsoft 365 или Office 365. В плане должны быть разрешается использовать функции для работы сконференцией с dial-in.

- Если на собрании вам нужны функции телефонного звонка, вам потребуется лицензия на аудиоконференцию и телефонную систему.  Если на собрании вам нужны функции телефонного дозвона, вам потребуется лицензия на аудиоконференцию.

- У пользователей клиента должны быть почтовые ящики Exchange.

- Для учетной записи комнат Microsoft Teams требуется как минимум лицензия на Skype для бизнеса Online (план 2), но лицензия на Exchange Online не требуется. Подробные [сведения см. в лицензиях на комнаты Microsoft Teams.](rooms-licensing.md)

Подробные сведения о планах Skype для бизнеса Online см. в описании [службы Skype для бизнеса Online.](https://technet.microsoft.com/library/jj822172.aspx)

### <a name="add-a-device-account"></a>Добавление учетной записи устройства

1. Подключите Exchange Online PowerShell. Инструкции см. в [инструкциях по подключению к Exchange Online PowerShell.](https://go.microsoft.com/fwlink/p/?linkid=396554)

2. В Exchange Online PowerShell создайте почтовый ящик новой комнаты или измените существующий. По умолчанию у почтовых ящиков помещений нет связанных учетных записей, поэтому вам потребуется добавить учетную запись при создании или изменении почтового ящика комнаты, которая позволяет ей аутентификацию с помощью систем комнат Skype 2.

   - Чтобы создать почтовый ящик помещения, используйте следующий синтаксис:

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     В этом примере создается почтовый ящик помещения со следующими настройками:

     - Имя: Карель-01

     - Псевдоним: Дарел1

     - Учетная запись: Rigel1@contoso.onmicrosoft.com

     - Пароль учетной записи: P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Чтобы изменить почтовый ящик помещения, используйте следующий синтаксис:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     В этом примере включается учетная запись существующего почтового ящика помещения, который имеет значение псевдонима "Иван2", и устанавливает пароль 9898P@$$W 0rd. Обратите внимание, что учетная запись будет Rigel2@contoso.onmicrosoft.com из-за существующего значения псевдонима.

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   Подробные сведения о синтаксисах и параметрах см. в настройках [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) [и Set-Mailbox.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)

3. В Exchange Online PowerShell настройте следующие параметры почтового ящика помещения, чтобы улучшить качество собрания:

   - AutomateProcessing: autoAccept (организаторы собраний принимают решение о резервировании помещений напрямую без участия человека: free = accept; busy = decline.)

   - AddOrganizerToSubject: $false (организатор собрания не добавляется в тему запроса на собрание.)

   - DeleteComments: $false (Текст должен быть в тексте входящих запросов на собрания).)

   - DeleteSubject: $false (Храните тему входящих запросов на собрания.)

   - RemovePrivateProperty: $false (Гарантирует, что личный флаг, отправленный организатором собрания в исходном запросе собрания, останется указанным.)

   - AddAdditionalResponse: $true (текст, заданный параметром AdditionalResponse, добавляется в запросы на собрания.)

   - AdditionalResponse: "Это комната для собраний Skype!" (Дополнительный текст, который нужно добавить в запрос на собрание.)

   В этом примере эти параметры настраиваются для почтового ящика помещения с именем Карели-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Подробные сведения о синтаксисе и параметрах см. в описании [set-CalendarProcessing.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)

4. Подключите MS Online PowerShell, чтобы внести параметры Active Directory, задав их с помощью `Connect-MsolService -Credential $cred` cmdlet PowerShell. Подробные сведения об Active Directory см. в [azure ActiveDirectory (MSOnline) 1.0.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) не поддерживается.

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

   Кроме того, можно настроить номер телефона для учетной записи, вы можете с помощью следующей команды:

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

> [!NOTE]
> Если для пароля не установлено действие "Никогда не истекает", учетная запись больше не будет вводиться на устройстве, когда срок действия учетной записи истечет. После этого потребуется изменить пароль для учетной записи, а также обновить его локально на устройстве MTR.

6. У учетной записи устройства должна быть действительная лицензия Microsoft 365 или Office 365 либо exchange, Microsoft Teams или Skype для бизнеса не будут работать. При наличии лицензии вам необходимо назначить учетной записи устройства место использования, которое определяет, какие номера SKU лицензий будут доступны вашей учетной записи. Вы можете использовать `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> чтобы получить список доступных skus для вашей организации Microsoft 365 или Office 365:

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   Затем вы можете добавить лицензию с помощью `Set-MsolUserLicense` <!--Set-AzureADUserLicense --> cmdlet. В этом примере лицензия на комнату для собраний добавляется к учетной записи:

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   Подробные инструкции см. в описании назначения лицензий учетным записям пользователей с помощью [Office 365 PowerShell.](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)

   Вы также можете добавить функции телефонной системы в эту учетную запись, но сначала необходимо ее настроить. Дополнительные сведения см. в [подмносях "Телефонная](../what-is-phone-system-in-office-365.md) система". В этом примере добавляется план внутренних и международных звонков по ПС:

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "Contoso:MCOPSTN2"
   ```

7. Затем необходимо включить учетную запись устройства в Skype для бизнеса. Убедитесь, что ваша среда соответствует требованиям, определенным в требованиях к комнатам [Microsoft Teams.](requirements.md)

   Начните [удаленный Windows PowerShell с](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) помощью таких компонентов (обязательно установите компоненты Skype для [бизнеса Online PowerShell):](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)

> [!NOTE]
> Соединитель Skype для бизнеса Online сейчас входит в состав последнего модуля Teams PowerShell.
>
> Если вы используете последний общедоступный выпуск [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать соединитель Skype для бизнеса Online.

   ``` Powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

   Получите данные RegistrarPool из новой учетной записи пользователя, как показано в примере:

   ``` Powershell
    Get-CsOnlineUser -Identity "Rigel1@contoso.onmicrosoft.com" | Select -Expand RegistrarPool
   ```

   Затем вите свою учетную запись комнат Microsoft Teams для Skype для бизнеса Server с помощью следующего командлета:

   ``` Powershell
   Enable-CsMeetingRoom -Identity "Rigel1@contoso.onmicrosoft.com" -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   > [!NOTE]
   > Возможно, новые учетные записи пользователей не будут созданы в том же пуле реестра, что и существующие учетные записи пользователей в клиенте. Эта команда предотвращает ошибки при настройке учетной записи в связи с этой ситуацией.

## <a name="validate"></a>Проверить

Для проверки вы сможете войти в созданную учетную запись с помощью любого клиента Skype для бизнеса.

## <a name="see-also"></a>См. также

[Настройка учетных записей для комнат Microsoft Teams](rooms-configure-accounts.md)

[Планирование комнат Microsoft Teams](rooms-plan.md)

[Развертывание комнат Microsoft Teams](rooms-deploy.md)

[Настройка консоли комнат Microsoft Teams](console.md)

[Управление комнатами Microsoft Teams](rooms-manage.md)

[Лицензирование комнат Microsoft Teams](rooms-licensing.md)
