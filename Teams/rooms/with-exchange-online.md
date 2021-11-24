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
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Дополнительные сведения о развертывании Комнаты Microsoft Teams с Exchange Online и Skype для бизнеса Server локальной основе.
ms.openlocfilehash: 7e80da026164fc2b1feba3d03c220e4622454e49
ms.sourcegitcommit: 95c7603b47fcd5fba8f762a4590693ee9f026328
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2021
ms.locfileid: "61153292"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Развертывание комнаты Microsoft Teams с Exchange Online

Дополнительные сведения о развертывании Комнаты Microsoft Teams с Exchange Online и Skype для бизнеса Server локальной основе.
  
Если в вашей организации есть несколько служб( одни из них — локально, а другие — в Интернете), то конфигурация будет зависеть от того, где именно находится та или иная служба. В этой теме описывается гибридное развертывание Комнаты Microsoft Teams с Exchange размещены в Интернете. Так как в развертывании такого типа много разных вариантов, предоставить подробные инструкции для всех из них невозможно. Этот процесс будет работать для многих конфигураций. Если процесс не подстроен для настройки, рекомендуем использовать Windows PowerShell, чтобы получить такой же конечный результат, как описано здесь, а также для других вариантов развертывания.

Самый простой способ настроить учетные записи пользователей — настроить их с помощью удаленной Windows PowerShell. Корпорация Майкрософт [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), сценарий, который поможет создать новые учетные записи пользователей или проверить существующие учетные записи ресурсов, чтобы сделать их совместимыми Комнаты Microsoft Teams пользователями. При этом вы можете настроить учетные записи, которые будут Комнаты Microsoft Teams устройство.

## <a name="requirements"></a>Требования

Прежде чем Комнаты Microsoft Teams с Exchange Online, убедитесь, что выполнены требования. Дополнительные сведения см. в Комнаты Microsoft Teams [требованиях.](requirements.md)
  
Чтобы развернуть Комнаты Microsoft Teams с Exchange Online, выполните следующие действия. Убедитесь в том, что у вас есть необходимые разрешения для выполнения соответствующих командлетов. 

   > [!NOTE]
   >  Модуль Azure Active Directory для [Windows PowerShell](/powershell/azure/active-directory/overview) в этом разделе (например, Set-MsolUser) был протестирован при настройке учетных записей для Комнаты Microsoft Teams устройств. Возможно, другие cmdlets могут работать, но они не были протестированы в этом конкретном сценарии.

Если вы развернули службы федерации Active Directory (AD FS), вам может потребоваться преобразовать учетную запись пользователя в управляемого пользователя, прежде чем выполнять эти действия, а затем преобразовать пользователя обратно в федератора.
  
### <a name="create-an-account-and-set-exchange-properties"></a>Создание учетной записи и настройка свойств Exchange

1. Начните сеанс удаленного Windows PowerShell на компьютере и подключите Exchange Online:

    ``` Powershell
    Set-ExecutionPolicy Unrestricted
    $org = 'contoso.microsoft.com'
    $cred = Get-Credential $admin@$org
    $sess = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
    Import-PSSession $sess -DisableNameChecking
    ```

2. После создания сеанса вы либо создайте новый почтовый ящик, чтобы включить его в качестве учетной записи RoomMailboxAccount, либо измените параметры существующего почтового ящика комнаты. Это позволит учетной записи в Комнаты Microsoft Teams.

   Изменение существующего почтового ящика ресурса:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECT01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Если вы создаете новый почтовый ящик ресурса:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECT01@contoso.com' -Alias PROJECT01 -Name "Project--01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Чтобы улучшить собрание, необходимо настроить свойства Exchange для учетной записи пользователя следующим образом:

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>Добавление адреса электронной почты для локальной учетной записи домена

1. В **средстве Active Directory Users and Computers AD** щелкните правой кнопкой мыши контейнер или организационную единицу, в котором будут созданы учетные записи Комнаты Microsoft Teams, нажмите кнопку Создать **и** выберите **пользователь**.
2. В поле Полное имя введите отображаемого имени (-Identity) из предыдущего  команды (Set-Mailbox или New-Mailbox) и псевдоним в поле Имя пользователя.  Нажмите кнопку **Далее**.
3. Введите пароль учетной записи. Подтвердите пароль. Убедитесь, что выбран только параметр **Срок действия пароля не ограничен**.

    > [!NOTE]
    > Выбор пароля **сроком действия не** истекает — это требование для Skype для бизнеса Server в Комнаты Microsoft Teams. В некоторых случаях пароли с неограниченным сроком действия могут быть запрещены правилами домена. В этом случае необходимо создать исключение для каждой учетной записи Комнаты Microsoft Teams пользователя.
  
