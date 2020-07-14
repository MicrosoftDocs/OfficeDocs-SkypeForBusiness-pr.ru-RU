---
title: Общие сведения о записи на основе политики в Teams для собраний по звонкам &
author: cabailey
ms.author: cabailey
manager: laurawi
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
localization_priority: Normal
search.appverid: MET150
description: Сведения о параметрах записи на основе политик групп для собраний по звонкам &
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 48cc430ea864614a306725958b56dda934e00eef
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121649"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>Общие сведения о записи на основе политики для групп звонков & собраний

Запись на основе политики позволяет организациям, которые применяют Microsoft Teams для звонков и собраний в соответствии с использованием политики администрирования, когда звонки и собраний по сети должны автоматически записываться и записываться для последующей обработки и хранения в соответствии с требованиями, предусмотренными корпоративными или нормативными политиками.

Группы были улучшены для поддержки интеграции сторонних решений для записи, в том числе функций платформы, взаимодействия с пользователем и административных интерфейсов, которые необходимы для создания комплексного решения для настройки, управления, записи, хранения и анализа коммуникаций в Teams. Сюда входят API платформы связи и события для записи, которые предоставляют следующие возможности.

- Высококачественная запись мультимедиа на разных устройствах и все поддерживаемые конечные точки для звука, видео, демонстрации экрана и чата.

- Поддержка захвата взаимодействия между пользователями Teams и поддерживаемыми конечными точками (Teams, Teams Mobile, Skype для бизнеса, КТСОП)

- Новые политики администрирования для записи соответствия требованиям, в том числе интеграция с существующими средствами администрирования, а также средства и политики для собраний.

- Разрешено для пользователей Teams с отдельной лицензией

Возможности интеграции с решением для записи соответствия требованиям также проверяются на Ignite 2019 в [<span class="underline">записи соответствия требованиям и сеансе Microsoft Teams</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions).

## <a name="teams-interaction-recording-overview"></a>Общие сведения о записи взаимодействия в Teams

Сценарии использования для записи взаимодействия можно разделить на четыре основных категории функциональных возможностей записи: удобные, функциональные, организационные и законных перехваты, как показано на рисунке.

![Снимок экрана, на котором показано, что такое запись взаимодействия и почему.](media/recording-taxonomy.png "На изображении отображаются категории записи.")

Каждая из категорий имеет разные требования для начала записи, что записывается, где хранятся записи, кто получает уведомление, кто управляет доступом и как выполняется обработка хранения.

|                        | Благодаря        | Функция         | Org — общие      | Поднадзорные Организации | Законных перехват   |
| ---------------------- | ------------------ | ------------------ | ------------------ | --------------- | ------------------ |
| Владельцы              | Пользователь               | Приложение/решение       | Администратор (система)     | Администратор (система)  | LEA                |
| Целевой объект                 | Для каждого звонка или собрания | Для каждого звонка или собрания | Для каждого звонка или собрания | Для каждого пользователя        | На конечную точку/выполнено |
| Владелец хранилища          | Пользователь               | ·                | RAS              | О      | LEA                |
| Требуется уведомление? | Да                 | Да                 | Да                 | Да             | Нет                 |
| Владелец Access           | Пользователь               | ·                | RAS              | О      | LEA                |
| Политика хранения?      | Необязательно            | Да                 | Да                 | Да              | Да                |

Teams предоставляет различные возможности для [<span class="underline">удобной</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) и функциональной записи для собраний и событий Live Events. Запись в Организации означает, что Организации, которые разрабатывают команды для звонков и собраний, в соответствии с политикой администрирования, при выполнении звонков и собраний по сети должны автоматически записываться и записываться для последующей обработки и хранения в соответствии с требованиями компании или законодательной политики. Пользователи в этой политике будут знать о том, что ваши цифровые взаимодействия с группами записываются, но они не смогут отключить запись и не получат доступ к записи после завершения взаимодействия. Запись становится частью организационного архива, доступного для соответствия и юридического персонала для обнаружения электронных данных, юридических удержаний и других целей хранения в корпоративной компании.

## <a name="example-user-needs"></a>Примеры потребностей пользователей

