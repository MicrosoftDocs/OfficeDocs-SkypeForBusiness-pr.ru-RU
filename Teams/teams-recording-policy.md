---
title: Общие сведения о записи на основе политики в Teams для собраний по звонкам &
author: microsoftheidi
ms.author: heidip
manager: serdars
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
ms.openlocfilehash: cc09323e7f0a25f0f7c7083307776ad1a08bf4fb
ms.sourcegitcommit: e0ed3b6478918c4737648e6c27eb01de0b622b0e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "44294054"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a><span data-ttu-id="fb6ae-103">Общие сведения о записи на основе политики для групп звонков & собраний</span><span class="sxs-lookup"><span data-stu-id="fb6ae-103">Introduction to Teams policy-based recording for callings & meetings</span></span>

<span data-ttu-id="fb6ae-104">Запись на основе политики позволяет организациям, которые применяют Microsoft Teams для звонков и собраний в соответствии с использованием политики администрирования, когда звонки и собраний по сети должны автоматически записываться и записываться для последующей обработки и хранения в соответствии с требованиями, предусмотренными корпоративными или нормативными политиками.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-104">Policy-based recording enables organizations that adopt Microsoft Teams for calling and meetings to stipulate, using an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span>

<span data-ttu-id="fb6ae-105">Группы были улучшены для поддержки интеграции сторонних решений для записи, в том числе функций платформы, взаимодействия с пользователем и административных интерфейсов, которые необходимы для создания комплексного решения для настройки, управления, записи, хранения и анализа коммуникаций в Teams.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-105">Teams has been enhanced to support integration of third-party recording solutions, including the platform functionality, user experiences, and administrative interfaces needed to provide an end-to-end solution for configuring, managing, recording, storing, and analyzing Teams communications.</span></span> <span data-ttu-id="fb6ae-106">Сюда входят API платформы связи и события для записи, которые предоставляют следующие возможности.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-106">This includes communications platform APIs and events for recording, which provides:</span></span>

- <span data-ttu-id="fb6ae-107">Высококачественная запись мультимедиа на разных устройствах и все поддерживаемые конечные точки для звука, видео, демонстрации экрана и чата.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-107">Seamless, high-quality media capture across devices and all   supported endpoints for audio, video, screen share, and chat.</span></span>

- <span data-ttu-id="fb6ae-108">Поддержка захвата взаимодействия между пользователями Teams и поддерживаемыми конечными точками (Teams, Teams Mobile, Skype для бизнеса, КТСОП)</span><span class="sxs-lookup"><span data-stu-id="fb6ae-108">Support for interaction capture between Teams users and supported   calling endpoints (Teams, Teams Mobile, Skype for Business, PSTN)</span></span>

- <span data-ttu-id="fb6ae-109">Новые политики администрирования для записи соответствия требованиям, в том числе интеграция с существующими средствами администрирования, а также средства и политики для собраний.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-109">New administrative policies for compliance recording, including   integration with existing Teams administrative calling and   meeting tools and policies</span></span>

- <span data-ttu-id="fb6ae-110">Разрешено для пользователей Teams с отдельной лицензией</span><span class="sxs-lookup"><span data-stu-id="fb6ae-110">Enabled for Teams users with a separate license</span></span>

<span data-ttu-id="fb6ae-111">Возможности интеграции с решением для записи соответствия требованиям также проверяются на Ignite 2019 в [<span class="underline">записи соответствия требованиям и сеансе Microsoft Teams</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions).</span><span class="sxs-lookup"><span data-stu-id="fb6ae-111">The compliance recording solution integration capabilities were also reviewed at Ignite 2019 in the [<span class="underline">Compliance Recording and Microsoft Teams session</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions).</span></span>

## <a name="teams-interaction-recording-overview"></a><span data-ttu-id="fb6ae-112">Общие сведения о записи взаимодействия в Teams</span><span class="sxs-lookup"><span data-stu-id="fb6ae-112">Teams interaction recording overview</span></span>

