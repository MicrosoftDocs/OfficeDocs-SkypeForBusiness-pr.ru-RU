---
title: Общие сведения о записи на основе политик Teams для звонков & собраний
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
description: Сведения о записи на основе политик Teams для звонков & собраний
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
- tier3
- purview-compliance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2e07da669e489a53dfabd2ee7c1fee2079497857
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392169"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>Общие сведения о записи на основе политик Teams для звонков & собраний

Запись на основе политик позволяет организациям, которые принимают Майкрософт Teams для звонков и собраний, чтобы указать, используя административную политику, когда звонки и собрания по сети должны автоматически записываться и записываться для последующей обработки и хранения в соответствии с требованиями соответствующей корпоративной или нормативной политики.

Teams была расширена для поддержки интеграции сторонних решений для записи, включая функциональные возможности платформы, интерфейсы пользователей и административные интерфейсы, необходимые для предоставления комплексного решения для настройки, управления, записи, хранения и анализа сообщений Teams. Усовершенствования включают API-интерфейсы платформы связи и события для записи, которые обеспечивают:

- Простой, высококачественный захват мультимедиа на разных устройствах и всех поддерживаемых конечных точках для аудио, видео, общего доступа к экрану и чата.

- Поддержка отслеживания взаимодействия между пользователями Teams и поддерживаемыми конечными точками вызовов (Teams, Teams Mobile, Skype для бизнеса, ТСОП)

- Новые административные политики для записи соответствия требованиям, включая интеграцию с существующими инструментами и политиками для административных звонков и собраний Teams.

Запись соответствия требованиям можно включить для пользователей Microsoft 365 A3/A5/E3/E5/Business Premium, Office 365 A3/A5/E3/E5, Комнаты Teams лицензии или лицензии Майкрософт общих устройств Teams.

> [!NOTE]
> Запись соответствия требованиям в настоящее время не поддерживается для служб экстренных вызовов E911.