<table>
<thead>
<tr class="header">
<th><strong>Дайте</strong></th>
<th><strong>Необходимо</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Записанные пользователи</td>
<td><ul>
<li><p>Получать уведомления о ходе записи.</p></li>
<li><p>Будьте в курсе событий, вызывающих ошибки политики и (или) записи, которые приводят к изменениям в поведении вызова.</p></li>
</ul></td>
</tr>
<tr class="even">
<td>Администратор связи</td>
<td><ul>
<li><p>Узнайте, почему и как применять политики записи к пользователям и конечным точкам Teams.</p></li>
<li><p>Настройте и настройте политики записи в Teams для Организации.</p></li>
<li><p>Отслеживание и устранение проблем, связанных с записью, в рамках звонков и собраний Teams.</p></li>
<li><p>Поддержка внутреннего сотрудника по обеспечению соответствия требованиям в отношении использования, качества и надежности.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>Сотрудник отдела соответствия требованиям</td>
<td><ul>
<li><p>Соберите все коммуникации в Teams так, чтобы они соответствовали обязательствам по обеспечению соответствия требованиям в соответствующих региональных регионах.</p></li>
<li><p>Поиск взаимодействий на основе метаданных или контента взаимодействия, связанных с связью. Ниже приведены распространенные примеры.</p>
<ul>
<li><p><strong>Метаданные</strong> - Участники, время, направление, набранный номер, номер источника, пользовательские бизнес-данные</p></li>
<li><p><strong>Содержимое</strong> — транскрипция, тональность, фонетическая информация, взаимосвязанные взаимодействия</p></li>
</ul></li>
<li><p>Анализ и взаимодействие с собранными связями, в том числе возможность отслеживать взаимодействия по мере их сбора.</p></li>
<li><p>Обеспечьте безопасность собранных сообщений и запретите все этапы.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>Общие сведения об архитектуре решения

Решения для записи соответствия требованиям объединены с группами, как показано на рисунке ниже.

![Снимок экрана: параметр "настраиваемое приложение группы"](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "Изображения показывают поток при отправке и получении собрания или звонка команды.")

## <a name="recorder"></a>Recorder

Основным компонентом решения для записи соответствия требованиям является средство записи.
Средства записи создаются как масштабируемые службы на основе Azure (ботов), которые [<span class="underline">используют платформу связи Майкрософт</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) и регистрируются в качестве приложений в Microsoft Graph. Средство записи обеспечивает непосредственное взаимодействие с [<span class="underline">API платформой связи</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) и собраний, а также предоставляет конечную точку для приема мультимедиа.

[<span class="underline">Будет доступно пример приложения для записи соответствия требованиям</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) , в котором показано, как настроить робот, создать экземпляр приложения и назначить политики соответствия требованиям. В образце также приведены примеры использования API для записи конкретных взаимодействий, например обработки маршрутизации [<span class="underline">входящих звонков</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244)   , [<span class="underline">изменения состояния записи</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)и [<span class="underline">удаления пользователя, который записывается</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).
Документацию по графике для конкретных API можно найти здесь для [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) и [<span class="underline">incomingContext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0).

Точная реализация службы записи зависит от партнера, но должна быть разработана для поддержки нескольких средств записи в целях обеспечения высокой доступности и географического распространения развертывания для сокращения задержки от команд до средства записи. Кроме того, ожидается, что сами средства записи должны быть спроектированы с учетом устойчивости и избыточности.

Перед отправкой решения о том, что все требования интеграции с записью соответствия требованиям, партнеры должны проверить минимальную требуемую версию API Microsoft Graph для обмена данными и пакеты SDK для Microsoft.

Существует два конкретных требования, которые являются фундаментальными для сценария записи соответствия требованиям:

- На самом и в Azure должны быть развернуты роботы для записи

- На виртуальной машине Windows в Azure должен выполняться робот средства записи.

Требования Azure и VM для Windows применимы только к компоненту Bot для Teams, а это означает, что партнер может реализовать оставшуюся платформу, если она подходит для обеспечения соблюдения требований к производительности и функциональным требованиям для записи соответствия требованиям.

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>Назначение и подготовка политики записи соответствия требованиям

