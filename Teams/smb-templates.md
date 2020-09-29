---
title: Шаблоны групп для малых и средних организаций, созданных с помощью Microsoft Graph
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
description: Используйте встроенные шаблоны Microsoft Teams, созданные в Microsoft Graph, для быстрого и простого создания групп для малых и средних предприятий.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7196dd93fc1245102a333c150715c4b4570986c7
ms.sourcegitcommit: 340c2f432b78af4e78b21056af56c6421627045d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294555"
---
# <a name="teams-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a><span data-ttu-id="beae6-103">Шаблоны групп, созданные в Microsoft Graph для малых и средних организаций</span><span class="sxs-lookup"><span data-stu-id="beae6-103">Teams templates built in Microsoft Graph for Small and Medium Businesses</span></span>

<span data-ttu-id="beae6-104">Шаблоны Microsoft Teams позволяют быстро и легко создавать группы, предоставляя готовый шаблон параметров, каналов и предустановленных приложений.</span><span class="sxs-lookup"><span data-stu-id="beae6-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="beae6-105">Для малых и средних организаций шаблоны могут быть особенно мощными, так как они помогают администраторам быстро развертывать группы в рамках своей организации.</span><span class="sxs-lookup"><span data-stu-id="beae6-105">For small and medium businesses, templates can be especially powerful, as they help administrators to quickly deploy Teams across their organization.</span></span> <span data-ttu-id="beae6-106">Шаблоны также помогают ориентироваться на пользователей и эффективно работать с группами.</span><span class="sxs-lookup"><span data-stu-id="beae6-106">Templates also help orient users and get started with using Teams effectively.</span></span> <span data-ttu-id="beae6-107">Эта статья предназначена для тех, кто ответственен за планирование, развертывание и управление несколькими группами в Организации.</span><span class="sxs-lookup"><span data-stu-id="beae6-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your organization.</span></span>

