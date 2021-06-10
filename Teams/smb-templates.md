---
title: Teams шаблоны для малого и среднего бизнеса, встроенные с помощью Microsoft Graph
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
description: Используйте Microsoft Teams шаблоны, встроенные в Microsoft Graph, чтобы быстро и легко создавать команды для малого и среднего бизнеса.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e3d29dca0bbdbd7b3487ac1738b84396a3d41117
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116997"
---
# <a name="teams-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a><span data-ttu-id="9369f-103">Teams, встроенные в Microsoft Graph для малого и среднего бизнеса</span><span class="sxs-lookup"><span data-stu-id="9369f-103">Teams templates built in Microsoft Graph for Small and Medium Businesses</span></span>

<span data-ttu-id="9369f-104">С помощью шаблонов Microsoft Teams можно быстро и удобно создавать команды: готовые шаблоны содержат параметры, каналы и предустановленные приложения.</span><span class="sxs-lookup"><span data-stu-id="9369f-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="9369f-105">Для малого и среднего бизнеса шаблоны могут быть особенно мощны, так как они помогают администраторам быстро Teams развертывание в организации.</span><span class="sxs-lookup"><span data-stu-id="9369f-105">For small and medium businesses, templates can be especially powerful, as they help administrators to quickly deploy Teams across their organization.</span></span> <span data-ttu-id="9369f-106">Шаблоны также помогают сориентировать пользователей и начать работу с Teams эффективно.</span><span class="sxs-lookup"><span data-stu-id="9369f-106">Templates also help orient users and get started with using Teams effectively.</span></span> <span data-ttu-id="9369f-107">Эта статья посвящена вам, если вы отвечаете за планирование, развертывание и управление несколькими командами в организации.</span><span class="sxs-lookup"><span data-stu-id="9369f-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your organization.</span></span>