ИТ администраторы могут определить, какие пользователи будут записаны, а какие будут использоваться для каждого пользователя, создавая и назначая политики записи соответствия требованиям. Средства записи автоматически приглашаются в беседы на основе конфигурации этих политик, когда происходит взаимодействие с связью. Политики записи соответствия управляются с помощью [<span class="underline">Microsoft PowerShell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) и могут применяться для каждой организации на уровне клиента, пользователя и группы безопасности. Дополнительную информацию можно найти в документах Microsoft для [<span class="underline">политик собраний</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams), [<span class="underline">политиках звонков</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy) и [<span class="underline">групповых политик</span>](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group).

1. Создайте экземпляр приложения в клиенте.

   ```powershell
   PS C:\> New-CsOnlineApplicationInstance -UserPrincipalName cr.instance@contoso.onmicrosoft.com -DisplayName ComplianceRecordingBotInstance -ApplicationId fcc88ff5-a42d-49cf-b3d8-f2e1f609d511

   RunspaceId        : 4c13efa6-77bc-42db-b5bf-bdd62cdfc5df
   ObjectId          : 5069aae5-c451-4983-9e57-9455ced220b7
   TenantId          : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   UserPrincipalName : cr.instance@contoso.onmicrosoft.com
   ApplicationId     : fcc88ff5-a42d-49cf-b3d8-f2e1f609d511
   DisplayName       : ComplianceRecordingBotInstance
   PhoneNumber       :
   ```

   ```powershell
   PS C:\> Sync-CsOnlineApplicationInstance -ObjectId 5069aae5-c451-4983-9e57-9455ced220b7
   ```

2. Создание политики записи соответствия требованиям.

   ```powershell
   PS C:\> New-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy -Enabled $true -Description "Test policy created by tenant admin"

   Identity                        : Global
   ComplianceRecordingApplications : {}
   Enabled                         : True
   WarnUserOnRemoval               : True
   Description                     : Test policy created by tenant admin
   ```

   ```powershell
   PS C:\> Set-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy `
   -ComplianceRecordingApplications @(New-CsTeamsComplianceRecordingApplication -Id 5069aae5-c451-4983-9e57-9455ced220b7 -Parent TestComplianceRecordingPolicy)
   ```

   [<span class="underline">Set-CsTeamsComplianceRecordingPolicy</span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. Назначение пользователю политики записи соответствия требованиям.

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   [<span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a>Взаимодействие с пользователем

Поддержка уведомлений включена с помощью клиента Teams. Этот интерфейс может быть визуальным или звуковым.

**Клиенты Teams-наглядное уведомление**
- Классическое и Интернет-
- Мобильный (iOS/Android)
- Телефоны Teams
- Комнаты команд

**Другие конечные точки — уведомление о звуке**
- Телефоны SIP
- Skype для бизнеса
- Аудиоконференции
- КОММУТИРУЕМые звонки

## <a name="compliance-recording-for-teams-certification-programs"></a>Запись соответствия требованиям для программ сертификации Teams

Помимо публикации общедоступных API-интерфейсов, позволяющих партнерам разрабатывать и интегрировать решения CCaaS с помощью Teams, мы разработали запись соответствия требованиям для программы сертификации Microsoft Teams, чтобы предоставить клиентам гарантию о том, что решение для каждого участника было проверено и проверено на предмет качества, совместимости и надежности, которые они ожидают от решений Microsoft.  

Следующие партнеры находятся в процессе сертификации своих решений для Microsoft Teams.  

|Сотрудничать|Веб-сайт решения |
|:--|:--|
|Технологии ASC |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|AudioCodes |[https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording) |
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|ПРИВЛЕКАТЕЛЬН |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|Красная рамка |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

Этот список будет обновляться по мере того, как дополнительные участники будут присоединяться к критерию сертификации и отвечать на них.

## <a name="next-steps"></a>Дальнейшие действия

Если вы хотите присоединиться к программе сертификации, пожалуйста, <a href= "mailto:Teamscategorypartner@microsoft.com">поTeamscategorypartner@microsoft.com</a>по электронной почте.
