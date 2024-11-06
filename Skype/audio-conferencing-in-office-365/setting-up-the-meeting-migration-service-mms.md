---
title: "Настройка службы переноса собраний (MMS)"
ms.author: tonysmit
author: tonysmit
ms.date: 9/25/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
description: "Служба переноса собраний (MMS)  это служба Skype для бизнеса, которая работает в фоновом режиме и автоматически обновляет собрания Skype для бизнеса и Microsoft Teams для пользователей. Эта служба позволяет пользователям не запускать средство переноса собраний для обновления собраний Skype для бизнеса и Microsoft Teams."
---

# Настройка службы переноса собраний (MMS)

Служба переноса собраний (MMS)  это служба Skype для бизнеса, которая работает в фоновом режиме и автоматически обновляет собрания Skype для бизнеса и Microsoft Teams для пользователей. Эта служба позволяет пользователям не запускать средство переноса собраний для обновления собраний Skype для бизнеса и Microsoft Teams.
  
 **Требования**
  
Для использования MMS почтовые ящики организаторов собрания должны находиться в Exchange Online.
  
 **Основные сценарии**
  
MMS обновляет собрания Skype для пользователей в следующих двух основных сценариях. 
  
- Перенос пользователя с локального сервера Skype для бизнеса в Skype для бизнеса Online.
    
- Изменение администратором параметров аудиоконференции для пользователя, при котором требуется изменение сведений об аудиоконференции в собраниях пользователя.
    
 **Распространенные сценарии, в которых невозможно использовать MMS**
  
