---
title: Изменение номеров телефонов на мосте аудиоконференции
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Узнайте, как назначить новый номер телефона службы мосту конференц-связи, чтобы расширить покрытие для пользователей.
ms.openlocfilehash: f39a963759e768f4fab70d2a06e6d90b480699e0
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2021
ms.locfileid: "60536720"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>Изменение номеров телефонов для моста аудиоконференций

При покупке **лицензий на** аудиоконференцию корпорация Майкрософт принимает ваш мост аудиоконференции для вашей организации. Мост аудиоконференации предоставляет номера телефонов для телефонного звонка из разных мест, чтобы организаторы и участники собрания могли использовать их для пользования Skype для бизнеса или Microsoft Teams собраниям по телефону.
  
Помимо номеров телефонов, уже назначенных мосту для аудиоконференции, вы можете получить дополнительные [номера](./getting-service-phone-numbers.md) служб (платные и бесплатные номера, используемые для аудиоконференации) из других мест, а затем назначить их мосту для аудиоконференации, чтобы расширить покрытие для пользователей.
  
> [!NOTE]
> Чтобы можно было назначить или отозначить номер телефона для моста услуг, номер телефонадолжен быть номером службы . Чтобы узнать тип номера, переведите номера голосовой Телефон в центре администрирования Microsoft Teams и посмотрите в столбце  >   **Тип** номера. Microsoft 365 или Office 365 кредиты на связь необходимо сначала настроить, чтобы пользователи смогут звонить на мост по бесплатному номеру.

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>Шаги для назначения нового служебного номера мосту конференц-связи

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>Шаг 1. Назначение нового номера телефона мосту аудиоконференции

 **С помощью Центра администрирования Microsoft Teams**

1. В области навигации слева перейдите к **голосовой** Телефон  >  **номера.**

2. Выберите номер телефона в списке и нажмите кнопку **Изменить**.

3. На странице **Редактирование** в области **Назначено** раз развернуть список и выберите Мост **конференции**  >  **Применить**.

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>Шаг 2. Изменение номера телефона по умолчанию для моста конференц-связи (необязательно)

Номер телефона по умолчанию для моста конференц-связи определяет ИД звоня, который будет использоваться при размещении исходячего звонка участником или организатором в рамках собрания.

В качестве номера по умолчанию для моста услуг можно установить только платный номер службы. **Бесплатные номера службы** нельзя сделать номером по умолчанию для моста услуг. Если вы назначаете платный номер службы и хотите сделать его новым номером по умолчанию для моста аудиоконференций, выполните следующие действия:

 **С помощью Центра администрирования Microsoft Teams**

1. В области навигации слева перейдите к **мосту Конференц-связь**  >  **собраний**.

2. Выделим платный номер службы, который вы хотите сделать номером по умолчанию.

3. Выберите **По умолчанию**.
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>Шаг 3. Изменение номеров телефонов по умолчанию, включенных в приглашения пользователей на собрания (необязательно)

Телефонные номера пользователей по умолчанию включаются в приглашения на собрания при их расписании. Дополнительные сведения, в том числе о том, как [](set-the-phone-numbers-included-on-invites-in-teams.md) новым пользователям назначены номера телефонов по умолчанию, см. в Microsoft Teams или Настройка номеров телефонов, включенных в приглашения в [Skype для бизнеса Online.](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)

 **С помощью Центра администрирования Microsoft Teams**

1. В области навигации слева перейдите к списку **Пользователи** и щелкните отображаемого имени нужного пользователя в списке.

2. Рядом с **кнопкой Аудиоконференция** **щелкните** Изменить .

3. В **области Платный** **номер** или Бесплатный номер выберите номер из dropdown и нажмите кнопку **Применить**.

После внесения изменений новые номера телефонов по умолчанию будут включены в приглашения организаторов при следующем расписании нового собрания.

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>Шаг 4. Обновление существующих приглашений пользователей на собрания с помощью службы переноса собраний (необязательно)

В первых двух шагах потребуется запустить Windows PowerShell.
  