<span data-ttu-id="9369f-108">В настоящее время мы предлагаем три шаблона для SMB, которые можно использовать в различных ситуациях.</span><span class="sxs-lookup"><span data-stu-id="9369f-108">We currently offer three first-party SMB templates that you can leverage for a variety of situations.</span></span> <span data-ttu-id="9369f-109">Все шаблоны будут создавать *частные Teams.*</span><span class="sxs-lookup"><span data-stu-id="9369f-109">All templates will create *Private* Teams.</span></span> <span data-ttu-id="9369f-110">После создания *веб-Teams* и готовности к его распространению в организации вы можете настроить конфиденциальность на все организации или на общедоступный *.*</span><span class="sxs-lookup"><span data-stu-id="9369f-110">Once you have created the Teams and are ready to roll out to your organization, you can set the privacy to *Org-Wide* or *Public*, as appropriate.</span></span> <span data-ttu-id="9369f-111">Дополнительные сведения о шаблонах команд см. в статье [Начало работы с шаблонами Teams](get-started-with-teams-templates.md).</span><span class="sxs-lookup"><span data-stu-id="9369f-111">To learn more about team templates in general, see [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="company-wide-template"></a><span data-ttu-id="9369f-112">Company-Wide шаблона</span><span class="sxs-lookup"><span data-stu-id="9369f-112">Company-Wide template</span></span>
<span data-ttu-id="9369f-113">Шаблон Company-Wide предназначен для общения и совместной работы, которые актуальны для всей компании.</span><span class="sxs-lookup"><span data-stu-id="9369f-113">The Company-Wide template is meant for communication and collaboration that are relevant for the entire company.</span></span> <span data-ttu-id="9369f-114">Канал "Общий" можно использовать для объявлений, отраслевых новостей или записей руководителей.</span><span class="sxs-lookup"><span data-stu-id="9369f-114">You can use the General channel for company-wide announcements, industry news or executive posts.</span></span> <span data-ttu-id="9369f-115">Канал кадров — это отличное место для консолидации всех действий, связанных с персоналом, таких как должности, обучение и разработка сотрудников.</span><span class="sxs-lookup"><span data-stu-id="9369f-115">The Human Resources channel is a great place to consolidate all HR-related activities like job posts, new employee onboarding, training, and development.</span></span> <span data-ttu-id="9369f-116">Канал Fun Stuff предоставляет социальную платформу для всех случайных и забавных записей.</span><span class="sxs-lookup"><span data-stu-id="9369f-116">The Fun Stuff channel provides a social platform for all random and fun posts.</span></span>

| <span data-ttu-id="9369f-117">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="9369f-117">Base template type</span></span>  | <span data-ttu-id="9369f-118">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="9369f-118">baseTemplateId</span></span> | <span data-ttu-id="9369f-119">Свойства базового шаблона</span><span class="sxs-lookup"><span data-stu-id="9369f-119">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="9369f-120">SMB —</span><span class="sxs-lookup"><span data-stu-id="9369f-120">SMB -</span></span> <br><span data-ttu-id="9369f-121">В масштабе организации</span><span class="sxs-lookup"><span data-stu-id="9369f-121">Company-wide</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| <span data-ttu-id="9369f-122">Каналы</span><span class="sxs-lookup"><span data-stu-id="9369f-122">Channels</span></span> <ul><li><span data-ttu-id="9369f-123">Общие\*</span><span class="sxs-lookup"><span data-stu-id="9369f-123">General\*</span></span></li><li><span data-ttu-id="9369f-124">Кадры\*</span><span class="sxs-lookup"><span data-stu-id="9369f-124">Human Resources\*</span></span></li><li><span data-ttu-id="9369f-125">Забавные материалы\*</span><span class="sxs-lookup"><span data-stu-id="9369f-125">Fun Stuff\*</span></span></li></ul><br> <span data-ttu-id="9369f-126">Приложения</span><span class="sxs-lookup"><span data-stu-id="9369f-126">Apps</span></span><ul><li><span data-ttu-id="9369f-127">Корпоративный портал (веб-сайт закреплен в **канале Кадров)**</span><span class="sxs-lookup"><span data-stu-id="9369f-127">Company Portal (Website pinned to the **Human Resources** channel)</span></span> </li> </UL><br><span data-ttu-id="9369f-128">Свойства команды</span><span class="sxs-lookup"><span data-stu-id="9369f-128">Team properties</span></span> <ul><li><span data-ttu-id="9369f-129">Установлен параметр видимости команды "Закрытая"</span><span class="sxs-lookup"><span data-stu-id="9369f-129">Team visibility set to Private</span></span></li></ul> |

<span data-ttu-id="9369f-130">\* Автоматически избранные каналы</span><span class="sxs-lookup"><span data-stu-id="9369f-130">\*Auto-favorited channels</span></span> 

<span data-ttu-id="9369f-131">Чтобы создать команду Company-Wide, задав значения по умолчанию из предварительно заранее определенного шаблона, предопределйте представление JSON объекта группы в теле запроса.</span><span class="sxs-lookup"><span data-stu-id="9369f-131">To create the Company-Wide team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="9369f-132">Дополнительные информацию о развертывании шаблонов Teams см. в статье microsoft Graph [о создании команды.](/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="9369f-132">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="9369f-133">Запрос</span><span class="sxs-lookup"><span data-stu-id="9369f-133">Request</span></span> 
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

## <a name="executive-team-template"></a><span data-ttu-id="9369f-134">Шаблон "Группа руководителей"</span><span class="sxs-lookup"><span data-stu-id="9369f-134">Executive Team template</span></span>

<span data-ttu-id="9369f-135">Шаблон "Группа руководителей" идеально подходит для создания команды для общения и совместной работы над корпоративными инициативами, например ежегодными приоритетами, финансовыми бюджетами, стратегическими инициативами и ведущими клиентами.</span><span class="sxs-lookup"><span data-stu-id="9369f-135">The Executive Team template is ideal for creating a team for company executives to communicate and collaborate on company initiatives like annual priorities, fiscal budgets, strategic initiatives, and top clients.</span></span> <span data-ttu-id="9369f-136">Этот шаблон поставляется с *закрытым каналом,* в который можно пригласить пользователей для определенных тем.</span><span class="sxs-lookup"><span data-stu-id="9369f-136">This template comes with a *Private* channel to invite select users for specific topics.</span></span>

| <span data-ttu-id="9369f-137">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="9369f-137">Base template type</span></span>  | <span data-ttu-id="9369f-138">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="9369f-138">baseTemplateId</span></span> | <span data-ttu-id="9369f-139">Свойства базового шаблона</span><span class="sxs-lookup"><span data-stu-id="9369f-139">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="9369f-140">SMB —</span><span class="sxs-lookup"><span data-stu-id="9369f-140">SMB -</span></span> <br><span data-ttu-id="9369f-141">Группа руководителей</span><span class="sxs-lookup"><span data-stu-id="9369f-141">Executives Team</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | <span data-ttu-id="9369f-142">Каналы</span><span class="sxs-lookup"><span data-stu-id="9369f-142">Channels</span></span> <ul><li><span data-ttu-id="9369f-143">Общие\*</span><span class="sxs-lookup"><span data-stu-id="9369f-143">General\*</span></span></li><li><span data-ttu-id="9369f-144">Частная \*</span><span class="sxs-lookup"><span data-stu-id="9369f-144">Private \*</span></span></li></ul> <span data-ttu-id="9369f-145">Приложения</span><span class="sxs-lookup"><span data-stu-id="9369f-145">Apps</span></span><ul><li><span data-ttu-id="9369f-146">OneNote (закреплен в частном **канале)**</span><span class="sxs-lookup"><span data-stu-id="9369f-146">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="9369f-147">Планировщик (закреплен в частном **канале)**</span><span class="sxs-lookup"><span data-stu-id="9369f-147">Planner (pinned to the **Private** channel)</span></span> </li></ul><br><span data-ttu-id="9369f-148">Свойства команды</span><span class="sxs-lookup"><span data-stu-id="9369f-148">Team properties</span></span> <ul><li><span data-ttu-id="9369f-149">Установлен параметр видимости команды "Закрытая"</span><span class="sxs-lookup"><span data-stu-id="9369f-149">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="9369f-150">\* Автоматически избранные каналы</span><span class="sxs-lookup"><span data-stu-id="9369f-150">\*Auto-favorited channels</span></span><br>

<span data-ttu-id="9369f-151">Чтобы создать команду руководителей, принимая значения по умолчанию из предварительно заранее определенного шаблона, укажийте в теле запроса представление JSON объекта группы.</span><span class="sxs-lookup"><span data-stu-id="9369f-151">To create the Executives team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="9369f-152">Дополнительные информацию о развертывании шаблонов Teams см. в статье microsoft Graph [о создании команды.](/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="9369f-152">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="9369f-153">Запрос</span><span class="sxs-lookup"><span data-stu-id="9369f-153">Request</span></span> 
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

## <a name="departmental-team-template"></a><span data-ttu-id="9369f-154">Шаблон "Отделная группа"</span><span class="sxs-lookup"><span data-stu-id="9369f-154">Departmental Team template</span></span>

<span data-ttu-id="9369f-155">Шаблон "Отделная группа" можно использовать для создания команды для отдельных отделов или проектов.</span><span class="sxs-lookup"><span data-stu-id="9369f-155">The Departmental team template can be used for creating a team for individual departments or for projects.</span></span> <span data-ttu-id="9369f-156">Шаблон финансовой группы идеально подходит для публикаций, объявлений, ежедневной совместной работы и общения в финансовой команде и руководителей.</span><span class="sxs-lookup"><span data-stu-id="9369f-156">The Finance team template is ideal for all posts, announcements, and daily collaboration and communication within the Finance team members and executive team members as appropriate.</span></span> <span data-ttu-id="9369f-157">Шаблон поставляется с закрытым *каналом,* в который можно пригласить пользователей для определенных тем.</span><span class="sxs-lookup"><span data-stu-id="9369f-157">The template comes with a *Private* channel to invite select users for specific topics.</span></span> <span data-ttu-id="9369f-158">Мы также предоставляем ниже сценарий для финансовой группы, который можно использовать для расширения шаблона до дополнительных отделов или определенных проектов путем добавления, удаления или редактирования по вашему желанию.</span><span class="sxs-lookup"><span data-stu-id="9369f-158">We also provide the script below for the Finance team that can be used to extend the template to additional departments or specific projects by adding, deleting from, or editing to your liking.</span></span> <span data-ttu-id="9369f-159">Например, если у  вас есть отдел маркетинга, сценарий можно адаптировать,  переименовав команду из финансовой в маркетинговую, чтобы создать новую команду по маркетингу. </span><span class="sxs-lookup"><span data-stu-id="9369f-159">For example, if you have a *Marketing* department, then the script can be adapted by renaming the team from *Finance* to *Marketing* to create a new Marketing team</span></span>

| <span data-ttu-id="9369f-160">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="9369f-160">Base template type</span></span> | <span data-ttu-id="9369f-161">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="9369f-161">baseTemplateId</span></span> | <span data-ttu-id="9369f-162">Свойства базового шаблона</span><span class="sxs-lookup"><span data-stu-id="9369f-162">Properties that come with this base template</span></span> |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="9369f-163">SMB —</span><span class="sxs-lookup"><span data-stu-id="9369f-163">SMB -</span></span> <br><span data-ttu-id="9369f-164">Финансы</span><span class="sxs-lookup"><span data-stu-id="9369f-164">Finance</span></span>  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| <span data-ttu-id="9369f-165">Каналы</span><span class="sxs-lookup"><span data-stu-id="9369f-165">Channels</span></span> <ul><li><span data-ttu-id="9369f-166">Общие\*</span><span class="sxs-lookup"><span data-stu-id="9369f-166">General\*</span></span></li><li><span data-ttu-id="9369f-167">Частная \*</span><span class="sxs-lookup"><span data-stu-id="9369f-167">Private \*</span></span></li></ul><br> <span data-ttu-id="9369f-168">Приложения</span><span class="sxs-lookup"><span data-stu-id="9369f-168">Apps</span></span><ul><li><span data-ttu-id="9369f-169">OneNote (закреплен в частном **канале)**</span><span class="sxs-lookup"><span data-stu-id="9369f-169">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="9369f-170">Планировщик (закреплен в частном **канале)**</span><span class="sxs-lookup"><span data-stu-id="9369f-170">Planner (pinned to the **Private** channel)</span></span> </li> </ul><br><span data-ttu-id="9369f-171">Свойства команды</span><span class="sxs-lookup"><span data-stu-id="9369f-171">Team properties</span></span> <ul><li><span data-ttu-id="9369f-172">Установлен параметр видимости команды "Закрытая"</span><span class="sxs-lookup"><span data-stu-id="9369f-172">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="9369f-173">\* Автоматически избранные каналы</span><span class="sxs-lookup"><span data-stu-id="9369f-173">\*Auto-favorited channels</span></span>

<span data-ttu-id="9369f-174">Чтобы создать команду финансового обеспечения, принимая значения по умолчанию из предварительно заранее определенного шаблона, укажийте в теле запроса представление JSON объекта группы.</span><span class="sxs-lookup"><span data-stu-id="9369f-174">To create the Finance team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="9369f-175">Дополнительные информацию о развертывании шаблонов Teams см. в статье microsoft Graph [о создании команды.](/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="9369f-175">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="9369f-176">Запрос</span><span class="sxs-lookup"><span data-stu-id="9369f-176">Request</span></span> 
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

### <a name="example-finance-team-template-extension-script"></a><span data-ttu-id="9369f-177">Пример: сценарий расширения шаблона финансовой группы</span><span class="sxs-lookup"><span data-stu-id="9369f-177">Example: Finance Team template extension script</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="9369f-178">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="9369f-178">Related topics</span></span>

- [<span data-ttu-id="9369f-179">Начало работы с шаблонами Teams в консоли администрирования</span><span class="sxs-lookup"><span data-stu-id="9369f-179">Get started with Teams templates in the admin console</span></span>](get-started-with-teams-templates-in-the-admin-console.md)
- [<span data-ttu-id="9369f-180">Начало работы с шаблонами Teams</span><span class="sxs-lookup"><span data-stu-id="9369f-180">Get started with Teams templates</span></span>](get-started-with-teams-templates.md)
- <span data-ttu-id="9369f-181">[Создание команды](/graph/api/team-post?view=graph-rest-beta) (в предварительной версии)</span><span class="sxs-lookup"><span data-stu-id="9369f-181">[Create team](/graph/api/team-post?view=graph-rest-beta) (in preview)</span></span>