---
title: Изменение номеров телефонов для моста аудио-конференций
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: В этой статье описаны действия, которые необходимо выполнить, чтобы назначить для моста конференц-связи новый служебный номер, чтобы расширить покрытие для пользователей.
ms.openlocfilehash: 307fe4839a96efa437ab08d8d5b674bb95bd7981
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814648"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>Изменение номеров телефонов для моста аудиоконференций

Если вы приобрели лицензии на **голосовую конференцию** , корпорация Майкрософт размещает ваш мост для голосовой связи в вашей организации. Мост видеоконференции предоставляет номера телефонов для телефонного подключения из различных местоположений, чтобы участники собрания организаторов и пользователи могли присоединяться к собраниям Skype для бизнеса или Microsoft Teams с помощью телефона.
  
Помимо номеров телефонов, уже назначенных для моста конференц-связи, вы можете [получить дополнительные служебные номера](/microsoftteams/getting-service-phone-numbers) (бесплатные и платные номера, используемые для голосовой конференции) из других источников, а затем назначить их мосту для Конференции, чтобы вы могли расширить покрытие для пользователей.
  
> [!NOTE]
> Чтобы назначить или отменить назначение номера телефона для моста конференц-связи, номер телефона должен быть номером*услуги*. Тип номера можно узнать, перейдя на номера **голосовых**  >  **телефонов** на портале Legacy и просматривая столбец **тип номера** . Для того чтобы пользователи настроили связь с мостом на бесплатный номер, необходимо сначала настроить Microsoft 365 или Office 365.

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>Шаги для назначения нового служебного номера мосту конференц-связи

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>Шаг 1. Назначение нового номера телефона мосту аудиоконференции

1. Войдите в Microsoft 365 или Office 365 с помощью своей рабочей учетной записи.

2. Перейдите в раздел центры администрирования **центра администрирования Microsoft 365**  >  **Admin centers**  >  **Teams &**  >  **Legacy portal**  >  **Voice**  >  **номера телефонов**Skype Legacy Portal.

3. Выберите номер телефона в списке, затем на панели действий нажмите кнопку **Назначить**.

4. На странице **Назначение** щелкните **Сохранить**.

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>Шаг 2: изменение номера телефона по умолчанию для моста конференц-связи (необязательно)

Номер телефона, используемый по умолчанию для моста конференц-связи, определяет идентификатор вызывающего абонента, который будет использоваться, когда исходящий звонок помещается участником или организатором в рамках собрания.

В качестве номера по умолчанию для моста конференц-связи может быть установлен только платный номер Услуги. Бесплатный **номер Услуги нельзя использовать в качестве номера по умолчанию для моста Конференц-** связи. Если вы назначаете номер сервисного обслуживания и хотите использовать его в качестве нового номера по умолчанию для вашего моста видеоконференций, выполните указанные ниже действия.

1. Войдите в Microsoft 365 или Office 365 с помощью своей рабочей учетной записи.

2. Перейдите в раздел центры администрирования **центра администрирования Microsoft 365**  >  **Admin centers**  >  **Teams &**  >  мосты Skype для**собраний**по  >  **конференциям**.

3. Выберите платный номер, который вы хотите настроить по умолчанию.

4. Выберите **По умолчанию**.
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>Шаг 3. Измените номера телефона по умолчанию, которые включены в приглашения на собрания пользователей (необязательно).

Номера телефонов по умолчанию для пользователей — это те, которые включаются в приглашения на собрания при планировании собрания. Дополнительные сведения, в том числе назначение номера телефона по умолчанию для новых пользователей, приведены в разделе [Настройка номеров телефонов, включенных в приглашения в Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) , или [Установка номеров телефонов, включенных в приглашения в Skype для бизнеса Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).
  
1. Войдите в свою рабочую или учебную учетную запись.

2. Перейдите в центр администрирования **центра администрирования Microsoft 365**  >  **Admin centers**  >  **Teams &**  >  **Legacy portal**  >  **Audio conferencing**  >  **Users**и выберите пользователей в списке.

