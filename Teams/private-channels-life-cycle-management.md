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
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Сведения о том, как управлять жизненным циклом личных каналов в Организации.
ms.openlocfilehash: 5fe3f29559e62b6b6b11833304aa7bb13206fe6a
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2019
ms.locfileid: "37969417"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="60297-103">Управление жизненным циклом частных каналов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="60297-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="60297-104">Здесь вы найдете рекомендации, которые необходимо выполнить для управления жизненным циклом [личных каналов](private-channels.md) в Организации.</span><span class="sxs-lookup"><span data-stu-id="60297-104">Here you'll find the guidance you need to manage the life cycle of [private channels](private-channels.md) in your organization.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="60297-105">Определение возможности создания личных каналов участниками группы</span><span class="sxs-lookup"><span data-stu-id="60297-105">Set whether team members can create private channels</span></span>

<span data-ttu-id="60297-106">Владельцы групп могут включать и отключать возможность создания личных каналов для пользователей в параметрах группы.</span><span class="sxs-lookup"><span data-stu-id="60297-106">Team owners can turn off or turn on the ability for members to create private channels in team settings.</span></span> <span data-ttu-id="60297-107">Для этого на вкладке Параметры для команды отключите или включите **параметр** **Разрешить участникам создавать закрытые каналы**.</span><span class="sxs-lookup"><span data-stu-id="60297-107">To do this, on the **Settings** tab for the team, turn off or turn on **Allow members to create private channels**.</span></span>

<span data-ttu-id="60297-108">Администраторы могут использовать Graph API для управления тем, могут ли участники создавать закрытые каналы в конкретных командах.</span><span class="sxs-lookup"><span data-stu-id="60297-108">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="60297-109">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="60297-109">Here's an example.</span></span>

```
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a><span data-ttu-id="60297-110">Настройка возможности создания частных каналов для пользователей в Организации</span><span class="sxs-lookup"><span data-stu-id="60297-110">Set whether users in your organization can create private channels</span></span>

<span data-ttu-id="60297-111">Администраторы могут настроить политики с помощью центра администрирования Microsoft Teams или PowerShell, чтобы управлять тем, какие пользователи в организации могут создавать закрытые каналы.</span><span class="sxs-lookup"><span data-stu-id="60297-111">As an admin, you can set policies by using the Microsoft Teams admin center or PowerShell to control which users in your organization are allowed to create private channels.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="60297-112">Использование центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="60297-112">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="60297-113">Используйте политики Teams, чтобы настроить, какие пользователи в организации смогут создавать закрытые каналы.</span><span class="sxs-lookup"><span data-stu-id="60297-113">Use teams policies to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="60297-114">Дополнительные сведения можно найти в разделе [Управление политиками Teams в Teams](teams-policies.md).</span><span class="sxs-lookup"><span data-stu-id="60297-114">To learn more, see [Manage teams policies in Teams](teams-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="60297-115">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="60297-115">Using PowerShell</span></span>

<span data-ttu-id="60297-116">С помощью **кстеамсчаннелсполици** можно указать, какие пользователи в вашей организации могут создавать закрытые каналы.</span><span class="sxs-lookup"><span data-stu-id="60297-116">Use **CsTeamsChannelsPolicy** to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="60297-117">Установите для параметра **алловприватечаннелкреатион** значение **true** , чтобы пользователи, которым назначена политика, могли создавать закрытые каналы.</span><span class="sxs-lookup"><span data-stu-id="60297-117">Set the **AllowPrivateChannelCreation** parameter to **true** to allow users who are assigned the policy to create private channels.</span></span> <span data-ttu-id="60297-118">Если задать для параметра **значение false** , возможность создания частных каналов для пользователей, которым назначена политика, будет отключена.</span><span class="sxs-lookup"><span data-stu-id="60297-118">Setting the parameter to **false** turns off the ability to create private channels for users who are assigned the policy.</span></span>

<span data-ttu-id="60297-119">Дополнительные сведения можно найти в статье [Создание и кстеамсчаннелсполици](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="60297-119">To learn more, see [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span></span>

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="60297-120">Создание закрытого канала от имени владельца команды</span><span class="sxs-lookup"><span data-stu-id="60297-120">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="60297-121">Администратор может использовать PowerShell или Graph API для создания закрытого канала от имени владельца команды.</span><span class="sxs-lookup"><span data-stu-id="60297-121">As an admin, you can use PowerShell or Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="60297-122">Например, это может потребоваться, если ваша организация хотела бы централизовать создание частных каналов.</span><span class="sxs-lookup"><span data-stu-id="60297-122">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="60297-123">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="60297-123">Using PowerShell</span></span>

```
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName “<Channel_Name>” –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a><span data-ttu-id="60297-124">Использование Graph API</span><span class="sxs-lookup"><span data-stu-id="60297-124">Using Graph API</span></span>

