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
ms.openlocfilehash: 0f2a1f9fc4921ae12092655102d4a442fd653df3
ms.sourcegitcommit: f3b698379eb663202ce127eeaf6c07328c166556
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2019
ms.locfileid: "38077412"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="6f958-103">Управление жизненным циклом частных каналов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6f958-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="6f958-104">Здесь вы найдете рекомендации, которые необходимо выполнить для управления жизненным циклом [личных каналов](private-channels.md) в Организации.</span><span class="sxs-lookup"><span data-stu-id="6f958-104">Here you'll find the guidance you need to manage the life cycle of [private channels](private-channels.md) in your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6f958-105">Если вы используете инструкции PowerShell, описанные в этой статье, для управления личными каналами, необходимо установить и использовать последнюю версию модуля Teams PowerShell из коллекции тестов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f958-105">If you're using the PowerShell steps in this article to manage private channels, you must install and use the latest version of the Teams PowerShell module from the PowerShell Test Gallery.</span></span> <span data-ttu-id="6f958-106">Инструкции, описанные в этой статье, описаны в [статье Установка последней версии модуля PowerShell для Teams из коллекции тестов PowerShell](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery).</span><span class="sxs-lookup"><span data-stu-id="6f958-106">For steps on how to do this, see [Install the latest Teams PowerShell module from the PowerShell Test Gallery](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery).</span></span> <span data-ttu-id="6f958-107">Самая свежая доступная версия модуля PowerShell Teams (в настоящее время — [1.0.2](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.2)) не поддерживает управление личными каналами.</span><span class="sxs-lookup"><span data-stu-id="6f958-107">The latest publicly available version of the Teams PowerShell module (currently [1.0.2](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.2)) doesn't support managing private channels.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="6f958-108">Определение возможности создания личных каналов участниками группы</span><span class="sxs-lookup"><span data-stu-id="6f958-108">Set whether team members can create private channels</span></span>

<span data-ttu-id="6f958-109">Владельцы групп могут включать и отключать возможность создания личных каналов для пользователей в параметрах группы.</span><span class="sxs-lookup"><span data-stu-id="6f958-109">Team owners can turn off or turn on the ability for members to create private channels in team settings.</span></span> <span data-ttu-id="6f958-110">Для этого на вкладке Параметры для команды отключите или включите **параметр** **Разрешить участникам создавать закрытые каналы**.</span><span class="sxs-lookup"><span data-stu-id="6f958-110">To do this, on the **Settings** tab for the team, turn off or turn on **Allow members to create private channels**.</span></span>

<span data-ttu-id="6f958-111">Администраторы могут использовать Graph API для управления тем, могут ли участники создавать закрытые каналы в конкретных командах.</span><span class="sxs-lookup"><span data-stu-id="6f958-111">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="6f958-112">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="6f958-112">Here's an example.</span></span>

