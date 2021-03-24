---
title: "\"Смены\" для Teams"
description: Получите руководство администратора, необходимое для создания и управления сменами, средством управления расписанием в Teams.
ms.topic: conceptual
author: cichur
ms.author: v-cichur
audience: admin
manager: serdars
f1.keywords:
- NOCSH
ms.date: 03/29/2019
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 889c3f4149489f6bcea44acde93d897a7f2e50e1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092557"
---
# <a name="shifts-for-teams"></a><span data-ttu-id="92a60-103">"Смены" для Teams</span><span class="sxs-lookup"><span data-stu-id="92a60-103">Shifts for Teams</span></span>

<span data-ttu-id="92a60-104">Teams предоставляет сотрудникам, работающим с телефонной связью, инструменты, необходимые для общения и эффективной совместной работы.</span><span class="sxs-lookup"><span data-stu-id="92a60-104">Teams gives Frontline Workers in your organization the tools they need to communicate and collaborate effectively.</span></span> <span data-ttu-id="92a60-105">В этой статье показано, как настроить их и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="92a60-105">This article shows you how to set up and manage.</span></span> <span data-ttu-id="92a60-106">Смены и использование средства управления расписанием в Teams.</span><span class="sxs-lookup"><span data-stu-id="92a60-106">Shifts and use the schedule management tool in Teams.</span></span>

### <a name="set-up-and-manage-shifts-for-your-organization"></a><span data-ttu-id="92a60-107">Настройка смен и управление ими в организации</span><span class="sxs-lookup"><span data-stu-id="92a60-107">Set up and manage Shifts for your organization</span></span>

|               |               |               |               |
| ------------- | ------------- | ------------- | ------------- |
|![task-checklist-planning-teams](../media/task-checklist-planning-teams-small.svg) | <span data-ttu-id="92a60-109">**[Управление сменами в организации](./shifts/manage-the-shifts-app-for-your-organization-in-teams.md)**</span><span class="sxs-lookup"><span data-stu-id="92a60-109">**[Manage Shifts in your organization](./shifts/manage-the-shifts-app-for-your-organization-in-teams.md)**</span></span> |![дизайн](../media/Help-small.svg)  | <span data-ttu-id="92a60-111">**[Справка по Сменам для сотрудников без компьютеров](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Specific_apps)**</span><span class="sxs-lookup"><span data-stu-id="92a60-111">**[Shifts Help for Frontline Workers](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Specific_apps)**</span></span> |

### <a name="shifts-extensions"></a><span data-ttu-id="92a60-112">Расширения смен</span><span class="sxs-lookup"><span data-stu-id="92a60-112">Shifts extensions</span></span>

|               |               |
| ------------- | ------------- |
| ![api](../media/api-small.svg) | <span data-ttu-id="92a60-114">**[API Shift Graph](/graph/api/resources/shift?view=graph-rest-1.0)** API Shifts Graph позволяют интегрировать данные Shifts с системами управления внешними ресурсами.</span><span class="sxs-lookup"><span data-stu-id="92a60-114">**[Shift Graph APIs](/graph/api/resources/shift?view=graph-rest-1.0)** Shifts Graph APIs allow you to integrate Shifts data with external workforce management systems.</span></span> <span data-ttu-id="92a60-115">Вы сможете создавать пользовательские смены на задней панели, одновременно предоставляя пользователям богатый и стойкий опыт работы в Teams.</span><span class="sxs-lookup"><span data-stu-id="92a60-115">You'll have the flexibility to build custom Shifts experiences in the back end, while giving users a rich, front-end experience in Teams.</span></span>             |
| ![api](../media/api-small.svg) | <span data-ttu-id="92a60-117">**[Интеграция управления трудовыми ресурсами](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors)** Если вы используете сторонние системы управления рабочими ресурсами, например Kronos и JDA, для планирования, планирования, времени и участия, вы можете интегрировать непосредственно с Shifts через API Shifts Graph и SDK с интеграцией с открытым кодом.</span><span class="sxs-lookup"><span data-stu-id="92a60-117">**[Workforce management integrations](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors)** If you're using third-party workforce management systems, such as Kronos and JDA, for scheduling, time, and attendance, you can integrate directly with Shifts through Shifts Graph APIs and SDK with open source integrations.</span></span> |
| ![api](../media/process-flow-teams-small.svg) | <span data-ttu-id="92a60-119">**[Shifts + Power Automate](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** Shifts + Power Automate позволяет принимать данные из Shifts и создавать настраиваемые рабочие процессы с другими приложениями и выполнять операции в масштабе.</span><span class="sxs-lookup"><span data-stu-id="92a60-119">**[Shifts + Power Automate](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** Shifts + Power Automate lets you take info from Shifts and create custom workflows with other apps and perform operations at scale.</span></span> <span data-ttu-id="92a60-120">Автоматизировать ключевые процессы практически без кода.</span><span class="sxs-lookup"><span data-stu-id="92a60-120">Automate key processes with little to no code.</span></span> <span data-ttu-id="92a60-121">Триггеры и шаблоны поддерживают различные сценарии, например автоматическое утверждение запросов на смену, когда утверждение руководителя не требуется.</span><span class="sxs-lookup"><span data-stu-id="92a60-121">The triggers and templates support a variety of scenarios such as enabling auto-approvals for shift requests when a manager’s approval isn't needed.</span></span> |

## <a name="featured-training"></a><span data-ttu-id="92a60-122">Тематическое обучение</span><span class="sxs-lookup"><span data-stu-id="92a60-122">Featured training</span></span>

|               |               |               |               |               |               |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| ![arrow-right-2-teams](../media/arrow-right-2-teams-small.svg)  |  [<span data-ttu-id="92a60-124">Видео. Что такое "Смены"?</span><span class="sxs-lookup"><span data-stu-id="92a60-124">Video: What is Shifts?</span></span>](https://support.office.com/article/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821) |![clock-teams](../media/clock-teams-small.svg)  |  [<span data-ttu-id="92a60-126">Видео. Что такое "Смены"?</span><span class="sxs-lookup"><span data-stu-id="92a60-126">Video: What is Shifts?</span></span>](https://support.office.com/article/create-a-shifts-schedule-2b94ca38-36db-4a1c-8fee-f8f0fec9a984) |![blocks-teams](../media/blocks-teams-small.svg)  |  [<span data-ttu-id="92a60-128">Видео: управление расписанием смен</span><span class="sxs-lookup"><span data-stu-id="92a60-128">Video: Manage a Shifts schedule</span></span>](https://support.office.com/article/manage-a-shifts-schedule-63acda7b-ea39-441a-b1c6-c404a72e79f7) |