```
POST /teams/{id}/channels
{ "membershipType": "Private",
  "displayName": "<Channel_Name>",
  "members":[{    
           "@odata.type":"#microsoft.graph.aadUserConversationMember",
           "user@odata.bind":"https://graph.microsoft.com/beta/users('<user_id>')",
           "roles":["owner"]
            }]
```

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="60297-125">Получение списка всех сообщений личного канала</span><span class="sxs-lookup"><span data-stu-id="60297-125">Get a list of all private channel messages</span></span>

<span data-ttu-id="60297-126">Для архивации и аудита может потребоваться просмотреть список всех сообщений и ответов, опубликованных в частном канале.</span><span class="sxs-lookup"><span data-stu-id="60297-126">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="60297-127">Ниже показано, как использовать Graph API.</span><span class="sxs-lookup"><span data-stu-id="60297-127">Here's how to use Graph API to do this.</span></span>

```
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="60297-128">Поиск URL-адресов SharePoint для всех частных каналов в команде</span><span class="sxs-lookup"><span data-stu-id="60297-128">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="60297-129">Если вы собираетесь проводить обнаружение электронных данных или судебных удержаний по файлам в частном канале или собираетесь создавать бизнес-приложение, которое поместит файлы в определенные закрытые каналы, вам будет нужен способ запроса уникальных семейств веб-сайтов SharePoint, созданных для Каждый частный канал.</span><span class="sxs-lookup"><span data-stu-id="60297-129">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a line-of-business app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="60297-130">Администратор может использовать команды PowerShell или Graph API для запроса этих URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="60297-130">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="60297-131">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="60297-131">Using PowerShell</span></span>

1. <span data-ttu-id="60297-132">Установите [консоль управления SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) и подключитесь к ней с помощью учетной записи администратора.</span><span class="sxs-lookup"><span data-stu-id="60297-132">Install and connect to the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) with your admin account.</span></span>
2. <span data-ttu-id="60297-133">Запустите следующую команду, где &lt;group_id&gt; — это идентификатор группы.</span><span class="sxs-lookup"><span data-stu-id="60297-133">Run the following, where &lt;group_id&gt; is the group Id of the team.</span></span> <span data-ttu-id="60297-134">(Идентификатор группы можно легко найти в ссылке на команду.)</span><span class="sxs-lookup"><span data-stu-id="60297-134">(You can easily find the group Id in the link to the team.)</span></span>

    ```
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a><span data-ttu-id="60297-135">Использование Graph API</span><span class="sxs-lookup"><span data-stu-id="60297-135">Using Graph API</span></span>

<span data-ttu-id="60297-136">Эти команды можно выполнить с помощью [проводника диаграмм](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="60297-136">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="60297-137">Воспользуйтесь приведенными ниже сведениями, чтобы получить список идентификаторов частных каналов для конкретной команды, где <group_id> является идентификатором группы для группы.</span><span class="sxs-lookup"><span data-stu-id="60297-137">Use the following to get the list of private channel Ids for a given team, where <group_id> is the group Id of the team.</span></span> <span data-ttu-id="60297-138">Это потребуется при последующих звонках.</span><span class="sxs-lookup"><span data-stu-id="60297-138">You'll need this in subsequent calls.</span></span> <span data-ttu-id="60297-139">(Идентификатор группы можно легко найти в ссылке на команду).</span><span class="sxs-lookup"><span data-stu-id="60297-139">(You can easily find the group Id in the link to the team).</span></span>

    <span data-ttu-id="60297-140">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="60297-140">**Request**</span></span>

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="60297-141">**Response (Ответ)**</span><span class="sxs-lookup"><span data-stu-id="60297-141">**Response**</span></span>

    ```
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

2. <span data-ttu-id="60297-142">Для каждого закрытого канала, для которого требуется получить URL-адрес SharePoint, сделайте следующий запрос, &lt;где&gt; channel_id — идентификатор канала.</span><span class="sxs-lookup"><span data-stu-id="60297-142">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel Id.</span></span>

    <span data-ttu-id="60297-143">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="60297-143">**Request**</span></span>

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="60297-144">**Response (Ответ)**</span><span class="sxs-lookup"><span data-stu-id="60297-144">**Response**</span></span>

    ```
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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="60297-145">Перечисление и обновление ролей владельцев и участников в частном канале</span><span class="sxs-lookup"><span data-stu-id="60297-145">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="60297-146">Вам может потребоваться указать владельцев и участников закрытого канала, чтобы решить, нужно ли распространить определенных участников закрытого канала на владельца.</span><span class="sxs-lookup"><span data-stu-id="60297-146">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="60297-147">Это может быть вызвано тем, что у вас есть владельцы частных каналов, которые оставили организацию и для личного канала требуется помощь администратора для утверждения прав собственности на канал.</span><span class="sxs-lookup"><span data-stu-id="60297-147">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="60297-148">Администратор может использовать команды PowerShell или Graph API для запроса этих URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="60297-148">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="60297-149">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="60297-149">Using PowerShell</span></span>

1. <span data-ttu-id="60297-150">Установите и подключитесь к [модулю Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) с учетной записью администратора.</span><span class="sxs-lookup"><span data-stu-id="60297-150">Install and connect to the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) with your admin account.</span></span>
2. <span data-ttu-id="60297-151">Выполните следующую команду, где &lt;group_id&gt; — это идентификатор группы, а &lt;channel_id&gt; — идентификатор канала.</span><span class="sxs-lookup"><span data-stu-id="60297-151">Run the following, where &lt;group_id&gt; is the group Id of the team and &lt;channel_id&gt; is the channel Id.</span></span>

    <span data-ttu-id="60297-152">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="60297-152">**Request**</span></span>

    ```
    Get-TeamChannelUser -GroupId <group_id> -MembershipType Private -DisplayName "<channel_name>" 
    ```
    
    <span data-ttu-id="60297-153">**Response (Ответ)**</span><span class="sxs-lookup"><span data-stu-id="60297-153">**Response**</span></span>

    ```
    HTTP/1.1 200 OK Content-type: application/json
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

3. <span data-ttu-id="60297-154">Повышение роли участника до владельца.</span><span class="sxs-lookup"><span data-stu-id="60297-154">Promote a member to an owner.</span></span>

    ```
    Add-TeamChannelUser -GroupId <group_id> -MembershipType Private -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a><span data-ttu-id="60297-155">Использование Graph API</span><span class="sxs-lookup"><span data-stu-id="60297-155">Using Graph API</span></span>

