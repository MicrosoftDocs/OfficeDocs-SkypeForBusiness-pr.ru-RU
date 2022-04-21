---
title: Изменение номеров телефонов в мосте аудиоконференций
ms.author: heidip
author: MicrosoftHeidi
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
description: Узнайте, как назначить новый номер телефона службы мосту конференций, чтобы расширить охват пользователей.
ms.openlocfilehash: 25af462ec7e531bdbaec01ee2a8b37c43376a48e
ms.sourcegitcommit: 296fbefe0481c0b8b94aee925118474375cdf138
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2022
ms.locfileid: "65016651"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>Изменение номеров телефонов для моста аудиоконференций

При покупке **лицензий** на аудиоконференции корпорация Майкрософт размещает мост аудиоконференций для вашей организации. Мост аудиоконференций предоставляет номера телефонов с телефонным подключением из разных расположений, чтобы организаторы и участники собрания могли использовать их для присоединения к собраниям Skype для бизнеса или Microsoft Teams собраниям с помощью телефона.
  
Помимо номеров телефонов, уже назначенных мосту конференц-связи, вы можете получить дополнительные номера [служб (](./getting-service-phone-numbers.md) платные и бесплатные номера, используемые для аудиоконференций) из других расположений, а затем назначить их мосту конференц-связи, чтобы расширить покрытие для пользователей.
  
> [!NOTE]
> Чтобы иметь возможность назначать или отменять назначение номера телефона для моста конференц-связи, номер телефона должен быть номером *службы*. Чтобы просмотреть тип  >  номера, перейдите к номерам голосовой Телефон **в** центре администрирования Microsoft Teams и просмотрите столбец **"Тип** номера". Microsoft 365 или Office 365 необходимо сначала настроить кредиты на связь, чтобы пользователи могли подключиться к мосту по бесплатному номеру.

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>Шаги для назначения нового служебного номера мосту конференц-связи

> [!NOTE]
> За исключением случаев, когда он вызывается в противном случае, все эти действия должны выполняться в Microsoft Teams администрирования.

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>Шаг 1. Назначение нового номера телефона мосту аудиоконференции

1. В области навигации слева перейдите к номерам **Телефон** >  **голосовой связи**.

2. Выберите номер телефона из списка и нажмите кнопку "Изменить **"**.

3. На странице **"Правка**" в **разделе "Назначено**" разверните раскрывающийся список и выберите **Conference** **bridgeApply** > .

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>Шаг 2. Изменение номера телефона по умолчанию для моста конференций (необязательно)

Номер телефона по умолчанию для моста конференций определяет идентификатор вызывающего абонента, который будет использоваться при размещении исходящего звонка участником или организатором из собрания.

В качестве номера по умолчанию для моста конференц-связи можно задать только платный номер службы. **Бесплатные номера службы не могут** быть заданы в качестве номера моста конференц-связи по умолчанию. Если вы назначаете платный номер службы и хотите задать его в качестве нового номера по умолчанию для моста аудиоконференций, выполните следующие действия:

1. В области навигации слева перейдите к **мостам MeetingsConference** > .

2. Выделите платный номер службы, который вы хотите настроить по умолчанию.

3. Выберите **По умолчанию**.

### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>Шаг 3. Изменение номеров телефонов по умолчанию, включенных в приглашения пользователей на собрания (необязательно)

Сведения о [настройке номеров телефонов, включенных в приглашения в Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).

> [!NOTE]
> Вы также можете задать номера телефонов, добавив их в *политику TeamsAudioconferencingpolicy* и назначив политику пользователям. Платные и бесплатные телефонные номера, добавленные в политику, имеют приоритет над номерами телефонов, заданные отдельно для пользователей через панель параметров аудиоконференций. Если в *Teamsaudioconferencingpolicy* не добавляются номера телефонов, номер телефона, заданный отдельно для пользователей с помощью области параметров аудиоконференций, будет отображаться в Microsoft Teams приглашениях на собрания. [Дополнительные сведения см. в](audio-conferencing-toll-free-numbers-policy.md) параметрах политики аудиоконференций для платных и бесплатных номеров.

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>Шаг 4. Обновление существующих приглашений пользователей на собрания с помощью службы переноса собраний (необязательно)

В первых двух шагах потребуется запустить Windows PowerShell.
  
