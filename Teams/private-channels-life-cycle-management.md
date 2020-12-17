---
title: Управление жизненным циклом закрытых каналов в Microsoft Teams
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
localization_priority: Normal
search.appverid: MET150
description: Сведения об управлении жизненным циклом закрытых каналов в организации.
ms.openlocfilehash: 336d97071c30bca145d26f4c853d5bb30265721f
ms.sourcegitcommit: 68dffc3aca46992448bc2be0689bfd352e016316
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/08/2020
ms.locfileid: "49601664"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a>Управление жизненным циклом закрытых каналов в Microsoft Teams

В этой статье приводятся необходимые инструкции по управлению жизненным циклом [закрытых каналов](private-channels.md) в организации.

> [!IMPORTANT]
> Чтобы использовать PowerShell для управления закрытыми каналами, как описано в этой статье, нужно установить и использовать модуль общедоступной предварительной версии PowerShell для Teams из [коллекции PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/). Инструкции по установке модуля см. в статье [Установка PowerShell для Teams](teams-powershell-install.md). Модуль последней общедоступной версии PowerShell для Teams не поддерживает управление закрытыми каналами.

## <a name="set-whether-team-members-can-create-private-channels"></a>Укажите, могут ли участники команды создавать закрытые каналы

Владельцы команды могут включить или отключить возможность создания закрытых каналов для участников в параметрах команды. Для этого на вкладке **Параметры** команды включите или отключите параметр **Разрешить участникам создавать закрытые каналы**.

Администратор может управлять возможностью создания закрытых каналов для членов конкретных команд с помощью API Graph. Приведем пример.

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a>Укажите, могут ли пользователи в вашей организации создавать закрытые каналы

Администратор может задать политики с помощью Центра администрирования Microsoft Teams или PowerShell, чтобы выбрать пользователей в организации, которым разрешено создавать закрытые каналы.

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

Используйте политики команд, чтобы указать пользователей в организации, которым разрешено создавать закрытые каналы. Дополнительные сведения см. в статье [Управление политиками команд в Teams](teams-policies.md).

### <a name="using-powershell"></a>С помощью PowerShell

Используйте **CsTeamsChannelsPolicy**, чтобы указать пользователей в организации, которым разрешено создавать закрытые каналы. Задайте значение **true** для параметра **AllowPrivateChannelCreation**, чтобы разрешить пользователям, которым назначена политика, создавать закрытые каналы. Если для этого параметра задать значение **false**, возможность создания закрытых каналов будет отключена для пользователей, которым назначена политика.

Дополнительные сведения см. в статье [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a>Создайте закрытый канал от имени владельца команды

Администратор может создать закрытый канал от имени владельца команды с помощью PowerShell или API Graph. Например, это можно сделать в случае централизации создания закрытых каналов в организации.

### <a name="using-powershell"></a>С помощью PowerShell

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName "<Channel_Name>" –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a>С помощью API Graph

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

Администратор может запросить эти URL-адреса с помощью команд PowerShell или API Graph.

### <a name="using-powershell"></a>С помощью PowerShell

1. Установите [командную консоль SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) и подключитесь к ней с учетной записью администратора.
2. Выполните следующие команды, где &lt;group_id&gt; — ИД группы. (Вы легко найдете ИД группы в ссылке на команду.)

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a>С помощью API Graph

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

Администратор может выполнить эти действия с помощью Центра администрирования Microsoft Teams, PowerShell или API Graph.

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

Сведения об управлении участниками команды с помощью Центра администрирования Microsoft Teams см. в статье [Управление командами в Центре администрирования Microsoft Teams](manage-teams-in-modern-portal.md).

### <a name="using-powershell"></a>С помощью PowerShell

1. Выполните следующие команды, где &lt;group_id&gt; — ИД группы, а &lt;channel_name&gt; — имя канала.

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" 
    ```

2. Повысьте уровень участника до владельца.

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a>С помощью API Graph

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

- [Обзор PowerShell в Teams](teams-powershell-overview.md)
- [Использование Microsoft Graph API для работы с Teams](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [Перечисление каналов](https://docs.microsoft.com/graph/api/channel-list)
    - [Создание канала](https://docs.microsoft.com/graph/api/channel-post)
    - [Добавление участника в канал](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [Обновление участника в канале](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [Удаление участника из канала](https://docs.microsoft.com/graph/api/conversationmember-delete)
