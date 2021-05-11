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
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a><span data-ttu-id="8598c-103">Введение в Teams на основе политики для звонков & собраниях</span><span class="sxs-lookup"><span data-stu-id="8598c-103">Introduction to Teams policy-based recording for callings & meetings</span></span>

<span data-ttu-id="8598c-104">Запись на основе политики позволяет организациям, которые Microsoft Teams звонки и собрания, используя административную политику, автоматически записывать и записывать звонки и собрания по сети для последующей обработки и хранения, как требуется соответствующей корпоративной или регулятивной политикой.</span><span class="sxs-lookup"><span data-stu-id="8598c-104">Policy-based recording enables organizations that adopt Microsoft Teams for calling and meetings to stipulate, using an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span>

<span data-ttu-id="8598c-105">Teams поддерживает интеграцию сторонних решений записи, включая функциональные возможности платформы, пользовательские интерфейсы и интерфейсы администрирования, необходимые для предоставления конечного решения для настройки, управления, записи, хранения и анализа Teams взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="8598c-105">Teams has been enhanced to support integration of third-party recording solutions, including the platform functionality, user experiences, and administrative interfaces needed to provide an end-to-end solution for configuring, managing, recording, storing, and analyzing Teams communications.</span></span> <span data-ttu-id="8598c-106">Усовершенствования включают API платформы связи и события для записи, которые предоставляют следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="8598c-106">Enhancements include communications platform APIs and events for recording, which provides:</span></span>

- <span data-ttu-id="8598c-107">Бесперебойная высококачественная запись мультимедиа на разных устройствах и все поддерживаемые конечные точки для аудио- и видеосвязи, обмена экранами и чата.</span><span class="sxs-lookup"><span data-stu-id="8598c-107">Seamless, high-quality media capture across devices and all   supported endpoints for audio, video, screen share, and chat.</span></span>

- <span data-ttu-id="8598c-108">Поддержка взаимодействия между пользователями Teams и поддерживаемых конечных точек звонков (Teams, Teams Mobile, Skype для бизнеса, STN)</span><span class="sxs-lookup"><span data-stu-id="8598c-108">Support for interaction capture between Teams users and supported   calling endpoints (Teams, Teams Mobile, Skype for Business, PSTN)</span></span>

- <span data-ttu-id="8598c-109">Новые административные политики для записи соответствия требованиям, в том числе интеграция с существующими Teams административными звонками, инструментами и политиками собраний</span><span class="sxs-lookup"><span data-stu-id="8598c-109">New administrative policies for compliance recording, including   integration with existing Teams administrative calling and   meeting tools and policies</span></span>

<span data-ttu-id="8598c-110">Запись соответствия требованиям можно включить Microsoft 365 пользователей A3/A5/E3/E5/Business Premium и Office 365 A3/A5/E3/E5.</span><span class="sxs-lookup"><span data-stu-id="8598c-110">Compliance Recording can be enabled on Microsoft 365 A3/A5/E3/E5/Business Premium and Office 365 A3/A5/E3/E5 users.</span></span> 

