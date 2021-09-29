---
title: Шаблоны команд для малого и среднего бизнеса, встроенные с помощью Microsoft Graph
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.reviewer: lavenkat
description: Используйте Microsoft Teams, встроенные в Microsoft Graph, чтобы быстро и легко создавать команды для малого и среднего бизнеса.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0855e7a61b52582b283a5c1f7c4c4f966045d743
ms.sourcegitcommit: 6a65e318d49d8990f2b3409ff7bb2c61ea1f2525
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2021
ms.locfileid: "59991218"
---
# <a name="team-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a>Шаблоны команд, встроенные в Microsoft Graph для малого и среднего бизнеса

Шаблоны команд в Microsoft Teams позволяют быстро и легко создавать команды, предоставляя предопределяемую структуру параметров, каналов и предварительно установленных приложений.

Для малого и среднего бизнеса шаблоны могут быть особенно мощны, так как они помогают быстро Teams развертывание в организации. Шаблоны также помогают пользователям ориентироваться в том, как эффективно Teams. Эта статья для вас, если вы отвечаете за планирование, развертывание и управление несколькими командами в организации.

В настоящее время мы предлагаем три встроенных шаблона для малого и среднего бизнеса, которые можно использовать в различных ситуациях. Все шаблоны создают *закрытые* команды. После создания команд и их распространения в организации вы можете  установить для конфиденциальности все организации или общедоступные *(* при необходимости).

Дополнительные информацию о шаблонах команд см. в этой [Graph.](get-started-with-teams-templates.md)

## <a name="company-wide-template"></a>Company-Wide шаблона

Шаблон Company-Wide предназначен для общения и совместной работы всей компании. Канал "Общее" можно использовать для объявлений, отраслевых новостей или записей руководителей. Канал кадров — это отличное место для консолидации всех действий, связанных с персоналом, таких как должности, обучение и разработка сотрудников. Канал Fun Stuff предоставляет социальную платформу для всех случайных и забавных записей.

| Тип шаблона  | TemplateId | Свойства этого шаблона |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB — <br>В масштабе организации | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| Каналы <ul><li>Общие\*</li><li>Кадры\*</li><li>Забавные материалы\*</li></ul><br> Приложения<ul><li>Корпоративный портал (веб-сайт закреплен в **канале Кадров)** </li> </UL><br>Свойства команды <ul><li>Установлен параметр видимости команды "Закрытая"</li></ul> |

* Автоматически избранные каналы 

Чтобы создать команду Company-Wide, задав стандартные параметры из предварительно заранее определенного шаблона, предопределйте представление JSON объекта группы в теле запроса. Дополнительные информацию о развертывании шаблонов группы см. в статье microsoft Graph о [создании команды.](/graph/api/team-post?view=graph-rest-beta)

#### <a name="request"></a>Запрос 
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

## <a name="executive-team-template"></a>Шаблон "Группа руководителей"

Шаблон "Группа руководителей" идеально подходит для создания команды для общения и совместной работы над корпоративными инициативами, например ежегодными приоритетами, финансовыми бюджетами, стратегическими инициативами и ведущими клиентами. Этот шаблон предлагает *закрытый канал* для приглашения пользователей на определенные темы.

| Тип шаблона  | TemplateId | Свойства этого шаблона |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB — <br>Группа руководителей | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | Каналы <ul><li>Общие\*</li><li>Частная \*</li></ul> Приложения<ul><li>OneNote (закреплена в частном **канале)**</li> <li>Планировщик (закреплен на частном **канале)** </li></ul><br>Свойства команды <ul><li>Установлен параметр видимости команды "Закрытая"</li></ul> | 

* Автоматически избранные каналы<br>

Чтобы создать команду руководителей, задав стандартные параметры из предварительно заранее определенного шаблона, укайте представление JSON объекта группы в теле запроса. Дополнительные информацию о развертывании шаблонов группы см. в статье microsoft Graph о [создании команды.](/graph/api/team-post?view=graph-rest-beta)

#### <a name="request"></a>Запрос 
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

## <a name="departmental-team-template"></a>Шаблон "Отделная группа"

Шаблон "Отделная группа" можно использовать для создания команды для отдельных отделов или проектов. Шаблон финансовой группы идеально подходит для публикаций, объявлений, ежедневной совместной работы и общения в финансовой группе и руководителей. Шаблон поставляется с *закрытым каналом,* в который можно пригласить пользователей для определенных тем.

Мы также предоставляем ниже сценарий для финансовой группы, который можно использовать для расширения шаблона до дополнительных отделов или определенных проектов путем добавления, удаления или редактирования по вашему желанию. Например, если у  вас есть отдел маркетинга, сценарий можно адаптировать,  переименовав команду из финансового отдела в отдел маркетинга, чтобы создать новую команду по маркетингу. 

| Тип шаблона | TemplateId | Свойства этого шаблона |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| SMB — <br>Финансы  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| Каналы <ul><li>Общие\*</li><li>Частная \*</li></ul><br> Приложения<ul><li>OneNote (закреплена в частном **канале)**</li> <li>Планировщик (закреплен на частном **канале)** </li> </ul><br>Свойства команды <ul><li>Установлен параметр видимости команды "Закрытая"</li></ul> | 

* Автоматически избранные каналы

Чтобы создать команду финансового обеспечения, задав стандартные параметры из предварительно заранее определенного шаблона, укайте в теле запроса представление JSON объекта группы. Дополнительные информацию о развертывании шаблонов группы см. в статье microsoft Graph о [создании команды.](/graph/api/team-post?view=graph-rest-beta)

#### <a name="request"></a>Запрос 
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

### <a name="example-finance-team-template-extension-script"></a>Пример: сценарий расширения шаблона финансовой группы

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

## <a name="related-topics"></a>См. также

- [Начало работы с шаблонами Teams в консоли администрирования](get-started-with-teams-templates-in-the-admin-console.md)
- [Начало работы с шаблонами Teams](get-started-with-teams-templates.md)
- [Создание команды](/graph/api/team-post?view=graph-rest-beta) (в предварительной версии)