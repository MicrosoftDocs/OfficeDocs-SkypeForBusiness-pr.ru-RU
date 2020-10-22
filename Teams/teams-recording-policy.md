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
ms.openlocfilehash: af369a04836fd12c032f468324bbaf920417878d
ms.sourcegitcommit: 3a577c07b4f399c81d8650a2bba8cfc00b695b49
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48650972"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a><span data-ttu-id="fb95a-103">Общие сведения о записи на основе политики для групп звонков & собраний</span><span class="sxs-lookup"><span data-stu-id="fb95a-103">Introduction to Teams policy-based recording for callings & meetings</span></span>

<span data-ttu-id="fb95a-104">Запись на основе политики позволяет организациям, которые применяют Microsoft Teams для звонков и собраний в соответствии с использованием политики администрирования, когда звонки и собраний по сети должны автоматически записываться и записываться для последующей обработки и хранения в соответствии с требованиями, предусмотренными корпоративными или нормативными политиками.</span><span class="sxs-lookup"><span data-stu-id="fb95a-104">Policy-based recording enables organizations that adopt Microsoft Teams for calling and meetings to stipulate, using an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span>

<span data-ttu-id="fb95a-105">Группы были улучшены для поддержки интеграции сторонних решений для записи, в том числе функций платформы, взаимодействия с пользователем и административных интерфейсов, которые необходимы для создания комплексного решения для настройки, управления, записи, хранения и анализа коммуникаций в Teams.</span><span class="sxs-lookup"><span data-stu-id="fb95a-105">Teams has been enhanced to support integration of third-party recording solutions, including the platform functionality, user experiences, and administrative interfaces needed to provide an end-to-end solution for configuring, managing, recording, storing, and analyzing Teams communications.</span></span> <span data-ttu-id="fb95a-106">Сюда входят API платформы связи и события для записи, которые предоставляют следующие возможности.</span><span class="sxs-lookup"><span data-stu-id="fb95a-106">This includes communications platform APIs and events for recording, which provides:</span></span>

- <span data-ttu-id="fb95a-107">Высококачественная запись мультимедиа на разных устройствах и все поддерживаемые конечные точки для звука, видео, демонстрации экрана и чата.</span><span class="sxs-lookup"><span data-stu-id="fb95a-107">Seamless, high-quality media capture across devices and all   supported endpoints for audio, video, screen share, and chat.</span></span>

- <span data-ttu-id="fb95a-108">Поддержка захвата взаимодействия между пользователями Teams и поддерживаемыми конечными точками (Teams, Teams Mobile, Skype для бизнеса, КТСОП)</span><span class="sxs-lookup"><span data-stu-id="fb95a-108">Support for interaction capture between Teams users and supported   calling endpoints (Teams, Teams Mobile, Skype for Business, PSTN)</span></span>

- <span data-ttu-id="fb95a-109">Новые политики администрирования для записи соответствия требованиям, в том числе интеграция с существующими средствами администрирования, а также средства и политики для собраний.</span><span class="sxs-lookup"><span data-stu-id="fb95a-109">New administrative policies for compliance recording, including   integration with existing Teams administrative calling and   meeting tools and policies</span></span>

<span data-ttu-id="fb95a-110">Возможности интеграции с решением для записи соответствия требованиям также проверяются на Ignite 2019 в [<span class="underline">записи соответствия требованиям и сеансе Microsoft Teams</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions).</span><span class="sxs-lookup"><span data-stu-id="fb95a-110">The compliance recording solution integration capabilities were also reviewed at Ignite 2019 in the [<span class="underline">Compliance Recording and Microsoft Teams session</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions).</span></span>

## <a name="teams-interaction-recording-overview"></a><span data-ttu-id="fb95a-111">Общие сведения о записи взаимодействия в Teams</span><span class="sxs-lookup"><span data-stu-id="fb95a-111">Teams interaction recording overview</span></span>

<span data-ttu-id="fb95a-112">Сценарии использования для записи взаимодействия можно разделить на четыре основных категории функциональных возможностей записи: удобные, функциональные, организационные и законных перехваты, как показано на рисунке.</span><span class="sxs-lookup"><span data-stu-id="fb95a-112">Interaction recording use cases can effectively be separated into four primary categories of recording functionality – Convenience, Functional, Organizational, and Lawful Intercept, as shown in the image:</span></span>

