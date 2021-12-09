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
ms.openlocfilehash: 8f8511f4dd05b6d2eb073aaab0a14305c9d67831
ms.sourcegitcommit: 1165a74b1d2e79e1a085b01e0e00f7c65483d729
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/08/2021
ms.locfileid: "61355638"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Развертывание комнаты Microsoft Teams с Exchange Online

Дополнительные сведения о развертывании Комнаты Microsoft Teams с помощью Exchange Online.
  
Если в вашей организации есть несколько служб( одни из них — локально, а другие — в Интернете), то конфигурация будет зависеть от того, где именно находится та или иная служба. В этой теме описывается гибридное развертывание Комнаты Microsoft Teams с Exchange размещены в Интернете. Так как в развертывании такого типа много разных вариантов, предоставить подробные инструкции для всех из них невозможно. Этот процесс будет работать для многих конфигураций. Если процесс не подстроен для настройки, рекомендуем использовать Windows PowerShell, чтобы получить такой же конечный результат, как описано здесь, а также для других вариантов развертывания.

## <a name="requirements"></a>Требования

Прежде чем Комнаты Microsoft Teams с Exchange Online, убедитесь, что выполнены требования. Дополнительные сведения см. в Комнаты Microsoft Teams [требованиях.](requirements.md)
  
Чтобы развернуть Комнаты Microsoft Teams с Exchange Online, выполните следующие действия. Убедитесь в том, что у вас есть необходимые разрешения для выполнения соответствующих командлетов. 

   > [!NOTE]
   >  Модуль Azure Active Directory для [Windows PowerShell](/powershell/azure/active-directory/overview) в этом разделе (например, Set-MsolUser) был протестирован при настройке учетных записей для Комнаты Microsoft Teams устройств. Возможно, другие cmdlets могут работать, но они не были протестированы в этом конкретном сценарии.

Если вы развернули службы федерации Active Directory (AD FS), вам может потребоваться преобразовать учетную запись пользователя в управляемого пользователя, прежде чем выполнять эти действия, а затем преобразовать пользователя обратно в федератора.
  
### <a name="create-an-account-and-set-exchange-properties"></a>Создание учетной записи и настройка свойств Exchange

1. Начните сеанс удаленного Windows PowerShell на компьютере и подключите Exchange Online:

    ``` Powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline
    ```

2. После создания сеанса вы либо создайте новый почтовый ящик, чтобы включить его в качестве учетной записи RoomMailboxAccount, либо измените параметры существующего почтового ящика комнаты. Это позволит учетной записи в Комнаты Microsoft Teams.

   Изменение существующего почтового ящика ресурса:

   ``` Powershell
   Set-Mailbox -Identity 'ConferenceRoom01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Если вы создаете новый почтовый ящик ресурса:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'ConferenceRoom01@contoso.com' -Alias ConferenceRoom01 -Name "Conference Room 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Чтобы улучшить собрание, необходимо настроить свойства Exchange для учетной записи пользователя следующим образом:

   ``` Powershell
   Set-CalendarProcessing -Identity 'ConferenceRoom01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'ConferenceRoom01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>Добавление адреса электронной почты для локальной учетной записи домена

1. В **средстве Active Directory Users and Computers AD** щелкните правой кнопкой мыши контейнер или организационную единицу, в котором будут созданы учетные записи Комнаты Microsoft Teams, нажмите кнопку Создать **и** выберите пользователь **.**
2. В поле Полное имя введите отображаемого имени (-Identity) из предыдущего  команды (Set-Mailbox или New-Mailbox) и псевдоним в поле Имя пользователя.  Нажмите кнопку **Далее**.
3. Введите пароль учетной записи. Подтвердите пароль. Убедитесь, что выбран только параметр **Срок действия пароля не ограничен**.

    > [!NOTE]
    > Выбор пароля **сроком действия не истекает** — это требование для Skype для бизнеса Server в Комнаты Microsoft Teams. В некоторых случаях пароли с неограниченным сроком действия могут быть запрещены правилами домена. В этом случае необходимо создать исключение для каждой учетной записи Комнаты Microsoft Teams пользователя.
  
4. Чтобы создать учетную запись, нажмите кнопку **Готово**.
5. После создания учетной записи запустите синхронизацию каталогов. Для этого можно использовать [set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration) в PowerShell. После этого перейдите на страницу пользователи и убедитесь, что две учетные записи, созданные на предыдущих шагах, объединены.

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Назначение лицензии Microsoft 365 или Office 365 лицензии

1. Сначала подключите Azure AD, чтобы применить некоторые параметры учетной записи. Для подключения можно использовать следующий командлет. Подробные сведения об Active Directory см. в [azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview)

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview) не поддерживается.

    ``` PowerShell
   Connect-MsolService
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. У учетной записи пользователя должна быть действительная Microsoft 365 или Office 365, чтобы Exchange работать. При наличии лицензии вам необходимо назначить учетной записи устройства место использования, которое определяет, какие номера SKU лицензий будут доступны вашей учетной записи. Задание будет выполняться в следующем шаге.
3. Затем используйте `Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> , чтобы получить список доступных skUs для вашей Microsoft 365 или Office 365 организации.
4. Вы можете добавить лицензию с помощью `Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> Командлет. В этом случае применяется Комнаты Microsoft Teams стандартный лицензия. 

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
    Get-MsolAccountSku
    Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses "contoso:MEETING_ROOM"
    ```
  <!--   ``` Powershell
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
     Get-AzureADSubscribedSku
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
     ``` -->

## <a name="related-topics"></a>Статьи по теме

[Настройка учетных записей для Комнаты Microsoft Teams](rooms-configure-accounts.md)

[Планирование комнат Microsoft Teams](rooms-plan.md)
  
[Развертывание комнат Microsoft Teams](rooms-deploy.md)
  
[Настройка консоли комнат Microsoft Teams](console.md)
  
[Управление комнатами Microsoft Teams](rooms-manage.md)
