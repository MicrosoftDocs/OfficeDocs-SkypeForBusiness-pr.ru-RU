---
title: Общие сведения Teams записи на основе политик для звонков & собраний
author: cabailey
ms.author: cabailey
manager: laurawi
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
ms.localizationpriority: medium
search.appverid: MET150
description: Сведения о Teams записи на основе политик для звонков & собраниях
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
ms.openlocfilehash: b6fb06062902ee5bb0b3ab3f41f25a712933dd37
ms.sourcegitcommit: e38776625a3623216b0d5f092fffaff67519b1a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/13/2022
ms.locfileid: "66056929"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>Общие сведения о Teams на основе политик для звонков & собраниях

Запись на основе политик позволяет организациям, использующим Microsoft Teams для звонков и собраний, назначать, используя административную политику, когда звонки и собрания по сети должны автоматически записываться и записываться для последующей обработки и хранения в соответствии с соответствующими корпоративными или нормативными политиками.

Teams улучшена для поддержки интеграции сторонних решений записи, включая функциональные возможности платформы, пользовательские интерфейсы и административные интерфейсы, необходимые для предоставления сквозного решения для настройки, управления, записи, хранения и анализа Teams взаимодействия. К усовершенствованиям относятся API-интерфейсы платформ коммуникации и события для записи, которые предоставляют следующие возможности:

- Простой и высококачественный захват мультимедиа на разных устройствах и всех поддерживаемых конечных точках для аудио, видео, демонстрации экрана и чата.

- Поддержка отслеживания взаимодействия между Teams пользователями и поддерживаемыми конечными точками звонков (Teams, Teams Mobile, Skype для бизнеса, ТСОП)

- Новые административные политики для записи соответствия требованиям, включая интеграцию с существующими Teams административными звонками, средствами и политиками собраний

Запись соответствия может быть включена для Microsoft 365 A3/A5/E3/E5/Business Premium и Office 365 A3/A5/E3/E5. 

