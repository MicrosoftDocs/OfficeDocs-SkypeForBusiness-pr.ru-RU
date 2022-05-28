---
title: Создание учетных записей ресурсов для комнат и общих Teams устройств
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
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: В этой статье содержатся сведения о том, как создавать учетные записи ресурсов для комнат и общих устройств, включая Комнаты Microsoft Teams, Комнаты Teams на Surface Hub и службу "горячее обслуживание" на Teams дисплеях.
ms.openlocfilehash: 53d69a5dd91e012bc948bad1b9d7350afcbbb1b2
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2022
ms.locfileid: "65760891"
---
# <a name="create-and-configure-resource-accounts-for-rooms-and-shared-teams-devices"></a>Создание и настройка учетных записей ресурсов для комнат и общих Teams устройств

В этой статье содержатся инструкции по созданию учетных записей ресурсов для общих пространств и устройств, а также по настройке учетных записей ресурсов для Комнаты Microsoft Teams в Windows, Комнаты Teams на Android, Комнаты Teams в Surface Hub, и горячее обслуживание на Teams дисплеях.

Microsoft 365 ресурсов — это почтовые ящики и Teams, выделенные для определенных ресурсов, таких как комната или проектор. Эти учетные записи ресурсов могут автоматически отвечать на приглашения на собрания с помощью правил, определяемых при их создании. Например, если у вас есть общий ресурс, например конференц-зал, вы можете настроить учетную запись ресурса для этого конференц-зала, которая будет автоматически принимать или отклонять приглашения на собрания в зависимости от доступности календаря. 

Каждая учетная запись ресурса уникальна для одной Комнаты Microsoft Teams или Teams реализации горячего рабочего места.

> [!NOTE]
> При использовании Microsoft Teams панели учетная запись Комнаты Teams входа в Комнаты Teams и связанные Teams панели.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

> [!NOTE]
> **Skype для бизнеса** <br><br>
> Если необходимо включить учетную запись ресурса для работы с Skype для бизнеса, см. раздел [Комнаты Microsoft Teams с Skype для бизнеса Server](with-skype-for-business-server-2015.md)

## <a name="before-you-begin"></a>Подготовка к работе

### <a name="requirements"></a>Требования

В зависимости от среды для создания учетных записей ресурсов требуется одна или несколько ролей.

|**Среды**|**Необходимые роли**|
|-----|-----|
|Azure Active Directory  <br/> |Глобальный администратор или администратор пользователей  <br/> |
|Active Directory  <br/> |Active Directory Enterprise администраторов, администраторов домена или имеют делегированные права на создание пользователей. Azure Active Directory Подключение синхронизации.  <br/> |
|Exchange Online  <br/> |Глобальный администратор или Exchange администратор   <br/> |
|Exchange Server  <br/> |Exchange "Управление организацией" или "Управление получателями"   <br/> |

Если вы создаете учетные записи ресурсов для Комнаты Teams, имя участника-пользователя должно соответствовать SMTP-адресу учетной записи ресурса. [Ознакомьтесь Комнаты Microsoft Teams требования перед](requirements.md) развертыванием Комнаты Teams.

### <a name="what-license-do-you-need"></a>Какая лицензия вам нужна?

Прежде чем создавать учетную запись Microsoft 365 ресурса, проверьте, какая лицензия требуется:

- **Teams** собраниях, если вы хотите связать учетную запись ресурса с общим устройством, например с комнатой Microsoft Teams или Teams, и использовать ее для присоединения к собранию Teams, чтобы участники могли использовать ее для представления видео и звука через него, вам потребуется лицензия Конференц-зал. Дополнительные сведения о лицензировании комнат для собраний см. [Teams Конференц-зал лицензировании](rooms-licensing.md).

- **Вызовы ТСОП** Если вы хотите, чтобы ресурс совершать или принимать звонки с внешнего номера телефона (называемого телефонной сетью общего пользования или вызовом ТСОП), вам потребуется лицензия Microsoft 365 телефонная система или Голосовая связь Microsoft 365 бизнес. Вам нужно выполнить шаг 1 только в следующем обзоре. Дополнительные сведения [см. Microsoft Teams](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) лицензиях на надстройки.

- &mdash;Если вы используете только учетную запись ресурса для резервации ресурса,&mdash;пригласите ресурс на собрание и предложите ему автоматически принять или отклонить приглашение, и вам не нужно назначать лицензию учетной записи ресурса, и вам нужно выполнить шаг 1 в следующем обзоре.  

## <a name="overview"></a>Обзор

