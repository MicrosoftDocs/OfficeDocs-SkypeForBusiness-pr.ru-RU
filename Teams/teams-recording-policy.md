---
title: Введение в Teams записи на основе политики для & собраний
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
description: Узнайте о Teams записи на основе политики для & собраний
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
ms.openlocfilehash: ba99e49aa546a57d412492737cae8f6520a9eb84
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308368"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>Введение в Teams на основе политики для звонков & собраниях

Запись на основе политики позволяет организациям, которые Microsoft Teams звонки и собрания, используя административную политику, автоматически записывать и записывать звонки и собрания по сети для последующей обработки и хранения, как требуется соответствующей корпоративной или регулятивной политикой.

Teams поддерживает интеграцию сторонних решений записи, включая функциональные возможности платформы, пользовательские интерфейсы и интерфейсы администрирования, необходимые для предоставления конечного решения для настройки, управления, записи, хранения и анализа Teams взаимодействия. Усовершенствования включают API платформы связи и события для записи, которые предоставляют следующие возможности:

- Бесперебойная высококачественная запись мультимедиа на разных устройствах и все поддерживаемые конечные точки для аудио- и видеосвязи, обмена экранами и чата.

- Поддержка взаимодействия между пользователями Teams и поддерживаемых конечных точек звонков (Teams, Teams Mobile, Skype для бизнеса, STN)

- Новые административные политики для записи соответствия требованиям, в том числе интеграция с существующими Teams административными звонками, инструментами и политиками собраний

Запись соответствия требованиям можно включить Microsoft 365 пользователей A3/A5/E3/E5/Business Premium и Office 365 A3/A5/E3/E5. 

