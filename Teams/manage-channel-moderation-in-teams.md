---
title: Настройка и управление управлением каналами
author: lanachin
ms.author: v-lanac
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
description: Сведения о настройке каналов для контроля в Microsoft Teams, в том числе о том, как добавлять участников группы в качестве модераторов каналов.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 128676bbe4ec27300013836425bf221e3de10f9b
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/03/2020
ms.locfileid: "43136809"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a><span data-ttu-id="34703-103">Настройка и управление управлением каналами в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="34703-103">Set up and manage channel moderation in Microsoft Teams</span></span>

<span data-ttu-id="34703-104">В Microsoft Teams владельцы групп могут включать для канала контрольные записи, чтобы управлять тем, кто может создавать новые сообщения и отвечать на них в канале.</span><span class="sxs-lookup"><span data-stu-id="34703-104">In Microsoft Teams, team owners can turn on moderation for a channel to control who can start new posts and reply to posts in that channel.</span></span>

<span data-ttu-id="34703-105">Владельцы групп могут также добавлять участников группы в качестве модераторов.</span><span class="sxs-lookup"><span data-stu-id="34703-105">Team owners can also add team members as moderators.</span></span> <span data-ttu-id="34703-106">Владелец команды может не получить эксперта в предметной области на уровне канала, чтобы обеспечить поддержку обслуживания каналов.</span><span class="sxs-lookup"><span data-stu-id="34703-106">A team owner might not have the subject matter expertise at the channel level to best support channel moderation.</span></span> <span data-ttu-id="34703-107">Разрешая определенным членам группы умеренный канал, ответственность за управление содержимым и контекстом в канале осуществляется между владельцами групп и модераторами каналов.</span><span class="sxs-lookup"><span data-stu-id="34703-107">By allowing specific team members to moderate a channel, the responsibility of managing content and context within a channel is shared between team owners and channel moderators.</span></span> <span data-ttu-id="34703-108">Например, владелец группы может добавить в качестве модераторов владельцам и владельцам содержимого, что позволяет им управлять обменом данными в этом канале.</span><span class="sxs-lookup"><span data-stu-id="34703-108">For example, a team owner can add business owners or content owners as moderators, which lets them control information sharing in that channel.</span></span>

## <a name="what-can-a-channel-moderator-do"></a><span data-ttu-id="34703-109">Что может сделать Модератор канала?</span><span class="sxs-lookup"><span data-stu-id="34703-109">What can a channel moderator do?</span></span>

<span data-ttu-id="34703-110">Модераторы каналов могут:</span><span class="sxs-lookup"><span data-stu-id="34703-110">Channel moderators can:</span></span>

- <span data-ttu-id="34703-111">Начните новые сообщения в канале.</span><span class="sxs-lookup"><span data-stu-id="34703-111">Start new posts in the channel.</span></span> <span data-ttu-id="34703-112">Если для канала включена возможность включения, только модераторы могут создавать новые сообщения в этом канале.</span><span class="sxs-lookup"><span data-stu-id="34703-112">When moderation is turned on for a channel, only moderators can start new posts in that channel.</span></span>
- <span data-ttu-id="34703-113">Добавляйте и удаляйте участников группы в канале в качестве модераторов.</span><span class="sxs-lookup"><span data-stu-id="34703-113">Add and remove team members as moderators to a channel.</span></span> <span data-ttu-id="34703-114">Имейте в виду, что по умолчанию владельцам групп являются модераторы канала и их нельзя удалить.</span><span class="sxs-lookup"><span data-stu-id="34703-114">Keep in mind that by default, team owners are channel moderators and can't be removed.</span></span>
- <span data-ttu-id="34703-115">Управлять тем, могут ли участники команд отвечать на существующие сообщения, а также могут ли ботов и соединители отправлять сообщения в каналах.</span><span class="sxs-lookup"><span data-stu-id="34703-115">Control whether team members can reply to existing channel messages and whether bots and connectors can submit channel messages.</span></span>