**Шаг 1. Создание** [учетной записи ресурса](#create-a-resource-account). Или, если почтовый ящик помещения уже существует и вы хотите преобразовать его в учетную запись ресурса, можно изменить существующий почтовый [ящик Exchange помещения](?tabs=existing-account#create-a-resource-account).

**Шаг 2.**  Затем [настройте учетную запись](#configure-mailbox-properties) для Teams собраний.

**Шаг 3.**  Если учетная запись ресурса будет связана с общим устройством, например Teams отображается с помощью службы "Горячее обслуживание", [отключите срок действия пароля](#turn-off-password-expiration).

**Шаг 4.**  Наконец, [назначьте лицензию на конференц-зал](#assign-a-meeting-room-license), чтобы учетная запись была Microsoft Teams.

После создания и настройки учетных записей ресурсов ознакомьтесь со [](#next-steps) следующими шагами, чтобы просмотреть дополнительные задачи настройки, включая группы рассылки, возможности сети и вызовы.

## <a name="create-a-resource-account"></a>Создание учетной записи ресурса

> [!TIP]
> При именовании учетных записей ресурсов рекомендуется использовать стандартное соглашение об именовании в начале адреса электронной почты. Это поможет создать динамические группы для упрощения управления в Azure Active Directory. Например, можно использовать mtr-для всех учетных записей ресурсов, которые будут связаны с Комнаты Microsoft Teams.

> [!TIP]
> Рекомендуется создавать все учетные записи ресурсов с помощью Exchange Online и Azure Active Directory.

Создайте учетную запись ресурса с помощью метода на одной из следующих вкладок:

#### <a name="in-microsoft-365-admin-center"></a>[**В Центр администрирования Microsoft 365**](#tab/m365-admin-center)

1. Войдите в Центр администрирования Microsoft 365.

2. Укажите учетные данные администратора для Microsoft 365 клиента.

3. Перейдите **к разделу "** Ресурсы" на панели слева, а затем **выберите "Комнаты& оборудование.** Если эти параметры недоступны на левой панели, может потребоваться сначала выбрать **"Показать все** ".

4. Выберите **"Добавить почтовый ящик ресурса"** , чтобы создать учетную запись комнаты. Введите отображаемое имя и адрес электронной почты для учетной записи **, выберите "** Добавить" и нажмите кнопку **"Закрыть"**.

5. По умолчанию учетные записи ресурсов настраиваются со следующими параметрами:

    - Разрешить повторяющиеся собрания
    - Автоматическое отклонение собраний за пределами следующих ограничений
      - Окно резервирования (в днях): 180
      - Максимальная длительность (часы): 24
    - Автоматическое принятие приглашений на собрания

    Если вы хотите изменить их, выберите " **Задать параметры планирования** " перед нажми кнопку **"Закрыть"**. Если вы хотите изменить их позже, перейдите  >  в раздел "Комнаты **ресурсов& оборудование**, выберите учетную запись ресурса. Затем в разделе **"Параметры резервирования**" выберите " **Изменить"**.

6. Перейдите **в раздел "** > Активные **пользователи**" и выберите комнату, которую вы создали, чтобы открыть панель свойств.

7. Затем назначьте пароль учетной записи ресурса. На панели выберите сброс **пароля**.
 
8. Требование пользователя изменить пароль на общем устройстве приведет к проблемам со входом. Снимите **флажок "Требовать от этого пользователя изменить пароль при первом входе**" и нажмите кнопку **"Сбросить"**.

9. В разделе **"Лицензии и приложения** " задайте для параметра **"** Выбрать расположение" страну или регион, где будет установлено устройство. Затем выберите лицензию, которую нужно назначить, например Конференц-зал и нажмите кнопку "Сохранить **изменения"**. Лицензия может отличаться в зависимости от организации.

Сведения об изменении параметров почтового ящика ресурсов см. [](#configure-mailbox-properties) в разделе "Настройка свойств почтового ящика" или в Exchange центра администрирования.

Вам также может потребоваться применить политики пропускной способности или политики собраний к этой учетной записи. [Дополнительные сведения см](#next-steps). в разделе "Дальнейшие действия".

#### <a name="with-exchange-online"></a>[**С Exchange Online**](#tab/exchange-online)

1. Подключение Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

    ``` PowerShell
    Connect-ExchangeOnline
    ```

2. По умолчанию почтовые ящики помещений не имеют связанных учетных записей. Добавьте учетную запись при создании почтового ящика помещения для проверки подлинности с помощью Microsoft Teams.

    Если вы создаете новый почтовый ящик ресурса:
    
    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID <Office365 ID> -Name <String> -Alias <string> -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
    ```
    
    В этом примере создается почтовый ящик помещения со следующими параметрами:

    - Учетная запись: ConferenceRoom01@contoso.com
          
    - Имя: ConferenceRoom01
        
     - Псевдоним: ConferenceRoom01
        
     - Пароль учетной записи: P@$$W 0rd5959

    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
    ```

Если вы не используете гибридную конфигурацию Exchange, можно перейти к следующему шагу — настройке [свойств почтового ящика](#configure-mailbox-properties).

Если вы используете гибридную конфигурацию Exchange, необходимо добавить адрес электронной почты для локальной учетной записи домена. Дополнительные сведения см. в статье ["Синхронизация локальных Office 365 учетных записей](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78) пользователей".

#### <a name="with-exchange-server"></a>[**С Exchange Server**](#tab/exchange-server)

  1. Подключение Exchange management Shell. [Откройте командную Exchange или](/powershell/exchange/exchange-server/open-the-exchange-management-shell) подключитесь к серверу Exchange [с помощью удаленной оболочки PowerShell](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).

   2. Чтобы создать почтовый ящик помещения:

      ``` PowerShell
      New-Mailbox -UserPrincipalName <UPN> -Name <String> -Alias <String> -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
      ```
     
   В этом примере создается почтовый ящик помещения со следующими параметрами:

   - Учетная запись: ConferenceRoom01@contoso.com
  
   - Имя: ConferenceRoom01

   - Псевдоним: ConferenceRoom01

   - Пароль учетной записи: P@$$W 0rd5959

   ``` PowerShell
   New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
   ```

#### <a name="modify-an-existing-exchange-room-mailbox"></a>[**Изменение существующего почтового ящика Exchange помещения**](#tab/existing-account)

Чтобы изменить существующий почтовый ящик помещения, чтобы он стал учетной записью ресурса, используйте следующий синтаксис:

``` PowerShell
Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
```

В этом примере включается учетная запись для существующего почтового ящика помещения с псевдонимом ConferenceRoom02 и устанавливается пароль 9898P@$$W 0rd.

``` PowerShell
Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
```

Если вы используете гибридную конфигурацию Exchange, вам также потребуется добавить адрес электронной почты для учетной записи локального домена. Дополнительные сведения см. в статье ["Синхронизация локальных Office 365 учетных записей](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78) пользователей".

Подробные сведения о синтаксисе и параметрах см. в разделах [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) и [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).

> [!NOTE]
> Если вы создаете эту учетную запись для Teams Room на Surface Hub, необходимо также включить ActiveSync для этой учетной записи. Это позволит отправлять сообщения электронной почты непосредственно из Surface Hub, которые можно использовать для таких функций, как доска. Дополнительные сведения см. в статье "Применение политик [ActiveSync](/surface-hub/apply-activesync-policies-for-surface-hub-device-accounts) к учетным записям устройств (Surface Hub)".

---

> [!IMPORTANT]
> Если вы используете эту учетную запись ресурса только для резервирования пространства и автоматически принимаете или отклоняете приглашения, настройка завершена. Если вы используете эту учетную запись ресурса для звонков по ТСОП, см[](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md). Microsoft Teams лицензии на надстройки, чтобы определить, какая лицензия требуется.
>
> Перейдите к следующему разделу, только если учетная запись ресурса предназначена для Комнаты Teams в Windows, Комнаты Teams на Android, Комнаты Teams в Surface Hub или Teams с горячим обслуживанием.

## <a name="configure-mailbox-properties"></a>Настройка свойств почтового ящика

В Exchange PowerShell в Сети или локальной среде настройте следующие параметры в почтовом ящике комнаты, чтобы улучшить взаимодействие с собранием:

- **AutomateProcessing: `AutoAccept`** Организаторы собраний получают решение о резервировании помещений напрямую без вмешательства человека.

- **AddOrganizerToSubject: `$false`** Организатор собрания не добавляется в тему приглашения на собрание.

- **DeleteComments: `$false`** Сохраните любой текст в тексте сообщения о входящих приглашениях на собрания. Это необходимо для обработки внешних Teams и сторонних собраний, чтобы обеспечить взаимодействие с One Touch Join.

- **DeleteSubject: `$false`** Оставьте тему входящих приглашений на собрание.

- **ProcessExternalMeetingMessages: `$true`** Указывает, следует ли обрабатывать приглашения на собрания, поступающие за Exchange организации. Требуется для внешних Teams собраний и [сторонних собраний](/microsoftteams/rooms/third-party-join).

- **RemovePrivateProperty: `$false`** Гарантирует, что закрытый флаг, отправленный организатором собрания в исходном приглашении на собрание, остается указанным.

- **AddAdditionalResponse: `$true`** Текст, указанный параметром AdditionalResponse, добавляется в приглашения на собрания.

- **AdditionalResponse: "Это Microsoft Teams конференц-зал!"** Дополнительный текст, добавляемый в ответ на принятие собрания.

В этом примере эти параметры настраиваются в почтовом ящике помещения с именем ConferenceRoom01:

``` PowerShell
Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -ProcessExternalMeetingMessages $true -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
```

Подробные сведения о синтаксисе и параметрах см [. в разделе Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

## <a name="turn-off-password-expiration"></a>Отключение срока действия пароля

Если срок действия пароля учетной записи ресурса истекает, устройство не будет выполнять вход после даты окончания срока действия. Затем пароль необходимо изменить для учетной записи ресурса, а затем обновить на каждом устройстве. Чтобы избежать этого, можно отключить срок действия пароля.
  
> [!NOTE]
> Для **общих устройств Microsoft Teams** установить срок действия пароля без Microsoft Teams срока действия. Если правила домена запрещают пароли, срок действия которых не истекает, необходимо создать исключение для каждой учетной записи Teams устройства.

Чтобы отключить срок действия пароля, выполните действия, описанные на одной из следующих вкладок:

#### <a name="azure-active-directory-20"></a>[**Azure Active Directory 2.0**](#tab/azure-active-directory2-password/)

Сначала Подключение в Active Directory PowerShell:

```PowerShell
   Connect-AzureAD
```

Затем см. раздел ["Установка бессрости пароля"](/microsoft-365/admin/add-users/set-password-to-never-expire?view=o365-worldwide#set-a-password-to-never-expire).

В этом примере пароль для учетной записи ConferenceRoom01@contoso.com срок действия не истекает.

```PowerShell
Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -PasswordPolicies DisablePasswordExpiration
```

#### <a name="azure-active-directory-10"></a>[**Azure Active Directory 1.0**](#tab/azure-active-directory1-password/)

 1. Подключение MSOnline PowerShell:

       ```PowerShell
       Connect-MsolService
       ```

       Дополнительные сведения об Active Directory см[. Azure Active Directory (MSOnline)](/powershell/azure/active-directory/overview?view=azureadps-1.0).

2. Задайте для пароля значение "Никогда не истекает", используя следующий синтаксис:

    ```PowerShell
    Set-MsolUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    В этом примере пароль для учетной записи ConferenceRoom01@contoso.com срок действия не истекает.

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -PasswordNeverExpires $true
    ```

#### <a name="active-directory-on-premises"></a>[**Active Directory (локальная среда)**](#tab/active-directory1-password/)

1. Подключение в Active Directory PowerShell:

    ```PowerShell
       Import-Module ActiveDirectory
    ```
    
    Дополнительные сведения об Active Directory PowerShell см. в [разделе ActiveDirectory](/powershell/module/activedirectory/?view=windowsserver2022-ps).

2. Задайте для пароля значение "Никогда не истекает", используя следующий синтаксис:

    ```PowerShell
    Set-ADUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    В этом примере пароль для учетной записи ConferenceRoom01@contoso.com срок действия не истекает.

    ```PowerShell
    Set-ADUser -Identity ConferenceRoom01@contoso.com -PasswordNeverExpires $true
    ```

---

## <a name="assign-a-meeting-room-license"></a>Назначение лицензии на конференц-зал

Учетной записи ресурса требуется Microsoft 365 или Office 365 для входа в Microsoft Teams.

> [!NOTE]
> Комнаты Microsoft Teams стандартный и Комнаты Microsoft Teams премиум доступны два номера SKU для общих устройств конференц-залов, включая Комнаты Teams. Лицензия на конференц-зал требуется для отображения Teams с помощью службы "Горячее обслуживание". Дополнительные сведения см[. в Teams конференц-залов](rooms-licensing.md).

Сведения о назначении лицензий с Центр администрирования Microsoft 365 см. в статье ["Назначение лицензий пользователям"](/microsoft-365/admin/manage/assign-licenses-to-users). Чтобы назначить лицензии с Azure AD, перейдите на одну из следующих вкладок:

#### <a name="active-directory-20"></a>[**Active Directory 2.0**](#tab/active-directory2-license/)


1. Подключение Azure AD
  
    ```PowerShell
    Connect-AzureAD
    ```

     Дополнительные сведения об Active Directory см. [в Azure Active Directory PowerShell для Graph](/powershell/azure/active-directory/overview?view=azureadps-2.0).
    
2. Назначьте расположение использования для учетной записи ресурса с помощью `Set-AzureADUser` командлета. Это определяет, какие номера SKU лицензий доступны.

    В этом примере пользователь находится в США (США):

    ```PowerShell
    Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -UsageLocation 'US'
    ```

3. Затем используйте для `Get-AzureADSubscribedSku` получения списка доступных номеров SKU для Microsoft 365 или Office 365 организации.

    ```PowerShell
    Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
    ```

4. Чтобы назначить лицензию, `Set-AzureADUser` используйте командлет и преобразуйте идентификатор номера SKU лицензии (см. шаг 2) в объект типа лицензии PowerShell. Затем назначьте этот объект учетной записи ресурса. В следующем примере идентификатором SKU лицензии является 6070a4c8-34c6-4937-8dfb-39bbc6397a60, и он назначается учетной записи conferenceroom01@contoso.com:

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

    Дополнительные сведения об Active Directory см. [в Azure Active Directory (MSOnline).](/powershell/azure/active-directory/overview?view=azureadps-1.0)

2.  Назначьте расположение использования для учетной записи ресурса с помощью `Set-MsolUser` командлета. Это определяет, какие номера SKU лицензий доступны.

    В этом примере пользователь находится в США (США).
    
    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
    ```
    
    Затем можно получить `Get-MsolAccountSku` список доступных номеров SKU для Microsoft 365 или Office 365 организации.

4. Чтобы назначить лицензию, используйте `Set-MsolUser` командлет. В этом примере лицензия contoso:MEETING_ROOM назначена учетной записи conferenceroom01@contoso.com:

    ```PowerShell
    Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM'
    ```

---

Чтобы проверить создание учетной записи и назначение лицензии, войдите в любой клиент Teams с помощью созданной учетной записи.

## <a name="next-steps"></a>Дальнейшие действия

### <a name="meeting-policies"></a>Политики собрания

К этой учетной записи может потребоваться применить настраиваемую сеть, пропускную способность или политики собраний. Дополнительные сведения о политиках сети и пропускной способности см. в разделе "Параметры политики собраний [" & видео](/microsoftteams/meeting-policies-audio-and-video). Для Комнаты Teams рекомендуется задать пропускную способность политики собраний в 10 Мбит/с.

В целях совместной работы включите PowerPoint Live, доску и общие заметки. Рекомендуется включить параметр политики собраний "Провести собрание сейчас в закрытых собраниях". Может потребоваться создать политику собраний для настройки параметров участников и гостей для Комнаты Teams. Например, просмотрите параметры "зал ожидания", например, какие участники будут автоматически допускаться на собрания. Дополнительные сведения о политиках Teams собраний см. в разделе "Управление политиками собраний[" Microsoft Teams](/microsoftteams/meeting-policies-overview).

### <a name="calling"></a>Звонки

Нет уникальных требований для включения вызовов с учетными записями ресурсов. Вы включаете учетную запись ресурса для вызова так же, как и обычный пользователь.

> [!NOTE]
> Мы рекомендуем отключить голосовую почту для общих устройств, назначив политику звонков учетным записям ресурсов устройств. [Дополнительные сведения см.](../teams-calling-policy.md) в разделе Teams вызовов и переадресации звонков.

### <a name="configure-distribution-groups-for-teams-calendar"></a>Настройка групп рассылки для Teams календаря

Чтобы упорядочить расположения конференц-залов, можно добавить учетные записи ресурсов устройств в Exchange группы рассылки. Например, если у вас есть офисы в трех разных географических расположениях, можно создать три группы рассылки и добавить соответствующие учетные записи ресурсов в каждое расположение. Дополнительные сведения см. в [разделе "Создание списка комнат"](/exchange/recipients/room-mailboxes?view=exchserver-2019#create-a-room-list).

### <a name="configure-places-for-outlook-calendar"></a>Настройка мест для Календарь Outlook
Чтобы расположения комнат собраний отображались в Outlook Room Finder, необходимо использовать командлет Set-Place Exchange PowerShell. Не только Set-Place заполнять поиск помещений в Outlook, но и добавлять дополнительные метаданные, такие как емкость комнаты или этаж здания комнаты. Дополнительные сведения см. в [разделе Set-Place](/powershell/module/exchange/set-place).

## <a name="related-articles"></a>Статьи по теме

[Настройка учетных записей для Комнаты Microsoft Teams](rooms-configure-accounts.md)

[Планирование комнат Microsoft Teams](rooms-plan.md)

[Развертывание комнат Microsoft Teams](rooms-deploy.md)

[Управление комнатами Microsoft Teams](rooms-manage.md)

[Комнаты Microsoft Teams лицензирования](rooms-licensing.md)
