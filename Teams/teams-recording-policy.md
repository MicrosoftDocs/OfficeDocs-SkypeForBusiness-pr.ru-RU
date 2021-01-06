---
title: Введение в запись на основе политик Teams для & собраний
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
description: Информация о записи на основе политики Teams для & собраний
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
ms.openlocfilehash: b37fcadb89c0ae88e48c20ab669aa91aef6d2f02
ms.sourcegitcommit: 7575fb476a594d70084c603e508dd311ef1d7edb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/05/2021
ms.locfileid: "49757774"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>Введение в запись на основе политик Teams для звонков & собраниях

Запись на основе политики позволяет организациям, использующим Microsoft Teams для звонков и собраний, использовать административную политику, когда звонки и собрания по сети должны автоматически записываться и записываться для последующей обработки и хранения, как требуется соответствующей корпоративной или регулятивной политикой.

В Teams улучшена поддержка интеграции сторонних решений для записи, включая функции платформы, пользовательский интерфейс и интерфейсы администрирования, необходимые для предоставления конечного решения для настройки, управления, записи, хранения и анализа сообщений Teams. Усовершенствования включают API информационной платформы и события для записи, которые обеспечивают:

- Простое и высококачественное видеосъемка мультимедиа на разных устройствах и все поддерживаемые конечные точки для аудио- и видеосвязи, обмена экранами и чата.

- Поддержка взаимодействия между пользователями Teams и поддерживаемых конечных точек звонков (Teams, Teams Mobile, Skype для бизнеса, PSTN)

- Новые административные политики для записи соответствия требованиям, включая интеграцию с существующими инструментами администрирования и политиками собраний Teams

Запись соответствия требованиям можно включить для пользователей Microsoft 365 A3/A5/E3/E5/Business Premium и Office 365 A3/A5/E3/E5. 

