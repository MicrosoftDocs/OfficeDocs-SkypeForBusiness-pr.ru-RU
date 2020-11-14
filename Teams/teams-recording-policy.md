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
ms.openlocfilehash: 61fbce79fc528f4b69baed9c08a8dabc9d40ed4a
ms.sourcegitcommit: 76fc38fe1fbbd93bf2815c57e66fc479df34d929
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2020
ms.locfileid: "49002201"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a><span data-ttu-id="c1e57-103">Общие сведения о записи на основе политики для групп звонков & собраний</span><span class="sxs-lookup"><span data-stu-id="c1e57-103">Introduction to Teams policy-based recording for callings & meetings</span></span>

<span data-ttu-id="c1e57-104">Запись на основе политики позволяет организациям, которые применяют Microsoft Teams для звонков и собраний в соответствии с использованием политики администрирования, когда звонки и собраний по сети должны автоматически записываться и записываться для последующей обработки и хранения в соответствии с требованиями, предусмотренными корпоративными или нормативными политиками.</span><span class="sxs-lookup"><span data-stu-id="c1e57-104">Policy-based recording enables organizations that adopt Microsoft Teams for calling and meetings to stipulate, using an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span>

<span data-ttu-id="c1e57-105">Группы были улучшены для поддержки интеграции сторонних решений для записи, в том числе функций платформы, взаимодействия с пользователем и административных интерфейсов, которые необходимы для создания комплексного решения для настройки, управления, записи, хранения и анализа коммуникаций в Teams.</span><span class="sxs-lookup"><span data-stu-id="c1e57-105">Teams has been enhanced to support integration of third-party recording solutions, including the platform functionality, user experiences, and administrative interfaces needed to provide an end-to-end solution for configuring, managing, recording, storing, and analyzing Teams communications.</span></span> <span data-ttu-id="c1e57-106">Сюда входят API платформы связи и события для записи, которые предоставляют следующие возможности.</span><span class="sxs-lookup"><span data-stu-id="c1e57-106">This includes communications platform APIs and events for recording, which provides:</span></span>

- <span data-ttu-id="c1e57-107">Высококачественная запись мультимедиа на разных устройствах и все поддерживаемые конечные точки для звука, видео, демонстрации экрана и чата.</span><span class="sxs-lookup"><span data-stu-id="c1e57-107">Seamless, high-quality media capture across devices and all   supported endpoints for audio, video, screen share, and chat.</span></span>

- <span data-ttu-id="c1e57-108">Поддержка захвата взаимодействия между пользователями Teams и поддерживаемыми конечными точками (Teams, Teams Mobile, Skype для бизнеса, КТСОП)</span><span class="sxs-lookup"><span data-stu-id="c1e57-108">Support for interaction capture between Teams users and supported   calling endpoints (Teams, Teams Mobile, Skype for Business, PSTN)</span></span>

- <span data-ttu-id="c1e57-109">Новые политики администрирования для записи соответствия требованиям, в том числе интеграция с существующими средствами администрирования, а также средства и политики для собраний.</span><span class="sxs-lookup"><span data-stu-id="c1e57-109">New administrative policies for compliance recording, including   integration with existing Teams administrative calling and   meeting tools and policies</span></span>

<span data-ttu-id="c1e57-110">Запись соответствия требованиям может быть включена в Microsoft 365 a3/A5/E3/для бизнеса премиум и Office 365 a3/A5/E3/водопользователи.</span><span class="sxs-lookup"><span data-stu-id="c1e57-110">Compliance Recording can be enabled on Microsoft 365 A3/A5/E3/E5/Business Premium and Office 365 A3/A5/E3/E5 users.</span></span> 

<span data-ttu-id="c1e57-111">Возможности интеграции с решением для записи соответствия требованиям также проверяются на Ignite 2019 в [<span class="underline">записи соответствия требованиям и сеансе Microsoft Teams</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions).</span><span class="sxs-lookup"><span data-stu-id="c1e57-111">The compliance recording solution integration capabilities were also reviewed at Ignite 2019 in the [<span class="underline">Compliance Recording and Microsoft Teams session</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions).</span></span>

## <a name="teams-interaction-recording-overview"></a><span data-ttu-id="c1e57-112">Общие сведения о записи взаимодействия в Teams</span><span class="sxs-lookup"><span data-stu-id="c1e57-112">Teams interaction recording overview</span></span>

