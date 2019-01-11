---
title: Начало работы с группами шаблонов
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/10/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
localization_priority: Normal
robots: NOINDEX, NOFOLLOW
search.appverid: MET150
description: Узнайте, как использовать шаблоны группы для создания группы с предварительно определенные каналы.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: ead0a3dc9e27b90c49808bcece0aab39bf01f13a
ms.sourcegitcommit: 4c5b9e8c4bdb1187d610209d365680702d4372fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2019
ms.locfileid: "27801466"
---
# <a name="get-started-with-teams-templates"></a>Начало работы с группами шаблонов 

Шаблоны группы — это готовые основе определения структуры группы, созданная на основе потребность или проекта. Шаблоны группы можно использовать для быстрого создания пробелы расширенными возможностями совместной работы с каналами для разных тем и Предустановка приложений для работы на критически важных контент и службы. Шаблоны группы предоставить структуру предварительно определенные группы, которая поможет вам легко создавать согласованные группам в организации. 

В этой статье мы расскажем свойства, которые могут быть определены в шаблонах, какие базового шаблона, все типы, и как можно использовать несколько примеров запросов на создание группы на основе шаблона.
 
Эта статья является для вас, если вы:

- Ответственность за планирование, развертывание и управление нескольких групп в организации<br>
- Разработчик, которым требуется для программного создания группы с предварительно определенные каналы и приложений 

## <a name="teams-template-capabilities"></a>Возможности шаблон группы

Большинство свойств в группе включены и поддерживаются в шаблонах. Однако некоторые свойства и функции, которые в настоящее время не поддерживается. Ниже приведены краткая сводка того, что реализовано и что не входит в группы шаблонов.

| **Свойства группы, поддерживаемые шаблоны группы** | **Свойства группы еще не поддерживаются шаблонами групп** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Тип базового шаблона | Членство в группы |
| Название команды | Изображение группы |
| Описание группы | Параметры канала |
| Группа видимости (public или private) | Соединители |
| Параметры группы (например, элемент, гостевой @ упоминания) | Файлы и контента |
| Auto избранного канала | |
| Установленного приложения | |
| Закрепленные вкладок | | 

> [!NOTE]
> Мы будем Добавление дополнительные возможности шаблона в будущих версиях Microsoft групп, поэтому советуем обновленные сведения о поддерживаемых свойств.

## <a name="what-are-base-template-types"></a>Что такое типы базового шаблона?

Типы базового шаблона — это специальные шаблоны, которые созданы Microsoft для конкретных отраслей. Эти шаблоны базового часто содержит собственный приложения, которые не доступны в свойства хранилища и группы, которые еще не поддерживаются по отдельности в шаблонах группами.

После определения типа базового шаблона можно расширить или переопределить эти специальные шаблоны, с помощью дополнительных свойств, которые вы хотите указать. Однако некоторые типы базового шаблона содержит свойства, которые не может быть переопределен. 

По умолчанию базового шаблона — это значение **Standard** которого не содержит все дополнительные специализированных приложений или специальные свойства. Ниже текущего списка шаблонов базовые типы недоступны.

| Тип базового шаблона | Идентификатор базового шаблона | Базовый шаблон собственные приложения и специальные свойства |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`standard` | Нет дополнительных приложений и свойства |
| Образование- <br>Класс группы<sup>1</sup> | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationClass` | Приложения:<ul><li>Записной книжке OneNote класс (прикрепленных к вкладке « **Общие** ») </li><li>Назначения приложения (прикрепленных к вкладке « **Общие** »)</li></ul> Свойства группы:<ul><li>Группа видимости, задайте значение **HiddenMembership** (не может быть переопределен)</li></ul> |
| Образование-<br>Персонал группы<sup>1</sup> | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationStaff` | Приложения:<ul><li>Записной книжке OneNote персонала (прикрепленных к вкладке « **Общие** »)</li></ul> |
|Образование-<br>Группа PLC |`https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationProfessionalLearningCommunity` | Приложения:<ul><li>Записной книжке OneNote PLC (прикрепленных к вкладке « **Общие** »)</ul></li>|
|||

<sup>1</sup> публикации в конце октября 2018 г.