```
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a><span data-ttu-id="6f958-113">Настройка возможности создания частных каналов для пользователей в Организации</span><span class="sxs-lookup"><span data-stu-id="6f958-113">Set whether users in your organization can create private channels</span></span>

<span data-ttu-id="6f958-114">Администраторы могут настроить политики с помощью центра администрирования Microsoft Teams или PowerShell, чтобы управлять тем, какие пользователи в организации могут создавать закрытые каналы.</span><span class="sxs-lookup"><span data-stu-id="6f958-114">As an admin, you can set policies by using the Microsoft Teams admin center or PowerShell to control which users in your organization are allowed to create private channels.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="6f958-115">Использование центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6f958-115">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="6f958-116">Используйте политики Teams, чтобы настроить, какие пользователи в организации смогут создавать закрытые каналы.</span><span class="sxs-lookup"><span data-stu-id="6f958-116">Use teams policies to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="6f958-117">Дополнительные сведения можно найти в разделе [Управление политиками Teams в Teams](teams-policies.md).</span><span class="sxs-lookup"><span data-stu-id="6f958-117">To learn more, see [Manage teams policies in Teams](teams-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="6f958-118">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f958-118">Using PowerShell</span></span>

<span data-ttu-id="6f958-119">С помощью **кстеамсчаннелсполици** можно указать, какие пользователи в вашей организации могут создавать закрытые каналы.</span><span class="sxs-lookup"><span data-stu-id="6f958-119">Use **CsTeamsChannelsPolicy** to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="6f958-120">Установите для параметра **алловприватечаннелкреатион** значение **true** , чтобы пользователи, которым назначена политика, могли создавать закрытые каналы.</span><span class="sxs-lookup"><span data-stu-id="6f958-120">Set the **AllowPrivateChannelCreation** parameter to **true** to allow users who are assigned the policy to create private channels.</span></span> <span data-ttu-id="6f958-121">Если задать для параметра **значение false** , возможность создания частных каналов для пользователей, которым назначена политика, будет отключена.</span><span class="sxs-lookup"><span data-stu-id="6f958-121">Setting the parameter to **false** turns off the ability to create private channels for users who are assigned the policy.</span></span>

<span data-ttu-id="6f958-122">Дополнительные сведения можно найти в статье [Создание и кстеамсчаннелсполици](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6f958-122">To learn more, see [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span></span>

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="6f958-123">Создание закрытого канала от имени владельца команды</span><span class="sxs-lookup"><span data-stu-id="6f958-123">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="6f958-124">Администратор может использовать PowerShell или Graph API для создания закрытого канала от имени владельца команды.</span><span class="sxs-lookup"><span data-stu-id="6f958-124">As an admin, you can use PowerShell or Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="6f958-125">Например, это может потребоваться, если ваша организация хотела бы централизовать создание частных каналов.</span><span class="sxs-lookup"><span data-stu-id="6f958-125">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="6f958-126">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f958-126">Using PowerShell</span></span>

```
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName “<Channel_Name>” –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a><span data-ttu-id="6f958-127">Использование Graph API</span><span class="sxs-lookup"><span data-stu-id="6f958-127">Using Graph API</span></span>

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

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="6f958-128">Получение списка всех сообщений личного канала</span><span class="sxs-lookup"><span data-stu-id="6f958-128">Get a list of all private channel messages</span></span>

<span data-ttu-id="6f958-129">Для архивации и аудита может потребоваться просмотреть список всех сообщений и ответов, опубликованных в частном канале.</span><span class="sxs-lookup"><span data-stu-id="6f958-129">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="6f958-130">Ниже показано, как использовать Graph API.</span><span class="sxs-lookup"><span data-stu-id="6f958-130">Here's how to use Graph API to do this.</span></span>

```
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="6f958-131">Поиск URL-адресов SharePoint для всех частных каналов в команде</span><span class="sxs-lookup"><span data-stu-id="6f958-131">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="6f958-132">Если вы собираетесь проводить обнаружение электронных данных или судебных удержаний по файлам в частном канале или собираетесь создавать бизнес-приложение, которое поместит файлы в определенные закрытые каналы, вам будет нужен способ запроса уникальных семейств веб-сайтов SharePoint, созданных для Каждый частный канал.</span><span class="sxs-lookup"><span data-stu-id="6f958-132">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a line-of-business app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="6f958-133">Администратор может использовать команды PowerShell или Graph API для запроса этих URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="6f958-133">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="6f958-134">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f958-134">Using PowerShell</span></span>

1. <span data-ttu-id="6f958-135">Установите [консоль управления SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) и подключитесь к ней с помощью учетной записи администратора.</span><span class="sxs-lookup"><span data-stu-id="6f958-135">Install and connect to the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) with your admin account.</span></span>
2. <span data-ttu-id="6f958-136">Запустите следующую команду, где &lt;Group_id&gt; — идентификатор группы.</span><span class="sxs-lookup"><span data-stu-id="6f958-136">Run the following, where &lt;group_id&gt; is the group Id of the team.</span></span> <span data-ttu-id="6f958-137">(Идентификатор группы можно легко найти в ссылке на команду.)</span><span class="sxs-lookup"><span data-stu-id="6f958-137">(You can easily find the group Id in the link to the team.)</span></span>

    ```
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a><span data-ttu-id="6f958-138">Использование Graph API</span><span class="sxs-lookup"><span data-stu-id="6f958-138">Using Graph API</span></span>

