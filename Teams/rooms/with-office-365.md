---
title: Создание учетных записей ресурсов для помещений и общих Teams устройств
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
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: В этой статье вы можете найти сведения о том, как создавать учетные записи ресурсов для помещений и общих устройств, включая Комнаты Microsoft Teams, Комнаты Teams на Surface Hub и службу Teams.
ms.openlocfilehash: e7525a9e9ec6737bab18de4351675d567b61611b
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514550"
---
# <a name="create-and-configure-resource-accounts-for-rooms-and-shared-teams-devices"></a>Создание и настройка учетных записей ресурсов для комнат и общих Teams устройств

В этой статье содержатся действия по созданию учетных записей ресурсов для общих пробелов и устройств, а также по настройке учетных записей ресурсов для Комнаты Microsoft Teams в Windows, Комнаты Teams на устройствах с Android, Комнаты Teams в Surface Hub и в службе Teams  Отображает.

Microsoft 365 — это почтовые ящики и Teams, предназначенные для определенных ресурсов, таких как помещение или проектор. Эти учетные записи ресурсов могут автоматически отвечать на приглашения на собрания с помощью правил, которые вы определяете при их создания. Например, если у вас есть общий ресурс, например конференц-зал, вы можете настроить для него учетную запись ресурса, которая будет автоматически принимать или отклонить приглашения на собрания в зависимости от доступности в календаре.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

> [!NOTE]
> **Skype для бизнеса** <br><br>
> Если вам нужно включить учетную запись ресурса для работы с Skype для бизнеса, см. [Комнаты Microsoft Teams с помощью Skype для бизнеса Server](with-skype-for-business-server-2015.md)

## <a name="before-you-begin"></a>Подготовка к работе

### <a name="requirements"></a>Требования

В зависимости от среды для создания учетных записей ресурсов необходима одна или несколько ролей.

|**Среды**|**Необходимые роли**|
|-----|-----|
|Azure Active Directory  <br/> |Глобальный администратор или администратор пользователя  <br/> |
|Active Directory  <br/> |Active Directory Enterprise администраторов, администраторов доменов или иметь делегированную праву на создание пользователей. Azure Active Directory Подключение синхронизации прав.  <br/> |
|Exchange Online  <br/> |Глобальный администратор или Exchange администратор   <br/> |
|Exchange Server  <br/> |Exchange управление организацией или управление получателями   <br/> |

Если вы создаете учетные записи ресурсов для Комнаты Teams, то они должны соответствовать SMTP-адресу учетной записи ресурса. Перед [развертыванием Комнаты Microsoft Teams](requirements.md) см. Комнаты Microsoft Teams требования к Комнаты Teams.

### <a name="what-license-do-you-need"></a>Какая лицензия вам нужна?

Перед созданием учетной записи Microsoft 365 ресурсов проверьте, какая у нее лицензия:

- **Teams** Собрания. Если вы хотите связать учетную запись ресурса с общим устройством, например комнатой Microsoft Teams или Teams, и использовать ее для пользования собранием Teams, чтобы участники могли использовать ее для демонстрации видео и звука через него, вам потребуется лицензия Конференц-зал. Дополнительные сведения о лицензировании помещений для собраний см. в Teams Конференц-зал [лицензировании](rooms-licensing.md).

- **Вызовы через ОКП** Если вы хотите, чтобы ресурс звонит или принимает звонки на внешний номер телефона или с него (он называется телефонной сетью общего звонков или вызовом ОКП), вам потребуется лицензия на Microsoft 365 телефонная система или Голосовая связь Microsoft 365 бизнес телефонную Голосовая связь Microsoft 365 бизнес телефонную сеть. Вам нужно выполнить шаг 1 только в следующем обзоре. Дополнительные сведения [см. Microsoft Teams лицензий](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) на надстройки.

- &mdash;Если вы используете только учетную запись ресурса для заказа ресурса,&mdash; пригласите ресурс на собрание и попросите его автоматически принять или отклонить приглашение. Вам не нужно назначать лицензию учетной записи ресурса, и вам нужно выполнить шаг 1 в следующем обзоре.  

## <a name="overview"></a>Обзор

