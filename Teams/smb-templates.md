---
title: Шаблоны групп для малых и средних организаций
author: kenwith
ms.author: kenwith
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
description: Начало работы с шаблонами групп для малых и средних организаций
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4aa620e241bd59ce39f415fca3e33583a3c26c01
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140852"
---
# <a name="get-started-with-teams-templates-for-small-and-medium-businesses"></a>Начало работы с шаблонами групп для малых и средних организаций

Шаблоны Microsoft Teams позволяют быстро и легко создавать группы, предоставляя готовый шаблон параметров, каналов и предустановленных приложений.

Для малых и средних организаций шаблоны могут быть особенно мощными, так как они помогают администраторам быстро развертывать группы в рамках своей организации. Шаблоны также помогают ориентироваться на пользователей и эффективно работать с группами. Эта статья предназначена для тех, кто ответственен за планирование, развертывание и управление несколькими группами в Организации.

В настоящее время мы предлагаем три шаблона SMB для первого производителя, которые можно использовать в различных ситуациях. Все шаблоны будут создавать *закрытые* команды. После создания групп и готовности к развертыванию в вашей организации вы можете настроить *конфиденциальность или* *общедоступное*приложение. Дополнительные сведения о шаблонах групп можно найти в разделе [Приступая к работе с шаблонами групп](get-started-with-teams-templates.md).

## <a name="company-wide-template"></a>Шаблон в масштабе компании
Шаблон всей компании предназначен для общения и совместной работы, которые относятся к всей компании. Вы можете использовать канал "Общие" для объявлений в масштабах компании, отраслевых новостей и публикаций для руководителей. Канал кадров — это удобное место для консолидации всех действий, связанных с персоналом, таких как создание и добавление новых сотрудников, обучение и разработка. Канал забавной связи предоставляет социальные платформы для всех случайных и забавных публикаций.

| Тип базового шаблона  | baseTemplateId | Свойства, которые поставляются с этим базовым шаблоном |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| Файл <br>В масштабах компании | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| Каналы <ul><li>Общий\*</li><li>Человеческие ресурсы\*</li><li>Забавные вещи\*</li></ul><br> Приложения<ul><li>Портал компании (веб-сайт, закрепленный по каналу **управления персоналом** ) </li> </UL><br>Свойства группы <ul><li>Для видимости команды установлено значение Private</li></ul> |

* Автоматически добавленные в избранное каналы 

Чтобы создать группу для всей компании, используя стандартные значения из предопределенного шаблона, укажите JSON-представление объекта группы в теле запроса. Чтобы узнать больше о том, как развертывать шаблоны групп, ознакомьтесь со [статьей Microsoft Graph по созданию групп](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

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

## <a name="executive-team-template"></a>Шаблон группы для руководителей

Шаблон группы руководителя идеально подходит для создания группы для руководителей компании по налаживанию связи и совместной работы над корпоративными инициативами, такими как ежегодные приоритеты, финансовые бюджеты, стратегические инициативы, лучшие клиенты и т. д. Этот шаблон сопровождается *личным* каналом, с помощью которого можно пригласить пользователей для выбора определенных тем.

| Тип базового шаблона  | baseTemplateId | Свойства, которые поставляются с этим базовым шаблоном |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| Файл <br>Группа руководителей | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | Каналы <ul><li>Общий\*</li><li>Конфиденциаль\*</li></ul> Приложения<ul><li>OneNote (закреплено в **частном** канале)</li> <li>Планировщик (закрепление в **частном** канале) </li></ul><br>Свойства группы <ul><li>Для видимости команды установлено значение Private</li></ul> | 

* Автоматически добавленные в избранное каналы<br>

Чтобы создать рабочую группу руководителей, используя стандартные значения из предопределенного шаблона, укажите в тексте запроса представление JSON объекта группы. Чтобы узнать больше о том, как развертывать шаблоны групп, ознакомьтесь со [статьей Microsoft Graph по созданию групп](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

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

Шаблон группы "Отдел" можно использовать для создания группы для отдельных отделов или для проектов. Шаблон "Финансы" идеально подходит для всех сообщений, объявлений и ежедневной совместной работы, а также общения между участниками группы "Финансы" (и, соответственно, участниками группы). Шаблон сопровождается *личным* каналом, с помощью которого можно пригласить пользователей в конкретные темы. Кроме того, мы предоставляем ниже сценарий для группы "Финансы", который можно использовать для продления шаблона до дополнительных отделов или конкретных проектов с помощью добавления, удаления или изменения. Например, если у вас есть отдел *маркетинга* , вы можете адаптировать сценарий, переименование команды из *финансового* в *маркетинг* для создания новой маркетинговой группы

| Тип базового шаблона | baseTemplateId | Свойства, которые поставляются с этим базовым шаблоном |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| Файл <br>Финансы  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| Каналы <ul><li>Общий\*</li><li>Конфиденциаль\*</li></ul><br> Приложения<ul><li>OneNote (закреплено в **частном** канале)</li> <li>Планировщик (закрепление в **частном** канале) </li> </ul><br>Свойства группы <ul><li>Для видимости команды установлено значение Private</li></ul> | 

* Автоматически добавленные в избранное каналы

Чтобы создать финансовую группу, используя стандартные значения из предопределенного шаблона, укажите в тексте запроса представление JSON объекта группы. Чтобы узнать больше о том, как развертывать шаблоны групп, ознакомьтесь со [статьей Microsoft Graph по созданию групп](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

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

### <a name="example-finance-team-template-extension-script"></a>Пример: сценарий расширения шаблона группы "Финансы"

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

- [Начало работы с шаблонами Teams](get-started-with-teams-templates.md)
- [Создание команды](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (в предварительной версии)