<span data-ttu-id="6f958-139">Эти команды можно выполнить с помощью [проводника диаграмм](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="6f958-139">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="6f958-140">Воспользуйтесь приведенными ниже сведениями, чтобы получить список идентификаторов частных каналов для конкретной команды, где <group_id> является идентификатором группы для группы.</span><span class="sxs-lookup"><span data-stu-id="6f958-140">Use the following to get the list of private channel Ids for a given team, where <group_id> is the group Id of the team.</span></span> <span data-ttu-id="6f958-141">Это потребуется при последующих звонках.</span><span class="sxs-lookup"><span data-stu-id="6f958-141">You'll need this in subsequent calls.</span></span> <span data-ttu-id="6f958-142">(Идентификатор группы можно легко найти в ссылке на команду).</span><span class="sxs-lookup"><span data-stu-id="6f958-142">(You can easily find the group Id in the link to the team).</span></span>

    <span data-ttu-id="6f958-143">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="6f958-143">**Request**</span></span>

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="6f958-144">**Response (Ответ)**</span><span class="sxs-lookup"><span data-stu-id="6f958-144">**Response**</span></span>

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

2. <span data-ttu-id="6f958-145">Для каждого закрытого канала, для которого требуется получить URL-адрес SharePoint, сделайте следующий запрос, &lt;где&gt; channel_id — идентификатор канала.</span><span class="sxs-lookup"><span data-stu-id="6f958-145">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel Id.</span></span>

    <span data-ttu-id="6f958-146">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="6f958-146">**Request**</span></span>

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="6f958-147">**Response (Ответ)**</span><span class="sxs-lookup"><span data-stu-id="6f958-147">**Response**</span></span>

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="6f958-148">Перечисление и обновление ролей владельцев и участников в частном канале</span><span class="sxs-lookup"><span data-stu-id="6f958-148">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="6f958-149">Вам может потребоваться указать владельцев и участников закрытого канала, чтобы решить, нужно ли распространить определенных участников закрытого канала на владельца.</span><span class="sxs-lookup"><span data-stu-id="6f958-149">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="6f958-150">Это может быть вызвано тем, что у вас есть владельцы частных каналов, которые оставили организацию и для личного канала требуется помощь администратора для утверждения прав собственности на канал.</span><span class="sxs-lookup"><span data-stu-id="6f958-150">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="6f958-151">Администратор может использовать команды PowerShell или Graph API для запроса этих URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="6f958-151">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="6f958-152">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f958-152">Using PowerShell</span></span>

1. <span data-ttu-id="6f958-153">Установите и подключитесь к [модулю Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) с учетной записью администратора.</span><span class="sxs-lookup"><span data-stu-id="6f958-153">Install and connect to the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) with your admin account.</span></span>
2. <span data-ttu-id="6f958-154">Запустите следующую команду, где &lt;group_id&gt; — это идентификатор группы, а &lt;channel_id&gt; — идентификатор канала.</span><span class="sxs-lookup"><span data-stu-id="6f958-154">Run the following, where &lt;group_id&gt; is the group Id of the team and &lt;channel_id&gt; is the channel Id.</span></span>

    <span data-ttu-id="6f958-155">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="6f958-155">**Request**</span></span>

    ```
    Get-TeamChannelUser -GroupId <group_id> -MembershipType Private -DisplayName "<channel_name>" 
    ```
    
    <span data-ttu-id="6f958-156">**Response (Ответ)**</span><span class="sxs-lookup"><span data-stu-id="6f958-156">**Response**</span></span>

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

