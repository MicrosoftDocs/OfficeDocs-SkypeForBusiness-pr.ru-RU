---
title: Настройка модерации канала и управление им
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jotaing
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Узнайте, как настроить каналы для модерации в Microsoft Teams, а также как добавить участников команды в качестве модераторов каналов.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9598723d1a88826d1efa5fb487d02fc93aa5d4e1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822899"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a><span data-ttu-id="81625-103">Настройка модерации канала и управление им в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="81625-103">Set up and manage channel moderation in Microsoft Teams</span></span>

<span data-ttu-id="81625-104">В Microsoft Teams владельцы команд могут включить модерацию для стандартного канала, чтобы контролировать, кто может начинать новые записи и отвечать на записи в этом канале.</span><span class="sxs-lookup"><span data-stu-id="81625-104">In Microsoft Teams, team owners can turn on moderation for a standard channel to control who can start new posts and reply to posts in that channel.</span></span>

<span data-ttu-id="81625-105">Владельцы команд также могут добавлять участников в качестве модераторов.</span><span class="sxs-lookup"><span data-stu-id="81625-105">Team owners can also add team members as moderators.</span></span> <span data-ttu-id="81625-106">Владелец команды может не иметь экспертных знаний по предмету на уровне канала для лучшей модерации канала поддержки.</span><span class="sxs-lookup"><span data-stu-id="81625-106">A team owner might not have the subject matter expertise at the channel level to best support channel moderation.</span></span> <span data-ttu-id="81625-107">Если вы разрешаете определенным участникам команды модерировать канал, ответственность за управление контентом и контекстом в канале разделяются между владельцами группы и модераторами каналов.</span><span class="sxs-lookup"><span data-stu-id="81625-107">By allowing specific team members to moderate a channel, the responsibility of managing content and context within a channel is shared between team owners and channel moderators.</span></span> <span data-ttu-id="81625-108">Например, владелец команды может добавить в качестве модераторов владельцев бизнес-сайтов или владельцев контента, что позволит им управлять совместным доступом к информации в канале.</span><span class="sxs-lookup"><span data-stu-id="81625-108">For example, a team owner can add business owners or content owners as moderators, which lets them control information sharing in that channel.</span></span>

> [!NOTE]
> <span data-ttu-id="81625-109">Модерирование канала доступно для стандартных каналов.</span><span class="sxs-lookup"><span data-stu-id="81625-109">Channel moderation is available for standard channels.</span></span> <span data-ttu-id="81625-110">Она недоступна для канала "Общий" или частных каналов.</span><span class="sxs-lookup"><span data-stu-id="81625-110">It's not available for the General channel or private channels.</span></span>

## <a name="what-can-a-channel-moderator-do"></a><span data-ttu-id="81625-111">Что может делать модератор канала?</span><span class="sxs-lookup"><span data-stu-id="81625-111">What can a channel moderator do?</span></span>

<span data-ttu-id="81625-112">Модераторы каналов могут:</span><span class="sxs-lookup"><span data-stu-id="81625-112">Channel moderators can:</span></span>

- <span data-ttu-id="81625-113">Начните новую публикацию на канале.</span><span class="sxs-lookup"><span data-stu-id="81625-113">Start new posts in the channel.</span></span> <span data-ttu-id="81625-114">Если для канала включено модерирование, только модераторы могут начинать в этом канале новые записи.</span><span class="sxs-lookup"><span data-stu-id="81625-114">When moderation is turned on for a channel, only moderators can start new posts in that channel.</span></span>
- <span data-ttu-id="81625-115">Добавляйте и удаляйте участников группы в качестве модераторов в канале.</span><span class="sxs-lookup"><span data-stu-id="81625-115">Add and remove team members as moderators to a channel.</span></span> <span data-ttu-id="81625-116">Имейте в виду, что по умолчанию владельцы команд являются модераторами каналов и их нельзя удалить.</span><span class="sxs-lookup"><span data-stu-id="81625-116">Keep in mind that by default, team owners are channel moderators and can't be removed.</span></span>
- <span data-ttu-id="81625-117">Контроль над тем, могут ли участники группы отвечать на существующие сообщения канала, а также могут ли боты и соединители отправлять сообщения каналов.</span><span class="sxs-lookup"><span data-stu-id="81625-117">Control whether team members can reply to existing channel messages and whether bots and connectors can submit channel messages.</span></span>

