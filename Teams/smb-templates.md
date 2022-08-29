---
title: Шаблоны команд для малого и среднего бизнеса, созданные с помощью Microsoft Graph
author: LanaChin
ms.author: v-lanachin
manager: samanro
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
description: Используйте стандартные шаблоны Microsoft Teams, встроенные в Microsoft Graph, чтобы быстро и легко создавать команды для малого и среднего бизнеса.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 644d45660fba729991796f33e7210222832e0c0f
ms.sourcegitcommit: 903abff4ce79c10bf1fb936b8ad71f6315a43c18
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2022
ms.locfileid: "67278483"
---
# <a name="team-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a>Шаблоны команд, созданные в Microsoft Graph для малого и среднего бизнеса

С помощью шаблонов команд в Microsoft Teams можно быстро и легко создавать команды с готовой командной структурой параметров, каналов и предустановленных приложений.

Для малого и среднего бизнеса шаблоны могут быть особенно мощными, так как они помогают быстро развертывать Teams в организации. Шаблоны также помогают пользователям сориентированию в том, как эффективно использовать Teams. Эта статья предназначена для вас, если вы отвечаете за планирование, развертывание и управление несколькими командами в организации.

В настоящее время мы предлагаем три предварительно созданных шаблона для малого и среднего бизнеса, которые можно использовать в различных ситуациях. Все шаблоны создают *частные* команды. После создания команд и подготовки к развертыванию в организации вы можете установить уровень конфиденциальности на уровне организации или  в общедоступном *режиме.*

> [!NOTE]
> Вы также можете использовать Microsoft Graph для создания собственных настраиваемых шаблонов. Дополнительные сведения см. в [описании типа ресурса teamTemplate](/graph/api/resources/teamtemplate).

Дополнительные сведения о шаблонах команд см. в статье "Начало работы с шаблонами групп [с помощью Microsoft Graph"](get-started-with-teams-templates.md).

## <a name="company-wide-template"></a>Company-Wide шаблона

Шаблон Company-Wide предназначен для обмена данными и совместной работы для всей компании. Канал "Общие" можно использовать для корпоративных объявлений, новостей в отрасли или записей руководителей. Канал "Управление персоналом" — это отличное место для консолидации всех действий, связанных с персоналом, таких как должность, адаптация новых сотрудников, обучение и разработка. Канал Fun Stuff предоставляет социальные платформы для всех случайных и интересных записей.

| Тип шаблона  | TemplateId | Свойства этого шаблона |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB — <br>На уровне компании | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| Каналы <ul><li>Общий\*</li><li>Отдел кадров\*</li><li>Интересные материалы\*</li></ul><br> Приложения<ul><li>Корпоративный портал (веб-сайт закреплен в **канале управления персоналом**) </li> </UL><br>Свойства команды <ul><li>Установлен параметр видимости команды "Закрытая"</li></ul> |

*Автоматически избранные каналы 

Чтобы создать группу Company-Wide, используя параметры по умолчанию из предварительно определенного шаблона, предоставьте представление объекта группы в формате JSON в тексте запроса. Дополнительные сведения о развертывании шаблонов команд см. в статье Microsoft Graph [о создании команды](/graph/api/team-post?view=graph-rest-beta).

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

## <a name="executive-team-template"></a>Шаблон команды руководителей

Шаблон команды руководителей идеально подходит для создания команды для руководителей компании для обмена данными и совместной работы над корпоративными инициативами, такими как ежегодные приоритеты, финансовые бюджеты, стратегические инициативы и основные клиенты. Этот шаблон поставляется с частным *каналом* для приглашения выбранных пользователей для определенных разделов.

| Тип шаблона  | TemplateId | Свойства этого шаблона |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB — <br>Команда руководителей | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | Каналы <ul><li>Общий\*</li><li>Частная \*</li></ul> Приложения<ul><li>OneNote (закреплено на **приватном канале** )</li> <li>Планировщик (закрепленный в **приватном канале** ) </li></ul><br>Свойства команды <ul><li>Установлен параметр видимости команды "Закрытая"</li></ul> | 

*Автоматически избранные каналы<br>

Чтобы создать команду руководителей, используя параметры по умолчанию из предварительно определенного шаблона, предоставьте представление объекта группы в формате JSON в тексте запроса. Дополнительные сведения о развертывании шаблонов команд см. в статье Microsoft Graph [о создании команды](/graph/api/team-post?view=graph-rest-beta).

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

## <a name="departmental-team-template"></a>Шаблон группы отделов

Шаблон группы отделов можно использовать для создания команды для отдельных отделов или для проектов. Шаблон финансовой команды идеально подходит для всех записей, объявлений, повседневной совместной работы и общения в финансовой команде и руководителей по мере необходимости. Шаблон поставляется с частным *каналом* для приглашения выбранных пользователей для определенных разделов.

Мы также предоставляем приведенный ниже сценарий для финансовой команды, который можно использовать для расширения шаблона на дополнительные отделы или конкретные проекты путем добавления, удаления или редактирования по своему желанию. Например, если у вас есть отдел  маркетинга, сценарий можно адаптировать, переименовав команду из *finance в* *marketing*, чтобы создать новую команду по маркетингу.

| Тип шаблона | TemplateId | Свойства этого шаблона |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| SMB — <br>Финансы  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| Каналы <ul><li>Общий\*</li><li>Частная \*</li></ul><br> Приложения<ul><li>OneNote (закреплено на **приватном канале** )</li> <li>Планировщик (закрепленный в **приватном канале** ) </li> </ul><br>Свойства команды <ul><li>Установлен параметр видимости команды "Закрытая"</li></ul> | 

*Автоматически избранные каналы

Чтобы создать группу "Финансы", используя параметры по умолчанию из предварительно определенного шаблона, предоставьте представление объекта группы в формате JSON в тексте запроса. Дополнительные сведения о развертывании шаблонов команд см. в статье Microsoft Graph [о создании команды](/graph/api/team-post?view=graph-rest-beta).

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

### <a name="example-finance-team-template-extension-script"></a>Пример: скрипт расширения шаблона финансовой команды

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

- [Начало работы с шаблонами команд в Центре администрирования Teams](get-started-with-teams-templates-in-the-admin-console.md)
- [Начало работы с шаблонами команд с помощью Microsoft Graph](get-started-with-teams-templates.md)
- [Создание команды](/graph/api/team-post?view=graph-rest-beta) (предварительная версия)
