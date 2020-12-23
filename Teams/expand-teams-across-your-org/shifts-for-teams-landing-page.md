---
title: "\"Смены\" для Teams"
description: Получите руководство администратора, необходимое для создания и управления сменами, средством управления расписанием в Teams.
ms.topic: conceptual
author: lanachin
ms.author: v-lanac
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
ms.openlocfilehash: eea5b36e9941872b5a0dbc4ce34d03b39b850dd3
ms.sourcegitcommit: 43dc627e9fef31a2508f54acf741000551ff68b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2020
ms.locfileid: "48878733"
---
# <a name="shifts-for-teams"></a><span data-ttu-id="cb99c-103">"Смены" для Teams</span><span class="sxs-lookup"><span data-stu-id="cb99c-103">Shifts for Teams</span></span>

<span data-ttu-id="cb99c-104">Teams предоставляет сотрудникам без компьютеров в вашей организации все необходимые инструменты для общения и совместной работы, а также для эффективной работы.</span><span class="sxs-lookup"><span data-stu-id="cb99c-104">Teams gives Firstline Workers in your organization the tools they need to communicate and collaborate effectively and do their best work.</span></span> <span data-ttu-id="cb99c-105">Здесь вы найдете руководство администратора, необходимое для того, чтобы настроить и управлять сменами, инструментом управления расписанием в Teams.</span><span class="sxs-lookup"><span data-stu-id="cb99c-105">Here you'll find the admin guidance you need to set up and manage Shifts, the schedule management tool, in Teams.</span></span>

### <a name="set-up-and-manage-shifts-for-your-organization"></a><span data-ttu-id="cb99c-106">Настройка смен для организации и управление ими</span><span class="sxs-lookup"><span data-stu-id="cb99c-106">Set up and manage Shifts for your organization</span></span>

|               |               |               |               |
| ------------- | ------------- | ------------- | ------------- |
|![task-checklist-planning-teams](../media/task-checklist-planning-teams-small.svg) | <span data-ttu-id="cb99c-108">**[Управление сменами в организации](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams)**</span><span class="sxs-lookup"><span data-stu-id="cb99c-108">**[Manage Shifts in your organization](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams)**</span></span> |![оформление](../media/Help-small.svg)  | <span data-ttu-id="cb99c-110">**[Справка по сменам для сотрудников без телефонов](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Specific_apps)**</span><span class="sxs-lookup"><span data-stu-id="cb99c-110">**[Shifts Help for Firstline Workers](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Specific_apps)**</span></span> |

### <a name="shifts-extensions"></a><span data-ttu-id="cb99c-111">Расширения смен</span><span class="sxs-lookup"><span data-stu-id="cb99c-111">Shifts extensions</span></span>

|               |               |
| ------------- | ------------- |
| ![api](../media/api-small.svg) | <span data-ttu-id="cb99c-113">**[API Shift Graph](/graph/api/resources/shift?view=graph-rest-1.0)** API Shifts Graph позволяют интегрировать данные Shifts с системами управления внешними ресурсами, предоставляя им гибкие возможности для создания пользовательских смен в задней части, предоставляя пользователям богатый, внешний опыт работы в Teams.</span><span class="sxs-lookup"><span data-stu-id="cb99c-113">**[Shift Graph APIs](/graph/api/resources/shift?view=graph-rest-1.0)** Shifts Graph APIs allow you to integrate Shifts data with external workforce management systems, providing you the flexibility to build custom Shifts experiences in the back end, while giving users a rich, front-end experience in Teams.</span></span>             |
| ![api](../media/api-small.svg) | <span data-ttu-id="cb99c-115">**[Интеграция управления трудовыми ресурсами](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors)** Если вы используете сторонние системы управления рабочими ресурсами, например Kronos и JDA, для планирования, планирования, времени и участия, вы можете интегрировать непосредственно с API Shifts Graph и SDK с интеграцией с открытым кодом.</span><span class="sxs-lookup"><span data-stu-id="cb99c-115">**[Workforce management integrations](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors)** If you're using third-party workforce management systems, such as Kronos and JDA, for scheduling, time, and attendance, you can integrate directly with Shifts through Shifts Graph APIs and SDK with open source integrations.</span></span> |
| ![api](../media/process-flow-teams-small.svg) | <span data-ttu-id="cb99c-117">**[Shifts + Power Automate](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** Shifts + Power Automate позволяет принимать данные из Shifts и создавать настраиваемые рабочие процессы с другими приложениями и выполнять операции в масштабе.</span><span class="sxs-lookup"><span data-stu-id="cb99c-117">**[Shifts + Power Automate](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** Shifts + Power Automate lets you take info from Shifts and create custom workflows with other apps and perform operations at scale.</span></span> <span data-ttu-id="cb99c-118">Автоматизировать ключевые процессы практически без кода.</span><span class="sxs-lookup"><span data-stu-id="cb99c-118">Automate key processes with little to no code.</span></span> <span data-ttu-id="cb99c-119">Триггеры и шаблоны поддерживают различные сценарии, например автоматическое утверждение запросов на смену, когда утверждение руководителя не требуется.</span><span class="sxs-lookup"><span data-stu-id="cb99c-119">The triggers and templates support a variety of scenarios such as enabling auto-approvals for shift requests when a manager’s approval isn't needed.</span></span> |

## <a name="featured-training"></a><span data-ttu-id="cb99c-120">Тематическое обучение</span><span class="sxs-lookup"><span data-stu-id="cb99c-120">Featured training</span></span>

|               |               |               |               |               |               |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| ![arrow-right-2-teams](../media/arrow-right-2-teams-small.svg)  |  [<span data-ttu-id="cb99c-122">Видео. Что такое "Смены"?</span><span class="sxs-lookup"><span data-stu-id="cb99c-122">Video: What is Shifts?</span></span>](https://support.office.com/article/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821) |![clock-teams](../media/clock-teams-small.svg)  |  [<span data-ttu-id="cb99c-124">Видео. Что такое "Смены"?</span><span class="sxs-lookup"><span data-stu-id="cb99c-124">Video: What is Shifts?</span></span>](https://support.office.com/article/create-a-shifts-schedule-2b94ca38-36db-4a1c-8fee-f8f0fec9a984) |![blocks-teams](../media/blocks-teams-small.svg)  |  [<span data-ttu-id="cb99c-126">Видео: управление расписанием смен</span><span class="sxs-lookup"><span data-stu-id="cb99c-126">Video: Manage a Shifts schedule</span></span>](https://support.office.com/article/manage-a-shifts-schedule-63acda7b-ea39-441a-b1c6-c404a72e79f7) |
