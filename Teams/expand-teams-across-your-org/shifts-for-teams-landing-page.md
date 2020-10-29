---
title: "\"Смены\" для Teams"
description: В этой статье приведены инструкции для администраторов по настройке и управлению сменами, а также с помощью средства управления планированием в Teams.
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
ms.openlocfilehash: 40e4fea69111ae916457584648fb81d40ea453d7
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790441"
---
# <a name="shifts-for-teams"></a><span data-ttu-id="ae358-103">"Смены" для Teams</span><span class="sxs-lookup"><span data-stu-id="ae358-103">Shifts for Teams</span></span>

<span data-ttu-id="ae358-104">Teams дает сотрудникам Firstline в вашей организации инструменты, необходимые для эффективного общения и совместной работы.</span><span class="sxs-lookup"><span data-stu-id="ae358-104">Teams gives Firstline Workers in your organization the tools they need to communicate and collaborate effectively and do their best work.</span></span> <span data-ttu-id="ae358-105">Здесь вы найдете руководство для администраторов по настройке и управлению сменами, а также с помощью средства управления планированием в Teams.</span><span class="sxs-lookup"><span data-stu-id="ae358-105">Here you'll find the admin guidance you need to set up and manage Shifts, the schedule management tool, in Teams.</span></span>

### <a name="set-up-and-manage-shifts-for-your-organization"></a><span data-ttu-id="ae358-106">Настройка смен и управление ими в Организации</span><span class="sxs-lookup"><span data-stu-id="ae358-106">Set up and manage Shifts for your organization</span></span>

|               |               |               |               |
| ------------- | ------------- | ------------- | ------------- |
|![Контрольный список задачи — планирование: teams](../media/task-checklist-planning-teams-small.svg) | <span data-ttu-id="ae358-108">**[Управление сменами в Организации](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams)**</span><span class="sxs-lookup"><span data-stu-id="ae358-108">**[Manage Shifts in your organization](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams)**</span></span> |![обозначение](../media/Help-small.svg)  | <span data-ttu-id="ae358-110">**[Справка по сменам для Firstline работников](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Specific_apps)**</span><span class="sxs-lookup"><span data-stu-id="ae358-110">**[Shifts Help for Firstline Workers](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Specific_apps)**</span></span> |

### <a name="shifts-extensions"></a><span data-ttu-id="ae358-111">Расширения смен</span><span class="sxs-lookup"><span data-stu-id="ae358-111">Shifts extensions</span></span>

|               |               |
| ------------- | ------------- |
| ![функции](../media/api-small.svg) | <span data-ttu-id="ae358-113">**[API сменной диаграммы](/graph/api/resources/shift?view=graph-rest-1.0)** API-интерфейсы смен предоставляют возможность интеграции смен данных с внешними системами управления трудами, обеспечивая гибкие возможности для создания настраиваемых смен в серверной части, а также для пользователей с богатым и внешним интерфейсом в Teams.</span><span class="sxs-lookup"><span data-stu-id="ae358-113">**[Shift Graph APIs](/graph/api/resources/shift?view=graph-rest-1.0)** Shifts Graph APIs allow you to integrate Shifts data with external workforce management systems, providing you the flexibility to build custom Shifts experiences in the back end, while giving users a rich, front-end experience in Teams.</span></span>             |
| ![функции](../media/api-small.svg) | <span data-ttu-id="ae358-115">**[Интеграция управления ресурсами](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors)** Если вы используете системы управления независимыми производителями, например Kronos и JDA, для планирования, времени и присутствия, вы можете напрямую интегрировать их с помощью перекрывающихся API-интерфейсов и SDK с помощью открытых источников интеграции.</span><span class="sxs-lookup"><span data-stu-id="ae358-115">**[Workforce management integrations](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors)** If you're using third-party workforce management systems, such as Kronos and JDA, for scheduling, time, and attendance, you can integrate directly with Shifts through Shifts Graph APIs and SDK with open source integrations.</span></span> |
| ![функции](../media/process-flow-teams-small.svg) | <span data-ttu-id="ae358-117">**[Сменные клавиши Shift + Power Автоматизация](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** Смену + Power Автоматизация позволяет вам получать информацию из смен и создавать собственные рабочие процессы с другими приложениями и выполнять операции с масштабом.</span><span class="sxs-lookup"><span data-stu-id="ae358-117">**[Shifts + Power Automate](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** Shifts + Power Automate lets you take info from Shifts and create custom workflows with other apps and perform operations at scale.</span></span> <span data-ttu-id="ae358-118">Автоматизация ключевых процессов с минимальным количеством кода.</span><span class="sxs-lookup"><span data-stu-id="ae358-118">Automate key processes with little to no code.</span></span> <span data-ttu-id="ae358-119">Триггеры и шаблоны поддерживают разнообразные сценарии, такие как включение автоматических утверждений для запросов на смену, если не требуется утверждение руководителя.</span><span class="sxs-lookup"><span data-stu-id="ae358-119">The triggers and templates support a variety of scenarios such as enabling auto-approvals for shift requests when a manager’s approval isn't needed.</span></span> |

## <a name="featured-training"></a><span data-ttu-id="ae358-120">Тематическое обучение</span><span class="sxs-lookup"><span data-stu-id="ae358-120">Featured training</span></span>

|               |               |               |               |               |               |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| ![стрелка-права на 2 группы](../media/arrow-right-2-teams-small.svg)  |  [<span data-ttu-id="ae358-122">Видео: что такое смены?</span><span class="sxs-lookup"><span data-stu-id="ae358-122">Video: What is Shifts?</span></span>](https://support.office.com/article/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821) |![Часы — Teams](../media/clock-teams-small.svg)  |  [<span data-ttu-id="ae358-124">Видео: что такое смены?</span><span class="sxs-lookup"><span data-stu-id="ae358-124">Video: What is Shifts?</span></span>](https://support.office.com/article/create-a-shifts-schedule-2b94ca38-36db-4a1c-8fee-f8f0fec9a984) |![блоки — группы](../media/blocks-teams-small.svg)  |  [<span data-ttu-id="ae358-126">Видео: управление расписанием смен</span><span class="sxs-lookup"><span data-stu-id="ae358-126">Video: Manage a Shifts schedule</span></span>](https://support.office.com/article/manage-a-shifts-schedule-63acda7b-ea39-441a-b1c6-c404a72e79f7) |