<span data-ttu-id="fb6ae-113">Сценарии использования для записи взаимодействия можно разделить на четыре основных категории функциональных возможностей записи: удобные, функциональные, организационные и законных перехваты, как показано на рисунке.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-113">Interaction recording use cases can effectively be separated into four primary categories of recording functionality – Convenience, Functional, Organizational, and Lawful Intercept, as shown in the image:</span></span>

<span data-ttu-id="fb6ae-114">![Снимок экрана, на котором показано, что такое запись взаимодействия и почему.](media/recording-taxonomy.png "На изображении отображаются категории записи.")</span><span class="sxs-lookup"><span data-stu-id="fb6ae-114">![Screenshot showing the interaction recording what and why.](media/recording-taxonomy.png "The image shows the recording categories.")</span></span>

<span data-ttu-id="fb6ae-115">Каждая из категорий имеет разные требования для начала записи, что записывается, где хранятся записи, кто получает уведомление, кто управляет доступом и как выполняется обработка хранения.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-115">Each of the categories entails different requirements for how recordings are initiated, what is recorded, where recordings are stored, who is notified, who controls access, and how retention is handled.</span></span>

|                        | <span data-ttu-id="fb6ae-116">Благодаря</span><span class="sxs-lookup"><span data-stu-id="fb6ae-116">Convenience</span></span>        | <span data-ttu-id="fb6ae-117">Функция</span><span class="sxs-lookup"><span data-stu-id="fb6ae-117">Functional</span></span>         | <span data-ttu-id="fb6ae-118">Org — общие</span><span class="sxs-lookup"><span data-stu-id="fb6ae-118">Org - General</span></span>      | <span data-ttu-id="fb6ae-119">Поднадзорные Организации</span><span class="sxs-lookup"><span data-stu-id="fb6ae-119">Org - Regulated</span></span> | <span data-ttu-id="fb6ae-120">Законных перехват</span><span class="sxs-lookup"><span data-stu-id="fb6ae-120">Lawful Intercept</span></span>   |
| ---------------------- | ------------------ | ------------------ | ------------------ | --------------- | ------------------ |
| <span data-ttu-id="fb6ae-121">Владельцы</span><span class="sxs-lookup"><span data-stu-id="fb6ae-121">Initiator</span></span>              | <span data-ttu-id="fb6ae-122">Пользователь</span><span class="sxs-lookup"><span data-stu-id="fb6ae-122">User</span></span>               | <span data-ttu-id="fb6ae-123">Приложение/решение</span><span class="sxs-lookup"><span data-stu-id="fb6ae-123">App/Solution</span></span>       | <span data-ttu-id="fb6ae-124">Администратор (система)</span><span class="sxs-lookup"><span data-stu-id="fb6ae-124">Admin (system)</span></span>     | <span data-ttu-id="fb6ae-125">Администратор (система)</span><span class="sxs-lookup"><span data-stu-id="fb6ae-125">Admin (system)</span></span>  | <span data-ttu-id="fb6ae-126">LEA</span><span class="sxs-lookup"><span data-stu-id="fb6ae-126">LEA</span></span>                |
| <span data-ttu-id="fb6ae-127">Целевой объект</span><span class="sxs-lookup"><span data-stu-id="fb6ae-127">Target</span></span>                 | <span data-ttu-id="fb6ae-128">Для каждого звонка или собрания</span><span class="sxs-lookup"><span data-stu-id="fb6ae-128">Per-call / meeting</span></span> | <span data-ttu-id="fb6ae-129">Для каждого звонка или собрания</span><span class="sxs-lookup"><span data-stu-id="fb6ae-129">Per-call / meeting</span></span> | <span data-ttu-id="fb6ae-130">Для каждого звонка или собрания</span><span class="sxs-lookup"><span data-stu-id="fb6ae-130">Per-call / meeting</span></span> | <span data-ttu-id="fb6ae-131">Для каждого пользователя</span><span class="sxs-lookup"><span data-stu-id="fb6ae-131">Per-user</span></span>        | <span data-ttu-id="fb6ae-132">На конечную точку/выполнено</span><span class="sxs-lookup"><span data-stu-id="fb6ae-132">Per-endpoint / DID</span></span> |
| <span data-ttu-id="fb6ae-133">Владелец хранилища</span><span class="sxs-lookup"><span data-stu-id="fb6ae-133">Storage owner</span></span>          | <span data-ttu-id="fb6ae-134">Пользователь</span><span class="sxs-lookup"><span data-stu-id="fb6ae-134">User</span></span>               | <span data-ttu-id="fb6ae-135">·</span><span class="sxs-lookup"><span data-stu-id="fb6ae-135">App</span></span>                | <span data-ttu-id="fb6ae-136">RAS</span><span class="sxs-lookup"><span data-stu-id="fb6ae-136">Admin</span></span>              | <span data-ttu-id="fb6ae-137">О</span><span class="sxs-lookup"><span data-stu-id="fb6ae-137">Compliance</span></span>      | <span data-ttu-id="fb6ae-138">LEA</span><span class="sxs-lookup"><span data-stu-id="fb6ae-138">LEA</span></span>                |
| <span data-ttu-id="fb6ae-139">Требуется уведомление?</span><span class="sxs-lookup"><span data-stu-id="fb6ae-139">Notification required?</span></span> | <span data-ttu-id="fb6ae-140">Да </span><span class="sxs-lookup"><span data-stu-id="fb6ae-140">Yes</span></span>                | <span data-ttu-id="fb6ae-141">Да </span><span class="sxs-lookup"><span data-stu-id="fb6ae-141">Yes</span></span>                | <span data-ttu-id="fb6ae-142">Да </span><span class="sxs-lookup"><span data-stu-id="fb6ae-142">Yes</span></span>                | <span data-ttu-id="fb6ae-143">Да</span><span class="sxs-lookup"><span data-stu-id="fb6ae-143">Yes</span></span>             | <span data-ttu-id="fb6ae-144">Нет</span><span class="sxs-lookup"><span data-stu-id="fb6ae-144">No</span></span>                 |
| <span data-ttu-id="fb6ae-145">Владелец Access</span><span class="sxs-lookup"><span data-stu-id="fb6ae-145">Access Owner</span></span>           | <span data-ttu-id="fb6ae-146">Пользователь</span><span class="sxs-lookup"><span data-stu-id="fb6ae-146">User</span></span>               | <span data-ttu-id="fb6ae-147">·</span><span class="sxs-lookup"><span data-stu-id="fb6ae-147">App</span></span>                | <span data-ttu-id="fb6ae-148">RAS</span><span class="sxs-lookup"><span data-stu-id="fb6ae-148">Admin</span></span>              | <span data-ttu-id="fb6ae-149">О</span><span class="sxs-lookup"><span data-stu-id="fb6ae-149">Compliance</span></span>      | <span data-ttu-id="fb6ae-150">LEA</span><span class="sxs-lookup"><span data-stu-id="fb6ae-150">LEA</span></span>                |
| <span data-ttu-id="fb6ae-151">Политика хранения?</span><span class="sxs-lookup"><span data-stu-id="fb6ae-151">Retention Policy?</span></span>      | <span data-ttu-id="fb6ae-152">Необязательно </span><span class="sxs-lookup"><span data-stu-id="fb6ae-152">Optional</span></span>           | <span data-ttu-id="fb6ae-153">Да </span><span class="sxs-lookup"><span data-stu-id="fb6ae-153">Yes</span></span>                | <span data-ttu-id="fb6ae-154">Да </span><span class="sxs-lookup"><span data-stu-id="fb6ae-154">Yes</span></span>                | <span data-ttu-id="fb6ae-155">Да </span><span class="sxs-lookup"><span data-stu-id="fb6ae-155">Yes</span></span>             | <span data-ttu-id="fb6ae-156">Да</span><span class="sxs-lookup"><span data-stu-id="fb6ae-156">Yes</span></span>                |