Возможности интеграции с решением для записи соответствия требованиям также [](https://myignite.microsoft.com/archives/IG19-VCE40)были рассмотрены на Microsoft Teams Ignite 2019.

## <a name="teams-interaction-recording-overview"></a>Teams обзор записи взаимодействия

Случаи использования записи взаимодействия можно разделить на четыре основные категории функций записи: удобство, функциональный, организационный и юридический отладок, как показано на рисунке:

> [!div class="mx-imgBorder"]
> ![Снимок экрана: запись о том, что и почему происходит при взаимодействии.](media/recording-taxonomy.png "На изображении показаны категории записи.")

Для каждой категории должны быть задаены разные требования к способу начала записи, хранению записей, хранению записей, уведомлению о том, кто контролирует доступ и как обрабатывается хранение.

| Тип                   | Удобство (обычная Teams запись) | Регулируемая организация (запись соответствия требованиям) |
| ---------------------- | ------------------ | --------------- |
| Инициатор              | Пользователь               | Администратор (система)  |
| Target (Назначение)                 | Per-call / meeting | Для пользователя        |
| служба хранилища владелец          | Пользователь               | Соответствие требованиям      |
| Обязательное уведомление? | Да                | Да             |
| Владелец Access           | Пользователь               | Соответствие требованиям      |
| Политика хранения?      | Необязательно            | Да             |

Teams возможности удобной и [](./cloud-recording.md) функциональной записи для собраний и трансляций. Организационная запись позволяет организациям Teams организации Teams звонков и собраний в соответствии с административной политикой, когда звонки и собрания по сети должны автоматически записываться и записываться для последующей обработки и хранения, как требуется соответствующей корпоративной или регулятивной политикой. Пользователи этой политики будут знать, что их цифровые взаимодействия с Teams записываются, но они не смогут отключить запись и не будут иметь доступа к записи после завершения взаимодействия. Запись становится частью архива организации, доступного для соответствия требованиям и юридических лиц при обнаружении электронных данных, удержании по юридическим и другим корпоративным средствам хранения.

## <a name="example-user-needs"></a>Пример потребностей пользователей

<table>
<thead>
<tr class="header">
<th>Персоной</th>
<th>Потребности</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Зарегистрированные пользователи</td>
<td><ul>
<li><p>По уведомлению о ходе записи.</p></li>
<li><p>Будьте в курсе, когда политика и/или ошибка записи приводит к изменениям поведения при звонках.</p></li>
</ul></td>
</tr>
<tr class="even">
<td>Администратор связи</td>
<td><ul>
<li><p>Понять, почему и как применять политики записи и применять к Teams пользователям и конечным точкам.</p></li>
<li><p>Настройте и Teams политики записи для организации.</p></li>
<li><p>Отслеживайте и устраняйте проблемы, связанные с записью, Teams звонками и собраниями.</p></li>
<li><p>Поддержка внутреннего сотрудника по обеспечению соответствия требованиям с помощью операционной аналитики по использованию, качеству и надежности.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>Сотрудник по обеспечению соответствия требованиям</td>
<td><ul>
<li><p>Сбор всех Teams сообщений в соответствии с обязательствами по соответствию требованиям в соответствующих региональных границах.</p></li>
<li><p>Поиск взаимодействий на основе связанных с общением метаданных или контента взаимодействия. Примерами могут быть следующие:</p>
<ul>
<li><p><strong>Метаданные</strong> - Участники, время, направление, номер набора, номер источника, пользовательские бизнес-данные</p></li>
<li><p><strong>Содержимое</strong> — транскрибация, расшифровка, фонетическое отношение, связанные взаимодействия</p></li>
</ul></li>
<li><p>Анализируйте собранные сообщения и взаимодействуйте с ними, в том числе отслеживайте взаимодействие по мере их сбора.</p></li>
<li><p>Обеспечение безопасности собранных сообщений и предотвращение подделывок на всех этапах.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>Обзор архитектуры решений

Решения записи соответствия требованиям интегрируются с Teams, как показано на схеме ниже.

> [!div class="mx-imgBorder"]
> ![Снимок экрана: настройка пользовательского приложения группы](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "На рисунках показан поток при Teams или звонка.")

## <a name="recorder"></a>Рекордер

Основным компонентом решения для записи соответствия требованиям является регистратор.
Записи — это масштабируемые службы (боты) Azure, которые используют платформу коммуникаций Майкрософт и регистрируются как приложения в Microsoft Graph. [](/graph/cloud-communications-concept-overview) Он обеспечивает непосредственное взаимодействие с API платформы [](/graph/api/resources/communications-api-overview?view=graph-rest-1.0) Teams звонков и собраний, а также конечную точку для передачи мультимедиа.

Доступно [образец приложения для записи](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) соответствия требованиям, в которое показано, как настроить бот, создать экземпляр приложения и назначить политики соответствия требованиям. В примере также есть примеры использования API для записи определенных взаимодействий, таких как обработка маршрутизаации входящих зовов, изменение состояния записи и удаление пользователя, [зарегистрированного.](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126) [](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) [](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)
Graph документацию по определенным API можно найти здесь для [updateRecordingStatus](/graph/api/call-updaterecordingstatus?tabs=http&view=graph-rest-1.0) и [incomingContext.](/graph/api/resources/incomingcontext?view=graph-rest-1.0)

Точное внедрение службы записи зависит от партнера, но необходимо обеспечить поддержку нескольких записей, чтобы обеспечить высокую доступность и географическое распределение развертывания, чтобы уменьшить задержки от Teams до регистратора. Кроме того, предполагается, что сами записи должны быть разработаны с учетом отказоустойчивости и избыточности.

Перед отправкой решения для сертификации партнерам необходимо подтвердить минимальную версию API и SDKs для связи Microsoft Graph, чтобы обеспечить поддержку всех требований интеграции с записью соответствия требованиям.

Основные требования для записи соответствия требованиям:

- Бот записи должен быть развернут в Azure

- Бот записи должен запускаться на Windows VM в Azure

Требования к VM для Azure и Windows применяются только к компоненту бота Teams, то есть партнеры могут реализовать остальные платформы, если им будут соответствовать соответствующие требования к производительности и функциональным требованиям для записи соответствия требованиям.

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>Назначение и подготовка политики записи соответствия

ИТ-администраторы могут определить, какие пользователи должны быть записаны и какие записи будут использоваться для каждого пользователя, создав и назначив политики записи соответствия. Регистраторы автоматически приглашаются к беседам в зависимости от конфигурации этих политик при взаимодействии. Политика записи соответствия требованиям управляется с помощью [Microsoft PowerShell](./teams-powershell-overview.md) и может применяться на уровне клиента, пользователя и группы безопасности для каждой организации. Дополнительные сведения о microsoft Docs для [собраний,](./meeting-policies-in-teams.md)политиках звонков и [групповых](./teams-calling-policy.md) [политиках.](./assign-policies.md#assign-a-policy-to-a-group)

1. Создайте экземпляр приложения в своем клиенте.

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

   См. [set-CsTeamsComplianceRecordingPolicy.](/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. Назначьте политику записи соответствия требованиям пользователю.

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   См. [grant-CsTeamsComplianceRecordingPolicy.](/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a>Пользовательские интерфейсы

Поддержка уведомлений включена с помощью Teams клиента. Эти функции могут быть визуальными или звукозаписями.

**Teams клиентов — визуальное уведомление**
- Рабочий стол или веб-сайт
- Мобильные устройства (iOS или Android)
- Teams телефонов
- Teams помещений

**Другие конечные точки — уведомление о звуке**
- Телефоны SIP
- Skype для бизнеса
- Аудиоконференции
- Вызыватели через ПСОП

## <a name="compliance-recording-for-teams-certification-programs"></a>Запись соответствия требованиям для Teams сертификации

Помимо публикации общедоступных API, позволяющих партнерам разрабатывать и интегрировать решения CCaaS с Teams, мы разработали запись соответствия требованиям для программы сертификации Microsoft Teams, чтобы гарантировать клиентам, что решение каждого из партнеров протестировали и проверили, чтобы обеспечить качество, совместимость и надежность решений Майкрософт.  

Следующие партнеры сертифицированы для Microsoft Teams.<br/><br/>

|Партнер|Веб-сайт решения |
|:--|:--|
|ASC Technologies |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|AudioCodes |[https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360](https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360) |
|Дублбер |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|Хороший |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |
|Theta Lake |[https://thetalake.com/integrations/microsoft/](https://thetalake.com/integrations/microsoft/) |
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |

<br/>
Следующие партнеры находятся в процессе сертификации своего решения для Microsoft Teams.<br/><br/>

|Партнер|Веб-сайт решения |
|:--|:--|
|Landis Technologies |[https://landistechnologies.com/](https://landistechnologies.com/) |
|Luware |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|Инновации |[https://www.oakinnovate.com/call-recording](https://www.oakinnovate.com/call-recording) |
|Красный квадрат |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |

Этот список будет обновляться по мере партнерами, которые присоединяются к ним и соответствуют условиям сертификации.

## <a name="next-steps"></a>Дальнейшие действия

Если вы хотите присоединиться к программе сертификации, обратитесь по электронной <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com.</a>
