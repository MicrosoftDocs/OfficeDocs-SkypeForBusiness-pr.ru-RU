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
ms.openlocfilehash: e3d29dca0bbdbd7b3487ac1738b84396a3d41117
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116997"
---
# <a name="teams-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a>Шаблоны Teams, встроенные в Microsoft Graph для малого и среднего бизнеса

С помощью шаблонов Microsoft Teams можно быстро и удобно создавать команды: готовые шаблоны содержат параметры, каналы и предустановленные приложения.

Шаблоны для малого и среднего бизнеса особенно мощны, так как они помогают администраторам быстро развернуть Teams в своей организации. Шаблоны также помогают сориентировать пользователей и эффективно использовать Teams. Эта статья для вас, если вы отвечаете за планирование, развертывание и управление несколькими командами в организации.

В настоящее время мы предлагаем три шаблона для работы с МБ, которые можно использовать в различных ситуациях. Все шаблоны будут создавать *закрытые* команды. Создав Teams и готов к его распространению в своей организации,  вы можете установить для нее конфиденциальность как для всей *организации,* так и для всех ее пользователей. Дополнительные сведения о шаблонах команд см. в статье [Начало работы с шаблонами Teams](get-started-with-teams-templates.md).

## <a name="company-wide-template"></a>Company-Wide шаблона
Шаблон Company-Wide предназначен для общения и совместной работы, которые важны для всей компании. Канал "Общий" можно использовать для объявлений, отраслевых новостей и записей руководителей. Канал управления персоналом — это отличное место для консолидации всех действий, связанных с персоналом, таких как вакансии, подготовка новых сотрудников, обучение и разработка. Канал Fun Stuff предоставляет социальную платформу для всех случайных и забавных записей.

| Тип базового шаблона  | baseTemplateId | Свойства базового шаблона |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>Во всей организации | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| Каналы <ul><li>Общие\*</li><li>Кадры\*</li><li>Забавные материалы\*</li></ul><br> Приложения<ul><li>Портал организации (веб-сайт закреплен в **канале "Кадры")** </li> </UL><br>Свойства команды <ul><li>Установлен параметр видимости команды "Закрытая"</li></ul> |

* Автоматически избранные каналы 

Чтобы создать команду Company-Wide, принимая значения по умолчанию из предварительно определенного шаблона, предопределйте представление JSON объекта группы в теле запроса. Дополнительные информацию о развертывании шаблонов Teams см. в статье Microsoft Graph [о создании команды.](/graph/api/team-post?view=graph-rest-beta)

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

Шаблон "Группа руководителей" идеально подходит для того, чтобы создать команду для руководителей компании, чтобы общаться и совместно работать над корпоративными инициативами, например ежегодными приоритетами, финансовыми бюджетами, стратегическими инициативами и лучшими клиентами. Этот шаблон поставляется с *закрытым* каналом, чтобы пригласить пользователей на определенные темы.

| Тип базового шаблона  | baseTemplateId | Свойства базового шаблона |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>Группа руководителей | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | Каналы <ul><li>Общие\*</li><li>Частное \*</li></ul> Приложения<ul><li>OneNote (закреплен на частном **канале)**</li> <li>Планировщик (закреплен в частном **канале)** </li></ul><br>Свойства команды <ul><li>Установлен параметр видимости команды "Закрытая"</li></ul> | 

* Автоматически избранные каналы<br>

Чтобы создать команду руководителей, принимая значения по умолчанию из предварительно определенного шаблона, предопределйте представление JSON объекта группы в теле запроса. Дополнительные информацию о развертывании шаблонов Teams см. в статье Microsoft Graph [о создании команды.](/graph/api/team-post?view=graph-rest-beta)

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

## <a name="departmental-team-template"></a>Шаблон команды отдела

Шаблон команды "Отдел" можно использовать для создания команды для отдельных отделов или проектов. Шаблон финансового группы идеально подходит для публикаций, объявлений, ежедневной совместной работы и общения в финансовом коллективе и руководителей. Шаблон поставляется с закрытым *каналом,* чтобы пригласить пользователей на определенные темы. Ниже приведен сценарий для финансовой группы, который можно использовать для добавления шаблона в другие отделы или отдельные проекты путем добавления, удаления или редактирования по вашему желанию. Например, если у  вас есть отдел маркетинга, сценарий можно адаптировать,  переименовав команду из отдела финансов в отдел маркетинга, чтобы создать новую команду маркетинга. 

| Тип базового шаблона | baseTemplateId | Свойства базового шаблона |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>Финансы  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| Каналы <ul><li>Общие\*</li><li>Частное \*</li></ul><br> Приложения<ul><li>OneNote (закреплен на частном **канале)**</li> <li>Планировщик (закреплен в частном **канале)** </li> </ul><br>Свойства команды <ul><li>Установлен параметр видимости команды "Закрытая"</li></ul> | 

* Автоматически избранные каналы

Чтобы создать финансовую команду, принимая значения по умолчанию из предварительно заранее определенного шаблона, предопределйте представление JSON объекта группы в теле запроса. Дополнительные информацию о развертывании шаблонов Teams см. в статье Microsoft Graph [о создании команды.](/graph/api/team-post?view=graph-rest-beta)

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

### <a name="example-finance-team-template-extension-script"></a>Пример: сценарий расширения для финансового группы

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

## <a name="related-topics"></a>Статьи по теме

- [Начало работы с шаблонами Teams в консоли администрирования](get-started-with-teams-templates-in-the-admin-console.md)
- [Начало работы с шаблонами Teams](get-started-with-teams-templates.md)
- [Создание команды](/graph/api/team-post?view=graph-rest-beta) (в предварительной версии)