> [!NOTE]
> Мы будем добавлять дополнительные базового шаблона в следующих типов выпусков группами Майкрософт, чтобы проверять обратно на самые последние сведения о поддерживаемых свойств.

## <a name="examples"></a>Примеры 

Можно начать с помощью шаблона для создания группы с помощью [Microsoft Graph API](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

### <a name="create-a-team-from-a-template"></a>Создание группы на основе шаблона

#### <a name="requests"></a>Запросы

**Запрос на создание группы с помощью стандартных базового шаблона**

~~~
POST /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates/standard",
  "displayName": "Sample Team",
  "description": "Sample Team’s Description"
}

~~~

**Запрос на создание группы с помощью дополнительных канала и запретить члены из каналы**

~~~
POST /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates/standard",
  "displayName": "My Sample Team",
  "description": "My Sample Team’s Description",
  "channels": [
    {
        "displayName": "Random",
        "isFavoriteByDefault": true
    }
              ],
    "memberSettings": {
        "allowDeleteChannels": false
    }
}

~~~

**Запрос на создание группы Все поддерживаемые свойства**

~~~
POST /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('standard')",
    "visibility": "Private",
    "displayName": "Sample Engineering Team",
    "description": "This is a sample engineering team, used to showcase the range of properties 
supported by this API",
    "channels": [
        {
            "displayName": "Announcements 📢",
            "isFavoriteByDefault": true,
            "description": "This is a sample announcements channel that is favorited by default. Use this 
channel to make important team, product, and service announcements."
        },
        {
            "displayName": "Training 🏋️",
            "isFavoriteByDefault": true,
            "description": "This is a sample training channel that is favorited by default and contains an 
example of pinned website and YouTube tabs.",
            "tabs": [
                {
                    "teamsApp@odata.bind":
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.web')",
                   "name": "A Pinned Website",
                    "configuration": {
                        "contentUrl": "https://docs.microsoft.com/en-us/microsoftteams/microsoft-teams"
                    }
                },
                {
                    "teamsApp@odata.bind": 
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.youtube')",
                    "name": "A Pinned YouTube Video",
                    "configuration": {
                        "contentUrl": "https://tabs.teams.microsoft.com/Youtube/Home/YoutubeTab?
videoId=X8krAMdGvCQ",
                        "websiteUrl": "https://www.youtube.com/watch?v=X8krAMdGvCQ"
                    }
                }
            ]
        },
        {
"displayName": "Planning 📅 ",
            "description": "This is a sample of a channel that is not favorited by default, these channels 
will appear in the more channels overflow menu.",
            "isFavoriteByDefault": false
        },
        {
            "displayName": "Issues and Feedback 🐞",
            "description": "This is a sample of a channel that is not favorited by default, these channels 
will appear in the more channels overflow menu."
        }
    ],
    "memberSettings": {
        "allowCreateUpdateChannels": true,
        "allowDeleteChannels": true,
        "allowAddRemoveApps": true,
        "allowCreateUpdateRemoveTabs": true,
        "allowCreateUpdateRemoveConnectors": true
    },
    "guestSettings": {
        "allowCreateUpdateChannels": false,
        "allowDeleteChannels": false
    },
    "funSettings": {
        "allowGiphy": true,
        "giphyContentRating": "Moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
    },
    "messagingSettings": {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
    },
    "installedApps": [
        {
            "teamsApp@odata.bind": 
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.vsts')"
        },
        {
            "teamsApp@odata.bind": 
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('1542629c-01b3-4a6d-8f76-1938b779e48d')"
        }
    ]
}
~~~

### <a name="get-status"></a>Получить сведения о состоянии

#### <a name="request"></a>Запрос

~~~
GET   /workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa
Authorization: Bearer <TOKEN>
~~~

#### <a name="response"></a>Response (Ответ)

~~~
HTTP/1.1 200 OK
Content-Type: application/json
{
    "status": "[InProgress|Completed|Cancelled|Failed]"
}
~~~

## <a name="related-topics"></a>Связанные разделы

- [Создание группы](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (в предварительной версии)
- [Новые группы](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [Обучение администратора для работы с Microsoft Teams](itadmin-readiness.md)