<span data-ttu-id="fb6ae-157">Teams предоставляет различные возможности для [<span class="underline">удобной</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) и функциональной записи для собраний и событий Live Events.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-157">Teams provides various capabilities for [<span class="underline">convenient</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) and functional recording for meetings and live events.</span></span> <span data-ttu-id="fb6ae-158">Запись в Организации означает, что Организации, которые разрабатывают команды для звонков и собраний, в соответствии с политикой администрирования, при выполнении звонков и собраний по сети должны автоматически записываться и записываться для последующей обработки и хранения в соответствии с требованиями компании или законодательной политики.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-158">Organizational recording means enabling organizations adopting Teams for calling and meetings to stipulate, by way of an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span> <span data-ttu-id="fb6ae-159">Пользователи в этой политике будут знать о том, что ваши цифровые взаимодействия с группами записываются, но они не смогут отключить запись и не получат доступ к записи после завершения взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-159">Users under this policy will be aware that their digital interactions with Teams are being recorded but will not be able to disable the recording and will not have access to the recording once the interaction is complete.</span></span> <span data-ttu-id="fb6ae-160">Запись становится частью организационного архива, доступного для соответствия и юридического персонала для обнаружения электронных данных, юридических удержаний и других целей хранения в корпоративной компании.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-160">The recording becomes part of the organizational archive available to compliance and legal personnel for eDiscovery, legal hold, and other corporate retention uses.</span></span>