3. <span data-ttu-id="6f958-157">Повышение роли участника до владельца.</span><span class="sxs-lookup"><span data-stu-id="6f958-157">Promote a member to an owner.</span></span>

    ```
    Add-TeamChannelUser -GroupId <group_id> -MembershipType Private -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a><span data-ttu-id="6f958-158">Использование Graph API</span><span class="sxs-lookup"><span data-stu-id="6f958-158">Using Graph API</span></span>

<span data-ttu-id="6f958-159">Эти команды можно выполнить с помощью [проводника диаграмм](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="6f958-159">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="6f958-160">Используйте следующую команду, где &lt;Group_id&gt; — идентификатор группы, а &lt;channel_id&gt; — идентификатор канала.</span><span class="sxs-lookup"><span data-stu-id="6f958-160">Use the following, where &lt;group_id&gt; is the group Id of the team and &lt;channel_id&gt; is the channel Id.</span></span>

    <span data-ttu-id="6f958-161">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="6f958-161">**Request**</span></span>

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="6f958-162">**Response (Ответ)**</span><span class="sxs-lookup"><span data-stu-id="6f958-162">**Response**</span></span>

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
2.  <span data-ttu-id="6f958-163">Используйте указанные ниже действия, чтобы повысить роль участника до владельца, &lt;где&gt;в &lt;предыдущем&gt;вызове &lt;возвращаются&gt; group_id, channel_id и идентификатор.</span><span class="sxs-lookup"><span data-stu-id="6f958-163">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="6f958-164">Обратите &lt;внимание&gt; , &lt;что&gt; идентификатор и UserID, возвращенные из предыдущего звонка, не являются взаимозаменяемыми.</span><span class="sxs-lookup"><span data-stu-id="6f958-164">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="6f958-165">Убедитесь, что вы &lt;используете&gt;ID.</span><span class="sxs-lookup"><span data-stu-id="6f958-165">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="6f958-166">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="6f958-166">**Request**</span></span>

    ```
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="6f958-167">**Response (Ответ)**</span><span class="sxs-lookup"><span data-stu-id="6f958-167">**Response**</span></span>

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

## <a name="teams-powershell-module"></a><span data-ttu-id="6f958-168">Модуль PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="6f958-168">Teams Powershell module</span></span>

### <a name="install-the-latest-teams-powershell-module-from-the-powershell-test-gallery"></a><span data-ttu-id="6f958-169">Установка новейшего модуля PowerShell для Teams из коллекции тестов PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f958-169">Install the latest Teams PowerShell module from the PowerShell Test Gallery</span></span>

<span data-ttu-id="6f958-170">Самая свежая доступная версия модуля PowerShell Teams (в настоящее время — [1.0.2](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.2)) не поддерживает управление личными каналами.</span><span class="sxs-lookup"><span data-stu-id="6f958-170">The latest publicly available version of the Teams PowerShell module (currently [1.0.2](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.2)) doesn't support managing private channels.</span></span> <span data-ttu-id="6f958-171">Выполните указанные ниже действия, чтобы установить последнюю версию модуля PowerShell Teams с поддержкой частных каналов (в настоящее время 1.0.18) из коллекции тестов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f958-171">Use these steps to install the latest version of the Teams PowerShell module with private channel support (currently 1.0.18) from the PowerShell Test Gallery.</span></span>

> [!NOTE]
> <span data-ttu-id="6f958-172">Не устанавливайте модуль PowerShell Teams из коллекции тестов PowerShell рядом с версией модуля из общедоступной галереи PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f958-172">Don't install the Teams PowerShell module from the PowerShell Test Gallery side-by-side with a version of the module from the public PowerShell Gallery.</span></span> <span data-ttu-id="6f958-173">Выполните эти действия, чтобы сначала удалить модуль Teams PowerShell из общедоступной коллекции PowerShell, а затем установить последнюю версию модуля из коллекции тестов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f958-173">Follow these steps to first uninstall the Teams PowerShell module from the public PowerShell Gallery, and then install the latest version of the module from the PowerShell Test Gallery.</span></span>