<span data-ttu-id="fb95a-113">![Снимок экрана, на котором показано, что такое запись взаимодействия и почему.](media/recording-taxonomy.png "На изображении отображаются категории записи.")</span><span class="sxs-lookup"><span data-stu-id="fb95a-113">![Screenshot showing the interaction recording what and why.](media/recording-taxonomy.png "The image shows the recording categories.")</span></span>

<span data-ttu-id="fb95a-114">Каждая из категорий имеет разные требования для начала записи, что записывается, где хранятся записи, кто получает уведомление, кто управляет доступом и как выполняется обработка хранения.</span><span class="sxs-lookup"><span data-stu-id="fb95a-114">Each of the categories entails different requirements for how recordings are initiated, what is recorded, where recordings are stored, who is notified, who controls access, and how retention is handled.</span></span>

|                        | <span data-ttu-id="fb95a-115">Благодаря</span><span class="sxs-lookup"><span data-stu-id="fb95a-115">Convenience</span></span>        | <span data-ttu-id="fb95a-116">Функция</span><span class="sxs-lookup"><span data-stu-id="fb95a-116">Functional</span></span>         | <span data-ttu-id="fb95a-117">Org — общие</span><span class="sxs-lookup"><span data-stu-id="fb95a-117">Org - General</span></span>      | <span data-ttu-id="fb95a-118">Поднадзорные Организации</span><span class="sxs-lookup"><span data-stu-id="fb95a-118">Org - Regulated</span></span> | <span data-ttu-id="fb95a-119">Законных перехват</span><span class="sxs-lookup"><span data-stu-id="fb95a-119">Lawful Intercept</span></span>   |
| ---------------------- | ------------------ | ------------------ | ------------------ | --------------- | ------------------ |
| <span data-ttu-id="fb95a-120">Владельцы</span><span class="sxs-lookup"><span data-stu-id="fb95a-120">Initiator</span></span>              | <span data-ttu-id="fb95a-121">Пользователь</span><span class="sxs-lookup"><span data-stu-id="fb95a-121">User</span></span>               | <span data-ttu-id="fb95a-122">Приложение/решение</span><span class="sxs-lookup"><span data-stu-id="fb95a-122">App/Solution</span></span>       | <span data-ttu-id="fb95a-123">Администратор (система)</span><span class="sxs-lookup"><span data-stu-id="fb95a-123">Admin (system)</span></span>     | <span data-ttu-id="fb95a-124">Администратор (система)</span><span class="sxs-lookup"><span data-stu-id="fb95a-124">Admin (system)</span></span>  | <span data-ttu-id="fb95a-125">LEA</span><span class="sxs-lookup"><span data-stu-id="fb95a-125">LEA</span></span>                |
| <span data-ttu-id="fb95a-126">Целевой объект</span><span class="sxs-lookup"><span data-stu-id="fb95a-126">Target</span></span>                 | <span data-ttu-id="fb95a-127">Для каждого звонка или собрания</span><span class="sxs-lookup"><span data-stu-id="fb95a-127">Per-call / meeting</span></span> | <span data-ttu-id="fb95a-128">Для каждого звонка или собрания</span><span class="sxs-lookup"><span data-stu-id="fb95a-128">Per-call / meeting</span></span> | <span data-ttu-id="fb95a-129">Для каждого звонка или собрания</span><span class="sxs-lookup"><span data-stu-id="fb95a-129">Per-call / meeting</span></span> | <span data-ttu-id="fb95a-130">Для каждого пользователя</span><span class="sxs-lookup"><span data-stu-id="fb95a-130">Per-user</span></span>        | <span data-ttu-id="fb95a-131">На конечную точку/выполнено</span><span class="sxs-lookup"><span data-stu-id="fb95a-131">Per-endpoint / DID</span></span> |
| <span data-ttu-id="fb95a-132">Владелец хранилища</span><span class="sxs-lookup"><span data-stu-id="fb95a-132">Storage owner</span></span>          | <span data-ttu-id="fb95a-133">Пользователь</span><span class="sxs-lookup"><span data-stu-id="fb95a-133">User</span></span>               | <span data-ttu-id="fb95a-134">·</span><span class="sxs-lookup"><span data-stu-id="fb95a-134">App</span></span>                | <span data-ttu-id="fb95a-135">RAS</span><span class="sxs-lookup"><span data-stu-id="fb95a-135">Admin</span></span>              | <span data-ttu-id="fb95a-136">Соответствие требованиям</span><span class="sxs-lookup"><span data-stu-id="fb95a-136">Compliance</span></span>      | <span data-ttu-id="fb95a-137">LEA</span><span class="sxs-lookup"><span data-stu-id="fb95a-137">LEA</span></span>                |
| <span data-ttu-id="fb95a-138">Требуется уведомление?</span><span class="sxs-lookup"><span data-stu-id="fb95a-138">Notification required?</span></span> | <span data-ttu-id="fb95a-139">Да</span><span class="sxs-lookup"><span data-stu-id="fb95a-139">Yes</span></span>                | <span data-ttu-id="fb95a-140">Да</span><span class="sxs-lookup"><span data-stu-id="fb95a-140">Yes</span></span>                | <span data-ttu-id="fb95a-141">Да</span><span class="sxs-lookup"><span data-stu-id="fb95a-141">Yes</span></span>                | <span data-ttu-id="fb95a-142">Да</span><span class="sxs-lookup"><span data-stu-id="fb95a-142">Yes</span></span>             | <span data-ttu-id="fb95a-143">Нет</span><span class="sxs-lookup"><span data-stu-id="fb95a-143">No</span></span>                 |
| <span data-ttu-id="fb95a-144">Владелец Access</span><span class="sxs-lookup"><span data-stu-id="fb95a-144">Access Owner</span></span>           | <span data-ttu-id="fb95a-145">Пользователь</span><span class="sxs-lookup"><span data-stu-id="fb95a-145">User</span></span>               | <span data-ttu-id="fb95a-146">·</span><span class="sxs-lookup"><span data-stu-id="fb95a-146">App</span></span>                | <span data-ttu-id="fb95a-147">RAS</span><span class="sxs-lookup"><span data-stu-id="fb95a-147">Admin</span></span>              | <span data-ttu-id="fb95a-148">Соответствие требованиям</span><span class="sxs-lookup"><span data-stu-id="fb95a-148">Compliance</span></span>      | <span data-ttu-id="fb95a-149">LEA</span><span class="sxs-lookup"><span data-stu-id="fb95a-149">LEA</span></span>                |
| <span data-ttu-id="fb95a-150">Политика хранения?</span><span class="sxs-lookup"><span data-stu-id="fb95a-150">Retention Policy?</span></span>      | <span data-ttu-id="fb95a-151">Необязательно </span><span class="sxs-lookup"><span data-stu-id="fb95a-151">Optional</span></span>           | <span data-ttu-id="fb95a-152">Да</span><span class="sxs-lookup"><span data-stu-id="fb95a-152">Yes</span></span>                | <span data-ttu-id="fb95a-153">Да</span><span class="sxs-lookup"><span data-stu-id="fb95a-153">Yes</span></span>                | <span data-ttu-id="fb95a-154">Да</span><span class="sxs-lookup"><span data-stu-id="fb95a-154">Yes</span></span>             | <span data-ttu-id="fb95a-155">Да</span><span class="sxs-lookup"><span data-stu-id="fb95a-155">Yes</span></span>                |