## <a name="example-user-needs"></a><span data-ttu-id="fb6ae-161">Примеры потребностей пользователей</span><span class="sxs-lookup"><span data-stu-id="fb6ae-161">Example user needs</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="fb6ae-162"><strong>Дайте</strong></span><span class="sxs-lookup"><span data-stu-id="fb6ae-162"><strong>Persona</strong></span></span></th>
<th><span data-ttu-id="fb6ae-163"><strong>Необходимо</strong></span><span class="sxs-lookup"><span data-stu-id="fb6ae-163"><strong>Needs</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="fb6ae-164">Записанные пользователи</span><span class="sxs-lookup"><span data-stu-id="fb6ae-164">Recorded users</span></span></td>
<td><ul>
<li><p><span data-ttu-id="fb6ae-165">Получать уведомления о ходе записи.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-165">Be notified when recording is in progress.</span></span></p></li>
<li><p><span data-ttu-id="fb6ae-166">Будьте в курсе событий, вызывающих ошибки политики и (или) записи, которые приводят к изменениям в поведении вызова.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-166">Be informed when policy and/or recorder error is causing changes in calling behavior.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="fb6ae-167">Администратор связи</span><span class="sxs-lookup"><span data-stu-id="fb6ae-167">Communications admin</span></span></td>
<td><ul>
<li><p><span data-ttu-id="fb6ae-168">Узнайте, почему и как применять политики записи к пользователям и конечным точкам Teams.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-168">Understand why and how to apply / enforce recording policies to Teams users / endpoints.</span></span></p></li>
<li><p><span data-ttu-id="fb6ae-169">Настройте и настройте политики записи в Teams для Организации.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-169">Configure and maintain Teams recording policies for the organization.</span></span></p></li>
<li><p><span data-ttu-id="fb6ae-170">Отслеживание и устранение проблем, связанных с записью, в рамках звонков и собраний Teams.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-170">Monitor and troubleshoot recording-related issues with Teams calls and meetings.</span></span></p></li>
<li><p><span data-ttu-id="fb6ae-171">Поддержка внутреннего сотрудника по обеспечению соответствия требованиям в отношении использования, качества и надежности.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-171">Support internal compliance officer with operational analytics on usage, quality, and reliability.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="fb6ae-172">Сотрудник отдела соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="fb6ae-172">Compliance officer</span></span></td>
<td><ul>
<li><p><span data-ttu-id="fb6ae-173">Соберите все коммуникации в Teams так, чтобы они соответствовали обязательствам по обеспечению соответствия требованиям в соответствующих региональных регионах.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-173">Collect all Teams communications in the manner required to meet compliance obligations in appropriate regional boundaries.</span></span></p></li>
<li><p><span data-ttu-id="fb6ae-174">Поиск взаимодействий на основе метаданных или контента взаимодействия, связанных с связью.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-174">Search for interactions based on communication-related metadata or interaction content.</span></span> <span data-ttu-id="fb6ae-175">Ниже приведены распространенные примеры.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-175">Common examples include:</span></span></p>
<ul>
<li><p><span data-ttu-id="fb6ae-176"><strong>Метаданные</strong> - Участники, время, направление, набранный номер, номер источника, пользовательские бизнес-данные</span><span class="sxs-lookup"><span data-stu-id="fb6ae-176"><strong>Metadata</strong> - Participants, time, direction, dialed number, origin number, Custom business data</span></span></p></li>
<li><p><span data-ttu-id="fb6ae-177"><strong>Содержимое</strong> — транскрипция, тональность, фонетическая информация, взаимосвязанные взаимодействия</span><span class="sxs-lookup"><span data-stu-id="fb6ae-177"><strong>Content</strong> – Transcription, sentiment, phonetics, related interactions</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="fb6ae-178">Анализ и взаимодействие с собранными связями, в том числе возможность отслеживать взаимодействия по мере их сбора.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-178">Analyze and interact with collected communications, including the ability to monitor interactions as they are being collected.</span></span></p></li>
<li><p><span data-ttu-id="fb6ae-179">Обеспечьте безопасность собранных сообщений и запретите все этапы.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-179">Ensure security of collected communications and prevent tampering at all stages.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a><span data-ttu-id="fb6ae-180">Общие сведения об архитектуре решения</span><span class="sxs-lookup"><span data-stu-id="fb6ae-180">Solution architecture overview</span></span>

