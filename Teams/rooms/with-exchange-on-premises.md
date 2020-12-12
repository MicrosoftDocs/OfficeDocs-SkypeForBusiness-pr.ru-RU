---
title: Развертывание комнат Microsoft Teams с локальной службой Exchange
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: Сведения о том, как развернуть комнаты Microsoft Teams в гибридной среде с локальной средой Exchange, можно найти в этой теме.
ms.openlocfilehash: f9f80f5b993b9be95e35c8178d996973558e2512
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662324"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a>Развертывание комнаты Microsoft Teams в локальной среде Exchange

Сведения о том, как развернуть комнаты Microsoft Teams в гибридной среде с локальной средой Exchange и Microsoft Teams или Skype для бизнеса Online, можно прочитать в этой теме.
  
Если в вашей организации имеется сочетание служб, одни из которых локально, а другие — в Интернете, то конфигурация будет зависеть от того, где именно. В этой теме описывается гибридное развертывание комнат Microsoft Teams с локальной службой Exchange. Так как в развертывании такого типа много разных вариантов, предоставить подробные инструкции для всех из них невозможно. Для многих конфигураций будет работать следующий процесс: Если процесс не подгоняет целевую настройку, рекомендуем использовать Windows PowerShell для достижения того же результата, что и здесь, а также для других вариантов развертывания.

Корпорация Майкрософт [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), сценарий, который помогает создавать новые учетные записи пользователей или проверять существующие учетные записи ресурсов, чтобы превратить их в совместимые учетные записи пользователей комнат Microsoft Teams. При этом вы можете настроить учетные записи, которые будут использовать ваше устройство Microsoft Teams Rooms, следуя этим шагам.
  
## <a name="requirements"></a>Требования

Прежде чем развертывать комнаты Microsoft Teams с локальной службой Exchange, убедитесь, что выполнили требования. Дополнительные сведения см. в требованиях [к комнатам Microsoft Teams.](requirements.md)
  
При развертывании комнат Microsoft Teams с локальной службой Exchange вы будете использовать средства администрирования Active Directory для добавления адреса электронной почты для локальной учетной записи домена. Эта учетная запись будет синхронизирована с Microsoft 365 или Office 365. Выполните указанные ниже действия.
  
- Создайте учетную запись и синхронизируйте ее с Active Directory.

- Включите удаленный почтовый ящик и задайте его свойства.

- Назначьте лицензию на Microsoft 365 или Office 365.

- В включить учетную запись устройства с помощью Skype для бизнеса Server. Для включения учетной записи устройства в вашей среде должны выполняться указанные ниже предварительные требования.

  - В плане Microsoft 365 или Office 365 вам потребуется Skype для бизнеса Online (план 2) или более высокий. План должен поддерживать функции конференц-связи.
  
  - Если вам Корпоративная голосовая связь телефонию (телефонную сеть ННР) с использованием поставщиков услуг телефонии для комнат Microsoft Teams, вам потребуется Skype для бизнеса Online (план 3).
  
  - У пользователей клиента должны быть почтовые ящики Exchange.
  
  - Для вашей учетной записи комнат Microsoft Teams требуется лицензия на Skype для бизнеса Online (план 2) или Skype для бизнеса Online (план 3), но лицензия на Exchange Online не требуется.

- Назначьте лицензию на сервер Skype для бизнеса учетной записи комнат Microsoft Teams.

### <a name="create-an-account-and-synchronize-with-active-directory"></a>Создание учетной записи и ее синхронизация с Active Directory

1. В средстве **"Пользователи** и компьютеры" Active Directory щелкните правой кнопкой мыши папку или подразделение, в которые будут созданы учетные записи комнат Microsoft Teams, щелкните "Создать", а затем выберите "Пользователь". 

2. Введите отображаемое имя из предыдущего командлета в поле **Полное имя**, а затем псевдоним в поле **Имя входа пользователя**. Нажмите кнопку **Далее**.

3. Введите пароль учетной записи. Подтвердите пароль. Убедитесь, что выбран только параметр **Срок действия пароля не ограничен**.

    > [!NOTE]
    > Выбор пароля **"Срок действия не истекает"** является требованием для сервера Skype для бизнеса в комнатах Microsoft Teams. В некоторых случаях пароли с неограниченным сроком действия могут быть запрещены правилами домена. В этом случае необходимо создать исключение для каждой учетной записи устройства в microsoft Teams Rooms.
  
4. После создания учетной записи выполните синхронизацию каталогов. После этого перейдите на страницу пользователей в Центре администрирования Microsoft 365 и убедитесь, что учетная запись, созданная на предыдущих шагах, была создана в Интернете.

### <a name="enable-the-remote-mailbox-and-set-properties"></a>Включите удаленный почтовый ящик и задайте его свойства.

