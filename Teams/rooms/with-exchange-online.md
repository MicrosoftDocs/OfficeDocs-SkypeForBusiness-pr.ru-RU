---
title: Развертывание комнаты Microsoft Teams с Exchange Online
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
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Сведения о том, как развернуть комнаты Microsoft Teams с Exchange Online и локальной службой Skype для бизнеса Server, можно найти в этой теме.
ms.openlocfilehash: 82fa0b1b521c7dd2feadcca2030869b746a444aa
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662314"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Развертывание комнаты Microsoft Teams с Exchange Online

Сведения о том, как развернуть комнаты Microsoft Teams с Exchange Online и локальной службой Skype для бизнеса Server, можно найти в этой теме.
  
Если в вашей организации имеется сочетание служб, одни из которых локально, а другие — в Интернете, то конфигурация будет зависеть от того, где именно. В этой теме описывается гибридное развертывание комнат Microsoft Teams с Exchange, размещенной в Интернете. Так как в развертывании такого типа много разных вариантов, предоставить подробные инструкции для всех из них невозможно. Для многих конфигураций будет работать следующий процесс: Если процесс не подстроен для вашей настройки, рекомендуем использовать Windows PowerShell для достижения того же результата, что и здесь, а также для других параметров развертывания.

Проще всего настроить учетные записи пользователей с помощью удаленной Windows PowerShell. Корпорация Майкрософт [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), сценарий, который помогает создавать новые учетные записи пользователей или проверять существующие учетные записи ресурсов, чтобы превратить их в совместимые учетные записи пользователей комнат Microsoft Teams. При этом вы можете настроить учетные записи, которые будут использовать устройства с комнатами Microsoft Teams, следуя этим шагам.

## <a name="requirements"></a>Требования

Прежде чем развертывать комнаты Microsoft Teams в Exchange Online, убедитесь, что выполнили требования. Дополнительные сведения см. в требованиях к комнатам [Microsoft Teams.](requirements.md)
  
Чтобы развернуть комнаты Microsoft Teams с Exchange Online, выполните следующие действия: Убедитесь в том, что у вас есть необходимые разрешения для выполнения соответствующих командлетов. 

   > [!NOTE]
   >  Модуль [Azure Active Directory](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) для Windows PowerShell в этом разделе (например, Set-MsolUser) был протестирован при настройке учетных записей для устройств с комнатами Microsoft Teams. Возможно, другие cmdlets работают, но в этом сценарии они не тестировали.

При развертывании служб федерации Active Directory (AD FS) может потребоваться преобразовать учетную запись пользователя в управляемого пользователя, а затем после выполнения этих действий снова преобразовать его в федератора.
  
### <a name="create-an-account-and-set-exchange-properties"></a>Создание учетной записи и настройка свойств Exchange

1. Начните удаленный Windows PowerShell на компьютере и подключите к Exchange Online следующим образом:

    ``` Powershell
    Set-ExecutionPolicy Unrestricted
    $org = 'contoso.microsoft.com'
    $cred = Get-Credential $admin@$org
    $sess = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
    Import-PSSession $sess -DisableNameChecking
    ```

2. После создания сеанса вам нужно будет создать новый почтовый ящик и включить его в качестве учетной записи RoomMailboxAccount или изменить параметры для существующего почтового ящика помещения. Это позволит учетной записи аутентификацию в комнатах Microsoft Teams.

   Изменение существующего почтового ящика ресурса:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECT01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Если вы создаете новый почтовый ящик ресурса:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECT01@contoso.com' -Alias PROJECT01 -Name "Project--01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Чтобы повысить эффективность собрания, необходимо настроить свойства Exchange для учетной записи пользователя следующим образом:

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>Добавление адреса электронной почты для локальной учетной записи домена

1. В **средстве Active Directory Users and Computers AD** щелкните правой кнопкой мыши контейнер или подразделение, в котором будут созданы учетные записи комнат Microsoft Teams, нажмите кнопку "Создать" и выберите **"Пользователь".**
2. В поле "Полное имя" введите отображаемого имени (-Identity) из предыдущего cmdlet (Set-Mailbox или New-Mailbox) и псевдоним в поле "Имя **пользователя".**  Нажмите кнопку **Далее**.
3. Введите пароль учетной записи. Подтвердите пароль. Убедитесь, что выбран только параметр **Срок действия пароля не ограничен**.

    > [!NOTE]
    > Выбор пароля **"Срок действия не истекает"** является требованием для сервера Skype для бизнеса в комнатах Microsoft Teams. В некоторых случаях пароли с неограниченным сроком действия могут быть запрещены правилами домена. В этом случае необходимо создать исключение для каждой учетной записи пользователя комнат Microsoft Teams.
  