<span data-ttu-id="fb95a-156">Teams предоставляет различные возможности для [<span class="underline">удобной</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) и функциональной записи для собраний и событий Live Events.</span><span class="sxs-lookup"><span data-stu-id="fb95a-156">Teams provides various capabilities for [<span class="underline">convenient</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) and functional recording for meetings and live events.</span></span> <span data-ttu-id="fb95a-157">Запись в Организации означает, что Организации, которые разрабатывают команды для звонков и собраний, в соответствии с политикой администрирования, при выполнении звонков и собраний по сети должны автоматически записываться и записываться для последующей обработки и хранения в соответствии с требованиями компании или законодательной политики.</span><span class="sxs-lookup"><span data-stu-id="fb95a-157">Organizational recording means enabling organizations adopting Teams for calling and meetings to stipulate, by way of an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span> <span data-ttu-id="fb95a-158">Пользователи в этой политике будут знать о том, что ваши цифровые взаимодействия с группами записываются, но они не смогут отключить запись и не получат доступ к записи после завершения взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="fb95a-158">Users under this policy will be aware that their digital interactions with Teams are being recorded but will not be able to disable the recording and will not have access to the recording once the interaction is complete.</span></span> <span data-ttu-id="fb95a-159">Запись становится частью организационного архива, доступного для соответствия и юридического персонала для обнаружения электронных данных, юридических удержаний и других целей хранения в корпоративной компании.</span><span class="sxs-lookup"><span data-stu-id="fb95a-159">The recording becomes part of the organizational archive available to compliance and legal personnel for eDiscovery, legal hold, and other corporate retention uses.</span></span>