1. <span data-ttu-id="6f958-174">Закройте все существующие сеансы PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f958-174">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="6f958-175">Начните новый экземпляр модуля Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f958-175">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="6f958-176">Выполните указанные ниже действия, чтобы удалить модуль PowerShell Teams из общедоступной галереи PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f958-176">Run the following to uninstall the Teams PowerShell module from the public PowerShell Gallery:</span></span>

    ```
    Uninstall-Module -Name MicrosoftTeams
    ```

4. <span data-ttu-id="6f958-177">Закройте все существующие сеансы PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f958-177">Close all existing PowerShell sessions.</span></span>
5. <span data-ttu-id="6f958-178">Запустите модуль Windows PowerShell еще раз, а затем выполните указанные ниже действия, чтобы зарегистрировать библиотеку тестов PowerShell в качестве надежного источника.</span><span class="sxs-lookup"><span data-stu-id="6f958-178">Start the Windows PowerShell module again, and then run the following to register the PowerShell Test Gallery as a trusted source:</span></span>

    ```
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. <span data-ttu-id="6f958-179">Выполните указанные ниже действия, чтобы установить последнюю версию модуля PowerShell для Teams из коллекции тестов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f958-179">Run the following to install the latest Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. <span data-ttu-id="6f958-180">Выполните указанные ниже действия, чтобы убедиться в том, что новейшая версия модуля Teams PowerShell из коллекции тестов PowerShell успешно установлена.</span><span class="sxs-lookup"><span data-stu-id="6f958-180">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a><span data-ttu-id="6f958-181">Обновите модуль PowerShell до последней версии из коллекции тестовых команд PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f958-181">Update to the latest version of the Teams PowerShell module from the PowerShell Test Gallery</span></span>

<span data-ttu-id="6f958-182">Если вы уже установили модуль Teams PowerShell из коллекции тестов PowerShell, выполните указанные ниже действия, чтобы обновить его до последней версии.</span><span class="sxs-lookup"><span data-stu-id="6f958-182">If you already installed the Teams PowerShell module from the PowerShell Test Gallery, use the following steps to update to the latest version.</span></span>

1. <span data-ttu-id="6f958-183">Закройте все существующие сеансы PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f958-183">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="6f958-184">Начните новый экземпляр модуля Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f958-184">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="6f958-185">Выполните указанные ниже действия, чтобы обновить текущую установленную версию модуля PowerShell Teams из коллекции тестов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f958-185">Run the following to update the currently installed version of the Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```
    Update-Module -Name MicrosoftTeams -Force
    ```

4. <span data-ttu-id="6f958-186">Выполните указанные ниже действия, чтобы убедиться в том, что новейшая версия модуля Teams PowerShell из коллекции тестов PowerShell успешно установлена.</span><span class="sxs-lookup"><span data-stu-id="6f958-186">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```
    Get-Module -Name MicrosoftTeams
    ```

## <a name="related-topics"></a><span data-ttu-id="6f958-187">См. также</span><span class="sxs-lookup"><span data-stu-id="6f958-187">Related topics</span></span>

- [<span data-ttu-id="6f958-188">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="6f958-188">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="6f958-189">Использование API Microsoft Graph для работы с Teams</span><span class="sxs-lookup"><span data-stu-id="6f958-189">Use the Microsoft Graph API to work with Teams</span></span>](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [<span data-ttu-id="6f958-190">Каналы списка</span><span class="sxs-lookup"><span data-stu-id="6f958-190">List channels</span></span>](https://docs.microsoft.com/graph/api/channel-list)
    - [<span data-ttu-id="6f958-191">Создать канал</span><span class="sxs-lookup"><span data-stu-id="6f958-191">Create channel</span></span>](https://docs.microsoft.com/graph/api/channel-post)
    - [<span data-ttu-id="6f958-192">Добавить участника в канал</span><span class="sxs-lookup"><span data-stu-id="6f958-192">Add member to channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [<span data-ttu-id="6f958-193">Обновить пользователя в канале</span><span class="sxs-lookup"><span data-stu-id="6f958-193">Update member in channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [<span data-ttu-id="6f958-194">Удалить участника из канала</span><span class="sxs-lookup"><span data-stu-id="6f958-194">Remove member from channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-delete)