<span data-ttu-id="c1e57-113">Сценарии использования для записи взаимодействия можно разделить на четыре основных категории функциональных возможностей записи: удобные, функциональные, организационные и законных перехваты, как показано на рисунке.</span><span class="sxs-lookup"><span data-stu-id="c1e57-113">Interaction recording use cases can effectively be separated into four primary categories of recording functionality – Convenience, Functional, Organizational, and Lawful Intercept, as shown in the image:</span></span>

<span data-ttu-id="c1e57-114">![Снимок экрана, на котором показано, что такое запись взаимодействия и почему.](media/recording-taxonomy.png "На изображении отображаются категории записи.")</span><span class="sxs-lookup"><span data-stu-id="c1e57-114">![Screenshot showing the interaction recording what and why.](media/recording-taxonomy.png "The image shows the recording categories.")</span></span>

<span data-ttu-id="c1e57-115">Каждая из категорий имеет разные требования для начала записи, что записывается, где хранятся записи, кто получает уведомление, кто управляет доступом и как выполняется обработка хранения.</span><span class="sxs-lookup"><span data-stu-id="c1e57-115">Each of the categories entails different requirements for how recordings are initiated, what is recorded, where recordings are stored, who is notified, who controls access, and how retention is handled.</span></span>

| <span data-ttu-id="c1e57-116">Тип</span><span class="sxs-lookup"><span data-stu-id="c1e57-116">Type</span></span>                   | <span data-ttu-id="c1e57-117">Благодаря</span><span class="sxs-lookup"><span data-stu-id="c1e57-117">Convenience</span></span>        | <span data-ttu-id="c1e57-118">Функция</span><span class="sxs-lookup"><span data-stu-id="c1e57-118">Functional</span></span>         | <span data-ttu-id="c1e57-119">Org — общие</span><span class="sxs-lookup"><span data-stu-id="c1e57-119">Org - General</span></span>      | <span data-ttu-id="c1e57-120">Поднадзорные Организации</span><span class="sxs-lookup"><span data-stu-id="c1e57-120">Org - Regulated</span></span> | <span data-ttu-id="c1e57-121">Законных перехват</span><span class="sxs-lookup"><span data-stu-id="c1e57-121">Lawful Intercept</span></span>   |
| ---------------------- | ------------------ | ------------------ | ------------------ | --------------- | ------------------ |
| <span data-ttu-id="c1e57-122">Владельцы</span><span class="sxs-lookup"><span data-stu-id="c1e57-122">Initiator</span></span>              | <span data-ttu-id="c1e57-123">Пользователь</span><span class="sxs-lookup"><span data-stu-id="c1e57-123">User</span></span>               | <span data-ttu-id="c1e57-124">Приложение/решение</span><span class="sxs-lookup"><span data-stu-id="c1e57-124">App/Solution</span></span>       | <span data-ttu-id="c1e57-125">Администратор (система)</span><span class="sxs-lookup"><span data-stu-id="c1e57-125">Admin (system)</span></span>     | <span data-ttu-id="c1e57-126">Администратор (система)</span><span class="sxs-lookup"><span data-stu-id="c1e57-126">Admin (system)</span></span>  | <span data-ttu-id="c1e57-127">LEA</span><span class="sxs-lookup"><span data-stu-id="c1e57-127">LEA</span></span>                |
| <span data-ttu-id="c1e57-128">Целевой объект</span><span class="sxs-lookup"><span data-stu-id="c1e57-128">Target</span></span>                 | <span data-ttu-id="c1e57-129">Для каждого звонка или собрания</span><span class="sxs-lookup"><span data-stu-id="c1e57-129">Per-call / meeting</span></span> | <span data-ttu-id="c1e57-130">Для каждого звонка или собрания</span><span class="sxs-lookup"><span data-stu-id="c1e57-130">Per-call / meeting</span></span> | <span data-ttu-id="c1e57-131">Для каждого звонка или собрания</span><span class="sxs-lookup"><span data-stu-id="c1e57-131">Per-call / meeting</span></span> | <span data-ttu-id="c1e57-132">Для каждого пользователя</span><span class="sxs-lookup"><span data-stu-id="c1e57-132">Per-user</span></span>        | <span data-ttu-id="c1e57-133">На конечную точку/выполнено</span><span class="sxs-lookup"><span data-stu-id="c1e57-133">Per-endpoint / DID</span></span> |
| <span data-ttu-id="c1e57-134">Владелец хранилища</span><span class="sxs-lookup"><span data-stu-id="c1e57-134">Storage owner</span></span>          | <span data-ttu-id="c1e57-135">Пользователь</span><span class="sxs-lookup"><span data-stu-id="c1e57-135">User</span></span>               | <span data-ttu-id="c1e57-136">·</span><span class="sxs-lookup"><span data-stu-id="c1e57-136">App</span></span>                | <span data-ttu-id="c1e57-137">RAS</span><span class="sxs-lookup"><span data-stu-id="c1e57-137">Admin</span></span>              | <span data-ttu-id="c1e57-138">Соответствие требованиям</span><span class="sxs-lookup"><span data-stu-id="c1e57-138">Compliance</span></span>      | <span data-ttu-id="c1e57-139">LEA</span><span class="sxs-lookup"><span data-stu-id="c1e57-139">LEA</span></span>                |
| <span data-ttu-id="c1e57-140">Требуется уведомление?</span><span class="sxs-lookup"><span data-stu-id="c1e57-140">Notification required?</span></span> | <span data-ttu-id="c1e57-141">Да</span><span class="sxs-lookup"><span data-stu-id="c1e57-141">Yes</span></span>                | <span data-ttu-id="c1e57-142">Да</span><span class="sxs-lookup"><span data-stu-id="c1e57-142">Yes</span></span>                | <span data-ttu-id="c1e57-143">Да</span><span class="sxs-lookup"><span data-stu-id="c1e57-143">Yes</span></span>                | <span data-ttu-id="c1e57-144">Да</span><span class="sxs-lookup"><span data-stu-id="c1e57-144">Yes</span></span>             | <span data-ttu-id="c1e57-145">Нет</span><span class="sxs-lookup"><span data-stu-id="c1e57-145">No</span></span>                 |
| <span data-ttu-id="c1e57-146">Владелец Access</span><span class="sxs-lookup"><span data-stu-id="c1e57-146">Access Owner</span></span>           | <span data-ttu-id="c1e57-147">Пользователь</span><span class="sxs-lookup"><span data-stu-id="c1e57-147">User</span></span>               | <span data-ttu-id="c1e57-148">·</span><span class="sxs-lookup"><span data-stu-id="c1e57-148">App</span></span>                | <span data-ttu-id="c1e57-149">RAS</span><span class="sxs-lookup"><span data-stu-id="c1e57-149">Admin</span></span>              | <span data-ttu-id="c1e57-150">Соответствие требованиям</span><span class="sxs-lookup"><span data-stu-id="c1e57-150">Compliance</span></span>      | <span data-ttu-id="c1e57-151">LEA</span><span class="sxs-lookup"><span data-stu-id="c1e57-151">LEA</span></span>                |
| <span data-ttu-id="c1e57-152">Политика хранения?</span><span class="sxs-lookup"><span data-stu-id="c1e57-152">Retention Policy?</span></span>      | <span data-ttu-id="c1e57-153">Необязательно </span><span class="sxs-lookup"><span data-stu-id="c1e57-153">Optional</span></span>           | <span data-ttu-id="c1e57-154">Да</span><span class="sxs-lookup"><span data-stu-id="c1e57-154">Yes</span></span>                | <span data-ttu-id="c1e57-155">Да</span><span class="sxs-lookup"><span data-stu-id="c1e57-155">Yes</span></span>                | <span data-ttu-id="c1e57-156">Да</span><span class="sxs-lookup"><span data-stu-id="c1e57-156">Yes</span></span>             | <span data-ttu-id="c1e57-157">Да</span><span class="sxs-lookup"><span data-stu-id="c1e57-157">Yes</span></span>                |