3. Нажмите кнопку **Изменить** на панели действий.

4. Под заголовком **Платный номер по умолчанию** или **Бесплатный номер по умолчанию** выберите номер в списке и нажмите кнопку **Сохранить**.

После сохранения изменений новые номера телефонов по умолчанию будут включены в приглашения на новые собрания при их планировании.

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>Шаг 4: обновление существующих приглашений на собрания для пользователей с помощью службы миграции собраний (необязательно)

В первых двух шагах потребуется запустить Windows PowerShell.
  
Если вы обновили номера телефонов по умолчанию, которые включены в приглашения на собрания для некоторых или всех пользователей, вы можете также обновить приглашения на собрания, которые уже были отправлены пользователям в вашей организации, прежде чем они будут изменены с помощью службы миграции собраний. Дополнительные сведения можно найти [в разделе Настройка службы миграции собраний (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
- Запустите службу перемещения собраний (MMS) для пользователей, у которых на шаге 2 были изменены номера телефонов по умолчанию. Для этого выполните следующую команду:

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- Также можно просмотреть состояние перемещения собрания. Когда не останется операций с состоянием  *Ожидает*  или *Выполняется*  , все собрания будут запланированы повторно.

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>Шаги для отмены назначения служебного номера мосту конференц-связи


После отмены назначения номера телефона мосту конференц-связи пользователи не смогут присоединяться к собраниям с его помощью. Так как номер телефона меняется, важно обновить всех пользователей, которые могут использовать номер телефона в качестве номера по умолчанию (если таковые имеются), а также обновить существующие приглашения на собрания, прежде чем номер телефона будет отменен из моста голосовых конференций.

Если номер телефона удален без обновления пользователей и собраний, они могут содержать номер телефона, который не подходит для присоединения к собраниям.

В первых трех шагах потребуется запустить Windows PowerShell. Сведения о том, как это сделать, можно найти в статье [Управление с помощью Windows PowerShell](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>Шаг 1. Обновите список пользователей, которым назначен номер телефона, по умолчанию в качестве одного из значений

Замените платный или бесплатный номер по умолчанию для всех пользователей, которые имеют номер, назначенный по умолчанию, и начните повторное Планирование собраний. Для этого выполните следующую команду:

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >Вы также можете изменить платный или бесплатный номер по умолчанию в центре администрирования Skype для бизнеса. Однако, это не повлечёт за собой автоматическую перепланировку их встреч. 
 
 Дополнительные сведения можно найти в разделе [Настройка номеров телефонов, включенных в приглашения в Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) , или [Установка номеров телефонов, включенных в приглашения в Skype для бизнеса Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).

  > [!NOTE]
  > В зависимости от размера организации это может занять некоторое время.

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>Шаг 2. Просмотр состояния перемещения собрания с помощью Windows PowerShell

Все собрания будут перепланированы после того, как в *ожидании* или *в состоянии выполнения* нет никаких операций.

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

Дополнительные сведения о службе перемещения собраний см. в разделе [Настройка службы переноса собраний (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>Шаг 3. Отмена назначения старого номера телефона мосту аудиоконференции

1. Войдите в свою рабочую или учебную учетную запись.

2. Перейдите в центр администрирования **центра администрирования Microsoft 365**  >  **Admin centers**  >  **группы &**  >  **Legacy portal**  >  **Voice**  >  **номера телефонов**Skype Legacy Portal.

3. Если номер телефона – бесплатный номер, выберите номер телефона в списке, а затем на панели действий нажмите кнопку **Отменить назначение**. Если номер телефона — платный номер, обратитесь в [службу поддержки Майкрософт](https://go.microsoft.com/fwlink/?linkid=2091806) , чтобы номер телефона не был назначен.

4. Если номер телефона – бесплатный номер, нажмите кнопку **Да** в окне подтверждения.

   > [!IMPORTANT]
   > После отмены назначения номера телефона для моста аудиоконференций, телефонный номер больше не будет доступен пользователям для подключения к новым или существующим собраниям.

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell
<a name="bkPowerShell"> </a>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a>Проверка готовности Windows PowerShell

 Эти действия предназначены для того, чтобы убедиться в том, что вы используете Windows PowerShell версии 3,0 или выше.

1. Введите **меню «Пуск»** > **Windows PowerShell**.

2. Введите _Get-Host_ в окне **Windows PowerShell** для проверки версии.

3. Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell. Чтобы скачать и обновить Windows PowerShell до версии 4,0, ознакомьтесь с разгрузкой [платформы Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) .
При появлении запроса перезагрузите компьютер.

4. Кроме того, необходимо установить модуль Windows PowerShell для Skype для бизнеса Online, который позволяет создавать удаленные сеансы Windows PowerShell, которые подключаются к Skype для бизнеса Online. Этот модуль поддерживается только на 64-разрядных компьютерах и может быть скачан из центра загрузки Майкрософт в [модуле Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).
При появлении запроса перезагрузите компьютер.

Дополнительные сведения можно найти в разделе [подключение ко всем службам Microsoft 365 или Office 365 в одном окне Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).

### <a name="to-start-windows-powershell"></a>Запуск Windows PowerShell

 **Запуск сеанса Windows PowerShell**

1. From the **Start Menu** > **Windows PowerShell**.

2. В окне **Windows PowerShell** подключитесь к Microsoft 365 или Office 365, выполнив следующие действия:

> [!NOTE]
> Skype для бизнеса Online уже входит в состав последнего модуля PowerShell для Teams.
>
> Если вы используете последнюю версию [общедоступной оболочки для Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), вам не нужно устанавливать соединитель Skype для бизнеса Online.

>
  ```PowerShell
    Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

> [!NOTE]
> Команду **Import-Module** нужно запускать только при первом использовании модуля Windows PowerShell в Skype для бизнеса Online.
Если вы хотите получить дополнительные сведения о запуске Windows PowerShell, ознакомьтесь со статьей [подключение ко всем службам Microsoft 365 или Office 365 в одном окне Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) или [Подключение к Skype для бизнеса Online с помощью Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).

### <a name="save-time-and-automate"></a>Экономия времени и автоматизация

Для экономии времени путем автоматизации процесса можно воспользоваться командлетами [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) или **Set-CsOnlineDialInConferencingUserDefaultNumber** .

- Используйте командлет [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) для изменения платного или бесплатного номера по умолчанию для определенных пользователей.

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
    > Указанное выше расположение должно совпадать с контактными данными пользователей, которые настроены в центре администрирования Microsoft 365.

## <a name="troubleshooting"></a>Устранение неполадок

**Кнопка отмены назначения недоступна**

Вы хотите отменить назначение номера, но кнопка недоступна, и при наведении указателя мыши на него вы будете перенаправлены в службу поддержки со следующим сообщением: _"по умолчанию или общие номера могут быть отменены из моста. Чтобы отменить присвоение специальных платных номеров, обратитесь в службу поддержки._".

Чтобы получить дополнительные сведения о мостах, выполните указанные ниже действия PowerShell.
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

Результат, помимо других данных, таких как идентификация, имя и регион, должен содержать DefaultServiceNumber.

**Например**, для отмены назначения DefaultServiceNumber "8005551234"
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a>О Windows PowerShell

С помощью Windows PowerShell вы можете управлять пользователями и тем, что им можно и что нельзя делать. Windows PowerShell поможет вам управлять Microsoft 365 или Office 365 и Skype для бизнеса Online с помощью одной точки администрирования, которая позволяет упростить повседневную работу, особенно если вам нужно выполнить несколько задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.

  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Шесть причин использовать Windows PowerShell для управления Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell обладает многими преимуществами для ускорения, простоты и продуктивности с помощью центра администрирования Microsoft 365, например при одновременном изменении параметров для нескольких пользователей. Подробнее об этих преимуществах можно узнать в следующих разделах:

  - [Лучшие способы управления Microsoft 365 и Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>См. также
[Изменение настроек для моста аудиоконференций](change-the-settings-for-an-audio-conferencing-bridge.md)
