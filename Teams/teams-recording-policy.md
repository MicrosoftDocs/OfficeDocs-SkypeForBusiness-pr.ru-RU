---
title: Введение в запись на основе политик Teams для & звонков
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
ms.openlocfilehash: 7972febeab134f0ec075418e351c35ef7e273fcf
ms.sourcegitcommit: f22e050213798a8ff69c6d502a2fc142104ab213
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/30/2021
ms.locfileid: "51439674"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a><span data-ttu-id="05162-103">Введение в запись на основе политик Teams для звонков & собраниях</span><span class="sxs-lookup"><span data-stu-id="05162-103">Introduction to Teams policy-based recording for callings & meetings</span></span>

<span data-ttu-id="05162-104">Запись на основе политики позволяет организациям, использующим Microsoft Teams для звонков и собраний, использовать административную политику, когда звонки и собрания по сети должны быть автоматически записаны и записаны для последующей обработки и хранения, как требуется соответствующей корпоративной или регулятивной политикой.</span><span class="sxs-lookup"><span data-stu-id="05162-104">Policy-based recording enables organizations that adopt Microsoft Teams for calling and meetings to stipulate, using an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span>

<span data-ttu-id="05162-105">В Teams улучшена поддержка интеграции сторонних решений для записи, включая функции платформы, пользовательский интерфейс и интерфейсы администрирования, необходимые для предоставления конечного решения для настройки, управления, записи, хранения и анализа сообщений Teams.</span><span class="sxs-lookup"><span data-stu-id="05162-105">Teams has been enhanced to support integration of third-party recording solutions, including the platform functionality, user experiences, and administrative interfaces needed to provide an end-to-end solution for configuring, managing, recording, storing, and analyzing Teams communications.</span></span> <span data-ttu-id="05162-106">Усовершенствования включают API информационной платформы и события для записи, которые обеспечивают:</span><span class="sxs-lookup"><span data-stu-id="05162-106">Enhancements include communications platform APIs and events for recording, which provides:</span></span>

- <span data-ttu-id="05162-107">Простое и высококачественное видеосъемка мультимедиа на разных устройствах и все поддерживаемые конечные точки для аудио- и видеосвязи, обмена экранами и чата.</span><span class="sxs-lookup"><span data-stu-id="05162-107">Seamless, high-quality media capture across devices and all   supported endpoints for audio, video, screen share, and chat.</span></span>

- <span data-ttu-id="05162-108">Поддержка взаимодействия между пользователями Teams и поддерживаемых конечных точек звонков (Teams, Teams Mobile, Skype для бизнеса, PSTN)</span><span class="sxs-lookup"><span data-stu-id="05162-108">Support for interaction capture between Teams users and supported   calling endpoints (Teams, Teams Mobile, Skype for Business, PSTN)</span></span>

- <span data-ttu-id="05162-109">Новые административные политики для записи соответствия требованиям, включая интеграцию с существующими инструментами администрирования и политиками собраний Teams</span><span class="sxs-lookup"><span data-stu-id="05162-109">New administrative policies for compliance recording, including   integration with existing Teams administrative calling and   meeting tools and policies</span></span>

<span data-ttu-id="05162-110">Запись соответствия требованиям можно включить для пользователей Microsoft 365 A3/A5/E3/E5/Business Premium и Office 365 A3/A5/E3/E5.</span><span class="sxs-lookup"><span data-stu-id="05162-110">Compliance Recording can be enabled on Microsoft 365 A3/A5/E3/E5/Business Premium and Office 365 A3/A5/E3/E5 users.</span></span> 