## <a name="scenarios"></a><span data-ttu-id="81625-118">Scenarios</span><span class="sxs-lookup"><span data-stu-id="81625-118">Scenarios</span></span>

<span data-ttu-id="81625-119">Вот несколько примеров использования модерации каналов в Teams в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="81625-119">Here's some examples of how your organization can use channel moderation in Teams.</span></span>

### <a name="use-a-channel-as-an-announcement-channel"></a><span data-ttu-id="81625-120">Использование канала в качестве канала объявлений</span><span class="sxs-lookup"><span data-stu-id="81625-120">Use a channel as an announcement channel</span></span>

<span data-ttu-id="81625-121">Группа маркетинга использует определенный канал для обмена ключевыми объявлениями и планами проекта.</span><span class="sxs-lookup"><span data-stu-id="81625-121">The Marketing team uses a specific channel to share key project announcements and deliverables.</span></span> <span data-ttu-id="81625-122">Иногда участники группы могут опубликовать в канале содержимое, которое подходит для других каналов.</span><span class="sxs-lookup"><span data-stu-id="81625-122">Sometimes team members post content to the channel that more appropriately belongs in other channels.</span></span> <span data-ttu-id="81625-123">Владелец команды хочет ограничить доступ к информации в канале только объявлениями, чтобы участники команды могли использовать этот канал, чтобы быть в верхней части важного.</span><span class="sxs-lookup"><span data-stu-id="81625-123">The team owner wants to restrict information sharing in the channel to only announcements so that team members can use that channel to stay on top of what's important.</span></span>

<span data-ttu-id="81625-124">В этом случае владелец группы добавляет интересов в качестве модераторов, чтобы они могли размещать объявления в канале и отключать для участников группы возможность отвечать на сообщения в этом канале.</span><span class="sxs-lookup"><span data-stu-id="81625-124">In this scenario, the team owner adds Marketing leads as moderators so they can post announcements in the channel and turns off the ability for team members to reply to messages in that channel.</span></span>

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a><span data-ttu-id="81625-125">Использование канала для обсуждения занятий в Teams для образовательных сфере</span><span class="sxs-lookup"><span data-stu-id="81625-125">Use a channel for class discussions in Teams for Education</span></span>

<span data-ttu-id="81625-126">В Teams для образовательных образования преподаватель естественных наук хочет использовать канал для вовлечения учащихся в обсуждения определенных тем классов.</span><span class="sxs-lookup"><span data-stu-id="81625-126">In Teams for Education, a science teacher wants to use a channel to engage students in focused discussions on specific classroom topics.</span></span>

<span data-ttu-id="81625-127">В этом случае преподаватель разрешает преподавателям модерировать канал.</span><span class="sxs-lookup"><span data-stu-id="81625-127">In this scenario, the teacher allows their teaching assistants to moderate the channel.</span></span> <span data-ttu-id="81625-128">После этого помощники могут создавать записи, чтобы начинать обсуждения со студентами и вести их.</span><span class="sxs-lookup"><span data-stu-id="81625-128">The teaching assistants can then create new posts to initiate and drive discussions with students.</span></span>

## <a name="manage-channel-moderation"></a><span data-ttu-id="81625-129">Управление модерированием канала</span><span class="sxs-lookup"><span data-stu-id="81625-129">Manage channel moderation</span></span>

<span data-ttu-id="81625-130">В Teams перейдите в канал и нажмите кнопку **"Дополнительные параметры..."**  >  **Управление каналом.**</span><span class="sxs-lookup"><span data-stu-id="81625-130">In Teams, go to the channel, click **More options ...** > **Manage channel**.</span></span> <span data-ttu-id="81625-131">Здесь вы можете включить и отключить модерацию, добавить участников команды в качестве модераторов и настроить параметры.</span><span class="sxs-lookup"><span data-stu-id="81625-131">From here you can turn on and turn off moderation, add team members as moderators, and set preferences.</span></span>

