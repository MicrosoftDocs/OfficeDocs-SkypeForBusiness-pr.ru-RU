---
title: Управление жизненным циклом частных каналов в Microsoft Teams
author: lanachin
ms.author: v-lanac
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
description: Сведения о том, как управлять жизненным циклом личных каналов в Организации.
ms.openlocfilehash: 39830035ba91b2fa50c7d5bbd82e6da6e60d0f00
ms.sourcegitcommit: 379bfaf6b0584c1ac93341af605f93ab932a442b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2020
ms.locfileid: "43240639"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a>Управление жизненным циклом частных каналов в Microsoft Teams

Здесь вы найдете рекомендации, которые необходимо выполнить для управления жизненным циклом [личных каналов](private-channels.md) в Организации.

> [!IMPORTANT]
> Если вы используете инструкции PowerShell, описанные в этой статье, для управления личными каналами, необходимо установить и использовать последнюю версию модуля Teams PowerShell из коллекции тестов PowerShell. Инструкции, описанные в этой статье, описаны в [статье Установка последней версии модуля PowerShell для Teams из коллекции тестов PowerShell](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery). Самая свежая доступная версия модуля PowerShell Teams (в настоящее время [1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3)) не поддерживает управление личными каналами.

## <a name="set-whether-team-members-can-create-private-channels"></a>Определение возможности создания личных каналов участниками группы

Владельцы групп могут включать и отключать возможность создания личных каналов для пользователей в параметрах группы. Для этого на вкладке Параметры для команды отключите или включите **параметр** **Разрешить участникам создавать закрытые каналы**.

Администраторы могут использовать Graph API для управления тем, могут ли участники создавать закрытые каналы в конкретных командах. Ниже приведен пример.

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a>Настройка возможности создания частных каналов для пользователей в Организации

Администраторы могут настроить политики с помощью центра администрирования Microsoft Teams или PowerShell, чтобы управлять тем, какие пользователи в организации могут создавать закрытые каналы.

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

Используйте политики Teams, чтобы настроить, какие пользователи в организации смогут создавать закрытые каналы. Дополнительные сведения можно найти в разделе [Управление политиками Teams в Teams](teams-policies.md).

### <a name="using-powershell"></a>Использование PowerShell

С помощью **CsTeamsChannelsPolicy** можно указать, какие пользователи в вашей организации могут создавать закрытые каналы. Установите для параметра **AllowPrivateChannelCreation** значение **true** , чтобы пользователи, которым назначена политика, могли создавать закрытые каналы. Если задать для параметра **значение false** , возможность создания частных каналов для пользователей, которым назначена политика, будет отключена.