<span data-ttu-id="c1e57-158">Teams предоставляет различные возможности для [<span class="underline">удобной</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) и функциональной записи для собраний и событий Live Events.</span><span class="sxs-lookup"><span data-stu-id="c1e57-158">Teams provides various capabilities for [<span class="underline">convenient</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) and functional recording for meetings and live events.</span></span> <span data-ttu-id="c1e57-159">Запись в Организации означает, что Организации, которые разрабатывают команды для звонков и собраний, в соответствии с политикой администрирования, при выполнении звонков и собраний по сети должны автоматически записываться и записываться для последующей обработки и хранения в соответствии с требованиями компании или законодательной политики.</span><span class="sxs-lookup"><span data-stu-id="c1e57-159">Organizational recording means enabling organizations adopting Teams for calling and meetings to stipulate, by way of an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span> <span data-ttu-id="c1e57-160">Пользователи в этой политике будут знать о том, что ваши цифровые взаимодействия с группами записываются, но они не смогут отключить запись и не получат доступ к записи после завершения взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="c1e57-160">Users under this policy will be aware that their digital interactions with Teams are being recorded but will not be able to disable the recording and will not have access to the recording once the interaction is complete.</span></span> <span data-ttu-id="c1e57-161">Запись становится частью организационного архива, доступного для соответствия и юридического персонала для обнаружения электронных данных, юридических удержаний и других целей хранения в корпоративной компании.</span><span class="sxs-lookup"><span data-stu-id="c1e57-161">The recording becomes part of the organizational archive available to compliance and legal personnel for eDiscovery, legal hold, and other corporate retention uses.</span></span>

