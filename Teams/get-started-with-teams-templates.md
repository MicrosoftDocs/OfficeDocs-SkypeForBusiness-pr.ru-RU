---
title: Начало работы с группами шаблонов
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/12/2018
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
ms.openlocfilehash: 151a789b6047540071aa5780fb81a895503dd70b
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2018
ms.locfileid: "25838893"
---
# <a name="get-started-with-teams-templates"></a>Начало работы с группами шаблонов 

Шаблоны группы — это готовые основе определения структуры группы, созданная на основе потребность или проекта. Шаблоны группы можно использовать для быстрого создания пробелы расширенными возможностями совместной работы с каналами для разных тем и Предустановка приложений для работы на критически важных контент и службы. Шаблоны группы предоставить структуру предварительно определенные группы, которая поможет вам легко создавать согласованные группам в организации. 

В этой статье мы расскажем свойства, которые могут быть определены в шаблонах, какие базового шаблона, все типы, и как можно использовать несколько примеров запросов на создание группы на основе шаблона.
 
Эта статья является для вас, если вы:

• Ответственность за планирования, развертывания и управления несколькими группами в рамках разработчиков • A вашей организации нужна для создания группы с предопределенное каналы и приложения программными средствами

## <a name="team-template-capabilities"></a>Возможности шаблон группы

Большинство свойств в группе включены и поддерживаются в шаблонах. Однако есть некоторые свойства и функции, которые в настоящее время не поддерживаются. Ниже приведены краткая сводка того, что реализовано и что не входит в группы шаблонов.

| **Свойства группы, поддерживаемые шаблоны группы** | **Свойства группы еще не поддерживаются шаблонами групп** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Тип базового шаблона | Членство в группы |
| Название команды | Изображение группы |
| Описание группы | Параметры канала (, например auto Избранное и конфиденциальность) |
| Группа видимости (public или private) | Соединители |
| Параметры группы (например, элемент, гостевой @ упоминания) | Файлы и контента |
| Auto избранного канала | |
| Установленного приложения | |
| Закрепленные вкладок | | 

> [!NOTE]
> Мы будем Добавление дополнительные возможности шаблона в будущих версиях Microsoft групп, поэтому советуем обновленные сведения о поддерживаемых свойств.

## <a name="what-are-base-template-types"></a>Что такое типы базового шаблона?

Типы базового шаблона — это специальные шаблоны, которые созданы Microsoft для конкретных отраслей. Эти шаблоны базового часто содержит собственный приложения, которые не доступны в свойства хранилища и группы, еще не поддерживаются в шаблонах группами по отдельности.

После определения типа базового шаблона можно расширить или переопределить эти специальные шаблоны, с помощью дополнительных свойств, которые вы хотите указать. Тем не менее некоторые типы базового шаблона содержит свойства, которые нельзя переопределить. 

По умолчанию базового шаблона — это значение **Standard** которого не содержит все дополнительные специализированных приложений или специальные свойства. Ниже текущего списка шаблонов базовые типы недоступны.

| Тип базового шаблона | Идентификатор базового шаблона | Базовый шаблон собственные приложения и специальные свойства |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json) | Нет дополнительных приложений и свойства |
| Здравоохранение - медицинскими координация | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-CC.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-CC.json#) | Приложения:<br/> -Приложение пострадавших (прикрепленных к вкладке « **Общие** »)<br/> <br/>Каналы: <br/> -Объявления<br/> -Diabetes<br/> -Cardiovascular<br/> -Зарегистрированные медсестры |
| Здравоохранение - ютиться процесса | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-PH.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-PH.json#) | Каналы:<br/> -Вызывает писателем в мире<br/> -Обзор mortality <br/> -Предотвращение представлена <br/> -Планы sepsis |
| Образование - класс группы<sup>1</sup> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-CT.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-CT.json#) | Приложения:<br/> -Класс заметки (прикрепленных к вкладке « **Общие** ») <br/> -Приложение назначений (прикрепленных к вкладке « **Общие** ») <br/><br/> Свойства группы <br/> -Задайте значение **HiddenMembership** (не может быть переопределен) видимости подключения группой разработки |
| Образование - персонала группы<sup>1</sup> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-ST.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-ST.json#) | Приложения<br/> -Персонала заметки (прикрепленных к вкладке « **Общие** ») |

<sup>1</sup> публикации в конце октября 2018 г.

> [!NOTE]
> Мы будем добавлять дополнительные базового шаблона в следующих типов выпусков группами Майкрософт, чтобы проверять обратно на самые последние сведения о поддерживаемых свойств.

## <a name="examples"></a>Примеры 

Можно приступать к созданию группы с помощью шаблона, установив [Microsoft Graph](https://developer.microsoft.com/en-us/graph/docs/concepts/overview).

### <a name="create-a-team-from-a-template"></a>Создание группы на основе шаблона

#### <a name="requests"></a>Запросы

**Запрос на создание группы с помощью стандартных базового шаблона**

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
    
    "teamDisplayName": "My Sample Team",
    "teamDescription": "My Sample Team’s Description",
}

~~~

**Запрос на создание группы с помощью дополнительных канала и запретить члены из каналы**

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
    
    "teamDisplayName": "My Sample Team",
    "teamDescription": "My Sample Team’s Description",
    "channels": [
        {
            "displayName": "Interns",
            "autoFavorite": false
        }
    ],
    "memberSettings": {
        "allowDeleteChannels": false,
    }
}

~~~

**Запрос на создание группы Все поддерживаемые свойства**

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
 
    "teamType": "Healthcare_CareCoordination",
    "visibility": "Private",
    "teamDisplayName": "My Care Team",
    "teamDescription": "My Care Team’s description",
 
    "channels": [
        {
            "displayName": "General  ",
            "autoFavorite": true,
            "tabs": [
                   {
                       "appId": "0d820ecd-def2-4297-adad-78056cde7c78",
                       "tabDisplayName": "Intranet”
                   }
               ]
        },
        {
            "displayName": "Announcements",
            "autoFavorite": true
        },
        {
            "displayName": "Diabetes",
            "autoFavorite": true
        },
        {
            "displayName": "Cardiovascular",
            "autoFavorite": true
        },
        {
            "displayName": "Registered Nurses",
            "autoFavorite": true
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
 
      "messagingSettings": {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
      },
 
      "funSettings": {
        "allowGiphy": true,
        "giphyContentRating": "moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
      }
 
 
    "installedApplications": [
      {
        "id": "0d820ecd-def2-4297-adad-78056cde7c78"
      }
    ]
}
~~~

#### <a name="response"></a>Response (Ответ)

~~~
HTTP/1.1 202 Accepted
Content-Type: application/json
Location: /workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa
{
    "workflowId": "c953c202-7b44-4a63-aa33-364fcb2d65aa",
    "statusUri": "https://<apihostandpath>/workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa"
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

- [Создание группы](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/team_put_teams) (в предварительной версии)
- [Новые группы](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [Обучение ИТ-администратора для работы с Microsoft Teams](itadmin-readiness.md)