Если вы обновили номера телефонов по умолчанию, включенные в приглашения на собрания для некоторых или всех пользователей, при необходимости можно обновить приглашения на собрания, которые уже были отправлены пользователям в вашей организации, прежде чем их номера телефонов по умолчанию были изменены с помощью службы переноса собраний. Дополнительные сведения см [. в разделе "Настройка службы миграции собраний (MMS)"](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
- Запустите службу перемещения собраний (MMS) для пользователей, у которых на шаге 2 были изменены номера телефонов по умолчанию. Для этого выполните следующую команду:

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- Также можно просмотреть состояние перемещения собрания. Когда не останется операций с состоянием  *Ожидает*  или *Выполняется*  , все собрания будут запланированы повторно.

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>Шаги для отмены назначения служебного номера мосту конференц-связи

После отмены назначения номера телефона мосту конференц-связи пользователи не смогут присоединяться к собраниям с его помощью. Так как номер телефона изменяется, важно обновить всех пользователей, у которых может быть номер телефона по умолчанию (если таковой имеется), и обновить существующие приглашения на собрания до того, как номер телефона не будет назначен мосту аудиоконференций.

Если номер телефона удаляется без обновления пользователей и их собраний, существующие приглашения на собрания могут содержать номер телефона, который не будет работать для присоединения к собраниям.

В первых трех шагах потребуется запустить Windows PowerShell. Чтобы узнать, как это сделать, щелкните "[Хотите узнать, как управлять с помощью Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>Шаг 1. Обновление пользователей, у которых номер телефона не назначен в качестве одного из номеров по умолчанию

Замените платный или бесплатный номер по умолчанию для всех пользователей, которым не назначен номер по умолчанию, и запустите процесс повторного планирования собраний. Для этого выполните следующую команду:

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```

 > [!IMPORTANT]
 >Вы также можете изменить платный или бесплатный номер пользователей по умолчанию в Microsoft Teams администрирования. Однако, это не повлечёт за собой автоматическую перепланировку их встреч.

 Дополнительные сведения см. [](set-the-phone-numbers-included-on-invites-in-teams.md) в разделе "Установка номеров телефонов, включенных в приглашения в Microsoft Teams" или "Настройка номеров телефонов, включенных в приглашения в Skype для бизнеса [Online"](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).

  > [!NOTE]
  > В зависимости от размера организации это может занять некоторое время.

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>Шаг 2. Просмотр состояния перемещения собрания с помощью Windows PowerShell

Все собрания будут перепланироваться после того, как операции не будут выполняться в состоянии *"* Ожидание" *или "Выполняется* ".

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

Дополнительные сведения о службе перемещения собраний см. в разделе [Настройка службы переноса собраний (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>Шаг 3. Отмена назначения старого номера телефона мосту аудиоконференции

Используйте командлет Unregister-CsOnlineDialInConferencingServiceNumber для отмены регистрации платного или бесплатного номера в мосте конференции.

```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -identity "toll number to be removed" -bridgeId "Conference Bridge ID"
Unregister-CsOnlineDialInConferencingServiceNumber -identity "toll free number to be removed" -bridgeId "Conference Bridge ID"
```

Примечание. Чтобы найти идентификатор моста конференции, выполните следующую команду PowerShell: Get-CsOnlineDialInConferencingBridge.

   > [!IMPORTANT]
   > После отмены назначения номера телефона для моста аудиоконференций, телефонный номер больше не будет доступен пользователям для подключения к новым или существующим собраниям.

### <a name="save-time-and-automate"></a>Экономия времени и автоматизация

Чтобы сэкономить время за счет автоматизации этого процесса, можно использовать [командлеты Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) или **Set-CsOnlineDialInConferencingUserDefaultNumber** .

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
    > Используемая выше папка должна соответствовать контактным данным пользователей, задаваемой в Центр администрирования Microsoft 365.

## <a name="troubleshooting"></a>Устранение неполадок

### <a name="the-unassign-button-isnt-available"></a>Кнопка "Отменить назначение" недоступна

Вы хотите отменить назначение номера, но кнопка недоступна, и при наведении на нее указателя мыши вы будете перенаправлены в службу поддержки со следующим сообщением: "Номера по умолчанию или общие номера нельзя отменить с моста. Чтобы отменить назначение выделенных платных номеров, обратитесь в службу поддержки".

Чтобы получить дополнительные сведения о мостах, выполните следующую команду PowerShell:

```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

Результат, помимо других сведений, таких как Identity, Name и Region, также должен содержать defaultServiceNumber.

**Например**, чтобы отменить назначение, значение DefaultServiceNumber "8005551234"

```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a>О Windows PowerShell

С помощью Windows PowerShell вы можете управлять пользователями и тем, что им можно и что нельзя делать. Windows PowerShell может помочь вам управлять Microsoft 365 или Office 365 и Skype для бизнеса Online с помощью единой точки администрирования, которая может упростить вашу ежедневную работу, особенно если у вас есть несколько задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.

- [Введение в Windows PowerShell и Skype для бизнеса Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

- [Шесть причин использовать Windows PowerShell для управления Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

Windows PowerShell имеет множество преимуществ в скорости, простоте и производительности по сравнению с использованием только Центр администрирования Microsoft 365 например, при одновременном внесении изменений в параметры для многих пользователей. Подробнее об этих преимуществах можно узнать в следующих разделах:

- [Лучшие способы управления Microsoft 365 Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))

- [Использование Windows PowerShell для управления Skype для бизнеса Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

- [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>Статьи по теме

[Изменение настроек для моста аудиоконференций](change-the-settings-for-an-audio-conferencing-bridge.md)
