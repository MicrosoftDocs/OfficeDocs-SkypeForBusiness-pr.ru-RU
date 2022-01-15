---
title: Развертывание комнаты Microsoft Teams с Exchange Online
ms.author: v-lanac
author: lanachin
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
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Дополнительные сведения о развертывании Комнаты Microsoft Teams с помощью Exchange Online.
ms.openlocfilehash: e6eb3253d7edb999ba74d28ef9a6d8ae835ac16d
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055489"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Развертывание комнаты Microsoft Teams с Exchange Online

Дополнительные сведения о развертывании Комнаты Microsoft Teams с помощью Exchange Online.
  
Если в вашей организации есть несколько служб( одни из них — локально, а другие — в Интернете), то конфигурация будет зависеть от того, где именно находится та или иная служба. В этой теме описывается гибридное развертывание Комнаты Microsoft Teams с Exchange размещены в Интернете. Так как в развертывании такого типа много разных вариантов, предоставить подробные инструкции для всех из них невозможно. Этот процесс будет работать для многих конфигураций. Если процесс не подстроен для настройки, рекомендуем использовать Windows PowerShell, чтобы получить такой же конечный результат, как описано здесь, а также для других вариантов развертывания.

## <a name="requirements"></a>Требования

Прежде чем Комнаты Microsoft Teams с Exchange Online, убедитесь, что выполнены требования. Дополнительные сведения см. в Комнаты Microsoft Teams [требованиях.](requirements.md)
  
Чтобы развернуть Комнаты Microsoft Teams с Exchange Online, выполните следующие действия: Убедитесь, что у вас есть права на запуск cmdlets. 

   > [!NOTE]
   >  Модуль Azure Active Directory для [Windows PowerShell](/powershell/azure/active-directory/overview?view=azureadps-1.0) в этом разделе (например, Set-MsolUser) был протестирован при настройке учетных записей для Комнаты Microsoft Teams. Возможно, другие cmdlets могут работать, но они не были протестированы в этом конкретном сценарии.

Если вы развернули службы федерации Active Directory (AD FS), вам может потребоваться преобразовать учетную запись пользователя в управляемого пользователя, прежде чем выполнять эти действия, а затем преобразовать пользователя обратно в федератора.
  
### <a name="create-an-account-and-set-exchange-properties"></a>Создание учетной записи и настройка свойств Exchange

1. Начните сеанс удаленного Windows PowerShell на компьютере и подключите его к Exchange Online следующим образом:

    ``` Powershell
   Connect-ExchangeOnline
    ```

2. После создания сеанса вы либо создайте новый почтовый ящик, чтобы включить его в качестве учетной записи RoomMailboxAccount, либо измените параметры существующего почтового ящика комнаты. Это позволит учетной записи в Комнаты Microsoft Teams.

   Изменение существующего почтового ящика ресурса:

   ``` Powershell
   Set-Mailbox -Identity 'ConferenceRoom01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Если вы создаете новый почтовый ящик ресурса:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'ConferenceRoom01@contoso.com' -Alias ConferenceRoom01 -Name 'ConferenceRoom01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Чтобы улучшить собрание, необходимо настроить свойства Exchange для учетной записи пользователя следующим образом:

   ``` Powershell
   Set-CalendarProcessing -Identity 'ConferenceRoom01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'ConferenceRoom01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Rooms enabled  room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>Добавление адреса электронной почты для локальной учетной записи домена

1. В **средстве Active Directory Users and Computers AD** щелкните правой кнопкой мыши контейнер или организационную единицу, в котором будут созданы учетные записи Комнаты Microsoft Teams, нажмите кнопку Создать **и** выберите пользователь **.**
2. В поле Полное имя введите отображаемого имени (-Identity) из предыдущего  команды (Set-Mailbox или New-Mailbox) и псевдоним в поле Имя пользователя.  Нажмите кнопку **Далее**.
3. Введите пароль учетной записи. Подтвердите пароль. Убедитесь, что выбран только параметр **Срок действия пароля не ограничен**.

    > [!NOTE]
    > Для **этого необходимо выбрать пароль без** Комнаты Microsoft Teams. В некоторых случаях пароли с неограниченным сроком действия могут быть запрещены правилами домена. В этом случае необходимо создать исключение для каждой учетной записи Комнаты Microsoft Teams пользователя.
  
4. Чтобы создать учетную запись, нажмите кнопку **Готово**.
5. После создания учетной записи запустите синхронизацию каталогов. Для этого можно использовать [set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) в PowerShell. После этого перейдите на страницу пользователя и убедитесь, что две учетные записи, созданные на предыдущих шагах, объединены.

### <a name="assign-an-office-365-license"></a>Назначение лицензии Office 365

1. Сначала подключите Azure AD, чтобы применить некоторые параметры учетной записи. Для подключения можно использовать следующий командлет. Подробные сведения об Active Directory см. в [azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0)

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) не поддерживается.

    ``` PowerShell
   Connect-MsolService
    ```

2. Для подключения к Office 365 учетной записи пользователя должна быть действительная Microsoft Teams. При наличии лицензии вам необходимо назначить учетной записи устройства место использования, которое определяет, какие номера SKU лицензий будут доступны вашей учетной записи.
3. Используйте get-MsolAccountSku, чтобы получить список доступных skus для Office 365 клиента.
4. После добавления номеров номеров номеров ВК можно добавить лицензию с помощью 'Set-MsolUserLicense'. <!-- Set-AzureADUserLicense--> Командлет. 

    ```PowerShell
     Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
     Get-MsolAccountSku
     Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM
    ```

## <a name="validate"></a>Проверить

Для проверки вы можете войти в созданную учетную запись с помощью Microsoft Teams клиента.
  
## <a name="see-also"></a>См. также

[Обновление почтовых ящиков помещений с помощью дополнительных метаданных для улучшения поиска и предложения помещений](/powershell/module/exchange/set-place)

[Настройка учетных записей для Комнаты Microsoft Teams](rooms-configure-accounts.md)

[Планирование комнат Microsoft Teams](rooms-plan.md)
  
[Развертывание комнат Microsoft Teams](rooms-deploy.md)
  
[Настройка консоли комнат Microsoft Teams](console.md)
  
[Управление комнатами Microsoft Teams](rooms-manage.md)