## <a name="scenarios"></a><span data-ttu-id="34703-116">Scenarios</span><span class="sxs-lookup"><span data-stu-id="34703-116">Scenarios</span></span>

<span data-ttu-id="34703-117">Вот несколько примеров того, как ваша организация может использовать в Teams контроль каналов.</span><span class="sxs-lookup"><span data-stu-id="34703-117">Here's some examples of how your organization can use channel moderation in Teams.</span></span>

### <a name="use-a-channel-as-an-announcement-channel"></a><span data-ttu-id="34703-118">Использование канала в качестве канала объявления</span><span class="sxs-lookup"><span data-stu-id="34703-118">Use a channel as an announcement channel</span></span>

<span data-ttu-id="34703-119">Группа маркетинга использует конкретный канал для совместного использования основных объявлений проекта и конечных результатов.</span><span class="sxs-lookup"><span data-stu-id="34703-119">The Marketing team uses a specific channel to share key project announcements and deliverables.</span></span> <span data-ttu-id="34703-120">Иногда участники команды размещает в канале содержимое, которое более подходящим образом входит в другие каналы.</span><span class="sxs-lookup"><span data-stu-id="34703-120">Sometimes team members post content to the channel that more appropriately belongs in other channels.</span></span> <span data-ttu-id="34703-121">Владелец группы хочет ограничить общий доступ к данным в канале только объявлениям, чтобы участники группы могли использовать этот канал, чтобы всегда быть в курсе важных событий.</span><span class="sxs-lookup"><span data-stu-id="34703-121">The team owner wants to restrict information sharing in the channel to only announcements so that team members can use that channel to stay on top of what's important.</span></span>

<span data-ttu-id="34703-122">В этом случае владелец группы добавляет в качестве модераторов маркетинговые интересы, чтобы они могли публиковать объявления в канале и отключать возможность для участников группы отвечать на сообщения в этом канале.</span><span class="sxs-lookup"><span data-stu-id="34703-122">In this scenario, the team owner adds Marketing leads as moderators so they can post announcements in the channel and turns off the ability for team members to reply to messages in that channel.</span></span>

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a><span data-ttu-id="34703-123">Использование канала для обсуждений занятий в Teams для образовательных учреждений</span><span class="sxs-lookup"><span data-stu-id="34703-123">Use a channel for class discussions in Teams for Education</span></span>

<span data-ttu-id="34703-124">В Teams для образовательных учреждений для образования в разделе "вопросы и маркетинг", предназначенных для студентов, нужно использовать канал для привлечение учащихся.</span><span class="sxs-lookup"><span data-stu-id="34703-124">In Teams for Education, a science teacher want to use a channel to engage students in focused discussions on specific classroom topics.</span></span>

<span data-ttu-id="34703-125">В этом случае преподаватель позволяет обучающимся помощникам получить канал на среднем.</span><span class="sxs-lookup"><span data-stu-id="34703-125">In this scenario, the teacher allows their teaching assistants to moderate the channel.</span></span> <span data-ttu-id="34703-126">Помощники по обучению могут затем создавать новые записи для начала и обсуждения обсуждений учащихся.</span><span class="sxs-lookup"><span data-stu-id="34703-126">The teaching assistants can then create new posts to initiate and drive discussions with students.</span></span>

## <a name="manage-channel-moderation"></a><span data-ttu-id="34703-127">Управление управлением каналами</span><span class="sxs-lookup"><span data-stu-id="34703-127">Manage channel moderation</span></span>

<span data-ttu-id="34703-128">В Teams перейдите в канал и нажмите кнопку **Дополнительные параметры...**  >  **Управление каналом**.</span><span class="sxs-lookup"><span data-stu-id="34703-128">In Teams, go to the channel, click **More options ...** > **Manage channel**.</span></span> <span data-ttu-id="34703-129">Здесь вы можете включить и отключить отображение, добавить участников группы в качестве модераторов и настроить настройки.</span><span class="sxs-lookup"><span data-stu-id="34703-129">From here you can turn on and turn off moderation, add team members as moderators, and set preferences.</span></span>