Интеграция решений для записи соответствия требованиям также была рассмотрена на веб-сайте Ignite 2019 в сеансе записи соответствия требованиям [<span class="underline">и Microsoft Teams.</span>](https://myignite.microsoft.com/archives/IG19-VCE40)

## <a name="teams-interaction-recording-overview"></a>Обзор записи взаимодействия в Teams

Дела записи взаимодействия можно разделить на четыре основные категории функций записи: удобство, функциональные, организационные и юридические, как показано на изображении:

![Снимок экрана: запись взаимодействия: что и почему.](media/recording-taxonomy.png "На изображении показаны категории записи.")

В каждой из категорий есть различные требования к способу и способу начала записи, хранимой записи, способу уведомления о том, кто контролирует доступ, а также способ обработки хранения.

| Тип                   | Удобство (обычная запись Teams) | Организация — регулируемый (запись соответствия требованиям) |
| ---------------------- | ------------------ | --------------- |
| Инициатор              | Пользователь               | Администратор (система)  |
| Целевой объект                 | Per-call /meeting | На пользователя        |
| Владелец хранилища          | Пользователь               | Соответствие требованиям      |
| Требуется уведомление? | Да                | Да             |
| Владелец Access           | Пользователь               | Соответствие требованиям      |
| Политика хранения?      | Необязательно            | Да             |

Teams предоставляет различные возможности для [<span class="underline">удобной</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) и функциональной записи для собраний и трансляций. Организационная запись означает, что организации могут использовать Teams для звонков и собраний в соответствии с административной политикой, когда звонки и собрания по сети должны автоматически записываться и записываться для последующей обработки и хранения, как требуется соответствующей корпоративной или регулятивной политикой. Пользователи, в соответствии с этой политикой, будут знать, что их цифровые взаимодействия с Teams записывают, но они не смогут отключить запись и не смогут получить доступ к записи после завершения взаимодействия. Запись становится частью архива организации, доступного для соответствия требованиям и юридических лиц для eDiscovery, удержания по юридическим и другим корпоративным средствам хранения.

## <a name="example-user-needs"></a>Пример потребностей пользователя

<table>
<thead>
<tr class="header">
<th><strong>Persona</strong></th>
<th><strong>Потребности</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Зарегистрированные пользователи</td>
<td><ul>
<li><p>По уведомлению о процессе записи.</p></li>
<li><p>Будьте в курсе, когда ошибка политики или записи вызывает изменения в поведение звонков.</p></li>
</ul></td>
</tr>
<tr class="even">
<td>Администратор связи</td>
<td><ul>
<li><p>Причины и применение политик записи для пользователей и конечных точек Teams.</p></li>
<li><p>Настройте и настройте политики записи Teams для организации.</p></li>
<li><p>Отслеживайте и устраняйте проблемы с записью звонков и собраний Teams.</p></li>
<li><p>Поддержка внутреннего сотрудника по обеспечению соответствия требованиям с помощью оперативных аналитики по использованию, качеству и надежности.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>Сотрудник, который соответствует требованиям</td>
<td><ul>
<li><p>Сбор всех коммуникаций Teams в соответствии с обязательствами по соответствию требованиям в соответствии с региональными границами.</p></li>
<li><p>Поиск взаимодействия на основе метаданных, связанных с коммуникациями, или контента для взаимодействия. Вот некоторые примеры:</p>
<ul>
<li><p><strong>Метаданные</strong> - Участники, время, направление, номер набора номера, источник, пользовательские бизнес-данные</p></li>
<li><p><strong>Содержимое</strong> — транскрипция, тональность, фонетическое отношение, связанные взаимодействия</p></li>
</ul></li>
<li><p>Анализируйте собранные сообщения и взаимодействуйте с ними, в том числе отслеживайте взаимодействия по мере их сбора.</p></li>
<li><p>Обеспечение безопасности собранных сообщений и предотвращение подделывки на всех этапах.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>Обзор архитектуры решения

Решения для записи соответствия требованиям интегрируются с Teams, как показано на приведенной ниже схеме.

![Снимок экрана: настройка пользовательского приложения группы](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "На рисунках показан поток при отправлении и получении собрания или звонка Teams.")

## <a name="recorder"></a>Recorder

Основным компонентом решения для записи соответствия требованиям является самозапись.
Записи основаны на масштабируемых службах (ботах) Azure, которые используют коммуникационную платформу [<span class="underline">Майкрософт</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) и регистрируются как приложения в Microsoft Graph. Регистратор обеспечивает прямое взаимодействие с [<span class="underline">API</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) платформы связи teams и собраний и предоставляет конечную точку для передачи медиазаписи.

Доступно [<span class="underline">образец приложения для записи</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) соответствия требованиям, в которое показано, как настроить бот, создать экземпляр приложения и назначить политики соответствия требованиям. В примере также есть примеры использования API для записи определенных взаимодействий, таких как обработка маршрутов входящих вызовов, изменение состояния записи и удаление пользователя, который [<span class="underline">записывается.</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126) [<span class="underline"></span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) [<span class="underline"></span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)
Документацию по определенным API-графикам можно найти здесь для [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) и [<span class="underline">incomingContext.</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0)

Конкретное внедрение службы записи зависит от партнера, но необходимо обеспечить поддержку нескольких записей для обеспечения высокой доступности и географического распространения развертывания, чтобы уменьшить задержки при доступе teams к средству записи. Кроме того, предполагается, что сами записи разработаны с учетом отказоустойчивости и избыточности.

Перед отправкой решения для сертификации партнерам необходимо подтвердить минимальную версию API для связи Microsoft Graph и SDKs, чтобы обеспечить поддержку всех требований интеграции с записью соответствия требованиям.

Основные требования для записи соответствия требованиям:

- Бот "Запись" должен быть развернут в Azure

- Бот "Запись" должен запускаться на windows VM в Azure

Требования к VM для Azure и Windows применяются только к компоненту бота Teams, поэтому партнер может реализовать оставшуюся платформу при условии, что он сможет соответствовать требованиям к производительности и функциональным требованиям для записи соответствия требованиям.

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>Назначение и подготовка политики записи соответствия

С помощью создания и назначения политик записи соответствия ИТ-администраторы могут определить, каких пользователей нужно записывать и какие записи будут использоваться для каждого пользователя. Регистраторам автоматически предлагается участвовать в беседах в зависимости от конфигурации этих политик при взаимодействии с другими участниками. Политика записи соответствия требованиям управляется с помощью [<span class="underline">Microsoft PowerShell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) и может применяться на уровне клиента, пользователя и группы безопасности для каждой организации. Дополнительные сведения о политиках [<span class="underline"></span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams)собраний, [<span class="underline"></span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy) политиках звонков и групповых политиках в Microsoft [<span class="underline">Docs.</span>](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group)

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

3. Назначьте политику записи соответствия требованиям пользователю.

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

## <a name="user-experiences"></a>Пользовательские интерфейсы

Поддержка уведомлений включена в клиентских приложениях Teams. Эти функции могут быть визуальными или звуковые.

**Клиенты Teams — визуальное уведомление**
- Настольный/веб-браузер
- Мобильные устройства (iOS и Android)
- Телефоны Teams
- Комнаты Teams

**Другие конечные точки — уведомление о звуке**
- Телефоны SIP
- Skype для бизнеса
- Аудиоконференции
- Вызыватели ННОП

## <a name="compliance-recording-for-teams-certification-programs"></a>Запись соответствия требованиям для программ сертификации Teams

Помимо публикации общедоступных API, позволяющих партнерам разрабатывать решения CCaaS и интегрировать их с Teams, мы разработали запись соответствия требованиям для программы сертификации Microsoft Teams, чтобы предоставить клиентам подтверждение того, что решение каждого из партнеров протестировали и проверили для обеспечения качества, совместимости и надежности, которых они ждут от решений Майкрософт.  

Следующие партнеры сертифицированы для Microsoft Teams.

|Партнер|Веб-сайт решения |
|:--|:--|
|AudioCodes |[https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360](https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360) |
|NICE |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |


Следующие партнеры находятся в процессе сертификации своего решения для Microsoft Teams.

|Партнер|Веб-сайт решения |
|:--|:--|
|ASC Technologies |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|Даббер |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|Landis Technologies |[https://landistechnologies.com/](https://landistechnologies.com/) |
|Luware |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|Инновации |[https://www.oakinnovate.com/call-recording](https://www.oakinnovate.com/call-recording) |
|Красный квадрат |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

Этот список будет обновляться по мере того, как другие партнеры присоединятся к нему и соответствуют условиям сертификации.

## <a name="next-steps"></a>Дальнейшие действия

Если вы — поставщик, который хочет присоединиться к программе сертификации, обратитесь в <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com.</a>