<span data-ttu-id="81625-132">Модерирование канала — это параметр для каждого канала.</span><span class="sxs-lookup"><span data-stu-id="81625-132">Channel moderation is a per-channel setting.</span></span> <span data-ttu-id="81625-133">Для модерации канала нет параметра на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="81625-133">There's no tenant-level setting for channel moderation.</span></span> <span data-ttu-id="81625-134">Если вы хотите, чтобы мы добавили параметр модерации канала на уровне клиента, запросив его на сайте [UserVoice для Teams.](https://microsoftteams.uservoice.com/)</span><span class="sxs-lookup"><span data-stu-id="81625-134">If you'd like us to add a tenant-level channel moderation setting, request it on [Teams UserVoice](https://microsoftteams.uservoice.com/).</span></span>

![manage-channel-moderation-in-teams-preferences.png](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a><span data-ttu-id="81625-136">Включите или отключите модерацию для канала</span><span class="sxs-lookup"><span data-stu-id="81625-136">Turn on or turn off moderation for a channel</span></span>

<span data-ttu-id="81625-137">По умолчанию модерация отключена, то есть стандартные параметры канала применяются к владельцам и участникам команд.</span><span class="sxs-lookup"><span data-stu-id="81625-137">By default, moderation is off, which means that the usual channel settings apply to team owners and team members.</span></span> <span data-ttu-id="81625-138">Например, можно разрешить только участникам группы, включая гостей, начинать новую публикацию.</span><span class="sxs-lookup"><span data-stu-id="81625-138">For example, you can restrict new posts to only team members or allow everyone, including guests, to start new posts.</span></span>

<span data-ttu-id="81625-139">Чтобы включить модерацию для канала, в области **"Модерирование** канала" выберите **"Включи".**</span><span class="sxs-lookup"><span data-stu-id="81625-139">To turn on moderation for a channel, under **Channel moderation**, click **On**.</span></span> <span data-ttu-id="81625-140">Когда модерация канала уже на этом, только модераторы могут начинать новые записи.</span><span class="sxs-lookup"><span data-stu-id="81625-140">When channel moderation is on, only moderators can start new posts.</span></span> 

### <a name="add-or-remove-channel-moderators"></a><span data-ttu-id="81625-141">Добавление и удаление модераторов каналов</span><span class="sxs-lookup"><span data-stu-id="81625-141">Add or remove channel moderators</span></span>

<span data-ttu-id="81625-142">В **группе "Кто является модераторами?"** **щелкните**"Управление", а затем добавьте или удалите участников группы в качестве модераторов.</span><span class="sxs-lookup"><span data-stu-id="81625-142">Under **Who are the moderators?**, click **Manage**, and then add or remove team members as moderators.</span></span> <span data-ttu-id="81625-143">Владельцы и модераторы команд могут добавлять и удалять других модераторов.</span><span class="sxs-lookup"><span data-stu-id="81625-143">Team owners and moderators can add and remove other moderators.</span></span>  

### <a name="set-team-member-permissions"></a><span data-ttu-id="81625-144">Настройка разрешений участника группы</span><span class="sxs-lookup"><span data-stu-id="81625-144">Set team member permissions</span></span>

<span data-ttu-id="81625-145">В **группе "Разрешения участника группы"** выберите флажки для действий, которые вы хотите разрешить.</span><span class="sxs-lookup"><span data-stu-id="81625-145">Under **Team member permissions**, select the check boxes next to the activities  you want to allow.</span></span>

## <a name="related-topics"></a><span data-ttu-id="81625-146">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="81625-146">Related topics</span></span>

- [<span data-ttu-id="81625-147">Обзор команд и каналов в Teams</span><span class="sxs-lookup"><span data-stu-id="81625-147">Overview of teams and channels in Teams</span></span>](teams-channels-overview.md)