<span data-ttu-id="05162-111">Интеграция решений для записи соответствия требованиям также была рассмотрена на веб-сайте Ignite 2019 в сеансе записи соответствия требованиям [<span class="underline">и Microsoft Teams.</span>](https://myignite.microsoft.com/archives/IG19-VCE40)</span><span class="sxs-lookup"><span data-stu-id="05162-111">The compliance recording solution integration capabilities were also reviewed at Ignite 2019 in the [<span class="underline">Compliance Recording and Microsoft Teams session</span>](https://myignite.microsoft.com/archives/IG19-VCE40).</span></span>

## <a name="teams-interaction-recording-overview"></a><span data-ttu-id="05162-112">Обзор записи взаимодействия в Teams</span><span class="sxs-lookup"><span data-stu-id="05162-112">Teams interaction recording overview</span></span>

<span data-ttu-id="05162-113">Дела записи взаимодействия можно разделить на четыре основные категории функций записи: удобство, функциональный, организационный и юридический перехват, как показано на изображении:</span><span class="sxs-lookup"><span data-stu-id="05162-113">Interaction recording use cases can effectively be separated into four primary categories of recording functionality – Convenience, Functional, Organizational, and Lawful Intercept, as shown in the image:</span></span>

<span data-ttu-id="05162-114">![Снимок экрана: запись взаимодействия: что и почему.](media/recording-taxonomy.png "На изображении показаны категории записи.")</span><span class="sxs-lookup"><span data-stu-id="05162-114">![Screenshot showing the interaction recording what and why.](media/recording-taxonomy.png "The image shows the recording categories.")</span></span>

<span data-ttu-id="05162-115">В каждой из категорий есть различные требования к способу начала записи, хранению записи, хранению записи, о том, кто уведомлен, кто контролирует доступ и как обрабатывается хранение.</span><span class="sxs-lookup"><span data-stu-id="05162-115">Each of the categories entails different requirements for how recordings are initiated, what is recorded, where recordings are stored, who is notified, who controls access, and how retention is handled.</span></span>

| <span data-ttu-id="05162-116">Тип</span><span class="sxs-lookup"><span data-stu-id="05162-116">Type</span></span>                   | <span data-ttu-id="05162-117">Удобство (обычная запись Teams)</span><span class="sxs-lookup"><span data-stu-id="05162-117">Convenience (Regular Teams Recording)</span></span> | <span data-ttu-id="05162-118">Регулируемая организация (запись соответствия требованиям)</span><span class="sxs-lookup"><span data-stu-id="05162-118">Org - Regulated (Compliance Recording)</span></span> |
| ---------------------- | ------------------ | --------------- |
| <span data-ttu-id="05162-119">Инициатор</span><span class="sxs-lookup"><span data-stu-id="05162-119">Initiator</span></span>              | <span data-ttu-id="05162-120">Пользователь</span><span class="sxs-lookup"><span data-stu-id="05162-120">User</span></span>               | <span data-ttu-id="05162-121">Администратор (система)</span><span class="sxs-lookup"><span data-stu-id="05162-121">Admin (system)</span></span>  |
| <span data-ttu-id="05162-122">Целевой объект</span><span class="sxs-lookup"><span data-stu-id="05162-122">Target</span></span>                 | <span data-ttu-id="05162-123">Per-call / meeting</span><span class="sxs-lookup"><span data-stu-id="05162-123">Per-call / meeting</span></span> | <span data-ttu-id="05162-124">На пользователя</span><span class="sxs-lookup"><span data-stu-id="05162-124">Per-user</span></span>        |
| <span data-ttu-id="05162-125">Владелец хранилища</span><span class="sxs-lookup"><span data-stu-id="05162-125">Storage owner</span></span>          | <span data-ttu-id="05162-126">Пользователь</span><span class="sxs-lookup"><span data-stu-id="05162-126">User</span></span>               | <span data-ttu-id="05162-127">Соответствие требованиям</span><span class="sxs-lookup"><span data-stu-id="05162-127">Compliance</span></span>      |
| <span data-ttu-id="05162-128">Требуется уведомление?</span><span class="sxs-lookup"><span data-stu-id="05162-128">Notification required?</span></span> | <span data-ttu-id="05162-129">Да</span><span class="sxs-lookup"><span data-stu-id="05162-129">Yes</span></span>                | <span data-ttu-id="05162-130">Да</span><span class="sxs-lookup"><span data-stu-id="05162-130">Yes</span></span>             |
| <span data-ttu-id="05162-131">Владелец Access</span><span class="sxs-lookup"><span data-stu-id="05162-131">Access Owner</span></span>           | <span data-ttu-id="05162-132">Пользователь</span><span class="sxs-lookup"><span data-stu-id="05162-132">User</span></span>               | <span data-ttu-id="05162-133">Соответствие требованиям</span><span class="sxs-lookup"><span data-stu-id="05162-133">Compliance</span></span>      |
| <span data-ttu-id="05162-134">Политика хранения?</span><span class="sxs-lookup"><span data-stu-id="05162-134">Retention Policy?</span></span>      | <span data-ttu-id="05162-135">Необязательно </span><span class="sxs-lookup"><span data-stu-id="05162-135">Optional</span></span>           | <span data-ttu-id="05162-136">Да</span><span class="sxs-lookup"><span data-stu-id="05162-136">Yes</span></span>             |

<span data-ttu-id="05162-137">Teams предоставляет различные возможности для [<span class="underline">удобной</span>](./cloud-recording.md) и функциональной записи для собраний и трансляций.</span><span class="sxs-lookup"><span data-stu-id="05162-137">Teams provides various capabilities for [<span class="underline">convenient</span>](./cloud-recording.md) and functional recording for meetings and live events.</span></span> <span data-ttu-id="05162-138">Организационная запись означает, что организации могут использовать Teams для звонков и собраний в соответствии с административной политикой, когда звонки и собрания по сети должны быть автоматически записаны и записаны для последующей обработки и хранения, как требуется соответствующей корпоративной или регулятивной политикой.</span><span class="sxs-lookup"><span data-stu-id="05162-138">Organizational recording means enabling organizations adopting Teams for calling and meetings to stipulate, by way of an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span> <span data-ttu-id="05162-139">Пользователи, в соответствии с этой политикой, будут знать, что их цифровые взаимодействия с Teams записывают, но не смогут отключить запись и не смогут получить доступ к записи после завершения взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="05162-139">Users under this policy will be aware that their digital interactions with Teams are being recorded but will not be able to disable the recording and will not have access to the recording once the interaction is complete.</span></span> <span data-ttu-id="05162-140">Запись становится частью архива организации, доступного для обеспечения соответствия требованиям и юридического персонала при обнаружении электронных данных, удержании по юридическим и другим корпоративным средствам хранения.</span><span class="sxs-lookup"><span data-stu-id="05162-140">The recording becomes part of the organizational archive available to compliance and legal personnel for eDiscovery, legal hold, and other corporate retention uses.</span></span>

## <a name="example-user-needs"></a><span data-ttu-id="05162-141">Пример потребностей пользователя</span><span class="sxs-lookup"><span data-stu-id="05162-141">Example user needs</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="05162-142"><strong>Persona</strong></span><span class="sxs-lookup"><span data-stu-id="05162-142"><strong>Persona</strong></span></span></th>
<th><span data-ttu-id="05162-143"><strong>Потребности</strong></span><span class="sxs-lookup"><span data-stu-id="05162-143"><strong>Needs</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="05162-144">Зарегистрированные пользователи</span><span class="sxs-lookup"><span data-stu-id="05162-144">Recorded users</span></span></td>
<td><ul>
<li><p><span data-ttu-id="05162-145">По уведомлению во время записи.</span><span class="sxs-lookup"><span data-stu-id="05162-145">Be notified when recording is in progress.</span></span></p></li>
<li><p><span data-ttu-id="05162-146">Будьте в курсе того, когда ошибка политики или записи вызывает изменения в поведение при вызове.</span><span class="sxs-lookup"><span data-stu-id="05162-146">Be informed when policy and/or recorder error is causing changes in calling behavior.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="05162-147">Администратор связи</span><span class="sxs-lookup"><span data-stu-id="05162-147">Communications admin</span></span></td>
<td><ul>
<li><p><span data-ttu-id="05162-148">В этой видео поймем, почему и как применять политики записи для пользователей и конечных точек Teams.</span><span class="sxs-lookup"><span data-stu-id="05162-148">Understand why and how to apply / enforce recording policies to Teams users / endpoints.</span></span></p></li>
<li><p><span data-ttu-id="05162-149">Настройте и настройте политики записи Teams для организации.</span><span class="sxs-lookup"><span data-stu-id="05162-149">Configure and maintain Teams recording policies for the organization.</span></span></p></li>
<li><p><span data-ttu-id="05162-150">Отслеживайте и устраняйте проблемы с записью звонков и собраний Teams.</span><span class="sxs-lookup"><span data-stu-id="05162-150">Monitor and troubleshoot recording-related issues with Teams calls and meetings.</span></span></p></li>
<li><p><span data-ttu-id="05162-151">Поддержка внутреннего сотрудника по обеспечению соответствия требованиям с помощью оперативных аналитики по использованию, качеству и надежности.</span><span class="sxs-lookup"><span data-stu-id="05162-151">Support internal compliance officer with operational analytics on usage, quality, and reliability.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="05162-152">Сотрудник, который соответствует требованиям</span><span class="sxs-lookup"><span data-stu-id="05162-152">Compliance officer</span></span></td>
<td><ul>
<li><p><span data-ttu-id="05162-153">Сбор всех коммуникаций Teams в соответствии с обязательствами по соответствию требованиям в соответствии с региональными границами.</span><span class="sxs-lookup"><span data-stu-id="05162-153">Collect all Teams communications in the manner required to meet compliance obligations in appropriate regional boundaries.</span></span></p></li>
<li><p><span data-ttu-id="05162-154">Поиск взаимодействия на основе метаданных, связанных с коммуникациями, или контента для взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="05162-154">Search for interactions based on communication-related metadata or interaction content.</span></span> <span data-ttu-id="05162-155">Вот некоторые примеры:</span><span class="sxs-lookup"><span data-stu-id="05162-155">Common examples include:</span></span></p>
<ul>
<li><p><span data-ttu-id="05162-156"><strong>Метаданные</strong> - Участники, время, направление, номер набора номера, источник, пользовательские бизнес-данные</span><span class="sxs-lookup"><span data-stu-id="05162-156"><strong>Metadata</strong> - Participants, time, direction, dialed number, origin number, Custom business data</span></span></p></li>
<li><p><span data-ttu-id="05162-157"><strong>Содержимое</strong> — транскрипция, тональность, фонетическое отношение, связанное взаимодействие</span><span class="sxs-lookup"><span data-stu-id="05162-157"><strong>Content</strong> – Transcription, sentiment, phonetics, related interactions</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="05162-158">Анализируйте собранные сообщения и взаимодействуйте с ними, в том числе отслеживайте взаимодействия по мере их сбора.</span><span class="sxs-lookup"><span data-stu-id="05162-158">Analyze and interact with collected communications, including the ability to monitor interactions as they are being collected.</span></span></p></li>
<li><p><span data-ttu-id="05162-159">Обеспечение безопасности собранных сообщений и предотвращение подделывки на всех этапах.</span><span class="sxs-lookup"><span data-stu-id="05162-159">Ensure security of collected communications and prevent tampering at all stages.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a><span data-ttu-id="05162-160">Обзор архитектуры решения</span><span class="sxs-lookup"><span data-stu-id="05162-160">Solution architecture overview</span></span>

<span data-ttu-id="05162-161">Решения для записи соответствия требованиям интегрируются с Teams, как показано на приведенной ниже схеме.</span><span class="sxs-lookup"><span data-stu-id="05162-161">Compliance recording solutions are integrated with Teams as shown in the following diagram:</span></span>

<span data-ttu-id="05162-162">![Снимок экрана: настройка пользовательского приложения группы](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "На рисунках показан поток при отправлении и получении собрания или звонка Teams.")</span><span class="sxs-lookup"><span data-stu-id="05162-162">![Screenshot showing the team custom app setting](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "The images shows the flow when a Teams meeting or call is sent and received.")</span></span>

## <a name="recorder"></a><span data-ttu-id="05162-163">Recorder</span><span class="sxs-lookup"><span data-stu-id="05162-163">Recorder</span></span>

<span data-ttu-id="05162-164">Основным компонентом решения для записи соответствия требованиям является самозапись.</span><span class="sxs-lookup"><span data-stu-id="05162-164">The core component of the compliance recording solution is the recorder.</span></span>
<span data-ttu-id="05162-165">Записи основаны на масштабируемых службах (ботах) Azure, которые используют платформу коммуникаций Майкрософт и регистрируются как приложения в Microsoft Graph. [<span class="underline"></span>](/graph/cloud-communications-concept-overview)</span><span class="sxs-lookup"><span data-stu-id="05162-165">Recorders are built as scalable Azure-based services (bots) that [<span class="underline">leverage Microsoft’s communications platform</span>](/graph/cloud-communications-concept-overview) and register as applications with Microsoft Graph.</span></span> <span data-ttu-id="05162-166">Регистратор обеспечивает непосредственное взаимодействие с [<span class="underline">API</span>](/graph/api/resources/communications-api-overview?view=graph-rest-1.0) платформы связи teams и собраний и предоставляет конечную точку для передачи медиазаписей.</span><span class="sxs-lookup"><span data-stu-id="05162-166">The recorder provides the direct interaction with the Teams calls and meetings [<span class="underline">communications platform APIs</span>](/graph/api/resources/communications-api-overview?view=graph-rest-1.0) and provides the endpoint for media ingestion.</span></span>

<span data-ttu-id="05162-167">Доступно [<span class="underline">образец приложения для записи</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) соответствия требованиям, в нем показано, как настроить бот, создать экземпляр приложения и назначить политики соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="05162-167">A [<span class="underline">sample compliance recorder application is available</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) that shows how to configure the bot, create the app instance and assign the compliance policies.</span></span> <span data-ttu-id="05162-168">В примере также есть примеры использования API для записи определенных взаимодействий, таких как обработка маршрутов входящих вызовов, изменение состояния записи и удаление пользователя, который [<span class="underline">записывается.</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126) [<span class="underline"></span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) [<span class="underline"></span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)</span><span class="sxs-lookup"><span data-stu-id="05162-168">The sample also has examples on API usage for recording specific interactions such as handling [<span class="underline">incoming call</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) routing, [<span class="underline">changing recording states</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138), and [<span class="underline">removing the user who is being recorded</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span></span>
<span data-ttu-id="05162-169">Документацию по определенным API-графикам можно найти здесь для [<span class="underline">updateRecordingStatus</span>](/graph/api/call-updaterecordingstatus?tabs=http&view=graph-rest-1.0) и [<span class="underline">incomingContext.</span>](/graph/api/resources/incomingcontext?view=graph-rest-1.0)</span><span class="sxs-lookup"><span data-stu-id="05162-169">Graph documentation on the specific APIs can be found here for [<span class="underline">updateRecordingStatus</span>](/graph/api/call-updaterecordingstatus?tabs=http&view=graph-rest-1.0) and [<span class="underline">incomingContext</span>](/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span></span>

<span data-ttu-id="05162-170">Конкретное внедрение службы записи зависит от партнера, но необходимо обеспечить поддержку нескольких записей для обеспечения высокой доступности и географического распространения развертывания, чтобы уменьшить задержки при доступе teams к средству записи.</span><span class="sxs-lookup"><span data-stu-id="05162-170">The exact implementation of the recorder service will vary by partner but must be designed to support multiple recorders in order to achieve high availability and geographical distribution of deployment to reduce latency from Teams to the recorder.</span></span> <span data-ttu-id="05162-171">Кроме того, предполагается, что сами записи разработаны с учетом устойчивость и избыточности.</span><span class="sxs-lookup"><span data-stu-id="05162-171">In addition, it is expected that Recorders themselves be designed with resiliency and redundancy in mind.</span></span>

<span data-ttu-id="05162-172">Перед отправкой решения для сертификации партнерам необходимо подтвердить минимальную версию API для связи Microsoft Graph и SDKs, чтобы обеспечить поддержку всех требований интеграции с записью соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="05162-172">Partners must confirm the minimum required release version of the Microsoft Graph communications APIs and SDKs with Microsoft before submitting their solution for certification to ensure that all requirements of compliance recording integration are supported.</span></span>

<span data-ttu-id="05162-173">Основные требования для записи соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="05162-173">Two specific requirements that are fundamental for compliance recording scenario are:</span></span>

- <span data-ttu-id="05162-174">Бот "Запись" должен быть развернут в Azure</span><span class="sxs-lookup"><span data-stu-id="05162-174">Recorder bot must be deployed in Azure</span></span>

- <span data-ttu-id="05162-175">Бот "Запись" должен запускаться на windows VM в Azure</span><span class="sxs-lookup"><span data-stu-id="05162-175">Recorder bot must run on a Windows VM in Azure</span></span>

<span data-ttu-id="05162-176">Требования к VM-версии Azure и Windows применяются только к компоненту бота Teams, поэтому партнер может реализовать оставшуюся платформу при условии, что он сможет соответствовать требованиям к производительности и функциональным требованиям для записи соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="05162-176">The Azure and Windows VM requirements only apply to the Teams Bot component, which means that a partner may implement the rest of the platform of their choice provided they can meet the relevant performance and functional requirements for compliance recording.</span></span>

## <a name="compliance-recording-policy-assignment-and-provisioning"></a><span data-ttu-id="05162-177">Назначение и подготовка политики записи соответствия</span><span class="sxs-lookup"><span data-stu-id="05162-177">Compliance recording policy assignment and provisioning</span></span>

<span data-ttu-id="05162-178">ИТ-администраторы могут определять, каких пользователей нужно записывать и какие записи будут использоваться для каждого пользователя, создавая и назначая политики записи соответствия.</span><span class="sxs-lookup"><span data-stu-id="05162-178">IT Administrators can determine which users are to be recorded and which recorder will be used for each user, by creating and assigning compliance recording policies.</span></span> <span data-ttu-id="05162-179">Регистраторам автоматически предлагается участвовать в беседах в зависимости от конфигурации этих политик при взаимодействии с другими участниками.</span><span class="sxs-lookup"><span data-stu-id="05162-179">Recorders are automatically invited to participate in conversations based on the configuration of these policies when a communication interaction takes place.</span></span> <span data-ttu-id="05162-180">Политика записи соответствия требованиям управляется с помощью [<span class="underline">Microsoft PowerShell</span>](./teams-powershell-overview.md) и может применяться на уровне клиента, пользователя и группы безопасности для каждой организации.</span><span class="sxs-lookup"><span data-stu-id="05162-180">Compliance recording policies are managed using [<span class="underline">Microsoft PowerShell</span>](./teams-powershell-overview.md) and can be applied at the tenant, per-user, and security group level for each organization.</span></span> <span data-ttu-id="05162-181">Дополнительные сведения о microsoft Docs для [<span class="underline"></span>](./teams-calling-policy.md) политик собраний, [<span class="underline"></span>](./meeting-policies-in-teams.md)политиках звонков и групповых политиках можно найти на сайте Microsoft [<span class="underline">Docs.</span>](./assign-policies.md#assign-a-policy-to-a-group)</span><span class="sxs-lookup"><span data-stu-id="05162-181">You can find more information on Microsoft Docs for [<span class="underline">Meeting policies</span>](./meeting-policies-in-teams.md), [<span class="underline">calling policies</span>](./teams-calling-policy.md) and  [<span class="underline">group policies</span>](./assign-policies.md#assign-a-policy-to-a-group).</span></span>

1. <span data-ttu-id="05162-182">Создайте экземпляр приложения в своем клиенте.</span><span class="sxs-lookup"><span data-stu-id="05162-182">Create an application instance in your tenant.</span></span>

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

2. <span data-ttu-id="05162-183">Создание политики записи соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="05162-183">Create a Compliance Recording policy.</span></span>

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

   [<span data-ttu-id="05162-184"><span class="underline">Set-CsTeamsComplianceRecordingPolicy</span></span><span class="sxs-lookup"><span data-stu-id="05162-184"><span class="underline">Set-CsTeamsComplianceRecordingPolicy</span></span></span>](/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. <span data-ttu-id="05162-185">Назначьте политику записи соответствия требованиям пользователю.</span><span class="sxs-lookup"><span data-stu-id="05162-185">Assign the Compliance Recording policy to a user.</span></span>

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   [<span data-ttu-id="05162-186"><span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span></span><span class="sxs-lookup"><span data-stu-id="05162-186"><span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span></span></span>](/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a><span data-ttu-id="05162-187">Пользовательские интерфейсы</span><span class="sxs-lookup"><span data-stu-id="05162-187">User experiences</span></span>

<span data-ttu-id="05162-188">Поддержка уведомлений включена в клиентских приложениях Teams.</span><span class="sxs-lookup"><span data-stu-id="05162-188">Support for notifications is enabled using the Teams client experiences.</span></span> <span data-ttu-id="05162-189">Эти функции могут быть визуальными или звуковые.</span><span class="sxs-lookup"><span data-stu-id="05162-189">The experiences can be either visual or audio.</span></span>

<span data-ttu-id="05162-190">**Клиенты Teams — визуальное уведомление**</span><span class="sxs-lookup"><span data-stu-id="05162-190">**Teams clients - visual notice**</span></span>
- <span data-ttu-id="05162-191">Настольный/веб-браузер</span><span class="sxs-lookup"><span data-stu-id="05162-191">Desktop/web</span></span>
- <span data-ttu-id="05162-192">Мобильные устройства (iOS и Android)</span><span class="sxs-lookup"><span data-stu-id="05162-192">Mobile (iOS/Android)</span></span>
- <span data-ttu-id="05162-193">Телефоны Teams</span><span class="sxs-lookup"><span data-stu-id="05162-193">Teams phones</span></span>
- <span data-ttu-id="05162-194">Комнаты Teams</span><span class="sxs-lookup"><span data-stu-id="05162-194">Teams rooms</span></span>

<span data-ttu-id="05162-195">**Другие конечные точки — уведомление о звуке**</span><span class="sxs-lookup"><span data-stu-id="05162-195">**Other endpoints - audio notice**</span></span>
- <span data-ttu-id="05162-196">Телефоны SIP</span><span class="sxs-lookup"><span data-stu-id="05162-196">SIP phones</span></span>
- <span data-ttu-id="05162-197">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="05162-197">Skype for Business</span></span>
- <span data-ttu-id="05162-198">Аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="05162-198">Audio conferencing</span></span>
- <span data-ttu-id="05162-199">Вызовы через ДНР</span><span class="sxs-lookup"><span data-stu-id="05162-199">PSTN callers</span></span>

## <a name="compliance-recording-for-teams-certification-programs"></a><span data-ttu-id="05162-200">Запись соответствия требованиям для программ сертификации Teams</span><span class="sxs-lookup"><span data-stu-id="05162-200">Compliance recording for Teams certification programs</span></span>

<span data-ttu-id="05162-201">Помимо публикации общедоступных API, позволяющих партнерам разрабатывать решения CCaaS и интегрировать их с Teams, мы разработали запись соответствия требованиям для программы сертификации Microsoft Teams, чтобы предоставить клиентам подтверждение того, что каждое решение партнера протестировали и проверили для обеспечения качества, совместимости и надежности, которых они ждут от решений Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="05162-201">In addition to publishing publicly available APIs allowing partners to develop and integrate CCaaS solutions with Teams, we have developed the compliance recording for Microsoft Teams certification program to provide customers with the assurance that each participating partner’s solution has been tested and verified to provide the quality, compatibility and reliability they expect from Microsoft solutions.</span></span>  

<span data-ttu-id="05162-202">Следующие партнеры сертифицированы для Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="05162-202">The following partners have certified their solution for Microsoft Teams.</span></span>

|<span data-ttu-id="05162-203">Партнер</span><span class="sxs-lookup"><span data-stu-id="05162-203">Partner</span></span>|<span data-ttu-id="05162-204">Веб-сайт решения</span><span class="sxs-lookup"><span data-stu-id="05162-204">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="05162-205">ASC Technologies</span><span class="sxs-lookup"><span data-stu-id="05162-205">ASC Technologies</span></span> |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|<span data-ttu-id="05162-206">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="05162-206">AudioCodes</span></span> |[https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360](https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360) |
|<span data-ttu-id="05162-207">Даббер</span><span class="sxs-lookup"><span data-stu-id="05162-207">Dubber</span></span> |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|<span data-ttu-id="05162-208">NICE</span><span class="sxs-lookup"><span data-stu-id="05162-208">NICE</span></span> |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |


<span data-ttu-id="05162-209">Следующие партнеры находятся в процессе сертификации своего решения для Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="05162-209">The following partners are in the process of certifying their solution for Microsoft Teams.</span></span>

|<span data-ttu-id="05162-210">Партнер</span><span class="sxs-lookup"><span data-stu-id="05162-210">Partner</span></span>|<span data-ttu-id="05162-211">Веб-сайт решения</span><span class="sxs-lookup"><span data-stu-id="05162-211">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="05162-212">CallCabinet</span><span class="sxs-lookup"><span data-stu-id="05162-212">CallCabinet</span></span> |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|<span data-ttu-id="05162-213">Landis Technologies</span><span class="sxs-lookup"><span data-stu-id="05162-213">Landis Technologies</span></span> |[https://landistechnologies.com/](https://landistechnologies.com/) |
|<span data-ttu-id="05162-214">Luware</span><span class="sxs-lookup"><span data-stu-id="05162-214">Luware</span></span> |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|<span data-ttu-id="05162-215">Numonix</span><span class="sxs-lookup"><span data-stu-id="05162-215">Numonix</span></span> |[https://numonix.cloud](https://numonix.cloud)    |
|<span data-ttu-id="05162-216">Инновации</span><span class="sxs-lookup"><span data-stu-id="05162-216">Oak Innovation</span></span> |[https://www.oakinnovate.com/call-recording](https://www.oakinnovate.com/call-recording) |
|<span data-ttu-id="05162-217">Красный квадрат</span><span class="sxs-lookup"><span data-stu-id="05162-217">Red Box</span></span> |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|<span data-ttu-id="05162-218">Verint</span><span class="sxs-lookup"><span data-stu-id="05162-218">Verint</span></span> |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |
|<span data-ttu-id="05162-219">Озеро Ата</span><span class="sxs-lookup"><span data-stu-id="05162-219">Theta Lake</span></span> |[https://thetalake.com/integrations/microsoft/](https://thetalake.com/integrations/microsoft/) |

<span data-ttu-id="05162-220">Этот список будет обновляться по мере того, как другие партнеры присоединятся к нему и соответствуют условиям сертификации.</span><span class="sxs-lookup"><span data-stu-id="05162-220">This list will be updated as more partners join and meet the certification criteria.</span></span>

## <a name="next-steps"></a><span data-ttu-id="05162-221">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="05162-221">Next steps</span></span>

<span data-ttu-id="05162-222">Если вы — поставщик, который хочет присоединиться к программе сертификации, <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com.</a></span><span class="sxs-lookup"><span data-stu-id="05162-222">If you are a vendor seeking to join the certification program, please mail  <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>.</span></span>
