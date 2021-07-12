---
title: 'Краткое руководство для администраторов: собрания и трансляции в Microsoft Teams'
ms.reviewer: ''
description: Краткое руководство для администраторов о получении соответствующих лицензий, развертывании и настройке собраний по сети и трансляций в Microsoft Teams.
ms.topic: article
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 03611f2d166883ce960e272e2f3b11300cd20c54
ms.sourcegitcommit: 616b6d0d5be2b333519b79ab59a4117036ba647e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2021
ms.locfileid: "53363584"
---
# <a name="admin-quick-start---meetings-and-live-events-in-microsoft-teams"></a><span data-ttu-id="1044b-103">Краткое руководство для администраторов: собрания и трансляции в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1044b-103">Admin quick start - Meetings and live events in Microsoft Teams</span></span>

<span data-ttu-id="1044b-p101">В Microsoft Teams существует 2 способа общения: собрания и трансляции. Воспользуйтесь этой статьей, чтобы быстро развернуть и настроить собрания и трансляции для своей организации.</span><span class="sxs-lookup"><span data-stu-id="1044b-p101">There are 2 ways to meet in Microsoft Teams - meetings and live events. Use this article to quickly roll out and configure meetings and live events for your organization.</span></span>

> [!Note]
> <span data-ttu-id="1044b-106">Подробные сведения о быстрой настройке собраний и событий Teams на разных платформах см. в статье [Возможности Teams на разных платформах](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span><span class="sxs-lookup"><span data-stu-id="1044b-106">For details about quickly configuring Teams meetings and events on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

 - <span data-ttu-id="1044b-p102">**Собрания** в Teams поддерживают передачу звука и видео, а также демонстрацию экрана для 1000 пользователей. И вам не нужно быть участником организации (и вам даже не нужна учетная запись Teams!), чтобы присоединиться к собранию Teams. Просто просмотрите в приглашении инструкции о присоединении.</span><span class="sxs-lookup"><span data-stu-id="1044b-p102">**Meetings** in Teams include audio, video, and screen sharing for up to 1000 people. They're one of the key ways to collaborate in Teams. And you don't need to be a member of an organization (or even have a Teams account!) to join a Teams meeting—just look in the invitation for instructions about calling in.</span></span>

 - <span data-ttu-id="1044b-p103">**Трансляции** — это расширение собраний Teams, с помощью которого можно планировать и проводить мероприятия с трансляцией для крупных аудиторий (до 10 000 пользователей) в Интернете. Если вам требуется провести собрание для более чем 1000 человек, используйте трансляцию.</span><span class="sxs-lookup"><span data-stu-id="1044b-p103">**Live events** are an extension of Teams meetings that enable you to schedule and produce events that stream to large online audiences - up to 10,000 people. If you need a meeting for more than 1000 people, use a live event.</span></span>

## <a name="get-licenses-for-meetings-and-live-events"></a><span data-ttu-id="1044b-112">Получение лицензий для собраний и трансляций</span><span class="sxs-lookup"><span data-stu-id="1044b-112">Get licenses for meetings and live events</span></span>

<span data-ttu-id="1044b-p104">Любой может бесплатно посетить собрание или открытую трансляцию Teams — лицензия не требуется. Участники могут присоединиться к собранию и трансляции Teams, нажав кнопку **Присоединиться** в Teams или в приглашении на собрание. Звук собрания — это часть собрания Teams, но если вы хотите, чтобы пользователи могли подключиться к собранию по телефону, потребуется указать номер телефона для подключения.</span><span class="sxs-lookup"><span data-stu-id="1044b-p104">Anyone can attend a Teams meeting or public live event for free - no license is required. Attendees join a Teams meeting or live event by clicking the **Join** button in Teams or the meeting invitation. Meeting audio is part of a Teams meeting, but if you want people to be able to dial in to a meeting by phone, you'll need to provide a dial-in number.</span></span>

<span data-ttu-id="1044b-116">Пользователям, организующим, планирующим и проводящим собрания или трансляции, потребуется один из планов лицензирования из статьи [Описание службы Microsoft Teams](/office365/servicedescriptions/teams-service-description)</span><span class="sxs-lookup"><span data-stu-id="1044b-116">For the people who will organize, schedule, and host meetings or live events, they'll need one of the licensing plans described in the [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span> 

<span data-ttu-id="1044b-117">Если вы уже используете Teams, возможно, у вас есть лицензия, необходимая для организации и проведения собраний и трансляций.</span><span class="sxs-lookup"><span data-stu-id="1044b-117">If you're already using Teams, you probably have the license you need for organizing and hosting meetings and live events.</span></span>

## <a name="make-sure-your-networks-ready"></a><span data-ttu-id="1044b-118">Проверка готовности сети</span><span class="sxs-lookup"><span data-stu-id="1044b-118">Make sure your network's ready</span></span>

<span data-ttu-id="1044b-p105">Если вы уже подготовили свою сеть при развертывании Microsoft 365 или Office 365, возможно, у вас все настроено. В любом случае, особенно если вы быстро развертываете Teams в качестве первой рабочей нагрузки Office 365 для поддержки **удаленных сотрудников**, ознакомьтесь со статьей [Подготовка сети организации к использованию Teams](prepare-network.md), чтобы убедиться в своей готовности.</span><span class="sxs-lookup"><span data-stu-id="1044b-p105">If you already prepared your network when you rolled out Microsoft 365 or Office 365, you're probably all set. In any case - and especially if you're rolling out Teams quickly as your first Office 365 workload to support **remote workers** - read [Prepare your organization's network for Teams](prepare-network.md) to be sure you're ready.</span></span>

## <a name="meetings-and-conferencing"></a><span data-ttu-id="1044b-121">Собрания и конференции</span><span class="sxs-lookup"><span data-stu-id="1044b-121">Meetings and conferencing</span></span>

- <span data-ttu-id="1044b-p106">В качестве администратора вы настроите [параметры собраний](meeting-settings-in-teams.md) для всех пользователей. Затем вы примените [политики собраний](meeting-policies-in-teams.md) для выбора функций, доступных (и недоступных) пользователям.</span><span class="sxs-lookup"><span data-stu-id="1044b-p106">As the admin, you'll configure [meeting settings](meeting-settings-in-teams.md) for everyone. Then you'll use [meeting policies](meeting-policies-in-teams.md) to control what meeting features are (and aren't) available for your users.</span></span>

- <span data-ttu-id="1044b-124">Дополнительные сведения об управлении записью собраний приведены в статье [Запись облачного собрания в Teams](cloud-recording.md).</span><span class="sxs-lookup"><span data-stu-id="1044b-124">To learn about managing meeting recording, read [Teams cloud meeting recording](cloud-recording.md).</span></span>

- <span data-ttu-id="1044b-p107">Если ваши пользователи впервые применяют собрание Teams, поделитесь с ними учебным курсом [Управление собраниями](https://support.office.com/article/join-a-teams-meeting-078e9868-f1aa-4414-8bb9-ee88e9236ee4). Ознакомьтесь с нашим онлайн-занятием под руководством инструктора [Проведение эффективных собраний в Teams](https://microsoftteams.eventbuilder.com/MaximizingTeamsMeetings).</span><span class="sxs-lookup"><span data-stu-id="1044b-p107">If your users are new to Teams meetings, share the [Manage meetings](https://support.office.com/article/join-a-teams-meeting-078e9868-f1aa-4414-8bb9-ee88e9236ee4) training with them. Check out our instructor-led online class, [Run effective meetings with Teams](https://microsoftteams.eventbuilder.com/MaximizingTeamsMeetings).</span></span>

- <span data-ttu-id="1044b-127">Сведения об управлении параметрами собраний см. в статье [Изменение параметров участников для собраний Teams](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e).</span><span class="sxs-lookup"><span data-stu-id="1044b-127">To learn about managing meeting options, read [Change participant settings for a Teams meeting](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e).</span></span>

- <span data-ttu-id="1044b-p108">Не забудьте об [управлении устройствами пользователей](./devices/device-management.md) — телефонами, гарнитурами и камерами. Чтобы получить актуальные сведения об устройствах, сертифицированных для Teams, перейдите в раздел [Устройства Teams](https://office.com/teamsdevices).</span><span class="sxs-lookup"><span data-stu-id="1044b-p108">Don't forget about [managing your users' devices](./devices/device-management.md) - phones, headsets, cameras. To get the latest and up-to-date information on Teams certified devices, go to [Teams devices](https://office.com/teamsdevices).</span></span>

## <a name="live-events"></a><span data-ttu-id="1044b-130">Трансляции</span><span class="sxs-lookup"><span data-stu-id="1044b-130">Live events</span></span>

- <span data-ttu-id="1044b-p109">Как и для собраний, вы в качестве администратора [настраиваете трансляции](teams-live-events/configure-teams-live-events.md) для всех пользователей. Затем настройте (и назначьте) [политики трансляций](teams-live-events/set-up-for-teams-live-events.md) для выбора доступных (и недоступных) возможностей для пользователей.</span><span class="sxs-lookup"><span data-stu-id="1044b-p109">Similar to meetings, you - the admin - [configure live events](teams-live-events/configure-teams-live-events.md) for everyone. Then set up (and assign) [live event policies](teams-live-events/set-up-for-teams-live-events.md) to control what your users can (and can't) do.</span></span>

- <span data-ttu-id="1044b-133">Обеспечьте подготовку инициаторов и организаторов трансляций — отправьте их на страницу [Начало работы с трансляциями](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a).</span><span class="sxs-lookup"><span data-stu-id="1044b-133">Make sure your live event producers and organizers are trained - send them to [Get started with live events](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a).</span></span>

- <span data-ttu-id="1044b-134">Если вы еще не работали с трансляциями, ознакомьтесь со статьями [Что такое трансляции Teams?](teams-live-events/what-are-teams-live-events.md) и [Планирование трансляций Teams](teams-live-events/plan-for-teams-live-events.md).</span><span class="sxs-lookup"><span data-stu-id="1044b-134">If you're new to live events, check out [What are Teams live events?](teams-live-events/what-are-teams-live-events.md) and [Plan for Teams live events](teams-live-events/plan-for-teams-live-events.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="1044b-135">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="1044b-135">Related topics</span></span>

[<span data-ttu-id="1044b-136">Собрания и конференции в Teams</span><span class="sxs-lookup"><span data-stu-id="1044b-136">Meetings and conferencing in Teams</span></span>](deploy-meetings-microsoft-teams-landing-page.md)

[<span data-ttu-id="1044b-137">Аудиоконференции в Teams</span><span class="sxs-lookup"><span data-stu-id="1044b-137">Audio conferencing in Teams</span></span>](deploy-audio-conferencing-teams-landing-page.md)

[<span data-ttu-id="1044b-138">Трансляции в Teams</span><span class="sxs-lookup"><span data-stu-id="1044b-138">Live events in Teams</span></span>](teams-live-events/what-are-teams-live-events.md)

[<span data-ttu-id="1044b-139">Ограничения и спецификации для Teams</span><span class="sxs-lookup"><span data-stu-id="1044b-139">Limits and specifications for Teams</span></span>](limits-specifications-teams.md)

[<span data-ttu-id="1044b-140">Техническое сообщество Майкрософт: трансляции в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1044b-140">Microsoft Technical Community: Live events in Microsoft 365</span></span>](https://resources.techcommunity.microsoft.com/live-events/)