<span data-ttu-id="8598c-111">Возможности интеграции с решением для записи соответствия требованиям также [](https://myignite.microsoft.com/archives/IG19-VCE40)были рассмотрены на Microsoft Teams Ignite 2019.</span><span class="sxs-lookup"><span data-stu-id="8598c-111">The compliance recording solution integration capabilities were also reviewed at Ignite 2019 in the [Compliance Recording and Microsoft Teams session](https://myignite.microsoft.com/archives/IG19-VCE40).</span></span>

## <a name="teams-interaction-recording-overview"></a><span data-ttu-id="8598c-112">Teams обзор записи взаимодействия</span><span class="sxs-lookup"><span data-stu-id="8598c-112">Teams interaction recording overview</span></span>

<span data-ttu-id="8598c-113">Случаи использования записи взаимодействия можно разделить на четыре основные категории функций записи: удобство, функциональный, организационный и юридический отладок, как показано на рисунке:</span><span class="sxs-lookup"><span data-stu-id="8598c-113">Interaction recording use cases can effectively be separated into four primary categories of recording functionality – Convenience, Functional, Organizational, and Lawful Intercept, as shown in the image:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8598c-114">![Снимок экрана: запись о том, что и почему происходит при взаимодействии.](media/recording-taxonomy.png "На изображении показаны категории записи.")</span><span class="sxs-lookup"><span data-stu-id="8598c-114">![Screenshot showing the interaction recording what and why.](media/recording-taxonomy.png "The image shows the recording categories.")</span></span>

<span data-ttu-id="8598c-115">Для каждой категории должны быть задаены разные требования к способу начала записи, хранению записей, хранению записей, уведомлению о том, кто контролирует доступ и как обрабатывается хранение.</span><span class="sxs-lookup"><span data-stu-id="8598c-115">Each of the categories entails different requirements for how recordings are initiated, what is recorded, where recordings are stored, who is notified, who controls access, and how retention is handled.</span></span>

| <span data-ttu-id="8598c-116">Тип</span><span class="sxs-lookup"><span data-stu-id="8598c-116">Type</span></span>                   | <span data-ttu-id="8598c-117">Удобство (обычная Teams запись)</span><span class="sxs-lookup"><span data-stu-id="8598c-117">Convenience (Regular Teams Recording)</span></span> | <span data-ttu-id="8598c-118">Регулируемая организация (запись соответствия требованиям)</span><span class="sxs-lookup"><span data-stu-id="8598c-118">Org - Regulated (Compliance Recording)</span></span> |
| ---------------------- | ------------------ | --------------- |
| <span data-ttu-id="8598c-119">Инициатор</span><span class="sxs-lookup"><span data-stu-id="8598c-119">Initiator</span></span>              | <span data-ttu-id="8598c-120">Пользователь</span><span class="sxs-lookup"><span data-stu-id="8598c-120">User</span></span>               | <span data-ttu-id="8598c-121">Администратор (система)</span><span class="sxs-lookup"><span data-stu-id="8598c-121">Admin (system)</span></span>  |
| <span data-ttu-id="8598c-122">Target (Назначение)</span><span class="sxs-lookup"><span data-stu-id="8598c-122">Target</span></span>                 | <span data-ttu-id="8598c-123">Per-call / meeting</span><span class="sxs-lookup"><span data-stu-id="8598c-123">Per-call / meeting</span></span> | <span data-ttu-id="8598c-124">Для пользователя</span><span class="sxs-lookup"><span data-stu-id="8598c-124">Per-user</span></span>        |
| <span data-ttu-id="8598c-125">служба хранилища владелец</span><span class="sxs-lookup"><span data-stu-id="8598c-125">Storage owner</span></span>          | <span data-ttu-id="8598c-126">Пользователь</span><span class="sxs-lookup"><span data-stu-id="8598c-126">User</span></span>               | <span data-ttu-id="8598c-127">Соответствие требованиям</span><span class="sxs-lookup"><span data-stu-id="8598c-127">Compliance</span></span>      |
| <span data-ttu-id="8598c-128">Обязательное уведомление?</span><span class="sxs-lookup"><span data-stu-id="8598c-128">Notification required?</span></span> | <span data-ttu-id="8598c-129">Да</span><span class="sxs-lookup"><span data-stu-id="8598c-129">Yes</span></span>                | <span data-ttu-id="8598c-130">Да</span><span class="sxs-lookup"><span data-stu-id="8598c-130">Yes</span></span>             |
| <span data-ttu-id="8598c-131">Владелец Access</span><span class="sxs-lookup"><span data-stu-id="8598c-131">Access Owner</span></span>           | <span data-ttu-id="8598c-132">Пользователь</span><span class="sxs-lookup"><span data-stu-id="8598c-132">User</span></span>               | <span data-ttu-id="8598c-133">Соответствие требованиям</span><span class="sxs-lookup"><span data-stu-id="8598c-133">Compliance</span></span>      |
| <span data-ttu-id="8598c-134">Политика хранения?</span><span class="sxs-lookup"><span data-stu-id="8598c-134">Retention Policy?</span></span>      | <span data-ttu-id="8598c-135">Необязательно </span><span class="sxs-lookup"><span data-stu-id="8598c-135">Optional</span></span>           | <span data-ttu-id="8598c-136">Да</span><span class="sxs-lookup"><span data-stu-id="8598c-136">Yes</span></span>             |

<span data-ttu-id="8598c-137">Teams возможности удобной и [](./cloud-recording.md) функциональной записи для собраний и трансляций.</span><span class="sxs-lookup"><span data-stu-id="8598c-137">Teams provides various capabilities for [convenient](./cloud-recording.md) and functional recording for meetings and live events.</span></span> <span data-ttu-id="8598c-138">Организационная запись позволяет организациям Teams организации Teams звонков и собраний в соответствии с административной политикой, когда звонки и собрания по сети должны автоматически записываться и записываться для последующей обработки и хранения, как требуется соответствующей корпоративной или регулятивной политикой.</span><span class="sxs-lookup"><span data-stu-id="8598c-138">Organizational recording means enabling organizations adopting Teams for calling and meetings to stipulate, by way of an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span> <span data-ttu-id="8598c-139">Пользователи этой политики будут знать, что их цифровые взаимодействия с Teams записываются, но они не смогут отключить запись и не будут иметь доступа к записи после завершения взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="8598c-139">Users under this policy will be aware that their digital interactions with Teams are being recorded but will not be able to disable the recording and will not have access to the recording once the interaction is complete.</span></span> <span data-ttu-id="8598c-140">Запись становится частью архива организации, доступного для соответствия требованиям и юридических лиц при обнаружении электронных данных, удержании по юридическим и другим корпоративным средствам хранения.</span><span class="sxs-lookup"><span data-stu-id="8598c-140">The recording becomes part of the organizational archive available to compliance and legal personnel for eDiscovery, legal hold, and other corporate retention uses.</span></span>

## <a name="example-user-needs"></a><span data-ttu-id="8598c-141">Пример потребностей пользователей</span><span class="sxs-lookup"><span data-stu-id="8598c-141">Example user needs</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="8598c-142">Персоной</span><span class="sxs-lookup"><span data-stu-id="8598c-142">Persona</span></span></th>
<th><span data-ttu-id="8598c-143">Потребности</span><span class="sxs-lookup"><span data-stu-id="8598c-143">Needs</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="8598c-144">Зарегистрированные пользователи</span><span class="sxs-lookup"><span data-stu-id="8598c-144">Recorded users</span></span></td>
<td><ul>
<li><p><span data-ttu-id="8598c-145">По уведомлению о ходе записи.</span><span class="sxs-lookup"><span data-stu-id="8598c-145">Be notified when recording is in progress.</span></span></p></li>
<li><p><span data-ttu-id="8598c-146">Будьте в курсе, когда политика и/или ошибка записи приводит к изменениям поведения при звонках.</span><span class="sxs-lookup"><span data-stu-id="8598c-146">Be informed when policy and/or recorder error is causing changes in calling behavior.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8598c-147">Администратор связи</span><span class="sxs-lookup"><span data-stu-id="8598c-147">Communications admin</span></span></td>
<td><ul>
<li><p><span data-ttu-id="8598c-148">Понять, почему и как применять политики записи и применять к Teams пользователям и конечным точкам.</span><span class="sxs-lookup"><span data-stu-id="8598c-148">Understand why and how to apply / enforce recording policies to Teams users / endpoints.</span></span></p></li>
<li><p><span data-ttu-id="8598c-149">Настройте и Teams политики записи для организации.</span><span class="sxs-lookup"><span data-stu-id="8598c-149">Configure and maintain Teams recording policies for the organization.</span></span></p></li>
<li><p><span data-ttu-id="8598c-150">Отслеживайте и устраняйте проблемы, связанные с записью, Teams звонками и собраниями.</span><span class="sxs-lookup"><span data-stu-id="8598c-150">Monitor and troubleshoot recording-related issues with Teams calls and meetings.</span></span></p></li>
<li><p><span data-ttu-id="8598c-151">Поддержка внутреннего сотрудника по обеспечению соответствия требованиям с помощью операционной аналитики по использованию, качеству и надежности.</span><span class="sxs-lookup"><span data-stu-id="8598c-151">Support internal compliance officer with operational analytics on usage, quality, and reliability.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8598c-152">Сотрудник по обеспечению соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="8598c-152">Compliance officer</span></span></td>
<td><ul>
<li><p><span data-ttu-id="8598c-153">Сбор всех Teams сообщений в соответствии с обязательствами по соответствию требованиям в соответствующих региональных границах.</span><span class="sxs-lookup"><span data-stu-id="8598c-153">Collect all Teams communications in the manner required to meet compliance obligations in appropriate regional boundaries.</span></span></p></li>
<li><p><span data-ttu-id="8598c-154">Поиск взаимодействий на основе связанных с общением метаданных или контента взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="8598c-154">Search for interactions based on communication-related metadata or interaction content.</span></span> <span data-ttu-id="8598c-155">Примерами могут быть следующие:</span><span class="sxs-lookup"><span data-stu-id="8598c-155">Common examples include:</span></span></p>
<ul>
<li><p><span data-ttu-id="8598c-156"><strong>Метаданные</strong> - Участники, время, направление, номер набора, номер источника, пользовательские бизнес-данные</span><span class="sxs-lookup"><span data-stu-id="8598c-156"><strong>Metadata</strong> - Participants, time, direction, dialed number, origin number, Custom business data</span></span></p></li>
<li><p><span data-ttu-id="8598c-157"><strong>Содержимое</strong> — транскрибация, расшифровка, фонетическое отношение, связанные взаимодействия</span><span class="sxs-lookup"><span data-stu-id="8598c-157"><strong>Content</strong> – Transcription, sentiment, phonetics, related interactions</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="8598c-158">Анализируйте собранные сообщения и взаимодействуйте с ними, в том числе отслеживайте взаимодействие по мере их сбора.</span><span class="sxs-lookup"><span data-stu-id="8598c-158">Analyze and interact with collected communications, including the ability to monitor interactions as they are being collected.</span></span></p></li>
<li><p><span data-ttu-id="8598c-159">Обеспечение безопасности собранных сообщений и предотвращение подделывок на всех этапах.</span><span class="sxs-lookup"><span data-stu-id="8598c-159">Ensure security of collected communications and prevent tampering at all stages.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a><span data-ttu-id="8598c-160">Обзор архитектуры решений</span><span class="sxs-lookup"><span data-stu-id="8598c-160">Solution architecture overview</span></span>

<span data-ttu-id="8598c-161">Решения записи соответствия требованиям интегрируются с Teams, как показано на схеме ниже.</span><span class="sxs-lookup"><span data-stu-id="8598c-161">Compliance recording solutions are integrated with Teams as shown in the following diagram:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8598c-162">![Снимок экрана: настройка пользовательского приложения группы](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "На рисунках показан поток при Teams или звонка.")</span><span class="sxs-lookup"><span data-stu-id="8598c-162">![Screenshot showing the team custom app setting](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "The images shows the flow when a Teams meeting or call is sent and received.")</span></span>

## <a name="recorder"></a><span data-ttu-id="8598c-163">Рекордер</span><span class="sxs-lookup"><span data-stu-id="8598c-163">Recorder</span></span>

<span data-ttu-id="8598c-164">Основным компонентом решения для записи соответствия требованиям является регистратор.</span><span class="sxs-lookup"><span data-stu-id="8598c-164">The core component of the compliance recording solution is the recorder.</span></span>
<span data-ttu-id="8598c-165">Записи — это масштабируемые службы (боты) Azure, которые используют платформу коммуникаций Майкрософт и регистрируются как приложения в Microsoft Graph. [](/graph/cloud-communications-concept-overview)</span><span class="sxs-lookup"><span data-stu-id="8598c-165">Recorders are built as scalable Azure-based services (bots) that [leverage Microsoft’s communications platform](/graph/cloud-communications-concept-overview) and register as applications with Microsoft Graph.</span></span> <span data-ttu-id="8598c-166">Он обеспечивает непосредственное взаимодействие с API платформы [](/graph/api/resources/communications-api-overview?view=graph-rest-1.0) Teams звонков и собраний, а также конечную точку для передачи мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="8598c-166">The recorder provides the direct interaction with the Teams calls and meetings [communications platform APIs](/graph/api/resources/communications-api-overview?view=graph-rest-1.0) and provides the endpoint for media ingestion.</span></span>

<span data-ttu-id="8598c-167">Доступно [образец приложения для записи](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) соответствия требованиям, в которое показано, как настроить бот, создать экземпляр приложения и назначить политики соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="8598c-167">A [sample compliance recorder application is available](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) that shows how to configure the bot, create the app instance and assign the compliance policies.</span></span> <span data-ttu-id="8598c-168">В примере также есть примеры использования API для записи определенных взаимодействий, таких как обработка маршрутизаации входящих зовов, изменение состояния записи и удаление пользователя, [зарегистрированного.](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126) [](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) [](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)</span><span class="sxs-lookup"><span data-stu-id="8598c-168">The sample also has examples on API usage for recording specific interactions such as handling [incoming call](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) routing, [changing recording states](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138), and [removing the user who is being recorded](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span></span>
<span data-ttu-id="8598c-169">Graph документацию по определенным API можно найти здесь для [updateRecordingStatus](/graph/api/call-updaterecordingstatus?tabs=http&view=graph-rest-1.0) и [incomingContext.](/graph/api/resources/incomingcontext?view=graph-rest-1.0)</span><span class="sxs-lookup"><span data-stu-id="8598c-169">Graph documentation on the specific APIs can be found here for [updateRecordingStatus](/graph/api/call-updaterecordingstatus?tabs=http&view=graph-rest-1.0) and [incomingContext](/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span></span>

<span data-ttu-id="8598c-170">Точное внедрение службы записи зависит от партнера, но необходимо обеспечить поддержку нескольких записей, чтобы обеспечить высокую доступность и географическое распределение развертывания, чтобы уменьшить задержки от Teams до регистратора.</span><span class="sxs-lookup"><span data-stu-id="8598c-170">The exact implementation of the recorder service will vary by partner but must be designed to support multiple recorders in order to achieve high availability and geographical distribution of deployment to reduce latency from Teams to the recorder.</span></span> <span data-ttu-id="8598c-171">Кроме того, предполагается, что сами записи должны быть разработаны с учетом отказоустойчивости и избыточности.</span><span class="sxs-lookup"><span data-stu-id="8598c-171">In addition, it is expected that Recorders themselves be designed with resiliency and redundancy in mind.</span></span>

<span data-ttu-id="8598c-172">Перед отправкой решения для сертификации партнерам необходимо подтвердить минимальную версию API и SDKs для связи Microsoft Graph, чтобы обеспечить поддержку всех требований интеграции с записью соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="8598c-172">Partners must confirm the minimum required release version of the Microsoft Graph communications APIs and SDKs with Microsoft before submitting their solution for certification to ensure that all requirements of compliance recording integration are supported.</span></span>

<span data-ttu-id="8598c-173">Основные требования для записи соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="8598c-173">Two specific requirements that are fundamental for compliance recording scenario are:</span></span>

- <span data-ttu-id="8598c-174">Бот записи должен быть развернут в Azure</span><span class="sxs-lookup"><span data-stu-id="8598c-174">Recorder bot must be deployed in Azure</span></span>

- <span data-ttu-id="8598c-175">Бот записи должен запускаться на Windows VM в Azure</span><span class="sxs-lookup"><span data-stu-id="8598c-175">Recorder bot must run on a Windows VM in Azure</span></span>

<span data-ttu-id="8598c-176">Требования к VM для Azure и Windows применяются только к компоненту бота Teams, то есть партнеры могут реализовать остальные платформы, если им будут соответствовать соответствующие требования к производительности и функциональным требованиям для записи соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="8598c-176">The Azure and Windows VM requirements only apply to the Teams Bot component, which means that a partner may implement the rest of the platform of their choice provided they can meet the relevant performance and functional requirements for compliance recording.</span></span>

## <a name="compliance-recording-policy-assignment-and-provisioning"></a><span data-ttu-id="8598c-177">Назначение и подготовка политики записи соответствия</span><span class="sxs-lookup"><span data-stu-id="8598c-177">Compliance recording policy assignment and provisioning</span></span>

<span data-ttu-id="8598c-178">ИТ-администраторы могут определить, какие пользователи должны быть записаны и какие записи будут использоваться для каждого пользователя, создав и назначив политики записи соответствия.</span><span class="sxs-lookup"><span data-stu-id="8598c-178">IT Administrators can determine which users are to be recorded and which recorder will be used for each user, by creating and assigning compliance recording policies.</span></span> <span data-ttu-id="8598c-179">Регистраторы автоматически приглашаются к беседам в зависимости от конфигурации этих политик при взаимодействии.</span><span class="sxs-lookup"><span data-stu-id="8598c-179">Recorders are automatically invited to participate in conversations based on the configuration of these policies when a communication interaction takes place.</span></span> <span data-ttu-id="8598c-180">Политика записи соответствия требованиям управляется с помощью [Microsoft PowerShell](./teams-powershell-overview.md) и может применяться на уровне клиента, пользователя и группы безопасности для каждой организации.</span><span class="sxs-lookup"><span data-stu-id="8598c-180">Compliance recording policies are managed using [Microsoft PowerShell](./teams-powershell-overview.md) and can be applied at the tenant, per-user, and security group level for each organization.</span></span> <span data-ttu-id="8598c-181">Дополнительные сведения о microsoft Docs для [собраний,](./meeting-policies-in-teams.md)политиках звонков и [групповых](./teams-calling-policy.md) [политиках.](./assign-policies.md#assign-a-policy-to-a-group)</span><span class="sxs-lookup"><span data-stu-id="8598c-181">You can find more information on Microsoft Docs for [Meeting policies](./meeting-policies-in-teams.md), [calling policies](./teams-calling-policy.md) and  [group policies](./assign-policies.md#assign-a-policy-to-a-group).</span></span>

1. <span data-ttu-id="8598c-182">Создайте экземпляр приложения в своем клиенте.</span><span class="sxs-lookup"><span data-stu-id="8598c-182">Create an application instance in your tenant.</span></span>

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

2. <span data-ttu-id="8598c-183">Создайте политику записи соответствия.</span><span class="sxs-lookup"><span data-stu-id="8598c-183">Create a Compliance Recording policy.</span></span>

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

   <span data-ttu-id="8598c-184">См. [set-CsTeamsComplianceRecordingPolicy.](/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="8598c-184">See [Set-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps).</span></span>

3. <span data-ttu-id="8598c-185">Назначьте политику записи соответствия требованиям пользователю.</span><span class="sxs-lookup"><span data-stu-id="8598c-185">Assign the Compliance Recording policy to a user.</span></span>

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   <span data-ttu-id="8598c-186">См. [grant-CsTeamsComplianceRecordingPolicy.](/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="8598c-186">See [Grant-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps).</span></span>

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a><span data-ttu-id="8598c-187">Пользовательские интерфейсы</span><span class="sxs-lookup"><span data-stu-id="8598c-187">User experiences</span></span>

<span data-ttu-id="8598c-188">Поддержка уведомлений включена с помощью Teams клиента.</span><span class="sxs-lookup"><span data-stu-id="8598c-188">Support for notifications is enabled using the Teams client experiences.</span></span> <span data-ttu-id="8598c-189">Эти функции могут быть визуальными или звукозаписями.</span><span class="sxs-lookup"><span data-stu-id="8598c-189">The experiences can be either visual or audio.</span></span>

<span data-ttu-id="8598c-190">**Teams клиентов — визуальное уведомление**</span><span class="sxs-lookup"><span data-stu-id="8598c-190">**Teams clients - visual notice**</span></span>
- <span data-ttu-id="8598c-191">Рабочий стол или веб-сайт</span><span class="sxs-lookup"><span data-stu-id="8598c-191">Desktop/web</span></span>
- <span data-ttu-id="8598c-192">Мобильные устройства (iOS или Android)</span><span class="sxs-lookup"><span data-stu-id="8598c-192">Mobile (iOS/Android)</span></span>
- <span data-ttu-id="8598c-193">Teams телефонов</span><span class="sxs-lookup"><span data-stu-id="8598c-193">Teams phones</span></span>
- <span data-ttu-id="8598c-194">Teams помещений</span><span class="sxs-lookup"><span data-stu-id="8598c-194">Teams rooms</span></span>

<span data-ttu-id="8598c-195">**Другие конечные точки — уведомление о звуке**</span><span class="sxs-lookup"><span data-stu-id="8598c-195">**Other endpoints - audio notice**</span></span>
- <span data-ttu-id="8598c-196">Телефоны SIP</span><span class="sxs-lookup"><span data-stu-id="8598c-196">SIP phones</span></span>
- <span data-ttu-id="8598c-197">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="8598c-197">Skype for Business</span></span>
- <span data-ttu-id="8598c-198">Аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="8598c-198">Audio conferencing</span></span>
- <span data-ttu-id="8598c-199">Вызыватели через ПСОП</span><span class="sxs-lookup"><span data-stu-id="8598c-199">PSTN callers</span></span>

## <a name="compliance-recording-for-teams-certification-programs"></a><span data-ttu-id="8598c-200">Запись соответствия требованиям для Teams сертификации</span><span class="sxs-lookup"><span data-stu-id="8598c-200">Compliance recording for Teams certification programs</span></span>

<span data-ttu-id="8598c-201">Помимо публикации общедоступных API, позволяющих партнерам разрабатывать и интегрировать решения CCaaS с Teams, мы разработали запись соответствия требованиям для программы сертификации Microsoft Teams, чтобы гарантировать клиентам, что решение каждого из партнеров протестировали и проверили, чтобы обеспечить качество, совместимость и надежность решений Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8598c-201">In addition to publishing publicly available APIs allowing partners to develop and integrate CCaaS solutions with Teams, we have developed the compliance recording for Microsoft Teams certification program to provide customers with the assurance that each participating partner’s solution has been tested and verified to provide the quality, compatibility and reliability they expect from Microsoft solutions.</span></span>  

<span data-ttu-id="8598c-202">Следующие партнеры сертифицированы для Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8598c-202">The following partners have certified their solution for Microsoft Teams.</span></span><br/><br/>

|<span data-ttu-id="8598c-203">Партнер</span><span class="sxs-lookup"><span data-stu-id="8598c-203">Partner</span></span>|<span data-ttu-id="8598c-204">Веб-сайт решения</span><span class="sxs-lookup"><span data-stu-id="8598c-204">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="8598c-205">ASC Technologies</span><span class="sxs-lookup"><span data-stu-id="8598c-205">ASC Technologies</span></span> |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|<span data-ttu-id="8598c-206">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="8598c-206">AudioCodes</span></span> |[https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360](https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360) |
|<span data-ttu-id="8598c-207">Дублбер</span><span class="sxs-lookup"><span data-stu-id="8598c-207">Dubber</span></span> |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|<span data-ttu-id="8598c-208">Хороший</span><span class="sxs-lookup"><span data-stu-id="8598c-208">NICE</span></span> |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|<span data-ttu-id="8598c-209">Numonix</span><span class="sxs-lookup"><span data-stu-id="8598c-209">Numonix</span></span> |[https://numonix.cloud](https://numonix.cloud)    |
|<span data-ttu-id="8598c-210">Verint</span><span class="sxs-lookup"><span data-stu-id="8598c-210">Verint</span></span> |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |
|<span data-ttu-id="8598c-211">Theta Lake</span><span class="sxs-lookup"><span data-stu-id="8598c-211">Theta Lake</span></span> |[https://thetalake.com/integrations/microsoft/](https://thetalake.com/integrations/microsoft/) |
|<span data-ttu-id="8598c-212">CallCabinet</span><span class="sxs-lookup"><span data-stu-id="8598c-212">CallCabinet</span></span> |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |

<br/>
<span data-ttu-id="8598c-213">Следующие партнеры находятся в процессе сертификации своего решения для Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8598c-213">The following partners are in the process of certifying their solution for Microsoft Teams.</span></span><br/><br/>

|<span data-ttu-id="8598c-214">Партнер</span><span class="sxs-lookup"><span data-stu-id="8598c-214">Partner</span></span>|<span data-ttu-id="8598c-215">Веб-сайт решения</span><span class="sxs-lookup"><span data-stu-id="8598c-215">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="8598c-216">Landis Technologies</span><span class="sxs-lookup"><span data-stu-id="8598c-216">Landis Technologies</span></span> |[https://landistechnologies.com/](https://landistechnologies.com/) |
|<span data-ttu-id="8598c-217">Luware</span><span class="sxs-lookup"><span data-stu-id="8598c-217">Luware</span></span> |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|<span data-ttu-id="8598c-218">Инновации</span><span class="sxs-lookup"><span data-stu-id="8598c-218">Oak Innovation</span></span> |[https://www.oakinnovate.com/call-recording](https://www.oakinnovate.com/call-recording) |
|<span data-ttu-id="8598c-219">Красный квадрат</span><span class="sxs-lookup"><span data-stu-id="8598c-219">Red Box</span></span> |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |

<span data-ttu-id="8598c-220">Этот список будет обновляться по мере партнерами, которые присоединяются к ним и соответствуют условиям сертификации.</span><span class="sxs-lookup"><span data-stu-id="8598c-220">This list will be updated as more partners join and meet the certification criteria.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8598c-221">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="8598c-221">Next steps</span></span>

<span data-ttu-id="8598c-222">Если вы хотите присоединиться к программе сертификации, обратитесь по электронной <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com.</a></span><span class="sxs-lookup"><span data-stu-id="8598c-222">If you are a vendor seeking to join the certification program, please mail  <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>.</span></span>