Дополнительные сведения можно найти в статье [Создание и CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a>Создание закрытого канала от имени владельца команды

Администратор может использовать PowerShell или Graph API для создания закрытого канала от имени владельца команды. Например, это может потребоваться, если ваша организация хотела бы централизовать создание частных каналов.

### <a name="using-powershell"></a>Использование PowerShell

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName “<Channel_Name>” –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a>Использование Graph API

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

## <a name="get-a-list-of-all-private-channel-messages"></a>Получение списка всех сообщений личного канала

Для архивации и аудита может потребоваться просмотреть список всех сообщений и ответов, опубликованных в частном канале.  Ниже показано, как использовать Graph API.

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a>Поиск URL-адресов SharePoint для всех частных каналов в команде

Если вы собираетесь проводить обнаружение электронных данных или судебных удержаний по файлам в частном канале или собираетесь создавать бизнес-приложение, которое поместит файлы в определенные закрытые каналы, вам будет нужен запрос уникальных семейств сайтов SharePoint, создаваемых для каждого частного канала.

Администратор может использовать команды PowerShell или Graph API для запроса этих URL-адресов.

### <a name="using-powershell"></a>Использование PowerShell

1. Установите [консоль управления SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) и подключитесь к ней с помощью учетной записи администратора.
2. Запустите следующую команду, где &lt;group_id&gt; — идентификатор группы. (Идентификатор группы можно легко найти в ссылке на команду.)

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a>Использование Graph API

Эти команды можно выполнить с помощью [проводника диаграмм](https://developer.microsoft.com/graph/graph-explorer).

1. Воспользуйтесь приведенными ниже сведениями, чтобы получить список идентификаторов частных каналов для конкретной команды, где <group_id> является ИДЕНТИФИКАТОРом группы для группы. Это потребуется при последующих звонках. (Идентификатор группы можно легко найти в ссылке на команду).

    **Запрос**

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    **Response (Ответ)**

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

2. Для каждого закрытого канала, для которого требуется получить URL-адрес SharePoint, сделайте следующий запрос, &lt;где&gt; channel_id — идентификатор канала.

    **Запрос**

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    **Response (Ответ)**

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a>Перечисление и обновление ролей владельцев и участников в частном канале

Вам может потребоваться указать владельцев и участников закрытого канала, чтобы решить, нужно ли распространить определенных участников закрытого канала на владельца. Это может быть вызвано тем, что у вас есть владельцы частных каналов, которые оставили организацию и для личного канала требуется помощь администратора для утверждения прав собственности на канал.

Администратор может использовать команды PowerShell или Graph API для запроса этих URL-адресов.

### <a name="using-powershell"></a>Использование PowerShell

1. Запустите следующую команду, где &lt;group_id&gt; — идентификатор группы, а &lt;channel_name&gt; — имя канала.

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" 
    ```

2. Повышение роли участника до владельца.

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a>Использование Graph API

Эти команды можно выполнить с помощью [проводника диаграмм](https://developer.microsoft.com/graph/graph-explorer).

1. Используйте следующую команду, где &lt;group_id&gt; — идентификатор группы, а &lt;channel_id&gt; — идентификатор канала.

    **Запрос**

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    **Response (Ответ)**

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
2.  Используйте указанные ниже действия, чтобы повысить роль участника до владельца, &lt;где&gt;в &lt;предыдущем&gt;вызове &lt;возвращаются&gt; group_id, channel_id и идентификатор. Обратите &lt;внимание&gt; , &lt;что&gt; идентификатор и UserID, возвращенные из предыдущего звонка, не являются взаимозаменяемыми. Убедитесь, что вы &lt;используете&gt;ID.

    **Запрос**

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    **Response (Ответ)**

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

## <a name="teams-powershell-module"></a>Модуль PowerShell Teams

### <a name="install-the-latest-teams-powershell-module-from-the-powershell-test-gallery"></a>Установка новейшего модуля PowerShell для Teams из коллекции тестов PowerShell

Самая свежая доступная версия модуля PowerShell Teams (в настоящее время [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5)) не поддерживает управление личными каналами. Выполните указанные ниже действия, чтобы установить последнюю версию модуля PowerShell Teams с поддержкой частных каналов (в настоящее время 1.0.21) из коллекции тестов PowerShell.

> [!NOTE]
> Не устанавливайте модуль PowerShell Teams из коллекции тестов PowerShell рядом с версией модуля из общедоступной галереи PowerShell. Выполните эти действия, чтобы сначала удалить модуль Teams PowerShell из общедоступной коллекции PowerShell, а затем установить последнюю версию модуля из коллекции тестов PowerShell.

1. Закройте все существующие сеансы PowerShell.
2. Начните новый экземпляр модуля Windows PowerShell.
3. Выполните указанные ниже действия, чтобы удалить модуль PowerShell Teams из общедоступной галереи PowerShell.

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. Закройте все существующие сеансы PowerShell.
5. Запустите модуль Windows PowerShell еще раз, а затем выполните указанные ниже действия, чтобы зарегистрировать библиотеку тестов PowerShell в качестве надежного источника.

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. Выполните указанные ниже действия, чтобы установить последнюю версию модуля PowerShell для Teams из коллекции тестов PowerShell.

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. Выполните указанные ниже действия, чтобы убедиться в том, что новейшая версия модуля Teams PowerShell из коллекции тестов PowerShell успешно установлена.

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a>Обновите модуль PowerShell до последней версии из коллекции тестовых команд PowerShell.

Если вы уже установили модуль Teams PowerShell из коллекции тестов PowerShell, выполните указанные ниже действия, чтобы обновить его до последней версии.

1. Закройте все существующие сеансы PowerShell.
2. Начните новый экземпляр модуля Windows PowerShell.
3. Выполните указанные ниже действия, чтобы обновить текущую установленную версию модуля PowerShell Teams из коллекции тестов PowerShell.

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. Выполните указанные ниже действия, чтобы убедиться в том, что новейшая версия модуля Teams PowerShell из коллекции тестов PowerShell успешно установлена.

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="related-topics"></a>Статьи по теме

- [Обзор PowerShell в Teams](teams-powershell-overview.md)
- [Использование Microsoft Graph API для работы с Teams](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [Каналы списка](https://docs.microsoft.com/graph/api/channel-list)
    - [Создать канал](https://docs.microsoft.com/graph/api/channel-post)
    - [Добавить участника в канал](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [Обновить пользователя в канале](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [Удалить участника из канала](https://docs.microsoft.com/graph/api/conversationmember-delete)