<span data-ttu-id="beae6-108">В настоящее время мы предлагаем три основного шаблона SMB, который можно использовать в различных ситуациях.</span><span class="sxs-lookup"><span data-stu-id="beae6-108">We currently offer three first-party SMB templates that you can leverage for a variety of situations.</span></span> <span data-ttu-id="beae6-109">Все шаблоны будут создавать *закрытые* команды.</span><span class="sxs-lookup"><span data-stu-id="beae6-109">All templates will create *Private* Teams.</span></span> <span data-ttu-id="beae6-110">После создания Teams и готовности к развертыванию в своей организации вы можете настроить *конфиденциальность или* *общедоступное*приложение.</span><span class="sxs-lookup"><span data-stu-id="beae6-110">Once you have created the Teams and are ready to roll out to your organization, you can set the privacy to *Org-Wide* or *Public*, as appropriate.</span></span> <span data-ttu-id="beae6-111">Дополнительные сведения о шаблонах групп можно найти в разделе [Начало работы с шаблонами групп](get-started-with-teams-templates.md).</span><span class="sxs-lookup"><span data-stu-id="beae6-111">To learn more about team templates in general, see [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="company-wide-template"></a><span data-ttu-id="beae6-112">Шаблон в масштабе компании</span><span class="sxs-lookup"><span data-stu-id="beae6-112">Company-Wide template</span></span>
<span data-ttu-id="beae6-113">Шаблон всей компании предназначен для общения и совместной работы, которые относятся к всей компании.</span><span class="sxs-lookup"><span data-stu-id="beae6-113">The Company-Wide template is meant for communication and collaboration that are relevant for the entire company.</span></span> <span data-ttu-id="beae6-114">Вы можете использовать канал "Общие" для объявлений в масштабах компании, отраслевых новостей и публикаций для руководителей.</span><span class="sxs-lookup"><span data-stu-id="beae6-114">You can use the General channel for company-wide announcements, industry news or executive posts.</span></span> <span data-ttu-id="beae6-115">Канал кадров — это удобное место для консолидации всех действий, связанных с персоналом, таких как создание и добавление новых сотрудников, обучение и разработка.</span><span class="sxs-lookup"><span data-stu-id="beae6-115">The Human Resources channel is a great place to consolidate all HR-related activities like job posts, new employee onboarding, training, and development.</span></span> <span data-ttu-id="beae6-116">Канал забавной связи предоставляет социальные платформы для всех случайных и забавных публикаций.</span><span class="sxs-lookup"><span data-stu-id="beae6-116">The Fun Stuff channel provides a social platform for all random and fun posts.</span></span>

| <span data-ttu-id="beae6-117">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="beae6-117">Base template type</span></span>  | <span data-ttu-id="beae6-118">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="beae6-118">baseTemplateId</span></span> | <span data-ttu-id="beae6-119">Свойства, которые поставляются с этим базовым шаблоном</span><span class="sxs-lookup"><span data-stu-id="beae6-119">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="beae6-120">Файл</span><span class="sxs-lookup"><span data-stu-id="beae6-120">SMB -</span></span> <br><span data-ttu-id="beae6-121">В масштабах компании</span><span class="sxs-lookup"><span data-stu-id="beae6-121">Company-wide</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| <span data-ttu-id="beae6-122">Каналы</span><span class="sxs-lookup"><span data-stu-id="beae6-122">Channels</span></span> <ul><li><span data-ttu-id="beae6-123">Общий\*</span><span class="sxs-lookup"><span data-stu-id="beae6-123">General\*</span></span></li><li><span data-ttu-id="beae6-124">Человеческие ресурсы\*</span><span class="sxs-lookup"><span data-stu-id="beae6-124">Human Resources\*</span></span></li><li><span data-ttu-id="beae6-125">Забавные вещи\*</span><span class="sxs-lookup"><span data-stu-id="beae6-125">Fun Stuff\*</span></span></li></ul><br> <span data-ttu-id="beae6-126">Приложения</span><span class="sxs-lookup"><span data-stu-id="beae6-126">Apps</span></span><ul><li><span data-ttu-id="beae6-127">Портал компании (веб-сайт, закрепленный по каналу **управления персоналом** )</span><span class="sxs-lookup"><span data-stu-id="beae6-127">Company Portal (Website pinned to the **Human Resources** channel)</span></span> </li> </UL><br><span data-ttu-id="beae6-128">Свойства группы</span><span class="sxs-lookup"><span data-stu-id="beae6-128">Team properties</span></span> <ul><li><span data-ttu-id="beae6-129">Для видимости команды установлено значение Private</span><span class="sxs-lookup"><span data-stu-id="beae6-129">Team visibility set to Private</span></span></li></ul> |

<span data-ttu-id="beae6-130">\* Автоматически добавленные в избранное каналы</span><span class="sxs-lookup"><span data-stu-id="beae6-130">\*Auto-favorited channels</span></span> 

<span data-ttu-id="beae6-131">Чтобы создать группу для всей компании, используя стандартные значения из предопределенного шаблона, укажите JSON-представление объекта группы в теле запроса.</span><span class="sxs-lookup"><span data-stu-id="beae6-131">To create the Company-Wide team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="beae6-132">Чтобы узнать больше о том, как развертывать шаблоны групп, ознакомьтесь со [статьей Microsoft Graph по созданию групп](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="beae6-132">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="beae6-133">Запрос</span><span class="sxs-lookup"><span data-stu-id="beae6-133">Request</span></span> 
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

## <a name="executive-team-template"></a><span data-ttu-id="beae6-134">Шаблон группы для руководителей</span><span class="sxs-lookup"><span data-stu-id="beae6-134">Executive Team template</span></span>

<span data-ttu-id="beae6-135">Шаблон группы руководителя идеально подходит для создания группы для руководителей компании по налаживанию связи и совместной работы над корпоративными инициативами, такими как ежегодные приоритеты, финансовые бюджеты, стратегические инициативы и лучшие клиенты.</span><span class="sxs-lookup"><span data-stu-id="beae6-135">The Executive Team template is ideal for creating a team for company executives to communicate and collaborate on company initiatives like annual priorities, fiscal budgets, strategic initiatives, and top clients.</span></span> <span data-ttu-id="beae6-136">Этот шаблон сопровождается *личным* каналом, с помощью которого можно пригласить пользователей для выбора определенных тем.</span><span class="sxs-lookup"><span data-stu-id="beae6-136">This template comes with a *Private* channel to invite select users for specific topics.</span></span>

| <span data-ttu-id="beae6-137">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="beae6-137">Base template type</span></span>  | <span data-ttu-id="beae6-138">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="beae6-138">baseTemplateId</span></span> | <span data-ttu-id="beae6-139">Свойства, которые поставляются с этим базовым шаблоном</span><span class="sxs-lookup"><span data-stu-id="beae6-139">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="beae6-140">Файл</span><span class="sxs-lookup"><span data-stu-id="beae6-140">SMB -</span></span> <br><span data-ttu-id="beae6-141">Группа руководителей</span><span class="sxs-lookup"><span data-stu-id="beae6-141">Executives Team</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | <span data-ttu-id="beae6-142">Каналы</span><span class="sxs-lookup"><span data-stu-id="beae6-142">Channels</span></span> <ul><li><span data-ttu-id="beae6-143">Общий\*</span><span class="sxs-lookup"><span data-stu-id="beae6-143">General\*</span></span></li><li><span data-ttu-id="beae6-144">Конфиденциаль \*</span><span class="sxs-lookup"><span data-stu-id="beae6-144">Private \*</span></span></li></ul> <span data-ttu-id="beae6-145">Приложения</span><span class="sxs-lookup"><span data-stu-id="beae6-145">Apps</span></span><ul><li><span data-ttu-id="beae6-146">OneNote (закреплено в **частном** канале)</span><span class="sxs-lookup"><span data-stu-id="beae6-146">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="beae6-147">Планировщик (закрепление в **частном** канале)</span><span class="sxs-lookup"><span data-stu-id="beae6-147">Planner (pinned to the **Private** channel)</span></span> </li></ul><br><span data-ttu-id="beae6-148">Свойства группы</span><span class="sxs-lookup"><span data-stu-id="beae6-148">Team properties</span></span> <ul><li><span data-ttu-id="beae6-149">Для видимости команды установлено значение Private</span><span class="sxs-lookup"><span data-stu-id="beae6-149">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="beae6-150">\* Автоматически добавленные в избранное каналы</span><span class="sxs-lookup"><span data-stu-id="beae6-150">\*Auto-favorited channels</span></span><br>

<span data-ttu-id="beae6-151">Чтобы создать рабочую группу руководителей, используя стандартные значения из предопределенного шаблона, укажите в тексте запроса представление JSON объекта группы.</span><span class="sxs-lookup"><span data-stu-id="beae6-151">To create the Executives team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="beae6-152">Чтобы узнать больше о том, как развертывать шаблоны групп, ознакомьтесь со [статьей Microsoft Graph по созданию групп](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="beae6-152">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="beae6-153">Запрос</span><span class="sxs-lookup"><span data-stu-id="beae6-153">Request</span></span> 
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

## <a name="departmental-team-template"></a><span data-ttu-id="beae6-154">Шаблон группы отделов</span><span class="sxs-lookup"><span data-stu-id="beae6-154">Departmental Team template</span></span>

<span data-ttu-id="beae6-155">Шаблон группы "Отдел" можно использовать для создания группы для отдельных отделов или для проектов.</span><span class="sxs-lookup"><span data-stu-id="beae6-155">The Departmental team template can be used for creating a team for individual departments or for projects.</span></span> <span data-ttu-id="beae6-156">Шаблон "Финансы" идеально подходит для всех сообщений, извещений и ежедневной совместной работы и обмена данными между участниками группы "Финансы" и соответствующими участниками группы.</span><span class="sxs-lookup"><span data-stu-id="beae6-156">The Finance team template is ideal for all posts, announcements, and daily collaboration and communication within the Finance team members and executive team members as appropriate.</span></span> <span data-ttu-id="beae6-157">Шаблон сопровождается *личным* каналом, с помощью которого можно пригласить пользователей в конкретные темы.</span><span class="sxs-lookup"><span data-stu-id="beae6-157">The template comes with a *Private* channel to invite select users for specific topics.</span></span> <span data-ttu-id="beae6-158">Кроме того, мы предоставляем ниже сценарий для группы "Финансы", который можно использовать для продления шаблона до дополнительных отделов или конкретных проектов с помощью добавления, удаления или изменения.</span><span class="sxs-lookup"><span data-stu-id="beae6-158">We also provide the script below for the Finance team that can be used to extend the template to additional departments or specific projects by adding, deleting from, or editing to your liking.</span></span> <span data-ttu-id="beae6-159">Например, если у вас есть отдел *маркетинга* , вы можете адаптировать сценарий, переименование команды из *финансового* в *маркетинг* для создания новой маркетинговой группы</span><span class="sxs-lookup"><span data-stu-id="beae6-159">For example, if you have a *Marketing* department, then the script can be adapted by renaming the team from *Finance* to *Marketing* to create a new Marketing team</span></span>

| <span data-ttu-id="beae6-160">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="beae6-160">Base template type</span></span> | <span data-ttu-id="beae6-161">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="beae6-161">baseTemplateId</span></span> | <span data-ttu-id="beae6-162">Свойства, которые поставляются с этим базовым шаблоном</span><span class="sxs-lookup"><span data-stu-id="beae6-162">Properties that come with this base template</span></span> |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="beae6-163">Файл</span><span class="sxs-lookup"><span data-stu-id="beae6-163">SMB -</span></span> <br><span data-ttu-id="beae6-164">Финансы</span><span class="sxs-lookup"><span data-stu-id="beae6-164">Finance</span></span>  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| <span data-ttu-id="beae6-165">Каналы</span><span class="sxs-lookup"><span data-stu-id="beae6-165">Channels</span></span> <ul><li><span data-ttu-id="beae6-166">Общий\*</span><span class="sxs-lookup"><span data-stu-id="beae6-166">General\*</span></span></li><li><span data-ttu-id="beae6-167">Конфиденциаль \*</span><span class="sxs-lookup"><span data-stu-id="beae6-167">Private \*</span></span></li></ul><br> <span data-ttu-id="beae6-168">Приложения</span><span class="sxs-lookup"><span data-stu-id="beae6-168">Apps</span></span><ul><li><span data-ttu-id="beae6-169">OneNote (закреплено в **частном** канале)</span><span class="sxs-lookup"><span data-stu-id="beae6-169">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="beae6-170">Планировщик (закрепление в **частном** канале)</span><span class="sxs-lookup"><span data-stu-id="beae6-170">Planner (pinned to the **Private** channel)</span></span> </li> </ul><br><span data-ttu-id="beae6-171">Свойства группы</span><span class="sxs-lookup"><span data-stu-id="beae6-171">Team properties</span></span> <ul><li><span data-ttu-id="beae6-172">Для видимости команды установлено значение Private</span><span class="sxs-lookup"><span data-stu-id="beae6-172">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="beae6-173">\* Автоматически добавленные в избранное каналы</span><span class="sxs-lookup"><span data-stu-id="beae6-173">\*Auto-favorited channels</span></span>

<span data-ttu-id="beae6-174">Чтобы создать финансовую группу, используя стандартные значения из предопределенного шаблона, укажите в тексте запроса представление JSON объекта группы.</span><span class="sxs-lookup"><span data-stu-id="beae6-174">To create the Finance team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="beae6-175">Чтобы узнать больше о том, как развертывать шаблоны групп, ознакомьтесь со [статьей Microsoft Graph по созданию групп](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="beae6-175">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="beae6-176">Запрос</span><span class="sxs-lookup"><span data-stu-id="beae6-176">Request</span></span> 
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

### <a name="example-finance-team-template-extension-script"></a><span data-ttu-id="beae6-177">Пример: сценарий расширения шаблона группы "Финансы"</span><span class="sxs-lookup"><span data-stu-id="beae6-177">Example: Finance Team template extension script</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="beae6-178">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="beae6-178">Related topics</span></span>

- [<span data-ttu-id="beae6-179">Начало работы с шаблонами групп на консоли администрирования</span><span class="sxs-lookup"><span data-stu-id="beae6-179">Get started with Teams templates in the admin console</span></span>](get-started-with-teams-templates-in-the-admin-console.md)
- [<span data-ttu-id="beae6-180">Начало работы с шаблонами Teams</span><span class="sxs-lookup"><span data-stu-id="beae6-180">Get started with Teams templates</span></span>](get-started-with-teams-templates.md)
- <span data-ttu-id="beae6-181">[Создание команды](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (в предварительной версии)</span><span class="sxs-lookup"><span data-stu-id="beae6-181">[Create team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (in preview)</span></span>