4. Чтобы создать учетную запись, нажмите кнопку **Готово**.
5. После создания учетной записи запустите синхронизацию каталогов. Для этого можно использовать [set-MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) в PowerShell. После этого перейдите на страницу пользователей и убедитесь, что две учетные записи, созданные на предыдущих шагах, объединены.

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Назначение лицензии на Microsoft 365 или Office 365

1. Сначала подключите Azure AD, чтобы применить некоторые параметры учетной записи. Для подключения можно использовать следующий командлет. Подробные сведения об Active Directory см. в [azure ActiveDirectory (MSOnline) 1.0.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) не поддерживается.

    ``` PowerShell
   Connect-MsolService -Credential $cred
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. Учетная запись пользователя должна иметь действуемую лицензию Microsoft 365 или Office 365, чтобы обеспечить работу Exchange и Skype для бизнеса Server. При наличии лицензии вам необходимо назначить учетной записи устройства место использования, которое определяет, какие номера SKU лицензий будут доступны вашей учетной записи. Задание нужно сделать в следующем шаге.
3. Затем используйте `Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> для получения списка доступных skus для вашей организации Microsoft 365 или Office 365.
4. После добавления номеров skus вы можете добавить лицензию с помощью `Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> cmdlet. В этом случае будет отображаться код SKU $strLicense (например, contoso:STANDARDPACK). 

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
     Get-MsolAccountSku
     Set-MsolUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
    ```
  <!--   ``` Powershell
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
     Get-AzureADSubscribedSku
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
     ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a>Включить учетную запись пользователя в Skype для бизнеса Server

1. Создайте удаленный Windows PowerShell с компьютера следующим образом:

> [!NOTE]
> Соединитель Skype для бизнеса Online сейчас является частью последнего модуля Teams PowerShell.
>
> Если вы используете последний общедоступный выпуск [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать соединитель Skype для бизнеса Online.

    ``` Powershell
    Import-Module -Name MicrosoftTeams
    $cred = Get-Credential
    $cssess = New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. Чтобы включить учетную запись комнат Microsoft Teams для Skype для бизнеса Server, запустите данной командой:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    Если вы не знаете, какое значение нужно использовать для параметра RegistrarPool в вашей среде, вы можете получить значение от существующего пользователя Skype для бизнеса Server с помощью этой команды

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a>Назначение лицензии на Сервер Skype для бизнеса учетной записи комнат Microsoft Teams

1. Войдите в систему как администратор клиента, откройте Центр администрирования Microsoft 365 и щелкните приложение "Администратор".
2. Выберите **Пользователи и группы**, после чего щелкните **Добавление пользователей, сброс паролей и другие действия**.
3. Щелкните учетную запись комнат Microsoft Teams, а затем щелкните значок пера, чтобы изменить сведения об учетной записи.
4. Щелкните **Лицензии**.
5. В разделе **Назначение лицензий** выберите Skype для бизнеса (план 2) или Skype для бизнеса (план 3), в зависимости от требований к лицензированию и Корпоративной голосовой связи. Если вы хотите использовать план 3, вам необходимо будет использовать Корпоративная голосовая связь в комнатах Microsoft Teams.
6. Щелкните **Сохранить**.

Для проверки вы сможете войти в эту учетную запись с помощью любого клиента Skype для бизнеса.

> [!NOTE]
> Если вы используете номера skus для E1, E3, E4 или E5 в Skype для бизнеса (план 2) с аудиоконференцией или телефонной системой и планом звонков, эти функции будут продолжать работать. Однако по истечении срока действия текущих лицензий следует двигаться на более простую модель лицензирования, как описано в обновлении лицензирования комнаты собраний [Teams.](rooms-licensing.md)

> [!IMPORTANT]
> Если вы используете Skype для бизнеса (план 2), вы можете использовать только комнаты Microsoft Teams в режиме "Только Skype для бизнеса", то есть все ваши собрания будут собраниями Skype для бизнеса. Чтобы включить комнату для собраний Microsoft Teams, мы рекомендуем приобрести лицензию на нее.
  
## <a name="related-topics"></a>Статьи по теме

[Настройка учетных записей для комнат Microsoft Teams](rooms-configure-accounts.md)

[Планирование комнат Microsoft Teams](rooms-plan.md)
  
[Развертывание комнат Microsoft Teams](rooms-deploy.md)
  
[Настройка консоли комнат Microsoft Teams](console.md)
  
[Управление комнатами Microsoft Teams](rooms-manage.md)
