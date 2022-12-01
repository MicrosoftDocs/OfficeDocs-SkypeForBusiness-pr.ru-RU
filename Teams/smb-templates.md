---
title: Шаблоны команд для малого и среднего бизнеса, созданные с помощью Майкрософт Graph
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
description: Используйте готовые шаблоны Майкрософт Teams, встроенные в Майкрософт Graph, чтобы быстро и легко создавать команды для малого и среднего бизнеса.
ms.custom:
- seo-marvel-mar2020
- chat-teams-channels-revamp
ms.openlocfilehash: 85f1573cb93f5362dc046ab97e2ac621f147fe4a
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198721"
---
# <a name="team-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a>Шаблоны команд, встроенные в Майкрософт Graph для малого и среднего бизнеса

С помощью шаблонов команд в Microsoft Teams можно быстро и легко создавать команды с готовой командной структурой параметров, каналов и предустановленных приложений.

Для малого и среднего бизнеса шаблоны могут быть особенно эффективными, так как они помогают быстро развертывать Teams в организации. Шаблоны также помогают пользователям ориентироваться на эффективное использование Teams. Эта статья поможет вам, если вы отвечаете за планирование, развертывание и управление несколькими командами в вашей организации.

В настоящее время мы предлагаем три готовых шаблона для малого и среднего бизнеса, которые можно использовать в различных ситуациях. Все шаблоны создают *частные* команды. После создания команд и подготовки к развертыванию в вашей организации вы можете задать для конфиденциальности *значение "Общеорганиционная* " или *"Общедоступная*" соответствующим образом.

> [!NOTE]
> Вы также можете использовать Майкрософт Graph для создания собственных пользовательских шаблонов. Дополнительные сведения см. в статье [Тип ресурса teamTemplate](/graph/api/resources/teamtemplate).

Дополнительные сведения о шаблонах команд в целом см. в статье [Начало работы с шаблонами команд с помощью Майкрософт Graph](get-started-with-teams-templates.md).

## <a name="company-wide-template"></a>шаблон Company-Wide

Шаблон Company-Wide предназначен для общения и совместной работы всей компании. Вы можете использовать общий канал для объявлений на уровне компании, отраслевых новостей или должностей руководителей. Канал управления персоналом — это отличное место для консолидации всех связанных с персоналом мероприятий, таких как должности, адаптация новых сотрудников, обучение и развитие. Канал Fun Stuff предоставляет социальную платформу для всех случайных и забавных сообщений.

| Тип шаблона  | TemplateId | Свойства этого шаблона |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB- <br>В масштабах всей компании | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| Каналы <ul><li>Общий\*</li><li>Кадровые ресурсы\*</li><li>Забавные вещи\*</li></ul><br> Приложения<ul><li>Корпоративный портал (веб-сайт, закрепленный в канале **управления персоналом**) </li> </UL><br>Свойства команды <ul><li>Установлен параметр видимости команды "Закрытая"</li></ul> |

*Автоматически избранные каналы 

Чтобы создать команду Company-Wide, приняв параметры по умолчанию из предварительно определенного шаблона, укажите представление объекта team в формате JSON в тексте запроса. Дополнительные сведения о развертывании шаблонов команд см. в статье Майкрософт Graph [о создании команды](/graph/api/team-post?view=graph-rest-beta&preserve-view=true).

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

## <a name="executive-team-template"></a>Шаблон группы руководителей

Шаблон "Команда руководителей" идеально подходит для создания команды руководителей компании для общения и совместной работы над инициативами компании, такими как ежегодные приоритеты, финансовые бюджеты, стратегические инициативы и ведущие клиенты. Этот шаблон поставляется с *частным* каналом для приглашения отдельных пользователей для определенных тем.

| Тип шаблона  | TemplateId | Свойства этого шаблона |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB- <br>Команда руководителей | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | Каналы <ul><li>Общий\*</li><li>Частная \*</li></ul> Приложения<ul><li>OneNote (закреплен на **частном** канале)</li> <li>Планировщик (закреплен в **частном** канале) </li></ul><br>Свойства команды <ul><li>Установлен параметр видимости команды "Закрытая"</li></ul> | 

*Автоматически избранные каналы<br>

Чтобы создать команду руководителей, используя параметры по умолчанию из предварительно определенного шаблона, укажите представление объекта команды в формате JSON в тексте запроса. Дополнительные сведения о развертывании шаблонов команд см. в статье Майкрософт Graph [о создании команды](/graph/api/team-post?view=graph-rest-beta&preserve-view=true).

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

## <a name="departmental-team-template"></a>Шаблон группы отдела

Шаблон команды отдела можно использовать для создания команды для отдельных отделов или проектов. Шаблон команды по финансам идеально подходит для всех сообщений, объявлений, а также для ежедневной совместной работы и общения между членами финансовой и исполнительной команды соответствующим образом. Шаблон поставляется с *частным* каналом для приглашения отдельных пользователей для определенных тем.

Мы также предоставляем приведенный ниже сценарий для финансовой команды, который можно использовать для расширения шаблона на дополнительные отделы или конкретные проекты путем добавления, удаления из или редактирования по своему усмотрению. Например, если у вас есть отдел *маркетинга*, скрипт можно адаптировать, переименовав команду из *"Финансы**" в "Маркетинг"*, чтобы создать новую команду по маркетингу.

| Тип шаблона | TemplateId | Свойства этого шаблона |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| SMB- <br>Финансы  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| Каналы <ul><li>Общий\*</li><li>Частная \*</li></ul><br> Приложения<ul><li>OneNote (закреплен на **частном** канале)</li> <li>Планировщик (закреплен в **частном** канале) </li> </ul><br>Свойства команды <ul><li>Установлен параметр видимости команды "Закрытая"</li></ul> | 

*Автоматически избранные каналы

Чтобы создать команду по финансам, используя параметры по умолчанию из предварительно определенного шаблона, укажите представление объекта team в формате JSON в тексте запроса. Дополнительные сведения о развертывании шаблонов команд см. в статье Майкрософт Graph [о создании команды](/graph/api/team-post?view=graph-rest-beta&preserve-view=true).

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

### <a name="example-finance-team-template-extension-script"></a>Пример. Сценарий расширения шаблона группы финансов

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
- [Создание команды](/graph/api/team-post?view=graph-rest-beta&preserve-view=true) (в предварительной версии)