## <a name="example-user-needs"></a><span data-ttu-id="c1e57-162">Примеры потребностей пользователей</span><span class="sxs-lookup"><span data-stu-id="c1e57-162">Example user needs</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="c1e57-163"><strong>Дайте</strong></span><span class="sxs-lookup"><span data-stu-id="c1e57-163"><strong>Persona</strong></span></span></th>
<th><span data-ttu-id="c1e57-164"><strong>Необходимо</strong></span><span class="sxs-lookup"><span data-stu-id="c1e57-164"><strong>Needs</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="c1e57-165">Записанные пользователи</span><span class="sxs-lookup"><span data-stu-id="c1e57-165">Recorded users</span></span></td>
<td><ul>
<li><p><span data-ttu-id="c1e57-166">Получать уведомления о ходе записи.</span><span class="sxs-lookup"><span data-stu-id="c1e57-166">Be notified when recording is in progress.</span></span></p></li>
<li><p><span data-ttu-id="c1e57-167">Будьте в курсе событий, вызывающих ошибки политики и (или) записи, которые приводят к изменениям в поведении вызова.</span><span class="sxs-lookup"><span data-stu-id="c1e57-167">Be informed when policy and/or recorder error is causing changes in calling behavior.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c1e57-168">Администратор связи</span><span class="sxs-lookup"><span data-stu-id="c1e57-168">Communications admin</span></span></td>
<td><ul>
<li><p><span data-ttu-id="c1e57-169">Узнайте, почему и как применять политики записи к пользователям и конечным точкам Teams.</span><span class="sxs-lookup"><span data-stu-id="c1e57-169">Understand why and how to apply / enforce recording policies to Teams users / endpoints.</span></span></p></li>
<li><p><span data-ttu-id="c1e57-170">Настройте и настройте политики записи в Teams для Организации.</span><span class="sxs-lookup"><span data-stu-id="c1e57-170">Configure and maintain Teams recording policies for the organization.</span></span></p></li>
<li><p><span data-ttu-id="c1e57-171">Отслеживание и устранение проблем, связанных с записью, в рамках звонков и собраний Teams.</span><span class="sxs-lookup"><span data-stu-id="c1e57-171">Monitor and troubleshoot recording-related issues with Teams calls and meetings.</span></span></p></li>
<li><p><span data-ttu-id="c1e57-172">Поддержка внутреннего сотрудника по обеспечению соответствия требованиям в отношении использования, качества и надежности.</span><span class="sxs-lookup"><span data-stu-id="c1e57-172">Support internal compliance officer with operational analytics on usage, quality, and reliability.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c1e57-173">Сотрудник отдела соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="c1e57-173">Compliance officer</span></span></td>
<td><ul>
<li><p><span data-ttu-id="c1e57-174">Соберите все коммуникации в Teams так, чтобы они соответствовали обязательствам по обеспечению соответствия требованиям в соответствующих региональных регионах.</span><span class="sxs-lookup"><span data-stu-id="c1e57-174">Collect all Teams communications in the manner required to meet compliance obligations in appropriate regional boundaries.</span></span></p></li>
<li><p><span data-ttu-id="c1e57-175">Поиск взаимодействий на основе метаданных или контента взаимодействия, связанных с связью.</span><span class="sxs-lookup"><span data-stu-id="c1e57-175">Search for interactions based on communication-related metadata or interaction content.</span></span> <span data-ttu-id="c1e57-176">Ниже приведены распространенные примеры.</span><span class="sxs-lookup"><span data-stu-id="c1e57-176">Common examples include:</span></span></p>
<ul>
<li><p><span data-ttu-id="c1e57-177"><strong>Метаданные</strong> - Участники, время, направление, набранный номер, номер источника, пользовательские бизнес-данные</span><span class="sxs-lookup"><span data-stu-id="c1e57-177"><strong>Metadata</strong> - Participants, time, direction, dialed number, origin number, Custom business data</span></span></p></li>
<li><p><span data-ttu-id="c1e57-178"><strong>Содержимое</strong> — транскрипция, тональность, фонетическая информация, взаимосвязанные взаимодействия</span><span class="sxs-lookup"><span data-stu-id="c1e57-178"><strong>Content</strong> – Transcription, sentiment, phonetics, related interactions</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="c1e57-179">Анализ и взаимодействие с собранными связями, в том числе возможность отслеживать взаимодействия по мере их сбора.</span><span class="sxs-lookup"><span data-stu-id="c1e57-179">Analyze and interact with collected communications, including the ability to monitor interactions as they are being collected.</span></span></p></li>
<li><p><span data-ttu-id="c1e57-180">Обеспечьте безопасность собранных сообщений и запретите все этапы.</span><span class="sxs-lookup"><span data-stu-id="c1e57-180">Ensure security of collected communications and prevent tampering at all stages.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a><span data-ttu-id="c1e57-181">Общие сведения об архитектуре решения</span><span class="sxs-lookup"><span data-stu-id="c1e57-181">Solution architecture overview</span></span>