4. Чтобы создать учетную запись, нажмите кнопку **Готово**.
5. После создания учетной записи запустите синхронизацию каталогов. Для этого можно использовать [set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration) в PowerShell. После этого перейдите на страницу пользователи и убедитесь, что две учетные записи, созданные на предыдущих шагах, объединены.

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Назначение лицензии Microsoft 365 или Office 365 лицензии

1. Сначала подключите Azure AD, чтобы применить некоторые параметры учетной записи. Для подключения можно использовать следующий командлет. Подробные сведения об Active Directory см. в [azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview)

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview) не поддерживается.

    ``` PowerShell
   Connect-MsolService -Credential $cred
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. У учетной записи пользователя должна быть действительная лицензия Microsoft 365 или Office 365, чтобы Exchange и Skype для бизнеса Server работать. При наличии лицензии вам необходимо назначить учетной записи устройства место использования, которое определяет, какие номера SKU лицензий будут доступны вашей учетной записи. Задание будет выполняться в следующем шаге.
3. Затем используйте `Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> , чтобы получить список доступных skUs для вашей Microsoft 365 или Office 365 организации.
4. После добавления номеров номеров номеров ВКК вы можете добавить лицензию с помощью `Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> Командлет. В этом случае будет отображаться код SKU $strLicense (например, contoso:STANDARDPACK). 

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

### <a name="enable-the-user-account-with-skype-for-business-server"></a>Включить учетную запись пользователя с помощью Skype для бизнеса Server

> [!NOTE]
> Если вы настраивали Комнаты Teams только для Microsoft Teams собраний, вам не нужно делать следующее: Следующие действия необходимы только в том случае, если вы хотите включить поддержку Skype для бизнеса.

1. Создайте удаленный сеанс Windows PowerShell на компьютере следующим образом:

   > [!NOTE]
   > Соединитель Skype для бизнеса Online в настоящее время является частью последнего модуля Teams PowerShell.
   >
   > Если вы используете последнюю версию [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать Skype для бизнеса Online Connector.

   ``` Powershell
   # When using Teams PowerShell Module
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

2. Чтобы включить учетную запись Комнаты Microsoft Teams для Skype для бизнеса Server, с помощью этой команды:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    Если вы не знаете, какое значение нужно использовать для параметра RegistrarPool в вашей среде, вы можете получить это значение от существующего пользователя Skype для бизнеса Server с помощью этой команды

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a>Назначение лицензии Skype для бизнеса Server вашей учетной записи Комнаты Microsoft Teams

> [!NOTE]
> Если вы настраивали Комнаты Teams только для Microsoft Teams собраний, вам не нужно делать следующее: Следующие действия необходимы только в том случае, если вы хотите включить поддержку Skype для бизнеса.

1. Войдите в систему как администратор клиента, откройте Центр администрирования Microsoft 365 и щелкните приложение Администратор.
2. Выберите **Пользователи и группы**, после чего щелкните **Добавление пользователей, сброс паролей и другие действия**.
3. Щелкните Комнаты Microsoft Teams учетной записи, а затем щелкните значок пера, чтобы изменить сведения об учетной записи.
4. Щелкните **Лицензии**.
5. В разделе **Назначение лицензий** выберите Skype для бизнеса (план 2) или Skype для бизнеса (план 3), в зависимости от требований к лицензированию и Корпоративной голосовой связи. Если вы хотите использовать Корпоративная голосовая связь на Комнаты Microsoft Teams, вам необходимо использовать лицензию Комнаты Microsoft Teams.
6. Нажмите кнопку **Сохранить**.

Для проверки вы сможете использовать любой клиент Skype для бизнеса для входа в эту учетную запись.

> [!NOTE]
> Если вы используете ВКП E1, E3, E4 или E5 с планом Skype для бизнеса 2 с аудиоконференцией или с телефонная система и планом звонков, эти функции будут продолжать работать. Однако следует двигаться на более простую модель лицензирования, как описано в Teams Конференц-зал лицензирования [,](rooms-licensing.md)после истечения срока действия текущих лицензий.

> [!IMPORTANT]
> Если вы используете Skype для бизнеса 2, вы можете использовать Комнаты Microsoft Teams только в режиме Skype для бизнеса, то есть все собрания будут Skype для бизнеса собраниями. Чтобы включить в комнате собрания Microsoft Teams собрания, рекомендуем приобрести лицензию Конференц-зал собрания.
  
## <a name="related-topics"></a>Статьи по теме

[Настройка учетных записей для Комнаты Microsoft Teams](rooms-configure-accounts.md)

[Планирование комнат Microsoft Teams](rooms-plan.md)
  
[Развертывание комнат Microsoft Teams](rooms-deploy.md)
  
[Настройка консоли комнат Microsoft Teams](console.md)
  
[Управление комнатами Microsoft Teams](rooms-manage.md)
