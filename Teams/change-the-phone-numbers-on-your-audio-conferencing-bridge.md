---
title: Изменение номеров телефонов для моста аудиоконференций
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: При покупке лицензий аудиоконференций для Skype для бизнеса корпорация Майкрософт предоставит вашей организации мост аудиоконференции . Мост аудиоконференции предоставляет номера телефонов для подключения из различных мест, так что организаторы и участники собрания могут использовать их, чтобы присоединяться к собраниям Skype для бизнеса или Microsoft Teams с помощью телефона.
ms.openlocfilehash: 178bafb7327fa4734a5f743c4a2eebdab07fc0d9
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2018
ms.locfileid: "23783216"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>Изменение номеров телефонов для моста аудиоконференций

[] При покупке лицензий **аудиоконференций для Skype для бизнеса** корпорация Майкрософт предоставит вашей организации *мост аудиоконференции*  . Мост аудиоконференции предоставляет номера телефонов для подключения из различных мест, так что организаторы и участники собрания могут использовать их, чтобы присоединяться к собраниям Skype для бизнеса или Microsoft Teams с помощью телефона.
  
В дополнение к телефонных номеров, назначенной конференц-канал, можно [получить дополнительные службы номеров](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers) (международную и обслуживание бесплатных номеров, используемый для аудиоконференций) из других расположениях и затем присвоить им для конференц-связи мост так, чтобы Разверните узел покрытия для пользователей.
  
> [!NOTE]
> Должны иметь возможность отменить роли и назначить номер телефона для конференц-канал, номер телефона должен быть номер «*службы*». Тип номера можно просмотреть на вкладке **Голосовая связь** > **Номера телефонов** в столбце **Тип номера**. Необходимо вначале настроить кредиты на связь Office 365, для того, чтобы пользователи, во время общения по мосту, могли звонить на бесплатный номер.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>Шаги для назначения нового служебного номера мосту конференц-связи

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>Шаг 1. Назначение нового номера телефона мосту аудиоконференции

1. Войдите в Office 365 со своей рабочей учетной записью.

2. Откройте **Центр администрирования Office 365** > **Центры администрирования** > **Skype для бизнеса** > **Голосовая связь** > **Номера телефонов**.

3. Выберите номер телефона в списке, затем на панели действий нажмите кнопку **Назначить**.

4. На странице **Назначение** щелкните **Сохранить**.

    В качестве номера по умолчанию для вашего моста конференц-связи может быть задан только платный служебный номер. **Бесплатные служебные номера невозможно делать номерами по умолчанию для моста конференц-связи**. Если при назначении платного служебного номера вы хотите сделать его новым номером по умолчанию для моста аудиоконференций, выберите **Использовать этот номер по умолчанию**.

    > [!NOTE]
    > Новый номер телефона был назначен, даже в том случае, если номер стала новый номер по умолчанию, не изменить номер по умолчанию для существующих пользователей. Для установки международную по умолчанию или телефоны, который добавляется организатора собрания приглашения, видеть инструкции для [Групп Майкрософт](set-the-phone-numbers-included-on-invites-in-teams.md) или инструкции по [Скайп для бизнеса в Интернет](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites). 
  


### <a name="step-2---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>Шаг 2. Изменение номеров телефонов по умолчанию, которые указаны в приглашениях на собрания пользователей (необязательно)

Номера телефонов по умолчанию для пользователя, из них, включенных в свои собрания приглашает при составлении приглашения на собрание. Дополнительные сведения можно [задать телефона, номера, находящимся на приглашает в группах Майкрософт](set-the-phone-numbers-included-on-invites-in-teams.md) или [телефона, номера, находящимся на приглашает в Скайп для бизнеса в Интернет](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).
  
1. Войдите в Office 365 под своей учебной или рабочей учетной записью.

2. Откройте раздел **Центр администрирования Office 365** > **Центры администрирования** > **Skype для бизнеса** > **Аудиоконференция** > **Пользователи** и выберите пользователей в списке.

3. Нажмите кнопку **Изменить** на панели действий.

4. Под заголовком **Платный номер по умолчанию** или **Бесплатный номер по умолчанию** выберите номер в списке и нажмите кнопку **Сохранить**.

После сохранения изменений новые номера телефонов по умолчанию будут включены в приглашения на новые собрания при их планировании.

### <a name="step-3---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>Шаг 3. Обновление существующих приглашений на собрания с помощью службы перемещения собраний (необязательно)

В первых двух шагах потребуется запустить Windows PowerShell.
  