## <a name="example-user-needs"></a><span data-ttu-id="fb95a-160">Примеры потребностей пользователей</span><span class="sxs-lookup"><span data-stu-id="fb95a-160">Example user needs</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="fb95a-161"><strong>Дайте</strong></span><span class="sxs-lookup"><span data-stu-id="fb95a-161"><strong>Persona</strong></span></span></th>
<th><span data-ttu-id="fb95a-162"><strong>Необходимо</strong></span><span class="sxs-lookup"><span data-stu-id="fb95a-162"><strong>Needs</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="fb95a-163">Записанные пользователи</span><span class="sxs-lookup"><span data-stu-id="fb95a-163">Recorded users</span></span></td>
<td><ul>
<li><p><span data-ttu-id="fb95a-164">Получать уведомления о ходе записи.</span><span class="sxs-lookup"><span data-stu-id="fb95a-164">Be notified when recording is in progress.</span></span></p></li>
<li><p><span data-ttu-id="fb95a-165">Будьте в курсе событий, вызывающих ошибки политики и (или) записи, которые приводят к изменениям в поведении вызова.</span><span class="sxs-lookup"><span data-stu-id="fb95a-165">Be informed when policy and/or recorder error is causing changes in calling behavior.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="fb95a-166">Администратор связи</span><span class="sxs-lookup"><span data-stu-id="fb95a-166">Communications admin</span></span></td>
<td><ul>
<li><p><span data-ttu-id="fb95a-167">Узнайте, почему и как применять политики записи к пользователям и конечным точкам Teams.</span><span class="sxs-lookup"><span data-stu-id="fb95a-167">Understand why and how to apply / enforce recording policies to Teams users / endpoints.</span></span></p></li>
<li><p><span data-ttu-id="fb95a-168">Настройте и настройте политики записи в Teams для Организации.</span><span class="sxs-lookup"><span data-stu-id="fb95a-168">Configure and maintain Teams recording policies for the organization.</span></span></p></li>
<li><p><span data-ttu-id="fb95a-169">Отслеживание и устранение проблем, связанных с записью, в рамках звонков и собраний Teams.</span><span class="sxs-lookup"><span data-stu-id="fb95a-169">Monitor and troubleshoot recording-related issues with Teams calls and meetings.</span></span></p></li>
<li><p><span data-ttu-id="fb95a-170">Поддержка внутреннего сотрудника по обеспечению соответствия требованиям в отношении использования, качества и надежности.</span><span class="sxs-lookup"><span data-stu-id="fb95a-170">Support internal compliance officer with operational analytics on usage, quality, and reliability.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="fb95a-171">Сотрудник отдела соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="fb95a-171">Compliance officer</span></span></td>
<td><ul>
<li><p><span data-ttu-id="fb95a-172">Соберите все коммуникации в Teams так, чтобы они соответствовали обязательствам по обеспечению соответствия требованиям в соответствующих региональных регионах.</span><span class="sxs-lookup"><span data-stu-id="fb95a-172">Collect all Teams communications in the manner required to meet compliance obligations in appropriate regional boundaries.</span></span></p></li>
<li><p><span data-ttu-id="fb95a-173">Поиск взаимодействий на основе метаданных или контента взаимодействия, связанных с связью.</span><span class="sxs-lookup"><span data-stu-id="fb95a-173">Search for interactions based on communication-related metadata or interaction content.</span></span> <span data-ttu-id="fb95a-174">Ниже приведены распространенные примеры.</span><span class="sxs-lookup"><span data-stu-id="fb95a-174">Common examples include:</span></span></p>
<ul>
<li><p><span data-ttu-id="fb95a-175"><strong>Метаданные</strong> - Участники, время, направление, набранный номер, номер источника, пользовательские бизнес-данные</span><span class="sxs-lookup"><span data-stu-id="fb95a-175"><strong>Metadata</strong> - Participants, time, direction, dialed number, origin number, Custom business data</span></span></p></li>
<li><p><span data-ttu-id="fb95a-176"><strong>Содержимое</strong> — транскрипция, тональность, фонетическая информация, взаимосвязанные взаимодействия</span><span class="sxs-lookup"><span data-stu-id="fb95a-176"><strong>Content</strong> – Transcription, sentiment, phonetics, related interactions</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="fb95a-177">Анализ и взаимодействие с собранными связями, в том числе возможность отслеживать взаимодействия по мере их сбора.</span><span class="sxs-lookup"><span data-stu-id="fb95a-177">Analyze and interact with collected communications, including the ability to monitor interactions as they are being collected.</span></span></p></li>
<li><p><span data-ttu-id="fb95a-178">Обеспечьте безопасность собранных сообщений и запретите все этапы.</span><span class="sxs-lookup"><span data-stu-id="fb95a-178">Ensure security of collected communications and prevent tampering at all stages.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a><span data-ttu-id="fb95a-179">Общие сведения об архитектуре решения</span><span class="sxs-lookup"><span data-stu-id="fb95a-179">Solution architecture overview</span></span>