Возможности интеграции решения для записи соответствия требованиям также были просмотрена на конференции Ignite 2019 в сеансе записи [Microsoft Teams соответствия](https://myignite.microsoft.com/archives/IG19-VCE40) требованиям.

## <a name="teams-interaction-recording-overview"></a>Teams записи взаимодействия

Варианты использования записи взаимодействия можно разделить на четыре основные категории функций записи— удобство, функциональное, организационное и юридическое перехват, как показано на рисунке:

> [!div class="mx-imgBorder"]
> ![Снимок экрана: запись взаимодействия, что и почему.](media/recording-taxonomy.png "На изображении показаны категории записи.")

Каждая из категорий влечет за собой различные требования к способу инициации записей, записи, хранению записей, уведомлению о том, кто управляет доступом и как обрабатывается хранение.

| Тип                   | Удобство (обычная Teams записи) | Организация — регулируемая (запись соответствия) |
| ---------------------- | ------------------ | --------------- |
| Инициатор              | Пользователь               | Администратор (система)  |
| Target (Назначение)                 | За звонок или собрание | Для пользователя        |
| служба хранилища владельца          | Пользователь               | Соответствие требованиям      |
| Требуется уведомление? | Да                | Да             |
| Владелец доступа           | Пользователь               | Соответствие требованиям      |
| Политика хранения?      | Необязательно            | Да             |

Teams предоставляет различные возможности [для удобной](./cloud-recording.md) и функциональной записи собраний и трансляций. Запись организации означает, что организации, использующие Teams для звонков и собраний, могут в соответствии с административной политикой назначать, когда звонки и собрания по сети должны автоматически записываться и записываться для последующей обработки и хранения в соответствии с требованиями соответствующей корпоративной или нормативный политики. Пользователи, использующие эту политику, будут знать, что их цифровые взаимодействия с Teams записываются, но не смогут отключить запись и не смогут получить доступ к записи после завершения взаимодействия. Запись становится частью архива организации, доступного сотрудникам по обеспечению соответствия требованиям и юридическим сотрудникам для обнаружения электронных данных, удержания по юридическим причинам и других корпоративных средств хранения.

## <a name="example-user-needs"></a>Примеры потребностей пользователей

<table>
<thead>
<tr class="header">
<th>Персоной</th>
<th>Потребности</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Записанные пользователи</td>
<td><ul>
<li><p>Получать уведомления при выполнении записи.</p></li>
<li><p>Будьте в курсе, когда политика и (или) ошибка записи вызывают изменения в поведении вызова.</p></li>
</ul></td>
</tr>
<tr class="even">
<td>Администратор связи</td>
<td><ul>
<li><p>Узнайте, почему и как применять политики записи к Teams пользователям или конечным точкам.</p></li>
<li><p>Настройте и Teams политики записи для организации.</p></li>
<li><p>Отслеживайте и устраняйте проблемы, связанные с записью Teams звонками и собраниями.</p></li>
<li><p>Поддержка внутреннего сотрудника по соответствию требованиям с операционной аналитикой по использованию, качеству и надежности.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>Специалист по соответствию требованиям</td>
<td><ul>
<li><p>Сбор всех Teams данных в соответствии с обязательствами по соответствию в соответствующих региональных границах.</p></li>
<li><p>Поиск взаимодействий на основе связанных с обменом данными метаданных или содержимого взаимодействия. К распространенным примерам относятся:</p>
<ul>
<li><p><strong>Метаданных</strong> - Участники, время, направление, номер набора, номер источника, пользовательские бизнес-данные</p></li>
<li><p><strong>Содержимое</strong> — транскрибирование, тональность, фонетика, связанные взаимодействия</p></li>
</ul></li>
<li><p>Анализ собранных сообщений и взаимодействие с ними, включая возможность отслеживать взаимодействия по мере их сбора.</p></li>
<li><p>Обеспечение безопасности собранных сообщений и предотвращение незаконного изменения на всех этапах.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>Обзор архитектуры решения

Решения для записи соответствия требованиям интегрируются с Teams, как показано на следующей схеме:

> [!div class="mx-imgBorder"]
> ![Снимок экрана: параметр настраиваемого приложения команды.](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "На изображениях показан поток при Teams или звонка.")

> [!NOTE]
> Это решение предназначено специально для включения записи соответствия на основе политик с Teams. Любое другое использование этого решения не будет поддерживаться.

## <a name="recorder"></a>Рекордер

Основным компонентом решения для записи соответствия требованиям является регистратор.
Записи создаются как масштабируемые службы (боты) на основе Azure[](/graph/cloud-communications-concept-overview), использующие платформу связи Майкрософт и регистрируемые в качестве приложений в Microsoft Graph. Запись обеспечивает прямое взаимодействие с интерфейсами API платформы Teams и собраний, [](/graph/api/resources/communications-api-overview) а также предоставляет конечную точку для приема мультимедиа.

Доступен [пример приложения для записи](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) соответствия требованиям, в котором показано, как настроить бот, создать экземпляр приложения и назначить политики соответствия. В примере также приведены примеры использования API для записи определенных взаимодействий, таких как [](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) обработка маршрутизации входящих вызовов[, изменение](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138) состояний записи и удаление записи [пользователя](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).
Graph документацию по конкретным API можно найти здесь для [updateRecordingStatus](/graph/api/call-updaterecordingstatus?tabs=http) и [incomingContext](/graph/api/resources/incomingcontext).

Точная реализация службы записи зависит от партнера, но должна быть разработана для поддержки нескольких записей, чтобы обеспечить высокий уровень доступности и географическое распределение развертывания, чтобы уменьшить задержку от Teams до регистратора. Кроме того, предполагается, что сами средства записи должны быть разработаны с учетом устойчивости и избыточности.

Прежде чем отправлять свое решение на сертификацию, партнеры должны подтвердить минимальную требуемую версию API и пакетов SDK microsoft Graph для связи, чтобы обеспечить соответствие всем требованиям интеграции записи соответствия.

Два конкретных требования, которые являются основными для сценария записи соответствия:

- Бот recorder должен быть развернут в Azure

- Бот recorder должен выполняться на виртуальной машине Windows в Azure

Требования к виртуальной машине Azure и Windows применяются только к компоненту Teams Bot. Это означает, что партнер может реализовать остальную часть выбранной платформы при условии, что он может соответствовать соответствующим требованиям к производительности и функциональным требованиям для записи соответствия требованиям.

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>Назначение и подготовка политики записи соответствия

ИТ-администраторы могут определить, какие пользователи должны быть записаны и какие средства записи будут использоваться для каждого пользователя, создав и назначив политики записи соответствия. Регистраторы автоматически приглашены для участия в беседах на основе конфигурации этих политик при взаимодействии с пользователем. Политики записи соответствия управляются с помощью [Microsoft PowerShell](./teams-powershell-overview.md) и могут применяться на уровне клиента, отдельного пользователя и группы безопасности для каждой организации. Дополнительные сведения см. в Документация Майкрософт [политиках собраний](./meeting-policies-overview.md)[,](./teams-calling-policy.md) политиках звонков и [групповых политиках](./assign-policies-users-and-groups.md#assign-a-policy-to-a-group).

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

2. Создайте политику записи соответствия.

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

   См [. раздел Set-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/set-csteamscompliancerecordingpolicy).

3. Назначьте политику записи соответствия пользователю.

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   См [. раздел Grant-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/grant-csteamscompliancerecordingpolicy).

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a>Взаимодействие с пользователем

Поддержка уведомлений включена с помощью Teams взаимодействия с клиентом. Интерфейс может быть визуальным или звуковым.

**Teams клиентов — визуальное уведомление**
- Рабочий стол или интернет
- Mobile (iOS/Android)
- Teams телефонов
- Teams комнат

**Другие конечные точки — уведомление о звуке**
- Телефоны SIP
- Skype для бизнеса
- Аудиоконференции
- Вызывающие объекты ТСОП

> [!NOTE]
> Запись соответствия не поддерживается в очередях звонков в режиме конференции. Используйте очереди вызовов в режиме передачи.
> Запись соответствия требованиям не будет работать, если у пользователей был сбой в Интернете, и они выполняют и получают вызовы ТСОП с помощью SBA.

## <a name="compliance-recording-for-teams-certification-programs"></a>Запись соответствия для Teams сертификации

Помимо публикации общедоступных API, позволяющих партнерам разрабатывать и интегрировать решения CCaaS с Teams, мы разработали запись соответствия для программы сертификации Microsoft Teams, чтобы предоставить клиентам уверенность в том, что каждое решение партнера-участника протестируется и проверено для обеспечения качества, совместимости и надежности, которые они ожидают от решений Майкрософт.  

Следующие партнеры сертифицируйте свое решение для Microsoft Teams.<br/><br/>

|Партнер|Веб-сайт решения |
|:--|:--|
|Технологии ASC |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|AudioCodes |[https://online.audiocodes.com/smarttap-360-live-for-microsoft-teams](https://online.audiocodes.com/smarttap-360-live-for-microsoft-teams) |
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|Даббер |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|Технология Insightful |[https://insightfultechnology.com/teams/](https://insightfultechnology.com/teams/) |
|NICE Engage |[https://www.nice.com/products/workforce-engagement/call-recording/air-and-engage](https://www.nice.com/products/workforce-engagement/call-recording/air-and-engage) |
|ХОРОШИЙ NTR |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|Инновации в Сфере инноваций |[https://www.oakinnovate.com/clarify](https://www.oakinnovate.com/clarify) |
|Красный прямоугольный |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/red-box-partners/microsoft-integration/compliance-recording-for-microsoft-teams)  |
|Theta Lake |[https://thetalake.com/integrations/microsoft/](https://thetalake.com/integrations/microsoft/) |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |
|Инновации в Сфере инноваций |[https://www.oakinnovate.com/clarify](https://www.oakinnovate.com/clarify) |

<br/>
Следующие партнеры находятся в процессе сертификации своего решения для Microsoft Teams.<br/><br/>

|Партнер|Веб-сайт решения |
|:--|:--|
|GuardRec |[https://www.guardrec.com/en/teams-compliance-recording/](https://www.guardrec.com/en/teams-compliance-recording/) |
|Технологии Landis |[https://landistechnologies.com/](https://landistechnologies.com/) |
|Luware |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |


Этот список будет обновлен по мере того, как к этому списку присоединяется больше партнеров и соответствует критериям сертификации.

## <a name="next-steps"></a>Дальнейшие действия

Если вы поставщик, который пытается присоединиться к программе сертификации, отправьте [почту Teamscategorypartner@microsoft.com.](mailto:Teamscategorypartner@microsoft.com)