<span data-ttu-id="c1e57-182">Решения для записи соответствия требованиям объединены с группами, как показано на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="c1e57-182">Compliance recording solutions are integrated with Teams as shown in the following diagram:</span></span>

<span data-ttu-id="c1e57-183">![Снимок экрана: параметр "настраиваемое приложение группы"](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "Изображения показывают поток при отправке и получении собрания или звонка команды.")</span><span class="sxs-lookup"><span data-stu-id="c1e57-183">![Screenshot showing the team custom app setting](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "The images shows the flow when a Teams meeting or call is sent and received.")</span></span>

## <a name="recorder"></a><span data-ttu-id="c1e57-184">Recorder</span><span class="sxs-lookup"><span data-stu-id="c1e57-184">Recorder</span></span>

<span data-ttu-id="c1e57-185">Основным компонентом решения для записи соответствия требованиям является средство записи.</span><span class="sxs-lookup"><span data-stu-id="c1e57-185">The core component of the compliance recording solution is the recorder.</span></span>
<span data-ttu-id="c1e57-186">Средства записи создаются как масштабируемые службы на основе Azure (ботов), которые [<span class="underline">используют платформу связи Майкрософт</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) и регистрируются в качестве приложений в Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="c1e57-186">Recorders are built as scalable Azure-based services (bots) that [<span class="underline">leverage Microsoft’s communications platform</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) and register as applications with Microsoft Graph.</span></span> <span data-ttu-id="c1e57-187">Средство записи обеспечивает непосредственное взаимодействие с [<span class="underline">API платформой связи</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) и собраний, а также предоставляет конечную точку для приема мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="c1e57-187">The recorder provides the direct interaction with the Teams calls and meetings [<span class="underline">communications platform APIs</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) and provides the endpoint for media ingestion.</span></span>