1. [Откройте управляющую оболочку Exchange или](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) подключите ее к [серверу Exchange с помощью удаленной оболочки PowerShell.](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)

2. В Exchange PowerShell создайте почтовый ящик для учетной записи (в том числе для этой учетной записи), выляв следующую команду:

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   Подробный синтаксис и сведения о параметрах см. в [описании enable-Mailbox.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox)

3. В Exchange PowerShell настройте следующие параметры почтового ящика помещения, чтобы улучшить качество собрания:

   - AutomateProcessing: autoAccept (организаторы собраний принимают решение о резервировании помещений напрямую без участия человека: бесплатно = принять; занят = отклонуть.)

   - AddOrganizerToSubject: $false (организатор собрания не добавляется в тему запроса на собрание.)

   - DeleteComments: $false (Текст должен быть в тексте входящих запросов на собрания).)

   - DeleteSubject: $false (Храните тему входящих запросов на собрания.)

   - RemovePrivateProperty: $false (Гарантирует, что личный флаг, отправленный организатором собрания в исходном запросе собрания, останется указанным.)

   - AddAdditionalResponse: $true (текст, заданный параметром AdditionalResponse, добавляется в запросы на собрания.)

   - AdditionalResponse: "Это комната для собраний Skype!" (Дополнительный текст, который нужно добавить в запрос на собрание.)

   В этом примере эти параметры настраиваются для почтового ящика помещения Project-Дорел-01.

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Подробные сведения о синтаксисе и параметрах см. в описании [set-CalendarProcessing.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Назначение лицензии на Microsoft 365 или Office 365

1. Подключите Azure Active Directory. Подробные сведения об Active Directory см. в [azure ActiveDirectory (MSOnline) 1.0.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) не поддерживается. 

2. У учетной записи устройства должна быть действительная лицензия Microsoft 365 или Office 365, либо Exchange и Microsoft Teams не будут работать. При наличии лицензии вам необходимо назначить учетной записи устройства место использования, которое определяет, какие номера SKU лицензий будут доступны вашей учетной записи. Вы можете использовать `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> , чтобы получить список доступных skus.

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. Затем вы можете добавить лицензию с помощью `Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> cmdlet. В этом случае будет отображаться код SKU $strLicense (например, contoso:STANDARDPACK).

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

   Подробные инструкции см. в описании назначения лицензий учетным записям пользователей с [помощью Office 365 PowerShell.](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)

### <a name="enable-the-device-account"></a>Включить учетную запись устройства

Skype для бизнеса Online PowerShell используется для управления службами Для Microsoft Teams и Skype для бизнеса Online.

1. Создайте удаленный Windows PowerShell с компьютера следующим образом:
> [!NOTE]
> Соединитель Skype для бизнеса Online сейчас является частью последнего модуля Teams PowerShell.
>
> Если вы используете последний общедоступный выпуск [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать соединитель Skype для бизнеса Online.

   ``` Powershell
   Import-Module -Name MicrosoftTeams  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. Получите SIP-адрес учетной записи:

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. Чтобы включить учетную запись комнат Microsoft Teams, запустите эту команду:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   Если вы не знаете, какое значение нужно использовать для параметра RegistrarPool в вашей среде, вы можете получить значение от существующего пользователя с помощью этой команды:

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a>Назначение лицензии учетной записи комнат Microsoft Teams

1. Войдите в систему как администратор клиента, откройте Центр администрирования Microsoft 365 и щелкните приложение "Администратор".
2. Выберите **Пользователи и группы**, после чего щелкните **Добавление пользователей, сброс паролей и другие действия**.
3. Щелкните учетную запись комнат Microsoft Teams, а затем щелкните значок пера, чтобы изменить сведения об учетной записи.
4. Щелкните **Лицензии**.
5. В разделе **Назначение лицензий** выберите Skype для бизнеса (план 2) или Skype для бизнеса (план 3), в зависимости от требований к лицензированию и Корпоративной голосовой связи. Если вы хотите использовать Корпоративная голосовая связь в комнатах Microsoft Teams, необходимо использовать лицензию на План 3.
6. Нажмите кнопку **Сохранить**.

Для проверки вы сможете использовать любой клиент для входа в эту учетную запись.
  
## <a name="related-topics"></a>Статьи по теме

[Настройка учетных записей для комнат Microsoft Teams](rooms-configure-accounts.md)

[Планирование комнат Microsoft Teams](rooms-plan.md)
  
[Развертывание комнат Microsoft Teams](rooms-deploy.md)
  
[Настройка консоли комнат Microsoft Teams](console.md)
  
[Управление комнатами Microsoft Teams](rooms-manage.md)