<span data-ttu-id="34703-130">Контроль каналов — это настройка по каналам.</span><span class="sxs-lookup"><span data-stu-id="34703-130">Channel moderation is a per-channel setting.</span></span> <span data-ttu-id="34703-131">На уровне клиента отсутствует параметр для контроля каналов.</span><span class="sxs-lookup"><span data-stu-id="34703-131">There's no tenant-level setting for channel moderation.</span></span> <span data-ttu-id="34703-132">Если вы хотите, чтобы мы хотели добавить параметр для контроля канала на уровне клиента, запросите его в [Teams UserVoice](https://microsoftteams.uservoice.com/).</span><span class="sxs-lookup"><span data-stu-id="34703-132">If you'd like us to add a tenant-level channel moderation setting, request it on [Teams UserVoice](https://microsoftteams.uservoice.com/).</span></span>

![Manage-Channel-moderation-in-Teams-Preferences. png](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a><span data-ttu-id="34703-134">Включение и отключение контроля для канала</span><span class="sxs-lookup"><span data-stu-id="34703-134">Turn on or turn off moderation for a channel</span></span>

<span data-ttu-id="34703-135">По умолчанию контроль отключен, что означает, что стандартные параметры канала применяются к владельцам групп и участникам группы.</span><span class="sxs-lookup"><span data-stu-id="34703-135">By default, moderation is off, which means that the usual channel settings apply to team owners and team members.</span></span> <span data-ttu-id="34703-136">Например, вы можете ограничить создание записей только для участников группы или разрешить всем, в том числе гостей, начать новую запись.</span><span class="sxs-lookup"><span data-stu-id="34703-136">For example, you can restrict new posts to only team members or allow everyone, including guests, to start new posts.</span></span>

<span data-ttu-id="34703-137">Чтобы включить контроль для канала, в разделе "контроль **каналов**" щелкните **вкл**.</span><span class="sxs-lookup"><span data-stu-id="34703-137">To turn on moderation for a channel, under **Channel moderation**, click **On**.</span></span> <span data-ttu-id="34703-138">Если включено контроль каналов, только модераторы могут создавать новые записи.</span><span class="sxs-lookup"><span data-stu-id="34703-138">When channel moderation is on, only moderators can start new posts.</span></span> 

### <a name="add-or-remove-channel-moderators"></a><span data-ttu-id="34703-139">Добавление и удаление модераторов каналов</span><span class="sxs-lookup"><span data-stu-id="34703-139">Add or remove channel moderators</span></span>

<span data-ttu-id="34703-140">В разделе **кто является модератором?** щелкните **Управление**, а затем добавьте или удалите участников группы в качестве модераторов.</span><span class="sxs-lookup"><span data-stu-id="34703-140">Under **Who are the moderators?**, click **Manage**, and then add or remove team members as moderators.</span></span> <span data-ttu-id="34703-141">Владельцы групп и модераторы могут добавлять и удалять других модераторов.</span><span class="sxs-lookup"><span data-stu-id="34703-141">Team owners and moderators can add and remove other moderators.</span></span>  

### <a name="set-team-member-permissions"></a><span data-ttu-id="34703-142">Настройка разрешений для участников группы</span><span class="sxs-lookup"><span data-stu-id="34703-142">Set team member permissions</span></span>

<span data-ttu-id="34703-143">В разделе **разрешения участников группы**установите флажки рядом с действиями, которые вы хотите разрешить.</span><span class="sxs-lookup"><span data-stu-id="34703-143">Under **Team member permissions**, select the check boxes next to the activities  you want to allow.</span></span>

## <a name="related-topics"></a><span data-ttu-id="34703-144">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="34703-144">Related topics</span></span>

- [<span data-ttu-id="34703-145">Обзор команд и каналов в Teams</span><span class="sxs-lookup"><span data-stu-id="34703-145">Overview of teams and channels in Teams</span></span>](teams-channels-overview.md)
