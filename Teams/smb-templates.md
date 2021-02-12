---
title: Шаблоны Teams для малого и среднего бизнеса, встроенные с помощью Microsoft Graph
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.reviewer: lavenkat
description: Используйте встроенные шаблоны Microsoft Teams, встроенные в Microsoft Graph, чтобы быстро и легко создавать команды для малого и среднего бизнеса.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7196dd93fc1245102a333c150715c4b4570986c7
ms.sourcegitcommit: 340c2f432b78af4e78b21056af56c6421627045d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294555"
---
# <a name="teams-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a><span data-ttu-id="33279-103">Шаблоны Teams, встроенные в Microsoft Graph для малого и среднего бизнеса</span><span class="sxs-lookup"><span data-stu-id="33279-103">Teams templates built in Microsoft Graph for Small and Medium Businesses</span></span>

<span data-ttu-id="33279-104">Шаблоны Microsoft Teams позволяют быстро и легко создавать команды, предоставляя предопределяющий шаблон настроек, каналов и предварительно установленных приложений.</span><span class="sxs-lookup"><span data-stu-id="33279-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="33279-105">Шаблоны для малого и среднего бизнеса особенно мощны, так как они помогают администраторам быстро развернуть Teams в своей организации.</span><span class="sxs-lookup"><span data-stu-id="33279-105">For small and medium businesses, templates can be especially powerful, as they help administrators to quickly deploy Teams across their organization.</span></span> <span data-ttu-id="33279-106">Шаблоны также помогают сориентировать пользователей и эффективно использовать Teams.</span><span class="sxs-lookup"><span data-stu-id="33279-106">Templates also help orient users and get started with using Teams effectively.</span></span> <span data-ttu-id="33279-107">Эта статья для вас, если вы отвечаете за планирование, развертывание и управление несколькими командами в организации.</span><span class="sxs-lookup"><span data-stu-id="33279-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your organization.</span></span>