<span data-ttu-id="fb95a-180">Решения для записи соответствия требованиям объединены с группами, как показано на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="fb95a-180">Compliance recording solutions are integrated with Teams as shown in the following diagram:</span></span>

<span data-ttu-id="fb95a-181">![Снимок экрана: параметр "настраиваемое приложение группы"](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "Изображения показывают поток при отправке и получении собрания или звонка команды.")</span><span class="sxs-lookup"><span data-stu-id="fb95a-181">![Screenshot showing the team custom app setting](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "The images shows the flow when a Teams meeting or call is sent and received.")</span></span>

## <a name="recorder"></a><span data-ttu-id="fb95a-182">Recorder</span><span class="sxs-lookup"><span data-stu-id="fb95a-182">Recorder</span></span>

<span data-ttu-id="fb95a-183">Основным компонентом решения для записи соответствия требованиям является средство записи.</span><span class="sxs-lookup"><span data-stu-id="fb95a-183">The core component of the compliance recording solution is the recorder.</span></span>
<span data-ttu-id="fb95a-184">Средства записи создаются как масштабируемые службы на основе Azure (ботов), которые [<span class="underline">используют платформу связи Майкрософт</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) и регистрируются в качестве приложений в Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="fb95a-184">Recorders are built as scalable Azure-based services (bots) that [<span class="underline">leverage Microsoft’s communications platform</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) and register as applications with Microsoft Graph.</span></span> <span data-ttu-id="fb95a-185">Средство записи обеспечивает непосредственное взаимодействие с [<span class="underline">API платформой связи</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) и собраний, а также предоставляет конечную точку для приема мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="fb95a-185">The recorder provides the direct interaction with the Teams calls and meetings [<span class="underline">communications platform APIs</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) and provides the endpoint for media ingestion.</span></span>