Возможности интеграции решения для записи соответствия также были рассмотрены на Ignite 2019 в [сеансе записи соответствия требованиям и Майкрософт Teams](https://myignite.microsoft.com/archives/IG19-VCE40).

## <a name="teams-interaction-recording-overview"></a>Общие сведения о записи взаимодействия с Teams

Варианты использования записи взаимодействия можно эффективно разделить на четыре основные категории функций записи: Удобство, Функциональный, Организационный и Законный перехват, как показано на рисунке:

> [!div class="mx-imgBorder"]
> ![Снимок экрана: запись о том, что и почему.](media/recording-taxonomy.png "На изображении показаны категории записи.")

Каждая из категорий влечет за собой различные требования к тому, как инициируются записи, что записывается, где хранятся записи, кто уведомляется, кто контролирует доступ и как обрабатывается хранение.

| Тип                   | Удобство (обычная запись Teams) | Организация — регулируется (запись соответствия требованиям) |
| ---------------------- | ------------------ | --------------- |
| Инициатор              | Пользователь               | Администратор (система)  |
| Target (Назначение)                 | За звонок или собрание | Для пользователя        |
| Владелец хранилища          | Пользователь               | Соответствие требованиям      |
| Требуется уведомление? | Да                | Да             |
| Владелец доступа           | Пользователь               | Соответствие требованиям      |
| Политика хранения?      | Необязательно            | Да             |

Teams предоставляет различные возможности для [удобной](./cloud-recording.md) и функциональной записи собраний и трансляций. Организационная запись означает, что организации, которые применяют Teams для звонков и собраний, определяют в рамках административной политики, когда звонки и собрания по сети должны быть автоматически записаны и записаны для последующей обработки и хранения в соответствии с требованиями соответствующей корпоративной или нормативной политики. Пользователи, использующие эту политику, будут знать, что их цифровое взаимодействие с Teams записывается, но не смогут отключить запись и не будут иметь доступа к записи после завершения взаимодействия. Запись становится частью архива организации, доступного сотрудникам по соответствию требованиям и юридическим сотрудникам для обнаружения электронных данных, удержания по юридическим причинам и других корпоративных средств хранения.

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
<li><p>Получать уведомления о выполнении записи.</p></li>
<li><p>Будьте осведомлены о том, что ошибка политики или средства записи приводит к изменениям в поведении вызовов.</p></li>
</ul></td>
</tr>
<tr class="even">
<td>Администратор коммуникаций</td>
<td><ul>
<li><p>Узнайте, почему и как применять политики записи к пользователям и конечным точкам Teams.</p></li>
<li><p>Настройка и обслуживание политик записи Teams для организации.</p></li>
<li><p>Мониторинг и устранение проблем, связанных с записью, с помощью звонков и собраний Teams.</p></li>
<li><p>Поддержка внутреннего сотрудника по соответствию требованиям с помощью оперативной аналитики по использованию, качеству и надежности.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>Сотрудник по соответствию требованиям</td>
<td><ul>
<li><p>Сбор всех сообщений Teams способом, необходимым для выполнения обязательств по соответствию в соответствующих региональных границах.</p></li>
<li><p>Поиск взаимодействий на основе метаданных или содержимого взаимодействия, связанных с взаимодействием. Ниже приведены распространенные примеры.</p>
<ul>
<li><p><strong>Метаданных</strong> - Участники, время, направление, набранный номер, номер источника, пользовательские бизнес-данные</p></li>
<li><p><strong>Содержимое</strong> — транскрибирование, тональность, фонетика, связанные взаимодействия</p></li>
</ul></li>
<li><p>Анализ собранных сообщений и взаимодействие с ними, включая возможность отслеживания взаимодействий по мере их сбора.</p></li>
<li><p>Обеспечьте безопасность собранных сообщений и предотвратите незаконное изменение на всех этапах.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>Обзор архитектуры решения

Решения для записи соответствия требованиям интегрированы с Teams, как показано на следующей схеме:

> [!div class="mx-imgBorder"]
> ![Снимок экрана, показывающий параметры настраиваемого приложения для группы.](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "На изображениях показан поток при отправке и получении собрания Или звонка Teams.")

> [!NOTE]
> Это решение предназначено специально для включения записи соответствия на основе политик в Teams. Любое другое использование этого решения не будет поддерживаться.

## <a name="recorder"></a>Рекордер

Основным компонентом решения для записи соответствия требованиям является средство записи.
Средства записи создаются как масштабируемые службы (боты) на основе Azure, которые [используют коммуникационную платформу Майкрософт](/graph/cloud-communications-concept-overview) и регистрируются в качестве приложений в Майкрософт Graph. Средство записи обеспечивает прямое взаимодействие с [API-интерфейсами платформы связи для вызовов](/graph/api/resources/communications-api-overview) и собраний Teams, а также предоставляет конечную точку для приема мультимедиа.

[Доступен пример приложения для записи соответствия требованиям](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot), который показывает, как настроить бота, создать экземпляр приложения и назначить политики соответствия. Пример также содержит примеры использования API для записи определенных взаимодействий, таких как обработка маршрутизации [входящих вызовов](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) , [изменение состояния записи](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138) и [удаление записываемого пользователя](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).
Документацию graph по определенным API можно найти здесь для [updateRecordingStatus](/graph/api/call-updaterecordingstatus?tabs=http) и [incomingContext](/graph/api/resources/incomingcontext).

Точная реализация службы регистратора будет отличаться в зависимости от партнера, но должна быть разработана для поддержки нескольких регистраторов, чтобы обеспечить высокий уровень доступности и географическое распределение развертывания, чтобы уменьшить задержку между Teams и регистратором. Кроме того, ожидается, что сами регистраторы будут разработаны с учетом устойчивости и избыточности.

Перед отправкой решения на сертификацию партнеры должны подтвердить минимальную требуемую версию API-интерфейсов и пакетов SDK для связи Майкрософт Graph с Майкрософт, чтобы обеспечить поддержку всех требований интеграции записи соответствия.

Два конкретных требования, которые имеют основополагающее значение для сценария записи соответствия требованиям:

- Бот средства записи должен быть развернут в Azure

- Бот средства записи должен работать на виртуальной машине Windows в Azure

Требования к виртуальным машинам Azure и Windows применяются только к компоненту Teams Bot, что означает, что партнер может реализовать остальную часть платформы по своему выбору при условии, что он может соответствовать соответствующим требованиям к производительности и функциональным требованиям для записи соответствия требованиям.

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>Назначение и подготовка политики записи соответствия требованиям

ИТ-администраторы могут определить, какие пользователи должны быть записаны и какие средства записи будут использоваться для каждого пользователя, создавая и назначая политики записи соответствия требованиям. Регистраторы автоматически приглашаются к участию в беседах на основе конфигурации этих политик при взаимодействии с обменом данными. Политики записи соответствия управляются [с помощью Майкрософт PowerShell](./teams-powershell-overview.md) и могут применяться на уровне клиента, пользователя и группы безопасности для каждой организации. Дополнительные сведения см. в статье Майкрософт Learn для [политик собраний](./meeting-policies-overview.md), [политик звонков](./teams-calling-policy.md) и [групповых политик](./assign-policies-users-and-groups.md#assign-a-policy-to-a-group).

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

2. Создайте политику записи соответствия требованиям.

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

Поддержка уведомлений включена с помощью клиентского интерфейса Teams. Интерфейсы могут быть визуальными или звуковыми.

**Клиенты Teams — визуальное уведомление**
- Настольные и веб-приложения
- Мобильные устройства (iOS/Android)
- Телефоны Teams
- Комнаты Teams

**Другие конечные точки — звуковое уведомление**
- SIP-телефоны
- Skype для бизнеса
- Аудиоконференции (звуковое уведомление на языке по умолчанию или выбранном пользователем номера телефонного подключения)
- Абоненты ТСОП (звуковое уведомление на языке пользователя Teams по умолчанию)

> [!NOTE]
> Запись соответствия требованиям не поддерживается в очередях звонков в режиме конференции. Используйте очереди вызовов в режиме передачи.
> Запись соответствия требованиям не будет работать, если пользователи столкнулись с сбоем в Интернете и выполняют и получают вызовы по ТСОП с помощью SBA.

## <a name="compliance-recording-for-teams-certification-programs"></a>Запись соответствия для программ сертификации Teams

Помимо публикации общедоступных API- интерфейсов, позволяющих партнерам разрабатывать и интегрировать решения CCaaS с Teams, мы разработали запись соответствия для программы сертификации Майкрософт Teams, чтобы предоставить клиентам уверенность в том, что каждое решение партнера-участника было протестировано и проверено, чтобы обеспечить качество, совместимость и надежность, которые они ожидают от Майкрософт решений.  

Следующие партнеры сертифицировали свое решение для Майкрософт Teams.<br/><br/>

|Партнер|Веб-сайт решения |
|:--|:--|
|Технологии ASC |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|AudioCodes |[https://online.audiocodes.com/smarttap-360-live-for-microsoft-teams](https://online.audiocodes.com/smarttap-360-live-for-microsoft-teams) |
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|Даббер |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|Аналитические технологии |[https://insightfultechnology.com/teams/](https://insightfultechnology.com/teams/) |
|Mida Solutions |[https://www.midasolutions.com/recorder-for-teams/](https://www.midasolutions.com/recorder-for-teams/) |
|NICE Engage |[https://www.nice.com/products/workforce-engagement/call-recording/air-and-engage](https://www.nice.com/products/workforce-engagement/call-recording/air-and-engage) |
|NICE NTR |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|Дуб инноваций |[https://www.oakinnovate.com/clarify](https://www.oakinnovate.com/clarify) |
|Красная рамка |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/red-box-partners/microsoft-integration/compliance-recording-for-microsoft-teams)  |
|Озеро Тета |[https://thetalake.com/integrations/microsoft/](https://thetalake.com/integrations/microsoft/) |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |
|Дуб инноваций |[https://www.oakinnovate.com/clarify](https://www.oakinnovate.com/clarify) |

<br/>
Следующие партнеры сертифицируют свое решение для Майкрософт Teams.<br/><br/>

|Партнер|Веб-сайт решения |
|:--|:--|
|GuardRec |[https://www.guardrec.com/en/teams-compliance-recording/](https://www.guardrec.com/en/teams-compliance-recording/) |
|Landis Technologies |[https://landistechnologies.com/](https://landistechnologies.com/) |
|Luware |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|Redwood Technologies |[https://www.contentguru.com/en-gb/solutions/needs/compliance-recording-MS-Teams/](https://www.contentguru.com/en-gb/solutions/needs/compliance-recording-MS-Teams/) |


Этот список будет обновлен по мере того, как все больше партнеров присоединяются и соответствуют критериям сертификации.


## <a name="next-steps"></a>Дальнейшие действия

Если вы являетесь поставщиком, желающим присоединиться к программе сертификации, заполните [эту форму](https://aka.ms/CallingPlatformIntake) в качестве следующего шага. Если вам нужно указать дополнительный контекст и сведения, отправьте сообщение [Teamscategorypartner@microsoft.com.](mailto:Teamscategorypartner@microsoft.com)
