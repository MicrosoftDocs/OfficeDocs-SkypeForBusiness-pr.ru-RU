---
title: Управление частными каналами в Microsoft Teams с помощью Graph API
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
ms.reviewer: suchakr, phlouie
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Узнайте, как управлять частными каналами в организации с Graph API.
ms.openlocfilehash: a2cb9b45afb005c837b260ac3da22c250d16c758
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615325"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a>Управление жизненным циклом закрытых каналов в Microsoft Teams

Здесь вы найдете рекомендации, необходимые для управления использованием API Graph API для управления Teams каналов [в](./private-channels.md) организации.

## <a name="set-whether-team-members-can-create-private-channels"></a>Укажите, могут ли участники команды создавать закрытые каналы

Администратор может управлять возможностью создания закрытых каналов для членов конкретных команд с помощью API Graph. Приведем пример.

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a>Создайте закрытый канал от имени владельца команды

Администраторы могут использовать API Graph для создания закрытого канала от имени владельца команды. Например, это можно сделать в случае централизации создания закрытых каналов в организации.

```Graph API
POST /teams/{id}/channels
{ "membershipType": "Private",
  "displayName": "<Channel_Name>",
  "members":[{    
           "@odata.type":"#microsoft.graph.aadUserConversationMember",
           "user@odata.bind":"https://graph.microsoft.com/beta/users('<user_id>')",
           "roles":["owner"]
            }]
```

## <a name="get-a-list-of-all-private-channel-messages"></a>Получите список всех сообщений закрытого канала

В целях архивирования и аудита вам может понадобиться список всех сообщений и ответов, опубликованных в закрытом канале.  Ниже описывается, как получить список с помощью API Graph.

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a>Найдите URL-адреса SharePoint для всех закрытых каналов в команде

Требуется ли выполнить обнаружение электронных данных или удержание по юридическим причинам для файлов в закрытом канале либо создать пользовательское приложение, которое помещает файлы в определенные закрытые каналы, вам понадобится запросить уникальные семейства веб-сайтов SharePoint, которые создаются для каждого закрытого канала.

Как администратор вы можете использовать Graph API для запроса этих URL-адресов.

Эти команды можно выполнить, используя [песочницу Graph](https://developer.microsoft.com/graph/graph-explorer).

1. Чтобы получить список ИД закрытых каналов для определенной команды, используйте следующие команды, где <group_id> — ИД группы. Вам потребуется эта информация для последующих вызовов. (Вы легко найдете ИД группы в ссылке на команду.)

    **Запрос**

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    **Ответ**

    ```Graph API
    HTTP/1.1 200 OK
    Content-type: application/json
    Content-length:
    
    {
      "value": [
        {
          "description": "description-value",
          "displayName": "display-name-value",
          "id": "channel_id",
          "membershipType": "membership-type-value",
          "isFavoriteByDefault": false,
          "webUrl": "webUrl-value",
          "email": "email-value"
        }
      ]
    }
    ```

2. Для каждого закрытого канала, для которого нужно получить URL-адрес SharePoint, выполните следующий запрос, где &lt;channel_id&gt; — ИД канала.

    **Запрос**

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    **Ответ**

    ```Graph API
    HTTP/1.1 200 OK
    Content-type: application/json
    Content-length:
      
    {
      "value": [
        {
          "description": "description-value",
          "displayName": "display-name-value",
          "id": "channel_id",
          "membershipType": "membership-type-value",
          "isFavoriteByDefault": false,
          "webUrl": "webUrl-value",
          "email": "email-value"
        }
      ]
    }
    ```

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a>Составьте список и обновите роли владельцев и участников в закрытом канале

Возможно, вы хотите составить список владельцев и участников закрытого канала, чтобы решить, нужно ли повысить уровень некоторых участников до владельца. Это происходит в тех случаях, когда владельцы закрытых каналов покинули организацию и необходима помощь администратора, чтобы заявить о праве собственности на закрытый канал.

Администратор может использовать API Graph для выполнения этих действий.

Эти команды можно выполнить, используя [песочницу Graph](https://developer.microsoft.com/graph/graph-explorer).

1. Используйте следующие команды, где &lt;group_id&gt; — ИД группы, а &lt;channel_id&gt; — ИД канала.

    **Запрос**

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```

    **Ответ**

    ```Graph API
    HTTP/1.1 200 OK Content-type: application/json
    Content-length: 
    {
          "@odata.context": "https://graph.microsoft.com/beta/$metadata#teams({group_id}')/channels('{channel_id}')/members",
          "@odata.count": 2,
          "value": [
              {
                  "@odata.type": "#microsoft.graph.aadUserConversationMember",
                  "id": "id-value",
                  "roles": [],
                  "displayName": "display-name-value",
                  "userId": "userId-value",
                  "email": "email-value"
              },
              {
                  "@odata.type": "#microsoft.graph.aadUserConversationMember",
              "id": "id-value",
              "roles": ["owner"],
              "displayName": "display-name-value",
              "userId": "userId-value",
              "email": "email-value"
              }
          ]
    }
    ```

2. Чтобы повысить уровень участника до владельца, используйте следующие команды, где &lt;group_id&gt;, &lt;channel_id&gt; и &lt;id&gt; возвращаются из предыдущего вызова. Обратите внимание, что &lt;id&gt; и &lt;userId&gt;, возвращенные из предыдущего вызова, не совпадают и не являются взаимозаменяемыми. Убедитесь, что вы используете &lt;id&gt;.

    **Запрос**

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    **Ответ**

    ```Graph API
    HTTP/1.1 200 OK
    Content-type: application/json

    {
      "@odata.context": "https://graph.microsoft.com/beta/$metadata#teams('{group_id}')/channels('{channel_id}')/members/$entity",
      "@odata.type": "#microsoft.graph.aadUserConversationMember",
      "id": "id-value",
      "roles": ["owner"],
      "displayName": "display-name-value",
      "userId": "userId-value",
      "email": "email-value"
     }
    ```

## <a name="related-topics"></a>Статьи по теме

[Использование Microsoft Graph API для работы с Teams](/graph/api/resources/teams-api-overview?view=graph-rest-1.0)

[Перечисление каналов](/graph/api/channel-list)

[Создание канала](/graph/api/channel-post)

[Добавление участника в канал](/graph/api/conversationmember-add)

[Обновление участника в канале](/graph/api/conversationmember-update)

[Удаление участника из канала](/graph/api/conversationmember-delete)