<span data-ttu-id="fb6ae-181">Решения для записи соответствия требованиям объединены с группами, как показано на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-181">Compliance recording solutions are integrated with Teams as shown in the following diagram:</span></span>

<span data-ttu-id="fb6ae-182">![Снимок экрана: параметр "настраиваемое приложение группы"](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "Изображения показывают поток при отправке и получении собрания или звонка команды.")</span><span class="sxs-lookup"><span data-stu-id="fb6ae-182">![Screenshot showing the team custom app setting](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "The images shows the flow when a Teams meeting or call is sent and received.")</span></span>

## <a name="recorder"></a><span data-ttu-id="fb6ae-183">Recorder</span><span class="sxs-lookup"><span data-stu-id="fb6ae-183">Recorder</span></span>

<span data-ttu-id="fb6ae-184">Основным компонентом решения для записи соответствия требованиям является средство записи.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-184">The core component of the compliance recording solution is the recorder.</span></span>
<span data-ttu-id="fb6ae-185">Средства записи создаются как масштабируемые службы на основе Azure (ботов), которые [<span class="underline">используют платформу связи Майкрософт</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) и регистрируются в качестве приложений в Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-185">Recorders are built as scalable Azure-based services (bots) that [<span class="underline">leverage Microsoft’s communications platform</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) and register as applications with Microsoft Graph.</span></span> <span data-ttu-id="fb6ae-186">Средство записи обеспечивает непосредственное взаимодействие с [<span class="underline">API платформой связи</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) и собраний, а также предоставляет конечную точку для приема мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-186">The recorder provides the direct interaction with the Teams calls and meetings [<span class="underline">communications platform APIs</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) and provides the endpoint for media ingestion.</span></span>