Если вы обновили номера телефонов по умолчанию, включенные в приглашения на собрания для некоторых или всех пользователей, вы можете при желании обновить приглашения на собрания, которые уже были отправлены пользователям в вашей организации до изменения их номеров телефонов по умолчанию с помощью службы переноса собраний. Дополнительные сведения см. в настройках службы [переноса собраний (MMS).](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
  
- Запустите службу перемещения собраний (MMS) для пользователей, у которых на шаге 2 были изменены номера телефонов по умолчанию. Для этого выполните следующую команду:

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- Также можно просмотреть состояние перемещения собрания. Когда не останется операций с состоянием  *Ожидает*  или *Выполняется*  , все собрания будут запланированы повторно.

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>Шаги для отмены назначения служебного номера мосту конференц-связи


После отмены назначения номера телефона мосту конференц-связи пользователи не смогут присоединяться к собраниям с его помощью. Так как номер телефона изменяется, важно обновить всех пользователей, у которых может быть номер телефона по умолчанию (если он есть), и обновить существующие приглашения на собрания до того, как этот номер не будет назначен мосту аудиоконференции.

Если удалить номер телефона без обновления пользователей и собраний, существующие приглашения на собрания могут содержать номер телефона, который не будет работать для присоединения к собраниям.

В первых трех шагах потребуется запустить Windows PowerShell. Чтобы узнать, как это сделать, нажмите кнопку Хотите узнать, как управлять [с помощью Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>Шаг 1. Обновление пользователей, у которых номер телефона не назначен в качестве одного из номеров по умолчанию

Замените платный или бесплатный номер по умолчанию для всех пользователей, которым этот номер не назначен, и начните процедуру повторного планирования собраний. Для этого выполните следующую команду:

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >Вы также можете изменить платный или бесплатный номер по умолчанию для пользователей в Microsoft Teams центре администрирования. Однако, это не повлечёт за собой автоматическую перепланировку их встреч. 
 
 Дополнительные сведения [](set-the-phone-numbers-included-on-invites-in-teams.md) см. в настройках номеров телефонов, включенных в приглашения в Microsoft Teams или Настройка номеров телефонов, включенных в приглашения в [Skype для бизнеса Online.](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)

  > [!NOTE]
  > В зависимости от размера организации это может занять некоторое время.

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>Шаг 2. Просмотр состояния перемещения собрания с помощью Windows PowerShell

Все собрания будут запланированы повторно, если  не будет операций в состоянии Ожидание или *Идет работа.*

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

Дополнительные сведения о службе перемещения собраний см. в разделе [Настройка службы переноса собраний (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>Шаг 3. Отмена назначения старого номера телефона мосту аудиоконференции

Используйте Unregister-CsOnlineDialInConferencingServiceNumber для регистрации платного или бесплатного номера в мосте конференции

```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -identity "toll number to be removed" -bridgeId "Conference Bridge ID"
Unregister-CsOnlineDialInConferencingServiceNumber -identity "toll free number to be removed" -bridgeId "Conference Bridge ID"
```
Примечание. Чтобы найти ИД моста конференц-залов, запустите следующую версию PowerShell: Get-CsOnlineDialInConferencingBridge.


   > [!IMPORTANT]
   > После отмены назначения номера телефона для моста аудиоконференций, телефонный номер больше не будет доступен пользователям для подключения к новым или существующим собраниям.

### <a name="save-time-and-automate"></a>Экономия времени и автоматизация

Чтобы сэкономить время за счет автоматизации этого процесса, вы можете [использоватьлеты Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) или **Set-CsOnlineDialInConferencingUserDefaultNumber.**

- Используйте командлет [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) для изменения платного или бесплатного номера по умолчанию для определенных пользователей.

  - Чтобы изменить бесплатный номер по умолчанию для определенного пользователя, выполните командлет

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- Используйте командлет **Set-CsOnlineDialInConferencingUserDefaultNumber** для изменения платного или бесплатного номера по умолчанию для пользователей на основе исходного номера по умолчанию, свойственного для местоположения этих пользователей.

    > [!NOTE]
    > Чтобы узнать идентификатор BridgeID, используйте командлет **Get-CsOnlineDialInConferencingBridge**.

  - Чтобы задать бесплатный номер 8005551234 в качестве номера по умолчанию для всех пользователей, не имеющих номера по умолчанию, выполните командлет

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Чтобы изменить бесплатный номер по умолчанию для всех пользователей с бесплатным номером по умолчанию 8005551234 на 8005551239 и автоматически повторно запланировать собрания, выполните командлет:

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - Чтобы задать бесплатный номер 8005551234 в качестве номера по умолчанию для всех пользователей, находящихся в США, и автоматически повторно запланировать собрания, выполните командлет:

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > Используемая выше информация должна соответствовать контактным данным пользователей, заданная в Центр администрирования Microsoft 365.

## <a name="troubleshooting"></a>Устранение неполадок

**Кнопка "Отогнать" недоступна**

Вы хотите отопределить номер, но кнопка недоступна, и если наведите на нее курсор, вы будете перенаправлены в службу поддержки со следующим сообщением: "От моста нельзя отоделить номера по умолчанию или общие _номера. Чтобы отоименовать выделенные платные номера, обратитесь в службу поддержки."_

Чтобы получить дополнительные сведения о мосте, запустите следующую powershell:
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

Результат, кроме других сведений, таких как Identity, Name и Region, также должен содержать номер DefaultServiceNumber.

**Пример**, чтобы отоброть, defaultServiceNumber "8005551234"
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a>О Windows PowerShell

С помощью Windows PowerShell вы можете управлять пользователями и тем, что им можно и что нельзя делать. Windows PowerShell вы можете управлять Microsoft 365 или Office 365 и Skype для бизнеса Online с помощью единого портала администрирования, который упростит вашу повседневную работу, особенно если вам нужно сделать несколько задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.

  - [Введение в Windows PowerShell и Skype для бизнеса Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Шесть причин использовать Windows PowerShell для управления Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центр администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:

  - [Лучшие способы управления Microsoft 365 Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))

  - [Использование Windows PowerShell для управления Skype для бизнеса Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>Статьи по теме
[Изменение настроек для моста аудиоконференций](change-the-settings-for-an-audio-conferencing-bridge.md)