<span data-ttu-id="fb95a-186">[<span class="underline">Будет доступно пример приложения для записи соответствия требованиям</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) , в котором показано, как настроить робот, создать экземпляр приложения и назначить политики соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="fb95a-186">A [<span class="underline">sample compliance recorder application is available</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) that shows how to configure the bot, create the app instance and assign the compliance policies.</span></span> <span data-ttu-id="fb95a-187">В образце также приведены примеры использования API для записи конкретных взаимодействий, например обработки маршрутизации [<span class="underline">входящих звонков</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) , [<span class="underline">изменения состояния записи</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)и [<span class="underline">удаления пользователя, который записывается</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span><span class="sxs-lookup"><span data-stu-id="fb95a-187">The sample also has examples on API usage for recording specific interactions such as handling [<span class="underline">incoming call</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) routing, [<span class="underline">changing recording states</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138), and [<span class="underline">removing the user who is being recorded</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span></span>
<span data-ttu-id="fb95a-188">Документацию по графике для конкретных API можно найти здесь для [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) и [<span class="underline">incomingContext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span><span class="sxs-lookup"><span data-stu-id="fb95a-188">Graph documentation on the specific APIs can be found here for [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) and [<span class="underline">incomingContext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span></span>

<span data-ttu-id="fb95a-189">Точная реализация службы записи зависит от партнера, но должна быть разработана для поддержки нескольких средств записи в целях обеспечения высокой доступности и географического распространения развертывания для сокращения задержки от команд до средства записи.</span><span class="sxs-lookup"><span data-stu-id="fb95a-189">The exact implementation of the recorder service will vary by partner but must be designed to support multiple recorders in order to achieve high availability and geographical distribution of deployment to reduce latency from Teams to the recorder.</span></span> <span data-ttu-id="fb95a-190">Кроме того, ожидается, что сами средства записи должны быть спроектированы с учетом устойчивости и избыточности.</span><span class="sxs-lookup"><span data-stu-id="fb95a-190">In addition, it is expected that Recorders themselves be designed with resiliency and redundancy in mind.</span></span>

<span data-ttu-id="fb95a-191">Перед отправкой решения о том, что все требования интеграции с записью соответствия требованиям, партнеры должны проверить минимальную требуемую версию API Microsoft Graph для обмена данными и пакеты SDK для Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fb95a-191">Partners must confirm the minimum required release version of the Microsoft Graph communications APIs and SDKs with Microsoft before submitting their solution for certification to ensure that all requirements of compliance recording integration are supported.</span></span>

<span data-ttu-id="fb95a-192">Существует два конкретных требования, которые являются фундаментальными для сценария записи соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="fb95a-192">Two specific requirements that are fundamental for compliance recording scenario are:</span></span>

- <span data-ttu-id="fb95a-193">На самом и в Azure должны быть развернуты роботы для записи</span><span class="sxs-lookup"><span data-stu-id="fb95a-193">Recorder bot must be deployed in Azure</span></span>

- <span data-ttu-id="fb95a-194">На виртуальной машине Windows в Azure должен выполняться робот средства записи.</span><span class="sxs-lookup"><span data-stu-id="fb95a-194">Recorder bot must run on a Windows VM in Azure</span></span>

<span data-ttu-id="fb95a-195">Требования Azure и VM для Windows применимы только к компоненту Bot для Teams, а это означает, что партнер может реализовать оставшуюся платформу, если она подходит для обеспечения соблюдения требований к производительности и функциональным требованиям для записи соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="fb95a-195">The Azure and Windows VM requirements only apply to the Teams Bot component, which means that a partner may implement the rest of the platform of their choice provided they can meet the relevant performance and functional requirements for compliance recording.</span></span>

## <a name="compliance-recording-policy-assignment-and-provisioning"></a><span data-ttu-id="fb95a-196">Назначение и подготовка политики записи соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="fb95a-196">Compliance recording policy assignment and provisioning</span></span>

<span data-ttu-id="fb95a-197">ИТ администраторы могут определить, какие пользователи будут записаны, а какие будут использоваться для каждого пользователя, создавая и назначая политики записи соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="fb95a-197">IT Administrators can determine which users are to be recorded and which recorder will be used for each user, by creating and assigning compliance recording policies.</span></span> <span data-ttu-id="fb95a-198">Средства записи автоматически приглашаются в беседы на основе конфигурации этих политик, когда происходит взаимодействие с связью.</span><span class="sxs-lookup"><span data-stu-id="fb95a-198">Recorders are automatically invited to participate in conversations based on the configuration of these policies when a communication interaction takes place.</span></span> <span data-ttu-id="fb95a-199">Политики записи соответствия управляются с помощью [<span class="underline">Microsoft PowerShell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) и могут применяться для каждой организации на уровне клиента, пользователя и группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="fb95a-199">Compliance recording policies are managed using [<span class="underline">Microsoft Powershell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) and can be applied at the tenant, per-user, and security group level for each organization.</span></span> <span data-ttu-id="fb95a-200">Дополнительную информацию можно найти в документах Microsoft для [<span class="underline">политик собраний</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams), [<span class="underline">политиках звонков</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy) и  [<span class="underline">групповых политик</span>](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group).</span><span class="sxs-lookup"><span data-stu-id="fb95a-200">You can find more information on Microsoft Docs for [<span class="underline">Meeting policies</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams), [<span class="underline">calling policies</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy) and  [<span class="underline">group policies</span>](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group).</span></span>

1. <span data-ttu-id="fb95a-201">Создайте экземпляр приложения в клиенте.</span><span class="sxs-lookup"><span data-stu-id="fb95a-201">Create an application instance in your tenant.</span></span>

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

2. <span data-ttu-id="fb95a-202">Создание политики записи соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="fb95a-202">Create a Compliance Recording policy.</span></span>

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

   [<span data-ttu-id="fb95a-203"><span class="underline">Set-CsTeamsComplianceRecordingPolicy</span></span><span class="sxs-lookup"><span data-stu-id="fb95a-203"><span class="underline">Set-CsTeamsComplianceRecordingPolicy</span></span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. <span data-ttu-id="fb95a-204">Назначение пользователю политики записи соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="fb95a-204">Assign the Compliance Recording policy to a user.</span></span>

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   [<span data-ttu-id="fb95a-205"><span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span></span><span class="sxs-lookup"><span data-stu-id="fb95a-205"><span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span></span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a><span data-ttu-id="fb95a-206">Взаимодействие с пользователем</span><span class="sxs-lookup"><span data-stu-id="fb95a-206">User experiences</span></span>

<span data-ttu-id="fb95a-207">Поддержка уведомлений включена с помощью клиента Teams.</span><span class="sxs-lookup"><span data-stu-id="fb95a-207">Support for notifications is enabled using the Teams client experiences.</span></span> <span data-ttu-id="fb95a-208">Этот интерфейс может быть визуальным или звуковым.</span><span class="sxs-lookup"><span data-stu-id="fb95a-208">The experiences can be either visual or audio.</span></span>

<span data-ttu-id="fb95a-209">**Клиенты Teams-наглядное уведомление**</span><span class="sxs-lookup"><span data-stu-id="fb95a-209">**Teams clients - visual notice**</span></span>
- <span data-ttu-id="fb95a-210">Классическое и Интернет-</span><span class="sxs-lookup"><span data-stu-id="fb95a-210">Desktop/web</span></span>
- <span data-ttu-id="fb95a-211">Мобильный (iOS/Android)</span><span class="sxs-lookup"><span data-stu-id="fb95a-211">Mobile (iOS/Android)</span></span>
- <span data-ttu-id="fb95a-212">Телефоны Teams</span><span class="sxs-lookup"><span data-stu-id="fb95a-212">Teams phones</span></span>
- <span data-ttu-id="fb95a-213">Комнаты команд</span><span class="sxs-lookup"><span data-stu-id="fb95a-213">Teams rooms</span></span>

<span data-ttu-id="fb95a-214">**Другие конечные точки — уведомление о звуке**</span><span class="sxs-lookup"><span data-stu-id="fb95a-214">**Other endpoints - audio notice**</span></span>
- <span data-ttu-id="fb95a-215">Телефоны SIP</span><span class="sxs-lookup"><span data-stu-id="fb95a-215">SIP phones</span></span>
- <span data-ttu-id="fb95a-216">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="fb95a-216">Skype for Business</span></span>
- <span data-ttu-id="fb95a-217">Аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="fb95a-217">Audio conferencing</span></span>
- <span data-ttu-id="fb95a-218">КОММУТИРУЕМые звонки</span><span class="sxs-lookup"><span data-stu-id="fb95a-218">PSTN callers</span></span>

## <a name="compliance-recording-for-teams-certification-programs"></a><span data-ttu-id="fb95a-219">Запись соответствия требованиям для программ сертификации Teams</span><span class="sxs-lookup"><span data-stu-id="fb95a-219">Compliance recording for Teams certification programs</span></span>

<span data-ttu-id="fb95a-220">Помимо публикации общедоступных API-интерфейсов, позволяющих партнерам разрабатывать и интегрировать решения CCaaS с помощью Teams, мы разработали запись соответствия требованиям для программы сертификации Microsoft Teams, чтобы предоставить клиентам гарантию о том, что решение для каждого участника было проверено и проверено на предмет качества, совместимости и надежности, которые они ожидают от решений Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fb95a-220">In addition to publishing publicly-available APIs allowing partners to develop and integrate CCaaS solutions with Teams, we have developed the compliance recording for Microsoft Teams certification program to provide customers with the assurance that each participating partner’s solution has been tested and verified to provide the quality, compatibility and reliability they expect from Microsoft solutions.</span></span>  

<span data-ttu-id="fb95a-221">Следующие партнеры находятся в процессе сертификации своих решений для Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fb95a-221">The following partners are in the process of certifying their solution for Microsoft Teams.</span></span>

|<span data-ttu-id="fb95a-222">Сотрудничать</span><span class="sxs-lookup"><span data-stu-id="fb95a-222">Partner</span></span>|<span data-ttu-id="fb95a-223">Веб-сайт решения</span><span class="sxs-lookup"><span data-stu-id="fb95a-223">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="fb95a-224">Технологии ASC</span><span class="sxs-lookup"><span data-stu-id="fb95a-224">ASC Technologies</span></span> |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|<span data-ttu-id="fb95a-225">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="fb95a-225">AudioCodes</span></span> |[https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording) |
|<span data-ttu-id="fb95a-226">CallCabinet</span><span class="sxs-lookup"><span data-stu-id="fb95a-226">CallCabinet</span></span> |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|<span data-ttu-id="fb95a-227">Dubber</span><span class="sxs-lookup"><span data-stu-id="fb95a-227">Dubber</span></span> |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|<span data-ttu-id="fb95a-228">Технологии Landis</span><span class="sxs-lookup"><span data-stu-id="fb95a-228">Landis Technologies</span></span> |[https://landistechnologies.com/](https://landistechnologies.com/) |
|<span data-ttu-id="fb95a-229">Luware</span><span class="sxs-lookup"><span data-stu-id="fb95a-229">Luware</span></span> |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|<span data-ttu-id="fb95a-230">ПРИВЛЕКАТЕЛЬН</span><span class="sxs-lookup"><span data-stu-id="fb95a-230">NICE</span></span> |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|<span data-ttu-id="fb95a-231">Numonix</span><span class="sxs-lookup"><span data-stu-id="fb95a-231">Numonix</span></span> |[https://numonix.cloud](https://numonix.cloud)    |
|<span data-ttu-id="fb95a-232">Для новаторства (дуб)</span><span class="sxs-lookup"><span data-stu-id="fb95a-232">Oak Innovation</span></span> |[https://www.oakinnovate.com/call-recording](https://www.oakinnovate.com/call-recording) |
|<span data-ttu-id="fb95a-233">Красная рамка</span><span class="sxs-lookup"><span data-stu-id="fb95a-233">Red Box</span></span> |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|<span data-ttu-id="fb95a-234">Verint</span><span class="sxs-lookup"><span data-stu-id="fb95a-234">Verint</span></span> |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

<span data-ttu-id="fb95a-235">Этот список будет обновляться по мере того, как дополнительные участники будут присоединяться к критерию сертификации и отвечать на них.</span><span class="sxs-lookup"><span data-stu-id="fb95a-235">This list will be updated as more partners join and meet the certification criteria.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fb95a-236">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="fb95a-236">Next steps</span></span>

<span data-ttu-id="fb95a-237">Если вы хотите присоединиться к программе сертификации, пожалуйста,  <a href= "mailto:Teamscategorypartner@microsoft.com">поTeamscategorypartner@microsoft.com</a>по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="fb95a-237">If you are a vendor seeking to join the certification program, please mail  <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>.</span></span>