<span data-ttu-id="fb6ae-187">[<span class="underline">Будет доступно пример приложения для записи соответствия требованиям</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) , в котором показано, как настроить робот, создать экземпляр приложения и назначить политики соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-187">A [<span class="underline">sample compliance recorder application is available</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) that shows how to configure the bot, create the app instance and assign the compliance policies.</span></span> <span data-ttu-id="fb6ae-188">В образце также приведены примеры использования API для записи конкретных взаимодействий, например обработки маршрутизации [<span class="underline">входящих звонков</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244)   , [<span class="underline">изменения состояния записи</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)и [<span class="underline">удаления пользователя, который записывается</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span><span class="sxs-lookup"><span data-stu-id="fb6ae-188">The sample also has examples on API usage for recording specific interactions such as handling [<span class="underline">incoming call</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) routing, [<span class="underline">changing recording states</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138), and [<span class="underline">removing the user who is being recorded</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span></span>
<span data-ttu-id="fb6ae-189">Документацию по графике для конкретных API можно найти здесь для [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) и [<span class="underline">incomingContext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span><span class="sxs-lookup"><span data-stu-id="fb6ae-189">Graph documentation on the specific APIs can be found here for [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) and [<span class="underline">incomingContext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span></span>

<span data-ttu-id="fb6ae-190">Точная реализация службы записи зависит от партнера, но должна быть разработана для поддержки нескольких средств записи в целях обеспечения высокой доступности и географического распространения развертывания для сокращения задержки от команд до средства записи.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-190">The exact implementation of the recorder service will vary by partner but must be designed to support multiple recorders in order to achieve high availability and geographical distribution of deployment to reduce latency from Teams to the recorder.</span></span> <span data-ttu-id="fb6ae-191">Кроме того, ожидается, что сами средства записи должны быть спроектированы с учетом устойчивости и избыточности.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-191">In addition, it is expected that Recorders themselves be designed with resiliency and redundancy in mind.</span></span>

<span data-ttu-id="fb6ae-192">Перед отправкой решения о том, что все требования интеграции с записью соответствия требованиям, партнеры должны проверить минимальную требуемую версию API Microsoft Graph для обмена данными и пакеты SDK для Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-192">Partners must confirm the minimum required release version of the Microsoft Graph communications APIs and SDKs with Microsoft before submitting their solution for certification to ensure that all requirements of compliance recording integration are supported.</span></span>

<span data-ttu-id="fb6ae-193">Существует два конкретных требования, которые являются фундаментальными для сценария записи соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="fb6ae-193">Two specific requirements that are fundamental for compliance recording scenario are:</span></span>

- <span data-ttu-id="fb6ae-194">На самом и в Azure должны быть развернуты роботы для записи</span><span class="sxs-lookup"><span data-stu-id="fb6ae-194">Recorder bot must be deployed in Azure</span></span>

- <span data-ttu-id="fb6ae-195">На виртуальной машине Windows в Azure должен выполняться робот средства записи.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-195">Recorder bot must run on a Windows VM in Azure</span></span>

<span data-ttu-id="fb6ae-196">Требования Azure и VM для Windows применимы только к компоненту Bot для Teams, а это означает, что партнер может реализовать оставшуюся платформу, если она подходит для обеспечения соблюдения требований к производительности и функциональным требованиям для записи соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-196">The Azure and Windows VM requirements only apply to the Teams Bot component, which means that a partner may implement the rest of the platform of their choice provided they can meet the relevant performance and functional requirements for compliance recording.</span></span>

## <a name="compliance-recording-policy-assignment-and-provisioning"></a><span data-ttu-id="fb6ae-197">Назначение и подготовка политики записи соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="fb6ae-197">Compliance recording policy assignment and provisioning</span></span>

<span data-ttu-id="fb6ae-198">ИТ администраторы могут определить, какие пользователи будут записаны, а какие будут использоваться для каждого пользователя, создавая и назначая политики записи соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-198">IT Administrators can determine which users are to be recorded and which recorder will be used for each user, by creating and assigning compliance recording policies.</span></span> <span data-ttu-id="fb6ae-199">Средства записи автоматически приглашаются в беседы на основе конфигурации этих политик, когда происходит взаимодействие с связью.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-199">Recorders are automatically invited to participate in conversations based on the configuration of these policies when a communication interaction takes place.</span></span> <span data-ttu-id="fb6ae-200">Политики записи соответствия управляются с помощью [<span class="underline">Microsoft PowerShell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) и могут применяться на уровне клиента и каждого пользователя для каждой организации.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-200">Compliance recording policies are managed using [<span class="underline">Microsoft Powershell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) and can be applied at the tenant and per-user level for each organization.</span></span> <span data-ttu-id="fb6ae-201">Дополнительные сведения можно найти в документах Microsoft для [<span class="underline">политик собраний</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) и для [<span class="underline">политик звонков</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy).</span><span class="sxs-lookup"><span data-stu-id="fb6ae-201">You can find more information on Microsoft Docs for [<span class="underline">Meeting policies</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) and [<span class="underline">calling policies</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy).</span></span>

1. <span data-ttu-id="fb6ae-202">Создайте экземпляр приложения в клиенте.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-202">Create an application instance in your tenant.</span></span>

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

2. <span data-ttu-id="fb6ae-203">Создание политики записи соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-203">Create a Compliance Recording policy.</span></span>

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

[<span class="underline">https://docs.microsoft.com/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps</span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. <span data-ttu-id="fb6ae-204">Назначение пользователю политики записи соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-204">Assign the Compliance Recording policy to a user.</span></span>

```powershell
PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
```

[<span class="underline">https://docs.microsoft.com/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps</span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

```powershell
PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

UserPrincipalName              : testuser@contoso.onmicrosoft.com
TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
```

## <a name="user-experiences"></a><span data-ttu-id="fb6ae-205">Взаимодействие с пользователем</span><span class="sxs-lookup"><span data-stu-id="fb6ae-205">User experiences</span></span>

<span data-ttu-id="fb6ae-206">Поддержка уведомлений включена с помощью клиента Teams.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-206">Support for notifications is enabled using the Teams client experiences.</span></span> <span data-ttu-id="fb6ae-207">Этот интерфейс может быть визуальным или звуковым.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-207">The experiences can be either visual or audio.</span></span>

<span data-ttu-id="fb6ae-208">**Клиенты Teams-наглядное уведомление**</span><span class="sxs-lookup"><span data-stu-id="fb6ae-208">**Teams clients - visual notice**</span></span>
- <span data-ttu-id="fb6ae-209">Классическое и Интернет-</span><span class="sxs-lookup"><span data-stu-id="fb6ae-209">Desktop/web</span></span>
- <span data-ttu-id="fb6ae-210">Мобильный (iOS/Android)</span><span class="sxs-lookup"><span data-stu-id="fb6ae-210">Mobile (iOS/Android)</span></span>
- <span data-ttu-id="fb6ae-211">Телефоны Teams</span><span class="sxs-lookup"><span data-stu-id="fb6ae-211">Teams phones</span></span>
- <span data-ttu-id="fb6ae-212">Комнаты команд</span><span class="sxs-lookup"><span data-stu-id="fb6ae-212">Teams rooms</span></span>

<span data-ttu-id="fb6ae-213">**Другие конечные точки — уведомление о звуке**</span><span class="sxs-lookup"><span data-stu-id="fb6ae-213">**Other endpoints - audio notice**</span></span>
- <span data-ttu-id="fb6ae-214">Телефоны SIP</span><span class="sxs-lookup"><span data-stu-id="fb6ae-214">SIP phones</span></span>
- <span data-ttu-id="fb6ae-215">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="fb6ae-215">Skype for Business</span></span>
- <span data-ttu-id="fb6ae-216">Аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="fb6ae-216">Audio conferencing</span></span>
- <span data-ttu-id="fb6ae-217">КОММУТИРУЕМые звонки</span><span class="sxs-lookup"><span data-stu-id="fb6ae-217">PSTN callers</span></span>

## <a name="compliance-recording-for-teams-certification-programs"></a><span data-ttu-id="fb6ae-218">Запись соответствия требованиям для программ сертификации Teams</span><span class="sxs-lookup"><span data-stu-id="fb6ae-218">Compliance recording for Teams certification programs</span></span>

<span data-ttu-id="fb6ae-219">Помимо публикации общедоступных API-интерфейсов, позволяющих партнерам разрабатывать и интегрировать решения CCaaS с помощью Teams, мы разработали запись соответствия требованиям для программы сертификации Microsoft Teams, чтобы предоставить клиентам гарантию о том, что решение для каждого участника было проверено и проверено на предмет качества, совместимости и надежности, которые они ожидают от решений Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-219">In addition to publishing publicly-available APIs allowing partners to develop and integrate CCaaS solutions with Teams, we have developed the compliance recording for Microsoft Teams certification program to provide customers with the assurance that each participating partner’s solution has been tested and verified to provide the quality, compatibility and reliability they expect from Microsoft solutions.</span></span>  

<span data-ttu-id="fb6ae-220">Следующие партнеры находятся в процессе сертификации своих решений для Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-220">The following partners are in the process of certifying their solution for Microsoft Teams.</span></span>  

|<span data-ttu-id="fb6ae-221">Сотрудничать</span><span class="sxs-lookup"><span data-stu-id="fb6ae-221">Partner</span></span>|<span data-ttu-id="fb6ae-222">Веб-сайт решения</span><span class="sxs-lookup"><span data-stu-id="fb6ae-222">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="fb6ae-223">Технологии ASC</span><span class="sxs-lookup"><span data-stu-id="fb6ae-223">ASC Technologies</span></span> |[https://www.asc.de/english/ASC_Recording_Insights_for_Microsoft_Teams.html](https://www.asc.de/english/ASC_Recording_Insights_for_Microsoft_Teams.html) |
|<span data-ttu-id="fb6ae-224">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="fb6ae-224">AudioCodes</span></span> |[https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording) |
|<span data-ttu-id="fb6ae-225">CallCabinet</span><span class="sxs-lookup"><span data-stu-id="fb6ae-225">CallCabinet</span></span> |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|<span data-ttu-id="fb6ae-226">ПРИВЛЕКАТЕЛЬН</span><span class="sxs-lookup"><span data-stu-id="fb6ae-226">NICE</span></span> |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|<span data-ttu-id="fb6ae-227">Numonix</span><span class="sxs-lookup"><span data-stu-id="fb6ae-227">Numonix</span></span> |[https://numonix.cloud](https://numonix.cloud)    |
|<span data-ttu-id="fb6ae-228">Красная рамка</span><span class="sxs-lookup"><span data-stu-id="fb6ae-228">Red Box</span></span> |[https://hubs.ly/H0qtN7Q0](https://hubs.ly/H0qtN7Q0)  |
|<span data-ttu-id="fb6ae-229">Verint</span><span class="sxs-lookup"><span data-stu-id="fb6ae-229">Verint</span></span> |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

<span data-ttu-id="fb6ae-230">Этот список будет обновляться по мере того, как дополнительные участники будут присоединяться к критерию сертификации и отвечать на них.</span><span class="sxs-lookup"><span data-stu-id="fb6ae-230">This list will be updated as more partners join and meet the certification criteria.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fb6ae-231">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="fb6ae-231">Next steps</span></span>

<span data-ttu-id="fb6ae-232">Если вы хотите присоединиться к программе сертификации, пожалуйста, <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a> почты</span><span class="sxs-lookup"><span data-stu-id="fb6ae-232">If you are a vendor seeking to join the certification program, please mail  <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a></span></span>