<span data-ttu-id="33279-108">В настоящее время мы предлагаем три шаблона для работы с МБ, которые можно использовать в различных ситуациях.</span><span class="sxs-lookup"><span data-stu-id="33279-108">We currently offer three first-party SMB templates that you can leverage for a variety of situations.</span></span> <span data-ttu-id="33279-109">Все шаблоны будут создавать *закрытые* команды.</span><span class="sxs-lookup"><span data-stu-id="33279-109">All templates will create *Private* Teams.</span></span> <span data-ttu-id="33279-110">Создав Teams и готов к его распространению в своей организации,  вы можете установить для нее конфиденциальность как для всей *организации,* так и для всех ее пользователей.</span><span class="sxs-lookup"><span data-stu-id="33279-110">Once you have created the Teams and are ready to roll out to your organization, you can set the privacy to *Org-Wide* or *Public*, as appropriate.</span></span> <span data-ttu-id="33279-111">Подробнее о шаблонах команд см. в шаблонах [Teams.](get-started-with-teams-templates.md)</span><span class="sxs-lookup"><span data-stu-id="33279-111">To learn more about team templates in general, see [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="company-wide-template"></a><span data-ttu-id="33279-112">Company-Wide шаблона</span><span class="sxs-lookup"><span data-stu-id="33279-112">Company-Wide template</span></span>
<span data-ttu-id="33279-113">Шаблон Company-Wide предназначен для общения и совместной работы, которые важны для всей компании.</span><span class="sxs-lookup"><span data-stu-id="33279-113">The Company-Wide template is meant for communication and collaboration that are relevant for the entire company.</span></span> <span data-ttu-id="33279-114">Канал "Общий" можно использовать для объявлений, отраслевых новостей и записей руководителей.</span><span class="sxs-lookup"><span data-stu-id="33279-114">You can use the General channel for company-wide announcements, industry news or executive posts.</span></span> <span data-ttu-id="33279-115">Канал управления персоналом — это отличное место для консолидации всех действий, связанных с персоналом, таких как вакансии, подготовка новых сотрудников, обучение и разработка.</span><span class="sxs-lookup"><span data-stu-id="33279-115">The Human Resources channel is a great place to consolidate all HR-related activities like job posts, new employee onboarding, training, and development.</span></span> <span data-ttu-id="33279-116">Канал Fun Stuff предоставляет социальную платформу для всех случайных и забавных записей.</span><span class="sxs-lookup"><span data-stu-id="33279-116">The Fun Stuff channel provides a social platform for all random and fun posts.</span></span>

| <span data-ttu-id="33279-117">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="33279-117">Base template type</span></span>  | <span data-ttu-id="33279-118">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="33279-118">baseTemplateId</span></span> | <span data-ttu-id="33279-119">Свойства, которые доступны с этим базовым шаблоном</span><span class="sxs-lookup"><span data-stu-id="33279-119">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="33279-120">SMB -</span><span class="sxs-lookup"><span data-stu-id="33279-120">SMB -</span></span> <br><span data-ttu-id="33279-121">Во всей организации</span><span class="sxs-lookup"><span data-stu-id="33279-121">Company-wide</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| <span data-ttu-id="33279-122">Каналы</span><span class="sxs-lookup"><span data-stu-id="33279-122">Channels</span></span> <ul><li><span data-ttu-id="33279-123">Общий\*</span><span class="sxs-lookup"><span data-stu-id="33279-123">General\*</span></span></li><li><span data-ttu-id="33279-124">Человеческие ресурсы\*</span><span class="sxs-lookup"><span data-stu-id="33279-124">Human Resources\*</span></span></li><li><span data-ttu-id="33279-125">Забавные материалы\*</span><span class="sxs-lookup"><span data-stu-id="33279-125">Fun Stuff\*</span></span></li></ul><br> <span data-ttu-id="33279-126">Приложения</span><span class="sxs-lookup"><span data-stu-id="33279-126">Apps</span></span><ul><li><span data-ttu-id="33279-127">Портал компании (веб-сайт закреплен в **канале "Кадры")**</span><span class="sxs-lookup"><span data-stu-id="33279-127">Company Portal (Website pinned to the **Human Resources** channel)</span></span> </li> </UL><br><span data-ttu-id="33279-128">Свойства группы</span><span class="sxs-lookup"><span data-stu-id="33279-128">Team properties</span></span> <ul><li><span data-ttu-id="33279-129">Видимость группы : "Частная"</span><span class="sxs-lookup"><span data-stu-id="33279-129">Team visibility set to Private</span></span></li></ul> |

<span data-ttu-id="33279-130">\* Автоматически избранные каналы</span><span class="sxs-lookup"><span data-stu-id="33279-130">\*Auto-favorited channels</span></span> 

<span data-ttu-id="33279-131">Чтобы создать команду Company-Wide, принимая значения по умолчанию из предварительно определенного шаблона, предопределйте представление JSON объекта группы в теле запроса.</span><span class="sxs-lookup"><span data-stu-id="33279-131">To create the Company-Wide team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="33279-132">Дополнительные информацию о развертывании шаблонов Teams см. в статье Microsoft Graph [о создании команды.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="33279-132">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="33279-133">Запрос</span><span class="sxs-lookup"><span data-stu-id="33279-133">Request</span></span> 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessOrgWide')",
    "displayName": "Org-wide",
    "description": "All posts that are relevant for entire company (e.g. Company-wide announcements, Exec posts, employee poll/feedback).",
    "visibility": "Private"
}
```

## <a name="executive-team-template"></a><span data-ttu-id="33279-134">Шаблон "Группа руководителей"</span><span class="sxs-lookup"><span data-stu-id="33279-134">Executive Team template</span></span>

<span data-ttu-id="33279-135">Шаблон "Группа руководителей" идеально подходит для того, чтобы создать команду для руководителей компании, чтобы общаться и совместно работать над корпоративными инициативами, например ежегодными приоритетами, финансовыми бюджетами, стратегическими инициативами и лучшими клиентами.</span><span class="sxs-lookup"><span data-stu-id="33279-135">The Executive Team template is ideal for creating a team for company executives to communicate and collaborate on company initiatives like annual priorities, fiscal budgets, strategic initiatives, and top clients.</span></span> <span data-ttu-id="33279-136">Этот шаблон поставляется с *закрытым каналом,* чтобы пригласить пользователей на определенные темы.</span><span class="sxs-lookup"><span data-stu-id="33279-136">This template comes with a *Private* channel to invite select users for specific topics.</span></span>

| <span data-ttu-id="33279-137">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="33279-137">Base template type</span></span>  | <span data-ttu-id="33279-138">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="33279-138">baseTemplateId</span></span> | <span data-ttu-id="33279-139">Свойства, которые доступны с этим базовым шаблоном</span><span class="sxs-lookup"><span data-stu-id="33279-139">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="33279-140">SMB -</span><span class="sxs-lookup"><span data-stu-id="33279-140">SMB -</span></span> <br><span data-ttu-id="33279-141">Группа руководителей</span><span class="sxs-lookup"><span data-stu-id="33279-141">Executives Team</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | <span data-ttu-id="33279-142">Каналы</span><span class="sxs-lookup"><span data-stu-id="33279-142">Channels</span></span> <ul><li><span data-ttu-id="33279-143">Общий\*</span><span class="sxs-lookup"><span data-stu-id="33279-143">General\*</span></span></li><li><span data-ttu-id="33279-144">Частное \*</span><span class="sxs-lookup"><span data-stu-id="33279-144">Private \*</span></span></li></ul> <span data-ttu-id="33279-145">Приложения</span><span class="sxs-lookup"><span data-stu-id="33279-145">Apps</span></span><ul><li><span data-ttu-id="33279-146">OneNote (закреплен на частном **канале)**</span><span class="sxs-lookup"><span data-stu-id="33279-146">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="33279-147">Планировщик (закреплен в частном **канале)**</span><span class="sxs-lookup"><span data-stu-id="33279-147">Planner (pinned to the **Private** channel)</span></span> </li></ul><br><span data-ttu-id="33279-148">Свойства группы</span><span class="sxs-lookup"><span data-stu-id="33279-148">Team properties</span></span> <ul><li><span data-ttu-id="33279-149">Видимость группы : "Частная"</span><span class="sxs-lookup"><span data-stu-id="33279-149">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="33279-150">\* Автоматически избранные каналы</span><span class="sxs-lookup"><span data-stu-id="33279-150">\*Auto-favorited channels</span></span><br>

<span data-ttu-id="33279-151">Чтобы создать команду руководителей, принимая значения по умолчанию из предварительно определенного шаблона, предопределйте представление JSON объекта группы в теле запроса.</span><span class="sxs-lookup"><span data-stu-id="33279-151">To create the Executives team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="33279-152">Дополнительные информацию о развертывании шаблонов Teams см. в статье Microsoft Graph [о создании команды.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="33279-152">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="33279-153">Запрос</span><span class="sxs-lookup"><span data-stu-id="33279-153">Request</span></span> 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessExecutive')",
    "displayName": "Executive",
    "description": "All posts, announcements and daily collaboration and communication for the company's leadership team.",
    "visibility": "Private"
}
```

## <a name="departmental-team-template"></a><span data-ttu-id="33279-154">Шаблон команды отдела</span><span class="sxs-lookup"><span data-stu-id="33279-154">Departmental Team template</span></span>

<span data-ttu-id="33279-155">Шаблон команды "Отдел" можно использовать для создания команды для отдельных отделов или проектов.</span><span class="sxs-lookup"><span data-stu-id="33279-155">The Departmental team template can be used for creating a team for individual departments or for projects.</span></span> <span data-ttu-id="33279-156">Шаблон финансового группы идеально подходит для публикаций, объявлений, ежедневной совместной работы и общения в финансовом коллективе и руководителей.</span><span class="sxs-lookup"><span data-stu-id="33279-156">The Finance team template is ideal for all posts, announcements, and daily collaboration and communication within the Finance team members and executive team members as appropriate.</span></span> <span data-ttu-id="33279-157">Шаблон поставляется с *закрытым* каналом, чтобы пригласить пользователей на определенные темы.</span><span class="sxs-lookup"><span data-stu-id="33279-157">The template comes with a *Private* channel to invite select users for specific topics.</span></span> <span data-ttu-id="33279-158">Ниже приведен сценарий для финансовой группы, который можно использовать для добавления шаблона в другие отделы или отдельные проекты путем добавления, удаления или редактирования по вашему желанию.</span><span class="sxs-lookup"><span data-stu-id="33279-158">We also provide the script below for the Finance team that can be used to extend the template to additional departments or specific projects by adding, deleting from, or editing to your liking.</span></span> <span data-ttu-id="33279-159">Например, если у  вас есть отдел маркетинга, сценарий можно адаптировать,  переименовав команду из отдела финансов в отдел маркетинга, чтобы создать новую команду маркетинга. </span><span class="sxs-lookup"><span data-stu-id="33279-159">For example, if you have a *Marketing* department, then the script can be adapted by renaming the team from *Finance* to *Marketing* to create a new Marketing team</span></span>

| <span data-ttu-id="33279-160">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="33279-160">Base template type</span></span> | <span data-ttu-id="33279-161">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="33279-161">baseTemplateId</span></span> | <span data-ttu-id="33279-162">Свойства, которые доступны с этим базовым шаблоном</span><span class="sxs-lookup"><span data-stu-id="33279-162">Properties that come with this base template</span></span> |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="33279-163">SMB -</span><span class="sxs-lookup"><span data-stu-id="33279-163">SMB -</span></span> <br><span data-ttu-id="33279-164">Финансы</span><span class="sxs-lookup"><span data-stu-id="33279-164">Finance</span></span>  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| <span data-ttu-id="33279-165">Каналы</span><span class="sxs-lookup"><span data-stu-id="33279-165">Channels</span></span> <ul><li><span data-ttu-id="33279-166">Общий\*</span><span class="sxs-lookup"><span data-stu-id="33279-166">General\*</span></span></li><li><span data-ttu-id="33279-167">Частное \*</span><span class="sxs-lookup"><span data-stu-id="33279-167">Private \*</span></span></li></ul><br> <span data-ttu-id="33279-168">Приложения</span><span class="sxs-lookup"><span data-stu-id="33279-168">Apps</span></span><ul><li><span data-ttu-id="33279-169">OneNote (закреплен на частном **канале)**</span><span class="sxs-lookup"><span data-stu-id="33279-169">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="33279-170">Планировщик (закреплен в частном **канале)**</span><span class="sxs-lookup"><span data-stu-id="33279-170">Planner (pinned to the **Private** channel)</span></span> </li> </ul><br><span data-ttu-id="33279-171">Свойства группы</span><span class="sxs-lookup"><span data-stu-id="33279-171">Team properties</span></span> <ul><li><span data-ttu-id="33279-172">Видимость группы : "Частная"</span><span class="sxs-lookup"><span data-stu-id="33279-172">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="33279-173">\* Автоматически избранные каналы</span><span class="sxs-lookup"><span data-stu-id="33279-173">\*Auto-favorited channels</span></span>

<span data-ttu-id="33279-174">Чтобы создать финансовую команду, принимая значения по умолчанию из предварительно заранее определенного шаблона, предопределйте представление JSON объекта группы в запросе.</span><span class="sxs-lookup"><span data-stu-id="33279-174">To create the Finance team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="33279-175">Дополнительные информацию о развертывании шаблонов Teams см. в статье Microsoft Graph [о создании команды.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="33279-175">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="33279-176">Запрос</span><span class="sxs-lookup"><span data-stu-id="33279-176">Request</span></span> 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessFinance')",
    "displayName": "Finance",
    "description": "All posts, announcements and daily collaboration and communication within the Finance team members (and exec team members as appropriate).",
    "visibility": "Private"
}
```

### <a name="example-finance-team-template-extension-script"></a><span data-ttu-id="33279-177">Пример: сценарий расширения для финансового группы</span><span class="sxs-lookup"><span data-stu-id="33279-177">Example: Finance Team template extension script</span></span>

```powershell
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('standard')",
  "displayName": "Finance",
  "description": "Finance Team",
  "channels": 
   [
        {
            "displayName": "Private",
            "isFavoriteByDefault": true,
            "description": "Invite a more select audience for specific topics.",
             "tabs": 
             [
                {
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('0d820ecd-def2-4297-adad-78056cde7c78')",
                    "name": "OneNote"
                },
                {
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.planner')",
                    "name": "Planner"
                }
            ]
        }
    ],
    "memberSettings": 
    {
        "allowCreateUpdateChannels": true,
        "allowDeleteChannels": true,
       "allowAddRemoveApps": true,
        "allowCreateUpdateRemoveTabs": true,
        "allowCreateUpdateRemoveConnectors": true
    },
    "guestSettings": 
    {
        "allowCreateUpdateChannels": false,
        "allowDeleteChannels": false
    },
    "funSettings": 
    {
        "allowGiphy": true,
        "giphyContentRating": "Moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
    },
    "messagingSettings": 
    {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
    },
    "discoverySettings": 
    {
        "showInTeamsSearchAndSuggestions": true
    },
    "installedApps": 
    [
        {
            "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('0d820ecd-def2-4297-adad-78056cde7c78')"
        },
        {
            "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.planner')"
        }
    ]
}

```

## <a name="related-topics"></a><span data-ttu-id="33279-178">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="33279-178">Related topics</span></span>

- [<span data-ttu-id="33279-179">Начало работы с шаблонами Teams в консоли администрирования</span><span class="sxs-lookup"><span data-stu-id="33279-179">Get started with Teams templates in the admin console</span></span>](get-started-with-teams-templates-in-the-admin-console.md)
- [<span data-ttu-id="33279-180">Начало работы с шаблонами Teams</span><span class="sxs-lookup"><span data-stu-id="33279-180">Get started with Teams templates</span></span>](get-started-with-teams-templates.md)
- <span data-ttu-id="33279-181">[Создание команды](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (в предварительной версии)</span><span class="sxs-lookup"><span data-stu-id="33279-181">[Create team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (in preview)</span></span>