<span data-ttu-id="c1e57-188">[<span class="underline">Будет доступно пример приложения для записи соответствия требованиям</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) , в котором показано, как настроить робот, создать экземпляр приложения и назначить политики соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="c1e57-188">A [<span class="underline">sample compliance recorder application is available</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) that shows how to configure the bot, create the app instance and assign the compliance policies.</span></span> <span data-ttu-id="c1e57-189">В образце также приведены примеры использования API для записи конкретных взаимодействий, например обработки маршрутизации [<span class="underline">входящих звонков</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) , [<span class="underline">изменения состояния записи</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)и [<span class="underline">удаления пользователя, который записывается</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span><span class="sxs-lookup"><span data-stu-id="c1e57-189">The sample also has examples on API usage for recording specific interactions such as handling [<span class="underline">incoming call</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) routing, [<span class="underline">changing recording states</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138), and [<span class="underline">removing the user who is being recorded</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span></span>
<span data-ttu-id="c1e57-190">Документацию по графике для конкретных API можно найти здесь для [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) и [<span class="underline">incomingContext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span><span class="sxs-lookup"><span data-stu-id="c1e57-190">Graph documentation on the specific APIs can be found here for [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) and [<span class="underline">incomingContext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span></span>

<span data-ttu-id="c1e57-191">Точная реализация службы записи зависит от партнера, но должна быть разработана для поддержки нескольких средств записи в целях обеспечения высокой доступности и географического распространения развертывания для сокращения задержки от команд до средства записи.</span><span class="sxs-lookup"><span data-stu-id="c1e57-191">The exact implementation of the recorder service will vary by partner but must be designed to support multiple recorders in order to achieve high availability and geographical distribution of deployment to reduce latency from Teams to the recorder.</span></span> <span data-ttu-id="c1e57-192">Кроме того, ожидается, что сами средства записи должны быть спроектированы с учетом устойчивости и избыточности.</span><span class="sxs-lookup"><span data-stu-id="c1e57-192">In addition, it is expected that Recorders themselves be designed with resiliency and redundancy in mind.</span></span>

<span data-ttu-id="c1e57-193">Перед отправкой решения о том, что все требования интеграции с записью соответствия требованиям, партнеры должны проверить минимальную требуемую версию API Microsoft Graph для обмена данными и пакеты SDK для Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c1e57-193">Partners must confirm the minimum required release version of the Microsoft Graph communications APIs and SDKs with Microsoft before submitting their solution for certification to ensure that all requirements of compliance recording integration are supported.</span></span>

<span data-ttu-id="c1e57-194">Существует два конкретных требования, которые являются фундаментальными для сценария записи соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="c1e57-194">Two specific requirements that are fundamental for compliance recording scenario are:</span></span>

- <span data-ttu-id="c1e57-195">На самом и в Azure должны быть развернуты роботы для записи</span><span class="sxs-lookup"><span data-stu-id="c1e57-195">Recorder bot must be deployed in Azure</span></span>

- <span data-ttu-id="c1e57-196">На виртуальной машине Windows в Azure должен выполняться робот средства записи.</span><span class="sxs-lookup"><span data-stu-id="c1e57-196">Recorder bot must run on a Windows VM in Azure</span></span>

<span data-ttu-id="c1e57-197">Требования Azure и VM для Windows применимы только к компоненту Bot для Teams, а это означает, что партнер может реализовать оставшуюся платформу, если она подходит для обеспечения соблюдения требований к производительности и функциональным требованиям для записи соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="c1e57-197">The Azure and Windows VM requirements only apply to the Teams Bot component, which means that a partner may implement the rest of the platform of their choice provided they can meet the relevant performance and functional requirements for compliance recording.</span></span>

## <a name="compliance-recording-policy-assignment-and-provisioning"></a><span data-ttu-id="c1e57-198">Назначение и подготовка политики записи соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="c1e57-198">Compliance recording policy assignment and provisioning</span></span>

<span data-ttu-id="c1e57-199">ИТ администраторы могут определить, какие пользователи будут записаны, а какие будут использоваться для каждого пользователя, создавая и назначая политики записи соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="c1e57-199">IT Administrators can determine which users are to be recorded and which recorder will be used for each user, by creating and assigning compliance recording policies.</span></span> <span data-ttu-id="c1e57-200">Средства записи автоматически приглашаются в беседы на основе конфигурации этих политик, когда происходит взаимодействие с связью.</span><span class="sxs-lookup"><span data-stu-id="c1e57-200">Recorders are automatically invited to participate in conversations based on the configuration of these policies when a communication interaction takes place.</span></span> <span data-ttu-id="c1e57-201">Политики записи соответствия управляются с помощью [<span class="underline">Microsoft PowerShell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) и могут применяться для каждой организации на уровне клиента, пользователя и группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="c1e57-201">Compliance recording policies are managed using [<span class="underline">Microsoft Powershell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) and can be applied at the tenant, per-user, and security group level for each organization.</span></span> <span data-ttu-id="c1e57-202">Дополнительную информацию можно найти в документах Microsoft для [<span class="underline">политик собраний</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams), [<span class="underline">политиках звонков</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy) и  [<span class="underline">групповых политик</span>](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group).</span><span class="sxs-lookup"><span data-stu-id="c1e57-202">You can find more information on Microsoft Docs for [<span class="underline">Meeting policies</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams), [<span class="underline">calling policies</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy) and  [<span class="underline">group policies</span>](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group).</span></span>

1. <span data-ttu-id="c1e57-203">Создайте экземпляр приложения в клиенте.</span><span class="sxs-lookup"><span data-stu-id="c1e57-203">Create an application instance in your tenant.</span></span>

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

2. <span data-ttu-id="c1e57-204">Создание политики записи соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="c1e57-204">Create a Compliance Recording policy.</span></span>

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

   [<span data-ttu-id="c1e57-205"><span class="underline">Set-CsTeamsComplianceRecordingPolicy</span></span><span class="sxs-lookup"><span data-stu-id="c1e57-205"><span class="underline">Set-CsTeamsComplianceRecordingPolicy</span></span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. <span data-ttu-id="c1e57-206">Назначение пользователю политики записи соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="c1e57-206">Assign the Compliance Recording policy to a user.</span></span>

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   [<span data-ttu-id="c1e57-207"><span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span></span><span class="sxs-lookup"><span data-stu-id="c1e57-207"><span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span></span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a><span data-ttu-id="c1e57-208">Взаимодействие с пользователем</span><span class="sxs-lookup"><span data-stu-id="c1e57-208">User experiences</span></span>

<span data-ttu-id="c1e57-209">Поддержка уведомлений включена с помощью клиента Teams.</span><span class="sxs-lookup"><span data-stu-id="c1e57-209">Support for notifications is enabled using the Teams client experiences.</span></span> <span data-ttu-id="c1e57-210">Этот интерфейс может быть визуальным или звуковым.</span><span class="sxs-lookup"><span data-stu-id="c1e57-210">The experiences can be either visual or audio.</span></span>

<span data-ttu-id="c1e57-211">**Клиенты Teams-наглядное уведомление**</span><span class="sxs-lookup"><span data-stu-id="c1e57-211">**Teams clients - visual notice**</span></span>
- <span data-ttu-id="c1e57-212">Классическое и Интернет-</span><span class="sxs-lookup"><span data-stu-id="c1e57-212">Desktop/web</span></span>
- <span data-ttu-id="c1e57-213">Мобильный (iOS/Android)</span><span class="sxs-lookup"><span data-stu-id="c1e57-213">Mobile (iOS/Android)</span></span>
- <span data-ttu-id="c1e57-214">Телефоны Teams</span><span class="sxs-lookup"><span data-stu-id="c1e57-214">Teams phones</span></span>
- <span data-ttu-id="c1e57-215">Комнаты команд</span><span class="sxs-lookup"><span data-stu-id="c1e57-215">Teams rooms</span></span>

<span data-ttu-id="c1e57-216">**Другие конечные точки — уведомление о звуке**</span><span class="sxs-lookup"><span data-stu-id="c1e57-216">**Other endpoints - audio notice**</span></span>
- <span data-ttu-id="c1e57-217">Телефоны SIP</span><span class="sxs-lookup"><span data-stu-id="c1e57-217">SIP phones</span></span>
- <span data-ttu-id="c1e57-218">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c1e57-218">Skype for Business</span></span>
- <span data-ttu-id="c1e57-219">Аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="c1e57-219">Audio conferencing</span></span>
- <span data-ttu-id="c1e57-220">КОММУТИРУЕМые звонки</span><span class="sxs-lookup"><span data-stu-id="c1e57-220">PSTN callers</span></span>

## <a name="compliance-recording-for-teams-certification-programs"></a><span data-ttu-id="c1e57-221">Запись соответствия требованиям для программ сертификации Teams</span><span class="sxs-lookup"><span data-stu-id="c1e57-221">Compliance recording for Teams certification programs</span></span>

<span data-ttu-id="c1e57-222">Помимо публикации общедоступных API-интерфейсов, позволяющих партнерам разрабатывать и интегрировать решения CCaaS с помощью Teams, мы разработали запись соответствия требованиям для программы сертификации Microsoft Teams, чтобы предоставить клиентам гарантию о том, что решение для каждого участника было проверено и проверено на предмет качества, совместимости и надежности, которые они ожидают от решений Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c1e57-222">In addition to publishing publicly-available APIs allowing partners to develop and integrate CCaaS solutions with Teams, we have developed the compliance recording for Microsoft Teams certification program to provide customers with the assurance that each participating partner’s solution has been tested and verified to provide the quality, compatibility and reliability they expect from Microsoft solutions.</span></span>  

<span data-ttu-id="c1e57-223">Следующие партнеры получили Вам свое решение для Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c1e57-223">The following partners have certified their solution for Microsoft Teams.</span></span>

|<span data-ttu-id="c1e57-224">Сотрудничать</span><span class="sxs-lookup"><span data-stu-id="c1e57-224">Partner</span></span>|<span data-ttu-id="c1e57-225">Веб-сайт решения</span><span class="sxs-lookup"><span data-stu-id="c1e57-225">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="c1e57-226">ПРИВЛЕКАТЕЛЬН</span><span class="sxs-lookup"><span data-stu-id="c1e57-226">NICE</span></span> |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |


<span data-ttu-id="c1e57-227">Следующие партнеры находятся в процессе сертификации своих решений для Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c1e57-227">The following partners are in the process of certifying their solution for Microsoft Teams.</span></span>

|<span data-ttu-id="c1e57-228">Сотрудничать</span><span class="sxs-lookup"><span data-stu-id="c1e57-228">Partner</span></span>|<span data-ttu-id="c1e57-229">Веб-сайт решения</span><span class="sxs-lookup"><span data-stu-id="c1e57-229">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="c1e57-230">Технологии ASC</span><span class="sxs-lookup"><span data-stu-id="c1e57-230">ASC Technologies</span></span> |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|<span data-ttu-id="c1e57-231">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="c1e57-231">AudioCodes</span></span> |[https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording) |
|<span data-ttu-id="c1e57-232">CallCabinet</span><span class="sxs-lookup"><span data-stu-id="c1e57-232">CallCabinet</span></span> |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|<span data-ttu-id="c1e57-233">Dubber</span><span class="sxs-lookup"><span data-stu-id="c1e57-233">Dubber</span></span> |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|<span data-ttu-id="c1e57-234">Технологии Landis</span><span class="sxs-lookup"><span data-stu-id="c1e57-234">Landis Technologies</span></span> |[https://landistechnologies.com/](https://landistechnologies.com/) |
|<span data-ttu-id="c1e57-235">Luware</span><span class="sxs-lookup"><span data-stu-id="c1e57-235">Luware</span></span> |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|<span data-ttu-id="c1e57-236">Numonix</span><span class="sxs-lookup"><span data-stu-id="c1e57-236">Numonix</span></span> |[https://numonix.cloud](https://numonix.cloud)    |
|<span data-ttu-id="c1e57-237">Для новаторства (дуб)</span><span class="sxs-lookup"><span data-stu-id="c1e57-237">Oak Innovation</span></span> |[https://www.oakinnovate.com/call-recording](https://www.oakinnovate.com/call-recording) |
|<span data-ttu-id="c1e57-238">Красная рамка</span><span class="sxs-lookup"><span data-stu-id="c1e57-238">Red Box</span></span> |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|<span data-ttu-id="c1e57-239">Verint</span><span class="sxs-lookup"><span data-stu-id="c1e57-239">Verint</span></span> |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

<span data-ttu-id="c1e57-240">Этот список будет обновляться по мере того, как дополнительные участники будут присоединяться к критерию сертификации и отвечать на них.</span><span class="sxs-lookup"><span data-stu-id="c1e57-240">This list will be updated as more partners join and meet the certification criteria.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c1e57-241">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="c1e57-241">Next steps</span></span>

<span data-ttu-id="c1e57-242">Если вы хотите присоединиться к программе сертификации, пожалуйста,  <a href= "mailto:Teamscategorypartner@microsoft.com">поTeamscategorypartner@microsoft.com</a>по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="c1e57-242">If you are a vendor seeking to join the certification program, please mail  <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>.</span></span>
