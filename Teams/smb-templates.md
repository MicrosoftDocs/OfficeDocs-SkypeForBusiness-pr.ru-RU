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
ms.openlocfilehash: 971b7b0d3be009938a05b7b8fd38105cc273d6158309c69c30cb7c22c51d3fce
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54323941"
---
# <a name="teams-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a>Teams, встроенные в Microsoft Graph для малого и среднего бизнеса

С помощью шаблонов Microsoft Teams можно быстро и удобно создавать команды: готовые шаблоны содержат параметры, каналы и предустановленные приложения.

Для малого и среднего бизнеса шаблоны могут быть особенно мощны, так как они помогают администраторам быстро Teams развертывание в организации. Шаблоны также помогают сориентировать пользователей и начать работу с Teams эффективно. Эта статья для вас, если вы отвечаете за планирование, развертывание и управление несколькими командами в организации.

В настоящее время мы предлагаем три шаблона для SMB, которые можно использовать в различных ситуациях. Все шаблоны будут создавать *частные Teams.* После создания *веб-Teams* и готовности к его распространению в организации вы можете настроить конфиденциальность на все организации или на общедоступный *.* Дополнительные сведения о шаблонах команд см. в статье [Начало работы с шаблонами Teams](get-started-with-teams-templates.md).

## <a name="company-wide-template"></a>Company-Wide шаблона
Шаблон Company-Wide предназначен для общения и совместной работы, которые актуальны для всей компании. Канал "Общее" можно использовать для объявлений, отраслевых новостей или записей руководителей. Канал кадров — это отличное место для консолидации всех действий, связанных с персоналом, таких как должности, новые сотрудники, обучение и развитие. Канал Fun Stuff предоставляет социальную платформу для всех случайных и забавных записей.

| Тип базового шаблона  | baseTemplateId | Свойства базового шаблона |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB — <br>В масштабе компании | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| Каналы <ul><li>Общие\*</li><li>Кадры\*</li><li>Забавные материалы\*</li></ul><br> Приложения<ul><li>Корпоративный портал (веб-сайт закреплен в **канале Кадров)** </li> </UL><br>Свойства команды <ul><li>Установлен параметр видимости команды "Закрытая"</li></ul> |

* Автоматически избранные каналы 

Чтобы создать команду Company-Wide, задав значения по умолчанию из предварительно заранее определенного шаблона, предопределйте представление JSON объекта группы в теле запроса. Дополнительные информацию о развертывании шаблонов Teams см. в статье microsoft Graph [о создании команды.](/graph/api/team-post?view=graph-rest-beta)

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

Шаблон "Группа руководителей" идеально подходит для создания команды для общения и совместной работы над корпоративными инициативами, например ежегодными приоритетами, финансовыми бюджетами, стратегическими инициативами и ведущими клиентами. Этот шаблон поставляется с *закрытым каналом* для приглашения пользователей на определенные темы.

| Тип базового шаблона  | baseTemplateId | Свойства базового шаблона |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB — <br>Группа руководителей | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | Каналы <ul><li>Общие\*</li><li>Частная \*</li></ul> Приложения<ul><li>OneNote (закреплен в частном **канале)**</li> <li>Планировщик (закреплен в частном **канале)** </li></ul><br>Свойства команды <ul><li>Установлен параметр видимости команды "Закрытая"</li></ul> | 

* Автоматически избранные каналы<br>

Чтобы создать команду руководителей, принимая значения по умолчанию из предварительно заранее определенного шаблона, укажийте в теле запроса представление JSON объекта группы. Дополнительные информацию о развертывании шаблонов Teams см. в статье microsoft Graph [о создании команды.](/graph/api/team-post?view=graph-rest-beta)

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

Шаблон "Отделная группа" можно использовать для создания команды для отдельных отделов или проектов. Шаблон финансовой группы идеально подходит для публикаций, объявлений, ежедневной совместной работы и общения в финансовой группе и руководителей. Шаблон поставляется с закрытым *каналом,* в который можно пригласить пользователей для определенных тем. Мы также предоставляем ниже сценарий для финансовой группы, который можно использовать для расширения шаблона до дополнительных отделов или определенных проектов путем добавления, удаления или редактирования по вашему желанию. Например, если у  вас есть отдел маркетинга, сценарий можно адаптировать,  переименовав команду из финансового отдела в отдел маркетинга, чтобы создать новую команду по маркетингу. 

| Тип базового шаблона | baseTemplateId | Свойства базового шаблона |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| SMB — <br>Финансы  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| Каналы <ul><li>Общие\*</li><li>Частная \*</li></ul><br> Приложения<ul><li>OneNote (закреплен в частном **канале)**</li> <li>Планировщик (закреплен в частном **канале)** </li> </ul><br>Свойства команды <ul><li>Установлен параметр видимости команды "Закрытая"</li></ul> | 

* Автоматически избранные каналы

Чтобы создать команду финансового обеспечения, принимая значения по умолчанию из предварительно заранее определенного шаблона, укажийте в теле запроса представление JSON объекта группы. Дополнительные информацию о развертывании шаблонов Teams см. в статье microsoft Graph [о создании команды.](/graph/api/team-post?view=graph-rest-beta)

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

## <a name="related-topics"></a>Статьи по теме

- [Начало работы с шаблонами Teams в консоли администрирования](get-started-with-teams-templates-in-the-admin-console.md)
- [Начало работы с шаблонами Teams](get-started-with-teams-templates.md)
- [Создание команды](/graph/api/team-post?view=graph-rest-beta) (в предварительной версии)