Вот несколько распространенных сценариев, которые могут относиться к вашей ситуации. Это все поддерживаемые сценарии переноса. Но в следующих сценариях MMS работать не будет, и вам придется использовать [средство переноса собраний](https://go.microsoft.com/fwlink/p/?linkid=626047).
  
- Почтовые ящики пользователей расположены на локальном сервере Exchange Server.
    
- Использование стороннего поставщика аудиоконференций
    
- Перенос пользователей из Skype для бизнеса Online на локальный сервер Skype Server
    
## Обновление собраний при переносе локального пользователя в Skype для бизнеса Online

Это наиболее распространенный сценарий, в котором MMS поможет обеспечить более удобный перенос для ваших пользователей. При переносе пользователя c локального сервера Skype для бизнеса в Skype для бизнеса Online MMS обнаружит нового пользователя и проверит календарь этого пользователя на наличие собраний Skype для бизнеса и Microsoft Teams. Во всех будущих собраниях будут заданы обновленные сведения об этом пользователе.
  
### Использование сервера Skype Server 2015 для аудиоконференции

Для наиболее эффективного использования MMS в этом сценарии советуем придерживаться приведенных ниже рекомендаций.
  
- Так как для работы MMS необходимо, чтобы почтовый ящик пользователя находился в Exchange Online, то если вы одновременно переносите почтовые ящики с локального сервера Exchange Server, сначала переместите почтовый ящик пользователя в Exchange Online.
    
- Перед запуском командлета ** для переноса пользователя назначьте этому пользователю лицензию для** аудиоконференции `Move-CSUser`. Это необходимо сделать, так как при изменении параметров аудиоконференции для пользователя MMS также обновляет собрания. Если сначала не назначить лицензию, MMS обновит все собрания повторно при назначении лицензии.
    
### Использование стороннего поставщика конференц-связи с телефонным подключением

Если вы используете сторонний поставщик аудиоконференций, то запуск MMS зависит от параметров аудиоконференций в вашей организации. Вы можете включить автоматическую замену номеров для телефонной связи у поставщика аудиоконференций при назначении пользователю лицензии для **аудиоконференции**. Может потребоваться и другая схема, при которой нужно будет сохранить номера для телефонной связи от поставщика аудиоконференций. Чтобы узнать значение этого параметра для своей организации, запустите следующий командлет Windows PowerShell и проверьте значение параметра  `AutomaticallyReplaceAcpProvider`. Если вам нужна помощь с PowerShell, обратитесь к разделу [Управление организацией Skype для бизнеса с помощью PowerShell](setting-up-the-meeting-migration-service-mms.md#WPSInfo) в конце этой статьи.
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- Если этот параметр имеет значение $true, то при назначении пользователю лицензии для **аудиоконференции** MMS будет запущена и обновит параметры пользователя. Номера для телефонной связи от вашего поставщика аудиоконференций будут сохранены до назначения лицензии для **аудиоконференции**.
    
- Если этот параметр имеет значение $false, то MMS не будет обновлять собрания даже при назначении пользователю лицензии для **аудиоконференции**. Номера для телефонной связи от вашего поставщика аудиоконференций будут сохранены до того момента, когда пользователь вручную не будет подготовлен для аудиоконференции в центре администрирования приложения Skype для бизнеса или с помощью Windows PowerShell.
    
## Обновление собраний при изменении параметров аудиоконференции для пользователя

MMS обновляет существующие собрания Skype для бизнеса Online и Microsoft Teams в следующих случаях.
  
- При назначении или удалении лицензии для **аудиоконференции**.
    
- При включении или отключении аудиоконференции.
    
- При изменении или сбросе идентификатора конференции для пользователя, участвующего в общедоступных собраниях.
    
- При переключении пользователя на новый мост аудиоконференции.
    
- При освобождении номера телефона на мосте аудиоконференции. Это сложный сценарий, который потребует дополнительных действий. Дополнительные сведения см. в разделе [Измените платные или бесплатные номера телефонов для моста аудиоконференций.](change-the-toll-or-toll-free-numbers-on-your-audio-conferencing-bridge.md).
    
> [!IMPORTANT]
> MMS обновляет собрания только в том случае, если вы используете мост Майкрософт. При использовании стороннего поставщика аудиоконференций пользователям потребуется обновить свои собрания вручную. В этом случае можно воспользоваться [средством переноса собраний](https://go.microsoft.com/fwlink/p/?linkid=626047). 
  
Не все изменения в параметрах аудиоконференции для пользователя приводят к запуску MMS. В частности, MMS не будет обновлять собрания в двух следующих случаях:
  
- При изменении SIP-адреса организатора собрания (его имени пользователя SIP или домена SIP)
    
- При изменении URL-адреса собрания организации с помощью команды [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442).
    
## Что делает MMS при обновлении собраний?

Когда служба MMS определяет, что необходимо обновить собрания пользователя, она выполняет следующие действия.
  
1. Определение всех собраний Skype для бизнеса и Microsoft Teams, которые пользователь запланировал на будущее
    
  - Все собрания Skype для бизнеса или Microsoft Teams, произошедшие до запуска MMS, не учитываются.
    
  - Обновляются только те собрания, организатором которых является пользователь.
    
2. Замена блока с информацией о собрании в сведениях о собрании
    
3. Отправка обновлений всем участникам собрания от имени организатора собрания
    
 **Сколько времени занимает перенос собраний с помощью MMS?**
  
Время, которое требуется MMS для переноса собраний, зависит от количества затронутых пользователей и от общего количества собраний Skype для бизнеса или Microsoft Teams в календаре для каждого пользователя. Минимальное время переноса составляет 10 минут. Хотя некоторые объемные операции переноса могут занимать до 12 часов, большинство операций должно завершиться в течение часа.
  
 **Ограничения и возможные проблемы**
  
- Переносятся только те собрания Skype для бизнеса или Microsoft Teams, которые были запланированы с помощью кнопки **Добавить собрание Skype** в Outlook в Интернете или с помощью надстройки "Собрание Skype" для Outlook. Другими словами, если пользователь копирует и вставляет сведения о собрании по сети из одного собрания в другое, это новое собрание не будет обновлено.
    
- При переносе собрания MMS заменяет все сведения в блоке информации о собрании по сети. Если же пользователь изменил этот блок, внесенные им изменения будут перезаписаны. Все остальные данные в сведениях о собрании, за исключением этого блока, останутся нетронутыми. 
    
     ![The meeting block that gets updated by MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- Содержимое собрания, которое было создано или присоединено к собранию (доски, опросы и т. д.), не сохранится после переноса с помощью MMS. Если организаторы собрания добавили содержимое к собранию заранее, это содержимое не придется снова создавать после запуска MMS.
    
- Ссылки на общие заметки собрания в элементе календаря и в собрании Skype также будут перезаписаны. Обратите внимание, что сами заметки собрания, которые хранятся в OneNote, останутся там; изменится только ссылка на общие заметки собрания.
    
- Собрания с числом участников больше 250 (включая организатора) не будут перенесены. 
    
- Некоторые символы Юникода в тексте приглашения могут ошибочно заменяться на один из следующих специальных символов: ï, ¿, ½, �.
    
### Что увидят пользователи после того, как MMS обновит их собрания?

Как и средство переноса собраний, MMS обновляет собрания от имени пользователей. Поэтому ваши пользователи увидят только принятия приглашений на собрание для своих собраний. Чтобы у пользователей не возникли затруднения, рекомендуем заранее оповещать их не только о переносе пользователей из локальной системы в Skype для бизнеса Online, но и об изменениях параметров аудиоконференции, которые приведут к запуску MMS.
  
## Управление MMS

Для управления MMS и проверки состояния операций переноса нужно использовать Windows PowerShell. В этом разделе предполагается, что вы знакомы с использованием PowerShell для управления организацией Skype для бизнеса. Если вам нужна помощь с PowerShell, обратитесь к разделу [Управление организацией Skype для бизнеса с помощью PowerShell](setting-up-the-meeting-migration-service-mms.md#WPSInfo) в конце этой статьи.
  
### Как проверить состояние переноса собраний?

Для проверки состояния переноса собраний можно запустить командлет  `Get-CsMeetingMigrationStatus`. Ниже приведено несколько примеров.
  
Для получения общего состояния переноса MMS выполните следующую команду:
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

Эта команда выведет состояния всех операций переноса в таблице:
  
State UserCount----- ---------Pending 21InProgress 6Failed 2Succeeded 131
> [!IMPORTANT]
> Если вы видите, что некоторые операции переноса завершились сбоем, устраните ошибки как можно быстрее. Пока вы не устраните ошибки, пользователи не смогут присоединяться к собраниям, создаваемым этими пользователями. Дополнительные сведения см. в разделе [Что делать, если произошла ошибка?](setting-up-the-meeting-migration-service-mms.md#Troubleshooting)
  
Для получения полных сведений об операциях переноса за определенный период времени воспользуйтесь параметрами  `StartTime` и `EndTime`. Например, следующая команда выведет сведения о всех операциях переноса, которые выполнялись с 1 по 8 октября 2016 г.
  
```
Get-CsMeetingMigrationStatus -StartTime "10/1/2016" -EndTime "10/8/2016"
```

Можно также проверить состояние переноса для конкретного пользователя с помощью параметра  `UserId`. Например, следующая команда получит состояние переноса для пользователя ashaw@contoso.com:
  
```
Get-CsMeetingMigrationStatus -UserId "ashaw@contoso.com"
```

### Что делать, если произошла ошибка?
<a name="Troubleshooting"> </a>

Если вы запустили командлет  `Get-CsMeetingMigrationStatus` для получения сведений о состоянии переноса и обнаружили, что некоторые операции переноса находятся в состоянии Сбой, сделайте следующее:
  
1. Определите пользователей, которых затронул сбой. Для получения списка пользователей, которых затронул сбой, и возникших ошибок выполните следующую команду:
    
  ```
  Get-CsMeetingMigrationStatus | Where {$_.State -eq "Failed"} | Format-Table UserId,LastErrorMessage
  ```

2. Для каждого из этих пользователей запустите [средство переноса собраний](https://go.microsoft.com/fwlink/p/?linkid=626047) для переноса собраний этих пользователей вручную.
    
3. Если с помощью средства переноса собраний перенос выполнить все равно не удается, есть два варианта действий.
    
  - Попросить пользователей создать собрания Skype заново.
    
  - [Связаться со службой поддержки](https://go.microsoft.com/fwlink/p/?LinkID=518322).
    
### Включение и отключение MMS
<a name="Troubleshooting"> </a>

MMS по умолчанию включена для всех организаций, но при необходимости ее можно отключить. Например, если вы хотите перенести все собрания вручную или пользуетесь сторонним поставщиком аудиоконференций, MMS может не понадобиться. Вы можете также временно отключить MMS. Например, это можно сделать, если вы вносите масштабные изменения в настройках аудиоконференции для вашей организации и не хотите, чтобы MMS запускалась, пока все изменения не будут завершены.
  
Чтобы узнать, включена ли MMS для вашей организации, выполните следующую команду и проверьте значение параметра  `MeetingMigrationEnabled`. Если этот параметр имеет значение $true, MMS включена.
  
```
Get-CsTenantMigrationConfiguration
```

Чтобы отключить MMS, выполните следующую команду:
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```

Чтобы включить MMS, выполните следующую команду:
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $true
```

### Включение и отключение MMS только для изменений параметров аудиоконференции
<a name="Troubleshooting"> </a>

Вы также можете отключить MMS только для изменений параметров аудиоконференции. При этом MMS по-прежнему будет запускаться при переносе локальной системы Skype для бизнеса в Skype для бизнеса Online. Чтобы узнать, включена ли MMS для изменений параметров аудиоконференции, выполните следующую команду и проверьте значение параметра  `AutomaticallyMigrateUserMeetings`. Если этот параметр имеет значение $true, MMS будет запускаться для обновления собраний пользователей при изменении параметров аудиоконференции.
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

Чтобы отключить MMS для аудиоконференции, выполните следующую команду.
  
```
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallyMigrateUserMeetings $false
```

Чтобы включить MMS для аудиоконференции, выполните следующую команду.
  
```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $true
```

### Как вручную запустить перенос собраний?
<a name="Troubleshooting"> </a>

Кроме автоматического переноса собраний, можно также запустить перенос собраний вручную с помощью командлета **Start-CsExMeetingMigration**. Этот командлет добавляет пользователя в очередь переноса собраний. Служба переноса собраний прочтет запрос пользователя и перенесет собрания. Состояние переноса можно проверить с помощью командлета **Get-CsMeetingMigrationStatus**.
  
Ниже показан пример, который удаляет перенос собраний для пользователя ashaw@contoso.com:
  
```
Start-CsExMeetingMigration -Identity ashaw@contoso.com
```

## Управление организацией Skype для бизнеса с помощью PowerShell
<a name="WPSInfo"> </a>

 **Убедитесь в том, что у вас установлена оболочка Windows PowerShell 3.0 или более поздней версии**
  
1. Чтобы проверить, установлена ли у вас версия 3.0 или более поздняя, в меню **Пуск** выберите пункт **Windows PowerShell**.
    
2. Проверьте версию, введя в окне **Windows PowerShell** команду _Get-Host_.
    
3. Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell. Чтобы скачать и обновить Windows PowerShell до версии 4.0, перейдите на страницу [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). При появлении запроса перезагрузите компьютер.
    
4. Вам также потребуется установить модуль Windows PowerShell для Skype для бизнеса online, с помощью которого можно создать удаленный сеанс Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-разрядных компьютерах, можно скачать в Центре загрузки Майкрософт на странице [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688). При появлении запроса перезагрузите компьютер.
    
Больше информации приведено в статье [Подключение ко всем службам Office 365 с помощью единого окна Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
  
 **Запуск сеанса Windows PowerShell**
  
1. В меню **Пуск** выберите пункт **Windows PowerShell**.
    
2. В окне **Windows PowerShell** подключитесь к организации Office 365, выполнив следующую команду:
    
    > [!NOTE]
    > Команду **Import-Module** нужно запускать только при первом использовании модуля Windows PowerShell в Skype для бизнеса Online.
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```

> 
  ```
  $credential = Get-Credential
  ```

> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```

> 
  ```
  Import-PSSession $session
  ```

Дополнительные сведения о запуске Windows PowerShell см. в статье [Подключение ко всем службам Office 365 с помощью единого окна Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) или[Подключение к Skype для бизнеса с использованием Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).
  
- Windows PowerShell, дает возможность управлять пользователями, предоставляя им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса online, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