С помощью службы перемещения собраний можно обновить отправленные приглашения на собрания в организации до изменения номеров телефонов по умолчанию. Дополнительные сведения см. в разделе [Настройка службы переноса собраний (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
- Запустите службу перемещения собраний (MMS) для пользователей, у которых на шаге 2 были изменены номера телефонов по умолчанию. Для этого выполните следующую команду:

```
    Start-CsExMeetingMigration user@contoso.com
```

- Также можно просмотреть состояние перемещения собрания. Когда не останется операций с состоянием  *Ожидает*  или *Выполняется*  , все собрания будут запланированы повторно.

```
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>Шаги для отмены назначения служебного номера мосту конференц-связи


После отмены назначения номера телефона мосту конференц-связи пользователи не смогут присоединяться к собраниям с его помощью. Так как номер телефона изменится, важно обновить данные всех пользователей, которые могли использовать этот номер по умолчанию, и существующие приглашения на собрания до отмены назначения такого номера мосту аудиоконференции.

Если номер телефона будет удален, а данные пользователей и собраний не обновятся, в существующих приглашениях может быть указан номер телефона, непригодный для присоединения к собранию.

В первых трех шагах потребуется запустить Windows PowerShell. Чтобы просмотреть, как это сделать, нажмите кнопку [хотели бы узнать, как управлять с помощью Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)

### <a name="step-1---update-users-that-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>Шаг 1. Обновление данных пользователей, у которых будет отменено назначение номера телефона по умолчанию

Замените платный или бесплатный номер по умолчанию для всех таких пользователей и повторно запланируйте собрания. Для этого выполните следующую команду:

```
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >Можно также изменить счета по умолчанию или бесплатная числа пользователей в Скайп по центру администрирования бизнес. Однако, это не повлечёт за собой автоматическую перепланировку их встреч. 
 
 Для получения дополнительных сведений см [задать телефона, номера, находящимся на приглашает в группах Майкрософт](set-the-phone-numbers-included-on-invites-in-teams.md) или [телефона, номера, находящимся на приглашает в Скайп для бизнеса в Интернет](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).

  > [!NOTE]
  > В зависимости от размера организации это может занять некоторое время.

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>Шаг 2. Просмотр состояния перемещения собрания с помощью Windows PowerShell

Будет выполнено всех собраний, когда нет операций в состоянии *ожидания* или *В процессе* .

```
Get-CsMeetingMigrationStatus -SummaryOnly
```

Дополнительные сведения о службе перемещения собраний см. в разделе [Настройка службы переноса собраний (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>Шаг 3. Отмена назначения старого номера телефона мосту аудиоконференции

1. Войдите в Office 365 под своей учебной или рабочей учетной записью.

2. Откройте **Центр администрирования Office 365** > **Центры администрирования** > **Skype для бизнеса** > **Голосовая связь** > **Номера телефонов**.

3. Выберите номер телефона в списке, затем на панели действий нажмите кнопку **Отменить назначение**.

4. В диалоговом окне подтверждения нажмите кнопку **Да**.

  > [!IMPORTANT]
  > После отмены назначения номера телефона для моста аудиоконференций, телефонный номер больше не будет доступен пользователям для подключения к новым или существующим собраниям.

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell
<a name="bkPowerShell"> </a>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a>Проверка готовности Windows PowerShell

 Эти шаги проверки под управлением Windows PowerShell версии 3.0 или выше.

1. Введите **меню «Пуск»** > **Windows PowerShell**.

2. Введите _Get-Host_ в окне **Windows PowerShell** для проверки версии.

3. Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell. Чтобы скачать и обновить Windows PowerShell до версии 4.0, перейдите на страницу [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). При появлении запроса перезагрузите компьютер.

4. Необходимо также установить модуль Windows PowerShell для Скайп для бизнеса в Интернет, который позволяет создавать удаленного сеанса Windows PowerShell, который подключается к Скайп для бизнеса в Интернет. В этом модуле поддерживается только в 64-разрядных компьютеров и можно загрузить из центра загрузки Майкрософт по [Windows PowerShell модуль для Скайп для бизнеса в Интернет](https://go.microsoft.com/fwlink/?LinkId=294688).
При появлении запроса перезагрузите компьютер.

Больше информации приведено в статье [Подключение ко всем службам Office 365 с помощью единого окна Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).

### <a name="to-start-windows-powershell"></a>Запуск Windows PowerShell

 **Запуск сеанса Windows PowerShell**

1. Из **меню "Пуск"** > **Windows PowerShell**.

2. В окне **Windows PowerShell** подключитесь к организации Office 365, выполнив следующую команду:

    > [!NOTE]
    > Команду **Import-Module** нужно запускать только при первом использовании модуля Windows PowerShell в Skype для бизнеса Online.

>
  ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

Дополнительные сведения о запуске Windows PowerShell, см [подключиться ко всем службам Office 365 в одном окне Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) или [подключение к Скайп для бизнеса в Интернет с помощью Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).

### <a name="save-time-and-automate"></a>Экономия времени и автоматизации

Экономия времени благодаря автоматизация этот процесс, можно использовать командлеты **Set-CsOnlineDialInConferencingUserDefaultNumber** или [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) .

- Используйте командлет [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) для изменения платного или бесплатного номера по умолчанию для определенных пользователей.

  - Чтобы изменить бесплатный номер по умолчанию для определенного пользователя, выполните командлет

  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- Используйте командлет **Set-CsOnlineDialInConferencingUserDefaultNumber** для изменения платного или бесплатного номера по умолчанию для пользователей на основе исходного номера по умолчанию, свойственного для местоположения этих пользователей.

    > [!NOTE]
    > Чтобы узнать идентификатор BridgeID, используйте командлет **Get-CsOnlineDialInConferencingBridge**.

  - Чтобы задать бесплатный номер 8005551234 в качестве номера по умолчанию для всех пользователей, не имеющих номера по умолчанию, выполните командлет

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Чтобы изменить бесплатный номер по умолчанию для всех пользователей с бесплатным номером по умолчанию 8005551234 на 8005551239 и автоматически повторно запланировать собрания, выполните командлет:

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - Чтобы задать бесплатный номер 8005551234 в качестве номера по умолчанию для всех пользователей, находящихся в США, и автоматически повторно запланировать собрания, выполните командлет:

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > Используемое выше местоположение должно совпадать с контактными данными пользователей, которые указаны в Центре администрирования Office 365.

## <a name="about-windows-powershell"></a>О Windows PowerShell

С помощью Windows PowerShell вы можете управлять пользователями и тем, что им можно и что нельзя делать. Windows PowerShell, которые помогут управлять Скайп и Office 365 для бизнеса Online с использованием точки администрирования, которые можно упростить повседневной работе, особенно в том случае, если у вас есть несколько задач для выполнения. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.

  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Шесть причин использовать Windows PowerShell для управления Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:

  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>See also
[Изменение параметров моста аудиоконференций](change-the-settings-for-an-audio-conferencing-bridge.md)