**Шаг 1. Создание** [новой учетной записи ресурса](#create-a-resource-account). Если почтовый ящик помещения уже существует и вы хотите преобразовать его в учетную запись ресурса, вы можете изменить существующий почтовый [Exchange помещения](?tabs=existing-account#create-a-resource-account).

**Шаг 2.**  Затем [настройте свою учетную запись для](#configure-mailbox-properties) Teams собраний.

**Шаг 3.**  Если учетная запись ресурса будет связана с общим устройством, например Teams отображается с помощью службы поддержки, отключите [срок действия пароля](#turn-off-password-expiration).

**Шаг 4.**  Наконец, [назначьте лицензию на комнату для](#assign-a-meeting-room-license) собрания, чтобы у учетной записи был доступ к Microsoft Teams.

После создания и настройки учетных записей ресурсов см. дополнительные действия по проверке дополнительных задач настройки, включая группы рассылки, возможности сети и вызовы.[](#next-steps)

## <a name="create-a-resource-account"></a>Создание учетной записи ресурса

> [!TIP]
> Для именования учетных записей ресурсов рекомендуется использовать стандартное соглашение об именовывом имени в начале адреса электронной почты. Это поможет создать динамические группы, чтобы упростить управление Azure Active Directory. Например, можно использовать "mtr-" для всех учетных записей ресурсов, которые будут связаны с Комнаты Microsoft Teams.

> [!TIP]
> Рекомендуем создать все учетные записи ресурсов с помощью Exchange Online и Azure Active Directory.

Создайте учетную запись ресурса, используя один из следующих способов:

#### <a name="in-microsoft-365-admin-center"></a>[**В Центр администрирования Microsoft 365**](#tab/m365-admin-center)

1. Войдите в Центр администрирования Microsoft 365.

2. Укайте учетные данные администратора для Microsoft 365 клиента.

3. На **панели слева** выберите Ресурсы, а затем выберите Помещения **& оборудования**. Если эти параметры недоступны на левой панели, возможно, сначала нужно выбрать **показать все** .

4. Выберите **Добавить почтовый ящик ресурса,** чтобы создать новую учетную запись комнаты. Введите отображаемую имя и адрес электронной почты для учетной записи, выберите **Добавить**, а затем выберите **Закрыть**.

5. По умолчанию для учетных записей ресурсов настроены следующие параметры:

    - Разрешить повторение собраний
    - Автоматическое отклонение собраний вне следующих ограничений
      - Окно резервирования (дней): 180
      - Максимальная длительность (часы): 24
    - Автоматическое принятие запросов на собрания

    Если вы хотите изменить их, выберите **Настроить параметры планирования** , прежде чем на выбор **Закрыть**. Если вы хотите изменить их позже, перейдите  >  в **resourcesRooms & оборудование**, выберите учетную запись ресурса. Затем в меню **Параметры резервирования** выберите **Изменить**.

6. Перейдите **в группу ПользователиАктивные** >  пользователи и выберите комнату, созданную вами, чтобы открыть панель свойств.

7. Затем назначьте пароль учетной записи ресурса. На панели выберите Сбросить **пароль**.
 
8. Требование изменения пароля на общем устройстве приведет к проблемам со входом. Отменить **. При** первом входе пользователь должен изменить пароль, а затем выберите **Сбросить**.

9. В разделе **Лицензии и приложения** выберите расположение для  страны или региона, в которых будет установлено устройство. Затем выберите лицензию, которая вы хотите назначить, например Конференц-зал, и выберите **Сохранить изменения**. Лицензия может отличаться в зависимости от организации.

Чтобы изменить параметры почтового ящика ресурса, см. [](#configure-mailbox-properties) настройка свойств почтового ящика или использование Exchange администрирования.

Кроме того, может потребоваться применить политики пропускной способности или политики собраний к этой учетной записи. [Дополнительные сведения см](#next-steps). в следующей информации.

#### <a name="with-exchange-online"></a>[**С помощью Exchange Online**](#tab/exchange-online)

1. Подключение Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

    ``` PowerShell
    Connect-ExchangeOnline
    ```

2. По умолчанию у почтовых ящиков помещений нет связанных учетных записей. Добавьте учетную запись при создании почтового ящика помещения для проверки подлинности с помощью Microsoft Teams.

    Если вы создаете новый почтовый ящик ресурса:
    
    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID <Office365 ID> -Name <String> -Alias <string> -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
    ```
    
    В этом примере создается почтовый ящик помещения со следующими настройками:

        - Account: ConferenceRoom01@contoso.com
          
        - Name: ConferenceRoom01
        
        - Alias: ConferenceRoom01
        
        - Account password: P@$$W0rd5959

    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
    ```

Если вы не в гибридной конфигурации Exchange, вы можете ступить к следующему шагу Настройка [свойств почтового ящика](#configure-mailbox-properties).

Если вы в гибридной Exchange, вам нужно добавить адрес электронной почты для локальной учетной записи домена. [Дополнительные сведения см. в Office 365 синхронизации](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78) локальной и локальной учетных записей пользователей.

#### <a name="with-exchange-server"></a>[**С Exchange Server**](#tab/exchange-server)

  1. Подключение Exchange management Shell. [Откройте Exchange или](/powershell/exchange/exchange-server/open-the-exchange-management-shell) подключите его к Exchange [с помощью удаленной оболочки PowerShell](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).

   2. Чтобы создать почтовый ящик помещения:

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

#### <a name="modify-an-existing-exchange-room-mailbox"></a>[**Изменение существующего почтового Exchange помещения**](#tab/existing-account)

Чтобы изменить существующий почтовый ящик помещения, чтобы он стал учетной записью ресурса, используйте следующий синтаксис:

``` PowerShell
Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
```

В этом примере включается учетная запись существующего почтового ящика комнаты со значением псевдонима ConferenceRoom02 и устанавливается пароль для 9898P@$$W 0rd.

``` PowerShell
Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
```

Если вы в гибридной Exchange, вам также потребуется добавить адрес электронной почты для локальной учетной записи домена. [Дополнительные сведения см. в Office 365 синхронизации](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78) локальной и локальной учетных записей пользователей.

Подробные сведения о синтаксисе и параметрах см. в настройках [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) и [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).

> [!NOTE]
> Если вы создаете эту учетную запись для Teams Room в Surface Hub, необходимо также включить ActiveSync в этой учетной записи. Это позволит вам отправлять сообщения электронной почты непосредственно из Surface Hub, которые можно использовать для таких функций, как Доска. Дополнительные Surface Hub см. в Surface Hub [activeSync](/surface-hub/apply-activesync-policies-for-surface-hub-device-accounts).

---

> [!IMPORTANT]
> Если вы используете эту учетную запись только для забронировать место и автоматически принимаете или отклоните приглашения, настройка завершена. Если вы используете эту учетную запись ресурса для звонков по ОКП, см[](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md). Microsoft Teams лицензии на надстройки, чтобы определить, какая лицензия нужна.
>
> Переход к следующему разделу только в том случае, если учетная запись ресурса Комнаты Teams в Windows, Комнаты Teams для Android, Комнаты Teams в Surface Hub или в Teams с помощью службы поддержки.

## <a name="configure-mailbox-properties"></a>Настройка свойств почтового ящика

В Exchange PowerShell (как в сети, так и локально) настройте следующие параметры почтового ящика комнаты, чтобы улучшить собрание:

- **AutomateProcessing: `AutoAccept`** Организаторы собраний получают решение о резервировании помещений напрямую без участия человека.

- **AddOrganizerToSubject: `$false`** Организатор собрания не добавляется в тему запроса на собрание.

- **DeleteComments: `$false`** Храните текст в тексте входящих запросов на собрания. Это необходимо для обработки внешних собраний Teams и сторонних собраний для обеспечения работы с one Touch Join.

- **DeleteSubject: `$false`** Храните тему входящих запросов на собрания.

- **ProcessExternalMeetingMessages: `$true`** Определяет, следует ли обрабатывать запросы на собрания, которые происходят за Exchange организации. Требуется для внешних Teams и [сторонних собраний](/microsoftteams/rooms/third-party-join).

- **RemovePrivateProperty: `$false`** Гарантирует, что личный флажок, отправленный организатором собрания в исходном запросе собрания, останется указанным.

- **AddAdditionalResponse: `$true`** Текст, заданный параметром AdditionalResponse, добавляется в запросы на собрания.

- **AdditionalResponse: "Это Microsoft Teams собрание!"** Дополнительный текст, который нужно добавить в ответ на принятие собрания.

В этом примере настроены эти параметры для почтового ящика комнаты с именем ConferenceRoom01:

``` PowerShell
Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -ProcessExternalMeetingMessages $true -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
```

Подробные сведения о синтаксисе и параметрах см. в описании [set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

## <a name="turn-off-password-expiration"></a>Отключение срока действия пароля

Если срок действия пароля учетной записи ресурса истек, устройство не будет вводить его после истечения срока действия. Затем пароль потребуется изменить для учетной записи ресурса, а затем обновить на каждом устройстве. Чтобы избежать этого, вы можете отключить срок действия пароля.
  
> [!NOTE]
> Установка **пароля без истечения срока** действия является требованием для общих Microsoft Teams устройств. Если правила домена запрещают пароли, срок действия которых не истек, необходимо создать исключение для каждой учетной записи ресурса Teams устройств.

Чтобы отключить срок действия пароля, выполните действия на одной из следующих вкладок:

#### <a name="azure-active-directory-20"></a>[**Azure Active Directory 2.0**](#tab/azure-active-directory2-password/)

Во-первых, Подключение к Active Directory PowerShell:

```PowerShell
   Connect-AzureAD
```

Затем см. [в этой записи. См. настройка срока действия пароля](/microsoft-365/admin/add-users/set-password-to-never-expire?view=o365-worldwide#set-a-password-to-never-expire).

В этом примере пароль учетной записи ConferenceRoom01@contoso.com срок действия никогда не истекает.

```PowerShell
Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -PasswordPolicies DisablePasswordExpiration
```

#### <a name="azure-active-directory-10"></a>[**Azure Active Directory 1.0**](#tab/azure-active-directory1-password/)

 1. Подключение msOnline PowerShell:

       ```PowerShell
       Connect-MsolService
       ```

       Подробные сведения об Active Directory см[. в Azure Active Directory (MSOnline).](/powershell/azure/active-directory/overview?view=azureadps-1.0)

2. Установите пароль так, чтобы он никогда не истекал, используя следующий синтаксис:

    ```PowerShell
    Set-MsolUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    В этом примере пароль учетной записи ConferenceRoom01@contoso.com срок действия никогда не истекает.

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -PasswordNeverExpires $true
    ```

#### <a name="active-directory-on-premises"></a>[**Active Directory (локально)**](#tab/active-directory1-password/)

1. Подключение в Active Directory PowerShell:

    ```PowerShell
       Import-Module ActiveDirectory
    ```
    
    Подробные сведения об Active Directory PowerShell см. в [activeDirectory](/powershell/module/activedirectory/?view=windowsserver2022-ps).

2. Установите пароль так, чтобы он никогда не истекал, используя следующий синтаксис:

    ```PowerShell
    Set-ADUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    В этом примере пароль учетной записи ConferenceRoom01@contoso.com срок действия никогда не истекает.

    ```PowerShell
    Set-ADUser -Identity ConferenceRoom01@contoso.com -PasswordNeverExpires $true
    ```

---

## <a name="assign-a-meeting-room-license"></a>Назначение лицензии на комнату для собраний

Для этого учетной записи Microsoft 365 или Office 365 лицензию на Microsoft Teams.

> [!NOTE]
> Комнаты Microsoft Teams стандартный и Комнаты Microsoft Teams премиум доступны два номера номеров для общих устройств в комнате собраний, включая Комнаты Teams. Для отображения с помощью службы Teams требуется лицензия на комнату для собраний. Дополнительные сведения см. [в Teams лицензирования комнаты собраний](rooms-licensing.md).

Чтобы назначить лицензии с помощью Центр администрирования Microsoft 365, см. [назначение лицензий пользователям](/microsoft-365/admin/manage/assign-licenses-to-users). Чтобы назначить лицензии с помощью Azure AD, см. одну из следующих вкладок:

#### <a name="active-directory-20"></a>[**Active Directory 2.0**](#tab/active-directory2-license/)


1. Подключение в Azure AD
  
    ```PowerShell
    Connect-AzureAD
    ```

     Подробные сведения об Active Directory см. [в Azure Active Directory PowerShell для Graph](/powershell/azure/active-directory/overview?view=azureadps-2.0).
    
2. Назначьте место использования своей учетной записи ресурса с помощью `Set-AzureADUser` этого cmdlet. Это определяет, какие номера номеров лицензий доступны.

    В этом примере пользователь находится в США:

    ```PowerShell
    Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -UsageLocation 'US'
    ```

3. Затем воспользуйтесь для `Get-AzureADSubscribedSku` получения списка доступных skUs для вашей Microsoft 365 или Office 365 организации.

    ```PowerShell
    Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
    ```

4. Чтобы назначить лицензию, `Set-AzureADUser` воспользуйтесь этим cmdlet и преобразуем код SKU лицензии (см. шаг 2) в объект типа лицензии PowerShell. Затем назначьте этот объект учетной записи ресурса. В следующем примере SKU лицензии: 6070a4c8-34c6-4937-8dfb-39bbc6397a60 и он назначен учетной conferenceroom01@contoso.com:

    ```PowerShell
    #Create an object for a single license type
    $License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
    $License.SkuId = "6070a4c8-34c6-4937-8dfb-39bbc6397a60" 
       
    #Create an object for a multiple license type
    $Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
       
    #Add the single license object to the multiple license object
    $Licenses.AddLicenses = $License 
       
    #Assign the license to the resource account
    Set-AzureADUserLicense -ObjectId ConferenceRoom01@contoso.com -AssignedLicenses $Licenses
    ```

#### <a name="active-directory-10"></a>[**Active Directory 1.0**](#tab/active-directory1-license/)

1. Подключение msOnline PowerShell.

   ```PowerShell
   Connect-MsolService
   ```

    Подробные сведения об Active Directory см. [в Azure Active Directory (MSOnline).](/powershell/azure/active-directory/overview?view=azureadps-1.0)

2.  Назначьте место использования своей учетной записи ресурса с помощью `Set-MsolUser` этого cmdlet. Это определяет, какие номера номеров лицензий доступны.

    В этом примере пользователь находится в США.
    
    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
    ```
    
    Затем вы можете получить `Get-MsolAccountSku` список доступных skUs для своей Microsoft 365 или Office 365 организации.

4. Чтобы назначить лицензию, воспользуйтесь этим `Set-MsolUser` cmdlet. В этом примере лицензии contoso:MEETING_ROOM" назначены учетной записи conferenceroom01@contoso.com:

    ```PowerShell
    Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM'
    ```

---

Чтобы проверить создание учетной записи и назначение лицензий, во Teams с помощью созданной учетной записи.

## <a name="next-steps"></a>Дальнейшие действия

### <a name="network-and-bandwidth"></a>Сеть и пропускная способность

Возможно, вам потребуется применить к этой учетной записи настраиваемую сеть, пропускную способность или политики собраний. Дополнительные сведения о политиках сети и пропускной способности см. в параметрах политики собраний [для & видео](/microsoftteams/meeting-policies-audio-and-video). Для Комнаты Teams советуем установить пропускную способность для политики собраний на 10 Мбит/с.

Для совместной работы включите PowerPoint Live, Доска и общие заметки. Вы можете создать политику собраний, чтобы настроить параметры участников и гостей для Комнаты Teams. Например, просмотрите параметры "вестибюля", например, какие участники будут автоматически допускаться на собрания. Дополнительные сведения о политиках Teams собраниях см. в [Microsoft Teams.](/microsoftteams/meeting-policies-overview)

### <a name="calling"></a>Звонки

Нет уникальных требований для звонков с учетными записями ресурсов. Учетную запись ресурса можно включить для звонков так же, как и обычных пользователей.

> [!NOTE]
> Мы рекомендуем отключить голосовую почту для общих устройств, назначив политику звонков учетным записям ресурсов устройств. [Дополнительные сведения см.](../teams-calling-policy.md) в Teams переад Teams звонках.

### <a name="configure-distribution-groups"></a>Настройка групп рассылки

Чтобы упорядочить места проведения собраний, вы можете добавить учетные записи ресурсов устройства Exchange группы рассылки. Например, если у вас есть офисы в трех разных географических расположениях, вы можете создать три группы рассылки и добавить в каждое расположение соответствующие учетные записи ресурсов. Дополнительные сведения см. [в списке комнат](/exchange/recipients/room-mailboxes?view=exchserver-2019#create-a-room-list).

## <a name="related-articles"></a>Статьи по теме

[Настройка учетных записей для Комнаты Microsoft Teams](rooms-configure-accounts.md)

[Планирование комнат Microsoft Teams](rooms-plan.md)

[Развертывание комнат Microsoft Teams](rooms-deploy.md)

[Управление комнатами Microsoft Teams](rooms-manage.md)

[Комнаты Microsoft Teams лицензирования](rooms-licensing.md)
