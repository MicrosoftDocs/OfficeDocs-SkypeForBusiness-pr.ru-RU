---
title: Управление политиками событий в реальном времени в группах
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sonua
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.liveevents.policies
description: Сведения о политиках событий в реальном времени группы и как их использовать для управления параметрами для пользователей в вашей организации, хранение событий в реальном времени.
ms.openlocfilehash: b02f8de8accd0baff5f87af8682eab486866acb5
ms.sourcegitcommit: 6447a3aa060452c8d6879524cd6a56aecf33b152
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2018
ms.locfileid: "25354350"
---
# <a name="manage-live-events-policies-in-teams"></a><span data-ttu-id="26af4-103">Управление политиками событий в реальном времени в группах</span><span class="sxs-lookup"><span data-stu-id="26af4-103">Manage live events policies in Teams</span></span>

<span data-ttu-id="26af4-104">Политики событий в реальном времени группы используются для управления кто в организации может содержать событий в реальном времени и функциональные возможности, доступные в события, которые они создают.</span><span class="sxs-lookup"><span data-stu-id="26af4-104">Teams live events policies are used to control who in your organization can hold live events and the features that are available in the events that they create.</span></span> <span data-ttu-id="26af4-105">После создания политики назначения ее пользователям или группам пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="26af4-105">After you create a policy, assign it to a user or groups of users in your organization.</span></span> 

- <span data-ttu-id="26af4-106">**Имя** Это имя политики, которая отображается на странице политик событий в реальном времени.</span><span class="sxs-lookup"><span data-stu-id="26af4-106">**Name** This is the name of the policy that appears on the live events policies page.</span></span> <span data-ttu-id="26af4-107">Не может превышать 64 символов или иметь специальные символы.</span><span class="sxs-lookup"><span data-stu-id="26af4-107">It can't be longer than 64 characters or have any special characters.</span></span>  
- <span data-ttu-id="26af4-108">**Описание** Используется для добавления понятное описание политики.</span><span class="sxs-lookup"><span data-stu-id="26af4-108">**Description** Use this to add a friendly description for the policy.</span></span> 
- <span data-ttu-id="26af4-109">**Разрешить планирование** Для включения это позволяет пользователям в организации Создание и планирование live события в группах.</span><span class="sxs-lookup"><span data-stu-id="26af4-109">**Allow scheduling** Turning this on lets users in your organization create and schedule live events in Teams.</span></span>  
- <span data-ttu-id="26af4-110">**Разрешить транскрибирования участников** Для включения это позволяет участникам live события для просмотра в режиме реального времени подписи и перевода во время события.</span><span class="sxs-lookup"><span data-stu-id="26af4-110">**Allow transcription for attendees** Turning this on enables live event attendees to see real-time captions and translation during the event.</span></span> 
- <span data-ttu-id="26af4-111">**Пользователей, которые могут присоединиться к расписанию событий в реальном времени**</span><span class="sxs-lookup"><span data-stu-id="26af4-111">**Who can join scheduled live events**</span></span>
    - <span data-ttu-id="26af4-112">**Всем пользователям** Пользователи могут создавать live события, которые все, включая людей за пределами вашей организации, могут посетить.</span><span class="sxs-lookup"><span data-stu-id="26af4-112">**Everyone** Users can create live events that everyone, including people outside your organization, can attend.</span></span>  
    - <span data-ttu-id="26af4-113">**Всем пользователям в организации** Пользователи могут создавать live события, которые могут присутствовать только пользователи в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="26af4-113">**Everyone in the organization** Users can create live events that only people in your organization can attend.</span></span> 
    - <span data-ttu-id="26af4-114">**Определенных пользователей или групп** Пользователи могут создавать событий в реальном времени, только определенным пользователям или группам в организации могут посещение.</span><span class="sxs-lookup"><span data-stu-id="26af4-114">**Specific users or groups** Users can create live events that only specific users or groups in your organization can attend.</span></span> 
- <span data-ttu-id="26af4-115">**Параметры записи** Этот параметр может применяться только к live события, которые создаются с помощью команды собраний, также известной как краткое событий в реальном времени.</span><span class="sxs-lookup"><span data-stu-id="26af4-115">**Recording setting** This setting can only be applied to live events that are produced using Teams meetings, also known as quick start live events.</span></span>  
    - <span data-ttu-id="26af4-116">**Запишите всегда** Всегда записываются live события, созданные пользователями.</span><span class="sxs-lookup"><span data-stu-id="26af4-116">**Always record** The live events created by users are always recorded.</span></span> <span data-ttu-id="26af4-117">После события, участники группы событий можно загрузить записи и участников можно отслеживать события.</span><span class="sxs-lookup"><span data-stu-id="26af4-117">After the event is over, event team members can download the recording and attendees can watch the event.</span></span> 
    - <span data-ttu-id="26af4-118">**Запишите никогда** Никогда не записываются live события, созданные пользователями.</span><span class="sxs-lookup"><span data-stu-id="26af4-118">**Never record** The live events created by users are never recorded.</span></span>
    - <span data-ttu-id="26af4-119">**Организатор можно записать или нет** Пользователи могут принять решение о записи live события.</span><span class="sxs-lookup"><span data-stu-id="26af4-119">**Organizer can record or not** Users can decide whether to record the live event.</span></span> <span data-ttu-id="26af4-120">Если он записан, после события, участники группы событий можно загрузить записи и участников можно отслеживать события.</span><span class="sxs-lookup"><span data-stu-id="26af4-120">If it is recorded, after the event is over, event team members can download the recording and attendees can watch the event.</span></span> 

 ### <a name="related-topics"></a><span data-ttu-id="26af4-121">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="26af4-121">Related topics</span></span>
- [<span data-ttu-id="26af4-122">Что такое группы live событий?</span><span class="sxs-lookup"><span data-stu-id="26af4-122">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="26af4-123">Планирование групп событий в реальном времени</span><span class="sxs-lookup"><span data-stu-id="26af4-123">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="26af4-124">Настройка для групп событий в реальном времени</span><span class="sxs-lookup"><span data-stu-id="26af4-124">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
- [<span data-ttu-id="26af4-125">Настройка групп событий в реальном времени</span><span class="sxs-lookup"><span data-stu-id="26af4-125">Configure Teams live events</span></span>](configure-teams-live-events.md)