<span data-ttu-id="60297-156">Эти команды можно выполнить с помощью [проводника диаграмм](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="60297-156">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="60297-157">Используйте следующую команду, где &lt;Group_id&gt; — идентификатор группы, а &lt;channel_id&gt; — идентификатор канала.</span><span class="sxs-lookup"><span data-stu-id="60297-157">Use the following, where &lt;group_id&gt; is the group Id of the team and &lt;channel_id&gt; is the channel Id.</span></span>

    <span data-ttu-id="60297-158">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="60297-158">**Request**</span></span>

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="60297-159">**Response (Ответ)**</span><span class="sxs-lookup"><span data-stu-id="60297-159">**Response**</span></span>

    ```
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
2.  <span data-ttu-id="60297-160">Используйте указанные ниже действия, чтобы повысить роль участника до владельца, &lt;где&gt;group_id &lt;,&gt;channel_id и &lt;ID&gt; будут возвращены из предыдущего звонка.</span><span class="sxs-lookup"><span data-stu-id="60297-160">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="60297-161">Обратите &lt;внимание&gt; , &lt;что&gt; идентификатор и UserID, возвращенные из предыдущего звонка, не являются взаимозаменяемыми.</span><span class="sxs-lookup"><span data-stu-id="60297-161">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="60297-162">Убедитесь, что вы &lt;используете&gt;ID.</span><span class="sxs-lookup"><span data-stu-id="60297-162">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="60297-163">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="60297-163">**Request**</span></span>

    ```
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="60297-164">**Response (Ответ)**</span><span class="sxs-lookup"><span data-stu-id="60297-164">**Response**</span></span>

    ```
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

## <a name="related-topics"></a><span data-ttu-id="60297-165">См. также</span><span class="sxs-lookup"><span data-stu-id="60297-165">Related topics</span></span>

- [<span data-ttu-id="60297-166">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="60297-166">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="60297-167">Использование API Microsoft Graph для работы с Teams</span><span class="sxs-lookup"><span data-stu-id="60297-167">Use the Microsoft Graph API to work with Teams</span></span>](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [<span data-ttu-id="60297-168">Каналы списка</span><span class="sxs-lookup"><span data-stu-id="60297-168">List channels</span></span>](https://docs.microsoft.com/graph/api/channel-list)
    - [<span data-ttu-id="60297-169">Создать канал</span><span class="sxs-lookup"><span data-stu-id="60297-169">Create channel</span></span>](https://docs.microsoft.com/graph/api/channel-post)
    - [<span data-ttu-id="60297-170">Добавить участника в канал</span><span class="sxs-lookup"><span data-stu-id="60297-170">Add member to channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [<span data-ttu-id="60297-171">Обновить пользователя в канале</span><span class="sxs-lookup"><span data-stu-id="60297-171">Update member in channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [<span data-ttu-id="60297-172">Удалить участника из канала</span><span class="sxs-lookup"><span data-stu-id="60297-172">Remove member from channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-delete)